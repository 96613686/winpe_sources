# wil::details::SetEvent(void *)

- ea: `0x180026044`
- end: `0x18002606e`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026074`

## callees

- `0x18000a730`
- `0x180026044`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026048`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026048`

## string_xrefs

- `0x180026057`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180026044  sub     rsp, 28h
0x180026048  call    cs:__imp_SetEvent
0x18002604e  test    eax, eax
0x180026050  jnz     short loc_180026069
0x180026052  mov     rcx, [rsp+28h]; this
0x180026057  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002605e  mov     edx, 0A01h; void *
0x180026063  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180026069  add     rsp, 28h
0x18002606d  retn
```
