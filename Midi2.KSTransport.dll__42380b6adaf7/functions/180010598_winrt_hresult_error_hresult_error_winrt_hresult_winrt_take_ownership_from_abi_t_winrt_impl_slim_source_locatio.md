# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180010598`
- end: `0x18001082a`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `658`
- prototype: ``
- caller_count: `14`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180010448`
- `0x1800104b4`
- `0x180010520`
- `0x180010548`
- `0x180010570`
- `0x180010830`
- `0x180010858`
- `0x180010880`
- `0x1800108a8`
- `0x180010914`
- `0x18001093c`
- `0x1800109a8`
- `0x1800109d0`
- `0x180015348`

## callees

- `0x1800051e6`
- `0x180005254`
- `0x18000526c`
- `0x1800052fc`
- `0x18000535c`
- `0x180005374`
- `0x1800053a4`
- `0x180005479`
- `0x18000d1c0`
- `0x180010598`
- `0x180011240`
- `0x180014ee4`
- `0x180014fc4`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010823`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010823`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180010713`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180010713`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010799`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010799`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 *v7; // rbx
  __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // rdi
  void (__fastcall *v11)(__int64, __int64); // r14
  void (__fastcall ***v12)(_QWORD, __int64 *, void **); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // ebx
  BSTR v15; // r12
  OLECHAR *v16; // r14
  const char *v17; // rdx
  struct winrt::impl::shared_hstring_header *v18; // r14
  void *v19; // rbx
  int v20; // eax
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r9
  size_t v25; // r8
  void *v26; // rcx
  signed __int32 v27; // r15d
  HANDLE v28; // rax
  BSTR pbstr; // [rsp+20h] [rbp-28h] BYREF
  void *v31; // [rsp+28h] [rbp-20h] BYREF
  void *v32; // [rsp+30h] [rbp-18h] BYREF
  LPVOID lpMem[2]; // [rsp+38h] [rbp-10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+90h] [rbp+48h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v7 = (__int64 *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  if ( pperrinfo )
  {
    v32 = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, void **))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &v32);
    v8 = (__int64)v32;
    v31 = v32;
  }
  else
  {
    v31 = 0;
    v8 = 0;
  }
  if ( v7 == (__int64 *)&v31 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v31);
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
    v11 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v7 + 32LL);
    if ( *(_QWORD *)a1 )
    {
      WINRT_IMPL_SysFreeString(*(BSTR *)a1);
      *(_QWORD *)a1 = 0;
    }
    v11(v10, a1);
    v12 = (void (__fastcall ***)(_QWORD, __int64 *, void **))*v7;
    if ( *v7 )
    {
      v32 = 0;
      (**v12)(v12, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &v32);
      lpMem[0] = v32;
      if ( v32 )
      {
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v32 + 40LL))(v32, 0);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)lpMem);
      }
    }
    goto LABEL_39;
  }
  pbstr = 0;
  v13 = 0;
  v32 = 0;
  if ( !pperrinfo )
    goto LABEL_34;
  ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr);
  if ( !pbstr )
    goto LABEL_34;
  v14 = SysStringLen_0(pbstr);
  v15 = pbstr;
  v16 = &pbstr[v14 - 1];
  if ( v14 )
  {
    while ( (unsigned int)_o_iswspace(*v16) )
    {
      --v16;
      if ( !--v14 )
        goto LABEL_21;
    }
    v22 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v14, v17);
    v18 = v22;
    v25 = 2LL * v14;
    if ( !v25 )
      goto LABEL_22;
    v26 = (char *)v22 + 28;
    if ( v22 != (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      if ( v15 )
      {
        memcpy_0(v26, v15, v25);
        goto LABEL_22;
      }
      memset_0(v26, 0, v25);
    }
    *(_DWORD *)_o__errno(v26, v23, v25, v24) = 22;
    invalid_parameter_noinfo();
    goto LABEL_22;
  }
LABEL_21:
  v18 = 0;
LABEL_22:
  lpMem[0] = v18;
  winrt::hstring::operator=(&v32, lpMem);
  v19 = lpMem[0];
  if ( lpMem[0] )
  {
    v20 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v20 )
    {
      if ( v20 < 0 )
        goto LABEL_43;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v19);
    }
  }
  v13 = (volatile signed __int32 *)v32;
LABEL_34:
  winrt::hresult_error::originate(a1, a2, v13, a4);
  if ( !v13 )
    goto LABEL_37;
  v27 = _InterlockedExchangeAdd(v13 + 6, 0xFFFFFFFF);
  if ( v27 == 1 )
  {
    v28 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v28, 0, (LPVOID)v13);
    goto LABEL_37;
  }
  if ( v27 - 1 < 0 )
LABEL_43:
    abort();
LABEL_37:
  if ( pbstr )
    WINRT_IMPL_SysFreeString(pbstr);
LABEL_39:
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180010598  push    rbp
0x18001059a  push    rbx
0x18001059b  push    rsi
0x18001059c  push    rdi
0x18001059d  push    r12
0x18001059f  push    r13
0x1800105a1  push    r14
0x1800105a3  push    r15
0x1800105a5  mov     rbp, rsp
0x1800105a8  sub     rsp, 48h
0x1800105ac  mov     r13, r9
0x1800105af  mov     edi, edx
0x1800105b1  mov     rsi, rcx
0x1800105b4  xor     r12d, r12d
0x1800105b7  mov     [rcx], r12
0x1800105ba  mov     dword ptr [rcx+8], 0AABBCCDDh
0x1800105c1  mov     [rcx+0Ch], edx
0x1800105c4  lea     rbx, [rcx+10h]
0x1800105c8  mov     [rbx], r12
0x1800105cb  mov     [rbp+pperrinfo], r12
0x1800105cf  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x1800105d3  xor     ecx, ecx; dwReserved
0x1800105d5  call    GetErrorInfo_0
0x1800105da  mov     rcx, [rbp+pperrinfo]
0x1800105de  test    rcx, rcx
0x1800105e1  jnz     short loc_1800105EC
0x1800105e3  mov     [rbp+var_20], r12
0x1800105e7  mov     r14d, r12d
0x1800105ea  jmp     short loc_18001060E
0x1800105ec  mov     [rbp+var_18], r12
0x1800105f0  mov     rax, [rcx]
0x1800105f3  lea     r8, [rbp+var_18]
0x1800105f7  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1800105fe  mov     rax, [rax]
0x180010601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010606  mov     r14, [rbp+var_18]
0x18001060a  mov     [rbp+var_20], r14
0x18001060e  lea     rax, [rbp+var_20]
0x180010612  cmp     rbx, rax
0x180010615  jz      short loc_18001062C
0x180010617  cmp     [rbx], r12
0x18001061a  jz      short loc_180010624
0x18001061c  mov     rcx, rbx
0x18001061f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010624  mov     [rbx], r14
0x180010627  mov     r15, r14
0x18001062a  jmp     short loc_18001063D
0x18001062c  mov     r15, [rbx]
0x18001062f  test    r14, r14
0x180010632  jz      short loc_18001063D
0x180010634  lea     rcx, [rbp+var_20]
0x180010638  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001063d  test    r15, r15
0x180010640  jz      short loc_1800106BD
0x180010642  mov     rdi, [rbx]
0x180010645  mov     rax, [rdi]
0x180010648  mov     r14, [rax+20h]
0x18001064c  mov     rcx, [rsi]; bstrString
0x18001064f  test    rcx, rcx
0x180010652  jz      short loc_18001065C
0x180010654  call    WINRT_IMPL_SysFreeString
0x180010659  mov     [rsi], r12
0x18001065c  mov     rdx, rsi
0x18001065f  mov     rcx, rdi
0x180010662  mov     rax, r14
0x180010665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001066a  mov     rcx, [rbx]
0x18001066d  test    rcx, rcx
0x180010670  jz      loc_1800107FE
0x180010676  mov     [rbp+var_18], r12
0x18001067a  mov     rax, [rcx]
0x18001067d  lea     r8, [rbp+var_18]
0x180010681  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x180010688  mov     rax, [rax]
0x18001068b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010690  mov     rcx, [rbp+var_18]
0x180010694  mov     [rbp+lpMem], rcx
0x180010698  test    rcx, rcx
0x18001069b  jz      loc_1800107FE
0x1800106a1  mov     rax, [rcx]
0x1800106a4  xor     edx, edx
0x1800106a6  mov     rax, [rax+28h]
0x1800106aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106af  lea     rcx, [rbp+lpMem]
0x1800106b3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800106b8  jmp     loc_1800107FE
0x1800106bd  mov     [rbp+pbstr], r12
0x1800106c1  mov     rbx, r12
0x1800106c4  mov     [rbp+var_18], rbx
0x1800106c8  or      r15d, 0FFFFFFFFh
0x1800106cc  mov     rcx, [rbp+pperrinfo]
0x1800106d0  test    rcx, rcx
0x1800106d3  jz      loc_1800107BA
0x1800106d9  mov     rax, [rcx]
0x1800106dc  lea     rdx, [rbp+pbstr]
0x1800106e0  mov     rax, [rax+28h]
0x1800106e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e9  mov     rcx, [rbp+pbstr]; pbstr
0x1800106ed  test    rcx, rcx
0x1800106f0  jz      loc_1800107BA
0x1800106f6  call    SysStringLen_0
0x1800106fb  mov     ebx, eax
0x1800106fd  mov     r12, [rbp+pbstr]
0x180010701  mov     r14d, eax
0x180010704  dec     r14
0x180010707  lea     r14, [r12+r14*2]
0x18001070b  test    eax, eax
0x18001070d  jz      short loc_180010726
0x18001070f  movzx   ecx, word ptr [r14]
0x180010713  call    cs:__imp__o_iswspace
0x180010719  test    eax, eax
0x18001071b  jz      short loc_180010768
0x18001071d  sub     r14, 2
0x180010721  add     ebx, 0FFFFFFFFh
0x180010724  jnz     short loc_18001070F
0x180010726  xor     r12d, r12d
0x180010729  mov     r14d, r12d
0x18001072c  mov     [rbp+lpMem], r14
0x180010730  lea     rdx, [rbp+lpMem]
0x180010734  lea     rcx, [rbp+var_18]
0x180010738  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18001073d  mov     rbx, [rbp+lpMem]
0x180010741  test    rbx, rbx
0x180010744  jz      short loc_1800107B6
0x180010746  mov     eax, r15d
0x180010749  lock xadd [rbx+18h], eax
0x18001074e  sub     eax, 1
0x180010751  jnz     short loc_1800107B2
0x180010753  nop
0x180010754  call    WINRT_IMPL_GetProcessHeap
0x180010759  mov     rcx, rax; hHeap
0x18001075c  mov     r8, rbx; lpMem
0x18001075f  xor     edx, edx; dwFlags
0x180010761  call    WINRT_IMPL_HeapFree
0x180010766  jmp     short loc_1800107B6
0x180010768  mov     ecx, ebx; this
0x18001076a  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001076f  mov     r14, rax
0x180010772  mov     r8d, ebx
0x180010775  add     r8, r8; Size
0x180010778  jz      short loc_1800107AA
0x18001077a  lea     rcx, [rax+1Ch]; void *
0x18001077e  test    rcx, rcx
0x180010781  jz      short loc_180010799
0x180010783  test    r12, r12
0x180010786  jz      short loc_180010792
0x180010788  mov     rdx, r12; Src
0x18001078b  call    memcpy_0
0x180010790  jmp     short loc_1800107AA
0x180010792  xor     edx, edx; Val
0x180010794  call    memset_0
0x180010799  call    cs:__imp__o__errno
0x18001079f  mov     dword ptr [rax], 16h
0x1800107a5  call    _invalid_parameter_noinfo
0x1800107aa  xor     r12d, r12d
0x1800107ad  jmp     loc_18001072C
0x1800107b2  test    eax, eax
0x1800107b4  js      short loc_180010823
0x1800107b6  mov     rbx, [rbp+var_18]
0x1800107ba  mov     r9, r13
0x1800107bd  mov     r8, rbx
0x1800107c0  mov     edx, edi
0x1800107c2  mov     rcx, rsi
0x1800107c5  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x1800107ca  test    rbx, rbx
0x1800107cd  jz      short loc_1800107F0
0x1800107cf  lock xadd [rbx+18h], r15d
0x1800107d5  lea     eax, [r15-1]
0x1800107d9  test    eax, eax
0x1800107db  jnz     short loc_180010821
0x1800107dd  nop
0x1800107de  call    WINRT_IMPL_GetProcessHeap
0x1800107e3  mov     rcx, rax; hHeap
0x1800107e6  mov     r8, rbx; lpMem
0x1800107e9  xor     edx, edx; dwFlags
0x1800107eb  call    WINRT_IMPL_HeapFree
0x1800107f0  mov     rcx, [rbp+pbstr]; bstrString
0x1800107f4  test    rcx, rcx
0x1800107f7  jz      short loc_1800107FE
0x1800107f9  call    WINRT_IMPL_SysFreeString
0x1800107fe  cmp     [rbp+pperrinfo], r12
0x180010802  jz      short loc_18001080D
0x180010804  lea     rcx, [rbp+pperrinfo]
0x180010808  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001080d  mov     rax, rsi
0x180010810  add     rsp, 48h
0x180010814  pop     r15
0x180010816  pop     r14
0x180010818  pop     r13
0x18001081a  pop     r12
0x18001081c  pop     rdi
0x18001081d  pop     rsi
0x18001081e  pop     rbx
0x18001081f  pop     rbp
0x180010820  retn
0x180010821  jns     short loc_1800107F0
0x180010823  call    cs:__imp_abort
```
