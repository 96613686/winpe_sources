# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t)

- ea: `0x180004590`
- end: `0x180004808`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z`
- size: `632`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `14`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003e80`
- `0x180003f20`
- `0x180003f40`
- `0x180003f60`
- `0x180003f80`
- `0x180003fa0`
- `0x180003fc0`
- `0x180003fe0`
- `0x180004000`
- `0x180004020`
- `0x180004040`
- `0x180004060`
- `0x180004080`
- `0x180004810`

## callees

- `0x1800040a0`
- `0x180004350`
- `0x180004480`
- `0x180004590`
- `0x180030ae5`
- `0x180030aeb`
- `0x180030b27`
- `0x180034ef0`
- `0x1800362c8`
- `0x180039887`
- `0x18003bed0`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004770`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180004770`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004801`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004801`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000477c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000477c`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18000472a`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18000472a`

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
0x180004590  mov     [rsp-28h+arg_8], rbx
0x180004595  mov     [rsp-28h+arg_10], rsi
0x18000459a  push    rbp
0x18000459b  push    rdi
0x18000459c  push    r12
0x18000459e  push    r14
0x1800045a0  push    r15
0x1800045a2  mov     rbp, rsp
0x1800045a5  sub     rsp, 40h
0x1800045a9  mov     rax, cs:__security_cookie
0x1800045b0  xor     rax, rsp
0x1800045b3  mov     [rbp+var_8], rax
0x1800045b7  mov     edi, edx
0x1800045b9  mov     r15, rcx
0x1800045bc  xor     ebx, ebx
0x1800045be  mov     [rcx], rbx
0x1800045c1  mov     dword ptr [rcx+8], 0AABBCCDDh
0x1800045c8  mov     [rcx+0Ch], edx
0x1800045cb  lea     rsi, [rcx+10h]
0x1800045cf  mov     [rsi], rbx
0x1800045d2  mov     [rbp+pperrinfo], rbx
0x1800045d6  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x1800045da  xor     ecx, ecx; dwReserved
0x1800045dc  call    GetErrorInfo_0
0x1800045e1  mov     rcx, [rbp+pperrinfo]
0x1800045e5  test    rcx, rcx
0x1800045e8  jnz     short loc_1800045F3
0x1800045ea  mov     [rbp+var_20], rbx
0x1800045ee  mov     r14d, ebx
0x1800045f1  jmp     short loc_18000461A
0x1800045f3  mov     [rbp+Src], rbx
0x1800045f7  mov     rax, [rcx]
0x1800045fa  lea     r8, [rbp+Src]
0x1800045fe  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180004605  mov     rax, [rax]
0x180004608  call    cs:__guard_dispatch_icall_fptr
0x18000460e  mov     r14, [rbp+Src]
0x180004612  mov     [rbp+var_20], r14
0x180004616  mov     rcx, [rbp+pperrinfo]
0x18000461a  lea     rax, [rbp+var_20]
0x18000461e  cmp     rsi, rax
0x180004621  jz      short loc_18000463C
0x180004623  cmp     [rsi], rbx
0x180004626  jz      short loc_180004634
0x180004628  mov     rcx, rsi
0x18000462b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004630  mov     rcx, [rbp+pperrinfo]
0x180004634  mov     [rsi], r14
0x180004637  mov     r12, r14
0x18000463a  jmp     short loc_180004651
0x18000463c  mov     r12, [rsi]
0x18000463f  test    r14, r14
0x180004642  jz      short loc_180004651
0x180004644  lea     rcx, [rbp+var_20]
0x180004648  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000464d  mov     rcx, [rbp+pperrinfo]
0x180004651  test    r12, r12
0x180004654  jz      loc_1800046E4
0x18000465a  mov     rdi, [rsi]
0x18000465d  mov     rax, [rdi]
0x180004660  mov     r14, [rax+20h]
0x180004664  mov     rcx, [r15]; bstrString
0x180004667  test    rcx, rcx
0x18000466a  jz      short loc_180004674
0x18000466c  call    WINRT_IMPL_SysFreeString
0x180004671  mov     [r15], rbx
0x180004674  mov     rdx, r15
0x180004677  mov     rcx, rdi
0x18000467a  mov     rax, r14
0x18000467d  call    cs:__guard_dispatch_icall_fptr
0x180004683  mov     rcx, [rsi]
0x180004686  test    rcx, rcx
0x180004689  jz      loc_1800047C4
0x18000468f  mov     [rbp+Src], rbx
0x180004693  mov     rax, [rcx]
0x180004696  lea     r8, [rbp+Src]
0x18000469a  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x1800046a1  mov     rax, [rax]
0x1800046a4  call    cs:__guard_dispatch_icall_fptr
0x1800046aa  mov     rbx, [rbp+Src]
0x1800046ae  mov     [rbp+Src], rbx
0x1800046b2  test    rbx, rbx
0x1800046b5  jz      loc_1800047C4
0x1800046bb  mov     rax, [rbx]
0x1800046be  xor     edx, edx
0x1800046c0  mov     rcx, rbx
0x1800046c3  mov     rax, [rax+28h]
0x1800046c7  call    cs:__guard_dispatch_icall_fptr
0x1800046cd  test    rbx, rbx
0x1800046d0  jz      loc_1800047C4
0x1800046d6  lea     rcx, [rbp+Src]
0x1800046da  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800046df  jmp     loc_1800047C4
0x1800046e4  mov     rax, rbx
0x1800046e7  mov     [rbp+Src], rbx
0x1800046eb  test    rcx, rcx
0x1800046ee  jz      short loc_180004705
0x1800046f0  mov     rax, [rcx]
0x1800046f3  lea     rdx, [rbp+Src]
0x1800046f7  mov     rax, [rax+28h]
0x1800046fb  call    cs:__guard_dispatch_icall_fptr
0x180004701  mov     rax, [rbp+Src]
0x180004705  test    rax, rax
0x180004708  jz      short loc_180004783
0x18000470a  mov     rcx, rax; pbstr
0x18000470d  call    SysStringLen_0
0x180004712  mov     esi, eax
0x180004714  mov     r12, [rbp+Src]
0x180004718  mov     r14d, eax
0x18000471b  dec     r14
0x18000471e  lea     r14, [r12+r14*2]
0x180004722  test    eax, eax
0x180004724  jz      short loc_180004783
0x180004726  movzx   ecx, word ptr [r14]; C
0x18000472a  call    cs:__imp_iswspace
0x180004730  test    eax, eax
0x180004732  jz      short loc_18000473F
0x180004734  sub     r14, 2
0x180004738  add     esi, 0FFFFFFFFh
0x18000473b  jnz     short loc_180004726
0x18000473d  jmp     short loc_180004783
0x18000473f  mov     ecx, esi; this
0x180004741  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180004746  mov     rbx, rax
0x180004749  mov     r8d, esi
0x18000474c  add     r8, r8; Size
0x18000474f  lea     rcx, [rax+1Ch]; void *
0x180004753  jz      short loc_180004783
0x180004755  test    rcx, rcx
0x180004758  jz      short loc_180004770
0x18000475a  test    r12, r12
0x18000475d  jz      short loc_180004769
0x18000475f  mov     rdx, r12; Src
0x180004762  call    memmove
0x180004767  jmp     short loc_180004783
0x180004769  xor     edx, edx; Val
0x18000476b  call    memset
0x180004770  call    cs:__imp__errno
0x180004776  mov     dword ptr [rax], 16h
0x18000477c  call    cs:__imp__invalid_parameter_noinfo
0x180004782  nop
0x180004783  mov     r8, rbx
0x180004786  mov     edx, edi
0x180004788  mov     rcx, r15
0x18000478b  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAX@Z; winrt::hresult_error::originate(winrt::hresult,void *)
0x180004790  test    rbx, rbx
0x180004793  jz      short loc_1800047B6
0x180004795  mov     eax, 0FFFFFFFFh
0x18000479a  lock xadd [rbx+18h], eax
0x18000479f  sub     eax, 1
0x1800047a2  jnz     short loc_1800047FD
0x1800047a4  call    WINRT_IMPL_GetProcessHeap
0x1800047a9  mov     rcx, rax; hHeap
0x1800047ac  mov     r8, rbx; lpMem
0x1800047af  xor     edx, edx; dwFlags
0x1800047b1  call    WINRT_IMPL_HeapFree
0x1800047b6  mov     rcx, [rbp+Src]; bstrString
0x1800047ba  test    rcx, rcx
0x1800047bd  jz      short loc_1800047C4
0x1800047bf  call    WINRT_IMPL_SysFreeString
0x1800047c4  cmp     [rbp+pperrinfo], 0
0x1800047c9  jz      short loc_1800047D4
0x1800047cb  lea     rcx, [rbp+pperrinfo]
0x1800047cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800047d4  mov     rax, r15
0x1800047d7  mov     rcx, [rbp+var_8]
0x1800047db  xor     rcx, rsp; StackCookie
0x1800047de  call    __security_check_cookie
0x1800047e3  mov     rbx, [rsp+40h+arg_8]
0x1800047e8  mov     rsi, [rsp+40h+arg_10]
0x1800047f0  add     rsp, 40h
0x1800047f4  pop     r15
0x1800047f6  pop     r14
0x1800047f8  pop     r12
0x1800047fa  pop     rdi
0x1800047fb  pop     rbp
0x1800047fc  retn
0x1800047fd  test    eax, eax
0x1800047ff  jns     short loc_1800047B6
0x180004801  call    cs:__imp_abort
```
