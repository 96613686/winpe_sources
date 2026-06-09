# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x180006878`
- end: `0x1800068da`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006208`
- `0x180006c68`
- `0x180007048`
- `0x18000a4b8`

## callees

- `0x180006878`
- `0x18000c268`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000688a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000689c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000688a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000689c`

## string_xrefs

- `0x1800068b1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800068c8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180006878  push    rbx
0x18000687a  sub     rsp, 20h
0x18000687e  mov     rbx, rcx
0x180006881  mov     rcx, [rcx+8]; hObject
0x180006885  test    rcx, rcx
0x180006888  jz      short loc_180006894
0x18000688a  call    cs:__imp_CloseHandle
0x180006890  test    eax, eax
0x180006892  jz      short loc_1800068C3
0x180006894  mov     rcx, [rbx]; hObject
0x180006897  test    rcx, rcx
0x18000689a  jz      short loc_1800068A6
0x18000689c  call    cs:__imp_CloseHandle
0x1800068a2  test    eax, eax
0x1800068a4  jz      short loc_1800068AC
0x1800068a6  add     rsp, 20h
0x1800068aa  pop     rbx
0x1800068ab  retn
0x1800068ac  mov     rcx, [rsp+28h]; this
0x1800068b1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800068b8  mov     edx, 0A0Bh; void *
0x1800068bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800068c3  mov     rcx, [rsp+28h]; this
0x1800068c8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800068cf  mov     edx, 0A0Bh; void *
0x1800068d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
