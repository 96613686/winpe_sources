# wil::details::SetEvent(void *)

- ea: `0x18002733c`
- end: `0x18002736d`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025f90`

## callees

- `0x180009c88`
- `0x18002733c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027340`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027340`

## string_xrefs

- `0x180027355`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18002733c  sub     rsp, 28h
0x180027340  call    cs:__imp_SetEvent
0x180027347  nop     dword ptr [rax+rax+00h]
0x18002734c  test    eax, eax
0x18002734e  jnz     short loc_180027367
0x180027350  mov     rcx, [rsp+28h]; this
0x180027355  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002735c  mov     edx, 0A01h; void *
0x180027361  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180027367  add     rsp, 28h
0x18002736b  retn
```
