# VfsPkgCtxTableElementFree

- ea: `0x1400059b0`
- end: `0x1400059df`
- name: `VfsPkgCtxTableElementFree`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140005888`
- `0x1400059b0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400059cd`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400059cd`

## pseudocode

```c
void __fastcall VfsPkgCtxTableElementFree(__int64 a1, _DWORD *a2)
{
  if ( (a2[17] & 1) != 0 )
    VfsPkgCtxRelease((__int64)(a2 + 8));
  else
    ExFreeToPagedLookasideList(&stru_14001F500, a2);
}

```

## disassembly

```asm
0x1400059b0  sub     rsp, 28h
0x1400059b4  lea     rcx, [rdx+20h]
0x1400059b8  mov     eax, [rcx+24h]
0x1400059bb  test    al, 1
0x1400059bd  jz      short loc_1400059C6
0x1400059bf  call    VfsPkgCtxRelease
0x1400059c4  jmp     short loc_1400059D9
0x1400059c6  lea     rcx, stru_14001F500; Lookaside
0x1400059cd  call    cs:__imp_ExFreeToPagedLookasideList
0x1400059d4  nop     dword ptr [rax+rax+00h]
0x1400059d9  add     rsp, 28h
0x1400059dd  retn
```
