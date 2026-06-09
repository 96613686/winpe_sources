# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t)

- ea: `0x180001530`
- end: `0x1800017a8`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z`
- size: `632`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `14`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180001960`
- `0x1800019c0`
- `0x1800019e0`
- `0x180001a00`
- `0x180001a20`
- `0x180001a40`
- `0x180001a60`
- `0x180001a80`
- `0x180001aa0`
- `0x180001ac0`
- `0x180001ae0`
- `0x180001b00`
- `0x180001b20`
- `0x180001b40`

## callees

- `0x1800012f0`
- `0x180001530`
- `0x180001850`
- `0x180005cb0`
- `0x180007250`
- `0x180007262`
- `0x180007280`
- `0x18000b80d`
- `0x18000b81f`
- `0x18000b82b`
- `0x18000b930`
- `0x18000b990`
- `0x18000bd50`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180001710`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180001710`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800017a1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800017a1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000171c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000171c`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800016ca`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800016ca`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2)
{
  volatile signed __int32 *v4; // rbx
  void **v5; // rsi
  IErrorInfo *v6; // rcx
  void *v7; // r14
  void *v8; // r12
  void *v9; // rdi
  void (__fastcall *v10)(void *, __int64); // r14
  void (__fastcall ***v11)(_QWORD, __int64 *, void **); // rcx
  OLECHAR *v12; // rax
  UINT v13; // esi
  void *v14; // r12
  wint_t *v15; // r14
  unsigned int v16; // edx
  struct winrt::impl::shared_hstring_header *v17; // rax
  size_t v18; // r8
  void *v19; // rcx
  int v20; // eax
  HANDLE ProcessHeap; // rax
  void *v23; // [rsp+20h] [rbp-20h] BYREF
  void *Src; // [rsp+28h] [rbp-18h] BYREF
  IErrorInfo *pperrinfo; // [rsp+30h] [rbp-10h] BYREF

  v4 = 0;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v5 = (void **)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  v6 = pperrinfo;
  if ( pperrinfo )
  {
    Src = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, void **))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &Src);
    v7 = Src;
    v23 = Src;
    v6 = pperrinfo;
  }
  else
  {
    v23 = 0;
    v7 = 0;
  }
  if ( v5 == &v23 )
  {
    v8 = *v5;
    if ( v7 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
      v6 = pperrinfo;
    }
  }
  else
  {
    if ( *v5 )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
      v6 = pperrinfo;
    }
    *v5 = v7;
    v8 = v7;
  }
  if ( v8 )
  {
    v9 = *v5;
    v10 = *(void (__fastcall **)(void *, __int64))(*(_QWORD *)*v5 + 32LL);
    if ( *(_QWORD *)a1 )
    {
      WINRT_IMPL_SysFreeString(*(BSTR *)a1);
      *(_QWORD *)a1 = 0;
    }
    v10(v9, a1);
    v11 = (void (__fastcall ***)(_QWORD, __int64 *, void **))*v5;
    if ( *v5 )
    {
      Src = 0;
      (**v11)(v11, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &Src);
      if ( Src )
      {
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)Src + 40LL))(Src, 0);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&Src);
      }
    }
    goto LABEL_34;
  }
  v12 = 0;
  Src = 0;
  if ( v6 )
  {
    ((void (__fastcall *)(IErrorInfo *, void **))v6->lpVtbl->GetDescription)(v6, &Src);
    v12 = (OLECHAR *)Src;
  }
  if ( v12 )
  {
    v13 = SysStringLen_0(v12);
    v14 = Src;
    v15 = (wint_t *)((char *)Src + 2 * v13 - 2);
    if ( v13 )
    {
      while ( iswspace(*v15) )
      {
        --v15;
        if ( !--v13 )
          goto LABEL_29;
      }
      v17 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v13, v16);
      v4 = (volatile signed __int32 *)v17;
      v18 = 2LL * v13;
      v19 = (char *)v17 + 28;
      if ( v18 )
      {
        if ( v17 != (struct winrt::impl::shared_hstring_header *)-28LL )
        {
          if ( v14 )
          {
            memmove(v19, v14, v18);
            goto LABEL_29;
          }
          memset(v19, 0, v18);
        }
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
    }
  }
LABEL_29:
  winrt::hresult_error::originate(a1, a2, v4);
  if ( v4 )
  {
    v20 = _InterlockedDecrement(v4 + 6);
    if ( v20 )
    {
      if ( v20 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
  }
  if ( Src )
    WINRT_IMPL_SysFreeString((BSTR)Src);
LABEL_34:
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180001530  mov     [rsp-28h+arg_8], rbx
0x180001535  mov     [rsp-28h+arg_10], rsi
0x18000153a  push    rbp
0x18000153b  push    rdi
0x18000153c  push    r12
0x18000153e  push    r14
0x180001540  push    r15
0x180001542  mov     rbp, rsp
0x180001545  sub     rsp, 40h
0x180001549  mov     rax, cs:__security_cookie
0x180001550  xor     rax, rsp
0x180001553  mov     [rbp+var_8], rax
0x180001557  mov     edi, edx
0x180001559  mov     r15, rcx
0x18000155c  xor     ebx, ebx
0x18000155e  mov     [rcx], rbx
0x180001561  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180001568  mov     [rcx+0Ch], edx
0x18000156b  lea     rsi, [rcx+10h]
0x18000156f  mov     [rsi], rbx
0x180001572  mov     [rbp+pperrinfo], rbx
0x180001576  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000157a  xor     ecx, ecx; dwReserved
0x18000157c  call    GetErrorInfo_0
0x180001581  mov     rcx, [rbp+pperrinfo]
0x180001585  test    rcx, rcx
0x180001588  jnz     short loc_180001593
0x18000158a  mov     [rbp+var_20], rbx
0x18000158e  mov     r14d, ebx
0x180001591  jmp     short loc_1800015BA
0x180001593  mov     [rbp+Src], rbx
0x180001597  mov     rax, [rcx]
0x18000159a  lea     r8, [rbp+Src]
0x18000159e  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1800015a5  mov     rax, [rax]
0x1800015a8  call    cs:__guard_dispatch_icall_fptr
0x1800015ae  mov     r14, [rbp+Src]
0x1800015b2  mov     [rbp+var_20], r14
0x1800015b6  mov     rcx, [rbp+pperrinfo]
0x1800015ba  lea     rax, [rbp+var_20]
0x1800015be  cmp     rsi, rax
0x1800015c1  jz      short loc_1800015DC
0x1800015c3  cmp     [rsi], rbx
0x1800015c6  jz      short loc_1800015D4
0x1800015c8  mov     rcx, rsi
0x1800015cb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800015d0  mov     rcx, [rbp+pperrinfo]
0x1800015d4  mov     [rsi], r14
0x1800015d7  mov     r12, r14
0x1800015da  jmp     short loc_1800015F1
0x1800015dc  mov     r12, [rsi]
0x1800015df  test    r14, r14
0x1800015e2  jz      short loc_1800015F1
0x1800015e4  lea     rcx, [rbp+var_20]
0x1800015e8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800015ed  mov     rcx, [rbp+pperrinfo]
0x1800015f1  test    r12, r12
0x1800015f4  jz      loc_180001684
0x1800015fa  mov     rdi, [rsi]
0x1800015fd  mov     rax, [rdi]
0x180001600  mov     r14, [rax+20h]
0x180001604  mov     rcx, [r15]; bstrString
0x180001607  test    rcx, rcx
0x18000160a  jz      short loc_180001614
0x18000160c  call    WINRT_IMPL_SysFreeString
0x180001611  mov     [r15], rbx
0x180001614  mov     rdx, r15
0x180001617  mov     rcx, rdi
0x18000161a  mov     rax, r14
0x18000161d  call    cs:__guard_dispatch_icall_fptr
0x180001623  mov     rcx, [rsi]
0x180001626  test    rcx, rcx
0x180001629  jz      loc_180001764
0x18000162f  mov     [rbp+Src], rbx
0x180001633  mov     rax, [rcx]
0x180001636  lea     r8, [rbp+Src]
0x18000163a  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x180001641  mov     rax, [rax]
0x180001644  call    cs:__guard_dispatch_icall_fptr
0x18000164a  mov     rbx, [rbp+Src]
0x18000164e  mov     [rbp+Src], rbx
0x180001652  test    rbx, rbx
0x180001655  jz      loc_180001764
0x18000165b  mov     rax, [rbx]
0x18000165e  xor     edx, edx
0x180001660  mov     rcx, rbx
0x180001663  mov     rax, [rax+28h]
0x180001667  call    cs:__guard_dispatch_icall_fptr
0x18000166d  test    rbx, rbx
0x180001670  jz      loc_180001764
0x180001676  lea     rcx, [rbp+Src]
0x18000167a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000167f  jmp     loc_180001764
0x180001684  mov     rax, rbx
0x180001687  mov     [rbp+Src], rbx
0x18000168b  test    rcx, rcx
0x18000168e  jz      short loc_1800016A5
0x180001690  mov     rax, [rcx]
0x180001693  lea     rdx, [rbp+Src]
0x180001697  mov     rax, [rax+28h]
0x18000169b  call    cs:__guard_dispatch_icall_fptr
0x1800016a1  mov     rax, [rbp+Src]
0x1800016a5  test    rax, rax
0x1800016a8  jz      short loc_180001723
0x1800016aa  mov     rcx, rax; pbstr
0x1800016ad  call    SysStringLen_0
0x1800016b2  mov     esi, eax
0x1800016b4  mov     r12, [rbp+Src]
0x1800016b8  mov     r14d, eax
0x1800016bb  dec     r14
0x1800016be  lea     r14, [r12+r14*2]
0x1800016c2  test    eax, eax
0x1800016c4  jz      short loc_180001723
0x1800016c6  movzx   ecx, word ptr [r14]; C
0x1800016ca  call    cs:__imp_iswspace
0x1800016d0  test    eax, eax
0x1800016d2  jz      short loc_1800016DF
0x1800016d4  sub     r14, 2
0x1800016d8  add     esi, 0FFFFFFFFh
0x1800016db  jnz     short loc_1800016C6
0x1800016dd  jmp     short loc_180001723
0x1800016df  mov     ecx, esi; this
0x1800016e1  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800016e6  mov     rbx, rax
0x1800016e9  mov     r8d, esi
0x1800016ec  add     r8, r8; Size
0x1800016ef  lea     rcx, [rax+1Ch]; void *
0x1800016f3  jz      short loc_180001723
0x1800016f5  test    rcx, rcx
0x1800016f8  jz      short loc_180001710
0x1800016fa  test    r12, r12
0x1800016fd  jz      short loc_180001709
0x1800016ff  mov     rdx, r12; Src
0x180001702  call    memmove
0x180001707  jmp     short loc_180001723
0x180001709  xor     edx, edx; Val
0x18000170b  call    memset
0x180001710  call    cs:__imp__errno
0x180001716  mov     dword ptr [rax], 16h
0x18000171c  call    cs:__imp__invalid_parameter_noinfo
0x180001722  nop
0x180001723  mov     r8, rbx
0x180001726  mov     edx, edi
0x180001728  mov     rcx, r15
0x18000172b  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAX@Z; winrt::hresult_error::originate(winrt::hresult,void *)
0x180001730  test    rbx, rbx
0x180001733  jz      short loc_180001756
0x180001735  mov     eax, 0FFFFFFFFh
0x18000173a  lock xadd [rbx+18h], eax
0x18000173f  sub     eax, 1
0x180001742  jnz     short loc_18000179D
0x180001744  call    WINRT_IMPL_GetProcessHeap
0x180001749  mov     rcx, rax; hHeap
0x18000174c  mov     r8, rbx; lpMem
0x18000174f  xor     edx, edx; dwFlags
0x180001751  call    WINRT_IMPL_HeapFree
0x180001756  mov     rcx, [rbp+Src]; bstrString
0x18000175a  test    rcx, rcx
0x18000175d  jz      short loc_180001764
0x18000175f  call    WINRT_IMPL_SysFreeString
0x180001764  cmp     [rbp+pperrinfo], 0
0x180001769  jz      short loc_180001774
0x18000176b  lea     rcx, [rbp+pperrinfo]
0x18000176f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180001774  mov     rax, r15
0x180001777  mov     rcx, [rbp+var_8]
0x18000177b  xor     rcx, rsp; StackCookie
0x18000177e  call    __security_check_cookie
0x180001783  mov     rbx, [rsp+40h+arg_8]
0x180001788  mov     rsi, [rsp+40h+arg_10]
0x180001790  add     rsp, 40h
0x180001794  pop     r15
0x180001796  pop     r14
0x180001798  pop     r12
0x18000179a  pop     rdi
0x18000179b  pop     rbp
0x18000179c  retn
0x18000179d  test    eax, eax
0x18000179f  jns     short loc_180001756
0x1800017a1  call    cs:__imp_abort
```
