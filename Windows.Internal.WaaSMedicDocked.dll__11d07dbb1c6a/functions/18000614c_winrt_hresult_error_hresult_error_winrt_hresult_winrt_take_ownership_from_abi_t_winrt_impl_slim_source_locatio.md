# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x18000614c`
- end: `0x1800063bf`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `627`
- prototype: ``
- caller_count: `14`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180006040`
- `0x1800060ac`
- `0x1800060d4`
- `0x1800060fc`
- `0x180006124`
- `0x18000640c`
- `0x180006478`
- `0x1800064a0`
- `0x1800064c8`
- `0x1800064f0`
- `0x180006518`
- `0x180006540`
- `0x180006568`
- `0x180009c90`

## callees

- `0x180001f8a`
- `0x180001fde`
- `0x18000204c`
- `0x180002070`
- `0x1800020a9`
- `0x1800020b5`
- `0x1800020cd`
- `0x18000614c`
- `0x18000964c`
- `0x18000972c`
- `0x18000a014`
- `0x18000b5a4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000639a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000639a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800063b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800063b8`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800062dc`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800062dc`

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
  size_t v23; // r8
  void *v24; // rcx
  BSTR pbstr; // [rsp+20h] [rbp-10h] BYREF
  BSTR v26; // [rsp+28h] [rbp-8h] BYREF
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
    v26 = pbstr;
  }
  else
  {
    v26 = 0;
    v8 = 0;
  }
  if ( v7 == (__int64 *)&v26 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v26);
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
  winrt::hresult_error::originate(a1, a2, v13, a4, pbstr);
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
0x18000614c  mov     [rsp-28h+arg_8], rbx
0x180006151  mov     [rsp-28h+arg_10], rsi
0x180006156  push    rbp
0x180006157  push    rdi
0x180006158  push    r12
0x18000615a  push    r14
0x18000615c  push    r15
0x18000615e  mov     rbp, rsp
0x180006161  sub     rsp, 30h
0x180006165  mov     r12, r9
0x180006168  mov     edi, edx
0x18000616a  mov     r14, rcx
0x18000616d  mov     qword ptr [rcx], 0
0x180006174  mov     dword ptr [rcx+8], 0AABBCCDDh
0x18000617b  mov     [rcx+0Ch], edx
0x18000617e  lea     rbx, [rcx+10h]
0x180006182  mov     qword ptr [rbx], 0
0x180006189  mov     [rbp+pperrinfo], 0
0x180006191  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180006195  xor     ecx, ecx; dwReserved
0x180006197  call    GetErrorInfo_0
0x18000619c  mov     rcx, [rbp+pperrinfo]
0x1800061a0  test    rcx, rcx
0x1800061a3  jnz     short loc_1800061AD
0x1800061a5  mov     [rbp+var_8], rcx
0x1800061a9  xor     esi, esi
0x1800061ab  jmp     short loc_1800061D3
0x1800061ad  mov     [rbp+pbstr], 0
0x1800061b5  mov     rax, [rcx]
0x1800061b8  lea     r8, [rbp+pbstr]
0x1800061bc  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1800061c3  mov     rax, [rax]
0x1800061c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061cb  mov     rsi, [rbp+pbstr]
0x1800061cf  mov     [rbp+var_8], rsi
0x1800061d3  lea     rax, [rbp+var_8]
0x1800061d7  cmp     rbx, rax
0x1800061da  jz      short loc_1800061F2
0x1800061dc  cmp     qword ptr [rbx], 0
0x1800061e0  jz      short loc_1800061EA
0x1800061e2  mov     rcx, rbx
0x1800061e5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800061ea  mov     [rbx], rsi
0x1800061ed  mov     r15, rsi
0x1800061f0  jmp     short loc_180006203
0x1800061f2  mov     r15, [rbx]
0x1800061f5  test    rsi, rsi
0x1800061f8  jz      short loc_180006203
0x1800061fa  lea     rcx, [rbp+var_8]
0x1800061fe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006203  test    r15, r15
0x180006206  jz      loc_18000628F
0x18000620c  mov     rdi, [rbx]
0x18000620f  mov     rax, [rdi]
0x180006212  mov     rsi, [rax+20h]
0x180006216  mov     rcx, [r14]; bstrString
0x180006219  test    rcx, rcx
0x18000621c  jz      short loc_18000622A
0x18000621e  call    WINRT_IMPL_SysFreeString
0x180006223  mov     qword ptr [r14], 0
0x18000622a  mov     rdx, r14
0x18000622d  mov     rcx, rdi
0x180006230  mov     rax, rsi
0x180006233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006238  mov     rcx, [rbx]
0x18000623b  test    rcx, rcx
0x18000623e  jz      loc_180006338
0x180006244  mov     [rbp+pbstr], 0
0x18000624c  mov     rax, [rcx]
0x18000624f  lea     r8, [rbp+pbstr]
0x180006253  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x18000625a  mov     rax, [rax]
0x18000625d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006262  mov     rcx, [rbp+pbstr]
0x180006266  mov     [rbp+pbstr], rcx
0x18000626a  test    rcx, rcx
0x18000626d  jz      loc_180006338
0x180006273  mov     rax, [rcx]
0x180006276  xor     edx, edx
0x180006278  mov     rax, [rax+28h]
0x18000627c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006281  lea     rcx, [rbp+pbstr]
0x180006285  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000628a  jmp     loc_180006338
0x18000628f  mov     [rbp+pbstr], 0
0x180006297  cmp     [rbp+pperrinfo], 0
0x18000629c  jnz     short loc_1800062A2
0x18000629e  xor     ebx, ebx
0x1800062a0  jmp     short loc_1800062F1
0x1800062a2  mov     rcx, [rbp+pperrinfo]
0x1800062a6  mov     rax, [rcx]
0x1800062a9  lea     rdx, [rbp+pbstr]
0x1800062ad  mov     rax, [rax+28h]
0x1800062b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b6  xor     ebx, ebx
0x1800062b8  mov     rcx, [rbp+pbstr]; pbstr
0x1800062bc  test    rcx, rcx
0x1800062bf  jz      short loc_1800062F1
0x1800062c1  call    SysStringLen_0
0x1800062c6  mov     esi, eax
0x1800062c8  mov     r15, [rbp+pbstr]
0x1800062cc  mov     ebx, eax
0x1800062ce  dec     rbx
0x1800062d1  lea     rbx, [r15+rbx*2]
0x1800062d5  test    eax, eax
0x1800062d7  jz      short loc_1800062EF
0x1800062d9  movzx   ecx, word ptr [rbx]
0x1800062dc  call    cs:__imp__o_iswspace
0x1800062e2  test    eax, eax
0x1800062e4  jz      short loc_180006362
0x1800062e6  sub     rbx, 2
0x1800062ea  add     esi, 0FFFFFFFFh
0x1800062ed  jnz     short loc_1800062D9
0x1800062ef  xor     ebx, ebx
0x1800062f1  mov     r9, r12
0x1800062f4  mov     r8, rbx
0x1800062f7  mov     edx, edi
0x1800062f9  mov     rcx, r14
0x1800062fc  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x180006301  test    rbx, rbx
0x180006304  jz      short loc_18000632A
0x180006306  or      eax, 0FFFFFFFFh
0x180006309  lock xadd [rbx+18h], eax
0x18000630e  sub     eax, 1
0x180006311  jnz     loc_1800063B0
0x180006317  nop
0x180006318  call    WINRT_IMPL_GetProcessHeap
0x18000631d  mov     rcx, rax; hHeap
0x180006320  mov     r8, rbx; lpMem
0x180006323  xor     edx, edx; dwFlags
0x180006325  call    WINRT_IMPL_HeapFree
0x18000632a  mov     rcx, [rbp+pbstr]; bstrString
0x18000632e  test    rcx, rcx
0x180006331  jz      short loc_180006338
0x180006333  call    WINRT_IMPL_SysFreeString
0x180006338  cmp     [rbp+pperrinfo], 0
0x18000633d  jz      short loc_180006348
0x18000633f  lea     rcx, [rbp+pperrinfo]
0x180006343  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006348  mov     rax, r14
0x18000634b  mov     rbx, [rsp+30h+arg_8]
0x180006350  mov     rsi, [rsp+30h+arg_10]
0x180006355  add     rsp, 30h
0x180006359  pop     r15
0x18000635b  pop     r14
0x18000635d  pop     r12
0x18000635f  pop     rdi
0x180006360  pop     rbp
0x180006361  retn
0x180006362  mov     ecx, esi; this
0x180006364  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180006369  mov     rbx, rax
0x18000636c  mov     r8d, esi
0x18000636f  add     r8, r8; Size
0x180006372  jz      loc_1800062F1
0x180006378  lea     rcx, [rax+1Ch]; void *
0x18000637c  test    rcx, rcx
0x18000637f  jz      short loc_18000639A
0x180006381  test    r15, r15
0x180006384  jz      short loc_180006393
0x180006386  mov     rdx, r15; Src
0x180006389  call    memcpy_0
0x18000638e  jmp     loc_1800062F1
0x180006393  xor     edx, edx; Val
0x180006395  call    memset_0
0x18000639a  call    cs:__imp__o__errno
0x1800063a0  mov     dword ptr [rax], 16h
0x1800063a6  call    _invalid_parameter_noinfo
0x1800063ab  jmp     loc_1800062F1
0x1800063b0  test    eax, eax
0x1800063b2  jns     loc_18000632A
0x1800063b8  call    cs:__imp_abort
```
