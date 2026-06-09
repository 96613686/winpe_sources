# wil::details::ReleaseMutex(void *)

- ea: `0x140004060`
- end: `0x14000408a`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002990`
- `0x140003f8c`

## callees

- `0x140004060`
- `0x140004a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004064`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004064`

## string_xrefs

- `0x140004073`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x140004060  sub     rsp, 28h
0x140004064  call    cs:__imp_ReleaseMutex
0x14000406a  test    eax, eax
0x14000406c  jnz     short loc_140004085
0x14000406e  mov     rcx, [rsp+28h]; this
0x140004073  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000407a  mov     edx, 0A15h; void *
0x14000407f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004085  add     rsp, 28h
0x140004089  retn
```
