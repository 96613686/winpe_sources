# wil::details::ReleaseMutex(void *)

- ea: `0x180008df8`
- end: `0x180008e22`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046cc`
- `0x18000b3e0`

## callees

- `0x180008df8`
- `0x18000ae70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008dfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008dfc`

## string_xrefs

- `0x180008e0b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::ReleaseMutex(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ReleaseMutex(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x180008df8  sub     rsp, 28h
0x180008dfc  call    cs:__imp_ReleaseMutex
0x180008e02  test    eax, eax
0x180008e04  jnz     short loc_180008E1D
0x180008e06  mov     rcx, [rsp+28h]; this
0x180008e0b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008e12  mov     edx, 0A15h; void *
0x180008e17  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e1d  add     rsp, 28h
0x180008e21  retn
```
