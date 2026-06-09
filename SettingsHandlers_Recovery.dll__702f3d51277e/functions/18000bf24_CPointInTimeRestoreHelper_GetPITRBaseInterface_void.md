# CPointInTimeRestoreHelper::GetPITRBaseInterface(void)

- ea: `0x18000bf24`
- end: `0x18000bfd9`
- name: `?GetPITRBaseInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRBase@PITR@@XZ`
- size: `181`
- prototype: `struct PITR::IPITRBase *__fastcall(CPointInTimeRestoreHelper *this, __int64, struct PITR::IPITRBase **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000bfe0`
- `0x18000c0a4`
- `0x18000cc80`

## callees

- `0x18000bef4`
- `0x18000bf24`
- `0x180027b20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf4e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bfbc`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000bfbc`
- `WDSCORE!CurrentIP` at `0x18000bf56`
- `WDSCORE!CurrentIP` at `0x18000bf56`

## string_xrefs

- `0x18000bfa5`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
struct PITR::IPITRBase *__fastcall CPointInTimeRestoreHelper::GetPITRBaseInterface(
        CPointInTimeRestoreHelper *this,
        __int64 a2,
        struct PITR::IPITRBase **a3)
{
  int PITRInterface; // esi
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax

  if ( *(_QWORD *)this )
    return *(struct PITR::IPITRBase **)this;
  PITRInterface = PITR::GetPITRInterface(this, (const unsigned __int16 *)this, a3);
  if ( PITRInterface >= 0 )
    return *(struct PITR::IPITRBase **)this;
  LastError = GetLastError();
  v6 = CurrentIP();
  v7 = ConstructPartialMsgW(
         0x2000000u,
         "CPointInTimeRestoreHelper::GetPITRBaseInterface: Failed to get PITR base interface. hr=0x%08X",
         PITRInterface);
  WdsSetupLogMessageW(
    v7,
    0,
    L"D",
    0,
    61,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPITRBaseInterface",
    v6,
    LastError,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x18000bf24  mov     [rsp+arg_0], rbx
0x18000bf29  mov     [rsp+arg_8], rsi
0x18000bf2e  push    rdi
0x18000bf2f  sub     rsp, 60h
0x18000bf33  cmp     qword ptr [rcx], 0
0x18000bf37  mov     rbx, rcx
0x18000bf3a  jnz     loc_18000BFC6
0x18000bf40  mov     rdx, rcx; unsigned __int16 *
0x18000bf43  call    ?GetPITRInterface@PITR@@YAJPEBGPEAPEAUIPITRBase@1@@Z; PITR::GetPITRInterface(ushort const *,PITR::IPITRBase * *)
0x18000bf48  mov     esi, eax
0x18000bf4a  test    eax, eax
0x18000bf4c  jns     short loc_18000BFC6
0x18000bf4e  call    cs:__imp_GetLastError
0x18000bf54  mov     edi, eax
0x18000bf56  call    cs:__imp_CurrentIP
0x18000bf5c  mov     r8d, esi
0x18000bf5f  lea     rdx, aCpointintimere_55; "CPointInTimeRestoreHelper::GetPITRBaseI"...
0x18000bf66  mov     ecx, 2000000h; unsigned int
0x18000bf6b  mov     rbx, rax
0x18000bf6e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bf73  mov     [rsp+68h+var_18], 0
0x18000bf7b  lea     rcx, aCpointintimere_4; "CPointInTimeRestoreHelper::GetPITRBaseI"...
0x18000bf82  mov     [rsp+68h+var_20], 0
0x18000bf8b  lea     r8, aD; "D"
0x18000bf92  mov     [rsp+68h+var_28], edi
0x18000bf96  xor     r9d, r9d
0x18000bf99  mov     [rsp+68h+var_30], rbx
0x18000bf9e  xor     edx, edx
0x18000bfa0  mov     [rsp+68h+var_38], rcx
0x18000bfa5  lea     rcx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000bfac  mov     [rsp+68h+var_40], rcx
0x18000bfb1  mov     rcx, rax
0x18000bfb4  mov     [rsp+68h+var_48], 3Dh ; '='
0x18000bfbc  call    cs:__imp_WdsSetupLogMessageW
0x18000bfc2  xor     eax, eax
0x18000bfc4  jmp     short loc_18000BFC9
0x18000bfc6  mov     rax, [rbx]
0x18000bfc9  mov     rbx, [rsp+68h+arg_0]
0x18000bfce  mov     rsi, [rsp+68h+arg_8]
0x18000bfd3  add     rsp, 60h
0x18000bfd7  pop     rdi
0x18000bfd8  retn
```
