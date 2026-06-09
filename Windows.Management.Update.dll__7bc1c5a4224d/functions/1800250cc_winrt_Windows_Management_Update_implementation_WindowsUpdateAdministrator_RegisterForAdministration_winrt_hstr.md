# winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::RegisterForAdministration(winrt::hstring const &,winrt::Windows::Management::Update::WindowsUpdateAdministratorOptions const &)

- ea: `0x1800250cc`
- end: `0x180025289`
- name: `?RegisterForAdministration@WindowsUpdateAdministrator@implementation@Update@Management@Windows@winrt@@SA?AW4WindowsUpdateAdministratorStatus@3456@AEBUhstring@6@AEBW4WindowsUpdateAdministratorOptions@3456@@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800148c0`

## callees

- `0x180011410`
- `0x180014eb4`
- `0x180016024`
- `0x18001d50c`
- `0x180024604`
- `0x1800250cc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002511c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180025269`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002511c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180025269`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator::RegisterForAdministration(
        __int64 a1,
        _DWORD *a2)
{
  __int64 v4; // rdx
  int v5; // edx
  unsigned int v6; // eax
  int *v7; // rdx
  int v8; // eax
  __int64 v10; // rdx
  unsigned int *v11; // rax
  __int64 v12; // r8
  __int64 v13; // rbx
  IUnknown *v14; // rax
  unsigned int v15; // eax
  unsigned int *v16; // rax
  _BYTE v17[40]; // [rsp+40h] [rbp-28h] BYREF
  char v18; // [rsp+80h] [rbp+18h] BYREF
  IUnknown *pProxy; // [rsp+88h] [rbp+20h] BYREF

  wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(&pProxy);
  if ( CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0) < 0 )
  {
    v13 = winrt::impl::slim_source_location::current(v17, v4);
    v14 = (IUnknown *)wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(&pProxy);
    v15 = CoSetProxyBlanket(v14, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
    v16 = (unsigned int *)msl::safeint3::SafeIntException::SafeIntException(&v18, v15);
    winrt::throw_hresult(*v16, v13);
  }
  v5 = *a2 & 1 | 2;
  if ( (*a2 & 2) == 0 )
    v5 = *a2 & 1;
  v6 = v5 | 4;
  if ( (*a2 & 4) == 0 )
    v6 = v5;
  if ( *(_QWORD *)a1 )
    v7 = *(int **)(*(_QWORD *)a1 + 16LL);
  else
    v7 = &dword_18002EB94;
  v8 = ((__int64 (__fastcall *)(IUnknown *, int *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(pProxy, v7, v6);
  if ( v8 >= 0 )
  {
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl->Release)(pProxy, (unsigned int)v8);
    return 0;
  }
  else if ( v8 == -2145083106 )
  {
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return 1;
  }
  else
  {
    if ( v8 != -2145083105 )
    {
      winrt::impl::slim_source_location::current(v17, (unsigned int)v8);
      v11 = (unsigned int *)msl::safeint3::SafeIntException::SafeIntException(&v18, v10);
      winrt::throw_hresult(*v11, v12);
    }
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return 2;
  }
}

```

## disassembly

```asm
0x1800250cc  mov     rax, rsp
0x1800250cf  mov     [rax+8], rbx
0x1800250d3  push    rdi
0x1800250d4  sub     rsp, 60h
0x1800250d8  mov     rbx, rdx
0x1800250db  mov     rdi, rcx
0x1800250de  lea     rcx, [rax+20h]
0x1800250e2  call    ??$CoCreateInstance@VWindowsUpdateAdministration@@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<WindowsUpdateAdministration,IWindowsUpdateAdministration,wil::err_exception_policy>(ulong)
0x1800250e7  nop
0x1800250e8  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x1800250f0  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x1800250f9  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180025101  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x180025109  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18002510d  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180025111  or      edx, r8d; dwAuthnSvc
0x180025114  mov     rcx, [rsp+68h+pProxy]; pProxy
0x18002511c  call    cs:__imp_CoSetProxyBlanket
0x180025122  test    eax, eax
0x180025124  js      loc_180025220
0x18002512a  mov     r9, [rsp+68h+pProxy]
0x180025132  mov     rax, [r9]
0x180025135  mov     r10, [rax+18h]
0x180025139  mov     r8d, [rbx]
0x18002513c  mov     ecx, r8d
0x18002513f  and     ecx, 1
0x180025142  mov     edx, ecx
0x180025144  or      edx, 2
0x180025147  test    r8b, 2
0x18002514b  cmovz   edx, ecx
0x18002514e  mov     eax, edx
0x180025150  or      eax, 4
0x180025153  test    r8b, 4
0x180025157  cmovz   eax, edx
0x18002515a  mov     rdx, [rdi]
0x18002515d  test    rdx, rdx
0x180025160  jz      short loc_180025168
0x180025162  mov     rdx, [rdx+10h]
0x180025166  jmp     short loc_18002516F
0x180025168  lea     rdx, dword_18002EB94
0x18002516f  mov     r8d, eax
0x180025172  mov     rcx, r9
0x180025175  mov     rax, r10
0x180025178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002517d  mov     edx, eax
0x18002517f  test    eax, eax
0x180025181  jns     short loc_1800251D4
0x180025183  cmp     eax, 8024A11Eh
0x180025188  jnz     short loc_1800251AB
0x18002518a  mov     rcx, [rsp+68h+pProxy]
0x180025192  test    rcx, rcx
0x180025195  jz      short loc_1800251A4
0x180025197  mov     rdx, [rcx]
0x18002519a  mov     rax, [rdx+10h]
0x18002519e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251a3  nop
0x1800251a4  mov     eax, 1
0x1800251a9  jmp     short loc_1800251F0
0x1800251ab  cmp     edx, 8024A11Fh
0x1800251b1  jnz     short loc_1800251FB
0x1800251b3  mov     rcx, [rsp+68h+pProxy]
0x1800251bb  test    rcx, rcx
0x1800251be  jz      short loc_1800251CD
0x1800251c0  mov     rdx, [rcx]
0x1800251c3  mov     rax, [rdx+10h]
0x1800251c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251cc  nop
0x1800251cd  mov     eax, 2
0x1800251d2  jmp     short loc_1800251F0
0x1800251d4  mov     rcx, [rsp+68h+pProxy]
0x1800251dc  test    rcx, rcx
0x1800251df  jz      short loc_1800251EE
0x1800251e1  mov     rax, [rcx]
0x1800251e4  mov     rax, [rax+10h]
0x1800251e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251ed  nop
0x1800251ee  xor     eax, eax
0x1800251f0  mov     rbx, [rsp+68h+arg_0]
0x1800251f5  add     rsp, 60h
0x1800251f9  pop     rdi
0x1800251fa  retn
0x1800251fb  lea     rcx, [rsp+68h+var_28]
0x180025200  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180025205  mov     r8, rax
0x180025208  lea     rcx, [rsp+68h+arg_10]
0x180025210  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x180025215  mov     rdx, r8
0x180025218  mov     ecx, [rax]
0x18002521a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180025220  lea     rcx, [rsp+68h+var_28]
0x180025225  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002522a  mov     rbx, rax
0x18002522d  lea     rcx, [rsp+68h+pProxy]
0x180025235  call    ??C?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEBAPEAUIWindowsUpdateAdministration@@XZ; wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::operator->(void)
0x18002523a  mov     rcx, rax; pProxy
0x18002523d  mov     [rsp+68h+dwCapabilities], 0; dwCapabilities
0x180025245  mov     [rsp+68h+pAuthInfo], 0; pAuthInfo
0x18002524e  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180025256  mov     [rsp+68h+dwAuthnLevel], 0; dwAuthnLevel
0x18002525e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180025262  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180025266  or      edx, r8d; dwAuthnSvc
0x180025269  call    cs:__imp_CoSetProxyBlanket
0x18002526f  mov     edx, eax
0x180025271  lea     rcx, [rsp+68h+arg_10]
0x180025279  call    ??0SafeIntException@safeint3@msl@@QEAA@W4SafeIntError@12@@Z; msl::safeint3::SafeIntException::SafeIntException(msl::safeint3::SafeIntError)
0x18002527e  mov     rdx, rbx
0x180025281  mov     ecx, [rax]
0x180025283  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
