# winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::UnregisterForAdministration(void *,int *)

- ea: `0x180015920`
- end: `0x180015ab9`
- name: `?UnregisterForAdministration@?$produce@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@UIWindowsUpdateAdministratorStatics@3456@@impl@winrt@@UEAAHPEAXPEAH@Z`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180011fa8`
- `0x180015920`
- `0x180015ac0`
- `0x180016c20`
- `0x18001e7a4`
- `0x180025980`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001596e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180015a6e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001596e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180015a6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::IWindowsUpdateAdministratorStatics>::UnregisterForAdministration(
        __int64 a1,
        __int64 a2,
        int *a3)
{
  int v5; // edi
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  __int64 result; // rax
  unsigned int *v9; // rbx
  IUnknown *v10; // rax
  HRESULT v11; // eax
  unsigned int *v12; // rax
  __int64 v13; // r8
  int v14; // edx
  unsigned int *v15; // rax
  unsigned int *v16; // r8
  IUnknown *pProxy; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v18[24]; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v19[32]; // [rsp+60h] [rbp-28h] BYREF
  __int64 v20; // [rsp+90h] [rbp+8h] BYREF
  char v21; // [rsp+A8h] [rbp+20h] BYREF

  v20 = a1;
  try
  {
    wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>((LPVOID *)&pProxy);
    v5 = 0;
    if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
    {
      v9 = (unsigned int *)winrt::impl::slim_source_location::current(v18);
      v10 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
      v11 = CoSetProxyBlanket(v10, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
      v12 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v20, v11);
      winrt::throw_hresult(*v12, v9, v13);
    }
    if ( a2 )
      v6 = *(const unsigned __int16 **)(a2 + 16);
    else
      v6 = &dword_180030C44;
    v7 = ((__int64 (__fastcall *)(IUnknown *, const unsigned __int16 *))pProxy->lpVtbl[1].AddRef)(pProxy, v6);
    if ( v7 >= 0 )
    {
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl->Release)(pProxy, (unsigned int)v7);
    }
    else if ( v7 == -2145083106 )
    {
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl->Release)(pProxy, (unsigned int)v7);
      v5 = 1;
    }
    else
    {
      if ( v7 != -2145083105 )
      {
        winrt::impl::slim_source_location::current(v19);
        v15 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v21, v14);
        winrt::throw_hresult(*v15, v16, (__int64)v16);
      }
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      v5 = 2;
    }
    *a3 = v5;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v20);
  }
  return result;
}

```

## disassembly

```asm
0x180015920  mov     rax, rsp
0x180015923  mov     [rax+10h], rbx
0x180015927  mov     [rax+18h], rsi
0x18001592b  mov     [rax+8], rcx
0x18001592f  push    rdi
0x180015930  sub     rsp, 80h
0x180015937  mov     rsi, r8
0x18001593a  mov     rbx, rdx
0x18001593d  lea     rcx, [rax-48h]
0x180015941  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x180015946  nop
0x180015947  xor     edi, edi
0x180015949  mov     [rsp+88h+dwCapabilities], edi; dwCapabilities
0x18001594d  mov     [rsp+88h+pAuthInfo], rdi; pAuthInfo
0x180015952  mov     [rsp+88h+dwImpLevel], 3; dwImpLevel
0x18001595a  mov     [rsp+88h+dwAuthnLevel], edi; dwAuthnLevel
0x18001595e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180015962  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180015966  or      edx, r8d; dwAuthnSvc
0x180015969  mov     rcx, [rsp+88h+pProxy]; pProxy
0x18001596e  call    cs:__imp_CoSetProxyBlanket
0x180015975  nop     dword ptr [rax+rax+00h]
0x18001597a  test    eax, eax
0x18001597c  js      loc_180015A34
0x180015982  mov     rcx, [rsp+88h+pProxy]
0x180015987  mov     rax, [rcx]
0x18001598a  test    rbx, rbx
0x18001598d  jz      short loc_180015995
0x18001598f  mov     rdx, [rbx+10h]
0x180015993  jmp     short loc_18001599C
0x180015995  lea     rdx, dword_180030C44
0x18001599c  mov     rax, [rax+20h]
0x1800159a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159a5  mov     edx, eax
0x1800159a7  test    eax, eax
0x1800159a9  jns     short loc_1800159FA
0x1800159ab  cmp     eax, 8024A11Eh
0x1800159b0  jnz     short loc_1800159D0
0x1800159b2  mov     rcx, [rsp+88h+pProxy]
0x1800159b7  test    rcx, rcx
0x1800159ba  jz      short loc_1800159C9
0x1800159bc  mov     rax, [rcx]
0x1800159bf  mov     rax, [rax+10h]
0x1800159c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c8  nop
0x1800159c9  mov     edi, 1
0x1800159ce  jmp     short loc_180015A11
0x1800159d0  cmp     edx, 8024A11Fh
0x1800159d6  jnz     loc_180015A93
0x1800159dc  mov     rcx, [rsp+88h+pProxy]
0x1800159e1  test    rcx, rcx
0x1800159e4  jz      short loc_1800159F3
0x1800159e6  mov     rax, [rcx]
0x1800159e9  mov     rax, [rax+10h]
0x1800159ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159f2  nop
0x1800159f3  mov     edi, 2
0x1800159f8  jmp     short loc_180015A11
0x1800159fa  mov     rcx, [rsp+88h+pProxy]
0x1800159ff  test    rcx, rcx
0x180015a02  jz      short loc_180015A11
0x180015a04  mov     rax, [rcx]
0x180015a07  mov     rax, [rax+10h]
0x180015a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a10  nop
0x180015a11  mov     [rsi], edi
0x180015a13  xor     eax, eax
0x180015a15  jmp     short loc_180015A1E
0x180015a17  mov     eax, dword ptr [rsp+88h+arg_0]
0x180015a1e  lea     r11, [rsp+88h+var_8]
0x180015a26  mov     rbx, [r11+18h]
0x180015a2a  mov     rsi, [r11+20h]
0x180015a2e  mov     rsp, r11
0x180015a31  pop     rdi
0x180015a32  retn
0x180015a34  lea     rcx, [rsp+88h+var_40]
0x180015a39  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180015a3e  mov     rbx, rax
0x180015a41  lea     rcx, [rsp+88h+pProxy]
0x180015a46  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x180015a4b  mov     rcx, rax; pProxy
0x180015a4e  mov     [rsp+88h+dwCapabilities], edi; dwCapabilities
0x180015a52  mov     [rsp+88h+pAuthInfo], rdi; pAuthInfo
0x180015a57  mov     [rsp+88h+dwImpLevel], 3; dwImpLevel
0x180015a5f  mov     [rsp+88h+dwAuthnLevel], edi; dwAuthnLevel
0x180015a63  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180015a67  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180015a6b  or      edx, r8d; dwAuthnSvc
0x180015a6e  call    cs:__imp_CoSetProxyBlanket
0x180015a75  nop     dword ptr [rax+rax+00h]
0x180015a7a  mov     edx, eax; int
0x180015a7c  lea     rcx, [rsp+88h+arg_0]; this
0x180015a84  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180015a89  mov     rdx, rbx
0x180015a8c  mov     ecx, [rax]
0x180015a8e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180015a93  lea     rcx, [rsp+88h+var_28]
0x180015a98  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180015a9d  mov     r8, rax
0x180015aa0  lea     rcx, [rsp+88h+arg_18]; this
0x180015aa8  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180015aad  mov     rdx, r8
0x180015ab0  mov     ecx, [rax]
0x180015ab2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
