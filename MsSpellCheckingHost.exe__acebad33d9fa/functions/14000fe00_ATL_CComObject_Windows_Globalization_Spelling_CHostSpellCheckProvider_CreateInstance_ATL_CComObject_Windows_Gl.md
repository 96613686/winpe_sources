# ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::CreateInstance(ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider> * *)

- ea: `0x14000fe00`
- end: `0x14000fee3`
- name: `?CreateInstance@?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@SAJPEAPEAV12@@Z`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000fef0`

## callees

- `0x1400014fc`
- `0x14000fe00`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::CreateInstance(
        _QWORD *a1)
{
  _QWORD *v1; // rsi
  unsigned int v3; // r14d
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rax
  _QWORD *v8; // [rsp+60h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x60u);
    v5 = v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 6) = 0;
      v4[6] = 0;
      v4[7] = 0;
      v6 = v4 + 8;
      *v6 = std::_Func_impl<std::_Callable_fun<std::map<std::wstring const,std::wstring> (*const)(__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool),0>,std::allocator<std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
      v6[1] = Windows::Globalization::Spelling::UserDictionariesWrapper::ReadWordsFromFileMappingInternal;
      v6[3] = v6;
      *v5 = &ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `ISpellCheckProvider'};
      v5[1] = &ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IComprehensiveSpellCheckProvider'};
      v5[2] = &ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IFileWordlistInitializer'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v8 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v8;
  }
  if ( v5 )
    v3 = 0;
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x14000fe00  mov     [rsp+arg_18], rbx
0x14000fe05  mov     [rsp+arg_0], rcx
0x14000fe0a  push    rsi
0x14000fe0b  push    rdi
0x14000fe0c  push    r14
0x14000fe0e  sub     rsp, 30h
0x14000fe12  mov     rsi, rcx
0x14000fe15  xor     ebx, ebx
0x14000fe17  test    rcx, rcx
0x14000fe1a  jnz     short loc_14000FE26
0x14000fe1c  mov     eax, 80004003h
0x14000fe21  jmp     loc_14000FED5
0x14000fe26  mov     [rcx], rbx
0x14000fe29  mov     r14d, 8007000Eh
0x14000fe2f  mov     [rsp+48h+arg_8], r14d
0x14000fe34  mov     [rsp+48h+arg_10], rbx
0x14000fe39  mov     ecx, 60h ; '`'; Size
0x14000fe3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fe43  mov     rdi, rax
0x14000fe46  mov     [rsp+48h+arg_10], rax
0x14000fe4b  test    rax, rax
0x14000fe4e  jz      short loc_14000FEAD
0x14000fe50  mov     [rax+18h], ebx
0x14000fe53  mov     [rax+30h], rbx
0x14000fe57  mov     [rax+38h], rbx
0x14000fe5b  add     rax, 40h ; '@'
0x14000fe5f  lea     rcx, ??_7?$_Func_impl@U?$_Callable_fun@Q6A?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_N@Z$0A@@std@@V?$allocator@V?$_Func_class@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@std@@@2@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U62@U62@U62@U62@@std@@6B@; const std::_Func_impl<std::_Callable_fun<std::map<std::wstring const,std::wstring> (*const)(__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool),0>,std::allocator<std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14000fe66  mov     [rax], rcx
0x14000fe69  lea     rcx, ?ReadWordsFromFileMappingInternal@UserDictionariesWrapper@Spelling@Globalization@Windows@@SA?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_N@Z; Windows::Globalization::Spelling::UserDictionariesWrapper::ReadWordsFromFileMappingInternal(__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool)
0x14000fe70  mov     [rax+8], rcx
0x14000fe74  mov     [rax+18h], rax
0x14000fe78  lea     rax, ??_7?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@6BISpellCheckProvider@@@; const ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `ISpellCheckProvider'}
0x14000fe7f  mov     [rdi], rax
0x14000fe82  lea     rax, ??_7?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@6BIComprehensiveSpellCheckProvider@@@; const ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IComprehensiveSpellCheckProvider'}
0x14000fe89  mov     [rdi+8], rax
0x14000fe8d  lea     rax, ??_7?$CComObject@VCHostSpellCheckProvider@Spelling@Globalization@Windows@@@ATL@@6BIFileWordlistInitializer@@@; const ATL::CComObject<Windows::Globalization::Spelling::CHostSpellCheckProvider>::`vftable'{for `IFileWordlistInitializer'}
0x14000fe94  mov     [rdi+10h], rax
0x14000fe98  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000fe9f  mov     rax, [rcx]
0x14000fea2  mov     rax, [rax+8]
0x14000fea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000feab  jmp     short loc_14000FEB0
0x14000fead  mov     rdi, rbx
0x14000feb0  mov     [rsp+48h+arg_10], rdi
0x14000feb5  jmp     short loc_14000FEC8
0x14000feb7  xor     ebx, ebx
0x14000feb9  mov     rsi, [rsp+48h+arg_0]
0x14000febe  mov     r14d, [rsp+48h+arg_8]
0x14000fec3  mov     rdi, [rsp+48h+arg_10]
0x14000fec8  test    rdi, rdi
0x14000fecb  cmovnz  r14d, ebx
0x14000fecf  mov     [rsi], rdi
0x14000fed2  mov     eax, r14d
0x14000fed5  mov     rbx, [rsp+48h+arg_18]
0x14000feda  add     rsp, 30h
0x14000fede  pop     r14
0x14000fee0  pop     rdi
0x14000fee1  pop     rsi
0x14000fee2  retn
```
