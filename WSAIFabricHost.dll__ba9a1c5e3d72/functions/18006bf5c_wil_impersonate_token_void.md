# wil::impersonate_token(void *)

- ea: `0x18006bf5c`
- end: `0x18006c092`
- name: `?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z`
- size: `310`
- prototype: `void **__fastcall(void **, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005517c`
- `0x180055220`

## callees

- `0x18000b044`
- `0x18000c008`
- `0x1800189b8`
- `0x18006bf5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bfb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bfb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c01d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c044`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c044`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006bf92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006bf92`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006bfa8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006bfa8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006bfcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006c02a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006bfcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006c02a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bffc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c03c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c05c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bffc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c03c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c05c`

## string_xrefs

- `0x18006bfda`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18006c080`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void **__fastcall wil::impersonate_token(void **a1, void *a2)
{
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  int LastError; // ebx
  void *v8; // rsi
  char *v9; // rcx
  void *v10; // rbx
  DWORD v11; // ebp
  wil::details::in1diag3 *v12; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  *a1 = (void *)-1LL;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v6 = 450;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v5);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    if ( LastError < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x208,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)(unsigned int)LastError,
        1);
    return a1;
  }
  if ( !SetThreadToken(0, a2) )
  {
    v6 = 454;
    goto LABEL_6;
  }
  v8 = TokenHandle;
  v9 = 0;
  TokenHandle = 0;
  v10 = *a1;
  if ( *a1 != (void *)-1LL )
  {
    v11 = GetLastError();
    if ( !SetThreadToken(0, v10) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
    if ( v10 )
      CloseHandle(v10);
    SetLastError(v11);
    v9 = (char *)TokenHandle;
  }
  *a1 = v8;
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  return a1;
}

```

## disassembly

```asm
0x18006bf5c  mov     rax, rsp
0x18006bf5f  mov     [rax+10h], rbx
0x18006bf63  mov     [rax+8], rcx
0x18006bf67  push    rbp
0x18006bf68  push    rsi
0x18006bf69  push    rdi
0x18006bf6a  sub     rsp, 30h
0x18006bf6e  mov     rbx, rdx
0x18006bf71  mov     rdi, rcx
0x18006bf74  mov     dword ptr [rax-28h], 0
0x18006bf7b  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18006bf82  mov     esi, 1
0x18006bf87  mov     [rax-28h], esi
0x18006bf8a  mov     qword ptr [rax+18h], 0
0x18006bf92  call    cs:__imp_GetCurrentThread
0x18006bf98  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18006bf9d  mov     r8d, esi; OpenAsSelf
0x18006bfa0  mov     edx, 0F01FFh; DesiredAccess
0x18006bfa5  mov     rcx, rax; ThreadHandle
0x18006bfa8  call    cs:__imp_OpenThreadToken
0x18006bfae  test    eax, eax
0x18006bfb0  jnz     short loc_18006BFC6
0x18006bfb2  call    cs:__imp_GetLastError
0x18006bfb8  cmp     eax, 3F0h
0x18006bfbd  jz      short loc_18006BFC6
0x18006bfbf  mov     edx, 1C2h
0x18006bfc4  jmp     short loc_18006BFDA
0x18006bfc6  mov     rdx, rbx; Token
0x18006bfc9  xor     ecx, ecx; Thread
0x18006bfcb  call    cs:__imp_SetThreadToken
0x18006bfd1  test    eax, eax
0x18006bfd3  jnz     short loc_18006C008
0x18006bfd5  mov     edx, 1C6h; void *
0x18006bfda  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006bfe1  mov     rcx, [rsp+48h]; this
0x18006bfe6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006bfeb  mov     ebx, eax
0x18006bfed  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18006bff2  lea     rax, [rcx-1]
0x18006bff6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006bffa  ja      short loc_18006C002
0x18006bffc  call    cs:__imp_CloseHandle
0x18006c002  test    ebx, ebx
0x18006c004  js      short loc_18006C078
0x18006c006  jmp     short loc_18006C062
0x18006c008  mov     rsi, [rsp+48h+TokenHandle]
0x18006c00d  xor     ecx, ecx
0x18006c00f  mov     [rsp+48h+TokenHandle], rcx
0x18006c014  mov     rbx, [rdi]
0x18006c017  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18006c01b  jz      short loc_18006C04F
0x18006c01d  call    cs:__imp_GetLastError
0x18006c023  mov     ebp, eax
0x18006c025  mov     rdx, rbx; Token
0x18006c028  xor     ecx, ecx; Thread
0x18006c02a  call    cs:__imp_SetThreadToken
0x18006c030  test    eax, eax
0x18006c032  jz      short loc_18006C072
0x18006c034  test    rbx, rbx
0x18006c037  jz      short loc_18006C042
0x18006c039  mov     rcx, rbx; hObject
0x18006c03c  call    cs:__imp_CloseHandle
0x18006c042  mov     ecx, ebp; dwErrCode
0x18006c044  call    cs:__imp_SetLastError
0x18006c04a  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18006c04f  mov     [rdi], rsi
0x18006c052  lea     rax, [rcx-1]
0x18006c056  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c05a  ja      short loc_18006C062
0x18006c05c  call    cs:__imp_CloseHandle
0x18006c062  mov     rax, rdi
0x18006c065  mov     rbx, [rsp+48h+arg_8]
0x18006c06a  add     rsp, 30h
0x18006c06e  pop     rdi
0x18006c06f  pop     rsi
0x18006c070  pop     rbp
0x18006c071  retn
0x18006c072  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18006c078  mov     rcx, [rsp+48h]; this
0x18006c07d  mov     r9d, ebx; char *
0x18006c080  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006c087  mov     edx, 208h; void *
0x18006c08c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
