# VaultEnableSinglePrivilege(long)

- ea: `0x180001970`
- end: `0x180001a47`
- name: `?VaultEnableSinglePrivilege@@YAKJ@Z`
- size: `215`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800021e8`

## callees

- `0x180001970`
- `0x180003140`
- `0x18003a580`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180001a06`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180001a06`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800019b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800019b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800019a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800019a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000198b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VaultEnableSinglePrivilege()
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  BOOL (__stdcall *v3)(HANDLE); // [rsp+30h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  int v5; // [rsp+40h] [rbp-20h]
  _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  v3 = CloseHandle;
  TokenHandle = 0;
  v5 = 0;
  NewState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && (NewState.Privileges[0].Luid = (LUID)7LL,
        NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Attributes = 2,
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0)) )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v3);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v3);
    return LastError;
  }
}

```

## disassembly

```asm
0x180001970  mov     [rsp-8+arg_0], rbx
0x180001975  push    rbp
0x180001976  mov     rbp, rsp
0x180001979  sub     rsp, 60h
0x18000197d  mov     rax, cs:__security_cookie
0x180001984  xor     rax, rsp
0x180001987  mov     [rbp+var_8], rax
0x18000198b  mov     rax, cs:__imp_CloseHandle
0x180001992  mov     [rbp+var_30], rax
0x180001996  xor     ebx, ebx
0x180001998  mov     [rbp+TokenHandle], rbx
0x18000199c  mov     [rbp+var_20], ebx
0x18000199f  xorps   xmm0, xmm0
0x1800019a2  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800019a6  call    cs:__imp_GetCurrentProcess
0x1800019ac  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800019b0  lea     edx, [rbx+28h]; DesiredAccess
0x1800019b3  mov     rcx, rax; ProcessHandle
0x1800019b6  call    cs:__imp_OpenProcessToken
0x1800019bc  test    eax, eax
0x1800019be  jnz     short loc_1800019D6
0x1800019c0  call    cs:__imp_GetLastError
0x1800019c6  mov     ebx, eax
0x1800019c8  lea     rcx, [rbp+var_30]
0x1800019cc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800019d1  nop
0x1800019d2  mov     eax, ebx
0x1800019d4  jmp     short loc_180001A30
0x1800019d6  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 7
0x1800019de  mov     [rbp+NewState.PrivilegeCount], 1
0x1800019e5  mov     [rbp+NewState.Privileges.Attributes], 2
0x1800019ec  mov     [rsp+60h+ReturnLength], rbx; ReturnLength
0x1800019f1  mov     [rsp+60h+PreviousState], rbx; PreviousState
0x1800019f6  mov     r9d, 10h; BufferLength
0x1800019fc  lea     r8, [rbp+NewState]; NewState
0x180001a00  xor     edx, edx; DisableAllPrivileges
0x180001a02  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180001a06  call    cs:__imp_AdjustTokenPrivileges
0x180001a0c  test    eax, eax
0x180001a0e  jnz     short loc_180001A24
0x180001a10  call    cs:__imp_GetLastError
0x180001a16  mov     ebx, eax
0x180001a18  lea     rcx, [rbp+var_30]
0x180001a1c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180001a21  nop
0x180001a22  jmp     short loc_1800019D2
0x180001a24  lea     rcx, [rbp+var_30]
0x180001a28  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180001a2d  nop
0x180001a2e  xor     eax, eax
0x180001a30  mov     rcx, [rbp+var_8]
0x180001a34  xor     rcx, rsp; StackCookie
0x180001a37  call    __security_check_cookie
0x180001a3c  mov     rbx, [rsp+60h+arg_0]
0x180001a41  add     rsp, 60h
0x180001a45  pop     rbp
0x180001a46  retn
```
