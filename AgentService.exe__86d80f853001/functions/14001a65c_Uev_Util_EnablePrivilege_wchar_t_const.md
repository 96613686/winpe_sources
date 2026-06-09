# Uev::Util::EnablePrivilege(wchar_t const *)

- ea: `0x14001a65c`
- end: `0x14001a7bb`
- name: `?EnablePrivilege@Util@Uev@@SAJPEB_W@Z`
- size: `351`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14000b2e0`

## callees

- `0x140003e50`
- `0x14000ac88`
- `0x14000acc4`
- `0x1400191ec`
- `0x14001a65c`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14001a6b9`
- `ADVAPI32!OpenProcessToken` at `0x14001a6b9`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14001a713`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14001a713`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14001a6d4`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14001a6d4`
- `KERNEL32!GetCurrentProcess` at `0x14001a6a9`
- `KERNEL32!GetCurrentProcess` at `0x14001a6a9`
- `KERNEL32!CloseHandle` at `0x14001a766`
- `KERNEL32!CloseHandle` at `0x14001a766`
- `KERNEL32!GetLastError` at `0x14001a721`
- `KERNEL32!GetLastError` at `0x14001a73f`
- `KERNEL32!GetLastError` at `0x14001a76e`
- `KERNEL32!GetLastError` at `0x14001a721`
- `KERNEL32!GetLastError` at `0x14001a73f`
- `KERNEL32!GetLastError` at `0x14001a76e`

## string_xrefs

- `0x14001a6cd`: `SeAssignPrimaryTokenPrivilege`
- `0x14001a692`: `AgentService.Util::EnablePrivilege: Entry`
- `0x14001a736`: `AgentService.Util::EnablePrivilege: AdjustTokenPrivileges failed, error = 0x%X`
- `0x14001a754`: `AgentService.Util::EnablePrivilege: LookupPrivilegeValue failed, error = 0x%X`
- `0x14001a785`: `AgentService.Util::EnablePrivilege: Failed to open process token, error = 0x%X`
- `0x14001a793`: `AgentService.Util::EnablePrivilege: Exit, retStatus = 0x%X`

## pseudocode

```c
__int64 __fastcall Uev::Util::EnablePrivilege(const wchar_t *a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int v2; // ebx
  signed int LastError; // eax
  wchar_t *v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-40h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp-18h] BYREF

  TokenHandle = 0;
  Luid = 0;
  NewState = 0;
  ReturnLength = 16;
  PreviousState = 0;
  DbgTrace<5>(L"AgentService.Util::EnablePrivilege: Entry");
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, L"SeAssignPrimaryTokenPrivilege", &Luid) )
    {
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) )
      {
        v2 = 0;
LABEL_12:
        CloseHandle(TokenHandle);
        goto LABEL_16;
      }
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v4 = L"AgentService.Util::EnablePrivilege: AdjustTokenPrivileges failed, error = 0x%X";
    }
    else
    {
      v5 = GetLastError();
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      v4 = (wchar_t *)L"AgentService.Util::EnablePrivilege: LookupPrivilegeValue failed, error = 0x%X";
    }
    DbgTraceFrmtErr<long>(v4);
    goto LABEL_12;
  }
  v6 = GetLastError();
  v2 = v6;
  if ( v6 > 0 )
    v2 = (unsigned __int16)v6 | 0x80070000;
  DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.Util::EnablePrivilege: Failed to open process token, error = 0x%X");
LABEL_16:
  DbgTraceFrmt<5,long>((wchar_t *)L"AgentService.Util::EnablePrivilege: Exit, retStatus = 0x%X");
  return v2;
}

```

## disassembly

```asm
0x14001a65c  mov     [rsp-8+arg_0], rbx
0x14001a661  push    rbp
0x14001a662  mov     rbp, rsp
0x14001a665  sub     rsp, 70h
0x14001a669  mov     rax, cs:__security_cookie
0x14001a670  xor     rax, rsp
0x14001a673  mov     [rbp+var_8], rax
0x14001a677  xorps   xmm0, xmm0
0x14001a67a  mov     [rbp+TokenHandle], 0
0x14001a682  xorps   xmm1, xmm1
0x14001a685  mov     qword ptr [rbp+Luid.LowPart], 0
0x14001a68d  mov     ebx, 10h
0x14001a692  lea     rcx, aAgentserviceUt_17; "AgentService.Util::EnablePrivilege: Ent"...
0x14001a699  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x14001a69d  mov     [rbp+var_38], ebx
0x14001a6a0  movups  xmmword ptr [rbp+var_18.PrivilegeCount], xmm1
0x14001a6a4  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001a6a9  call    cs:__imp_GetCurrentProcess
0x14001a6af  mov     rcx, rax; ProcessHandle
0x14001a6b2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14001a6b6  lea     edx, [rbx+18h]; DesiredAccess
0x14001a6b9  call    cs:__imp_OpenProcessToken
0x14001a6bf  test    eax, eax
0x14001a6c1  jz      loc_14001A76E
0x14001a6c7  lea     r8, [rbp+Luid]; lpLuid
0x14001a6cb  xor     ecx, ecx; lpSystemName
0x14001a6cd  lea     rdx, Name; "SeAssignPrimaryTokenPrivilege"
0x14001a6d4  call    cs:__imp_LookupPrivilegeValueW
0x14001a6da  test    eax, eax
0x14001a6dc  jz      short loc_14001A73F
0x14001a6de  mov     rax, qword ptr [rbp+Luid.LowPart]
0x14001a6e2  lea     r8, [rbp+NewState]; NewState
0x14001a6e6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14001a6ea  mov     r9d, ebx; BufferLength
0x14001a6ed  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x14001a6f1  xor     edx, edx; DisableAllPrivileges
0x14001a6f3  lea     rax, [rbp+var_38]
0x14001a6f7  mov     [rbp+NewState.PrivilegeCount], 1
0x14001a6fe  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14001a703  lea     rax, [rbp+var_18]
0x14001a707  mov     [rsp+70h+PreviousState], rax; PreviousState
0x14001a70c  mov     [rbp+NewState.Privileges.Attributes], 2
0x14001a713  call    cs:__imp_AdjustTokenPrivileges
0x14001a719  test    eax, eax
0x14001a71b  jz      short loc_14001A721
0x14001a71d  xor     ebx, ebx
0x14001a71f  jmp     short loc_14001A762
0x14001a721  call    cs:__imp_GetLastError
0x14001a727  mov     ebx, eax
0x14001a729  test    eax, eax
0x14001a72b  jle     short loc_14001A736
0x14001a72d  movzx   ebx, ax
0x14001a730  or      ebx, 80070000h
0x14001a736  lea     rcx, aAgentserviceUt_27; "AgentService.Util::EnablePrivilege: Adj"...
0x14001a73d  jmp     short loc_14001A75B
0x14001a73f  call    cs:__imp_GetLastError
0x14001a745  mov     ebx, eax
0x14001a747  test    eax, eax
0x14001a749  jle     short loc_14001A754
0x14001a74b  movzx   ebx, ax
0x14001a74e  or      ebx, 80070000h
0x14001a754  lea     rcx, aAgentserviceUt_5; "AgentService.Util::EnablePrivilege: Loo"...
0x14001a75b  mov     edx, ebx
0x14001a75d  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001a762  mov     rcx, [rbp+TokenHandle]; hObject
0x14001a766  call    cs:__imp_CloseHandle
0x14001a76c  jmp     short loc_14001A791
0x14001a76e  call    cs:__imp_GetLastError
0x14001a774  mov     ebx, eax
0x14001a776  test    eax, eax
0x14001a778  jle     short loc_14001A783
0x14001a77a  movzx   ebx, ax
0x14001a77d  or      ebx, 80070000h
0x14001a783  mov     edx, ebx
0x14001a785  lea     rcx, aAgentserviceUt; "AgentService.Util::EnablePrivilege: Fai"...
0x14001a78c  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001a791  mov     edx, ebx
0x14001a793  lea     rcx, aAgentserviceUt_28; "AgentService.Util::EnablePrivilege: Exi"...
0x14001a79a  call    ??$DbgTraceFrmt@$04J@@YAXPEB_WJ@Z; DbgTraceFrmt<5,long>(wchar_t const *,long)
0x14001a79f  mov     eax, ebx
0x14001a7a1  mov     rcx, [rbp+var_8]
0x14001a7a5  xor     rcx, rsp; StackCookie
0x14001a7a8  call    __security_check_cookie
0x14001a7ad  mov     rbx, [rsp+70h+arg_0]
0x14001a7b5  add     rsp, 70h
0x14001a7b9  pop     rbp
0x14001a7ba  retn
```
