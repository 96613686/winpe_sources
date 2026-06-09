# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x18000ed60`
- end: `0x18000edc2`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ec44`
- `0x18000ef68`
- `0x180012814`
- `0x180014a78`

## callees

- `0x18000ed60`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed84`

## string_xrefs

- `0x18000ed99`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000edb0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  const char *v3; // r9
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
  }
}

```

## disassembly

```asm
0x18000ed60  push    rbx
0x18000ed62  sub     rsp, 20h
0x18000ed66  mov     rbx, rcx
0x18000ed69  mov     rcx, [rcx+8]; hObject
0x18000ed6d  test    rcx, rcx
0x18000ed70  jz      short loc_18000ED7C
0x18000ed72  call    cs:__imp_CloseHandle
0x18000ed78  test    eax, eax
0x18000ed7a  jz      short loc_18000EDAB
0x18000ed7c  mov     rcx, [rbx]; hObject
0x18000ed7f  test    rcx, rcx
0x18000ed82  jz      short loc_18000ED8E
0x18000ed84  call    cs:__imp_CloseHandle
0x18000ed8a  test    eax, eax
0x18000ed8c  jz      short loc_18000ED94
0x18000ed8e  add     rsp, 20h
0x18000ed92  pop     rbx
0x18000ed93  retn
0x18000ed94  mov     rcx, [rsp+28h]; this
0x18000ed99  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000eda0  mov     edx, 0A0Bh; void *
0x18000eda5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000edab  mov     rcx, [rsp+28h]; this
0x18000edb0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000edb7  mov     edx, 0A0Bh; void *
0x18000edbc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
