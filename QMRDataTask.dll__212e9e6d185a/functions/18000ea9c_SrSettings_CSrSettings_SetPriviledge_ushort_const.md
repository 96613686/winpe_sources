# SrSettings::CSrSettings::SetPriviledge(ushort const *)

- ea: `0x18000ea9c`
- end: `0x18000ebf2`
- name: `?SetPriviledge@CSrSettings@SrSettings@@AEAAJPEBG@Z`
- size: `342`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e074`

## callees

- `0x18000ea9c`
- `0x180010a0c`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000eb07`
- `KERNEL32!GetLastError` at `0x18000eb3f`
- `KERNEL32!GetLastError` at `0x18000eb97`
- `KERNEL32!GetLastError` at `0x18000eb07`
- `KERNEL32!GetLastError` at `0x18000eb3f`
- `KERNEL32!GetLastError` at `0x18000eb97`
- `KERNEL32!GetCurrentProcess` at `0x18000eaeb`
- `KERNEL32!GetCurrentProcess` at `0x18000eaeb`
- `KERNEL32!CloseHandle` at `0x18000ebcc`
- `KERNEL32!CloseHandle` at `0x18000ebcc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000eb8d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000eb8d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000eafd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000eafd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000eb35`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000eb35`

## string_xrefs

- `0x18000eac7`: `SeTakeOwnershipPrivilege`
- `0x18000eb2e`: `SeTakeOwnershipPrivilege`
- `0x18000eb1c`: `Failed to open process token. Error: 0x%08x`
- `0x18000eb54`: `Failed to lookup privilege value. Error: 0x%08x`
- `0x18000ebac`: `Failed to adjust token privileges. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::SetPriviledge(SrSettings::CSrSettings *this, const unsigned __int16 *a2)
{
  HANDLE CurrentProcess; // rax
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int v6; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  Luid = 0;
  NewState = 0;
  SrSettings::CSrSettings::Trace(this, 0, L"Setting priviledge %s", L"SeTakeOwnershipPrivilege");
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, L"SeTakeOwnershipPrivilege", &Luid) )
    {
      v5 = 0;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Luid = Luid;
      NewState.Privileges[0].Attributes = 2;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        SrSettings::CSrSettings::Trace(this, 2, L"Failed to adjust token privileges. Error: 0x%08x", v5);
      }
    }
    else
    {
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to lookup privilege value. Error: 0x%08x", v5);
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to open process token. Error: 0x%08x", v5);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18000ea9c  mov     [rsp-8+arg_8], rbx
0x18000eaa1  mov     [rsp-8+arg_10], rdi
0x18000eaa6  push    rbp
0x18000eaa7  mov     rbp, rsp
0x18000eaaa  sub     rsp, 60h
0x18000eaae  mov     rax, cs:__security_cookie
0x18000eab5  xor     rax, rsp
0x18000eab8  mov     [rbp+var_10], rax
0x18000eabc  xorps   xmm0, xmm0
0x18000eabf  mov     [rbp+TokenHandle], 0
0x18000eac7  lea     r9, Name; "SeTakeOwnershipPrivilege"
0x18000eace  mov     qword ptr [rbp+Luid.LowPart], 0
0x18000ead6  lea     r8, aSettingPrivile; "Setting priviledge %s"
0x18000eadd  xor     edx, edx
0x18000eadf  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18000eae3  mov     rdi, rcx
0x18000eae6  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000eaeb  call    cs:__imp_GetCurrentProcess
0x18000eaf1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000eaf5  mov     edx, 28h ; '('; DesiredAccess
0x18000eafa  mov     rcx, rax; ProcessHandle
0x18000eafd  call    cs:__imp_OpenProcessToken
0x18000eb03  test    eax, eax
0x18000eb05  jnz     short loc_18000EB28
0x18000eb07  call    cs:__imp_GetLastError
0x18000eb0d  mov     ebx, eax
0x18000eb0f  test    eax, eax
0x18000eb11  jle     short loc_18000EB1C
0x18000eb13  movzx   ebx, ax
0x18000eb16  or      ebx, 80070000h
0x18000eb1c  lea     r8, aFailedToOpenPr; "Failed to open process token. Error: 0x"...
0x18000eb23  jmp     loc_18000EBB3
0x18000eb28  lea     r8, [rbp+Luid]; lpLuid
0x18000eb2c  xor     ecx, ecx; lpSystemName
0x18000eb2e  lea     rdx, Name; "SeTakeOwnershipPrivilege"
0x18000eb35  call    cs:__imp_LookupPrivilegeValueW
0x18000eb3b  test    eax, eax
0x18000eb3d  jnz     short loc_18000EB5D
0x18000eb3f  call    cs:__imp_GetLastError
0x18000eb45  mov     ebx, eax
0x18000eb47  test    eax, eax
0x18000eb49  jle     short loc_18000EB54
0x18000eb4b  movzx   ebx, ax
0x18000eb4e  or      ebx, 80070000h
0x18000eb54  lea     r8, aFailedToLookup; "Failed to lookup privilege value. Error"...
0x18000eb5b  jmp     short loc_18000EBB3
0x18000eb5d  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18000eb61  lea     r8, [rbp+NewState]; NewState
0x18000eb65  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000eb69  xor     ebx, ebx
0x18000eb6b  mov     [rsp+60h+ReturnLength], rbx; ReturnLength
0x18000eb70  xor     edx, edx; DisableAllPrivileges
0x18000eb72  mov     [rbp+NewState.PrivilegeCount], 1
0x18000eb79  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18000eb7d  lea     r9d, [rbx+10h]; BufferLength
0x18000eb81  mov     [rbp+NewState.Privileges.Attributes], 2
0x18000eb88  mov     [rsp+60h+PreviousState], rbx; PreviousState
0x18000eb8d  call    cs:__imp_AdjustTokenPrivileges
0x18000eb93  test    eax, eax
0x18000eb95  jnz     short loc_18000EBC3
0x18000eb97  call    cs:__imp_GetLastError
0x18000eb9d  mov     ebx, eax
0x18000eb9f  test    eax, eax
0x18000eba1  jle     short loc_18000EBAC
0x18000eba3  movzx   ebx, ax
0x18000eba6  or      ebx, 80070000h
0x18000ebac  lea     r8, aFailedToAdjust; "Failed to adjust token privileges. Erro"...
0x18000ebb3  mov     r9d, ebx
0x18000ebb6  mov     edx, 2
0x18000ebbb  mov     rcx, rdi
0x18000ebbe  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ebc3  mov     rcx, [rbp+TokenHandle]; hObject
0x18000ebc7  test    rcx, rcx
0x18000ebca  jz      short loc_18000EBD2
0x18000ebcc  call    cs:__imp_CloseHandle
0x18000ebd2  mov     eax, ebx
0x18000ebd4  mov     rcx, [rbp+var_10]
0x18000ebd8  xor     rcx, rsp; StackCookie
0x18000ebdb  call    __security_check_cookie
0x18000ebe0  lea     r11, [rsp+60h+var_s0]
0x18000ebe5  mov     rbx, [r11+18h]
0x18000ebe9  mov     rdi, [r11+20h]
0x18000ebed  mov     rsp, r11
0x18000ebf0  pop     rbp
0x18000ebf1  retn
```
