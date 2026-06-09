# [thunk]:ATL::CComObject<COpusDecMFT>::AddRef`adjustor{152}' (void)

- ea: `0x18001f3b0`
- end: `0x18001f3bc`
- name: `?AddRef@?$CComObject@VCOpusDecMFT@@@ATL@@WJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001f370`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<COpusDecMFT>::AddRef(__int64 a1)
{
  return ATL::CComObject<COpusDecMFT>::AddRef(a1 - 152);
}

```

## disassembly

```asm
0x18001f3b0  sub     rcx, 98h
0x18001f3b7  jmp     ?AddRef@?$CComObject@VCOpusDecMFT@@@ATL@@UEAAKXZ; ATL::CComObject<COpusDecMFT>::AddRef(void)
```
