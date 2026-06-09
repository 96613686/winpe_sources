# [thunk]:ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release`adjustor{16}' (void)

- ea: `0x140010200`
- end: `0x140010209`
- name: `?Release@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release((volatile signed __int32 *)(a1 - 16));
}

```

## disassembly

```asm
0x140010200  sub     rcx, 10h
0x140010204  jmp     ?Release@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ; ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::Release(void)
```
