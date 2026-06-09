# AudioServerGetMixFormat_RPC(ushort const *,VadServerSettings *,tWAVEFORMATEX * *)

- ea: `0x180013d40`
- end: `0x180013ed4`
- name: `?AudioServerGetMixFormat_RPC@@YAJPEBGPEAUVadServerSettings@@PEAPEAUtWAVEFORMATEX@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct VadServerSettings *, struct tWAVEFORMATEX **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015570`
- `0x1800fd360`
- `0x180105920`

## callees

- `0x180010a90`
- `0x180011e7c`
- `0x180013d40`
- `0x180015174`
- `0x18006ee24`
- `0x180078c9c`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180013dab`
- `RPCRT4!RpcStringFreeW` at `0x180013dab`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013d9f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013d9f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013d8b`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013d8b`
- `RPCRT4!RpcBindingFree` at `0x180013e2a`
- `RPCRT4!RpcBindingFree` at `0x180013e2a`

## pseudocode

```c

```
