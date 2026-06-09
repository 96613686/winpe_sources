# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180043a94`
- end: `0x180043ae0`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180043788`

## callees

- `0x180043a94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043ac4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180043aba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180043aba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043aa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180043aa4`

## pseudocode

```c
DWORD __fastcall ARI::ProcessToken::SysAppId::OpenTokenForProcess(HANDLE ProcessHandle, PHANDLE TokenHandle, void **a3)
{
  if ( ProcessHandle == GetCurrentProcess() )
  {
    *TokenHandle = (void *)-4LL;
  }
  else if ( !OpenProcessToken(ProcessHandle, 8u, TokenHandle) )
  {
    return GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x180043a94  mov     [rsp+arg_0], rbx
0x180043a99  push    rdi
0x180043a9a  sub     rsp, 20h
0x180043a9e  mov     rbx, rdx
0x180043aa1  mov     rdi, rcx
0x180043aa4  call    cs:__imp_GetCurrentProcess
0x180043aaa  cmp     rdi, rax
0x180043aad  jz      short loc_180043ACC
0x180043aaf  mov     r8, rbx; TokenHandle
0x180043ab2  mov     edx, 8; DesiredAccess
0x180043ab7  mov     rcx, rdi; ProcessHandle
0x180043aba  call    cs:__imp_OpenProcessToken
0x180043ac0  test    eax, eax
0x180043ac2  jnz     short loc_180043AD3
0x180043ac4  call    cs:__imp_GetLastError
0x180043aca  jmp     short loc_180043AD5
0x180043acc  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x180043ad3  xor     eax, eax
0x180043ad5  mov     rbx, [rsp+28h+arg_0]
0x180043ada  add     rsp, 20h
0x180043ade  pop     rdi
0x180043adf  retn
```
