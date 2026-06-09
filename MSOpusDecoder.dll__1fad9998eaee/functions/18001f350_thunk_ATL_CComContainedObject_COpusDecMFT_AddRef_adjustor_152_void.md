# [thunk]:ATL::CComContainedObject<COpusDecMFT>::AddRef`adjustor{152}' (void)

- ea: `0x18001f350`
- end: `0x18001f35c`
- name: `?AddRef@?$CComContainedObject@VCOpusDecMFT@@@ATL@@WJI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001f320`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<COpusDecMFT>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<COpusDecMFT>::AddRef(a1 - 152);
}

```

## disassembly

```asm
0x18001f350  sub     rcx, 98h
0x18001f357  jmp     ?AddRef@?$CComContainedObject@VCOpusDecMFT@@@ATL@@UEAAKXZ; ATL::CComContainedObject<COpusDecMFT>::AddRef(void)
```
