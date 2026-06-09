# wil::details::CloseHandle(void *)

- ea: `0x18000bd88`
- end: `0x18000bdb2`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5ac`
- `0x1800103c8`

## callees

- `0x18000bd88`
- `0x180010020`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd8c`

## string_xrefs

- `0x18000bd9b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000bd88  sub     rsp, 28h
0x18000bd8c  call    cs:__imp_CloseHandle
0x18000bd92  test    eax, eax
0x18000bd94  jnz     short loc_18000BDAD
0x18000bd96  mov     rcx, [rsp+28h]; this
0x18000bd9b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bda2  mov     edx, 0A0Bh; void *
0x18000bda7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bdad  add     rsp, 28h
0x18000bdb1  retn
```
