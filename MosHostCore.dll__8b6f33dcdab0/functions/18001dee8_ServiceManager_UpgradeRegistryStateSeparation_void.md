# ServiceManager::UpgradeRegistryStateSeparation(void)

- ea: `0x18001dee8`
- end: `0x18001e0a5`
- name: `?UpgradeRegistryStateSeparation@ServiceManager@@AEAAJXZ`
- size: `445`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18001546c`

## callees

- `0x180003410`
- `0x1800079d4`
- `0x18000816c`
- `0x18001dee8`
- `0x180020480`
- `0x180020b1c`
- `0x180020d80`
- `0x180020ec8`
- `0x1800211f4`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001e04e`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001e079`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001e04e`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001e079`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001df5a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001df5a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001df9b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001df9b`

## string_xrefs

- `0x18001df20`: `System\Maps\Configuration`
- `0x18001df51`: `ServiceManager::UpgradeRegistryStateSeparation`
- `0x18001df92`: `ServiceManager::UpgradeRegistryStateSeparation`
- `0x18001e045`: `ServiceManager::UpgradeRegistryStateSeparation`
- `0x18001e070`: `ServiceManager::UpgradeRegistryStateSeparation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::UpgradeRegistryStateSeparation(ServiceManager *this)
{
  int RegBoolean; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // eax
  int v6; // r8d
  unsigned int v7; // eax
  unsigned int v8; // ebx
  int v9; // r8d
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  bool v14; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+28h] [rbp-30h] BYREF

  v14 = 0;
  std::wstring::wstring((__int64)v15);
  RegBoolean = RegUtils::GetRegBoolean(L"System\\Maps\\Configuration", L"UseMOSStack", &v14);
  if ( RegBoolean < 0 )
  {
    if ( RegBoolean != -2147024894 )
    {
      v9 = 3872;
      goto LABEL_10;
    }
  }
  else
  {
    LOBYTE(v4) = v14;
    v5 = RegUtils::SetMapsPersistedRegBoolean(v3, L"UseMOSStack", v4);
    if ( v5 < 0 )
    {
      v6 = 3867;
LABEL_4:
      v7 = ZTraceReportPropagation(v5, "ServiceManager::UpgradeRegistryStateSeparation", v6, this);
LABEL_5:
      v8 = v7;
      goto LABEL_25;
    }
    v5 = RegUtils::DeleteRegValue(L"System\\Maps\\Configuration", L"UseMOSStack");
    if ( v5 < 0 )
    {
      v6 = 3868;
      goto LABEL_4;
    }
  }
  RegBoolean = RegUtils::GetRegString(L"System\\Maps\\Configuration", L"ApprovedPFNList");
  if ( RegBoolean < 0 )
  {
    if ( RegBoolean == -2147024894 )
      goto LABEL_18;
    v9 = 3884;
LABEL_10:
    v7 = ZTraceReportOrigination(RegBoolean, "ServiceManager::UpgradeRegistryStateSeparation", v9, this);
    goto LABEL_5;
  }
  v5 = RegUtils::SetMapsPersistedRegString(v10, L"ApprovedPFNList", (__int64)v15);
  if ( v5 < 0 )
  {
    v6 = 3879;
    goto LABEL_4;
  }
  v5 = RegUtils::DeleteRegValue(L"System\\Maps\\Configuration", L"ApprovedPFNList");
  if ( v5 < 0 )
  {
    v6 = 3880;
    goto LABEL_4;
  }
LABEL_18:
  v5 = RegUtils::DeleteRegValue(L"System\\Maps\\Configuration", L"OfflineMaps");
  if ( v5 < 0 )
  {
    v6 = 3888;
    goto LABEL_4;
  }
  v11 = RegUtils::DeleteRegValue(L"System\\Maps\\Configuration", L"MOSChinaServerName");
  if ( v11 < 0 )
    ZTraceReportIgnore(v11, "ServiceManager::UpgradeRegistryStateSeparation", 3891, this);
  v12 = RegUtils::DeleteRegValue(L"System\\Maps\\Configuration", L"MOSServerName");
  if ( v12 < 0 )
    ZTraceReportIgnore(v12, "ServiceManager::UpgradeRegistryStateSeparation", 3894, this);
  v8 = 0;
LABEL_25:
  std::wstring::_Tidy_deallocate((__int64)v15);
  return v8;
}

```

## disassembly

```asm
0x18001dee8  mov     [rsp+arg_8], rbx
0x18001deed  push    rdi
0x18001deee  sub     rsp, 50h
0x18001def2  mov     rax, cs:__security_cookie
0x18001def9  xor     rax, rsp
0x18001defc  mov     [rsp+58h+var_10], rax
0x18001df01  mov     rbx, rcx
0x18001df04  mov     [rsp+58h+var_38], 0
0x18001df09  lea     rcx, [rsp+58h+var_30]
0x18001df0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001df13  nop
0x18001df14  lea     r8, [rsp+58h+var_38]; bool *
0x18001df19  lea     rdx, aUsemosstack; "UseMOSStack"
0x18001df20  lea     rdi, SubKey; "System\\Maps\\Configuration"
0x18001df27  mov     rcx, rdi; lpSubKey
0x18001df2a  call    ?GetRegBoolean@RegUtils@@SAJPEBG0PEA_N@Z; RegUtils::GetRegBoolean(ushort const *,ushort const *,bool *)
0x18001df2f  test    eax, eax
0x18001df31  js      short loc_18001DF82
0x18001df33  mov     r8b, [rsp+58h+var_38]
0x18001df38  lea     rdx, aUsemosstack; "UseMOSStack"
0x18001df3f  call    ?SetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_N@Z; RegUtils::SetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool)
0x18001df44  test    eax, eax
0x18001df46  jns     short loc_18001DF67
0x18001df48  mov     r8d, 0F1Bh
0x18001df4e  mov     r9, rbx
0x18001df51  lea     rdx, aServicemanager_23; "ServiceManager::UpgradeRegistryStateSep"...
0x18001df58  mov     ecx, eax
0x18001df5a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001df60  mov     ebx, eax
0x18001df62  jmp     loc_18001E081
0x18001df67  lea     rdx, aUsemosstack; "UseMOSStack"
0x18001df6e  mov     rcx, rdi; lpSubKey
0x18001df71  call    ?DeleteRegValue@RegUtils@@SAJPEBG0@Z; RegUtils::DeleteRegValue(ushort const *,ushort const *)
0x18001df76  test    eax, eax
0x18001df78  jns     short loc_18001DFA3
0x18001df7a  mov     r8d, 0F1Ch
0x18001df80  jmp     short loc_18001DF4E
0x18001df82  cmp     eax, 80070002h
0x18001df87  jz      short loc_18001DFA3
0x18001df89  mov     r8d, 0F20h
0x18001df8f  mov     r9, rbx
0x18001df92  lea     rdx, aServicemanager_23; "ServiceManager::UpgradeRegistryStateSep"...
0x18001df99  mov     ecx, eax
0x18001df9b  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001dfa1  jmp     short loc_18001DF60
0x18001dfa3  lea     r9, [rsp+58h+var_30]
0x18001dfa8  xor     r8d, r8d
0x18001dfab  lea     rdx, aApprovedpfnlis; "ApprovedPFNList"
0x18001dfb2  mov     rcx, rdi; lpSubKey
0x18001dfb5  call    ?GetRegString@RegUtils@@SAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetRegString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18001dfba  test    eax, eax
0x18001dfbc  js      short loc_18001DFFC
0x18001dfbe  lea     r8, [rsp+58h+var_30]
0x18001dfc3  lea     rdx, aApprovedpfnlis; "ApprovedPFNList"
0x18001dfca  call    ?SetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::SetMapsPersistedRegString(MapsRegKeys,ushort const *,std::wstring const &)
0x18001dfcf  test    eax, eax
0x18001dfd1  jns     short loc_18001DFDE
0x18001dfd3  mov     r8d, 0F27h
0x18001dfd9  jmp     loc_18001DF4E
0x18001dfde  lea     rdx, aApprovedpfnlis; "ApprovedPFNList"
0x18001dfe5  mov     rcx, rdi; lpSubKey
0x18001dfe8  call    ?DeleteRegValue@RegUtils@@SAJPEBG0@Z; RegUtils::DeleteRegValue(ushort const *,ushort const *)
0x18001dfed  test    eax, eax
0x18001dfef  jns     short loc_18001E00B
0x18001dff1  mov     r8d, 0F28h
0x18001dff7  jmp     loc_18001DF4E
0x18001dffc  cmp     eax, 80070002h
0x18001e001  jz      short loc_18001E00B
0x18001e003  mov     r8d, 0F2Ch
0x18001e009  jmp     short loc_18001DF8F
0x18001e00b  lea     rdx, aOfflinemaps; "OfflineMaps"
0x18001e012  mov     rcx, rdi; lpSubKey
0x18001e015  call    ?DeleteRegValue@RegUtils@@SAJPEBG0@Z; RegUtils::DeleteRegValue(ushort const *,ushort const *)
0x18001e01a  test    eax, eax
0x18001e01c  jns     short loc_18001E029
0x18001e01e  mov     r8d, 0F30h
0x18001e024  jmp     loc_18001DF4E
0x18001e029  lea     rdx, aMoschinaserver; "MOSChinaServerName"
0x18001e030  mov     rcx, rdi; lpSubKey
0x18001e033  call    ?DeleteRegValue@RegUtils@@SAJPEBG0@Z; RegUtils::DeleteRegValue(ushort const *,ushort const *)
0x18001e038  test    eax, eax
0x18001e03a  jns     short loc_18001E054
0x18001e03c  mov     r9, rbx
0x18001e03f  mov     r8d, 0F33h
0x18001e045  lea     rdx, aServicemanager_23; "ServiceManager::UpgradeRegistryStateSep"...
0x18001e04c  mov     ecx, eax
0x18001e04e  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001e054  lea     rdx, aMosservername; "MOSServerName"
0x18001e05b  mov     rcx, rdi; lpSubKey
0x18001e05e  call    ?DeleteRegValue@RegUtils@@SAJPEBG0@Z; RegUtils::DeleteRegValue(ushort const *,ushort const *)
0x18001e063  test    eax, eax
0x18001e065  jns     short loc_18001E07F
0x18001e067  mov     r9, rbx
0x18001e06a  mov     r8d, 0F36h
0x18001e070  lea     rdx, aServicemanager_23; "ServiceManager::UpgradeRegistryStateSep"...
0x18001e077  mov     ecx, eax
0x18001e079  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001e07f  xor     ebx, ebx
0x18001e081  lea     rcx, [rsp+58h+var_30]
0x18001e086  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e08b  mov     eax, ebx
0x18001e08d  mov     rcx, [rsp+58h+var_10]
0x18001e092  xor     rcx, rsp; StackCookie
0x18001e095  call    __security_check_cookie
0x18001e09a  mov     rbx, [rsp+58h+arg_8]
0x18001e09f  add     rsp, 50h
0x18001e0a3  pop     rdi
0x18001e0a4  retn
```
