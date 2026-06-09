# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x14001d6c0`
- end: `0x14001d70c`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001d320`
- `0x14001d4b0`
- `0x14001dd70`

## callees

- `0x14001d6c0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14001d6e6`
- `ADVAPI32!OpenProcessToken` at `0x14001d6e6`
- `KERNEL32!GetLastError` at `0x14001d6f0`
- `KERNEL32!GetLastError` at `0x14001d6f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001d6d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001d6d0`

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
0x14001d6c0  mov     [rsp+arg_0], rbx
0x14001d6c5  push    rdi
0x14001d6c6  sub     rsp, 20h
0x14001d6ca  mov     rbx, rdx
0x14001d6cd  mov     rdi, rcx
0x14001d6d0  call    cs:__imp_GetCurrentProcess
0x14001d6d6  cmp     rdi, rax
0x14001d6d9  jz      short loc_14001D6F8
0x14001d6db  mov     r8, rbx; TokenHandle
0x14001d6de  mov     edx, 8; DesiredAccess
0x14001d6e3  mov     rcx, rdi; ProcessHandle
0x14001d6e6  call    cs:__imp_OpenProcessToken
0x14001d6ec  test    eax, eax
0x14001d6ee  jnz     short loc_14001D6FF
0x14001d6f0  call    cs:__imp_GetLastError
0x14001d6f6  jmp     short loc_14001D701
0x14001d6f8  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x14001d6ff  xor     eax, eax
0x14001d701  mov     rbx, [rsp+28h+arg_0]
0x14001d706  add     rsp, 20h
0x14001d70a  pop     rdi
0x14001d70b  retn
```
