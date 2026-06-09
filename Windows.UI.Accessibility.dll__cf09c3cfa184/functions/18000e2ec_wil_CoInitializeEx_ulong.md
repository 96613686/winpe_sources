# wil::CoInitializeEx(ulong)

- ea: `0x18000e2ec`
- end: `0x18000e32c`
- name: `?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e340`
- `0x18002a010`

## callees

- `0x18000cf94`
- `0x18000e2ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e2fc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e2fc`

## string_xrefs

- `0x18000e30b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_BYTE *__fastcall wil::CoInitializeEx(_BYTE *a1)
{
  HRESULT v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = CoInitializeEx(0, 2u);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v4);
  *a1 = 1;
  return a1;
}

```

## disassembly

```asm
0x18000e2ec  push    rbx
0x18000e2ee  sub     rsp, 30h
0x18000e2f2  mov     rbx, rcx
0x18000e2f5  mov     edx, 2; dwCoInit
0x18000e2fa  xor     ecx, ecx; pvReserved
0x18000e2fc  call    cs:__imp_CoInitializeEx
0x18000e302  test    eax, eax
0x18000e304  jns     short loc_18000E320
0x18000e306  mov     rcx, [rsp+38h]; this
0x18000e30b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e312  mov     r9d, eax; char *
0x18000e315  mov     edx, 14D3h; void *
0x18000e31a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e320  mov     byte ptr [rbx], 1
0x18000e323  mov     rax, rbx
0x18000e326  add     rsp, 30h
0x18000e32a  pop     rbx
0x18000e32b  retn
```
