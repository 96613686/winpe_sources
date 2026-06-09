# EnableSinglePrivilege

- ea: `0x180008250`
- end: `0x180008371`
- name: `EnableSinglePrivilege`
- size: `289`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008100`

## callees

- `0x180008250`
- `0x180009130`
- `0x180009850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000827a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000827a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000828d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000828d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000830a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000830a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008351`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008351`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180008300`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180008300`

## pseudocode

```c
__int64 EnableSinglePrivilege()
{
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  LastError = 0;
  TokenHandle = 0;
  NewState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) || (LastError = GetLastError()) == 0 )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)21LL;
    NewState.Privileges[0].Attributes = 2;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v3 = 11;
          goto LABEL_11;
        }
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v3 = 10;
LABEL_11:
      WPP_SF_L(v2[2], v3, WPP_cbdeac6122cb33a3291d8f4078d0acf6_Traceguids, LastError);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180008250  mov     [rsp+arg_0], rbx
0x180008255  push    rdi
0x180008256  sub     rsp, 50h
0x18000825a  mov     rax, cs:__security_cookie
0x180008261  xor     rax, rsp
0x180008264  mov     [rsp+58h+var_10], rax
0x180008269  xor     edi, edi
0x18000826b  xorps   xmm0, xmm0
0x18000826e  mov     ebx, edi
0x180008270  mov     [rsp+58h+TokenHandle], rdi
0x180008275  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x18000827a  call    cs:__imp_GetCurrentProcess
0x180008280  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180008285  mov     edx, 28h ; '('; DesiredAccess
0x18000828a  mov     rcx, rax; ProcessHandle
0x18000828d  call    cs:__imp_OpenProcessToken
0x180008293  test    eax, eax
0x180008295  jnz     short loc_1800082CB
0x180008297  call    cs:__imp_GetLastError
0x18000829d  mov     ebx, eax
0x18000829f  test    eax, eax
0x1800082a1  jz      short loc_1800082CB
0x1800082a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082aa  lea     rax, WPP_GLOBAL_Control
0x1800082b1  cmp     rcx, rax
0x1800082b4  jz      loc_180008347
0x1800082ba  test    byte ptr [rcx+1Ch], 4
0x1800082be  jz      loc_180008347
0x1800082c4  mov     edx, 0Ah
0x1800082c9  jmp     short loc_180008334
0x1800082cb  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800082d0  lea     r8, [rsp+58h+NewState]; NewState
0x1800082d5  mov     [rsp+58h+ReturnLength], rdi; ReturnLength
0x1800082da  mov     r9d, 10h; BufferLength
0x1800082e0  xor     edx, edx; DisableAllPrivileges
0x1800082e2  mov     [rsp+58h+PreviousState], rdi; PreviousState
0x1800082e7  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1800082ef  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 15h
0x1800082f8  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x180008300  call    cs:__imp_AdjustTokenPrivileges
0x180008306  test    eax, eax
0x180008308  jnz     short loc_180008347
0x18000830a  call    cs:__imp_GetLastError
0x180008310  mov     ebx, eax
0x180008312  test    eax, eax
0x180008314  jz      short loc_180008347
0x180008316  mov     rcx, cs:WPP_GLOBAL_Control
0x18000831d  lea     rax, WPP_GLOBAL_Control
0x180008324  cmp     rcx, rax
0x180008327  jz      short loc_180008347
0x180008329  test    byte ptr [rcx+1Ch], 4
0x18000832d  jz      short loc_180008347
0x18000832f  mov     edx, 0Bh
0x180008334  mov     rcx, [rcx+10h]
0x180008338  lea     r8, WPP_cbdeac6122cb33a3291d8f4078d0acf6_Traceguids
0x18000833f  mov     r9d, ebx
0x180008342  call    WPP_SF_L
0x180008347  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000834c  test    rcx, rcx
0x18000834f  jz      short loc_180008357
0x180008351  call    cs:__imp_CloseHandle
0x180008357  mov     eax, ebx
0x180008359  mov     rcx, [rsp+58h+var_10]
0x18000835e  xor     rcx, rsp; StackCookie
0x180008361  call    __security_check_cookie
0x180008366  mov     rbx, [rsp+58h+arg_0]
0x18000836b  add     rsp, 50h
0x18000836f  pop     rdi
0x180008370  retn
```
