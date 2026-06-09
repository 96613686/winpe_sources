# wil::details::CloseHandle(void *)

- ea: `0x180006470`
- end: `0x18000649a`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d04`
- `0x18000aac8`

## callees

- `0x180006470`
- `0x18000a730`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006474`

## string_xrefs

- `0x180006483`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
}

```

## disassembly

```asm
0x180006470  sub     rsp, 28h
0x180006474  call    cs:__imp_CloseHandle
0x18000647a  test    eax, eax
0x18000647c  jnz     short loc_180006495
0x18000647e  mov     rcx, [rsp+28h]; this
0x180006483  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000648a  mov     edx, 0A0Bh; void *
0x18000648f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006495  add     rsp, 28h
0x180006499  retn
```
