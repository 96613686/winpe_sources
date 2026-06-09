# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x1800132d0`
- end: `0x180013643`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `883`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011aa0`

## callees

- `0x180002370`
- `0x1800025d0`
- `0x180003840`
- `0x180012fc0`
- `0x180013150`
- `0x1800132d0`
- `0x180016280`
- `0x180016286`
- `0x1800165b0`
- `0x1800181b0`
- `0x18001c573`
- `0x18001c75f`
- `0x18001c771`
- `0x18001c777`
- `0x18001cdf0`

## string_xrefs

- `0x180013337`: `combase.dll`
- `0x180013599`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // esi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  LPCWSTR *v15; // rbx
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdi
  LPCWSTR *v20; // rax
  unsigned __int64 v21; // rcx
  LPCWSTR *v22; // r8
  _WORD *v23; // rdi
  unsigned __int64 v24; // rcx
  LPCWSTR *v25; // rax
  const WCHAR *v26; // rcx
  HMODULE v27; // rbx
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rcx
  LPCWSTR *v30; // rax
  LPCWSTR *v31; // rdx
  _WORD *v32; // rdi
  __int64 i; // rcx
  FARPROC v34; // rax
  __int64 v35; // rax
  __int64 v37; // [rsp+30h] [rbp-48h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v39; // [rsp+48h] [rbp-30h]
  unsigned __int64 v40; // [rsp+50h] [rbp-28h]
  IErrorInfo *pperrinfo; // [rsp+58h] [rbp-20h] BYREF

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
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
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v37);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)lpLibFileName = 0;
      v39 = 0;
      v40 = 0;
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
      std::wstring::_Construct<1,wchar_t const *>(lpLibFileName, v13, v14);
      while ( 1 )
      {
        v15 = lpLibFileName;
        if ( v40 > 7 )
          v15 = (LPCWSTR *)lpLibFileName[0];
        if ( !v39 )
          break;
        v16 = (char *)v15 + 2 * v39;
        last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
        if ( (char *)last_trivial_2 == v16 )
          break;
        v18 = (last_trivial_2 - (__int64)v15) >> 1;
        if ( v18 == -1 )
          break;
        v19 = v39;
        if ( v18 > v39 )
        {
          v21 = v18 - v39;
          if ( v18 - v39 > v40 - v39 )
          {
            _mm_lfence();
            std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(lpLibFileName);
          }
          else
          {
            v39 = (last_trivial_2 - (__int64)v15) >> 1;
            v22 = lpLibFileName;
            if ( v40 > 7 )
              v22 = (LPCWSTR *)lpLibFileName[0];
            v23 = (_WORD *)v22 + v19;
            if ( v21 )
            {
              while ( v21 )
              {
                *v23++ = 0;
                --v21;
              }
            }
            *((_WORD *)v22 + v18) = 0;
          }
        }
        else
        {
          v39 = (last_trivial_2 - (__int64)v15) >> 1;
          v20 = lpLibFileName;
          if ( v40 > 7 )
            v20 = (LPCWSTR *)lpLibFileName[0];
          *((_WORD *)v20 + v18) = 0;
        }
        v24 = v39;
        if ( v40 - v39 < 4 )
        {
          _mm_lfence();
          std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(
            lpLibFileName,
            4);
        }
        else
        {
          v39 += 4LL;
          v25 = lpLibFileName;
          if ( v40 > 7 )
            v25 = (LPCWSTR *)lpLibFileName[0];
          *(LPCWSTR *)((char *)v25 + 2 * v24) = (LPCWSTR)0x6C006C0064002ELL;
          *((_WORD *)v25 + v24 + 4) = 0;
        }
        v26 = (const WCHAR *)lpLibFileName;
        if ( v40 > 7 )
          v26 = lpLibFileName[0];
        v27 = LoadLibraryExW_0(v26, 0, 0x1000u);
        v28 = v39;
        v29 = v39 - 4;
        if ( v39 < 4 )
        {
          if ( v40 - v39 < 0xFFFFFFFFFFFFFFFCuLL )
          {
            std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(lpLibFileName);
          }
          else
          {
            v39 -= 4LL;
            v31 = lpLibFileName;
            if ( v40 > 7 )
              v31 = (LPCWSTR *)lpLibFileName[0];
            v32 = (_WORD *)v31 + v28;
            for ( i = 0x7FFFFFFFFFFFFFFCLL; i; --i )
              *v32++ = 0;
            *((_WORD *)v31 + v28 - 4) = 0;
          }
        }
        else
        {
          v39 -= 4LL;
          v30 = lpLibFileName;
          if ( v40 > 7 )
            v30 = (LPCWSTR *)lpLibFileName[0];
          *((_WORD *)v30 + v29) = 0;
        }
        if ( v27 )
        {
          v34 = WINRT_IMPL_GetProcAddress(v27, "DllGetActivationFactory");
          if ( v34 )
          {
            v37 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v34)(*a2, &v37) )
            {
              v35 = v37;
              v37 = 0;
              *a4 = v35;
              *a1 = 0;
              goto LABEL_58;
            }
            if ( v37 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
          }
          WINRT_IMPL_FreeLibrary(v27);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_58:
      std::wstring::~wstring(lpLibFileName);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800132d0  push    rbp
0x1800132d2  push    rbx
0x1800132d3  push    rsi
0x1800132d4  push    rdi
0x1800132d5  push    r12
0x1800132d7  push    r13
0x1800132d9  push    r14
0x1800132db  push    r15
0x1800132dd  mov     rbp, rsp
0x1800132e0  sub     rsp, 78h
0x1800132e4  mov     rax, cs:__security_cookie
0x1800132eb  xor     rax, rsp
0x1800132ee  mov     [rbp+var_18], rax
0x1800132f2  mov     r13, r9
0x1800132f5  mov     rdi, r8
0x1800132f8  mov     r12, rdx
0x1800132fb  mov     r15, rcx
0x1800132fe  mov     rcx, [rdx]
0x180013301  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180013308  mov     r8, r9
0x18001330b  mov     rdx, rdi
0x18001330e  test    rax, rax
0x180013311  jz      short loc_180013321
0x180013313  call    cs:__guard_dispatch_icall_fptr
0x180013319  mov     [r15], eax
0x18001331c  jmp     loc_180013623
0x180013321  call    RoGetActivationFactory_0
0x180013326  mov     esi, eax
0x180013328  cmp     eax, 800401F0h
0x18001332d  jnz     short loc_18001337E
0x18001332f  xor     edx, edx; hFile
0x180013331  mov     r8d, 1000h; dwFlags
0x180013337  lea     rcx, LibFileName; "combase.dll"
0x18001333e  call    LoadLibraryExW_0
0x180013343  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001334a  mov     rcx, rax; hModule
0x18001334d  call    WINRT_IMPL_GetProcAddress
0x180013352  test    rax, rax
0x180013355  jnz     short loc_180013363
0x180013357  mov     dword ptr [r15], 800401F0h
0x18001335e  jmp     loc_180013623
0x180013363  lea     rcx, [rbp+var_48]
0x180013367  call    cs:__guard_dispatch_icall_fptr
0x18001336d  mov     r8, r13
0x180013370  mov     rdx, rdi
0x180013373  mov     rcx, [r12]
0x180013377  call    RoGetActivationFactory_0
0x18001337c  mov     esi, eax
0x18001337e  xor     r14d, r14d
0x180013381  test    esi, esi
0x180013383  jnz     short loc_18001338D
0x180013385  mov     [r15], r14d
0x180013388  jmp     loc_180013623
0x18001338d  mov     [rbp+pperrinfo], r14
0x180013391  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180013395  xor     ecx, ecx; dwReserved
0x180013397  call    GetErrorInfo_0
0x18001339c  xorps   xmm0, xmm0
0x18001339f  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x1800133a3  mov     [rbp+var_30], r14
0x1800133a7  mov     [rbp+var_28], r14
0x1800133ab  mov     rax, [r12]
0x1800133af  test    rax, rax
0x1800133b2  jz      short loc_1800133BE
0x1800133b4  mov     rdx, [rax+10h]
0x1800133b8  mov     r8d, [rax+4]
0x1800133bc  jmp     short loc_1800133C8
0x1800133be  lea     rdx, S2
0x1800133c5  mov     r8, r14
0x1800133c8  lea     rcx, [rbp+lpLibFileName]
0x1800133cc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800133d1  lea     rbx, [rbp+lpLibFileName]
0x1800133d5  cmp     [rbp+var_28], 7
0x1800133da  cmova   rbx, [rbp+lpLibFileName]
0x1800133df  mov     rcx, [rbp+var_30]
0x1800133e3  test    rcx, rcx
0x1800133e6  jz      loc_1800135FD
0x1800133ec  dec     rcx
0x1800133ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800133f6  cmp     rcx, rax
0x1800133f9  cmovb   rax, rcx
0x1800133fd  inc     rax
0x180013400  lea     rdi, [rbx+rax*2]
0x180013404  mov     r8d, 2Eh ; '.'
0x18001340a  mov     rdx, rdi
0x18001340d  mov     rcx, rbx
0x180013410  call    __std_find_last_trivial_2
0x180013415  mov     rdx, rax
0x180013418  cmp     rax, rdi
0x18001341b  jz      loc_1800135FD
0x180013421  sub     rdx, rbx
0x180013424  sar     rdx, 1
0x180013427  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001342b  jz      loc_1800135FD
0x180013431  mov     rdi, [rbp+var_30]
0x180013435  cmp     rdx, rdi
0x180013438  ja      short loc_180013453
0x18001343a  mov     [rbp+var_30], rdx
0x18001343e  lea     rax, [rbp+lpLibFileName]
0x180013442  cmp     [rbp+var_28], 7
0x180013447  cmova   rax, [rbp+lpLibFileName]
0x18001344c  mov     [rax+rdx*2], r14w
0x180013451  jmp     short loc_1800134A2
0x180013453  mov     rcx, rdx
0x180013456  sub     rcx, rdi
0x180013459  mov     r9, [rbp+var_28]
0x18001345d  mov     rax, r9
0x180013460  sub     rax, rdi
0x180013463  cmp     rcx, rax
0x180013466  ja      short loc_180013490
0x180013468  mov     [rbp+var_30], rdx
0x18001346c  lea     r8, [rbp+lpLibFileName]
0x180013470  cmp     r9, 7
0x180013474  cmova   r8, [rbp+lpLibFileName]
0x180013479  lea     rdi, [r8+rdi*2]
0x18001347d  test    rcx, rcx
0x180013480  jz      short loc_180013489
0x180013482  movzx   eax, r14w
0x180013486  rep stosw
0x180013489  mov     [r8+rdx*2], r14w
0x18001348e  jmp     short loc_1800134A2
0x180013490  lfence
0x180013493  mov     r9, rcx
0x180013496  mov     rdx, rcx
0x180013499  lea     rcx, [rbp+lpLibFileName]; Src
0x18001349d  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x1800134a2  mov     rcx, [rbp+var_30]
0x1800134a6  mov     rdx, [rbp+var_28]
0x1800134aa  mov     rax, rdx
0x1800134ad  sub     rax, rcx
0x1800134b0  cmp     rax, 4
0x1800134b4  jb      short loc_1800134E1
0x1800134b6  lea     rax, [rcx+4]
0x1800134ba  mov     [rbp+var_30], rax
0x1800134be  lea     rax, [rbp+lpLibFileName]
0x1800134c2  cmp     rdx, 7
0x1800134c6  cmova   rax, [rbp+lpLibFileName]
0x1800134cb  mov     rdx, 6C006C0064002Eh
0x1800134d5  mov     [rax+rcx*2], rdx
0x1800134d9  mov     [rax+rcx*2+8], r14w
0x1800134df  jmp     short loc_1800134FB
0x1800134e1  lfence
0x1800134e4  mov     [rsp+78h+var_58], 4; __int64
0x1800134ed  mov     edx, 4
0x1800134f2  lea     rcx, [rbp+lpLibFileName]; Src
0x1800134f6  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x1800134fb  lea     rcx, [rbp+lpLibFileName]
0x1800134ff  cmp     [rbp+var_28], 7
0x180013504  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180013509  xor     edx, edx; hFile
0x18001350b  mov     r8d, 1000h; dwFlags
0x180013511  call    LoadLibraryExW_0
0x180013516  mov     rbx, rax
0x180013519  mov     r8, [rbp+var_30]
0x18001351d  lea     rcx, [r8-4]
0x180013521  cmp     rcx, r8
0x180013524  ja      short loc_18001353F
0x180013526  mov     [rbp+var_30], rcx
0x18001352a  lea     rax, [rbp+lpLibFileName]
0x18001352e  cmp     [rbp+var_28], 7
0x180013533  cmova   rax, [rbp+lpLibFileName]
0x180013538  mov     [rax+rcx*2], r14w
0x18001353d  jmp     short loc_180013590
0x18001353f  mov     rdi, [rbp+var_28]
0x180013543  mov     rax, rdi
0x180013546  sub     rax, r8
0x180013549  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x18001354d  jb      short loc_18001357D
0x18001354f  mov     [rbp+var_30], rcx
0x180013553  lea     rdx, [rbp+lpLibFileName]
0x180013557  cmp     rdi, 7
0x18001355b  cmova   rdx, [rbp+lpLibFileName]
0x180013560  lea     rdi, [rdx+r8*2]
0x180013564  movzx   eax, r14w
0x180013568  mov     rcx, 7FFFFFFFFFFFFFFCh
0x180013572  rep stosw
0x180013575  mov     [rdx+r8*2-8], r14w
0x18001357b  jmp     short loc_180013590
0x18001357d  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x180013584  mov     r9, rdx
0x180013587  lea     rcx, [rbp+lpLibFileName]; Src
0x18001358b  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x180013590  test    rbx, rbx
0x180013593  jz      loc_1800133D1
0x180013599  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x1800135a0  mov     rcx, rbx; hModule
0x1800135a3  call    WINRT_IMPL_GetProcAddress
0x1800135a8  test    rax, rax
0x1800135ab  jnz     short loc_1800135BA
0x1800135ad  mov     rcx, rbx; hLibModule
0x1800135b0  call    WINRT_IMPL_FreeLibrary
0x1800135b5  jmp     loc_1800133D1
0x1800135ba  mov     [rbp+var_48], r14
0x1800135be  lea     rdx, [rbp+var_48]
0x1800135c2  mov     rcx, [r12]
0x1800135c6  call    cs:__guard_dispatch_icall_fptr
0x1800135cc  test    eax, eax
0x1800135ce  jz      short loc_1800135EC
0x1800135d0  cmp     [rbp+var_48], r14
0x1800135d4  jz      short loc_1800135DF
0x1800135d6  lea     rcx, [rbp+var_48]
0x1800135da  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800135df  mov     rcx, rbx; hLibModule
0x1800135e2  call    WINRT_IMPL_FreeLibrary
0x1800135e7  jmp     loc_1800133D1
0x1800135ec  mov     rax, [rbp+var_48]
0x1800135f0  mov     [rbp+var_48], r14
0x1800135f4  mov     [r13+0], rax
0x1800135f8  mov     [r15], r14d
0x1800135fb  jmp     short loc_18001360B
0x1800135fd  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180013601  xor     ecx, ecx; dwReserved
0x180013603  call    SetErrorInfo_0
0x180013608  mov     [r15], esi
0x18001360b  lea     rcx, [rbp+lpLibFileName]
0x18001360f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013614  cmp     [rbp+pperrinfo], r14
0x180013618  jz      short loc_180013623
0x18001361a  lea     rcx, [rbp+pperrinfo]
0x18001361e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013623  mov     rax, r15
0x180013626  mov     rcx, [rbp+var_18]
0x18001362a  xor     rcx, rsp; StackCookie
0x18001362d  call    __security_check_cookie
0x180013632  add     rsp, 78h
0x180013636  pop     r15
0x180013638  pop     r14
0x18001363a  pop     r13
0x18001363c  pop     r12
0x18001363e  pop     rdi
0x18001363f  pop     rsi
0x180013640  pop     rbx
0x180013641  pop     rbp
0x180013642  retn
```
