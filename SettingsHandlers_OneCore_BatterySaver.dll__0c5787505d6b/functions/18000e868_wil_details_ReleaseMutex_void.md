# wil::details::ReleaseMutex(void *)

- ea: `0x18000e868`
- end: `0x18000e892`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5c8`
- `0x18001041c`

## callees

- `0x18000e868`
- `0x180010020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e86c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e86c`

## string_xrefs

- `0x18000e87b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000e868  sub     rsp, 28h
0x18000e86c  call    cs:__imp_ReleaseMutex
0x18000e872  test    eax, eax
0x18000e874  jnz     short loc_18000E88D
0x18000e876  mov     rcx, [rsp+28h]; this
0x18000e87b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e882  mov     edx, 0A15h; void *
0x18000e887  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e88d  add     rsp, 28h
0x18000e891  retn
```
