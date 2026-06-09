# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x18003b8a0`
- end: `0x18003b8ec`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003b554`

## callees

- `0x18003b8a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b8c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b8c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b8b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8d0`

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
0x18003b8a0  mov     [rsp+arg_0], rbx
0x18003b8a5  push    rdi
0x18003b8a6  sub     rsp, 20h
0x18003b8aa  mov     rbx, rdx
0x18003b8ad  mov     rdi, rcx
0x18003b8b0  call    cs:__imp_GetCurrentProcess
0x18003b8b6  cmp     rdi, rax
0x18003b8b9  jz      short loc_18003B8D8
0x18003b8bb  mov     r8, rbx; TokenHandle
0x18003b8be  mov     edx, 8; DesiredAccess
0x18003b8c3  mov     rcx, rdi; ProcessHandle
0x18003b8c6  call    cs:__imp_OpenProcessToken
0x18003b8cc  test    eax, eax
0x18003b8ce  jnz     short loc_18003B8DF
0x18003b8d0  call    cs:__imp_GetLastError
0x18003b8d6  jmp     short loc_18003B8E1
0x18003b8d8  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x18003b8df  xor     eax, eax
0x18003b8e1  mov     rbx, [rsp+28h+arg_0]
0x18003b8e6  add     rsp, 20h
0x18003b8ea  pop     rdi
0x18003b8eb  retn
```
