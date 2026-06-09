# wil::details::CloseHandle(void *)

- ea: `0x180005074`
- end: `0x1800050a5`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000473c`
- `0x18000a614`

## callees

- `0x180005074`
- `0x180009c88`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005078`

## string_xrefs

- `0x18000508d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::CloseHandle(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !CloseHandle(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x180005074  sub     rsp, 28h
0x180005078  call    cs:__imp_CloseHandle
0x18000507f  nop     dword ptr [rax+rax+00h]
0x180005084  test    eax, eax
0x180005086  jnz     short loc_18000509F
0x180005088  mov     rcx, [rsp+28h]; this
0x18000508d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005094  mov     edx, 0A0Bh; void *
0x180005099  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000509f  add     rsp, 28h
0x1800050a3  retn
```
