# CInputBitStream::getMaxBits(ulong,uchar *)

- ea: `0x18000dd4c`
- end: `0x18000debf`
- name: `?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z`
- size: `371`
- prototype: `unsigned __int8 __fastcall(CInputBitStream *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000da60`
- `0x18000db8c`
- `0x18000df50`
- `0x18000e180`
- `0x18000e270`
- `0x18000e350`
- `0x18000e5e0`
- `0x18000e760`
- `0x18000e9d0`
- `0x180012898`
- `0x180012c04`

## callees

- `0x18000dd4c`

## pseudocode

```c
unsigned __int8 __fastcall CInputBitStream::getMaxBits(CInputBitStream *this, unsigned int a2, unsigned __int8 *a3)
{
  unsigned int v3; // r11d
  __int64 v5; // rbx
  __int64 v6; // rcx
  int v7; // r11d
  int v9; // r9d
  unsigned __int8 *v10; // rcx
  int v11; // eax
  unsigned int v12; // edx
  int v13; // edx
  unsigned __int8 *v14; // rdx
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // ecx

  v3 = *((_DWORD *)this + 4);
  v5 = a2;
  if ( a2 <= v3 )
  {
    _mm_lfence();
    v6 = 2 * (*((_DWORD *)&getMask + a2) & (*((_DWORD *)this + 3) >> (v3 - a2)));
LABEL_3:
    v7 = v3 - a3[v6];
LABEL_4:
    *((_DWORD *)this + 4) = v7;
    if ( a3[v6 + 1] == 0xFF )
      *((_DWORD *)this + 5) = 3;
    return a3[v6 + 1];
  }
  v9 = *((_DWORD *)this + 2);
  if ( v9 >= 2 )
  {
    *((_DWORD *)this + 3) <<= 16;
    v10 = *(unsigned __int8 **)this;
    v11 = *((_DWORD *)this + 3) | v10[1];
    *((_DWORD *)this + 3) = v11;
    v12 = v11 | (*v10 << 8);
    *((_DWORD *)this + 3) = v12;
    *(_QWORD *)this = v10 + 2;
    v13 = 2 * (*((_DWORD *)&getMask + v5) & (v12 >> (v3 - v5 + 16)));
    *((_DWORD *)this + 2) = v9 - 2;
    v6 = v13;
    *((_DWORD *)this + 4) = v3 + 16;
    v7 = v3 - a3[v13] + 16;
    goto LABEL_4;
  }
  if ( v9 )
  {
    v14 = *(unsigned __int8 **)this;
    do
    {
      v3 += 8;
      v15 = *((_DWORD *)this + 3) << 8;
      *((_DWORD *)this + 3) = v15;
      v16 = *v14++;
      *(_QWORD *)this = v14;
      --v9;
      *((_DWORD *)this + 3) = v16 | v15;
      *((_DWORD *)this + 2) = v9;
      *((_DWORD *)this + 4) = v3;
    }
    while ( v9 );
  }
  if ( v3 >= (unsigned int)v5 )
  {
    _mm_lfence();
    v6 = 2 * (*((_DWORD *)&getMask + v5) & (*((_DWORD *)this + 3) >> (v3 - v5)));
    goto LABEL_3;
  }
  v17 = (*((_DWORD *)this + 3) & *((_DWORD *)&getMask + v3)) << (v5 - v3 + 1);
  v18 = a3[v17];
  if ( v3 < v18 )
  {
    *((_DWORD *)this + 5) = 1;
    return -1;
  }
  else
  {
    *((_DWORD *)this + 4) = v3 - v18;
    if ( a3[v17 + 1] == 0xFF )
      *((_DWORD *)this + 5) = 3;
    return a3[v17 + 1];
  }
}

```

## disassembly

```asm
0x18000dd4c  mov     [rsp+arg_0], rbx
0x18000dd51  mov     r11d, [rcx+10h]
0x18000dd55  mov     r10, rcx
0x18000dd58  mov     ebx, edx
0x18000dd5a  cmp     edx, r11d
0x18000dd5d  ja      short loc_18000DDA5
0x18000dd5f  lfence
0x18000dd62  mov     r9d, [r10+0Ch]
0x18000dd66  mov     ecx, r11d
0x18000dd69  sub     ecx, ebx
0x18000dd6b  shr     r9d, cl
0x18000dd6e  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000dd75  and     r9d, [rcx+rbx*4]
0x18000dd79  add     r9d, r9d
0x18000dd7c  movsxd  rcx, r9d
0x18000dd7f  movzx   eax, byte ptr [rcx+r8]
0x18000dd84  sub     r11d, eax
0x18000dd87  mov     [r10+10h], r11d
0x18000dd8b  cmp     byte ptr [rcx+r8+1], 0FFh
0x18000dd91  jnz     short loc_18000DD9B
0x18000dd93  mov     dword ptr [r10+14h], 3
0x18000dd9b  mov     al, [rcx+r8+1]
0x18000dda0  jmp     loc_18000DEB9
0x18000dda5  mov     r9d, [rcx+8]
0x18000dda9  cmp     r9d, 2
0x18000ddad  jl      short loc_18000DE0F
0x18000ddaf  shl     dword ptr [rcx+0Ch], 10h
0x18000ddb3  mov     rcx, [rcx]
0x18000ddb6  movzx   eax, byte ptr [rcx+1]
0x18000ddba  or      eax, [r10+0Ch]
0x18000ddbe  mov     [r10+0Ch], eax
0x18000ddc2  movzx   edx, byte ptr [rcx]
0x18000ddc5  shl     edx, 8
0x18000ddc8  or      edx, eax
0x18000ddca  lea     rax, [rcx+2]
0x18000ddce  mov     ecx, r11d
0x18000ddd1  mov     [r10+0Ch], edx
0x18000ddd5  sub     ecx, ebx
0x18000ddd7  mov     [r10], rax
0x18000ddda  add     ecx, 10h
0x18000dddd  lea     eax, [r9-2]
0x18000dde1  shr     edx, cl
0x18000dde3  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000ddea  and     edx, [rcx+rbx*4]
0x18000dded  add     edx, edx
0x18000ddef  mov     [r10+8], eax
0x18000ddf3  lea     eax, [r11+10h]
0x18000ddf7  movsxd  rcx, edx
0x18000ddfa  mov     [r10+10h], eax
0x18000ddfe  movzx   eax, byte ptr [rcx+r8]
0x18000de03  sub     r11d, eax
0x18000de06  add     r11d, 10h
0x18000de0a  jmp     loc_18000DD87
0x18000de0f  test    r9d, r9d
0x18000de12  jz      short loc_18000DE45
0x18000de14  mov     rdx, [rcx]
0x18000de17  mov     ecx, [r10+0Ch]
0x18000de1b  add     r11d, 8
0x18000de1f  shl     ecx, 8
0x18000de22  mov     [r10+0Ch], ecx
0x18000de26  movzx   eax, byte ptr [rdx]
0x18000de29  inc     rdx
0x18000de2c  or      ecx, eax
0x18000de2e  mov     [r10], rdx
0x18000de31  dec     r9d
0x18000de34  mov     [r10+0Ch], ecx
0x18000de38  mov     [r10+8], r9d
0x18000de3c  mov     [r10+10h], r11d
0x18000de40  test    r9d, r9d
0x18000de43  jnz     short loc_18000DE17
0x18000de45  cmp     r11d, ebx
0x18000de48  jb      short loc_18000DE6C
0x18000de4a  lfence
0x18000de4d  mov     edx, [r10+0Ch]
0x18000de51  mov     ecx, r11d
0x18000de54  sub     ecx, ebx
0x18000de56  shr     edx, cl
0x18000de58  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000de5f  and     edx, [rcx+rbx*4]
0x18000de62  add     edx, edx
0x18000de64  movsxd  rcx, edx
0x18000de67  jmp     loc_18000DD7F
0x18000de6c  mov     eax, r11d
0x18000de6f  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000de76  sub     ebx, r11d
0x18000de79  mov     eax, [rcx+rax*4]
0x18000de7c  and     eax, [r10+0Ch]
0x18000de80  lea     ecx, [rbx+1]
0x18000de83  shl     eax, cl
0x18000de85  cdqe
0x18000de87  movzx   ecx, byte ptr [rax+r8]
0x18000de8c  cmp     r11d, ecx
0x18000de8f  jb      short loc_18000DEAF
0x18000de91  sub     r11d, ecx
0x18000de94  mov     [r10+10h], r11d
0x18000de98  cmp     byte ptr [rax+r8+1], 0FFh
0x18000de9e  jnz     short loc_18000DEA8
0x18000dea0  mov     dword ptr [r10+14h], 3
0x18000dea8  mov     al, [rax+r8+1]
0x18000dead  jmp     short loc_18000DEB9
0x18000deaf  mov     dword ptr [r10+14h], 1
0x18000deb7  mov     al, 0FFh
0x18000deb9  mov     rbx, [rsp+arg_0]
0x18000debe  retn
```
