# ?_Move@?$_Func_impl@U?$_Callable_fun@Q6A?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_N@Z$0A@@std@@V?$allocator@V?$_Func_class@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@std@@@2@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U62@U62@U62@U62@@std@@UEAAPEAV?$_Func_base@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@2@PEAX@Z

- ea: `0x14000e9e0`
- end: `0x14000ea1f`
- name: `?_Move@?$_Func_impl@U?$_Callable_fun@Q6A?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_N@Z$0A@@std@@V?$allocator@V?$_Func_class@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@std@@@2@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U62@U62@U62@U62@@std@@UEAAPEAV?$_Func_base@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@2@PEAX@Z`
- size: `63`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400014fc`
- `0x140001758`
- `0x14000e9e0`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl<std::_Callable_fun<std::map<std::wstring const,std::wstring> (*const)(__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool),0>,std::allocator<std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = std::_Func_impl<std::_Callable_fun<std::map<std::wstring const,std::wstring> (*const)(__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool),0>,std::allocator<std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x14000e9e0  push    rbx
0x14000e9e2  sub     rsp, 20h
0x14000e9e6  mov     rbx, rcx
0x14000e9e9  test    rdx, rdx
0x14000e9ec  jnz     short loc_14000E9FE
0x14000e9ee  lea     ecx, [rdx+18h]; Size
0x14000e9f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e9f6  mov     rdx, rax
0x14000e9f9  test    rax, rax
0x14000e9fc  jz      short loc_14000EA19
0x14000e9fe  lea     rax, ??_7?$_Func_impl@U?$_Callable_fun@Q6A?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_N@Z$0A@@std@@V?$allocator@V?$_Func_class@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@std@@@2@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U62@U62@U62@U62@@std@@6B@; const std::_Func_impl<std::_Callable_fun<std::map<std::wstring const,std::wstring> (*const)(__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool),0>,std::allocator<std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14000ea05  mov     [rdx], rax
0x14000ea08  mov     rax, [rbx+8]
0x14000ea0c  mov     [rdx+8], rax
0x14000ea10  mov     rax, rdx
0x14000ea13  add     rsp, 20h
0x14000ea17  pop     rbx
0x14000ea18  retn
0x14000ea19  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
