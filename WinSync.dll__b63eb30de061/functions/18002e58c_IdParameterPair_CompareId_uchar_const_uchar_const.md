# IdParameterPair::CompareId(uchar const *,uchar const *)

- ea: `0x18002e58c`
- end: `0x18002e656`
- name: `?CompareId@IdParameterPair@@QEBAHPEBE0@Z`
- size: `202`
- prototype: `__int64 __fastcall(IdParameterPair *__hidden this, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `22`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002e0d4`
- `0x180030478`
- `0x180033cec`
- `0x180036264`
- `0x18003a64c`
- `0x18003ce20`
- `0x18003f34c`
- `0x1800407ec`
- `0x18004c4c4`
- `0x18004dae0`
- `0x18004e17c`
- `0x18004f560`
- `0x18005022c`
- `0x180051480`
- `0x180051da0`
- `0x180056aec`
- `0x180056f84`
- `0x180057920`
- `0x180058560`
- `0x180059370`
- `0x18006d0c4`
- `0x180079544`

## callees

- `0x18002e58c`

## pseudocode

```c
__int64 __fastcall IdParameterPair::CompareId(
        IdParameterPair *this,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3)
{
  int v5; // r11d
  const unsigned __int8 *v6; // rcx
  const unsigned __int8 *v7; // rdx
  __int64 v8; // r10
  const unsigned __int8 *v9; // rcx
  const unsigned __int8 *v10; // r10
  const unsigned __int8 *v11; // r8
  const unsigned __int8 *v12; // rdx
  unsigned __int8 v13; // al
  unsigned __int8 v14; // al
  unsigned __int8 v15; // al

  if ( a2 == a3 )
    return 0;
  v5 = *(_DWORD *)this;
  if ( *(_DWORD *)this )
  {
    v6 = a2;
    v7 = a3;
  }
  else
  {
    v6 = (const unsigned __int8 *)this + 4;
    v7 = v6;
  }
  v8 = *(unsigned __int16 *)v6;
  v9 = a3 + 2;
  v10 = &a2[v8];
  v11 = &a3[*(unsigned __int16 *)v7];
  v12 = a2 + 2;
  if ( !v5 )
  {
    v12 = a2;
    v9 = a3;
  }
  while ( v10 - v12 >= 4 && v11 - v9 >= 4 )
  {
    if ( *v12 > *v9 )
      return 1;
    if ( *v12 < *v9 )
      return 0xFFFFFFFFLL;
    v13 = v9[1];
    if ( v12[1] > v13 )
      return 1;
    if ( v12[1] < v13 )
      return 0xFFFFFFFFLL;
    v14 = v9[2];
    if ( v12[2] > v14 )
      return 1;
    if ( v12[2] < v14 )
      return 0xFFFFFFFFLL;
    v15 = v9[3];
    if ( v12[3] > v15 )
      return 1;
    if ( v12[3] < v15 )
      return 0xFFFFFFFFLL;
    v12 += 4;
    v9 += 4;
  }
  while ( v12 < v10 )
  {
    if ( v9 >= v11 )
      return v9 == v11;
    if ( *v12 > *v9 )
      return 1;
    if ( *v12 < *v9 )
      return 0xFFFFFFFFLL;
    ++v12;
    ++v9;
  }
  if ( v12 == v10 )
    return (unsigned int)-(v11 != v9);
  return v9 == v11;
}

```

## disassembly

```asm
0x18002e58c  mov     rax, r8
0x18002e58f  mov     r9, rdx
0x18002e592  cmp     rdx, r8
0x18002e595  jz      loc_18002E653
0x18002e59b  mov     r11d, [rcx]
0x18002e59e  test    r11d, r11d
0x18002e5a1  jz      short loc_18002E5AB
0x18002e5a3  mov     rcx, rdx
0x18002e5a6  mov     rdx, rax
0x18002e5a9  jmp     short loc_18002E5B2
0x18002e5ab  add     rcx, 4
0x18002e5af  mov     rdx, rcx
0x18002e5b2  movzx   r10d, word ptr [rcx]
0x18002e5b6  lea     rcx, [rax+2]
0x18002e5ba  movzx   r8d, word ptr [rdx]
0x18002e5be  add     r10, r9
0x18002e5c1  add     r8, rax
0x18002e5c4  lea     rdx, [r9+2]
0x18002e5c8  test    r11d, r11d
0x18002e5cb  cmovz   rdx, r9
0x18002e5cf  cmovz   rcx, rax
0x18002e5d3  mov     rax, r10
0x18002e5d6  sub     rax, rdx
0x18002e5d9  cmp     rax, 4
0x18002e5dd  jl      short loc_18002E61B
0x18002e5df  mov     rax, r8
0x18002e5e2  sub     rax, rcx
0x18002e5e5  cmp     rax, 4
0x18002e5e9  jl      short loc_18002E61B
0x18002e5eb  mov     al, [rcx]
0x18002e5ed  cmp     [rdx], al
0x18002e5ef  ja      short loc_18002E639
0x18002e5f1  jb      short loc_18002E635
0x18002e5f3  mov     al, [rcx+1]
0x18002e5f6  cmp     [rdx+1], al
0x18002e5f9  ja      short loc_18002E639
0x18002e5fb  jb      short loc_18002E635
0x18002e5fd  mov     al, [rcx+2]
0x18002e600  cmp     [rdx+2], al
0x18002e603  ja      short loc_18002E639
0x18002e605  jb      short loc_18002E635
0x18002e607  mov     al, [rcx+3]
0x18002e60a  cmp     [rdx+3], al
0x18002e60d  ja      short loc_18002E639
0x18002e60f  jb      short loc_18002E635
0x18002e611  add     rdx, 4
0x18002e615  add     rcx, 4
0x18002e619  jmp     short loc_18002E5D3
0x18002e61b  cmp     rdx, r10
0x18002e61e  jnb     short loc_18002E63F
0x18002e620  cmp     rcx, r8
0x18002e623  jnb     short loc_18002E64A
0x18002e625  mov     al, [rdx]
0x18002e627  cmp     al, [rcx]
0x18002e629  ja      short loc_18002E639
0x18002e62b  jb      short loc_18002E635
0x18002e62d  inc     rdx
0x18002e630  inc     rcx
0x18002e633  jmp     short loc_18002E61B
0x18002e635  or      eax, 0FFFFFFFFh
0x18002e638  retn
0x18002e639  mov     eax, 1
0x18002e63e  retn
0x18002e63f  jnz     short loc_18002E64A
0x18002e641  sub     rcx, r8
0x18002e644  neg     rcx
0x18002e647  sbb     eax, eax
0x18002e649  retn
0x18002e64a  xor     eax, eax
0x18002e64c  cmp     rcx, r8
0x18002e64f  setz    al
0x18002e652  retn
0x18002e653  xor     eax, eax
0x18002e655  retn
```
