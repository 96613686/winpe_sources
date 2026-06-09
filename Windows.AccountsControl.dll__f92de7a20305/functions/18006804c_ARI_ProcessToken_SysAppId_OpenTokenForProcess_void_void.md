# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x18006804c`
- end: `0x180068098`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180067fa4`
- `0x180068384`

## callees

- `0x18006804c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006807c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006807c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006805c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006805c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068072`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180068072`

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
0x18006804c  mov     [rsp+arg_0], rbx
0x180068051  push    rdi
0x180068052  sub     rsp, 20h
0x180068056  mov     rbx, rdx
0x180068059  mov     rdi, rcx
0x18006805c  call    cs:__imp_GetCurrentProcess
0x180068062  cmp     rdi, rax
0x180068065  jz      short loc_180068084
0x180068067  mov     r8, rbx; TokenHandle
0x18006806a  mov     edx, 8; DesiredAccess
0x18006806f  mov     rcx, rdi; ProcessHandle
0x180068072  call    cs:__imp_OpenProcessToken
0x180068078  test    eax, eax
0x18006807a  jnz     short loc_18006808B
0x18006807c  call    cs:__imp_GetLastError
0x180068082  jmp     short loc_18006808D
0x180068084  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x18006808b  xor     eax, eax
0x18006808d  mov     rbx, [rsp+28h+arg_0]
0x180068092  add     rsp, 20h
0x180068096  pop     rdi
0x180068097  retn
```
