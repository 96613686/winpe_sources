# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::UnregisterForAdministration(void *,int *)

- ea: `0x180014d10`
- end: `0x180014eac`
- name: `?UnregisterForAdministration@?$produce@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@UIWindowsUpdateAdministratorStatics@3456@@impl@winrt@@UEAAHPEAXPEAH@Z`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int64, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180011410`
- `0x180014d10`
- `0x180014eb4`
- `0x180016024`
- `0x18001d50c`
- `0x180024604`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014d64`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014e6d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014d64`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014e6d`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::UnregisterForAdministration(
        __int64 a1,
        __int64 a2,
        int *a3)
{
  __int64 v5; // rdx
  int *v6; // rdx
  unsigned int v7; // eax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rbx
  IUnknown *v11; // rax
  unsigned int v12; // eax
  unsigned int *v13; // rax
  __int64 v14; // rdx
  unsigned int *v15; // rax
  __int64 v16; // r8
  _BYTE v17[40]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF
  IUnknown *pProxy; // [rsp+88h] [rbp+20h] BYREF

  v18 = a1;
  try
  {
    wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>((LPVOID *)&pProxy);
    if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
    {
      v10 = winrt::impl::slim_source_location::current(v17, v5);
      v11 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
      v12 = CoSetProxyBlanket(v11, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
      v13 = (unsigned int *)msl::safeint3::SafeIntException::SafeIntException(&v18, v12);
      winrt::throw_hresult(*v13, v10);
    }
    if ( a2 )
      v6 = *(int **)(a2 + 16);
    else
      v6 = &dword_18002EB94;
    v7 = ((__int64 (__fastcall *)(IUnknown *, int *))pProxy->lpVtbl[1].AddRef)(pProxy, v6);
    if ( (v7 & 0x80000000) == 0 )
    {
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl->Release)(pProxy, v7);
      v8 = 0;
    }
    else if ( v7 == -2145083106 )
    {
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl->Release)(pProxy, v7);
      v8 = 1;
    }
    else
    {
      if ( v7 != -2145083105 )
      {
        winrt::impl::slim_source_location::current(v17, v7);
        v15 = (unsigned int *)msl::safeint3::SafeIntException::SafeIntException(&v18, v14);
        winrt::throw_hresult(*v15, v16);
      }
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      v8 = 2;
    }
    *a3 = v8;
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
0x180014d10  mov     rax, rsp
0x180014d13  mov     [rax+10h], rbx
0x180014d17  mov     [rax+8], rcx
0x180014d1b  push    rdi
0x180014d1c  sub     rsp, 60h
0x180014d20  mov     rdi, r8
0x180014d23  mov     rbx, rdx
0x180014d26  lea     rcx, [rax+20h]
0x180014d2a  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x180014d2f  nop
0x180014d30  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x180014d38  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x180014d41  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180014d49  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x180014d51  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180014d55  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180014d59  or      edx, r8d; dwAuthnSvc
0x180014d5c  mov     rcx, [rsp+68h+pProxy]; pProxy
0x180014d64  call    cs:__imp_CoSetProxyBlanket
0x180014d6a  test    eax, eax
0x180014d6c  js      loc_180014E24
0x180014d72  mov     rcx, [rsp+68h+pProxy]
0x180014d7a  mov     rax, [rcx]
0x180014d7d  test    rbx, rbx
0x180014d80  jz      short loc_180014D88
0x180014d82  mov     rdx, [rbx+10h]
0x180014d86  jmp     short loc_180014D8F
0x180014d88  lea     rdx, dword_18002EB94
0x180014d8f  mov     rax, [rax+20h]
0x180014d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d98  mov     edx, eax
0x180014d9a  test    eax, eax
0x180014d9c  jns     short loc_180014DF3
0x180014d9e  cmp     eax, 8024A11Eh
0x180014da3  jnz     short loc_180014DC6
0x180014da5  mov     rcx, [rsp+68h+pProxy]
0x180014dad  test    rcx, rcx
0x180014db0  jz      short loc_180014DBF
0x180014db2  mov     rax, [rcx]
0x180014db5  mov     rax, [rax+10h]
0x180014db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dbe  nop
0x180014dbf  mov     eax, 1
0x180014dc4  jmp     short loc_180014E0F
0x180014dc6  cmp     edx, 8024A11Fh
0x180014dcc  jnz     loc_180014E89
0x180014dd2  mov     rcx, [rsp+68h+pProxy]
0x180014dda  test    rcx, rcx
0x180014ddd  jz      short loc_180014DEC
0x180014ddf  mov     rax, [rcx]
0x180014de2  mov     rax, [rax+10h]
0x180014de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014deb  nop
0x180014dec  mov     eax, 2
0x180014df1  jmp     short loc_180014E0F
0x180014df3  mov     rcx, [rsp+68h+pProxy]
0x180014dfb  test    rcx, rcx
0x180014dfe  jz      short loc_180014E0D
0x180014e00  mov     rax, [rcx]
0x180014e03  mov     rax, [rax+10h]
0x180014e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e0c  nop
0x180014e0d  xor     eax, eax
0x180014e0f  mov     [rdi], eax
0x180014e11  xor     eax, eax
0x180014e13  jmp     short loc_180014E19
0x180014e15  mov     eax, dword ptr [rsp+68h+arg_0]
0x180014e19  mov     rbx, [rsp+68h+arg_8]
0x180014e1e  add     rsp, 60h
0x180014e22  pop     rdi
0x180014e23  retn
0x180014e24  lea     rcx, [rsp+68h+var_28]
0x180014e29  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180014e2e  mov     rbx, rax
0x180014e31  lea     rcx, [rsp+68h+pProxy]
0x180014e39  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x180014e3e  mov     rcx, rax; pProxy
0x180014e41  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x180014e49  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x180014e52  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180014e5a  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x180014e62  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180014e66  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180014e6a  or      edx, r8d; dwAuthnSvc
0x180014e6d  call    cs:__imp_CoSetProxyBlanket
0x180014e73  mov     edx, eax
0x180014e75  lea     rcx, [rsp+68h+arg_0]
0x180014e7a  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x180014e7f  mov     rdx, rbx
0x180014e82  mov     ecx, [rax]
0x180014e84  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180014e89  lea     rcx, [rsp+68h+var_28]
0x180014e8e  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180014e93  mov     r8, rax
0x180014e96  lea     rcx, [rsp+68h+arg_0]
0x180014e9b  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x180014ea0  mov     rdx, r8
0x180014ea3  mov     ecx, [rax]
0x180014ea5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
