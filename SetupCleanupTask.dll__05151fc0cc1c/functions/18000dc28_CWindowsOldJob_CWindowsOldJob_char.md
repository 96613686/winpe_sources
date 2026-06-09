# CWindowsOldJob::CWindowsOldJob(char *)

- ea: `0x18000dc28`
- end: `0x18000dd10`
- name: `??0CWindowsOldJob@@AEAA@PEAD@Z`
- size: `232`
- prototype: `CWindowsOldJob *__fastcall(CWindowsOldJob *__hidden this, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006838`
- `0x18000f3bc`

## callees

- `0x18000638c`
- `0x18000dc28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc7c`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x18000dc45`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x18000dc45`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x18000dc70`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x18000dc70`
- `WDSCORE!CurrentIP` at `0x18000dc84`
- `WDSCORE!CurrentIP` at `0x18000dc84`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dcea`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dcea`

## string_xrefs

- `0x18000dcc7`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x18000dc67`: `WindowsOldSetupCleanupTask`

## pseudocode

```c
CWindowsOldJob *__fastcall CWindowsOldJob::CWindowsOldJob(CWindowsOldJob *this, char *a2)
{
  int UpdateReserveManagerLoader; // ebp
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax

  UnBCL::Object::Object(this);
  *(_QWORD *)this = &ISetupCleanupJob::`vftable';
  *(_QWORD *)this = &CWindowsOldJob::`vftable';
  UpdateReserveManagerLoader = GetUpdateReserveManagerLoader(0, L"WindowsOldSetupCleanupTask", a2, (char *)this + 16);
  if ( UpdateReserveManagerLoader < 0 )
  {
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(0x3000000u, "Failed to get ReserveManagerLoader. hr = %x", UpdateReserveManagerLoader);
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      595,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"CWindowsOldJob::CWindowsOldJob",
      v6,
      LastError,
      0,
      0);
    *((_QWORD *)this + 2) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18000dc28  mov     [rsp+arg_8], rbx
0x18000dc2d  mov     [rsp+arg_10], rbp
0x18000dc32  mov     [rsp+arg_0], rcx
0x18000dc37  push    rsi
0x18000dc38  push    rdi
0x18000dc39  push    r14
0x18000dc3b  sub     rsp, 60h
0x18000dc3f  mov     rbx, rdx
0x18000dc42  mov     rsi, rcx
0x18000dc45  call    cs:__imp_??0Object@UnBCL@@QEAA@XZ; UnBCL::Object::Object(void)
0x18000dc4b  nop
0x18000dc4c  lea     rax, ??_7ISetupCleanupJob@@6B@; const ISetupCleanupJob::`vftable'
0x18000dc53  mov     [rsi], rax
0x18000dc56  lea     rax, ??_7CWindowsOldJob@@6B@; const CWindowsOldJob::`vftable'
0x18000dc5d  mov     [rsi], rax
0x18000dc60  lea     r9, [rsi+10h]
0x18000dc64  mov     r8, rbx
0x18000dc67  lea     rdx, aWindowsoldsetu; "WindowsOldSetupCleanupTask"
0x18000dc6e  xor     ecx, ecx
0x18000dc70  call    cs:__imp_GetUpdateReserveManagerLoader
0x18000dc76  mov     ebp, eax
0x18000dc78  test    eax, eax
0x18000dc7a  jns     short loc_18000DCF8
0x18000dc7c  call    cs:__imp_GetLastError
0x18000dc82  mov     edi, eax
0x18000dc84  call    cs:__imp_CurrentIP
0x18000dc8a  mov     rbx, rax
0x18000dc8d  mov     r8d, ebp
0x18000dc90  lea     rdx, aFailedToGetRes_1; "Failed to get ReserveManagerLoader. hr "...
0x18000dc97  mov     ecx, 3000000h; unsigned int
0x18000dc9c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000dca1  mov     [rsp+78h+var_28], 0
0x18000dca9  mov     [rsp+78h+var_30], 0
0x18000dcb2  mov     [rsp+78h+var_38], edi
0x18000dcb6  mov     [rsp+78h+var_40], rbx
0x18000dcbb  lea     rcx, aCwindowsoldjob_2; "CWindowsOldJob::CWindowsOldJob"
0x18000dcc2  mov     [rsp+78h+var_48], rcx
0x18000dcc7  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000dcce  mov     [rsp+78h+var_50], rcx
0x18000dcd3  mov     [rsp+78h+var_58], 253h
0x18000dcdb  xor     r9d, r9d
0x18000dcde  lea     r8, aD_0; "D"
0x18000dce5  xor     edx, edx
0x18000dce7  mov     rcx, rax
0x18000dcea  call    cs:__imp_WdsSetupLogMessageW
0x18000dcf0  mov     qword ptr [rsi+10h], 0
0x18000dcf8  mov     rax, rsi
0x18000dcfb  lea     r11, [rsp+78h+var_18]
0x18000dd00  mov     rbx, [r11+28h]
0x18000dd04  mov     rbp, [r11+30h]
0x18000dd08  mov     rsp, r11
0x18000dd0b  pop     r14
0x18000dd0d  pop     rdi
0x18000dd0e  pop     rsi
0x18000dd0f  retn
```
