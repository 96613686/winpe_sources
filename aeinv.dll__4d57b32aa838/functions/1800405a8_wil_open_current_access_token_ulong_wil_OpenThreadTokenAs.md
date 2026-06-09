# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x1800405a8`
- end: `0x180040650`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003f1c8`

## callees

- `0x1800405a8`
- `0x1800679f8`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180040605`
- `ADVAPI32!OpenProcessToken` at `0x180040605`
- `ADVAPI32!OpenThreadToken` at `0x1800405cf`
- `ADVAPI32!OpenThreadToken` at `0x1800405cf`
- `KERNEL32!GetCurrentProcess` at `0x1800405f2`
- `KERNEL32!GetCurrentProcess` at `0x1800405f2`
- `KERNEL32!GetCurrentThread` at `0x1800405ba`
- `KERNEL32!GetCurrentThread` at `0x1800405ba`
- `KERNEL32!GetLastError` at `0x1800405d9`
- `KERNEL32!GetLastError` at `0x18004060f`
- `KERNEL32!GetLastError` at `0x1800405d9`
- `KERNEL32!GetLastError` at `0x18004060f`

## string_xrefs

- `0x18004062a`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
0x1800405a8  push    rbx
0x1800405aa  sub     rsp, 30h
0x1800405ae  mov     rbx, rcx
0x1800405b1  mov     [rsp+38h+TokenHandle], 0
0x1800405ba  call    cs:__imp_GetCurrentThread
0x1800405c0  xor     r8d, r8d; OpenAsSelf
0x1800405c3  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800405c8  mov     rcx, rax; ThreadHandle
0x1800405cb  lea     edx, [r8+8]; DesiredAccess
0x1800405cf  call    cs:__imp_OpenThreadToken
0x1800405d5  test    eax, eax
0x1800405d7  jnz     short loc_18004063F
0x1800405d9  call    cs:__imp_GetLastError
0x1800405df  test    eax, eax
0x1800405e1  jle     short loc_1800405EB
0x1800405e3  movzx   eax, ax
0x1800405e6  or      eax, 80070000h
0x1800405eb  cmp     eax, 800703F0h
0x1800405f0  jnz     short loc_180040621
0x1800405f2  call    cs:__imp_GetCurrentProcess
0x1800405f8  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800405fd  mov     edx, 8; DesiredAccess
0x180040602  mov     rcx, rax; ProcessHandle
0x180040605  call    cs:__imp_OpenProcessToken
0x18004060b  test    eax, eax
0x18004060d  jnz     short loc_18004063F
0x18004060f  call    cs:__imp_GetLastError
0x180040615  test    eax, eax
0x180040617  jle     short loc_180040623
0x180040619  movzx   eax, ax
0x18004061c  or      eax, 80070000h
0x180040621  test    eax, eax
0x180040623  jns     short loc_18004063F
0x180040625  mov     rcx, [rsp+38h]; this
0x18004062a  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180040631  mov     r9d, eax; char *
0x180040634  mov     edx, 0E1h; void *
0x180040639  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004063f  mov     rax, [rsp+38h+TokenHandle]
0x180040644  mov     [rbx], rax
0x180040647  mov     rax, rbx
0x18004064a  add     rsp, 30h
0x18004064e  pop     rbx
0x18004064f  retn
```
