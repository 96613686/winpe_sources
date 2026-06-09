# CInputBitStream::getMaxBits(ulong,uchar const *)

- ea: `0x1800079c0`
- end: `0x180007b74`
- name: `?getMaxBits@CInputBitStream@@QEAAEKPEBE@Z`
- size: `436`
- prototype: `unsigned __int8 __fastcall(CInputBitStream *__hidden this, unsigned int, const unsigned __int8 *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e0`
- `0x1800038e0`
- `0x180006200`
- `0x1800065b0`
- `0x180006fe0`
- `0x1800081b0`
- `0x18000b748`
- `0x180033ed0`
- `0x180034844`
- `0x180034998`
- `0x180034b30`
- `0x180034ce0`
- `0x1800350e0`
- `0x180035268`

## callees

- `0x1800079c0`

## pseudocode

```c
unsigned __int8 __fastcall CInputBitStream::getMaxBits(
        CInputBitStream *this,
        unsigned int a2,
        const unsigned __int8 *a3)
{
  unsigned int v3; // eax
  __int64 v5; // r11
  __int64 v7; // rdx
  int v9; // r9d
  unsigned __int8 *v10; // rdx
  int v11; // ecx
  unsigned int v12; // r8d
  __int64 v13; // rdx
  int v14; // eax
  unsigned __int8 *v15; // r8
  int v16; // edx
  int v17; // ecx
  __int64 v18; // rcx
  unsigned int v19; // edx

  v3 = *((_DWORD *)this + 4);
  v5 = a2;
  if ( a2 <= v3 )
  {
    _mm_lfence();
    v7 = 2 * (*((_DWORD *)&GetMask + a2) & (*((_DWORD *)this + 3) >> (v3 - a2)));
    *((_DWORD *)this + 4) = v3 - a3[v7];
    if ( a3[v7 + 1] == 0xFF )
      *((_DWORD *)this + 5) = 3;
    return a3[v7 + 1];
  }
  v9 = *((_DWORD *)this + 2);
  if ( v9 >= 2 )
  {
    *((_DWORD *)this + 3) <<= 16;
    v10 = *(unsigned __int8 **)this;
    v11 = *((_DWORD *)this + 3) | *(unsigned __int8 *)(*(_QWORD *)this + 1LL);
    *((_DWORD *)this + 3) = v11;
    v12 = v11 | (*v10 << 8);
    *(_QWORD *)this = v10 + 2;
    *((_DWORD *)this + 2) = v9 - 2;
    *((_DWORD *)this + 4) = v3 + 16;
    *((_DWORD *)this + 3) = v12;
    v13 = (int)(2 * (*((_DWORD *)&GetMask + v5) & (v12 >> (v3 - v5 + 16))));
    v14 = v3 - a3[v13] + 16;
LABEL_7:
    *((_DWORD *)this + 4) = v14;
    if ( a3[v13 + 1] == 0xFF )
      *((_DWORD *)this + 5) = 3;
    return a3[v13 + 1];
  }
  if ( v9 )
  {
    v15 = *(unsigned __int8 **)this;
    do
    {
      v3 += 8;
      v16 = *((_DWORD *)this + 3) << 8;
      *((_DWORD *)this + 3) = v16;
      v17 = *v15++;
      *(_QWORD *)this = v15;
      --v9;
      *((_DWORD *)this + 3) = v17 | v16;
      *((_DWORD *)this + 2) = v9;
      *((_DWORD *)this + 4) = v3;
    }
    while ( v9 );
  }
  if ( v3 >= (unsigned int)v5 )
  {
    _mm_lfence();
    v13 = 2 * (*((_DWORD *)&GetMask + v5) & (*((_DWORD *)this + 3) >> (v3 - v5)));
    v14 = v3 - a3[v13];
    goto LABEL_7;
  }
  v18 = (*((_DWORD *)this + 3) & *((_DWORD *)&GetMask + v3)) << (v5 - v3 + 1);
  v19 = a3[v18];
  if ( v3 < v19 )
  {
    *((_DWORD *)this + 5) = 1;
    return -1;
  }
  else
  {
    *((_DWORD *)this + 4) = v3 - v19;
    if ( a3[v18 + 1] == 0xFF )
      *((_DWORD *)this + 5) = 3;
    return a3[v18 + 1];
  }
}

```

## disassembly

```asm
0x1800079c0  mov     [rsp+arg_0], rbx
0x1800079c5  mov     [rsp+arg_8], rdi
0x1800079ca  mov     eax, [rcx+10h]
0x1800079cd  mov     rbx, r8
0x1800079d0  mov     r11d, edx
0x1800079d3  mov     r10, rcx
0x1800079d6  cmp     edx, eax
0x1800079d8  ja      short loc_180007A22
0x1800079da  lfence
0x1800079dd  mov     r9d, [r10+0Ch]
0x1800079e1  lea     rdi, ?GetMask@@3QBKB; ulong const near * const GetMask
0x1800079e8  mov     ecx, eax
0x1800079ea  sub     ecx, r11d
0x1800079ed  shr     r9d, cl
0x1800079f0  and     r9d, [rdi+r11*4]
0x1800079f4  add     r9d, r9d
0x1800079f7  movsxd  rdx, r9d
0x1800079fa  movzx   ecx, byte ptr [rdx+r8]
0x1800079ff  sub     eax, ecx
0x180007a01  mov     [r10+10h], eax
0x180007a05  cmp     byte ptr [rdx+r8+1], 0FFh
0x180007a0b  jz      loc_180007B5D
0x180007a11  movzx   eax, byte ptr [rdx+r8+1]
0x180007a17  mov     rbx, [rsp+arg_0]
0x180007a1c  mov     rdi, [rsp+arg_8]
0x180007a21  retn
0x180007a22  mov     r9d, [rcx+8]
0x180007a26  cmp     r9d, 2
0x180007a2a  jl      loc_180007AB0
0x180007a30  shl     dword ptr [rcx+0Ch], 10h
0x180007a34  lea     rdi, ?GetMask@@3QBKB; ulong const near * const GetMask
0x180007a3b  mov     rdx, [rcx]
0x180007a3e  movzx   ecx, byte ptr [rdx+1]
0x180007a42  or      ecx, [r10+0Ch]
0x180007a46  mov     [r10+0Ch], ecx
0x180007a4a  movzx   r8d, byte ptr [rdx]
0x180007a4e  shl     r8d, 8
0x180007a52  or      r8d, ecx
0x180007a55  lea     rcx, [rdx+2]
0x180007a59  mov     [r10], rcx
0x180007a5c  lea     ecx, [r9-2]
0x180007a60  mov     [r10+8], ecx
0x180007a64  lea     ecx, [rax+10h]
0x180007a67  mov     [r10+10h], ecx
0x180007a6b  mov     ecx, eax
0x180007a6d  mov     [r10+0Ch], r8d
0x180007a71  sub     ecx, r11d
0x180007a74  add     ecx, 10h
0x180007a77  shr     r8d, cl
0x180007a7a  and     r8d, [rdi+r11*4]
0x180007a7e  add     r8d, r8d
0x180007a81  movsxd  rdx, r8d
0x180007a84  movzx   ecx, byte ptr [rdx+rbx]
0x180007a88  sub     eax, ecx
0x180007a8a  add     eax, 10h
0x180007a8d  mov     [r10+10h], eax
0x180007a91  cmp     byte ptr [rdx+rbx+1], 0FFh
0x180007a96  jnz     short loc_180007AA0
0x180007a98  mov     dword ptr [r10+14h], 3
0x180007aa0  movzx   eax, byte ptr [rdx+rbx+1]
0x180007aa5  mov     rbx, [rsp+arg_0]
0x180007aaa  mov     rdi, [rsp+arg_8]
0x180007aaf  retn
0x180007ab0  test    r9d, r9d
0x180007ab3  jz      short loc_180007AE6
0x180007ab5  mov     r8, [rcx]
0x180007ab8  mov     edx, [r10+0Ch]
0x180007abc  add     eax, 8
0x180007abf  shl     edx, 8
0x180007ac2  mov     [r10+0Ch], edx
0x180007ac6  movzx   ecx, byte ptr [r8]
0x180007aca  inc     r8
0x180007acd  or      edx, ecx
0x180007acf  mov     [r10], r8
0x180007ad2  dec     r9d
0x180007ad5  mov     [r10+0Ch], edx
0x180007ad9  mov     [r10+8], r9d
0x180007add  mov     [r10+10h], eax
0x180007ae1  test    r9d, r9d
0x180007ae4  jnz     short loc_180007AB8
0x180007ae6  lea     rdi, ?GetMask@@3QBKB; ulong const near * const GetMask
0x180007aed  cmp     eax, r11d
0x180007af0  jb      short loc_180007B14
0x180007af2  lfence
0x180007af5  mov     edx, [r10+0Ch]
0x180007af9  mov     ecx, eax
0x180007afb  sub     ecx, r11d
0x180007afe  shr     edx, cl
0x180007b00  and     edx, [rdi+r11*4]
0x180007b04  add     edx, edx
0x180007b06  movsxd  rdx, edx
0x180007b09  movzx   ecx, byte ptr [rdx+rbx]
0x180007b0d  sub     eax, ecx
0x180007b0f  jmp     loc_180007A8D
0x180007b14  mov     ecx, eax
0x180007b16  sub     r11d, eax
0x180007b19  mov     edx, [rdi+rcx*4]
0x180007b1c  lea     ecx, [r11+1]
0x180007b20  and     edx, [r10+0Ch]
0x180007b24  shl     edx, cl
0x180007b26  movsxd  rcx, edx
0x180007b29  movzx   edx, byte ptr [rcx+rbx]
0x180007b2d  cmp     eax, edx
0x180007b2f  jb      short loc_180007B4E
0x180007b31  sub     eax, edx
0x180007b33  mov     [r10+10h], eax
0x180007b37  cmp     byte ptr [rcx+rbx+1], 0FFh
0x180007b3c  jz      short loc_180007B6A
0x180007b3e  movzx   eax, byte ptr [rcx+rbx+1]
0x180007b43  mov     rbx, [rsp+arg_0]
0x180007b48  mov     rdi, [rsp+arg_8]
0x180007b4d  retn
0x180007b4e  mov     dword ptr [r10+14h], 1
0x180007b56  mov     al, 0FFh
0x180007b58  jmp     loc_180007A17
0x180007b5d  mov     dword ptr [r10+14h], 3
0x180007b65  jmp     loc_180007A11
0x180007b6a  mov     dword ptr [r10+14h], 3
0x180007b72  jmp     short loc_180007B3E
```
