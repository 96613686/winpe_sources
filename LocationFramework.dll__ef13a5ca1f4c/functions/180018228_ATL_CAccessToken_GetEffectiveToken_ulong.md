# ATL::CAccessToken::GetEffectiveToken(ulong)

- ea: `0x180018228`
- end: `0x180018301`
- name: `?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z`
- size: `217`
- prototype: `bool(ATL::CAccessToken *__hidden this, unsigned int)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001733c`
- `0x180017c0c`
- `0x180019870`
- `0x180019bb0`
- `0x1800567ac`
- `0x18009772c`
- `0x18009b528`
- `0x1800c157c`
- `0x180117508`

## callees

- `0x180018228`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018276`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001826c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001826c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018283`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001829c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001829c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001824b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001824b`

## pseudocode

```c
char __fastcall ATL::CAccessToken::GetEffectiveToken(ATL::CAccessToken *this, DWORD a2)
{
  HANDLE CurrentThread; // rax
  char v5; // di
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  CurrentThread = GetCurrentThread();
  v5 = 1;
  TokenHandle = 0;
  if ( OpenThreadToken(CurrentThread, a2, 1, &TokenHandle) )
    goto LABEL_4;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    TokenHandle = 0;
    if ( !OpenProcessToken(CurrentProcess, a2, &TokenHandle) )
      return 0;
LABEL_4:
    (*(void (__fastcall **)(ATL::CAccessToken *))(*(_QWORD *)this + 8LL))(this);
    *((_QWORD *)this + 1) = TokenHandle;
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180018228  mov     [rsp+arg_10], rbx
0x18001822d  mov     [rsp+arg_18], rsi
0x180018232  push    rdi
0x180018233  sub     rsp, 30h
0x180018237  mov     rax, cs:__security_cookie
0x18001823e  xor     rax, rsp
0x180018241  mov     [rsp+38h+var_10], rax
0x180018246  mov     esi, edx
0x180018248  mov     rbx, rcx
0x18001824b  call    cs:__imp_GetCurrentThread
0x180018251  mov     edi, 1
0x180018256  mov     [rsp+38h+TokenHandle], 0
0x18001825f  mov     r8d, edi; OpenAsSelf
0x180018262  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180018267  mov     rcx, rax; ThreadHandle
0x18001826a  mov     edx, esi; DesiredAccess
0x18001826c  call    cs:__imp_OpenThreadToken
0x180018272  test    eax, eax
0x180018274  jnz     short loc_1800182DE
0x180018276  call    cs:__imp_GetLastError
0x18001827c  cmp     eax, 3F0h
0x180018281  jnz     short loc_1800182FD
0x180018283  call    cs:__imp_GetCurrentProcess
0x180018289  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18001828e  mov     [rsp+38h+TokenHandle], 0
0x180018297  mov     rcx, rax; ProcessHandle
0x18001829a  mov     edx, esi; DesiredAccess
0x18001829c  call    cs:__imp_OpenProcessToken
0x1800182a2  test    eax, eax
0x1800182a4  jz      short loc_1800182F8
0x1800182a6  mov     rax, [rbx]
0x1800182a9  mov     rcx, rbx
0x1800182ac  mov     rax, [rax+8]
0x1800182b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182b5  mov     rax, [rsp+38h+TokenHandle]
0x1800182ba  mov     [rbx+8], rax
0x1800182be  mov     al, dil
0x1800182c1  mov     rcx, [rsp+38h+var_10]
0x1800182c6  xor     rcx, rsp; StackCookie
0x1800182c9  call    __security_check_cookie
0x1800182ce  mov     rbx, [rsp+38h+arg_10]
0x1800182d3  mov     rsi, [rsp+38h+arg_18]
0x1800182d8  add     rsp, 30h
0x1800182dc  pop     rdi
0x1800182dd  retn
0x1800182de  mov     rcx, [rbx]
0x1800182e1  mov     rax, [rcx+8]
0x1800182e5  mov     rcx, rbx
0x1800182e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182ed  mov     rcx, [rsp+38h+TokenHandle]
0x1800182f2  mov     [rbx+8], rcx
0x1800182f6  jmp     short loc_1800182BE
0x1800182f8  xor     dil, dil
0x1800182fb  jmp     short loc_1800182BE
0x1800182fd  xor     al, al
0x1800182ff  jmp     short loc_1800182C1
```
