# SetPrivilegeAttribute(ushort const *,ulong,ulong *)

- ea: `0x140069988`
- end: `0x140069a7c`
- name: `?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z`
- size: `244`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x1400698d8`
- `0x140069988`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140069a4c`
- `KERNEL32!CloseHandle` at `0x140069a4c`
- `KERNEL32!GetLastError` at `0x140069a40`
- `KERNEL32!GetLastError` at `0x140069a54`
- `KERNEL32!GetLastError` at `0x140069a40`
- `KERNEL32!GetLastError` at `0x140069a54`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140069a2c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140069a2c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1400699c2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1400699c2`

## string_xrefs

- `0x1400699b9`: `SeShutdownPrivilege`

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
0x140069988  mov     [rsp-8+arg_0], rbx
0x14006998d  mov     [rsp-8+arg_8], rdi
0x140069992  push    rbp
0x140069993  mov     rbp, rsp
0x140069996  sub     rsp, 70h
0x14006999a  mov     rax, cs:__security_cookie
0x1400699a1  xor     rax, rsp
0x1400699a4  mov     [rbp+var_8], rax
0x1400699a8  mov     rbx, r8
0x1400699ab  mov     qword ptr [rbp+Luid.LowPart], 0
0x1400699b3  mov     edi, edx
0x1400699b5  lea     r8, [rbp+Luid]; lpLuid
0x1400699b9  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x1400699c0  xor     ecx, ecx; lpSystemName
0x1400699c2  call    cs:__imp_LookupPrivilegeValueW
0x1400699c8  test    eax, eax
0x1400699ca  jz      loc_140069A54
0x1400699d0  mov     edx, 1; int
0x1400699d5  mov     [rbp+TokenHandle], 0
0x1400699dd  lea     r8, [rbp+TokenHandle]; void **
0x1400699e1  lea     ecx, [rdx+27h]; DesiredAccess
0x1400699e4  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1400699e9  test    eax, eax
0x1400699eb  js      short loc_140069A54
0x1400699ed  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1400699f1  lea     r8, [rbp+NewState]; NewState
0x1400699f5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400699f9  xorps   xmm0, xmm0
0x1400699fc  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x140069a00  mov     r9d, 10h; BufferLength
0x140069a06  lea     rax, [rbp+var_40]
0x140069a0a  mov     [rbp+NewState.PrivilegeCount], 1
0x140069a11  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x140069a16  xor     edx, edx; DisableAllPrivileges
0x140069a18  lea     rax, [rbp+var_18]
0x140069a1c  mov     [rbp+NewState.Privileges.Attributes], edi
0x140069a1f  mov     [rsp+70h+PreviousState], rax; PreviousState
0x140069a24  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm0
0x140069a28  mov     [rbp+var_40], r9d
0x140069a2c  call    cs:__imp_AdjustTokenPrivileges
0x140069a32  test    eax, eax
0x140069a34  jz      short loc_140069A40
0x140069a36  test    rbx, rbx
0x140069a39  jz      short loc_140069A40
0x140069a3b  mov     eax, [rbp+var_18.Privileges.Attributes]
0x140069a3e  mov     [rbx], eax
0x140069a40  call    cs:__imp_GetLastError
0x140069a46  mov     rcx, [rbp+TokenHandle]; hObject
0x140069a4a  mov     ebx, eax
0x140069a4c  call    cs:__imp_CloseHandle
0x140069a52  jmp     short loc_140069A5C
0x140069a54  call    cs:__imp_GetLastError
0x140069a5a  mov     ebx, eax
0x140069a5c  mov     eax, ebx
0x140069a5e  mov     rcx, [rbp+var_8]
0x140069a62  xor     rcx, rsp; StackCookie
0x140069a65  call    __security_check_cookie
0x140069a6a  lea     r11, [rsp+70h+var_s0]
0x140069a6f  mov     rbx, [r11+10h]
0x140069a73  mov     rdi, [r11+18h]
0x140069a77  mov     rsp, r11
0x140069a7a  pop     rbp
0x140069a7b  retn
```
