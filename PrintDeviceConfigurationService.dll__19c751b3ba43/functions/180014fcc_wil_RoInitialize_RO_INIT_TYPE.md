# wil::RoInitialize(RO_INIT_TYPE)

- ea: `0x180014fcc`
- end: `0x18001500a`
- name: `?RoInitialize@wil@@YA?AV?$unique_call@P6AXXZ$1?RoUninitialize@@YAXXZ$00@1@W4RO_INIT_TYPE@@@Z`
- size: `62`
- prototype: `_BYTE *__fastcall(_BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015678`

## callees

- `0x18000dc94`
- `0x180014fcc`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180014fda`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180014fda`

## string_xrefs

- `0x180014fe9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_BYTE *__fastcall wil::RoInitialize(_BYTE *a1)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = RoInitialize(1);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14F2,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v4);
  *a1 = 1;
  return a1;
}

```

## disassembly

```asm
0x180014fcc  push    rbx
0x180014fce  sub     rsp, 30h
0x180014fd2  mov     rbx, rcx
0x180014fd5  mov     ecx, 1
0x180014fda  call    cs:__imp_RoInitialize
0x180014fe0  test    eax, eax
0x180014fe2  jns     short loc_180014FFE
0x180014fe4  mov     rcx, [rsp+38h]; this
0x180014fe9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014ff0  mov     r9d, eax; char *
0x180014ff3  mov     edx, 14F2h; void *
0x180014ff8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014ffe  mov     byte ptr [rbx], 1
0x180015001  mov     rax, rbx
0x180015004  add     rsp, 30h
0x180015008  pop     rbx
0x180015009  retn
```
