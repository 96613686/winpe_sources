# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18002d6a4`
- end: `0x18002d9aa`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `774`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c218`
- `0x18000c808`
- `0x18003aeb0`
- `0x180047864`
- `0x180047e08`

## callees

- `0x180009380`
- `0x18002d1a4`
- `0x18002d62c`
- `0x18002d6a4`
- `0x18002f1f0`
- `0x1800338a4`
- `0x180036c10`
- `0x180056161`
- `0x18005619d`
- `0x180056500`
- `0x18005c49e`
- `0x18005c4aa`
- `0x18005c4b6`
- `0x18005c5e0`

## string_xrefs

- `0x18002d702`: `combase.dll`
- `0x18002d74e`: `combase.dll`
- `0x18002d8e5`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  FARPROC ProcAddress; // rax
  HMODULE LibraryW_0; // rax
  int v10; // ebx
  HMODULE v11; // rax
  FARPROC v12; // rax
  LPCWSTR *v13; // r14
  char *v14; // rdi
  __int64 traits_2_unsigned_short; // rax
  unsigned __int64 v16; // rdx
  LPCWSTR *v17; // rax
  const WCHAR *v18; // rcx
  HMODULE v19; // rdi
  unsigned __int64 v20; // rax
  LPCWSTR *v21; // rcx
  FARPROC v22; // rax
  bool v23; // zf
  unsigned int (__fastcall ***v25)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v28; // [rsp+40h] [rbp-28h]
  unsigned __int64 v29; // [rsp+48h] [rbp-20h]

  if ( winrt_activation_handler )
  {
    *a1 = winrt_activation_handler(*a2, a3, a4);
    return a1;
  }
  ProcAddress = (FARPROC)`winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler;
  if ( !`winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler )
  {
    LibraryW_0 = LoadLibraryW_0(L"combase.dll");
    ProcAddress = WINRT_IMPL_GetProcAddress(LibraryW_0, "RoGetActivationFactory");
    `winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      ProcAddress = (FARPROC)winrt::impl::fallback_RoGetActivationFactory;
      `winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler = (__int64)winrt::impl::fallback_RoGetActivationFactory;
    }
  }
  v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(*a2, a3, a4);
  if ( v10 == -2147221008 )
  {
    v11 = LoadLibraryW_0(L"combase.dll");
    v12 = WINRT_IMPL_GetProcAddress(v11, "CoIncrementMTAUsage");
    if ( !v12 )
    {
      *a1 = -2147221008;
      return a1;
    }
    v25 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v12)(&v25);
    v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))`winrt::impl::get_runtime_activation_factory_impl<0>'::`2'::handler)(
            *a2,
            a3,
            a4);
  }
  if ( !v10 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  *(_OWORD *)lpLibFileName = 0;
  v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,wchar_t const *>(lpLibFileName);
  while ( 1 )
  {
    do
    {
      v13 = lpLibFileName;
      if ( v29 > 7 )
        v13 = (LPCWSTR *)lpLibFileName[0];
      if ( !v28
        || (v14 = (char *)v13 + 2 * v28,
            traits_2_unsigned_short = anonymous_namespace_::__std_find_last_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                        v13,
                                        v14,
                                        46),
            (char *)traits_2_unsigned_short == v14)
        || (v16 = (traits_2_unsigned_short - (__int64)v13) >> 1, v16 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = v10;
        std::wstring::~wstring(lpLibFileName);
        v23 = pperrinfo == 0;
        goto LABEL_41;
      }
      if ( v16 > v28 )
      {
        std::wstring::append(lpLibFileName);
      }
      else
      {
        v28 = (traits_2_unsigned_short - (__int64)v13) >> 1;
        v17 = lpLibFileName;
        if ( v29 > 7 )
          v17 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v17 + v16) = 0;
      }
      std::wstring::append(lpLibFileName);
      v18 = (const WCHAR *)lpLibFileName;
      if ( v29 > 7 )
        v18 = lpLibFileName[0];
      v19 = LoadLibraryW_0(v18);
      v20 = v28 - 4;
      v21 = lpLibFileName;
      if ( v28 < 4 )
      {
        std::wstring::append(lpLibFileName);
      }
      else
      {
        v28 -= 4LL;
        if ( v29 > 7 )
          v21 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v21 + v20) = 0;
      }
    }
    while ( !v19 );
    v22 = WINRT_IMPL_GetProcAddress(v19, "DllGetActivationFactory");
    if ( v22 )
      break;
LABEL_36:
    WINRT_IMPL_FreeLibrary(v19);
  }
  v25 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v22)(*a2, &v25)
    || (**v25)(v25, a3, a4) )
  {
    if ( v25 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
    goto LABEL_36;
  }
  *a1 = 0;
  if ( v25 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
  std::wstring::~wstring(lpLibFileName);
  v23 = pperrinfo == 0;
LABEL_41:
  if ( !v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18002d6a4  push    rbp
0x18002d6a6  push    rbx
0x18002d6a7  push    rsi
0x18002d6a8  push    rdi
0x18002d6a9  push    r12
0x18002d6ab  push    r13
0x18002d6ad  push    r14
0x18002d6af  push    r15
0x18002d6b1  mov     rbp, rsp
0x18002d6b4  sub     rsp, 68h
0x18002d6b8  mov     rax, cs:__security_cookie
0x18002d6bf  xor     rax, rsp
0x18002d6c2  mov     [rbp+var_18], rax
0x18002d6c6  mov     r13, r9
0x18002d6c9  mov     r12, r8
0x18002d6cc  mov     r15, rdx
0x18002d6cf  mov     rsi, rcx
0x18002d6d2  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18002d6d9  xor     r14d, r14d
0x18002d6dc  test    rax, rax
0x18002d6df  jz      short loc_18002D6F6
0x18002d6e1  mov     r8, r9
0x18002d6e4  mov     rdx, r12
0x18002d6e7  mov     rcx, [r15]
0x18002d6ea  call    _guard_dispatch_icall
0x18002d6ef  mov     [rsi], eax
0x18002d6f1  jmp     loc_18002D98A
0x18002d6f6  mov     rax, cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA
0x18002d6fd  test    rax, rax
0x18002d700  jnz     short loc_18002D737
0x18002d702  lea     rcx, LibFileName; "combase.dll"
0x18002d709  call    LoadLibraryW_0
0x18002d70e  mov     rcx, rax; hModule
0x18002d711  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x18002d718  call    WINRT_IMPL_GetProcAddress
0x18002d71d  mov     cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA, rax
0x18002d724  test    rax, rax
0x18002d727  jnz     short loc_18002D737
0x18002d729  lea     rax, ?fallback_RoGetActivationFactory@impl@winrt@@YAHPEAXAEBUguid@2@PEAPEAX@Z; winrt::impl::fallback_RoGetActivationFactory(void *,winrt::guid const &,void * *)
0x18002d730  mov     cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA, rax
0x18002d737  mov     r8, r13
0x18002d73a  mov     rdx, r12
0x18002d73d  mov     rcx, [r15]
0x18002d740  call    _guard_dispatch_icall
0x18002d745  mov     ebx, eax
0x18002d747  cmp     eax, 800401F0h
0x18002d74c  jnz     short loc_18002D79D
0x18002d74e  lea     rcx, LibFileName; "combase.dll"
0x18002d755  call    LoadLibraryW_0
0x18002d75a  mov     rcx, rax; hModule
0x18002d75d  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18002d764  call    WINRT_IMPL_GetProcAddress
0x18002d769  test    rax, rax
0x18002d76c  jnz     short loc_18002D779
0x18002d76e  mov     dword ptr [rsi], 800401F0h
0x18002d774  jmp     loc_18002D98A
0x18002d779  mov     [rbp+var_48], r14
0x18002d77d  lea     rcx, [rbp+var_48]
0x18002d781  call    _guard_dispatch_icall
0x18002d786  mov     r8, r13
0x18002d789  mov     rdx, r12
0x18002d78c  mov     rcx, [r15]
0x18002d78f  mov     rax, cs:?handler@?1???$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@2@AEBUhstring@param@2@AEBUguid@2@PEAPEAX@Z@4P6AHPEAX12@_EEA
0x18002d796  call    _guard_dispatch_icall
0x18002d79b  mov     ebx, eax
0x18002d79d  test    ebx, ebx
0x18002d79f  jnz     short loc_18002D7A9
0x18002d7a1  mov     [rsi], r14d
0x18002d7a4  jmp     loc_18002D98A
0x18002d7a9  mov     [rbp+pperrinfo], r14
0x18002d7ad  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18002d7b1  xor     ecx, ecx; dwReserved
0x18002d7b3  call    GetErrorInfo_0
0x18002d7b8  xorps   xmm0, xmm0
0x18002d7bb  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18002d7bf  mov     [rbp+var_28], r14
0x18002d7c3  mov     [rbp+var_20], r14
0x18002d7c7  mov     rax, [r15]
0x18002d7ca  test    rax, rax
0x18002d7cd  jz      short loc_18002D7D9
0x18002d7cf  mov     rdx, [rax+10h]
0x18002d7d3  mov     r8d, [rax+4]
0x18002d7d7  jmp     short loc_18002D7E3
0x18002d7d9  lea     rdx, S2
0x18002d7e0  mov     r8, r14
0x18002d7e3  lea     rcx, [rbp+lpLibFileName]
0x18002d7e7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002d7ec  lea     r14, [rbp+lpLibFileName]
0x18002d7f0  cmp     [rbp+var_20], 7
0x18002d7f5  cmova   r14, [rbp+lpLibFileName]
0x18002d7fa  mov     rcx, [rbp+var_28]
0x18002d7fe  test    rcx, rcx
0x18002d801  jz      loc_18002D963
0x18002d807  dec     rcx
0x18002d80a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d80e  cmp     rcx, rax
0x18002d811  cmovb   rax, rcx
0x18002d815  inc     rax
0x18002d818  lea     rdi, [r14+rax*2]
0x18002d81c  mov     r8d, 2Eh ; '.'
0x18002d822  mov     rdx, rdi
0x18002d825  mov     rcx, r14
0x18002d828  call    _anonymous_namespace_____std_find_last_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18002d82d  mov     rdx, rax
0x18002d830  cmp     rax, rdi
0x18002d833  jz      loc_18002D963
0x18002d839  sub     rdx, r14
0x18002d83c  sar     rdx, 1
0x18002d83f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002d843  jz      loc_18002D963
0x18002d849  cmp     rdx, [rbp+var_28]
0x18002d84d  ja      short loc_18002D86B
0x18002d84f  mov     [rbp+var_28], rdx
0x18002d853  lea     rax, [rbp+lpLibFileName]
0x18002d857  cmp     [rbp+var_20], 7
0x18002d85c  cmova   rax, [rbp+lpLibFileName]
0x18002d861  xor     r14d, r14d
0x18002d864  mov     [rax+rdx*2], r14w
0x18002d869  jmp     short loc_18002D87E
0x18002d86b  xor     r8d, r8d
0x18002d86e  sub     rdx, [rbp+var_28]
0x18002d872  lea     rcx, [rbp+lpLibFileName]; Src
0x18002d876  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18002d87b  xor     r14d, r14d
0x18002d87e  mov     r8d, 4
0x18002d884  lea     rdx, aDll; ".dll"
0x18002d88b  lea     rcx, [rbp+lpLibFileName]; Src
0x18002d88f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18002d894  lea     rcx, [rbp+lpLibFileName]
0x18002d898  cmp     [rbp+var_20], 7
0x18002d89d  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18002d8a2  call    LoadLibraryW_0
0x18002d8a7  mov     rdi, rax
0x18002d8aa  mov     rcx, [rbp+var_28]
0x18002d8ae  lea     rax, [rcx-4]
0x18002d8b2  cmp     rax, rcx
0x18002d8b5  lea     rcx, [rbp+lpLibFileName]; Src
0x18002d8b9  ja      short loc_18002D8D0
0x18002d8bb  mov     [rbp+var_28], rax
0x18002d8bf  cmp     [rbp+var_20], 7
0x18002d8c4  cmova   rcx, [rbp+lpLibFileName]
0x18002d8c9  mov     [rcx+rax*2], r14w
0x18002d8ce  jmp     short loc_18002D8DC
0x18002d8d0  xor     r8d, r8d
0x18002d8d3  lea     rdx, [r8-4]
0x18002d8d7  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18002d8dc  test    rdi, rdi
0x18002d8df  jz      loc_18002D7EC
0x18002d8e5  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18002d8ec  mov     rcx, rdi; hModule
0x18002d8ef  call    WINRT_IMPL_GetProcAddress
0x18002d8f4  test    rax, rax
0x18002d8f7  jz      short loc_18002D935
0x18002d8f9  mov     [rbp+var_48], r14
0x18002d8fd  lea     rdx, [rbp+var_48]
0x18002d901  mov     rcx, [r15]
0x18002d904  call    _guard_dispatch_icall
0x18002d909  test    eax, eax
0x18002d90b  jnz     short loc_18002D926
0x18002d90d  mov     rcx, [rbp+var_48]
0x18002d911  mov     rax, [rcx]
0x18002d914  mov     r8, r13
0x18002d917  mov     rdx, r12
0x18002d91a  mov     rax, [rax]
0x18002d91d  call    _guard_dispatch_icall
0x18002d922  test    eax, eax
0x18002d924  jz      short loc_18002D942
0x18002d926  cmp     [rbp+var_48], r14
0x18002d92a  jz      short loc_18002D935
0x18002d92c  lea     rcx, [rbp+var_48]
0x18002d930  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002d935  mov     rcx, rdi; hLibModule
0x18002d938  call    WINRT_IMPL_FreeLibrary
0x18002d93d  jmp     loc_18002D7EC
0x18002d942  mov     [rsi], r14d
0x18002d945  cmp     [rbp+var_48], r14
0x18002d949  jz      short loc_18002D954
0x18002d94b  lea     rcx, [rbp+var_48]
0x18002d94f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002d954  lea     rcx, [rbp+lpLibFileName]; void *
0x18002d958  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d95d  cmp     [rbp+pperrinfo], r14
0x18002d961  jmp     short loc_18002D97F
0x18002d963  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18002d967  xor     ecx, ecx; dwReserved
0x18002d969  call    SetErrorInfo_0
0x18002d96e  mov     [rsi], ebx
0x18002d970  lea     rcx, [rbp+lpLibFileName]; void *
0x18002d974  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d979  xor     eax, eax
0x18002d97b  cmp     [rbp+pperrinfo], rax
0x18002d97f  jz      short loc_18002D98A
0x18002d981  lea     rcx, [rbp+pperrinfo]
0x18002d985  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002d98a  mov     rax, rsi
0x18002d98d  mov     rcx, [rbp+var_18]
0x18002d991  xor     rcx, rsp; StackCookie
0x18002d994  call    __security_check_cookie
0x18002d999  add     rsp, 68h
0x18002d99d  pop     r15
0x18002d99f  pop     r14
0x18002d9a1  pop     r13
0x18002d9a3  pop     r12
0x18002d9a5  pop     rdi
0x18002d9a6  pop     rsi
0x18002d9a7  pop     rbx
0x18002d9a8  pop     rbp
0x18002d9a9  retn
```
