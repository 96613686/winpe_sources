# wil::details::CloseHandle(void *)

- ea: `0x140002b90`
- end: `0x140002bba`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002974`
- `0x140004b0c`

## callees

- `0x140002b90`
- `0x140004a10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b94`

## string_xrefs

- `0x140002ba3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x140002b90  sub     rsp, 28h
0x140002b94  call    cs:__imp_CloseHandle
0x140002b9a  test    eax, eax
0x140002b9c  jnz     short loc_140002BB5
0x140002b9e  mov     rcx, [rsp+28h]; this
0x140002ba3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002baa  mov     edx, 0A0Bh; void *
0x140002baf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002bb5  add     rsp, 28h
0x140002bb9  retn
```
