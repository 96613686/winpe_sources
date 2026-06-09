# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180008f84`
- end: `0x180009261`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `733`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008c80`
- `0x180010f38`
- `0x180015a3c`

## callees

- `0x180002020`
- `0x180002c2c`
- `0x180002c44`
- `0x180003350`
- `0x180003441`
- `0x180003465`
- `0x180003471`
- `0x18000347d`
- `0x18000750c`
- `0x180007668`
- `0x180008008`
- `0x1800084d8`
- `0x180008f84`
- `0x18000f0d0`
- `0x18000ff2c`
- `0x180018010`

## string_xrefs

- `0x180008fe9`: `combase.dll`
- `0x18000915b`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
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
  bool v26; // zf
  unsigned int (__fastcall ***v28)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *Src[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-28h]
  unsigned __int64 v32; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
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
      ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v28);
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
        if ( v32 - v31 < 4 )
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
            if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v25)(
                    *a2,
                    &v28)
              && !(**v28)(v28, a3, a4) )
            {
              *a1 = 0;
              if ( v28 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
              if ( v32 > 7 )
                std::_Deallocate<16>(Src[0], 2 * v32 + 2);
              v31 = 0;
              LOWORD(Src[0]) = 0;
              v26 = pperrinfo == 0;
              goto LABEL_33;
            }
            if ( v28 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
          }
          WINRT_IMPL_FreeLibrary(v24);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
      if ( v32 > 7 )
        std::_Deallocate<16>(Src[0], 2 * v32 + 2);
      v31 = 0;
      LOWORD(Src[0]) = 0;
      v26 = pperrinfo == 0;
LABEL_33:
      v32 = 7;
      if ( !v26 )
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
0x180008f84  push    rbp
0x180008f86  push    rbx
0x180008f87  push    rsi
0x180008f88  push    rdi
0x180008f89  push    r12
0x180008f8b  push    r13
0x180008f8d  push    r14
0x180008f8f  push    r15
0x180008f91  mov     rbp, rsp
0x180008f94  sub     rsp, 78h
0x180008f98  mov     rax, cs:__security_cookie
0x180008f9f  xor     rax, rsp
0x180008fa2  mov     [rbp+var_18], rax
0x180008fa6  mov     r13, r9
0x180008fa9  mov     r12, r8
0x180008fac  mov     r15, rdx
0x180008faf  mov     rsi, rcx
0x180008fb2  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180008fb9  mov     r8, r9
0x180008fbc  mov     rdx, r12
0x180008fbf  mov     rcx, [r15]
0x180008fc2  test    rax, rax
0x180008fc5  jz      short loc_180008FD3
0x180008fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fcc  mov     [rsi], eax
0x180008fce  jmp     loc_180009241
0x180008fd3  call    RoGetActivationFactory_0
0x180008fd8  mov     edi, eax
0x180008fda  cmp     eax, 800401F0h
0x180008fdf  jnz     short loc_180009035
0x180008fe1  xor     edx, edx; hFile
0x180008fe3  mov     r8d, 1000h; dwFlags
0x180008fe9  lea     rcx, LibFileName; "combase.dll"
0x180008ff0  call    LoadLibraryExW_0
0x180008ff5  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x180008ffc  mov     rcx, rax; hModule
0x180008fff  call    WINRT_IMPL_GetProcAddress
0x180009004  test    rax, rax
0x180009007  jnz     short loc_180009014
0x180009009  mov     dword ptr [rsi], 800401F0h
0x18000900f  jmp     loc_180009241
0x180009014  mov     [rbp+var_48], 0
0x18000901c  lea     rcx, [rbp+var_48]
0x180009020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009025  mov     r8, r13
0x180009028  mov     rdx, r12
0x18000902b  mov     rcx, [r15]
0x18000902e  call    RoGetActivationFactory_0
0x180009033  mov     edi, eax
0x180009035  test    edi, edi
0x180009037  jnz     short loc_180009040
0x180009039  mov     [rsi], edi
0x18000903b  jmp     loc_180009241
0x180009040  mov     [rbp+pperrinfo], 0
0x180009048  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000904c  xor     ecx, ecx; dwReserved
0x18000904e  call    GetErrorInfo_0
0x180009053  mov     rdx, r15
0x180009056  lea     rcx, [rbp+Src]
0x18000905a  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18000905f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009063  mov     rdx, [rbp+var_28]
0x180009067  lea     rcx, [rbp+Src]
0x18000906b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180009070  mov     r14, rax
0x180009073  test    rdx, rdx
0x180009076  jz      loc_1800091F4
0x18000907c  lea     rcx, [rdx-1]
0x180009080  cmp     rcx, r8
0x180009083  cmovnb  rcx, r8
0x180009087  add     rax, 2
0x18000908b  lea     rbx, [rax+rcx*2]
0x18000908f  mov     r8d, 2Eh ; '.'
0x180009095  mov     rdx, rbx
0x180009098  mov     rcx, r14
0x18000909b  call    __std_find_last_trivial_2
0x1800090a0  cmp     rax, rbx
0x1800090a3  jz      loc_1800091F4
0x1800090a9  sub     rax, r14
0x1800090ac  sar     rax, 1
0x1800090af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800090b3  jz      loc_1800091F4
0x1800090b9  mov     rdx, rax
0x1800090bc  lea     rcx, [rbp+Src]
0x1800090c0  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800090c5  mov     r8, [rbp+var_28]
0x1800090c9  mov     rax, [rbp+var_20]
0x1800090cd  sub     rax, r8
0x1800090d0  mov     ecx, 4
0x1800090d5  cmp     rax, rcx
0x1800090d8  jb      short loc_180009103
0x1800090da  lea     rdx, [r8+4]
0x1800090de  mov     [rbp+var_28], rdx
0x1800090e2  lea     rcx, [rbp+Src]
0x1800090e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800090eb  mov     rcx, 6C006C0064002Eh
0x1800090f5  mov     [rax+r8*2], rcx
0x1800090f9  xor     r14d, r14d
0x1800090fc  mov     [rax+rdx*2], r14w
0x180009101  jmp     short loc_18000911E
0x180009103  mov     [rsp+78h+var_58], rcx; __int64
0x180009108  lea     r9, aDll; ".dll"
0x18000910f  mov     rdx, rcx
0x180009112  lea     rcx, [rbp+Src]; Src
0x180009116  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18000911b  xor     r14d, r14d
0x18000911e  lea     rcx, [rbp+Src]
0x180009122  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180009127  mov     rcx, rax; lpLibFileName
0x18000912a  xor     edx, edx; hFile
0x18000912c  mov     r8d, 1000h; dwFlags
0x180009132  call    LoadLibraryExW_0
0x180009137  mov     rbx, rax
0x18000913a  mov     rdx, [rbp+var_28]
0x18000913e  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180009142  lea     rcx, [rbp+Src]
0x180009146  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000914b  test    rbx, rbx
0x18000914e  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180009155  jz      loc_180009063
0x18000915b  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x180009162  mov     rcx, rbx; hModule
0x180009165  call    WINRT_IMPL_GetProcAddress
0x18000916a  test    rax, rax
0x18000916d  jz      short loc_1800091AB
0x18000916f  mov     [rbp+var_48], r14
0x180009173  lea     rdx, [rbp+var_48]
0x180009177  mov     rcx, [r15]
0x18000917a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000917f  test    eax, eax
0x180009181  jnz     short loc_18000919C
0x180009183  mov     rcx, [rbp+var_48]
0x180009187  mov     rax, [rcx]
0x18000918a  mov     r8, r13
0x18000918d  mov     rdx, r12
0x180009190  mov     rax, [rax]
0x180009193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009198  test    eax, eax
0x18000919a  jz      short loc_1800091B8
0x18000919c  cmp     [rbp+var_48], r14
0x1800091a0  jz      short loc_1800091AB
0x1800091a2  lea     rcx, [rbp+var_48]
0x1800091a6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800091ab  mov     rcx, rbx; hLibModule
0x1800091ae  call    WINRT_IMPL_FreeLibrary
0x1800091b3  jmp     loc_18000905F
0x1800091b8  mov     [rsi], r14d
0x1800091bb  cmp     [rbp+var_48], r14
0x1800091bf  jz      short loc_1800091CA
0x1800091c1  lea     rcx, [rbp+var_48]
0x1800091c5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800091ca  mov     rdx, [rbp+var_20]
0x1800091ce  cmp     rdx, 7
0x1800091d2  jbe     short loc_1800091E5
0x1800091d4  lea     rdx, ds:2[rdx*2]
0x1800091dc  mov     rcx, [rbp+Src]
0x1800091e0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800091e5  mov     [rbp+var_28], r14
0x1800091e9  mov     word ptr [rbp+Src], r14w
0x1800091ee  cmp     [rbp+pperrinfo], r14
0x1800091f2  jmp     short loc_18000922E
0x1800091f4  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1800091f8  xor     ecx, ecx; dwReserved
0x1800091fa  call    SetErrorInfo_0
0x1800091ff  mov     [rsi], edi
0x180009201  mov     rdx, [rbp+var_20]
0x180009205  cmp     rdx, 7
0x180009209  jbe     short loc_18000921C
0x18000920b  lea     rdx, ds:2[rdx*2]
0x180009213  mov     rcx, [rbp+Src]
0x180009217  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000921c  mov     [rbp+var_28], 0
0x180009224  xor     eax, eax
0x180009226  mov     word ptr [rbp+Src], ax
0x18000922a  cmp     [rbp+pperrinfo], rax
0x18000922e  mov     [rbp+var_20], 7
0x180009236  jz      short loc_180009241
0x180009238  lea     rcx, [rbp+pperrinfo]
0x18000923c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009241  mov     rax, rsi
0x180009244  mov     rcx, [rbp+var_18]
0x180009248  xor     rcx, rsp; StackCookie
0x18000924b  call    __security_check_cookie
0x180009250  add     rsp, 78h
0x180009254  pop     r15
0x180009256  pop     r14
0x180009258  pop     r13
0x18000925a  pop     r12
0x18000925c  pop     rdi
0x18000925d  pop     rsi
0x18000925e  pop     rbx
0x18000925f  pop     rbp
0x180009260  retn
```
