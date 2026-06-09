# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::CancelRestartRequest(void *)

- ea: `0x180012430`
- end: `0x180012597`
- name: `?CancelRestartRequest@?$produce@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@UIWindowsUpdateAdministratorStatics@3456@@impl@winrt@@UEAAHPEAX@Z`
- size: `359`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180011410`
- `0x180012430`
- `0x180014eb4`
- `0x180016024`
- `0x18001c9f0`
- `0x18001d50c`
- `0x180024604`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180012481`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001252a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180012481`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001252a`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::CancelRestartRequest(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdx
  int *v4; // rdx
  __int64 v5; // rdx
  __int64 result; // rax
  __int64 v7; // rbx
  IUnknown *v8; // rax
  unsigned int v9; // eax
  unsigned int *v10; // rax
  __int64 v11; // rbx
  const unsigned __int16 *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // eax
  unsigned int *v16; // rax
  _BYTE v17[40]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF
  __int64 v19; // [rsp+78h] [rbp+10h] BYREF
  IUnknown *pProxy; // [rsp+80h] [rbp+18h] BYREF

  v19 = a2;
  v18 = a1;
  try
  {
    wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(&pProxy);
    if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
    {
      v7 = winrt::impl::slim_source_location::current(v17, v3);
      v8 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
      v9 = CoSetProxyBlanket(v8, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
      v10 = (unsigned int *)msl::safeint3::SafeIntException::SafeIntException(&v18, v9);
      winrt::throw_hresult(*v10, v7);
    }
    if ( a2 )
      v4 = *(int **)(a2 + 16);
    else
      v4 = &dword_18002EB94;
    if ( ((int (__fastcall *)(IUnknown *, int *))pProxy->lpVtbl[2].Release)(pProxy, v4) < 0 )
    {
      v11 = winrt::impl::slim_source_location::current(v17, v5);
      wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
      v12 = winrt::hstring::c_str((winrt::hstring *)&v19);
      v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(v13 + 64))(v14, v12);
      v16 = (unsigned int *)msl::safeint3::SafeIntException::SafeIntException(&v18, v15);
      winrt::throw_hresult(*v16, v11);
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
0x180012430  mov     rax, rsp
0x180012433  mov     [rax+10h], rdx
0x180012437  mov     [rax+8], rcx
0x18001243b  push    rbx
0x18001243c  sub     rsp, 60h
0x180012440  mov     rbx, rdx
0x180012443  lea     rcx, [rax+18h]
0x180012447  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x18001244c  nop
0x18001244d  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x180012455  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18001245e  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180012466  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x18001246e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180012472  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180012476  or      edx, r8d; dwAuthnSvc
0x180012479  mov     rcx, [rsp+68h+pProxy]; pProxy
0x180012481  call    cs:__imp_CoSetProxyBlanket
0x180012487  test    eax, eax
0x180012489  js      short loc_1800124E1
0x18001248b  mov     rcx, [rsp+68h+pProxy]
0x180012493  mov     rax, [rcx]
0x180012496  test    rbx, rbx
0x180012499  jz      short loc_1800124A1
0x18001249b  mov     rdx, [rbx+10h]
0x18001249f  jmp     short loc_1800124A8
0x1800124a1  lea     rdx, dword_18002EB94
0x1800124a8  mov     rax, [rax+40h]
0x1800124ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b1  test    eax, eax
0x1800124b3  js      loc_180012546
0x1800124b9  mov     rcx, [rsp+68h+pProxy]
0x1800124c1  test    rcx, rcx
0x1800124c4  jz      short loc_1800124D3
0x1800124c6  mov     rax, [rcx]
0x1800124c9  mov     rax, [rax+10h]
0x1800124cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124d2  nop
0x1800124d3  xor     eax, eax
0x1800124d5  jmp     short loc_1800124DB
0x1800124d7  mov     eax, dword ptr [rsp+68h+arg_0]
0x1800124db  add     rsp, 60h
0x1800124df  pop     rbx
0x1800124e0  retn
0x1800124e1  lea     rcx, [rsp+68h+var_28]
0x1800124e6  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800124eb  mov     rbx, rax
0x1800124ee  lea     rcx, [rsp+68h+pProxy]
0x1800124f6  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x1800124fb  mov     rcx, rax; pProxy
0x1800124fe  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x180012506  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18001250f  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180012517  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x18001251f  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180012523  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180012527  or      edx, r8d; dwAuthnSvc
0x18001252a  call    cs:__imp_CoSetProxyBlanket
0x180012530  mov     edx, eax
0x180012532  lea     rcx, [rsp+68h+arg_0]
0x180012537  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x18001253c  mov     rdx, rbx
0x18001253f  mov     ecx, [rax]
0x180012541  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180012546  lea     rcx, [rsp+68h+var_28]
0x18001254b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012550  mov     rbx, rax
0x180012553  lea     rcx, [rsp+68h+pProxy]
0x18001255b  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x180012560  mov     r9, rax
0x180012563  mov     r8, [rax]
0x180012566  lea     rcx, [rsp+68h+arg_8]; this
0x18001256b  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180012570  mov     rdx, rax
0x180012573  mov     rcx, r9
0x180012576  mov     rax, [r8+40h]
0x18001257a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001257f  mov     edx, eax
0x180012581  lea     rcx, [rsp+68h+arg_0]
0x180012586  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x18001258b  mov     rdx, rbx
0x18001258e  mov     ecx, [rax]
0x180012590  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
