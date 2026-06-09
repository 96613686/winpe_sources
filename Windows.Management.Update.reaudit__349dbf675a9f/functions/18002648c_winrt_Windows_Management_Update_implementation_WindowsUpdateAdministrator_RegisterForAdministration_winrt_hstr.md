# winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::RegisterForAdministration(winrt::hstring const &,winrt::Windows::Management::Update::WindowsUpdateAdministratorOptions const &)

- ea: `0x18002648c`
- end: `0x180026646`
- name: `?RegisterForAdministration@WindowsUpdateAdministrator@implementation@Update@Management@Windows@winrt@@SA?AW4WindowsUpdateAdministratorStatus@3456@AEBUhstring@6@AEBW4WindowsUpdateAdministratorOptions@3456@@Z`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015490`

## callees

- `0x180011fa8`
- `0x180015ac0`
- `0x180016c20`
- `0x18001e7a4`
- `0x180025980`
- `0x18002648c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800264d3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026620`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800264d3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026620`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::RegisterForAdministration(
        __int64 a1,
        _DWORD *a2)
{
  int v4; // r8d
  unsigned int v5; // eax
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  int v9; // edx
  unsigned int *v10; // rax
  unsigned int *v11; // r8
  unsigned int *v12; // rbx
  IUnknown *v13; // rax
  HRESULT v14; // eax
  unsigned int *v15; // rax
  __int64 v16; // r8
  _BYTE v17[40]; // [rsp+40h] [rbp-28h] BYREF
  char v18; // [rsp+80h] [rbp+18h] BYREF
  IUnknown *pProxy; // [rsp+88h] [rbp+20h] BYREF

  wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>((LPVOID *)&pProxy);
  if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
  {
    v12 = (unsigned int *)winrt::impl::slim_source_location::current(v17);
    v13 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
    v14 = CoSetProxyBlanket(v13, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
    v15 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v18, v14);
    winrt::throw_hresult(*v15, v12, v16);
  }
  v4 = *a2 & 1 | 2;
  if ( (*a2 & 2) == 0 )
    v4 = *a2 & 1;
  v5 = v4 | 4;
  if ( (*a2 & 4) == 0 )
    v5 = v4;
  if ( *(_QWORD *)a1 )
    v6 = *(const unsigned __int16 **)(*(_QWORD *)a1 + 16LL);
  else
    v6 = &dword_180030C44;
  v7 = ((__int64 (__fastcall *)(IUnknown *, const unsigned __int16 *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
         pProxy,
         v6,
         v5);
  if ( v7 >= 0 )
  {
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl->Release)(pProxy, (unsigned int)v7);
    return 0;
  }
  else if ( v7 == -2145083106 )
  {
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return 1;
  }
  else
  {
    if ( v7 != -2145083105 )
    {
      winrt::impl::slim_source_location::current(v17);
      v10 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v18, v9);
      winrt::throw_hresult(*v10, v11, (__int64)v11);
    }
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return 2;
  }
}

```

## disassembly

```asm
0x18002648c  mov     rax, rsp
0x18002648f  mov     [rax+8], rbx
0x180026493  push    rdi
0x180026494  sub     rsp, 60h
0x180026498  mov     rbx, rdx
0x18002649b  mov     rdi, rcx
0x18002649e  lea     rcx, [rax+20h]
0x1800264a2  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x1800264a7  nop
0x1800264a8  and     [rsp+68h+var_30], 0
0x1800264ad  and     [rsp+68h+var_38], 0
0x1800264b3  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x1800264bb  and     [rsp+68h+var_48], 0
0x1800264c0  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800264c4  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1800264c8  or      edx, r8d; dwAuthnSvc
0x1800264cb  mov     rcx, [rsp+68h+pProxy]; pProxy
0x1800264d3  call    cs:__imp_CoSetProxyBlanket
0x1800264da  nop     dword ptr [rax+rax+00h]
0x1800264df  test    eax, eax
0x1800264e1  js      loc_1800265E0
0x1800264e7  mov     rcx, [rsp+68h+pProxy]
0x1800264ef  mov     rax, [rcx]
0x1800264f2  mov     r10, [rax+18h]
0x1800264f6  mov     r9d, [rbx]
0x1800264f9  mov     edx, r9d
0x1800264fc  and     edx, 1
0x1800264ff  mov     r8d, edx
0x180026502  or      r8d, 2
0x180026506  test    r9b, 2
0x18002650a  cmovz   r8d, edx
0x18002650e  mov     eax, r8d
0x180026511  or      eax, 4
0x180026514  test    r9b, 4
0x180026518  cmovz   eax, r8d
0x18002651c  mov     rdx, [rdi]
0x18002651f  test    rdx, rdx
0x180026522  jz      short loc_18002652A
0x180026524  mov     rdx, [rdx+10h]
0x180026528  jmp     short loc_180026531
0x18002652a  lea     rdx, dword_180030C44
0x180026531  mov     r8d, eax
0x180026534  mov     rax, r10
0x180026537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002653c  mov     edx, eax
0x18002653e  test    eax, eax
0x180026540  jns     short loc_180026593
0x180026542  cmp     eax, 8024A11Eh
0x180026547  jnz     short loc_18002656A
0x180026549  mov     rcx, [rsp+68h+pProxy]
0x180026551  test    rcx, rcx
0x180026554  jz      short loc_180026563
0x180026556  mov     rdx, [rcx]
0x180026559  mov     rax, [rdx+10h]
0x18002655d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026562  nop
0x180026563  mov     eax, 1
0x180026568  jmp     short loc_1800265AF
0x18002656a  cmp     edx, 8024A11Fh
0x180026570  jnz     short loc_1800265BB
0x180026572  mov     rcx, [rsp+68h+pProxy]
0x18002657a  test    rcx, rcx
0x18002657d  jz      short loc_18002658C
0x18002657f  mov     rdx, [rcx]
0x180026582  mov     rax, [rdx+10h]
0x180026586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002658b  nop
0x18002658c  mov     eax, 2
0x180026591  jmp     short loc_1800265AF
0x180026593  mov     rcx, [rsp+68h+pProxy]
0x18002659b  test    rcx, rcx
0x18002659e  jz      short loc_1800265AD
0x1800265a0  mov     rax, [rcx]
0x1800265a3  mov     rax, [rax+10h]
0x1800265a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265ac  nop
0x1800265ad  xor     eax, eax
0x1800265af  mov     rbx, [rsp+68h+arg_0]
0x1800265b4  add     rsp, 60h
0x1800265b8  pop     rdi
0x1800265b9  retn
0x1800265bb  lea     rcx, [rsp+68h+var_28]
0x1800265c0  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800265c5  mov     r8, rax
0x1800265c8  lea     rcx, [rsp+68h+arg_10]; this
0x1800265d0  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800265d5  mov     rdx, r8
0x1800265d8  mov     ecx, [rax]
0x1800265da  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800265e0  lea     rcx, [rsp+68h+var_28]
0x1800265e5  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800265ea  mov     rbx, rax
0x1800265ed  lea     rcx, [rsp+68h+pProxy]
0x1800265f5  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x1800265fa  mov     rcx, rax; pProxy
0x1800265fd  and     [rsp+68h+var_30], 0
0x180026602  and     [rsp+68h+var_38], 0
0x180026608  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180026610  and     [rsp+68h+var_48], 0
0x180026615  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180026619  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18002661d  or      edx, r8d; dwAuthnSvc
0x180026620  call    cs:__imp_CoSetProxyBlanket
0x180026627  nop     dword ptr [rax+rax+00h]
0x18002662c  mov     edx, eax; int
0x18002662e  lea     rcx, [rsp+68h+arg_10]; this
0x180026636  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18002663b  mov     rdx, rbx
0x18002663e  mov     ecx, [rax]
0x180026640  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
