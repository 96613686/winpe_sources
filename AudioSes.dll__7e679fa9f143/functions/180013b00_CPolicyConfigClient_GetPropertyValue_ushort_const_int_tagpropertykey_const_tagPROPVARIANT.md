# CPolicyConfigClient::GetPropertyValue(ushort const *,int,_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180013b00`
- end: `0x180013c7d`
- name: `?GetPropertyValue@CPolicyConfigClient@@UEAAJPEBGHAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(CPolicyConfigClient *__hidden this, const unsigned __int16 *, int, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cef50`

## callees

- `0x180010a90`
- `0x180013b00`
- `0x180013c84`
- `0x180015174`
- `0x180078c9c`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180013b71`
- `RPCRT4!RpcStringFreeW` at `0x180013b71`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013b65`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013b65`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013b51`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013b51`
- `RPCRT4!RpcBindingFree` at `0x180013bc9`
- `RPCRT4!RpcBindingFree` at `0x180013c0d`
- `RPCRT4!RpcBindingFree` at `0x180013bc9`
- `RPCRT4!RpcBindingFree` at `0x180013c0d`

## string_xrefs

- `0x180013be8`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`

## pseudocode

```c

```
