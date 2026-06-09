# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x18002d5a8`
- end: `0x18002d5f4`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002d41c`

## callees

- `0x18002d5a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d5b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002d5b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d5ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002d5ce`

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
0x18002d5a8  mov     [rsp+arg_0], rbx
0x18002d5ad  push    rdi
0x18002d5ae  sub     rsp, 20h
0x18002d5b2  mov     rbx, rdx
0x18002d5b5  mov     rdi, rcx
0x18002d5b8  call    cs:__imp_GetCurrentProcess
0x18002d5be  cmp     rdi, rax
0x18002d5c1  jz      short loc_18002D5E0
0x18002d5c3  mov     r8, rbx; TokenHandle
0x18002d5c6  mov     edx, 8; DesiredAccess
0x18002d5cb  mov     rcx, rdi; ProcessHandle
0x18002d5ce  call    cs:__imp_OpenProcessToken
0x18002d5d4  test    eax, eax
0x18002d5d6  jnz     short loc_18002D5E7
0x18002d5d8  call    cs:__imp_GetLastError
0x18002d5de  jmp     short loc_18002D5E9
0x18002d5e0  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x18002d5e7  xor     eax, eax
0x18002d5e9  mov     rbx, [rsp+28h+arg_0]
0x18002d5ee  add     rsp, 20h
0x18002d5f2  pop     rdi
0x18002d5f3  retn
```
