# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180056190`
- end: `0x1800561dc`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180056464`

## callees

- `0x180056190`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800561a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800561a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800561b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800561b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800561c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800561c0`

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
0x180056190  mov     [rsp+arg_0], rbx
0x180056195  push    rdi
0x180056196  sub     rsp, 20h
0x18005619a  mov     rbx, rdx
0x18005619d  mov     rdi, rcx
0x1800561a0  call    cs:__imp_GetCurrentProcess
0x1800561a6  cmp     rdi, rax
0x1800561a9  jz      short loc_1800561C8
0x1800561ab  mov     r8, rbx; TokenHandle
0x1800561ae  mov     edx, 8; DesiredAccess
0x1800561b3  mov     rcx, rdi; ProcessHandle
0x1800561b6  call    cs:__imp_OpenProcessToken
0x1800561bc  test    eax, eax
0x1800561be  jnz     short loc_1800561CF
0x1800561c0  call    cs:__imp_GetLastError
0x1800561c6  jmp     short loc_1800561D1
0x1800561c8  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x1800561cf  xor     eax, eax
0x1800561d1  mov     rbx, [rsp+28h+arg_0]
0x1800561d6  add     rsp, 20h
0x1800561da  pop     rdi
0x1800561db  retn
```
