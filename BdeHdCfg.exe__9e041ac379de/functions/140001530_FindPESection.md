# _FindPESection

- ea: `0x140001530`
- end: `0x140001573`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001580`

## callees

- `0x140001530`

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
0x140001530  movsxd  r8, dword ptr [rcx+3Ch]
0x140001534  xor     r9d, r9d
0x140001537  add     r8, rcx
0x14000153a  movzx   eax, word ptr [r8+14h]
0x14000153f  movzx   r10d, word ptr [r8+6]
0x140001544  add     rax, 18h
0x140001548  add     rax, r8
0x14000154b  test    r10d, r10d
0x14000154e  jz      short loc_140001570
0x140001550  mov     r8d, [rax+0Ch]
0x140001554  cmp     rdx, r8
0x140001557  jb      short loc_140001564
0x140001559  mov     ecx, [rax+8]
0x14000155c  add     ecx, r8d
0x14000155f  cmp     rdx, rcx
0x140001562  jb      short locret_140001572
0x140001564  inc     r9d
0x140001567  add     rax, 28h ; '('
0x14000156b  cmp     r9d, r10d
0x14000156e  jb      short loc_140001550
0x140001570  xor     eax, eax
0x140001572  retn
```
