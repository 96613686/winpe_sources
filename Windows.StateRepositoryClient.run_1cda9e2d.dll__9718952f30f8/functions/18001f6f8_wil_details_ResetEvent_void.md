# wil::details::ResetEvent(void *)

- ea: `0x18001f6f8`
- end: `0x18001f722`
- name: `?ResetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020080`

## callees

- `0x1800082e4`
- `0x18001f6f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f6fc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f6fc`

## string_xrefs

- `0x18001f70b`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall wil::details::ResetEvent(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ResetEvent(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA06,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
}

```

## disassembly

```asm
0x18001f6f8  sub     rsp, 28h
0x18001f6fc  call    cs:__imp_ResetEvent
0x18001f702  test    eax, eax
0x18001f704  jnz     short loc_18001F71D
0x18001f706  mov     rcx, [rsp+28h]; this
0x18001f70b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f712  mov     edx, 0A06h; void *
0x18001f717  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f71d  add     rsp, 28h
0x18001f721  retn
```
