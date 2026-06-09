# UpdateInternalStatsOnFlush

- ea: `0x18000c3b0`
- end: `0x18000c3f2`
- name: `UpdateInternalStatsOnFlush`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000be00`
- `0x18000c038`

## callees

- `0x18000c3b0`

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
0x18000c3b0  test    edx, edx
0x18000c3b2  jz      short locret_18000C3F1
0x18000c3b4  lea     r8, [rcx+118h]
0x18000c3bb  cmp     [rcx+128h], edx
0x18000c3c1  ja      short loc_18000C3CB
0x18000c3c3  mov     rax, [r8]
0x18000c3c6  test    rax, rax
0x18000c3c9  jnz     short loc_18000C3D4
0x18000c3cb  mov     rax, [r8]
0x18000c3ce  mov     [rcx+128h], edx
0x18000c3d4  cmp     [rcx+124h], edx
0x18000c3da  jnb     short loc_18000C3E2
0x18000c3dc  mov     [rcx+124h], edx
0x18000c3e2  inc     rax
0x18000c3e5  mov     [r8], rax
0x18000c3e8  mov     eax, edx
0x18000c3ea  add     [rcx+110h], rax
0x18000c3f1  retn
```
