# CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive(int)

- ea: `0x18000d36c`
- end: `0x18000d5c3`
- name: `?SetPointInTimeRestoreFeatureActive@CPointInTimeRestoreHelper@@QEAAJH@Z`
- size: `599`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000ec30`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000d36c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d550`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d3f1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d464`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d54a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d5ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d3f1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d464`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d54a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d5ac`
- `WDSCORE!CurrentIP` at `0x18000d388`
- `WDSCORE!CurrentIP` at `0x18000d410`
- `WDSCORE!CurrentIP` at `0x18000d49e`
- `WDSCORE!CurrentIP` at `0x18000d4f6`
- `WDSCORE!CurrentIP` at `0x18000d558`
- `WDSCORE!CurrentIP` at `0x18000d388`
- `WDSCORE!CurrentIP` at `0x18000d410`
- `WDSCORE!CurrentIP` at `0x18000d49e`
- `WDSCORE!CurrentIP` at `0x18000d4f6`
- `WDSCORE!CurrentIP` at `0x18000d558`

## string_xrefs

- `0x18000d3bd`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive(
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
         "Enter CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive: setting PITR settings, PITR On=%d",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    412,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive",
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
           "CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive: Setting PITR toggle to %d",
           a2);
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      419,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive",
      v8,
      v7,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this);
    v11 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, _QWORD))(*(_QWORD *)PITRSettingsInterface
                                                                                   + 8LL))(
            PITRSettingsInterface,
            2,
            a2);
    if ( v11 < 0 )
    {
      v12 = GetLastError();
      v13 = CurrentIP();
      v14 = ConstructPartialMsgW(
              0x2000000u,
              "CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive: Failed to set PITR toggle. hr=0x%08X",
              v11);
      WdsSetupLogMessageW(
        v14,
        0,
        L"D",
        0,
        423,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
        L"CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive",
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
            "CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive: PITR setting interface is unexpectedly null. hr=0x%08X",
            -2147418113);
    WdsSetupLogMessageW(
      v17,
      0,
      L"D",
      0,
      430,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive",
      v16,
      v15,
      0,
      0);
  }
  v18 = GetLastError();
  v19 = CurrentIP();
  v20 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive: Exiting with hr=0x%08X",
          v11);
  WdsSetupLogMessageW(
    v20,
    0,
    L"D",
    0,
    436,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive",
    v19,
    v18,
    0,
    0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d36c  push    rbx
0x18000d36e  push    rbp
0x18000d36f  push    rsi
0x18000d370  push    rdi
0x18000d371  push    r12
0x18000d373  push    r13
0x18000d375  push    r15
0x18000d377  sub     rsp, 60h
0x18000d37b  mov     esi, edx
0x18000d37d  mov     rbp, rcx
0x18000d380  call    cs:__imp_GetLastError
0x18000d386  mov     edi, eax
0x18000d388  call    cs:__imp_CurrentIP
0x18000d38e  mov     r8d, esi
0x18000d391  lea     rdx, aEnterCpointint_4; "Enter CPointInTimeRestoreHelper::SetPoi"...
0x18000d398  mov     ecx, 4000000h; unsigned int
0x18000d39d  mov     rbx, rax
0x18000d3a0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d3a5  mov     [rsp+98h+var_48], 0
0x18000d3ad  lea     r12, aCpointintimere_37; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d3b4  mov     [rsp+98h+var_50], 0
0x18000d3bd  lea     r13, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000d3c4  mov     [rsp+98h+var_58], edi
0x18000d3c8  lea     r15, aD; "D"
0x18000d3cf  mov     [rsp+98h+var_60], rbx
0x18000d3d4  xor     r9d, r9d
0x18000d3d7  mov     [rsp+98h+var_68], r12
0x18000d3dc  mov     r8, r15
0x18000d3df  mov     [rsp+98h+var_70], r13
0x18000d3e4  xor     edx, edx
0x18000d3e6  mov     rcx, rax
0x18000d3e9  mov     [rsp+98h+var_78], 19Ch
0x18000d3f1  call    cs:__imp_WdsSetupLogMessageW
0x18000d3f7  mov     rcx, rbp; this
0x18000d3fa  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000d3ff  test    rax, rax
0x18000d402  jz      loc_18000D4E9
0x18000d408  call    cs:__imp_GetLastError
0x18000d40e  mov     edi, eax
0x18000d410  call    cs:__imp_CurrentIP
0x18000d416  mov     r8d, esi
0x18000d419  lea     rdx, aCpointintimere_20; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d420  mov     ecx, 4000000h; unsigned int
0x18000d425  mov     rbx, rax
0x18000d428  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d42d  mov     [rsp+98h+var_48], 0
0x18000d435  xor     r9d, r9d
0x18000d438  mov     [rsp+98h+var_50], 0
0x18000d441  mov     r8, r15
0x18000d444  mov     [rsp+98h+var_58], edi
0x18000d448  xor     edx, edx
0x18000d44a  mov     [rsp+98h+var_60], rbx
0x18000d44f  mov     rcx, rax
0x18000d452  mov     [rsp+98h+var_68], r12
0x18000d457  mov     [rsp+98h+var_70], r13
0x18000d45c  mov     [rsp+98h+var_78], 1A3h
0x18000d464  call    cs:__imp_WdsSetupLogMessageW
0x18000d46a  mov     rcx, rbp; this
0x18000d46d  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000d472  mov     r9, rax
0x18000d475  mov     r8d, esi
0x18000d478  mov     edx, 2
0x18000d47d  mov     rcx, [rax]
0x18000d480  mov     rax, [rcx+8]
0x18000d484  mov     rcx, r9
0x18000d487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d48c  mov     esi, eax
0x18000d48e  test    eax, eax
0x18000d490  jns     loc_18000D550
0x18000d496  call    cs:__imp_GetLastError
0x18000d49c  mov     edi, eax
0x18000d49e  call    cs:__imp_CurrentIP
0x18000d4a4  mov     r8d, esi
0x18000d4a7  lea     rdx, aCpointintimere_3; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d4ae  mov     ecx, 2000000h; unsigned int
0x18000d4b3  mov     rbx, rax
0x18000d4b6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d4bb  mov     [rsp+98h+var_48], 0
0x18000d4c3  mov     [rsp+98h+var_50], 0
0x18000d4cc  mov     [rsp+98h+var_58], edi
0x18000d4d0  mov     [rsp+98h+var_60], rbx
0x18000d4d5  mov     [rsp+98h+var_68], r12
0x18000d4da  mov     [rsp+98h+var_70], r13
0x18000d4df  mov     [rsp+98h+var_78], 1A7h
0x18000d4e7  jmp     short loc_18000D53F
0x18000d4e9  mov     esi, 8000FFFFh
0x18000d4ee  call    cs:__imp_GetLastError
0x18000d4f4  mov     edi, eax
0x18000d4f6  call    cs:__imp_CurrentIP
0x18000d4fc  mov     r8d, esi
0x18000d4ff  lea     rdx, aCpointintimere_31; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d506  mov     ecx, 2000000h; unsigned int
0x18000d50b  mov     rbx, rax
0x18000d50e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d513  mov     [rsp+98h+var_48], 0
0x18000d51b  mov     [rsp+98h+var_50], 0
0x18000d524  mov     [rsp+98h+var_58], edi
0x18000d528  mov     [rsp+98h+var_60], rbx
0x18000d52d  mov     [rsp+98h+var_68], r12
0x18000d532  mov     [rsp+98h+var_70], r13
0x18000d537  mov     [rsp+98h+var_78], 1AEh
0x18000d53f  xor     r9d, r9d
0x18000d542  mov     r8, r15
0x18000d545  xor     edx, edx
0x18000d547  mov     rcx, rax
0x18000d54a  call    cs:__imp_WdsSetupLogMessageW
0x18000d550  call    cs:__imp_GetLastError
0x18000d556  mov     edi, eax
0x18000d558  call    cs:__imp_CurrentIP
0x18000d55e  mov     r8d, esi
0x18000d561  lea     rdx, aCpointintimere_17; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d568  mov     ecx, 4000000h; unsigned int
0x18000d56d  mov     rbx, rax
0x18000d570  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d575  mov     [rsp+98h+var_48], 0
0x18000d57d  xor     r9d, r9d
0x18000d580  mov     [rsp+98h+var_50], 0
0x18000d589  mov     r8, r15
0x18000d58c  mov     [rsp+98h+var_58], edi
0x18000d590  xor     edx, edx
0x18000d592  mov     [rsp+98h+var_60], rbx
0x18000d597  mov     rcx, rax
0x18000d59a  mov     [rsp+98h+var_68], r12
0x18000d59f  mov     [rsp+98h+var_70], r13
0x18000d5a4  mov     [rsp+98h+var_78], 1B4h
0x18000d5ac  call    cs:__imp_WdsSetupLogMessageW
0x18000d5b2  mov     eax, esi
0x18000d5b4  add     rsp, 60h
0x18000d5b8  pop     r15
0x18000d5ba  pop     r13
0x18000d5bc  pop     r12
0x18000d5be  pop     rdi
0x18000d5bf  pop     rsi
0x18000d5c0  pop     rbp
0x18000d5c1  pop     rbx
0x18000d5c2  retn
```
