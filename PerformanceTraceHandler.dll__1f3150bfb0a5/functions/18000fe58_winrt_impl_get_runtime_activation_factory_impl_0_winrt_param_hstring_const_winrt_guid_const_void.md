# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000fe58`
- end: `0x180010052`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `506`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f73c`
- `0x18000f888`
- `0x18000f9d4`

## callees

- `0x180002c00`
- `0x180003865`
- `0x18000387d`
- `0x180003889`
- `0x180003895`
- `0x1800038ad`
- `0x1800038d1`
- `0x180009c74`
- `0x18000eea8`
- `0x18000fe58`
- `0x180012c9c`
- `0x180012d18`
- `0x180013454`
- `0x1800134d0`
- `0x18001c010`

## string_xrefs

- `0x18000febb`: `combase.dll`
- `0x18000ff94`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  HMODULE v14; // rdi
  FARPROC v15; // rax
  unsigned int (__fastcall ***v17)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[4]; // [rsp+30h] [rbp-30h] BYREF

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
    v17 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v17);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(lpLibFileName, a2);
  while ( 1 )
  {
    do
    {
      v12 = std::wstring::rfind(lpLibFileName);
      if ( v12 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_23;
      }
      std::wstring::resize(lpLibFileName, v12);
      std::wstring::append(lpLibFileName, L".dll");
      v13 = (const WCHAR *)lpLibFileName;
      if ( lpLibFileName[3] > (LPCWSTR)7 )
        v13 = lpLibFileName[0];
      v14 = LoadLibraryExW_0(v13, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, lpLibFileName[2] - 2);
    }
    while ( !v14 );
    v15 = WINRT_IMPL_GetProcAddress(v14, "DllGetActivationFactory");
    if ( v15 )
      break;
LABEL_19:
    WINRT_IMPL_FreeLibrary(v14);
  }
  v17 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v15)(*a2, &v17)
    || (**v17)(v17, a3, a4) )
  {
    if ( v17 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v17);
    goto LABEL_19;
  }
  *a1 = 0;
  if ( v17 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v17);
LABEL_23:
  std::wstring::_Tidy_deallocate(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000fe58  push    rbp
0x18000fe5a  push    rbx
0x18000fe5b  push    rsi
0x18000fe5c  push    rdi
0x18000fe5d  push    r12
0x18000fe5f  push    r14
0x18000fe61  push    r15
0x18000fe63  mov     rbp, rsp
0x18000fe66  sub     rsp, 60h
0x18000fe6a  mov     rax, cs:__security_cookie
0x18000fe71  xor     rax, rsp
0x18000fe74  mov     [rbp+var_10], rax
0x18000fe78  mov     r12, r9
0x18000fe7b  mov     r15, r8
0x18000fe7e  mov     r14, rdx
0x18000fe81  mov     rsi, rcx
0x18000fe84  mov     rcx, [rdx]
0x18000fe87  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000fe8e  mov     r8, r9
0x18000fe91  mov     rdx, r15
0x18000fe94  test    rax, rax
0x18000fe97  jz      short loc_18000FEA5
0x18000fe99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe9e  mov     [rsi], eax
0x18000fea0  jmp     loc_180010034
0x18000fea5  call    RoGetActivationFactory_0
0x18000feaa  mov     ebx, eax
0x18000feac  cmp     eax, 800401F0h
0x18000feb1  jnz     short loc_18000FF07
0x18000feb3  xor     edx, edx; hFile
0x18000feb5  mov     r8d, 1000h; dwFlags
0x18000febb  lea     rcx, LibFileName; "combase.dll"
0x18000fec2  call    LoadLibraryExW_0
0x18000fec7  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000fece  mov     rcx, rax; hModule
0x18000fed1  call    WINRT_IMPL_GetProcAddress
0x18000fed6  test    rax, rax
0x18000fed9  jnz     short loc_18000FEE6
0x18000fedb  mov     dword ptr [rsi], 800401F0h
0x18000fee1  jmp     loc_180010034
0x18000fee6  mov     [rbp+var_40], 0
0x18000feee  lea     rcx, [rbp+var_40]
0x18000fef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fef7  mov     r8, r12
0x18000fefa  mov     rdx, r15
0x18000fefd  mov     rcx, [r14]
0x18000ff00  call    RoGetActivationFactory_0
0x18000ff05  mov     ebx, eax
0x18000ff07  test    ebx, ebx
0x18000ff09  jnz     short loc_18000FF12
0x18000ff0b  mov     [rsi], ebx
0x18000ff0d  jmp     loc_180010034
0x18000ff12  mov     [rbp+pperrinfo], 0
0x18000ff1a  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000ff1e  xor     ecx, ecx; dwReserved
0x18000ff20  call    GetErrorInfo_0
0x18000ff25  mov     rdx, r14
0x18000ff28  lea     rcx, [rbp+lpLibFileName]
0x18000ff2c  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18000ff31  lea     rcx, [rbp+lpLibFileName]
0x18000ff35  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18000ff3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ff3e  jz      loc_18001000E
0x18000ff44  mov     rdx, rax
0x18000ff47  lea     rcx, [rbp+lpLibFileName]
0x18000ff4b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000ff50  lea     rdx, aDll; ".dll"
0x18000ff57  lea     rcx, [rbp+lpLibFileName]; Src
0x18000ff5b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000ff60  lea     rcx, [rbp+lpLibFileName]
0x18000ff64  cmp     [rbp+var_18], 7
0x18000ff69  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000ff6e  xor     edx, edx; hFile
0x18000ff70  mov     r8d, 1000h; dwFlags
0x18000ff76  call    LoadLibraryExW_0
0x18000ff7b  mov     rdi, rax
0x18000ff7e  mov     rdx, [rbp+var_20]
0x18000ff82  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18000ff86  lea     rcx, [rbp+lpLibFileName]
0x18000ff8a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000ff8f  test    rdi, rdi
0x18000ff92  jz      short loc_18000FF31
0x18000ff94  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18000ff9b  mov     rcx, rdi; hModule
0x18000ff9e  call    WINRT_IMPL_GetProcAddress
0x18000ffa3  test    rax, rax
0x18000ffa6  jz      short loc_18000FFE9
0x18000ffa8  mov     [rbp+var_40], 0
0x18000ffb0  lea     rdx, [rbp+var_40]
0x18000ffb4  mov     rcx, [r14]
0x18000ffb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffbc  test    eax, eax
0x18000ffbe  jnz     short loc_18000FFD9
0x18000ffc0  mov     rcx, [rbp+var_40]
0x18000ffc4  mov     rax, [rcx]
0x18000ffc7  mov     r8, r12
0x18000ffca  mov     rdx, r15
0x18000ffcd  mov     rax, [rax]
0x18000ffd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd5  test    eax, eax
0x18000ffd7  jz      short loc_18000FFF6
0x18000ffd9  cmp     [rbp+var_40], 0
0x18000ffde  jz      short loc_18000FFE9
0x18000ffe0  lea     rcx, [rbp+var_40]
0x18000ffe4  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000ffe9  mov     rcx, rdi; hLibModule
0x18000ffec  call    WINRT_IMPL_FreeLibrary
0x18000fff1  jmp     loc_18000FF31
0x18000fff6  mov     dword ptr [rsi], 0
0x18000fffc  cmp     [rbp+var_40], 0
0x180010001  jz      short loc_18001001B
0x180010003  lea     rcx, [rbp+var_40]
0x180010007  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001000c  jmp     short loc_18001001B
0x18001000e  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180010012  xor     ecx, ecx; dwReserved
0x180010014  call    SetErrorInfo_0
0x180010019  mov     [rsi], ebx
0x18001001b  lea     rcx, [rbp+lpLibFileName]
0x18001001f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010024  cmp     [rbp+pperrinfo], 0
0x180010029  jz      short loc_180010034
0x18001002b  lea     rcx, [rbp+pperrinfo]
0x18001002f  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180010034  mov     rax, rsi
0x180010037  mov     rcx, [rbp+var_10]
0x18001003b  xor     rcx, rsp; StackCookie
0x18001003e  call    __security_check_cookie
0x180010043  add     rsp, 60h
0x180010047  pop     r15
0x180010049  pop     r14
0x18001004b  pop     r12
0x18001004d  pop     rdi
0x18001004e  pop     rsi
0x18001004f  pop     rbx
0x180010050  pop     rbp
0x180010051  retn
```
