# wil::details::ReleaseMutex(void *)

- ea: `0x180007254`
- end: `0x18000727e`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000535c`
- `0x180008510`

## callees

- `0x180007254`
- `0x1800082e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007258`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007258`

## string_xrefs

- `0x180007267`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180007254  sub     rsp, 28h
0x180007258  call    cs:__imp_ReleaseMutex
0x18000725e  test    eax, eax
0x180007260  jnz     short loc_180007279
0x180007262  mov     rcx, [rsp+28h]; this
0x180007267  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000726e  mov     edx, 0A15h; void *
0x180007273  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007279  add     rsp, 28h
0x18000727d  retn
```
