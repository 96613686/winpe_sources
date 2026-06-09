# CBridgeWindow::_GetHostId(unsigned __int64 *)

- ea: `0x18004f460`
- end: `0x18004f60b`
- name: `?_GetHostId@CBridgeWindow@@AEAAJPEA_K@Z`
- size: `427`
- prototype: `int(CBridgeWindow *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18005a5a0`
- `0x18005cd30`

## callees

- `0x18002a700`
- `0x180034768`
- `0x180034db4`
- `0x1800492e4`
- `0x18004f460`
- `0x18005cb90`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f50e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f50e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004f57e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004f57e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004f4f6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004f524`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004f4f6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004f524`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x18004f5a6`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x18004f5a6`
- `USER32!GetWindowThreadProcessId` at `0x18004f4e5`
- `USER32!GetWindowThreadProcessId` at `0x18004f4e5`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::_GetHostId(CBridgeWindow *this, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rax
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // esi
  HWND v9; // rcx
  HANDLE v10; // rsi
  const char *v11; // r9
  HANDLE v12; // rax
  unsigned int LastError; // ebx
  const char *v14; // r9
  int v15; // eax
  int TokenHostIdAsUlong64; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  DWORD dwProcessId; // [rsp+40h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+28h] BYREF
  HANDLE v21; // [rsp+50h] [rbp+30h] BYREF

  v2 = *((_QWORD *)this + 50);
  *a2 = v2;
  if ( v2 != -1 )
    return 0;
  v5 = *((_QWORD *)this + 43);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65E,
        (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
        (const char *)(unsigned int)v6,
        savedregs);
      return v7;
    }
    goto LABEL_18;
  }
  v9 = (HWND)*((_QWORD *)this + 24);
  if ( v9 )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId(v9, &dwProcessId);
    v10 = OpenProcess(0x101000u, 0, dwProcessId);
    v21 = v10;
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && GetLastError() == 5 )
    {
      v12 = OpenProcess(0x100400u, 0, dwProcessId);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v21,
        v12);
      v10 = v21;
    }
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x674,
                    (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
                    v11);
LABEL_16:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
      return LastError;
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    if ( !OpenProcessToken(v10, 8u, &TokenHandle) )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x677,
              (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
              v14);
LABEL_15:
      LastError = v15;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_16;
    }
    TokenHostIdAsUlong64 = RtlQueryTokenHostIdAsUlong64(TokenHandle, a2);
    if ( TokenHostIdAsUlong64 < 0 )
    {
      v15 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x678,
              (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
              (const char *)(unsigned int)TokenHostIdAsUlong64,
              savedregs);
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
  }
LABEL_18:
  *((_QWORD *)this + 50) = *a2;
  return 0;
}

```

## disassembly

```asm
0x18004f460  mov     [rsp-18h+arg_18], rbx
0x18004f465  push    rbp
0x18004f466  push    rsi
0x18004f467  push    rdi; int
0x18004f468  mov     rbp, rsp
0x18004f46b  sub     rsp, 20h
0x18004f46f  mov     rax, [rcx+190h]
0x18004f476  mov     rdi, rdx
0x18004f479  mov     [rdx], rax
0x18004f47c  mov     rbx, rcx
0x18004f47f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f483  jnz     loc_18004F5FC
0x18004f489  mov     rcx, [rcx+158h]
0x18004f490  test    rcx, rcx
0x18004f493  jz      short loc_18004F4CA
0x18004f495  mov     rax, [rcx]
0x18004f498  mov     rax, [rax+48h]
0x18004f49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4a1  mov     esi, eax
0x18004f4a3  test    eax, eax
0x18004f4a5  jns     loc_18004F5F2
0x18004f4ab  mov     rcx, [rbp+18h]; this
0x18004f4af  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x18004f4b6  mov     r9d, eax; char *
0x18004f4b9  mov     edx, 65Eh; void *
0x18004f4be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f4c3  mov     eax, esi
0x18004f4c5  jmp     loc_18004F5FE
0x18004f4ca  mov     rcx, [rbx+0C0h]; hWnd
0x18004f4d1  test    rcx, rcx
0x18004f4d4  jz      loc_18004F5F2
0x18004f4da  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18004f4de  mov     [rbp+dwProcessId], 0
0x18004f4e5  call    cs:__imp_GetWindowThreadProcessId
0x18004f4eb  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18004f4ef  xor     edx, edx; bInheritHandle
0x18004f4f1  mov     ecx, 101000h; dwDesiredAccess
0x18004f4f6  call    cs:__imp_OpenProcess
0x18004f4fc  mov     rsi, rax
0x18004f4ff  mov     [rbp+arg_10], rax
0x18004f503  inc     rax
0x18004f506  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004f50c  jnz     short loc_18004F53A
0x18004f50e  call    cs:__imp_GetLastError
0x18004f514  cmp     eax, 5
0x18004f517  jnz     short loc_18004F53A
0x18004f519  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18004f51d  xor     edx, edx; bInheritHandle
0x18004f51f  mov     ecx, 100400h; dwDesiredAccess
0x18004f524  call    cs:__imp_OpenProcess
0x18004f52a  mov     rdx, rax
0x18004f52d  lea     rcx, [rbp+arg_10]
0x18004f531  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004f536  mov     rsi, [rbp+arg_10]
0x18004f53a  lea     rax, [rsi+1]
0x18004f53e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004f544  jnz     short loc_18004F55F
0x18004f546  mov     rcx, [rbp+18h]; this
0x18004f54a  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x18004f551  mov     edx, 674h; void *
0x18004f556  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f55b  mov     ebx, eax
0x18004f55d  jmp     short loc_18004F5D3
0x18004f55f  xor     edx, edx
0x18004f561  mov     [rbp+TokenHandle], 0
0x18004f569  lea     rcx, [rbp+TokenHandle]
0x18004f56d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004f572  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004f576  mov     edx, 8; DesiredAccess
0x18004f57b  mov     rcx, rsi; ProcessHandle
0x18004f57e  call    cs:__imp_OpenProcessToken
0x18004f584  test    eax, eax
0x18004f586  jnz     short loc_18004F59F
0x18004f588  mov     rcx, [rbp+18h]; this
0x18004f58c  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x18004f593  mov     edx, 677h; void *
0x18004f598  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f59d  jmp     short loc_18004F5C8
0x18004f59f  mov     rcx, [rbp+TokenHandle]
0x18004f5a3  mov     rdx, rdi
0x18004f5a6  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x18004f5ac  test    eax, eax
0x18004f5ae  jns     short loc_18004F5E0
0x18004f5b0  mov     rcx, [rbp+18h]; this
0x18004f5b4  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x18004f5bb  mov     r9d, eax; char *
0x18004f5be  mov     edx, 678h; void *
0x18004f5c3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004f5c8  lea     rcx, [rbp+TokenHandle]
0x18004f5cc  mov     ebx, eax
0x18004f5ce  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f5d3  lea     rcx, [rbp+arg_10]
0x18004f5d7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f5dc  mov     eax, ebx
0x18004f5de  jmp     short loc_18004F5FE
0x18004f5e0  lea     rcx, [rbp+TokenHandle]
0x18004f5e4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f5e9  lea     rcx, [rbp+arg_10]
0x18004f5ed  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f5f2  mov     rax, [rdi]
0x18004f5f5  mov     [rbx+190h], rax
0x18004f5fc  xor     eax, eax
0x18004f5fe  mov     rbx, [rsp+20h+arg_18]
0x18004f603  add     rsp, 20h
0x18004f607  pop     rdi
0x18004f608  pop     rsi
0x18004f609  pop     rbp
0x18004f60a  retn
```
