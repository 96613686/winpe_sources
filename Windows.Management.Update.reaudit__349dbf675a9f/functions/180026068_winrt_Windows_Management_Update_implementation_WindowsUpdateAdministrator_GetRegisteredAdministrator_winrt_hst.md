# winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministrator(winrt::hstring const &)

- ea: `0x180026068`
- end: `0x180026229`
- name: `?GetRegisteredAdministrator@WindowsUpdateAdministrator@implementation@Update@Management@Windows@winrt@@SA?AUWindowsUpdateGetAdministratorResult@3456@AEBUhstring@6@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014a80`

## callees

- `0x180011fa8`
- `0x180015ac0`
- `0x180016c20`
- `0x180017c3c`
- `0x18001e7a4`
- `0x180025980`
- `0x1800259f0`
- `0x180026068`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026151`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800261e7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026151`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800261e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministrator(
        __int64 a1,
        __int64 a2)
{
  const unsigned __int16 *v4; // rdx
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
  int v16; // [rsp+88h] [rbp+28h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp+30h] BYREF
  LPVOID v18; // [rsp+98h] [rbp+38h] BYREF

  wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(&v18);
  pProxy = 0;
  if ( *(_QWORD *)a2 )
    v4 = *(const unsigned __int16 **)(*(_QWORD *)a2 + 16LL);
  else
    v4 = &dword_180030C44;
  v5 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *, IUnknown **))(*(_QWORD *)v18 + 48LL))(
         v18,
         v4,
         winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>,
         &pProxy);
  if ( v5 >= 0 )
  {
    if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
    {
      v7 = (unsigned int *)winrt::impl::slim_source_location::current(v15);
      v8 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
      v9 = CoSetProxyBlanket(v8, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
      v10 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v16, v9);
      winrt::throw_hresult(*v10, v7, v11);
    }
    v16 = 0;
    winrt::make<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateAdministrator &,enum winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus>(
      a1,
      &pProxy,
      &v16);
    if ( pProxy )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pProxy);
  }
  else if ( v5 == -2145083106 )
  {
    v16 = 1;
    winrt::make<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateAdministrator &,enum winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus>(
      a1,
      &pProxy,
      &v16);
    if ( pProxy )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&pProxy);
  }
  else
  {
    if ( v5 != -2145083105 )
    {
      winrt::impl::slim_source_location::current(v15);
      v13 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v16, v12);
      winrt::throw_hresult(*v13, v14, (__int64)v14);
    }
    v16 = 2;
    winrt::make<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::IWindowsUpdateAdministrator &,enum winrt::Windows::Management::Update::WindowsUpdateAdministratorStatus>(
      a1,
      &pProxy,
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
0x180026068  mov     [rsp-18h+arg_0], rbx
0x18002606d  push    rbp
0x18002606e  push    rsi
0x18002606f  push    rdi
0x180026070  mov     rbp, rsp
0x180026073  sub     rsp, 60h
0x180026077  mov     rbx, rdx
0x18002607a  mov     rdi, rcx
0x18002607d  xor     esi, esi
0x18002607f  lea     rcx, [rbp+arg_18]
0x180026083  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x180026088  nop
0x180026089  mov     [rbp+pProxy], rsi
0x18002608d  mov     rcx, [rbp+arg_18]
0x180026091  mov     rax, [rcx]
0x180026094  mov     rdx, [rbx]
0x180026097  test    rdx, rdx
0x18002609a  jz      short loc_1800260A2
0x18002609c  mov     rdx, [rdx+10h]
0x1800260a0  jmp     short loc_1800260A9
0x1800260a2  lea     rdx, dword_180030C44
0x1800260a9  lea     r9, [rbp+pProxy]
0x1800260ad  lea     r8, ??$guid_v@UIWindowsUpdateAdministrator@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateAdministrator>
0x1800260b4  mov     rax, [rax+30h]
0x1800260b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260bd  mov     edx, eax
0x1800260bf  test    eax, eax
0x1800260c1  jns     short loc_18002612D
0x1800260c3  cmp     eax, 8024A11Eh
0x1800260c8  jnz     short loc_1800260F7
0x1800260ca  mov     [rbp+arg_8], 1
0x1800260d1  lea     r8, [rbp+arg_8]
0x1800260d5  lea     rdx, [rbp+pProxy]
0x1800260d9  mov     rcx, rdi
0x1800260dc  call    ??$make@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@AEAUIWindowsUpdateAdministrator@3456@W4WindowsUpdateAdministratorStatus@3456@@winrt@@YA?A_PAEAUIWindowsUpdateAdministrator@Update@Management@Windows@0@$$QEAW4WindowsUpdateAdministratorStatus@2340@@Z
0x1800260e1  nop
0x1800260e2  cmp     [rbp+pProxy], rsi
0x1800260e6  jz      short loc_1800260F2
0x1800260e8  lea     rcx, [rbp+pProxy]
0x1800260ec  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800260f1  nop
0x1800260f2  jmp     loc_180026185
0x1800260f7  cmp     edx, 8024A11Fh
0x1800260fd  jnz     loc_180026209
0x180026103  mov     [rbp+arg_8], 2
0x18002610a  lea     r8, [rbp+arg_8]
0x18002610e  lea     rdx, [rbp+pProxy]
0x180026112  mov     rcx, rdi
0x180026115  call    ??$make@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@AEAUIWindowsUpdateAdministrator@3456@W4WindowsUpdateAdministratorStatus@3456@@winrt@@YA?A_PAEAUIWindowsUpdateAdministrator@Update@Management@Windows@0@$$QEAW4WindowsUpdateAdministratorStatus@2340@@Z
0x18002611a  nop
0x18002611b  cmp     [rbp+pProxy], rsi
0x18002611f  jz      short loc_18002612B
0x180026121  lea     rcx, [rbp+pProxy]
0x180026125  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002612a  nop
0x18002612b  jmp     short loc_180026185
0x18002612d  mov     [rsp+60h+dwCapabilities], esi; dwCapabilities
0x180026131  mov     [rsp+60h+pAuthInfo], rsi; pAuthInfo
0x180026136  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x18002613e  mov     [rsp+60h+dwAuthnLevel], esi; dwAuthnLevel
0x180026142  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180026146  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18002614a  or      edx, r8d; dwAuthnSvc
0x18002614d  mov     rcx, [rbp+pProxy]; pProxy
0x180026151  call    cs:__imp_CoSetProxyBlanket
0x180026158  nop     dword ptr [rax+rax+00h]
0x18002615d  test    eax, eax
0x18002615f  js      short loc_1800261AF
0x180026161  mov     [rbp+arg_8], esi
0x180026164  lea     r8, [rbp+arg_8]
0x180026168  lea     rdx, [rbp+pProxy]
0x18002616c  mov     rcx, rdi
0x18002616f  call    ??$make@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@AEAUIWindowsUpdateAdministrator@3456@W4WindowsUpdateAdministratorStatus@3456@@winrt@@YA?A_PAEAUIWindowsUpdateAdministrator@Update@Management@Windows@0@$$QEAW4WindowsUpdateAdministratorStatus@2340@@Z
0x180026174  nop
0x180026175  cmp     [rbp+pProxy], rsi
0x180026179  jz      short loc_180026185
0x18002617b  lea     rcx, [rbp+pProxy]
0x18002617f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026184  nop
0x180026185  mov     rcx, [rbp+arg_18]
0x180026189  test    rcx, rcx
0x18002618c  jz      short loc_18002619B
0x18002618e  mov     rax, [rcx]
0x180026191  mov     rax, [rax+10h]
0x180026195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002619a  nop
0x18002619b  mov     rax, rdi
0x18002619e  mov     rbx, [rsp+60h+arg_0]
0x1800261a6  add     rsp, 60h
0x1800261aa  pop     rdi
0x1800261ab  pop     rsi
0x1800261ac  pop     rbp
0x1800261ad  retn
0x1800261af  lea     rcx, [rbp+var_18]
0x1800261b3  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800261b8  mov     rbx, rax
0x1800261bb  lea     rcx, [rbp+pProxy]
0x1800261bf  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x1800261c4  mov     rcx, rax; pProxy
0x1800261c7  mov     [rsp+60h+dwCapabilities], esi; dwCapabilities
0x1800261cb  mov     [rsp+60h+pAuthInfo], rsi; pAuthInfo
0x1800261d0  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x1800261d8  mov     [rsp+60h+dwAuthnLevel], esi; dwAuthnLevel
0x1800261dc  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800261e0  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1800261e4  or      edx, r8d; dwAuthnSvc
0x1800261e7  call    cs:__imp_CoSetProxyBlanket
0x1800261ee  nop     dword ptr [rax+rax+00h]
0x1800261f3  mov     edx, eax; int
0x1800261f5  lea     rcx, [rbp+arg_8]; this
0x1800261f9  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800261fe  mov     rdx, rbx
0x180026201  mov     ecx, [rax]
0x180026203  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180026209  lea     rcx, [rbp+var_18]
0x18002620d  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180026212  mov     r8, rax
0x180026215  lea     rcx, [rbp+arg_8]; this
0x180026219  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18002621e  mov     rdx, r8
0x180026221  mov     ecx, [rax]
0x180026223  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
