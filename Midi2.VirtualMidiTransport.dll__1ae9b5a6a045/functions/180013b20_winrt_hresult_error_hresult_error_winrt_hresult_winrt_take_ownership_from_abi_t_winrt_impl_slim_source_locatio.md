# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180013b20`
- end: `0x180013d93`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `627`
- prototype: ``
- caller_count: `14`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800139d0`
- `0x180013a3c`
- `0x180013aa8`
- `0x180013ad0`
- `0x180013af8`
- `0x180013d9c`
- `0x180013dc4`
- `0x180013dec`
- `0x180013e14`
- `0x180013e80`
- `0x180013ea8`
- `0x180013f14`
- `0x180013f3c`
- `0x18001a3fc`

## callees

- `0x180004626`
- `0x180004688`
- `0x1800046a0`
- `0x180004718`
- `0x18000476c`
- `0x180004784`
- `0x1800047a8`
- `0x1800047d5`
- `0x180013b20`
- `0x18001a010`
- `0x18001a0f0`
- `0x18001a798`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013d6e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013d6e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013d8c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013d8c`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180013cb0`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180013cb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 *v7; // rbx
  BSTR v8; // rsi
  __int64 v9; // r15
  __int64 v10; // rdi
  void (__fastcall *v11)(__int64, __int64); // rsi
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // esi
  BSTR v15; // r15
  OLECHAR *v16; // rbx
  const char *v17; // rdx
  int v18; // eax
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r9
  size_t v24; // r8
  void *v25; // rcx
  BSTR pbstr; // [rsp+20h] [rbp-10h] BYREF
  BSTR v27; // [rsp+28h] [rbp-8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v7 = (__int64 *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  if ( pperrinfo )
  {
    pbstr = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &pbstr);
    v8 = pbstr;
    v27 = pbstr;
  }
  else
  {
    v27 = 0;
    v8 = 0;
  }
  if ( v7 == (__int64 *)&v27 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v27);
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    *v7 = (__int64)v8;
    v9 = (__int64)v8;
  }
  if ( v9 )
  {
    v10 = *v7;
    v11 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v7 + 32LL);
    if ( *(_QWORD *)a1 )
    {
      WINRT_IMPL_SysFreeString(*(BSTR *)a1);
      *(_QWORD *)a1 = 0;
    }
    v11(v10, a1);
    v12 = (void (__fastcall ***)(_QWORD, __int64 *, BSTR *))*v7;
    if ( *v7 )
    {
      pbstr = 0;
      (**v12)(v12, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &pbstr);
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pbstr);
      }
    }
    goto LABEL_28;
  }
  pbstr = 0;
  if ( pperrinfo )
  {
    ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr);
    v13 = 0;
    if ( pbstr )
    {
      v14 = SysStringLen_0(pbstr);
      v15 = pbstr;
      v16 = &pbstr[v14 - 1];
      if ( v14 )
      {
        while ( (unsigned int)_o_iswspace(*v16) )
        {
          --v16;
          if ( !--v14 )
            goto LABEL_22;
        }
        v21 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v14, v17);
        v13 = (volatile signed __int32 *)v21;
        v24 = 2LL * v14;
        if ( !v24 )
          goto LABEL_23;
        v25 = (char *)v21 + 28;
        if ( v21 != (struct winrt::impl::shared_hstring_header *)-28LL )
        {
          if ( v15 )
          {
            memcpy_0(v25, v15, v24);
            goto LABEL_23;
          }
          memset_0(v25, 0, v24);
        }
        *(_DWORD *)_o__errno(v25, v22, v24, v23) = 22;
        invalid_parameter_noinfo();
        goto LABEL_23;
      }
LABEL_22:
      v13 = 0;
    }
  }
  else
  {
    v13 = 0;
  }
LABEL_23:
  winrt::hresult_error::originate(a1, a2, v13, a4);
  if ( v13 )
  {
    v18 = _InterlockedDecrement(v13 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v13);
    }
  }
  if ( pbstr )
    WINRT_IMPL_SysFreeString(pbstr);
LABEL_28:
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180013b20  mov     [rsp-28h+arg_8], rbx
0x180013b25  mov     [rsp-28h+arg_10], rsi
0x180013b2a  push    rbp
0x180013b2b  push    rdi
0x180013b2c  push    r12
0x180013b2e  push    r14
0x180013b30  push    r15
0x180013b32  mov     rbp, rsp
0x180013b35  sub     rsp, 30h
0x180013b39  mov     r12, r9
0x180013b3c  mov     edi, edx
0x180013b3e  mov     r14, rcx
0x180013b41  mov     qword ptr [rcx], 0
0x180013b48  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180013b4f  mov     [rcx+0Ch], edx
0x180013b52  lea     rbx, [rcx+10h]
0x180013b56  mov     qword ptr [rbx], 0
0x180013b5d  mov     [rbp+pperrinfo], 0
0x180013b65  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180013b69  xor     ecx, ecx; dwReserved
0x180013b6b  call    GetErrorInfo_0
0x180013b70  mov     rcx, [rbp+pperrinfo]
0x180013b74  test    rcx, rcx
0x180013b77  jnz     short loc_180013B81
0x180013b79  mov     [rbp+var_8], rcx
0x180013b7d  xor     esi, esi
0x180013b7f  jmp     short loc_180013BA7
0x180013b81  mov     [rbp+pbstr], 0
0x180013b89  mov     rax, [rcx]
0x180013b8c  lea     r8, [rbp+pbstr]
0x180013b90  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180013b97  mov     rax, [rax]
0x180013b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b9f  mov     rsi, [rbp+pbstr]
0x180013ba3  mov     [rbp+var_8], rsi
0x180013ba7  lea     rax, [rbp+var_8]
0x180013bab  cmp     rbx, rax
0x180013bae  jz      short loc_180013BC6
0x180013bb0  cmp     qword ptr [rbx], 0
0x180013bb4  jz      short loc_180013BBE
0x180013bb6  mov     rcx, rbx
0x180013bb9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013bbe  mov     [rbx], rsi
0x180013bc1  mov     r15, rsi
0x180013bc4  jmp     short loc_180013BD7
0x180013bc6  mov     r15, [rbx]
0x180013bc9  test    rsi, rsi
0x180013bcc  jz      short loc_180013BD7
0x180013bce  lea     rcx, [rbp+var_8]
0x180013bd2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013bd7  test    r15, r15
0x180013bda  jz      loc_180013C63
0x180013be0  mov     rdi, [rbx]
0x180013be3  mov     rax, [rdi]
0x180013be6  mov     rsi, [rax+20h]
0x180013bea  mov     rcx, [r14]; bstrString
0x180013bed  test    rcx, rcx
0x180013bf0  jz      short loc_180013BFE
0x180013bf2  call    WINRT_IMPL_SysFreeString
0x180013bf7  mov     qword ptr [r14], 0
0x180013bfe  mov     rdx, r14
0x180013c01  mov     rcx, rdi
0x180013c04  mov     rax, rsi
0x180013c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c0c  mov     rcx, [rbx]
0x180013c0f  test    rcx, rcx
0x180013c12  jz      loc_180013D0C
0x180013c18  mov     [rbp+pbstr], 0
0x180013c20  mov     rax, [rcx]
0x180013c23  lea     r8, [rbp+pbstr]
0x180013c27  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x180013c2e  mov     rax, [rax]
0x180013c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c36  mov     rcx, [rbp+pbstr]
0x180013c3a  mov     [rbp+pbstr], rcx
0x180013c3e  test    rcx, rcx
0x180013c41  jz      loc_180013D0C
0x180013c47  mov     rax, [rcx]
0x180013c4a  xor     edx, edx
0x180013c4c  mov     rax, [rax+28h]
0x180013c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c55  lea     rcx, [rbp+pbstr]
0x180013c59  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013c5e  jmp     loc_180013D0C
0x180013c63  mov     [rbp+pbstr], 0
0x180013c6b  cmp     [rbp+pperrinfo], 0
0x180013c70  jnz     short loc_180013C76
0x180013c72  xor     ebx, ebx
0x180013c74  jmp     short loc_180013CC5
0x180013c76  mov     rcx, [rbp+pperrinfo]
0x180013c7a  mov     rax, [rcx]
0x180013c7d  lea     rdx, [rbp+pbstr]
0x180013c81  mov     rax, [rax+28h]
0x180013c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c8a  xor     ebx, ebx
0x180013c8c  mov     rcx, [rbp+pbstr]; pbstr
0x180013c90  test    rcx, rcx
0x180013c93  jz      short loc_180013CC5
0x180013c95  call    SysStringLen_0
0x180013c9a  mov     esi, eax
0x180013c9c  mov     r15, [rbp+pbstr]
0x180013ca0  mov     ebx, eax
0x180013ca2  dec     rbx
0x180013ca5  lea     rbx, [r15+rbx*2]
0x180013ca9  test    eax, eax
0x180013cab  jz      short loc_180013CC3
0x180013cad  movzx   ecx, word ptr [rbx]
0x180013cb0  call    cs:__imp__o_iswspace
0x180013cb6  test    eax, eax
0x180013cb8  jz      short loc_180013D36
0x180013cba  sub     rbx, 2
0x180013cbe  add     esi, 0FFFFFFFFh
0x180013cc1  jnz     short loc_180013CAD
0x180013cc3  xor     ebx, ebx
0x180013cc5  mov     r9, r12
0x180013cc8  mov     r8, rbx
0x180013ccb  mov     edx, edi
0x180013ccd  mov     rcx, r14
0x180013cd0  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x180013cd5  test    rbx, rbx
0x180013cd8  jz      short loc_180013CFE
0x180013cda  or      eax, 0FFFFFFFFh
0x180013cdd  lock xadd [rbx+18h], eax
0x180013ce2  sub     eax, 1
0x180013ce5  jnz     loc_180013D84
0x180013ceb  nop
0x180013cec  call    WINRT_IMPL_GetProcessHeap
0x180013cf1  mov     rcx, rax; hHeap
0x180013cf4  mov     r8, rbx; lpMem
0x180013cf7  xor     edx, edx; dwFlags
0x180013cf9  call    WINRT_IMPL_HeapFree
0x180013cfe  mov     rcx, [rbp+pbstr]; bstrString
0x180013d02  test    rcx, rcx
0x180013d05  jz      short loc_180013D0C
0x180013d07  call    WINRT_IMPL_SysFreeString
0x180013d0c  cmp     [rbp+pperrinfo], 0
0x180013d11  jz      short loc_180013D1C
0x180013d13  lea     rcx, [rbp+pperrinfo]
0x180013d17  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180013d1c  mov     rax, r14
0x180013d1f  mov     rbx, [rsp+30h+arg_8]
0x180013d24  mov     rsi, [rsp+30h+arg_10]
0x180013d29  add     rsp, 30h
0x180013d2d  pop     r15
0x180013d2f  pop     r14
0x180013d31  pop     r12
0x180013d33  pop     rdi
0x180013d34  pop     rbp
0x180013d35  retn
0x180013d36  mov     ecx, esi; this
0x180013d38  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180013d3d  mov     rbx, rax
0x180013d40  mov     r8d, esi
0x180013d43  add     r8, r8; Size
0x180013d46  jz      loc_180013CC5
0x180013d4c  lea     rcx, [rax+1Ch]; void *
0x180013d50  test    rcx, rcx
0x180013d53  jz      short loc_180013D6E
0x180013d55  test    r15, r15
0x180013d58  jz      short loc_180013D67
0x180013d5a  mov     rdx, r15; Src
0x180013d5d  call    memcpy_0
0x180013d62  jmp     loc_180013CC5
0x180013d67  xor     edx, edx; Val
0x180013d69  call    memset_0
0x180013d6e  call    cs:__imp__o__errno
0x180013d74  mov     dword ptr [rax], 16h
0x180013d7a  call    _invalid_parameter_noinfo
0x180013d7f  jmp     loc_180013CC5
0x180013d84  test    eax, eax
0x180013d86  jns     loc_180013CFE
0x180013d8c  call    cs:__imp_abort
```
