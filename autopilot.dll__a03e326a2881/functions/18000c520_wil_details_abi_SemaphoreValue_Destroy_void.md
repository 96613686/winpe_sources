# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x18000c520`
- end: `0x18000c5ca`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fda8`
- `0x18000fed0`

## callees

- `0x18000c520`
- `0x180012114`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c53a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c53a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c567`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c551`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c57e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c551`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c545`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c545`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c572`

## string_xrefs

- `0x18000c5a1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c5b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(v6);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000c520  mov     [rsp+arg_0], rbx
0x18000c525  mov     [rsp+arg_8], rsi
0x18000c52a  push    rdi
0x18000c52b  sub     rsp, 20h
0x18000c52f  mov     rdi, [rcx]
0x18000c532  mov     rbx, rcx
0x18000c535  test    rdi, rdi
0x18000c538  jz      short loc_18000C557
0x18000c53a  call    cs:__imp_GetLastError
0x18000c540  mov     rcx, rdi; hObject
0x18000c543  mov     esi, eax
0x18000c545  call    cs:__imp_CloseHandle
0x18000c54b  test    eax, eax
0x18000c54d  jz      short loc_18000C5B3
0x18000c54f  mov     ecx, esi; dwErrCode
0x18000c551  call    cs:__imp_SetLastError
0x18000c557  mov     qword ptr [rbx], 0
0x18000c55e  mov     rdi, [rbx+8]
0x18000c562  test    rdi, rdi
0x18000c565  jz      short loc_18000C584
0x18000c567  call    cs:__imp_GetLastError
0x18000c56d  mov     rcx, rdi; hObject
0x18000c570  mov     esi, eax
0x18000c572  call    cs:__imp_CloseHandle
0x18000c578  test    eax, eax
0x18000c57a  jz      short loc_18000C59C
0x18000c57c  mov     ecx, esi; dwErrCode
0x18000c57e  call    cs:__imp_SetLastError
0x18000c584  mov     rsi, [rsp+28h+arg_8]
0x18000c589  mov     qword ptr [rbx+8], 0
0x18000c591  mov     rbx, [rsp+28h+arg_0]
0x18000c596  add     rsp, 20h
0x18000c59a  pop     rdi
0x18000c59b  retn
0x18000c59c  mov     rcx, [rsp+28h]; this
0x18000c5a1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c5a8  mov     edx, 0A0Bh; void *
0x18000c5ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c5b3  mov     rcx, [rsp+28h]; this
0x18000c5b8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c5bf  mov     edx, 0A0Bh; void *
0x18000c5c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
