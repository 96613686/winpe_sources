# WJComputeCloudDomainJoinRecoveryTaskState

- ea: `0x18001dcc0`
- end: `0x18001ded4`
- name: `WJComputeCloudDomainJoinRecoveryTaskState`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001dcc0`
- `0x18001e420`
- `0x18001ed46`
- `0x18002b39c`
- `0x18002ba14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ddcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ddcd`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001dd2d`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001dd2d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001dd62`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001dd62`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001dd8d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ddf9`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001de40`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001de9d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001dd8d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ddf9`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001de40`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001de9d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001dd1b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001deb0`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001dd1b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001deb0`

## string_xrefs

- `0x18001dd86`: `AutoJoinSvc/%s: GetPersistedRegistryLocationW(%s) falied with status 0x%08x\n`
- `0x18001dd0a`: `WJComputeCloudDomainJoinRecoveryTaskState`
- `0x18001ddf2`: `AutoJoinSvc/%s: Failed to read AAD CloudAP plugin registry value "%s\%s@%s" with status 0x%08x.`
- `0x18001de39`: `AutoJoinSvc/%s: AAD CloudAP plugin registry value ("%s\%s@%s"): 0x%08x.\n`
- `0x18001de96`: `AutoJoinSvc/%s: Failed to compute recovery task ("%s\%s") state with status 0x%08x.`

## pseudocode

```c
__int64 WJComputeCloudDomainJoinRecoveryTaskState()
{
  int PersistedRegistryLocationW; // eax
  unsigned int v1; // ebx
  LSTATUS ValueW; // eax
  int v3; // eax
  unsigned __int16 v4; // ax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  int v8; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = 0;
  pcbData[0] = 4;
  memset_0(SubKey, 0, 0x208u);
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJComputeCloudDomainJoinRecoveryTaskState");
  if ( qword_18004E3B0 && !IsThreadpoolTimerSet(qword_18004E3B0) )
    WJCloseSetTaskStateRetryTimer(g_RecoveryCheckTaskRetryState);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"IDStoreLoadParametersAad",
                                 g_szAADCloudAPPluginParamsKey,
                                 SubKey,
                                 520,
                                 0);
  v1 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v1 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: GetPersistedRegistryLocationW(%s) falied with status 0x%08x\n",
      L"WJComputeCloudDomainJoinRecoveryTaskState",
      L"IDStoreLoadParametersAad",
      v1);
    goto LABEL_17;
  }
  v1 = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, g_szAADRunRecoveryValue, 0x10u, 0, &v8, pcbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    LODWORD(pvData) = ValueW;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to read AAD CloudAP plugin registry value \"%s\\%s@%s\" with status 0x%08x.",
      L"WJComputeCloudDomainJoinRecoveryTaskState",
      L"HKEY_LOCAL_MACHINE",
      SubKey,
      g_szAADRunRecoveryValue,
      pvData);
    v3 = -1;
    v8 = -1;
  }
  else
  {
    v3 = v8;
  }
  if ( v3 != -1 && dword_18004DA50 != v3 )
  {
    LODWORD(pvData) = v3;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: AAD CloudAP plugin registry value (\"%s\\%s@%s\"): 0x%08x.\n",
      L"WJComputeCloudDomainJoinRecoveryTaskState",
      L"HKEY_LOCAL_MACHINE",
      SubKey,
      g_szAADRunRecoveryValue,
      pvData);
    if ( v8 )
      v4 = -1;
    else
      v4 = 0;
    v1 = WJSetScheduledTaskState(g_szTaskFolder, g_szRecoveryCheckTaskName, v4, g_RecoveryCheckTaskRetryState);
    dword_18004DA50 = v8;
LABEL_17:
    if ( (v1 & 0x80000000) != 0 )
    {
      LODWORD(pdwType) = v1;
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: Failed to compute recovery task (\"%s\\%s\") state with status 0x%08x.",
        L"WJComputeCloudDomainJoinRecoveryTaskState",
        g_szTaskFolder,
        g_szRecoveryCheckTaskName,
        pdwType);
    }
  }
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: finished - hr: 0x%08x",
    L"WJComputeCloudDomainJoinRecoveryTaskState",
    v1);
  return v1;
}

```

## disassembly

```asm
0x18001dcc0  push    rbp
0x18001dcc2  push    rbx
0x18001dcc3  push    rsi
0x18001dcc4  push    r15
0x18001dcc6  lea     rbp, [rsp-178h]
0x18001dcce  sub     rsp, 278h
0x18001dcd5  mov     rax, cs:__security_cookie
0x18001dcdc  xor     rax, rsp
0x18001dcdf  mov     [rbp+190h+var_30], rax
0x18001dce6  mov     ebx, 208h
0x18001dceb  mov     [rsp+290h+var_250], 0
0x18001dcf3  mov     r8d, ebx; Size
0x18001dcf6  mov     [rsp+290h+var_24C], 4
0x18001dcfe  xor     edx, edx; Val
0x18001dd00  lea     rcx, [rsp+290h+SubKey]; void *
0x18001dd05  call    memset_0
0x18001dd0a  lea     rsi, aWjcomputecloud; "WJComputeCloudDomainJoinRecoveryTaskSta"...
0x18001dd11  mov     rdx, rsi
0x18001dd14  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001dd1b  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001dd21  mov     rcx, cs:qword_18004E3B0; pti
0x18001dd28  test    rcx, rcx
0x18001dd2b  jz      short loc_18001DD43
0x18001dd2d  call    cs:__imp_IsThreadpoolTimerSet
0x18001dd33  test    eax, eax
0x18001dd35  jnz     short loc_18001DD43
0x18001dd37  lea     rcx, g_RecoveryCheckTaskRetryState
0x18001dd3e  call    WJCloseSetTaskStateRetryTimer
0x18001dd43  mov     r9d, ebx
0x18001dd46  mov     [rsp+290h+pdwType], 0
0x18001dd4f  lea     r8, [rsp+290h+SubKey]
0x18001dd54  lea     rdx, g_szAADCloudAPPluginParamsKey; "Software\\Microsoft\\IdentityStore\\Loa"...
0x18001dd5b  lea     rcx, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001dd62  call    cs:__imp_GetPersistedRegistryLocationW
0x18001dd68  mov     ebx, eax
0x18001dd6a  test    eax, eax
0x18001dd6c  jz      short loc_18001DD98
0x18001dd6e  jle     short loc_18001DD79
0x18001dd70  movzx   ebx, ax
0x18001dd73  or      ebx, 80070000h
0x18001dd79  mov     r9d, ebx
0x18001dd7c  lea     r8, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x18001dd83  mov     rdx, rsi
0x18001dd86  lea     rcx, aAutojoinsvcSGe_0; "AutoJoinSvc/%s: GetPersistedRegistryLoc"...
0x18001dd8d  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001dd93  jmp     loc_18001DE7D
0x18001dd98  xor     ebx, ebx
0x18001dd9a  lea     rax, [rsp+290h+var_24C]
0x18001dd9f  mov     [rsp+290h+pcbData], rax; pcbData
0x18001dda4  lea     r15, g_szAADRunRecoveryValue; "RunRecovery"
0x18001ddab  lea     rax, [rsp+290h+var_250]
0x18001ddb0  mov     r8, r15; lpValue
0x18001ddb3  mov     [rsp+290h+pvData], rax; pvData
0x18001ddb8  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18001ddbd  lea     r9d, [rbx+10h]; dwFlags
0x18001ddc1  mov     [rsp+290h+pdwType], rbx; pdwType
0x18001ddc6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ddcd  call    cs:__imp_RegGetValueW
0x18001ddd3  test    eax, 0FFFFFFFDh
0x18001ddd8  jz      short loc_18001DE08
0x18001ddda  mov     dword ptr [rsp+290h+pvData], eax
0x18001ddde  lea     r9, [rsp+290h+SubKey]
0x18001dde3  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001ddea  mov     [rsp+290h+pdwType], r15
0x18001ddef  mov     rdx, rsi
0x18001ddf2  lea     rcx, aAutojoinsvcSFa_3; "AutoJoinSvc/%s: Failed to read AAD Clou"...
0x18001ddf9  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001ddff  or      eax, 0FFFFFFFFh
0x18001de02  mov     [rsp+290h+var_250], eax
0x18001de06  jmp     short loc_18001DE0C
0x18001de08  mov     eax, [rsp+290h+var_250]
0x18001de0c  cmp     eax, 0FFFFFFFFh
0x18001de0f  jz      loc_18001DEA3
0x18001de15  cmp     cs:dword_18004DA50, eax
0x18001de1b  jz      loc_18001DEA3
0x18001de21  mov     dword ptr [rsp+290h+pvData], eax
0x18001de25  lea     r9, [rsp+290h+SubKey]
0x18001de2a  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18001de31  mov     [rsp+290h+pdwType], r15
0x18001de36  mov     rdx, rsi
0x18001de39  lea     rcx, aAutojoinsvcSAa; "AutoJoinSvc/%s: AAD CloudAP plugin regi"...
0x18001de40  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001de46  cmp     [rsp+290h+var_250], ebx
0x18001de4a  jz      short loc_18001DE51
0x18001de4c  or      eax, 0FFFFFFFFh
0x18001de4f  jmp     short loc_18001DE53
0x18001de51  xor     eax, eax
0x18001de53  lea     r9, g_RecoveryCheckTaskRetryState
0x18001de5a  movzx   r8d, ax
0x18001de5e  lea     rdx, g_szRecoveryCheckTaskName; "Recovery-Check"
0x18001de65  lea     rcx, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001de6c  call    WJSetScheduledTaskState
0x18001de71  mov     ecx, [rsp+290h+var_250]
0x18001de75  mov     ebx, eax
0x18001de77  mov     cs:dword_18004DA50, ecx
0x18001de7d  test    ebx, ebx
0x18001de7f  jns     short loc_18001DEA3
0x18001de81  lea     r9, g_szRecoveryCheckTaskName; "Recovery-Check"
0x18001de88  mov     dword ptr [rsp+290h+pdwType], ebx
0x18001de8c  lea     r8, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18001de93  mov     rdx, rsi
0x18001de96  lea     rcx, aAutojoinsvcSFa_6; "AutoJoinSvc/%s: Failed to compute recov"...
0x18001de9d  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001dea3  mov     r8d, ebx
0x18001dea6  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001dead  mov     rdx, rsi
0x18001deb0  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001deb6  mov     eax, ebx
0x18001deb8  mov     rcx, [rbp+190h+var_30]
0x18001debf  xor     rcx, rsp; StackCookie
0x18001dec2  call    __security_check_cookie
0x18001dec7  add     rsp, 278h
0x18001dece  pop     r15
0x18001ded0  pop     rsi
0x18001ded1  pop     rbx
0x18001ded2  pop     rbp
0x18001ded3  retn
```
