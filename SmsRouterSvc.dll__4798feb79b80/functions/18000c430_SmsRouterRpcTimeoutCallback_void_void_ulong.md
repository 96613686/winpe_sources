# SmsRouterRpcTimeoutCallback(void *,void *,ulong)

- ea: `0x18000c430`
- end: `0x18000c49a`
- name: `?SmsRouterRpcTimeoutCallback@@YAXPEAX0K@Z`
- size: `106`
- prototype: `void __fastcall(void *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000bcf8`
- `0x18000c430`
- `0x18000cd64`
- `0x180051628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c48e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c48e`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x18000c450`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x18000c450`

## string_xrefs

- `0x18000c45a`: `Initiating service stop for SmsRouter due to RPC timeout.`

## pseudocode

```c

```
