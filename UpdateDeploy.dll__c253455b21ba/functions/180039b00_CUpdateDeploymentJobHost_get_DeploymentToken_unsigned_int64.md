# CUpdateDeploymentJobHost::get_DeploymentToken(unsigned __int64 *)

- ea: `0x180039b00`
- end: `0x180039c7c`
- name: `?get_DeploymentToken@CUpdateDeploymentJobHost@@UEAAJPEA_K@Z`
- size: `380`
- prototype: `__int64 __fastcall(CUpdateDeploymentJobHost *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180002214`
- `0x180003180`
- `0x1800098fc`
- `0x180039b00`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180039b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180039b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039bc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039bc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039b90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039b90`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180039bf0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180039bf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c52`

## string_xrefs

- `0x180039b75`: `C:\__w\1\s\src\Client\UpdateDeployment\JobHost\DeploymentJobHost.cpp`
- `0x180039bfe`: `C:\__w\1\s\src\Client\UpdateDeployment\JobHost\DeploymentJobHost.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJobHost::get_DeploymentToken(CUpdateDeploymentJobHost *this, unsigned __int64 *a2)
{
  HANDLE v3; // rbx
  int CallerProcessHandle; // esi
  __int64 v6; // rdx
  HANDLE v7; // r14
  DWORD CurrentProcessId; // esi
  HANDLE CurrentProcess; // rax
  const char *v10; // r9
  HANDLE v11; // rcx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-40h]
  HANDLE Process; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hSourceHandle; // [rsp+48h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  Process = 0;
  v3 = 0;
  hSourceHandle = 0;
  hObject = 0;
  CallerProcessHandle = GetCallerProcessHandle((__int64)this, &Process);
  if ( CallerProcessHandle < 0 )
  {
    v6 = 207;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\JobHost\\DeploymentJobHost.cpp",
      (const char *)(unsigned int)CallerProcessHandle,
      dwDesiredAccess);
LABEL_13:
    v11 = hObject;
    goto LABEL_16;
  }
  CallerProcessHandle = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**((_QWORD **)this + 8) + 40LL))(
                          *((_QWORD *)this + 8),
                          &hSourceHandle);
  if ( CallerProcessHandle < 0 )
  {
    v6 = 209;
    goto LABEL_5;
  }
  v7 = hSourceHandle;
  v3 = hSourceHandle;
  CurrentProcessId = GetCurrentProcessId();
  if ( GetProcessId(Process) == CurrentProcessId )
  {
    v3 = 0;
    if ( hObject )
      CloseHandle(hObject);
  }
  else
  {
    if ( hObject )
      CloseHandle(hObject);
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(CurrentProcess, v3, Process, &hObject, 0, 0, 2u) )
    {
      CallerProcessHandle = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0xE0,
                              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\JobHost\\DeploymentJobHost.cpp",
                              v10);
      goto LABEL_13;
    }
    v7 = hObject;
  }
  v11 = 0;
  *a2 = (unsigned __int64)v7;
  hObject = 0;
  CallerProcessHandle = 0;
LABEL_16:
  if ( v11 )
  {
    CloseHandle(v11);
    hObject = 0;
  }
  if ( v3 )
    CloseHandle(v3);
  if ( Process )
    CloseHandle(Process);
  return (unsigned int)CallerProcessHandle;
}

```

## disassembly

```asm
0x180039b00  mov     [rsp-18h+arg_10], rbx
0x180039b05  mov     [rsp-18h+arg_18], rsi
0x180039b0a  push    rbp
0x180039b0b  push    r14
0x180039b0d  push    r15
0x180039b0f  mov     rbp, rsp
0x180039b12  sub     rsp, 60h
0x180039b16  mov     rax, cs:__security_cookie
0x180039b1d  xor     rax, rsp
0x180039b20  mov     [rbp+var_8], rax
0x180039b24  mov     r15, rdx
0x180039b27  mov     [rbp+Process], 0
0x180039b2f  xor     ebx, ebx
0x180039b31  lea     rdx, [rbp+Process]
0x180039b35  mov     [rbp+hSourceHandle], rbx
0x180039b39  mov     r14, rcx
0x180039b3c  mov     [rbp+hObject], rbx
0x180039b40  call    GetCallerProcessHandle
0x180039b45  mov     esi, eax
0x180039b47  test    eax, eax
0x180039b49  jns     short loc_180039B52
0x180039b4b  mov     edx, 0CFh
0x180039b50  jmp     short loc_180039B71
0x180039b52  mov     rcx, [r14+40h]
0x180039b56  lea     rdx, [rbp+hSourceHandle]
0x180039b5a  mov     rax, [rcx]
0x180039b5d  mov     rax, [rax+28h]
0x180039b61  call    _guard_dispatch_icall
0x180039b66  mov     esi, eax
0x180039b68  test    eax, eax
0x180039b6a  jns     short loc_180039B89
0x180039b6c  mov     edx, 0D1h; void *
0x180039b71  mov     rcx, [rbp+18h]; this
0x180039b75  lea     r8, aCW1SSrcClientU_1; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180039b7c  mov     r9d, esi; char *
0x180039b7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b84  jmp     loc_180039C11
0x180039b89  mov     r14, [rbp+hSourceHandle]
0x180039b8d  mov     rbx, r14
0x180039b90  call    cs:__imp_GetCurrentProcessId
0x180039b96  mov     rcx, [rbp+Process]; Process
0x180039b9a  mov     esi, eax
0x180039b9c  call    cs:__imp_GetProcessId
0x180039ba2  mov     rcx, [rbp+hObject]; hObject
0x180039ba6  cmp     eax, esi
0x180039ba8  jnz     short loc_180039BB9
0x180039baa  xor     ebx, ebx
0x180039bac  test    rcx, rcx
0x180039baf  jz      short loc_180039C1B
0x180039bb1  call    cs:__imp_CloseHandle
0x180039bb7  jmp     short loc_180039C1B
0x180039bb9  test    rcx, rcx
0x180039bbc  jz      short loc_180039BC4
0x180039bbe  call    cs:__imp_CloseHandle
0x180039bc4  call    cs:__imp_GetCurrentProcess
0x180039bca  mov     r8, [rbp+Process]; hTargetProcessHandle
0x180039bce  lea     r9, [rbp+hObject]; lpTargetHandle
0x180039bd2  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180039bda  mov     rcx, rax; hSourceProcessHandle
0x180039bdd  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x180039be5  mov     rdx, rbx; hSourceHandle
0x180039be8  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x180039bf0  call    cs:__imp_DuplicateHandle
0x180039bf6  test    eax, eax
0x180039bf8  jnz     short loc_180039C17
0x180039bfa  mov     rcx, [rbp+18h]; this
0x180039bfe  lea     r8, aCW1SSrcClientU_1; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180039c05  mov     edx, 0E0h; void *
0x180039c0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039c0f  mov     esi, eax
0x180039c11  mov     rcx, [rbp+hObject]
0x180039c15  jmp     short loc_180039C26
0x180039c17  mov     r14, [rbp+hObject]
0x180039c1b  xor     ecx, ecx; hObject
0x180039c1d  mov     [r15], r14
0x180039c20  mov     [rbp+hObject], rcx
0x180039c24  xor     esi, esi
0x180039c26  test    rcx, rcx
0x180039c29  jz      short loc_180039C39
0x180039c2b  call    cs:__imp_CloseHandle
0x180039c31  mov     [rbp+hObject], 0
0x180039c39  test    rbx, rbx
0x180039c3c  jz      short loc_180039C47
0x180039c3e  mov     rcx, rbx; hObject
0x180039c41  call    cs:__imp_CloseHandle
0x180039c47  cmp     [rbp+Process], 0
0x180039c4c  jz      short loc_180039C58
0x180039c4e  mov     rcx, [rbp+Process]; hObject
0x180039c52  call    cs:__imp_CloseHandle
0x180039c58  mov     eax, esi
0x180039c5a  mov     rcx, [rbp+var_8]
0x180039c5e  xor     rcx, rsp; StackCookie
0x180039c61  call    __security_check_cookie
0x180039c66  lea     r11, [rsp+60h+var_s0]
0x180039c6b  mov     rbx, [r11+30h]
0x180039c6f  mov     rsi, [r11+38h]
0x180039c73  mov     rsp, r11
0x180039c76  pop     r15
0x180039c78  pop     r14
0x180039c7a  pop     rbp
0x180039c7b  retn
```
