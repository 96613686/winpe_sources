# CMetadataFilter::RemoveRedundantPoints(void)

- ea: `0x100460890`
- end: `0x100460a46`
- name: `?RemoveRedundantPoints@CMetadataFilter@@AEAAXXZ`
- size: `438`
- prototype: `void __fastcall(CMetadataFilter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1004602b0`

## callees

- `0x100460890`
- `0x100460a50`

## pseudocode

```c
void __fastcall CMetadataFilter::RemoveRedundantPoints(CMetadataFilter *this)
{
  unsigned int v1; // r9d
  unsigned int v3; // ebp
  unsigned int v4; // r14d
  unsigned int i; // edi
  __int64 v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // ecx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r9
  _OWORD *v16; // rdx

  v1 = *((_DWORD *)this + 7);
  v3 = 1;
  if ( v1 >= 2 )
  {
    v4 = 1;
    for ( i = 1; i < v1 - 1; ++i )
    {
      v6 = 8LL * i;
      v7 = HIDWORD(*(_QWORD *)(v6 + *((_QWORD *)this + 6)));
      if ( (_BYTE)v7 != 3 && (_BYTE)v7 != 5 && (_BYTE)v7 != 2 || !CMetadataFilter::IsOnTheLine(this, i, v4 - 1, i + 1) )
      {
        v8 = 2LL * v4;
        v9 = v4++;
        *(_OWORD *)(*((_QWORD *)this + 4) + 8 * v8) = *(_OWORD *)(*((_QWORD *)this + 4) + 16LL * i);
        *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v9) = *(_QWORD *)(v6 + *((_QWORD *)this + 6));
      }
      v1 = *((_DWORD *)this + 7);
    }
    v10 = v1 - 1;
    v1 = v4 + 1;
    *(_OWORD *)(*((_QWORD *)this + 4) + 16LL * v4) = *(_OWORD *)(*((_QWORD *)this + 4) + 16 * v10);
    *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v4) = *(_QWORD *)(*((_QWORD *)this + 6)
                                                              + 8LL * (unsigned int)(*((_DWORD *)this + 11) - 1));
    *((_DWORD *)this + 7) = v4 + 1;
    *((_DWORD *)this + 11) = v4 + 1;
  }
  if ( *((_BYTE *)this + 17) )
  {
    if ( v1 >= 4 )
    {
      v11 = HIDWORD(**((_QWORD **)this + 6));
      if ( ((_BYTE)v11 == 3 || (_BYTE)v11 == 5 || (_BYTE)v11 == 2) && CMetadataFilter::IsOnTheLine(this, 0, 1u, v1 - 2) )
      {
        v12 = *((_DWORD *)this + 7);
        if ( (unsigned int)(v12 - 1) > 1 )
        {
          do
          {
            v13 = v3 - 1;
            v14 = 2LL * v3;
            v15 = v3++;
            *(_OWORD *)(*((_QWORD *)this + 4) + 16 * v13) = *(_OWORD *)(*((_QWORD *)this + 4) + 8 * v14);
            *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v13) = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v15);
            v12 = *((_DWORD *)this + 7);
          }
          while ( v3 < v12 - 1 );
        }
        --*((_DWORD *)this + 11);
        v16 = (_OWORD *)*((_QWORD *)this + 4);
        *((_DWORD *)this + 7) = v12 - 1;
        v16[v12 - 2] = *v16;
        *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * (unsigned int)(*((_DWORD *)this + 11) - 1)) = **((_QWORD **)this + 6);
      }
    }
  }
}

```

## disassembly

```asm
0x100460890  push    rbx
0x100460892  push    rbp
0x100460893  sub     rsp, 28h
0x100460897  mov     r9d, [rcx+1Ch]
0x10046089b  mov     rbx, rcx
0x10046089e  mov     ebp, 1
0x1004608a3  cmp     r9d, 2
0x1004608a7  jb      loc_10046098F
0x1004608ad  mov     [rsp+38h+arg_8], rdi
0x1004608b2  lea     eax, [r9-1]
0x1004608b6  mov     [rsp+38h+arg_10], r14
0x1004608bb  mov     r14d, ebp
0x1004608be  mov     edi, ebp
0x1004608c0  cmp     eax, ebp
0x1004608c2  jbe     loc_10046094C
0x1004608c8  mov     [rsp+38h+arg_0], rsi
0x1004608cd  mov     [rsp+38h+var_18], r15
0x1004608d2  mov     rax, [rbx+30h]
0x1004608d6  mov     esi, edi
0x1004608d8  lea     r15, ds:0[rsi*8]
0x1004608e0  mov     rcx, [r15+rax]
0x1004608e4  shr     rcx, 20h
0x1004608e8  cmp     cl, 3
0x1004608eb  jz      short loc_1004608F7
0x1004608ed  cmp     cl, 5
0x1004608f0  jz      short loc_1004608F7
0x1004608f2  cmp     cl, 2
0x1004608f5  jnz     short loc_10046090D
0x1004608f7  lea     r9d, [rdi+1]; unsigned int
0x1004608fb  mov     edx, edi; unsigned int
0x1004608fd  lea     r8d, [r14-1]; unsigned int
0x100460901  mov     rcx, rbx; this
0x100460904  call    ?IsOnTheLine@CMetadataFilter@@AEBA_NIII@Z; CMetadataFilter::IsOnTheLine(uint,uint,uint)
0x100460909  test    al, al
0x10046090b  jnz     short loc_100460934
0x10046090d  mov     rcx, [rbx+20h]
0x100460911  add     rsi, rsi
0x100460914  mov     eax, r14d
0x100460917  add     rax, rax
0x10046091a  mov     edx, r14d
0x10046091d  inc     r14d
0x100460920  movups  xmm0, xmmword ptr [rcx+rsi*8]
0x100460924  movups  xmmword ptr [rcx+rax*8], xmm0
0x100460928  mov     rcx, [rbx+30h]
0x10046092c  mov     rax, [r15+rcx]
0x100460930  mov     [rcx+rdx*8], rax
0x100460934  mov     r9d, [rbx+1Ch]
0x100460938  inc     edi
0x10046093a  lea     eax, [r9-1]
0x10046093e  cmp     edi, eax
0x100460940  jb      short loc_1004608D2
0x100460942  mov     r15, [rsp+38h+var_18]
0x100460947  mov     rsi, [rsp+38h+arg_0]
0x10046094c  mov     rdx, [rbx+20h]
0x100460950  lea     ecx, [r9-1]
0x100460954  mov     rdi, [rsp+38h+arg_8]
0x100460959  lea     r9d, [r14+1]
0x10046095d  add     rcx, rcx
0x100460960  mov     eax, r14d
0x100460963  add     rax, rax
0x100460966  mov     r8d, r14d
0x100460969  mov     r14, [rsp+38h+arg_10]
0x10046096e  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x100460972  movups  xmmword ptr [rdx+rax*8], xmm0
0x100460976  mov     eax, [rbx+2Ch]
0x100460979  mov     rdx, [rbx+30h]
0x10046097d  dec     eax
0x10046097f  mov     rcx, [rdx+rax*8]
0x100460983  mov     [rdx+r8*8], rcx
0x100460987  mov     [rbx+1Ch], r9d
0x10046098b  mov     [rbx+2Ch], r9d
0x10046098f  cmp     byte ptr [rbx+11h], 0
0x100460993  jz      loc_100460A3F
0x100460999  cmp     r9d, 4
0x10046099d  jb      loc_100460A3F
0x1004609a3  mov     rax, [rbx+30h]
0x1004609a7  mov     rcx, [rax]
0x1004609aa  shr     rcx, 20h
0x1004609ae  cmp     cl, 3
0x1004609b1  jz      short loc_1004609C1
0x1004609b3  cmp     cl, 5
0x1004609b6  jz      short loc_1004609C1
0x1004609b8  cmp     cl, 2
0x1004609bb  jnz     loc_100460A3F
0x1004609c1  add     r9d, 0FFFFFFFEh; unsigned int
0x1004609c5  mov     r8d, ebp; unsigned int
0x1004609c8  xor     edx, edx; unsigned int
0x1004609ca  mov     rcx, rbx; this
0x1004609cd  call    ?IsOnTheLine@CMetadataFilter@@AEBA_NIII@Z; CMetadataFilter::IsOnTheLine(uint,uint,uint)
0x1004609d2  test    al, al
0x1004609d4  jz      short loc_100460A3F
0x1004609d6  mov     ecx, [rbx+1Ch]
0x1004609d9  lea     eax, [rcx-1]
0x1004609dc  cmp     eax, ebp
0x1004609de  jbe     short loc_100460A15
0x1004609e0  mov     rdx, [rbx+20h]
0x1004609e4  lea     eax, [rbp-1]
0x1004609e7  mov     r8d, eax
0x1004609ea  add     rax, rax
0x1004609ed  mov     ecx, ebp
0x1004609ef  add     rcx, rcx
0x1004609f2  mov     r9d, ebp
0x1004609f5  inc     ebp
0x1004609f7  movups  xmm0, xmmword ptr [rdx+rcx*8]
0x1004609fb  movups  xmmword ptr [rdx+rax*8], xmm0
0x1004609ff  mov     rcx, [rbx+30h]
0x100460a03  mov     rax, [rcx+r9*8]
0x100460a07  mov     [rcx+r8*8], rax
0x100460a0b  mov     ecx, [rbx+1Ch]
0x100460a0e  lea     eax, [rcx-1]
0x100460a11  cmp     ebp, eax
0x100460a13  jb      short loc_1004609E0
0x100460a15  dec     dword ptr [rbx+2Ch]
0x100460a18  lea     eax, [rcx-1]
0x100460a1b  mov     rdx, [rbx+20h]
0x100460a1f  lea     ecx, [rax-1]
0x100460a22  mov     [rbx+1Ch], eax
0x100460a25  add     rcx, rcx
0x100460a28  movups  xmm0, xmmword ptr [rdx]
0x100460a2b  movups  xmmword ptr [rdx+rcx*8], xmm0
0x100460a2f  mov     rdx, [rbx+30h]
0x100460a33  mov     ecx, [rbx+2Ch]
0x100460a36  dec     ecx
0x100460a38  mov     rax, [rdx]
0x100460a3b  mov     [rdx+rcx*8], rax
0x100460a3f  add     rsp, 28h
0x100460a43  pop     rbp
0x100460a44  pop     rbx
0x100460a45  retn
```
