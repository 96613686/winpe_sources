# unique_adjust_token_privilege::unique_adjust_token_privilege(ushort const *)

- ea: `0x180036434`
- end: `0x180036568`
- name: `??0unique_adjust_token_privilege@@QEAA@PEBG@Z`
- size: `308`
- prototype: `unique_adjust_token_privilege *__fastcall(PHANDLE TokenHandle, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004088c`

## callees

- `0x180014d04`
- `0x180025ee4`
- `0x180036434`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003649a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003649a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036484`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180036484`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180036505`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180036505`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800364c4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800364c4`

## string_xrefs

- `0x180036529`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003653e`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180036553`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800364bb`: `SeTimeZonePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unique_adjust_token_privilege *__fastcall unique_adjust_token_privilege::unique_adjust_token_privilege(
        char *TokenHandle,
        const unsigned __int16 *a2)
{
  struct _TOKEN_PRIVILEGES *v3; // rsi
  struct _TOKEN_PRIVILEGES *PreviousState; // rbp
  DWORD *ReturnLength; // r14
  HANDLE CurrentProcess; // rax
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _LUID Luid; // [rsp+58h] [rbp+10h] BYREF

  Luid = (struct _LUID)a2;
  *(_QWORD *)TokenHandle = 0;
  v3 = (struct _TOKEN_PRIVILEGES *)(TokenHandle + 12);
  PreviousState = (struct _TOKEN_PRIVILEGES *)(TokenHandle + 28);
  ReturnLength = (DWORD *)(TokenHandle + 44);
  TokenHandle[8] = 0;
  *((_DWORD *)TokenHandle + 11) = 0;
  *(_OWORD *)(TokenHandle + 28) = 0;
  *(_OWORD *)(TokenHandle + 12) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, (PHANDLE)TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x71,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      v7);
  Luid = 0;
  if ( !LookupPrivilegeValueW(0, L"SeTimeZonePrivilege", &Luid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x75,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      v8);
  v3->PrivilegeCount = 1;
  *((struct _LUID *)TokenHandle + 2) = Luid;
  *((_DWORD *)TokenHandle + 6) = 2;
  if ( !AdjustTokenPrivileges(*(HANDLE *)TokenHandle, 0, v3, 0x10u, PreviousState, ReturnLength) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x83,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      v9);
  TokenHandle[8] = 1;
  return (unique_adjust_token_privilege *)TokenHandle;
}

```

## disassembly

```asm
0x180036434  mov     rax, rsp
0x180036437  mov     [rax+18h], rbx
0x18003643b  mov     [rax+20h], rbp
0x18003643f  mov     [rax+10h], rdx
0x180036443  mov     [rax+8], rcx
0x180036447  push    rsi
0x180036448  push    rdi
0x180036449  push    r14
0x18003644b  sub     rsp, 30h
0x18003644f  mov     rbx, rcx
0x180036452  mov     qword ptr [rcx], 0
0x180036459  lea     rsi, [rcx+0Ch]
0x18003645d  lea     rbp, [rcx+1Ch]
0x180036461  lea     r14, [rcx+2Ch]
0x180036465  mov     byte ptr [rcx+8], 0
0x180036469  mov     dword ptr [r14], 0
0x180036470  xorps   xmm0, xmm0
0x180036473  movups  xmmword ptr [rbp+0], xmm0
0x180036477  xorps   xmm1, xmm1
0x18003647a  movups  xmmword ptr [rsi], xmm1
0x18003647d  xor     edx, edx
0x18003647f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180036484  call    cs:__imp_GetCurrentProcess
0x18003648a  mov     rdi, [rsp+48h]
0x18003648f  mov     r8, rbx; TokenHandle
0x180036492  mov     edx, 28h ; '('; DesiredAccess
0x180036497  mov     rcx, rax; ProcessHandle
0x18003649a  call    cs:__imp_OpenProcessToken
0x1800364a0  test    eax, eax
0x1800364a2  jz      loc_18003653E
0x1800364a8  mov     qword ptr [rsp+48h+Luid.LowPart], 0
0x1800364b1  mov     rdi, [rsp+48h]
0x1800364b6  lea     r8, [rsp+48h+Luid]; lpLuid
0x1800364bb  lea     rdx, Name; "SeTimeZonePrivilege"
0x1800364c2  xor     ecx, ecx; lpSystemName
0x1800364c4  call    cs:__imp_LookupPrivilegeValueW
0x1800364ca  test    eax, eax
0x1800364cc  jz      loc_180036553
0x1800364d2  mov     dword ptr [rsi], 1
0x1800364d8  mov     rax, qword ptr [rsp+48h+Luid.LowPart]
0x1800364dd  mov     [rbx+10h], rax
0x1800364e1  mov     dword ptr [rbx+18h], 2
0x1800364e8  mov     rdi, [rsp+48h]
0x1800364ed  mov     [rsp+48h+ReturnLength], r14; ReturnLength
0x1800364f2  mov     [rsp+48h+PreviousState], rbp; PreviousState
0x1800364f7  mov     r9d, 10h; BufferLength
0x1800364fd  mov     r8, rsi; NewState
0x180036500  xor     edx, edx; DisableAllPrivileges
0x180036502  mov     rcx, [rbx]; TokenHandle
0x180036505  call    cs:__imp_AdjustTokenPrivileges
0x18003650b  test    eax, eax
0x18003650d  jz      short loc_180036529
0x18003650f  mov     byte ptr [rbx+8], 1
0x180036513  mov     rax, rbx
0x180036516  mov     rbx, [rsp+48h+arg_10]
0x18003651b  mov     rbp, [rsp+48h+arg_18]
0x180036520  add     rsp, 30h
0x180036524  pop     r14
0x180036526  pop     rdi
0x180036527  pop     rsi
0x180036528  retn
0x180036529  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180036530  mov     edx, 83h; void *
0x180036535  mov     rcx, rdi; this
0x180036538  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003653e  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180036545  mov     edx, 71h ; 'q'; void *
0x18003654a  mov     rcx, rdi; this
0x18003654d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180036553  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003655a  mov     edx, 75h ; 'u'; void *
0x18003655f  mov     rcx, rdi; this
0x180036562  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
