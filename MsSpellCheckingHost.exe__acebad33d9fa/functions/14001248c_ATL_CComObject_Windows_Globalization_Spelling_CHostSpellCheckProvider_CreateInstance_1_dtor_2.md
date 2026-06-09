# _ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$2

- ea: `0x14001248c`
- end: `0x14001249c`
- name: `_ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$2`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400085f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<ISpellCheckProvider>::~CComPtr<ISpellCheckProvider>((__int64 *)(*(_QWORD *)(a2 + 96) + 48LL));
}

```

## disassembly

```asm
0x14001248c  mov     rcx, [rdx+60h]
0x140012493  add     rcx, 30h ; '0'
0x140012497  jmp     ??1?$CComPtr@UISpellCheckProvider@@@ATL@@QEAA@XZ; ATL::CComPtr<ISpellCheckProvider>::~CComPtr<ISpellCheckProvider>(void)
```
