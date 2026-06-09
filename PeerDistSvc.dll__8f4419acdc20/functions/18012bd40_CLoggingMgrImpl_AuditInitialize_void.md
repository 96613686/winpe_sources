# CLoggingMgrImpl::AuditInitialize(void)

- ea: `0x18012bd40`
- end: `0x18012beb7`
- name: `?AuditInitialize@CLoggingMgrImpl@@AEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(CLoggingMgrImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012b880`

## callees

- `0x180008290`
- `0x18012bd40`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012be0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012be43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012be0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012be43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18012bd66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18012bd66`
- `KERNEL32!CloseHandle` at `0x18012be9c`
- `KERNEL32!CloseHandle` at `0x18012be9c`
- `ADVAPI32!OpenProcessToken` at `0x18012bd79`
- `ADVAPI32!OpenProcessToken` at `0x18012bd79`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18012be00`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18012be00`

## pseudocode

```c
__int64 __fastcall CLoggingMgrImpl::AuditInitialize(CLoggingMgrImpl *this)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  CHostedCacheMsgEncoding *v3; // rcx
  __int64 v4; // rdx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  NewState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    NewState.Privileges[0].Luid = (LUID)21LL;
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
    {
      LastError = GetLastError();
      if ( !LastError )
      {
        LastError = 0;
        goto LABEL_20;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v4 = 11;
        goto LABEL_17;
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v4 = 12;
        goto LABEL_17;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v4 = 10;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v3 + 12), v4, WPP_65552b8c4e7b3865e4dedb40c7613b4b_Traceguids, LastError);
    }
  }
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18012bd40  push    rbx
0x18012bd42  sub     rsp, 50h
0x18012bd46  mov     rax, cs:__security_cookie
0x18012bd4d  xor     rax, rsp
0x18012bd50  mov     [rsp+58h+var_10], rax
0x18012bd55  xorps   xmm0, xmm0
0x18012bd58  mov     [rsp+58h+TokenHandle], 0
0x18012bd61  movups  xmmword ptr [rsp+58h+NewState.PrivilegeCount], xmm0
0x18012bd66  call    cs:__imp_GetCurrentProcess
0x18012bd6c  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18012bd71  mov     edx, 28h ; '('; DesiredAccess
0x18012bd76  mov     rcx, rax; ProcessHandle
0x18012bd79  call    cs:__imp_OpenProcessToken
0x18012bd7f  test    eax, eax
0x18012bd81  jnz     short loc_18012BDC3
0x18012bd83  call    cs:__imp_GetLastError
0x18012bd89  mov     ebx, eax
0x18012bd8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18012bd92  lea     rax, WPP_GLOBAL_Control
0x18012bd99  cmp     rcx, rax
0x18012bd9c  jz      loc_18012BE85
0x18012bda2  test    dword ptr [rcx+6Ch], 2000h
0x18012bda9  jz      loc_18012BE85
0x18012bdaf  cmp     byte ptr [rcx+69h], 1
0x18012bdb3  jb      loc_18012BE85
0x18012bdb9  mov     edx, 0Ah
0x18012bdbe  jmp     loc_18012BE72
0x18012bdc3  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18012bdc8  lea     r8, [rsp+58h+NewState]; NewState
0x18012bdcd  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18012bdd6  mov     r9d, 10h; BufferLength
0x18012bddc  xor     edx, edx; DisableAllPrivileges
0x18012bdde  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18012bde7  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x18012bdef  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x18012bdf7  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], 15h
0x18012be00  call    cs:__imp_AdjustTokenPrivileges
0x18012be06  test    eax, eax
0x18012be08  jz      short loc_18012BE43
0x18012be0a  call    cs:__imp_GetLastError
0x18012be10  mov     ebx, eax
0x18012be12  test    eax, eax
0x18012be14  jz      short loc_18012BE3F
0x18012be16  mov     rcx, cs:WPP_GLOBAL_Control
0x18012be1d  lea     rax, WPP_GLOBAL_Control
0x18012be24  cmp     rcx, rax
0x18012be27  jz      short loc_18012BE85
0x18012be29  test    dword ptr [rcx+6Ch], 2000h
0x18012be30  jz      short loc_18012BE85
0x18012be32  cmp     byte ptr [rcx+69h], 1
0x18012be36  jb      short loc_18012BE85
0x18012be38  mov     edx, 0Bh
0x18012be3d  jmp     short loc_18012BE72
0x18012be3f  xor     ebx, ebx
0x18012be41  jmp     short loc_18012BE92
0x18012be43  call    cs:__imp_GetLastError
0x18012be49  mov     ebx, eax
0x18012be4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18012be52  lea     rax, WPP_GLOBAL_Control
0x18012be59  cmp     rcx, rax
0x18012be5c  jz      short loc_18012BE85
0x18012be5e  test    dword ptr [rcx+6Ch], 2000h
0x18012be65  jz      short loc_18012BE85
0x18012be67  cmp     byte ptr [rcx+69h], 1
0x18012be6b  jb      short loc_18012BE85
0x18012be6d  mov     edx, 0Ch
0x18012be72  mov     rcx, [rcx+60h]
0x18012be76  lea     r8, WPP_65552b8c4e7b3865e4dedb40c7613b4b_Traceguids
0x18012be7d  mov     r9d, ebx
0x18012be80  call    WPP_SF_d
0x18012be85  test    ebx, ebx
0x18012be87  jle     short loc_18012BE92
0x18012be89  movzx   ebx, bx
0x18012be8c  or      ebx, 80070000h
0x18012be92  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18012be97  test    rcx, rcx
0x18012be9a  jz      short loc_18012BEA2
0x18012be9c  call    cs:__imp_CloseHandle
0x18012bea2  mov     eax, ebx
0x18012bea4  mov     rcx, [rsp+58h+var_10]
0x18012bea9  xor     rcx, rsp; StackCookie
0x18012beac  call    __security_check_cookie
0x18012beb1  add     rsp, 50h
0x18012beb5  pop     rbx
0x18012beb6  retn
```
