# [thunk]:ATL::CComContainedObject<COpusDecMFT>::Release`adjustor{152}' (void)

- ea: `0x180021c70`
- end: `0x180021c7c`
- name: `?Release@?$CComContainedObject@VCOpusDecMFT@@@ATL@@WJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180021c40`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<COpusDecMFT>::Release(__int64 a1)
{
  return ATL::CComContainedObject<COpusDecMFT>::Release(a1 - 152);
}

```

## disassembly

```asm
0x180021c70  sub     rcx, 98h
0x180021c77  jmp     ?Release@?$CComContainedObject@VCOpusDecMFT@@@ATL@@UEAAKXZ; ATL::CComContainedObject<COpusDecMFT>::Release(void)
```
