# sqlite3ExprCompare

- ea: `0x180032568`
- end: `0x1800327c7`
- name: `sqlite3ExprCompare`
- size: `607`
- prototype: ``
- caller_count: `21`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005338`
- `0x180032568`
- `0x180052df0`
- `0x18005dbd8`
- `0x18005e094`
- `0x18005e730`
- `0x18007512c`
- `0x1800751d0`
- `0x180075de0`
- `0x180080034`
- `0x180080290`
- `0x18008096c`
- `0x180080d8c`
- `0x180083fbc`
- `0x18008beec`
- `0x1800917c8`
- `0x1800a0eb0`
- `0x1800a0fc4`
- `0x1800a1210`
- `0x1800a5bd8`
- `0x1800a5cb8`

## callees

- `0x18002e290`
- `0x180032568`
- `0x18005dee0`
- `0x180080d8c`
- `0x1800917c8`
- `0x180097ea0`

## pseudocode

```c
__int64 __fastcall sqlite3ExprCompare(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v8; // esi
  bool v9; // zf
  char v10; // cl
  unsigned __int8 *v12; // r8
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // eax

  if ( a2 && a3 )
  {
    if ( a1 && *(_BYTE *)a2 == 0x9C && (unsigned int)exprCompareVariable() )
      return 0;
    v8 = *(_DWORD *)(a3 + 4) | *(_DWORD *)(a2 + 4);
    if ( (v8 & 0x800) != 0 )
    {
      if ( (*(_DWORD *)(a3 + 4) & *(_DWORD *)(a2 + 4) & 0x800) != 0 )
      {
        v9 = *(_DWORD *)(a2 + 8) == *(_DWORD *)(a3 + 8);
        goto LABEL_53;
      }
      return 2;
    }
    v10 = *(_BYTE *)a2;
    if ( *(_BYTE *)a2 != *(_BYTE *)a3 || v10 == 71 )
    {
      if ( v10 == 113 && (int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 16), a3, a4) < 2
        || *(_BYTE *)a3 == 113 && (int)sqlite3ExprCompare(a1, a2, *(_QWORD *)(a3 + 16), a4) < 2 )
      {
        return 1;
      }
      v10 = -87;
      if ( *(_BYTE *)a2 != 0xA9 || *(_BYTE *)a3 != 0xA7 || *(int *)(a3 + 44) >= 0 || *(_DWORD *)(a2 + 44) != a4 )
        return 2;
    }
    v12 = *(unsigned __int8 **)(a2 + 8);
    if ( v12 )
    {
      if ( ((v10 + 88) & 0xFB) != 0 )
      {
        if ( v10 == 121 )
          return 0;
        v13 = *(_QWORD *)(a3 + 8);
        if ( v10 == 113 )
        {
          v14 = sqlite3_stricmp(*(_QWORD *)(a2 + 8), v13);
          goto LABEL_36;
        }
        if ( v13 && ((v10 + 89) & 0xFD) != 0 )
        {
          v15 = v13 - (_QWORD)v12;
          do
          {
            v16 = v12[v15];
            v14 = *v12 - v16;
            if ( v14 )
              break;
            ++v12;
          }
          while ( v16 );
LABEL_36:
          if ( v14 )
            return 2;
        }
      }
      else
      {
        if ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(a2 + 8), *(_QWORD *)(a3 + 8))
          || ((*(_DWORD *)(a2 + 4) & 0x1000000) != 0) != (*(_BYTE *)(a3 + 7) & 1) )
        {
          return 2;
        }
        if ( (*(_DWORD *)(a2 + 4) & 0x1000000) != 0 )
        {
          v14 = sqlite3WindowCompare(a1, *(_QWORD *)(a2 + 64), *(_QWORD *)(a3 + 64), 1);
          goto LABEL_36;
        }
      }
    }
    if ( ((*(_DWORD *)(a2 + 4) ^ *(_DWORD *)(a3 + 4)) & 0x404) == 0 )
    {
      if ( (v8 & 0x10000) != 0 )
        return 0;
      if ( (v8 & 0x1000) != 0
        || (v8 & 0x20) == 0 && (unsigned int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 16), *(_QWORD *)(a3 + 16), a4)
        || (unsigned int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 24), *(_QWORD *)(a3 + 24), a4)
        || (unsigned int)sqlite3ExprListCompare(*(_QWORD *)(a2 + 32), *(_QWORD *)(a3 + 32), a4) )
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
      v17 = *(_DWORD *)(a2 + 44);
      if ( v17 == *(_DWORD *)(a3 + 44) )
        return 0;
      v9 = v17 == a4;
LABEL_53:
      if ( !v9 )
        return 2;
      return 0;
    }
    return 2;
  }
  return a2 != a3 ? 2 : 0;
}

```

## disassembly

```asm
0x180032568  push    rbx
0x18003256a  push    rbp
0x18003256b  push    rsi
0x18003256c  push    rdi
0x18003256d  push    r14
0x18003256f  sub     rsp, 20h
0x180032573  mov     r14d, r9d
0x180032576  mov     rbx, r8
0x180032579  mov     rdi, rdx
0x18003257c  mov     rbp, rcx
0x18003257f  test    rdx, rdx
0x180032582  jz      loc_1800327B1
0x180032588  test    rbx, rbx
0x18003258b  jz      loc_1800327B1
0x180032591  test    rcx, rcx
0x180032594  jz      short loc_1800325A8
0x180032596  cmp     byte ptr [rdx], 9Ch
0x180032599  jnz     short loc_1800325A8
0x18003259b  call    exprCompareVariable
0x1800325a0  test    eax, eax
0x1800325a2  jnz     loc_18003265B
0x1800325a8  mov     eax, [rdi+4]
0x1800325ab  mov     esi, eax
0x1800325ad  or      esi, [rbx+4]
0x1800325b0  bt      esi, 0Bh
0x1800325b4  jnb     short loc_1800325CE
0x1800325b6  and     eax, [rbx+4]
0x1800325b9  bt      eax, 0Bh
0x1800325bd  jnb     loc_1800327AA
0x1800325c3  mov     eax, [rbx+8]
0x1800325c6  cmp     [rdi+8], eax
0x1800325c9  jmp     loc_1800327A4
0x1800325ce  mov     cl, [rdi]
0x1800325d0  cmp     cl, [rbx]
0x1800325d2  jnz     short loc_1800325D9
0x1800325d4  cmp     cl, 47h ; 'G'
0x1800325d7  jnz     short loc_180032642
0x1800325d9  cmp     cl, 71h ; 'q'
0x1800325dc  jnz     short loc_1800325F5
0x1800325de  mov     rdx, [rdi+10h]
0x1800325e2  mov     r9d, r14d
0x1800325e5  mov     r8, rbx
0x1800325e8  mov     rcx, rbp
0x1800325eb  call    sqlite3ExprCompare
0x1800325f0  cmp     eax, 2
0x1800325f3  jl      short loc_180032611
0x1800325f5  cmp     byte ptr [rbx], 71h ; 'q'
0x1800325f8  jnz     short loc_18003261B
0x1800325fa  mov     r8, [rbx+10h]
0x1800325fe  mov     r9d, r14d
0x180032601  mov     rdx, rdi
0x180032604  mov     rcx, rbp
0x180032607  call    sqlite3ExprCompare
0x18003260c  cmp     eax, 2
0x18003260f  jge     short loc_18003261B
0x180032611  mov     eax, 1
0x180032616  jmp     loc_1800327BC
0x18003261b  mov     cl, 0A9h
0x18003261d  cmp     [rdi], cl
0x18003261f  jnz     loc_1800327AA
0x180032625  cmp     byte ptr [rbx], 0A7h
0x180032628  jnz     loc_1800327AA
0x18003262e  cmp     dword ptr [rbx+2Ch], 0
0x180032632  jge     loc_1800327AA
0x180032638  cmp     [rdi+2Ch], r14d
0x18003263c  jnz     loc_1800327AA
0x180032642  mov     r8, [rdi+8]
0x180032646  test    r8, r8
0x180032649  jz      loc_1800326EC
0x18003264f  lea     eax, [rcx+58h]
0x180032652  test    al, 0FBh
0x180032654  jz      short loc_18003269B
0x180032656  cmp     cl, 79h ; 'y'
0x180032659  jnz     short loc_180032662
0x18003265b  xor     eax, eax
0x18003265d  jmp     loc_1800327BC
0x180032662  mov     rdx, [rbx+8]
0x180032666  cmp     cl, 71h ; 'q'
0x180032669  jnz     short loc_180032675
0x18003266b  mov     rcx, r8
0x18003266e  call    sqlite3_stricmp
0x180032673  jmp     short loc_1800326E4
0x180032675  test    rdx, rdx
0x180032678  jz      short loc_1800326EC
0x18003267a  add     cl, 59h ; 'Y'
0x18003267d  test    cl, 0FDh
0x180032680  jz      short loc_1800326EC
0x180032682  sub     rdx, r8
0x180032685  movzx   eax, byte ptr [r8]
0x180032689  movzx   ecx, byte ptr [r8+rdx]
0x18003268e  sub     eax, ecx
0x180032690  jnz     short loc_1800326E4
0x180032692  inc     r8
0x180032695  test    ecx, ecx
0x180032697  jnz     short loc_180032685
0x180032699  jmp     short loc_1800326E4
0x18003269b  mov     rdx, [rbx+8]
0x18003269f  mov     rcx, r8
0x1800326a2  call    sqlite3StrICmp
0x1800326a7  test    eax, eax
0x1800326a9  jnz     loc_1800327AA
0x1800326af  movzx   ecx, byte ptr [rbx+7]
0x1800326b3  mov     edx, [rdi+4]
0x1800326b6  and     ecx, 1
0x1800326b9  and     edx, 1000000h
0x1800326bf  setnz   al
0x1800326c2  cmp     eax, ecx
0x1800326c4  jnz     loc_1800327AA
0x1800326ca  test    edx, edx
0x1800326cc  jz      short loc_1800326EC
0x1800326ce  mov     r8, [rbx+40h]
0x1800326d2  mov     r9d, 1
0x1800326d8  mov     rdx, [rdi+40h]
0x1800326dc  mov     rcx, rbp
0x1800326df  call    sqlite3WindowCompare
0x1800326e4  test    eax, eax
0x1800326e6  jnz     loc_1800327AA
0x1800326ec  mov     eax, [rbx+4]
0x1800326ef  xor     eax, [rdi+4]
0x1800326f2  test    eax, 404h
0x1800326f7  jnz     loc_1800327AA
0x1800326fd  bt      esi, 10h
0x180032701  jb      loc_18003265B
0x180032707  bt      esi, 0Ch
0x18003270b  jb      loc_1800327AA
0x180032711  test    sil, 20h
0x180032715  jnz     short loc_18003272E
0x180032717  mov     r8, [rbx+10h]
0x18003271b  mov     r9d, r14d
0x18003271e  mov     rdx, [rdi+10h]
0x180032722  mov     rcx, rbp
0x180032725  call    sqlite3ExprCompare
0x18003272a  test    eax, eax
0x18003272c  jnz     short loc_1800327AA
0x18003272e  mov     r8, [rbx+18h]
0x180032732  mov     r9d, r14d
0x180032735  mov     rdx, [rdi+18h]
0x180032739  mov     rcx, rbp
0x18003273c  call    sqlite3ExprCompare
0x180032741  test    eax, eax
0x180032743  jnz     short loc_1800327AA
0x180032745  mov     rdx, [rbx+20h]
0x180032749  mov     r8d, r14d
0x18003274c  mov     rcx, [rdi+20h]
0x180032750  call    sqlite3ExprListCompare
0x180032755  test    eax, eax
0x180032757  jnz     short loc_1800327AA
0x180032759  cmp     byte ptr [rdi], 75h ; 'u'
0x18003275c  jz      loc_18003265B
0x180032762  cmp     byte ptr [rdi], 0AAh
0x180032765  jz      loc_18003265B
0x18003276b  bt      esi, 0Eh
0x18003276f  jb      loc_18003265B
0x180032775  movzx   eax, word ptr [rbx+30h]
0x180032779  cmp     [rdi+30h], ax
0x18003277d  jnz     short loc_1800327AA
0x18003277f  mov     al, [rbx+2]
0x180032782  cmp     [rdi+2], al
0x180032785  jz      short loc_18003278C
0x180032787  cmp     byte ptr [rdi], 0AFh
0x18003278a  jz      short loc_1800327AA
0x18003278c  cmp     byte ptr [rdi], 31h ; '1'
0x18003278f  jz      loc_18003265B
0x180032795  mov     eax, [rdi+2Ch]
0x180032798  cmp     eax, [rbx+2Ch]
0x18003279b  jz      loc_18003265B
0x1800327a1  cmp     eax, r14d
0x1800327a4  jz      loc_18003265B
0x1800327aa  mov     eax, 2
0x1800327af  jmp     short loc_1800327BC
0x1800327b1  sub     rbx, rdi
0x1800327b4  neg     rbx
0x1800327b7  sbb     eax, eax
0x1800327b9  and     eax, 2
0x1800327bc  add     rsp, 20h
0x1800327c0  pop     r14
0x1800327c2  pop     rdi
0x1800327c3  pop     rsi
0x1800327c4  pop     rbp
0x1800327c5  pop     rbx
0x1800327c6  retn
```
