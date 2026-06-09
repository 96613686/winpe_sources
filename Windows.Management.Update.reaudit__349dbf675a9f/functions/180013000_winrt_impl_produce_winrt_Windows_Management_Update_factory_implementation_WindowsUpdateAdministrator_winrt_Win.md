# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::CancelRestartRequest(void *)

- ea: `0x180013000`
- end: `0x180013165`
- name: `?CancelRestartRequest@?$produce@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@UIWindowsUpdateAdministratorStatics@3456@@impl@winrt@@UEAAHPEAX@Z`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180011fa8`
- `0x180013000`
- `0x180015ac0`
- `0x180016c20`
- `0x18001dcb8`
- `0x18001e7a4`
- `0x180025980`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180013048`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800130ef`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180013048`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800130ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::CancelRestartRequest(
        __int64 a1,
        __int64 a2)
{
  const unsigned __int16 *v3; // rdx
  __int64 result; // rax
  unsigned int *v5; // rbx
  IUnknown *v6; // rax
  HRESULT v7; // eax
  unsigned int *v8; // rax
  __int64 v9; // r8
  unsigned int *v10; // rbx
  const unsigned __int16 *v11; // rax
  __int64 (__fastcall *v12)(__int64, const unsigned __int16 *); // r8
  __int64 v13; // r9
  int v14; // eax
  unsigned int *v15; // rax
  __int64 v16; // r8
  _BYTE v17[40]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF
  __int64 v19; // [rsp+78h] [rbp+10h] BYREF
  IUnknown *pProxy; // [rsp+80h] [rbp+18h] BYREF

  v19 = a2;
  v18 = a1;
  try
  {
    wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>((LPVOID *)&pProxy);
    if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
    {
      v5 = (unsigned int *)winrt::impl::slim_source_location::current(v17);
      v6 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
      v7 = CoSetProxyBlanket(v6, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
      v8 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v18, v7);
      winrt::throw_hresult(*v8, v5, v9);
    }
    if ( a2 )
      v3 = *(const unsigned __int16 **)(a2 + 16);
    else
      v3 = &dword_180030C44;
    if ( ((int (__fastcall *)(IUnknown *, const unsigned __int16 *))pProxy->lpVtbl[2].Release)(pProxy, v3) < 0 )
    {
      v10 = (unsigned int *)winrt::impl::slim_source_location::current(v17);
      wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
      v11 = winrt::hstring::c_str((winrt::hstring *)&v19);
      v14 = v12(v13, v11);
      v15 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v18, v14);
      winrt::throw_hresult(*v15, v10, v16);
    }
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v18);
  }
  return result;
}

```

## disassembly

```asm
0x180013000  mov     rax, rsp
0x180013003  mov     [rax+10h], rdx
0x180013007  mov     [rax+8], rcx
0x18001300b  push    rbx
0x18001300c  sub     rsp, 60h
0x180013010  mov     rbx, rdx
0x180013013  lea     rcx, [rax+18h]
0x180013017  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x18001301c  nop
0x18001301d  and     [rsp+68h+var_30], 0
0x180013022  and     [rsp+68h+var_38], 0
0x180013028  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180013030  and     [rsp+68h+var_48], 0
0x180013035  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180013039  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18001303d  or      edx, r8d; dwAuthnSvc
0x180013040  mov     rcx, [rsp+68h+pProxy]; pProxy
0x180013048  call    cs:__imp_CoSetProxyBlanket
0x18001304f  nop     dword ptr [rax+rax+00h]
0x180013054  test    eax, eax
0x180013056  js      short loc_1800130AF
0x180013058  mov     rcx, [rsp+68h+pProxy]
0x180013060  mov     rax, [rcx]
0x180013063  test    rbx, rbx
0x180013066  jz      short loc_18001306E
0x180013068  mov     rdx, [rbx+10h]
0x18001306c  jmp     short loc_180013075
0x18001306e  lea     rdx, dword_180030C44
0x180013075  mov     rax, [rax+40h]
0x180013079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001307e  test    eax, eax
0x180013080  js      loc_180013111
0x180013086  mov     rcx, [rsp+68h+pProxy]
0x18001308e  test    rcx, rcx
0x180013091  jz      short loc_1800130A0
0x180013093  mov     rax, [rcx]
0x180013096  mov     rax, [rax+10h]
0x18001309a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001309f  nop
0x1800130a0  xor     eax, eax
0x1800130a2  jmp     short loc_1800130A8
0x1800130a4  mov     eax, dword ptr [rsp+68h+arg_0]
0x1800130a8  add     rsp, 60h
0x1800130ac  pop     rbx
0x1800130ad  retn
0x1800130af  lea     rcx, [rsp+68h+var_28]
0x1800130b4  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800130b9  mov     rbx, rax
0x1800130bc  lea     rcx, [rsp+68h+pProxy]
0x1800130c4  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x1800130c9  mov     rcx, rax; pProxy
0x1800130cc  and     [rsp+68h+var_30], 0
0x1800130d1  and     [rsp+68h+var_38], 0
0x1800130d7  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x1800130df  and     [rsp+68h+var_48], 0
0x1800130e4  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800130e8  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1800130ec  or      edx, r8d; dwAuthnSvc
0x1800130ef  call    cs:__imp_CoSetProxyBlanket
0x1800130f6  nop     dword ptr [rax+rax+00h]
0x1800130fb  mov     edx, eax; int
0x1800130fd  lea     rcx, [rsp+68h+arg_0]; this
0x180013102  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180013107  mov     rdx, rbx
0x18001310a  mov     ecx, [rax]
0x18001310c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180013111  lea     rcx, [rsp+68h+var_28]
0x180013116  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001311b  mov     rbx, rax
0x18001311e  lea     rcx, [rsp+68h+pProxy]
0x180013126  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x18001312b  mov     r9, rax
0x18001312e  mov     rcx, [rax]
0x180013131  mov     r8, [rcx+40h]
0x180013135  lea     rcx, [rsp+68h+arg_8]; this
0x18001313a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18001313f  mov     rdx, rax
0x180013142  mov     rcx, r9
0x180013145  mov     rax, r8
0x180013148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001314d  mov     edx, eax; int
0x18001314f  lea     rcx, [rsp+68h+arg_0]; this
0x180013154  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180013159  mov     rdx, rbx
0x18001315c  mov     ecx, [rax]
0x18001315e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
