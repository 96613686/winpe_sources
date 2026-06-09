# CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage(__int64 *)

- ea: `0x18000c0a4`
- end: `0x18000c2e8`
- name: `?GetPointInTimeRestoreCurrentDiskUsage@CPointInTimeRestoreHelper@@QEAAJPEA_J@Z`
- size: `580`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000e670`

## callees

- `0x18000bef4`
- `0x18000bf24`
- `0x18000c0a4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c13d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c26b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c13d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c26b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c126`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c19a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c260`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c2cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c126`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c19a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c260`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c2cb`
- `WDSCORE!CurrentIP` at `0x18000c0c3`
- `WDSCORE!CurrentIP` at `0x18000c145`
- `WDSCORE!CurrentIP` at `0x18000c20b`
- `WDSCORE!CurrentIP` at `0x18000c273`
- `WDSCORE!CurrentIP` at `0x18000c0c3`
- `WDSCORE!CurrentIP` at `0x18000c145`
- `WDSCORE!CurrentIP` at `0x18000c20b`
- `WDSCORE!CurrentIP` at `0x18000c273`

## string_xrefs

- `0x18000c0f5`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage(
        CPointInTimeRestoreHelper *this,
        __int64 *a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  __int64 v7; // rdx
  struct PITR::IPITRBase **v8; // r8
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  __int64 v12; // rdx
  struct PITR::IPITRBase **v13; // r8
  struct PITR::IPITRBase *PITRBaseInterface; // rax
  int v15; // esi
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  _QWORD v23[7]; // [rsp+60h] [rbp-38h] BYREF
  __int64 v24; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+20h] BYREF

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(0x4000000u, "Enter CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage");
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    92,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage",
    v5,
    LastError,
    0,
    0);
  if ( CPointInTimeRestoreHelper::GetPITRBaseInterface(this, v7, v8) )
  {
    v9 = GetLastError();
    v10 = CurrentIP();
    v11 = ConstructPartialMsgW(
            0x4000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage: getting PITR snapshot enumerator");
    WdsSetupLogMessageW(
      v11,
      0,
      L"D",
      0,
      99,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage",
      v10,
      v9,
      0,
      0);
    v24 = 0;
    v23[0] = 0;
    v25 = 0;
    PITRBaseInterface = CPointInTimeRestoreHelper::GetPITRBaseInterface(this, v12, v13);
    v15 = (*(__int64 (__fastcall **)(struct PITR::IPITRBase *, __int64 *, _QWORD *, __int64 *))(*(_QWORD *)PITRBaseInterface
                                                                                              + 40LL))(
            PITRBaseInterface,
            &v24,
            v23,
            &v25);
    if ( v15 >= 0 )
      *a2 = v24;
  }
  else
  {
    v16 = GetLastError();
    v17 = CurrentIP();
    v18 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage: PITR base interface is unexpectedly null.");
    WdsSetupLogMessageW(
      v18,
      0,
      L"D",
      0,
      111,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage",
      v17,
      v16,
      0,
      0);
    v15 = -2147418113;
  }
  v19 = GetLastError();
  v20 = CurrentIP();
  v21 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage: Exiting with hr=0x%08X",
          v15);
  WdsSetupLogMessageW(
    v21,
    0,
    L"D",
    0,
    117,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage",
    v20,
    v19,
    0,
    0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000c0a4  mov     [rsp+arg_0], rbx
0x18000c0a9  push    rsi
0x18000c0aa  push    rdi
0x18000c0ab  push    r12
0x18000c0ad  push    r13
0x18000c0af  push    r14
0x18000c0b1  sub     rsp, 70h
0x18000c0b5  mov     r14, rdx
0x18000c0b8  mov     rsi, rcx
0x18000c0bb  call    cs:__imp_GetLastError
0x18000c0c1  mov     edi, eax
0x18000c0c3  call    cs:__imp_CurrentIP
0x18000c0c9  lea     rdx, aEnterCpointint_7; "Enter CPointInTimeRestoreHelper::GetPoi"...
0x18000c0d0  mov     ecx, 4000000h; unsigned int
0x18000c0d5  mov     rbx, rax
0x18000c0d8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c0dd  mov     [rsp+98h+var_48], 0
0x18000c0e5  lea     r12, aCpointintimere_33; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c0ec  mov     [rsp+98h+var_50], 0
0x18000c0f5  lea     r13, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c0fc  mov     [rsp+98h+var_58], edi
0x18000c100  lea     r8, aD; "D"
0x18000c107  mov     [rsp+98h+var_60], rbx
0x18000c10c  xor     r9d, r9d
0x18000c10f  mov     [rsp+98h+var_68], r12
0x18000c114  xor     edx, edx
0x18000c116  mov     [rsp+98h+var_70], r13
0x18000c11b  mov     rcx, rax
0x18000c11e  mov     [rsp+98h+var_78], 5Ch ; '\'
0x18000c126  call    cs:__imp_WdsSetupLogMessageW
0x18000c12c  mov     rcx, rsi; this
0x18000c12f  call    ?GetPITRBaseInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRBase@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRBaseInterface(void)
0x18000c134  test    rax, rax
0x18000c137  jz      loc_18000C203
0x18000c13d  call    cs:__imp_GetLastError
0x18000c143  mov     edi, eax
0x18000c145  call    cs:__imp_CurrentIP
0x18000c14b  lea     rdx, aCpointintimere_74; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c152  mov     ecx, 4000000h; unsigned int
0x18000c157  mov     rbx, rax
0x18000c15a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c15f  mov     [rsp+98h+var_48], 0
0x18000c167  lea     r8, aD; "D"
0x18000c16e  mov     [rsp+98h+var_50], 0
0x18000c177  xor     r9d, r9d
0x18000c17a  mov     [rsp+98h+var_58], edi
0x18000c17e  xor     edx, edx
0x18000c180  mov     [rsp+98h+var_60], rbx
0x18000c185  mov     rcx, rax
0x18000c188  mov     [rsp+98h+var_68], r12
0x18000c18d  mov     [rsp+98h+var_70], r13
0x18000c192  mov     [rsp+98h+var_78], 63h ; 'c'
0x18000c19a  call    cs:__imp_WdsSetupLogMessageW
0x18000c1a0  mov     rcx, rsi; this
0x18000c1a3  mov     [rsp+98h+arg_10], 0
0x18000c1af  mov     [rsp+98h+var_38], 0
0x18000c1b8  mov     [rsp+98h+arg_18], 0
0x18000c1c4  call    ?GetPITRBaseInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRBase@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRBaseInterface(void)
0x18000c1c9  mov     r10, rax
0x18000c1cc  lea     r9, [rsp+98h+arg_18]
0x18000c1d4  lea     r8, [rsp+98h+var_38]
0x18000c1d9  lea     rdx, [rsp+98h+arg_10]
0x18000c1e1  mov     rcx, [rax]
0x18000c1e4  mov     rax, [rcx+28h]
0x18000c1e8  mov     rcx, r10
0x18000c1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f0  mov     esi, eax
0x18000c1f2  test    eax, eax
0x18000c1f4  js      short loc_18000C26B
0x18000c1f6  mov     rcx, [rsp+98h+arg_10]
0x18000c1fe  mov     [r14], rcx
0x18000c201  jmp     short loc_18000C26B
0x18000c203  call    cs:__imp_GetLastError
0x18000c209  mov     edi, eax
0x18000c20b  call    cs:__imp_CurrentIP
0x18000c211  lea     rdx, aCpointintimere_21; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c218  mov     ecx, 2000000h; unsigned int
0x18000c21d  mov     rbx, rax
0x18000c220  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c225  mov     [rsp+98h+var_48], 0
0x18000c22d  lea     r8, aD; "D"
0x18000c234  mov     [rsp+98h+var_50], 0
0x18000c23d  xor     r9d, r9d
0x18000c240  mov     [rsp+98h+var_58], edi
0x18000c244  xor     edx, edx
0x18000c246  mov     [rsp+98h+var_60], rbx
0x18000c24b  mov     rcx, rax
0x18000c24e  mov     [rsp+98h+var_68], r12
0x18000c253  mov     [rsp+98h+var_70], r13
0x18000c258  mov     [rsp+98h+var_78], 6Fh ; 'o'
0x18000c260  call    cs:__imp_WdsSetupLogMessageW
0x18000c266  mov     esi, 8000FFFFh
0x18000c26b  call    cs:__imp_GetLastError
0x18000c271  mov     edi, eax
0x18000c273  call    cs:__imp_CurrentIP
0x18000c279  mov     r8d, esi
0x18000c27c  lea     rdx, aCpointintimere_58; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000c283  mov     ecx, 4000000h; unsigned int
0x18000c288  mov     rbx, rax
0x18000c28b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c290  mov     [rsp+98h+var_48], 0
0x18000c298  lea     r8, aD; "D"
0x18000c29f  mov     [rsp+98h+var_50], 0
0x18000c2a8  xor     r9d, r9d
0x18000c2ab  mov     [rsp+98h+var_58], edi
0x18000c2af  xor     edx, edx
0x18000c2b1  mov     [rsp+98h+var_60], rbx
0x18000c2b6  mov     rcx, rax
0x18000c2b9  mov     [rsp+98h+var_68], r12
0x18000c2be  mov     [rsp+98h+var_70], r13
0x18000c2c3  mov     [rsp+98h+var_78], 75h ; 'u'
0x18000c2cb  call    cs:__imp_WdsSetupLogMessageW
0x18000c2d1  mov     rbx, [rsp+98h+arg_0]
0x18000c2d9  mov     eax, esi
0x18000c2db  add     rsp, 70h
0x18000c2df  pop     r14
0x18000c2e1  pop     r13
0x18000c2e3  pop     r12
0x18000c2e5  pop     rdi
0x18000c2e6  pop     rsi
0x18000c2e7  retn
```
