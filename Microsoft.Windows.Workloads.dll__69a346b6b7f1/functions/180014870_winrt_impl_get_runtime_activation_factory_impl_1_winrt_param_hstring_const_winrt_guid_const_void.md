# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180014870`
- end: `0x180014ba6`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `822`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013c10`
- `0x180014bb0`
- `0x18001c100`
- `0x18001c400`
- `0x18002b010`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x1800040a0`
- `0x180014650`
- `0x1800146e0`
- `0x180014870`
- `0x180030acd`
- `0x180030ad3`
- `0x180030b09`
- `0x180032db0`
- `0x180034ef0`
- `0x1800362c8`
- `0x1800362ce`
- `0x18003988d`
- `0x18003bed0`

## string_xrefs

- `0x1800148d7`: `combase.dll`
- `0x180014afc`: `DllGetActivationFactory`

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
  unsigned __int64 v14; // r8
  LPCWSTR *v15; // rbx
  char *v16; // rdi
  __int64 last_trivial_2; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdi
  LPCWSTR *v20; // rax
  unsigned __int64 v21; // rcx
  LPCWSTR *v22; // r8
  _WORD *v23; // rdi
  const WCHAR *v24; // rcx
  HMODULE v25; // rbx
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // rcx
  LPCWSTR *v28; // rax
  LPCWSTR *v29; // rdx
  _WORD *v30; // rdi
  __int64 i; // rcx
  FARPROC v32; // rax
  __int64 v33; // rax
  __int64 v35; // [rsp+30h] [rbp-48h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v37; // [rsp+48h] [rbp-30h]
  unsigned __int64 v38; // [rsp+50h] [rbp-28h]
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
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v35);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)lpLibFileName = 0;
      v37 = 0;
      v38 = 0;
      v12 = *a2;
      if ( *a2 )
      {
        v13 = *(const wchar_t **)(v12 + 16);
        v14 = *(unsigned int *)(v12 + 4);
      }
      else
      {
        v13 = &Src;
        v14 = 0;
      }
      std::wstring::_Construct<1,wchar_t const *>(lpLibFileName, v13, v14);
      while ( 1 )
      {
        v15 = lpLibFileName;
        if ( v38 > 7 )
          v15 = (LPCWSTR *)lpLibFileName[0];
        if ( !v37 )
          break;
        v16 = (char *)v15 + 2 * v37;
        last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46);
        if ( (char *)last_trivial_2 == v16 )
          break;
        v18 = (last_trivial_2 - (__int64)v15) >> 1;
        if ( v18 == -1 )
          break;
        v19 = v37;
        if ( v18 > v37 )
        {
          v21 = v18 - v37;
          if ( v18 - v37 > v38 - v37 )
          {
            _mm_lfence();
            std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(
              lpLibFileName,
              0);
          }
          else
          {
            v37 = (last_trivial_2 - (__int64)v15) >> 1;
            v22 = lpLibFileName;
            if ( v38 > 7 )
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
          v37 = (last_trivial_2 - (__int64)v15) >> 1;
          v20 = lpLibFileName;
          if ( v38 > 7 )
            v20 = (LPCWSTR *)lpLibFileName[0];
          *((_WORD *)v20 + v18) = 0;
        }
        std::wstring::append(lpLibFileName, L".dll");
        v24 = (const WCHAR *)lpLibFileName;
        if ( v38 > 7 )
          v24 = lpLibFileName[0];
        v25 = LoadLibraryExW_0(v24, 0, 0x1000u);
        v26 = v37;
        v27 = v37 - 4;
        if ( v37 < 4 )
        {
          if ( v38 - v37 < 0xFFFFFFFFFFFFFFFCuLL )
          {
            std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(
              lpLibFileName,
              0);
          }
          else
          {
            v37 -= 4LL;
            v29 = lpLibFileName;
            if ( v38 > 7 )
              v29 = (LPCWSTR *)lpLibFileName[0];
            v30 = (_WORD *)v29 + v26;
            for ( i = 0x7FFFFFFFFFFFFFFCLL; i; --i )
              *v30++ = 0;
            *((_WORD *)v29 + v26 - 4) = 0;
          }
        }
        else
        {
          v37 -= 4LL;
          v28 = lpLibFileName;
          if ( v38 > 7 )
            v28 = (LPCWSTR *)lpLibFileName[0];
          *((_WORD *)v28 + v27) = 0;
        }
        if ( v25 )
        {
          v32 = WINRT_IMPL_GetProcAddress(v25, "DllGetActivationFactory");
          if ( v32 )
          {
            v35 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v32)(*a2, &v35) )
            {
              v33 = v35;
              v35 = 0;
              *a4 = v33;
              *a1 = 0;
              goto LABEL_53;
            }
            if ( v35 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v35);
          }
          WINRT_IMPL_FreeLibrary(v25);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_53:
      std::wstring::_Tidy_deallocate(lpLibFileName);
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
0x180014870  push    rbp
0x180014872  push    rbx
0x180014873  push    rsi
0x180014874  push    rdi
0x180014875  push    r12
0x180014877  push    r13
0x180014879  push    r14
0x18001487b  push    r15
0x18001487d  mov     rbp, rsp
0x180014880  sub     rsp, 78h
0x180014884  mov     rax, cs:__security_cookie
0x18001488b  xor     rax, rsp
0x18001488e  mov     [rbp+var_18], rax
0x180014892  mov     r13, r9
0x180014895  mov     rdi, r8
0x180014898  mov     r12, rdx
0x18001489b  mov     r15, rcx
0x18001489e  mov     rcx, [rdx]
0x1800148a1  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x1800148a8  mov     r8, r9
0x1800148ab  mov     rdx, rdi
0x1800148ae  test    rax, rax
0x1800148b1  jz      short loc_1800148C1
0x1800148b3  call    cs:__guard_dispatch_icall_fptr
0x1800148b9  mov     [r15], eax
0x1800148bc  jmp     loc_180014B86
0x1800148c1  call    RoGetActivationFactory_0
0x1800148c6  mov     esi, eax
0x1800148c8  cmp     eax, 800401F0h
0x1800148cd  jnz     short loc_18001491E
0x1800148cf  xor     edx, edx; hFile
0x1800148d1  mov     r8d, 1000h; dwFlags
0x1800148d7  lea     rcx, aCombaseDll; "combase.dll"
0x1800148de  call    LoadLibraryExW_0
0x1800148e3  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x1800148ea  mov     rcx, rax; hModule
0x1800148ed  call    WINRT_IMPL_GetProcAddress
0x1800148f2  test    rax, rax
0x1800148f5  jnz     short loc_180014903
0x1800148f7  mov     dword ptr [r15], 800401F0h
0x1800148fe  jmp     loc_180014B86
0x180014903  lea     rcx, [rbp+var_48]
0x180014907  call    cs:__guard_dispatch_icall_fptr
0x18001490d  mov     r8, r13
0x180014910  mov     rdx, rdi
0x180014913  mov     rcx, [r12]
0x180014917  call    RoGetActivationFactory_0
0x18001491c  mov     esi, eax
0x18001491e  xor     r14d, r14d
0x180014921  test    esi, esi
0x180014923  jnz     short loc_18001492D
0x180014925  mov     [r15], r14d
0x180014928  jmp     loc_180014B86
0x18001492d  mov     [rbp+pperrinfo], r14
0x180014931  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180014935  xor     ecx, ecx; dwReserved
0x180014937  call    GetErrorInfo_0
0x18001493c  xorps   xmm0, xmm0
0x18001493f  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180014943  mov     [rbp+var_30], r14
0x180014947  mov     [rbp+var_28], r14
0x18001494b  mov     rax, [r12]
0x18001494f  test    rax, rax
0x180014952  jz      short loc_18001495E
0x180014954  mov     rdx, [rax+10h]
0x180014958  mov     r8d, [rax+4]
0x18001495c  jmp     short loc_180014968
0x18001495e  lea     rdx, Src
0x180014965  mov     r8, r14
0x180014968  lea     rcx, [rbp+lpLibFileName]
0x18001496c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014971  lea     rbx, [rbp+lpLibFileName]
0x180014975  cmp     [rbp+var_28], 7
0x18001497a  cmova   rbx, [rbp+lpLibFileName]
0x18001497f  mov     rcx, [rbp+var_30]
0x180014983  test    rcx, rcx
0x180014986  jz      loc_180014B60
0x18001498c  dec     rcx
0x18001498f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014996  cmp     rcx, rax
0x180014999  cmovb   rax, rcx
0x18001499d  inc     rax
0x1800149a0  lea     rdi, [rbx+rax*2]
0x1800149a4  mov     r8d, 2Eh ; '.'
0x1800149aa  mov     rdx, rdi
0x1800149ad  mov     rcx, rbx
0x1800149b0  call    __std_find_last_trivial_2
0x1800149b5  mov     rdx, rax
0x1800149b8  cmp     rax, rdi
0x1800149bb  jz      loc_180014B60
0x1800149c1  sub     rdx, rbx
0x1800149c4  sar     rdx, 1
0x1800149c7  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800149cb  jz      loc_180014B60
0x1800149d1  mov     rdi, [rbp+var_30]
0x1800149d5  cmp     rdx, rdi
0x1800149d8  ja      short loc_1800149F3
0x1800149da  mov     [rbp+var_30], rdx
0x1800149de  lea     rax, [rbp+lpLibFileName]
0x1800149e2  cmp     [rbp+var_28], 7
0x1800149e7  cmova   rax, [rbp+lpLibFileName]
0x1800149ec  mov     [rax+rdx*2], r14w
0x1800149f1  jmp     short loc_180014A48
0x1800149f3  mov     rcx, rdx
0x1800149f6  sub     rcx, rdi
0x1800149f9  mov     r9, [rbp+var_28]
0x1800149fd  mov     rax, r9
0x180014a00  sub     rax, rdi
0x180014a03  cmp     rcx, rax
0x180014a06  ja      short loc_180014A30
0x180014a08  mov     [rbp+var_30], rdx
0x180014a0c  lea     r8, [rbp+lpLibFileName]
0x180014a10  cmp     r9, 7
0x180014a14  cmova   r8, [rbp+lpLibFileName]
0x180014a19  lea     rdi, [r8+rdi*2]
0x180014a1d  test    rcx, rcx
0x180014a20  jz      short loc_180014A29
0x180014a22  movzx   eax, r14w
0x180014a26  rep stosw
0x180014a29  mov     [r8+rdx*2], r14w
0x180014a2e  jmp     short loc_180014A48
0x180014a30  lfence
0x180014a33  mov     [rsp+78h+var_58], r14w; __int16
0x180014a39  mov     r9, rcx
0x180014a3c  mov     rdx, rcx
0x180014a3f  lea     rcx, [rbp+lpLibFileName]; Src
0x180014a43  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x180014a48  lea     rdx, aDll; ".dll"
0x180014a4f  lea     rcx, [rbp+lpLibFileName]; Src
0x180014a53  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180014a58  lea     rcx, [rbp+lpLibFileName]
0x180014a5c  cmp     [rbp+var_28], 7
0x180014a61  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180014a66  xor     edx, edx; hFile
0x180014a68  mov     r8d, 1000h; dwFlags
0x180014a6e  call    LoadLibraryExW_0
0x180014a73  mov     rbx, rax
0x180014a76  mov     r8, [rbp+var_30]
0x180014a7a  lea     rcx, [r8-4]
0x180014a7e  cmp     rcx, r8
0x180014a81  ja      short loc_180014A9C
0x180014a83  mov     [rbp+var_30], rcx
0x180014a87  lea     rax, [rbp+lpLibFileName]
0x180014a8b  cmp     [rbp+var_28], 7
0x180014a90  cmova   rax, [rbp+lpLibFileName]
0x180014a95  mov     [rax+rcx*2], r14w
0x180014a9a  jmp     short loc_180014AF3
0x180014a9c  mov     rdi, [rbp+var_28]
0x180014aa0  mov     rax, rdi
0x180014aa3  sub     rax, r8
0x180014aa6  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x180014aaa  jb      short loc_180014ADA
0x180014aac  mov     [rbp+var_30], rcx
0x180014ab0  lea     rdx, [rbp+lpLibFileName]
0x180014ab4  cmp     rdi, 7
0x180014ab8  cmova   rdx, [rbp+lpLibFileName]
0x180014abd  lea     rdi, [rdx+r8*2]
0x180014ac1  movzx   eax, r14w
0x180014ac5  mov     rcx, 7FFFFFFFFFFFFFFCh
0x180014acf  rep stosw
0x180014ad2  mov     [rdx+r8*2-8], r14w
0x180014ad8  jmp     short loc_180014AF3
0x180014ada  mov     [rsp+78h+var_58], r14w; __int16
0x180014ae0  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x180014ae7  mov     r9, rdx
0x180014aea  lea     rcx, [rbp+lpLibFileName]; Src
0x180014aee  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x180014af3  test    rbx, rbx
0x180014af6  jz      loc_180014971
0x180014afc  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180014b03  mov     rcx, rbx; hModule
0x180014b06  call    WINRT_IMPL_GetProcAddress
0x180014b0b  test    rax, rax
0x180014b0e  jnz     short loc_180014B1D
0x180014b10  mov     rcx, rbx; hLibModule
0x180014b13  call    WINRT_IMPL_FreeLibrary
0x180014b18  jmp     loc_180014971
0x180014b1d  mov     [rbp+var_48], r14
0x180014b21  lea     rdx, [rbp+var_48]
0x180014b25  mov     rcx, [r12]
0x180014b29  call    cs:__guard_dispatch_icall_fptr
0x180014b2f  test    eax, eax
0x180014b31  jz      short loc_180014B4F
0x180014b33  cmp     [rbp+var_48], r14
0x180014b37  jz      short loc_180014B42
0x180014b39  lea     rcx, [rbp+var_48]
0x180014b3d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014b42  mov     rcx, rbx; hLibModule
0x180014b45  call    WINRT_IMPL_FreeLibrary
0x180014b4a  jmp     loc_180014971
0x180014b4f  mov     rax, [rbp+var_48]
0x180014b53  mov     [rbp+var_48], r14
0x180014b57  mov     [r13+0], rax
0x180014b5b  mov     [r15], r14d
0x180014b5e  jmp     short loc_180014B6E
0x180014b60  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180014b64  xor     ecx, ecx; dwReserved
0x180014b66  call    SetErrorInfo_0
0x180014b6b  mov     [r15], esi
0x180014b6e  lea     rcx, [rbp+lpLibFileName]
0x180014b72  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014b77  cmp     [rbp+pperrinfo], r14
0x180014b7b  jz      short loc_180014B86
0x180014b7d  lea     rcx, [rbp+pperrinfo]
0x180014b81  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014b86  mov     rax, r15
0x180014b89  mov     rcx, [rbp+var_18]
0x180014b8d  xor     rcx, rsp; StackCookie
0x180014b90  call    __security_check_cookie
0x180014b95  add     rsp, 78h
0x180014b99  pop     r15
0x180014b9b  pop     r14
0x180014b9d  pop     r13
0x180014b9f  pop     r12
0x180014ba1  pop     rdi
0x180014ba2  pop     rsi
0x180014ba3  pop     rbx
0x180014ba4  pop     rbp
0x180014ba5  retn
```
