# ImpersonateAndGetToken(void * *)

- ea: `0x18002723c`
- end: `0x1800272dd`
- name: `?ImpersonateAndGetToken@@YAJPEAPEAX@Z`
- size: `161`
- prototype: `signed int __fastcall(void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002643c`
- `0x180026bd0`
- `0x180026f00`
- `0x1800270b0`
- `0x180027368`

## callees

- `0x18002723c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002728e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002728e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027277`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002725e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002725e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800272a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800272a1`
- `RPCRT4!RpcImpersonateClient` at `0x18002724b`
- `RPCRT4!RpcImpersonateClient` at `0x18002724b`
- `RPCRT4!RpcRevertToSelf` at `0x18002727f`
- `RPCRT4!RpcRevertToSelf` at `0x18002727f`

## pseudocode

```c
signed int __fastcall ImpersonateAndGetToken(void **a1)
{
  RPC_STATUS v2; // eax
  HANDLE CurrentThread; // rax
  BOOL v4; // ebx
  HANDLE CurrentProcess; // rax
  signed int result; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  v2 = RpcImpersonateClient(0);
  TokenHandle = 0;
  if ( v2 )
  {
    if ( v2 != 1725 )
      return -2147467259;
    CurrentProcess = GetCurrentProcess();
    v4 = OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v4 = OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle);
    RpcRevertToSelf();
  }
  if ( v4 )
  {
    *a1 = TokenHandle;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002723c  mov     [rsp+arg_0], rbx
0x180027241  push    rdi
0x180027242  sub     rsp, 20h
0x180027246  mov     rdi, rcx
0x180027249  xor     ecx, ecx; BindingHandle
0x18002724b  call    cs:__imp_RpcImpersonateClient
0x180027251  mov     [rsp+28h+TokenHandle], 0
0x18002725a  test    eax, eax
0x18002725c  jnz     short loc_180027287
0x18002725e  call    cs:__imp_GetCurrentThread
0x180027264  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180027269  mov     edx, 20008h; DesiredAccess
0x18002726e  mov     rcx, rax; ThreadHandle
0x180027271  mov     r8d, 1; OpenAsSelf
0x180027277  call    cs:__imp_OpenThreadToken
0x18002727d  mov     ebx, eax
0x18002727f  call    cs:__imp_RpcRevertToSelf
0x180027285  jmp     short loc_1800272A9
0x180027287  cmp     eax, 6BDh
0x18002728c  jnz     short loc_1800272CD
0x18002728e  call    cs:__imp_GetCurrentProcess
0x180027294  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180027299  mov     edx, 20008h; DesiredAccess
0x18002729e  mov     rcx, rax; ProcessHandle
0x1800272a1  call    cs:__imp_OpenProcessToken
0x1800272a7  mov     ebx, eax
0x1800272a9  test    ebx, ebx
0x1800272ab  jnz     short loc_1800272C1
0x1800272ad  call    cs:__imp_GetLastError
0x1800272b3  test    eax, eax
0x1800272b5  jle     short loc_1800272D2
0x1800272b7  movzx   eax, ax
0x1800272ba  or      eax, 80070000h
0x1800272bf  jmp     short loc_1800272D2
0x1800272c1  mov     rax, [rsp+28h+TokenHandle]
0x1800272c6  mov     [rdi], rax
0x1800272c9  xor     eax, eax
0x1800272cb  jmp     short loc_1800272D2
0x1800272cd  mov     eax, 80004005h
0x1800272d2  mov     rbx, [rsp+28h+arg_0]
0x1800272d7  add     rsp, 20h
0x1800272db  pop     rdi
0x1800272dc  retn
```
