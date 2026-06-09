# Windows::AdjustProcessPrivilege(wchar_t const *,bool)

- ea: `0x1402421f0`
- end: `0x140242313`
- name: `?AdjustProcessPrivilege@Windows@@YAXPEB_W_N@Z`
- size: `291`
- prototype: `void __fastcall(LPCWSTR lpName, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140242320`
- `0x140242774`

## callees

- `0x14003c578`
- `0x1402421f0`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140242230`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140242230`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14024221d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14024221d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402422b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402422b7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140242299`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140242299`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x140242262`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x140242262`

## string_xrefs

- `0x1402422da`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x1402422ec`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x1402422fe`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::AdjustProcessPrivilege(LPCWSTR lpName, unsigned __int8 a2)
{
  int v2; // esi
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x61,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v5);
  *(_OWORD *)&Luid[0].LowPart = 0;
  Luid[0].LowPart = 1;
  if ( !LookupPrivilegeValueW(0, lpName, (PLUID)&Luid[0].HighPart) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x65,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v6);
  Luid[1].HighPart = 2 * v2;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x6E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v7);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
}

```

## disassembly

```asm
0x1402421f0  mov     [rsp+arg_8], rbx
0x1402421f5  mov     [rsp+arg_10], rsi
0x1402421fa  push    rdi
0x1402421fb  sub     rsp, 50h
0x1402421ff  mov     rax, cs:__security_cookie
0x140242206  xor     rax, rsp
0x140242209  mov     [rsp+58h+var_10], rax
0x14024220e  movzx   esi, dl
0x140242211  mov     rdi, rcx
0x140242214  mov     [rsp+58h+TokenHandle], 0
0x14024221d  call    cs:__imp_GetCurrentProcess
0x140242223  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x140242228  mov     edx, 28h ; '('; DesiredAccess
0x14024222d  mov     rcx, rax; ProcessHandle
0x140242230  call    cs:__imp_OpenProcessToken
0x140242236  mov     rcx, [rsp+58h]; this
0x14024223b  test    eax, eax
0x14024223d  jz      loc_1402422EC
0x140242243  xorps   xmm0, xmm0
0x140242246  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x14024224b  mov     [rsp+58h+Luid.LowPart], 1
0x140242253  mov     rbx, [rsp+58h]
0x140242258  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x14024225d  mov     rdx, rdi; lpName
0x140242260  xor     ecx, ecx; lpSystemName
0x140242262  call    cs:__imp_LookupPrivilegeValueW
0x140242268  test    eax, eax
0x14024226a  jz      loc_1402422FE
0x140242270  mov     eax, esi
0x140242272  add     eax, eax
0x140242274  mov     [rsp+58h+Luid.HighPart+8], eax
0x140242278  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x140242281  mov     [rsp+58h+PreviousState], 0; PreviousState
0x14024228a  xor     r9d, r9d; BufferLength
0x14024228d  lea     r8, [rsp+58h+Luid]; NewState
0x140242292  xor     edx, edx; DisableAllPrivileges
0x140242294  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x140242299  call    cs:__imp_AdjustTokenPrivileges
0x14024229f  mov     rcx, [rsp+58h]; this
0x1402422a4  test    eax, eax
0x1402422a6  jz      short loc_1402422DA
0x1402422a8  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1402422ad  lea     rax, [rcx-1]
0x1402422b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402422b5  ja      short loc_1402422BD
0x1402422b7  call    cs:__imp_CloseHandle
0x1402422bd  mov     rcx, [rsp+58h+var_10]
0x1402422c2  xor     rcx, rsp; StackCookie
0x1402422c5  call    __security_check_cookie
0x1402422ca  mov     rbx, [rsp+58h+arg_8]
0x1402422cf  mov     rsi, [rsp+58h+arg_10]
0x1402422d4  add     rsp, 50h
0x1402422d8  pop     rdi
0x1402422d9  retn
0x1402422da  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402422e1  mov     edx, 6Eh ; 'n'; void *
0x1402422e6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1402422ec  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402422f3  mov     edx, 61h ; 'a'; void *
0x1402422f8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1402422fe  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140242305  mov     edx, 65h ; 'e'; void *
0x14024230a  mov     rcx, rbx; this
0x14024230d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
