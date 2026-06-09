# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x18003e258`
- end: `0x18003e2a4`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003df54`

## callees

- `0x18003e258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e288`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e27e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e27e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e268`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e268`

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
0x18003e258  mov     [rsp+arg_0], rbx
0x18003e25d  push    rdi
0x18003e25e  sub     rsp, 20h
0x18003e262  mov     rbx, rdx
0x18003e265  mov     rdi, rcx
0x18003e268  call    cs:__imp_GetCurrentProcess
0x18003e26e  cmp     rdi, rax
0x18003e271  jz      short loc_18003E290
0x18003e273  mov     r8, rbx; TokenHandle
0x18003e276  mov     edx, 8; DesiredAccess
0x18003e27b  mov     rcx, rdi; ProcessHandle
0x18003e27e  call    cs:__imp_OpenProcessToken
0x18003e284  test    eax, eax
0x18003e286  jnz     short loc_18003E297
0x18003e288  call    cs:__imp_GetLastError
0x18003e28e  jmp     short loc_18003E299
0x18003e290  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x18003e297  xor     eax, eax
0x18003e299  mov     rbx, [rsp+28h+arg_0]
0x18003e29e  add     rsp, 20h
0x18003e2a2  pop     rdi
0x18003e2a3  retn
```
