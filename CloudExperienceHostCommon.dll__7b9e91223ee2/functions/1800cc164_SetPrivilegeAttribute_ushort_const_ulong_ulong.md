# SetPrivilegeAttribute(ushort const *,ulong,ulong *)

- ea: `0x1800cc164`
- end: `0x1800cc24c`
- name: `?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z`
- size: `232`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180049674`
- `0x180049ff0`

## callees

- `0x18001a540`
- `0x1800cc0c8`
- `0x1800cc164`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc224`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc21c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc21c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800cc1fc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800cc1fc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800cc19e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800cc19e`

## string_xrefs

- `0x1800cc195`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall SetPrivilegeAttribute(const unsigned __int16 *a1, DWORD a2, unsigned int *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  Luid = 0;
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid)
    && (TokenHandle = 0, (int)SHOpenEffectiveToken(v6, v5, &TokenHandle) >= 0) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a2;
    PreviousState = 0;
    ReturnLength = 16;
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) && a3 )
      *a3 = PreviousState.Privileges[0].Attributes;
    LastError = GetLastError();
    CloseHandle(TokenHandle);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800cc164  mov     [rsp-8+arg_0], rbx
0x1800cc169  mov     [rsp-8+arg_8], rdi
0x1800cc16e  push    rbp
0x1800cc16f  mov     rbp, rsp
0x1800cc172  sub     rsp, 70h
0x1800cc176  mov     rax, cs:__security_cookie
0x1800cc17d  xor     rax, rsp
0x1800cc180  mov     [rbp+var_8], rax
0x1800cc184  mov     rbx, r8
0x1800cc187  mov     qword ptr [rbp+Luid.LowPart], 0
0x1800cc18f  mov     edi, edx
0x1800cc191  lea     r8, [rbp+Luid]; lpLuid
0x1800cc195  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x1800cc19c  xor     ecx, ecx; lpSystemName
0x1800cc19e  call    cs:__imp_LookupPrivilegeValueW
0x1800cc1a4  test    eax, eax
0x1800cc1a6  jz      short loc_1800CC224
0x1800cc1a8  lea     r8, [rbp+TokenHandle]; void **
0x1800cc1ac  mov     [rbp+TokenHandle], 0
0x1800cc1b4  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800cc1b9  test    eax, eax
0x1800cc1bb  js      short loc_1800CC224
0x1800cc1bd  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800cc1c1  lea     r8, [rbp+NewState]; NewState
0x1800cc1c5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800cc1c9  xorps   xmm0, xmm0
0x1800cc1cc  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x1800cc1d0  mov     r9d, 10h; BufferLength
0x1800cc1d6  lea     rax, [rbp+var_40]
0x1800cc1da  mov     [rbp+NewState.PrivilegeCount], 1
0x1800cc1e1  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800cc1e6  xor     edx, edx; DisableAllPrivileges
0x1800cc1e8  lea     rax, [rbp+var_18]
0x1800cc1ec  mov     [rbp+NewState.Privileges.Attributes], edi
0x1800cc1ef  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800cc1f4  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm0
0x1800cc1f8  mov     [rbp+var_40], r9d
0x1800cc1fc  call    cs:__imp_AdjustTokenPrivileges
0x1800cc202  test    eax, eax
0x1800cc204  jz      short loc_1800CC210
0x1800cc206  test    rbx, rbx
0x1800cc209  jz      short loc_1800CC210
0x1800cc20b  mov     eax, [rbp+var_18.Privileges.Attributes]
0x1800cc20e  mov     [rbx], eax
0x1800cc210  call    cs:__imp_GetLastError
0x1800cc216  mov     rcx, [rbp+TokenHandle]; hObject
0x1800cc21a  mov     ebx, eax
0x1800cc21c  call    cs:__imp_CloseHandle
0x1800cc222  jmp     short loc_1800CC22C
0x1800cc224  call    cs:__imp_GetLastError
0x1800cc22a  mov     ebx, eax
0x1800cc22c  mov     eax, ebx
0x1800cc22e  mov     rcx, [rbp+var_8]
0x1800cc232  xor     rcx, rsp; StackCookie
0x1800cc235  call    __security_check_cookie
0x1800cc23a  lea     r11, [rsp+70h+var_s0]
0x1800cc23f  mov     rbx, [r11+10h]
0x1800cc243  mov     rdi, [r11+18h]
0x1800cc247  mov     rsp, r11
0x1800cc24a  pop     rbp
0x1800cc24b  retn
```
