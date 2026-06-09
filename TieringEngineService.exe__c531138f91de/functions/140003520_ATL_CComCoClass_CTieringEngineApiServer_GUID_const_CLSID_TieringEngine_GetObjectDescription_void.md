# ATL::CComCoClass<CTieringEngineApiServer,&_GUID const CLSID_TieringEngine>::GetObjectDescription(void)

- ea: `0x140003520`
- end: `0x140003523`
- name: `?GetObjectDescription@?$CComCoClass@VCTieringEngineApiServer@@$1?CLSID_TieringEngine@@3U_GUID@@B@ATL@@SAPEBGXZ`
- size: `3`
- prototype: `__int64 __fastcall(struct _exception *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001a60`

## pseudocode

```c
__int64 __fastcall ATL::CComCoClass<CTieringEngineApiServer,&_GUID const CLSID_TieringEngine>::GetObjectDescription(
        struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x140003520  xor     eax, eax
0x140003522  retn
```
