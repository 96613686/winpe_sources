# CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage(int *,int *,ulong *)

- ea: `0x18000c550`
- end: `0x18000c7af`
- name: `?GetPointInTimeRestoreMaxDiskUsage@CPointInTimeRestoreHelper@@QEAAJPEAH0PEAK@Z`
- size: `607`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, int *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000e7e0`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000c550`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c56b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c56b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c72a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c5d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c65a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c71f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c798`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c5d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c65a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c71f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c798`
- `WDSCORE!CurrentIP` at `0x18000c573`
- `WDSCORE!CurrentIP` at `0x18000c5ff`
- `WDSCORE!CurrentIP` at `0x18000c6c3`
- `WDSCORE!CurrentIP` at `0x18000c732`
- `WDSCORE!CurrentIP` at `0x18000c573`
- `WDSCORE!CurrentIP` at `0x18000c5ff`
- `WDSCORE!CurrentIP` at `0x18000c6c3`
- `WDSCORE!CurrentIP` at `0x18000c732`

## string_xrefs

- `0x18000c595`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c643`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c6e5`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c781`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage(
        CPointInTimeRestoreHelper *this,
        int *a2,
        int *a3,
        unsigned int *a4)
{
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  __int64 v11; // rdx
  struct PITR::IPITRBase **v12; // r8
  unsigned int v13; // esi
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  __int64 v17; // rdx
  struct PITR::IPITRBase **v18; // r8
  struct PITR::IPITRSettings *PITRSettingsInterface; // rax
  __int64 v20; // rdx
  struct PITR::IPITRBase **v21; // r8
  struct PITR::IPITRSettings *v22; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  int v30[18]; // [rsp+60h] [rbp-48h] BYREF

  LastError = GetLastError();
  v9 = CurrentIP();
  v10 = ConstructPartialMsgW(
          0x4000000u,
          "Enter CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage: Getting max disk usage");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    224,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage",
    v9,
    LastError,
    0,
    0);
  v30[0] = 0;
  if ( CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v11, v12) )
  {
    v13 = 0;
    v14 = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(
            0x4000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage: querying PITR maximum disk usage setting");
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      231,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage",
      v15,
      v14,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v17, v18);
    *a4 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)PITRSettingsInterface
                                                                                  + 160LL))(
            PITRSettingsInterface,
            5,
            v30);
    *a2 = v30[0] > 2;
    v22 = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v20, v21);
    *a3 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64))(*(_QWORD *)v22 + 184LL))(v22, 2);
  }
  else
  {
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage: PITR setting interface is unexpectedly null.");
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      238,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage",
      v24,
      v23,
      0,
      0);
    v13 = -2147418113;
  }
  v26 = GetLastError();
  v27 = CurrentIP();
  v28 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage: Exiting with hr=0x%08X",
          v13);
  WdsSetupLogMessageW(
    v28,
    0,
    L"D",
    0,
    245,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage",
    v27,
    v26,
    0,
    0);
  return v13;
}

```

## disassembly

```asm
0x18000c550  push    rbx
0x18000c552  push    rbp
0x18000c553  push    rsi
0x18000c554  push    rdi
0x18000c555  push    r12
0x18000c557  push    r14
0x18000c559  push    r15
0x18000c55b  sub     rsp, 70h
0x18000c55f  mov     r14, r9
0x18000c562  mov     r15, r8
0x18000c565  mov     r12, rdx
0x18000c568  mov     rbp, rcx
0x18000c56b  call    cs:__imp_GetLastError
0x18000c571  mov     edi, eax
0x18000c573  call    cs:__imp_CurrentIP
0x18000c579  lea     rdx, aEnterCpointint; "Enter CPointInTimeRestoreHelper::GetPoi"...
0x18000c580  mov     ecx, 4000000h; unsigned int
0x18000c585  mov     rbx, rax
0x18000c588  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c58d  mov     [rsp+0A8h+var_58], 0
0x18000c595  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c59c  mov     [rsp+0A8h+var_60], 0
0x18000c5a5  lea     rsi, aCpointintimere_11; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c5ac  mov     [rsp+0A8h+var_68], edi
0x18000c5b0  lea     r8, aD; "D"
0x18000c5b7  mov     [rsp+0A8h+var_70], rbx
0x18000c5bc  xor     r9d, r9d
0x18000c5bf  mov     [rsp+0A8h+var_78], rsi
0x18000c5c4  xor     edx, edx
0x18000c5c6  mov     [rsp+0A8h+var_80], rcx
0x18000c5cb  mov     rcx, rax
0x18000c5ce  mov     [rsp+0A8h+var_88], 0E0h
0x18000c5d6  call    cs:__imp_WdsSetupLogMessageW
0x18000c5dc  mov     rcx, rbp; this
0x18000c5df  mov     [rsp+0A8h+var_48], 0
0x18000c5e7  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c5ec  test    rax, rax
0x18000c5ef  jz      loc_18000C6BB
0x18000c5f5  xor     esi, esi
0x18000c5f7  call    cs:__imp_GetLastError
0x18000c5fd  mov     edi, eax
0x18000c5ff  call    cs:__imp_CurrentIP
0x18000c605  lea     rdx, aCpointintimere_52; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c60c  mov     ecx, 4000000h; unsigned int
0x18000c611  mov     rbx, rax
0x18000c614  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c619  mov     [rsp+0A8h+var_58], esi
0x18000c61d  lea     rcx, aCpointintimere_11; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c624  mov     [rsp+0A8h+var_60], rsi
0x18000c629  lea     r8, aD; "D"
0x18000c630  mov     [rsp+0A8h+var_68], edi
0x18000c634  xor     r9d, r9d
0x18000c637  mov     [rsp+0A8h+var_70], rbx
0x18000c63c  xor     edx, edx
0x18000c63e  mov     [rsp+0A8h+var_78], rcx
0x18000c643  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c64a  mov     [rsp+0A8h+var_80], rcx
0x18000c64f  mov     rcx, rax
0x18000c652  mov     [rsp+0A8h+var_88], 0E7h
0x18000c65a  call    cs:__imp_WdsSetupLogMessageW
0x18000c660  mov     rcx, rbp; this
0x18000c663  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c668  mov     r9, rax
0x18000c66b  lea     r8, [rsp+0A8h+var_48]
0x18000c670  lea     edx, [rsi+5]
0x18000c673  mov     rcx, [rax]
0x18000c676  mov     rax, [rcx+0A0h]
0x18000c67d  mov     rcx, r9
0x18000c680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c685  mov     [r14], eax
0x18000c688  mov     rcx, rbp; this
0x18000c68b  xor     eax, eax
0x18000c68d  cmp     [rsp+0A8h+var_48], 2
0x18000c692  setnle  al
0x18000c695  mov     [r12], eax
0x18000c699  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c69e  mov     r8, rax
0x18000c6a1  lea     edx, [rsi+2]
0x18000c6a4  mov     rcx, [rax]
0x18000c6a7  mov     rax, [rcx+0B8h]
0x18000c6ae  mov     rcx, r8
0x18000c6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b6  mov     [r15], eax
0x18000c6b9  jmp     short loc_18000C72A
0x18000c6bb  call    cs:__imp_GetLastError
0x18000c6c1  mov     edi, eax
0x18000c6c3  call    cs:__imp_CurrentIP
0x18000c6c9  lea     rdx, aCpointintimere_44; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c6d0  mov     ecx, 2000000h; unsigned int
0x18000c6d5  mov     rbx, rax
0x18000c6d8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c6dd  mov     [rsp+0A8h+var_58], 0
0x18000c6e5  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c6ec  mov     [rsp+0A8h+var_60], 0
0x18000c6f5  lea     r8, aD; "D"
0x18000c6fc  mov     [rsp+0A8h+var_68], edi
0x18000c700  xor     r9d, r9d
0x18000c703  mov     [rsp+0A8h+var_70], rbx
0x18000c708  xor     edx, edx
0x18000c70a  mov     [rsp+0A8h+var_78], rsi
0x18000c70f  mov     [rsp+0A8h+var_80], rcx
0x18000c714  mov     rcx, rax
0x18000c717  mov     [rsp+0A8h+var_88], 0EEh
0x18000c71f  call    cs:__imp_WdsSetupLogMessageW
0x18000c725  mov     esi, 8000FFFFh
0x18000c72a  call    cs:__imp_GetLastError
0x18000c730  mov     edi, eax
0x18000c732  call    cs:__imp_CurrentIP
0x18000c738  mov     r8d, esi
0x18000c73b  lea     rdx, aCpointintimere_18; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c742  mov     ecx, 4000000h; unsigned int
0x18000c747  mov     rbx, rax
0x18000c74a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c74f  mov     [rsp+0A8h+var_58], 0
0x18000c757  lea     rcx, aCpointintimere_11; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c75e  mov     [rsp+0A8h+var_60], 0
0x18000c767  lea     r8, aD; "D"
0x18000c76e  mov     [rsp+0A8h+var_68], edi
0x18000c772  xor     r9d, r9d
0x18000c775  mov     [rsp+0A8h+var_70], rbx
0x18000c77a  xor     edx, edx
0x18000c77c  mov     [rsp+0A8h+var_78], rcx
0x18000c781  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c788  mov     [rsp+0A8h+var_80], rcx
0x18000c78d  mov     rcx, rax
0x18000c790  mov     [rsp+0A8h+var_88], 0F5h
0x18000c798  call    cs:__imp_WdsSetupLogMessageW
0x18000c79e  mov     eax, esi
0x18000c7a0  add     rsp, 70h
0x18000c7a4  pop     r15
0x18000c7a6  pop     r14
0x18000c7a8  pop     r12
0x18000c7aa  pop     rdi
0x18000c7ab  pop     rsi
0x18000c7ac  pop     rbp
0x18000c7ad  pop     rbx
0x18000c7ae  retn
```
