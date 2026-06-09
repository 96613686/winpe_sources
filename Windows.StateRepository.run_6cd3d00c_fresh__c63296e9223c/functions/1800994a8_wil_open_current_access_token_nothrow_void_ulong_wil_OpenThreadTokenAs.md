# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x1800994a8`
- end: `0x18009951e`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800b284c`

## callees

- `0x1800994a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009950a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009950a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800994ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800994ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800994b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800994b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180099500`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180099500`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800994c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800994c4`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 0, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xCu, a1) )
      return 0;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800994a8  push    rbx
0x1800994aa  sub     rsp, 20h
0x1800994ae  mov     rbx, rcx
0x1800994b1  call    cs:__imp_GetCurrentThread
0x1800994b7  xor     r8d, r8d; OpenAsSelf
0x1800994ba  mov     r9, rbx; TokenHandle
0x1800994bd  mov     rcx, rax; ThreadHandle
0x1800994c0  lea     edx, [r8+0Ch]; DesiredAccess
0x1800994c4  call    cs:__imp_OpenThreadToken
0x1800994ca  test    eax, eax
0x1800994cc  jz      short loc_1800994D6
0x1800994ce  xor     eax, eax
0x1800994d0  add     rsp, 20h
0x1800994d4  pop     rbx
0x1800994d5  retn
0x1800994d6  call    cs:__imp_GetLastError
0x1800994dc  test    eax, eax
0x1800994de  jle     short loc_1800994E8
0x1800994e0  movzx   eax, ax
0x1800994e3  or      eax, 80070000h
0x1800994e8  cmp     eax, 800703F0h
0x1800994ed  jnz     short loc_1800994D0
0x1800994ef  call    cs:__imp_GetCurrentProcess
0x1800994f5  mov     r8, rbx; TokenHandle
0x1800994f8  mov     edx, 0Ch; DesiredAccess
0x1800994fd  mov     rcx, rax; ProcessHandle
0x180099500  call    cs:__imp_OpenProcessToken
0x180099506  test    eax, eax
0x180099508  jnz     short loc_1800994CE
0x18009950a  call    cs:__imp_GetLastError
0x180099510  test    eax, eax
0x180099512  jle     short loc_1800994D0
0x180099514  movzx   eax, ax
0x180099517  or      eax, 80070000h
0x18009951c  jmp     short loc_1800994D0
```
