# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x18005cf70`
- end: `0x18005cfbc`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18005cdb8`

## callees

- `0x18005cf70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cfa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cfa0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005cf96`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005cf96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cf80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cf80`

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
0x18005cf70  mov     [rsp+arg_0], rbx
0x18005cf75  push    rdi
0x18005cf76  sub     rsp, 20h
0x18005cf7a  mov     rbx, rdx
0x18005cf7d  mov     rdi, rcx
0x18005cf80  call    cs:__imp_GetCurrentProcess
0x18005cf86  cmp     rdi, rax
0x18005cf89  jz      short loc_18005CFA8
0x18005cf8b  mov     r8, rbx; TokenHandle
0x18005cf8e  mov     edx, 8; DesiredAccess
0x18005cf93  mov     rcx, rdi; ProcessHandle
0x18005cf96  call    cs:__imp_OpenProcessToken
0x18005cf9c  test    eax, eax
0x18005cf9e  jnz     short loc_18005CFAF
0x18005cfa0  call    cs:__imp_GetLastError
0x18005cfa6  jmp     short loc_18005CFB1
0x18005cfa8  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x18005cfaf  xor     eax, eax
0x18005cfb1  mov     rbx, [rsp+28h+arg_0]
0x18005cfb6  add     rsp, 20h
0x18005cfba  pop     rdi
0x18005cfbb  retn
```
