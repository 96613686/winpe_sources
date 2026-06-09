# CGeodeticScannerConstruction::CJunction::Connect(void)

- ea: `0x100465040`
- end: `0x100465261`
- name: `?Connect@CJunction@CGeodeticScannerConstruction@@AEAAXXZ`
- size: `545`
- prototype: `void __fastcall(CGeodeticScannerConstruction::CJunction *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x100462e10`

## callees

- `0x100465040`

## pseudocode

```c
void __fastcall CGeodeticScannerConstruction::CJunction::Connect(CGeodeticScannerConstruction::CJunction *this)
{
  __int64 v1; // r10
  unsigned int v3; // r9d
  unsigned int v4; // eax
  __int64 v5; // r8
  char *v6; // r11
  __int64 v7; // r10
  __int64 v8; // r8
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r10
  unsigned int v13; // eax
  __int64 v14; // r8
  char *v15; // r11
  __int64 v16; // r10
  __int64 v17; // r8
  int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r10
  unsigned int v22; // eax
  __int64 v23; // r8
  char *v24; // r11
  __int64 v25; // r10
  __int64 v26; // r8
  int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r10
  unsigned int v31; // eax
  __int64 v32; // r8
  char *v33; // r11
  __int64 v34; // r10
  __int64 v35; // r8
  int v36; // ecx
  __int64 v37; // rax
  __int64 v38; // rcx
  char v39; // r10
  __int64 v40; // r8
  __int64 v41; // rax

  v1 = *((_QWORD *)this + 2);
  v3 = 1;
  if ( v1 )
  {
    v4 = 1;
    while ( 1 )
    {
      v5 = *((_QWORD *)this + v4 + 6);
      if ( v5 )
        break;
      v4 = ((_BYTE)v4 + 1) & 3;
      if ( v4 == 1 )
        goto LABEL_11;
    }
    *(_QWORD *)(v1 + 48) = v5;
    v6 = (char *)this + 8 * v4;
    v7 = *((_QWORD *)this + 2);
    v8 = *((_QWORD *)v6 + 6);
    v9 = *(_DWORD *)(v7 + 80);
    if ( *(_DWORD *)(v8 + 80) != v9 )
    {
      v10 = *((_QWORD *)v6 + 6);
      do
      {
        *(_DWORD *)(v10 + 80) = v9;
        v10 = *(_QWORD *)(v10 + 56);
      }
      while ( v10 != v8 );
      v11 = *(_QWORD *)(v8 + 56);
      *(_QWORD *)(v8 + 56) = *(_QWORD *)(v7 + 56);
      *(_QWORD *)(v7 + 56) = v11;
    }
    *((_QWORD *)v6 + 6) = 0;
  }
LABEL_11:
  v12 = *((_QWORD *)this + 3);
  if ( v12 )
  {
    v13 = 2;
    while ( 1 )
    {
      v14 = *((_QWORD *)this + v13 + 6);
      if ( v14 )
        break;
      v13 = ((_BYTE)v13 + 1) & 3;
      if ( v13 == 2 )
        goto LABEL_21;
    }
    *(_QWORD *)(v12 + 48) = v14;
    v15 = (char *)this + 8 * v13;
    v16 = *((_QWORD *)this + 3);
    v17 = *((_QWORD *)v15 + 6);
    v18 = *(_DWORD *)(v16 + 80);
    if ( *(_DWORD *)(v17 + 80) != v18 )
    {
      v19 = *((_QWORD *)v15 + 6);
      do
      {
        *(_DWORD *)(v19 + 80) = v18;
        v19 = *(_QWORD *)(v19 + 56);
      }
      while ( v19 != v17 );
      v20 = *(_QWORD *)(v17 + 56);
      *(_QWORD *)(v17 + 56) = *(_QWORD *)(v16 + 56);
      *(_QWORD *)(v16 + 56) = v20;
    }
    *((_QWORD *)v15 + 6) = 0;
  }
LABEL_21:
  v21 = *((_QWORD *)this + 4);
  if ( v21 )
  {
    v22 = 3;
    while ( 1 )
    {
      v23 = *((_QWORD *)this + v22 + 6);
      if ( v23 )
        break;
      v22 = ((_BYTE)v22 + 1) & 3;
      if ( v22 == 3 )
        goto LABEL_31;
    }
    *(_QWORD *)(v21 + 48) = v23;
    v24 = (char *)this + 8 * v22;
    v25 = *((_QWORD *)this + 4);
    v26 = *((_QWORD *)v24 + 6);
    v27 = *(_DWORD *)(v25 + 80);
    if ( *(_DWORD *)(v26 + 80) != v27 )
    {
      v28 = *((_QWORD *)v24 + 6);
      do
      {
        *(_DWORD *)(v28 + 80) = v27;
        v28 = *(_QWORD *)(v28 + 56);
      }
      while ( v28 != v26 );
      v29 = *(_QWORD *)(v26 + 56);
      *(_QWORD *)(v26 + 56) = *(_QWORD *)(v25 + 56);
      *(_QWORD *)(v25 + 56) = v29;
    }
    *((_QWORD *)v24 + 6) = 0;
  }
LABEL_31:
  v30 = *((_QWORD *)this + 5);
  if ( v30 )
  {
    v31 = 0;
    while ( 1 )
    {
      v32 = *((_QWORD *)this + v31 + 6);
      if ( v32 )
        break;
      v31 = ((_BYTE)v31 + 1) & 3;
      if ( !v31 )
        goto LABEL_41;
    }
    *(_QWORD *)(v30 + 48) = v32;
    v33 = (char *)this + 8 * v31;
    v34 = *((_QWORD *)this + 5);
    v35 = *((_QWORD *)v33 + 6);
    v36 = *(_DWORD *)(v34 + 80);
    if ( *(_DWORD *)(v35 + 80) != v36 )
    {
      v37 = *((_QWORD *)v33 + 6);
      do
      {
        *(_DWORD *)(v37 + 80) = v36;
        v37 = *(_QWORD *)(v37 + 56);
      }
      while ( v37 != v35 );
      v38 = *(_QWORD *)(v35 + 56);
      *(_QWORD *)(v35 + 56) = *(_QWORD *)(v34 + 56);
      *(_QWORD *)(v34 + 56) = v38;
    }
    *((_QWORD *)v33 + 6) = 0;
  }
LABEL_41:
  if ( *((_DWORD *)this + 40) > 1u )
  {
    do
    {
      v39 = *((_BYTE *)this + v3 + 168);
      v40 = *((_QWORD *)this + v3 + 10);
      v41 = *((_QWORD *)this + v3 + 9);
      if ( *((_BYTE *)this + v3 + 167) )
        *(_QWORD *)(v41 + 48) = v40;
      else
        *(_QWORD *)(v41 + 64) = v40;
      if ( v39 )
        *(_QWORD *)(v40 + 48) = v41;
      else
        *(_QWORD *)(v40 + 64) = v41;
      v3 += 2;
    }
    while ( v3 < *((_DWORD *)this + 40) );
  }
}

```

## disassembly

```asm
0x100465040  mov     [rsp+arg_0], rbx
0x100465045  mov     r10, [rcx+10h]
0x100465049  xor     ebx, ebx
0x10046504b  mov     rdx, rcx
0x10046504e  lea     r9d, [rbx+1]
0x100465052  test    r10, r10
0x100465055  jz      short loc_1004650C0
0x100465057  mov     eax, r9d
0x10046505a  nop     word ptr [rax+rax+00h]
0x100465060  mov     ecx, eax
0x100465062  mov     r8, [rdx+rcx*8+30h]
0x100465067  test    r8, r8
0x10046506a  jnz     short loc_100465078
0x10046506c  inc     eax
0x10046506e  and     eax, 3
0x100465071  cmp     eax, r9d
0x100465074  jnz     short loc_100465060
0x100465076  jmp     short loc_1004650C0
0x100465078  mov     [r10+30h], r8
0x10046507c  lea     r11, [rdx+rcx*8]
0x100465080  mov     r10, [rdx+10h]
0x100465084  mov     r8, [r11+30h]
0x100465088  mov     ecx, [r10+50h]
0x10046508c  cmp     [r8+50h], ecx
0x100465090  jz      short loc_1004650BC
0x100465092  mov     rax, r8
0x100465095  nop     word ptr [rax+rax+00000000h]
0x1004650a0  mov     [rax+50h], ecx
0x1004650a3  mov     rax, [rax+38h]
0x1004650a7  cmp     rax, r8
0x1004650aa  jnz     short loc_1004650A0
0x1004650ac  mov     rax, [r10+38h]
0x1004650b0  mov     rcx, [r8+38h]
0x1004650b4  mov     [r8+38h], rax
0x1004650b8  mov     [r10+38h], rcx
0x1004650bc  mov     [r11+30h], rbx
0x1004650c0  mov     r10, [rdx+18h]
0x1004650c4  test    r10, r10
0x1004650c7  jz      short loc_100465130
0x1004650c9  mov     eax, 2
0x1004650ce  xchg    ax, ax
0x1004650d0  mov     ecx, eax
0x1004650d2  mov     r8, [rdx+rcx*8+30h]
0x1004650d7  test    r8, r8
0x1004650da  jnz     short loc_1004650E8
0x1004650dc  inc     eax
0x1004650de  and     eax, 3
0x1004650e1  cmp     eax, 2
0x1004650e4  jnz     short loc_1004650D0
0x1004650e6  jmp     short loc_100465130
0x1004650e8  mov     [r10+30h], r8
0x1004650ec  lea     r11, [rdx+rcx*8]
0x1004650f0  mov     r10, [rdx+18h]
0x1004650f4  mov     r8, [r11+30h]
0x1004650f8  mov     ecx, [r10+50h]
0x1004650fc  cmp     [r8+50h], ecx
0x100465100  jz      short loc_10046512C
0x100465102  mov     rax, r8
0x100465105  nop     word ptr [rax+rax+00000000h]
0x100465110  mov     [rax+50h], ecx
0x100465113  mov     rax, [rax+38h]
0x100465117  cmp     rax, r8
0x10046511a  jnz     short loc_100465110
0x10046511c  mov     rax, [r10+38h]
0x100465120  mov     rcx, [r8+38h]
0x100465124  mov     [r8+38h], rax
0x100465128  mov     [r10+38h], rcx
0x10046512c  mov     [r11+30h], rbx
0x100465130  mov     r10, [rdx+20h]
0x100465134  test    r10, r10
0x100465137  jz      short loc_1004651A0
0x100465139  mov     eax, 3
0x10046513e  xchg    ax, ax
0x100465140  mov     ecx, eax
0x100465142  mov     r8, [rdx+rcx*8+30h]
0x100465147  test    r8, r8
0x10046514a  jnz     short loc_100465158
0x10046514c  inc     eax
0x10046514e  and     eax, 3
0x100465151  cmp     eax, 3
0x100465154  jnz     short loc_100465140
0x100465156  jmp     short loc_1004651A0
0x100465158  mov     [r10+30h], r8
0x10046515c  lea     r11, [rdx+rcx*8]
0x100465160  mov     r10, [rdx+20h]
0x100465164  mov     r8, [r11+30h]
0x100465168  mov     ecx, [r10+50h]
0x10046516c  cmp     [r8+50h], ecx
0x100465170  jz      short loc_10046519C
0x100465172  mov     rax, r8
0x100465175  nop     word ptr [rax+rax+00000000h]
0x100465180  mov     [rax+50h], ecx
0x100465183  mov     rax, [rax+38h]
0x100465187  cmp     rax, r8
0x10046518a  jnz     short loc_100465180
0x10046518c  mov     rax, [r10+38h]
0x100465190  mov     rcx, [r8+38h]
0x100465194  mov     [r8+38h], rax
0x100465198  mov     [r10+38h], rcx
0x10046519c  mov     [r11+30h], rbx
0x1004651a0  mov     r10, [rdx+28h]
0x1004651a4  test    r10, r10
0x1004651a7  jz      short loc_100465202
0x1004651a9  mov     eax, ebx
0x1004651ab  nop     dword ptr [rax+rax+00h]
0x1004651b0  mov     ecx, eax
0x1004651b2  mov     r8, [rdx+rcx*8+30h]
0x1004651b7  test    r8, r8
0x1004651ba  jnz     short loc_1004651C5
0x1004651bc  inc     eax
0x1004651be  and     eax, 3
0x1004651c1  jnz     short loc_1004651B0
0x1004651c3  jmp     short loc_100465202
0x1004651c5  mov     [r10+30h], r8
0x1004651c9  lea     r11, [rdx+rcx*8]
0x1004651cd  mov     r10, [rdx+28h]
0x1004651d1  mov     r8, [r11+30h]
0x1004651d5  mov     ecx, [r10+50h]
0x1004651d9  cmp     [r8+50h], ecx
0x1004651dd  jz      short loc_1004651FE
0x1004651df  mov     rax, r8
0x1004651e2  mov     [rax+50h], ecx
0x1004651e5  mov     rax, [rax+38h]
0x1004651e9  cmp     rax, r8
0x1004651ec  jnz     short loc_1004651E2
0x1004651ee  mov     rax, [r10+38h]
0x1004651f2  mov     rcx, [r8+38h]
0x1004651f6  mov     [r8+38h], rax
0x1004651fa  mov     [r10+38h], rcx
0x1004651fe  mov     [r11+30h], rbx
0x100465202  cmp     [rdx+0A0h], r9d
0x100465209  jbe     short loc_10046525B
0x10046520b  nop     dword ptr [rax+rax+00h]
0x100465210  mov     eax, r9d
0x100465213  movzx   r10d, byte ptr [rax+rdx+0A8h]
0x10046521c  mov     r8, [rdx+rax*8+50h]
0x100465221  lea     eax, [r9-1]
0x100465225  mov     ecx, eax
0x100465227  mov     rax, [rdx+rax*8+50h]
0x10046522c  cmp     [rcx+rdx+0A8h], bl
0x100465233  jz      short loc_10046523B
0x100465235  mov     [rax+30h], r8
0x100465239  jmp     short loc_10046523F
0x10046523b  mov     [rax+40h], r8
0x10046523f  test    r10b, r10b
0x100465242  jz      short loc_10046524A
0x100465244  mov     [r8+30h], rax
0x100465248  jmp     short loc_10046524E
0x10046524a  mov     [r8+40h], rax
0x10046524e  add     r9d, 2
0x100465252  cmp     r9d, [rdx+0A0h]
0x100465259  jb      short loc_100465210
0x10046525b  mov     rbx, [rsp+arg_0]
0x100465260  retn
```
