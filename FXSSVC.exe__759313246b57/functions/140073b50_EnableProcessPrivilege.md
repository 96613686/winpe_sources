# EnableProcessPrivilege

- ea: `0x140073b50`
- end: `0x140073d53`
- name: `EnableProcessPrivilege`
- size: `515`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14004ae64`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140073b50`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x140073c41`
- `ADVAPI32!OpenProcessToken` at `0x140073c41`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140073bc7`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140073bc7`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140073c97`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140073c97`
- `KERNEL32!GetLastError` at `0x140073bd7`
- `KERNEL32!GetLastError` at `0x140073c51`
- `KERNEL32!GetLastError` at `0x140073ca7`
- `KERNEL32!GetLastError` at `0x140073d12`
- `KERNEL32!GetLastError` at `0x140073bd7`
- `KERNEL32!GetLastError` at `0x140073c51`
- `KERNEL32!GetLastError` at `0x140073ca7`
- `KERNEL32!GetLastError` at `0x140073d12`
- `KERNEL32!CloseHandle` at `0x140073cea`
- `KERNEL32!CloseHandle` at `0x140073cea`
- `KERNEL32!GetCurrentProcess` at `0x140073c29`
- `KERNEL32!GetCurrentProcess` at `0x140073c29`

## string_xrefs

- `0x140073bc0`: `SeAuditPrivilege`

## pseudocode

```c
__int64 EnableProcessPrivilege()
{
  DWORD LastError; // eax
  DWORD v1; // ebx
  CMapDeviceId *v2; // rcx
  __int64 v3; // rdx
  HANDLE CurrentProcess; // rax
  DWORD v5; // eax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  NewState = 0;
  Luid = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
  }
  if ( LookupPrivilegeValueW(0, L"SeAuditPrivilege", &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
    {
      v1 = 0;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        LastError = GetLastError();
        v1 = LastError;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v3 = 18;
          goto LABEL_20;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 17;
        goto LABEL_20;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 16;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LastError);
    }
  }
  if ( TokenHandle
    && !CloseHandle(TokenHandle)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, v5);
  }
  return v1;
}

```

## disassembly

```asm
0x140073b50  push    rbp
0x140073b52  push    rbx
0x140073b53  push    r14
0x140073b55  push    r15
0x140073b57  mov     rbp, rsp
0x140073b5a  sub     rsp, 68h
0x140073b5e  mov     rax, cs:__security_cookie
0x140073b65  xor     rax, rsp
0x140073b68  mov     [rbp+var_18], rax
0x140073b6c  xorps   xmm0, xmm0
0x140073b6f  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140073b77  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x140073b7b  mov     qword ptr [rbp+Luid.LowPart], 0
0x140073b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b8a  lea     r14, WPP_GLOBAL_Control
0x140073b91  lea     r15, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x140073b98  cmp     rcx, r14
0x140073b9b  jz      short loc_140073BBA
0x140073b9d  test    byte ptr [rcx+1Ch], 2
0x140073ba1  jz      short loc_140073BBA
0x140073ba3  cmp     byte ptr [rcx+19h], 5
0x140073ba7  jb      short loc_140073BBA
0x140073ba9  mov     rcx, [rcx+10h]
0x140073bad  mov     edx, 0Fh
0x140073bb2  mov     r8, r15
0x140073bb5  call    WPP_SF_
0x140073bba  lea     r8, [rbp+Luid]; lpLuid
0x140073bbe  xor     ecx, ecx; lpSystemName
0x140073bc0  lea     rdx, Name; "SeAuditPrivilege"
0x140073bc7  call    cs:__imp_LookupPrivilegeValueW
0x140073bce  nop     dword ptr [rax+rax+00h]
0x140073bd3  test    eax, eax
0x140073bd5  jnz     short loc_140073C13
0x140073bd7  call    cs:__imp_GetLastError
0x140073bde  nop     dword ptr [rax+rax+00h]
0x140073be3  mov     ebx, eax
0x140073be5  mov     rcx, cs:WPP_GLOBAL_Control
0x140073bec  cmp     rcx, r14
0x140073bef  jz      loc_140073CE1
0x140073bf5  test    byte ptr [rcx+1Ch], 2
0x140073bf9  jz      loc_140073CE1
0x140073bff  cmp     byte ptr [rcx+19h], 2
0x140073c03  jb      loc_140073CE1
0x140073c09  mov     edx, 10h
0x140073c0e  jmp     loc_140073CD2
0x140073c13  mov     rax, qword ptr [rbp+Luid.LowPart]
0x140073c17  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x140073c1b  mov     [rbp+NewState.PrivilegeCount], 1
0x140073c22  mov     [rbp+NewState.Privileges.Attributes], 2
0x140073c29  call    cs:__imp_GetCurrentProcess
0x140073c30  nop     dword ptr [rax+rax+00h]
0x140073c35  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140073c39  mov     edx, 20h ; ' '; DesiredAccess
0x140073c3e  mov     rcx, rax; ProcessHandle
0x140073c41  call    cs:__imp_OpenProcessToken
0x140073c48  nop     dword ptr [rax+rax+00h]
0x140073c4d  test    eax, eax
0x140073c4f  jnz     short loc_140073C7E
0x140073c51  call    cs:__imp_GetLastError
0x140073c58  nop     dword ptr [rax+rax+00h]
0x140073c5d  mov     ebx, eax
0x140073c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140073c66  cmp     rcx, r14
0x140073c69  jz      short loc_140073CE1
0x140073c6b  test    byte ptr [rcx+1Ch], 2
0x140073c6f  jz      short loc_140073CE1
0x140073c71  cmp     byte ptr [rcx+19h], 2
0x140073c75  jb      short loc_140073CE1
0x140073c77  mov     edx, 11h
0x140073c7c  jmp     short loc_140073CD2
0x140073c7e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140073c82  lea     r8, [rbp+NewState]; NewState
0x140073c86  xor     ebx, ebx
0x140073c88  xor     r9d, r9d; BufferLength
0x140073c8b  mov     [rsp+68h+ReturnLength], rbx; ReturnLength
0x140073c90  xor     edx, edx; DisableAllPrivileges
0x140073c92  mov     [rsp+68h+PreviousState], rbx; PreviousState
0x140073c97  call    cs:__imp_AdjustTokenPrivileges
0x140073c9e  nop     dword ptr [rax+rax+00h]
0x140073ca3  test    eax, eax
0x140073ca5  jnz     short loc_140073CE1
0x140073ca7  call    cs:__imp_GetLastError
0x140073cae  nop     dword ptr [rax+rax+00h]
0x140073cb3  mov     ebx, eax
0x140073cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140073cbc  cmp     rcx, r14
0x140073cbf  jz      short loc_140073CE1
0x140073cc1  test    byte ptr [rcx+1Ch], 2
0x140073cc5  jz      short loc_140073CE1
0x140073cc7  cmp     byte ptr [rcx+19h], 2
0x140073ccb  jb      short loc_140073CE1
0x140073ccd  mov     edx, 12h
0x140073cd2  mov     rcx, [rcx+10h]
0x140073cd6  mov     r9d, eax
0x140073cd9  mov     r8, r15
0x140073cdc  call    WPP_SF_d
0x140073ce1  mov     rcx, [rbp+TokenHandle]; hObject
0x140073ce5  test    rcx, rcx
0x140073ce8  jz      short loc_140073D39
0x140073cea  call    cs:__imp_CloseHandle
0x140073cf1  nop     dword ptr [rax+rax+00h]
0x140073cf6  test    eax, eax
0x140073cf8  jnz     short loc_140073D39
0x140073cfa  mov     rax, cs:WPP_GLOBAL_Control
0x140073d01  cmp     rax, r14
0x140073d04  jz      short loc_140073D39
0x140073d06  test    byte ptr [rax+1Ch], 2
0x140073d0a  jz      short loc_140073D39
0x140073d0c  cmp     byte ptr [rax+19h], 2
0x140073d10  jb      short loc_140073D39
0x140073d12  call    cs:__imp_GetLastError
0x140073d19  nop     dword ptr [rax+rax+00h]
0x140073d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d25  mov     edx, 13h
0x140073d2a  mov     r9d, eax
0x140073d2d  mov     r8, r15
0x140073d30  mov     rcx, [rcx+10h]
0x140073d34  call    WPP_SF_d
0x140073d39  mov     eax, ebx
0x140073d3b  mov     rcx, [rbp+var_18]
0x140073d3f  xor     rcx, rsp; StackCookie
0x140073d42  call    __security_check_cookie
0x140073d47  add     rsp, 68h
0x140073d4b  pop     r15
0x140073d4d  pop     r14
0x140073d4f  pop     rbx
0x140073d50  pop     rbp
0x140073d51  retn
```
