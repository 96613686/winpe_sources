# _FindPESection

- ea: `0x140001510`
- end: `0x140001553`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001560`

## callees

- `0x140001510`

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
0x140001510  movsxd  r8, dword ptr [rcx+3Ch]
0x140001514  xor     r9d, r9d
0x140001517  add     r8, rcx
0x14000151a  movzx   eax, word ptr [r8+14h]
0x14000151f  movzx   r10d, word ptr [r8+6]
0x140001524  add     rax, 18h
0x140001528  add     rax, r8
0x14000152b  test    r10d, r10d
0x14000152e  jz      short loc_140001550
0x140001530  mov     r8d, [rax+0Ch]
0x140001534  cmp     rdx, r8
0x140001537  jb      short loc_140001544
0x140001539  mov     ecx, [rax+8]
0x14000153c  add     ecx, r8d
0x14000153f  cmp     rdx, rcx
0x140001542  jb      short locret_140001552
0x140001544  inc     r9d
0x140001547  add     rax, 28h ; '('
0x14000154b  cmp     r9d, r10d
0x14000154e  jb      short loc_140001530
0x140001550  xor     eax, eax
0x140001552  retn
```
