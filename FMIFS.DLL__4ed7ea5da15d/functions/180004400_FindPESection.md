# _FindPESection

- ea: `0x180004400`
- end: `0x180004443`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004450`

## callees

- `0x180004400`

## pseudocode

```c
__int64 __fastcall FindPESection(__int64 a1, unsigned __int64 a2)
{
  unsigned int v2; // r9d
  __int64 v3; // r8
  unsigned int v4; // r10d
  __int64 result; // rax
  unsigned __int64 v6; // r8

  v2 = 0;
  v3 = a1 + *(int *)(a1 + 60);
  v4 = *(unsigned __int16 *)(v3 + 6);
  result = v3 + *(unsigned __int16 *)(v3 + 20) + 24LL;
  if ( !*(_WORD *)(v3 + 6) )
    return 0;
  while ( 1 )
  {
    v6 = *(unsigned int *)(result + 12);
    if ( a2 >= v6 && a2 < (unsigned int)(v6 + *(_DWORD *)(result + 8)) )
      break;
    ++v2;
    result += 40;
    if ( v2 >= v4 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004400  movsxd  r8, dword ptr [rcx+3Ch]
0x180004404  xor     r9d, r9d
0x180004407  add     r8, rcx
0x18000440a  movzx   eax, word ptr [r8+14h]
0x18000440f  movzx   r10d, word ptr [r8+6]
0x180004414  add     rax, 18h
0x180004418  add     rax, r8
0x18000441b  test    r10d, r10d
0x18000441e  jz      short loc_180004440
0x180004420  mov     r8d, [rax+0Ch]
0x180004424  cmp     rdx, r8
0x180004427  jb      short loc_180004434
0x180004429  mov     ecx, [rax+8]
0x18000442c  add     ecx, r8d
0x18000442f  cmp     rdx, rcx
0x180004432  jb      short locret_180004442
0x180004434  inc     r9d
0x180004437  add     rax, 28h ; '('
0x18000443b  cmp     r9d, r10d
0x18000443e  jb      short loc_180004420
0x180004440  xor     eax, eax
0x180004442  retn
```
