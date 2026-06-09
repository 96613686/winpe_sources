# _ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$0

- ea: `0x140012478`
- end: `0x140012486`
- name: `_ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14001247f`

## pseudocode

```c
void __fastcall ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 96));
}

```

## disassembly

```asm
0x140012478  mov     rcx, [rdx+60h]
0x14001247f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
