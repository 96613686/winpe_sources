# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000fb5c`
- end: `0x18000fdd4`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `632`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f9fc`
- `0x180017a00`
- `0x180020f0c`
- `0x180021960`

## callees

- `0x180003fe0`
- `0x180004410`
- `0x180005368`
- `0x180005380`
- `0x180005398`
- `0x180005479`
- `0x180005491`
- `0x1800054b5`
- `0x18000c250`
- `0x18000d1c0`
- `0x18000f304`
- `0x18000fb5c`
- `0x180011400`
- `0x1800152cc`
- `0x180041010`

## string_xrefs

- `0x18000fbc4`: `combase.dll`
- `0x18000fd10`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // r14
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  const WCHAR *v18; // rcx
  HMODULE v19; // rdi
  FARPROC v20; // rax
  bool v21; // zf
  unsigned int (__fastcall ***v23)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v26; // [rsp+40h] [rbp-28h]
  unsigned __int64 v27; // [rsp+48h] [rbp-20h]

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
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(const wchar_t **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = &S1;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
  while ( 1 )
  {
    do
    {
      v15 = lpLibFileName;
      if ( v27 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      if ( !v26
        || (v16 = (char *)v15 + 2 * v26,
            last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46),
            (char *)last_trivial_2 == v16)
        || (last_trivial_2 - (__int64)v15) >> 1 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::~wstring(lpLibFileName);
        v21 = pperrinfo == 0;
        goto LABEL_31;
      }
      std::wstring::resize(lpLibFileName);
      std::wstring::operator+=(lpLibFileName, L".dll");
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
LABEL_26:
    WINRT_IMPL_FreeLibrary(v19);
  }
  v23 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v20)(*a2, &v23)
    || (**v23)(v23, a3, a4) )
  {
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    goto LABEL_26;
  }
  *a1 = 0;
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
  std::wstring::~wstring(lpLibFileName);
  v21 = pperrinfo == 0;
LABEL_31:
  if ( !v21 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000fb5c  push    rbp
0x18000fb5e  push    rbx
0x18000fb5f  push    rsi
0x18000fb60  push    rdi
0x18000fb61  push    r12
0x18000fb63  push    r13
0x18000fb65  push    r14
0x18000fb67  push    r15
0x18000fb69  mov     rbp, rsp
0x18000fb6c  sub     rsp, 68h
0x18000fb70  mov     rax, cs:__security_cookie
0x18000fb77  xor     rax, rsp
0x18000fb7a  mov     [rbp+var_18], rax
0x18000fb7e  mov     r13, r9
0x18000fb81  mov     r12, r8
0x18000fb84  mov     r15, rdx
0x18000fb87  mov     rsi, rcx
0x18000fb8a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000fb91  xor     r14d, r14d
0x18000fb94  mov     r8, r9
0x18000fb97  mov     rdx, r12
0x18000fb9a  mov     rcx, [r15]
0x18000fb9d  test    rax, rax
0x18000fba0  jz      short loc_18000FBAE
0x18000fba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fba7  mov     [rsi], eax
0x18000fba9  jmp     loc_18000FDB4
0x18000fbae  call    RoGetActivationFactory_0
0x18000fbb3  mov     ebx, eax
0x18000fbb5  cmp     eax, 800401F0h
0x18000fbba  jnz     short loc_18000FC0C
0x18000fbbc  xor     edx, edx; hFile
0x18000fbbe  mov     r8d, 1000h; dwFlags
0x18000fbc4  lea     rcx, aCombaseDll; "combase.dll"
0x18000fbcb  call    LoadLibraryExW_0
0x18000fbd0  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000fbd7  mov     rcx, rax; hModule
0x18000fbda  call    WINRT_IMPL_GetProcAddress
0x18000fbdf  test    rax, rax
0x18000fbe2  jnz     short loc_18000FBEF
0x18000fbe4  mov     dword ptr [rsi], 800401F0h
0x18000fbea  jmp     loc_18000FDB4
0x18000fbef  mov     [rbp+var_48], r14
0x18000fbf3  lea     rcx, [rbp+var_48]
0x18000fbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbfc  mov     r8, r13
0x18000fbff  mov     rdx, r12
0x18000fc02  mov     rcx, [r15]
0x18000fc05  call    RoGetActivationFactory_0
0x18000fc0a  mov     ebx, eax
0x18000fc0c  test    ebx, ebx
0x18000fc0e  jnz     short loc_18000FC18
0x18000fc10  mov     [rsi], r14d
0x18000fc13  jmp     loc_18000FDB4
0x18000fc18  mov     [rbp+pperrinfo], r14
0x18000fc1c  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000fc20  xor     ecx, ecx; dwReserved
0x18000fc22  call    GetErrorInfo_0
0x18000fc27  xorps   xmm0, xmm0
0x18000fc2a  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18000fc2e  mov     [rbp+var_28], r14
0x18000fc32  mov     [rbp+var_20], r14
0x18000fc36  mov     rax, [r15]
0x18000fc39  test    rax, rax
0x18000fc3c  jz      short loc_18000FC48
0x18000fc3e  mov     rdx, [rax+10h]
0x18000fc42  mov     r8d, [rax+4]
0x18000fc46  jmp     short loc_18000FC52
0x18000fc48  lea     rdx, S1
0x18000fc4f  mov     r8, r14
0x18000fc52  lea     rcx, [rbp+lpLibFileName]
0x18000fc56  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000fc5b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fc5f  mov     rax, [rbp+var_28]
0x18000fc63  lea     r14, [rbp+lpLibFileName]
0x18000fc67  cmp     [rbp+var_20], 7
0x18000fc6c  cmova   r14, [rbp+lpLibFileName]
0x18000fc71  test    rax, rax
0x18000fc74  jz      loc_18000FD8E
0x18000fc7a  dec     rax
0x18000fc7d  cmp     rax, rcx
0x18000fc80  cmovnb  rax, rcx
0x18000fc84  inc     rax
0x18000fc87  lea     rdi, [r14+rax*2]
0x18000fc8b  mov     r8d, 2Eh ; '.'
0x18000fc91  mov     rdx, rdi
0x18000fc94  mov     rcx, r14
0x18000fc97  call    __std_find_last_trivial_2
0x18000fc9c  cmp     rax, rdi
0x18000fc9f  jz      loc_18000FD8E
0x18000fca5  sub     rax, r14
0x18000fca8  sar     rax, 1
0x18000fcab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fcaf  jz      loc_18000FD8E
0x18000fcb5  mov     rdx, rax
0x18000fcb8  lea     rcx, [rbp+lpLibFileName]; Src
0x18000fcbc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000fcc1  lea     rdx, aDll; ".dll"
0x18000fcc8  lea     rcx, [rbp+lpLibFileName]; Src
0x18000fccc  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18000fcd1  lea     rcx, [rbp+lpLibFileName]
0x18000fcd5  cmp     [rbp+var_20], 7
0x18000fcda  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000fcdf  xor     edx, edx; hFile
0x18000fce1  mov     r8d, 1000h; dwFlags
0x18000fce7  call    LoadLibraryExW_0
0x18000fcec  mov     rdi, rax
0x18000fcef  mov     rdx, [rbp+var_28]
0x18000fcf3  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18000fcf7  lea     rcx, [rbp+lpLibFileName]; Src
0x18000fcfb  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000fd00  xor     r14d, r14d
0x18000fd03  test    rdi, rdi
0x18000fd06  lea     rcx, [r14-1]
0x18000fd0a  jz      loc_18000FC5F
0x18000fd10  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18000fd17  mov     rcx, rdi; hModule
0x18000fd1a  call    WINRT_IMPL_GetProcAddress
0x18000fd1f  test    rax, rax
0x18000fd22  jz      short loc_18000FD60
0x18000fd24  mov     [rbp+var_48], r14
0x18000fd28  lea     rdx, [rbp+var_48]
0x18000fd2c  mov     rcx, [r15]
0x18000fd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd34  test    eax, eax
0x18000fd36  jnz     short loc_18000FD51
0x18000fd38  mov     rcx, [rbp+var_48]
0x18000fd3c  mov     rax, [rcx]
0x18000fd3f  mov     r8, r13
0x18000fd42  mov     rdx, r12
0x18000fd45  mov     rax, [rax]
0x18000fd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd4d  test    eax, eax
0x18000fd4f  jz      short loc_18000FD6D
0x18000fd51  cmp     [rbp+var_48], r14
0x18000fd55  jz      short loc_18000FD60
0x18000fd57  lea     rcx, [rbp+var_48]
0x18000fd5b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fd60  mov     rcx, rdi; hLibModule
0x18000fd63  call    WINRT_IMPL_FreeLibrary
0x18000fd68  jmp     loc_18000FC5B
0x18000fd6d  mov     [rsi], r14d
0x18000fd70  cmp     [rbp+var_48], r14
0x18000fd74  jz      short loc_18000FD7F
0x18000fd76  lea     rcx, [rbp+var_48]
0x18000fd7a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fd7f  lea     rcx, [rbp+lpLibFileName]; void *
0x18000fd83  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fd88  cmp     [rbp+pperrinfo], r14
0x18000fd8c  jmp     short loc_18000FDA9
0x18000fd8e  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000fd92  xor     ecx, ecx; dwReserved
0x18000fd94  call    SetErrorInfo_0
0x18000fd99  mov     [rsi], ebx
0x18000fd9b  lea     rcx, [rbp+lpLibFileName]; void *
0x18000fd9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fda4  cmp     [rbp+pperrinfo], 0
0x18000fda9  jz      short loc_18000FDB4
0x18000fdab  lea     rcx, [rbp+pperrinfo]
0x18000fdaf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fdb4  mov     rax, rsi
0x18000fdb7  mov     rcx, [rbp+var_18]
0x18000fdbb  xor     rcx, rsp; StackCookie
0x18000fdbe  call    __security_check_cookie
0x18000fdc3  add     rsp, 68h
0x18000fdc7  pop     r15
0x18000fdc9  pop     r14
0x18000fdcb  pop     r13
0x18000fdcd  pop     r12
0x18000fdcf  pop     rdi
0x18000fdd0  pop     rsi
0x18000fdd1  pop     rbx
0x18000fdd2  pop     rbp
0x18000fdd3  retn
```
