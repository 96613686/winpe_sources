# sqlite3ExprCompare

- ea: `0x180014e58`
- end: `0x1800150c8`
- name: `sqlite3ExprCompare`
- size: `624`
- prototype: ``
- caller_count: `21`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800024dc`
- `0x180002860`
- `0x180014bf0`
- `0x180014dc0`
- `0x180014e58`
- `0x18001631c`
- `0x180016748`
- `0x18005ab60`
- `0x18005aea0`
- `0x18005c084`
- `0x180062894`
- `0x180063f04`
- `0x180066a50`
- `0x180067cd4`
- `0x18006e650`
- `0x18007f720`
- `0x180087bc0`
- `0x18008b730`
- `0x180095ef0`
- `0x180098b1c`
- `0x180098bfc`

## callees

- `0x1800143f0`
- `0x180014b90`
- `0x180014e58`
- `0x180016748`
- `0x180048060`
- `0x18008b730`

## pseudocode

```c
__int64 __fastcall sqlite3ExprCompare(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v8; // esi
  char v9; // al
  bool v11; // zf
  unsigned __int8 *v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // r8d

  if ( !a2 || !a3 )
    return a2 != a3 ? 2 : 0;
  if ( a1 && *(_BYTE *)a2 == 0x9D && (unsigned int)exprCompareVariable(a1, a2, a3) )
    return 0;
  v8 = *(_DWORD *)(a3 + 4) | *(_DWORD *)(a2 + 4);
  if ( (v8 & 0x800) != 0 )
  {
    if ( (*(_DWORD *)(a3 + 4) & *(_DWORD *)(a2 + 4) & 0x800) == 0 )
      return 2;
    v11 = *(_DWORD *)(a2 + 8) == *(_DWORD *)(a3 + 8);
    goto LABEL_15;
  }
  v9 = *(_BYTE *)a2;
  if ( *(_BYTE *)a2 == *(_BYTE *)a3 && v9 != 72 )
  {
LABEL_22:
    v12 = *(unsigned __int8 **)(a2 + 8);
    if ( !v12 )
      goto LABEL_23;
    if ( v9 == -84 || v9 == -87 )
    {
      if ( (unsigned int)sqlite3StrICmp(v12, *(_QWORD *)(a3 + 8))
        || ((*(_DWORD *)(a2 + 4) & 0x1000000) != 0) != (*(_BYTE *)(a3 + 7) & 1) )
      {
        return 2;
      }
      if ( (*(_DWORD *)(a2 + 4) & 0x1000000) == 0 )
        goto LABEL_23;
      v14 = sqlite3WindowCompare(a1, *(_QWORD *)(a2 + 64), *(_QWORD *)(a3 + 64), 1);
    }
    else
    {
      if ( v9 == 122 )
        return 0;
      v15 = *(_QWORD *)(a3 + 8);
      if ( v9 == 114 )
      {
        v14 = sqlite3_stricmp(v12, v15);
      }
      else
      {
        if ( !v15 || ((v9 + 88) & 0xFD) == 0 )
          goto LABEL_23;
        v16 = v15 - (_QWORD)v12;
        do
        {
          v17 = v12[v16];
          v14 = *v12 - v17;
          if ( v14 )
            break;
          ++v12;
        }
        while ( v17 );
      }
    }
    if ( v14 )
      return 2;
LABEL_23:
    if ( ((*(_DWORD *)(a2 + 4) ^ *(_DWORD *)(a3 + 4)) & 0x404) != 0 )
      return 2;
    if ( (v8 & 0x10000) == 0 )
    {
      if ( (v8 & 0x1000) != 0
        || (v8 & 0x20) == 0 && (unsigned int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 16), *(_QWORD *)(a3 + 16), a4)
        || (unsigned int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 24), *(_QWORD *)(a3 + 24), a4)
        || (unsigned int)sqlite3ExprListCompare(*(_QWORD *)(a2 + 32), *(_QWORD *)(a3 + 32), a4) )
      {
        return 2;
      }
      if ( *(_BYTE *)a2 == 0xAB || *(_BYTE *)a2 == 118 || (v8 & 0x4000) != 0 )
        return 0;
      if ( *(_WORD *)(a2 + 48) != *(_WORD *)(a3 + 48)
        || *(_BYTE *)(a2 + 2) != *(_BYTE *)(a3 + 2) && *(_BYTE *)a2 == 0xAF )
      {
        return 2;
      }
      if ( *(_BYTE *)a2 == 50 )
        return 0;
      v13 = *(_DWORD *)(a2 + 44);
      if ( v13 == *(_DWORD *)(a3 + 44) )
        return 0;
      v11 = v13 == a4;
LABEL_15:
      if ( v11 )
        return 0;
      return 2;
    }
    return 0;
  }
  if ( (v9 != 114 || (int)sqlite3ExprCompare(a1, *(_QWORD *)(a2 + 16), a3, a4) >= 2)
    && (*(_BYTE *)a3 != 114 || (int)sqlite3ExprCompare(a1, a2, *(_QWORD *)(a3 + 16), a4) >= 2) )
  {
    v9 = -86;
    if ( *(_BYTE *)a2 != 0xAA || *(_BYTE *)a3 != 0xA8 || *(int *)(a3 + 44) >= 0 || *(_DWORD *)(a2 + 44) != a4 )
      return 2;
    goto LABEL_22;
  }
  return 1;
}

```

## disassembly

```asm
0x180014e58  push    rbx
0x180014e5a  push    rbp
0x180014e5b  push    rsi
0x180014e5c  push    rdi
0x180014e5d  push    r14
0x180014e5f  sub     rsp, 20h
0x180014e63  mov     r14d, r9d
0x180014e66  mov     rbx, r8
0x180014e69  mov     rdi, rdx
0x180014e6c  mov     rbp, rcx
0x180014e6f  test    rdx, rdx
0x180014e72  jz      loc_180014FC2
0x180014e78  test    rbx, rbx
0x180014e7b  jz      loc_180014FC2
0x180014e81  test    rcx, rcx
0x180014e84  jnz     short loc_180014EC1
0x180014e86  mov     eax, [rdi+4]
0x180014e89  mov     esi, eax
0x180014e8b  or      esi, [rbx+4]
0x180014e8e  bt      esi, 0Bh
0x180014e92  jb      short loc_180014ED5
0x180014e94  mov     al, [rdi]
0x180014e96  cmp     al, [rbx]
0x180014e98  jz      short loc_180014EEB
0x180014e9a  cmp     al, 72h ; 'r'
0x180014e9c  jz      loc_18001506A
0x180014ea2  cmp     byte ptr [rbx], 72h ; 'r'
0x180014ea5  jz      loc_180015086
0x180014eab  mov     al, 0AAh
0x180014ead  cmp     [rdi], al
0x180014eaf  jz      short loc_180014EF1
0x180014eb1  mov     eax, 2
0x180014eb6  add     rsp, 20h
0x180014eba  pop     r14
0x180014ebc  pop     rdi
0x180014ebd  pop     rsi
0x180014ebe  pop     rbp
0x180014ebf  pop     rbx
0x180014ec0  retn
0x180014ec1  cmp     byte ptr [rdx], 9Dh
0x180014ec4  jnz     short loc_180014E86
0x180014ec6  call    exprCompareVariable
0x180014ecb  test    eax, eax
0x180014ecd  jnz     loc_180014FBB
0x180014ed3  jmp     short loc_180014E86
0x180014ed5  and     eax, [rbx+4]
0x180014ed8  bt      eax, 0Bh
0x180014edc  jnb     short loc_180014EB1
0x180014ede  mov     eax, [rbx+8]
0x180014ee1  cmp     [rdi+8], eax
0x180014ee4  jnz     short loc_180014EB1
0x180014ee6  jmp     loc_180014FBB
0x180014eeb  cmp     al, 48h ; 'H'
0x180014eed  jz      short loc_180014E9A
0x180014eef  jmp     short loc_180014F02
0x180014ef1  cmp     byte ptr [rbx], 0A8h
0x180014ef4  jnz     short loc_180014EB1
0x180014ef6  cmp     dword ptr [rbx+2Ch], 0
0x180014efa  jge     short loc_180014EB1
0x180014efc  cmp     [rdi+2Ch], r14d
0x180014f00  jnz     short loc_180014EB1
0x180014f02  mov     rcx, [rdi+8]
0x180014f06  test    rcx, rcx
0x180014f09  jnz     loc_180014FD2
0x180014f0f  mov     eax, [rbx+4]
0x180014f12  xor     eax, [rdi+4]
0x180014f15  test    eax, 404h
0x180014f1a  jnz     short loc_180014EB1
0x180014f1c  bt      esi, 10h
0x180014f20  jb      loc_180014FBB
0x180014f26  bt      esi, 0Ch
0x180014f2a  jb      short loc_180014EB1
0x180014f2c  test    sil, 20h
0x180014f30  jnz     short loc_180014F4D
0x180014f32  mov     r8, [rbx+10h]
0x180014f36  mov     r9d, r14d
0x180014f39  mov     rdx, [rdi+10h]
0x180014f3d  mov     rcx, rbp
0x180014f40  call    sqlite3ExprCompare
0x180014f45  test    eax, eax
0x180014f47  jnz     loc_180014EB1
0x180014f4d  mov     r8, [rbx+18h]
0x180014f51  mov     r9d, r14d
0x180014f54  mov     rdx, [rdi+18h]
0x180014f58  mov     rcx, rbp
0x180014f5b  call    sqlite3ExprCompare
0x180014f60  test    eax, eax
0x180014f62  jnz     loc_180014EB1
0x180014f68  mov     rdx, [rbx+20h]
0x180014f6c  mov     r8d, r14d
0x180014f6f  mov     rcx, [rdi+20h]
0x180014f73  call    sqlite3ExprListCompare
0x180014f78  test    eax, eax
0x180014f7a  jnz     loc_180014EB1
0x180014f80  cmp     byte ptr [rdi], 0ABh
0x180014f83  jz      short loc_180014FBB
0x180014f85  cmp     byte ptr [rdi], 76h ; 'v'
0x180014f88  jz      short loc_180014FBB
0x180014f8a  bt      esi, 0Eh
0x180014f8e  jb      short loc_180014FBB
0x180014f90  movzx   eax, word ptr [rbx+30h]
0x180014f94  cmp     [rdi+30h], ax
0x180014f98  jnz     loc_180014EB1
0x180014f9e  mov     al, [rbx+2]
0x180014fa1  cmp     [rdi+2], al
0x180014fa4  jnz     loc_1800150B2
0x180014faa  cmp     byte ptr [rdi], 32h ; '2'
0x180014fad  jz      short loc_180014FBB
0x180014faf  mov     eax, [rdi+2Ch]
0x180014fb2  cmp     eax, [rbx+2Ch]
0x180014fb5  jnz     loc_1800150C0
0x180014fbb  xor     eax, eax
0x180014fbd  jmp     loc_180014EB6
0x180014fc2  sub     rbx, rdi
0x180014fc5  neg     rbx
0x180014fc8  sbb     eax, eax
0x180014fca  and     eax, 2
0x180014fcd  jmp     loc_180014EB6
0x180014fd2  cmp     al, 0ACh
0x180014fd4  jnz     short loc_180015022
0x180014fd6  mov     rdx, [rbx+8]
0x180014fda  call    sqlite3StrICmp
0x180014fdf  test    eax, eax
0x180014fe1  jnz     loc_180014EB1
0x180014fe7  movzx   ecx, byte ptr [rbx+7]
0x180014feb  mov     edx, [rdi+4]
0x180014fee  and     ecx, 1
0x180014ff1  and     edx, 1000000h
0x180014ff7  setnz   al
0x180014ffa  cmp     eax, ecx
0x180014ffc  jnz     loc_180014EB1
0x180015002  test    edx, edx
0x180015004  jz      loc_180014F0F
0x18001500a  mov     r8, [rbx+40h]
0x18001500e  mov     r9d, 1
0x180015014  mov     rdx, [rdi+40h]
0x180015018  mov     rcx, rbp
0x18001501b  call    sqlite3WindowCompare
0x180015020  jmp     short loc_18001505D
0x180015022  cmp     al, 0A9h
0x180015024  jz      short loc_180014FD6
0x180015026  cmp     al, 7Ah ; 'z'
0x180015028  jz      short loc_180014FBB
0x18001502a  mov     rdx, [rbx+8]
0x18001502e  cmp     al, 72h ; 'r'
0x180015030  jz      short loc_1800150AB
0x180015032  test    rdx, rdx
0x180015035  jz      loc_180014F0F
0x18001503b  add     al, 58h ; 'X'
0x18001503d  test    al, 0FDh
0x18001503f  jz      loc_180014F0F
0x180015045  sub     rdx, rcx
0x180015048  movzx   eax, byte ptr [rcx]
0x18001504b  movzx   r8d, byte ptr [rcx+rdx]
0x180015050  sub     eax, r8d
0x180015053  jnz     short loc_18001505D
0x180015055  inc     rcx
0x180015058  test    r8d, r8d
0x18001505b  jnz     short loc_180015048
0x18001505d  test    eax, eax
0x18001505f  jz      loc_180014F0F
0x180015065  jmp     loc_180014EB1
0x18001506a  mov     rdx, [rdi+10h]
0x18001506e  mov     r9d, r14d
0x180015071  mov     r8, rbx
0x180015074  mov     rcx, rbp
0x180015077  call    sqlite3ExprCompare
0x18001507c  cmp     eax, 2
0x18001507f  jl      short loc_1800150A1
0x180015081  jmp     loc_180014EA2
0x180015086  mov     r8, [rbx+10h]
0x18001508a  mov     r9d, r14d
0x18001508d  mov     rdx, rdi
0x180015090  mov     rcx, rbp
0x180015093  call    sqlite3ExprCompare
0x180015098  cmp     eax, 2
0x18001509b  jge     loc_180014EAB
0x1800150a1  mov     eax, 1
0x1800150a6  jmp     loc_180014EB6
0x1800150ab  call    sqlite3_stricmp
0x1800150b0  jmp     short loc_18001505D
0x1800150b2  cmp     byte ptr [rdi], 0AFh
0x1800150b5  jz      loc_180014EB1
0x1800150bb  jmp     loc_180014FAA
0x1800150c0  cmp     eax, r14d
0x1800150c3  jmp     loc_180014EE4
```
