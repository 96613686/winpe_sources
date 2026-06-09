# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180004ab8`
- end: `0x180004b1a`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004450`
- `0x180004e58`
- `0x18000522c`
- `0x1800088c0`

## callees

- `0x180004ab8`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004aca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004adc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004aca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004adc`

## string_xrefs

- `0x180004af1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004b08`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004ab8  push    rbx
0x180004aba  sub     rsp, 20h
0x180004abe  mov     rbx, rcx
0x180004ac1  mov     rcx, [rcx+8]; hObject
0x180004ac5  test    rcx, rcx
0x180004ac8  jz      short loc_180004AD4
0x180004aca  call    cs:__imp_CloseHandle
0x180004ad0  test    eax, eax
0x180004ad2  jz      short loc_180004B03
0x180004ad4  mov     rcx, [rbx]; hObject
0x180004ad7  test    rcx, rcx
0x180004ada  jz      short loc_180004AE6
0x180004adc  call    cs:__imp_CloseHandle
0x180004ae2  test    eax, eax
0x180004ae4  jz      short loc_180004AEC
0x180004ae6  add     rsp, 20h
0x180004aea  pop     rbx
0x180004aeb  retn
0x180004aec  mov     rcx, [rsp+28h]; this
0x180004af1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004af8  mov     edx, 0A0Bh; void *
0x180004afd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b03  mov     rcx, [rsp+28h]; this
0x180004b08  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004b0f  mov     edx, 0A0Bh; void *
0x180004b14  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
