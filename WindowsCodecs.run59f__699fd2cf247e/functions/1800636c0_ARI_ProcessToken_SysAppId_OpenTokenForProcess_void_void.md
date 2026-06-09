# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x1800636c0`
- end: `0x18006371f`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `95`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800635f4`

## callees

- `0x1800636c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180063701`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180063701`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800636d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800636d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063711`

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
0x1800636c0  mov     [rsp+arg_0], rbx
0x1800636c5  push    rdi
0x1800636c6  sub     rsp, 20h
0x1800636ca  mov     rbx, rdx
0x1800636cd  mov     rdi, rcx
0x1800636d0  call    cs:__imp_GetCurrentProcess
0x1800636d7  nop     dword ptr [rax+rax+00h]
0x1800636dc  cmp     rdi, rax
0x1800636df  jnz     short loc_1800636F6
0x1800636e1  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x1800636e8  xor     eax, eax
0x1800636ea  mov     rbx, [rsp+28h+arg_0]
0x1800636ef  add     rsp, 20h
0x1800636f3  pop     rdi
0x1800636f4  retn
0x1800636f6  mov     r8, rbx; TokenHandle
0x1800636f9  mov     edx, 8; DesiredAccess
0x1800636fe  mov     rcx, rdi; ProcessHandle
0x180063701  call    cs:__imp_OpenProcessToken
0x180063708  nop     dword ptr [rax+rax+00h]
0x18006370d  test    eax, eax
0x18006370f  jnz     short loc_1800636E8
0x180063711  call    cs:__imp_GetLastError
0x180063718  nop     dword ptr [rax+rax+00h]
0x18006371d  jmp     short loc_1800636EA
```
