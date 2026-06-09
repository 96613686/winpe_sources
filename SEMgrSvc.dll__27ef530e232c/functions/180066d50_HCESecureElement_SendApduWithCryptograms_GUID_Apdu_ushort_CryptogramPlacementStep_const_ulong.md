# HCESecureElement::SendApduWithCryptograms(_GUID *,_Apdu,ushort,_CryptogramPlacementStep const *,ulong *)

- ea: `0x180066d50`
- end: `0x18006706e`
- name: `?SendApduWithCryptograms@HCESecureElement@@QEAAJPEAU_GUID@@U_Apdu@@GPEBU_CryptogramPlacementStep@@PEAK@Z`
- size: `798`
- prototype: `int __high(struct _GUID *, struct _Apdu, unsigned __int16, const struct _CryptogramPlacementStep *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18006b670`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x180013274`
- `0x1800436c0`
- `0x180047f88`
- `0x1800480dc`
- `0x18004830c`
- `0x180048aac`
- `0x18004bf9c`
- `0x180066d50`
- `0x180068a1c`
- `0x18009d010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient2` at `0x180066dd1`
- `RPCRT4!RpcImpersonateClient2` at `0x180066dd1`
- `RPCRT4!RpcRevertToSelfEx` at `0x180066df6`
- `RPCRT4!RpcRevertToSelfEx` at `0x180066e01`
- `RPCRT4!RpcRevertToSelfEx` at `0x180066df6`
- `RPCRT4!RpcRevertToSelfEx` at `0x180066e01`

## pseudocode

```c

```
