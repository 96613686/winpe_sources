# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x140004648`
- end: `0x140004827`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `479`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `14`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140004538`
- `0x140004560`
- `0x140004588`
- `0x1400045b0`
- `0x1400045d8`
- `0x140004830`
- `0x140004858`
- `0x140004880`
- `0x1400048a8`
- `0x1400048d0`
- `0x1400048f8`
- `0x140004920`
- `0x140004948`
- `0x140007c54`

## callees

- `0x1400030a3`
- `0x1400030af`
- `0x140004648`
- `0x140004ce4`
- `0x140007860`
- `0x14000788c`
- `0x140007964`
- `0x140007e80`
- `0x140007eec`
- `0x140012010`

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
  IErrorInfo *v18; // [rsp+20h] [rbp-28h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-20h] BYREF
  _BYTE v20[24]; // [rsp+30h] [rbp-18h] BYREF
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
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pbstr);
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
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pbstr);
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
      v18 = 0;
      if ( pbstr )
      {
        v15 = SysStringLen_0(pbstr);
        v16 = (IErrorInfo **)winrt::impl::trim_hresult_message(v20, pbstr, v15);
        if ( &v18 != v16 )
        {
          v13 = *v16;
          *v16 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
          v18 = v13;
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(v20);
      }
    }
    else
    {
      v18 = 0;
    }
    winrt::hresult_error::originate(a1, a2, v13, a4, v18);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
    winrt::handle_type<winrt::impl::bstr_traits>::close(&pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x140004648  push    rbp
0x14000464a  push    rbx
0x14000464b  push    rsi
0x14000464c  push    rdi
0x14000464d  push    r14
0x14000464f  push    r15
0x140004651  mov     rbp, rsp
0x140004654  sub     rsp, 48h
0x140004658  mov     qword ptr [rcx], 0
0x14000465f  lea     rsi, [rcx+10h]
0x140004663  mov     dword ptr [rcx+8], 0AABBCCDDh
0x14000466a  mov     edi, edx
0x14000466c  mov     [rcx+0Ch], edx
0x14000466f  mov     r14, rcx
0x140004672  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x140004676  mov     qword ptr [rsi], 0
0x14000467d  xor     ecx, ecx; dwReserved
0x14000467f  mov     [rbp+pperrinfo], 0
0x140004687  mov     r15, r9
0x14000468a  call    GetErrorInfo_0
0x14000468f  mov     rcx, [rbp+pperrinfo]
0x140004693  mov     [rbp+pbstr], 0
0x14000469b  test    rcx, rcx
0x14000469e  jz      short loc_1400046BE
0x1400046a0  mov     rax, [rcx]
0x1400046a3  lea     r8, [rbp+pbstr]
0x1400046a7  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1400046ae  mov     rax, [rax]
0x1400046b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046b6  mov     rax, [rbp+pbstr]
0x1400046ba  mov     [rbp+pbstr], rax
0x1400046be  lea     rdx, [rbp+pbstr]
0x1400046c2  mov     rcx, rsi
0x1400046c5  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x1400046ca  cmp     [rbp+pbstr], 0
0x1400046cf  mov     rbx, [rax]
0x1400046d2  jz      short loc_1400046DD
0x1400046d4  lea     rcx, [rbp+pbstr]
0x1400046d8  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1400046dd  test    rbx, rbx
0x1400046e0  jz      short loc_140004759
0x1400046e2  mov     rdi, [rsi]
0x1400046e5  mov     rcx, r14
0x1400046e8  mov     rax, [rdi]
0x1400046eb  mov     rbx, [rax+20h]
0x1400046ef  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x1400046f4  mov     rdx, r14
0x1400046f7  mov     rcx, rdi
0x1400046fa  mov     rax, rbx
0x1400046fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004702  mov     rcx, [rsi]
0x140004705  test    rcx, rcx
0x140004708  jz      loc_140004807
0x14000470e  mov     rax, [rcx]
0x140004711  lea     r8, [rbp+pbstr]
0x140004715  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x14000471c  mov     [rbp+pbstr], 0
0x140004724  mov     rax, [rax]
0x140004727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000472c  mov     rcx, [rbp+pbstr]
0x140004730  mov     [rbp+pbstr], rcx
0x140004734  test    rcx, rcx
0x140004737  jz      loc_140004807
0x14000473d  mov     rax, [rcx]
0x140004740  xor     edx, edx
0x140004742  mov     rax, [rax+28h]
0x140004746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000474b  lea     rcx, [rbp+pbstr]
0x14000474f  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140004754  jmp     loc_140004807
0x140004759  mov     rbx, [rbp+pperrinfo]
0x14000475d  mov     [rbp+pbstr], 0
0x140004765  test    rbx, rbx
0x140004768  jnz     short loc_140004770
0x14000476a  mov     [rbp+var_28], rbx
0x14000476e  jmp     short loc_1400047E5
0x140004770  mov     rax, [rbx]
0x140004773  lea     rcx, [rbp+pbstr]
0x140004777  mov     rsi, [rax+28h]
0x14000477b  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x140004780  lea     rdx, [rbp+pbstr]
0x140004784  mov     rcx, rbx
0x140004787  mov     rax, rsi
0x14000478a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000478f  mov     rcx, [rbp+pbstr]; pbstr
0x140004793  xor     ebx, ebx
0x140004795  mov     [rbp+var_28], rbx
0x140004799  test    rcx, rcx
0x14000479c  jz      short loc_1400047E5
0x14000479e  call    SysStringLen_0
0x1400047a3  mov     rdx, [rbp+pbstr]
0x1400047a7  lea     rcx, [rbp+var_18]
0x1400047ab  mov     r8d, eax
0x1400047ae  call    ?trim_hresult_message@impl@winrt@@YA?AUhstring@2@QEBGI@Z; winrt::impl::trim_hresult_message(ushort const * const,uint)
0x1400047b3  lea     rcx, [rbp+var_28]
0x1400047b7  cmp     rcx, rax
0x1400047ba  jz      short loc_1400047DC
0x1400047bc  mov     rbx, [rax]
0x1400047bf  lea     rcx, [rbp+var_28]
0x1400047c3  mov     qword ptr [rax], 0
0x1400047ca  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1400047cf  lea     rcx, [rbp+var_28]
0x1400047d3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1400047d8  mov     [rbp+var_28], rbx
0x1400047dc  lea     rcx, [rbp+var_18]
0x1400047e0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1400047e5  mov     r9, r15
0x1400047e8  mov     r8, rbx
0x1400047eb  mov     edx, edi
0x1400047ed  mov     rcx, r14
0x1400047f0  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x1400047f5  lea     rcx, [rbp+var_28]
0x1400047f9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1400047fe  lea     rcx, [rbp+pbstr]
0x140004802  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x140004807  cmp     [rbp+pperrinfo], 0
0x14000480c  jz      short loc_140004817
0x14000480e  lea     rcx, [rbp+pperrinfo]
0x140004812  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140004817  mov     rax, r14
0x14000481a  add     rsp, 48h
0x14000481e  pop     r15
0x140004820  pop     r14
0x140004822  pop     rdi
0x140004823  pop     rsi
0x140004824  pop     rbx
0x140004825  pop     rbp
0x140004826  retn
```
