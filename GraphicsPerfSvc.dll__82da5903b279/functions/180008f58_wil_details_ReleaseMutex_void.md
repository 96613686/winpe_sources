# wil::details::ReleaseMutex(void *)

- ea: `0x180008f58`
- end: `0x180008f82`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d20`
- `0x18000ab1c`

## callees

- `0x180008f58`
- `0x18000a730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008f5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008f5c`

## string_xrefs

- `0x180008f6b`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
}

```

## disassembly

```asm
0x180008f58  sub     rsp, 28h
0x180008f5c  call    cs:__imp_ReleaseMutex
0x180008f62  test    eax, eax
0x180008f64  jnz     short loc_180008F7D
0x180008f66  mov     rcx, [rsp+28h]; this
0x180008f6b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008f72  mov     edx, 0A15h; void *
0x180008f77  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f7d  add     rsp, 28h
0x180008f81  retn
```
