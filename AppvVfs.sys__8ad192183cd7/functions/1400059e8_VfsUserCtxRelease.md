# VfsUserCtxRelease

- ea: `0x1400059e8`
- end: `0x140005a25`
- name: `VfsUserCtxRelease`
- size: `61`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140005b10`
- `0x140009298`
- `0x140009784`
- `0x140009d44`

## callees

- `0x14000535c`
- `0x1400059e8`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140005a12`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140005a12`

## pseudocode

```c
void __fastcall VfsUserCtxRelease(__int64 a1)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 80), 0xFFFFFFFF) == 1 )
  {
    VfsCtxTableDelete((PRTL_AVL_TABLE)(a1 + 96));
    ExFreeToPagedLookasideList(&stru_14001F580, (PVOID)(a1 - 32));
  }
}

```

## disassembly

```asm
0x1400059e8  push    rbx
0x1400059ea  sub     rsp, 20h
0x1400059ee  mov     rbx, rcx
0x1400059f1  or      eax, 0FFFFFFFFh
0x1400059f4  lock xadd [rcx+50h], eax
0x1400059f9  cmp     eax, 1
0x1400059fc  jnz     short loc_140005A1E
0x1400059fe  add     rcx, 60h ; '`'; Table
0x140005a02  call    VfsCtxTableDelete
0x140005a07  lea     rdx, [rbx-20h]; Entry
0x140005a0b  lea     rcx, stru_14001F580; Lookaside
0x140005a12  call    cs:__imp_ExFreeToPagedLookasideList
0x140005a19  nop     dword ptr [rax+rax+00h]
0x140005a1e  add     rsp, 20h
0x140005a22  pop     rbx
0x140005a23  retn
```
