# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800104f8`
- end: `0x18001081e`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `806`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010390`
- `0x180012674`

## callees

- `0x180002250`
- `0x180002de0`
- `0x180003380`
- `0x1800039f0`
- `0x180003a65`
- `0x180003a95`
- `0x180003ac5`
- `0x180003ad1`
- `0x180007b84`
- `0x18000c13c`
- `0x18000c37c`
- `0x1800101c0`
- `0x1800104f8`
- `0x180011704`
- `0x1800ca010`

## string_xrefs

- `0x180010560`: `combase.dll`
- `0x18001075e`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const wchar_t *v12; // rdx
  LPCWSTR *v13; // r14
  char *v14; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  LPCWSTR *v18; // rcx
  unsigned __int64 v19; // rcx
  LPCWSTR *v20; // r8
  _WORD *v21; // rdi
  const WCHAR *v22; // rcx
  HMODULE v23; // rdi
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // r8
  LPCWSTR *v26; // rcx
  FARPROC v27; // rax
  unsigned int (__fastcall ***v29)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v32; // [rsp+50h] [rbp-28h]
  unsigned __int64 v33; // [rsp+58h] [rbp-20h]

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
    v29 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v29);
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
  v32 = 0;
  v33 = 0;
  if ( *a2 )
    v12 = *(const wchar_t **)(*a2 + 16LL);
  else
    v12 = &S2;
  std::wstring::_Construct<1,wchar_t const *>(lpLibFileName, v12);
  while ( 1 )
  {
    do
    {
      v13 = lpLibFileName;
      if ( v33 > 7 )
        v13 = (LPCWSTR *)lpLibFileName[0];
      if ( !v32
        || (v14 = (char *)v13 + 2 * v32,
            last_trivial_2 = _std_find_last_trivial_2(v13, v14, 46),
            (char *)last_trivial_2 == v14)
        || (v16 = (last_trivial_2 - (__int64)v13) >> 1, v16 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_52;
      }
      v17 = v32;
      if ( v16 > v32 )
      {
        v19 = v16 - v32;
        if ( v16 - v32 > v33 - v32 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpLibFileName);
        }
        else
        {
          v32 = (last_trivial_2 - (__int64)v13) >> 1;
          v20 = lpLibFileName;
          if ( v33 > 7 )
            v20 = (LPCWSTR *)lpLibFileName[0];
          v21 = (_WORD *)v20 + v17;
          if ( v19 )
          {
            while ( v19 )
            {
              *v21++ = 0;
              --v19;
            }
          }
          *((_WORD *)v20 + v16) = 0;
        }
      }
      else
      {
        v32 = (last_trivial_2 - (__int64)v13) >> 1;
        v18 = lpLibFileName;
        if ( v33 > 7 )
          v18 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v18 + v16) = 0;
      }
      std::wstring::operator+=(lpLibFileName, L".dll");
      v22 = (const WCHAR *)lpLibFileName;
      if ( v33 > 7 )
        v22 = lpLibFileName[0];
      v23 = LoadLibraryExW_0(v22, 0, 0x1000u);
      v24 = v32;
      v25 = v32 - 4;
      v26 = lpLibFileName;
      if ( v32 >= 4 )
      {
        v32 -= 4LL;
        if ( v33 > 7 )
          v26 = (LPCWSTR *)lpLibFileName[0];
LABEL_40:
        *((_WORD *)v26 + v25) = 0;
        continue;
      }
      if ( v33 - v32 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v32 -= 4LL;
        if ( v33 > 7 )
          v26 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v26 + 2 * v24) = 0;
        goto LABEL_40;
      }
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34__K_W_Z__K_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0_W_Z__K_W_Z(lpLibFileName);
    }
    while ( !v23 );
    v27 = WINRT_IMPL_GetProcAddress(v23, "DllGetActivationFactory");
    if ( !v27 )
      goto LABEL_48;
    v29 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v27)(
            *a2,
            &v29)
      && !(**v29)(v29, a3, a4) )
    {
      break;
    }
    if ( v29 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
LABEL_48:
    WINRT_IMPL_FreeLibrary(v23);
  }
  *a1 = 0;
  if ( v29 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
LABEL_52:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x1800104f8  push    rbp
0x1800104fa  push    rbx
0x1800104fb  push    rsi
0x1800104fc  push    rdi
0x1800104fd  push    r12
0x1800104ff  push    r13
0x180010501  push    r14
0x180010503  push    r15
0x180010505  mov     rbp, rsp
0x180010508  sub     rsp, 78h
0x18001050c  mov     rax, cs:__security_cookie
0x180010513  xor     rax, rsp
0x180010516  mov     [rbp+var_18], rax
0x18001051a  mov     r13, r9
0x18001051d  mov     r12, r8
0x180010520  mov     r15, rdx
0x180010523  mov     rsi, rcx
0x180010526  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001052d  xor     r14d, r14d
0x180010530  mov     r8, r9
0x180010533  mov     rdx, r12
0x180010536  mov     rcx, [r15]
0x180010539  test    rax, rax
0x18001053c  jz      short loc_18001054A
0x18001053e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010543  mov     [rsi], eax
0x180010545  jmp     loc_1800107FE
0x18001054a  call    RoGetActivationFactory_0
0x18001054f  mov     ebx, eax
0x180010551  cmp     eax, 800401F0h
0x180010556  jnz     short loc_1800105A8
0x180010558  xor     edx, edx; hFile
0x18001055a  mov     r8d, 1000h; dwFlags
0x180010560  lea     rcx, LibFileName; "combase.dll"
0x180010567  call    LoadLibraryExW_0
0x18001056c  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180010573  mov     rcx, rax; hModule
0x180010576  call    WINRT_IMPL_GetProcAddress
0x18001057b  test    rax, rax
0x18001057e  jnz     short loc_18001058B
0x180010580  mov     dword ptr [rsi], 800401F0h
0x180010586  jmp     loc_1800107FE
0x18001058b  mov     [rbp+var_48], r14
0x18001058f  lea     rcx, [rbp+var_48]
0x180010593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010598  mov     r8, r13
0x18001059b  mov     rdx, r12
0x18001059e  mov     rcx, [r15]
0x1800105a1  call    RoGetActivationFactory_0
0x1800105a6  mov     ebx, eax
0x1800105a8  test    ebx, ebx
0x1800105aa  jnz     short loc_1800105B4
0x1800105ac  mov     [rsi], r14d
0x1800105af  jmp     loc_1800107FE
0x1800105b4  mov     [rbp+pperrinfo], r14
0x1800105b8  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x1800105bc  xor     ecx, ecx; dwReserved
0x1800105be  call    GetErrorInfo_0
0x1800105c3  xorps   xmm0, xmm0
0x1800105c6  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x1800105ca  mov     [rbp+var_28], r14
0x1800105ce  mov     [rbp+var_20], r14
0x1800105d2  mov     rax, [r15]
0x1800105d5  test    rax, rax
0x1800105d8  jz      short loc_1800105E4
0x1800105da  mov     rdx, [rax+10h]
0x1800105de  mov     r8d, [rax+4]
0x1800105e2  jmp     short loc_1800105EE
0x1800105e4  lea     rdx, S2
0x1800105eb  mov     r8, r14
0x1800105ee  lea     rcx, [rbp+lpLibFileName]
0x1800105f2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800105f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800105fb  mov     rax, [rbp+var_28]
0x1800105ff  lea     r14, [rbp+lpLibFileName]
0x180010603  cmp     [rbp+var_20], 7
0x180010608  cmova   r14, [rbp+lpLibFileName]
0x18001060d  test    rax, rax
0x180010610  jz      loc_1800107D8
0x180010616  dec     rax
0x180010619  cmp     rax, rcx
0x18001061c  cmovnb  rax, rcx
0x180010620  inc     rax
0x180010623  lea     rdi, [r14+rax*2]
0x180010627  mov     r8d, 2Eh ; '.'
0x18001062d  mov     rdx, rdi
0x180010630  mov     rcx, r14
0x180010633  call    __std_find_last_trivial_2
0x180010638  mov     rdx, rax
0x18001063b  cmp     rax, rdi
0x18001063e  jz      loc_1800107D8
0x180010644  sub     rdx, r14
0x180010647  sar     rdx, 1
0x18001064a  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001064e  jz      loc_1800107D8
0x180010654  mov     rdi, [rbp+var_28]
0x180010658  cmp     rdx, rdi
0x18001065b  ja      short loc_180010677
0x18001065d  mov     [rbp+var_28], rdx
0x180010661  lea     rcx, [rbp+lpLibFileName]
0x180010665  cmp     [rbp+var_20], 7
0x18001066a  cmova   rcx, [rbp+lpLibFileName]
0x18001066f  xor     eax, eax
0x180010671  mov     [rcx+rdx*2], ax
0x180010675  jmp     short loc_1800106C4
0x180010677  mov     rcx, rdx
0x18001067a  sub     rcx, rdi
0x18001067d  mov     rax, [rbp+var_20]
0x180010681  sub     rax, rdi
0x180010684  cmp     rcx, rax
0x180010687  ja      short loc_1800106B5
0x180010689  mov     [rbp+var_28], rdx
0x18001068d  lea     r8, [rbp+lpLibFileName]
0x180010691  cmp     [rbp+var_20], 7
0x180010696  cmova   r8, [rbp+lpLibFileName]
0x18001069b  lea     rdi, [r8+rdi*2]
0x18001069f  test    rcx, rcx
0x1800106a2  jz      short loc_1800106AC
0x1800106a4  xor     eax, eax
0x1800106a6  movzx   eax, ax
0x1800106a9  rep stosw
0x1800106ac  xor     eax, eax
0x1800106ae  mov     [r8+rdx*2], ax
0x1800106b3  jmp     short loc_1800106C4
0x1800106b5  mov     r9, rcx
0x1800106b8  mov     rdx, rcx
0x1800106bb  lea     rcx, [rbp+lpLibFileName]; Src
0x1800106bf  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x1800106c4  lea     rdx, aDll; ".dll"
0x1800106cb  lea     rcx, [rbp+lpLibFileName]; Src
0x1800106cf  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator+=(wchar_t const * const)
0x1800106d4  lea     rcx, [rbp+lpLibFileName]
0x1800106d8  cmp     [rbp+var_20], 7
0x1800106dd  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800106e2  xor     edx, edx; hFile
0x1800106e4  mov     r8d, 1000h; dwFlags
0x1800106ea  call    LoadLibraryExW_0
0x1800106ef  mov     rdi, rax
0x1800106f2  mov     rdx, [rbp+var_28]
0x1800106f6  lea     r8, [rdx-4]
0x1800106fa  lea     rcx, [rbp+lpLibFileName]; Src
0x1800106fe  cmp     r8, rdx
0x180010701  ja      short loc_180010715
0x180010703  mov     [rbp+var_28], r8
0x180010707  cmp     [rbp+var_20], 7
0x18001070c  cmova   rcx, [rbp+lpLibFileName]
0x180010711  xor     eax, eax
0x180010713  jmp     short loc_18001073C
0x180010715  mov     rax, [rbp+var_20]
0x180010719  sub     rax, rdx
0x18001071c  mov     r10, 0FFFFFFFFFFFFFFFCh
0x180010723  cmp     rax, r10
0x180010726  jb      short loc_180010743
0x180010728  mov     [rbp+var_28], r8
0x18001072c  cmp     [rbp+var_20], 7
0x180010731  cmova   rcx, [rbp+lpLibFileName]
0x180010736  xor     eax, eax
0x180010738  mov     [rcx+rdx*2], rax
0x18001073c  mov     [rcx+r8*2], ax
0x180010741  jmp     short loc_18001074E
0x180010743  mov     r9, r10
0x180010746  mov     rdx, r10
0x180010749  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@_K_W@Z@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0_W@Z@_K_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t>(unsigned __int64,`std::wstring::append(unsigned __int64,wchar_t)'::`2'::_lambda_1_,unsigned __int64,wchar_t)
0x18001074e  test    rdi, rdi
0x180010751  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010758  jz      loc_1800105FB
0x18001075e  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180010765  mov     rcx, rdi; hModule
0x180010768  call    WINRT_IMPL_GetProcAddress
0x18001076d  test    rax, rax
0x180010770  jz      short loc_1800107B3
0x180010772  mov     [rbp+var_48], 0
0x18001077a  lea     rdx, [rbp+var_48]
0x18001077e  mov     rcx, [r15]
0x180010781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010786  test    eax, eax
0x180010788  jnz     short loc_1800107A3
0x18001078a  mov     rcx, [rbp+var_48]
0x18001078e  mov     rax, [rcx]
0x180010791  mov     r8, r13
0x180010794  mov     rdx, r12
0x180010797  mov     rax, [rax]
0x18001079a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001079f  test    eax, eax
0x1800107a1  jz      short loc_1800107C0
0x1800107a3  cmp     [rbp+var_48], 0
0x1800107a8  jz      short loc_1800107B3
0x1800107aa  lea     rcx, [rbp+var_48]
0x1800107ae  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800107b3  mov     rcx, rdi; hLibModule
0x1800107b6  call    WINRT_IMPL_FreeLibrary
0x1800107bb  jmp     loc_1800105F7
0x1800107c0  mov     dword ptr [rsi], 0
0x1800107c6  cmp     [rbp+var_48], 0
0x1800107cb  jz      short loc_1800107E5
0x1800107cd  lea     rcx, [rbp+var_48]
0x1800107d1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800107d6  jmp     short loc_1800107E5
0x1800107d8  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1800107dc  xor     ecx, ecx; dwReserved
0x1800107de  call    SetErrorInfo_0
0x1800107e3  mov     [rsi], ebx
0x1800107e5  lea     rcx, [rbp+lpLibFileName]
0x1800107e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800107ee  cmp     [rbp+pperrinfo], 0
0x1800107f3  jz      short loc_1800107FE
0x1800107f5  lea     rcx, [rbp+pperrinfo]
0x1800107f9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800107fe  mov     rax, rsi
0x180010801  mov     rcx, [rbp+var_18]
0x180010805  xor     rcx, rsp; StackCookie
0x180010808  call    __security_check_cookie
0x18001080d  add     rsp, 78h
0x180010811  pop     r15
0x180010813  pop     r14
0x180010815  pop     r13
0x180010817  pop     r12
0x180010819  pop     rdi
0x18001081a  pop     rsi
0x18001081b  pop     rbx
0x18001081c  pop     rbp
0x18001081d  retn
```
