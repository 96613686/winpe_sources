# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x140013170`
- end: `0x1400133e8`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `632`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `6`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012b5c`
- `0x140021fe0`
- `0x1400221d0`
- `0x140022678`
- `0x140028558`
- `0x1400392b0`

## callees

- `0x140005150`
- `0x1400054c0`
- `0x1400061dc`
- `0x140006224`
- `0x140006230`
- `0x1400062bc`
- `0x1400062e0`
- `0x140006304`
- `0x1400072d4`
- `0x140007c20`
- `0x14000cc2c`
- `0x140013170`
- `0x14001487c`
- `0x14001f64c`
- `0x14005a010`

## string_xrefs

- `0x1400131d8`: `combase.dll`
- `0x140013324`: `DllGetActivationFactory`

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
  unsigned __int64 v14; // r8
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
    v13 = &S2;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>((char **)lpLibFileName, v13, v14);
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
0x140013170  push    rbp
0x140013172  push    rbx
0x140013173  push    rsi
0x140013174  push    rdi
0x140013175  push    r12
0x140013177  push    r13
0x140013179  push    r14
0x14001317b  push    r15
0x14001317d  mov     rbp, rsp
0x140013180  sub     rsp, 68h
0x140013184  mov     rax, cs:__security_cookie
0x14001318b  xor     rax, rsp
0x14001318e  mov     [rbp+var_18], rax
0x140013192  mov     r13, r9
0x140013195  mov     r12, r8
0x140013198  mov     r15, rdx
0x14001319b  mov     rsi, rcx
0x14001319e  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x1400131a5  xor     r14d, r14d
0x1400131a8  mov     r8, r9
0x1400131ab  mov     rdx, r12
0x1400131ae  mov     rcx, [r15]
0x1400131b1  test    rax, rax
0x1400131b4  jz      short loc_1400131C2
0x1400131b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131bb  mov     [rsi], eax
0x1400131bd  jmp     loc_1400133C8
0x1400131c2  call    RoGetActivationFactory_0
0x1400131c7  mov     ebx, eax
0x1400131c9  cmp     eax, 800401F0h
0x1400131ce  jnz     short loc_140013220
0x1400131d0  xor     edx, edx; hFile
0x1400131d2  mov     r8d, 1000h; dwFlags
0x1400131d8  lea     rcx, LibFileName; "combase.dll"
0x1400131df  call    LoadLibraryExW_0
0x1400131e4  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x1400131eb  mov     rcx, rax; hModule
0x1400131ee  call    WINRT_IMPL_GetProcAddress
0x1400131f3  test    rax, rax
0x1400131f6  jnz     short loc_140013203
0x1400131f8  mov     dword ptr [rsi], 800401F0h
0x1400131fe  jmp     loc_1400133C8
0x140013203  mov     [rbp+var_48], r14
0x140013207  lea     rcx, [rbp+var_48]
0x14001320b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013210  mov     r8, r13
0x140013213  mov     rdx, r12
0x140013216  mov     rcx, [r15]
0x140013219  call    RoGetActivationFactory_0
0x14001321e  mov     ebx, eax
0x140013220  test    ebx, ebx
0x140013222  jnz     short loc_14001322C
0x140013224  mov     [rsi], r14d
0x140013227  jmp     loc_1400133C8
0x14001322c  mov     [rbp+pperrinfo], r14
0x140013230  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x140013234  xor     ecx, ecx; dwReserved
0x140013236  call    GetErrorInfo_0
0x14001323b  xorps   xmm0, xmm0
0x14001323e  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x140013242  mov     [rbp+var_28], r14
0x140013246  mov     [rbp+var_20], r14
0x14001324a  mov     rax, [r15]
0x14001324d  test    rax, rax
0x140013250  jz      short loc_14001325C
0x140013252  mov     rdx, [rax+10h]
0x140013256  mov     r8d, [rax+4]
0x14001325a  jmp     short loc_140013266
0x14001325c  lea     rdx, S2
0x140013263  mov     r8, r14
0x140013266  lea     rcx, [rbp+lpLibFileName]
0x14001326a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001326f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140013273  mov     rax, [rbp+var_28]
0x140013277  lea     r14, [rbp+lpLibFileName]
0x14001327b  cmp     [rbp+var_20], 7
0x140013280  cmova   r14, [rbp+lpLibFileName]
0x140013285  test    rax, rax
0x140013288  jz      loc_1400133A2
0x14001328e  dec     rax
0x140013291  cmp     rax, rcx
0x140013294  cmovnb  rax, rcx
0x140013298  inc     rax
0x14001329b  lea     rdi, [r14+rax*2]
0x14001329f  mov     r8d, 2Eh ; '.'
0x1400132a5  mov     rdx, rdi
0x1400132a8  mov     rcx, r14
0x1400132ab  call    __std_find_last_trivial_2
0x1400132b0  cmp     rax, rdi
0x1400132b3  jz      loc_1400133A2
0x1400132b9  sub     rax, r14
0x1400132bc  sar     rax, 1
0x1400132bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400132c3  jz      loc_1400133A2
0x1400132c9  mov     rdx, rax
0x1400132cc  lea     rcx, [rbp+lpLibFileName]; Src
0x1400132d0  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400132d5  lea     rdx, aDll; ".dll"
0x1400132dc  lea     rcx, [rbp+lpLibFileName]; Src
0x1400132e0  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400132e5  lea     rcx, [rbp+lpLibFileName]
0x1400132e9  cmp     [rbp+var_20], 7
0x1400132ee  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1400132f3  xor     edx, edx; hFile
0x1400132f5  mov     r8d, 1000h; dwFlags
0x1400132fb  call    LoadLibraryExW_0
0x140013300  mov     rdi, rax
0x140013303  mov     rdx, [rbp+var_28]
0x140013307  add     rdx, 0FFFFFFFFFFFFFFFCh
0x14001330b  lea     rcx, [rbp+lpLibFileName]; Src
0x14001330f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140013314  xor     r14d, r14d
0x140013317  test    rdi, rdi
0x14001331a  lea     rcx, [r14-1]
0x14001331e  jz      loc_140013273
0x140013324  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x14001332b  mov     rcx, rdi; hModule
0x14001332e  call    WINRT_IMPL_GetProcAddress
0x140013333  test    rax, rax
0x140013336  jz      short loc_140013374
0x140013338  mov     [rbp+var_48], r14
0x14001333c  lea     rdx, [rbp+var_48]
0x140013340  mov     rcx, [r15]
0x140013343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013348  test    eax, eax
0x14001334a  jnz     short loc_140013365
0x14001334c  mov     rcx, [rbp+var_48]
0x140013350  mov     rax, [rcx]
0x140013353  mov     r8, r13
0x140013356  mov     rdx, r12
0x140013359  mov     rax, [rax]
0x14001335c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013361  test    eax, eax
0x140013363  jz      short loc_140013381
0x140013365  cmp     [rbp+var_48], r14
0x140013369  jz      short loc_140013374
0x14001336b  lea     rcx, [rbp+var_48]
0x14001336f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140013374  mov     rcx, rdi; hLibModule
0x140013377  call    WINRT_IMPL_FreeLibrary
0x14001337c  jmp     loc_14001326F
0x140013381  mov     [rsi], r14d
0x140013384  cmp     [rbp+var_48], r14
0x140013388  jz      short loc_140013393
0x14001338a  lea     rcx, [rbp+var_48]
0x14001338e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140013393  lea     rcx, [rbp+lpLibFileName]; void *
0x140013397  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001339c  cmp     [rbp+pperrinfo], r14
0x1400133a0  jmp     short loc_1400133BD
0x1400133a2  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1400133a6  xor     ecx, ecx; dwReserved
0x1400133a8  call    SetErrorInfo_0
0x1400133ad  mov     [rsi], ebx
0x1400133af  lea     rcx, [rbp+lpLibFileName]; void *
0x1400133b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400133b8  cmp     [rbp+pperrinfo], 0
0x1400133bd  jz      short loc_1400133C8
0x1400133bf  lea     rcx, [rbp+pperrinfo]
0x1400133c3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400133c8  mov     rax, rsi
0x1400133cb  mov     rcx, [rbp+var_18]
0x1400133cf  xor     rcx, rsp; StackCookie
0x1400133d2  call    __security_check_cookie
0x1400133d7  add     rsp, 68h
0x1400133db  pop     r15
0x1400133dd  pop     r14
0x1400133df  pop     r13
0x1400133e1  pop     r12
0x1400133e3  pop     rdi
0x1400133e4  pop     rsi
0x1400133e5  pop     rbx
0x1400133e6  pop     rbp
0x1400133e7  retn
```
