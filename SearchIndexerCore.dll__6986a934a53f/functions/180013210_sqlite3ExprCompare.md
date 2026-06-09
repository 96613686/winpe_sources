# sqlite3ExprCompare

- ea: `0x180013210`
- end: `0x180013516`
- name: `sqlite3ExprCompare`
- size: `774`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011d40`
- `0x180012200`
- `0x180013210`
- `0x18001354c`
- `0x1800192e0`
- `0x1800312e0`
- `0x18004dcc8`
- `0x180053b88`
- `0x180057c70`
- `0x180060400`
- `0x1800617f4`
- `0x180064ab0`
- `0x180066270`
- `0x18006d180`
- `0x18006e90c`
- `0x180076264`
- `0x18007e4d0`
- `0x18008e550`
- `0x18008ed70`
- `0x180098a50`
- `0x1800a39a0`
- `0x1800a6344`

## callees

- `0x18000a710`
- `0x180013210`
- `0x180053f60`
- `0x18005737c`
- `0x180076264`

## pseudocode

```c
__int64 __fastcall sqlite3ExprCompare(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v8; // r15d
  char v9; // cl
  unsigned __int8 *v11; // r8
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // edx
  int v15; // ecx
  bool v16; // zf
  _DWORD *v17; // rbp
  _DWORD *v18; // rsi
  int v19; // eax
  int v20; // eax
  bool v21; // zf
  int i; // r14d
  __int64 v23; // rdx

  if ( !a2 || !a3 )
    return a2 != a3 ? 2 : 0;
  if ( a1 && *(_BYTE *)a2 == 0x9C && (unsigned int)exprCompareVariable(a1, a2, a3) )
    return 0;
  v8 = *(_DWORD *)(a3 + 4) | *(_DWORD *)(a2 + 4);
  if ( (v8 & 0x800) != 0 )
  {
    if ( (*(_DWORD *)(a3 + 4) & *(_DWORD *)(a2 + 4) & 0x800) == 0 )
      return 2;
    v21 = *(_DWORD *)(a2 + 8) == *(_DWORD *)(a3 + 8);
LABEL_58:
    if ( v21 )
      return 0;
    return 2;
  }
  v9 = *(_BYTE *)a2;
  if ( *(_BYTE *)a2 == *(_BYTE *)a3 && v9 != 71 )
  {
LABEL_12:
    v11 = *(unsigned __int8 **)(a2 + 8);
    if ( !v11 )
      goto LABEL_23;
    if ( ((v9 + 88) & 0xFB) != 0 )
    {
      if ( v9 == 121 )
        return 0;
      if ( v9 != 113 )
      {
        v12 = *(_QWORD *)(a3 + 8);
        if ( v12 && ((v9 + 89) & 0xFD) != 0 )
        {
          v13 = v12 - (_QWORD)v11;
          do
          {
            v14 = v11[v13];
            v15 = *v11 - v14;
            if ( v15 )
              break;
            ++v11;
          }
          while ( v14 );
          v16 = v15 == 0;
LABEL_22:
          if ( !v16 )
            return 2;
        }
LABEL_23:
        if ( ((*(_DWORD *)(a2 + 4) ^ *(_DWORD *)(a3 + 4)) & 0x404) != 0 )
          return 2;
        if ( (v8 & 0x10000) != 0 )
          return 0;
        if ( (v8 & 0x1000) != 0
          || (v8 & 0x20) == 0 && (unsigned int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 16), *(_QWORD *)(a3 + 16), a4)
          || (unsigned int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 24), *(_QWORD *)(a3 + 24), a4) )
        {
          return 2;
        }
        v17 = *(_DWORD **)(a2 + 32);
        v18 = *(_DWORD **)(a3 + 32);
        if ( v17 )
        {
          if ( !v18 || *v17 != *v18 )
            return 2;
          for ( i = 0; i < *v17; ++i )
          {
            v23 = 8LL * i;
            if ( LOBYTE(v17[v23 + 6]) != LOBYTE(v18[v23 + 6])
              || (unsigned int)sqlite3ExprCompare(0, *(_QWORD *)&v17[v23 + 2], *(_QWORD *)&v18[v23 + 2], a4) )
            {
              return 2;
            }
          }
        }
        else if ( v18 )
        {
          return 2;
        }
        if ( *(_BYTE *)a2 == 117 || *(_BYTE *)a2 == 0xAA || (v8 & 0x4000) != 0 )
          return 0;
        if ( *(_WORD *)(a2 + 48) != *(_WORD *)(a3 + 48)
          || *(_BYTE *)(a2 + 2) != *(_BYTE *)(a3 + 2) && *(_BYTE *)a2 == 0xAF )
        {
          return 2;
        }
        if ( *(_BYTE *)a2 == 49 )
          return 0;
        v19 = *(_DWORD *)(a2 + 44);
        if ( v19 == *(_DWORD *)(a3 + 44) )
          return 0;
        v21 = v19 == a4;
        goto LABEL_58;
      }
      v20 = sqlite3_stricmp(*(_QWORD *)(a2 + 8), *(_QWORD *)(a3 + 8));
    }
    else
    {
      if ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(a2 + 8), *(_QWORD *)(a3 + 8))
        || ((*(_DWORD *)(a2 + 4) & 0x1000000) != 0) != (*(_BYTE *)(a3 + 7) & 1) )
      {
        return 2;
      }
      if ( (*(_DWORD *)(a2 + 4) & 0x1000000) == 0 )
        goto LABEL_23;
      v20 = sqlite3WindowCompare(a1, *(_QWORD *)(a2 + 64), *(_QWORD *)(a3 + 64), 1);
    }
    v16 = v20 == 0;
    goto LABEL_22;
  }
  if ( (v9 != 113 || (int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 16), a3, a4) >= 2)
    && (*(_BYTE *)a3 != 113 || (int)sqlite3ExprCompare(a1, a2, *(_QWORD *)(a3 + 16), a4) >= 2) )
  {
    v9 = -87;
    if ( *(_BYTE *)a2 != 0xA9 || *(_BYTE *)a3 != 0xA7 || *(int *)(a3 + 44) >= 0 || *(_DWORD *)(a2 + 44) != a4 )
      return 2;
    goto LABEL_12;
  }
  return 1;
}

```

## disassembly

```asm
0x180013210  push    rbx
0x180013212  push    rbp
0x180013213  push    rsi
0x180013214  push    rdi
0x180013215  push    r12
0x180013217  push    r14
0x180013219  push    r15
0x18001321b  sub     rsp, 20h
0x18001321f  mov     r12d, r9d
0x180013222  mov     rbx, r8
0x180013225  mov     rdi, rdx
0x180013228  mov     rsi, rcx
0x18001322b  test    rdx, rdx
0x18001322e  jz      short loc_18001327F
0x180013230  test    rbx, rbx
0x180013233  jz      short loc_18001327F
0x180013235  test    rcx, rcx
0x180013238  jnz     loc_1800133CD
0x18001323e  mov     eax, [rdi+4]
0x180013241  mov     r15d, eax
0x180013244  or      r15d, [rbx+4]
0x180013248  bt      r15d, 0Bh
0x18001324d  jb      loc_18001348E
0x180013253  mov     cl, [rdi]
0x180013255  mov     bpl, 71h ; 'q'
0x180013258  cmp     cl, [rbx]
0x18001325a  jz      short loc_180013299
0x18001325c  cmp     cl, bpl
0x18001325f  jz      loc_1800133B0
0x180013265  cmp     [rbx], bpl
0x180013268  jz      loc_1800133E5
0x18001326e  mov     cl, 0A9h
0x180013270  cmp     [rdi], cl
0x180013272  jz      loc_18001346C
0x180013278  mov     eax, 2
0x18001327d  jmp     short loc_18001328A
0x18001327f  sub     rbx, rdi
0x180013282  neg     rbx
0x180013285  sbb     eax, eax
0x180013287  and     eax, 2
0x18001328a  add     rsp, 20h
0x18001328e  pop     r15
0x180013290  pop     r14
0x180013292  pop     r12
0x180013294  pop     rdi
0x180013295  pop     rsi
0x180013296  pop     rbp
0x180013297  pop     rbx
0x180013298  retn
0x180013299  cmp     cl, 47h ; 'G'
0x18001329c  jz      short loc_18001325C
0x18001329e  mov     r8, [rdi+8]
0x1800132a2  test    r8, r8
0x1800132a5  jz      short loc_1800132F0
0x1800132a7  lea     eax, [rcx+58h]
0x1800132aa  test    al, 0FBh
0x1800132ac  jz      loc_18001340A
0x1800132b2  cmp     cl, 79h ; 'y'
0x1800132b5  jz      loc_1800133A9
0x1800132bb  cmp     cl, bpl
0x1800132be  jz      loc_180013459
0x1800132c4  mov     rax, [rbx+8]
0x1800132c8  test    rax, rax
0x1800132cb  jz      short loc_1800132F0
0x1800132cd  add     cl, 59h ; 'Y'
0x1800132d0  test    cl, 0FDh
0x1800132d3  jz      short loc_1800132F0
0x1800132d5  sub     rax, r8
0x1800132d8  movzx   ecx, byte ptr [r8]
0x1800132dc  movzx   edx, byte ptr [r8+rax]
0x1800132e1  sub     ecx, edx
0x1800132e3  jnz     short loc_1800132EC
0x1800132e5  inc     r8
0x1800132e8  test    edx, edx
0x1800132ea  jnz     short loc_1800132D8
0x1800132ec  test    ecx, ecx
0x1800132ee  jnz     short loc_180013278
0x1800132f0  mov     eax, [rbx+4]
0x1800132f3  xor     eax, [rdi+4]
0x1800132f6  test    eax, 404h
0x1800132fb  jnz     loc_180013278
0x180013301  bt      r15d, 10h
0x180013306  jb      loc_1800133A9
0x18001330c  bt      r15d, 0Ch
0x180013311  jb      loc_180013278
0x180013317  test    r15b, 20h
0x18001331b  jnz     short loc_180013338
0x18001331d  mov     r8, [rbx+10h]
0x180013321  mov     r9d, r12d
0x180013324  mov     rdx, [rdi+10h]
0x180013328  mov     rcx, rsi
0x18001332b  call    sqlite3ExprCompare
0x180013330  test    eax, eax
0x180013332  jnz     loc_180013278
0x180013338  mov     r8, [rbx+18h]
0x18001333c  mov     r9d, r12d
0x18001333f  mov     rdx, [rdi+18h]
0x180013343  mov     rcx, rsi
0x180013346  call    sqlite3ExprCompare
0x18001334b  test    eax, eax
0x18001334d  jnz     loc_180013278
0x180013353  mov     rbp, [rdi+20h]
0x180013357  mov     rsi, [rbx+20h]
0x18001335b  test    rbp, rbp
0x18001335e  jnz     loc_1800134BF
0x180013364  test    rsi, rsi
0x180013367  jnz     loc_180013278
0x18001336d  cmp     byte ptr [rdi], 75h ; 'u'
0x180013370  jz      short loc_1800133A9
0x180013372  cmp     byte ptr [rdi], 0AAh
0x180013375  jz      short loc_1800133A9
0x180013377  bt      r15d, 0Eh
0x18001337c  jb      short loc_1800133A9
0x18001337e  movzx   eax, word ptr [rbx+30h]
0x180013382  cmp     [rdi+30h], ax
0x180013386  jnz     loc_180013278
0x18001338c  mov     al, [rbx+2]
0x18001338f  cmp     [rdi+2], al
0x180013392  jnz     loc_1800134AC
0x180013398  cmp     byte ptr [rdi], 31h ; '1'
0x18001339b  jz      short loc_1800133A9
0x18001339d  mov     eax, [rdi+2Ch]
0x1800133a0  cmp     eax, [rbx+2Ch]
0x1800133a3  jnz     loc_1800134BA
0x1800133a9  xor     eax, eax
0x1800133ab  jmp     loc_18001328A
0x1800133b0  mov     rdx, [rdi+10h]
0x1800133b4  mov     r9d, r12d
0x1800133b7  mov     r8, rbx
0x1800133ba  mov     rcx, rsi
0x1800133bd  call    sqlite3ExprCompare
0x1800133c2  cmp     eax, 2
0x1800133c5  jge     loc_180013265
0x1800133cb  jmp     short loc_180013400
0x1800133cd  cmp     byte ptr [rdx], 9Ch
0x1800133d0  jnz     loc_18001323E
0x1800133d6  call    exprCompareVariable
0x1800133db  test    eax, eax
0x1800133dd  jz      loc_18001323E
0x1800133e3  jmp     short loc_1800133A9
0x1800133e5  mov     r8, [rbx+10h]
0x1800133e9  mov     r9d, r12d
0x1800133ec  mov     rdx, rdi
0x1800133ef  mov     rcx, rsi
0x1800133f2  call    sqlite3ExprCompare
0x1800133f7  cmp     eax, 2
0x1800133fa  jge     loc_18001326E
0x180013400  mov     eax, 1
0x180013405  jmp     loc_18001328A
0x18001340a  mov     rdx, [rbx+8]
0x18001340e  mov     rcx, r8
0x180013411  call    sqlite3StrICmp
0x180013416  test    eax, eax
0x180013418  jnz     loc_180013278
0x18001341e  movzx   ecx, byte ptr [rbx+7]
0x180013422  mov     edx, [rdi+4]
0x180013425  and     ecx, 1
0x180013428  and     edx, 1000000h
0x18001342e  setnz   al
0x180013431  cmp     eax, ecx
0x180013433  jnz     loc_180013278
0x180013439  test    edx, edx
0x18001343b  jz      loc_1800132F0
0x180013441  mov     r8, [rbx+40h]
0x180013445  mov     r9d, 1
0x18001344b  mov     rdx, [rdi+40h]
0x18001344f  mov     rcx, rsi
0x180013452  call    sqlite3WindowCompare
0x180013457  jmp     short loc_180013465
0x180013459  mov     rdx, [rbx+8]
0x18001345d  mov     rcx, r8
0x180013460  call    sqlite3_stricmp
0x180013465  test    eax, eax
0x180013467  jmp     loc_1800132EE
0x18001346c  cmp     byte ptr [rbx], 0A7h
0x18001346f  jnz     loc_180013278
0x180013475  cmp     dword ptr [rbx+2Ch], 0
0x180013479  jge     loc_180013278
0x18001347f  cmp     [rdi+2Ch], r12d
0x180013483  jnz     loc_180013278
0x180013489  jmp     loc_18001329E
0x18001348e  and     eax, [rbx+4]
0x180013491  bt      eax, 0Bh
0x180013495  jnb     loc_180013278
0x18001349b  mov     eax, [rbx+8]
0x18001349e  cmp     [rdi+8], eax
0x1800134a1  jnz     loc_180013278
0x1800134a7  jmp     loc_1800133A9
0x1800134ac  cmp     byte ptr [rdi], 0AFh
0x1800134af  jnz     loc_180013398
0x1800134b5  jmp     loc_180013278
0x1800134ba  cmp     eax, r12d
0x1800134bd  jmp     short loc_1800134A1
0x1800134bf  test    rsi, rsi
0x1800134c2  jz      loc_180013278
0x1800134c8  mov     eax, [rsi]
0x1800134ca  cmp     [rbp+0], eax
0x1800134cd  jnz     loc_180013278
0x1800134d3  xor     r14d, r14d
0x1800134d6  cmp     r14d, [rbp+0]
0x1800134da  jge     loc_18001336D
0x1800134e0  movsxd  rdx, r14d
0x1800134e3  shl     rdx, 5
0x1800134e7  mov     al, [rdx+rsi+18h]
0x1800134eb  cmp     [rdx+rbp+18h], al
0x1800134ef  jnz     loc_180013278
0x1800134f5  mov     r8, [rdx+rsi+8]
0x1800134fa  mov     r9d, r12d
0x1800134fd  mov     rdx, [rdx+rbp+8]
0x180013502  xor     ecx, ecx
0x180013504  call    sqlite3ExprCompare
0x180013509  test    eax, eax
0x18001350b  jnz     loc_180013278
0x180013511  inc     r14d
0x180013514  jmp     short loc_1800134D6
```
