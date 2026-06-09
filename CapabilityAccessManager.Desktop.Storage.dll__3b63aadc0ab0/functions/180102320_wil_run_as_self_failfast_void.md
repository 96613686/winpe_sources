# wil::run_as_self_failfast(void)

- ea: `0x180102320`
- end: `0x18010243a`
- name: `?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ`
- size: `282`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180103f28`
- `0x180106144`
- `0x180107620`
- `0x180107720`
- `0x1801077b0`
- `0x180107830`
- `0x1801079e0`

## callees

- `0x1800eabd4`
- `0x1800ec608`
- `0x1800edb2c`
- `0x180102320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801023f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801023f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010235f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801023c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010235f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801023c9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180102377`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801023d6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180102377`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801023d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102355`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010233c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010233c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801023a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801023e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801023a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801023e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102408`

## string_xrefs

- `0x180102386`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180102428`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall wil::run_as_self_failfast(void **a1)
{
  HANDLE CurrentThread; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // ebx
  void *v6; // rsi
  char *v7; // rcx
  void *v8; // rbx
  DWORD v9; // ebp
  wil::details::in1diag3 *v10; // rcx
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF

  *a1 = (void *)-1LL;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v4 = 450;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v3);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    if ( LastError < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)(unsigned int)LastError,
        v12);
    return a1;
  }
  if ( !SetThreadToken(0, 0) )
  {
    v4 = 454;
    goto LABEL_6;
  }
  v6 = TokenHandle;
  v7 = 0;
  TokenHandle = 0;
  v8 = *a1;
  if ( *a1 != (void *)-1LL )
  {
    v9 = GetLastError();
    if ( !SetThreadToken(0, v8) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v10);
    if ( v8 )
      CloseHandle(v8);
    SetLastError(v9);
    v7 = (char *)TokenHandle;
  }
  *a1 = v6;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return a1;
}

```

## disassembly

```asm
0x180102320  push    rbx
0x180102322  push    rbp
0x180102323  push    rsi
0x180102324  push    rdi
0x180102325  sub     rsp, 28h
0x180102329  mov     rdi, rcx
0x18010232c  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180102333  mov     [rsp+48h+TokenHandle], 0
0x18010233c  call    cs:__imp_GetCurrentThread
0x180102342  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180102347  mov     edx, 0F01FFh; DesiredAccess
0x18010234c  mov     r8d, 1; OpenAsSelf
0x180102352  mov     rcx, rax; ThreadHandle
0x180102355  call    cs:__imp_OpenThreadToken
0x18010235b  test    eax, eax
0x18010235d  jnz     short loc_180102373
0x18010235f  call    cs:__imp_GetLastError
0x180102365  cmp     eax, 3F0h
0x18010236a  jz      short loc_180102373
0x18010236c  mov     edx, 1C2h
0x180102371  jmp     short loc_180102386
0x180102373  xor     edx, edx; Token
0x180102375  xor     ecx, ecx; Thread
0x180102377  call    cs:__imp_SetThreadToken
0x18010237d  test    eax, eax
0x18010237f  jnz     short loc_1801023B4
0x180102381  mov     edx, 1C6h; void *
0x180102386  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18010238d  mov     rcx, [rsp+48h]; this
0x180102392  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180102397  mov     ebx, eax
0x180102399  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18010239e  lea     rax, [rcx-1]
0x1801023a2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801023a6  ja      short loc_1801023AE
0x1801023a8  call    cs:__imp_CloseHandle
0x1801023ae  test    ebx, ebx
0x1801023b0  js      short loc_180102420
0x1801023b2  jmp     short loc_18010240E
0x1801023b4  mov     rsi, [rsp+48h+TokenHandle]
0x1801023b9  xor     ecx, ecx
0x1801023bb  mov     [rsp+48h+TokenHandle], rcx
0x1801023c0  mov     rbx, [rdi]
0x1801023c3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801023c7  jz      short loc_1801023FB
0x1801023c9  call    cs:__imp_GetLastError
0x1801023cf  mov     ebp, eax
0x1801023d1  mov     rdx, rbx; Token
0x1801023d4  xor     ecx, ecx; Thread
0x1801023d6  call    cs:__imp_SetThreadToken
0x1801023dc  test    eax, eax
0x1801023de  jz      short loc_18010241A
0x1801023e0  test    rbx, rbx
0x1801023e3  jz      short loc_1801023EE
0x1801023e5  mov     rcx, rbx; hObject
0x1801023e8  call    cs:__imp_CloseHandle
0x1801023ee  mov     ecx, ebp; dwErrCode
0x1801023f0  call    cs:__imp_SetLastError
0x1801023f6  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1801023fb  mov     [rdi], rsi
0x1801023fe  lea     rax, [rcx-1]
0x180102402  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180102406  ja      short loc_18010240E
0x180102408  call    cs:__imp_CloseHandle
0x18010240e  mov     rax, rdi
0x180102411  add     rsp, 28h
0x180102415  pop     rdi
0x180102416  pop     rsi
0x180102417  pop     rbp
0x180102418  pop     rbx
0x180102419  retn
0x18010241a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180102420  mov     rcx, [rsp+48h]; this
0x180102425  mov     r9d, ebx; char *
0x180102428  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18010242f  mov     edx, 1E8h; void *
0x180102434  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
