# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x18000f3e8`
- end: `0x18000f65b`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `627`
- prototype: ``
- caller_count: `14`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000f298`
- `0x18000f304`
- `0x18000f370`
- `0x18000f398`
- `0x18000f3c0`
- `0x18000f664`
- `0x18000f68c`
- `0x18000f6b4`
- `0x18000f6dc`
- `0x18000f748`
- `0x18000f770`
- `0x18000f7dc`
- `0x18000f804`
- `0x1800145d8`

## callees

- `0x180004f86`
- `0x180004ff4`
- `0x18000500c`
- `0x18000509c`
- `0x1800050f0`
- `0x180005108`
- `0x180005138`
- `0x1800051e5`
- `0x18000f3e8`
- `0x180014170`
- `0x180014250`
- `0x180014974`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f636`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f636`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f654`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f654`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000f578`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000f578`

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
0x18000f3e8  mov     [rsp-28h+arg_8], rbx
0x18000f3ed  mov     [rsp-28h+arg_10], rsi
0x18000f3f2  push    rbp
0x18000f3f3  push    rdi
0x18000f3f4  push    r12
0x18000f3f6  push    r14
0x18000f3f8  push    r15
0x18000f3fa  mov     rbp, rsp
0x18000f3fd  sub     rsp, 30h
0x18000f401  mov     r12, r9
0x18000f404  mov     edi, edx
0x18000f406  mov     r14, rcx
0x18000f409  mov     qword ptr [rcx], 0
0x18000f410  mov     dword ptr [rcx+8], 0AABBCCDDh
0x18000f417  mov     [rcx+0Ch], edx
0x18000f41a  lea     rbx, [rcx+10h]
0x18000f41e  mov     qword ptr [rbx], 0
0x18000f425  mov     [rbp+pperrinfo], 0
0x18000f42d  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000f431  xor     ecx, ecx; dwReserved
0x18000f433  call    GetErrorInfo_0
0x18000f438  mov     rcx, [rbp+pperrinfo]
0x18000f43c  test    rcx, rcx
0x18000f43f  jnz     short loc_18000F449
0x18000f441  mov     [rbp+var_8], rcx
0x18000f445  xor     esi, esi
0x18000f447  jmp     short loc_18000F46F
0x18000f449  mov     [rbp+pbstr], 0
0x18000f451  mov     rax, [rcx]
0x18000f454  lea     r8, [rbp+pbstr]
0x18000f458  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x18000f45f  mov     rax, [rax]
0x18000f462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f467  mov     rsi, [rbp+pbstr]
0x18000f46b  mov     [rbp+var_8], rsi
0x18000f46f  lea     rax, [rbp+var_8]
0x18000f473  cmp     rbx, rax
0x18000f476  jz      short loc_18000F48E
0x18000f478  cmp     qword ptr [rbx], 0
0x18000f47c  jz      short loc_18000F486
0x18000f47e  mov     rcx, rbx
0x18000f481  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f486  mov     [rbx], rsi
0x18000f489  mov     r15, rsi
0x18000f48c  jmp     short loc_18000F49F
0x18000f48e  mov     r15, [rbx]
0x18000f491  test    rsi, rsi
0x18000f494  jz      short loc_18000F49F
0x18000f496  lea     rcx, [rbp+var_8]
0x18000f49a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f49f  test    r15, r15
0x18000f4a2  jz      loc_18000F52B
0x18000f4a8  mov     rdi, [rbx]
0x18000f4ab  mov     rax, [rdi]
0x18000f4ae  mov     rsi, [rax+20h]
0x18000f4b2  mov     rcx, [r14]; bstrString
0x18000f4b5  test    rcx, rcx
0x18000f4b8  jz      short loc_18000F4C6
0x18000f4ba  call    WINRT_IMPL_SysFreeString
0x18000f4bf  mov     qword ptr [r14], 0
0x18000f4c6  mov     rdx, r14
0x18000f4c9  mov     rcx, rdi
0x18000f4cc  mov     rax, rsi
0x18000f4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4d4  mov     rcx, [rbx]
0x18000f4d7  test    rcx, rcx
0x18000f4da  jz      loc_18000F5D4
0x18000f4e0  mov     [rbp+pbstr], 0
0x18000f4e8  mov     rax, [rcx]
0x18000f4eb  lea     r8, [rbp+pbstr]
0x18000f4ef  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x18000f4f6  mov     rax, [rax]
0x18000f4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4fe  mov     rcx, [rbp+pbstr]
0x18000f502  mov     [rbp+pbstr], rcx
0x18000f506  test    rcx, rcx
0x18000f509  jz      loc_18000F5D4
0x18000f50f  mov     rax, [rcx]
0x18000f512  xor     edx, edx
0x18000f514  mov     rax, [rax+28h]
0x18000f518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f51d  lea     rcx, [rbp+pbstr]
0x18000f521  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f526  jmp     loc_18000F5D4
0x18000f52b  mov     [rbp+pbstr], 0
0x18000f533  cmp     [rbp+pperrinfo], 0
0x18000f538  jnz     short loc_18000F53E
0x18000f53a  xor     ebx, ebx
0x18000f53c  jmp     short loc_18000F58D
0x18000f53e  mov     rcx, [rbp+pperrinfo]
0x18000f542  mov     rax, [rcx]
0x18000f545  lea     rdx, [rbp+pbstr]
0x18000f549  mov     rax, [rax+28h]
0x18000f54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f552  xor     ebx, ebx
0x18000f554  mov     rcx, [rbp+pbstr]; pbstr
0x18000f558  test    rcx, rcx
0x18000f55b  jz      short loc_18000F58D
0x18000f55d  call    SysStringLen_0
0x18000f562  mov     esi, eax
0x18000f564  mov     r15, [rbp+pbstr]
0x18000f568  mov     ebx, eax
0x18000f56a  dec     rbx
0x18000f56d  lea     rbx, [r15+rbx*2]
0x18000f571  test    eax, eax
0x18000f573  jz      short loc_18000F58B
0x18000f575  movzx   ecx, word ptr [rbx]
0x18000f578  call    cs:__imp__o_iswspace
0x18000f57e  test    eax, eax
0x18000f580  jz      short loc_18000F5FE
0x18000f582  sub     rbx, 2
0x18000f586  add     esi, 0FFFFFFFFh
0x18000f589  jnz     short loc_18000F575
0x18000f58b  xor     ebx, ebx
0x18000f58d  mov     r9, r12
0x18000f590  mov     r8, rbx
0x18000f593  mov     edx, edi
0x18000f595  mov     rcx, r14
0x18000f598  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000f59d  test    rbx, rbx
0x18000f5a0  jz      short loc_18000F5C6
0x18000f5a2  or      eax, 0FFFFFFFFh
0x18000f5a5  lock xadd [rbx+18h], eax
0x18000f5aa  sub     eax, 1
0x18000f5ad  jnz     loc_18000F64C
0x18000f5b3  nop
0x18000f5b4  call    WINRT_IMPL_GetProcessHeap
0x18000f5b9  mov     rcx, rax; hHeap
0x18000f5bc  mov     r8, rbx; lpMem
0x18000f5bf  xor     edx, edx; dwFlags
0x18000f5c1  call    WINRT_IMPL_HeapFree
0x18000f5c6  mov     rcx, [rbp+pbstr]; bstrString
0x18000f5ca  test    rcx, rcx
0x18000f5cd  jz      short loc_18000F5D4
0x18000f5cf  call    WINRT_IMPL_SysFreeString
0x18000f5d4  cmp     [rbp+pperrinfo], 0
0x18000f5d9  jz      short loc_18000F5E4
0x18000f5db  lea     rcx, [rbp+pperrinfo]
0x18000f5df  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f5e4  mov     rax, r14
0x18000f5e7  mov     rbx, [rsp+30h+arg_8]
0x18000f5ec  mov     rsi, [rsp+30h+arg_10]
0x18000f5f1  add     rsp, 30h
0x18000f5f5  pop     r15
0x18000f5f7  pop     r14
0x18000f5f9  pop     r12
0x18000f5fb  pop     rdi
0x18000f5fc  pop     rbp
0x18000f5fd  retn
0x18000f5fe  mov     ecx, esi; this
0x18000f600  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000f605  mov     rbx, rax
0x18000f608  mov     r8d, esi
0x18000f60b  add     r8, r8; Size
0x18000f60e  jz      loc_18000F58D
0x18000f614  lea     rcx, [rax+1Ch]; void *
0x18000f618  test    rcx, rcx
0x18000f61b  jz      short loc_18000F636
0x18000f61d  test    r15, r15
0x18000f620  jz      short loc_18000F62F
0x18000f622  mov     rdx, r15; Src
0x18000f625  call    memcpy_0
0x18000f62a  jmp     loc_18000F58D
0x18000f62f  xor     edx, edx; Val
0x18000f631  call    memset_0
0x18000f636  call    cs:__imp__o__errno
0x18000f63c  mov     dword ptr [rax], 16h
0x18000f642  call    _invalid_parameter_noinfo
0x18000f647  jmp     loc_18000F58D
0x18000f64c  test    eax, eax
0x18000f64e  jns     loc_18000F5C6
0x18000f654  call    cs:__imp_abort
```
