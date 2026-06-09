# wil::details::ReleaseMutex(void *)

- ea: `0x180007afc`
- end: `0x180007b26`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d1c`
- `0x180009410`

## callees

- `0x180007afc`
- `0x180008a54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b00`

## string_xrefs

- `0x180007b0f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180007afc  sub     rsp, 28h
0x180007b00  call    cs:__imp_ReleaseMutex
0x180007b06  test    eax, eax
0x180007b08  jnz     short loc_180007B21
0x180007b0a  mov     rcx, [rsp+28h]; this
0x180007b0f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007b16  mov     edx, 0A15h; void *
0x180007b1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b21  add     rsp, 28h
0x180007b25  retn
```
