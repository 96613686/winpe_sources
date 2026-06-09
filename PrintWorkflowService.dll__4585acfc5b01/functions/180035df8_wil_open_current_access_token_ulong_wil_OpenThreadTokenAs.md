# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x180035df8`
- end: `0x180035ea0`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180032bf4`
- `0x18003b0b4`

## callees

- `0x1800127a4`
- `0x180035df8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035e0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035e0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035e55`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035e55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035e42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035e42`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035e1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035e1f`

## string_xrefs

- `0x180035e8b`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_10;
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)(unsigned int)LastError,
      v7);
LABEL_10:
  *a1 = TokenHandle;
  return a1;
}

```

## disassembly

```asm
0x180035df8  push    rbx
0x180035dfa  sub     rsp, 30h
0x180035dfe  mov     rbx, rcx
0x180035e01  mov     [rsp+38h+TokenHandle], 0
0x180035e0a  call    cs:__imp_GetCurrentThread
0x180035e10  xor     r8d, r8d; OpenAsSelf
0x180035e13  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180035e18  mov     rcx, rax; ThreadHandle
0x180035e1b  lea     edx, [r8+8]; DesiredAccess
0x180035e1f  call    cs:__imp_OpenThreadToken
0x180035e25  test    eax, eax
0x180035e27  jnz     short loc_180035E75
0x180035e29  call    cs:__imp_GetLastError
0x180035e2f  test    eax, eax
0x180035e31  jle     short loc_180035E3B
0x180035e33  movzx   eax, ax
0x180035e36  or      eax, 80070000h
0x180035e3b  cmp     eax, 800703F0h
0x180035e40  jnz     short loc_180035E71
0x180035e42  call    cs:__imp_GetCurrentProcess
0x180035e48  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180035e4d  mov     edx, 8; DesiredAccess
0x180035e52  mov     rcx, rax; ProcessHandle
0x180035e55  call    cs:__imp_OpenProcessToken
0x180035e5b  test    eax, eax
0x180035e5d  jnz     short loc_180035E75
0x180035e5f  call    cs:__imp_GetLastError
0x180035e65  test    eax, eax
0x180035e67  jle     short loc_180035E73
0x180035e69  movzx   eax, ax
0x180035e6c  or      eax, 80070000h
0x180035e71  test    eax, eax
0x180035e73  js      short loc_180035E86
0x180035e75  mov     rax, [rsp+38h+TokenHandle]
0x180035e7a  mov     [rbx], rax
0x180035e7d  mov     rax, rbx
0x180035e80  add     rsp, 30h
0x180035e84  pop     rbx
0x180035e85  retn
0x180035e86  mov     rcx, [rsp+38h]; this
0x180035e8b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035e92  mov     r9d, eax; char *
0x180035e95  mov     edx, 0E1h; void *
0x180035e9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
