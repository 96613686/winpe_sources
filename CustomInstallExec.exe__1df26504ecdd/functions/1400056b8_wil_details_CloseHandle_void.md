# wil::details::CloseHandle(void *)

- ea: `0x1400056b8`
- end: `0x1400056e2`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400053c0`
- `0x140007884`
- `0x1400088ec`

## callees

- `0x1400056b8`
- `0x140007764`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400056bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400056bc`

## string_xrefs

- `0x1400056cb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1400056b8  sub     rsp, 28h
0x1400056bc  call    cs:__imp_CloseHandle
0x1400056c2  test    eax, eax
0x1400056c4  jnz     short loc_1400056DD
0x1400056c6  mov     rcx, [rsp+28h]; this
0x1400056cb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400056d2  mov     edx, 0A0Bh; void *
0x1400056d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400056dd  add     rsp, 28h
0x1400056e1  retn
```
