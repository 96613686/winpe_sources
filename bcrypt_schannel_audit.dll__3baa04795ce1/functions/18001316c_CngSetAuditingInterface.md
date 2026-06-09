# CngSetAuditingInterface

- ea: `0x18001316c`
- end: `0x180013322`
- name: `CngSetAuditingInterface`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014d60`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x18001316c`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800131a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800131a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800131ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800131ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132f9`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180013274`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180013274`

## string_xrefs

- `0x180013228`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`
- `0x1800132c8`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`

## pseudocode

```c
__int64 CngSetAuditingInterface()
{
  HANDLE CurrentProcess; // rax
  int v1; // edx
  unsigned int LastError; // ebx
  __int64 v3; // rcx
  WINBOOL pfResult; // [rsp+40h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  pfResult = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    *(_QWORD *)&RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)7LL;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    if ( PrivilegeCheck(TokenHandle, &RequiredPrivileges, &pfResult) )
    {
      if ( pfResult )
      {
        LastError = 0;
        goto LABEL_17;
      }
      LastError = -1073741727;
      v3 = 3221225569LL;
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      v3 = LastError;
    }
    DebugTraceError(v3, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c");
    goto LABEL_17;
  }
  if ( (int)GetLastError() > 0 )
    LastError = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v1,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c",
      (unsigned int)"Status",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c",
      86);
LABEL_17:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001316c  mov     [rsp-8+arg_0], rbx
0x180013171  push    rbp
0x180013172  mov     rbp, rsp
0x180013175  sub     rsp, 70h
0x180013179  mov     rax, cs:__security_cookie
0x180013180  xor     rax, rsp
0x180013183  mov     [rbp+var_8], rax
0x180013187  xorps   xmm0, xmm0
0x18001318a  mov     [rbp+TokenHandle], 0
0x180013192  xor     eax, eax
0x180013194  mov     [rbp+pfResult], 0
0x18001319b  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x18001319f  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1800131a2  call    cs:__imp_GetCurrentProcess
0x1800131a9  nop     dword ptr [rax+rax+00h]
0x1800131ae  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800131b2  mov     edx, 8; DesiredAccess
0x1800131b7  mov     rcx, rax; ProcessHandle
0x1800131ba  call    cs:__imp_OpenProcessToken
0x1800131c1  nop     dword ptr [rax+rax+00h]
0x1800131c6  test    eax, eax
0x1800131c8  jnz     loc_180013251
0x1800131ce  call    cs:__imp_GetLastError
0x1800131d5  nop     dword ptr [rax+rax+00h]
0x1800131da  test    eax, eax
0x1800131dc  jg      short loc_1800131EE
0x1800131de  call    cs:__imp_GetLastError
0x1800131e5  nop     dword ptr [rax+rax+00h]
0x1800131ea  mov     ebx, eax
0x1800131ec  jmp     short loc_180013203
0x1800131ee  call    cs:__imp_GetLastError
0x1800131f5  nop     dword ptr [rax+rax+00h]
0x1800131fa  movzx   ebx, ax
0x1800131fd  or      ebx, 0C0070000h
0x180013203  mov     rcx, cs:WPP_GLOBAL_Control
0x18001320a  lea     rax, WPP_GLOBAL_Control
0x180013211  cmp     rcx, rax
0x180013214  jz      loc_1800132F0
0x18001321a  test    byte ptr [rcx+1Ch], 1
0x18001321e  jz      loc_1800132F0
0x180013224  mov     rcx, [rcx+10h]
0x180013228  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001322f  mov     [rsp+70h+var_40], 56h ; 'V'
0x180013237  lea     r9, aStatus; "Status"
0x18001323e  mov     [rsp+70h+var_48], r8
0x180013243  mov     [rsp+70h+var_50], ebx
0x180013247  call    WPP_SF_sDsd
0x18001324c  jmp     loc_1800132F0
0x180013251  mov     rcx, [rbp+TokenHandle]; ClientToken
0x180013255  lea     r8, [rbp+pfResult]; pfResult
0x180013259  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x18001325d  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180013265  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 7
0x18001326d  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x180013274  call    cs:__imp_PrivilegeCheck
0x18001327b  nop     dword ptr [rax+rax+00h]
0x180013280  test    eax, eax
0x180013282  jnz     short loc_1800132D6
0x180013284  call    cs:__imp_GetLastError
0x18001328b  nop     dword ptr [rax+rax+00h]
0x180013290  test    eax, eax
0x180013292  jg      short loc_1800132A4
0x180013294  call    cs:__imp_GetLastError
0x18001329b  nop     dword ptr [rax+rax+00h]
0x1800132a0  mov     ebx, eax
0x1800132a2  jmp     short loc_1800132B9
0x1800132a4  call    cs:__imp_GetLastError
0x1800132ab  nop     dword ptr [rax+rax+00h]
0x1800132b0  movzx   ebx, ax
0x1800132b3  or      ebx, 0C0070000h
0x1800132b9  mov     r9d, 64h ; 'd'
0x1800132bf  mov     ecx, ebx
0x1800132c1  lea     rdx, aStatus; "Status"
0x1800132c8  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800132cf  call    DebugTraceError
0x1800132d4  jmp     short loc_1800132F0
0x1800132d6  cmp     [rbp+pfResult], 0
0x1800132da  jnz     short loc_1800132EE
0x1800132dc  mov     ebx, 0C0000061h
0x1800132e1  mov     r9d, 6Bh ; 'k'
0x1800132e7  mov     ecx, 0C0000061h
0x1800132ec  jmp     short loc_1800132C1
0x1800132ee  xor     ebx, ebx
0x1800132f0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800132f4  test    rcx, rcx
0x1800132f7  jz      short loc_180013305
0x1800132f9  call    cs:__imp_CloseHandle
0x180013300  nop     dword ptr [rax+rax+00h]
0x180013305  mov     eax, ebx
0x180013307  mov     rcx, [rbp+var_8]
0x18001330b  xor     rcx, rsp; StackCookie
0x18001330e  call    __security_check_cookie
0x180013313  mov     rbx, [rsp+70h+arg_0]
0x18001331b  add     rsp, 70h
0x18001331f  pop     rbp
0x180013320  retn
```
