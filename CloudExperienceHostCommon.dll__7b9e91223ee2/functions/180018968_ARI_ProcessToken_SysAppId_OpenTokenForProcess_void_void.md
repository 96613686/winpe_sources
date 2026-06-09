# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180018968`
- end: `0x1800189b4`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800188b0`

## callees

- `0x180018968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018998`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001898e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001898e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018978`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018978`

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
0x180018968  mov     [rsp+arg_0], rbx
0x18001896d  push    rdi
0x18001896e  sub     rsp, 20h
0x180018972  mov     rbx, rdx
0x180018975  mov     rdi, rcx
0x180018978  call    cs:__imp_GetCurrentProcess
0x18001897e  cmp     rdi, rax
0x180018981  jz      short loc_1800189A0
0x180018983  mov     r8, rbx; TokenHandle
0x180018986  mov     edx, 8; DesiredAccess
0x18001898b  mov     rcx, rdi; ProcessHandle
0x18001898e  call    cs:__imp_OpenProcessToken
0x180018994  test    eax, eax
0x180018996  jnz     short loc_1800189A7
0x180018998  call    cs:__imp_GetLastError
0x18001899e  jmp     short loc_1800189A9
0x1800189a0  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x1800189a7  xor     eax, eax
0x1800189a9  mov     rbx, [rsp+28h+arg_0]
0x1800189ae  add     rsp, 20h
0x1800189b2  pop     rdi
0x1800189b3  retn
```
