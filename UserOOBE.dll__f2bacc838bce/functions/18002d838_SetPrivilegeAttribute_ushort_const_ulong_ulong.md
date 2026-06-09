# SetPrivilegeAttribute(ushort const *,ulong,ulong *)

- ea: `0x18002d838`
- end: `0x18002d92c`
- name: `?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z`
- size: `244`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022eac`
- `0x18002abbc`

## callees

- `0x1800032b0`
- `0x18001e7e0`
- `0x18002d838`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d8fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d8fc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002d8dc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002d8dc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002d872`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002d872`

## string_xrefs

- `0x18002d869`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall SetPrivilegeAttribute(const unsigned __int16 *a1, DWORD a2, unsigned int *a3)
{
  DWORD LastError; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  Luid = 0;
  if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &Luid)
    && (TokenHandle = 0, (int)SHOpenEffectiveToken(0x28u, 1, &TokenHandle) >= 0) )
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
0x18002d838  mov     [rsp-8+arg_0], rbx
0x18002d83d  mov     [rsp-8+arg_8], rdi
0x18002d842  push    rbp
0x18002d843  mov     rbp, rsp
0x18002d846  sub     rsp, 70h
0x18002d84a  mov     rax, cs:__security_cookie
0x18002d851  xor     rax, rsp
0x18002d854  mov     [rbp+var_8], rax
0x18002d858  mov     rbx, r8
0x18002d85b  mov     qword ptr [rbp+Luid.LowPart], 0
0x18002d863  mov     edi, edx
0x18002d865  lea     r8, [rbp+Luid]; lpLuid
0x18002d869  lea     rdx, Name; "SeShutdownPrivilege"
0x18002d870  xor     ecx, ecx; lpSystemName
0x18002d872  call    cs:__imp_LookupPrivilegeValueW
0x18002d878  test    eax, eax
0x18002d87a  jz      loc_18002D904
0x18002d880  mov     edx, 1; int
0x18002d885  mov     [rbp+TokenHandle], 0
0x18002d88d  lea     r8, [rbp+TokenHandle]; void **
0x18002d891  lea     ecx, [rdx+27h]; DesiredAccess
0x18002d894  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18002d899  test    eax, eax
0x18002d89b  js      short loc_18002D904
0x18002d89d  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18002d8a1  lea     r8, [rbp+NewState]; NewState
0x18002d8a5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002d8a9  xorps   xmm0, xmm0
0x18002d8ac  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18002d8b0  mov     r9d, 10h; BufferLength
0x18002d8b6  lea     rax, [rbp+var_40]
0x18002d8ba  mov     [rbp+NewState.PrivilegeCount], 1
0x18002d8c1  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002d8c6  xor     edx, edx; DisableAllPrivileges
0x18002d8c8  lea     rax, [rbp+var_18]
0x18002d8cc  mov     [rbp+NewState.Privileges.Attributes], edi
0x18002d8cf  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18002d8d4  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm0
0x18002d8d8  mov     [rbp+var_40], r9d
0x18002d8dc  call    cs:__imp_AdjustTokenPrivileges
0x18002d8e2  test    eax, eax
0x18002d8e4  jz      short loc_18002D8F0
0x18002d8e6  test    rbx, rbx
0x18002d8e9  jz      short loc_18002D8F0
0x18002d8eb  mov     eax, [rbp+var_18.Privileges.Attributes]
0x18002d8ee  mov     [rbx], eax
0x18002d8f0  call    cs:__imp_GetLastError
0x18002d8f6  mov     rcx, [rbp+TokenHandle]; hObject
0x18002d8fa  mov     ebx, eax
0x18002d8fc  call    cs:__imp_CloseHandle
0x18002d902  jmp     short loc_18002D90C
0x18002d904  call    cs:__imp_GetLastError
0x18002d90a  mov     ebx, eax
0x18002d90c  mov     eax, ebx
0x18002d90e  mov     rcx, [rbp+var_8]
0x18002d912  xor     rcx, rsp; StackCookie
0x18002d915  call    __security_check_cookie
0x18002d91a  lea     r11, [rsp+70h+var_s0]
0x18002d91f  mov     rbx, [r11+10h]
0x18002d923  mov     rdi, [r11+18h]
0x18002d927  mov     rsp, r11
0x18002d92a  pop     rbp
0x18002d92b  retn
```
