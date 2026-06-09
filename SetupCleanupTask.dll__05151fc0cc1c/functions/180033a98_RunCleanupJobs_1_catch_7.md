# _RunCleanupJobs_::_1_::catch$7

- ea: `0x180033a98`
- end: `0x180033b41`
- name: `_RunCleanupJobs_::_1_::catch$7`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x18000638c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ab8`
- `WDSCORE!CurrentIP` at `0x180033aaf`
- `WDSCORE!CurrentIP` at `0x180033aaf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033b1b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180033b1b`

## string_xrefs

- `0x180033af8`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x180033ac1`: `Failed to delete cleanup job. GLE = %d`

## pseudocode

```c
__int64 __fastcall RunCleanupJobs_::_1_::catch_7(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  DWORD v5; // eax
  struct tagLOG_PARTIAL_MSG *v6; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = GetLastError();
  v6 = ConstructPartialMsgW(0x4000000, "Failed to delete cleanup job. GLE = %d", v5);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    623,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"RunCleanupJobs",
    v4,
    LastError,
    0,
    0);
  **(_DWORD **)(a2 + 280) = 1;
  return 0;
}

```

## disassembly

```asm
0x180033a98  mov     [rsp+arg_8], rdx
0x180033a9d  push    rbx
0x180033a9e  push    rbp
0x180033a9f  push    rdi
0x180033aa0  sub     rsp, 60h
0x180033aa4  mov     rbp, rdx
0x180033aa7  call    cs:__imp_GetLastError
0x180033aad  mov     edi, eax
0x180033aaf  call    cs:__imp_CurrentIP
0x180033ab5  mov     rbx, rax
0x180033ab8  call    cs:__imp_GetLastError
0x180033abe  mov     r8d, eax
0x180033ac1  lea     rdx, aFailedToDelete_1; "Failed to delete cleanup job. GLE = %d"
0x180033ac8  mov     ecx, 4000000h; unsigned int
0x180033acd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180033ad2  mov     [rsp+78h+var_28], 0
0x180033ada  mov     [rsp+78h+var_30], 0
0x180033ae3  mov     [rsp+78h+var_38], edi
0x180033ae7  mov     [rsp+78h+var_40], rbx
0x180033aec  lea     rcx, aRuncleanupjobs; "RunCleanupJobs"
0x180033af3  mov     [rsp+78h+var_48], rcx
0x180033af8  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180033aff  mov     [rsp+78h+var_50], rcx
0x180033b04  mov     [rsp+78h+var_58], 26Fh
0x180033b0c  xor     r9d, r9d
0x180033b0f  lea     r8, aD_0; "D"
0x180033b16  xor     edx, edx
0x180033b18  mov     rcx, rax
0x180033b1b  call    cs:__imp_WdsSetupLogMessageW
0x180033b21  mov     rax, [rbp+118h]
0x180033b28  mov     dword ptr [rax], 1
0x180033b2e  mov     rax, 0
0x180033b38  add     rsp, 60h
0x180033b3c  pop     rdi
0x180033b3d  pop     rbp
0x180033b3e  pop     rbx
0x180033b3f  retn
```
