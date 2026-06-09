# winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministratorName(void)

- ea: `0x180026230`
- end: `0x1800263f8`
- name: `?GetRegisteredAdministratorName@WindowsUpdateAdministrator@implementation@Update@Management@Windows@winrt@@SA?AUhstring@6@XZ`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014ad0`

## callees

- `0x180008bf4`
- `0x180008c0c`
- `0x180011fa8`
- `0x180012078`
- `0x180015ac0`
- `0x180015ae8`
- `0x180016c20`
- `0x18001e7a4`
- `0x180025980`
- `0x180026230`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026370`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026370`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026277`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800263d6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026277`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800263d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002633a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002633a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::GetRegisteredAdministratorName(
        winrt::hstring *a1)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v3; // edx
  __int64 v4; // r8
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
  _BYTE v18[24]; // [rsp+48h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp+40h] BYREF
  IUnknown *pProxy; // [rsp+A8h] [rbp+48h] BYREF

  wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>((LPVOID *)&pProxy);
  if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
  {
    v13 = (unsigned int *)winrt::impl::slim_source_location::current(v18);
    v14 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
    v15 = CoSetProxyBlanket(v14, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
    v16 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&lpMem, v15);
    winrt::throw_hresult(*v16, v13, v17);
  }
  bstrString = 0;
  lpVtbl = pProxy->lpVtbl;
  bstrString = 0;
  v3 = ((__int64 (__fastcall *)(IUnknown *, BSTR *))lpVtbl[1].Release)(pProxy, &bstrString);
  if ( v3 == -2145083106 )
  {
    winrt::hstring::hstring(a1, &dword_180030C44, 0);
    if ( bstrString )
      SysFreeString(bstrString);
  }
  else
  {
    if ( v3 < 0 )
    {
      winrt::impl::slim_source_location::current(v18);
      v11 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&lpMem, v10);
      winrt::throw_hresult(*v11, v12, (__int64)v12);
    }
    v4 = -1;
    do
      ++v4;
    while ( bstrString[v4] );
    winrt::hstring::hstring((winrt::hstring *)&lpMem, bstrString, v4);
    v5 = (volatile signed __int32 *)lpMem;
    *(_QWORD *)a1 = winrt::impl::duplicate_hstring((winrt::impl *)lpMem, v6);
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
        WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
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
0x180026230  push    rbp
0x180026232  push    rbx
0x180026233  push    rsi
0x180026234  push    rdi
0x180026235  push    r14
0x180026237  mov     rbp, rsp
0x18002623a  sub     rsp, 60h
0x18002623e  mov     rsi, rcx
0x180026241  xor     r14d, r14d
0x180026244  lea     rcx, [rbp+pProxy]
0x180026248  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x18002624d  nop
0x18002624e  mov     [rsp+60h+dwCapabilities], r14d; dwCapabilities
0x180026253  mov     [rsp+60h+pAuthInfo], r14; pAuthInfo
0x180026258  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x180026260  mov     [rsp+60h+dwAuthnLevel], r14d; dwAuthnLevel
0x180026265  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026269  mov     r9, rdi; pServerPrincName
0x18002626c  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180026270  or      edx, r8d; dwAuthnSvc
0x180026273  mov     rcx, [rbp+pProxy]; pProxy
0x180026277  call    cs:__imp_CoSetProxyBlanket
0x18002627e  nop     dword ptr [rax+rax+00h]
0x180026283  test    eax, eax
0x180026285  js      loc_18002639D
0x18002628b  mov     [rbp+bstrString], r14
0x18002628f  mov     rcx, [rbp+pProxy]
0x180026293  mov     rax, [rcx]
0x180026296  mov     [rbp+bstrString], r14
0x18002629a  lea     rdx, [rbp+bstrString]
0x18002629e  mov     rax, [rax+28h]
0x1800262a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262a7  mov     edx, eax
0x1800262a9  cmp     eax, 8024A11Eh
0x1800262ae  jnz     short loc_1800262DB
0x1800262b0  xor     r8d, r8d; unsigned int
0x1800262b3  lea     rdx, dword_180030C44; unsigned __int16 *
0x1800262ba  mov     rcx, rsi; this
0x1800262bd  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x1800262c2  nop
0x1800262c3  mov     rcx, [rbp+bstrString]; bstrString
0x1800262c7  test    rcx, rcx
0x1800262ca  jz      short loc_1800262D9
0x1800262cc  call    cs:__imp_SysFreeString
0x1800262d3  nop     dword ptr [rax+rax+00h]
0x1800262d8  nop
0x1800262d9  jmp     short loc_180026347
0x1800262db  test    edx, edx
0x1800262dd  js      loc_18002637D
0x1800262e3  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x1800262e7  mov     r8, rdi
0x1800262ea  inc     r8; unsigned int
0x1800262ed  cmp     [rdx+r8*2], r14w
0x1800262f2  jnz     short loc_1800262EA
0x1800262f4  lea     rcx, [rbp+lpMem]; this
0x1800262f8  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x1800262fd  nop
0x1800262fe  mov     rbx, [rbp+lpMem]
0x180026302  mov     rcx, rbx; this
0x180026305  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18002630a  mov     [rsi], rax
0x18002630d  test    rbx, rbx
0x180026310  jz      short loc_180026331
0x180026312  lock xadd [rbx+18h], edi
0x180026317  sub     edi, 1
0x18002631a  jnz     short loc_18002636C
0x18002631c  nop
0x18002631d  call    WINRT_IMPL_GetProcessHeap
0x180026322  mov     rcx, rax; hHeap
0x180026325  mov     r8, [rbp+lpMem]; lpMem
0x180026329  xor     edx, edx; dwFlags
0x18002632b  call    WINRT_IMPL_HeapFree
0x180026330  nop
0x180026331  mov     rcx, [rbp+bstrString]; bstrString
0x180026335  test    rcx, rcx
0x180026338  jz      short loc_180026347
0x18002633a  call    cs:__imp_SysFreeString
0x180026341  nop     dword ptr [rax+rax+00h]
0x180026346  nop
0x180026347  mov     rcx, [rbp+pProxy]
0x18002634b  test    rcx, rcx
0x18002634e  jz      short loc_18002635D
0x180026350  mov     rax, [rcx]
0x180026353  mov     rax, [rax+10h]
0x180026357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002635c  nop
0x18002635d  mov     rax, rsi
0x180026360  add     rsp, 60h
0x180026364  pop     r14
0x180026366  pop     rdi
0x180026367  pop     rsi
0x180026368  pop     rbx
0x180026369  pop     rbp
0x18002636a  retn
0x18002636c  test    edi, edi
0x18002636e  jns     short loc_180026331
0x180026370  call    cs:__imp_abort
0x18002637d  lea     rcx, [rbp+var_18]
0x180026381  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180026386  mov     r8, rax
0x180026389  lea     rcx, [rbp+lpMem]; this
0x18002638d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180026392  mov     rdx, r8
0x180026395  mov     ecx, [rax]
0x180026397  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002639d  lea     rcx, [rbp+var_18]
0x1800263a1  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800263a6  mov     rbx, rax
0x1800263a9  lea     rcx, [rbp+pProxy]
0x1800263ad  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x1800263b2  mov     rcx, rax; pProxy
0x1800263b5  mov     [rsp+60h+dwCapabilities], r14d; dwCapabilities
0x1800263ba  mov     [rsp+60h+pAuthInfo], r14; pAuthInfo
0x1800263bf  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x1800263c7  mov     [rsp+60h+dwAuthnLevel], r14d; dwAuthnLevel
0x1800263cc  mov     r9, rdi; pServerPrincName
0x1800263cf  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1800263d3  or      edx, r8d; dwAuthnSvc
0x1800263d6  call    cs:__imp_CoSetProxyBlanket
0x1800263dd  nop     dword ptr [rax+rax+00h]
0x1800263e2  mov     edx, eax; int
0x1800263e4  lea     rcx, [rbp+lpMem]; this
0x1800263e8  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800263ed  mov     rdx, rbx
0x1800263f0  mov     ecx, [rax]
0x1800263f2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
