# CSessEnvRpc::SetPrivilege(ushort const *,int)

- ea: `0x180036ef8`
- end: `0x180037050`
- name: `?SetPrivilege@CSessEnvRpc@@SAJPEBGH@Z`
- size: `344`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017e40`

## callees

- `0x18001a280`
- `0x180036ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003702e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003702e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036f37`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036f49`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180036f49`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180036fc0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180037015`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180036fc0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180037015`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180036f7e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180036f7e`

## string_xrefs

- `0x180036f77`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall CSessEnvRpc::SetPrivilege(const unsigned __int16 *a1, int a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  DWORD v6; // ecx
  DWORD v7; // ecx
  DWORD BufferLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+58h] [rbp-18h] BYREF

  Luid = 0;
  NewState = 0;
  BufferLength = 16;
  PreviousState = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    goto LABEL_2;
  if ( !LookupPrivilegeValueW(0, L"SeRestorePrivilege", &Luid) )
    goto LABEL_2;
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &BufferLength) )
    goto LABEL_2;
  v6 = PreviousState.PrivilegeCount ? PreviousState.Privileges[0].Attributes : 0;
  PreviousState.Privileges[0].Luid = Luid;
  PreviousState.PrivilegeCount = 1;
  v7 = a2 ? v6 | 2 : v6 & 0xFFFFFFFD;
  PreviousState.Privileges[0].Attributes = v7;
  if ( AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, BufferLength, 0, 0) )
  {
    v5 = 0;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x180036ef8  mov     [rsp-8+arg_0], rbx
0x180036efd  push    rbp
0x180036efe  mov     rbp, rsp
0x180036f01  sub     rsp, 70h
0x180036f05  mov     rax, cs:__security_cookie
0x180036f0c  xor     rax, rsp
0x180036f0f  mov     [rbp+var_8], rax
0x180036f13  xorps   xmm0, xmm0
0x180036f16  mov     qword ptr [rbp+Luid.LowPart], 0
0x180036f1e  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180036f22  mov     ebx, edx
0x180036f24  mov     [rbp+BufferLength], 10h
0x180036f2b  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm0
0x180036f2f  mov     [rbp+TokenHandle], 0
0x180036f37  call    cs:__imp_GetCurrentProcess
0x180036f3d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180036f41  mov     edx, 28h ; '('; DesiredAccess
0x180036f46  mov     rcx, rax; ProcessHandle
0x180036f49  call    cs:__imp_OpenProcessToken
0x180036f4f  test    eax, eax
0x180036f51  jnz     short loc_180036F71
0x180036f53  call    cs:__imp_GetLastError
0x180036f59  mov     ebx, eax
0x180036f5b  test    eax, eax
0x180036f5d  jle     loc_180037025
0x180036f63  movzx   ebx, ax
0x180036f66  or      ebx, 80070000h
0x180036f6c  jmp     loc_180037025
0x180036f71  lea     r8, [rbp+Luid]; lpLuid
0x180036f75  xor     ecx, ecx; lpSystemName
0x180036f77  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x180036f7e  call    cs:__imp_LookupPrivilegeValueW
0x180036f84  test    eax, eax
0x180036f86  jz      short loc_180036F53
0x180036f88  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180036f8c  lea     r8, [rbp+NewState]; NewState
0x180036f90  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180036f94  mov     r9d, 10h; BufferLength
0x180036f9a  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180036f9e  xor     edx, edx; DisableAllPrivileges
0x180036fa0  lea     rax, [rbp+BufferLength]
0x180036fa4  mov     [rbp+NewState.PrivilegeCount], 1
0x180036fab  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180036fb0  lea     rax, [rbp+var_28]
0x180036fb4  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180036fb9  mov     [rbp+NewState.Privileges.Attributes], 0
0x180036fc0  call    cs:__imp_AdjustTokenPrivileges
0x180036fc6  test    eax, eax
0x180036fc8  jz      short loc_180036F53
0x180036fca  cmp     [rbp+var_28.PrivilegeCount], 0
0x180036fce  jnz     short loc_180036FD4
0x180036fd0  xor     ecx, ecx
0x180036fd2  jmp     short loc_180036FD7
0x180036fd4  mov     ecx, [rbp+var_28.Privileges.Attributes]
0x180036fd7  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180036fdb  mov     qword ptr [rbp+var_28.Privileges.Luid.LowPart], rax
0x180036fdf  mov     [rbp+var_28.PrivilegeCount], 1
0x180036fe6  test    ebx, ebx
0x180036fe8  jz      short loc_180036FEF
0x180036fea  or      ecx, 2
0x180036fed  jmp     short loc_180036FF2
0x180036fef  and     ecx, 0FFFFFFFDh
0x180036ff2  mov     r9d, [rbp+BufferLength]; BufferLength
0x180036ff6  lea     r8, [rbp+var_28]; NewState
0x180036ffa  mov     [rbp+var_28.Privileges.Attributes], ecx
0x180036ffd  xor     edx, edx; DisableAllPrivileges
0x180036fff  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180037003  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x18003700c  mov     [rsp+70h+PreviousState], 0; PreviousState
0x180037015  call    cs:__imp_AdjustTokenPrivileges
0x18003701b  test    eax, eax
0x18003701d  jz      loc_180036F53
0x180037023  xor     ebx, ebx
0x180037025  mov     rcx, [rbp+TokenHandle]; hObject
0x180037029  test    rcx, rcx
0x18003702c  jz      short loc_180037034
0x18003702e  call    cs:__imp_CloseHandle
0x180037034  mov     eax, ebx
0x180037036  mov     rcx, [rbp+var_8]
0x18003703a  xor     rcx, rsp; StackCookie
0x18003703d  call    __security_check_cookie
0x180037042  mov     rbx, [rsp+70h+arg_0]
0x18003704a  add     rsp, 70h
0x18003704e  pop     rbp
0x18003704f  retn
```
