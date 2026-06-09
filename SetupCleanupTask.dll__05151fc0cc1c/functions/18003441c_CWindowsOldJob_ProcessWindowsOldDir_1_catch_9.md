# _CWindowsOldJob::ProcessWindowsOldDir_::_1_::catch$9

- ea: `0x18003441c`
- end: `0x18003450e`
- name: `_CWindowsOldJob::ProcessWindowsOldDir_::_1_::catch$9`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x18003441c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003442e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003442e`
- `unbcl!?get_Win32ErrorCode@Win32Exception@UnBCL@@QEBAKXZ` at `0x180034449`
- `unbcl!?get_Win32ErrorCode@Win32Exception@UnBCL@@QEBAKXZ` at `0x180034449`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034467`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180034467`
- `WDSCORE!CurrentIP` at `0x180034436`
- `WDSCORE!CurrentIP` at `0x180034436`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800344cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800344cd`

## string_xrefs

- `0x1800344aa`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`

## pseudocode

```c
__int64 __fastcall CWindowsOldJob::ProcessWindowsOldDir_::_1_::catch_9(__int64 a1, __int64 a2)
{
  DWORD LastError; // edi
  __int64 v4; // rsi
  UnBCL::Win32Exception *v5; // rbx
  unsigned int Win32ErrorCode; // r14d
  UnBCL::String *v7; // rcx
  const wchar_t *CString; // rax
  struct tagLOG_PARTIAL_MSG *v9; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = *(UnBCL::Win32Exception **)(a2 + 232);
  Win32ErrorCode = UnBCL::Win32Exception::get_Win32ErrorCode(v5);
  v7 = *(UnBCL::String **)(a2 + 312);
  if ( v7 )
    CString = UnBCL::String::get_CString(v7);
  else
    CString = L"(NULL)";
  v9 = ConstructPartialMsgW(
         0x2000000,
         "Failed to get directories in %s. GLE = %d",
         (const char *)CString,
         Win32ErrorCode);
  WdsSetupLogMessageW(
    v9,
    0,
    L"D",
    0,
    987,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
    L"CWindowsOldJob::ProcessWindowsOldDir",
    v4,
    LastError,
    0,
    0);
  if ( v5 )
    (**(void (__fastcall ***)(UnBCL::Win32Exception *, __int64))v5)(v5, 1);
  **(_DWORD **)(a2 + 336) = 1;
  return 0;
}

```

## disassembly

```asm
0x18003441c  mov     [rsp+arg_8], rdx
0x180034421  push    rbx
0x180034422  push    rbp
0x180034423  push    rsi
0x180034424  push    rdi
0x180034425  push    r14
0x180034427  sub     rsp, 60h
0x18003442b  mov     rbp, rdx
0x18003442e  call    cs:__imp_GetLastError
0x180034434  mov     edi, eax
0x180034436  call    cs:__imp_CurrentIP
0x18003443c  mov     rsi, rax
0x18003443f  mov     rbx, [rbp+0E8h]
0x180034446  mov     rcx, rbx
0x180034449  call    cs:__imp_?get_Win32ErrorCode@Win32Exception@UnBCL@@QEBAKXZ; UnBCL::Win32Exception::get_Win32ErrorCode(void)
0x18003444f  mov     r14d, eax
0x180034452  mov     rcx, [rbp+138h]
0x180034459  test    rcx, rcx
0x18003445c  jnz     short loc_180034467
0x18003445e  lea     rax, aNull; "(NULL)"
0x180034465  jmp     short loc_18003446D
0x180034467  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003446d  mov     r9d, r14d
0x180034470  mov     r8, rax
0x180034473  lea     rdx, aFailedToGetDir; "Failed to get directories in %s. GLE = "...
0x18003447a  mov     ecx, 2000000h; unsigned int
0x18003447f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180034484  mov     [rsp+88h+var_38], 0
0x18003448c  mov     [rsp+88h+var_40], 0
0x180034495  mov     [rsp+88h+var_48], edi
0x180034499  mov     [rsp+88h+var_50], rsi
0x18003449e  lea     rcx, aCwindowsoldjob_0; "CWindowsOldJob::ProcessWindowsOldDir"
0x1800344a5  mov     [rsp+88h+var_58], rcx
0x1800344aa  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800344b1  mov     [rsp+88h+var_60], rcx
0x1800344b6  mov     [rsp+88h+var_68], 3DBh
0x1800344be  xor     r9d, r9d
0x1800344c1  lea     r8, aD_0; "D"
0x1800344c8  xor     edx, edx
0x1800344ca  mov     rcx, rax
0x1800344cd  call    cs:__imp_WdsSetupLogMessageW
0x1800344d3  test    rbx, rbx
0x1800344d6  jz      short loc_1800344EB
0x1800344d8  mov     rax, [rbx]
0x1800344db  mov     edx, 1
0x1800344e0  mov     rcx, rbx
0x1800344e3  mov     rax, [rax]
0x1800344e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344eb  mov     rax, [rbp+150h]
0x1800344f2  mov     dword ptr [rax], 1
0x1800344f8  mov     rax, 0
0x180034502  add     rsp, 60h
0x180034506  pop     r14
0x180034508  pop     rdi
0x180034509  pop     rsi
0x18003450a  pop     rbp
0x18003450b  pop     rbx
0x18003450c  retn
```
