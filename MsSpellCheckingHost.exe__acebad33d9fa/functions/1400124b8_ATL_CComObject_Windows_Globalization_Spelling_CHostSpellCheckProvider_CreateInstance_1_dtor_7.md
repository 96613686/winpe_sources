# _ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$7

- ea: `0x1400124b8`
- end: `0x1400124c4`
- name: `_ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000878c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_Windows::Globalization::Spelling::CHostSpellCheckProvider_::CreateInstance_::_1_::dtor_7(
        __int64 a1,
        __int64 a2)
{
  return std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(
           *(_QWORD *)(a2 + 32),
           a2);
}

```

## disassembly

```asm
0x1400124b8  mov     rcx, [rdx+20h]
0x1400124bf  jmp     ??1?$_Func_class@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@std@@QEAA@XZ; std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(void)
```
