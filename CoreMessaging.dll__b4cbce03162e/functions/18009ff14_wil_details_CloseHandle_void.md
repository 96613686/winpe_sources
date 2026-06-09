# wil::details::CloseHandle(void *)

- ea: `0x18009ff14`
- end: `0x18009ff3e`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18009fc80`
- `0x1800a1bf4`

## callees

- `0x18009ff14`
- `0x1800a1ae8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff18`

## string_xrefs

- `0x18009ff27`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18009ff14  sub     rsp, 28h
0x18009ff18  call    cs:__imp_CloseHandle
0x18009ff1e  test    eax, eax
0x18009ff20  jnz     short loc_18009FF39
0x18009ff22  mov     rcx, [rsp+28h]; this
0x18009ff27  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009ff2e  mov     edx, 0A0Bh; void *
0x18009ff33  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18009ff39  add     rsp, 28h
0x18009ff3d  retn
```
