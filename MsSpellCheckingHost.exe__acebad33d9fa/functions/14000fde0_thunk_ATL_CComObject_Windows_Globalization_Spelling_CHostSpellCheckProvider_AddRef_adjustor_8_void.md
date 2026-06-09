# [thunk]:ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::AddRef`adjustor{8}' (void)

- ea: `0x14000fde0`
- end: `0x14000fde9`
- name: `?AddRef@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000fdb0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::AddRef(__int64 a1)
{
  return ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x14000fde0  sub     rcx, 8
0x14000fde4  jmp     ?AddRef@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@UEAAKXZ; ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::AddRef(void)
```
