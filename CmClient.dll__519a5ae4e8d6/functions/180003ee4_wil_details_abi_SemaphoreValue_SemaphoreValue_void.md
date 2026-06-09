# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180003ee4`
- end: `0x180003f46`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d24`
- `0x180003fd0`

## callees

- `0x180003ee4`
- `0x18000700c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f08`

## string_xrefs

- `0x180003f1d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180003f34`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003ee4  push    rbx
0x180003ee6  sub     rsp, 20h
0x180003eea  mov     rbx, rcx
0x180003eed  mov     rcx, [rcx+8]; hObject
0x180003ef1  test    rcx, rcx
0x180003ef4  jz      short loc_180003F00
0x180003ef6  call    cs:__imp_CloseHandle
0x180003efc  test    eax, eax
0x180003efe  jz      short loc_180003F2F
0x180003f00  mov     rcx, [rbx]; hObject
0x180003f03  test    rcx, rcx
0x180003f06  jz      short loc_180003F12
0x180003f08  call    cs:__imp_CloseHandle
0x180003f0e  test    eax, eax
0x180003f10  jz      short loc_180003F18
0x180003f12  add     rsp, 20h
0x180003f16  pop     rbx
0x180003f17  retn
0x180003f18  mov     rcx, [rsp+28h]; this
0x180003f1d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003f24  mov     edx, 0A0Bh; void *
0x180003f29  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f2f  mov     rcx, [rsp+28h]; this
0x180003f34  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003f3b  mov     edx, 0A0Bh; void *
0x180003f40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
