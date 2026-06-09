# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x1800cff88`
- end: `0x1800d0030`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800cbe2c`

## callees

- `0x1800c97f0`
- `0x1800cff88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cffe5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cffe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cffd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cffd2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cffaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cffaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cff9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cff9a`

## string_xrefs

- `0x1800d000a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
    goto LABEL_11;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
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
    wil::details::in1diag3::_Throw_Hr(
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
0x1800cff88  push    rbx
0x1800cff8a  sub     rsp, 30h
0x1800cff8e  mov     rbx, rcx
0x1800cff91  mov     [rsp+38h+TokenHandle], 0
0x1800cff9a  call    cs:__imp_GetCurrentThread
0x1800cffa0  xor     r8d, r8d; OpenAsSelf
0x1800cffa3  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800cffa8  mov     rcx, rax; ThreadHandle
0x1800cffab  lea     edx, [r8+8]; DesiredAccess
0x1800cffaf  call    cs:__imp_OpenThreadToken
0x1800cffb5  test    eax, eax
0x1800cffb7  jnz     short loc_1800D001F
0x1800cffb9  call    cs:__imp_GetLastError
0x1800cffbf  test    eax, eax
0x1800cffc1  jle     short loc_1800CFFCB
0x1800cffc3  movzx   eax, ax
0x1800cffc6  or      eax, 80070000h
0x1800cffcb  cmp     eax, 800703F0h
0x1800cffd0  jnz     short loc_1800D0001
0x1800cffd2  call    cs:__imp_GetCurrentProcess
0x1800cffd8  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800cffdd  mov     edx, 8; DesiredAccess
0x1800cffe2  mov     rcx, rax; ProcessHandle
0x1800cffe5  call    cs:__imp_OpenProcessToken
0x1800cffeb  test    eax, eax
0x1800cffed  jnz     short loc_1800D001F
0x1800cffef  call    cs:__imp_GetLastError
0x1800cfff5  test    eax, eax
0x1800cfff7  jle     short loc_1800D0003
0x1800cfff9  movzx   eax, ax
0x1800cfffc  or      eax, 80070000h
0x1800d0001  test    eax, eax
0x1800d0003  jns     short loc_1800D001F
0x1800d0005  mov     rcx, [rsp+38h]; this
0x1800d000a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d0011  mov     r9d, eax; char *
0x1800d0014  mov     edx, 0E1h; void *
0x1800d0019  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d001f  mov     rax, [rsp+38h+TokenHandle]
0x1800d0024  mov     [rbx], rax
0x1800d0027  mov     rax, rbx
0x1800d002a  add     rsp, 30h
0x1800d002e  pop     rbx
0x1800d002f  retn
```
