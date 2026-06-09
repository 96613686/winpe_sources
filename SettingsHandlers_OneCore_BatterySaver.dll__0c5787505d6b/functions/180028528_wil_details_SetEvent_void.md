# wil::details::SetEvent(void *)

- ea: `0x180028528`
- end: `0x180028552`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023f90`

## callees

- `0x180010020`
- `0x180028528`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002852c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002852c`

## string_xrefs

- `0x18002853b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::SetEvent(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !SetEvent(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x180028528  sub     rsp, 28h
0x18002852c  call    cs:__imp_SetEvent
0x180028532  test    eax, eax
0x180028534  jnz     short loc_18002854D
0x180028536  mov     rcx, [rsp+28h]; this
0x18002853b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028542  mov     edx, 0A01h; void *
0x180028547  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002854d  add     rsp, 28h
0x180028551  retn
```
