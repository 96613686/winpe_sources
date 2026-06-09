# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180006460`
- end: `0x18000666e`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `526`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `8`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006400`
- `0x18001218c`
- `0x180015824`
- `0x18001787c`
- `0x1800178dc`
- `0x180025768`
- `0x1800258b4`
- `0x180032f74`

## callees

- `0x180002d40`
- `0x180003b4c`
- `0x180004428`
- `0x180004434`
- `0x180004645`
- `0x180004651`
- `0x18000468d`
- `0x180004a0c`
- `0x1800061ec`
- `0x180006460`
- `0x18000f8a8`
- `0x18000f97c`
- `0x180010ef0`
- `0x1800115a4`
- `0x180048010`

## string_xrefs

- `0x1800064c3`: `combase.dll`
- `0x1800065b0`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // r8
  LPCWSTR *v13; // rcx
  __int64 v14; // rax
  const WCHAR *v15; // rcx
  HMODULE v16; // rdi
  FARPROC v17; // rax
  unsigned int (__fastcall ***v19)(_QWORD, __int64, __int64); // [rsp+20h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h]
  unsigned __int64 v23; // [rsp+48h] [rbp-18h]

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
    v19 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v19);
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
      v13 = lpLibFileName;
      if ( v23 > 7 )
        v13 = (LPCWSTR *)lpLibFileName[0];
      v14 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v13, v22, v12, 46);
      if ( v14 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_25;
      }
      std::wstring::resize(lpLibFileName, v14);
      std::wstring::append(lpLibFileName, L".dll");
      v15 = (const WCHAR *)lpLibFileName;
      if ( v23 > 7 )
        v15 = lpLibFileName[0];
      v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, v22 - 4);
    }
    while ( !v16 );
    v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
    if ( v17 )
      break;
LABEL_21:
    WINRT_IMPL_FreeLibrary(v16);
  }
  v19 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v17)(*a2, &v19)
    || (**v19)(v19, a3, a4) )
  {
    if ( v19 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
    goto LABEL_21;
  }
  *a1 = 0;
  if ( v19 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
LABEL_25:
  std::wstring::_Tidy_deallocate(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180006460  push    rbp
0x180006462  push    rbx
0x180006463  push    rsi
0x180006464  push    rdi
0x180006465  push    r12
0x180006467  push    r14
0x180006469  push    r15
0x18000646b  mov     rbp, rsp
0x18000646e  sub     rsp, 60h
0x180006472  mov     rax, cs:__security_cookie
0x180006479  xor     rax, rsp
0x18000647c  mov     [rbp+var_10], rax
0x180006480  mov     r12, r9
0x180006483  mov     r15, r8
0x180006486  mov     r14, rdx
0x180006489  mov     rsi, rcx
0x18000648c  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180006493  mov     r8, r9
0x180006496  mov     rdx, r15
0x180006499  mov     rcx, [r14]
0x18000649c  test    rax, rax
0x18000649f  jz      short loc_1800064AD
0x1800064a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a6  mov     [rsi], eax
0x1800064a8  jmp     loc_180006650
0x1800064ad  call    RoGetActivationFactory_0
0x1800064b2  mov     ebx, eax
0x1800064b4  cmp     eax, 800401F0h
0x1800064b9  jnz     short loc_18000650F
0x1800064bb  xor     edx, edx; hFile
0x1800064bd  mov     r8d, 1000h; dwFlags
0x1800064c3  lea     rcx, LibFileName; "combase.dll"
0x1800064ca  call    LoadLibraryExW_0
0x1800064cf  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x1800064d6  mov     rcx, rax; hModule
0x1800064d9  call    WINRT_IMPL_GetProcAddress
0x1800064de  test    rax, rax
0x1800064e1  jnz     short loc_1800064EE
0x1800064e3  mov     dword ptr [rsi], 800401F0h
0x1800064e9  jmp     loc_180006650
0x1800064ee  mov     [rbp+var_40], 0
0x1800064f6  lea     rcx, [rbp+var_40]
0x1800064fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ff  mov     r8, r12
0x180006502  mov     rdx, r15
0x180006505  mov     rcx, [r14]
0x180006508  call    RoGetActivationFactory_0
0x18000650d  mov     ebx, eax
0x18000650f  test    ebx, ebx
0x180006511  jnz     short loc_18000651A
0x180006513  mov     [rsi], ebx
0x180006515  jmp     loc_180006650
0x18000651a  mov     [rbp+pperrinfo], 0
0x180006522  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180006526  xor     ecx, ecx; dwReserved
0x180006528  call    GetErrorInfo_0
0x18000652d  mov     rdx, r14
0x180006530  lea     rcx, [rbp+lpLibFileName]
0x180006534  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180006539  lea     rcx, [rbp+lpLibFileName]
0x18000653d  cmp     [rbp+var_18], 7
0x180006542  cmova   rcx, [rbp+lpLibFileName]
0x180006547  mov     r9d, 2Eh ; '.'
0x18000654d  mov     rdx, [rbp+var_20]
0x180006551  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180006556  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000655a  jz      loc_18000662A
0x180006560  mov     rdx, rax
0x180006563  lea     rcx, [rbp+lpLibFileName]
0x180006567  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000656c  lea     rdx, aDll; ".dll"
0x180006573  lea     rcx, [rbp+lpLibFileName]
0x180006577  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000657c  lea     rcx, [rbp+lpLibFileName]
0x180006580  cmp     [rbp+var_18], 7
0x180006585  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000658a  xor     edx, edx; hFile
0x18000658c  mov     r8d, 1000h; dwFlags
0x180006592  call    LoadLibraryExW_0
0x180006597  mov     rdi, rax
0x18000659a  mov     rdx, [rbp+var_20]
0x18000659e  add     rdx, 0FFFFFFFFFFFFFFFCh
0x1800065a2  lea     rcx, [rbp+lpLibFileName]
0x1800065a6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800065ab  test    rdi, rdi
0x1800065ae  jz      short loc_180006539
0x1800065b0  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x1800065b7  mov     rcx, rdi; hModule
0x1800065ba  call    WINRT_IMPL_GetProcAddress
0x1800065bf  test    rax, rax
0x1800065c2  jz      short loc_180006605
0x1800065c4  mov     [rbp+var_40], 0
0x1800065cc  lea     rdx, [rbp+var_40]
0x1800065d0  mov     rcx, [r14]
0x1800065d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d8  test    eax, eax
0x1800065da  jnz     short loc_1800065F5
0x1800065dc  mov     rcx, [rbp+var_40]
0x1800065e0  mov     rax, [rcx]
0x1800065e3  mov     r8, r12
0x1800065e6  mov     rdx, r15
0x1800065e9  mov     rax, [rax]
0x1800065ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f1  test    eax, eax
0x1800065f3  jz      short loc_180006612
0x1800065f5  cmp     [rbp+var_40], 0
0x1800065fa  jz      short loc_180006605
0x1800065fc  lea     rcx, [rbp+var_40]
0x180006600  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006605  mov     rcx, rdi; hLibModule
0x180006608  call    WINRT_IMPL_FreeLibrary
0x18000660d  jmp     loc_180006539
0x180006612  mov     dword ptr [rsi], 0
0x180006618  cmp     [rbp+var_40], 0
0x18000661d  jz      short loc_180006637
0x18000661f  lea     rcx, [rbp+var_40]
0x180006623  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006628  jmp     short loc_180006637
0x18000662a  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000662e  xor     ecx, ecx; dwReserved
0x180006630  call    SetErrorInfo_0
0x180006635  mov     [rsi], ebx
0x180006637  lea     rcx, [rbp+lpLibFileName]
0x18000663b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180006640  cmp     [rbp+pperrinfo], 0
0x180006645  jz      short loc_180006650
0x180006647  lea     rcx, [rbp+pperrinfo]
0x18000664b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006650  mov     rax, rsi
0x180006653  mov     rcx, [rbp+var_10]
0x180006657  xor     rcx, rsp; StackCookie
0x18000665a  call    __security_check_cookie
0x18000665f  add     rsp, 60h
0x180006663  pop     r15
0x180006665  pop     r14
0x180006667  pop     r12
0x180006669  pop     rdi
0x18000666a  pop     rsi
0x18000666b  pop     rbx
0x18000666c  pop     rbp
0x18000666d  retn
```
