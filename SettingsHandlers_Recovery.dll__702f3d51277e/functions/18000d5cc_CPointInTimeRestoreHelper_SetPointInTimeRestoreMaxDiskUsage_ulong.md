# CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage(ulong)

- ea: `0x18000d5cc`
- end: `0x18000d826`
- name: `?SetPointInTimeRestoreMaxDiskUsage@CPointInTimeRestoreHelper@@QEAAJK@Z`
- size: `602`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000ece0`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000d5cc`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7b3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d651`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d6c4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d7ad`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d80f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d651`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d6c4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d7ad`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d80f`
- `WDSCORE!CurrentIP` at `0x18000d5e8`
- `WDSCORE!CurrentIP` at `0x18000d670`
- `WDSCORE!CurrentIP` at `0x18000d701`
- `WDSCORE!CurrentIP` at `0x18000d759`
- `WDSCORE!CurrentIP` at `0x18000d7bb`
- `WDSCORE!CurrentIP` at `0x18000d5e8`
- `WDSCORE!CurrentIP` at `0x18000d670`
- `WDSCORE!CurrentIP` at `0x18000d701`
- `WDSCORE!CurrentIP` at `0x18000d759`
- `WDSCORE!CurrentIP` at `0x18000d7bb`

## string_xrefs

- `0x18000d61d`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage(
        CPointInTimeRestoreHelper *this,
        unsigned int a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  struct PITR::IPITRSettings *PITRSettingsInterface; // rax
  int v11; // esi
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "Enter CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage: setting PITR max disk usage to %d MB",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    509,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage",
    v5,
    LastError,
    0,
    0);
  if ( CPointInTimeRestoreHelper::GetPITRSettingsInterface(this) )
  {
    v7 = GetLastError();
    v8 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x4000000u,
           "CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage: Setting snapshot disk usage limit to %d MB",
           a2);
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      515,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage",
      v8,
      v7,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this);
    v11 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, _QWORD))(*(_QWORD *)PITRSettingsInterface
                                                                                   + 168LL))(
            PITRSettingsInterface,
            2,
            a2);
    if ( v11 < 0 )
    {
      v12 = GetLastError();
      v13 = CurrentIP();
      v14 = ConstructPartialMsgW(
              0x2000000u,
              "CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage: Failed to set PITR snapshot disk usage limit. hr=0x%08X",
              v11);
      WdsSetupLogMessageW(
        v14,
        0,
        L"D",
        0,
        519,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
        L"CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage",
        v13,
        v12,
        0,
        0);
    }
  }
  else
  {
    v11 = -2147418113;
    v15 = GetLastError();
    v16 = CurrentIP();
    v17 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage: PITR setting interface is unexpectedly null. hr=0x%08X",
            -2147418113);
    WdsSetupLogMessageW(
      v17,
      0,
      L"D",
      0,
      526,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage",
      v16,
      v15,
      0,
      0);
  }
  v18 = GetLastError();
  v19 = CurrentIP();
  v20 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage: Exiting with hr=0x%08X",
          v11);
  WdsSetupLogMessageW(
    v20,
    0,
    L"D",
    0,
    532,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage",
    v19,
    v18,
    0,
    0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d5cc  push    rbx
0x18000d5ce  push    rbp
0x18000d5cf  push    rsi
0x18000d5d0  push    rdi
0x18000d5d1  push    r12
0x18000d5d3  push    r13
0x18000d5d5  push    r15
0x18000d5d7  sub     rsp, 60h
0x18000d5db  mov     esi, edx
0x18000d5dd  mov     rbp, rcx
0x18000d5e0  call    cs:__imp_GetLastError
0x18000d5e6  mov     edi, eax
0x18000d5e8  call    cs:__imp_CurrentIP
0x18000d5ee  mov     r8d, esi
0x18000d5f1  lea     rdx, aEnterCpointint_6; "Enter CPointInTimeRestoreHelper::SetPoi"...
0x18000d5f8  mov     ecx, 4000000h; unsigned int
0x18000d5fd  mov     rbx, rax
0x18000d600  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d605  mov     [rsp+98h+var_48], 0
0x18000d60d  lea     r12, aCpointintimere_27; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d614  mov     [rsp+98h+var_50], 0
0x18000d61d  lea     r13, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000d624  mov     [rsp+98h+var_58], edi
0x18000d628  lea     r15, aD; "D"
0x18000d62f  mov     [rsp+98h+var_60], rbx
0x18000d634  xor     r9d, r9d
0x18000d637  mov     [rsp+98h+var_68], r12
0x18000d63c  mov     r8, r15
0x18000d63f  mov     [rsp+98h+var_70], r13
0x18000d644  xor     edx, edx
0x18000d646  mov     rcx, rax
0x18000d649  mov     [rsp+98h+var_78], 1FDh
0x18000d651  call    cs:__imp_WdsSetupLogMessageW
0x18000d657  mov     rcx, rbp; this
0x18000d65a  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000d65f  test    rax, rax
0x18000d662  jz      loc_18000D74C
0x18000d668  call    cs:__imp_GetLastError
0x18000d66e  mov     edi, eax
0x18000d670  call    cs:__imp_CurrentIP
0x18000d676  mov     r8d, esi
0x18000d679  lea     rdx, aCpointintimere_5; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d680  mov     ecx, 4000000h; unsigned int
0x18000d685  mov     rbx, rax
0x18000d688  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d68d  mov     [rsp+98h+var_48], 0
0x18000d695  xor     r9d, r9d
0x18000d698  mov     [rsp+98h+var_50], 0
0x18000d6a1  mov     r8, r15
0x18000d6a4  mov     [rsp+98h+var_58], edi
0x18000d6a8  xor     edx, edx
0x18000d6aa  mov     [rsp+98h+var_60], rbx
0x18000d6af  mov     rcx, rax
0x18000d6b2  mov     [rsp+98h+var_68], r12
0x18000d6b7  mov     [rsp+98h+var_70], r13
0x18000d6bc  mov     [rsp+98h+var_78], 203h
0x18000d6c4  call    cs:__imp_WdsSetupLogMessageW
0x18000d6ca  mov     rcx, rbp; this
0x18000d6cd  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000d6d2  mov     r9, rax
0x18000d6d5  mov     r8d, esi
0x18000d6d8  mov     edx, 2
0x18000d6dd  mov     rcx, [rax]
0x18000d6e0  mov     rax, [rcx+0A8h]
0x18000d6e7  mov     rcx, r9
0x18000d6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ef  mov     esi, eax
0x18000d6f1  test    eax, eax
0x18000d6f3  jns     loc_18000D7B3
0x18000d6f9  call    cs:__imp_GetLastError
0x18000d6ff  mov     edi, eax
0x18000d701  call    cs:__imp_CurrentIP
0x18000d707  mov     r8d, esi
0x18000d70a  lea     rdx, aCpointintimere_75; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d711  mov     ecx, 2000000h; unsigned int
0x18000d716  mov     rbx, rax
0x18000d719  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d71e  mov     [rsp+98h+var_48], 0
0x18000d726  mov     [rsp+98h+var_50], 0
0x18000d72f  mov     [rsp+98h+var_58], edi
0x18000d733  mov     [rsp+98h+var_60], rbx
0x18000d738  mov     [rsp+98h+var_68], r12
0x18000d73d  mov     [rsp+98h+var_70], r13
0x18000d742  mov     [rsp+98h+var_78], 207h
0x18000d74a  jmp     short loc_18000D7A2
0x18000d74c  mov     esi, 8000FFFFh
0x18000d751  call    cs:__imp_GetLastError
0x18000d757  mov     edi, eax
0x18000d759  call    cs:__imp_CurrentIP
0x18000d75f  mov     r8d, esi
0x18000d762  lea     rdx, aCpointintimere_34; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d769  mov     ecx, 2000000h; unsigned int
0x18000d76e  mov     rbx, rax
0x18000d771  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d776  mov     [rsp+98h+var_48], 0
0x18000d77e  mov     [rsp+98h+var_50], 0
0x18000d787  mov     [rsp+98h+var_58], edi
0x18000d78b  mov     [rsp+98h+var_60], rbx
0x18000d790  mov     [rsp+98h+var_68], r12
0x18000d795  mov     [rsp+98h+var_70], r13
0x18000d79a  mov     [rsp+98h+var_78], 20Eh
0x18000d7a2  xor     r9d, r9d
0x18000d7a5  mov     r8, r15
0x18000d7a8  xor     edx, edx
0x18000d7aa  mov     rcx, rax
0x18000d7ad  call    cs:__imp_WdsSetupLogMessageW
0x18000d7b3  call    cs:__imp_GetLastError
0x18000d7b9  mov     edi, eax
0x18000d7bb  call    cs:__imp_CurrentIP
0x18000d7c1  mov     r8d, esi
0x18000d7c4  lea     rdx, aCpointintimere_64; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d7cb  mov     ecx, 4000000h; unsigned int
0x18000d7d0  mov     rbx, rax
0x18000d7d3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d7d8  mov     [rsp+98h+var_48], 0
0x18000d7e0  xor     r9d, r9d
0x18000d7e3  mov     [rsp+98h+var_50], 0
0x18000d7ec  mov     r8, r15
0x18000d7ef  mov     [rsp+98h+var_58], edi
0x18000d7f3  xor     edx, edx
0x18000d7f5  mov     [rsp+98h+var_60], rbx
0x18000d7fa  mov     rcx, rax
0x18000d7fd  mov     [rsp+98h+var_68], r12
0x18000d802  mov     [rsp+98h+var_70], r13
0x18000d807  mov     [rsp+98h+var_78], 214h
0x18000d80f  call    cs:__imp_WdsSetupLogMessageW
0x18000d815  mov     eax, esi
0x18000d817  add     rsp, 60h
0x18000d81b  pop     r15
0x18000d81d  pop     r13
0x18000d81f  pop     r12
0x18000d821  pop     rdi
0x18000d822  pop     rsi
0x18000d823  pop     rbp
0x18000d824  pop     rbx
0x18000d825  retn
```
