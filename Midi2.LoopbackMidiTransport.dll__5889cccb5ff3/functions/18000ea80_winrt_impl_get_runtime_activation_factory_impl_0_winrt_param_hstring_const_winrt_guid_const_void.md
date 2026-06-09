# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000ea80`
- end: `0x18000ed46`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `710`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e920`
- `0x180015198`
- `0x180015e90`

## callees

- `0x180003d50`
- `0x180004180`
- `0x1800050fc`
- `0x180005114`
- `0x18000512c`
- `0x1800051e5`
- `0x180005209`
- `0x180005215`
- `0x18000b740`
- `0x18000e178`
- `0x18000e5a0`
- `0x18000ea80`
- `0x18001455c`
- `0x180014974`
- `0x180032010`

## string_xrefs

- `0x18000eae8`: `combase.dll`
- `0x18000ec82`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const wchar_t *v12; // rdx
  LPCWSTR *v13; // r14
  LPCWSTR *v14; // rbx
  __int64 last_trivial_2; // rax
  unsigned __int64 v16; // r8
  LPCWSTR *v17; // rcx
  const WCHAR *v18; // rcx
  HMODULE v19; // rbx
  FARPROC v20; // rax
  bool v21; // zf
  unsigned int (__fastcall ***v23)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-28h]
  unsigned __int64 v27; // [rsp+58h] [rbp-20h]

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
    v23 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v23);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)lpLibFileName = 0;
  v26 = 0;
  v27 = 0;
  if ( *a2 )
    v12 = *(const wchar_t **)(*a2 + 16LL);
  else
    v12 = &S2;
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v12);
  while ( 1 )
  {
    do
    {
      v13 = lpLibFileName;
      if ( v27 > 7 )
        v13 = (LPCWSTR *)lpLibFileName[0];
      if ( !v26
        || (v14 = &v13[v26 / 4],
            last_trivial_2 = _std_find_last_trivial_2(v13, v14, 46),
            (LPCWSTR *)last_trivial_2 == v14)
        || (last_trivial_2 - (__int64)v13) >> 1 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::~wstring(lpLibFileName);
        v21 = pperrinfo == 0;
        goto LABEL_36;
      }
      std::wstring::resize(lpLibFileName);
      v16 = v26;
      if ( v27 - v26 < 4 )
      {
        ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
          lpLibFileName,
          4);
      }
      else
      {
        v26 += 4LL;
        v17 = lpLibFileName;
        if ( v27 > 7 )
          v17 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v17 + 2 * v16) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v17 + v16 + 4) = 0;
      }
      v18 = (const WCHAR *)lpLibFileName;
      if ( v27 > 7 )
        v18 = lpLibFileName[0];
      v19 = LoadLibraryExW_0(v18, 0, 0x1000u);
      std::wstring::resize(lpLibFileName);
    }
    while ( !v19 );
    v20 = WINRT_IMPL_GetProcAddress(v19, "DllGetActivationFactory");
    if ( v20 )
      break;
LABEL_31:
    WINRT_IMPL_FreeLibrary(v19);
  }
  v23 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v20)(*a2, &v23)
    || (**v23)(v23, a3, a4) )
  {
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    goto LABEL_31;
  }
  *a1 = 0;
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
  std::wstring::~wstring(lpLibFileName);
  v21 = pperrinfo == 0;
LABEL_36:
  if ( !v21 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000ea80  push    rbp
0x18000ea82  push    rbx
0x18000ea83  push    rsi
0x18000ea84  push    rdi
0x18000ea85  push    r12
0x18000ea87  push    r13
0x18000ea89  push    r14
0x18000ea8b  push    r15
0x18000ea8d  mov     rbp, rsp
0x18000ea90  sub     rsp, 78h
0x18000ea94  mov     rax, cs:__security_cookie
0x18000ea9b  xor     rax, rsp
0x18000ea9e  mov     [rbp+var_18], rax
0x18000eaa2  mov     r13, r9
0x18000eaa5  mov     r12, r8
0x18000eaa8  mov     r15, rdx
0x18000eaab  mov     rsi, rcx
0x18000eaae  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000eab5  xor     r14d, r14d
0x18000eab8  mov     r8, r9
0x18000eabb  mov     rdx, r12
0x18000eabe  mov     rcx, [r15]
0x18000eac1  test    rax, rax
0x18000eac4  jz      short loc_18000EAD2
0x18000eac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eacb  mov     [rsi], eax
0x18000eacd  jmp     loc_18000ED26
0x18000ead2  call    RoGetActivationFactory_0
0x18000ead7  mov     edi, eax
0x18000ead9  cmp     eax, 800401F0h
0x18000eade  jnz     short loc_18000EB30
0x18000eae0  xor     edx, edx; hFile
0x18000eae2  mov     r8d, 1000h; dwFlags
0x18000eae8  lea     rcx, aCombaseDll; "combase.dll"
0x18000eaef  call    LoadLibraryExW_0
0x18000eaf4  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000eafb  mov     rcx, rax; hModule
0x18000eafe  call    WINRT_IMPL_GetProcAddress
0x18000eb03  test    rax, rax
0x18000eb06  jnz     short loc_18000EB13
0x18000eb08  mov     dword ptr [rsi], 800401F0h
0x18000eb0e  jmp     loc_18000ED26
0x18000eb13  mov     [rbp+var_48], r14
0x18000eb17  lea     rcx, [rbp+var_48]
0x18000eb1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb20  mov     r8, r13
0x18000eb23  mov     rdx, r12
0x18000eb26  mov     rcx, [r15]
0x18000eb29  call    RoGetActivationFactory_0
0x18000eb2e  mov     edi, eax
0x18000eb30  test    edi, edi
0x18000eb32  jnz     short loc_18000EB3C
0x18000eb34  mov     [rsi], r14d
0x18000eb37  jmp     loc_18000ED26
0x18000eb3c  mov     [rbp+pperrinfo], r14
0x18000eb40  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000eb44  xor     ecx, ecx; dwReserved
0x18000eb46  call    GetErrorInfo_0
0x18000eb4b  xorps   xmm0, xmm0
0x18000eb4e  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18000eb52  mov     [rbp+var_28], r14
0x18000eb56  mov     [rbp+var_20], r14
0x18000eb5a  mov     rax, [r15]
0x18000eb5d  test    rax, rax
0x18000eb60  jz      short loc_18000EB6C
0x18000eb62  mov     rdx, [rax+10h]
0x18000eb66  mov     r8d, [rax+4]
0x18000eb6a  jmp     short loc_18000EB76
0x18000eb6c  lea     rdx, S2
0x18000eb73  mov     r8, r14
0x18000eb76  lea     rcx, [rbp+lpLibFileName]
0x18000eb7a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000eb7f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000eb83  mov     rax, [rbp+var_28]
0x18000eb87  lea     r14, [rbp+lpLibFileName]
0x18000eb8b  cmp     [rbp+var_20], 7
0x18000eb90  cmova   r14, [rbp+lpLibFileName]
0x18000eb95  test    rax, rax
0x18000eb98  jz      loc_18000ED00
0x18000eb9e  dec     rax
0x18000eba1  cmp     rax, rcx
0x18000eba4  cmovnb  rax, rcx
0x18000eba8  inc     rax
0x18000ebab  lea     rbx, [r14+rax*2]
0x18000ebaf  mov     r8d, 2Eh ; '.'
0x18000ebb5  mov     rdx, rbx
0x18000ebb8  mov     rcx, r14
0x18000ebbb  call    __std_find_last_trivial_2
0x18000ebc0  cmp     rax, rbx
0x18000ebc3  jz      loc_18000ED00
0x18000ebc9  sub     rax, r14
0x18000ebcc  sar     rax, 1
0x18000ebcf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ebd3  jz      loc_18000ED00
0x18000ebd9  mov     rdx, rax
0x18000ebdc  lea     rcx, [rbp+lpLibFileName]; Src
0x18000ebe0  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000ebe5  mov     r8, [rbp+var_28]
0x18000ebe9  mov     rax, [rbp+var_20]
0x18000ebed  sub     rax, r8
0x18000ebf0  mov     ecx, 4
0x18000ebf5  cmp     rax, rcx
0x18000ebf8  jb      short loc_18000EC28
0x18000ebfa  lea     rdx, [r8+4]
0x18000ebfe  mov     [rbp+var_28], rdx
0x18000ec02  lea     rcx, [rbp+lpLibFileName]
0x18000ec06  cmp     [rbp+var_20], 7
0x18000ec0b  cmova   rcx, [rbp+lpLibFileName]
0x18000ec10  mov     rax, 6C006C0064002Eh
0x18000ec1a  mov     [rcx+r8*2], rax
0x18000ec1e  xor     r14d, r14d
0x18000ec21  mov     [rcx+rdx*2], r14w
0x18000ec26  jmp     short loc_18000EC43
0x18000ec28  mov     [rsp+78h+var_58], rcx; __int64
0x18000ec2d  lea     r9, aDll; ".dll"
0x18000ec34  mov     rdx, rcx
0x18000ec37  lea     rcx, [rbp+lpLibFileName]; Src
0x18000ec3b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x18000ec40  xor     r14d, r14d
0x18000ec43  lea     rcx, [rbp+lpLibFileName]
0x18000ec47  cmp     [rbp+var_20], 7
0x18000ec4c  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000ec51  xor     edx, edx; hFile
0x18000ec53  mov     r8d, 1000h; dwFlags
0x18000ec59  call    LoadLibraryExW_0
0x18000ec5e  mov     rbx, rax
0x18000ec61  mov     rdx, [rbp+var_28]
0x18000ec65  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18000ec69  lea     rcx, [rbp+lpLibFileName]; Src
0x18000ec6d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000ec72  test    rbx, rbx
0x18000ec75  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ec7c  jz      loc_18000EB83
0x18000ec82  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18000ec89  mov     rcx, rbx; hModule
0x18000ec8c  call    WINRT_IMPL_GetProcAddress
0x18000ec91  test    rax, rax
0x18000ec94  jz      short loc_18000ECD2
0x18000ec96  mov     [rbp+var_48], r14
0x18000ec9a  lea     rdx, [rbp+var_48]
0x18000ec9e  mov     rcx, [r15]
0x18000eca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eca6  test    eax, eax
0x18000eca8  jnz     short loc_18000ECC3
0x18000ecaa  mov     rcx, [rbp+var_48]
0x18000ecae  mov     rax, [rcx]
0x18000ecb1  mov     r8, r13
0x18000ecb4  mov     rdx, r12
0x18000ecb7  mov     rax, [rax]
0x18000ecba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecbf  test    eax, eax
0x18000ecc1  jz      short loc_18000ECDF
0x18000ecc3  cmp     [rbp+var_48], r14
0x18000ecc7  jz      short loc_18000ECD2
0x18000ecc9  lea     rcx, [rbp+var_48]
0x18000eccd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ecd2  mov     rcx, rbx; hLibModule
0x18000ecd5  call    WINRT_IMPL_FreeLibrary
0x18000ecda  jmp     loc_18000EB7F
0x18000ecdf  mov     [rsi], r14d
0x18000ece2  cmp     [rbp+var_48], r14
0x18000ece6  jz      short loc_18000ECF1
0x18000ece8  lea     rcx, [rbp+var_48]
0x18000ecec  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ecf1  lea     rcx, [rbp+lpLibFileName]; void *
0x18000ecf5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ecfa  cmp     [rbp+pperrinfo], r14
0x18000ecfe  jmp     short loc_18000ED1B
0x18000ed00  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000ed04  xor     ecx, ecx; dwReserved
0x18000ed06  call    SetErrorInfo_0
0x18000ed0b  mov     [rsi], edi
0x18000ed0d  lea     rcx, [rbp+lpLibFileName]; void *
0x18000ed11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed16  cmp     [rbp+pperrinfo], 0
0x18000ed1b  jz      short loc_18000ED26
0x18000ed1d  lea     rcx, [rbp+pperrinfo]
0x18000ed21  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ed26  mov     rax, rsi
0x18000ed29  mov     rcx, [rbp+var_18]
0x18000ed2d  xor     rcx, rsp; StackCookie
0x18000ed30  call    __security_check_cookie
0x18000ed35  add     rsp, 78h
0x18000ed39  pop     r15
0x18000ed3b  pop     r14
0x18000ed3d  pop     r13
0x18000ed3f  pop     r12
0x18000ed41  pop     rdi
0x18000ed42  pop     rsi
0x18000ed43  pop     rbx
0x18000ed44  pop     rbp
0x18000ed45  retn
```
