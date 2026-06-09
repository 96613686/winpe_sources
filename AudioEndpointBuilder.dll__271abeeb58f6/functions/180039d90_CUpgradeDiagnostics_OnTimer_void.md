# CUpgradeDiagnostics::OnTimer(void)

- ea: `0x180039d90`
- end: `0x180039eec`
- name: `?OnTimer@CUpgradeDiagnostics@@AEAAXXZ`
- size: `348`
- prototype: `void __fastcall(CUpgradeDiagnostics *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005ad40`

## callees

- `0x180012e80`
- `0x18001707c`
- `0x180021060`
- `0x180039d90`
- `0x180039ef4`
- `0x18003a6c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039db0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039db0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180039ec4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180039ec4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180039ddd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180039ddd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039edb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039edb`

## string_xrefs

- `0x180039eaa`: `UpgradeProcessingComplete`
- `0x180039eb6`: `System\CurrentControlSet\Services\AudioEndpointBuilder\Upgrade`
- `0x180039dee`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x180039e40`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x180039e6b`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x180039e04`: `Already coinitialized (0x%08x)\n`
- `0x180039e86`: `Migration diagnostics complete\n`

## pseudocode

```c
void __fastcall CUpgradeDiagnostics::OnTimer(CUpgradeDiagnostics *this)
{
  bool v2; // zf
  HRESULT v3; // eax
  unsigned int v4; // ebx
  char v5; // di
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 i; // ebx
  int v7; // eax
  int v8; // eax
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char *v11; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  AudMigLibSetupLog(L"Migration diagnostics running\r\n");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = *((_BYTE *)this + 8) == 0;
  v11 = (char *)this + 16;
  if ( v2 )
  {
    *((_BYTE *)this + 8) = 1;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v11);
    v3 = CoInitializeEx(0, 0);
    v4 = v3;
    if ( v3 >= 0 )
    {
      AudMigLibSetupLog(L"Coinialized\r\n");
      v5 = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7C8,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
        (const char *)(unsigned int)v3,
        lpData);
      v5 = 0;
      AudMigLibSetupLog(L"Already coinitialized (0x%08x)\r\n", v4);
    }
    for ( i = eRender; (unsigned int)i < eAll; ++i )
    {
      LOBYTE(v11) = 0;
      v7 = IdentifyDriverAndMigrationIssues(i, (bool *)&v11);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7E4,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
          (const char *)(unsigned int)v7,
          lpData);
      if ( (_BYTE)v11 )
      {
        v8 = ValidateAndRepairDefaultSelection(i);
        if ( v8 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7E8,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
            (const char *)(unsigned int)v8,
            lpData);
      }
    }
    AudMigLibSetupLog(L"Migration diagnostics complete\r\n");
    Data = 1;
    RegSetKeyValueW(
      HKEY_LOCAL_MACHINE,
      L"System\\CurrentControlSet\\Services\\AudioEndpointBuilder\\Upgrade",
      L"UpgradeProcessingComplete",
      4u,
      &Data,
      4u);
    if ( v5 )
    {
      AudMigLibSetupLog(L"CoUninitialized\r\n");
      CoUninitialize();
    }
  }
  else
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v11);
  }
}

```

## disassembly

```asm
0x180039d90  mov     [rsp+arg_10], rbx
0x180039d95  push    rdi
0x180039d96  sub     rsp, 30h
0x180039d9a  mov     rdi, rcx
0x180039d9d  lea     rcx, aMigrationDiagn_1; "Migration diagnostics running\r\n"
0x180039da4  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180039da9  lea     rbx, [rdi+10h]
0x180039dad  mov     rcx, rbx; lpCriticalSection
0x180039db0  call    cs:__imp_EnterCriticalSection
0x180039db6  cmp     byte ptr [rdi+8], 0
0x180039dba  lea     rcx, [rsp+38h+arg_0]
0x180039dbf  mov     [rsp+38h+arg_0], rbx
0x180039dc4  jz      short loc_180039DD0
0x180039dc6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180039dcb  jmp     loc_180039EE1
0x180039dd0  mov     byte ptr [rdi+8], 1
0x180039dd4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180039dd9  xor     edx, edx; dwCoInit
0x180039ddb  xor     ecx, ecx; pvReserved
0x180039ddd  call    cs:__imp_CoInitializeEx
0x180039de3  mov     ebx, eax
0x180039de5  test    eax, eax
0x180039de7  jns     short loc_180039E15
0x180039de9  mov     rcx, [rsp+38h]; this
0x180039dee  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x180039df5  mov     r9d, eax; char *
0x180039df8  mov     edx, 7C8h; void *
0x180039dfd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039e02  mov     edx, ebx
0x180039e04  lea     rcx, aAlreadyCoiniti; "Already coinitialized (0x%08x)\r\n"
0x180039e0b  xor     dil, dil
0x180039e0e  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180039e13  jmp     short loc_180039E24
0x180039e15  lea     rcx, aCoinialized; "Coinialized\r\n"
0x180039e1c  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180039e21  mov     dil, 1
0x180039e24  xor     ebx, ebx
0x180039e26  lea     rdx, [rsp+38h+arg_0]; bool *
0x180039e2b  mov     byte ptr [rsp+38h+arg_0], 0
0x180039e30  mov     ecx, ebx; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001
0x180039e32  call    ?IdentifyDriverAndMigrationIssues@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@AEA_N@Z; IdentifyDriverAndMigrationIssues(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,bool &)
0x180039e37  test    eax, eax
0x180039e39  jns     short loc_180039E54
0x180039e3b  mov     rcx, [rsp+38h]; this
0x180039e40  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x180039e47  mov     r9d, eax; char *
0x180039e4a  mov     edx, 7E4h; void *
0x180039e4f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039e54  cmp     byte ptr [rsp+38h+arg_0], 0
0x180039e59  jz      short loc_180039E7F
0x180039e5b  mov     ecx, ebx; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001
0x180039e5d  call    ?ValidateAndRepairDefaultSelection@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@@Z; ValidateAndRepairDefaultSelection(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)
0x180039e62  test    eax, eax
0x180039e64  jns     short loc_180039E7F
0x180039e66  mov     rcx, [rsp+38h]; this
0x180039e6b  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x180039e72  mov     r9d, eax; char *
0x180039e75  mov     edx, 7E8h; void *
0x180039e7a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039e7f  inc     ebx
0x180039e81  cmp     ebx, 2
0x180039e84  jb      short loc_180039E26
0x180039e86  lea     rcx, aMigrationDiagn; "Migration diagnostics complete\r\n"
0x180039e8d  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180039e92  mov     r9d, 4; dwType
0x180039e98  mov     [rsp+38h+Data], 1
0x180039ea0  lea     rax, [rsp+38h+Data]
0x180039ea5  mov     [rsp+38h+cbData], r9d; cbData
0x180039eaa  lea     r8, ValueName; "UpgradeProcessingComplete"
0x180039eb1  mov     [rsp+38h+lpData], rax; lpData
0x180039eb6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Au"...
0x180039ebd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039ec4  call    cs:__imp_RegSetKeyValueW
0x180039eca  test    dil, dil
0x180039ecd  jz      short loc_180039EE1
0x180039ecf  lea     rcx, aCouninitialize_0; "CoUninitialized\r\n"
0x180039ed6  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180039edb  call    cs:__imp_CoUninitialize
0x180039ee1  mov     rbx, [rsp+38h+arg_10]
0x180039ee6  add     rsp, 30h
0x180039eea  pop     rdi
0x180039eeb  retn
```
