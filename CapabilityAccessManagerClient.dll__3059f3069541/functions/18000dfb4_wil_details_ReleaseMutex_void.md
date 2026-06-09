# wil::details::ReleaseMutex(void *)

- ea: `0x18000dfb4`
- end: `0x18000dfde`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa98`
- `0x18000fdf4`

## callees

- `0x18000dfb4`
- `0x18000f97c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000dfb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000dfb8`

## string_xrefs

- `0x18000dfc7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000dfb4  sub     rsp, 28h
0x18000dfb8  call    cs:__imp_ReleaseMutex
0x18000dfbe  test    eax, eax
0x18000dfc0  jnz     short loc_18000DFD9
0x18000dfc2  mov     rcx, [rsp+28h]; this
0x18000dfc7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dfce  mov     edx, 0A15h; void *
0x18000dfd3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dfd9  add     rsp, 28h
0x18000dfdd  retn
```
