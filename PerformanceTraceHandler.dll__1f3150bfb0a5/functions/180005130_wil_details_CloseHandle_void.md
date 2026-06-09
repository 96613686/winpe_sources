# wil::details::CloseHandle(void *)

- ea: `0x180005130`
- end: `0x18000515a`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049b0`
- `0x180009aa0`

## callees

- `0x180005130`
- `0x1800093a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005134`

## string_xrefs

- `0x180005143`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180005130  sub     rsp, 28h
0x180005134  call    cs:__imp_CloseHandle
0x18000513a  test    eax, eax
0x18000513c  jnz     short loc_180005155
0x18000513e  mov     rcx, [rsp+28h]; this
0x180005143  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000514a  mov     edx, 0A0Bh; void *
0x18000514f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005155  add     rsp, 28h
0x180005159  retn
```
