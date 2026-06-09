# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180017e7c`
- end: `0x1800180ef`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `627`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `14`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180017db4`
- `0x180017ddc`
- `0x180017e04`
- `0x180017e2c`
- `0x180017e54`
- `0x1800180f8`
- `0x180018120`
- `0x180018148`
- `0x180018170`
- `0x180018198`
- `0x1800181c0`
- `0x1800181e8`
- `0x180018210`
- `0x18001d50c`

## callees

- `0x180003392`
- `0x1800033e8`
- `0x180008653`
- `0x18000866b`
- `0x180008677`
- `0x180008833`
- `0x180008861`
- `0x18000889d`
- `0x1800165c0`
- `0x1800166a0`
- `0x180016fe4`
- `0x180017e7c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800180ca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800180ca`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800180e8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800180e8`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18001800c`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18001800c`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  BSTR *v7; // rbx
  BSTR v8; // rsi
  BSTR v9; // r15
  BSTR v10; // rdi
  void (__fastcall *v11)(BSTR, __int64); // rsi
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // esi
  BSTR v15; // r15
  OLECHAR *v16; // rbx
  unsigned int v17; // edx
  int v18; // eax
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *v21; // rax
  __int64 v22; // rdx
  size_t v23; // r8
  void *v24; // rcx
  BSTR pbstr; // [rsp+20h] [rbp-10h] BYREF
  BSTR v26; // [rsp+28h] [rbp-8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v7 = (BSTR *)(a1 + 16);
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
    v26 = pbstr;
  }
  else
  {
    v26 = 0;
    v8 = 0;
  }
  if ( v7 == &v26 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    *v7 = v8;
    v9 = v8;
  }
  if ( v9 )
  {
    v10 = *v7;
    v11 = *(void (__fastcall **)(BSTR, __int64))(*(_QWORD *)*v7 + 32LL);
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
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pbstr);
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
        v23 = 2LL * v14;
        if ( !v23 )
          goto LABEL_23;
        v24 = (char *)v21 + 28;
        if ( v21 != (struct winrt::impl::shared_hstring_header *)-28LL )
        {
          if ( v15 )
          {
            memcpy_0(v24, v15, v23);
            goto LABEL_23;
          }
          memset_0(v24, 0, v23);
        }
        *(_DWORD *)_o__errno(v24, v22, v23) = 22;
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
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180017e7c  mov     [rsp-28h+arg_8], rbx
0x180017e81  mov     [rsp-28h+arg_10], rsi
0x180017e86  push    rbp
0x180017e87  push    rdi
0x180017e88  push    r12
0x180017e8a  push    r14
0x180017e8c  push    r15
0x180017e8e  mov     rbp, rsp
0x180017e91  sub     rsp, 30h
0x180017e95  mov     r12, r9
0x180017e98  mov     edi, edx
0x180017e9a  mov     r14, rcx
0x180017e9d  mov     qword ptr [rcx], 0
0x180017ea4  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180017eab  mov     [rcx+0Ch], edx
0x180017eae  lea     rbx, [rcx+10h]
0x180017eb2  mov     qword ptr [rbx], 0
0x180017eb9  mov     [rbp+pperrinfo], 0
0x180017ec1  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180017ec5  xor     ecx, ecx; dwReserved
0x180017ec7  call    GetErrorInfo_0
0x180017ecc  mov     rcx, [rbp+pperrinfo]
0x180017ed0  test    rcx, rcx
0x180017ed3  jnz     short loc_180017EDD
0x180017ed5  mov     [rbp+var_8], rcx
0x180017ed9  xor     esi, esi
0x180017edb  jmp     short loc_180017F03
0x180017edd  mov     [rbp+pbstr], 0
0x180017ee5  mov     rax, [rcx]
0x180017ee8  lea     r8, [rbp+pbstr]
0x180017eec  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180017ef3  mov     rax, [rax]
0x180017ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017efb  mov     rsi, [rbp+pbstr]
0x180017eff  mov     [rbp+var_8], rsi
0x180017f03  lea     rax, [rbp+var_8]
0x180017f07  cmp     rbx, rax
0x180017f0a  jz      short loc_180017F22
0x180017f0c  cmp     qword ptr [rbx], 0
0x180017f10  jz      short loc_180017F1A
0x180017f12  mov     rcx, rbx
0x180017f15  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017f1a  mov     [rbx], rsi
0x180017f1d  mov     r15, rsi
0x180017f20  jmp     short loc_180017F33
0x180017f22  mov     r15, [rbx]
0x180017f25  test    rsi, rsi
0x180017f28  jz      short loc_180017F33
0x180017f2a  lea     rcx, [rbp+var_8]
0x180017f2e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017f33  test    r15, r15
0x180017f36  jz      loc_180017FBF
0x180017f3c  mov     rdi, [rbx]
0x180017f3f  mov     rax, [rdi]
0x180017f42  mov     rsi, [rax+20h]
0x180017f46  mov     rcx, [r14]; bstrString
0x180017f49  test    rcx, rcx
0x180017f4c  jz      short loc_180017F5A
0x180017f4e  call    WINRT_IMPL_SysFreeString
0x180017f53  mov     qword ptr [r14], 0
0x180017f5a  mov     rdx, r14
0x180017f5d  mov     rcx, rdi
0x180017f60  mov     rax, rsi
0x180017f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f68  mov     rcx, [rbx]
0x180017f6b  test    rcx, rcx
0x180017f6e  jz      loc_180018068
0x180017f74  mov     [rbp+pbstr], 0
0x180017f7c  mov     rax, [rcx]
0x180017f7f  lea     r8, [rbp+pbstr]
0x180017f83  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x180017f8a  mov     rax, [rax]
0x180017f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f92  mov     rcx, [rbp+pbstr]
0x180017f96  mov     [rbp+pbstr], rcx
0x180017f9a  test    rcx, rcx
0x180017f9d  jz      loc_180018068
0x180017fa3  mov     rax, [rcx]
0x180017fa6  xor     edx, edx
0x180017fa8  mov     rax, [rax+28h]
0x180017fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fb1  lea     rcx, [rbp+pbstr]
0x180017fb5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180017fba  jmp     loc_180018068
0x180017fbf  mov     [rbp+pbstr], 0
0x180017fc7  cmp     [rbp+pperrinfo], 0
0x180017fcc  jnz     short loc_180017FD2
0x180017fce  xor     ebx, ebx
0x180017fd0  jmp     short loc_180018021
0x180017fd2  mov     rcx, [rbp+pperrinfo]
0x180017fd6  mov     rax, [rcx]
0x180017fd9  lea     rdx, [rbp+pbstr]
0x180017fdd  mov     rax, [rax+28h]
0x180017fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fe6  xor     ebx, ebx
0x180017fe8  mov     rcx, [rbp+pbstr]; pbstr
0x180017fec  test    rcx, rcx
0x180017fef  jz      short loc_180018021
0x180017ff1  call    SysStringLen_0
0x180017ff6  mov     esi, eax
0x180017ff8  mov     r15, [rbp+pbstr]
0x180017ffc  mov     ebx, eax
0x180017ffe  dec     rbx
0x180018001  lea     rbx, [r15+rbx*2]
0x180018005  test    eax, eax
0x180018007  jz      short loc_18001801F
0x180018009  movzx   ecx, word ptr [rbx]
0x18001800c  call    cs:__imp__o_iswspace
0x180018012  test    eax, eax
0x180018014  jz      short loc_180018092
0x180018016  sub     rbx, 2
0x18001801a  add     esi, 0FFFFFFFFh
0x18001801d  jnz     short loc_180018009
0x18001801f  xor     ebx, ebx
0x180018021  mov     r9, r12
0x180018024  mov     r8, rbx
0x180018027  mov     edx, edi
0x180018029  mov     rcx, r14
0x18001802c  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x180018031  test    rbx, rbx
0x180018034  jz      short loc_18001805A
0x180018036  or      eax, 0FFFFFFFFh
0x180018039  lock xadd [rbx+18h], eax
0x18001803e  sub     eax, 1
0x180018041  jnz     loc_1800180E0
0x180018047  nop
0x180018048  call    WINRT_IMPL_GetProcessHeap
0x18001804d  mov     rcx, rax; hHeap
0x180018050  mov     r8, rbx; lpMem
0x180018053  xor     edx, edx; dwFlags
0x180018055  call    WINRT_IMPL_HeapFree
0x18001805a  mov     rcx, [rbp+pbstr]; bstrString
0x18001805e  test    rcx, rcx
0x180018061  jz      short loc_180018068
0x180018063  call    WINRT_IMPL_SysFreeString
0x180018068  cmp     [rbp+pperrinfo], 0
0x18001806d  jz      short loc_180018078
0x18001806f  lea     rcx, [rbp+pperrinfo]
0x180018073  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180018078  mov     rax, r14
0x18001807b  mov     rbx, [rsp+30h+arg_8]
0x180018080  mov     rsi, [rsp+30h+arg_10]
0x180018085  add     rsp, 30h
0x180018089  pop     r15
0x18001808b  pop     r14
0x18001808d  pop     r12
0x18001808f  pop     rdi
0x180018090  pop     rbp
0x180018091  retn
0x180018092  mov     ecx, esi; this
0x180018094  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180018099  mov     rbx, rax
0x18001809c  mov     r8d, esi
0x18001809f  add     r8, r8; Size
0x1800180a2  jz      loc_180018021
0x1800180a8  lea     rcx, [rax+1Ch]; void *
0x1800180ac  test    rcx, rcx
0x1800180af  jz      short loc_1800180CA
0x1800180b1  test    r15, r15
0x1800180b4  jz      short loc_1800180C3
0x1800180b6  mov     rdx, r15; Src
0x1800180b9  call    memcpy_0
0x1800180be  jmp     loc_180018021
0x1800180c3  xor     edx, edx; Val
0x1800180c5  call    memset_0
0x1800180ca  call    cs:__imp__o__errno
0x1800180d0  mov     dword ptr [rax], 16h
0x1800180d6  call    _invalid_parameter_noinfo
0x1800180db  jmp     loc_180018021
0x1800180e0  test    eax, eax
0x1800180e2  jns     loc_18001805A
0x1800180e8  call    cs:__imp_abort
```
