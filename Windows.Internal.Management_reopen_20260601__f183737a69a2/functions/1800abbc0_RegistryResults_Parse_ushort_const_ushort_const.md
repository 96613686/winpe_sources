# RegistryResults::Parse(ushort const *,ushort const *)

- ea: `0x1800abbc0`
- end: `0x1800abdfe`
- name: `?Parse@RegistryResults@@QEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEBG0@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007aa70`

## callees

- `0x180002cdc`
- `0x180003884`
- `0x18000d388`
- `0x1800131a8`
- `0x180016698`
- `0x180017118`
- `0x1800abb18`
- `0x1800abb54`
- `0x1800abbc0`
- `0x1800abfcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abc1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abc65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abc1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abc65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800abca5`

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
  _QWORD **v18; // r14
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
    if ( (unsigned int)dword_1800FE488 > 2 )
    {
      if ( *(_QWORD *)(a1 + 32) > 7u )
        v7 = *(HKEY *)v7;
      v25 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v9,
        (unsigned int)word_1800EDD82,
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
      if ( (unsigned int)dword_1800FE488 > 2 )
      {
        v25 = (HKEY)L"PrimaryContext";
        if ( *(_QWORD *)(a1 + 32) > 7u )
          v7 = *(HKEY *)v7;
        v23[0] = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)&byte_1800EDF37,
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
      if ( (unsigned int)dword_1800FE488 > 2 )
      {
        v23[0] = a4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v15,
          (unsigned int)&byte_1800EDE07,
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
  v18 = (_QWORD **)v23[0];
  **(_QWORD **)(v23[0] + 8LL) = 0;
  v19 = *v18;
  if ( *v18 )
  {
    do
    {
      v20 = (_QWORD *)*v19;
      std::wstring::_Tidy_deallocate(v19 + 2);
      std::_Deallocate<16>(v19, 56);
      v19 = v20;
    }
    while ( v20 );
  }
  std::_Deallocate<16>(v18, 56);
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a2;
}

```

## disassembly

```asm
0x1800abbc0  mov     [rsp-18h+arg_8], rbx
0x1800abbc5  mov     [rsp-18h+arg_18], rsi
0x1800abbca  mov     [rsp-18h+arg_10], r8
0x1800abbcf  push    rbp
0x1800abbd0  push    rdi
0x1800abbd1  push    r14
0x1800abbd3  mov     rbp, rsp
0x1800abbd6  sub     rsp, 50h
0x1800abbda  mov     rdi, r9
0x1800abbdd  mov     rsi, rdx
0x1800abbe0  mov     r14, rcx
0x1800abbe3  mov     [rbp+hKey], 0
0x1800abbeb  xor     edx, edx
0x1800abbed  lea     rcx, [rbp+hKey]
0x1800abbf1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800abbf6  lea     rbx, [r14+8]
0x1800abbfa  cmp     qword ptr [rbx+18h], 7
0x1800abbff  jbe     short loc_1800ABC06
0x1800abc01  mov     rdx, [rbx]
0x1800abc04  jmp     short loc_1800ABC09
0x1800abc06  mov     rdx, rbx; lpSubKey
0x1800abc09  lea     rax, [rbp+hKey]
0x1800abc0d  mov     [rsp+50h+phkResult], rax; phkResult
0x1800abc12  mov     r9d, 20019h; samDesired
0x1800abc18  xor     r8d, r8d; ulOptions
0x1800abc1b  mov     rcx, [r14]; hKey
0x1800abc1e  call    cs:__imp_RegOpenKeyExW
0x1800abc25  nop     dword ptr [rax+rax+00h]
0x1800abc2a  test    eax, eax
0x1800abc2c  jnz     loc_1800ABD51
0x1800abc32  mov     [rbp+arg_0], 0
0x1800abc3a  xor     edx, edx
0x1800abc3c  lea     rcx, [rbp+arg_0]
0x1800abc40  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800abc45  lea     rax, [rbp+arg_0]
0x1800abc49  mov     [rsp+50h+phkResult], rax; phkResult
0x1800abc4e  mov     r9d, 20019h; samDesired
0x1800abc54  xor     r8d, r8d; ulOptions
0x1800abc57  lea     r14, aPrimarycontext; "PrimaryContext"
0x1800abc5e  mov     rdx, r14; lpSubKey
0x1800abc61  mov     rcx, [rbp+hKey]; hKey
0x1800abc65  call    cs:__imp_RegOpenKeyExW
0x1800abc6c  nop     dword ptr [rax+rax+00h]
0x1800abc71  test    eax, eax
0x1800abc73  jnz     loc_1800ABD0A
0x1800abc79  mov     [rbp+arg_10], 0
0x1800abc81  xor     edx, edx
0x1800abc83  lea     rcx, [rbp+arg_10]
0x1800abc87  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800abc8c  lea     rax, [rbp+arg_10]
0x1800abc90  mov     [rsp+50h+phkResult], rax; phkResult
0x1800abc95  mov     r9d, 20019h; samDesired
0x1800abc9b  xor     r8d, r8d; ulOptions
0x1800abc9e  mov     rdx, rdi; lpSubKey
0x1800abca1  mov     rcx, [rbp+arg_0]; hKey
0x1800abca5  call    cs:__imp_RegOpenKeyExW
0x1800abcac  nop     dword ptr [rax+rax+00h]
0x1800abcb1  test    eax, eax
0x1800abcb3  jnz     short loc_1800ABCDA
0x1800abcb5  mov     r8, [rbp+arg_10]
0x1800abcb9  mov     rdx, rsi
0x1800abcbc  call    ?ParsePackageResults@RegistryResults@@AEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEAUHKEY__@@@Z; RegistryResults::ParsePackageResults(HKEY__ *)
0x1800abcc1  nop
0x1800abcc2  lea     rcx, [rbp+arg_10]
0x1800abcc6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abccb  nop
0x1800abccc  lea     rcx, [rbp+arg_0]
0x1800abcd0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abcd5  jmp     loc_1800ABDDC
0x1800abcda  mov     eax, cs:dword_1800FE488
0x1800abce0  cmp     eax, 2
0x1800abce3  jbe     short loc_1800ABCFF
0x1800abce5  mov     [rbp+var_10], rdi
0x1800abce9  lea     rax, [rbp+var_10]
0x1800abced  mov     [rsp+50h+phkResult], rax
0x1800abcf2  lea     rdx, byte_1800EDE07
0x1800abcf9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800abcfe  nop
0x1800abcff  lea     rcx, [rbp+arg_10]
0x1800abd03  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abd08  jmp     short loc_1800ABD46
0x1800abd0a  mov     eax, cs:dword_1800FE488
0x1800abd10  cmp     eax, 2
0x1800abd13  jbe     short loc_1800ABD46
0x1800abd15  mov     [rbp+arg_10], r14
0x1800abd19  cmp     qword ptr [rbx+18h], 7
0x1800abd1e  jbe     short loc_1800ABD23
0x1800abd20  mov     rbx, [rbx]
0x1800abd23  mov     [rbp+var_10], rbx
0x1800abd27  lea     rax, [rbp+arg_10]
0x1800abd2b  mov     [rsp+50h+var_28], rax
0x1800abd30  lea     rax, [rbp+var_10]
0x1800abd34  mov     [rsp+50h+phkResult], rax
0x1800abd39  lea     rdx, byte_1800EDF37
0x1800abd40  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800abd45  nop
0x1800abd46  lea     rcx, [rbp+arg_0]
0x1800abd4a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abd4f  jmp     short loc_1800ABD7F
0x1800abd51  mov     eax, cs:dword_1800FE488
0x1800abd57  cmp     eax, 2
0x1800abd5a  jbe     short loc_1800ABD7F
0x1800abd5c  cmp     qword ptr [rbx+18h], 7
0x1800abd61  jbe     short loc_1800ABD66
0x1800abd63  mov     rbx, [rbx]
0x1800abd66  mov     [rbp+arg_10], rbx
0x1800abd6a  lea     rax, [rbp+arg_10]
0x1800abd6e  mov     [rsp+50h+phkResult], rax
0x1800abd73  lea     rdx, word_1800EDD82
0x1800abd7a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800abd7f  lea     rcx, [rbp+var_10]
0x1800abd83  call    ??0?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::list<CommandResult>(void)
0x1800abd88  nop
0x1800abd89  lea     rdx, [rbp+var_10]
0x1800abd8d  mov     rcx, rsi
0x1800abd90  call    ??0?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@$$QEAV01@@Z; std::list<CommandResult>::list<CommandResult>(std::list<CommandResult> &&)
0x1800abd95  nop
0x1800abd96  mov     r14, [rbp+var_10]
0x1800abd9a  mov     rax, [r14+8]
0x1800abd9e  mov     qword ptr [rax], 0
0x1800abda5  mov     rdi, [r14]
0x1800abda8  test    rdi, rdi
0x1800abdab  jz      short loc_1800ABDCE
0x1800abdad  mov     rbx, [rdi]
0x1800abdb0  lea     rcx, [rdi+10h]
0x1800abdb4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800abdb9  mov     edx, 38h ; '8'
0x1800abdbe  mov     rcx, rdi
0x1800abdc1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800abdc6  mov     rdi, rbx
0x1800abdc9  test    rbx, rbx
0x1800abdcc  jnz     short loc_1800ABDAD
0x1800abdce  mov     edx, 38h ; '8'
0x1800abdd3  mov     rcx, r14
0x1800abdd6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800abddb  nop
0x1800abddc  lea     rcx, [rbp+hKey]
0x1800abde0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abde5  mov     rax, rsi
0x1800abde8  lea     r11, [rsp+50h+var_s0]
0x1800abded  mov     rbx, [r11+28h]
0x1800abdf1  mov     rsi, [r11+38h]
0x1800abdf5  mov     rsp, r11
0x1800abdf8  pop     r14
0x1800abdfa  pop     rdi
0x1800abdfb  pop     rbp
0x1800abdfc  retn
```
