# CTSSDFarmRpc::AddUserAndSetupMonitoring(ushort const *,int)

- ea: `0x180038628`
- end: `0x18003880d`
- name: `?AddUserAndSetupMonitoring@CTSSDFarmRpc@@AEAAJPEBGH@Z`
- size: `485`
- prototype: `__int64 __fastcall(char *Parameter, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18003a460`

## callees

- `0x180003f30`
- `0x180005190`
- `0x180012be0`
- `0x180016630`
- `0x180038628`
- `0x180038c44`
- `0x18003984c`
- `0x1800399a4`
- `0x180039afc`
- `0x180039ed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038656`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038656`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800387f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800387f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003874e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003874e`

## string_xrefs

- `0x1800386ff`: `OpenKey REG_TS_CLUSTERSETTINGS failed: 0x%x in %s`
- `0x180038676`: `LocalGroupAddUser pszUserSid failed: 0x%x in %s`
- `0x18003869f`: `LogGrantUserTSAccessEvent() failed to log event 0x%08s`
- `0x180038769`: `WriteRegDWord TSSDFARM_ADDED_ASADMIN failed: 0x%x in %s`
- `0x18003879a`: `WriteRegString TSSDFARM_ADDED_USER failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::AddUserAndSetupMonitoring(char *Parameter, const unsigned __int16 *a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  CTSSDFarmRpc *v7; // rcx
  CTSSDFarmRpc *v8; // rcx
  int v9; // eax
  CTSSDFarmRpc *v10; // rcx
  signed int v11; // ebx
  CTSSDFarmRpc *v12; // rcx
  int v13; // eax
  int v14; // eax
  LSTATUS v15; // eax
  int v16; // eax
  int started; // eax
  BYTE *lpData; // [rsp+20h] [rbp-40h]
  _QWORD v20[2]; // [rsp+30h] [rbp-30h] BYREF
  int v21; // [rsp+40h] [rbp-20h]
  HKEY hKey; // [rsp+48h] [rbp-18h]
  int v23; // [rsp+50h] [rbp-10h]
  int v24; // [rsp+54h] [rbp-Ch]
  int v25; // [rsp+90h] [rbp+30h] BYREF
  int Data; // [rsp+A8h] [rbp+48h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 1608);
  v25 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1608));
  CTSSDFarmRpc::DeleteAddedUser(v7);
  v9 = CTSSDFarmRpc::LocalGroupAddUser(v8, a2, a3, &v25);
  v11 = v9;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(
      8,
      "LocalGroupAddUser pszUserSid failed: 0x%x in %s",
      (unsigned int)v9,
      "CTSSDFarmRpc::AddUserAndSetupMonitoring");
    goto LABEL_25;
  }
  if ( v25 )
  {
    v13 = CTSSDFarmRpc::LogGrantUserTSAccessEvent(v10, a2, a3);
    if ( v13 < 0 )
      _DbgPrintMessage(8, "LogGrantUserTSAccessEvent() failed to log event 0x%08s", (const char *)(unsigned int)v13);
    v20[1] = 0;
    v20[0] = &CRegistry::`vftable';
    v21 = 0;
    v23 = -1;
    v24 = -1;
    hKey = 0;
    v14 = CRegistry::OpenKey(
            (CRegistry *)v20,
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\ClusterSettings",
            0x2001Fu,
            (const unsigned __int16 *)lpData);
    v11 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      if ( v11 < 0 )
      {
        _DbgPrintMessage(
          8,
          "OpenKey REG_TS_CLUSTERSETTINGS failed: 0x%x in %s",
          (unsigned int)v11,
          "CTSSDFarmRpc::AddUserAndSetupMonitoring");
LABEL_11:
        CRegistry::~CRegistry((CRegistry *)v20);
        goto LABEL_25;
      }
    }
    Data = a3;
    v15 = RegSetValueExW(hKey, L"AddedAsAdmin", 0, 4u, (const BYTE *)&Data, 4u);
    v11 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v11 = (unsigned __int16)v15 | 0x80070000;
      if ( v11 < 0 )
      {
        _DbgPrintMessage(
          8,
          "WriteRegDWord TSSDFARM_ADDED_ASADMIN failed: 0x%x in %s",
          (unsigned int)v11,
          "CTSSDFarmRpc::AddUserAndSetupMonitoring");
        goto LABEL_11;
      }
    }
    v16 = CRegistry::WriteRegString((CRegistry *)v20, L"AddedRDSUser", a2);
    v11 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( v11 < 0 )
      {
        _DbgPrintMessage(
          8,
          "WriteRegString TSSDFARM_ADDED_USER failed: 0x%x in %s",
          (unsigned int)v11,
          "CTSSDFarmRpc::AddUserAndSetupMonitoring");
        goto LABEL_11;
      }
    }
    CRegistry::~CRegistry((CRegistry *)v20);
  }
  started = CTSSDFarmRpc::StartConnectionMonitoringTimer(Parameter);
  v11 = started;
  if ( started >= 0 )
    goto LABEL_27;
  _DbgPrintMessage(
    8,
    "StartConnectionMonitoringTimer failed: 0x%x in %s",
    (unsigned int)started,
    "CTSSDFarmRpc::AddUserAndSetupMonitoring");
LABEL_25:
  if ( v25 == 1 )
    CTSSDFarmRpc::LocalGroupRemoveUser(v12, a2, a3, &v25);
LABEL_27:
  LeaveCriticalSection(v3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180038628  mov     [rsp-28h+arg_8], rbx
0x18003862d  push    rbp
0x18003862e  push    rsi
0x18003862f  push    r12
0x180038631  push    r13
0x180038633  push    r14
0x180038635  mov     rbp, rsp
0x180038638  sub     rsp, 60h
0x18003863c  lea     r12, [rcx+648h]
0x180038643  mov     [rbp+arg_0], 0
0x18003864a  mov     r13, rcx
0x18003864d  mov     r14d, r8d
0x180038650  mov     rcx, r12; lpCriticalSection
0x180038653  mov     rsi, rdx
0x180038656  call    cs:__imp_EnterCriticalSection
0x18003865c  call    ?DeleteAddedUser@CTSSDFarmRpc@@AEAAJXZ; CTSSDFarmRpc::DeleteAddedUser(void)
0x180038661  lea     r9, [rbp+arg_0]; int *
0x180038665  mov     r8d, r14d; int
0x180038668  mov     rdx, rsi; unsigned __int16 *
0x18003866b  call    ?LocalGroupAddUser@CTSSDFarmRpc@@AEAAJPEBGHPEAH@Z; CTSSDFarmRpc::LocalGroupAddUser(ushort const *,int,int *)
0x180038670  mov     ebx, eax
0x180038672  test    eax, eax
0x180038674  jns     short loc_180038682
0x180038676  lea     rdx, aLocalgroupaddu; "LocalGroupAddUser pszUserSid failed: 0x"...
0x18003867d  jmp     loc_1800387C4
0x180038682  xor     ebx, ebx
0x180038684  cmp     [rbp+arg_0], ebx
0x180038687  jz      loc_1800387AF
0x18003868d  mov     r8d, r14d; int
0x180038690  mov     rdx, rsi; unsigned __int16 *
0x180038693  call    ?LogGrantUserTSAccessEvent@CTSSDFarmRpc@@AEAAJPEBGH@Z; CTSSDFarmRpc::LogGrantUserTSAccessEvent(ushort const *,int)
0x180038698  test    eax, eax
0x18003869a  jns     short loc_1800386AE
0x18003869c  mov     r8d, eax
0x18003869f  lea     rdx, aLoggrantuserts; "LogGrantUserTSAccessEvent() failed to l"...
0x1800386a6  lea     ecx, [rbx+8]; int
0x1800386a9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800386ae  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800386b5  mov     [rbp+var_28], rbx
0x1800386b9  mov     [rbp+var_30], rax
0x1800386bd  lea     r8, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800386c4  or      eax, 0FFFFFFFFh
0x1800386c7  mov     [rbp+var_20], ebx
0x1800386ca  mov     r9d, 2001Fh; unsigned int
0x1800386d0  mov     [rbp+var_10], eax
0x1800386d3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800386da  mov     [rbp+var_C], eax
0x1800386dd  lea     rcx, [rbp+var_30]; this
0x1800386e1  mov     [rbp+hKey], rbx
0x1800386e5  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800386ea  mov     ebx, eax
0x1800386ec  test    eax, eax
0x1800386ee  jz      short loc_180038728
0x1800386f0  jle     short loc_1800386FB
0x1800386f2  movzx   ebx, ax
0x1800386f5  or      ebx, 80070000h
0x1800386fb  test    ebx, ebx
0x1800386fd  jns     short loc_180038728
0x1800386ff  lea     rdx, aOpenkeyRegTsCl; "OpenKey REG_TS_CLUSTERSETTINGS failed: "...
0x180038706  lea     r9, aCtssdfarmrpcAd; "CTSSDFarmRpc::AddUserAndSetupMonitoring"
0x18003870d  mov     r8d, ebx
0x180038710  mov     ecx, 8; int
0x180038715  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003871a  lea     rcx, [rbp+var_30]; this
0x18003871e  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180038723  jmp     loc_1800387D8
0x180038728  mov     rcx, [rbp+hKey]; hKey
0x18003872c  lea     rax, [rbp+Data]
0x180038730  mov     r9d, 4; dwType
0x180038736  mov     [rbp+Data], r14d
0x18003873a  mov     [rsp+60h+cbData], r9d; cbData
0x18003873f  lea     rdx, aAddedasadmin; "AddedAsAdmin"
0x180038746  xor     r8d, r8d; Reserved
0x180038749  mov     [rsp+60h+lpData], rax; lpData
0x18003874e  call    cs:__imp_RegSetValueExW
0x180038754  mov     ebx, eax
0x180038756  test    eax, eax
0x180038758  jz      short loc_180038772
0x18003875a  jle     short loc_180038765
0x18003875c  movzx   ebx, ax
0x18003875f  or      ebx, 80070000h
0x180038765  test    ebx, ebx
0x180038767  jns     short loc_180038772
0x180038769  lea     rdx, aWriteregdwordT; "WriteRegDWord TSSDFARM_ADDED_ASADMIN fa"...
0x180038770  jmp     short loc_180038706
0x180038772  mov     r8, rsi; unsigned __int16 *
0x180038775  lea     rdx, ValueName; "AddedRDSUser"
0x18003877c  lea     rcx, [rbp+var_30]; this
0x180038780  call    ?WriteRegString@CRegistry@@QEAAKPEBG0@Z; CRegistry::WriteRegString(ushort const *,ushort const *)
0x180038785  mov     ebx, eax
0x180038787  test    eax, eax
0x180038789  jz      short loc_1800387A6
0x18003878b  jle     short loc_180038796
0x18003878d  movzx   ebx, ax
0x180038790  or      ebx, 80070000h
0x180038796  test    ebx, ebx
0x180038798  jns     short loc_1800387A6
0x18003879a  lea     rdx, aWriteregstring_0; "WriteRegString TSSDFARM_ADDED_USER fail"...
0x1800387a1  jmp     loc_180038706
0x1800387a6  lea     rcx, [rbp+var_30]; this
0x1800387aa  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800387af  mov     rcx, r13; Parameter
0x1800387b2  call    ?StartConnectionMonitoringTimer@CTSSDFarmRpc@@AEAAJXZ; CTSSDFarmRpc::StartConnectionMonitoringTimer(void)
0x1800387b7  mov     ebx, eax
0x1800387b9  test    eax, eax
0x1800387bb  jns     short loc_1800387ED
0x1800387bd  lea     rdx, aStartconnectio; "StartConnectionMonitoringTimer failed: "...
0x1800387c4  lea     r9, aCtssdfarmrpcAd; "CTSSDFarmRpc::AddUserAndSetupMonitoring"
0x1800387cb  mov     r8d, eax
0x1800387ce  mov     ecx, 8; int
0x1800387d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800387d8  cmp     [rbp+arg_0], 1
0x1800387dc  jnz     short loc_1800387ED
0x1800387de  lea     r9, [rbp+arg_0]; int *
0x1800387e2  mov     r8d, r14d; int
0x1800387e5  mov     rdx, rsi; unsigned __int16 *
0x1800387e8  call    ?LocalGroupRemoveUser@CTSSDFarmRpc@@AEAAJPEBGHPEAH@Z; CTSSDFarmRpc::LocalGroupRemoveUser(ushort const *,int,int *)
0x1800387ed  mov     rcx, r12; lpCriticalSection
0x1800387f0  call    cs:__imp_LeaveCriticalSection
0x1800387f6  mov     eax, ebx
0x1800387f8  mov     rbx, [rsp+60h+arg_8]
0x180038800  add     rsp, 60h
0x180038804  pop     r14
0x180038806  pop     r13
0x180038808  pop     r12
0x18003880a  pop     rsi
0x18003880b  pop     rbp
0x18003880c  retn
```
