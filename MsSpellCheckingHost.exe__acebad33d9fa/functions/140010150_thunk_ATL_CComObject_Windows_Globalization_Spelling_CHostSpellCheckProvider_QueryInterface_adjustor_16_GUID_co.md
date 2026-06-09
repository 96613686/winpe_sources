# [thunk]:ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x140010150`
- end: `0x140010159`
- name: `?QueryInterface@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010120`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::QueryInterface(
           (char *)(a1 - 16),
           a2,
           a3);
}

```

## disassembly

```asm
0x140010150  sub     rcx, 10h
0x140010154  jmp     ?QueryInterface@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::QueryInterface(_GUID const &,void * *)
```
