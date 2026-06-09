# winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministrator(winrt::hstring const &)

- ea: `0x180024ca8`
- end: `0x180024e5c`
- name: `?GetRegisteredAdministrator@WindowsUpdateAdministrator@implementation@Update@Management@Windows@winrt@@SA?AUWindowsUpdateGetAdministratorResult@3456@AEBUhstring@6@@Z`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013dc0`

## callees

- `0x180011410`
- `0x180014eb4`
- `0x180016024`
- `0x180016fe4`
- `0x18001d50c`
- `0x180024604`
- `0x180024674`
- `0x180024ca8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024d91`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024e20`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024d91`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024e20`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministrator(
        __int64 *a1,
        __int64 a2)
{
  int *v4; // rdx
  int v5; // eax
  unsigned int *v7; // rbx
  IUnknown *v8; // rax
  HRESULT v9; // eax
  unsigned int *v10; // rax
  __int64 v11; // r8
  int v12; // edx
  unsigned int *v13; // rax
  unsigned int *v14; // r8
  _BYTE v15[24]; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v16; // [rsp+88h] [rbp+28h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp+30h] BYREF
  LPVOID v18; // [rsp+98h] [rbp+38h] BYREF

  wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(&v18);
  pProxy = 0;
  if ( *(_QWORD *)a2 )
    v4 = *(int **)(*(_QWORD *)a2 + 16LL);
  else
    v4 = &dword_18002EB94;
  v5 = (*(__int64 (__fastcall **)(LPVOID, int *, __int64 *, IUnknown **))(*(_QWORD *)v18 + 48LL))(
         v18,
         v4,
         winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>,
         &pProxy);
  if ( v5 >= 0 )
  {
    if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
    {
      v7 = (unsigned int *)winrt::impl::slim_source_location::current((__int64)v15);
      v8 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->((__int64)&pProxy);
      v9 = CoSetProxyBlanket(v8, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
      v10 = msl::safeint3::SafeIntException::SafeIntException(&v16, v9);
      winrt::throw_hresult(*v10, v7, v11);
    }
    v16 = 0;
    winrt::make<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateAdministrator &,enum winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus>(
      a1,
      (__int64 **)&pProxy,
      &v16);
    if ( pProxy )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pProxy);
  }
  else if ( v5 == -2145083106 )
  {
    v16 = 1;
    winrt::make<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateAdministrator &,enum winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus>(
      a1,
      (__int64 **)&pProxy,
      &v16);
    if ( pProxy )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pProxy);
  }
  else
  {
    if ( v5 != -2145083105 )
    {
      winrt::impl::slim_source_location::current((__int64)v15);
      v13 = msl::safeint3::SafeIntException::SafeIntException(&v16, v12);
      winrt::throw_hresult(*v13, v14, (__int64)v14);
    }
    v16 = 2;
    winrt::make<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateAdministrator &,enum winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus>(
      a1,
      (__int64 **)&pProxy,
      &v16);
    if ( pProxy )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pProxy);
  }
  if ( v18 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  return a1;
}

```

## disassembly

```asm
0x180024ca8  mov     [rsp-18h+arg_0], rbx
0x180024cad  push    rbp
0x180024cae  push    rsi
0x180024caf  push    rdi
0x180024cb0  mov     rbp, rsp
0x180024cb3  sub     rsp, 60h
0x180024cb7  mov     rbx, rdx
0x180024cba  mov     rdi, rcx
0x180024cbd  xor     esi, esi
0x180024cbf  lea     rcx, [rbp+arg_18]
0x180024cc3  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x180024cc8  nop
0x180024cc9  mov     [rbp+pProxy], rsi
0x180024ccd  mov     rcx, [rbp+arg_18]
0x180024cd1  mov     rax, [rcx]
0x180024cd4  mov     rdx, [rbx]
0x180024cd7  test    rdx, rdx
0x180024cda  jz      short loc_180024CE2
0x180024cdc  mov     rdx, [rdx+10h]
0x180024ce0  jmp     short loc_180024CE9
0x180024ce2  lea     rdx, dword_18002EB94
0x180024ce9  lea     r9, [rbp+pProxy]
0x180024ced  lea     r8, ??$guid_v@UIWindowsUpdateAdministrator@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>
0x180024cf4  mov     rax, [rax+30h]
0x180024cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cfd  mov     edx, eax
0x180024cff  test    eax, eax
0x180024d01  jns     short loc_180024D6D
0x180024d03  cmp     eax, 8024A11Eh
0x180024d08  jnz     short loc_180024D37
0x180024d0a  mov     [rbp+arg_8], 1
0x180024d11  lea     r8, [rbp+arg_8]
0x180024d15  lea     rdx, [rbp+pProxy]
0x180024d19  mov     rcx, rdi
0x180024d1c  call    ??$make@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@AEAUIWindowsUpdateAdministrator@3456@W4WindowsUpdateAdministratorStatus@3456@@winrt@@YA?A_PAEAUIWindowsUpdateAdministrator@Update@Management@Windows@0@$$QEAW4WindowsUpdateAdministratorStatus@2340@@Z
0x180024d21  nop
0x180024d22  cmp     [rbp+pProxy], rsi
0x180024d26  jz      short loc_180024D32
0x180024d28  lea     rcx, [rbp+pProxy]
0x180024d2c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024d31  nop
0x180024d32  jmp     loc_180024DBF
0x180024d37  cmp     edx, 8024A11Fh
0x180024d3d  jnz     loc_180024E3C
0x180024d43  mov     [rbp+arg_8], 2
0x180024d4a  lea     r8, [rbp+arg_8]
0x180024d4e  lea     rdx, [rbp+pProxy]
0x180024d52  mov     rcx, rdi
0x180024d55  call    ??$make@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@AEAUIWindowsUpdateAdministrator@3456@W4WindowsUpdateAdministratorStatus@3456@@winrt@@YA?A_PAEAUIWindowsUpdateAdministrator@Update@Management@Windows@0@$$QEAW4WindowsUpdateAdministratorStatus@2340@@Z
0x180024d5a  nop
0x180024d5b  cmp     [rbp+pProxy], rsi
0x180024d5f  jz      short loc_180024D6B
0x180024d61  lea     rcx, [rbp+pProxy]
0x180024d65  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024d6a  nop
0x180024d6b  jmp     short loc_180024DBF
0x180024d6d  mov     [rsp+60h+dwCapabilities], esi; dwCapabilities
0x180024d71  mov     [rsp+60h+pAuthInfo], rsi; pAuthInfo
0x180024d76  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x180024d7e  mov     [rsp+60h+dwAuthnLevel], esi; dwAuthnLevel
0x180024d82  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180024d86  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180024d8a  or      edx, r8d; dwAuthnSvc
0x180024d8d  mov     rcx, [rbp+pProxy]; pProxy
0x180024d91  call    cs:__imp_CoSetProxyBlanket
0x180024d97  test    eax, eax
0x180024d99  js      short loc_180024DE8
0x180024d9b  mov     [rbp+arg_8], esi
0x180024d9e  lea     r8, [rbp+arg_8]
0x180024da2  lea     rdx, [rbp+pProxy]
0x180024da6  mov     rcx, rdi
0x180024da9  call    ??$make@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@AEAUIWindowsUpdateAdministrator@3456@W4WindowsUpdateAdministratorStatus@3456@@winrt@@YA?A_PAEAUIWindowsUpdateAdministrator@Update@Management@Windows@0@$$QEAW4WindowsUpdateAdministratorStatus@2340@@Z
0x180024dae  nop
0x180024daf  cmp     [rbp+pProxy], rsi
0x180024db3  jz      short loc_180024DBF
0x180024db5  lea     rcx, [rbp+pProxy]
0x180024db9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024dbe  nop
0x180024dbf  mov     rcx, [rbp+arg_18]
0x180024dc3  test    rcx, rcx
0x180024dc6  jz      short loc_180024DD5
0x180024dc8  mov     rax, [rcx]
0x180024dcb  mov     rax, [rax+10h]
0x180024dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dd4  nop
0x180024dd5  mov     rax, rdi
0x180024dd8  mov     rbx, [rsp+60h+arg_0]
0x180024de0  add     rsp, 60h
0x180024de4  pop     rdi
0x180024de5  pop     rsi
0x180024de6  pop     rbp
0x180024de7  retn
0x180024de8  lea     rcx, [rbp+var_18]
0x180024dec  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180024df1  mov     rbx, rax
0x180024df4  lea     rcx, [rbp+pProxy]
0x180024df8  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x180024dfd  mov     rcx, rax; pProxy
0x180024e00  mov     [rsp+60h+dwCapabilities], esi; dwCapabilities
0x180024e04  mov     [rsp+60h+pAuthInfo], rsi; pAuthInfo
0x180024e09  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x180024e11  mov     [rsp+60h+dwAuthnLevel], esi; dwAuthnLevel
0x180024e15  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180024e19  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180024e1d  or      edx, r8d; dwAuthnSvc
0x180024e20  call    cs:__imp_CoSetProxyBlanket
0x180024e26  mov     edx, eax
0x180024e28  lea     rcx, [rbp+arg_8]
0x180024e2c  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x180024e31  mov     rdx, rbx
0x180024e34  mov     ecx, [rax]
0x180024e36  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024e3c  lea     rcx, [rbp+var_18]
0x180024e40  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180024e45  mov     r8, rax
0x180024e48  lea     rcx, [rbp+arg_8]
0x180024e4c  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x180024e51  mov     rdx, r8
0x180024e54  mov     ecx, [rax]
0x180024e56  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
