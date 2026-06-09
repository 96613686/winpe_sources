# [thunk]:ATL::CComObject<COpusDecMFT>::QueryInterface`adjustor{152}' (_GUID const &,void * *)

- ea: `0x180020ef0`
- end: `0x180020efc`
- name: `?QueryInterface@?$CComObject@VCOpusDecMFT@@@ATL@@WJI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180020ed0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<COpusDecMFT>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<COpusDecMFT>::QueryInterface((char *)(a1 - 152), a2, a3);
}

```

## disassembly

```asm
0x180020ef0  sub     rcx, 98h
0x180020ef7  jmp     ?QueryInterface@?$CComObject@VCOpusDecMFT@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<COpusDecMFT>::QueryInterface(_GUID const &,void * *)
```
