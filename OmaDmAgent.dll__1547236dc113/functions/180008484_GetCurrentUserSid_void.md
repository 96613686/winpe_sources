# GetCurrentUserSid(void * *)

- ea: `0x180008484`
- end: `0x18000853e`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `186`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800083fc`

## callees

- `0x180008484`
- `0x18000867c`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x1800084c2`
- `ADVAPI32!OpenThreadToken` at `0x1800084c2`
- `ADVAPI32!OpenProcessToken` at `0x1800084fe`
- `ADVAPI32!OpenProcessToken` at `0x1800084fe`
- `KERNEL32!GetLastError` at `0x1800084d2`
- `KERNEL32!GetLastError` at `0x18000850e`
- `KERNEL32!GetLastError` at `0x1800084d2`
- `KERNEL32!GetLastError` at `0x18000850e`
- `KERNEL32!GetCurrentProcess` at `0x1800084e5`
- `KERNEL32!GetCurrentProcess` at `0x1800084e5`
- `KERNEL32!GetCurrentThread` at `0x1800084a5`
- `KERNEL32!GetCurrentThread` at `0x1800084a5`

## pseudocode

```c
signed int __fastcall GetCurrentUserSid(void **a1)
{
  signed int result; // eax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  bool v5; // sf
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 )
    return -2147024809;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    return GetUserSidFromToken(TokenHandle, a1);
  result = GetLastError();
  if ( result == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      return GetUserSidFromToken(TokenHandle, a1);
    result = GetLastError();
  }
  v5 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
    return GetUserSidFromToken(TokenHandle, a1);
  return result;
}

```

## disassembly

```asm
0x180008484  push    rbx
0x180008486  sub     rsp, 20h
0x18000848a  mov     rbx, rcx
0x18000848d  test    rcx, rcx
0x180008490  jnz     short loc_18000849C
0x180008492  mov     eax, 80070057h
0x180008497  jmp     loc_180008537
0x18000849c  mov     [rsp+28h+TokenHandle], 0
0x1800084a5  call    cs:__imp_GetCurrentThread
0x1800084ac  nop     dword ptr [rax+rax+00h]
0x1800084b1  mov     edx, 8; DesiredAccess
0x1800084b6  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800084bb  mov     rcx, rax; ThreadHandle
0x1800084be  lea     r8d, [rdx-7]; OpenAsSelf
0x1800084c2  call    cs:__imp_OpenThreadToken
0x1800084c9  nop     dword ptr [rax+rax+00h]
0x1800084ce  test    eax, eax
0x1800084d0  jnz     short loc_18000852A
0x1800084d2  call    cs:__imp_GetLastError
0x1800084d9  nop     dword ptr [rax+rax+00h]
0x1800084de  cmp     eax, 3F0h
0x1800084e3  jnz     short loc_18000851A
0x1800084e5  call    cs:__imp_GetCurrentProcess
0x1800084ec  nop     dword ptr [rax+rax+00h]
0x1800084f1  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800084f6  mov     edx, 8; DesiredAccess
0x1800084fb  mov     rcx, rax; ProcessHandle
0x1800084fe  call    cs:__imp_OpenProcessToken
0x180008505  nop     dword ptr [rax+rax+00h]
0x18000850a  test    eax, eax
0x18000850c  jnz     short loc_18000852A
0x18000850e  call    cs:__imp_GetLastError
0x180008515  nop     dword ptr [rax+rax+00h]
0x18000851a  test    eax, eax
0x18000851c  jle     short loc_180008528
0x18000851e  movzx   eax, ax
0x180008521  or      eax, 80070000h
0x180008526  test    eax, eax
0x180008528  js      short loc_180008537
0x18000852a  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18000852f  mov     rdx, rbx; void **
0x180008532  call    ?GetUserSidFromToken@@YAJPEAXPEAPEAX@Z; GetUserSidFromToken(void *,void * *)
0x180008537  add     rsp, 20h
0x18000853b  pop     rbx
0x18000853c  retn
```
