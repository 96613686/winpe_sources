# wil::details::ReleaseMutex(void *)

- ea: `0x140006b74`
- end: `0x140006b9e`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400053dc`
- `0x1400078d8`

## callees

- `0x140006b74`
- `0x140007764`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006b78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006b78`

## string_xrefs

- `0x140006b87`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140006b74  sub     rsp, 28h
0x140006b78  call    cs:__imp_ReleaseMutex
0x140006b7e  test    eax, eax
0x140006b80  jnz     short loc_140006B99
0x140006b82  mov     rcx, [rsp+28h]; this
0x140006b87  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006b8e  mov     edx, 0A15h; void *
0x140006b93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006b99  add     rsp, 28h
0x140006b9d  retn
```
