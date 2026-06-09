# RestartWindows(void)

- ea: `0x18004fa08`
- end: `0x18004facb`
- name: `?RestartWindows@@YAHXZ`
- size: `195`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800298e4`
- `0x180032ce0`

## callees

- `0x18004fa08`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fa94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fa94`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004fa3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004fa3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fa2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fa2c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004fa57`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004fa57`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004fa8e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004fa8e`
- `USER32!ExitWindowsEx` at `0x18004faa6`
- `USER32!ExitWindowsEx` at `0x18004faa6`

## string_xrefs

- `0x18004fa50`: `SeShutdownPrivilege`

## pseudocode

```c
_BOOL8 RestartWindows(void)
{
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    return 0;
  LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart);
  Luid[0].LowPart = 1;
  Luid[1].HighPart = 2;
  AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
  return !GetLastError() && ExitWindowsEx(2u, 0x80020000);
}

```

## disassembly

```asm
0x18004fa08  sub     rsp, 58h
0x18004fa0c  mov     rax, cs:__security_cookie
0x18004fa13  xor     rax, rsp
0x18004fa16  mov     [rsp+58h+var_10], rax
0x18004fa1b  xorps   xmm0, xmm0
0x18004fa1e  mov     [rsp+58h+TokenHandle], 0
0x18004fa27  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18004fa2c  call    cs:__imp_GetCurrentProcess
0x18004fa32  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18004fa37  mov     edx, 28h ; '('; DesiredAccess
0x18004fa3c  mov     rcx, rax; ProcessHandle
0x18004fa3f  call    cs:__imp_OpenProcessToken
0x18004fa45  test    eax, eax
0x18004fa47  jz      short loc_18004FAB7
0x18004fa49  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18004fa4e  xor     ecx, ecx; lpSystemName
0x18004fa50  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18004fa57  call    cs:__imp_LookupPrivilegeValueW
0x18004fa5d  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18004fa62  lea     r8, [rsp+58h+Luid]; NewState
0x18004fa67  xor     r9d, r9d; BufferLength
0x18004fa6a  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18004fa73  xor     edx, edx; DisableAllPrivileges
0x18004fa75  mov     [rsp+58h+Luid.LowPart], 1
0x18004fa7d  mov     [rsp+58h+Luid.HighPart+8], 2
0x18004fa85  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18004fa8e  call    cs:__imp_AdjustTokenPrivileges
0x18004fa94  call    cs:__imp_GetLastError
0x18004fa9a  test    eax, eax
0x18004fa9c  jnz     short loc_18004FAB7
0x18004fa9e  mov     edx, 80020000h; dwReason
0x18004faa3  lea     ecx, [rax+2]; uFlags
0x18004faa6  call    cs:__imp_ExitWindowsEx
0x18004faac  xor     ecx, ecx
0x18004faae  test    eax, eax
0x18004fab0  setnz   cl
0x18004fab3  mov     eax, ecx
0x18004fab5  jmp     short loc_18004FAB9
0x18004fab7  xor     eax, eax
0x18004fab9  mov     rcx, [rsp+58h+var_10]
0x18004fabe  xor     rcx, rsp; StackCookie
0x18004fac1  call    __security_check_cookie
0x18004fac6  add     rsp, 58h
0x18004faca  retn
```
