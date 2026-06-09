# [thunk]:ATL::CComObject<COpusDecMFT>::Release`adjustor{152}' (void)

- ea: `0x180021d30`
- end: `0x180021d3c`
- name: `?Release@?$CComObject@VCOpusDecMFT@@@ATL@@WJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180021c90`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<COpusDecMFT>::Release(__int64 a1)
{
  return ATL::CComObject<COpusDecMFT>::Release((volatile signed __int32 *)(a1 - 152));
}

```

## disassembly

```asm
0x180021d30  sub     rcx, 98h
0x180021d37  jmp     ?Release@?$CComObject@VCOpusDecMFT@@@ATL@@UEAAKXZ; ATL::CComObject<COpusDecMFT>::Release(void)
```
