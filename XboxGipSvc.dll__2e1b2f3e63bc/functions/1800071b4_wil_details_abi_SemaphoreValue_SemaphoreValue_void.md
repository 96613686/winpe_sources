# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1800071b4`
- end: `0x180007216`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007098`
- `0x1800073b8`

## callees

- `0x1800071b4`
- `0x180009260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071d8`

## string_xrefs

- `0x1800071ed`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007204`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800071b4  push    rbx
0x1800071b6  sub     rsp, 20h
0x1800071ba  mov     rbx, rcx
0x1800071bd  mov     rcx, [rcx+8]; hObject
0x1800071c1  test    rcx, rcx
0x1800071c4  jz      short loc_1800071D0
0x1800071c6  call    cs:__imp_CloseHandle
0x1800071cc  test    eax, eax
0x1800071ce  jz      short loc_1800071FF
0x1800071d0  mov     rcx, [rbx]; hObject
0x1800071d3  test    rcx, rcx
0x1800071d6  jz      short loc_1800071E2
0x1800071d8  call    cs:__imp_CloseHandle
0x1800071de  test    eax, eax
0x1800071e0  jz      short loc_1800071E8
0x1800071e2  add     rsp, 20h
0x1800071e6  pop     rbx
0x1800071e7  retn
0x1800071e8  mov     rcx, [rsp+28h]; this
0x1800071ed  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800071f4  mov     edx, 0A0Bh; void *
0x1800071f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071ff  mov     rcx, [rsp+28h]; this
0x180007204  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000720b  mov     edx, 0A0Bh; void *
0x180007210  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
