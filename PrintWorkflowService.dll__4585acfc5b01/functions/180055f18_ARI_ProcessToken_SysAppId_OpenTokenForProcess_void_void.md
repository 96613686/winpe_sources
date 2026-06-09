# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180055f18`
- end: `0x180055f64`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180055b7c`
- `0x180055d08`

## callees

- `0x180055f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055f48`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180055f3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180055f3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055f28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055f28`

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
0x180055f18  mov     [rsp+arg_0], rbx
0x180055f1d  push    rdi
0x180055f1e  sub     rsp, 20h
0x180055f22  mov     rbx, rdx
0x180055f25  mov     rdi, rcx
0x180055f28  call    cs:__imp_GetCurrentProcess
0x180055f2e  cmp     rdi, rax
0x180055f31  jz      short loc_180055F50
0x180055f33  mov     r8, rbx; TokenHandle
0x180055f36  mov     edx, 8; DesiredAccess
0x180055f3b  mov     rcx, rdi; ProcessHandle
0x180055f3e  call    cs:__imp_OpenProcessToken
0x180055f44  test    eax, eax
0x180055f46  jnz     short loc_180055F57
0x180055f48  call    cs:__imp_GetLastError
0x180055f4e  jmp     short loc_180055F59
0x180055f50  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x180055f57  xor     eax, eax
0x180055f59  mov     rbx, [rsp+28h+arg_0]
0x180055f5e  add     rsp, 20h
0x180055f62  pop     rdi
0x180055f63  retn
```
