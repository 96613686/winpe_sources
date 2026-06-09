# BfspGetUserToken

- ea: `0x18004d35c`
- end: `0x18004d3d9`
- name: `BfspGetUserToken`
- size: `125`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18004cf64`
- `0x18004d214`

## callees

- `0x18004d35c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d3a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d38a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d38a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004d3c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004d3c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d3b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004d3b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d37e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d39c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d37e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d39c`

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
0x18004d35c  mov     [rsp+arg_0], rbx
0x18004d361  push    rdi
0x18004d362  sub     rsp, 20h
0x18004d366  mov     rdi, rcx
0x18004d369  call    cs:__imp_GetCurrentThread
0x18004d36f  mov     edx, 28h ; '('; DesiredAccess
0x18004d374  mov     r9, rdi; TokenHandle
0x18004d377  mov     rcx, rax; ThreadHandle
0x18004d37a  lea     r8d, [rdx-27h]; OpenAsSelf
0x18004d37e  call    cs:__imp_OpenThreadToken
0x18004d384  mov     ebx, eax
0x18004d386  test    eax, eax
0x18004d388  jnz     short loc_18004D3CC
0x18004d38a  call    cs:__imp_GetCurrentThread
0x18004d390  mov     r9, rdi; TokenHandle
0x18004d393  lea     edx, [rbx+28h]; DesiredAccess
0x18004d396  mov     rcx, rax; ThreadHandle
0x18004d399  xor     r8d, r8d; OpenAsSelf
0x18004d39c  call    cs:__imp_OpenThreadToken
0x18004d3a2  mov     ebx, eax
0x18004d3a4  test    eax, eax
0x18004d3a6  jnz     short loc_18004D3CC
0x18004d3a8  call    cs:__imp_GetLastError
0x18004d3ae  cmp     eax, 3F0h
0x18004d3b3  jnz     short loc_18004D3CC
0x18004d3b5  call    cs:__imp_GetCurrentProcess
0x18004d3bb  mov     r8, rdi; TokenHandle
0x18004d3be  lea     edx, [rbx+28h]; DesiredAccess
0x18004d3c1  mov     rcx, rax; ProcessHandle
0x18004d3c4  call    cs:__imp_OpenProcessToken
0x18004d3ca  mov     ebx, eax
0x18004d3cc  mov     eax, ebx
0x18004d3ce  mov     rbx, [rsp+28h+arg_0]
0x18004d3d3  add     rsp, 20h
0x18004d3d7  pop     rdi
0x18004d3d8  retn
```
