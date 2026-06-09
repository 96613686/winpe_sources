# SrSettings::CSrSettings::SetPriviledge(ushort const *)

- ea: `0x18004a6b8`
- end: `0x18004a80e`
- name: `?SetPriviledge@CSrSettings@SrSettings@@AEAAJPEBG@Z`
- size: `342`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004a3bc`

## callees

- `0x18004a6b8`
- `0x18004c0e8`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004a723`
- `KERNEL32!GetLastError` at `0x18004a75b`
- `KERNEL32!GetLastError` at `0x18004a7b3`
- `KERNEL32!GetLastError` at `0x18004a723`
- `KERNEL32!GetLastError` at `0x18004a75b`
- `KERNEL32!GetLastError` at `0x18004a7b3`
- `KERNEL32!GetCurrentProcess` at `0x18004a707`
- `KERNEL32!GetCurrentProcess` at `0x18004a707`
- `KERNEL32!CloseHandle` at `0x18004a7e8`
- `KERNEL32!CloseHandle` at `0x18004a7e8`
- `ADVAPI32!OpenProcessToken` at `0x18004a719`
- `ADVAPI32!OpenProcessToken` at `0x18004a719`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18004a751`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18004a751`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18004a7a9`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18004a7a9`

## string_xrefs

- `0x18004a6e3`: `SeTakeOwnershipPrivilege`
- `0x18004a74a`: `SeTakeOwnershipPrivilege`
- `0x18004a738`: `Failed to open process token. Error: 0x%08x`
- `0x18004a770`: `Failed to lookup privilege value. Error: 0x%08x`
- `0x18004a7c8`: `Failed to adjust token privileges. Error: 0x%08x`

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
  struct _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
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
0x18004a6b8  mov     [rsp-8+arg_8], rbx
0x18004a6bd  mov     [rsp-8+arg_10], rdi
0x18004a6c2  push    rbp
0x18004a6c3  mov     rbp, rsp
0x18004a6c6  sub     rsp, 60h
0x18004a6ca  mov     rax, cs:__security_cookie
0x18004a6d1  xor     rax, rsp
0x18004a6d4  mov     [rbp+var_10], rax
0x18004a6d8  xorps   xmm0, xmm0
0x18004a6db  mov     [rbp+TokenHandle], 0
0x18004a6e3  lea     r9, Name; "SeTakeOwnershipPrivilege"
0x18004a6ea  mov     qword ptr [rbp+Luid.LowPart], 0
0x18004a6f2  lea     r8, aSettingPrivile; "Setting priviledge %s"
0x18004a6f9  xor     edx, edx
0x18004a6fb  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18004a6ff  mov     rdi, rcx
0x18004a702  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a707  call    cs:__imp_GetCurrentProcess
0x18004a70d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004a711  mov     edx, 28h ; '('; DesiredAccess
0x18004a716  mov     rcx, rax; ProcessHandle
0x18004a719  call    cs:__imp_OpenProcessToken
0x18004a71f  test    eax, eax
0x18004a721  jnz     short loc_18004A744
0x18004a723  call    cs:__imp_GetLastError
0x18004a729  mov     ebx, eax
0x18004a72b  test    eax, eax
0x18004a72d  jle     short loc_18004A738
0x18004a72f  movzx   ebx, ax
0x18004a732  or      ebx, 80070000h
0x18004a738  lea     r8, aFailedToOpenPr; "Failed to open process token. Error: 0x"...
0x18004a73f  jmp     loc_18004A7CF
0x18004a744  lea     r8, [rbp+Luid]; lpLuid
0x18004a748  xor     ecx, ecx; lpSystemName
0x18004a74a  lea     rdx, Name; "SeTakeOwnershipPrivilege"
0x18004a751  call    cs:__imp_LookupPrivilegeValueW
0x18004a757  test    eax, eax
0x18004a759  jnz     short loc_18004A779
0x18004a75b  call    cs:__imp_GetLastError
0x18004a761  mov     ebx, eax
0x18004a763  test    eax, eax
0x18004a765  jle     short loc_18004A770
0x18004a767  movzx   ebx, ax
0x18004a76a  or      ebx, 80070000h
0x18004a770  lea     r8, aFailedToLookup; "Failed to lookup privilege value. Error"...
0x18004a777  jmp     short loc_18004A7CF
0x18004a779  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18004a77d  lea     r8, [rbp+NewState]; NewState
0x18004a781  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004a785  xor     ebx, ebx
0x18004a787  mov     [rsp+60h+ReturnLength], rbx; ReturnLength
0x18004a78c  xor     edx, edx; DisableAllPrivileges
0x18004a78e  mov     [rbp+NewState.PrivilegeCount], 1
0x18004a795  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18004a799  lea     r9d, [rbx+10h]; BufferLength
0x18004a79d  mov     [rbp+NewState.Privileges.Attributes], 2
0x18004a7a4  mov     [rsp+60h+PreviousState], rbx; PreviousState
0x18004a7a9  call    cs:__imp_AdjustTokenPrivileges
0x18004a7af  test    eax, eax
0x18004a7b1  jnz     short loc_18004A7DF
0x18004a7b3  call    cs:__imp_GetLastError
0x18004a7b9  mov     ebx, eax
0x18004a7bb  test    eax, eax
0x18004a7bd  jle     short loc_18004A7C8
0x18004a7bf  movzx   ebx, ax
0x18004a7c2  or      ebx, 80070000h
0x18004a7c8  lea     r8, aFailedToAdjust; "Failed to adjust token privileges. Erro"...
0x18004a7cf  mov     r9d, ebx
0x18004a7d2  mov     edx, 2
0x18004a7d7  mov     rcx, rdi
0x18004a7da  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a7df  mov     rcx, [rbp+TokenHandle]; hObject
0x18004a7e3  test    rcx, rcx
0x18004a7e6  jz      short loc_18004A7EE
0x18004a7e8  call    cs:__imp_CloseHandle
0x18004a7ee  mov     eax, ebx
0x18004a7f0  mov     rcx, [rbp+var_10]
0x18004a7f4  xor     rcx, rsp; StackCookie
0x18004a7f7  call    __security_check_cookie
0x18004a7fc  lea     r11, [rsp+60h+var_s0]
0x18004a801  mov     rbx, [r11+18h]
0x18004a805  mov     rdi, [r11+20h]
0x18004a809  mov     rsp, r11
0x18004a80c  pop     rbp
0x18004a80d  retn
```
