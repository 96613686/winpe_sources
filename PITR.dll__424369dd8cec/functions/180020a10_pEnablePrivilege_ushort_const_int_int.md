# pEnablePrivilege(ushort const *,int,int *)

- ea: `0x180020a10`
- end: `0x180020b18`
- name: `?pEnablePrivilege@@YAHPEBGHPEAH@Z`
- size: `264`
- prototype: `__int64 __fastcall(LPCWSTR lpName, int, int *)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800044f4`
- `0x180004dc8`
- `0x180005614`
- `0x180006530`
- `0x18000b280`
- `0x18000fab0`
- `0x1800170f0`

## callees

- `0x180020a10`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ad0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020a5c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020a5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020a4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020a4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aef`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180020ac6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180020ac6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180020a77`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180020a77`

## pseudocode

```c
__int64 __fastcall pEnablePrivilege(LPCWSTR lpName, int a2, int *a3)
{
  unsigned int v3; // edi
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-40h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  v3 = 0;
  if ( a3 )
    *a3 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    Luid = 0;
    if ( LookupPrivilegeValueW(0, lpName, &Luid) )
    {
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      PreviousState = 0;
      ReturnLength = 0;
      NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) )
      {
        if ( !GetLastError() )
        {
          v3 = 1;
          if ( a3 )
            *a3 = PreviousState.PrivilegeCount != 0;
        }
      }
    }
    CloseHandle(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x180020a10  mov     [rsp-18h+arg_8], rbx
0x180020a15  mov     [rsp-18h+arg_18], rsi
0x180020a1a  push    rbp
0x180020a1b  push    rdi
0x180020a1c  push    r14
0x180020a1e  mov     rbp, rsp
0x180020a21  sub     rsp, 70h
0x180020a25  mov     rax, cs:__security_cookie
0x180020a2c  xor     rax, rsp
0x180020a2f  mov     [rbp+var_8], rax
0x180020a33  xor     edi, edi
0x180020a35  mov     rbx, r8
0x180020a38  mov     r14d, edx
0x180020a3b  mov     rsi, rcx
0x180020a3e  test    r8, r8
0x180020a41  jz      short loc_180020A46
0x180020a43  mov     [r8], edi
0x180020a46  mov     [rbp+TokenHandle], rdi
0x180020a4a  call    cs:__imp_GetCurrentProcess
0x180020a50  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180020a54  mov     edx, 28h ; '('; DesiredAccess
0x180020a59  mov     rcx, rax; ProcessHandle
0x180020a5c  call    cs:__imp_OpenProcessToken
0x180020a62  test    eax, eax
0x180020a64  jz      loc_180020AF5
0x180020a6a  lea     r8, [rbp+Luid]; lpLuid
0x180020a6e  mov     qword ptr [rbp+Luid.LowPart], rdi
0x180020a72  mov     rdx, rsi; lpName
0x180020a75  xor     ecx, ecx; lpSystemName
0x180020a77  call    cs:__imp_LookupPrivilegeValueW
0x180020a7d  test    eax, eax
0x180020a7f  jz      short loc_180020AEB
0x180020a81  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180020a85  lea     r8, [rbp+NewState]; NewState
0x180020a89  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180020a8d  mov     esi, 1
0x180020a92  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180020a96  xorps   xmm0, xmm0
0x180020a99  neg     r14d
0x180020a9c  mov     [rbp+NewState.PrivilegeCount], esi
0x180020a9f  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm0
0x180020aa3  sbb     eax, eax
0x180020aa5  mov     [rbp+var_38], edi
0x180020aa8  and     eax, 2
0x180020aab  lea     r9d, [rsi+0Fh]; BufferLength
0x180020aaf  mov     [rbp+NewState.Privileges.Attributes], eax
0x180020ab2  xor     edx, edx; DisableAllPrivileges
0x180020ab4  lea     rax, [rbp+var_38]
0x180020ab8  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180020abd  lea     rax, [rbp+var_18]
0x180020ac1  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180020ac6  call    cs:__imp_AdjustTokenPrivileges
0x180020acc  test    eax, eax
0x180020ace  jz      short loc_180020AEB
0x180020ad0  call    cs:__imp_GetLastError
0x180020ad6  test    eax, eax
0x180020ad8  jnz     short loc_180020AEB
0x180020ada  mov     edi, esi
0x180020adc  test    rbx, rbx
0x180020adf  jz      short loc_180020AEB
0x180020ae1  xor     ecx, ecx
0x180020ae3  cmp     [rbp+var_18.PrivilegeCount], ecx
0x180020ae6  setnbe  cl
0x180020ae9  mov     [rbx], ecx
0x180020aeb  mov     rcx, [rbp+TokenHandle]; hObject
0x180020aef  call    cs:__imp_CloseHandle
0x180020af5  mov     eax, edi
0x180020af7  mov     rcx, [rbp+var_8]
0x180020afb  xor     rcx, rsp; StackCookie
0x180020afe  call    __security_check_cookie
0x180020b03  lea     r11, [rsp+70h+var_s0]
0x180020b08  mov     rbx, [r11+28h]
0x180020b0c  mov     rsi, [r11+38h]
0x180020b10  mov     rsp, r11
0x180020b13  pop     r14
0x180020b15  pop     rdi
0x180020b16  pop     rbp
0x180020b17  retn
```
