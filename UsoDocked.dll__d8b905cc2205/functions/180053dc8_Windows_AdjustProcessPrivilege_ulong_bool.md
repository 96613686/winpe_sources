# Windows::AdjustProcessPrivilege(ulong,bool)

- ea: `0x180053dc8`
- end: `0x180053ee3`
- name: `?AdjustProcessPrivilege@Windows@@YAXK_N@Z`
- size: `283`
- prototype: `void __fastcall(unsigned int, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180051924`
- `0x180053da4`
- `0x180054050`

## callees

- `0x180007660`
- `0x1800209fc`
- `0x180023a18`
- `0x180053dc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180053e03`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180053e03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053df0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053e86`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180053e56`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180053e56`

## string_xrefs

- `0x180053eaa`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\reboot.cpp`
- `0x180053ebf`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\reboot.cpp`
- `0x180053ed1`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\reboot.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::AdjustProcessPrivilege(int a1, unsigned __int8 a2)
{
  int v2; // ebx
  LUID v3; // rdi
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  const char *v6; // r9
  int PreviousState; // [rsp+20h] [rbp-38h]
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  v3 = (LUID)a1;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\reboot.cpp",
      v5);
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = v3;
  NewState.Privileges[0].Attributes = 2 * v2;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\reboot.cpp",
      v6);
  if ( GetLastError() == 1300 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\reboot.cpp",
      (const char *)0x80070514LL,
      PreviousState);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
}

```

## disassembly

```asm
0x180053dc8  mov     [rsp+arg_0], rbx
0x180053dcd  push    rdi
0x180053dce  sub     rsp, 50h
0x180053dd2  mov     rax, cs:__security_cookie
0x180053dd9  xor     rax, rsp
0x180053ddc  mov     [rsp+58h+var_10], rax
0x180053de1  movzx   ebx, dl
0x180053de4  movsxd  rdi, ecx
0x180053de7  mov     [rsp+58h+TokenHandle], 0
0x180053df0  call    cs:__imp_GetCurrentProcess
0x180053df6  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180053dfb  mov     edx, 28h ; '('; DesiredAccess
0x180053e00  mov     rcx, rax; ProcessHandle
0x180053e03  call    cs:__imp_OpenProcessToken
0x180053e09  mov     rcx, [rsp+58h]; this
0x180053e0e  test    eax, eax
0x180053e10  jz      loc_180053EBF
0x180053e16  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x180053e1e  mov     rcx, rdi
0x180053e21  shr     rcx, 20h
0x180053e25  mov     [rsp+58h+NewState.Privileges.Luid.LowPart], edi
0x180053e29  mov     [rsp+58h+NewState.Privileges.Luid.HighPart], ecx
0x180053e2d  mov     eax, ebx
0x180053e2f  add     eax, eax
0x180053e31  mov     [rsp+58h+NewState.Privileges.Attributes], eax
0x180053e35  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x180053e3e  mov     [rsp+58h+PreviousState], 0; int
0x180053e47  xor     r9d, r9d; BufferLength
0x180053e4a  lea     r8, [rsp+58h+NewState]; NewState
0x180053e4f  xor     edx, edx; DisableAllPrivileges
0x180053e51  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180053e56  call    cs:__imp_AdjustTokenPrivileges
0x180053e5c  mov     rcx, [rsp+58h]; this
0x180053e61  test    eax, eax
0x180053e63  jz      short loc_180053ED1
0x180053e65  mov     rbx, [rsp+58h]
0x180053e6a  call    cs:__imp_GetLastError
0x180053e70  cmp     eax, 514h
0x180053e75  jz      short loc_180053EA4
0x180053e77  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180053e7c  lea     rax, [rcx-1]
0x180053e80  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180053e84  ja      short loc_180053E8C
0x180053e86  call    cs:__imp_CloseHandle
0x180053e8c  mov     rcx, [rsp+58h+var_10]
0x180053e91  xor     rcx, rsp; StackCookie
0x180053e94  call    __security_check_cookie
0x180053e99  mov     rbx, [rsp+58h+arg_0]
0x180053e9e  add     rsp, 50h
0x180053ea2  pop     rdi
0x180053ea3  retn
0x180053ea4  mov     r9d, 80070514h; char *
0x180053eaa  lea     r8, aOnecoreEnduser_27; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180053eb1  mov     edx, 4Ah ; 'J'; void *
0x180053eb6  mov     rcx, rbx; this
0x180053eb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053ebf  lea     r8, aOnecoreEnduser_27; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180053ec6  mov     edx, 3Bh ; ';'; void *
0x180053ecb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180053ed1  lea     r8, aOnecoreEnduser_27; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180053ed8  mov     edx, 48h ; 'H'; void *
0x180053edd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
