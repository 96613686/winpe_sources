# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x18000c554`
- end: `0x18000c623`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fe78`
- `0x180010000`

## callees

- `0x18000c554`
- `0x180012220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c57f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c57f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5be`

## string_xrefs

- `0x18000c5fa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c611`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::Destroy(wil::details_abi::SemaphoreValue *this)
{
  void *v1; // rdi
  DWORD LastError; // esi
  const char *v4; // r9
  void *v5; // rdi
  DWORD v6; // esi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    v6 = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(v6);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000c554  mov     [rsp+arg_0], rbx
0x18000c559  mov     [rsp+arg_8], rsi
0x18000c55e  push    rdi
0x18000c55f  sub     rsp, 20h
0x18000c563  mov     rdi, [rcx]
0x18000c566  mov     rbx, rcx
0x18000c569  test    rdi, rdi
0x18000c56c  jz      short loc_18000C59D
0x18000c56e  call    cs:__imp_GetLastError
0x18000c575  nop     dword ptr [rax+rax+00h]
0x18000c57a  mov     rcx, rdi; hObject
0x18000c57d  mov     esi, eax
0x18000c57f  call    cs:__imp_CloseHandle
0x18000c586  nop     dword ptr [rax+rax+00h]
0x18000c58b  test    eax, eax
0x18000c58d  jz      short loc_18000C60C
0x18000c58f  mov     ecx, esi; dwErrCode
0x18000c591  call    cs:__imp_SetLastError
0x18000c598  nop     dword ptr [rax+rax+00h]
0x18000c59d  mov     qword ptr [rbx], 0
0x18000c5a4  mov     rdi, [rbx+8]
0x18000c5a8  test    rdi, rdi
0x18000c5ab  jz      short loc_18000C5DC
0x18000c5ad  call    cs:__imp_GetLastError
0x18000c5b4  nop     dword ptr [rax+rax+00h]
0x18000c5b9  mov     rcx, rdi; hObject
0x18000c5bc  mov     esi, eax
0x18000c5be  call    cs:__imp_CloseHandle
0x18000c5c5  nop     dword ptr [rax+rax+00h]
0x18000c5ca  test    eax, eax
0x18000c5cc  jz      short loc_18000C5F5
0x18000c5ce  mov     ecx, esi; dwErrCode
0x18000c5d0  call    cs:__imp_SetLastError
0x18000c5d7  nop     dword ptr [rax+rax+00h]
0x18000c5dc  mov     rsi, [rsp+28h+arg_8]
0x18000c5e1  mov     qword ptr [rbx+8], 0
0x18000c5e9  mov     rbx, [rsp+28h+arg_0]
0x18000c5ee  add     rsp, 20h
0x18000c5f2  pop     rdi
0x18000c5f3  retn
0x18000c5f5  mov     rcx, [rsp+28h]; this
0x18000c5fa  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c601  mov     edx, 0A0Bh; void *
0x18000c606  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c60c  mov     rcx, [rsp+28h]; this
0x18000c611  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c618  mov     edx, 0A0Bh; void *
0x18000c61d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
