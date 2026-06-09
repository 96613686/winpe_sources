# EdpCredSvcCheckCallerIsLocalSystem(void)

- ea: `0x180080bc4`
- end: `0x180080d97`
- name: `?EdpCredSvcCheckCallerIsLocalSystem@@YAJXZ`
- size: `467`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180092240`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180080bc4`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080cfb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180080c3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180080c3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080c27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d38`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180080c93`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180080c93`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180080cf1`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180080cf1`

## pseudocode

```c
__int64 __fastcall EdpCredSvcCheckCallerIsLocalSystem(int a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v3; // ebx
  int v4; // r8d
  signed int v5; // eax
  signed int v6; // eax
  char v8; // [rsp+20h] [rbp-50h]
  WINBOOL IsMember; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL pfResult; // [rsp+44h] [rbp-2Ch] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  IsMember = 0;
  pfResult = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  fnEfsLogTrace1Strings(a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 38, 24);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v8 = 35;
LABEL_5:
    v4 = v3;
LABEL_6:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v4, 38, v8);
    goto LABEL_21;
  }
  if ( !CheckTokenMembership(TokenHandle, qword_1800F59F0, &IsMember) )
  {
    v5 = GetLastError();
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v8 = 42;
    goto LABEL_5;
  }
  if ( !IsMember )
  {
    v8 = 47;
LABEL_13:
    v3 = -2147024891;
    v4 = -2147024891;
    goto LABEL_6;
  }
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
  if ( !PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult) )
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    v8 = 62;
    goto LABEL_5;
  }
  if ( !pfResult )
  {
    v8 = 67;
    goto LABEL_13;
  }
  v3 = 0;
LABEL_21:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v3,
    38,
    74);
  return v3;
}

```

## disassembly

```asm
0x180080bc4  mov     [rsp-8+arg_0], rbx
0x180080bc9  mov     [rsp-8+arg_8], rsi
0x180080bce  push    rbp
0x180080bcf  mov     rbp, rsp
0x180080bd2  sub     rsp, 70h
0x180080bd6  mov     rax, cs:__security_cookie
0x180080bdd  xor     rax, rsp
0x180080be0  mov     [rbp+var_8], rax
0x180080be4  xor     eax, eax
0x180080be6  mov     [rbp+TokenHandle], 0
0x180080bee  xorps   xmm0, xmm0
0x180080bf1  mov     [rbp+IsMember], 0
0x180080bf8  lea     r8, sourceString
0x180080bff  mov     [rbp+pfResult], 0
0x180080c06  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180080c0d  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x180080c10  lea     esi, [rax+26h]
0x180080c13  mov     dword ptr [rsp+70h+var_50], 218h
0x180080c1b  mov     r9d, esi
0x180080c1e  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x180080c22  call    fnEfsLogTrace1Strings
0x180080c27  call    cs:__imp_GetCurrentThread
0x180080c2d  lea     ebx, [rsi-25h]
0x180080c30  mov     edx, 20008h; DesiredAccess
0x180080c35  mov     rcx, rax; ThreadHandle
0x180080c38  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180080c3c  mov     r8d, ebx; OpenAsSelf
0x180080c3f  call    cs:__imp_OpenThreadToken
0x180080c45  test    eax, eax
0x180080c47  jnz     short loc_180080C84
0x180080c49  call    cs:__imp_GetLastError
0x180080c4f  mov     ebx, eax
0x180080c51  test    eax, eax
0x180080c53  jle     short loc_180080C5E
0x180080c55  movzx   ebx, ax
0x180080c58  or      ebx, 80070000h
0x180080c5e  mov     dword ptr [rsp+70h+var_50], 223h
0x180080c66  mov     r8d, ebx
0x180080c69  mov     rcx, cs:g_hPublisher
0x180080c70  lea     rdx, EFS_TRACE_ERROR
0x180080c77  mov     r9d, esi
0x180080c7a  call    fnEfsLogTrace1
0x180080c7f  jmp     loc_180080D2F
0x180080c84  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180080c88  lea     r8, [rbp+IsMember]; IsMember
0x180080c8c  lea     rdx, qword_1800F59F0; SidToCheck
0x180080c93  call    cs:__imp_CheckTokenMembership
0x180080c99  test    eax, eax
0x180080c9b  jnz     short loc_180080CBC
0x180080c9d  call    cs:__imp_GetLastError
0x180080ca3  mov     ebx, eax
0x180080ca5  test    eax, eax
0x180080ca7  jle     short loc_180080CB2
0x180080ca9  movzx   ebx, ax
0x180080cac  or      ebx, 80070000h
0x180080cb2  mov     dword ptr [rsp+70h+var_50], 22Ah
0x180080cba  jmp     short loc_180080C66
0x180080cbc  cmp     [rbp+IsMember], 0
0x180080cc0  jnz     short loc_180080CD7
0x180080cc2  mov     dword ptr [rsp+70h+var_50], 22Fh
0x180080cca  mov     ebx, 80070005h
0x180080ccf  mov     r8d, 80070005h
0x180080cd5  jmp     short loc_180080C69
0x180080cd7  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180080cdb  lea     r8, [rbp+pfResult]; pfResult
0x180080cdf  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180080ce3  mov     [rbp+RequiredPrivileges.PrivilegeCount], ebx
0x180080ce6  mov     [rbp+RequiredPrivileges.Control], ebx
0x180080ce9  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x180080cf1  call    cs:__imp_PrivilegeCheck
0x180080cf7  test    eax, eax
0x180080cf9  jnz     short loc_180080D1D
0x180080cfb  call    cs:__imp_GetLastError
0x180080d01  mov     ebx, eax
0x180080d03  test    eax, eax
0x180080d05  jle     short loc_180080D10
0x180080d07  movzx   ebx, ax
0x180080d0a  or      ebx, 80070000h
0x180080d10  mov     dword ptr [rsp+70h+var_50], 23Eh
0x180080d18  jmp     loc_180080C66
0x180080d1d  cmp     [rbp+pfResult], 0
0x180080d21  jnz     short loc_180080D2D
0x180080d23  mov     dword ptr [rsp+70h+var_50], 243h
0x180080d2b  jmp     short loc_180080CCA
0x180080d2d  xor     ebx, ebx
0x180080d2f  mov     rcx, [rbp+TokenHandle]; hObject
0x180080d33  test    rcx, rcx
0x180080d36  jz      short loc_180080D46
0x180080d38  call    cs:__imp_CloseHandle
0x180080d3e  mov     [rbp+TokenHandle], 0
0x180080d46  mov     rcx, cs:g_hPublisher
0x180080d4d  lea     r9, sourceString
0x180080d54  mov     [rsp+70h+var_40], 24Ah
0x180080d5c  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180080d63  mov     [rsp+70h+var_48], esi
0x180080d67  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180080d6e  mov     dword ptr [rsp+70h+var_50], ebx
0x180080d72  call    fnEfsLogTrace1String1Dword
0x180080d77  mov     eax, ebx
0x180080d79  mov     rcx, [rbp+var_8]
0x180080d7d  xor     rcx, rsp; StackCookie
0x180080d80  call    __security_check_cookie
0x180080d85  lea     r11, [rsp+70h+var_s0]
0x180080d8a  mov     rbx, [r11+10h]
0x180080d8e  mov     rsi, [r11+18h]
0x180080d92  mov     rsp, r11
0x180080d95  pop     rbp
0x180080d96  retn
```
