# UpdateInternalStatsOnFlush

- ea: `0x1800136d4`
- end: `0x180013716`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001181c`
- `0x18001b070`

## callees

- `0x1800136d4`

## pseudocode

```c
void __fastcall UpdateInternalStatsOnFlush(__int64 a1, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 v3; // rax

  if ( a2 )
  {
    v2 = (__int64 *)(a1 + 280);
    if ( *(_DWORD *)(a1 + 296) > a2 || (v3 = *v2) == 0 )
    {
      v3 = *v2;
      *(_DWORD *)(a1 + 296) = a2;
    }
    if ( *(_DWORD *)(a1 + 292) < a2 )
      *(_DWORD *)(a1 + 292) = a2;
    *v2 = v3 + 1;
    *(_QWORD *)(a1 + 272) += a2;
  }
}

```

## disassembly

```asm
0x1800136d4  test    edx, edx
0x1800136d6  jz      short locret_180013715
0x1800136d8  lea     r8, [rcx+118h]
0x1800136df  cmp     [rcx+128h], edx
0x1800136e5  ja      short loc_1800136EF
0x1800136e7  mov     rax, [r8]
0x1800136ea  test    rax, rax
0x1800136ed  jnz     short loc_1800136F8
0x1800136ef  mov     rax, [r8]
0x1800136f2  mov     [rcx+128h], edx
0x1800136f8  cmp     [rcx+124h], edx
0x1800136fe  jnb     short loc_180013706
0x180013700  mov     [rcx+124h], edx
0x180013706  inc     rax
0x180013709  mov     [r8], rax
0x18001370c  mov     eax, edx
0x18001370e  add     [rcx+110h], rax
0x180013715  retn
```
