# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x18007b1e8`
- end: `0x18007b28c`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180029e04`
- `0x18007b024`

## callees

- `0x18007b1e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b268`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007b211`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007b211`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b240`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b240`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b1f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b1f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b254`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b254`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1, DWORD a2)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a2, 1, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, a2, a1) )
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
0x18007b1e8  mov     [rsp+arg_0], rbx
0x18007b1ed  push    rdi
0x18007b1ee  sub     rsp, 20h
0x18007b1f2  mov     ebx, edx
0x18007b1f4  mov     rdi, rcx
0x18007b1f7  call    cs:__imp_GetCurrentThread
0x18007b1fe  nop     dword ptr [rax+rax+00h]
0x18007b203  mov     r9, rdi; TokenHandle
0x18007b206  mov     r8d, 1; OpenAsSelf
0x18007b20c  mov     rcx, rax; ThreadHandle
0x18007b20f  mov     edx, ebx; DesiredAccess
0x18007b211  call    cs:__imp_OpenThreadToken
0x18007b218  nop     dword ptr [rax+rax+00h]
0x18007b21d  test    eax, eax
0x18007b21f  jnz     short loc_18007B264
0x18007b221  call    cs:__imp_GetLastError
0x18007b228  nop     dword ptr [rax+rax+00h]
0x18007b22d  test    eax, eax
0x18007b22f  jle     short loc_18007B239
0x18007b231  movzx   eax, ax
0x18007b234  or      eax, 80070000h
0x18007b239  cmp     eax, 800703F0h
0x18007b23e  jnz     short loc_18007B280
0x18007b240  call    cs:__imp_GetCurrentProcess
0x18007b247  nop     dword ptr [rax+rax+00h]
0x18007b24c  mov     r8, rdi; TokenHandle
0x18007b24f  mov     edx, ebx; DesiredAccess
0x18007b251  mov     rcx, rax; ProcessHandle
0x18007b254  call    cs:__imp_OpenProcessToken
0x18007b25b  nop     dword ptr [rax+rax+00h]
0x18007b260  test    eax, eax
0x18007b262  jz      short loc_18007B268
0x18007b264  xor     eax, eax
0x18007b266  jmp     short loc_18007B280
0x18007b268  call    cs:__imp_GetLastError
0x18007b26f  nop     dword ptr [rax+rax+00h]
0x18007b274  test    eax, eax
0x18007b276  jle     short loc_18007B280
0x18007b278  movzx   eax, ax
0x18007b27b  or      eax, 80070000h
0x18007b280  mov     rbx, [rsp+28h+arg_0]
0x18007b285  add     rsp, 20h
0x18007b289  pop     rdi
0x18007b28a  retn
```
