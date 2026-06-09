# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t)

- ea: `0x180003c60`
- end: `0x180003ed8`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z`
- size: `632`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `14`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003620`
- `0x1800036c0`
- `0x1800036e0`
- `0x180003700`
- `0x180003720`
- `0x180003740`
- `0x180003760`
- `0x180003780`
- `0x1800037a0`
- `0x1800037c0`
- `0x1800037e0`
- `0x180003800`
- `0x180003820`
- `0x180003ee0`

## callees

- `0x180003840`
- `0x180003a20`
- `0x180003b50`
- `0x180003c60`
- `0x180016298`
- `0x18001629e`
- `0x1800181b0`
- `0x18001c759`
- `0x18001c75f`
- `0x18001c76b`
- `0x18001cdf0`
- `0x18001cf40`
- `0x18001d600`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180003e4c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180003e4c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180003e40`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180003e40`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180003ed1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180003ed1`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180003dfa`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180003dfa`

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
0x180003c60  mov     [rsp-28h+arg_8], rbx
0x180003c65  mov     [rsp-28h+arg_10], rsi
0x180003c6a  push    rbp
0x180003c6b  push    rdi
0x180003c6c  push    r12
0x180003c6e  push    r14
0x180003c70  push    r15
0x180003c72  mov     rbp, rsp
0x180003c75  sub     rsp, 40h
0x180003c79  mov     rax, cs:__security_cookie
0x180003c80  xor     rax, rsp
0x180003c83  mov     [rbp+var_8], rax
0x180003c87  mov     edi, edx
0x180003c89  mov     r15, rcx
0x180003c8c  xor     ebx, ebx
0x180003c8e  mov     [rcx], rbx
0x180003c91  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180003c98  mov     [rcx+0Ch], edx
0x180003c9b  lea     rsi, [rcx+10h]
0x180003c9f  mov     [rsi], rbx
0x180003ca2  mov     [rbp+pperrinfo], rbx
0x180003ca6  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180003caa  xor     ecx, ecx; dwReserved
0x180003cac  call    GetErrorInfo_0
0x180003cb1  mov     rcx, [rbp+pperrinfo]
0x180003cb5  test    rcx, rcx
0x180003cb8  jnz     short loc_180003CC3
0x180003cba  mov     [rbp+var_20], rbx
0x180003cbe  mov     r14d, ebx
0x180003cc1  jmp     short loc_180003CEA
0x180003cc3  mov     [rbp+Src], rbx
0x180003cc7  mov     rax, [rcx]
0x180003cca  lea     r8, [rbp+Src]
0x180003cce  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180003cd5  mov     rax, [rax]
0x180003cd8  call    cs:__guard_dispatch_icall_fptr
0x180003cde  mov     r14, [rbp+Src]
0x180003ce2  mov     [rbp+var_20], r14
0x180003ce6  mov     rcx, [rbp+pperrinfo]
0x180003cea  lea     rax, [rbp+var_20]
0x180003cee  cmp     rsi, rax
0x180003cf1  jz      short loc_180003D0C
0x180003cf3  cmp     [rsi], rbx
0x180003cf6  jz      short loc_180003D04
0x180003cf8  mov     rcx, rsi
0x180003cfb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180003d00  mov     rcx, [rbp+pperrinfo]
0x180003d04  mov     [rsi], r14
0x180003d07  mov     r12, r14
0x180003d0a  jmp     short loc_180003D21
0x180003d0c  mov     r12, [rsi]
0x180003d0f  test    r14, r14
0x180003d12  jz      short loc_180003D21
0x180003d14  lea     rcx, [rbp+var_20]
0x180003d18  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180003d1d  mov     rcx, [rbp+pperrinfo]
0x180003d21  test    r12, r12
0x180003d24  jz      loc_180003DB4
0x180003d2a  mov     rdi, [rsi]
0x180003d2d  mov     rax, [rdi]
0x180003d30  mov     r14, [rax+20h]
0x180003d34  mov     rcx, [r15]; bstrString
0x180003d37  test    rcx, rcx
0x180003d3a  jz      short loc_180003D44
0x180003d3c  call    WINRT_IMPL_SysFreeString
0x180003d41  mov     [r15], rbx
0x180003d44  mov     rdx, r15
0x180003d47  mov     rcx, rdi
0x180003d4a  mov     rax, r14
0x180003d4d  call    cs:__guard_dispatch_icall_fptr
0x180003d53  mov     rcx, [rsi]
0x180003d56  test    rcx, rcx
0x180003d59  jz      loc_180003E94
0x180003d5f  mov     [rbp+Src], rbx
0x180003d63  mov     rax, [rcx]
0x180003d66  lea     r8, [rbp+Src]
0x180003d6a  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x180003d71  mov     rax, [rax]
0x180003d74  call    cs:__guard_dispatch_icall_fptr
0x180003d7a  mov     rbx, [rbp+Src]
0x180003d7e  mov     [rbp+Src], rbx
0x180003d82  test    rbx, rbx
0x180003d85  jz      loc_180003E94
0x180003d8b  mov     rax, [rbx]
0x180003d8e  xor     edx, edx
0x180003d90  mov     rcx, rbx
0x180003d93  mov     rax, [rax+28h]
0x180003d97  call    cs:__guard_dispatch_icall_fptr
0x180003d9d  test    rbx, rbx
0x180003da0  jz      loc_180003E94
0x180003da6  lea     rcx, [rbp+Src]
0x180003daa  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180003daf  jmp     loc_180003E94
0x180003db4  mov     rax, rbx
0x180003db7  mov     [rbp+Src], rbx
0x180003dbb  test    rcx, rcx
0x180003dbe  jz      short loc_180003DD5
0x180003dc0  mov     rax, [rcx]
0x180003dc3  lea     rdx, [rbp+Src]
0x180003dc7  mov     rax, [rax+28h]
0x180003dcb  call    cs:__guard_dispatch_icall_fptr
0x180003dd1  mov     rax, [rbp+Src]
0x180003dd5  test    rax, rax
0x180003dd8  jz      short loc_180003E53
0x180003dda  mov     rcx, rax; pbstr
0x180003ddd  call    SysStringLen_0
0x180003de2  mov     esi, eax
0x180003de4  mov     r12, [rbp+Src]
0x180003de8  mov     r14d, eax
0x180003deb  dec     r14
0x180003dee  lea     r14, [r12+r14*2]
0x180003df2  test    eax, eax
0x180003df4  jz      short loc_180003E53
0x180003df6  movzx   ecx, word ptr [r14]; C
0x180003dfa  call    cs:__imp_iswspace
0x180003e00  test    eax, eax
0x180003e02  jz      short loc_180003E0F
0x180003e04  sub     r14, 2
0x180003e08  add     esi, 0FFFFFFFFh
0x180003e0b  jnz     short loc_180003DF6
0x180003e0d  jmp     short loc_180003E53
0x180003e0f  mov     ecx, esi; this
0x180003e11  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180003e16  mov     rbx, rax
0x180003e19  mov     r8d, esi
0x180003e1c  add     r8, r8; Size
0x180003e1f  lea     rcx, [rax+1Ch]; void *
0x180003e23  jz      short loc_180003E53
0x180003e25  test    rcx, rcx
0x180003e28  jz      short loc_180003E40
0x180003e2a  test    r12, r12
0x180003e2d  jz      short loc_180003E39
0x180003e2f  mov     rdx, r12; Src
0x180003e32  call    memmove
0x180003e37  jmp     short loc_180003E53
0x180003e39  xor     edx, edx; Val
0x180003e3b  call    memset
0x180003e40  call    cs:__imp__errno
0x180003e46  mov     dword ptr [rax], 16h
0x180003e4c  call    cs:__imp__invalid_parameter_noinfo
0x180003e52  nop
0x180003e53  mov     r8, rbx
0x180003e56  mov     edx, edi
0x180003e58  mov     rcx, r15
0x180003e5b  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAX@Z; winrt::hresult_error::originate(winrt::hresult,void *)
0x180003e60  test    rbx, rbx
0x180003e63  jz      short loc_180003E86
0x180003e65  mov     eax, 0FFFFFFFFh
0x180003e6a  lock xadd [rbx+18h], eax
0x180003e6f  sub     eax, 1
0x180003e72  jnz     short loc_180003ECD
0x180003e74  call    WINRT_IMPL_GetProcessHeap
0x180003e79  mov     rcx, rax; hHeap
0x180003e7c  mov     r8, rbx; lpMem
0x180003e7f  xor     edx, edx; dwFlags
0x180003e81  call    WINRT_IMPL_HeapFree
0x180003e86  mov     rcx, [rbp+Src]; bstrString
0x180003e8a  test    rcx, rcx
0x180003e8d  jz      short loc_180003E94
0x180003e8f  call    WINRT_IMPL_SysFreeString
0x180003e94  cmp     [rbp+pperrinfo], 0
0x180003e99  jz      short loc_180003EA4
0x180003e9b  lea     rcx, [rbp+pperrinfo]
0x180003e9f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180003ea4  mov     rax, r15
0x180003ea7  mov     rcx, [rbp+var_8]
0x180003eab  xor     rcx, rsp; StackCookie
0x180003eae  call    __security_check_cookie
0x180003eb3  mov     rbx, [rsp+40h+arg_8]
0x180003eb8  mov     rsi, [rsp+40h+arg_10]
0x180003ec0  add     rsp, 40h
0x180003ec4  pop     r15
0x180003ec6  pop     r14
0x180003ec8  pop     r12
0x180003eca  pop     rdi
0x180003ecb  pop     rbp
0x180003ecc  retn
0x180003ecd  test    eax, eax
0x180003ecf  jns     short loc_180003E86
0x180003ed1  call    cs:__imp_abort
```
