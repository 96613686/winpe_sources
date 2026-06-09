# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x18000b2f8`
- end: `0x18000b367`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b8cc`
- `0x18000bcd4`
- `0x18000fe78`
- `0x180010000`

## callees

- `0x18000b2f8`
- `0x180012220`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b30a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b30a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b322`

## string_xrefs

- `0x18000b33e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b355`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000b2f8  push    rbx
0x18000b2fa  sub     rsp, 20h
0x18000b2fe  mov     rbx, rcx
0x18000b301  mov     rcx, [rcx+8]; hObject
0x18000b305  test    rcx, rcx
0x18000b308  jz      short loc_18000B31A
0x18000b30a  call    cs:__imp_CloseHandle
0x18000b311  nop     dword ptr [rax+rax+00h]
0x18000b316  test    eax, eax
0x18000b318  jz      short loc_18000B350
0x18000b31a  mov     rcx, [rbx]; hObject
0x18000b31d  test    rcx, rcx
0x18000b320  jz      short loc_18000B332
0x18000b322  call    cs:__imp_CloseHandle
0x18000b329  nop     dword ptr [rax+rax+00h]
0x18000b32e  test    eax, eax
0x18000b330  jz      short loc_18000B339
0x18000b332  add     rsp, 20h
0x18000b336  pop     rbx
0x18000b337  retn
0x18000b339  mov     rcx, [rsp+28h]; this
0x18000b33e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b345  mov     edx, 0A0Bh; void *
0x18000b34a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b350  mov     rcx, [rsp+28h]; this
0x18000b355  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b35c  mov     edx, 0A0Bh; void *
0x18000b361  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
