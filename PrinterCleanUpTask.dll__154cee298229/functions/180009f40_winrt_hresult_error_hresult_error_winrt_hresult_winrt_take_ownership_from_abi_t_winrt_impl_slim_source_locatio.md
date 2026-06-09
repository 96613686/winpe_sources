# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180009f40`
- end: `0x18000a112`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `466`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `14`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180009d90`
- `0x180009de0`
- `0x180009e08`
- `0x180009e30`
- `0x180009e58`
- `0x18000a118`
- `0x18000a140`
- `0x18000a168`
- `0x18000a190`
- `0x18000a1b8`
- `0x18000a1e0`
- `0x18000a230`
- `0x18000a258`
- `0x18001000c`

## callees

- `0x18000344d`
- `0x180003471`
- `0x1800070ac`
- `0x180007118`
- `0x1800074b4`
- `0x18000750c`
- `0x180009f40`
- `0x18000a9dc`
- `0x18000f358`
- `0x18000fa50`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 *v4; // rsi
  __int64 v8; // rbx
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, __int64); // rbx
  void (__fastcall ***v11)(_QWORD, __int64 *, BSTR *); // rcx
  void (__fastcall **v12)(_QWORD, __int64 *, BSTR *); // rax
  IErrorInfo *v13; // rbx
  HRESULT (__stdcall *GetDescription)(IErrorInfo *, BSTR *); // rsi
  UINT v15; // eax
  IErrorInfo **v16; // rax
  IErrorInfo *v17; // rdx
  IErrorInfo *v19; // [rsp+20h] [rbp-28h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-20h] BYREF
  _BYTE v21[24]; // [rsp+30h] [rbp-18h] BYREF
  BSTR pbstr; // [rsp+80h] [rbp+38h] BYREF

  *(_QWORD *)a1 = 0;
  v4 = (__int64 *)(a1 + 16);
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  pbstr = 0;
  if ( pperrinfo )
    ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &pbstr);
  v8 = *(_QWORD *)winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(v4, &pbstr);
  if ( pbstr )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pbstr);
  if ( v8 )
  {
    v9 = *v4;
    v10 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v4 + 32LL);
    winrt::handle_type<winrt::impl::bstr_traits>::close(a1);
    v10(v9, a1);
    v11 = (void (__fastcall ***)(_QWORD, __int64 *, BSTR *))*v4;
    if ( *v4 )
    {
      v12 = *v11;
      pbstr = 0;
      (*v12)(v11, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &pbstr);
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pbstr);
      }
    }
  }
  else
  {
    v13 = pperrinfo;
    pbstr = 0;
    if ( pperrinfo )
    {
      GetDescription = pperrinfo->lpVtbl->GetDescription;
      winrt::handle_type<winrt::impl::bstr_traits>::close(&pbstr);
      ((void (__fastcall *)(IErrorInfo *, BSTR *))GetDescription)(v13, &pbstr);
      v13 = 0;
      v19 = 0;
      if ( pbstr )
      {
        v15 = SysStringLen_0(pbstr);
        v16 = (IErrorInfo **)winrt::impl::trim_hresult_message(v21, pbstr, v15);
        if ( &v19 != v16 )
        {
          v17 = *v16;
          *v16 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v19, v17);
          v13 = v19;
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(v21);
      }
    }
    else
    {
      v19 = 0;
    }
    winrt::hresult_error::originate(a1, a2, v13, a4);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v19);
    winrt::handle_type<winrt::impl::bstr_traits>::close(&pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180009f40  push    rbp
0x180009f42  push    rbx
0x180009f43  push    rsi
0x180009f44  push    rdi
0x180009f45  push    r14
0x180009f47  push    r15
0x180009f49  mov     rbp, rsp
0x180009f4c  sub     rsp, 48h
0x180009f50  mov     qword ptr [rcx], 0
0x180009f57  lea     rsi, [rcx+10h]
0x180009f5b  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180009f62  mov     edi, edx
0x180009f64  mov     [rcx+0Ch], edx
0x180009f67  mov     r14, rcx
0x180009f6a  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180009f6e  mov     qword ptr [rsi], 0
0x180009f75  xor     ecx, ecx; dwReserved
0x180009f77  mov     [rbp+pperrinfo], 0
0x180009f7f  mov     r15, r9
0x180009f82  call    GetErrorInfo_0
0x180009f87  mov     rcx, [rbp+pperrinfo]
0x180009f8b  mov     [rbp+pbstr], 0
0x180009f93  test    rcx, rcx
0x180009f96  jz      short loc_180009FB6
0x180009f98  mov     rax, [rcx]
0x180009f9b  lea     r8, [rbp+pbstr]
0x180009f9f  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180009fa6  mov     rax, [rax]
0x180009fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fae  mov     rax, [rbp+pbstr]
0x180009fb2  mov     [rbp+pbstr], rax
0x180009fb6  lea     rdx, [rbp+pbstr]
0x180009fba  mov     rcx, rsi
0x180009fbd  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x180009fc2  cmp     [rbp+pbstr], 0
0x180009fc7  mov     rbx, [rax]
0x180009fca  jz      short loc_180009FD5
0x180009fcc  lea     rcx, [rbp+pbstr]
0x180009fd0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009fd5  test    rbx, rbx
0x180009fd8  jz      short loc_18000A051
0x180009fda  mov     rdi, [rsi]
0x180009fdd  mov     rcx, r14
0x180009fe0  mov     rax, [rdi]
0x180009fe3  mov     rbx, [rax+20h]
0x180009fe7  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x180009fec  mov     rdx, r14
0x180009fef  mov     rcx, rdi
0x180009ff2  mov     rax, rbx
0x180009ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ffa  mov     rcx, [rsi]
0x180009ffd  test    rcx, rcx
0x18000a000  jz      loc_18000A0F2
0x18000a006  mov     rax, [rcx]
0x18000a009  lea     r8, [rbp+pbstr]
0x18000a00d  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x18000a014  mov     [rbp+pbstr], 0
0x18000a01c  mov     rax, [rax]
0x18000a01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a024  mov     rcx, [rbp+pbstr]
0x18000a028  mov     [rbp+pbstr], rcx
0x18000a02c  test    rcx, rcx
0x18000a02f  jz      loc_18000A0F2
0x18000a035  mov     rax, [rcx]
0x18000a038  xor     edx, edx
0x18000a03a  mov     rax, [rax+28h]
0x18000a03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a043  lea     rcx, [rbp+pbstr]
0x18000a047  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000a04c  jmp     loc_18000A0F2
0x18000a051  mov     rbx, [rbp+pperrinfo]
0x18000a055  mov     [rbp+pbstr], 0
0x18000a05d  test    rbx, rbx
0x18000a060  jnz     short loc_18000A068
0x18000a062  mov     [rbp+var_28], rbx
0x18000a066  jmp     short loc_18000A0D0
0x18000a068  mov     rax, [rbx]
0x18000a06b  lea     rcx, [rbp+pbstr]
0x18000a06f  mov     rsi, [rax+28h]
0x18000a073  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x18000a078  lea     rdx, [rbp+pbstr]
0x18000a07c  mov     rcx, rbx
0x18000a07f  mov     rax, rsi
0x18000a082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a087  mov     rcx, [rbp+pbstr]; pbstr
0x18000a08b  xor     ebx, ebx
0x18000a08d  mov     [rbp+var_28], rbx
0x18000a091  test    rcx, rcx
0x18000a094  jz      short loc_18000A0D0
0x18000a096  call    SysStringLen_0
0x18000a09b  mov     rdx, [rbp+pbstr]
0x18000a09f  lea     rcx, [rbp+var_18]
0x18000a0a3  mov     r8d, eax
0x18000a0a6  call    ?trim_hresult_message@impl@winrt@@YA?AUhstring@2@QEBGI@Z; winrt::impl::trim_hresult_message(ushort const * const,uint)
0x18000a0ab  lea     rcx, [rbp+var_28]
0x18000a0af  cmp     rcx, rax
0x18000a0b2  jz      short loc_18000A0C7
0x18000a0b4  mov     rdx, [rax]
0x18000a0b7  lea     rcx, [rbp+var_28]
0x18000a0bb  mov     [rax], rbx
0x18000a0be  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18000a0c3  mov     rbx, [rbp+var_28]
0x18000a0c7  lea     rcx, [rbp+var_18]
0x18000a0cb  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000a0d0  mov     r9, r15
0x18000a0d3  mov     r8, rbx
0x18000a0d6  mov     edx, edi
0x18000a0d8  mov     rcx, r14
0x18000a0db  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000a0e0  lea     rcx, [rbp+var_28]
0x18000a0e4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000a0e9  lea     rcx, [rbp+pbstr]
0x18000a0ed  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x18000a0f2  cmp     [rbp+pperrinfo], 0
0x18000a0f7  jz      short loc_18000A102
0x18000a0f9  lea     rcx, [rbp+pperrinfo]
0x18000a0fd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000a102  mov     rax, r14
0x18000a105  add     rsp, 48h
0x18000a109  pop     r15
0x18000a10b  pop     r14
0x18000a10d  pop     rdi
0x18000a10e  pop     rsi
0x18000a10f  pop     rbx
0x18000a110  pop     rbp
0x18000a111  retn
```
