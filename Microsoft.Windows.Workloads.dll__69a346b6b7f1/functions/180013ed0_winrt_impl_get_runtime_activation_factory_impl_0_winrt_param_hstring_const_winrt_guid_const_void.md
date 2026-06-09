# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180013ed0`
- end: `0x180014226`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `854`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004c70`
- `0x180014230`
- `0x18001b040`
- `0x18001c640`
- `0x18002ade0`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x1800040a0`
- `0x180013ed0`
- `0x180014650`
- `0x1800146e0`
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

- `0x180013f3b`: `combase.dll`
- `0x18001416b`: `DllGetActivationFactory`

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
  unsigned int (__fastcall ***v35)(_QWORD, __int64, __int64); // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v37; // [rsp+50h] [rbp-28h]
  unsigned __int64 v38; // [rsp+58h] [rbp-20h]
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
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v35);
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
    do
    {
      v15 = lpLibFileName;
      if ( v38 > 7 )
        v15 = (LPCWSTR *)lpLibFileName[0];
      if ( !v37
        || (v16 = (char *)v15 + 2 * v37,
            last_trivial_2 = _std_find_last_trivial_2(v15, v16, 46),
            (char *)last_trivial_2 == v16)
        || (v18 = (last_trivial_2 - (__int64)v15) >> 1, v18 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_54;
      }
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
    }
    while ( !v25 );
    v32 = WINRT_IMPL_GetProcAddress(v25, "DllGetActivationFactory");
    if ( v32 )
      break;
LABEL_50:
    WINRT_IMPL_FreeLibrary(v25);
  }
  v35 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v32)(*a2, &v35)
    || (**v35)(v35, a3, a4) )
  {
    if ( v35 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v35);
    goto LABEL_50;
  }
  *a1 = 0;
  if ( v35 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v35);
LABEL_54:
  std::wstring::_Tidy_deallocate(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180013ed0  push    rbp
0x180013ed2  push    rbx
0x180013ed3  push    rsi
0x180013ed4  push    rdi
0x180013ed5  push    r12
0x180013ed7  push    r13
0x180013ed9  push    r14
0x180013edb  push    r15
0x180013edd  mov     rbp, rsp
0x180013ee0  sub     rsp, 78h
0x180013ee4  mov     rax, cs:__security_cookie
0x180013eeb  xor     rax, rsp
0x180013eee  mov     [rbp+var_10], rax
0x180013ef2  mov     rdi, r9
0x180013ef5  mov     [rbp+var_48], r9
0x180013ef9  mov     r13, r8
0x180013efc  mov     r12, rdx
0x180013eff  mov     r15, rcx
0x180013f02  mov     rcx, [rdx]
0x180013f05  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180013f0c  mov     r8, r9
0x180013f0f  mov     rdx, r13
0x180013f12  test    rax, rax
0x180013f15  jz      short loc_180013F25
0x180013f17  call    cs:__guard_dispatch_icall_fptr
0x180013f1d  mov     [r15], eax
0x180013f20  jmp     loc_180014206
0x180013f25  call    RoGetActivationFactory_0
0x180013f2a  mov     esi, eax
0x180013f2c  cmp     eax, 800401F0h
0x180013f31  jnz     short loc_180013F82
0x180013f33  xor     edx, edx; hFile
0x180013f35  mov     r8d, 1000h; dwFlags
0x180013f3b  lea     rcx, aCombaseDll; "combase.dll"
0x180013f42  call    LoadLibraryExW_0
0x180013f47  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180013f4e  mov     rcx, rax; hModule
0x180013f51  call    WINRT_IMPL_GetProcAddress
0x180013f56  test    rax, rax
0x180013f59  jnz     short loc_180013F67
0x180013f5b  mov     dword ptr [r15], 800401F0h
0x180013f62  jmp     loc_180014206
0x180013f67  lea     rcx, [rbp+var_40]
0x180013f6b  call    cs:__guard_dispatch_icall_fptr
0x180013f71  mov     r8, rdi
0x180013f74  mov     rdx, r13
0x180013f77  mov     rcx, [r12]
0x180013f7b  call    RoGetActivationFactory_0
0x180013f80  mov     esi, eax
0x180013f82  xor     r14d, r14d
0x180013f85  test    esi, esi
0x180013f87  jnz     short loc_180013F91
0x180013f89  mov     [r15], r14d
0x180013f8c  jmp     loc_180014206
0x180013f91  mov     [rbp+pperrinfo], r14
0x180013f95  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180013f99  xor     ecx, ecx; dwReserved
0x180013f9b  call    GetErrorInfo_0
0x180013fa0  xorps   xmm0, xmm0
0x180013fa3  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180013fa7  mov     [rbp+var_28], r14
0x180013fab  mov     [rbp+var_20], r14
0x180013faf  mov     rax, [r12]
0x180013fb3  test    rax, rax
0x180013fb6  jz      short loc_180013FC2
0x180013fb8  mov     rdx, [rax+10h]
0x180013fbc  mov     r8d, [rax+4]
0x180013fc0  jmp     short loc_180013FCC
0x180013fc2  lea     rdx, Src
0x180013fc9  mov     r8, r14
0x180013fcc  lea     rcx, [rbp+lpLibFileName]
0x180013fd0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180013fd5  nop     word ptr [rax+rax+00000000h]
0x180013fe0  lea     rbx, [rbp+lpLibFileName]
0x180013fe4  cmp     [rbp+var_20], 7
0x180013fe9  cmova   rbx, [rbp+lpLibFileName]
0x180013fee  mov     rcx, [rbp+var_28]
0x180013ff2  test    rcx, rcx
0x180013ff5  jz      loc_1800141E0
0x180013ffb  dec     rcx
0x180013ffe  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014005  cmp     rcx, rax
0x180014008  cmovb   rax, rcx
0x18001400c  inc     rax
0x18001400f  lea     rdi, [rbx+rax*2]
0x180014013  mov     r8d, 2Eh ; '.'
0x180014019  mov     rdx, rdi
0x18001401c  mov     rcx, rbx
0x18001401f  call    __std_find_last_trivial_2
0x180014024  mov     rdx, rax
0x180014027  cmp     rax, rdi
0x18001402a  jz      loc_1800141E0
0x180014030  sub     rdx, rbx
0x180014033  sar     rdx, 1
0x180014036  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001403a  jz      loc_1800141E0
0x180014040  mov     rdi, [rbp+var_28]
0x180014044  cmp     rdx, rdi
0x180014047  ja      short loc_180014062
0x180014049  mov     [rbp+var_28], rdx
0x18001404d  lea     rax, [rbp+lpLibFileName]
0x180014051  cmp     [rbp+var_20], 7
0x180014056  cmova   rax, [rbp+lpLibFileName]
0x18001405b  mov     [rax+rdx*2], r14w
0x180014060  jmp     short loc_1800140B7
0x180014062  mov     rcx, rdx
0x180014065  sub     rcx, rdi
0x180014068  mov     r9, [rbp+var_20]
0x18001406c  mov     rax, r9
0x18001406f  sub     rax, rdi
0x180014072  cmp     rcx, rax
0x180014075  ja      short loc_18001409F
0x180014077  mov     [rbp+var_28], rdx
0x18001407b  lea     r8, [rbp+lpLibFileName]
0x18001407f  cmp     r9, 7
0x180014083  cmova   r8, [rbp+lpLibFileName]
0x180014088  lea     rdi, [r8+rdi*2]
0x18001408c  test    rcx, rcx
0x18001408f  jz      short loc_180014098
0x180014091  movzx   eax, r14w
0x180014095  rep stosw
0x180014098  mov     [r8+rdx*2], r14w
0x18001409d  jmp     short loc_1800140B7
0x18001409f  lfence
0x1800140a2  mov     [rsp+78h+var_58], r14w; __int16
0x1800140a8  mov     r9, rcx
0x1800140ab  mov     rdx, rcx
0x1800140ae  lea     rcx, [rbp+lpLibFileName]; Src
0x1800140b2  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x1800140b7  lea     rdx, aDll; ".dll"
0x1800140be  lea     rcx, [rbp+lpLibFileName]; Src
0x1800140c2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800140c7  lea     rcx, [rbp+lpLibFileName]
0x1800140cb  cmp     [rbp+var_20], 7
0x1800140d0  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800140d5  xor     edx, edx; hFile
0x1800140d7  mov     r8d, 1000h; dwFlags
0x1800140dd  call    LoadLibraryExW_0
0x1800140e2  mov     rbx, rax
0x1800140e5  mov     r8, [rbp+var_28]
0x1800140e9  lea     rcx, [r8-4]
0x1800140ed  cmp     rcx, r8
0x1800140f0  ja      short loc_18001410B
0x1800140f2  mov     [rbp+var_28], rcx
0x1800140f6  lea     rax, [rbp+lpLibFileName]
0x1800140fa  cmp     [rbp+var_20], 7
0x1800140ff  cmova   rax, [rbp+lpLibFileName]
0x180014104  mov     [rax+rcx*2], r14w
0x180014109  jmp     short loc_180014162
0x18001410b  mov     rdi, [rbp+var_20]
0x18001410f  mov     rax, rdi
0x180014112  sub     rax, r8
0x180014115  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x180014119  jb      short loc_180014149
0x18001411b  mov     [rbp+var_28], rcx
0x18001411f  lea     rdx, [rbp+lpLibFileName]
0x180014123  cmp     rdi, 7
0x180014127  cmova   rdx, [rbp+lpLibFileName]
0x18001412c  lea     rdi, [rdx+r8*2]
0x180014130  movzx   eax, r14w
0x180014134  mov     rcx, 7FFFFFFFFFFFFFFCh
0x18001413e  rep stosw
0x180014141  mov     [rdx+r8*2-8], r14w
0x180014147  jmp     short loc_180014162
0x180014149  mov     [rsp+78h+var_58], r14w; __int16
0x18001414f  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x180014156  mov     r9, rdx
0x180014159  lea     rcx, [rbp+lpLibFileName]; Src
0x18001415d  call    ??$_Reallocate_grow_by@V_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_a3050a43f3157934f354774ab3dd2e02_@@_K_W@Z; std::wstring::_Reallocate_grow_by<_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t>(unsigned __int64,_lambda_a3050a43f3157934f354774ab3dd2e02_,unsigned __int64,wchar_t)
0x180014162  test    rbx, rbx
0x180014165  jz      loc_180013FE0
0x18001416b  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180014172  mov     rcx, rbx; hModule
0x180014175  call    WINRT_IMPL_GetProcAddress
0x18001417a  test    rax, rax
0x18001417d  jz      short loc_1800141BF
0x18001417f  mov     [rbp+var_40], r14
0x180014183  lea     rdx, [rbp+var_40]
0x180014187  mov     rcx, [r12]
0x18001418b  call    cs:__guard_dispatch_icall_fptr
0x180014191  test    eax, eax
0x180014193  jnz     short loc_1800141B0
0x180014195  mov     rcx, [rbp+var_40]
0x180014199  mov     rax, [rcx]
0x18001419c  mov     r8, [rbp+var_48]
0x1800141a0  mov     rdx, r13
0x1800141a3  mov     rax, [rax]
0x1800141a6  call    cs:__guard_dispatch_icall_fptr
0x1800141ac  test    eax, eax
0x1800141ae  jz      short loc_1800141CC
0x1800141b0  cmp     [rbp+var_40], r14
0x1800141b4  jz      short loc_1800141BF
0x1800141b6  lea     rcx, [rbp+var_40]
0x1800141ba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800141bf  mov     rcx, rbx; hLibModule
0x1800141c2  call    WINRT_IMPL_FreeLibrary
0x1800141c7  jmp     loc_180013FE0
0x1800141cc  mov     [r15], r14d
0x1800141cf  cmp     [rbp+var_40], r14
0x1800141d3  jz      short loc_1800141EE
0x1800141d5  lea     rcx, [rbp+var_40]
0x1800141d9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800141de  jmp     short loc_1800141EE
0x1800141e0  mov     rdx, [rbp+pperrinfo]; perrinfo
0x1800141e4  xor     ecx, ecx; dwReserved
0x1800141e6  call    SetErrorInfo_0
0x1800141eb  mov     [r15], esi
0x1800141ee  lea     rcx, [rbp+lpLibFileName]
0x1800141f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800141f7  cmp     [rbp+pperrinfo], r14
0x1800141fb  jz      short loc_180014206
0x1800141fd  lea     rcx, [rbp+pperrinfo]
0x180014201  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180014206  mov     rax, r15
0x180014209  mov     rcx, [rbp+var_10]
0x18001420d  xor     rcx, rsp; StackCookie
0x180014210  call    __security_check_cookie
0x180014215  add     rsp, 78h
0x180014219  pop     r15
0x18001421b  pop     r14
0x18001421d  pop     r13
0x18001421f  pop     r12
0x180014221  pop     rdi
0x180014222  pop     rsi
0x180014223  pop     rbx
0x180014224  pop     rbp
0x180014225  retn
```
