# CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)

- ea: `0x18000bfe0`
- end: `0x18000c09e`
- name: `?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ`
- size: `190`
- prototype: `struct PITR::IPITRSettings *__fastcall(CPointInTimeRestoreHelper *this, __int64, struct PITR::IPITRBase **)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000c2f0`
- `0x18000c550`
- `0x18000c7b8`
- `0x18000ca18`
- `0x18000d36c`
- `0x18000d5cc`
- `0x18000d82c`
- `0x18000da8c`

## callees

- `0x18000bef4`
- `0x18000bf24`
- `0x18000bfe0`
- `0x180027fc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c013`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c081`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000c081`
- `WDSCORE!CurrentIP` at `0x18000c01b`
- `WDSCORE!CurrentIP` at `0x18000c01b`

## string_xrefs

- `0x18000c06a`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct PITR::IPITRSettings *__fastcall CPointInTimeRestoreHelper::GetPITRSettingsInterface(
        CPointInTimeRestoreHelper *this,
        __int64 a2,
        struct PITR::IPITRBase **a3)
{
  struct PITR::IPITRBase *v3; // rbx
  PITR *PITRBaseInterface; // rax
  struct PITR::IPITRSettings **v5; // r8
  int SettingsInterface; // esi
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax

  v3 = (CPointInTimeRestoreHelper *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
    return *(struct PITR::IPITRSettings **)v3;
  PITRBaseInterface = CPointInTimeRestoreHelper::GetPITRBaseInterface(this, a2, a3);
  SettingsInterface = PITR::GetSettingsInterface(PITRBaseInterface, v3, v5);
  if ( SettingsInterface >= 0 )
    return *(struct PITR::IPITRSettings **)v3;
  LastError = GetLastError();
  v8 = CurrentIP();
  v9 = ConstructPartialMsgW(
         0x2000000u,
         "CPointInTimeRestoreHelper::GetPITRSettingsInterface: Failed to get PITR settings interface. hr=0x%08X",
         SettingsInterface);
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    79,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPITRSettingsInterface",
    v8,
    LastError,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x18000bfe0  mov     [rsp+arg_0], rbx
0x18000bfe5  mov     [rsp+arg_8], rsi
0x18000bfea  push    rdi
0x18000bfeb  sub     rsp, 60h
0x18000bfef  lea     rbx, [rcx+8]
0x18000bff3  cmp     qword ptr [rbx], 0
0x18000bff7  jnz     loc_18000C08B
0x18000bffd  call    ?GetPITRBaseInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRBase@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRBaseInterface(void)
0x18000c002  mov     rcx, rax; this
0x18000c005  mov     rdx, rbx; struct PITR::IPITRBase *
0x18000c008  call    ?GetSettingsInterface@PITR@@YAJPEAUIPITRBase@1@PEAPEAUIPITRSettings@1@@Z; PITR::GetSettingsInterface(PITR::IPITRBase *,PITR::IPITRSettings * *)
0x18000c00d  mov     esi, eax
0x18000c00f  test    eax, eax
0x18000c011  jns     short loc_18000C08B
0x18000c013  call    cs:__imp_GetLastError
0x18000c019  mov     edi, eax
0x18000c01b  call    cs:__imp_CurrentIP
0x18000c021  mov     r8d, esi
0x18000c024  lea     rdx, aCpointintimere_38; "CPointInTimeRestoreHelper::GetPITRSetti"...
0x18000c02b  mov     ecx, 2000000h; unsigned int
0x18000c030  mov     rbx, rax
0x18000c033  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c038  mov     [rsp+68h+var_18], 0
0x18000c040  lea     rcx, aCpointintimere_51; "CPointInTimeRestoreHelper::GetPITRSetti"...
0x18000c047  mov     [rsp+68h+var_20], 0
0x18000c050  lea     r8, aD; "D"
0x18000c057  mov     [rsp+68h+var_28], edi
0x18000c05b  xor     r9d, r9d
0x18000c05e  mov     [rsp+68h+var_30], rbx
0x18000c063  xor     edx, edx
0x18000c065  mov     [rsp+68h+var_38], rcx
0x18000c06a  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000c071  mov     [rsp+68h+var_40], rcx
0x18000c076  mov     rcx, rax
0x18000c079  mov     [rsp+68h+var_48], 4Fh ; 'O'
0x18000c081  call    cs:__imp_WdsSetupLogMessageW
0x18000c087  xor     eax, eax
0x18000c089  jmp     short loc_18000C08E
0x18000c08b  mov     rax, [rbx]
0x18000c08e  mov     rbx, [rsp+68h+arg_0]
0x18000c093  mov     rsi, [rsp+68h+arg_8]
0x18000c098  add     rsp, 60h
0x18000c09c  pop     rdi
0x18000c09d  retn
```
