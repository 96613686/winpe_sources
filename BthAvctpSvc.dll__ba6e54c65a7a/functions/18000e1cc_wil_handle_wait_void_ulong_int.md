# wil::handle_wait(void *,ulong,int)

- ea: `0x18000e1cc`
- end: `0x18000e208`
- name: `?handle_wait@wil@@YA_NPEAXKH@Z`
- size: `60`
- prototype: `bool __fastcall(wil *__hidden this, void *, unsigned int, int)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c020`
- `0x18000dd7c`
- `0x180010bc0`
- `0x180011700`
- `0x1800265a0`
- `0x1800412d8`
- `0x1800542d0`
- `0x1800547d0`
- `0x180054810`

## callees

- `0x180004bd8`
- `0x18000e1cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e1d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e1d6`

## string_xrefs

- `0x18000e1ec`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
bool __fastcall wil::handle_wait(wil *this, void *a2)
{
  DWORD v2; // eax
  const char *v3; // r9
  bool v4; // zf
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = WaitForSingleObjectEx(this, 0xFFFFFFFF, 0);
  if ( v2 == 258 )
    return 0;
  v4 = v2 == 0;
  if ( v2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v3);
  return v4;
}

```

## disassembly

```asm
0x18000e1cc  sub     rsp, 28h
0x18000e1d0  xor     r8d, r8d; bAlertable
0x18000e1d3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000e1d6  call    cs:__imp_WaitForSingleObjectEx
0x18000e1dc  cmp     eax, 102h
0x18000e1e1  jz      short loc_18000E1FE
0x18000e1e3  test    eax, eax
0x18000e1e5  jz      short loc_18000E200
0x18000e1e7  mov     rcx, [rsp+28h]; this
0x18000e1ec  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e1f3  mov     edx, 0B0Fh; void *
0x18000e1f8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000e1fe  test    eax, eax
0x18000e200  setz    al
0x18000e203  add     rsp, 28h
0x18000e207  retn
```
