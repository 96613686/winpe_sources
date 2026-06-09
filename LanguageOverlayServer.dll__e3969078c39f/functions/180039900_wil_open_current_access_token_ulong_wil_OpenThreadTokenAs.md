# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x180039900`
- end: `0x1800399c0`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800362a0`

## callees

- `0x180012a98`
- `0x180039900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039978`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003995e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003995e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039926`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039926`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039939`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039939`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003996e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003996e`

## string_xrefs

- `0x1800399ab`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void **__fastcall wil::open_current_access_token(void **a1, DWORD a2, int a3)
{
  BOOL v5; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  bool v9; // sf
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  v5 = a3 == 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a2, v5, &TokenHandle) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, a2, &TokenHandle) )
      goto LABEL_10;
    LastError = GetLastError();
    v9 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v9 = LastError < 0;
LABEL_9:
  if ( v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)(unsigned int)LastError,
      v11);
LABEL_10:
  *a1 = TokenHandle;
  return a1;
}

```

## disassembly

```asm
0x180039900  mov     [rsp+arg_0], rbx
0x180039905  mov     [rsp+arg_8], rsi
0x18003990a  push    rdi
0x18003990b  sub     rsp, 30h
0x18003990f  xor     ebx, ebx
0x180039911  mov     [rsp+38h+TokenHandle], 0
0x18003991a  cmp     r8d, 1
0x18003991e  mov     esi, edx
0x180039920  mov     rdi, rcx
0x180039923  setz    bl
0x180039926  call    cs:__imp_GetCurrentThread
0x18003992c  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180039931  mov     r8d, ebx; OpenAsSelf
0x180039934  mov     rcx, rax; ThreadHandle
0x180039937  mov     edx, esi; DesiredAccess
0x180039939  call    cs:__imp_OpenThreadToken
0x18003993f  test    eax, eax
0x180039941  jnz     short loc_18003998B
0x180039943  call    cs:__imp_GetLastError
0x180039949  mov     ebx, 80070000h
0x18003994e  test    eax, eax
0x180039950  jle     short loc_180039957
0x180039952  movzx   eax, ax
0x180039955  or      eax, ebx
0x180039957  cmp     eax, 800703F0h
0x18003995c  jnz     short loc_180039987
0x18003995e  call    cs:__imp_GetCurrentProcess
0x180039964  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180039969  mov     edx, esi; DesiredAccess
0x18003996b  mov     rcx, rax; ProcessHandle
0x18003996e  call    cs:__imp_OpenProcessToken
0x180039974  test    eax, eax
0x180039976  jnz     short loc_18003998B
0x180039978  call    cs:__imp_GetLastError
0x18003997e  test    eax, eax
0x180039980  jle     short loc_180039989
0x180039982  movzx   eax, ax
0x180039985  or      eax, ebx
0x180039987  test    eax, eax
0x180039989  js      short loc_1800399A6
0x18003998b  mov     rax, [rsp+38h+TokenHandle]
0x180039990  mov     rbx, [rsp+38h+arg_0]
0x180039995  mov     rsi, [rsp+38h+arg_8]
0x18003999a  mov     [rdi], rax
0x18003999d  mov     rax, rdi
0x1800399a0  add     rsp, 30h
0x1800399a4  pop     rdi
0x1800399a5  retn
0x1800399a6  mov     rcx, [rsp+38h]; this
0x1800399ab  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800399b2  mov     r9d, eax; char *
0x1800399b5  mov     edx, 0E1h; void *
0x1800399ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
