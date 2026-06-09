# RegistryResults::Parse(ushort const *,ushort const *)

- ea: `0x1800a8650`
- end: `0x1800a887b`
- name: `?Parse@RegistryResults@@QEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEBG0@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180079260`

## callees

- `0x180002bdc`
- `0x18000377c`
- `0x18000ce64`
- `0x180012ae8`
- `0x180015f70`
- `0x1800169b8`
- `0x1800a85a8`
- `0x1800a85e4`
- `0x1800a8650`
- `0x1800a8a40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a86ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a86ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8729`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a86ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a86ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8729`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RegistryResults::Parse(__int64 a1, __int64 a2, HKEY a3, const WCHAR *a4)
{
  HKEY v7; // rbx
  const WCHAR *v8; // rdx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // r9d
  _QWORD *v18; // r14
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+20h] BYREF
  HKEY v25; // [rsp+80h] [rbp+30h] BYREF

  v25 = a3;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = (HKEY)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) <= 7u )
    v8 = (const WCHAR *)(a1 + 8);
  else
    v8 = *(const WCHAR **)v7;
  if ( RegOpenKeyExW(*(HKEY *)a1, v8, 0, 0x20019u, &hKey) )
  {
    if ( (unsigned int)dword_1800FA480 > 2 )
    {
      if ( *(_QWORD *)(a1 + 32) > 7u )
        v7 = *(HKEY *)v7;
      v25 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v9,
        (unsigned int)word_1800E9FA2,
        v10,
        v11,
        (__int64)&v25);
    }
  }
  else
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    if ( RegOpenKeyExW(hKey, L"PrimaryContext", 0, 0x20019u, &phkResult) )
    {
      if ( (unsigned int)dword_1800FA480 > 2 )
      {
        v25 = (HKEY)L"PrimaryContext";
        if ( *(_QWORD *)(a1 + 32) > 7u )
          v7 = *(HKEY *)v7;
        v23[0] = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)&byte_1800EA157,
          v13,
          v14,
          (__int64)v23,
          (__int64)&v25);
      }
    }
    else
    {
      v25 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v25,
        0);
      if ( !RegOpenKeyExW(phkResult, a4, 0, 0x20019u, &v25) )
      {
        RegistryResults::ParsePackageResults(v15, a2, v25);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        goto LABEL_23;
      }
      if ( (unsigned int)dword_1800FA480 > 2 )
      {
        v23[0] = a4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)&byte_1800EA027,
          v16,
          v17,
          (__int64)v23);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  std::list<CommandResult>::list<CommandResult>(v23);
  std::list<CommandResult>::list<CommandResult>(a2, v23);
  v18 = (_QWORD *)v23[0];
  **(_QWORD **)(v23[0] + 8LL) = 0;
  v19 = (_QWORD *)*v18;
  if ( *v18 )
  {
    do
    {
      v20 = (_QWORD *)*v19;
      std::wstring::_Tidy_deallocate(v19 + 2);
      std::_Deallocate<16>(v19, 0x38u);
      v19 = v20;
    }
    while ( v20 );
  }
  std::_Deallocate<16>(v18, 0x38u);
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a2;
}

```

## disassembly

```asm
0x1800a8650  mov     [rsp-18h+arg_8], rbx
0x1800a8655  mov     [rsp-18h+arg_18], rsi
0x1800a865a  mov     [rsp-18h+arg_10], r8
0x1800a865f  push    rbp
0x1800a8660  push    rdi
0x1800a8661  push    r14
0x1800a8663  mov     rbp, rsp
0x1800a8666  sub     rsp, 50h
0x1800a866a  mov     rdi, r9
0x1800a866d  mov     rsi, rdx
0x1800a8670  mov     r14, rcx
0x1800a8673  mov     [rbp+hKey], 0
0x1800a867b  xor     edx, edx
0x1800a867d  lea     rcx, [rbp+hKey]
0x1800a8681  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a8686  lea     rbx, [r14+8]
0x1800a868a  cmp     qword ptr [rbx+18h], 7
0x1800a868f  jbe     short loc_1800A8696
0x1800a8691  mov     rdx, [rbx]
0x1800a8694  jmp     short loc_1800A8699
0x1800a8696  mov     rdx, rbx; lpSubKey
0x1800a8699  lea     rax, [rbp+hKey]
0x1800a869d  mov     [rsp+50h+phkResult], rax; phkResult
0x1800a86a2  mov     r9d, 20019h; samDesired
0x1800a86a8  xor     r8d, r8d; ulOptions
0x1800a86ab  mov     rcx, [r14]; hKey
0x1800a86ae  call    cs:__imp_RegOpenKeyExW
0x1800a86b4  test    eax, eax
0x1800a86b6  jnz     loc_1800A87CF
0x1800a86bc  mov     [rbp+arg_0], 0
0x1800a86c4  xor     edx, edx
0x1800a86c6  lea     rcx, [rbp+arg_0]
0x1800a86ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a86cf  lea     rax, [rbp+arg_0]
0x1800a86d3  mov     [rsp+50h+phkResult], rax; phkResult
0x1800a86d8  mov     r9d, 20019h; samDesired
0x1800a86de  xor     r8d, r8d; ulOptions
0x1800a86e1  lea     r14, aPrimarycontext; "PrimaryContext"
0x1800a86e8  mov     rdx, r14; lpSubKey
0x1800a86eb  mov     rcx, [rbp+hKey]; hKey
0x1800a86ef  call    cs:__imp_RegOpenKeyExW
0x1800a86f5  test    eax, eax
0x1800a86f7  jnz     loc_1800A8788
0x1800a86fd  mov     [rbp+arg_10], 0
0x1800a8705  xor     edx, edx
0x1800a8707  lea     rcx, [rbp+arg_10]
0x1800a870b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a8710  lea     rax, [rbp+arg_10]
0x1800a8714  mov     [rsp+50h+phkResult], rax; phkResult
0x1800a8719  mov     r9d, 20019h; samDesired
0x1800a871f  xor     r8d, r8d; ulOptions
0x1800a8722  mov     rdx, rdi; lpSubKey
0x1800a8725  mov     rcx, [rbp+arg_0]; hKey
0x1800a8729  call    cs:__imp_RegOpenKeyExW
0x1800a872f  test    eax, eax
0x1800a8731  jnz     short loc_1800A8758
0x1800a8733  mov     r8, [rbp+arg_10]
0x1800a8737  mov     rdx, rsi
0x1800a873a  call    ?ParsePackageResults@RegistryResults@@AEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEAUHKEY__@@@Z; RegistryResults::ParsePackageResults(HKEY__ *)
0x1800a873f  nop
0x1800a8740  lea     rcx, [rbp+arg_10]
0x1800a8744  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a8749  nop
0x1800a874a  lea     rcx, [rbp+arg_0]
0x1800a874e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a8753  jmp     loc_1800A885A
0x1800a8758  mov     eax, cs:dword_1800FA480
0x1800a875e  cmp     eax, 2
0x1800a8761  jbe     short loc_1800A877D
0x1800a8763  mov     [rbp+var_10], rdi
0x1800a8767  lea     rax, [rbp+var_10]
0x1800a876b  mov     [rsp+50h+phkResult], rax
0x1800a8770  lea     rdx, byte_1800EA027
0x1800a8777  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a877c  nop
0x1800a877d  lea     rcx, [rbp+arg_10]
0x1800a8781  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a8786  jmp     short loc_1800A87C4
0x1800a8788  mov     eax, cs:dword_1800FA480
0x1800a878e  cmp     eax, 2
0x1800a8791  jbe     short loc_1800A87C4
0x1800a8793  mov     [rbp+arg_10], r14
0x1800a8797  cmp     qword ptr [rbx+18h], 7
0x1800a879c  jbe     short loc_1800A87A1
0x1800a879e  mov     rbx, [rbx]
0x1800a87a1  mov     [rbp+var_10], rbx
0x1800a87a5  lea     rax, [rbp+arg_10]
0x1800a87a9  mov     [rsp+50h+var_28], rax
0x1800a87ae  lea     rax, [rbp+var_10]
0x1800a87b2  mov     [rsp+50h+phkResult], rax
0x1800a87b7  lea     rdx, byte_1800EA157
0x1800a87be  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800a87c3  nop
0x1800a87c4  lea     rcx, [rbp+arg_0]
0x1800a87c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a87cd  jmp     short loc_1800A87FD
0x1800a87cf  mov     eax, cs:dword_1800FA480
0x1800a87d5  cmp     eax, 2
0x1800a87d8  jbe     short loc_1800A87FD
0x1800a87da  cmp     qword ptr [rbx+18h], 7
0x1800a87df  jbe     short loc_1800A87E4
0x1800a87e1  mov     rbx, [rbx]
0x1800a87e4  mov     [rbp+arg_10], rbx
0x1800a87e8  lea     rax, [rbp+arg_10]
0x1800a87ec  mov     [rsp+50h+phkResult], rax
0x1800a87f1  lea     rdx, word_1800E9FA2
0x1800a87f8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a87fd  lea     rcx, [rbp+var_10]
0x1800a8801  call    ??0?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::list<CommandResult>(void)
0x1800a8806  nop
0x1800a8807  lea     rdx, [rbp+var_10]
0x1800a880b  mov     rcx, rsi
0x1800a880e  call    ??0?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@$$QEAV01@@Z; std::list<CommandResult>::list<CommandResult>(std::list<CommandResult> &&)
0x1800a8813  nop
0x1800a8814  mov     r14, [rbp+var_10]
0x1800a8818  mov     rax, [r14+8]
0x1800a881c  mov     qword ptr [rax], 0
0x1800a8823  mov     rdi, [r14]
0x1800a8826  test    rdi, rdi
0x1800a8829  jz      short loc_1800A884C
0x1800a882b  mov     rbx, [rdi]
0x1800a882e  lea     rcx, [rdi+10h]
0x1800a8832  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8837  mov     edx, 38h ; '8'
0x1800a883c  mov     rcx, rdi
0x1800a883f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a8844  mov     rdi, rbx
0x1800a8847  test    rbx, rbx
0x1800a884a  jnz     short loc_1800A882B
0x1800a884c  mov     edx, 38h ; '8'
0x1800a8851  mov     rcx, r14
0x1800a8854  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a8859  nop
0x1800a885a  lea     rcx, [rbp+hKey]
0x1800a885e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a8863  mov     rax, rsi
0x1800a8866  lea     r11, [rsp+50h+var_s0]
0x1800a886b  mov     rbx, [r11+28h]
0x1800a886f  mov     rsi, [r11+38h]
0x1800a8873  mov     rsp, r11
0x1800a8876  pop     r14
0x1800a8878  pop     rdi
0x1800a8879  pop     rbp
0x1800a887a  retn
```
