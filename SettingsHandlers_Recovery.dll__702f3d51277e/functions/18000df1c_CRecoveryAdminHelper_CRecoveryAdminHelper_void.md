# CRecoveryAdminHelper::~CRecoveryAdminHelper(void)

- ea: `0x18000df1c`
- end: `0x18000e05d`
- name: `??1CRecoveryAdminHelper@@UEAA@XZ`
- size: `321`
- prototype: `void __fastcall(CRecoveryAdminHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18000e0a0`

## callees

- `0x18000282c`
- `0x18000bdcc`
- `0x18000bef4`
- `0x18000df1c`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfb1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dfa3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e01c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dfa3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e01c`
- `WDSCORE!WdsTerminate` at `0x18000e022`
- `WDSCORE!WdsTerminate` at `0x18000e022`
- `WDSCORE!CurrentIP` at `0x18000df40`
- `WDSCORE!CurrentIP` at `0x18000dfb9`
- `WDSCORE!CurrentIP` at `0x18000df40`
- `WDSCORE!CurrentIP` at `0x18000dfb9`

## string_xrefs

- `0x18000dff9`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000df80`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
void __fastcall CRecoveryAdminHelper::~CRecoveryAdminHelper(CPointInTimeRestoreHelper **this)
{
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  CPointInTimeRestoreHelper *v8; // rbx

  *this = (CPointInTimeRestoreHelper *)&CRecoveryAdminHelper::`vftable';
  LastError = GetLastError();
  v3 = CurrentIP();
  v4 = ConstructPartialMsgW(0x4000000u, "CRecoveryAdminHelper::~CRecoveryAdminHelper: terminated.");
  WdsSetupLogMessageW(
    v4,
    0,
    L"D",
    0,
    17,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::~CRecoveryAdminHelper",
    v3,
    LastError,
    0,
    0);
  CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper((CRecoveryAdminHelper *)this);
  v5 = GetLastError();
  v6 = CurrentIP();
  v7 = ConstructPartialMsgW(0x4000000u, "CPointInTimeRestoreHelper::TerminateLogging: terminating logging.");
  WdsSetupLogMessageW(
    v7,
    0,
    L"D",
    0,
    47,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::TerminateLogging",
    v6,
    v5,
    0,
    0);
  WdsTerminate();
  v8 = this[2];
  if ( v8 )
  {
    CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper(this[2]);
    operator delete(v8);
  }
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000df1c  mov     [rsp+arg_0], rbx
0x18000df21  mov     [rsp+arg_8], rsi
0x18000df26  push    rdi
0x18000df27  sub     rsp, 60h
0x18000df2b  mov     rsi, rcx
0x18000df2e  lea     rax, ??_7CRecoveryAdminHelper@@6B@; const CRecoveryAdminHelper::`vftable'
0x18000df35  mov     [rcx], rax
0x18000df38  call    cs:__imp_GetLastError
0x18000df3e  mov     edi, eax
0x18000df40  call    cs:__imp_CurrentIP
0x18000df46  mov     rbx, rax
0x18000df49  lea     rdx, aCrecoveryadmin; "CRecoveryAdminHelper::~CRecoveryAdminHe"...
0x18000df50  mov     ecx, 4000000h; unsigned int
0x18000df55  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000df5a  mov     [rsp+68h+var_18], 0
0x18000df62  mov     [rsp+68h+var_20], 0
0x18000df6b  mov     [rsp+68h+var_28], edi
0x18000df6f  mov     [rsp+68h+var_30], rbx
0x18000df74  lea     rcx, aCrecoveryadmin_10; "CRecoveryAdminHelper::~CRecoveryAdminHe"...
0x18000df7b  mov     [rsp+68h+var_38], rcx
0x18000df80  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000df87  mov     [rsp+68h+var_40], rcx
0x18000df8c  mov     [rsp+68h+var_48], 11h
0x18000df94  xor     r9d, r9d
0x18000df97  lea     r8, aD; "D"
0x18000df9e  xor     edx, edx
0x18000dfa0  mov     rcx, rax
0x18000dfa3  call    cs:__imp_WdsSetupLogMessageW
0x18000dfa9  mov     rcx, rsi; this
0x18000dfac  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000dfb1  call    cs:__imp_GetLastError
0x18000dfb7  mov     edi, eax
0x18000dfb9  call    cs:__imp_CurrentIP
0x18000dfbf  mov     rbx, rax
0x18000dfc2  lea     rdx, aCpointintimere_65; "CPointInTimeRestoreHelper::TerminateLog"...
0x18000dfc9  mov     ecx, 4000000h; unsigned int
0x18000dfce  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000dfd3  mov     [rsp+68h+var_18], 0
0x18000dfdb  mov     [rsp+68h+var_20], 0
0x18000dfe4  mov     [rsp+68h+var_28], edi
0x18000dfe8  mov     [rsp+68h+var_30], rbx
0x18000dfed  lea     rcx, aCpointintimere_62; "CPointInTimeRestoreHelper::TerminateLog"...
0x18000dff4  mov     [rsp+68h+var_38], rcx
0x18000dff9  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000e000  mov     [rsp+68h+var_40], rcx
0x18000e005  mov     [rsp+68h+var_48], 2Fh ; '/'
0x18000e00d  xor     r9d, r9d
0x18000e010  lea     r8, aD; "D"
0x18000e017  xor     edx, edx
0x18000e019  mov     rcx, rax
0x18000e01c  call    cs:__imp_WdsSetupLogMessageW
0x18000e022  call    cs:__imp_WdsTerminate
0x18000e028  mov     rbx, [rsi+10h]
0x18000e02c  test    rbx, rbx
0x18000e02f  jz      short loc_18000E046
0x18000e031  mov     rcx, rbx; this
0x18000e034  call    ??1CPointInTimeRestoreHelper@@QEAA@XZ; CPointInTimeRestoreHelper::~CPointInTimeRestoreHelper(void)
0x18000e039  mov     edx, 10h
0x18000e03e  mov     rcx, rbx; Block
0x18000e041  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e046  mov     dword ptr [rsi+0Ch], 0C0000001h
0x18000e04d  mov     rbx, [rsp+68h+arg_0]
0x18000e052  mov     rsi, [rsp+68h+arg_8]
0x18000e057  add     rsp, 60h
0x18000e05b  pop     rdi
0x18000e05c  retn
```
