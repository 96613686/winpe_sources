# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x18007229c`
- end: `0x1800722e8`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800721e0`

## callees

- `0x18007229c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800722d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800722d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800722ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800722ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800722e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800722e0`

## pseudocode

```c
DWORD __fastcall ARI::ProcessToken::SysAppId::OpenTokenForProcess(HANDLE ProcessHandle, PHANDLE TokenHandle, void **a3)
{
  if ( ProcessHandle == GetCurrentProcess() )
  {
    *TokenHandle = (void *)-4LL;
    return 0;
  }
  if ( OpenProcessToken(ProcessHandle, 8u, TokenHandle) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x18007229c  mov     [rsp+arg_0], rbx
0x1800722a1  push    rdi
0x1800722a2  sub     rsp, 20h
0x1800722a6  mov     rbx, rdx
0x1800722a9  mov     rdi, rcx
0x1800722ac  call    cs:__imp_GetCurrentProcess
0x1800722b2  cmp     rdi, rax
0x1800722b5  jnz     short loc_1800722CB
0x1800722b7  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x1800722be  xor     eax, eax
0x1800722c0  mov     rbx, [rsp+28h+arg_0]
0x1800722c5  add     rsp, 20h
0x1800722c9  pop     rdi
0x1800722ca  retn
0x1800722cb  mov     r8, rbx; TokenHandle
0x1800722ce  mov     edx, 8; DesiredAccess
0x1800722d3  mov     rcx, rdi; ProcessHandle
0x1800722d6  call    cs:__imp_OpenProcessToken
0x1800722dc  test    eax, eax
0x1800722de  jnz     short loc_1800722BE
0x1800722e0  call    cs:__imp_GetLastError
0x1800722e6  jmp     short loc_1800722C0
```
