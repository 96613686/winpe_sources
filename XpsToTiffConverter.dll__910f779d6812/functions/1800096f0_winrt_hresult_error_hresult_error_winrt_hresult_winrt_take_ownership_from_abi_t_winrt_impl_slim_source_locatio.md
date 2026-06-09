# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x1800096f0`
- end: `0x180009999`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `14`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009628`
- `0x180009650`
- `0x180009678`
- `0x1800096a0`
- `0x1800096c8`
- `0x1800099a0`
- `0x1800099c8`
- `0x1800099f0`
- `0x180009a18`
- `0x180009a40`
- `0x180009a68`
- `0x180009a90`
- `0x180009ab8`
- `0x18000b3ac`

## callees

- `0x180002150`
- `0x180002174`
- `0x180002195`
- `0x1800021a1`
- `0x1800021b9`
- `0x1800021c5`
- `0x1800030c0`
- `0x180008b38`
- `0x1800096f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180009992`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180009992`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000985b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000985b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  __int64 *v7; // rsi
  BSTR v8; // rbx
  __int64 v9; // r15
  __int64 v10; // rbx
  void (__fastcall *v11)(__int64, __int64); // rdi
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // ebx
  const unsigned __int16 *v15; // r12
  OLECHAR *i; // r15
  __int64 v17; // rdi
  int v18; // eax
  HANDLE ProcessHeap; // rax
  IErrorInfo *v21; // [rsp+30h] [rbp-38h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-30h] BYREF
  BSTR v23; // [rsp+40h] [rbp-28h] BYREF
  __int64 v24; // [rsp+48h] [rbp-20h] BYREF
  __int64 v25[3]; // [rsp+50h] [rbp-18h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+40h]
  IErrorInfo *pperrinfo; // [rsp+B0h] [rbp+48h] BYREF

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
    v23 = pbstr;
  }
  else
  {
    v23 = 0;
    v8 = 0;
  }
  if ( v7 == (__int64 *)&v23 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v23);
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
      v25[0] = (__int64)pbstr;
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v25);
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
        v15 = pbstr;
        for ( i = &pbstr[v14 - 1]; v14; --v14 )
        {
          if ( !(unsigned int)_o_iswspace(*i) )
            break;
          --i;
        }
        winrt::hstring::hstring((winrt::hstring *)v25, v15, v14);
        v13 = (volatile signed __int32 *)v25[0];
      }
    }
    else
    {
      v13 = 0;
    }
    RoOriginateLanguageException_0(a2, v13, 0);
    if ( winrt_throw_hresult_handler )
      winrt_throw_hresult_handler(*a4, *((_QWORD *)a4 + 1), *((_QWORD *)a4 + 2), retaddr, a2);
    v21 = 0;
    GetErrorInfo_0(0, &v21);
    if ( v21 )
    {
      v25[0] = 0;
      ((void (__fastcall *)(IErrorInfo *, __int64 *, __int64 *))v21->lpVtbl->QueryInterface)(
        v21,
        winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
        v25);
      v17 = v25[0];
      v24 = v25[0];
    }
    else
    {
      v24 = 0;
      v17 = 0;
    }
    if ( v7 == &v24 )
    {
      if ( v17 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
    }
    else
    {
      if ( *v7 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
      *v7 = v17;
    }
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v21);
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
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x1800096f0  push    rbp
0x1800096f2  push    rbx
0x1800096f3  push    rsi
0x1800096f4  push    rdi
0x1800096f5  push    r12
0x1800096f7  push    r13
0x1800096f9  push    r14
0x1800096fb  push    r15
0x1800096fd  mov     rbp, rsp
0x180009700  sub     rsp, 68h
0x180009704  mov     r13, r9
0x180009707  mov     edi, edx
0x180009709  mov     r14, rcx
0x18000970c  xor     r12d, r12d
0x18000970f  mov     [rcx], r12
0x180009712  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180009719  mov     [rcx+0Ch], edx
0x18000971c  lea     rsi, [rcx+10h]
0x180009720  mov     [rsi], r12
0x180009723  mov     [rbp+pperrinfo], r12
0x180009727  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000972b  xor     ecx, ecx; dwReserved
0x18000972d  call    GetErrorInfo_0
0x180009732  mov     rcx, [rbp+pperrinfo]
0x180009736  test    rcx, rcx
0x180009739  jnz     short loc_180009744
0x18000973b  mov     [rbp+var_28], r12
0x18000973f  mov     ebx, r12d
0x180009742  jmp     short loc_180009766
0x180009744  mov     [rbp+pbstr], r12
0x180009748  mov     rax, [rcx]
0x18000974b  lea     r8, [rbp+pbstr]
0x18000974f  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180009756  mov     rax, [rax]
0x180009759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000975e  mov     rbx, [rbp+pbstr]
0x180009762  mov     [rbp+var_28], rbx
0x180009766  lea     rax, [rbp+var_28]
0x18000976a  cmp     rsi, rax
0x18000976d  jz      short loc_180009784
0x18000976f  cmp     [rsi], r12
0x180009772  jz      short loc_18000977C
0x180009774  mov     rcx, rsi
0x180009777  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000977c  mov     [rsi], rbx
0x18000977f  mov     r15, rbx
0x180009782  jmp     short loc_180009795
0x180009784  mov     r15, [rsi]
0x180009787  test    rbx, rbx
0x18000978a  jz      short loc_180009795
0x18000978c  lea     rcx, [rbp+var_28]
0x180009790  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009795  test    r15, r15
0x180009798  jz      short loc_180009815
0x18000979a  mov     rbx, [rsi]
0x18000979d  mov     rax, [rbx]
0x1800097a0  mov     rdi, [rax+20h]
0x1800097a4  mov     rcx, [r14]; bstrString
0x1800097a7  test    rcx, rcx
0x1800097aa  jz      short loc_1800097B4
0x1800097ac  call    WINRT_IMPL_SysFreeString
0x1800097b1  mov     [r14], r12
0x1800097b4  mov     rdx, r14
0x1800097b7  mov     rcx, rbx
0x1800097ba  mov     rax, rdi
0x1800097bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097c2  mov     rcx, [rsi]
0x1800097c5  test    rcx, rcx
0x1800097c8  jz      loc_18000996B
0x1800097ce  mov     [rbp+pbstr], r12
0x1800097d2  mov     rax, [rcx]
0x1800097d5  lea     r8, [rbp+pbstr]
0x1800097d9  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x1800097e0  mov     rax, [rax]
0x1800097e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097e8  mov     rcx, [rbp+pbstr]
0x1800097ec  mov     [rbp+var_18], rcx
0x1800097f0  test    rcx, rcx
0x1800097f3  jz      loc_18000996B
0x1800097f9  mov     rax, [rcx]
0x1800097fc  xor     edx, edx
0x1800097fe  mov     rax, [rax+28h]
0x180009802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009807  lea     rcx, [rbp+var_18]
0x18000980b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009810  jmp     loc_18000996B
0x180009815  mov     [rbp+pbstr], r12
0x180009819  mov     rcx, [rbp+pperrinfo]
0x18000981d  test    rcx, rcx
0x180009820  jz      short loc_180009887
0x180009822  mov     rax, [rcx]
0x180009825  lea     rdx, [rbp+pbstr]
0x180009829  mov     rax, [rax+28h]
0x18000982d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009832  mov     rbx, r12
0x180009835  mov     rcx, [rbp+pbstr]; pbstr
0x180009839  test    rcx, rcx
0x18000983c  jz      short loc_18000988A
0x18000983e  call    SysStringLen_0
0x180009843  mov     ebx, eax
0x180009845  mov     r12, [rbp+pbstr]
0x180009849  mov     r15d, eax
0x18000984c  dec     r15
0x18000984f  lea     r15, [r12+r15*2]
0x180009853  test    eax, eax
0x180009855  jz      short loc_18000986E
0x180009857  movzx   ecx, word ptr [r15]
0x18000985b  call    cs:__imp__o_iswspace
0x180009861  test    eax, eax
0x180009863  jz      short loc_18000986E
0x180009865  sub     r15, 2
0x180009869  add     ebx, 0FFFFFFFFh
0x18000986c  jnz     short loc_180009857
0x18000986e  mov     r8d, ebx; unsigned int
0x180009871  mov     rdx, r12; unsigned __int16 *
0x180009874  lea     rcx, [rbp+var_18]; this
0x180009878  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18000987d  nop
0x18000987e  mov     rbx, [rbp+var_18]
0x180009882  xor     r12d, r12d
0x180009885  jmp     short loc_18000988A
0x180009887  mov     rbx, r12
0x18000988a  xor     r8d, r8d
0x18000988d  mov     rdx, rbx
0x180009890  mov     ecx, edi
0x180009892  call    RoOriginateLanguageException_0
0x180009897  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x18000989e  test    rax, rax
0x1800098a1  jz      short loc_1800098BC
0x1800098a3  mov     r9, [rbp+40h]
0x1800098a7  mov     [rsp+68h+var_48], edi
0x1800098ab  mov     r8, [r13+10h]
0x1800098af  mov     rdx, [r13+8]
0x1800098b3  mov     ecx, [r13+0]
0x1800098b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098bc  mov     [rbp+var_38], r12
0x1800098c0  lea     rdx, [rbp+var_38]; pperrinfo
0x1800098c4  xor     ecx, ecx; dwReserved
0x1800098c6  call    GetErrorInfo_0
0x1800098cb  mov     rcx, [rbp+var_38]
0x1800098cf  test    rcx, rcx
0x1800098d2  jnz     short loc_1800098DD
0x1800098d4  mov     [rbp+var_20], r12
0x1800098d8  mov     rdi, r12
0x1800098db  jmp     short loc_1800098FF
0x1800098dd  mov     [rbp+var_18], r12
0x1800098e1  mov     rax, [rcx]
0x1800098e4  lea     r8, [rbp+var_18]
0x1800098e8  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1800098ef  mov     rax, [rax]
0x1800098f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f7  mov     rdi, [rbp+var_18]
0x1800098fb  mov     [rbp+var_20], rdi
0x1800098ff  lea     rax, [rbp+var_20]
0x180009903  cmp     rsi, rax
0x180009906  jz      short loc_18000991A
0x180009908  cmp     [rsi], r12
0x18000990b  jz      short loc_180009915
0x18000990d  mov     rcx, rsi
0x180009910  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009915  mov     [rsi], rdi
0x180009918  jmp     short loc_180009928
0x18000991a  test    rdi, rdi
0x18000991d  jz      short loc_180009928
0x18000991f  lea     rcx, [rbp+var_20]
0x180009923  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009928  cmp     [rbp+var_38], r12
0x18000992c  jz      short loc_180009938
0x18000992e  lea     rcx, [rbp+var_38]
0x180009932  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009937  nop
0x180009938  test    rbx, rbx
0x18000993b  jz      short loc_18000995D
0x18000993d  or      eax, 0FFFFFFFFh
0x180009940  lock xadd [rbx+18h], eax
0x180009945  sub     eax, 1
0x180009948  jnz     short loc_18000998E
0x18000994a  nop
0x18000994b  call    WINRT_IMPL_GetProcessHeap
0x180009950  mov     rcx, rax; hHeap
0x180009953  mov     r8, rbx; lpMem
0x180009956  xor     edx, edx; dwFlags
0x180009958  call    WINRT_IMPL_HeapFree
0x18000995d  mov     rcx, [rbp+pbstr]; bstrString
0x180009961  test    rcx, rcx
0x180009964  jz      short loc_18000996B
0x180009966  call    WINRT_IMPL_SysFreeString
0x18000996b  cmp     [rbp+pperrinfo], r12
0x18000996f  jz      short loc_18000997A
0x180009971  lea     rcx, [rbp+pperrinfo]
0x180009975  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000997a  mov     rax, r14
0x18000997d  add     rsp, 68h
0x180009981  pop     r15
0x180009983  pop     r14
0x180009985  pop     r13
0x180009987  pop     r12
0x180009989  pop     rdi
0x18000998a  pop     rsi
0x18000998b  pop     rbx
0x18000998c  pop     rbp
0x18000998d  retn
0x18000998e  test    eax, eax
0x180009990  jns     short loc_18000995D
0x180009992  call    cs:__imp_abort
```
