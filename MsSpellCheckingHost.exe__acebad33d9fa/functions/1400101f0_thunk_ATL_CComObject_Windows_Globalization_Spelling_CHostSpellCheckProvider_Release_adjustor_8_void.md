# [thunk]:ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release`adjustor{8}' (void)

- ea: `0x1400101f0`
- end: `0x1400101f9`
- name: `?Release@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010160`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release(__int64 a1)
{
  return ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x1400101f0  sub     rcx, 8
0x1400101f4  jmp     ?Release@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ; ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release(void)
```
