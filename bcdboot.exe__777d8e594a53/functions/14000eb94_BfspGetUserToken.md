# BfspGetUserToken

- ea: `0x14000eb94`
- end: `0x14000ec11`
- name: `BfspGetUserToken`
- size: `125`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000e79c`
- `0x14000ea4c`

## callees

- `0x14000eb94`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000ebe0`
- `KERNEL32!GetLastError` at `0x14000ebe0`
- `KERNEL32!GetCurrentThread` at `0x14000eba1`
- `KERNEL32!GetCurrentThread` at `0x14000ebc2`
- `KERNEL32!GetCurrentThread` at `0x14000eba1`
- `KERNEL32!GetCurrentThread` at `0x14000ebc2`
- `KERNEL32!GetCurrentProcess` at `0x14000ebed`
- `KERNEL32!GetCurrentProcess` at `0x14000ebed`
- `ADVAPI32!OpenProcessToken` at `0x14000ebfc`
- `ADVAPI32!OpenProcessToken` at `0x14000ebfc`
- `ADVAPI32!OpenThreadToken` at `0x14000ebb6`
- `ADVAPI32!OpenThreadToken` at `0x14000ebd4`
- `ADVAPI32!OpenThreadToken` at `0x14000ebb6`
- `ADVAPI32!OpenThreadToken` at `0x14000ebd4`

## pseudocode

```c
__int64 __fastcall BfspGetUserToken(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // ebx
  HANDLE v4; // rax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0x28u, 1, TokenHandle);
  if ( !v3 )
  {
    v4 = GetCurrentThread();
    v3 = OpenThreadToken(v4, 0x28u, 0, TokenHandle);
    if ( !v3 && GetLastError() == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      return OpenProcessToken(CurrentProcess, 0x28u, TokenHandle);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000eb94  mov     [rsp+arg_0], rbx
0x14000eb99  push    rdi
0x14000eb9a  sub     rsp, 20h
0x14000eb9e  mov     rdi, rcx
0x14000eba1  call    cs:__imp_GetCurrentThread
0x14000eba7  mov     edx, 28h ; '('; DesiredAccess
0x14000ebac  mov     r9, rdi; TokenHandle
0x14000ebaf  mov     rcx, rax; ThreadHandle
0x14000ebb2  lea     r8d, [rdx-27h]; OpenAsSelf
0x14000ebb6  call    cs:__imp_OpenThreadToken
0x14000ebbc  mov     ebx, eax
0x14000ebbe  test    eax, eax
0x14000ebc0  jnz     short loc_14000EC04
0x14000ebc2  call    cs:__imp_GetCurrentThread
0x14000ebc8  mov     r9, rdi; TokenHandle
0x14000ebcb  lea     edx, [rbx+28h]; DesiredAccess
0x14000ebce  mov     rcx, rax; ThreadHandle
0x14000ebd1  xor     r8d, r8d; OpenAsSelf
0x14000ebd4  call    cs:__imp_OpenThreadToken
0x14000ebda  mov     ebx, eax
0x14000ebdc  test    eax, eax
0x14000ebde  jnz     short loc_14000EC04
0x14000ebe0  call    cs:__imp_GetLastError
0x14000ebe6  cmp     eax, 3F0h
0x14000ebeb  jnz     short loc_14000EC04
0x14000ebed  call    cs:__imp_GetCurrentProcess
0x14000ebf3  mov     r8, rdi; TokenHandle
0x14000ebf6  lea     edx, [rbx+28h]; DesiredAccess
0x14000ebf9  mov     rcx, rax; ProcessHandle
0x14000ebfc  call    cs:__imp_OpenProcessToken
0x14000ec02  mov     ebx, eax
0x14000ec04  mov     eax, ebx
0x14000ec06  mov     rbx, [rsp+28h+arg_0]
0x14000ec0b  add     rsp, 20h
0x14000ec0f  pop     rdi
0x14000ec10  retn
```
