# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180004ae8`
- end: `0x180004e39`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `849`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int *)`
- caller_count: `14`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004a20`
- `0x180004a48`
- `0x180004a70`
- `0x180004a98`
- `0x180004ac0`
- `0x180004e40`
- `0x180004e68`
- `0x180004e90`
- `0x180004eb8`
- `0x180004ee0`
- `0x180004f08`
- `0x180004f30`
- `0x180004f58`
- `0x18000bde4`

## callees

- `0x1800022b4`
- `0x180002314`
- `0x180002320`
- `0x18000232c`
- `0x180002365`
- `0x180002371`
- `0x18000237d`
- `0x180002395`
- `0x18000490c`
- `0x180004ae8`
- `0x180004fc4`
- `0x18000c010`
- `0x18000c398`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180004dfe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180004dfe`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004c61`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180004c61`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  unsigned int *v4; // r12
  BSTR *v7; // rsi
  BSTR v8; // rbx
  BSTR v9; // r14
  BSTR v10; // rbx
  void (__fastcall *v11)(BSTR, __int64); // rdi
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // eax
  __int64 v15; // r14
  BSTR v16; // r13
  OLECHAR *v17; // rbx
  const char *v18; // rdx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v20; // rax
  BSTR v21; // rdi
  int v22; // eax
  HANDLE v23; // rax
  IErrorInfo *v25; // [rsp+30h] [rbp-40h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-38h] BYREF
  BSTR v27; // [rsp+40h] [rbp-30h] BYREF
  BSTR v28; // [rsp+48h] [rbp-28h] BYREF
  BSTR v29; // [rsp+50h] [rbp-20h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-18h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+38h]
  IErrorInfo *pperrinfo; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int *v33; // [rsp+C8h] [rbp+58h]

  v33 = a4;
  v4 = a4;
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
    v27 = pbstr;
  }
  else
  {
    v27 = 0;
    v8 = 0;
  }
  if ( v7 == &v27 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v27);
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v7);
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
      v29 = pbstr;
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v29);
      }
    }
  }
  else
  {
    pbstr = 0;
    if ( pperrinfo )
    {
      ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr);
      v13 = 0;
      if ( pbstr )
      {
        v14 = SysStringLen_0(pbstr);
        v15 = v14;
        v16 = pbstr;
        v17 = &pbstr[v14 - 1];
        if ( v14 )
        {
          while ( (unsigned int)_o_iswspace(*v17) )
          {
            --v17;
            v15 = (unsigned int)(v15 - 1);
            if ( !(_DWORD)v15 )
              goto LABEL_21;
          }
          if ( (unsigned __int64)(2 * v15 + 32) > 0xFFFFFFFF )
          {
            std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, v18);
            throw (std::invalid_argument *)pExceptionObject;
          }
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          v20 = (volatile signed __int32 *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, 2 * v15 + 32);
          v13 = v20;
          if ( !v20 )
          {
            std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
            throw (std::bad_alloc *)pExceptionObject;
          }
          *v20 = 0;
          *((_DWORD *)v20 + 1) = v15;
          *((_QWORD *)v20 + 2) = v20 + 7;
          _InterlockedExchange(v20 + 6, 1);
          *((_WORD *)v20 + v15 + 14) = 0;
          memcpy_s((void *const)(v20 + 7), 2 * v15, v16, 2 * v15);
          v4 = v33;
        }
        else
        {
LABEL_21:
          v13 = 0;
        }
      }
    }
    else
    {
      v13 = 0;
    }
    RoOriginateLanguageException_0(a2, v13, 0);
    if ( winrt_throw_hresult_handler )
      winrt_throw_hresult_handler(*v4, *((_QWORD *)v4 + 1), *((_QWORD *)v4 + 2), retaddr, a2);
    v25 = 0;
    GetErrorInfo_0(0, &v25);
    if ( v25 )
    {
      v29 = 0;
      ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))v25->lpVtbl->QueryInterface)(
        v25,
        winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
        &v29);
      v21 = v29;
      v28 = v29;
    }
    else
    {
      v28 = 0;
      v21 = 0;
    }
    if ( v7 == &v28 )
    {
      if ( v21 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
    }
    else
    {
      if ( *v7 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v7);
      *v7 = v21;
    }
    if ( v25 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v25);
    if ( v13 )
    {
      v22 = _InterlockedDecrement(v13 + 6);
      if ( v22 )
      {
        if ( v22 < 0 )
          abort();
      }
      else
      {
        v23 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v23, 0, (LPVOID)v13);
      }
    }
    if ( pbstr )
      WINRT_IMPL_SysFreeString(pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180004ae8  mov     [rsp-38h+arg_8], rbx
0x180004aed  mov     [rsp-38h+arg_18], r9
0x180004af2  push    rbp
0x180004af3  push    rsi
0x180004af4  push    rdi
0x180004af5  push    r12
0x180004af7  push    r13
0x180004af9  push    r14
0x180004afb  push    r15
0x180004afd  mov     rbp, rsp
0x180004b00  sub     rsp, 70h
0x180004b04  mov     r12, r9
0x180004b07  mov     edi, edx
0x180004b09  mov     r15, rcx
0x180004b0c  xor     r13d, r13d
0x180004b0f  mov     [rcx], r13
0x180004b12  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180004b19  mov     [rcx+0Ch], edx
0x180004b1c  lea     rsi, [rcx+10h]
0x180004b20  mov     [rsi], r13
0x180004b23  mov     [rbp+pperrinfo], r13
0x180004b27  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180004b2b  xor     ecx, ecx; dwReserved
0x180004b2d  call    GetErrorInfo_0
0x180004b32  mov     rcx, [rbp+pperrinfo]
0x180004b36  test    rcx, rcx
0x180004b39  jnz     short loc_180004B44
0x180004b3b  mov     [rbp+var_30], r13
0x180004b3f  mov     ebx, r13d
0x180004b42  jmp     short loc_180004B66
0x180004b44  mov     [rbp+pbstr], r13
0x180004b48  mov     rax, [rcx]
0x180004b4b  lea     r8, [rbp+pbstr]
0x180004b4f  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180004b56  mov     rax, [rax]
0x180004b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5e  mov     rbx, [rbp+pbstr]
0x180004b62  mov     [rbp+var_30], rbx
0x180004b66  lea     rax, [rbp+var_30]
0x180004b6a  cmp     rsi, rax
0x180004b6d  jz      short loc_180004B84
0x180004b6f  cmp     [rsi], r13
0x180004b72  jz      short loc_180004B7C
0x180004b74  mov     rcx, rsi
0x180004b77  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004b7c  mov     [rsi], rbx
0x180004b7f  mov     r14, rbx
0x180004b82  jmp     short loc_180004B95
0x180004b84  mov     r14, [rsi]
0x180004b87  test    rbx, rbx
0x180004b8a  jz      short loc_180004B95
0x180004b8c  lea     rcx, [rbp+var_30]
0x180004b90  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004b95  test    r14, r14
0x180004b98  jz      short loc_180004C15
0x180004b9a  mov     rbx, [rsi]
0x180004b9d  mov     rax, [rbx]
0x180004ba0  mov     rdi, [rax+20h]
0x180004ba4  mov     rcx, [r15]; bstrString
0x180004ba7  test    rcx, rcx
0x180004baa  jz      short loc_180004BB4
0x180004bac  call    WINRT_IMPL_SysFreeString
0x180004bb1  mov     [r15], r13
0x180004bb4  mov     rdx, r15
0x180004bb7  mov     rcx, rbx
0x180004bba  mov     rax, rdi
0x180004bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc2  mov     rcx, [rsi]
0x180004bc5  test    rcx, rcx
0x180004bc8  jz      loc_180004DD0
0x180004bce  mov     [rbp+pbstr], r13
0x180004bd2  mov     rax, [rcx]
0x180004bd5  lea     r8, [rbp+pbstr]
0x180004bd9  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x180004be0  mov     rax, [rax]
0x180004be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be8  mov     rcx, [rbp+pbstr]
0x180004bec  mov     [rbp+var_20], rcx
0x180004bf0  test    rcx, rcx
0x180004bf3  jz      loc_180004DD0
0x180004bf9  mov     rax, [rcx]
0x180004bfc  xor     edx, edx
0x180004bfe  mov     rax, [rax+28h]
0x180004c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c07  lea     rcx, [rbp+var_20]
0x180004c0b  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004c10  jmp     loc_180004DD0
0x180004c15  mov     [rbp+pbstr], r13
0x180004c19  mov     rcx, [rbp+pperrinfo]
0x180004c1d  test    rcx, rcx
0x180004c20  jz      loc_180004CEA
0x180004c26  mov     rax, [rcx]
0x180004c29  lea     rdx, [rbp+pbstr]
0x180004c2d  mov     rax, [rax+28h]
0x180004c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c36  mov     rbx, r13
0x180004c39  mov     rcx, [rbp+pbstr]; pbstr
0x180004c3d  test    rcx, rcx
0x180004c40  jz      loc_180004CED
0x180004c46  call    SysStringLen_0
0x180004c4b  mov     r14d, eax
0x180004c4e  mov     r13, [rbp+pbstr]
0x180004c52  lea     rbx, [r13-2]
0x180004c56  lea     rbx, [rbx+r14*2]
0x180004c5a  test    eax, eax
0x180004c5c  jz      short loc_180004C79
0x180004c5e  movzx   ecx, word ptr [rbx]
0x180004c61  call    cs:__imp__o_iswspace
0x180004c67  test    eax, eax
0x180004c69  mov     eax, 0FFFFFFFFh
0x180004c6e  jz      short loc_180004C81
0x180004c70  sub     rbx, 2
0x180004c74  add     r14d, eax
0x180004c77  jnz     short loc_180004C5E
0x180004c79  xor     r13d, r13d
0x180004c7c  mov     ebx, r13d
0x180004c7f  jmp     short loc_180004CED
0x180004c81  lea     rbx, ds:20h[r14*2]
0x180004c89  cmp     rbx, rax
0x180004c8c  ja      loc_180004E1F
0x180004c92  call    WINRT_IMPL_GetProcessHeap
0x180004c97  mov     rcx, rax; hHeap
0x180004c9a  mov     r8, rbx; dwBytes
0x180004c9d  xor     edx, edx; dwFlags
0x180004c9f  call    WINRT_IMPL_HeapAlloc
0x180004ca4  mov     rbx, rax
0x180004ca7  test    rax, rax
0x180004caa  jz      loc_180004E05
0x180004cb0  mov     dword ptr [rax], 0
0x180004cb6  mov     [rax+4], r14d
0x180004cba  lea     rcx, [rax+1Ch]; Destination
0x180004cbe  mov     [rax+10h], rcx
0x180004cc2  mov     eax, 1
0x180004cc7  xchg    eax, [rbx+18h]
0x180004cca  xor     edx, edx
0x180004ccc  mov     [rbx+r14*2+1Ch], dx
0x180004cd2  lea     rdx, [r14+r14]; DestinationSize
0x180004cd6  mov     r9, rdx; SourceSize
0x180004cd9  mov     r8, r13; Source
0x180004cdc  call    memcpy_s
0x180004ce1  mov     r12, [rbp+arg_18]
0x180004ce5  xor     r13d, r13d
0x180004ce8  jmp     short loc_180004C7F
0x180004cea  mov     rbx, r13
0x180004ced  xor     r8d, r8d
0x180004cf0  mov     rdx, rbx
0x180004cf3  mov     ecx, edi
0x180004cf5  call    RoOriginateLanguageException_0
0x180004cfa  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180004d01  test    rax, rax
0x180004d04  jz      short loc_180004D21
0x180004d06  mov     r9, [rbp+38h]
0x180004d0a  mov     [rsp+70h+var_50], edi
0x180004d0e  mov     r8, [r12+10h]
0x180004d13  mov     rdx, [r12+8]
0x180004d18  mov     ecx, [r12]
0x180004d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d21  mov     [rbp+var_40], r13
0x180004d25  lea     rdx, [rbp+var_40]; pperrinfo
0x180004d29  xor     ecx, ecx; dwReserved
0x180004d2b  call    GetErrorInfo_0
0x180004d30  mov     rcx, [rbp+var_40]
0x180004d34  test    rcx, rcx
0x180004d37  jnz     short loc_180004D42
0x180004d39  mov     [rbp+var_28], r13
0x180004d3d  mov     rdi, r13
0x180004d40  jmp     short loc_180004D64
0x180004d42  mov     [rbp+var_20], r13
0x180004d46  mov     rax, [rcx]
0x180004d49  lea     r8, [rbp+var_20]
0x180004d4d  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180004d54  mov     rax, [rax]
0x180004d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d5c  mov     rdi, [rbp+var_20]
0x180004d60  mov     [rbp+var_28], rdi
0x180004d64  lea     rax, [rbp+var_28]
0x180004d68  cmp     rsi, rax
0x180004d6b  jz      short loc_180004D7F
0x180004d6d  cmp     [rsi], r13
0x180004d70  jz      short loc_180004D7A
0x180004d72  mov     rcx, rsi
0x180004d75  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004d7a  mov     [rsi], rdi
0x180004d7d  jmp     short loc_180004D8D
0x180004d7f  test    rdi, rdi
0x180004d82  jz      short loc_180004D8D
0x180004d84  lea     rcx, [rbp+var_28]
0x180004d88  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004d8d  cmp     [rbp+var_40], r13
0x180004d91  jz      short loc_180004D9D
0x180004d93  lea     rcx, [rbp+var_40]
0x180004d97  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004d9c  nop
0x180004d9d  test    rbx, rbx
0x180004da0  jz      short loc_180004DC2
0x180004da2  or      eax, 0FFFFFFFFh
0x180004da5  lock xadd [rbx+18h], eax
0x180004daa  sub     eax, 1
0x180004dad  jnz     short loc_180004DFA
0x180004daf  nop
0x180004db0  call    WINRT_IMPL_GetProcessHeap
0x180004db5  mov     rcx, rax; hHeap
0x180004db8  mov     r8, rbx; lpMem
0x180004dbb  xor     edx, edx; dwFlags
0x180004dbd  call    WINRT_IMPL_HeapFree
0x180004dc2  mov     rcx, [rbp+pbstr]; bstrString
0x180004dc6  test    rcx, rcx
0x180004dc9  jz      short loc_180004DD0
0x180004dcb  call    WINRT_IMPL_SysFreeString
0x180004dd0  cmp     [rbp+pperrinfo], r13
0x180004dd4  jz      short loc_180004DDF
0x180004dd6  lea     rcx, [rbp+pperrinfo]
0x180004dda  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180004ddf  mov     rax, r15
0x180004de2  mov     rbx, [rsp+70h+arg_8]
0x180004dea  add     rsp, 70h
0x180004dee  pop     r15
0x180004df0  pop     r14
0x180004df2  pop     r13
0x180004df4  pop     r12
0x180004df6  pop     rdi
0x180004df7  pop     rsi
0x180004df8  pop     rbp
0x180004df9  retn
0x180004dfa  test    eax, eax
0x180004dfc  jns     short loc_180004DC2
0x180004dfe  call    cs:__imp_abort
0x180004e05  lea     rcx, [rbp+pExceptionObject]; this
0x180004e09  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180004e0e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180004e15  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004e19  call    _CxxThrowException_0
0x180004e1f  lea     rcx, [rbp+pExceptionObject]; this
0x180004e23  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180004e28  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180004e2f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180004e33  call    _CxxThrowException_0
```
