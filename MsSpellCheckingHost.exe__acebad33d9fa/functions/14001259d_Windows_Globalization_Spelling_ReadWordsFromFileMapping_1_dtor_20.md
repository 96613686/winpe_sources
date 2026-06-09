# _Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$20

- ea: `0x14001259d`
- end: `0x1400125a9`
- name: `_Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$20`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000878c`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  return std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(
           a2 + 144,
           a2);
}

```

## disassembly

```asm
0x14001259d  lea     rcx, [rdx+90h]
0x1400125a4  jmp     ??1?$_Func_class@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@std@@QEAA@XZ; std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(void)
```
