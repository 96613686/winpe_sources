# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18000ec30`
- end: `0x18000f073`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `1091`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180004c30`

## callees

- `0x1800025d0`
- `0x180003840`
- `0x18000ec30`
- `0x180012fc0`
- `0x180013150`
- `0x180016280`
- `0x180016286`
- `0x1800165b0`
- `0x1800181b0`
- `0x180018238`
- `0x18001c573`
- `0x18001c75f`
- `0x18001c771`
- `0x18001c777`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000efc9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000f024`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000efc9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000f024`

## string_xrefs

- `0x18000ec9b`: `combase.dll`
- `0x18000ef08`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
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
  unsigned __int64 v35; // rdx
  WCHAR *v36; // rcx
  unsigned int (__fastcall ***v39)(_QWORD, __int64, __int64); // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v41; // [rsp+50h] [rbp-28h]
  unsigned __int64 v42; // [rsp+58h] [rbp-20h]
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp-18h] BYREF

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
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v39);
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
  v41 = 0;
  v42 = 0;
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
    do
    {
      v15 = lpLibFileName;
      if ( v42 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      if ( !v41
        || (v16 = (char *)v15 + 2 * v41,
            last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46),
            (char *)last_trivial_2 == v16)
        || (v18 = (last_trivial_2 - (__int64)v15) >> 1, v18 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        if ( v42 <= 7 )
          goto LABEL_67;
        v35 = 2 * v42 + 2;
        v36 = (WCHAR *)lpLibFileName[0];
        if ( v35 >= 0x1000 )
        {
          v35 = 2 * v42 + 41;
          v36 = (WCHAR *)*((_QWORD *)lpLibFileName[0] - 1);
          if ( (unsigned __int64)((char *)lpLibFileName[0] - (char *)v36 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        goto LABEL_66;
      }
      v19 = v41;
      if ( v18 > v41 )
      {
        v21 = v18 - v41;
        if ( v18 - v41 > v42 - v41 )
        {
          _mm_lfence();
          std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(lpLibFileName);
        }
        else
        {
          v41 = (last_trivial_2 - (__int64)v15) >> 1;
          v22 = lpLibFileName;
          if ( v42 > 7 )
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
        v41 = (last_trivial_2 - (__int64)v15) >> 1;
        v20 = lpLibFileName;
        if ( v42 > 7 )
          v20 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v20 + v18) = 0;
      }
      v24 = v41;
      if ( v42 - v41 < 4 )
      {
        _mm_lfence();
        std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v41 += 4LL;
        v25 = lpLibFileName;
        if ( v42 > 7 )
          v25 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v25 + 2 * v24) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v25 + v24 + 4) = 0;
      }
      v26 = (const WCHAR *)lpLibFileName;
      if ( v42 > 7 )
        v26 = lpLibFileName[0];
      v27 = LoadLibraryExW_0(v26, 0, 0x1000u);
      v28 = v41;
      v29 = v41 - 4;
      if ( v41 < 4 )
      {
        if ( v42 - v41 < 0xFFFFFFFFFFFFFFFCuLL )
        {
          std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(lpLibFileName);
        }
        else
        {
          v41 -= 4LL;
          v31 = lpLibFileName;
          if ( v42 > 7 )
            v31 = (LPCWSTR *)lpLibFileName[0];
          v32 = (_WORD *)v31 + v28;
          for ( i = 0x7FFFFFFFFFFFFFFCLL; i; --i )
            *v32++ = 0;
          *((_WORD *)v31 + v28 - 4) = 0;
        }
      }
      else
      {
        v41 -= 4LL;
        v30 = lpLibFileName;
        if ( v42 > 7 )
          v30 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v30 + v29) = 0;
      }
    }
    while ( !v27 );
    v34 = WINRT_IMPL_GetProcAddress(v27, "DllGetActivationFactory");
    if ( v34 )
      break;
LABEL_55:
    WINRT_IMPL_FreeLibrary(v27);
  }
  v39 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v34)(*a2, &v39)
    || (**v39)(v39, a3, a4) )
  {
    if ( v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
    goto LABEL_55;
  }
  *a1 = 0;
  if ( v39 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
  if ( v42 > 7 )
  {
    v35 = 2 * v42 + 2;
    v36 = (WCHAR *)lpLibFileName[0];
    if ( v35 >= 0x1000 )
    {
      v35 = 2 * v42 + 41;
      v36 = (WCHAR *)*((_QWORD *)lpLibFileName[0] - 1);
      if ( (unsigned __int64)((char *)lpLibFileName[0] - (char *)v36 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
LABEL_66:
    _mm_lfence();
    operator delete(v36, v35);
  }
LABEL_67:
  LOWORD(lpLibFileName[0]) = 0;
  v42 = 7;
  v41 = 0;
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000ec30  push    rbp
0x18000ec32  push    rbx
0x18000ec33  push    rsi
0x18000ec34  push    rdi
0x18000ec35  push    r12
0x18000ec37  push    r13
0x18000ec39  push    r14
0x18000ec3b  push    r15
0x18000ec3d  mov     rbp, rsp
0x18000ec40  sub     rsp, 78h
0x18000ec44  mov     rax, cs:__security_cookie
0x18000ec4b  xor     rax, rsp
0x18000ec4e  mov     [rbp+var_10], rax
0x18000ec52  mov     rdi, r9
0x18000ec55  mov     [rbp+var_48], r9
0x18000ec59  mov     r13, r8
0x18000ec5c  mov     r12, rdx
0x18000ec5f  mov     r15, rcx
0x18000ec62  mov     rcx, [rdx]
0x18000ec65  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18000ec6c  mov     r8, r9
0x18000ec6f  mov     rdx, r13
0x18000ec72  test    rax, rax
0x18000ec75  jz      short loc_18000EC85
0x18000ec77  call    cs:__guard_dispatch_icall_fptr
0x18000ec7d  mov     [r15], eax
0x18000ec80  jmp     loc_18000F053
0x18000ec85  call    RoGetActivationFactory_0
0x18000ec8a  mov     esi, eax
0x18000ec8c  cmp     eax, 800401F0h
0x18000ec91  jnz     short loc_18000ECE2
0x18000ec93  xor     edx, edx; hFile
0x18000ec95  mov     r8d, 1000h; dwFlags
0x18000ec9b  lea     rcx, LibFileName; "combase.dll"
0x18000eca2  call    LoadLibraryExW_0
0x18000eca7  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18000ecae  mov     rcx, rax; hModule
0x18000ecb1  call    WINRT_IMPL_GetProcAddress
0x18000ecb6  test    rax, rax
0x18000ecb9  jnz     short loc_18000ECC7
0x18000ecbb  mov     dword ptr [r15], 800401F0h
0x18000ecc2  jmp     loc_18000F053
0x18000ecc7  lea     rcx, [rbp+var_40]
0x18000eccb  call    cs:__guard_dispatch_icall_fptr
0x18000ecd1  mov     r8, rdi
0x18000ecd4  mov     rdx, r13
0x18000ecd7  mov     rcx, [r12]
0x18000ecdb  call    RoGetActivationFactory_0
0x18000ece0  mov     esi, eax
0x18000ece2  xor     r14d, r14d
0x18000ece5  test    esi, esi
0x18000ece7  jnz     short loc_18000ECF1
0x18000ece9  mov     [r15], r14d
0x18000ecec  jmp     loc_18000F053
0x18000ecf1  mov     [rbp+pperrinfo], r14
0x18000ecf5  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000ecf9  xor     ecx, ecx; dwReserved
0x18000ecfb  call    GetErrorInfo_0
0x18000ed00  xorps   xmm0, xmm0
0x18000ed03  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x18000ed07  mov     [rbp+var_28], r14
0x18000ed0b  mov     [rbp+var_20], r14
0x18000ed0f  mov     rax, [r12]
0x18000ed13  test    rax, rax
0x18000ed16  jz      short loc_18000ED22
0x18000ed18  mov     rdx, [rax+10h]
0x18000ed1c  mov     r8d, [rax+4]
0x18000ed20  jmp     short loc_18000ED2C
0x18000ed22  lea     rdx, S2
0x18000ed29  mov     r8, r14
0x18000ed2c  lea     rcx, [rbp+lpLibFileName]
0x18000ed30  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000ed35  nop     word ptr [rax+rax+00000000h]
0x18000ed40  lea     rbx, [rbp+lpLibFileName]
0x18000ed44  cmp     [rbp+var_20], 7
0x18000ed49  cmova   rbx, [rbp+lpLibFileName]
0x18000ed4e  mov     rcx, [rbp+var_28]
0x18000ed52  test    rcx, rcx
0x18000ed55  jz      loc_18000EFD0
0x18000ed5b  dec     rcx
0x18000ed5e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ed65  cmp     rcx, rax
0x18000ed68  cmovb   rax, rcx
0x18000ed6c  inc     rax
0x18000ed6f  lea     rdi, [rbx+rax*2]
0x18000ed73  mov     r8d, 2Eh ; '.'
0x18000ed79  mov     rdx, rdi
0x18000ed7c  mov     rcx, rbx
0x18000ed7f  call    __std_find_last_trivial_2
0x18000ed84  mov     rdx, rax
0x18000ed87  cmp     rax, rdi
0x18000ed8a  jz      loc_18000EFD0
0x18000ed90  sub     rdx, rbx
0x18000ed93  sar     rdx, 1
0x18000ed96  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000ed9a  jz      loc_18000EFD0
0x18000eda0  mov     rdi, [rbp+var_28]
0x18000eda4  cmp     rdx, rdi
0x18000eda7  ja      short loc_18000EDC2
0x18000eda9  mov     [rbp+var_28], rdx
0x18000edad  lea     rax, [rbp+lpLibFileName]
0x18000edb1  cmp     [rbp+var_20], 7
0x18000edb6  cmova   rax, [rbp+lpLibFileName]
0x18000edbb  mov     [rax+rdx*2], r14w
0x18000edc0  jmp     short loc_18000EE11
0x18000edc2  mov     rcx, rdx
0x18000edc5  sub     rcx, rdi
0x18000edc8  mov     r9, [rbp+var_20]
0x18000edcc  mov     rax, r9
0x18000edcf  sub     rax, rdi
0x18000edd2  cmp     rcx, rax
0x18000edd5  ja      short loc_18000EDFF
0x18000edd7  mov     [rbp+var_28], rdx
0x18000eddb  lea     r8, [rbp+lpLibFileName]
0x18000eddf  cmp     r9, 7
0x18000ede3  cmova   r8, [rbp+lpLibFileName]
0x18000ede8  lea     rdi, [r8+rdi*2]
0x18000edec  test    rcx, rcx
0x18000edef  jz      short loc_18000EDF8
0x18000edf1  movzx   eax, r14w
0x18000edf5  rep stosw
0x18000edf8  mov     [r8+rdx*2], r14w
0x18000edfd  jmp     short loc_18000EE11
0x18000edff  lfence
0x18000ee02  mov     r9, rcx
0x18000ee05  mov     rdx, rcx
0x18000ee08  lea     rcx, [rbp+lpLibFileName]; Src
0x18000ee0c  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x18000ee11  mov     rcx, [rbp+var_28]
0x18000ee15  mov     rdx, [rbp+var_20]
0x18000ee19  mov     rax, rdx
0x18000ee1c  sub     rax, rcx
0x18000ee1f  cmp     rax, 4
0x18000ee23  jb      short loc_18000EE50
0x18000ee25  lea     rax, [rcx+4]
0x18000ee29  mov     [rbp+var_28], rax
0x18000ee2d  lea     rax, [rbp+lpLibFileName]
0x18000ee31  cmp     rdx, 7
0x18000ee35  cmova   rax, [rbp+lpLibFileName]
0x18000ee3a  mov     rdx, 6C006C0064002Eh
0x18000ee44  mov     [rax+rcx*2], rdx
0x18000ee48  mov     [rax+rcx*2+8], r14w
0x18000ee4e  jmp     short loc_18000EE6A
0x18000ee50  lfence
0x18000ee53  mov     [rsp+78h+Reserved], 4; __int64
0x18000ee5c  mov     edx, 4
0x18000ee61  lea     rcx, [rbp+lpLibFileName]; Src
0x18000ee65  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x18000ee6a  lea     rcx, [rbp+lpLibFileName]
0x18000ee6e  cmp     [rbp+var_20], 7
0x18000ee73  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000ee78  xor     edx, edx; hFile
0x18000ee7a  mov     r8d, 1000h; dwFlags
0x18000ee80  call    LoadLibraryExW_0
0x18000ee85  mov     rbx, rax
0x18000ee88  mov     r8, [rbp+var_28]
0x18000ee8c  lea     rcx, [r8-4]
0x18000ee90  cmp     rcx, r8
0x18000ee93  ja      short loc_18000EEAE
0x18000ee95  mov     [rbp+var_28], rcx
0x18000ee99  lea     rax, [rbp+lpLibFileName]
0x18000ee9d  cmp     [rbp+var_20], 7
0x18000eea2  cmova   rax, [rbp+lpLibFileName]
0x18000eea7  mov     [rax+rcx*2], r14w
0x18000eeac  jmp     short loc_18000EEFF
0x18000eeae  mov     rdi, [rbp+var_20]
0x18000eeb2  mov     rax, rdi
0x18000eeb5  sub     rax, r8
0x18000eeb8  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x18000eebc  jb      short loc_18000EEEC
0x18000eebe  mov     [rbp+var_28], rcx
0x18000eec2  lea     rdx, [rbp+lpLibFileName]
0x18000eec6  cmp     rdi, 7
0x18000eeca  cmova   rdx, [rbp+lpLibFileName]
0x18000eecf  lea     rdi, [rdx+r8*2]
0x18000eed3  movzx   eax, r14w
0x18000eed7  mov     rcx, 7FFFFFFFFFFFFFFCh
0x18000eee1  rep stosw
0x18000eee4  mov     [rdx+r8*2-8], r14w
0x18000eeea  jmp     short loc_18000EEFF
0x18000eeec  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x18000eef3  mov     r9, rdx
0x18000eef6  lea     rcx, [rbp+lpLibFileName]; Src
0x18000eefa  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x18000eeff  test    rbx, rbx
0x18000ef02  jz      loc_18000ED40
0x18000ef08  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18000ef0f  mov     rcx, rbx; hModule
0x18000ef12  call    WINRT_IMPL_GetProcAddress
0x18000ef17  test    rax, rax
0x18000ef1a  jz      short loc_18000EF5C
0x18000ef1c  mov     [rbp+var_40], r14
0x18000ef20  lea     rdx, [rbp+var_40]
0x18000ef24  mov     rcx, [r12]
0x18000ef28  call    cs:__guard_dispatch_icall_fptr
0x18000ef2e  test    eax, eax
0x18000ef30  jnz     short loc_18000EF4D
0x18000ef32  mov     rcx, [rbp+var_40]
0x18000ef36  mov     rax, [rcx]
0x18000ef39  mov     r8, [rbp+var_48]
0x18000ef3d  mov     rdx, r13
0x18000ef40  mov     rax, [rax]
0x18000ef43  call    cs:__guard_dispatch_icall_fptr
0x18000ef49  test    eax, eax
0x18000ef4b  jz      short loc_18000EF69
0x18000ef4d  cmp     [rbp+var_40], r14
0x18000ef51  jz      short loc_18000EF5C
0x18000ef53  lea     rcx, [rbp+var_40]
0x18000ef57  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ef5c  mov     rcx, rbx; hLibModule
0x18000ef5f  call    WINRT_IMPL_FreeLibrary
0x18000ef64  jmp     loc_18000ED40
0x18000ef69  mov     [r15], r14d
0x18000ef6c  cmp     [rbp+var_40], r14
0x18000ef70  jz      short loc_18000EF7B
0x18000ef72  lea     rcx, [rbp+var_40]
0x18000ef76  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000ef7b  mov     rdx, [rbp+var_20]
0x18000ef7f  cmp     rdx, 7
0x18000ef83  jbe     loc_18000F033
0x18000ef89  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000ef91  mov     rcx, [rbp+lpLibFileName]; void *
0x18000ef95  mov     rax, rcx
0x18000ef98  cmp     rdx, 1000h
0x18000ef9f  jb      loc_18000F02B
0x18000efa5  add     rdx, 27h ; '''
0x18000efa9  mov     rcx, [rcx-8]
0x18000efad  sub     rax, rcx
0x18000efb0  sub     rax, 8
0x18000efb4  cmp     rax, 1Fh
0x18000efb8  jbe     short loc_18000F02B
0x18000efba  mov     [rsp+78h+Reserved], r14; Reserved
0x18000efbf  xor     r9d, r9d; LineNo
0x18000efc2  xor     r8d, r8d; FileName
0x18000efc5  xor     edx, edx; FunctionName
0x18000efc7  xor     ecx, ecx; Expression
0x18000efc9  call    cs:__imp__invoke_watson
0x18000efd0  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000efd4  xor     ecx, ecx; dwReserved
0x18000efd6  call    SetErrorInfo_0
0x18000efdb  mov     [r15], esi
0x18000efde  mov     rdx, [rbp+var_20]
0x18000efe2  cmp     rdx, 7
0x18000efe6  jbe     short loc_18000F033
0x18000efe8  lea     rdx, ds:2[rdx*2]
0x18000eff0  mov     rcx, [rbp+lpLibFileName]
0x18000eff4  mov     rax, rcx
0x18000eff7  cmp     rdx, 1000h
0x18000effe  jb      short loc_18000F02B
0x18000f000  add     rdx, 27h ; '''
0x18000f004  mov     rcx, [rcx-8]
0x18000f008  sub     rax, rcx
0x18000f00b  sub     rax, 8
0x18000f00f  cmp     rax, 1Fh
0x18000f013  jbe     short loc_18000F02B
0x18000f015  mov     [rsp+78h+Reserved], r14; Reserved
0x18000f01a  xor     r9d, r9d; LineNo
0x18000f01d  xor     r8d, r8d; FileName
0x18000f020  xor     edx, edx; FunctionName
0x18000f022  xor     ecx, ecx; Expression
0x18000f024  call    cs:__imp__invoke_watson
0x18000f02b  lfence
0x18000f02e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f033  cmp     [rbp+pperrinfo], r14
0x18000f037  mov     word ptr [rbp+lpLibFileName], r14w
0x18000f03c  mov     [rbp+var_20], 7
0x18000f044  mov     [rbp+var_28], r14
0x18000f048  jz      short loc_18000F053
0x18000f04a  lea     rcx, [rbp+pperrinfo]
0x18000f04e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f053  mov     rax, r15
0x18000f056  mov     rcx, [rbp+var_10]
0x18000f05a  xor     rcx, rsp; StackCookie
0x18000f05d  call    __security_check_cookie
0x18000f062  add     rsp, 78h
0x18000f066  pop     r15
0x18000f068  pop     r14
0x18000f06a  pop     r13
0x18000f06c  pop     r12
0x18000f06e  pop     rdi
0x18000f06f  pop     rsi
0x18000f070  pop     rbx
0x18000f071  pop     rbp
0x18000f072  retn
```
