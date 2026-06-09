# CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence(int *,int *,ulong *)

- ea: `0x18000c7b8`
- end: `0x18000ca11`
- name: `?GetPointInTimeRestoreSnapshotCadence@CPointInTimeRestoreHelper@@QEAAJPEAH0PEAK@Z`
- size: `601`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, int *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000e8a0`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000c7b8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c98c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c98c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c83e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c8c2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c981`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c9fa`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c83e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c8c2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c981`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c9fa`
- `WDSCORE!CurrentIP` at `0x18000c7db`
- `WDSCORE!CurrentIP` at `0x18000c867`
- `WDSCORE!CurrentIP` at `0x18000c925`
- `WDSCORE!CurrentIP` at `0x18000c994`
- `WDSCORE!CurrentIP` at `0x18000c7db`
- `WDSCORE!CurrentIP` at `0x18000c867`
- `WDSCORE!CurrentIP` at `0x18000c925`
- `WDSCORE!CurrentIP` at `0x18000c994`

## string_xrefs

- `0x18000c7fd`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c8ab`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c947`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c9e3`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence(
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
          "Enter CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence: Getting setting cadence");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    160,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence",
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
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence: querying PITR snapshot cadence setting");
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      167,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence",
      v15,
      v14,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v17, v18);
    *a4 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)PITRSettingsInterface
                                                                                  + 64LL))(
            PITRSettingsInterface,
            5,
            v30);
    *a2 = v30[0] > 2;
    v22 = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v20, v21);
    *a3 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64))(*(_QWORD *)v22 + 88LL))(v22, 2);
  }
  else
  {
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence: PITR setting interface is unexpectedly null.");
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      174,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence",
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
          "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence: Exiting with hr=0x%08X",
          v13);
  WdsSetupLogMessageW(
    v28,
    0,
    L"D",
    0,
    181,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence",
    v27,
    v26,
    0,
    0);
  return v13;
}

```

## disassembly

```asm
0x18000c7b8  push    rbx
0x18000c7ba  push    rbp
0x18000c7bb  push    rsi
0x18000c7bc  push    rdi
0x18000c7bd  push    r12
0x18000c7bf  push    r14
0x18000c7c1  push    r15
0x18000c7c3  sub     rsp, 70h
0x18000c7c7  mov     r14, r9
0x18000c7ca  mov     r15, r8
0x18000c7cd  mov     r12, rdx
0x18000c7d0  mov     rbp, rcx
0x18000c7d3  call    cs:__imp_GetLastError
0x18000c7d9  mov     edi, eax
0x18000c7db  call    cs:__imp_CurrentIP
0x18000c7e1  lea     rdx, aEnterCpointint_0; "Enter CPointInTimeRestoreHelper::GetPoi"...
0x18000c7e8  mov     ecx, 4000000h; unsigned int
0x18000c7ed  mov     rbx, rax
0x18000c7f0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c7f5  mov     [rsp+0A8h+var_58], 0
0x18000c7fd  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c804  mov     [rsp+0A8h+var_60], 0
0x18000c80d  lea     rsi, aCpointintimere_43; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c814  mov     [rsp+0A8h+var_68], edi
0x18000c818  lea     r8, aD; "D"
0x18000c81f  mov     [rsp+0A8h+var_70], rbx
0x18000c824  xor     r9d, r9d
0x18000c827  mov     [rsp+0A8h+var_78], rsi
0x18000c82c  xor     edx, edx
0x18000c82e  mov     [rsp+0A8h+var_80], rcx
0x18000c833  mov     rcx, rax
0x18000c836  mov     [rsp+0A8h+var_88], 0A0h
0x18000c83e  call    cs:__imp_WdsSetupLogMessageW
0x18000c844  mov     rcx, rbp; this
0x18000c847  mov     [rsp+0A8h+var_48], 0
0x18000c84f  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c854  test    rax, rax
0x18000c857  jz      loc_18000C91D
0x18000c85d  xor     esi, esi
0x18000c85f  call    cs:__imp_GetLastError
0x18000c865  mov     edi, eax
0x18000c867  call    cs:__imp_CurrentIP
0x18000c86d  lea     rdx, aCpointintimere_15; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c874  mov     ecx, 4000000h; unsigned int
0x18000c879  mov     rbx, rax
0x18000c87c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c881  mov     [rsp+0A8h+var_58], esi
0x18000c885  lea     rcx, aCpointintimere_43; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c88c  mov     [rsp+0A8h+var_60], rsi
0x18000c891  lea     r8, aD; "D"
0x18000c898  mov     [rsp+0A8h+var_68], edi
0x18000c89c  xor     r9d, r9d
0x18000c89f  mov     [rsp+0A8h+var_70], rbx
0x18000c8a4  xor     edx, edx
0x18000c8a6  mov     [rsp+0A8h+var_78], rcx
0x18000c8ab  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c8b2  mov     [rsp+0A8h+var_80], rcx
0x18000c8b7  mov     rcx, rax
0x18000c8ba  mov     [rsp+0A8h+var_88], 0A7h
0x18000c8c2  call    cs:__imp_WdsSetupLogMessageW
0x18000c8c8  mov     rcx, rbp; this
0x18000c8cb  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c8d0  mov     r9, rax
0x18000c8d3  lea     r8, [rsp+0A8h+var_48]
0x18000c8d8  lea     edx, [rsi+5]
0x18000c8db  mov     rcx, [rax]
0x18000c8de  mov     rax, [rcx+40h]
0x18000c8e2  mov     rcx, r9
0x18000c8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8ea  mov     [r14], eax
0x18000c8ed  mov     rcx, rbp; this
0x18000c8f0  xor     eax, eax
0x18000c8f2  cmp     [rsp+0A8h+var_48], 2
0x18000c8f7  setnle  al
0x18000c8fa  mov     [r12], eax
0x18000c8fe  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c903  mov     r8, rax
0x18000c906  lea     edx, [rsi+2]
0x18000c909  mov     rcx, [rax]
0x18000c90c  mov     rax, [rcx+58h]
0x18000c910  mov     rcx, r8
0x18000c913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c918  mov     [r15], eax
0x18000c91b  jmp     short loc_18000C98C
0x18000c91d  call    cs:__imp_GetLastError
0x18000c923  mov     edi, eax
0x18000c925  call    cs:__imp_CurrentIP
0x18000c92b  lea     rdx, aCpointintimere_6; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c932  mov     ecx, 2000000h; unsigned int
0x18000c937  mov     rbx, rax
0x18000c93a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c93f  mov     [rsp+0A8h+var_58], 0
0x18000c947  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c94e  mov     [rsp+0A8h+var_60], 0
0x18000c957  lea     r8, aD; "D"
0x18000c95e  mov     [rsp+0A8h+var_68], edi
0x18000c962  xor     r9d, r9d
0x18000c965  mov     [rsp+0A8h+var_70], rbx
0x18000c96a  xor     edx, edx
0x18000c96c  mov     [rsp+0A8h+var_78], rsi
0x18000c971  mov     [rsp+0A8h+var_80], rcx
0x18000c976  mov     rcx, rax
0x18000c979  mov     [rsp+0A8h+var_88], 0AEh
0x18000c981  call    cs:__imp_WdsSetupLogMessageW
0x18000c987  mov     esi, 8000FFFFh
0x18000c98c  call    cs:__imp_GetLastError
0x18000c992  mov     edi, eax
0x18000c994  call    cs:__imp_CurrentIP
0x18000c99a  mov     r8d, esi
0x18000c99d  lea     rdx, aCpointintimere_47; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c9a4  mov     ecx, 4000000h; unsigned int
0x18000c9a9  mov     rbx, rax
0x18000c9ac  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c9b1  mov     [rsp+0A8h+var_58], 0
0x18000c9b9  lea     rcx, aCpointintimere_43; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c9c0  mov     [rsp+0A8h+var_60], 0
0x18000c9c9  lea     r8, aD; "D"
0x18000c9d0  mov     [rsp+0A8h+var_68], edi
0x18000c9d4  xor     r9d, r9d
0x18000c9d7  mov     [rsp+0A8h+var_70], rbx
0x18000c9dc  xor     edx, edx
0x18000c9de  mov     [rsp+0A8h+var_78], rcx
0x18000c9e3  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c9ea  mov     [rsp+0A8h+var_80], rcx
0x18000c9ef  mov     rcx, rax
0x18000c9f2  mov     [rsp+0A8h+var_88], 0B5h
0x18000c9fa  call    cs:__imp_WdsSetupLogMessageW
0x18000ca00  mov     eax, esi
0x18000ca02  add     rsp, 70h
0x18000ca06  pop     r15
0x18000ca08  pop     r14
0x18000ca0a  pop     r12
0x18000ca0c  pop     rdi
0x18000ca0d  pop     rsi
0x18000ca0e  pop     rbp
0x18000ca0f  pop     rbx
0x18000ca10  retn
```
