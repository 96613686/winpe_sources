# CMilBackChannel::WaitForSyncFlush(void)

- ea: `0x1800e45bc`
- end: `0x1800e4611`
- name: `?WaitForSyncFlush@CMilBackChannel@@QEAAJXZ`
- size: `85`
- prototype: `__int64 __fastcall(CMilBackChannel *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800e33d8`

## callees

- `0x1800802e8`
- `0x1800878c4`
- `0x1800e45bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e45ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e45ca`

## string_xrefs

- `0x1800e45e5`: `clientcore\windows\dwm\common\dwm\milbackchannel.cpp`
- `0x1800e45ff`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
DWORD __fastcall CMilBackChannel::WaitForSyncFlush(HANDLE *this)
{
  DWORD result; // eax
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = WaitForSingleObjectEx(this[3], 0xFFFFFFFF, 0);
  if ( result == 258 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x53,
             (unsigned int)"clientcore\\windows\\dwm\\common\\dwm\\milbackchannel.cpp",
             v2);
  if ( result )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
  return result;
}

```

## disassembly

```asm
0x1800e45bc  sub     rsp, 28h
0x1800e45c0  mov     rcx, [rcx+18h]; hHandle
0x1800e45c4  xor     r8d, r8d; bAlertable
0x1800e45c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800e45ca  call    cs:__imp_WaitForSingleObjectEx
0x1800e45d0  cmp     eax, 102h
0x1800e45d5  jz      short loc_1800E45E0
0x1800e45d7  test    eax, eax
0x1800e45d9  jnz     short loc_1800E45FA
0x1800e45db  add     rsp, 28h
0x1800e45df  retn
0x1800e45e0  mov     rcx, [rsp+28h]; this
0x1800e45e5  lea     r8, aClientcoreWind_53; "clientcore\\windows\\dwm\\common\\dwm\\"...
0x1800e45ec  mov     edx, 53h ; 'S'; void *
0x1800e45f1  add     rsp, 28h
0x1800e45f5  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e45fa  mov     rcx, [rsp+28h]; this
0x1800e45ff  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800e4606  mov     edx, 0B0Fh; void *
0x1800e460b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
