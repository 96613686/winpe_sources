# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x140009f74`
- end: `0x14000a23e`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `714`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int *)`
- caller_count: `14`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009eac`
- `0x140009ed4`
- `0x140009efc`
- `0x140009f24`
- `0x140009f4c`
- `0x14000a244`
- `0x14000a26c`
- `0x14000a294`
- `0x14000a2bc`
- `0x14000a2e4`
- `0x14000a30c`
- `0x14000a334`
- `0x14000a35c`
- `0x14000b0a8`

## callees

- `0x1400022ac`
- `0x1400022d0`
- `0x1400022dc`
- `0x1400022e8`
- `0x1400022f4`
- `0x140002300`
- `0x140009f74`
- `0x14000b2d4`
- `0x14000b3f0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14000a17c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14000a237`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14000a17c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14000a237`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  BSTR *v7; // rsi
  BSTR v8; // rbx
  BSTR v9; // r15
  BSTR v10; // rbx
  void (__fastcall *v11)(BSTR, __int64); // rdi
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // eax
  char *v15; // rax
  void *v16; // r15
  int v17; // eax
  HANDLE ProcessHeap; // rax
  OLECHAR *v19; // rdi
  signed __int32 v20; // r13d
  HANDLE v21; // rax
  IErrorInfo *v23; // [rsp+30h] [rbp-38h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-30h] BYREF
  BSTR v25; // [rsp+40h] [rbp-28h] BYREF
  LPVOID v26; // [rsp+48h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-18h] BYREF
  char v28; // [rsp+58h] [rbp-10h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+40h]
  IErrorInfo *pperrinfo; // [rsp+B0h] [rbp+48h] BYREF

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
    v25 = pbstr;
  }
  else
  {
    v25 = 0;
    v8 = 0;
  }
  if ( v7 == &v25 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v25);
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
      lpMem = pbstr;
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&lpMem);
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
        v15 = (char *)winrt::impl::trim_hresult_message(&lpMem, pbstr, v14);
        if ( &v28 != v15 )
        {
          v13 = *(volatile signed __int32 **)v15;
          *(_QWORD *)v15 = 0;
        }
        v16 = lpMem;
        if ( lpMem )
        {
          v17 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v17 )
          {
            if ( v17 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v16);
          }
        }
      }
    }
    else
    {
      v13 = 0;
    }
    RoOriginateLanguageException_0(a2, v13, 0);
    if ( winrt_throw_hresult_handler )
      winrt_throw_hresult_handler(*a4, *((_QWORD *)a4 + 1), *((_QWORD *)a4 + 2), retaddr, a2);
    v23 = 0;
    GetErrorInfo_0(0, &v23);
    if ( v23 )
    {
      lpMem = 0;
      ((void (__fastcall *)(IErrorInfo *, __int64 *, LPVOID *))v23->lpVtbl->QueryInterface)(
        v23,
        winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
        &lpMem);
      v19 = (OLECHAR *)lpMem;
      v26 = lpMem;
    }
    else
    {
      v26 = 0;
      v19 = 0;
    }
    if ( v7 == (BSTR *)&v26 )
    {
      if ( v19 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v26);
    }
    else
    {
      if ( *v7 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v7);
      *v7 = v19;
    }
    if ( v23 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v23);
    if ( v13 )
    {
      v20 = _InterlockedExchangeAdd(v13 + 6, 0xFFFFFFFF);
      if ( v20 == 1 )
      {
        v21 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v21, 0, (LPVOID)v13);
      }
      else if ( v20 - 1 < 0 )
      {
        abort();
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
0x140009f74  push    rbp
0x140009f76  push    rbx
0x140009f77  push    rsi
0x140009f78  push    rdi
0x140009f79  push    r12
0x140009f7b  push    r13
0x140009f7d  push    r14
0x140009f7f  push    r15
0x140009f81  mov     rbp, rsp
0x140009f84  sub     rsp, 68h
0x140009f88  mov     r12, r9
0x140009f8b  mov     edi, edx
0x140009f8d  mov     r14, rcx
0x140009f90  xor     r13d, r13d
0x140009f93  mov     [rcx], r13
0x140009f96  mov     dword ptr [rcx+8], 0AABBCCDDh
0x140009f9d  mov     [rcx+0Ch], edx
0x140009fa0  lea     rsi, [rcx+10h]
0x140009fa4  mov     [rsi], r13
0x140009fa7  mov     [rbp+pperrinfo], r13
0x140009fab  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x140009faf  xor     ecx, ecx; dwReserved
0x140009fb1  call    GetErrorInfo_0
0x140009fb6  mov     rcx, [rbp+pperrinfo]
0x140009fba  test    rcx, rcx
0x140009fbd  jnz     short loc_140009FC8
0x140009fbf  mov     [rbp+var_28], r13
0x140009fc3  mov     ebx, r13d
0x140009fc6  jmp     short loc_140009FEA
0x140009fc8  mov     [rbp+pbstr], r13
0x140009fcc  mov     rax, [rcx]
0x140009fcf  lea     r8, [rbp+pbstr]
0x140009fd3  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x140009fda  mov     rax, [rax]
0x140009fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fe2  mov     rbx, [rbp+pbstr]
0x140009fe6  mov     [rbp+var_28], rbx
0x140009fea  lea     rax, [rbp+var_28]
0x140009fee  cmp     rsi, rax
0x140009ff1  jz      short loc_14000A008
0x140009ff3  cmp     [rsi], r13
0x140009ff6  jz      short loc_14000A000
0x140009ff8  mov     rcx, rsi
0x140009ffb  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a000  mov     [rsi], rbx
0x14000a003  mov     r15, rbx
0x14000a006  jmp     short loc_14000A019
0x14000a008  mov     r15, [rsi]
0x14000a00b  test    rbx, rbx
0x14000a00e  jz      short loc_14000A019
0x14000a010  lea     rcx, [rbp+var_28]
0x14000a014  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a019  test    r15, r15
0x14000a01c  jz      short loc_14000A09C
0x14000a01e  mov     rbx, [rsi]
0x14000a021  mov     rax, [rbx]
0x14000a024  mov     rdi, [rax+20h]
0x14000a028  mov     rcx, [r14]; bstrString
0x14000a02b  xor     r15d, r15d
0x14000a02e  test    rcx, rcx
0x14000a031  jz      short loc_14000A03B
0x14000a033  call    WINRT_IMPL_SysFreeString
0x14000a038  mov     [r14], r15
0x14000a03b  mov     rdx, r14
0x14000a03e  mov     rcx, rbx
0x14000a041  mov     rax, rdi
0x14000a044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a049  mov     rcx, [rsi]
0x14000a04c  test    rcx, rcx
0x14000a04f  jz      loc_14000A212
0x14000a055  mov     [rbp+pbstr], r15
0x14000a059  mov     rax, [rcx]
0x14000a05c  lea     r8, [rbp+pbstr]
0x14000a060  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x14000a067  mov     rax, [rax]
0x14000a06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a06f  mov     rcx, [rbp+pbstr]
0x14000a073  mov     [rbp+lpMem], rcx
0x14000a077  test    rcx, rcx
0x14000a07a  jz      loc_14000A212
0x14000a080  mov     rax, [rcx]
0x14000a083  xor     edx, edx
0x14000a085  mov     rax, [rax+28h]
0x14000a089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a08e  lea     rcx, [rbp+lpMem]
0x14000a092  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a097  jmp     loc_14000A212
0x14000a09c  mov     [rbp+pbstr], r15
0x14000a0a0  or      r13d, 0FFFFFFFFh
0x14000a0a4  cmp     [rbp+pperrinfo], r15
0x14000a0a8  jnz     short loc_14000A0AF
0x14000a0aa  mov     rbx, r15
0x14000a0ad  jmp     short loc_14000A120
0x14000a0af  mov     rcx, [rbp+pperrinfo]
0x14000a0b3  mov     rax, [rcx]
0x14000a0b6  lea     rdx, [rbp+pbstr]
0x14000a0ba  mov     rax, [rax+28h]
0x14000a0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0c3  mov     rbx, r15
0x14000a0c6  mov     rcx, [rbp+pbstr]; pbstr
0x14000a0ca  test    rcx, rcx
0x14000a0cd  jz      short loc_14000A120
0x14000a0cf  call    SysStringLen_0
0x14000a0d4  mov     r8d, eax
0x14000a0d7  mov     rdx, [rbp+pbstr]
0x14000a0db  lea     rcx, [rbp+lpMem]
0x14000a0df  call    ?trim_hresult_message@impl@winrt@@YA?AUhstring@2@QEB_WI@Z; winrt::impl::trim_hresult_message(wchar_t const * const,uint)
0x14000a0e4  lea     rcx, [rbp+var_10]
0x14000a0e8  cmp     rcx, rax
0x14000a0eb  jz      short loc_14000A0F3
0x14000a0ed  mov     rbx, [rax]
0x14000a0f0  mov     [rax], r15
0x14000a0f3  mov     r15, [rbp+lpMem]
0x14000a0f7  test    r15, r15
0x14000a0fa  jz      short loc_14000A11D
0x14000a0fc  mov     eax, r13d
0x14000a0ff  lock xadd [r15+18h], eax
0x14000a105  sub     eax, 1
0x14000a108  jnz     short loc_14000A175
0x14000a10a  nop
0x14000a10b  call    WINRT_IMPL_GetProcessHeap
0x14000a110  mov     rcx, rax; hHeap
0x14000a113  mov     r8, r15; lpMem
0x14000a116  xor     edx, edx; dwFlags
0x14000a118  call    WINRT_IMPL_HeapFree
0x14000a11d  xor     r15d, r15d
0x14000a120  xor     r8d, r8d
0x14000a123  mov     rdx, rbx
0x14000a126  mov     ecx, edi
0x14000a128  call    RoOriginateLanguageException_0
0x14000a12d  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x14000a134  test    rax, rax
0x14000a137  jz      short loc_14000A154
0x14000a139  mov     r9, [rbp+40h]
0x14000a13d  mov     [rsp+68h+var_48], edi
0x14000a141  mov     r8, [r12+10h]
0x14000a146  mov     rdx, [r12+8]
0x14000a14b  mov     ecx, [r12]
0x14000a14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a154  mov     [rbp+var_38], r15
0x14000a158  lea     rdx, [rbp+var_38]; pperrinfo
0x14000a15c  xor     ecx, ecx; dwReserved
0x14000a15e  call    GetErrorInfo_0
0x14000a163  mov     rcx, [rbp+var_38]
0x14000a167  test    rcx, rcx
0x14000a16a  jnz     short loc_14000A183
0x14000a16c  mov     [rbp+var_20], r15
0x14000a170  mov     rdi, r15
0x14000a173  jmp     short loc_14000A1A5
0x14000a175  xor     r15d, r15d
0x14000a178  test    eax, eax
0x14000a17a  jns     short loc_14000A120
0x14000a17c  call    cs:__imp_abort
0x14000a183  mov     [rbp+lpMem], r15
0x14000a187  mov     rax, [rcx]
0x14000a18a  lea     r8, [rbp+lpMem]
0x14000a18e  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x14000a195  mov     rax, [rax]
0x14000a198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a19d  mov     rdi, [rbp+lpMem]
0x14000a1a1  mov     [rbp+var_20], rdi
0x14000a1a5  lea     rax, [rbp+var_20]
0x14000a1a9  cmp     rsi, rax
0x14000a1ac  jz      short loc_14000A1C0
0x14000a1ae  cmp     [rsi], r15
0x14000a1b1  jz      short loc_14000A1BB
0x14000a1b3  mov     rcx, rsi
0x14000a1b6  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a1bb  mov     [rsi], rdi
0x14000a1be  jmp     short loc_14000A1CE
0x14000a1c0  test    rdi, rdi
0x14000a1c3  jz      short loc_14000A1CE
0x14000a1c5  lea     rcx, [rbp+var_20]
0x14000a1c9  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a1ce  cmp     [rbp+var_38], r15
0x14000a1d2  jz      short loc_14000A1DE
0x14000a1d4  lea     rcx, [rbp+var_38]
0x14000a1d8  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a1dd  nop
0x14000a1de  test    rbx, rbx
0x14000a1e1  jz      short loc_14000A204
0x14000a1e3  lock xadd [rbx+18h], r13d
0x14000a1e9  lea     eax, [r13-1]
0x14000a1ed  test    eax, eax
0x14000a1ef  jnz     short loc_14000A235
0x14000a1f1  nop
0x14000a1f2  call    WINRT_IMPL_GetProcessHeap
0x14000a1f7  mov     rcx, rax; hHeap
0x14000a1fa  mov     r8, rbx; lpMem
0x14000a1fd  xor     edx, edx; dwFlags
0x14000a1ff  call    WINRT_IMPL_HeapFree
0x14000a204  mov     rcx, [rbp+pbstr]; bstrString
0x14000a208  test    rcx, rcx
0x14000a20b  jz      short loc_14000A212
0x14000a20d  call    WINRT_IMPL_SysFreeString
0x14000a212  cmp     [rbp+pperrinfo], r15
0x14000a216  jz      short loc_14000A221
0x14000a218  lea     rcx, [rbp+pperrinfo]
0x14000a21c  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a221  mov     rax, r14
0x14000a224  add     rsp, 68h
0x14000a228  pop     r15
0x14000a22a  pop     r14
0x14000a22c  pop     r13
0x14000a22e  pop     r12
0x14000a230  pop     rdi
0x14000a231  pop     rsi
0x14000a232  pop     rbx
0x14000a233  pop     rbp
0x14000a234  retn
0x14000a235  jns     short loc_14000A204
0x14000a237  call    cs:__imp_abort
```
