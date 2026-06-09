# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x18000494c`
- end: `0x1800049ae`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004830`
- `0x180004ba8`
- `0x180008b94`
- `0x18000a898`

## callees

- `0x18000494c`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000495e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004970`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000495e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004970`

## string_xrefs

- `0x180004985`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000499c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000494c  push    rbx
0x18000494e  sub     rsp, 20h
0x180004952  mov     rbx, rcx
0x180004955  mov     rcx, [rcx+8]; hObject
0x180004959  test    rcx, rcx
0x18000495c  jz      short loc_180004968
0x18000495e  call    cs:__imp_CloseHandle
0x180004964  test    eax, eax
0x180004966  jz      short loc_180004997
0x180004968  mov     rcx, [rbx]; hObject
0x18000496b  test    rcx, rcx
0x18000496e  jz      short loc_18000497A
0x180004970  call    cs:__imp_CloseHandle
0x180004976  test    eax, eax
0x180004978  jz      short loc_180004980
0x18000497a  add     rsp, 20h
0x18000497e  pop     rbx
0x18000497f  retn
0x180004980  mov     rcx, [rsp+28h]; this
0x180004985  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000498c  mov     edx, 0A0Bh; void *
0x180004991  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004997  mov     rcx, [rsp+28h]; this
0x18000499c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800049a3  mov     edx, 0A0Bh; void *
0x1800049a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
