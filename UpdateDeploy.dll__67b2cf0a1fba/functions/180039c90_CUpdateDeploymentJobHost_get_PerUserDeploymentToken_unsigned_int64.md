# CUpdateDeploymentJobHost::get_PerUserDeploymentToken(unsigned __int64 *)

- ea: `0x180039c90`
- end: `0x180039e35`
- name: `?get_PerUserDeploymentToken@CUpdateDeploymentJobHost@@UEAAJPEA_K@Z`
- size: `421`
- prototype: `__int64 __fastcall(CUpdateDeploymentJobHost *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180002214`
- `0x180003180`
- `0x1800098fc`
- `0x180039c90`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180039d55`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180039d55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039d49`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180039da9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180039da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039d6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039d77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039e0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039d6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039d77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039e0b`

## string_xrefs

- `0x180039cc3`: `C:\__w\1\s\src\Client\UpdateDeployment\JobHost\DeploymentJobHost.cpp`
- `0x180039d2e`: `C:\__w\1\s\src\Client\UpdateDeployment\JobHost\DeploymentJobHost.cpp`
- `0x180039db7`: `C:\__w\1\s\src\Client\UpdateDeployment\JobHost\DeploymentJobHost.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJobHost::get_PerUserDeploymentToken(
        CUpdateDeploymentJobHost *this,
        unsigned __int64 *a2)
{
  HANDLE v5; // rbx
  int CallerProcessHandle; // esi
  __int64 v7; // rdx
  HANDLE v8; // r14
  DWORD CurrentProcessId; // esi
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  HANDLE v12; // rcx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-40h]
  HANDLE Process; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hSourceHandle; // [rsp+48h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\JobHost\\DeploymentJobHost.cpp",
      (const char *)0x80004003LL,
      dwDesiredAccess);
    return 2147500035LL;
  }
  v5 = 0;
  Process = 0;
  hSourceHandle = 0;
  hObject = 0;
  CallerProcessHandle = GetCallerProcessHandle((__int64)this, &Process);
  if ( CallerProcessHandle >= 0 )
  {
    CallerProcessHandle = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**((_QWORD **)this + 8) + 48LL))(
                            *((_QWORD *)this + 8),
                            &hSourceHandle);
    if ( CallerProcessHandle >= 0 )
    {
      v8 = hSourceHandle;
      v5 = hSourceHandle;
      CurrentProcessId = GetCurrentProcessId();
      if ( GetProcessId(Process) == CurrentProcessId )
      {
        v5 = 0;
        if ( hObject )
          CloseHandle(hObject);
      }
      else
      {
        if ( hObject )
          CloseHandle(hObject);
        CurrentProcess = GetCurrentProcess();
        if ( !DuplicateHandle(CurrentProcess, v5, Process, &hObject, 0, 0, 2u) )
        {
          CallerProcessHandle = wil::details::in1diag3::Return_GetLastError(
                                  retaddr,
                                  (void *)0x104,
                                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\JobHost\\DeploymentJobHost.cpp",
                                  v11);
          goto LABEL_15;
        }
        v8 = hObject;
      }
      v12 = 0;
      *a2 = (unsigned __int64)v8;
      hObject = 0;
      CallerProcessHandle = 0;
      goto LABEL_18;
    }
    v7 = 245;
  }
  else
  {
    v7 = 243;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\JobHost\\DeploymentJobHost.cpp",
    (const char *)(unsigned int)CallerProcessHandle,
    dwDesiredAccess);
LABEL_15:
  v12 = hObject;
LABEL_18:
  if ( v12 )
  {
    CloseHandle(v12);
    hObject = 0;
  }
  if ( v5 )
    CloseHandle(v5);
  if ( Process )
    CloseHandle(Process);
  return (unsigned int)CallerProcessHandle;
}

```

## disassembly

```asm
0x180039c90  mov     [rsp-18h+arg_10], rbx
0x180039c95  mov     [rsp-18h+arg_18], rsi
0x180039c9a  push    rbp
0x180039c9b  push    r14
0x180039c9d  push    r15
0x180039c9f  mov     rbp, rsp
0x180039ca2  sub     rsp, 60h
0x180039ca6  mov     rax, cs:__security_cookie
0x180039cad  xor     rax, rsp
0x180039cb0  mov     [rbp+var_8], rax
0x180039cb4  mov     r15, rdx
0x180039cb7  mov     r14, rcx
0x180039cba  test    rdx, rdx
0x180039cbd  jnz     short loc_180039CE3
0x180039cbf  mov     rcx, [rbp+18h]; this
0x180039cc3  lea     r8, aCW1SSrcClientU_1; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180039cca  mov     ebx, 80004003h
0x180039ccf  mov     edx, 0EAh; void *
0x180039cd4  mov     r9d, ebx; char *
0x180039cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039cdc  mov     eax, ebx
0x180039cde  jmp     loc_180039E13
0x180039ce3  xor     ebx, ebx
0x180039ce5  mov     [rbp+Process], 0
0x180039ced  lea     rdx, [rbp+Process]
0x180039cf1  mov     [rbp+hSourceHandle], rbx
0x180039cf5  mov     [rbp+hObject], rbx
0x180039cf9  call    GetCallerProcessHandle
0x180039cfe  mov     esi, eax
0x180039d00  test    eax, eax
0x180039d02  jns     short loc_180039D0B
0x180039d04  mov     edx, 0F3h
0x180039d09  jmp     short loc_180039D2A
0x180039d0b  mov     rcx, [r14+40h]
0x180039d0f  lea     rdx, [rbp+hSourceHandle]
0x180039d13  mov     rax, [rcx]
0x180039d16  mov     rax, [rax+30h]
0x180039d1a  call    _guard_dispatch_icall
0x180039d1f  mov     esi, eax
0x180039d21  test    eax, eax
0x180039d23  jns     short loc_180039D42
0x180039d25  mov     edx, 0F5h; void *
0x180039d2a  mov     rcx, [rbp+18h]; this
0x180039d2e  lea     r8, aCW1SSrcClientU_1; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180039d35  mov     r9d, esi; char *
0x180039d38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d3d  jmp     loc_180039DCA
0x180039d42  mov     r14, [rbp+hSourceHandle]
0x180039d46  mov     rbx, r14
0x180039d49  call    cs:__imp_GetCurrentProcessId
0x180039d4f  mov     rcx, [rbp+Process]; Process
0x180039d53  mov     esi, eax
0x180039d55  call    cs:__imp_GetProcessId
0x180039d5b  mov     rcx, [rbp+hObject]; hObject
0x180039d5f  cmp     eax, esi
0x180039d61  jnz     short loc_180039D72
0x180039d63  xor     ebx, ebx
0x180039d65  test    rcx, rcx
0x180039d68  jz      short loc_180039DD4
0x180039d6a  call    cs:__imp_CloseHandle
0x180039d70  jmp     short loc_180039DD4
0x180039d72  test    rcx, rcx
0x180039d75  jz      short loc_180039D7D
0x180039d77  call    cs:__imp_CloseHandle
0x180039d7d  call    cs:__imp_GetCurrentProcess
0x180039d83  mov     r8, [rbp+Process]; hTargetProcessHandle
0x180039d87  lea     r9, [rbp+hObject]; lpTargetHandle
0x180039d8b  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180039d93  mov     rcx, rax; hSourceProcessHandle
0x180039d96  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x180039d9e  mov     rdx, rbx; hSourceHandle
0x180039da1  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x180039da9  call    cs:__imp_DuplicateHandle
0x180039daf  test    eax, eax
0x180039db1  jnz     short loc_180039DD0
0x180039db3  mov     rcx, [rbp+18h]; this
0x180039db7  lea     r8, aCW1SSrcClientU_1; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180039dbe  mov     edx, 104h; void *
0x180039dc3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039dc8  mov     esi, eax
0x180039dca  mov     rcx, [rbp+hObject]
0x180039dce  jmp     short loc_180039DDF
0x180039dd0  mov     r14, [rbp+hObject]
0x180039dd4  xor     ecx, ecx; hObject
0x180039dd6  mov     [r15], r14
0x180039dd9  mov     [rbp+hObject], rcx
0x180039ddd  xor     esi, esi
0x180039ddf  test    rcx, rcx
0x180039de2  jz      short loc_180039DF2
0x180039de4  call    cs:__imp_CloseHandle
0x180039dea  mov     [rbp+hObject], 0
0x180039df2  test    rbx, rbx
0x180039df5  jz      short loc_180039E00
0x180039df7  mov     rcx, rbx; hObject
0x180039dfa  call    cs:__imp_CloseHandle
0x180039e00  cmp     [rbp+Process], 0
0x180039e05  jz      short loc_180039E11
0x180039e07  mov     rcx, [rbp+Process]; hObject
0x180039e0b  call    cs:__imp_CloseHandle
0x180039e11  mov     eax, esi
0x180039e13  mov     rcx, [rbp+var_8]
0x180039e17  xor     rcx, rsp; StackCookie
0x180039e1a  call    __security_check_cookie
0x180039e1f  lea     r11, [rsp+60h+var_s0]
0x180039e24  mov     rbx, [r11+30h]
0x180039e28  mov     rsi, [r11+38h]
0x180039e2c  mov     rsp, r11
0x180039e2f  pop     r15
0x180039e31  pop     r14
0x180039e33  pop     rbp
0x180039e34  retn
```
