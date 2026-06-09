# wil::details::CloseHandle(void *)

- ea: `0x1800050b4`
- end: `0x1800050de`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046b0`
- `0x18000b38c`

## callees

- `0x1800050b4`
- `0x18000ae70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050b8`

## string_xrefs

- `0x1800050c7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800050b4  sub     rsp, 28h
0x1800050b8  call    cs:__imp_CloseHandle
0x1800050be  test    eax, eax
0x1800050c0  jnz     short loc_1800050D9
0x1800050c2  mov     rcx, [rsp+28h]; this
0x1800050c7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800050ce  mov     edx, 0A0Bh; void *
0x1800050d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050d9  add     rsp, 28h
0x1800050dd  retn
```
