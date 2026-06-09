# winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministratorName(void)

- ea: `0x180024e64`
- end: `0x180025021`
- name: `?GetRegisteredAdministratorName@WindowsUpdateAdministrator@implementation@Update@Management@Windows@winrt@@SA?AUhstring@6@XZ`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013e10`

## callees

- `0x180008653`
- `0x18000866b`
- `0x180011410`
- `0x1800114ec`
- `0x180014eb4`
- `0x180014ee0`
- `0x180016024`
- `0x18001d50c`
- `0x180024604`
- `0x180024e64`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024fa5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024fa5`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024eab`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180025005`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024eab`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180025005`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f03`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f76`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f03`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f76`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministratorName(
        struct winrt::impl::shared_hstring_header **a1)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v3; // edx
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  struct winrt::impl::hstring_header *v6; // rdx
  int v7; // edi
  HANDLE ProcessHeap; // rax
  int v10; // edx
  unsigned int *v11; // rax
  unsigned int *v12; // r8
  unsigned int *v13; // rbx
  IUnknown *v14; // rax
  HRESULT v15; // eax
  unsigned int *v16; // rax
  __int64 v17; // r8
  BSTR v18; // [rsp+48h] [rbp-18h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  LPVOID lpMem; // [rsp+98h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp+40h] BYREF
  IUnknown *pProxy; // [rsp+A8h] [rbp+48h] BYREF

  wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>((LPVOID *)&pProxy);
  if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
  {
    v13 = (unsigned int *)winrt::impl::slim_source_location::current((__int64)&v18);
    v14 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->((__int64)&pProxy);
    v15 = CoSetProxyBlanket(v14, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
    v16 = msl::safeint3::SafeIntException::SafeIntException(&lpMem, v15);
    winrt::throw_hresult(*v16, v13, v17);
  }
  bstrString = 0;
  lpVtbl = pProxy->lpVtbl;
  bstrString = 0;
  v3 = ((__int64 (__fastcall *)(IUnknown *, BSTR *))lpVtbl[1].Release)(pProxy, &bstrString);
  if ( v3 == -2145083106 )
  {
    v18 = (BSTR)&dword_18002EB94;
    v19 = 0;
    winrt::hstring::hstring(a1, (__int64)&v18);
    if ( bstrString )
      SysFreeString(bstrString);
  }
  else
  {
    if ( v3 < 0 )
    {
      winrt::impl::slim_source_location::current((__int64)&v18);
      v11 = msl::safeint3::SafeIntException::SafeIntException(&lpMem, v10);
      winrt::throw_hresult(*v11, v12, (__int64)v12);
    }
    v18 = bstrString;
    v4 = -1;
    do
      ++v4;
    while ( bstrString[v4] );
    v19 = v4;
    winrt::hstring::hstring((struct winrt::impl::shared_hstring_header **)&lpMem, (__int64)&v18);
    v5 = (volatile signed __int32 *)lpMem;
    *a1 = winrt::impl::duplicate_hstring((winrt::impl *)lpMem, v6);
    if ( v5 )
    {
      v7 = _InterlockedDecrement(v5 + 6);
      if ( v7 )
      {
        if ( v7 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v5);
      }
    }
    if ( bstrString )
      SysFreeString(bstrString);
  }
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  return a1;
}

```

## disassembly

```asm
0x180024e64  push    rbp
0x180024e66  push    rbx
0x180024e67  push    rsi
0x180024e68  push    rdi
0x180024e69  push    r14
0x180024e6b  mov     rbp, rsp
0x180024e6e  sub     rsp, 60h
0x180024e72  mov     rsi, rcx
0x180024e75  xor     r14d, r14d
0x180024e78  lea     rcx, [rbp+pProxy]
0x180024e7c  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x180024e81  nop
0x180024e82  mov     [rsp+60h+dwCapabilities], r14d; dwCapabilities
0x180024e87  mov     [rsp+60h+pAuthInfo], r14; pAuthInfo
0x180024e8c  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x180024e94  mov     [rsp+60h+dwAuthnLevel], r14d; dwAuthnLevel
0x180024e99  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024e9d  mov     r9, rdi; pServerPrincName
0x180024ea0  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180024ea4  or      edx, r8d; dwAuthnSvc
0x180024ea7  mov     rcx, [rbp+pProxy]; pProxy
0x180024eab  call    cs:__imp_CoSetProxyBlanket
0x180024eb1  test    eax, eax
0x180024eb3  js      loc_180024FCC
0x180024eb9  mov     [rbp+bstrString], r14
0x180024ebd  mov     rcx, [rbp+pProxy]
0x180024ec1  mov     rax, [rcx]
0x180024ec4  mov     [rbp+bstrString], r14
0x180024ec8  lea     rdx, [rbp+bstrString]
0x180024ecc  mov     rax, [rax+28h]
0x180024ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ed5  mov     edx, eax
0x180024ed7  cmp     eax, 8024A11Eh
0x180024edc  jnz     short loc_180024F0C
0x180024ede  lea     rax, dword_18002EB94
0x180024ee5  mov     [rbp+var_18], rax
0x180024ee9  mov     [rbp+var_10], r14
0x180024eed  lea     rdx, [rbp+var_18]
0x180024ef1  mov     rcx, rsi
0x180024ef4  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180024ef9  nop
0x180024efa  mov     rcx, [rbp+bstrString]; bstrString
0x180024efe  test    rcx, rcx
0x180024f01  jz      short loc_180024F0A
0x180024f03  call    cs:__imp_SysFreeString
0x180024f09  nop
0x180024f0a  jmp     short loc_180024F7D
0x180024f0c  test    edx, edx
0x180024f0e  js      loc_180024FAC
0x180024f14  mov     rcx, [rbp+bstrString]
0x180024f18  mov     [rbp+var_18], rcx
0x180024f1c  mov     rax, rdi
0x180024f1f  inc     rax
0x180024f22  cmp     [rcx+rax*2], r14w
0x180024f27  jnz     short loc_180024F1F
0x180024f29  mov     [rbp+var_10], rax
0x180024f2d  lea     rdx, [rbp+var_18]
0x180024f31  lea     rcx, [rbp+lpMem]
0x180024f35  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180024f3a  nop
0x180024f3b  mov     rbx, [rbp+lpMem]
0x180024f3f  mov     rcx, rbx; this
0x180024f42  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180024f47  mov     [rsi], rax
0x180024f4a  test    rbx, rbx
0x180024f4d  jz      short loc_180024F6D
0x180024f4f  lock xadd [rbx+18h], edi
0x180024f54  sub     edi, 1
0x180024f57  jnz     short loc_180024FA1
0x180024f59  nop
0x180024f5a  call    WINRT_IMPL_GetProcessHeap
0x180024f5f  mov     rcx, rax; hHeap
0x180024f62  mov     r8, rbx; lpMem
0x180024f65  xor     edx, edx; dwFlags
0x180024f67  call    WINRT_IMPL_HeapFree
0x180024f6c  nop
0x180024f6d  mov     rcx, [rbp+bstrString]; bstrString
0x180024f71  test    rcx, rcx
0x180024f74  jz      short loc_180024F7D
0x180024f76  call    cs:__imp_SysFreeString
0x180024f7c  nop
0x180024f7d  mov     rcx, [rbp+pProxy]
0x180024f81  test    rcx, rcx
0x180024f84  jz      short loc_180024F93
0x180024f86  mov     rax, [rcx]
0x180024f89  mov     rax, [rax+10h]
0x180024f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f92  nop
0x180024f93  mov     rax, rsi
0x180024f96  add     rsp, 60h
0x180024f9a  pop     r14
0x180024f9c  pop     rdi
0x180024f9d  pop     rsi
0x180024f9e  pop     rbx
0x180024f9f  pop     rbp
0x180024fa0  retn
0x180024fa1  test    edi, edi
0x180024fa3  jns     short loc_180024F6D
0x180024fa5  call    cs:__imp_abort
0x180024fac  lea     rcx, [rbp+var_18]
0x180024fb0  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180024fb5  mov     r8, rax
0x180024fb8  lea     rcx, [rbp+lpMem]
0x180024fbc  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x180024fc1  mov     rdx, r8
0x180024fc4  mov     ecx, [rax]
0x180024fc6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024fcc  lea     rcx, [rbp+var_18]
0x180024fd0  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180024fd5  mov     rbx, rax
0x180024fd8  lea     rcx, [rbp+pProxy]
0x180024fdc  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x180024fe1  mov     rcx, rax; pProxy
0x180024fe4  mov     [rsp+60h+dwCapabilities], r14d; dwCapabilities
0x180024fe9  mov     [rsp+60h+pAuthInfo], r14; pAuthInfo
0x180024fee  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x180024ff6  mov     [rsp+60h+dwAuthnLevel], r14d; dwAuthnLevel
0x180024ffb  mov     r9, rdi; pServerPrincName
0x180024ffe  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180025002  or      edx, r8d; dwAuthnSvc
0x180025005  call    cs:__imp_CoSetProxyBlanket
0x18002500b  mov     edx, eax
0x18002500d  lea     rcx, [rbp+lpMem]
0x180025011  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x180025016  mov     rdx, rbx
0x180025019  mov     ecx, [rax]
0x18002501b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
