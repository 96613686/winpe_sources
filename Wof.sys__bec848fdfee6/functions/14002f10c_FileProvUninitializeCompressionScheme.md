# FileProvUninitializeCompressionScheme

- ea: `0x14002f10c`
- end: `0x14002f17e`
- name: `FileProvUninitializeCompressionScheme`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ece0`

## callees

- `0x14002f10c`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f158`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f16b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f158`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002f16b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f11f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f132`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f145`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f11f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f132`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002f145`

## pseudocode

```c
void __fastcall FileProvUninitializeCompressionScheme(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 16) )
  {
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 64));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 192));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 384));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 512));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 640));
  }
}

```

## disassembly

```asm
0x14002f10c  push    rbx
0x14002f10e  sub     rsp, 20h
0x14002f112  cmp     byte ptr [rcx+10h], 0
0x14002f116  mov     rbx, rcx
0x14002f119  jz      short loc_14002F177
0x14002f11b  add     rcx, 40h ; '@'; Lookaside
0x14002f11f  call    cs:__imp_ExDeletePagedLookasideList
0x14002f126  nop     dword ptr [rax+rax+00h]
0x14002f12b  lea     rcx, [rbx+0C0h]; Lookaside
0x14002f132  call    cs:__imp_ExDeletePagedLookasideList
0x14002f139  nop     dword ptr [rax+rax+00h]
0x14002f13e  lea     rcx, [rbx+180h]; Lookaside
0x14002f145  call    cs:__imp_ExDeletePagedLookasideList
0x14002f14c  nop     dword ptr [rax+rax+00h]
0x14002f151  lea     rcx, [rbx+200h]; Lookaside
0x14002f158  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002f15f  nop     dword ptr [rax+rax+00h]
0x14002f164  lea     rcx, [rbx+280h]; Lookaside
0x14002f16b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002f172  nop     dword ptr [rax+rax+00h]
0x14002f177  add     rsp, 20h
0x14002f17b  pop     rbx
0x14002f17c  retn
```
