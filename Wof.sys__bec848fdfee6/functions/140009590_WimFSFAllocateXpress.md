# WimFSFAllocateXpress

- ea: `0x140009590`
- end: `0x1400095f8`
- name: `WimFSFAllocateXpress`
- size: `104`
- prototype: `_DWORD *__fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140009000`

## callees

- `0x140009590`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400095a8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400095a8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400095d3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400095d3`

## pseudocode

```c
_DWORD *__fastcall WimFSFAllocateXpress(__int64 a1, unsigned int a2)
{
  _DWORD *PoolWithTag; // rax

  if ( !a1 || a2 > *(_DWORD *)(a1 + 256) )
  {
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, (int)a2 + 4LL, 0x70787077u);
    if ( PoolWithTag )
    {
      *PoolWithTag = 0;
      return PoolWithTag + 1;
    }
    return 0;
  }
  PoolWithTag = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 320));
  if ( !PoolWithTag )
    return 0;
  *PoolWithTag = 1;
  return PoolWithTag + 1;
}

```

## disassembly

```asm
0x140009590  sub     rsp, 28h
0x140009594  test    rcx, rcx
0x140009597  jz      short loc_1400095C1
0x140009599  cmp     edx, [rcx+100h]
0x14000959f  ja      short loc_1400095C1
0x1400095a1  add     rcx, 140h; Lookaside
0x1400095a8  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400095af  nop     dword ptr [rax+rax+00h]
0x1400095b4  test    rax, rax
0x1400095b7  jz      short loc_1400095E4
0x1400095b9  mov     dword ptr [rax], 1
0x1400095bf  jmp     short loc_1400095EE
0x1400095c1  movsxd  rdx, edx
0x1400095c4  mov     ecx, 1; PoolType
0x1400095c9  add     rdx, 4; NumberOfBytes
0x1400095cd  mov     r8d, 70787077h; Tag
0x1400095d3  call    cs:__imp_ExAllocatePoolWithTag
0x1400095da  nop     dword ptr [rax+rax+00h]
0x1400095df  test    rax, rax
0x1400095e2  jnz     short loc_1400095E8
0x1400095e4  xor     eax, eax
0x1400095e6  jmp     short loc_1400095F2
0x1400095e8  mov     dword ptr [rax], 0
0x1400095ee  add     rax, 4
0x1400095f2  add     rsp, 28h
0x1400095f6  retn
```
