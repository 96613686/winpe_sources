# wil::details::CloseHandle(void *)

- ea: `0x18000b270`
- end: `0x18000b29a`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa7c`
- `0x18000fda0`

## callees

- `0x18000b270`
- `0x18000f97c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b274`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b274`

## string_xrefs

- `0x18000b283`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000b270  sub     rsp, 28h
0x18000b274  call    cs:__imp_CloseHandle
0x18000b27a  test    eax, eax
0x18000b27c  jnz     short loc_18000B295
0x18000b27e  mov     rcx, [rsp+28h]; this
0x18000b283  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b28a  mov     edx, 0A0Bh; void *
0x18000b28f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b295  add     rsp, 28h
0x18000b299  retn
```
