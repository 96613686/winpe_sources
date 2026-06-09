# CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention(int *,int *,ulong *)

- ea: `0x18000ca18`
- end: `0x18000cc77`
- name: `?GetPointInTimeRestoreSnapshotRetention@CPointInTimeRestoreHelper@@QEAAJPEAH0PEAK@Z`
- size: `607`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, int *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000e960`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000ca18`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cabf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cabf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbf2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ca9e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cb22`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cbe7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cc60`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ca9e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cb22`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cbe7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cc60`
- `WDSCORE!CurrentIP` at `0x18000ca3b`
- `WDSCORE!CurrentIP` at `0x18000cac7`
- `WDSCORE!CurrentIP` at `0x18000cb8b`
- `WDSCORE!CurrentIP` at `0x18000cbfa`
- `WDSCORE!CurrentIP` at `0x18000ca3b`
- `WDSCORE!CurrentIP` at `0x18000cac7`
- `WDSCORE!CurrentIP` at `0x18000cb8b`
- `WDSCORE!CurrentIP` at `0x18000cbfa`

## string_xrefs

- `0x18000ca5d`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000cb0b`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000cbad`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000cc49`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention(
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
          "Enter CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention: Getting snapshot retention");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    192,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention",
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
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention: querying PITR snapshot retention setting");
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      199,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention",
      v15,
      v14,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v17, v18);
    *a4 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, int *))(*(_QWORD *)PITRSettingsInterface
                                                                                  + 128LL))(
            PITRSettingsInterface,
            5,
            v30);
    *a2 = v30[0] > 2;
    v22 = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v20, v21);
    *a3 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64))(*(_QWORD *)v22 + 152LL))(v22, 2);
  }
  else
  {
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention: PITR setting interface is unexpectedly null.");
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      206,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention",
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
          "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention: Exiting with hr=0x%08X",
          v13);
  WdsSetupLogMessageW(
    v28,
    0,
    L"D",
    0,
    213,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention",
    v27,
    v26,
    0,
    0);
  return v13;
}

```

## disassembly

```asm
0x18000ca18  push    rbx
0x18000ca1a  push    rbp
0x18000ca1b  push    rsi
0x18000ca1c  push    rdi
0x18000ca1d  push    r12
0x18000ca1f  push    r14
0x18000ca21  push    r15
0x18000ca23  sub     rsp, 70h
0x18000ca27  mov     r14, r9
0x18000ca2a  mov     r15, r8
0x18000ca2d  mov     r12, rdx
0x18000ca30  mov     rbp, rcx
0x18000ca33  call    cs:__imp_GetLastError
0x18000ca39  mov     edi, eax
0x18000ca3b  call    cs:__imp_CurrentIP
0x18000ca41  lea     rdx, aEnterCpointint_3; "Enter CPointInTimeRestoreHelper::GetPoi"...
0x18000ca48  mov     ecx, 4000000h; unsigned int
0x18000ca4d  mov     rbx, rax
0x18000ca50  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ca55  mov     [rsp+0A8h+var_58], 0
0x18000ca5d  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000ca64  mov     [rsp+0A8h+var_60], 0
0x18000ca6d  lea     rsi, aCpointintimere_48; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000ca74  mov     [rsp+0A8h+var_68], edi
0x18000ca78  lea     r8, aD; "D"
0x18000ca7f  mov     [rsp+0A8h+var_70], rbx
0x18000ca84  xor     r9d, r9d
0x18000ca87  mov     [rsp+0A8h+var_78], rsi
0x18000ca8c  xor     edx, edx
0x18000ca8e  mov     [rsp+0A8h+var_80], rcx
0x18000ca93  mov     rcx, rax
0x18000ca96  mov     [rsp+0A8h+var_88], 0C0h
0x18000ca9e  call    cs:__imp_WdsSetupLogMessageW
0x18000caa4  mov     rcx, rbp; this
0x18000caa7  mov     [rsp+0A8h+var_48], 0
0x18000caaf  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000cab4  test    rax, rax
0x18000cab7  jz      loc_18000CB83
0x18000cabd  xor     esi, esi
0x18000cabf  call    cs:__imp_GetLastError
0x18000cac5  mov     edi, eax
0x18000cac7  call    cs:__imp_CurrentIP
0x18000cacd  lea     rdx, aCpointintimere_30; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cad4  mov     ecx, 4000000h; unsigned int
0x18000cad9  mov     rbx, rax
0x18000cadc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cae1  mov     [rsp+0A8h+var_58], esi
0x18000cae5  lea     rcx, aCpointintimere_48; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000caec  mov     [rsp+0A8h+var_60], rsi
0x18000caf1  lea     r8, aD; "D"
0x18000caf8  mov     [rsp+0A8h+var_68], edi
0x18000cafc  xor     r9d, r9d
0x18000caff  mov     [rsp+0A8h+var_70], rbx
0x18000cb04  xor     edx, edx
0x18000cb06  mov     [rsp+0A8h+var_78], rcx
0x18000cb0b  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000cb12  mov     [rsp+0A8h+var_80], rcx
0x18000cb17  mov     rcx, rax
0x18000cb1a  mov     [rsp+0A8h+var_88], 0C7h
0x18000cb22  call    cs:__imp_WdsSetupLogMessageW
0x18000cb28  mov     rcx, rbp; this
0x18000cb2b  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000cb30  mov     r9, rax
0x18000cb33  lea     r8, [rsp+0A8h+var_48]
0x18000cb38  lea     edx, [rsi+5]
0x18000cb3b  mov     rcx, [rax]
0x18000cb3e  mov     rax, [rcx+80h]
0x18000cb45  mov     rcx, r9
0x18000cb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb4d  mov     [r14], eax
0x18000cb50  mov     rcx, rbp; this
0x18000cb53  xor     eax, eax
0x18000cb55  cmp     [rsp+0A8h+var_48], 2
0x18000cb5a  setnle  al
0x18000cb5d  mov     [r12], eax
0x18000cb61  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000cb66  mov     r8, rax
0x18000cb69  lea     edx, [rsi+2]
0x18000cb6c  mov     rcx, [rax]
0x18000cb6f  mov     rax, [rcx+98h]
0x18000cb76  mov     rcx, r8
0x18000cb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7e  mov     [r15], eax
0x18000cb81  jmp     short loc_18000CBF2
0x18000cb83  call    cs:__imp_GetLastError
0x18000cb89  mov     edi, eax
0x18000cb8b  call    cs:__imp_CurrentIP
0x18000cb91  lea     rdx, aCpointintimere_76; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cb98  mov     ecx, 2000000h; unsigned int
0x18000cb9d  mov     rbx, rax
0x18000cba0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cba5  mov     [rsp+0A8h+var_58], 0
0x18000cbad  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000cbb4  mov     [rsp+0A8h+var_60], 0
0x18000cbbd  lea     r8, aD; "D"
0x18000cbc4  mov     [rsp+0A8h+var_68], edi
0x18000cbc8  xor     r9d, r9d
0x18000cbcb  mov     [rsp+0A8h+var_70], rbx
0x18000cbd0  xor     edx, edx
0x18000cbd2  mov     [rsp+0A8h+var_78], rsi
0x18000cbd7  mov     [rsp+0A8h+var_80], rcx
0x18000cbdc  mov     rcx, rax
0x18000cbdf  mov     [rsp+0A8h+var_88], 0CEh
0x18000cbe7  call    cs:__imp_WdsSetupLogMessageW
0x18000cbed  mov     esi, 8000FFFFh
0x18000cbf2  call    cs:__imp_GetLastError
0x18000cbf8  mov     edi, eax
0x18000cbfa  call    cs:__imp_CurrentIP
0x18000cc00  mov     r8d, esi
0x18000cc03  lea     rdx, aCpointintimere_67; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cc0a  mov     ecx, 4000000h; unsigned int
0x18000cc0f  mov     rbx, rax
0x18000cc12  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cc17  mov     [rsp+0A8h+var_58], 0
0x18000cc1f  lea     rcx, aCpointintimere_48; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cc26  mov     [rsp+0A8h+var_60], 0
0x18000cc2f  lea     r8, aD; "D"
0x18000cc36  mov     [rsp+0A8h+var_68], edi
0x18000cc3a  xor     r9d, r9d
0x18000cc3d  mov     [rsp+0A8h+var_70], rbx
0x18000cc42  xor     edx, edx
0x18000cc44  mov     [rsp+0A8h+var_78], rcx
0x18000cc49  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000cc50  mov     [rsp+0A8h+var_80], rcx
0x18000cc55  mov     rcx, rax
0x18000cc58  mov     [rsp+0A8h+var_88], 0D5h
0x18000cc60  call    cs:__imp_WdsSetupLogMessageW
0x18000cc66  mov     eax, esi
0x18000cc68  add     rsp, 70h
0x18000cc6c  pop     r15
0x18000cc6e  pop     r14
0x18000cc70  pop     r12
0x18000cc72  pop     rdi
0x18000cc73  pop     rsi
0x18000cc74  pop     rbp
0x18000cc75  pop     rbx
0x18000cc76  retn
```
