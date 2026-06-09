# NetioGetDataBufferIfSafe

- ea: `0x18001d3a4`
- end: `0x18001d40c`
- name: `NetioGetDataBufferIfSafe`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ce30`

## callees

- `0x18001d3a4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18001d3e3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18001d3e3`

## pseudocode

```c
char *__fastcall NetioGetDataBufferIfSafe(__int64 a1, unsigned int a2)
{
  __int64 v3; // rcx
  char *v4; // rax
  char *v5; // rdx
  char *result; // rax

  v3 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v3 + 40) - *(_DWORD *)(a1 + 16) < a2 )
    return 0;
  if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    v4 = *(char **)(v3 + 24);
  else
    v4 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000000u);
  v5 = &v4[*(unsigned int *)(a1 + 16)];
  result = 0;
  if ( ((unsigned __int8)v5 & 1) == 0 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x18001d3a4  push    rbx
0x18001d3a6  sub     rsp, 30h
0x18001d3aa  mov     rbx, rcx
0x18001d3ad  mov     rcx, [rcx+8]; MemoryDescriptorList
0x18001d3b1  mov     r8d, [rcx+28h]
0x18001d3b5  sub     r8d, [rbx+10h]
0x18001d3b9  cmp     r8d, edx
0x18001d3bc  jb      short loc_18001D403
0x18001d3be  test    byte ptr [rcx+0Ah], 5
0x18001d3c2  jz      short loc_18001D3CA
0x18001d3c4  mov     rax, [rcx+18h]
0x18001d3c8  jmp     short loc_18001D3EF
0x18001d3ca  xor     r9d, r9d; RequestedAddress
0x18001d3cd  mov     [rsp+38h+Priority], 40000000h; Priority
0x18001d3d5  xor     edx, edx; AccessMode
0x18001d3d7  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x18001d3df  lea     r8d, [r9+1]; CacheType
0x18001d3e3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18001d3ea  nop     dword ptr [rax+rax+00h]
0x18001d3ef  mov     edx, [rbx+10h]
0x18001d3f2  add     rdx, rax
0x18001d3f5  mov     eax, 0
0x18001d3fa  test    dl, 1
0x18001d3fd  cmovz   rax, rdx
0x18001d401  jmp     short loc_18001D405
0x18001d403  xor     eax, eax
0x18001d405  add     rsp, 30h
0x18001d409  pop     rbx
0x18001d40a  retn
```
