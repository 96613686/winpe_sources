# CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive(int *,int *,int *)

- ea: `0x18000c2f0`
- end: `0x18000c548`
- name: `?GetPointInTimeRestoreFeatureActive@CPointInTimeRestoreHelper@@QEAAJPEAH00@Z`
- size: `600`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, int *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000e720`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000c2f0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c30b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c30b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4c3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c376`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c3fa`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c4b8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c531`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c376`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c3fa`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c4b8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c531`
- `WDSCORE!CurrentIP` at `0x18000c313`
- `WDSCORE!CurrentIP` at `0x18000c39f`
- `WDSCORE!CurrentIP` at `0x18000c45c`
- `WDSCORE!CurrentIP` at `0x18000c4cb`
- `WDSCORE!CurrentIP` at `0x18000c313`
- `WDSCORE!CurrentIP` at `0x18000c39f`
- `WDSCORE!CurrentIP` at `0x18000c45c`
- `WDSCORE!CurrentIP` at `0x18000c4cb`

## string_xrefs

- `0x18000c335`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c3e3`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c47e`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000c51a`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive(
        CPointInTimeRestoreHelper *this,
        int *a2,
        int *a3,
        int *a4)
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
          "Enter CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive: Getting feature active");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    128,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive",
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
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive: Querying feature active");
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      135,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive",
      v15,
      v14,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v17, v18);
    *a4 = (**(__int64 (__fastcall ***)(struct PITR::IPITRSettings *, __int64, int *))PITRSettingsInterface)(
            PITRSettingsInterface,
            5,
            v30);
    *a2 = v30[0] > 2;
    v22 = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this, v20, v21);
    *a3 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64))(*(_QWORD *)v22 + 24LL))(v22, 2);
  }
  else
  {
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive: PITR setting interface is unexpectedly null.");
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      142,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive",
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
          "CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive: Exiting with hr=0x%08X",
          v13);
  WdsSetupLogMessageW(
    v28,
    0,
    L"D",
    0,
    149,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive",
    v27,
    v26,
    0,
    0);
  return v13;
}

```

## disassembly

```asm
0x18000c2f0  push    rbx
0x18000c2f2  push    rbp
0x18000c2f3  push    rsi
0x18000c2f4  push    rdi
0x18000c2f5  push    r12
0x18000c2f7  push    r14
0x18000c2f9  push    r15
0x18000c2fb  sub     rsp, 70h
0x18000c2ff  mov     r14, r9
0x18000c302  mov     r15, r8
0x18000c305  mov     r12, rdx
0x18000c308  mov     rbp, rcx
0x18000c30b  call    cs:__imp_GetLastError
0x18000c311  mov     edi, eax
0x18000c313  call    cs:__imp_CurrentIP
0x18000c319  lea     rdx, aEnterCpointint_2; "Enter CPointInTimeRestoreHelper::GetPoi"...
0x18000c320  mov     ecx, 4000000h; unsigned int
0x18000c325  mov     rbx, rax
0x18000c328  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c32d  mov     [rsp+0A8h+var_58], 0
0x18000c335  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c33c  mov     [rsp+0A8h+var_60], 0
0x18000c345  lea     rsi, aCpointintimere_22; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c34c  mov     [rsp+0A8h+var_68], edi
0x18000c350  lea     r8, aD; "D"
0x18000c357  mov     [rsp+0A8h+var_70], rbx
0x18000c35c  xor     r9d, r9d
0x18000c35f  mov     [rsp+0A8h+var_78], rsi
0x18000c364  xor     edx, edx
0x18000c366  mov     [rsp+0A8h+var_80], rcx
0x18000c36b  mov     rcx, rax
0x18000c36e  mov     [rsp+0A8h+var_88], 80h
0x18000c376  call    cs:__imp_WdsSetupLogMessageW
0x18000c37c  mov     rcx, rbp; this
0x18000c37f  mov     [rsp+0A8h+var_48], 0
0x18000c387  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c38c  test    rax, rax
0x18000c38f  jz      loc_18000C454
0x18000c395  xor     esi, esi
0x18000c397  call    cs:__imp_GetLastError
0x18000c39d  mov     edi, eax
0x18000c39f  call    cs:__imp_CurrentIP
0x18000c3a5  lea     rdx, aCpointintimere_68; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c3ac  mov     ecx, 4000000h; unsigned int
0x18000c3b1  mov     rbx, rax
0x18000c3b4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c3b9  mov     [rsp+0A8h+var_58], esi
0x18000c3bd  lea     rcx, aCpointintimere_22; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c3c4  mov     [rsp+0A8h+var_60], rsi
0x18000c3c9  lea     r8, aD; "D"
0x18000c3d0  mov     [rsp+0A8h+var_68], edi
0x18000c3d4  xor     r9d, r9d
0x18000c3d7  mov     [rsp+0A8h+var_70], rbx
0x18000c3dc  xor     edx, edx
0x18000c3de  mov     [rsp+0A8h+var_78], rcx
0x18000c3e3  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c3ea  mov     [rsp+0A8h+var_80], rcx
0x18000c3ef  mov     rcx, rax
0x18000c3f2  mov     [rsp+0A8h+var_88], 87h
0x18000c3fa  call    cs:__imp_WdsSetupLogMessageW
0x18000c400  mov     rcx, rbp; this
0x18000c403  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c408  mov     r9, rax
0x18000c40b  lea     r8, [rsp+0A8h+var_48]
0x18000c410  lea     edx, [rsi+5]
0x18000c413  mov     rcx, [rax]
0x18000c416  mov     rax, [rcx]
0x18000c419  mov     rcx, r9
0x18000c41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c421  mov     [r14], eax
0x18000c424  mov     rcx, rbp; this
0x18000c427  xor     eax, eax
0x18000c429  cmp     [rsp+0A8h+var_48], 2
0x18000c42e  setnle  al
0x18000c431  mov     [r12], eax
0x18000c435  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000c43a  mov     r8, rax
0x18000c43d  lea     edx, [rsi+2]
0x18000c440  mov     rcx, [rax]
0x18000c443  mov     rax, [rcx+18h]
0x18000c447  mov     rcx, r8
0x18000c44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c44f  mov     [r15], eax
0x18000c452  jmp     short loc_18000C4C3
0x18000c454  call    cs:__imp_GetLastError
0x18000c45a  mov     edi, eax
0x18000c45c  call    cs:__imp_CurrentIP
0x18000c462  lea     rdx, aCpointintimere_16; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c469  mov     ecx, 2000000h; unsigned int
0x18000c46e  mov     rbx, rax
0x18000c471  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c476  mov     [rsp+0A8h+var_58], 0
0x18000c47e  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c485  mov     [rsp+0A8h+var_60], 0
0x18000c48e  lea     r8, aD; "D"
0x18000c495  mov     [rsp+0A8h+var_68], edi
0x18000c499  xor     r9d, r9d
0x18000c49c  mov     [rsp+0A8h+var_70], rbx
0x18000c4a1  xor     edx, edx
0x18000c4a3  mov     [rsp+0A8h+var_78], rsi
0x18000c4a8  mov     [rsp+0A8h+var_80], rcx
0x18000c4ad  mov     rcx, rax
0x18000c4b0  mov     [rsp+0A8h+var_88], 8Eh
0x18000c4b8  call    cs:__imp_WdsSetupLogMessageW
0x18000c4be  mov     esi, 8000FFFFh
0x18000c4c3  call    cs:__imp_GetLastError
0x18000c4c9  mov     edi, eax
0x18000c4cb  call    cs:__imp_CurrentIP
0x18000c4d1  mov     r8d, esi
0x18000c4d4  lea     rdx, aCpointintimere_19; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c4db  mov     ecx, 4000000h; unsigned int
0x18000c4e0  mov     rbx, rax
0x18000c4e3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c4e8  mov     [rsp+0A8h+var_58], 0
0x18000c4f0  lea     rcx, aCpointintimere_22; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c4f7  mov     [rsp+0A8h+var_60], 0
0x18000c500  lea     r8, aD; "D"
0x18000c507  mov     [rsp+0A8h+var_68], edi
0x18000c50b  xor     r9d, r9d
0x18000c50e  mov     [rsp+0A8h+var_70], rbx
0x18000c513  xor     edx, edx
0x18000c515  mov     [rsp+0A8h+var_78], rcx
0x18000c51a  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c521  mov     [rsp+0A8h+var_80], rcx
0x18000c526  mov     rcx, rax
0x18000c529  mov     [rsp+0A8h+var_88], 95h
0x18000c531  call    cs:__imp_WdsSetupLogMessageW
0x18000c537  mov     eax, esi
0x18000c539  add     rsp, 70h
0x18000c53d  pop     r15
0x18000c53f  pop     r14
0x18000c541  pop     r12
0x18000c543  pop     rdi
0x18000c544  pop     rsi
0x18000c545  pop     rbp
0x18000c546  pop     rbx
0x18000c547  retn
```
