# SPDX-FileCopyrightText: 2020 Friedrich-Alexander University Erlangen-Nürnberg (FAU)
#
# SPDX-License-Identifier: Apache-2.0

FROM golang:1.15 as builder

COPY main.go .

RUN go get -d -v ./...
RUN go build -o fh main.go
RUN pwd

FROM alpine:latest

COPY --from=builder /go/fh fh
