# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(ulong,_CVDD *,ulong *)

- ea: `0x1800150b8`
- end: `0x18001525e`
- name: `?RemovePIIFromCvDD@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAT_CVDD@@PEAK@Z`
- size: `422`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, union _CVDD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f5dc`

## callees

- `0x1800027bd`
- `0x1800150b8`

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
0x1800150b8  push    rbx
0x1800150ba  push    rbp
0x1800150bb  push    rsi
0x1800150bc  push    rdi
0x1800150bd  push    r12
0x1800150bf  push    r13
0x1800150c1  push    r14
0x1800150c3  push    r15
0x1800150c5  sub     rsp, 28h
0x1800150c9  xor     r13d, r13d
0x1800150cc  mov     r14, r9
0x1800150cf  mov     r12, r8
0x1800150d2  mov     r15d, edx
0x1800150d5  mov     esi, r13d
0x1800150d8  test    edx, edx
0x1800150da  jz      loc_180015244
0x1800150e0  mov     ebp, esi
0x1800150e2  cmp     dword ptr [r14+rbp*4], 4
0x1800150e7  jb      loc_180015239
0x1800150ed  cmp     dword ptr [r14+rbp*4], 628h
0x1800150f5  ja      loc_180015257
0x1800150fb  imul    rbx, rbp, 628h
0x180015102  add     rbx, r12
0x180015105  mov     ecx, [rbx]
0x180015107  sub     ecx, 1
0x18001510a  jz      loc_1800151DD
0x180015110  sub     ecx, 1
0x180015113  jz      loc_1800151DD
0x180015119  sub     ecx, 1
0x18001511c  jz      short loc_180015132
0x18001511e  sub     ecx, 3031424Bh
0x180015124  jz      short loc_18001518D
0x180015126  cmp     ecx, 23131104h
0x18001512c  jnz     loc_180015239
0x180015132  lea     rcx, [rbx+18h]; void *
0x180015136  mov     rdi, r13
0x180015139  lea     rdx, [rcx+30Ch]
0x180015140  mov     rax, rcx
0x180015143  cmp     rcx, rdx
0x180015146  jnb     loc_180015239
0x18001514c  cmp     [rax], r13b
0x18001514f  jz      short loc_180015160
0x180015151  cmp     byte ptr [rax], 5Ch ; '\'
0x180015154  cmovz   rdi, rax
0x180015158  inc     rax
0x18001515b  cmp     rax, rdx
0x18001515e  jb      short loc_18001514C
0x180015160  test    rdi, rdi
0x180015163  jz      loc_180015239
0x180015169  mov     r8d, ebx
0x18001516c  lea     rdx, [rdi+1]; Src
0x180015170  sub     r8d, edi
0x180015173  add     r8d, 323h; Size
0x18001517a  call    memmove_0
0x18001517f  sub     ebx, edi
0x180015181  add     ebx, 17h
0x180015184  add     [r14+rbp*4], ebx
0x180015188  jmp     loc_180015239
0x18001518d  lea     rcx, [rbx+10h]; void *
0x180015191  mov     rdi, r13
0x180015194  lea     rdx, [rcx+104h]
0x18001519b  mov     rax, rcx
0x18001519e  cmp     rcx, rdx
0x1800151a1  jnb     loc_180015239
0x1800151a7  cmp     [rax], r13b
0x1800151aa  jz      short loc_1800151BB
0x1800151ac  cmp     byte ptr [rax], 5Ch ; '\'
0x1800151af  cmovz   rdi, rax
0x1800151b3  inc     rax
0x1800151b6  cmp     rax, rdx
0x1800151b9  jb      short loc_1800151A7
0x1800151bb  test    rdi, rdi
0x1800151be  jz      short loc_180015239
0x1800151c0  mov     r8d, ebx
0x1800151c3  lea     rdx, [rdi+1]; Src
0x1800151c7  sub     r8d, edi
0x1800151ca  add     r8d, 113h; Size
0x1800151d1  call    memmove_0
0x1800151d6  sub     ebx, edi
0x1800151d8  add     ebx, 0Fh
0x1800151db  jmp     short loc_180015184
0x1800151dd  lea     rcx, [rbx+10h]; void *
0x1800151e1  mov     rdx, r13
0x1800151e4  lea     r8, [rcx+618h]
0x1800151eb  mov     rax, rcx
0x1800151ee  cmp     rcx, r8
0x1800151f1  jnb     short loc_180015239
0x1800151f3  cmp     [rax], r13w
0x1800151f7  jz      short loc_18001520A
0x1800151f9  cmp     word ptr [rax], 5Ch ; '\'
0x1800151fd  cmovz   rdx, rax
0x180015201  add     rax, 2
0x180015205  cmp     rax, r8
0x180015208  jb      short loc_1800151F3
0x18001520a  test    rdx, rdx
0x18001520d  jz      short loc_180015239
0x18001520f  mov     rax, rdx
0x180015212  mov     r8d, 618h
0x180015218  sub     rax, rbx
0x18001521b  add     rdx, 2; Src
0x18001521f  sub     rax, 10h
0x180015223  sar     rax, 1
0x180015226  lea     ebx, ds:2[rax*2]
0x18001522d  sub     r8d, ebx; Size
0x180015230  call    memmove_0
0x180015235  sub     [r14+rbp*4], ebx
0x180015239  inc     esi
0x18001523b  cmp     esi, r15d
0x18001523e  jb      loc_1800150E0
0x180015244  xor     eax, eax
0x180015246  add     rsp, 28h
0x18001524a  pop     r15
0x18001524c  pop     r14
0x18001524e  pop     r13
0x180015250  pop     r12
0x180015252  pop     rdi
0x180015253  pop     rsi
0x180015254  pop     rbp
0x180015255  pop     rbx
0x180015256  retn
0x180015257  mov     eax, 8000FFFFh
0x18001525c  jmp     short loc_180015246
```
