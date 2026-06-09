# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(ulong,_CVDD *,ulong *)

- ea: `0x180026188`
- end: `0x18002632e`
- name: `?RemovePIIFromCvDD@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAT_CVDD@@PEAK@Z`
- size: `422`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, union _CVDD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020204`

## callees

- `0x180002d01`
- `0x180026188`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        unsigned int a2,
        union _CVDD *a3,
        unsigned int *a4)
{
  unsigned int v7; // esi
  char *v8; // rbx
  char *v9; // rdi
  char *v10; // rax
  int v11; // ebx
  char *v12; // rdi
  char *v13; // rax
  void *v14; // rcx
  char *v15; // rdx
  char *v16; // rax
  int v17; // ebx

  v7 = 0;
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    if ( a4[v7] < 4 )
      goto LABEL_31;
    if ( a4[v7] > 0x628 )
      return 2147549183LL;
    v8 = (char *)a3 + 1576 * v7;
    switch ( *(_DWORD *)v8 )
    {
      case 1:
      case 2:
        v14 = v8 + 16;
        v15 = 0;
        v16 = v8 + 16;
        if ( v8 + 16 < v8 + 1576 )
        {
          do
          {
            if ( !*(_WORD *)v16 )
              break;
            if ( *(_WORD *)v16 == 92 )
              v15 = v16;
            v16 += 2;
          }
          while ( v16 < v8 + 1576 );
          if ( v15 )
          {
            v17 = 2 * ((v15 - v8 - 16) >> 1) + 2;
            memmove_0(v14, v15 + 2, (unsigned int)(1560 - v17));
            a4[v7] -= v17;
          }
        }
        break;
      case 3:
LABEL_9:
        v9 = 0;
        v10 = v8 + 24;
        if ( v8 + 24 >= v8 + 804 )
          break;
        do
        {
          if ( !*v10 )
            break;
          if ( *v10 == 92 )
            v9 = v10;
          ++v10;
        }
        while ( v10 < v8 + 804 );
        if ( !v9 )
          break;
        memmove_0(v8 + 24, v9 + 1, (unsigned int)((_DWORD)v8 - (_DWORD)v9 + 803));
        v11 = (_DWORD)v8 - (_DWORD)v9 + 23;
        goto LABEL_16;
      case 0x3031424E:
        v12 = 0;
        v13 = v8 + 16;
        if ( v8 + 16 >= v8 + 276 )
          break;
        do
        {
          if ( !*v13 )
            break;
          if ( *v13 == 92 )
            v12 = v13;
          ++v13;
        }
        while ( v13 < v8 + 276 );
        if ( !v12 )
          break;
        memmove_0(v8 + 16, v12 + 1, (unsigned int)((_DWORD)v8 - (_DWORD)v12 + 275));
        v11 = (_DWORD)v8 - (_DWORD)v12 + 15;
LABEL_16:
        a4[v7] += v11;
        break;
      case 0x53445352:
        goto LABEL_9;
    }
LABEL_31:
    if ( ++v7 >= a2 )
      return 0;
  }
}

```

## disassembly

```asm
0x180026188  push    rbx
0x18002618a  push    rbp
0x18002618b  push    rsi
0x18002618c  push    rdi
0x18002618d  push    r12
0x18002618f  push    r13
0x180026191  push    r14
0x180026193  push    r15
0x180026195  sub     rsp, 28h
0x180026199  xor     r13d, r13d
0x18002619c  mov     r14, r9
0x18002619f  mov     r12, r8
0x1800261a2  mov     r15d, edx
0x1800261a5  mov     esi, r13d
0x1800261a8  test    edx, edx
0x1800261aa  jz      loc_180026314
0x1800261b0  mov     ebp, esi
0x1800261b2  cmp     dword ptr [r14+rbp*4], 4
0x1800261b7  jb      loc_180026309
0x1800261bd  cmp     dword ptr [r14+rbp*4], 628h
0x1800261c5  ja      loc_180026327
0x1800261cb  imul    rbx, rbp, 628h
0x1800261d2  add     rbx, r12
0x1800261d5  mov     ecx, [rbx]
0x1800261d7  sub     ecx, 1
0x1800261da  jz      loc_1800262AD
0x1800261e0  sub     ecx, 1
0x1800261e3  jz      loc_1800262AD
0x1800261e9  sub     ecx, 1
0x1800261ec  jz      short loc_180026202
0x1800261ee  sub     ecx, 3031424Bh
0x1800261f4  jz      short loc_18002625D
0x1800261f6  cmp     ecx, 23131104h
0x1800261fc  jnz     loc_180026309
0x180026202  lea     rcx, [rbx+18h]; void *
0x180026206  mov     rdi, r13
0x180026209  lea     rdx, [rcx+30Ch]
0x180026210  mov     rax, rcx
0x180026213  cmp     rcx, rdx
0x180026216  jnb     loc_180026309
0x18002621c  cmp     [rax], r13b
0x18002621f  jz      short loc_180026230
0x180026221  cmp     byte ptr [rax], 5Ch ; '\'
0x180026224  cmovz   rdi, rax
0x180026228  inc     rax
0x18002622b  cmp     rax, rdx
0x18002622e  jb      short loc_18002621C
0x180026230  test    rdi, rdi
0x180026233  jz      loc_180026309
0x180026239  mov     r8d, ebx
0x18002623c  lea     rdx, [rdi+1]; Src
0x180026240  sub     r8d, edi
0x180026243  add     r8d, 323h; Size
0x18002624a  call    memmove_0
0x18002624f  sub     ebx, edi
0x180026251  add     ebx, 17h
0x180026254  add     [r14+rbp*4], ebx
0x180026258  jmp     loc_180026309
0x18002625d  lea     rcx, [rbx+10h]; void *
0x180026261  mov     rdi, r13
0x180026264  lea     rdx, [rcx+104h]
0x18002626b  mov     rax, rcx
0x18002626e  cmp     rcx, rdx
0x180026271  jnb     loc_180026309
0x180026277  cmp     [rax], r13b
0x18002627a  jz      short loc_18002628B
0x18002627c  cmp     byte ptr [rax], 5Ch ; '\'
0x18002627f  cmovz   rdi, rax
0x180026283  inc     rax
0x180026286  cmp     rax, rdx
0x180026289  jb      short loc_180026277
0x18002628b  test    rdi, rdi
0x18002628e  jz      short loc_180026309
0x180026290  mov     r8d, ebx
0x180026293  lea     rdx, [rdi+1]; Src
0x180026297  sub     r8d, edi
0x18002629a  add     r8d, 113h; Size
0x1800262a1  call    memmove_0
0x1800262a6  sub     ebx, edi
0x1800262a8  add     ebx, 0Fh
0x1800262ab  jmp     short loc_180026254
0x1800262ad  lea     rcx, [rbx+10h]; void *
0x1800262b1  mov     rdx, r13
0x1800262b4  lea     r8, [rcx+618h]
0x1800262bb  mov     rax, rcx
0x1800262be  cmp     rcx, r8
0x1800262c1  jnb     short loc_180026309
0x1800262c3  cmp     [rax], r13w
0x1800262c7  jz      short loc_1800262DA
0x1800262c9  cmp     word ptr [rax], 5Ch ; '\'
0x1800262cd  cmovz   rdx, rax
0x1800262d1  add     rax, 2
0x1800262d5  cmp     rax, r8
0x1800262d8  jb      short loc_1800262C3
0x1800262da  test    rdx, rdx
0x1800262dd  jz      short loc_180026309
0x1800262df  mov     rax, rdx
0x1800262e2  mov     r8d, 618h
0x1800262e8  sub     rax, rbx
0x1800262eb  add     rdx, 2; Src
0x1800262ef  sub     rax, 10h
0x1800262f3  sar     rax, 1
0x1800262f6  lea     ebx, ds:2[rax*2]
0x1800262fd  sub     r8d, ebx; Size
0x180026300  call    memmove_0
0x180026305  sub     [r14+rbp*4], ebx
0x180026309  inc     esi
0x18002630b  cmp     esi, r15d
0x18002630e  jb      loc_1800261B0
0x180026314  xor     eax, eax
0x180026316  add     rsp, 28h
0x18002631a  pop     r15
0x18002631c  pop     r14
0x18002631e  pop     r13
0x180026320  pop     r12
0x180026322  pop     rdi
0x180026323  pop     rsi
0x180026324  pop     rbp
0x180026325  pop     rbx
0x180026326  retn
0x180026327  mov     eax, 8000FFFFh
0x18002632c  jmp     short loc_180026316
```
