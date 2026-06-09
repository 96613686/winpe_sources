# wil::details::ReleaseMutex(void *)

- ea: `0x1800082a0`
- end: `0x1800082d1`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000475c`
- `0x18000a668`

## callees

- `0x1800082a0`
- `0x180009c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800082a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800082a4`

## string_xrefs

- `0x1800082b9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800082a0  sub     rsp, 28h
0x1800082a4  call    cs:__imp_ReleaseMutex
0x1800082ab  nop     dword ptr [rax+rax+00h]
0x1800082b0  test    eax, eax
0x1800082b2  jnz     short loc_1800082CB
0x1800082b4  mov     rcx, [rsp+28h]; this
0x1800082b9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800082c0  mov     edx, 0A15h; void *
0x1800082c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800082cb  add     rsp, 28h
0x1800082cf  retn
```
