# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x18007d56c`
- end: `0x18007d616`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18007d4bc`

## callees

- `0x18001be60`
- `0x18007d56c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d59f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d59f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d5d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007d5b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007d5b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007d5cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007d5cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007d57e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007d57e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007d595`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007d595`

## string_xrefs

- `0x18007d5f0`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void **__fastcall wil::open_current_access_token(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  bool v5; // sf
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    goto LABEL_11;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
      goto LABEL_11;
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v5 = LastError < 0;
LABEL_9:
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)(unsigned int)LastError,
      v7);
LABEL_11:
  *a1 = TokenHandle;
  return a1;
}

```

## disassembly

```asm
0x18007d56c  push    rbx
0x18007d56e  sub     rsp, 30h
0x18007d572  mov     rbx, rcx
0x18007d575  mov     [rsp+38h+TokenHandle], 0
0x18007d57e  call    cs:__imp_GetCurrentThread
0x18007d584  mov     edx, 0Eh; DesiredAccess
0x18007d589  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18007d58e  mov     rcx, rax; ThreadHandle
0x18007d591  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x18007d595  call    cs:__imp_OpenThreadToken
0x18007d59b  test    eax, eax
0x18007d59d  jnz     short loc_18007D605
0x18007d59f  call    cs:__imp_GetLastError
0x18007d5a5  test    eax, eax
0x18007d5a7  jle     short loc_18007D5B1
0x18007d5a9  movzx   eax, ax
0x18007d5ac  or      eax, 80070000h
0x18007d5b1  cmp     eax, 800703F0h
0x18007d5b6  jnz     short loc_18007D5E7
0x18007d5b8  call    cs:__imp_GetCurrentProcess
0x18007d5be  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18007d5c3  mov     edx, 0Eh; DesiredAccess
0x18007d5c8  mov     rcx, rax; ProcessHandle
0x18007d5cb  call    cs:__imp_OpenProcessToken
0x18007d5d1  test    eax, eax
0x18007d5d3  jnz     short loc_18007D605
0x18007d5d5  call    cs:__imp_GetLastError
0x18007d5db  test    eax, eax
0x18007d5dd  jle     short loc_18007D5E9
0x18007d5df  movzx   eax, ax
0x18007d5e2  or      eax, 80070000h
0x18007d5e7  test    eax, eax
0x18007d5e9  jns     short loc_18007D605
0x18007d5eb  mov     rcx, [rsp+38h]; this
0x18007d5f0  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007d5f7  mov     r9d, eax; char *
0x18007d5fa  mov     edx, 0E1h; void *
0x18007d5ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007d605  mov     rax, [rsp+38h+TokenHandle]
0x18007d60a  mov     [rbx], rax
0x18007d60d  mov     rax, rbx
0x18007d610  add     rsp, 30h
0x18007d614  pop     rbx
0x18007d615  retn
```
