# wil::details::SetEvent(void *)

- ea: `0x18001bab8`
- end: `0x18001bae2`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180013400`
- `0x180018b80`

## callees

- `0x18000ae70`
- `0x18001bab8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001babc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001babc`

## string_xrefs

- `0x18001bacb`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
}

```

## disassembly

```asm
0x18001bab8  sub     rsp, 28h
0x18001babc  call    cs:__imp_SetEvent
0x18001bac2  test    eax, eax
0x18001bac4  jnz     short loc_18001BADD
0x18001bac6  mov     rcx, [rsp+28h]; this
0x18001bacb  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001bad2  mov     edx, 0A01h; void *
0x18001bad7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001badd  add     rsp, 28h
0x18001bae1  retn
```
