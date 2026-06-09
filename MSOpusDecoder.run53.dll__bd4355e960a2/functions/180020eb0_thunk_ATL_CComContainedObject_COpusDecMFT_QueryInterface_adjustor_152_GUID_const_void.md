# [thunk]:ATL::CComContainedObject<COpusDecMFT>::QueryInterface`adjustor{152}' (_GUID const &,void * *)

- ea: `0x180020eb0`
- end: `0x180020ebc`
- name: `?QueryInterface@?$CComContainedObject@VCOpusDecMFT@@@ATL@@WJI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180020e80`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<COpusDecMFT>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<COpusDecMFT>::QueryInterface(a1 - 152);
}

```

## disassembly

```asm
0x180020eb0  sub     rcx, 98h
0x180020eb7  jmp     ?QueryInterface@?$CComContainedObject@VCOpusDecMFT@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<COpusDecMFT>::QueryInterface(_GUID const &,void * *)
```
