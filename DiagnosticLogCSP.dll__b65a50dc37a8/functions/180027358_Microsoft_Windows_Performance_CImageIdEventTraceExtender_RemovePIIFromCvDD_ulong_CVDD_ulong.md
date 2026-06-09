# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(ulong,_CVDD *,ulong *)

- ea: `0x180027358`
- end: `0x1800274ff`
- name: `?RemovePIIFromCvDD@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAT_CVDD@@PEAK@Z`
- size: `423`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, unsigned int, union _CVDD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021250`

## callees

- `0x180002d31`
- `0x180027358`

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
0x180027358  push    rbx
0x18002735a  push    rbp
0x18002735b  push    rsi
0x18002735c  push    rdi
0x18002735d  push    r12
0x18002735f  push    r13
0x180027361  push    r14
0x180027363  push    r15
0x180027365  sub     rsp, 28h
0x180027369  xor     r13d, r13d
0x18002736c  mov     r14, r9
0x18002736f  mov     r12, r8
0x180027372  mov     r15d, edx
0x180027375  mov     esi, r13d
0x180027378  test    edx, edx
0x18002737a  jz      loc_1800274E4
0x180027380  mov     ebp, esi
0x180027382  cmp     dword ptr [r14+rbp*4], 4
0x180027387  jb      loc_1800274D9
0x18002738d  cmp     dword ptr [r14+rbp*4], 628h
0x180027395  ja      loc_1800274F8
0x18002739b  imul    rbx, rbp, 628h
0x1800273a2  add     rbx, r12
0x1800273a5  mov     ecx, [rbx]
0x1800273a7  sub     ecx, 1
0x1800273aa  jz      loc_18002747D
0x1800273b0  sub     ecx, 1
0x1800273b3  jz      loc_18002747D
0x1800273b9  sub     ecx, 1
0x1800273bc  jz      short loc_1800273D2
0x1800273be  sub     ecx, 3031424Bh
0x1800273c4  jz      short loc_18002742D
0x1800273c6  cmp     ecx, 23131104h
0x1800273cc  jnz     loc_1800274D9
0x1800273d2  lea     rcx, [rbx+18h]; void *
0x1800273d6  mov     rdi, r13
0x1800273d9  lea     rdx, [rcx+30Ch]
0x1800273e0  mov     rax, rcx
0x1800273e3  cmp     rcx, rdx
0x1800273e6  jnb     loc_1800274D9
0x1800273ec  cmp     [rax], r13b
0x1800273ef  jz      short loc_180027400
0x1800273f1  cmp     byte ptr [rax], 5Ch ; '\'
0x1800273f4  cmovz   rdi, rax
0x1800273f8  inc     rax
0x1800273fb  cmp     rax, rdx
0x1800273fe  jb      short loc_1800273EC
0x180027400  test    rdi, rdi
0x180027403  jz      loc_1800274D9
0x180027409  mov     r8d, ebx
0x18002740c  lea     rdx, [rdi+1]; Src
0x180027410  sub     r8d, edi
0x180027413  add     r8d, 323h; Size
0x18002741a  call    memmove_0
0x18002741f  sub     ebx, edi
0x180027421  add     ebx, 17h
0x180027424  add     [r14+rbp*4], ebx
0x180027428  jmp     loc_1800274D9
0x18002742d  lea     rcx, [rbx+10h]; void *
0x180027431  mov     rdi, r13
0x180027434  lea     rdx, [rcx+104h]
0x18002743b  mov     rax, rcx
0x18002743e  cmp     rcx, rdx
0x180027441  jnb     loc_1800274D9
0x180027447  cmp     [rax], r13b
0x18002744a  jz      short loc_18002745B
0x18002744c  cmp     byte ptr [rax], 5Ch ; '\'
0x18002744f  cmovz   rdi, rax
0x180027453  inc     rax
0x180027456  cmp     rax, rdx
0x180027459  jb      short loc_180027447
0x18002745b  test    rdi, rdi
0x18002745e  jz      short loc_1800274D9
0x180027460  mov     r8d, ebx
0x180027463  lea     rdx, [rdi+1]; Src
0x180027467  sub     r8d, edi
0x18002746a  add     r8d, 113h; Size
0x180027471  call    memmove_0
0x180027476  sub     ebx, edi
0x180027478  add     ebx, 0Fh
0x18002747b  jmp     short loc_180027424
0x18002747d  lea     rcx, [rbx+10h]; void *
0x180027481  mov     rdx, r13
0x180027484  lea     r8, [rcx+618h]
0x18002748b  mov     rax, rcx
0x18002748e  cmp     rcx, r8
0x180027491  jnb     short loc_1800274D9
0x180027493  cmp     [rax], r13w
0x180027497  jz      short loc_1800274AA
0x180027499  cmp     word ptr [rax], 5Ch ; '\'
0x18002749d  cmovz   rdx, rax
0x1800274a1  add     rax, 2
0x1800274a5  cmp     rax, r8
0x1800274a8  jb      short loc_180027493
0x1800274aa  test    rdx, rdx
0x1800274ad  jz      short loc_1800274D9
0x1800274af  mov     rax, rdx
0x1800274b2  mov     r8d, 618h
0x1800274b8  sub     rax, rbx
0x1800274bb  add     rdx, 2; Src
0x1800274bf  sub     rax, 10h
0x1800274c3  sar     rax, 1
0x1800274c6  lea     ebx, ds:2[rax*2]
0x1800274cd  sub     r8d, ebx; Size
0x1800274d0  call    memmove_0
0x1800274d5  sub     [r14+rbp*4], ebx
0x1800274d9  inc     esi
0x1800274db  cmp     esi, r15d
0x1800274de  jb      loc_180027380
0x1800274e4  xor     eax, eax
0x1800274e6  add     rsp, 28h
0x1800274ea  pop     r15
0x1800274ec  pop     r14
0x1800274ee  pop     r13
0x1800274f0  pop     r12
0x1800274f2  pop     rdi
0x1800274f3  pop     rsi
0x1800274f4  pop     rbp
0x1800274f5  pop     rbx
0x1800274f6  retn
0x1800274f8  mov     eax, 8000FFFFh
0x1800274fd  jmp     short loc_1800274E6
```
