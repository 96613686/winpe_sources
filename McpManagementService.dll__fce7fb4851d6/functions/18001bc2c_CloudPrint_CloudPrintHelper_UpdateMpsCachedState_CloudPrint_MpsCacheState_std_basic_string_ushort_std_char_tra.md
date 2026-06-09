# CloudPrint::CloudPrintHelper::UpdateMpsCachedState(CloudPrint::MpsCacheState,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001bc2c`
- end: `0x18001bfa8`
- name: `?UpdateMpsCachedState@CloudPrintHelper@CloudPrint@@IEAAXW4MpsCacheState@2@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `892`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001963c`

## callees

- `0x180007468`
- `0x18000e164`
- `0x180012700`
- `0x18001a404`
- `0x18001bc2c`
- `0x18001bfe4`
- `0x18001c0a8`
- `0x18001c298`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bca4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bd0a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bd70`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bddb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001be5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001beb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bf2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bca4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bd0a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bd70`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bddb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001be5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001beb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bf2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001be39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001be39`

## string_xrefs

- `0x18001bc49`: `UpdateMpsCachedState`
- `0x18001bcb8`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001bd1e`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001bd84`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001bdef`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001be72`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001becc`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001bf40`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001bf73`: `CloudPrint::CloudPrintHelper::UpdateMpsCachedState`
- `0x18001bf6c`: `Successfully added MPS state cache. State: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall CloudPrint::CloudPrintHelper::UpdateMpsCachedState(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  HKEY v8; // rbx
  unsigned int v9; // eax
  const char *v10; // r9
  const BYTE *lpData; // rax
  DWORD cbData; // edx
  unsigned int v13; // eax
  const BYTE *v14; // rax
  DWORD v15; // edx
  unsigned int v16; // eax
  const BYTE *v17; // rax
  DWORD v18; // edx
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  const BYTE *v22; // rax
  DWORD v23; // edx
  unsigned int v24; // eax
  HKEY v25; // [rsp+30h] [rbp-98h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v27[136]; // [rsp+40h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  int Data; // [rsp+D8h] [rbp+10h] BYREF

  Data = a2;
  CloudPrintHelperTelemetry::WatchCurrentThread(v27, "UpdateMpsCachedState");
  try
  {
    v8 = (HKEY)CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(a1, 1, 1, 0x2001Fu);
    v25 = v8;
    v9 = RegSetValueExW(v8, L"State", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v9 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Couldn't set State regkey value. status: %d",
        v9);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
      return;
    }
    lpData = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    v13 = RegSetValueExW(v8, L"OAuthAuthority", 0, 1u, lpData, cbData);
    if ( v13 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Couldn't set OAuthAuthority regkey value. status: %d",
        v13);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
      return;
    }
    v14 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    v16 = RegSetValueExW(v8, L"MSGraphResourceId", 0, 1u, v14, v15);
    if ( v16 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Couldn't set MSGraphResourceId regkey value. status: %d",
        v16);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
      return;
    }
    v17 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    v19 = RegSetValueExW(v8, L"MSGraphBaseUrl", 0, 1u, v17, v18);
    if ( v19 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Couldn't set MSGraphBaseUrl regkey value. status: %d",
        v19);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
      return;
    }
    if ( (unsigned int)(Data - 3) > 1 )
      goto LABEL_18;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v20 = RegSetValueExW(v8, L"TimestampLow", 0, 4u, (const BYTE *)&SystemTimeAsFileTime, 4u);
    if ( v20 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Couldn't set TimestampLow regkey value. status: %d",
        v20);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
      return;
    }
    v21 = RegSetValueExW(v8, L"TimestampHigh", 0, 4u, (const BYTE *)&SystemTimeAsFileTime.dwHighDateTime, 4u);
    if ( v21 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Couldn't set TimestampHigh regkey value. status: %d",
        v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
      return;
    }
    if ( Data == 4
      && (v22 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 40),
          (v24 = RegSetValueExW(v8, L"DiscoveryEndpoint", 0, 1u, v22, v23)) != 0) )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Couldn't set DiscoveryEndpoint regkey value. status: %d",
        v24);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
    }
    else
    {
LABEL_18:
      CloudPrintHelperTelemetry::WriteDbgTraceInfo(
        "CloudPrint::CloudPrintHelper::UpdateMpsCachedState",
        L"Successfully added MPS state cache. State: %d");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x5A3,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      v10);
  }
}

```

## disassembly

```asm
0x18001bc2c  mov     [rsp+Data], edx
0x18001bc30  push    rbx
0x18001bc31  push    rsi
0x18001bc32  push    rdi
0x18001bc33  push    r12
0x18001bc35  push    r14
0x18001bc37  push    r15
0x18001bc39  sub     rsp, 98h
0x18001bc40  mov     rsi, r9
0x18001bc43  mov     rdi, r8
0x18001bc46  mov     r14, rcx
0x18001bc49  lea     rdx, aUpdatempscache; "UpdateMpsCachedState"
0x18001bc50  lea     rcx, [rsp+0C8h+var_88]
0x18001bc55  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x18001bc5a  nop
0x18001bc5b  mov     r9d, 2001Fh
0x18001bc61  mov     r12d, 1
0x18001bc67  mov     r8b, r12b
0x18001bc6a  mov     edx, r12d
0x18001bc6d  mov     rcx, r14
0x18001bc70  call    ?OpenCurrentUserMpsRegKey@CloudPrintHelper@CloudPrint@@IEAAPEAUHKEY__@@W4MpsRegKey@2@_NK@Z; CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(CloudPrint::MpsRegKey,bool,ulong)
0x18001bc75  mov     rbx, rax
0x18001bc78  mov     [rsp+0C8h+var_98], rax
0x18001bc7d  lea     r15d, [r12+3]
0x18001bc82  mov     [rsp+0C8h+cbData], r15d; cbData
0x18001bc87  lea     rax, [rsp+0C8h+Data]
0x18001bc8f  mov     [rsp+0C8h+lpData], rax; lpData
0x18001bc94  mov     r9d, r15d; dwType
0x18001bc97  xor     r8d, r8d; Reserved
0x18001bc9a  lea     rdx, ValueName; "State"
0x18001bca1  mov     rcx, rbx; hKey
0x18001bca4  call    cs:__imp_RegSetValueExW
0x18001bcaa  test    eax, eax
0x18001bcac  jz      short loc_18001BCDF
0x18001bcae  mov     r8d, eax
0x18001bcb1  lea     rdx, aCouldnTSetStat; "Couldn't set State regkey value. status"...
0x18001bcb8  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001bcbf  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001bcc4  lea     rcx, [rsp+0C8h+var_98]
0x18001bcc9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001bcce  nop
0x18001bccf  lea     rcx, [rsp+0C8h+var_88]; this
0x18001bcd4  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001bcd9  nop
0x18001bcda  jmp     loc_18001BF97
0x18001bcdf  mov     eax, [rdi+10h]
0x18001bce2  lea     edx, ds:2[rax*2]
0x18001bce9  mov     rcx, rdi
0x18001bcec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bcf1  mov     [rsp+0C8h+cbData], edx; cbData
0x18001bcf5  mov     [rsp+0C8h+lpData], rax; lpData
0x18001bcfa  mov     r9d, r12d; dwType
0x18001bcfd  xor     r8d, r8d; Reserved
0x18001bd00  lea     rdx, aOauthauthority; "OAuthAuthority"
0x18001bd07  mov     rcx, rbx; hKey
0x18001bd0a  call    cs:__imp_RegSetValueExW
0x18001bd10  test    eax, eax
0x18001bd12  jz      short loc_18001BD45
0x18001bd14  mov     r8d, eax
0x18001bd17  lea     rdx, aCouldnTSetOaut; "Couldn't set OAuthAuthority regkey valu"...
0x18001bd1e  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001bd25  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001bd2a  lea     rcx, [rsp+0C8h+var_98]
0x18001bd2f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001bd34  nop
0x18001bd35  lea     rcx, [rsp+0C8h+var_88]; this
0x18001bd3a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001bd3f  nop
0x18001bd40  jmp     loc_18001BF97
0x18001bd45  mov     eax, [rsi+10h]
0x18001bd48  lea     edx, ds:2[rax*2]
0x18001bd4f  mov     rcx, rsi
0x18001bd52  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bd57  mov     [rsp+0C8h+cbData], edx; cbData
0x18001bd5b  mov     [rsp+0C8h+lpData], rax; lpData
0x18001bd60  mov     r9d, r12d; dwType
0x18001bd63  xor     r8d, r8d; Reserved
0x18001bd66  lea     rdx, aMsgraphresourc; "MSGraphResourceId"
0x18001bd6d  mov     rcx, rbx; hKey
0x18001bd70  call    cs:__imp_RegSetValueExW
0x18001bd76  test    eax, eax
0x18001bd78  jz      short loc_18001BDAB
0x18001bd7a  mov     r8d, eax
0x18001bd7d  lea     rdx, aCouldnTSetMsgr_0; "Couldn't set MSGraphResourceId regkey v"...
0x18001bd84  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001bd8b  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001bd90  lea     rcx, [rsp+0C8h+var_98]
0x18001bd95  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001bd9a  nop
0x18001bd9b  lea     rcx, [rsp+0C8h+var_88]; this
0x18001bda0  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001bda5  nop
0x18001bda6  jmp     loc_18001BF97
0x18001bdab  mov     rcx, [rsp+0C8h+arg_20]
0x18001bdb3  mov     eax, [rcx+10h]
0x18001bdb6  lea     edx, ds:2[rax*2]
0x18001bdbd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bdc2  mov     [rsp+0C8h+cbData], edx; cbData
0x18001bdc6  mov     [rsp+0C8h+lpData], rax; lpData
0x18001bdcb  mov     r9d, r12d; dwType
0x18001bdce  xor     r8d, r8d; Reserved
0x18001bdd1  lea     rdx, aMsgraphbaseurl; "MSGraphBaseUrl"
0x18001bdd8  mov     rcx, rbx; hKey
0x18001bddb  call    cs:__imp_RegSetValueExW
0x18001bde1  test    eax, eax
0x18001bde3  jz      short loc_18001BE16
0x18001bde5  mov     r8d, eax
0x18001bde8  lea     rdx, aCouldnTSetMsgr; "Couldn't set MSGraphBaseUrl regkey valu"...
0x18001bdef  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001bdf6  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001bdfb  lea     rcx, [rsp+0C8h+var_98]
0x18001be00  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001be05  nop
0x18001be06  lea     rcx, [rsp+0C8h+var_88]; this
0x18001be0b  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001be10  nop
0x18001be11  jmp     loc_18001BF97
0x18001be16  mov     r8d, [rsp+0C8h+Data]
0x18001be1e  lea     eax, [r8-3]
0x18001be22  cmp     eax, r12d
0x18001be25  ja      loc_18001BF6C
0x18001be2b  mov     qword ptr [rsp+0C8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001be34  lea     rcx, [rsp+0C8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001be39  call    cs:__imp_GetSystemTimeAsFileTime
0x18001be3f  mov     [rsp+0C8h+cbData], r15d; cbData
0x18001be44  lea     rax, [rsp+0C8h+SystemTimeAsFileTime]
0x18001be49  mov     [rsp+0C8h+lpData], rax; lpData
0x18001be4e  mov     r9d, r15d; dwType
0x18001be51  xor     r8d, r8d; Reserved
0x18001be54  lea     rdx, aTimestamplow; "TimestampLow"
0x18001be5b  mov     rcx, rbx; hKey
0x18001be5e  call    cs:__imp_RegSetValueExW
0x18001be64  test    eax, eax
0x18001be66  jz      short loc_18001BE99
0x18001be68  mov     r8d, eax
0x18001be6b  lea     rdx, aCouldnTSetTime_0; "Couldn't set TimestampLow regkey value."...
0x18001be72  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001be79  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001be7e  lea     rcx, [rsp+0C8h+var_98]
0x18001be83  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001be88  nop
0x18001be89  lea     rcx, [rsp+0C8h+var_88]; this
0x18001be8e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001be93  nop
0x18001be94  jmp     loc_18001BF97
0x18001be99  mov     [rsp+0C8h+cbData], r15d; cbData
0x18001be9e  lea     rax, [rsp+0C8h+SystemTimeAsFileTime.dwHighDateTime]
0x18001bea3  mov     [rsp+0C8h+lpData], rax; lpData
0x18001bea8  mov     r9d, r15d; dwType
0x18001beab  xor     r8d, r8d; Reserved
0x18001beae  lea     rdx, aTimestamphigh; "TimestampHigh"
0x18001beb5  mov     rcx, rbx; hKey
0x18001beb8  call    cs:__imp_RegSetValueExW
0x18001bebe  test    eax, eax
0x18001bec0  jz      short loc_18001BEF3
0x18001bec2  mov     r8d, eax
0x18001bec5  lea     rdx, aCouldnTSetTime; "Couldn't set TimestampHigh regkey value"...
0x18001becc  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001bed3  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001bed8  lea     rcx, [rsp+0C8h+var_98]
0x18001bedd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001bee2  nop
0x18001bee3  lea     rcx, [rsp+0C8h+var_88]; this
0x18001bee8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001beed  nop
0x18001beee  jmp     loc_18001BF97
0x18001bef3  mov     r8d, [rsp+0C8h+Data]
0x18001befb  cmp     r8d, r15d
0x18001befe  jnz     short loc_18001BF6C
0x18001bf00  lea     rcx, [r14+28h]
0x18001bf04  mov     eax, [rcx+10h]
0x18001bf07  lea     edx, ds:2[rax*2]
0x18001bf0e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bf13  mov     [rsp+0C8h+cbData], edx; cbData
0x18001bf17  mov     [rsp+0C8h+lpData], rax; lpData
0x18001bf1c  mov     r9d, r12d; dwType
0x18001bf1f  xor     r8d, r8d; Reserved
0x18001bf22  lea     rdx, aDiscoveryendpo; "DiscoveryEndpoint"
0x18001bf29  mov     rcx, rbx; hKey
0x18001bf2c  call    cs:__imp_RegSetValueExW
0x18001bf32  test    eax, eax
0x18001bf34  jz      short loc_18001BF64
0x18001bf36  mov     r8d, eax
0x18001bf39  lea     rdx, aCouldnTSetDisc; "Couldn't set DiscoveryEndpoint regkey v"...
0x18001bf40  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001bf47  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001bf4c  lea     rcx, [rsp+0C8h+var_98]
0x18001bf51  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001bf56  nop
0x18001bf57  lea     rcx, [rsp+0C8h+var_88]; this
0x18001bf5c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001bf61  nop
0x18001bf62  jmp     short loc_18001BF97
0x18001bf64  mov     r8d, [rsp+0C8h+Data]
0x18001bf6c  lea     rdx, aSuccessfullyAd; "Successfully added MPS state cache. Sta"...
0x18001bf73  lea     rcx, aCloudprintClou_12; "CloudPrint::CloudPrintHelper::UpdateMps"...
0x18001bf7a  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001bf7f  lea     rcx, [rsp+0C8h+var_98]
0x18001bf84  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001bf89  nop
0x18001bf8a  lea     rcx, [rsp+0C8h+var_88]; this
0x18001bf8f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001bf94  nop
0x18001bf95  jmp     short $+2
0x18001bf97  add     rsp, 98h
0x18001bf9e  pop     r15
0x18001bfa0  pop     r14
0x18001bfa2  pop     r12
0x18001bfa4  pop     rdi
0x18001bfa5  pop     rsi
0x18001bfa6  pop     rbx
0x18001bfa7  retn
```
