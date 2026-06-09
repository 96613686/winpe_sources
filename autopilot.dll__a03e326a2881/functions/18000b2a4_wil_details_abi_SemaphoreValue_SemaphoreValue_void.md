# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x18000b2a4`
- end: `0x18000b306`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac1c`
- `0x18000b848`
- `0x18000bc20`
- `0x18000fed0`

## callees

- `0x18000b2a4`
- `0x180012114`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2c8`

## string_xrefs

- `0x18000b2dd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b2f4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000b2a4  push    rbx
0x18000b2a6  sub     rsp, 20h
0x18000b2aa  mov     rbx, rcx
0x18000b2ad  mov     rcx, [rcx+8]; hObject
0x18000b2b1  test    rcx, rcx
0x18000b2b4  jz      short loc_18000B2C0
0x18000b2b6  call    cs:__imp_CloseHandle
0x18000b2bc  test    eax, eax
0x18000b2be  jz      short loc_18000B2EF
0x18000b2c0  mov     rcx, [rbx]; hObject
0x18000b2c3  test    rcx, rcx
0x18000b2c6  jz      short loc_18000B2D2
0x18000b2c8  call    cs:__imp_CloseHandle
0x18000b2ce  test    eax, eax
0x18000b2d0  jz      short loc_18000B2D8
0x18000b2d2  add     rsp, 20h
0x18000b2d6  pop     rbx
0x18000b2d7  retn
0x18000b2d8  mov     rcx, [rsp+28h]; this
0x18000b2dd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b2e4  mov     edx, 0A0Bh; void *
0x18000b2e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2ef  mov     rcx, [rsp+28h]; this
0x18000b2f4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b2fb  mov     edx, 0A0Bh; void *
0x18000b300  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
