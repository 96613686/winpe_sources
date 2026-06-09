# wil::details::SetEvent(void *)

- ea: `0x18000e940`
- end: `0x18000e96a`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fad0`
- `0x1800110b0`
- `0x18001c010`

## callees

- `0x180008a54`
- `0x18000e940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e944`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e944`

## string_xrefs

- `0x18000e953`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
0x18000e940  sub     rsp, 28h
0x18000e944  call    cs:__imp_SetEvent
0x18000e94a  test    eax, eax
0x18000e94c  jnz     short loc_18000E965
0x18000e94e  mov     rcx, [rsp+28h]; this
0x18000e953  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e95a  mov     edx, 0A01h; void *
0x18000e95f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e965  add     rsp, 28h
0x18000e969  retn
```
