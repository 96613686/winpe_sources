# CSessionConfig::EnablePrivilege(ushort const *)

- ea: `0x18002cd18`
- end: `0x18002ce74`
- name: `?EnablePrivilege@CSessionConfig@@AEAAJPEBG@Z`
- size: `348`
- prototype: `__int64 __fastcall(CSessionConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002cff0`

## callees

- `0x180003f30`
- `0x18001a280`
- `0x18002cd18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cdcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cdcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002cd40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002cd40`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cd51`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cd51`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002cdf3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002cdf3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002cd8f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002cd8f`

## string_xrefs

- `0x18002cd75`: `OpenThreadToken failed: 0x%x in %s`
- `0x18002cd88`: `SeShutdownPrivilege`
- `0x18002ce3b`: `CSessionConfig::EnablePrivilege`
- `0x18002cdae`: `LookupPrivilegeValue failed: 0x%x in %s`
- `0x18002ce34`: `AdjustTokenPrivileges failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSessionConfig::EnablePrivilege(CSessionConfig *this, const unsigned __int16 *a2)
{
  signed int v2; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  v2 = 0;
  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    goto LABEL_9;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_9:
    if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
      goto LABEL_11;
    v5 = GetLastError();
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_11:
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      SetLastError(0);
      if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
      {
        v6 = GetLastError();
        v2 = v6;
        if ( v6 > 0 )
          v2 = (unsigned __int16)v6 | 0x80070000;
        if ( v2 < 0 )
          goto LABEL_19;
      }
      if ( GetLastError() == 1300 )
      {
        v7 = GetLastError();
        v2 = v7;
        if ( v7 > 0 )
          v2 = (unsigned __int16)v7 | 0x80070000;
        if ( v2 < 0 )
LABEL_19:
          _DbgPrintMessage(
            8,
            "AdjustTokenPrivileges failed: 0x%x in %s",
            (unsigned int)v2,
            "CSessionConfig::EnablePrivilege");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "LookupPrivilegeValue failed: 0x%x in %s",
        (unsigned int)v2,
        "CSessionConfig::EnablePrivilege");
    }
  }
  else
  {
    _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", (unsigned int)v2, "CSessionConfig::EnablePrivilege");
  }
  CloseHandle(TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002cd18  mov     [rsp+arg_0], rbx
0x18002cd1d  push    rsi
0x18002cd1e  sub     rsp, 50h
0x18002cd22  mov     rax, cs:__security_cookie
0x18002cd29  xor     rax, rsp
0x18002cd2c  mov     [rsp+58h+var_10], rax
0x18002cd31  xorps   xmm0, xmm0
0x18002cd34  xor     ebx, ebx
0x18002cd36  mov     [rsp+58h+TokenHandle], rbx
0x18002cd3b  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18002cd40  call    cs:__imp_GetCurrentProcess
0x18002cd46  mov     rcx, rax; ProcessHandle
0x18002cd49  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18002cd4e  lea     edx, [rbx+28h]; DesiredAccess
0x18002cd51  call    cs:__imp_OpenProcessToken
0x18002cd57  mov     esi, 80070000h
0x18002cd5c  test    eax, eax
0x18002cd5e  jnz     short loc_18002CD81
0x18002cd60  call    cs:__imp_GetLastError
0x18002cd66  mov     ebx, eax
0x18002cd68  test    eax, eax
0x18002cd6a  jle     short loc_18002CD71
0x18002cd6c  movzx   ebx, ax
0x18002cd6f  or      ebx, esi
0x18002cd71  test    ebx, ebx
0x18002cd73  jns     short loc_18002CD81
0x18002cd75  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18002cd7c  jmp     loc_18002CE3B
0x18002cd81  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18002cd86  xor     ecx, ecx; lpSystemName
0x18002cd88  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18002cd8f  call    cs:__imp_LookupPrivilegeValueW
0x18002cd95  test    eax, eax
0x18002cd97  jnz     short loc_18002CDBA
0x18002cd99  call    cs:__imp_GetLastError
0x18002cd9f  mov     ebx, eax
0x18002cda1  test    eax, eax
0x18002cda3  jle     short loc_18002CDAA
0x18002cda5  movzx   ebx, ax
0x18002cda8  or      ebx, esi
0x18002cdaa  test    ebx, ebx
0x18002cdac  jns     short loc_18002CDBA
0x18002cdae  lea     rdx, aLookupprivileg_0; "LookupPrivilegeValue failed: 0x%x in %s"
0x18002cdb5  jmp     loc_18002CE3B
0x18002cdba  xor     ecx, ecx; dwErrCode
0x18002cdbc  mov     [rsp+58h+Luid.LowPart], 1
0x18002cdc4  mov     [rsp+58h+Luid.HighPart+8], 2
0x18002cdcc  call    cs:__imp_SetLastError
0x18002cdd2  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18002cdd7  lea     r8, [rsp+58h+Luid]; NewState
0x18002cddc  xor     r9d, r9d; BufferLength
0x18002cddf  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18002cde8  xor     edx, edx; DisableAllPrivileges
0x18002cdea  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18002cdf3  call    cs:__imp_AdjustTokenPrivileges
0x18002cdf9  test    eax, eax
0x18002cdfb  jnz     short loc_18002CE12
0x18002cdfd  call    cs:__imp_GetLastError
0x18002ce03  mov     ebx, eax
0x18002ce05  test    eax, eax
0x18002ce07  jle     short loc_18002CE0E
0x18002ce09  movzx   ebx, ax
0x18002ce0c  or      ebx, esi
0x18002ce0e  test    ebx, ebx
0x18002ce10  js      short loc_18002CE34
0x18002ce12  call    cs:__imp_GetLastError
0x18002ce18  cmp     eax, 514h
0x18002ce1d  jnz     short loc_18002CE4F
0x18002ce1f  call    cs:__imp_GetLastError
0x18002ce25  mov     ebx, eax
0x18002ce27  test    eax, eax
0x18002ce29  jle     short loc_18002CE30
0x18002ce2b  movzx   ebx, ax
0x18002ce2e  or      ebx, esi
0x18002ce30  test    ebx, ebx
0x18002ce32  jns     short loc_18002CE4F
0x18002ce34  lea     rdx, aAdjusttokenpri_0; "AdjustTokenPrivileges failed: 0x%x in %"...
0x18002ce3b  lea     r9, aCsessionconfig; "CSessionConfig::EnablePrivilege"
0x18002ce42  mov     r8d, ebx
0x18002ce45  mov     ecx, 8; int
0x18002ce4a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ce4f  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18002ce54  call    cs:__imp_CloseHandle
0x18002ce5a  mov     eax, ebx
0x18002ce5c  mov     rcx, [rsp+58h+var_10]
0x18002ce61  xor     rcx, rsp; StackCookie
0x18002ce64  call    __security_check_cookie
0x18002ce69  mov     rbx, [rsp+58h+arg_0]
0x18002ce6e  add     rsp, 50h
0x18002ce72  pop     rsi
0x18002ce73  retn
```
