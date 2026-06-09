# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800130d0`
- end: `0x18001338f`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `703`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012f70`
- `0x18001bea8`
- `0x18001c250`
- `0x18001c428`

## callees

- `0x1800034d0`
- `0x1800038f0`
- `0x180004778`
- `0x180004790`
- `0x18000479c`
- `0x1800047d5`
- `0x1800047f9`
- `0x180004805`
- `0x18000bf6c`
- `0x18000cb48`
- `0x180012090`
- `0x180012e20`
- `0x1800130d0`
- `0x18001a798`
- `0x180021010`

## string_xrefs

- `0x180013138`: `combase.dll`
- `0x1800132cb`: `DllGetActivationFactory`

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
0x1800130d0  push    rbp
0x1800130d2  push    rbx
0x1800130d3  push    rsi
0x1800130d4  push    rdi
0x1800130d5  push    r12
0x1800130d7  push    r13
0x1800130d9  push    r14
0x1800130db  push    r15
0x1800130dd  mov     rbp, rsp
0x1800130e0  sub     rsp, 78h
0x1800130e4  mov     rax, cs:__security_cookie
0x1800130eb  xor     rax, rsp
0x1800130ee  mov     [rbp+var_18], rax
0x1800130f2  mov     r13, r9
0x1800130f5  mov     r12, r8
0x1800130f8  mov     r15, rdx
0x1800130fb  mov     rsi, rcx
0x1800130fe  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180013105  xor     r14d, r14d
0x180013108  mov     r8, r9
0x18001310b  mov     rdx, r12
0x18001310e  mov     rcx, [r15]
0x180013111  test    rax, rax
0x180013114  jz      short loc_180013122
0x180013116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001311b  mov     [rsi], eax
0x18001311d  jmp     loc_18001336F
0x180013122  call    RoGetActivationFactory_0
0x180013127  mov     edi, eax
0x180013129  cmp     eax, 800401F0h
0x18001312e  jnz     short loc_180013180
0x180013130  xor     edx, edx; hFile
0x180013132  mov     r8d, 1000h; dwFlags
0x180013138  lea     rcx, aCombaseDll; "combase.dll"
0x18001313f  call    LoadLibraryExW_0
0x180013144  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001314b  mov     rcx, rax; hModule
0x18001314e  call    WINRT_IMPL_GetProcAddress
0x180013153  test    rax, rax
0x180013156  jnz     short loc_180013163
0x180013158  mov     dword ptr [rsi], 800401F0h
0x18001315e  jmp     loc_18001336F
0x180013163  mov     [rbp+var_48], r14
0x180013167  lea     rcx, [rbp+var_48]
0x18001316b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013170  mov     r8, r13
0x180013173  mov     rdx, r12
0x180013176  mov     rcx, [r15]
0x180013179  call    RoGetActivationFactory_0
0x18001317e  mov     edi, eax
0x180013180  test    edi, edi
0x180013182  jnz     short loc_18001318C
0x180013184  mov     [rsi], r14d
0x180013187  jmp     loc_18001336F
0x18001318c  mov     [rbp+pperrinfo], r14
0x180013190  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180013194  xor     ecx, ecx; dwReserved
0x180013196  call    GetErrorInfo_0
0x18001319b  xorps   xmm0, xmm0
0x18001319e  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x1800131a2  mov     [rbp+var_28], r14
0x1800131a6  mov     [rbp+var_20], r14
0x1800131aa  mov     rax, [r15]
0x1800131ad  test    rax, rax
0x1800131b0  jz      short loc_1800131BC
0x1800131b2  mov     rdx, [rax+10h]
0x1800131b6  mov     r8d, [rax+4]
0x1800131ba  jmp     short loc_1800131C6
0x1800131bc  lea     rdx, S2
0x1800131c3  mov     r8, r14
0x1800131c6  lea     rcx, [rbp+lpLibFileName]
0x1800131ca  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800131cf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800131d3  mov     rax, [rbp+var_28]
0x1800131d7  lea     r14, [rbp+lpLibFileName]
0x1800131db  cmp     [rbp+var_20], 7
0x1800131e0  cmova   r14, [rbp+lpLibFileName]
0x1800131e5  test    rax, rax
0x1800131e8  jz      loc_180013349
0x1800131ee  dec     rax
0x1800131f1  cmp     rax, rcx
0x1800131f4  cmovnb  rax, rcx
0x1800131f8  inc     rax
0x1800131fb  lea     rbx, [r14+rax*2]
0x1800131ff  mov     r8d, 2Eh ; '.'
0x180013205  mov     rdx, rbx
0x180013208  mov     rcx, r14
0x18001320b  call    __std_find_last_trivial_2
0x180013210  cmp     rax, rbx
0x180013213  jz      loc_180013349
0x180013219  sub     rax, r14
0x18001321c  sar     rax, 1
0x18001321f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013223  jz      loc_180013349
0x180013229  mov     rdx, rax
0x18001322c  lea     rcx, [rbp+lpLibFileName]; Src
0x180013230  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180013235  mov     r8, [rbp+var_28]
0x180013239  mov     rax, [rbp+var_20]
0x18001323d  sub     rax, r8
0x180013240  mov     ecx, 4
0x180013245  cmp     rax, rcx
0x180013248  jb      short loc_180013278
0x18001324a  lea     rdx, [r8+4]
0x18001324e  mov     [rbp+var_28], rdx
0x180013252  lea     rcx, [rbp+lpLibFileName]
0x180013256  cmp     [rbp+var_20], 7
0x18001325b  cmova   rcx, [rbp+lpLibFileName]
0x180013260  mov     rax, 6C006C0064002Eh
0x18001326a  mov     [rcx+r8*2], rax
0x18001326e  xor     r14d, r14d
0x180013271  mov     [rcx+rdx*2], r14w
0x180013276  jmp     short loc_18001328C
0x180013278  mov     [rsp+78h+var_58], rcx; __int64
0x18001327d  mov     rdx, rcx
0x180013280  lea     rcx, [rbp+lpLibFileName]; Src
0x180013284  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180013289  xor     r14d, r14d
0x18001328c  lea     rcx, [rbp+lpLibFileName]
0x180013290  cmp     [rbp+var_20], 7
0x180013295  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001329a  xor     edx, edx; hFile
0x18001329c  mov     r8d, 1000h; dwFlags
0x1800132a2  call    LoadLibraryExW_0
0x1800132a7  mov     rbx, rax
0x1800132aa  mov     rdx, [rbp+var_28]
0x1800132ae  add     rdx, 0FFFFFFFFFFFFFFFCh
0x1800132b2  lea     rcx, [rbp+lpLibFileName]; Src
0x1800132b6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800132bb  test    rbx, rbx
0x1800132be  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800132c5  jz      loc_1800131D3
0x1800132cb  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1800132d2  mov     rcx, rbx; hModule
0x1800132d5  call    WINRT_IMPL_GetProcAddress
0x1800132da  test    rax, rax
0x1800132dd  jz      short loc_18001331B
0x1800132df  mov     [rbp+var_48], r14
0x1800132e3  lea     rdx, [rbp+var_48]
0x1800132e7  mov     rcx, [r15]
0x1800132ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ef  test    eax, eax
0x1800132f1  jnz     short loc_18001330C
0x1800132f3  mov     rcx, [rbp+var_48]
0x1800132f7  mov     rax, [rcx]
0x1800132fa  mov     r8, r13
0x1800132fd  mov     rdx, r12
0x180013300  mov     rax, [rax]
0x180013303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013308  test    eax, eax
0x18001330a  jz      short loc_180013328
0x18001330c  cmp     [rbp+var_48], r14
0x180013310  jz      short loc_18001331B
0x180013312  lea     rcx, [rbp+var_48]
0x180013316  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001331b  mov     rcx, rbx; hLibModule
0x18001331e  call    WINRT_IMPL_FreeLibrary
0x180013323  jmp     loc_1800131CF
0x180013328  mov     [rsi], r14d
0x18001332b  cmp     [rbp+var_48], r14
0x18001332f  jz      short loc_18001333A
0x180013331  lea     rcx, [rbp+var_48]
0x180013335  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001333a  lea     rcx, [rbp+lpLibFileName]
0x18001333e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013343  cmp     [rbp+pperrinfo], r14
0x180013347  jmp     short loc_180013364
0x180013349  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001334d  xor     ecx, ecx; dwReserved
0x18001334f  call    SetErrorInfo_0
0x180013354  mov     [rsi], edi
0x180013356  lea     rcx, [rbp+lpLibFileName]
0x18001335a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001335f  cmp     [rbp+pperrinfo], 0
0x180013364  jz      short loc_18001336F
0x180013366  lea     rcx, [rbp+pperrinfo]
0x18001336a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001336f  mov     rax, rsi
0x180013372  mov     rcx, [rbp+var_18]
0x180013376  xor     rcx, rsp; StackCookie
0x180013379  call    __security_check_cookie
0x18001337e  add     rsp, 78h
0x180013382  pop     r15
0x180013384  pop     r14
0x180013386  pop     r13
0x180013388  pop     r12
0x18001338a  pop     rdi
0x18001338b  pop     rsi
0x18001338c  pop     rbx
0x18001338d  pop     rbp
0x18001338e  retn
```
