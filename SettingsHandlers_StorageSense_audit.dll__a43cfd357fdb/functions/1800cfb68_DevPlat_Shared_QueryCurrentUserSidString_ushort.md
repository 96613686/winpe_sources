# DevPlat::Shared::QueryCurrentUserSidString(ushort * *)

- ea: `0x1800cfb68`
- end: `0x1800cfc42`
- name: `?QueryCurrentUserSidString@Shared@DevPlat@@YAJPEAPEAG@Z`
- size: `218`
- prototype: `__int64 __fastcall(LPWSTR *StringSid, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c89b0`
- `0x1800c9be4`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x1800cfb68`
- `0x1800cfc48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfbfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfbfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cfbb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cfbb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cfbc9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cfbc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cfc19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cfc19`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cfbf0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cfbf0`

## pseudocode

```c
__int64 __fastcall DevPlat::Shared::QueryCurrentUserSidString(LPWSTR *StringSid, unsigned __int16 **a2)
{
  int TokenInformation; // ebx
  HANDLE CurrentProcess; // rax
  struct DevPlat::Shared::_EM_SID *v5; // r8
  unsigned int *v6; // r9
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-78h] BYREF
  _BYTE Sid[80]; // [rsp+30h] [rbp-68h] BYREF

  TokenHandle = 0;
  memset_0(Sid, 0, 0x44u);
  if ( StringSid )
  {
    *StringSid = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle)
      || (TokenInformation = DevPlat::Shared::QueryTokenInformation(TokenHandle, Sid, v5, v6), TokenInformation >= 0)
      && !ConvertSidToStringSidW(Sid, StringSid) )
    {
      LastError = GetLastError();
      TokenInformation = LastError;
      if ( LastError > 0 )
        TokenInformation = (unsigned __int16)LastError | 0x80070000;
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)TokenInformation;
}

```

## disassembly

```asm
0x1800cfb68  mov     [rsp+arg_8], rbx
0x1800cfb6d  push    rdi
0x1800cfb6e  sub     rsp, 90h
0x1800cfb75  mov     rax, cs:__security_cookie
0x1800cfb7c  xor     rax, rsp
0x1800cfb7f  mov     [rsp+98h+var_18], rax
0x1800cfb87  xor     edx, edx; Val
0x1800cfb89  mov     [rsp+98h+TokenHandle], 0
0x1800cfb92  mov     rdi, rcx
0x1800cfb95  lea     rcx, [rsp+98h+Sid]; void *
0x1800cfb9a  lea     r8d, [rdx+44h]; Size
0x1800cfb9e  call    memset_0
0x1800cfba3  test    rdi, rdi
0x1800cfba6  jnz     short loc_1800CFBAF
0x1800cfba8  mov     ebx, 80070057h
0x1800cfbad  jmp     short loc_1800CFC1F
0x1800cfbaf  mov     qword ptr [rdi], 0
0x1800cfbb6  call    cs:__imp_GetCurrentProcess
0x1800cfbbc  lea     r8, [rsp+98h+TokenHandle]; TokenHandle
0x1800cfbc1  mov     edx, 8; DesiredAccess
0x1800cfbc6  mov     rcx, rax; ProcessHandle
0x1800cfbc9  call    cs:__imp_OpenProcessToken
0x1800cfbcf  test    eax, eax
0x1800cfbd1  jz      short loc_1800CFBFA
0x1800cfbd3  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x1800cfbd8  lea     rdx, [rsp+98h+Sid]; Sid
0x1800cfbdd  call    ?QueryTokenInformation@Shared@DevPlat@@YAJPEAXPEAU_EM_SID@12@PEAK@Z; DevPlat::Shared::QueryTokenInformation(void *,DevPlat::Shared::_EM_SID *,ulong *)
0x1800cfbe2  mov     ebx, eax
0x1800cfbe4  test    eax, eax
0x1800cfbe6  js      short loc_1800CFC0F
0x1800cfbe8  mov     rdx, rdi; StringSid
0x1800cfbeb  lea     rcx, [rsp+98h+Sid]; Sid
0x1800cfbf0  call    cs:__imp_ConvertSidToStringSidW
0x1800cfbf6  test    eax, eax
0x1800cfbf8  jnz     short loc_1800CFC0F
0x1800cfbfa  call    cs:__imp_GetLastError
0x1800cfc00  mov     ebx, eax
0x1800cfc02  test    eax, eax
0x1800cfc04  jle     short loc_1800CFC0F
0x1800cfc06  movzx   ebx, ax
0x1800cfc09  or      ebx, 80070000h
0x1800cfc0f  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x1800cfc14  test    rcx, rcx
0x1800cfc17  jz      short loc_1800CFC1F
0x1800cfc19  call    cs:__imp_CloseHandle
0x1800cfc1f  mov     eax, ebx
0x1800cfc21  mov     rcx, [rsp+98h+var_18]
0x1800cfc29  xor     rcx, rsp; StackCookie
0x1800cfc2c  call    __security_check_cookie
0x1800cfc31  mov     rbx, [rsp+98h+arg_8]
0x1800cfc39  add     rsp, 90h
0x1800cfc40  pop     rdi
0x1800cfc41  retn
```
