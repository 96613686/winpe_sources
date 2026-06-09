# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000fbc4`
- end: `0x18000fde9`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `549`
- prototype: ``
- caller_count: `7`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec34`
- `0x18000edf0`
- `0x18000ef74`
- `0x18000f400`
- `0x18000faa4`
- `0x18000fb04`
- `0x18000fb64`

## callees

- `0x1800021d0`
- `0x180002d8b`
- `0x180002d97`
- `0x180002da3`
- `0x1800033b1`
- `0x1800033ed`
- `0x1800033f9`
- `0x18000df10`
- `0x18000df90`
- `0x18000ea18`
- `0x18000fbc4`
- `0x180012530`
- `0x180020158`
- `0x1800215e8`
- `0x180024010`

## string_xrefs

- `0x18000fc2c`: `combase.dll`
- `0x18000fd33`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  char *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // rcx
  __int64 v16; // rax
  const WCHAR *v17; // rcx
  HMODULE v18; // rdi
  FARPROC v19; // rax
  unsigned int (__fastcall ***v21)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v24; // [rsp+40h] [rbp-28h]
  unsigned __int64 v25; // [rsp+48h] [rbp-20h]

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
    v21 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v21);
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
  v24 = 0;
  v25 = 0;
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(char **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = byte_180026660;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v13, v14);
  while ( 1 )
  {
    do
    {
      v15 = lpLibFileName;
      if ( v25 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      v16 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v15, v24);
      if ( v16 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_28;
      }
      std::wstring::resize(lpLibFileName, v16);
      std::wstring::_Append<unsigned short>(lpLibFileName);
      v17 = (const WCHAR *)lpLibFileName;
      if ( v25 > 7 )
        v17 = lpLibFileName[0];
      v18 = LoadLibraryExW_0(v17, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, v24 - 4);
    }
    while ( !v18 );
    v19 = WINRT_IMPL_GetProcAddress(v18, "DllGetActivationFactory");
    if ( v19 )
      break;
LABEL_24:
    WINRT_IMPL_FreeLibrary(v18);
  }
  v21 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v19)(*a2, &v21)
    || (**v21)(v21, a3, a4) )
  {
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
    goto LABEL_24;
  }
  *a1 = 0;
  if ( v21 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
LABEL_28:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000fbc4  push    rbp
0x18000fbc6  push    rbx
0x18000fbc7  push    rsi
0x18000fbc8  push    rdi
0x18000fbc9  push    r12
0x18000fbcb  push    r13
0x18000fbcd  push    r14
0x18000fbcf  push    r15
0x18000fbd1  mov     rbp, rsp
0x18000fbd4  sub     rsp, 68h
0x18000fbd8  mov     rax, cs:__security_cookie
0x18000fbdf  xor     rax, rsp
0x18000fbe2  mov     [rbp+var_18], rax
0x18000fbe6  mov     r12, r9
0x18000fbe9  mov     r15, r8
0x18000fbec  mov     r14, rdx
0x18000fbef  mov     rsi, rcx
0x18000fbf2  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000fbf9  xor     r13d, r13d
0x18000fbfc  mov     r8, r9
0x18000fbff  mov     rdx, r15
0x18000fc02  mov     rcx, [r14]
0x18000fc05  test    rax, rax
0x18000fc08  jz      short loc_18000FC16
0x18000fc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc0f  mov     [rsi], eax
0x18000fc11  jmp     loc_18000FDC9
0x18000fc16  call    RoGetActivationFactory_0
0x18000fc1b  mov     ebx, eax
0x18000fc1d  cmp     eax, 800401F0h
0x18000fc22  jnz     short loc_18000FC74
0x18000fc24  xor     edx, edx; hFile
0x18000fc26  mov     r8d, 1000h; dwFlags
0x18000fc2c  lea     rcx, LibFileName; "combase.dll"
0x18000fc33  call    LoadLibraryExW_0
0x18000fc38  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000fc3f  mov     rcx, rax; hModule
0x18000fc42  call    WINRT_IMPL_GetProcAddress
0x18000fc47  test    rax, rax
0x18000fc4a  jnz     short loc_18000FC57
0x18000fc4c  mov     dword ptr [rsi], 800401F0h
0x18000fc52  jmp     loc_18000FDC9
0x18000fc57  mov     [rbp+var_48], r13
0x18000fc5b  lea     rcx, [rbp+var_48]
0x18000fc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc64  mov     r8, r12
0x18000fc67  mov     rdx, r15
0x18000fc6a  mov     rcx, [r14]
0x18000fc6d  call    RoGetActivationFactory_0
0x18000fc72  mov     ebx, eax
0x18000fc74  test    ebx, ebx
0x18000fc76  jnz     short loc_18000FC80
0x18000fc78  mov     [rsi], r13d
0x18000fc7b  jmp     loc_18000FDC9
0x18000fc80  mov     [rbp+pperrinfo], r13
0x18000fc84  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000fc88  xor     ecx, ecx; dwReserved
0x18000fc8a  call    GetErrorInfo_0
0x18000fc8f  xorps   xmm0, xmm0
0x18000fc92  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18000fc96  mov     [rbp+var_28], r13
0x18000fc9a  mov     [rbp+var_20], r13
0x18000fc9e  mov     rax, [r14]
0x18000fca1  test    rax, rax
0x18000fca4  jz      short loc_18000FCB0
0x18000fca6  mov     rdx, [rax+10h]
0x18000fcaa  mov     r8d, [rax+4]
0x18000fcae  jmp     short loc_18000FCBA
0x18000fcb0  lea     rdx, byte_180026660
0x18000fcb7  mov     r8, r13
0x18000fcba  lea     rcx, [rbp+lpLibFileName]
0x18000fcbe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000fcc3  lea     rcx, [rbp+lpLibFileName]
0x18000fcc7  cmp     [rbp+var_20], 7
0x18000fccc  cmova   rcx, [rbp+lpLibFileName]
0x18000fcd1  mov     rdx, [rbp+var_28]
0x18000fcd5  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18000fcda  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fcde  jz      loc_18000FDA4
0x18000fce4  mov     rdx, rax
0x18000fce7  lea     rcx, [rbp+lpLibFileName]
0x18000fceb  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000fcf0  mov     r8d, 4
0x18000fcf6  lea     rcx, [rbp+lpLibFileName]; Src
0x18000fcfa  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000fcff  lea     rcx, [rbp+lpLibFileName]
0x18000fd03  cmp     [rbp+var_20], 7
0x18000fd08  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000fd0d  xor     edx, edx; hFile
0x18000fd0f  mov     r8d, 1000h; dwFlags
0x18000fd15  call    LoadLibraryExW_0
0x18000fd1a  mov     rdi, rax
0x18000fd1d  mov     rdx, [rbp+var_28]
0x18000fd21  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18000fd25  lea     rcx, [rbp+lpLibFileName]
0x18000fd29  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000fd2e  test    rdi, rdi
0x18000fd31  jz      short loc_18000FCC3
0x18000fd33  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18000fd3a  mov     rcx, rdi; hModule
0x18000fd3d  call    WINRT_IMPL_GetProcAddress
0x18000fd42  test    rax, rax
0x18000fd45  jz      short loc_18000FD83
0x18000fd47  mov     [rbp+var_48], r13
0x18000fd4b  lea     rdx, [rbp+var_48]
0x18000fd4f  mov     rcx, [r14]
0x18000fd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd57  test    eax, eax
0x18000fd59  jnz     short loc_18000FD74
0x18000fd5b  mov     rcx, [rbp+var_48]
0x18000fd5f  mov     rax, [rcx]
0x18000fd62  mov     r8, r12
0x18000fd65  mov     rdx, r15
0x18000fd68  mov     rax, [rax]
0x18000fd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd70  test    eax, eax
0x18000fd72  jz      short loc_18000FD90
0x18000fd74  cmp     [rbp+var_48], r13
0x18000fd78  jz      short loc_18000FD83
0x18000fd7a  lea     rcx, [rbp+var_48]
0x18000fd7e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fd83  mov     rcx, rdi; hLibModule
0x18000fd86  call    WINRT_IMPL_FreeLibrary
0x18000fd8b  jmp     loc_18000FCC3
0x18000fd90  mov     [rsi], r13d
0x18000fd93  cmp     [rbp+var_48], r13
0x18000fd97  jz      short loc_18000FDB1
0x18000fd99  lea     rcx, [rbp+var_48]
0x18000fd9d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fda2  jmp     short loc_18000FDB1
0x18000fda4  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000fda8  xor     ecx, ecx; dwReserved
0x18000fdaa  call    SetErrorInfo_0
0x18000fdaf  mov     [rsi], ebx
0x18000fdb1  lea     rcx, [rbp+lpLibFileName]
0x18000fdb5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fdba  cmp     [rbp+pperrinfo], r13
0x18000fdbe  jz      short loc_18000FDC9
0x18000fdc0  lea     rcx, [rbp+pperrinfo]
0x18000fdc4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fdc9  mov     rax, rsi
0x18000fdcc  mov     rcx, [rbp+var_18]
0x18000fdd0  xor     rcx, rsp; StackCookie
0x18000fdd3  call    __security_check_cookie
0x18000fdd8  add     rsp, 68h
0x18000fddc  pop     r15
0x18000fdde  pop     r14
0x18000fde0  pop     r13
0x18000fde2  pop     r12
0x18000fde4  pop     rdi
0x18000fde5  pop     rsi
0x18000fde6  pop     rbx
0x18000fde7  pop     rbp
0x18000fde8  retn
```
