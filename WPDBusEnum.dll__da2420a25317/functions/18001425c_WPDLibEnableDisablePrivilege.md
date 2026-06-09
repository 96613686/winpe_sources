# WPDLibEnableDisablePrivilege

- ea: `0x18001425c`
- end: `0x18001432e`
- name: `WPDLibEnableDisablePrivilege`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800143f8`

## callees

- `0x1800097d0`
- `0x18001425c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014284`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014297`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014313`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180014302`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180014302`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800142b7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800142b7`

## string_xrefs

- `0x1800142b0`: `SeShutdownPrivilege`

## pseudocode

```c
DWORD __fastcall WPDLibEnableDisablePrivilege(__int64 a1, int a2)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    return GetLastError();
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart)
    && (Luid[0].LowPart = 1,
        Luid[1].HighPart = a2 != 0 ? 2 : 4,
        AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0)) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001425c  push    rbx
0x18001425e  sub     rsp, 50h
0x180014262  mov     rax, cs:__security_cookie
0x180014269  xor     rax, rsp
0x18001426c  mov     [rsp+58h+var_10], rax
0x180014271  xorps   xmm0, xmm0
0x180014274  mov     [rsp+58h+TokenHandle], 0
0x18001427d  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x180014282  mov     ebx, edx
0x180014284  call    cs:__imp_GetCurrentProcess
0x18001428a  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18001428f  mov     edx, 28h ; '('; DesiredAccess
0x180014294  mov     rcx, rax; ProcessHandle
0x180014297  call    cs:__imp_OpenProcessToken
0x18001429d  test    eax, eax
0x18001429f  jnz     short loc_1800142A9
0x1800142a1  call    cs:__imp_GetLastError
0x1800142a7  jmp     short loc_18001431B
0x1800142a9  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x1800142ae  xor     ecx, ecx; lpSystemName
0x1800142b0  lea     rdx, Name; "SeShutdownPrivilege"
0x1800142b7  call    cs:__imp_LookupPrivilegeValueW
0x1800142bd  test    eax, eax
0x1800142bf  jnz     short loc_1800142CB
0x1800142c1  call    cs:__imp_GetLastError
0x1800142c7  mov     ebx, eax
0x1800142c9  jmp     short loc_18001430E
0x1800142cb  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800142d0  lea     r8, [rsp+58h+Luid]; NewState
0x1800142d5  neg     ebx
0x1800142d7  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1800142e0  mov     [rsp+58h+Luid.LowPart], 1
0x1800142e8  sbb     eax, eax
0x1800142ea  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1800142f3  and     eax, 0FFFFFFFEh
0x1800142f6  xor     r9d, r9d; BufferLength
0x1800142f9  add     eax, 4
0x1800142fc  xor     edx, edx; DisableAllPrivileges
0x1800142fe  mov     [rsp+58h+Luid.HighPart+8], eax
0x180014302  call    cs:__imp_AdjustTokenPrivileges
0x180014308  test    eax, eax
0x18001430a  jz      short loc_1800142C1
0x18001430c  xor     ebx, ebx
0x18001430e  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180014313  call    cs:__imp_CloseHandle
0x180014319  mov     eax, ebx
0x18001431b  mov     rcx, [rsp+58h+var_10]
0x180014320  xor     rcx, rsp; StackCookie
0x180014323  call    __security_check_cookie
0x180014328  add     rsp, 50h
0x18001432c  pop     rbx
0x18001432d  retn
```
