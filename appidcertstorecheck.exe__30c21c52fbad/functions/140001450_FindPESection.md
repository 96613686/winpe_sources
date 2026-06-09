# _FindPESection

- ea: `0x140001450`
- end: `0x140001493`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140001450`

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
0x140001450  movsxd  r8, dword ptr [rcx+3Ch]
0x140001454  xor     r9d, r9d
0x140001457  add     r8, rcx
0x14000145a  movzx   eax, word ptr [r8+14h]
0x14000145f  movzx   r10d, word ptr [r8+6]
0x140001464  add     rax, 18h
0x140001468  add     rax, r8
0x14000146b  test    r10d, r10d
0x14000146e  jz      short loc_140001490
0x140001470  mov     r8d, [rax+0Ch]
0x140001474  cmp     rdx, r8
0x140001477  jb      short loc_140001484
0x140001479  mov     ecx, [rax+8]
0x14000147c  add     ecx, r8d
0x14000147f  cmp     rdx, rcx
0x140001482  jb      short locret_140001492
0x140001484  inc     r9d
0x140001487  add     rax, 28h ; '('
0x14000148b  cmp     r9d, r10d
0x14000148e  jb      short loc_140001470
0x140001490  xor     eax, eax
0x140001492  retn
```
