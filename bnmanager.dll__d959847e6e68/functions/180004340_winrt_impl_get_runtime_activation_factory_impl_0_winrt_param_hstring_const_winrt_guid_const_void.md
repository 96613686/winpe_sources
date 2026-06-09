# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180004340`
- end: `0x180004683`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `835`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000355c`
- `0x1800038cc`
- `0x180003b84`

## callees

- `0x1800013c0`
- `0x1800017c0`
- `0x180002338`
- `0x180002359`
- `0x180002371`
- `0x180002389`
- `0x1800023a1`
- `0x1800023b9`
- `0x1800025d0`
- `0x1800030a0`
- `0x18000322c`
- `0x180004340`
- `0x180005178`
- `0x18000c010`
- `0x18000d010`

## string_xrefs

- `0x1800043a9`: `combase.dll`
- `0x1800045c2`: `DllGetActivationFactory`

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
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  LPCWSTR *v17; // rcx
  unsigned __int64 v18; // rcx
  LPCWSTR *v19; // r8
  _WORD *v20; // rdi
  unsigned __int64 v21; // rdi
  LPCWSTR *v22; // rcx
  const WCHAR *v23; // rcx
  HMODULE v24; // rdi
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // r8
  LPCWSTR *v27; // rcx
  FARPROC v28; // rax
  unsigned int (__fastcall ***v30)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-28h]
  unsigned __int64 v34; // [rsp+58h] [rbp-20h]

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
    v30 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v30);
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
      v12 = lpLibFileName;
      if ( v34 > 7 )
        v12 = (LPCWSTR *)lpLibFileName[0];
      if ( !v33
        || (v13 = (char *)v12 + 2 * v33,
            last_trivial_2 = _std_find_last_trivial_2(v12, v13, 46),
            (char *)last_trivial_2 == v13)
        || (v15 = (last_trivial_2 - (__int64)v12) >> 1, v15 == -1) )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_54;
      }
      v16 = v33;
      if ( v15 > v33 )
      {
        v18 = v15 - v33;
        if ( v15 - v33 > v34 - v33 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
        }
        else
        {
          v33 = (last_trivial_2 - (__int64)v12) >> 1;
          v19 = lpLibFileName;
          if ( v34 > 7 )
            v19 = (LPCWSTR *)lpLibFileName[0];
          v20 = (_WORD *)v19 + v16;
          if ( v18 )
          {
            while ( v18 )
            {
              *v20++ = 0;
              --v18;
            }
          }
          *((_WORD *)v19 + v15) = 0;
        }
      }
      else
      {
        v33 = (last_trivial_2 - (__int64)v12) >> 1;
        v17 = lpLibFileName;
        if ( v34 > 7 )
          v17 = (LPCWSTR *)lpLibFileName[0];
        *((_WORD *)v17 + v15) = 0;
      }
      v21 = v33;
      if ( v34 - v33 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v33 += 4LL;
        v22 = lpLibFileName;
        if ( v34 > 7 )
          v22 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v22 + 2 * v21) = (LPCWSTR)0x6C006C0064002ELL;
        *((_WORD *)v22 + v21 + 4) = 0;
      }
      v23 = (const WCHAR *)lpLibFileName;
      if ( v34 > 7 )
        v23 = lpLibFileName[0];
      v24 = LoadLibraryExW_0(v23, 0, 0x1000u);
      v25 = v33;
      v26 = v33 - 4;
      v27 = lpLibFileName;
      if ( v33 >= 4 )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
LABEL_42:
        *((_WORD *)v27 + v26) = 0;
        continue;
      }
      if ( v34 - v33 >= 0xFFFFFFFFFFFFFFFCuLL )
      {
        v33 -= 4LL;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpLibFileName[0];
        *(LPCWSTR *)((char *)v27 + 2 * v25) = 0;
        goto LABEL_42;
      }
      std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(lpLibFileName);
    }
    while ( !v24 );
    v28 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
    if ( !v28 )
      goto LABEL_50;
    v30 = 0;
    if ( !((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v28)(
            *a2,
            &v30)
      && !(**v30)(v30, a3, a4) )
    {
      break;
    }
    if ( v30 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v30);
LABEL_50:
    WINRT_IMPL_FreeLibrary(v24);
  }
  *a1 = 0;
  if ( v30 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v30);
LABEL_54:
  std::wstring::~wstring(lpLibFileName);
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180004340  push    rbp
0x180004342  push    rbx
0x180004343  push    rsi
0x180004344  push    rdi
0x180004345  push    r12
0x180004347  push    r13
0x180004349  push    r14
0x18000434b  push    r15
0x18000434d  mov     rbp, rsp
0x180004350  sub     rsp, 78h
0x180004354  mov     rax, cs:__security_cookie
0x18000435b  xor     rax, rsp
0x18000435e  mov     [rbp+var_18], rax
0x180004362  mov     r12, r9
0x180004365  mov     r15, r8
0x180004368  mov     r13, rdx
0x18000436b  mov     rsi, rcx
0x18000436e  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180004375  xor     r14d, r14d
0x180004378  mov     r8, r9
0x18000437b  mov     rdx, r15
0x18000437e  mov     rcx, [r13+0]
0x180004382  test    rax, rax
0x180004385  jz      short loc_180004393
0x180004387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000438c  mov     [rsi], eax
0x18000438e  jmp     loc_180004663
0x180004393  call    RoGetActivationFactory_0
0x180004398  mov     ebx, eax
0x18000439a  cmp     eax, 800401F0h
0x18000439f  jnz     short loc_1800043F2
0x1800043a1  xor     edx, edx; hFile
0x1800043a3  mov     r8d, 1000h; dwFlags
0x1800043a9  lea     rcx, LibFileName; "combase.dll"
0x1800043b0  call    LoadLibraryExW_0
0x1800043b5  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x1800043bc  mov     rcx, rax; hModule
0x1800043bf  call    WINRT_IMPL_GetProcAddress
0x1800043c4  test    rax, rax
0x1800043c7  jnz     short loc_1800043D4
0x1800043c9  mov     dword ptr [rsi], 800401F0h
0x1800043cf  jmp     loc_180004663
0x1800043d4  mov     [rbp+var_48], r14
0x1800043d8  lea     rcx, [rbp+var_48]
0x1800043dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e1  mov     r8, r12
0x1800043e4  mov     rdx, r15
0x1800043e7  mov     rcx, [r13+0]
0x1800043eb  call    RoGetActivationFactory_0
0x1800043f0  mov     ebx, eax
0x1800043f2  test    ebx, ebx
0x1800043f4  jnz     short loc_1800043FE
0x1800043f6  mov     [rsi], r14d
0x1800043f9  jmp     loc_180004663
0x1800043fe  mov     [rbp+pperrinfo], r14
0x180004402  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180004406  xor     ecx, ecx; dwReserved
0x180004408  call    GetErrorInfo_0
0x18000440d  mov     rdx, r13
0x180004410  lea     rcx, [rbp+lpLibFileName]
0x180004414  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180004419  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000441d  mov     rax, [rbp+var_28]
0x180004421  lea     r14, [rbp+lpLibFileName]
0x180004425  cmp     [rbp+var_20], 7
0x18000442a  cmova   r14, [rbp+lpLibFileName]
0x18000442f  test    rax, rax
0x180004432  jz      loc_18000463D
0x180004438  dec     rax
0x18000443b  cmp     rax, rcx
0x18000443e  cmovnb  rax, rcx
0x180004442  inc     rax
0x180004445  lea     rdi, [r14+rax*2]
0x180004449  mov     r8d, 2Eh ; '.'
0x18000444f  mov     rdx, rdi
0x180004452  mov     rcx, r14
0x180004455  call    __std_find_last_trivial_2
0x18000445a  mov     rdx, rax
0x18000445d  cmp     rax, rdi
0x180004460  jz      loc_18000463D
0x180004466  sub     rdx, r14
0x180004469  sar     rdx, 1
0x18000446c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180004470  jz      loc_18000463D
0x180004476  mov     rdi, [rbp+var_28]
0x18000447a  cmp     rdx, rdi
0x18000447d  ja      short loc_180004499
0x18000447f  mov     [rbp+var_28], rdx
0x180004483  lea     rcx, [rbp+lpLibFileName]
0x180004487  cmp     [rbp+var_20], 7
0x18000448c  cmova   rcx, [rbp+lpLibFileName]
0x180004491  xor     eax, eax
0x180004493  mov     [rcx+rdx*2], ax
0x180004497  jmp     short loc_1800044E6
0x180004499  mov     rcx, rdx
0x18000449c  sub     rcx, rdi
0x18000449f  mov     rax, [rbp+var_20]
0x1800044a3  sub     rax, rdi
0x1800044a6  cmp     rcx, rax
0x1800044a9  ja      short loc_1800044D7
0x1800044ab  mov     [rbp+var_28], rdx
0x1800044af  lea     r8, [rbp+lpLibFileName]
0x1800044b3  cmp     [rbp+var_20], 7
0x1800044b8  cmova   r8, [rbp+lpLibFileName]
0x1800044bd  lea     rdi, [r8+rdi*2]
0x1800044c1  test    rcx, rcx
0x1800044c4  jz      short loc_1800044CE
0x1800044c6  xor     eax, eax
0x1800044c8  movzx   eax, ax
0x1800044cb  rep stosw
0x1800044ce  xor     eax, eax
0x1800044d0  mov     [r8+rdx*2], ax
0x1800044d5  jmp     short loc_1800044E6
0x1800044d7  mov     r9, rcx
0x1800044da  mov     rdx, rcx
0x1800044dd  lea     rcx, [rbp+lpLibFileName]; Src
0x1800044e1  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800044e6  mov     rdi, [rbp+var_28]
0x1800044ea  mov     rax, [rbp+var_20]
0x1800044ee  sub     rax, rdi
0x1800044f1  mov     ecx, 4
0x1800044f6  cmp     rax, rcx
0x1800044f9  jb      short loc_180004527
0x1800044fb  lea     rdx, [rdi+4]
0x1800044ff  mov     [rbp+var_28], rdx
0x180004503  lea     rcx, [rbp+lpLibFileName]
0x180004507  cmp     [rbp+var_20], 7
0x18000450c  cmova   rcx, [rbp+lpLibFileName]
0x180004511  mov     rax, 6C006C0064002Eh
0x18000451b  mov     [rcx+rdi*2], rax
0x18000451f  xor     eax, eax
0x180004521  mov     [rcx+rdx*2], ax
0x180004525  jmp     short loc_180004538
0x180004527  mov     [rsp+78h+var_58], rcx; __int64
0x18000452c  mov     rdx, rcx
0x18000452f  lea     rcx, [rbp+lpLibFileName]; Src
0x180004533  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180004538  lea     rcx, [rbp+lpLibFileName]
0x18000453c  cmp     [rbp+var_20], 7
0x180004541  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180004546  xor     edx, edx; hFile
0x180004548  mov     r8d, 1000h; dwFlags
0x18000454e  call    LoadLibraryExW_0
0x180004553  mov     rdi, rax
0x180004556  mov     rdx, [rbp+var_28]
0x18000455a  lea     r8, [rdx-4]
0x18000455e  lea     rcx, [rbp+lpLibFileName]; Src
0x180004562  cmp     r8, rdx
0x180004565  ja      short loc_180004579
0x180004567  mov     [rbp+var_28], r8
0x18000456b  cmp     [rbp+var_20], 7
0x180004570  cmova   rcx, [rbp+lpLibFileName]
0x180004575  xor     eax, eax
0x180004577  jmp     short loc_1800045A0
0x180004579  mov     rax, [rbp+var_20]
0x18000457d  sub     rax, rdx
0x180004580  mov     r10, 0FFFFFFFFFFFFFFFCh
0x180004587  cmp     rax, r10
0x18000458a  jb      short loc_1800045A7
0x18000458c  mov     [rbp+var_28], r8
0x180004590  cmp     [rbp+var_20], 7
0x180004595  cmova   rcx, [rbp+lpLibFileName]
0x18000459a  xor     eax, eax
0x18000459c  mov     [rcx+rdx*2], rax
0x1800045a0  mov     [rcx+r8*2], ax
0x1800045a5  jmp     short loc_1800045B2
0x1800045a7  mov     r9, r10
0x1800045aa  mov     rdx, r10
0x1800045ad  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800045b2  test    rdi, rdi
0x1800045b5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800045bc  jz      loc_18000441D
0x1800045c2  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1800045c9  mov     rcx, rdi; hModule
0x1800045cc  call    WINRT_IMPL_GetProcAddress
0x1800045d1  test    rax, rax
0x1800045d4  jz      short loc_180004618
0x1800045d6  mov     [rbp+var_48], 0
0x1800045de  lea     rdx, [rbp+var_48]
0x1800045e2  mov     rcx, [r13+0]
0x1800045e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045eb  test    eax, eax
0x1800045ed  jnz     short loc_180004608
0x1800045ef  mov     rcx, [rbp+var_48]
0x1800045f3  mov     rax, [rcx]
0x1800045f6  mov     r8, r12
0x1800045f9  mov     rdx, r15
0x1800045fc  mov     rax, [rax]
0x1800045ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004604  test    eax, eax
0x180004606  jz      short loc_180004625
0x180004608  cmp     [rbp+var_48], 0
0x18000460d  jz      short loc_180004618
0x18000460f  lea     rcx, [rbp+var_48]
0x180004613  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004618  mov     rcx, rdi; hLibModule
0x18000461b  call    WINRT_IMPL_FreeLibrary
0x180004620  jmp     loc_180004419
0x180004625  mov     dword ptr [rsi], 0
0x18000462b  cmp     [rbp+var_48], 0
0x180004630  jz      short loc_18000464A
0x180004632  lea     rcx, [rbp+var_48]
0x180004636  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000463b  jmp     short loc_18000464A
0x18000463d  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180004641  xor     ecx, ecx; dwReserved
0x180004643  call    SetErrorInfo_0
0x180004648  mov     [rsi], ebx
0x18000464a  lea     rcx, [rbp+lpLibFileName]
0x18000464e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004653  cmp     [rbp+pperrinfo], 0
0x180004658  jz      short loc_180004663
0x18000465a  lea     rcx, [rbp+pperrinfo]
0x18000465e  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004663  mov     rax, rsi
0x180004666  mov     rcx, [rbp+var_18]
0x18000466a  xor     rcx, rsp; StackCookie
0x18000466d  call    __security_check_cookie
0x180004672  add     rsp, 78h
0x180004676  pop     r15
0x180004678  pop     r14
0x18000467a  pop     r13
0x18000467c  pop     r12
0x18000467e  pop     rdi
0x18000467f  pop     rsi
0x180004680  pop     rbx
0x180004681  pop     rbp
0x180004682  retn
```
