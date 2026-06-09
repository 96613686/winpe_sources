# _ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$3

- ea: `0x1400124a2`
- end: `0x1400124b2`
- name: `_ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400085f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<ISpellCheckProvider>::~CComPtr<ISpellCheckProvider>((__int64 *)(*(_QWORD *)(a2 + 96) + 56LL));
}

```

## disassembly

```asm
0x1400124a2  mov     rcx, [rdx+60h]
0x1400124a9  add     rcx, 38h ; '8'
0x1400124ad  jmp     ??1?$CComPtr@UISpellCheckProvider@@@ATL@@QEAA@XZ; ATL::CComPtr<ISpellCheckProvider>::~CComPtr<ISpellCheckProvider>(void)
```
