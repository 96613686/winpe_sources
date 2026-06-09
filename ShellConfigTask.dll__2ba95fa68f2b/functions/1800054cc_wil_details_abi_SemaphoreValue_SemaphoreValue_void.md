# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1800054cc`
- end: `0x18000552e`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e54`
- `0x180005a58`
- `0x180005e38`
- `0x18000a118`

## callees

- `0x1800054cc`
- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054f0`

## string_xrefs

- `0x180005505`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000551c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800054cc  push    rbx
0x1800054ce  sub     rsp, 20h
0x1800054d2  mov     rbx, rcx
0x1800054d5  mov     rcx, [rcx+8]; hObject
0x1800054d9  test    rcx, rcx
0x1800054dc  jz      short loc_1800054E8
0x1800054de  call    cs:__imp_CloseHandle
0x1800054e4  test    eax, eax
0x1800054e6  jz      short loc_180005517
0x1800054e8  mov     rcx, [rbx]; hObject
0x1800054eb  test    rcx, rcx
0x1800054ee  jz      short loc_1800054FA
0x1800054f0  call    cs:__imp_CloseHandle
0x1800054f6  test    eax, eax
0x1800054f8  jz      short loc_180005500
0x1800054fa  add     rsp, 20h
0x1800054fe  pop     rbx
0x1800054ff  retn
0x180005500  mov     rcx, [rsp+28h]; this
0x180005505  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000550c  mov     edx, 0A0Bh; void *
0x180005511  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005517  mov     rcx, [rsp+28h]; this
0x18000551c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005523  mov     edx, 0A0Bh; void *
0x180005528  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
