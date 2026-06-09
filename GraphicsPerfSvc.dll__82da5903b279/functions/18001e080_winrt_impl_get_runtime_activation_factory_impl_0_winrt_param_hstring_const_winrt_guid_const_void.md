# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001e080`
- end: `0x18001e310`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `656`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `7`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001db68`
- `0x18001dbc8`
- `0x18001dc28`
- `0x18001dc88`
- `0x18001dce8`
- `0x18001dd48`
- `0x18001dda8`

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
- `0x18001e080`
- `0x180021860`
- `0x18002255c`
- `0x180022a18`
- `0x180031010`

## string_xrefs

- `0x18001e0e8`: `combase.dll`
- `0x18001e24c`: `DllGetActivationFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  _BYTE Src[16]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-28h]
  __int64 v32; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
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
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(Src, a2);
  while ( 1 )
  {
    do
    {
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      v15 = v12;
      if ( !v13 )
        goto LABEL_28;
      v16 = v13 - 1;
      if ( v13 - 1 >= v14 )
        v16 = v14;
      v17 = v12 + 2 + 2 * v16;
      last_trivial_2 = _std_find_last_trivial_2(v12, v17, 46);
      if ( last_trivial_2 == v17 || (v19 = (last_trivial_2 - v15) >> 1, v19 == -1) )
      {
LABEL_28:
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::_Tidy_deallocate(Src);
        v26 = pperrinfo == 0;
        goto LABEL_29;
      }
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
    }
    while ( !v24 );
    v25 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
    if ( v25 )
      break;
LABEL_24:
    WINRT_IMPL_FreeLibrary(v24);
  }
  v28 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v25)(*a2, &v28)
    || (**v28)(v28, a3, a4) )
  {
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
    goto LABEL_24;
  }
  *a1 = 0;
  if ( v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
  std::wstring::_Tidy_deallocate(Src);
  v26 = pperrinfo == 0;
LABEL_29:
  if ( !v26 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18001e080  push    rbp
0x18001e082  push    rbx
0x18001e083  push    rsi
0x18001e084  push    rdi
0x18001e085  push    r12
0x18001e087  push    r13
0x18001e089  push    r14
0x18001e08b  push    r15
0x18001e08d  mov     rbp, rsp
0x18001e090  sub     rsp, 78h
0x18001e094  mov     rax, cs:__security_cookie
0x18001e09b  xor     rax, rsp
0x18001e09e  mov     [rbp+var_18], rax
0x18001e0a2  mov     r13, r9
0x18001e0a5  mov     r12, r8
0x18001e0a8  mov     r15, rdx
0x18001e0ab  mov     rsi, rcx
0x18001e0ae  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001e0b5  xor     r14d, r14d
0x18001e0b8  mov     r8, r9
0x18001e0bb  mov     rdx, r12
0x18001e0be  mov     rcx, [r15]
0x18001e0c1  test    rax, rax
0x18001e0c4  jz      short loc_18001E0D2
0x18001e0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0cb  mov     [rsi], eax
0x18001e0cd  jmp     loc_18001E2F0
0x18001e0d2  call    RoGetActivationFactory_0
0x18001e0d7  mov     edi, eax
0x18001e0d9  cmp     eax, 800401F0h
0x18001e0de  jnz     short loc_18001E130
0x18001e0e0  xor     edx, edx; hFile
0x18001e0e2  mov     r8d, 1000h; dwFlags
0x18001e0e8  lea     rcx, LibFileName; "combase.dll"
0x18001e0ef  call    LoadLibraryExW_0
0x18001e0f4  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001e0fb  mov     rcx, rax; hModule
0x18001e0fe  call    WINRT_IMPL_GetProcAddress
0x18001e103  test    rax, rax
0x18001e106  jnz     short loc_18001E113
0x18001e108  mov     dword ptr [rsi], 800401F0h
0x18001e10e  jmp     loc_18001E2F0
0x18001e113  mov     [rbp+var_48], r14
0x18001e117  lea     rcx, [rbp+var_48]
0x18001e11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e120  mov     r8, r13
0x18001e123  mov     rdx, r12
0x18001e126  mov     rcx, [r15]
0x18001e129  call    RoGetActivationFactory_0
0x18001e12e  mov     edi, eax
0x18001e130  test    edi, edi
0x18001e132  jnz     short loc_18001E13C
0x18001e134  mov     [rsi], r14d
0x18001e137  jmp     loc_18001E2F0
0x18001e13c  mov     [rbp+pperrinfo], r14
0x18001e140  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001e144  xor     ecx, ecx; dwReserved
0x18001e146  call    GetErrorInfo_0
0x18001e14b  mov     rdx, r15
0x18001e14e  lea     rcx, [rbp+Src]
0x18001e152  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18001e157  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e15b  mov     rdx, [rbp+var_28]
0x18001e15f  lea     rcx, [rbp+Src]
0x18001e163  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e168  mov     r14, rax
0x18001e16b  test    rdx, rdx
0x18001e16e  jz      loc_18001E2CA
0x18001e174  lea     rcx, [rdx-1]
0x18001e178  cmp     rcx, r8
0x18001e17b  cmovnb  rcx, r8
0x18001e17f  add     rax, 2
0x18001e183  lea     rbx, [rax+rcx*2]
0x18001e187  mov     r8d, 2Eh ; '.'
0x18001e18d  mov     rdx, rbx
0x18001e190  mov     rcx, r14
0x18001e193  call    __std_find_last_trivial_2
0x18001e198  cmp     rax, rbx
0x18001e19b  jz      loc_18001E2CA
0x18001e1a1  sub     rax, r14
0x18001e1a4  sar     rax, 1
0x18001e1a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e1ab  jz      loc_18001E2CA
0x18001e1b1  mov     rdx, rax
0x18001e1b4  lea     rcx, [rbp+Src]
0x18001e1b8  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001e1bd  mov     r8, [rbp+var_28]
0x18001e1c1  mov     rax, [rbp+var_20]
0x18001e1c5  sub     rax, r8
0x18001e1c8  mov     ecx, 4
0x18001e1cd  cmp     rax, rcx
0x18001e1d0  jb      short loc_18001E1FB
0x18001e1d2  lea     rdx, [r8+4]
0x18001e1d6  mov     [rbp+var_28], rdx
0x18001e1da  lea     rcx, [rbp+Src]
0x18001e1de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e1e3  mov     rcx, 6C006C0064002Eh
0x18001e1ed  mov     [rax+r8*2], rcx
0x18001e1f1  xor     r14d, r14d
0x18001e1f4  mov     [rax+rdx*2], r14w
0x18001e1f9  jmp     short loc_18001E20F
0x18001e1fb  mov     [rsp+78h+var_58], rcx; __int64
0x18001e200  mov     rdx, rcx
0x18001e203  lea     rcx, [rbp+Src]; Src
0x18001e207  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001e20c  xor     r14d, r14d
0x18001e20f  lea     rcx, [rbp+Src]
0x18001e213  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e218  mov     rcx, rax; lpLibFileName
0x18001e21b  xor     edx, edx; hFile
0x18001e21d  mov     r8d, 1000h; dwFlags
0x18001e223  call    LoadLibraryExW_0
0x18001e228  mov     rbx, rax
0x18001e22b  mov     rdx, [rbp+var_28]
0x18001e22f  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001e233  lea     rcx, [rbp+Src]
0x18001e237  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001e23c  test    rbx, rbx
0x18001e23f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001e246  jz      loc_18001E15B
0x18001e24c  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18001e253  mov     rcx, rbx; hModule
0x18001e256  call    WINRT_IMPL_GetProcAddress
0x18001e25b  test    rax, rax
0x18001e25e  jz      short loc_18001E29C
0x18001e260  mov     [rbp+var_48], r14
0x18001e264  lea     rdx, [rbp+var_48]
0x18001e268  mov     rcx, [r15]
0x18001e26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e270  test    eax, eax
0x18001e272  jnz     short loc_18001E28D
0x18001e274  mov     rcx, [rbp+var_48]
0x18001e278  mov     rax, [rcx]
0x18001e27b  mov     r8, r13
0x18001e27e  mov     rdx, r12
0x18001e281  mov     rax, [rax]
0x18001e284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e289  test    eax, eax
0x18001e28b  jz      short loc_18001E2A9
0x18001e28d  cmp     [rbp+var_48], r14
0x18001e291  jz      short loc_18001E29C
0x18001e293  lea     rcx, [rbp+var_48]
0x18001e297  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e29c  mov     rcx, rbx; hLibModule
0x18001e29f  call    WINRT_IMPL_FreeLibrary
0x18001e2a4  jmp     loc_18001E157
0x18001e2a9  mov     [rsi], r14d
0x18001e2ac  cmp     [rbp+var_48], r14
0x18001e2b0  jz      short loc_18001E2BB
0x18001e2b2  lea     rcx, [rbp+var_48]
0x18001e2b6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e2bb  lea     rcx, [rbp+Src]
0x18001e2bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e2c4  cmp     [rbp+pperrinfo], r14
0x18001e2c8  jmp     short loc_18001E2E5
0x18001e2ca  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001e2ce  xor     ecx, ecx; dwReserved
0x18001e2d0  call    SetErrorInfo_0
0x18001e2d5  mov     [rsi], edi
0x18001e2d7  lea     rcx, [rbp+Src]
0x18001e2db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e2e0  cmp     [rbp+pperrinfo], 0
0x18001e2e5  jz      short loc_18001E2F0
0x18001e2e7  lea     rcx, [rbp+pperrinfo]
0x18001e2eb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e2f0  mov     rax, rsi
0x18001e2f3  mov     rcx, [rbp+var_18]
0x18001e2f7  xor     rcx, rsp; StackCookie
0x18001e2fa  call    __security_check_cookie
0x18001e2ff  add     rsp, 78h
0x18001e303  pop     r15
0x18001e305  pop     r14
0x18001e307  pop     r13
0x18001e309  pop     r12
0x18001e30b  pop     rdi
0x18001e30c  pop     rsi
0x18001e30d  pop     rbx
0x18001e30e  pop     rbp
0x18001e30f  retn
```
