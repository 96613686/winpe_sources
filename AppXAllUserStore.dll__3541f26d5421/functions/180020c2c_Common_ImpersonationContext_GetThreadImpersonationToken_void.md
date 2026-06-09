# Common::ImpersonationContext::GetThreadImpersonationToken(void * *)

- ea: `0x180020c2c`
- end: `0x180020c8a`
- name: `?GetThreadImpersonationToken@ImpersonationContext@Common@@SAJPEAPEAX@Z`
- size: `94`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020b04`
- `0x180020bb4`

## callees

- `0x180020c2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020c65`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020c50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020c50`

## pseudocode

```c
signed int __fastcall Common::ImpersonationContext::GetThreadImpersonationToken(PHANDLE TokenHandle)
{
  signed int result; // eax
  HANDLE CurrentThread; // rax

  if ( !NtCurrentTeb()->IsImpersonating )
  {
    *TokenHandle = 0;
    return 0;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, TokenHandle) )
    return 0;
  result = GetLastError();
  if ( result == 1008 )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180020c2c  push    rbx
0x180020c2e  sub     rsp, 20h
0x180020c32  mov     eax, gs:179Ch
0x180020c3a  mov     rbx, rcx
0x180020c3d  test    eax, eax
0x180020c3f  jnz     short loc_180020C50
0x180020c41  mov     qword ptr [rcx], 0
0x180020c48  xor     eax, eax
0x180020c4a  add     rsp, 20h
0x180020c4e  pop     rbx
0x180020c4f  retn
0x180020c50  call    cs:__imp_GetCurrentThread
0x180020c56  mov     edx, 0Ch; DesiredAccess
0x180020c5b  mov     r9, rbx; TokenHandle
0x180020c5e  mov     rcx, rax; ThreadHandle
0x180020c61  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180020c65  call    cs:__imp_OpenThreadToken
0x180020c6b  test    eax, eax
0x180020c6d  jnz     short loc_180020C48
0x180020c6f  call    cs:__imp_GetLastError
0x180020c75  cmp     eax, 3F0h
0x180020c7a  jz      short loc_180020C48
0x180020c7c  test    eax, eax
0x180020c7e  jle     short loc_180020C4A
0x180020c80  movzx   eax, ax
0x180020c83  or      eax, 80070000h
0x180020c88  jmp     short loc_180020C4A
```
