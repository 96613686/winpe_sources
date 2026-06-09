# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180013a40`
- end: `0x180013cb8`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `632`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800139d4`
- `0x18001bab4`
- `0x18001c508`
- `0x1800216e8`

## callees

- `0x180004ac0`
- `0x180005020`
- `0x180005f98`
- `0x180005fb0`
- `0x180005fc8`
- `0x180006001`
- `0x180006019`
- `0x18000603d`
- `0x18000d430`
- `0x180010b94`
- `0x180013118`
- `0x180013a40`
- `0x180015144`
- `0x18001a42c`
- `0x18005e010`

## string_xrefs

- `0x180013aa8`: `combase.dll`
- `0x180013bf4`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR *v12; // r14
  char *v13; // rdi
  __int64 last_trivial_2; // rax
  const WCHAR *v15; // rcx
  HMODULE v16; // rdi
  FARPROC v17; // rax
  bool v18; // zf
  unsigned int (__fastcall ***v20)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v23; // [rsp+40h] [rbp-28h]
  unsigned __int64 v24; // [rsp+48h] [rbp-20h]

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
    v20 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v20);
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
  v23 = 0;
  v24 = 0;
  std::wstring::_Construct<1,unsigned short const *>(lpLibFileName);
  while ( 1 )
  {
    do
    {
      v12 = lpLibFileName;
      if ( v24 > 7 )
        v12 = (LPCWSTR *)lpLibFileName[0];
      if ( !v23
        || (v13 = (char *)v12 + 2 * v23,
            last_trivial_2 = _std_find_last_trivial_2(v12, v13, 46),
            (char *)last_trivial_2 == v13)
        || (last_trivial_2 - (__int64)v12) >> 1 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::~wstring(lpLibFileName);
        v18 = pperrinfo == 0;
        goto LABEL_28;
      }
      std::wstring::resize(lpLibFileName);
      std::wstring::operator+=(lpLibFileName, L".dll");
      v15 = (const WCHAR *)lpLibFileName;
      if ( v24 > 7 )
        v15 = lpLibFileName[0];
      v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
      std::wstring::resize(lpLibFileName);
    }
    while ( !v16 );
    v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
    if ( v17 )
      break;
LABEL_23:
    WINRT_IMPL_FreeLibrary(v16);
  }
  v20 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v17)(*a2, &v20)
    || (**v20)(v20, a3, a4) )
  {
    if ( v20 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
    goto LABEL_23;
  }
  *a1 = 0;
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  std::wstring::~wstring(lpLibFileName);
  v18 = pperrinfo == 0;
LABEL_28:
  if ( !v18 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180013a40  push    rbp
0x180013a42  push    rbx
0x180013a43  push    rsi
0x180013a44  push    rdi
0x180013a45  push    r12
0x180013a47  push    r13
0x180013a49  push    r14
0x180013a4b  push    r15
0x180013a4d  mov     rbp, rsp
0x180013a50  sub     rsp, 68h
0x180013a54  mov     rax, cs:__security_cookie
0x180013a5b  xor     rax, rsp
0x180013a5e  mov     [rbp+var_18], rax
0x180013a62  mov     r13, r9
0x180013a65  mov     r12, r8
0x180013a68  mov     r15, rdx
0x180013a6b  mov     rsi, rcx
0x180013a6e  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180013a75  xor     r14d, r14d
0x180013a78  mov     r8, r9
0x180013a7b  mov     rdx, r12
0x180013a7e  mov     rcx, [r15]
0x180013a81  test    rax, rax
0x180013a84  jz      short loc_180013A92
0x180013a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a8b  mov     [rsi], eax
0x180013a8d  jmp     loc_180013C98
0x180013a92  call    RoGetActivationFactory_0
0x180013a97  mov     ebx, eax
0x180013a99  cmp     eax, 800401F0h
0x180013a9e  jnz     short loc_180013AF0
0x180013aa0  xor     edx, edx; hFile
0x180013aa2  mov     r8d, 1000h; dwFlags
0x180013aa8  lea     rcx, aCombaseDll; "combase.dll"
0x180013aaf  call    LoadLibraryExW_0
0x180013ab4  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180013abb  mov     rcx, rax; hModule
0x180013abe  call    WINRT_IMPL_GetProcAddress
0x180013ac3  test    rax, rax
0x180013ac6  jnz     short loc_180013AD3
0x180013ac8  mov     dword ptr [rsi], 800401F0h
0x180013ace  jmp     loc_180013C98
0x180013ad3  mov     [rbp+var_48], r14
0x180013ad7  lea     rcx, [rbp+var_48]
0x180013adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ae0  mov     r8, r13
0x180013ae3  mov     rdx, r12
0x180013ae6  mov     rcx, [r15]
0x180013ae9  call    RoGetActivationFactory_0
0x180013aee  mov     ebx, eax
0x180013af0  test    ebx, ebx
0x180013af2  jnz     short loc_180013AFC
0x180013af4  mov     [rsi], r14d
0x180013af7  jmp     loc_180013C98
0x180013afc  mov     [rbp+pperrinfo], r14
0x180013b00  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180013b04  xor     ecx, ecx; dwReserved
0x180013b06  call    GetErrorInfo_0
0x180013b0b  xorps   xmm0, xmm0
0x180013b0e  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180013b12  mov     [rbp+var_28], r14
0x180013b16  mov     [rbp+var_20], r14
0x180013b1a  mov     rax, [r15]
0x180013b1d  test    rax, rax
0x180013b20  jz      short loc_180013B2C
0x180013b22  mov     rdx, [rax+10h]
0x180013b26  mov     r8d, [rax+4]
0x180013b2a  jmp     short loc_180013B36
0x180013b2c  lea     rdx, S1
0x180013b33  mov     r8, r14
0x180013b36  lea     rcx, [rbp+lpLibFileName]
0x180013b3a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013b3f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013b43  mov     rax, [rbp+var_28]
0x180013b47  lea     r14, [rbp+lpLibFileName]
0x180013b4b  cmp     [rbp+var_20], 7
0x180013b50  cmova   r14, [rbp+lpLibFileName]
0x180013b55  test    rax, rax
0x180013b58  jz      loc_180013C72
0x180013b5e  dec     rax
0x180013b61  cmp     rax, rcx
0x180013b64  cmovnb  rax, rcx
0x180013b68  inc     rax
0x180013b6b  lea     rdi, [r14+rax*2]
0x180013b6f  mov     r8d, 2Eh ; '.'
0x180013b75  mov     rdx, rdi
0x180013b78  mov     rcx, r14
0x180013b7b  call    __std_find_last_trivial_2
0x180013b80  cmp     rax, rdi
0x180013b83  jz      loc_180013C72
0x180013b89  sub     rax, r14
0x180013b8c  sar     rax, 1
0x180013b8f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013b93  jz      loc_180013C72
0x180013b99  mov     rdx, rax
0x180013b9c  lea     rcx, [rbp+lpLibFileName]; Src
0x180013ba0  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180013ba5  lea     rdx, aDll; ".dll"
0x180013bac  lea     rcx, [rbp+lpLibFileName]; Src
0x180013bb0  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180013bb5  lea     rcx, [rbp+lpLibFileName]
0x180013bb9  cmp     [rbp+var_20], 7
0x180013bbe  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180013bc3  xor     edx, edx; hFile
0x180013bc5  mov     r8d, 1000h; dwFlags
0x180013bcb  call    LoadLibraryExW_0
0x180013bd0  mov     rdi, rax
0x180013bd3  mov     rdx, [rbp+var_28]
0x180013bd7  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180013bdb  lea     rcx, [rbp+lpLibFileName]; Src
0x180013bdf  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180013be4  xor     r14d, r14d
0x180013be7  test    rdi, rdi
0x180013bea  lea     rcx, [r14-1]
0x180013bee  jz      loc_180013B43
0x180013bf4  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x180013bfb  mov     rcx, rdi; hModule
0x180013bfe  call    WINRT_IMPL_GetProcAddress
0x180013c03  test    rax, rax
0x180013c06  jz      short loc_180013C44
0x180013c08  mov     [rbp+var_48], r14
0x180013c0c  lea     rdx, [rbp+var_48]
0x180013c10  mov     rcx, [r15]
0x180013c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c18  test    eax, eax
0x180013c1a  jnz     short loc_180013C35
0x180013c1c  mov     rcx, [rbp+var_48]
0x180013c20  mov     rax, [rcx]
0x180013c23  mov     r8, r13
0x180013c26  mov     rdx, r12
0x180013c29  mov     rax, [rax]
0x180013c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c31  test    eax, eax
0x180013c33  jz      short loc_180013C51
0x180013c35  cmp     [rbp+var_48], r14
0x180013c39  jz      short loc_180013C44
0x180013c3b  lea     rcx, [rbp+var_48]
0x180013c3f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013c44  mov     rcx, rdi; hLibModule
0x180013c47  call    WINRT_IMPL_FreeLibrary
0x180013c4c  jmp     loc_180013B3F
0x180013c51  mov     [rsi], r14d
0x180013c54  cmp     [rbp+var_48], r14
0x180013c58  jz      short loc_180013C63
0x180013c5a  lea     rcx, [rbp+var_48]
0x180013c5e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013c63  lea     rcx, [rbp+lpLibFileName]; void *
0x180013c67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013c6c  cmp     [rbp+pperrinfo], r14
0x180013c70  jmp     short loc_180013C8D
0x180013c72  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180013c76  xor     ecx, ecx; dwReserved
0x180013c78  call    SetErrorInfo_0
0x180013c7d  mov     [rsi], ebx
0x180013c7f  lea     rcx, [rbp+lpLibFileName]; void *
0x180013c83  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013c88  cmp     [rbp+pperrinfo], 0
0x180013c8d  jz      short loc_180013C98
0x180013c8f  lea     rcx, [rbp+pperrinfo]
0x180013c93  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013c98  mov     rax, rsi
0x180013c9b  mov     rcx, [rbp+var_18]
0x180013c9f  xor     rcx, rsp; StackCookie
0x180013ca2  call    __security_check_cookie
0x180013ca7  add     rsp, 68h
0x180013cab  pop     r15
0x180013cad  pop     r14
0x180013caf  pop     r13
0x180013cb1  pop     r12
0x180013cb3  pop     rdi
0x180013cb4  pop     rsi
0x180013cb5  pop     rbx
0x180013cb6  pop     rbp
0x180013cb7  retn
```
