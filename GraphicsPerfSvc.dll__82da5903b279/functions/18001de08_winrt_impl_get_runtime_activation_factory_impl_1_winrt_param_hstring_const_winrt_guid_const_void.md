# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001de08`
- end: `0x18001e07a`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `626`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001db08`

## callees

- `0x180003ab0`
- `0x1800048f5`
- `0x180004931`
- `0x180004a90`
- `0x180004b4d`
- `0x180004b59`
- `0x180004b95`
- `0x180004bad`
- `0x18001c158`
- `0x18001c954`
- `0x18001cecc`
- `0x18001de08`
- `0x180021860`
- `0x18002255c`
- `0x180022a18`
- `0x180031010`

## string_xrefs

- `0x18001de6c`: `combase.dll`
- `0x18001dfd3`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r8
  __int64 v15; // r14
  unsigned __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 last_trivial_2; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  const WCHAR *v23; // rax
  HMODULE v24; // rbx
  FARPROC v25; // rax
  __int64 v26; // rax
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-38h] BYREF
  _BYTE Src[16]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v31; // [rsp+50h] [rbp-20h]
  __int64 v32; // [rsp+58h] [rbp-18h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
    ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
    if ( ActivationFactory_0 == -2147221008 )
    {
      Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
      ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
      if ( !ProcAddress )
      {
        *a1 = -2147221008;
        return a1;
      }
      v28 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v28);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(Src, a2);
      while ( 1 )
      {
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        v15 = v12;
        if ( !v13 )
          break;
        v16 = v13 - 1;
        if ( v13 - 1 >= v14 )
          v16 = v14;
        v17 = v12 + 2 + 2 * v16;
        last_trivial_2 = _std_find_last_trivial_2(v12, v17, 46);
        if ( last_trivial_2 == v17 )
          break;
        v19 = (last_trivial_2 - v15) >> 1;
        if ( v19 == -1 )
          break;
        std::wstring::resize(Src, v19);
        if ( (unsigned __int64)(v32 - v31) < 4 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            Src,
            4);
        }
        else
        {
          v31 += 4;
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
          *(_QWORD *)(v20 + 2 * v21) = 0x6C006C0064002ELL;
          *(_WORD *)(v20 + 2 * v22) = 0;
        }
        v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        v24 = LoadLibraryExW_0(v23, 0, 0x1000u);
        std::wstring::resize(Src, v31 - 4);
        if ( v24 )
        {
          v25 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
          if ( v25 )
          {
            v28 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v25)(*a2, &v28) )
            {
              v26 = v28;
              v28 = 0;
              *a4 = v26;
              *a1 = 0;
              goto LABEL_26;
            }
            if ( v28 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
          }
          WINRT_IMPL_FreeLibrary(v24);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_26:
      std::wstring::_Tidy_deallocate(Src);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001de08  push    rbp
0x18001de0a  push    rbx
0x18001de0b  push    rsi
0x18001de0c  push    rdi
0x18001de0d  push    r12
0x18001de0f  push    r14
0x18001de11  push    r15
0x18001de13  mov     rbp, rsp
0x18001de16  sub     rsp, 70h
0x18001de1a  mov     rax, cs:__security_cookie
0x18001de21  xor     rax, rsp
0x18001de24  mov     [rbp+var_10], rax
0x18001de28  mov     r15, r9
0x18001de2b  mov     rbx, r8
0x18001de2e  mov     r12, rdx
0x18001de31  mov     rsi, rcx
0x18001de34  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001de3b  mov     r8, r9
0x18001de3e  mov     rdx, rbx
0x18001de41  mov     rcx, [r12]
0x18001de45  test    rax, rax
0x18001de48  jz      short loc_18001DE56
0x18001de4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de4f  mov     [rsi], eax
0x18001de51  jmp     loc_18001E05C
0x18001de56  call    RoGetActivationFactory_0
0x18001de5b  mov     edi, eax
0x18001de5d  cmp     eax, 800401F0h
0x18001de62  jnz     short loc_18001DEB9
0x18001de64  xor     edx, edx; hFile
0x18001de66  mov     r8d, 1000h; dwFlags
0x18001de6c  lea     rcx, LibFileName; "combase.dll"
0x18001de73  call    LoadLibraryExW_0
0x18001de78  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001de7f  mov     rcx, rax; hModule
0x18001de82  call    WINRT_IMPL_GetProcAddress
0x18001de87  test    rax, rax
0x18001de8a  jnz     short loc_18001DE97
0x18001de8c  mov     dword ptr [rsi], 800401F0h
0x18001de92  jmp     loc_18001E05C
0x18001de97  mov     [rbp+var_40], 0
0x18001de9f  lea     rcx, [rbp+var_40]
0x18001dea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dea8  mov     r8, r15
0x18001deab  mov     rdx, rbx
0x18001deae  mov     rcx, [r12]
0x18001deb2  call    RoGetActivationFactory_0
0x18001deb7  mov     edi, eax
0x18001deb9  test    edi, edi
0x18001debb  jnz     short loc_18001DEC4
0x18001debd  mov     [rsi], edi
0x18001debf  jmp     loc_18001E05C
0x18001dec4  mov     [rbp+pperrinfo], 0
0x18001decc  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001ded0  xor     ecx, ecx; dwReserved
0x18001ded2  call    GetErrorInfo_0
0x18001ded7  mov     rdx, r12
0x18001deda  lea     rcx, [rbp+Src]
0x18001dede  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18001dee3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001dee7  mov     rdx, [rbp+var_20]
0x18001deeb  lea     rcx, [rbp+Src]
0x18001deef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001def4  mov     r14, rax
0x18001def7  test    rdx, rdx
0x18001defa  jz      loc_18001E036
0x18001df00  lea     rcx, [rdx-1]
0x18001df04  cmp     rcx, r8
0x18001df07  cmovnb  rcx, r8
0x18001df0b  add     rax, 2
0x18001df0f  lea     rbx, [rax+rcx*2]
0x18001df13  mov     r8d, 2Eh ; '.'
0x18001df19  mov     rdx, rbx
0x18001df1c  mov     rcx, r14
0x18001df1f  call    __std_find_last_trivial_2
0x18001df24  cmp     rax, rbx
0x18001df27  jz      loc_18001E036
0x18001df2d  sub     rax, r14
0x18001df30  sar     rax, 1
0x18001df33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001df37  jz      loc_18001E036
0x18001df3d  mov     rdx, rax
0x18001df40  lea     rcx, [rbp+Src]
0x18001df44  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001df49  mov     r8, [rbp+var_20]
0x18001df4d  mov     rax, [rbp+var_18]
0x18001df51  sub     rax, r8
0x18001df54  mov     ecx, 4
0x18001df59  cmp     rax, rcx
0x18001df5c  jb      short loc_18001DF85
0x18001df5e  lea     rdx, [r8+4]
0x18001df62  mov     [rbp+var_20], rdx
0x18001df66  lea     rcx, [rbp+Src]
0x18001df6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001df6f  mov     rcx, 6C006C0064002Eh
0x18001df79  mov     [rax+r8*2], rcx
0x18001df7d  xor     ecx, ecx
0x18001df7f  mov     [rax+rdx*2], cx
0x18001df83  jmp     short loc_18001DF96
0x18001df85  mov     [rsp+70h+var_50], rcx; __int64
0x18001df8a  mov     rdx, rcx
0x18001df8d  lea     rcx, [rbp+Src]; Src
0x18001df91  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001df96  lea     rcx, [rbp+Src]
0x18001df9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001df9f  mov     rcx, rax; lpLibFileName
0x18001dfa2  xor     edx, edx; hFile
0x18001dfa4  mov     r8d, 1000h; dwFlags
0x18001dfaa  call    LoadLibraryExW_0
0x18001dfaf  mov     rbx, rax
0x18001dfb2  mov     rdx, [rbp+var_20]
0x18001dfb6  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001dfba  lea     rcx, [rbp+Src]
0x18001dfbe  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001dfc3  test    rbx, rbx
0x18001dfc6  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001dfcd  jz      loc_18001DEE7
0x18001dfd3  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18001dfda  mov     rcx, rbx; hModule
0x18001dfdd  call    WINRT_IMPL_GetProcAddress
0x18001dfe2  test    rax, rax
0x18001dfe5  jnz     short loc_18001DFF4
0x18001dfe7  mov     rcx, rbx; hLibModule
0x18001dfea  call    WINRT_IMPL_FreeLibrary
0x18001dfef  jmp     loc_18001DEE3
0x18001dff4  mov     [rbp+var_40], 0
0x18001dffc  lea     rdx, [rbp+var_40]
0x18001e000  mov     rcx, [r12]
0x18001e004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e009  test    eax, eax
0x18001e00b  jz      short loc_18001E01F
0x18001e00d  cmp     [rbp+var_40], 0
0x18001e012  jz      short loc_18001DFE7
0x18001e014  lea     rcx, [rbp+var_40]
0x18001e018  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e01d  jmp     short loc_18001DFE7
0x18001e01f  mov     rax, [rbp+var_40]
0x18001e023  mov     [rbp+var_40], 0
0x18001e02b  mov     [r15], rax
0x18001e02e  mov     dword ptr [rsi], 0
0x18001e034  jmp     short loc_18001E043
0x18001e036  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001e03a  xor     ecx, ecx; dwReserved
0x18001e03c  call    SetErrorInfo_0
0x18001e041  mov     [rsi], edi
0x18001e043  lea     rcx, [rbp+Src]
0x18001e047  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e04c  cmp     [rbp+pperrinfo], 0
0x18001e051  jz      short loc_18001E05C
0x18001e053  lea     rcx, [rbp+pperrinfo]
0x18001e057  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e05c  mov     rax, rsi
0x18001e05f  mov     rcx, [rbp+var_10]
0x18001e063  xor     rcx, rsp; StackCookie
0x18001e066  call    __security_check_cookie
0x18001e06b  add     rsp, 70h
0x18001e06f  pop     r15
0x18001e071  pop     r14
0x18001e073  pop     r12
0x18001e075  pop     rdi
0x18001e076  pop     rsi
0x18001e077  pop     rbx
0x18001e078  pop     rbp
0x18001e079  retn
```
