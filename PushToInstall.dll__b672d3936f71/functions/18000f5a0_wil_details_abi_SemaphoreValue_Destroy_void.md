# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x18000f5a0`
- end: `0x18000f64a`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800108dc`
- `0x180014a78`

## callees

- `0x18000f5a0`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f5fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5f2`

## string_xrefs

- `0x18000f621`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f638`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000f5a0  mov     [rsp+arg_0], rbx
0x18000f5a5  mov     [rsp+arg_8], rsi
0x18000f5aa  push    rdi
0x18000f5ab  sub     rsp, 20h
0x18000f5af  mov     rdi, [rcx]
0x18000f5b2  mov     rbx, rcx
0x18000f5b5  test    rdi, rdi
0x18000f5b8  jz      short loc_18000F5D7
0x18000f5ba  call    cs:__imp_GetLastError
0x18000f5c0  mov     rcx, rdi; hObject
0x18000f5c3  mov     esi, eax
0x18000f5c5  call    cs:__imp_CloseHandle
0x18000f5cb  test    eax, eax
0x18000f5cd  jz      short loc_18000F633
0x18000f5cf  mov     ecx, esi; dwErrCode
0x18000f5d1  call    cs:__imp_SetLastError
0x18000f5d7  mov     qword ptr [rbx], 0
0x18000f5de  mov     rdi, [rbx+8]
0x18000f5e2  test    rdi, rdi
0x18000f5e5  jz      short loc_18000F604
0x18000f5e7  call    cs:__imp_GetLastError
0x18000f5ed  mov     rcx, rdi; hObject
0x18000f5f0  mov     esi, eax
0x18000f5f2  call    cs:__imp_CloseHandle
0x18000f5f8  test    eax, eax
0x18000f5fa  jz      short loc_18000F61C
0x18000f5fc  mov     ecx, esi; dwErrCode
0x18000f5fe  call    cs:__imp_SetLastError
0x18000f604  mov     rsi, [rsp+28h+arg_8]
0x18000f609  mov     qword ptr [rbx+8], 0
0x18000f611  mov     rbx, [rsp+28h+arg_0]
0x18000f616  add     rsp, 20h
0x18000f61a  pop     rdi
0x18000f61b  retn
0x18000f61c  mov     rcx, [rsp+28h]; this
0x18000f621  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f628  mov     edx, 0A0Bh; void *
0x18000f62d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f633  mov     rcx, [rsp+28h]; this
0x18000f638  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f63f  mov     edx, 0A0Bh; void *
0x18000f644  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
