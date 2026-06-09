# sqlite3VdbeDelete

- ea: `0x180023bd0`
- end: `0x1800241fc`
- name: `sqlite3VdbeDelete`
- size: `1580`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: ``

## callers

- `0x180023a80`
- `0x180032b14`
- `0x180070218`
- `0x18009bab0`
- `0x18009e270`

## callees

- `0x180023b60`
- `0x180023bd0`
- `0x180024250`
- `0x180024770`
- `0x180024860`
- `0x180025770`
- `0x180041d10`
- `0x180041eb0`
- `0x180058118`
- `0x180059560`
- `0x18005a234`
- `0x18006f234`
- `0x180077180`
- `0x18007f828`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeDelete(unsigned __int64 a1, __int64 a2, __int16 *a3)
{
  unsigned __int64 v3; // rbx
  _QWORD *v4; // rdi
  __int64 v6; // r14
  unsigned __int64 v7; // rbx
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  _QWORD *i; // rbp
  __int16 *v11; // kr08_8
  __int64 v12; // kr10_8
  _QWORD *v13; // rcx
  __int64 v14; // rcx
  __int64 result; // rax
  __int64 v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rbp
  unsigned __int64 v19; // r14
  _QWORD *v20; // rcx
  _QWORD *v21; // rbp
  unsigned __int64 v22; // r14
  _QWORD *v23; // rcx
  __int64 v24; // rbx

  v3 = *(_QWORD *)(a1 + 152);
  v4 = *(_QWORD **)a1;
  if ( !v3 )
    goto LABEL_2;
  v16 = *(unsigned __int16 *)(a1 + 194);
  if ( (_WORD)v16 )
  {
    v21 = *(_QWORD **)(v3 + 24);
    v22 = v3 + 112 * v16;
    if ( v21[97] )
    {
      do
      {
        if ( *(_DWORD *)(v3 + 32) )
          sqlite3DbFree(v21, *(_QWORD *)(v3 + 40));
        v3 += 56LL;
      }
      while ( v3 < v22 );
      goto LABEL_35;
    }
    while ( (*(_WORD *)(v3 + 20) & 0x9000) == 0 )
    {
      if ( *(_DWORD *)(v3 + 32) )
      {
        v23 = *(_QWORD **)(v3 + 40);
        if ( (unsigned __int64)v23 >= v21[62] )
          goto LABEL_118;
        if ( (unsigned __int64)v23 >= v21[60] )
        {
          *v23 = v21[59];
          v21[59] = v23;
          goto LABEL_65;
        }
        if ( (unsigned __int64)v23 < v21[61] )
        {
LABEL_118:
          if ( v21[97] )
            measureAllocationSize(v21, *(_QWORD *)(v3 + 40));
          else
            sqlite3_free(v23);
        }
        else
        {
          *v23 = v21[57];
          v21[57] = v23;
        }
LABEL_65:
        *(_DWORD *)(v3 + 32) = 0;
LABEL_66:
        *(_WORD *)(v3 + 20) = 0;
      }
      v3 += 56LL;
      if ( v3 >= v22 )
        goto LABEL_35;
    }
    sqlite3VdbeMemRelease(v3);
    goto LABEL_66;
  }
LABEL_35:
  v17 = *(_QWORD **)(a1 + 152);
  if ( (unsigned __int64)v17 >= v4[62] )
    goto LABEL_119;
  if ( (unsigned __int64)v17 >= v4[60] )
  {
    *v17 = v4[59];
    v4[59] = v17;
    goto LABEL_2;
  }
  if ( (unsigned __int64)v17 < v4[61] )
  {
LABEL_119:
    if ( v4[97] )
      measureAllocationSize(v4, *(_QWORD *)(a1 + 152));
    else
      sqlite3_free(v17);
  }
  else
  {
    *v17 = v4[57];
    v4[57] = v17;
  }
LABEL_2:
  v6 = *(_QWORD *)(a1 + 288);
  if ( v6 )
  {
    do
    {
      v24 = *(_QWORD *)(v6 + 40);
      vdbeFreeOpArray(v4, *(_QWORD *)v6, *(unsigned int *)(v6 + 8));
      sqlite3DbFree(v4, v6);
      v6 = v24;
    }
    while ( v24 );
  }
  if ( !*(_BYTE *)(a1 + 199) )
    goto LABEL_9;
  v7 = *(_QWORD *)(a1 + 128);
  if ( v7 && *(_WORD *)(a1 + 32) )
  {
    v18 = *(_QWORD **)(v7 + 24);
    v19 = v7 + 56LL * *(__int16 *)(a1 + 32);
    if ( v18[97] )
    {
      do
      {
        if ( *(_DWORD *)(v7 + 32) )
          sqlite3DbFree(v18, *(_QWORD *)(v7 + 40));
        v7 += 56LL;
      }
      while ( v7 < v19 );
      goto LABEL_6;
    }
    while ( (*(_WORD *)(v7 + 20) & 0x9000) == 0 )
    {
      if ( *(_DWORD *)(v7 + 32) )
      {
        v20 = *(_QWORD **)(v7 + 40);
        if ( (unsigned __int64)v20 >= v18[62] )
          goto LABEL_120;
        if ( (unsigned __int64)v20 >= v18[60] )
        {
          *v20 = v18[59];
          v18[59] = v20;
          goto LABEL_46;
        }
        if ( (unsigned __int64)v20 < v18[61] )
        {
LABEL_120:
          if ( v18[97] )
            measureAllocationSize(v18, *(_QWORD *)(v7 + 40));
          else
            sqlite3_free(v20);
        }
        else
        {
          *v20 = v18[57];
          v18[57] = v20;
        }
LABEL_46:
        *(_DWORD *)(v7 + 32) = 0;
LABEL_47:
        *(_WORD *)(v7 + 20) = 0;
      }
      v7 += 56LL;
      if ( v7 >= v19 )
        goto LABEL_6;
    }
    sqlite3VdbeMemRelease(v7);
    goto LABEL_47;
  }
LABEL_6:
  a2 = *(_QWORD *)(a1 + 176);
  if ( a2 )
    sqlite3DbNNFreeNN(v4, a2);
  v8 = *(_QWORD **)(a1 + 256);
  if ( v8 )
  {
    if ( (unsigned __int64)v8 >= v4[62] )
      goto LABEL_121;
    if ( (unsigned __int64)v8 >= v4[60] )
    {
      *v8 = v4[59];
      v4[59] = v8;
      goto LABEL_9;
    }
    if ( (unsigned __int64)v8 < v4[61] )
    {
LABEL_121:
      if ( v4[97] )
        measureAllocationSize(v4, *(_QWORD *)(a1 + 256));
      else
        sqlite3_free(v8);
    }
    else
    {
      *v8 = v4[57];
      v4[57] = v8;
    }
  }
LABEL_9:
  v9 = *(_QWORD **)(a1 + 136);
  if ( v9 )
  {
    for ( i = &v9[3 * *(_DWORD *)(a1 + 144) - 3]; ; i -= 3 )
    {
      if ( *((char *)i + 1) <= -6 )
      {
        v11 = a3;
        v12 = a2;
        a2 = i[2];
        a3 = &_ImageBase;
        switch ( *((_BYTE *)i + 1) )
        {
          case 0xF0:
            if ( !v4[97] )
              sqlite3DeleteTable(v4, a2);
            break;
          case 0xF1:
            freeP4FuncCtx(v4, a2);
            break;
          case 0xF2:
          case 0xF3:
          case 0xF4:
          case 0xFA:
            if ( a2 )
              sqlite3DbNNFreeNN(v4, a2);
            break;
          case 0xF5:
            if ( !v4[97] )
              sqlite3VtabUnlock(i[2]);
            break;
          case 0xF6:
            if ( v4[97] )
              freeP4Mem(v4, a2);
            else
              sqlite3ValueFree(i[2]);
            break;
          case 0xF8:
            if ( !v4[97] )
              sqlite3KeyInfoUnref(i[2]);
            break;
          case 0xF9:
            freeEphemeralFunction(v4, a2);
            break;
          default:
            a2 = v12;
            a3 = v11;
            break;
        }
      }
      if ( i == v9 )
        break;
    }
    if ( (unsigned __int64)v9 < v4[62] )
    {
      if ( (unsigned __int64)v9 >= v4[60] )
      {
        *v9 = v4[59];
        v4[59] = v9;
        goto LABEL_24;
      }
      if ( (unsigned __int64)v9 >= v4[61] )
      {
        *v9 = v4[57];
        v4[57] = v9;
        goto LABEL_24;
      }
    }
    if ( v4[97] )
      measureAllocationSize(v4, v9);
    else
      sqlite3_free(v9);
  }
LABEL_24:
  v13 = *(_QWORD **)(a1 + 248);
  if ( !v13 )
    goto LABEL_28;
  if ( (unsigned __int64)v13 >= v4[62] )
    goto LABEL_122;
  if ( (unsigned __int64)v13 >= v4[60] )
  {
    *v13 = v4[59];
    v4[59] = v13;
    goto LABEL_28;
  }
  if ( (unsigned __int64)v13 < v4[61] )
  {
LABEL_122:
    if ( v4[97] )
      measureAllocationSize(v4, *(_QWORD *)(a1 + 248));
    else
      sqlite3_free(v13);
    goto LABEL_28;
  }
  *v13 = v4[57];
  v4[57] = v13;
LABEL_28:
  if ( !v4[97] )
  {
    **(_QWORD **)(a1 + 8) = *(_QWORD *)(a1 + 16);
    v14 = *(_QWORD *)(a1 + 16);
    if ( v14 )
      *(_QWORD *)(v14 + 8) = *(_QWORD *)(a1 + 8);
  }
  if ( a1 >= v4[62] )
    goto LABEL_123;
  if ( a1 >= v4[60] )
  {
    result = v4[59];
    *(_QWORD *)a1 = result;
    v4[59] = a1;
    return result;
  }
  if ( a1 < v4[61] )
  {
LABEL_123:
    if ( v4[97] )
      return measureAllocationSize(v4, a1);
    else
      return sqlite3_free(a1);
  }
  else
  {
    result = v4[57];
    *(_QWORD *)a1 = result;
    v4[57] = a1;
  }
  return result;
}

```

## disassembly

```asm
0x180023bd0  push    rbx
0x180023bd2  push    rbp
0x180023bd3  push    rsi
0x180023bd4  push    rdi
0x180023bd5  push    r12
0x180023bd7  push    r14
0x180023bd9  push    r15
0x180023bdb  sub     rsp, 20h
0x180023bdf  mov     rbx, [rcx+98h]
0x180023be6  xor     r15d, r15d
0x180023be9  mov     rdi, [rcx]
0x180023bec  mov     rsi, rcx
0x180023bef  mov     r12d, 9000h
0x180023bf5  test    rbx, rbx
0x180023bf8  jnz     loc_180023D97
0x180023bfe  mov     r14, [rsi+120h]
0x180023c05  test    r14, r14
0x180023c08  jnz     loc_18002414A
0x180023c0e  cmp     [rsi+0C7h], r15b
0x180023c15  jz      short loc_180023C4E
0x180023c17  mov     rbx, [rsi+80h]
0x180023c1e  test    rbx, rbx
0x180023c21  jz      short loc_180023C2E
0x180023c23  cmp     [rsi+20h], r15w
0x180023c28  jnz     loc_180023DFE
0x180023c2e  mov     rdx, [rsi+0B0h]
0x180023c35  test    rdx, rdx
0x180023c38  jnz     loc_180024054
0x180023c3e  mov     rcx, [rsi+100h]
0x180023c45  test    rcx, rcx
0x180023c48  jnz     loc_180023EE1
0x180023c4e  mov     rbx, [rsi+88h]
0x180023c55  test    rbx, rbx
0x180023c58  jz      loc_180023D09
0x180023c5e  mov     eax, [rsi+90h]
0x180023c64  dec     eax
0x180023c66  cdqe
0x180023c68  lea     rcx, [rax+rax*2]
0x180023c6c  lea     rbp, [rbx+rcx*8]
0x180023c70  cmp     byte ptr [rbp+1], 0FAh
0x180023c74  jg      short def_180023C9A; jumptable 0000000180023C9A default case, case -9
0x180023c76  movsx   eax, byte ptr [rbp+1]
0x180023c7a  add     eax, 10h; switch 11 cases
0x180023c7d  cmp     eax, 0Ah
0x180023c80  ja      short def_180023C9A; jumptable 0000000180023C9A default case, case -9
0x180023c82  mov     rdx, [rbp+10h]
0x180023c86  lea     r8, __ImageBase
0x180023c8d  cdqe
0x180023c8f  mov     ecx, ds:(jpt_180023C9A - 180000000h)[r8+rax*4]
0x180023c97  add     rcx, r8
0x180023c9a  jmp     rcx; switch jump
0x180023c9c  cmp     [rdi+308h], r15; jumptable 0000000180023C9A case -10
0x180023ca3  jnz     loc_18002418F
0x180023ca9  mov     rcx, rdx
0x180023cac  call    sqlite3ValueFree
0x180023cb1  cmp     rbp, rbx; jumptable 0000000180023C9A default case, case -9
0x180023cb4  jz      short loc_180023CDE
0x180023cb6  sub     rbp, 18h
0x180023cba  jmp     short loc_180023C70
0x180023cbc  test    rdx, rdx; jumptable 0000000180023C9A cases -14--12,-6
0x180023cbf  jz      short def_180023C9A; jumptable 0000000180023C9A default case, case -9
0x180023cc1  mov     rcx, rdi
0x180023cc4  call    sqlite3DbNNFreeNN
0x180023cc9  jmp     short def_180023C9A; jumptable 0000000180023C9A default case, case -9
0x180023ccb  cmp     [rdi+308h], r15; jumptable 0000000180023C9A case -8
0x180023cd2  jnz     short def_180023C9A; jumptable 0000000180023C9A default case, case -9
0x180023cd4  mov     rcx, rdx
0x180023cd7  call    sqlite3KeyInfoUnref
0x180023cdc  jmp     short def_180023C9A; jumptable 0000000180023C9A default case, case -9
0x180023cde  cmp     rbx, [rdi+1F0h]
0x180023ce5  jnb     loc_180024061
0x180023ceb  cmp     rbx, [rdi+1E0h]
0x180023cf2  jb      loc_180023EB1
0x180023cf8  mov     rax, [rdi+1D8h]
0x180023cff  mov     [rbx], rax
0x180023d02  mov     [rdi+1D8h], rbx
0x180023d09  mov     rcx, [rsi+0F8h]
0x180023d10  test    rcx, rcx
0x180023d13  jz      short loc_180023D40
0x180023d15  cmp     rcx, [rdi+1F0h]
0x180023d1c  jnb     loc_18002403B
0x180023d22  cmp     rcx, [rdi+1E0h]
0x180023d29  jb      loc_180023E8E
0x180023d2f  mov     rax, [rdi+1D8h]
0x180023d36  mov     [rcx], rax
0x180023d39  mov     [rdi+1D8h], rcx
0x180023d40  cmp     [rdi+308h], r15
0x180023d47  jnz     short loc_180023D61
0x180023d49  mov     rcx, [rsi+8]
0x180023d4d  mov     rax, [rsi+10h]
0x180023d51  mov     [rcx], rax
0x180023d54  mov     rcx, [rsi+10h]
0x180023d58  test    rcx, rcx
0x180023d5b  jnz     loc_180023ED4
0x180023d61  cmp     rsi, [rdi+1F0h]
0x180023d68  jnb     loc_180023FD8
0x180023d6e  cmp     rsi, [rdi+1E0h]
0x180023d75  jb      short loc_180023DDE
0x180023d77  mov     rax, [rdi+1D8h]
0x180023d7e  mov     [rsi], rax
0x180023d81  mov     [rdi+1D8h], rsi
0x180023d88  add     rsp, 20h
0x180023d8c  pop     r15
0x180023d8e  pop     r14
0x180023d90  pop     r12
0x180023d92  pop     rdi
0x180023d93  pop     rsi
0x180023d94  pop     rbp
0x180023d95  pop     rbx
0x180023d96  retn
0x180023d97  movzx   eax, word ptr [rcx+0C2h]
0x180023d9e  test    ax, ax
0x180023da1  jnz     loc_180023F11
0x180023da7  mov     rcx, [rsi+98h]
0x180023dae  cmp     rcx, [rdi+1F0h]
0x180023db5  jnb     loc_1800240A8
0x180023dbb  cmp     rcx, [rdi+1E0h]
0x180023dc2  jb      loc_180023F9C
0x180023dc8  mov     rax, [rdi+1D8h]
0x180023dcf  mov     [rcx], rax
0x180023dd2  mov     [rdi+1D8h], rcx
0x180023dd9  jmp     loc_180023BFE
0x180023dde  cmp     rsi, [rdi+1E8h]
0x180023de5  jb      loc_180023FD8
0x180023deb  mov     rax, [rdi+1C8h]
0x180023df2  mov     [rsi], rax
0x180023df5  mov     [rdi+1C8h], rsi
0x180023dfc  jmp     short loc_180023D88
0x180023dfe  movsx   rax, word ptr [rsi+20h]
0x180023e03  mov     rbp, [rbx+18h]
0x180023e07  imul    r14, rax, 38h ; '8'
0x180023e0b  add     r14, rbx
0x180023e0e  cmp     [rbp+308h], r15
0x180023e15  jnz     loc_180024108
0x180023e1b  test    [rbx+14h], r12w
0x180023e20  jnz     loc_1800240C1
0x180023e26  cmp     [rbx+20h], r15d
0x180023e2a  jz      short loc_180023E60
0x180023e2c  mov     rcx, [rbx+28h]
0x180023e30  cmp     rcx, [rbp+1F0h]
0x180023e37  jnb     loc_180023FBF
0x180023e3d  cmp     rcx, [rbp+1E0h]
0x180023e44  jb      short loc_180023E6E
0x180023e46  mov     rax, [rbp+1D8h]
0x180023e4d  mov     [rcx], rax
0x180023e50  mov     [rbp+1D8h], rcx
0x180023e57  mov     [rbx+20h], r15d
0x180023e5b  mov     [rbx+14h], r15w
0x180023e60  add     rbx, 38h ; '8'
0x180023e64  cmp     rbx, r14
0x180023e67  jb      short loc_180023E1B
0x180023e69  jmp     loc_180023C2E
0x180023e6e  cmp     rcx, [rbp+1E8h]
0x180023e75  jb      loc_180023FBF
0x180023e7b  mov     rax, [rbp+1C8h]
0x180023e82  mov     [rcx], rax
0x180023e85  mov     [rbp+1C8h], rcx
0x180023e8c  jmp     short loc_180023E57
0x180023e8e  cmp     rcx, [rdi+1E8h]
0x180023e95  jb      loc_18002403B
0x180023e9b  mov     rax, [rdi+1C8h]
0x180023ea2  mov     [rcx], rax
0x180023ea5  mov     [rdi+1C8h], rcx
0x180023eac  jmp     loc_180023D40
0x180023eb1  cmp     rbx, [rdi+1E8h]
0x180023eb8  jb      loc_180024061
0x180023ebe  mov     rax, [rdi+1C8h]
0x180023ec5  mov     [rbx], rax
0x180023ec8  mov     [rdi+1C8h], rbx
0x180023ecf  jmp     loc_180023D09
0x180023ed4  mov     rax, [rsi+8]
0x180023ed8  mov     [rcx+8], rax
0x180023edc  jmp     loc_180023D61
0x180023ee1  cmp     rcx, [rdi+1F0h]
0x180023ee8  jnb     loc_1800240D8
0x180023eee  cmp     rcx, [rdi+1E0h]
0x180023ef5  jb      loc_180023FFF
0x180023efb  mov     rax, [rdi+1D8h]
0x180023f02  mov     [rcx], rax
0x180023f05  mov     [rdi+1D8h], rcx
0x180023f0c  jmp     loc_180023C4E
0x180023f11  mov     rbp, [rbx+18h]
0x180023f15  imul    r14, rax, 70h ; 'p'
0x180023f19  add     r14, rbx
0x180023f1c  cmp     [rbp+308h], r15
0x180023f23  jnz     loc_180024129
0x180023f29  test    [rbx+14h], r12w
0x180023f2e  jnz     loc_1800240F1
0x180023f34  cmp     [rbx+20h], r15d
0x180023f38  jz      short loc_180023F6E
0x180023f3a  mov     rcx, [rbx+28h]
0x180023f3e  cmp     rcx, [rbp+1F0h]
0x180023f45  jnb     loc_180024022
0x180023f4b  cmp     rcx, [rbp+1E0h]
0x180023f52  jb      short loc_180023F7C
0x180023f54  mov     rax, [rbp+1D8h]
0x180023f5b  mov     [rcx], rax
0x180023f5e  mov     [rbp+1D8h], rcx
0x180023f65  mov     [rbx+20h], r15d
0x180023f69  mov     [rbx+14h], r15w
0x180023f6e  add     rbx, 38h ; '8'
0x180023f72  cmp     rbx, r14
0x180023f75  jb      short loc_180023F29
0x180023f77  jmp     loc_180023DA7
0x180023f7c  cmp     rcx, [rbp+1E8h]
0x180023f83  jb      loc_180024022
0x180023f89  mov     rax, [rbp+1C8h]
0x180023f90  mov     [rcx], rax
0x180023f93  mov     [rbp+1C8h], rcx
0x180023f9a  jmp     short loc_180023F65
0x180023f9c  cmp     rcx, [rdi+1E8h]
0x180023fa3  jb      loc_1800240A8
0x180023fa9  mov     rax, [rdi+1C8h]
0x180023fb0  mov     [rcx], rax
0x180023fb3  mov     [rdi+1C8h], rcx
0x180023fba  jmp     loc_180023BFE
0x180023fbf  cmp     [rbp+308h], r15
0x180023fc6  jz      short loc_180023FF5
0x180023fc8  mov     rdx, rcx
0x180023fcb  mov     rcx, rbp
0x180023fce  call    measureAllocationSize
0x180023fd3  jmp     loc_180023E57
0x180023fd8  cmp     [rdi+308h], r15
0x180023fdf  jz      loc_18002407A
0x180023fe5  mov     rdx, rsi
0x180023fe8  mov     rcx, rdi
0x180023feb  call    measureAllocationSize
0x180023ff0  jmp     loc_180023D88
0x180023ff5  call    sqlite3_free
0x180023ffa  jmp     loc_180023E57
0x180023fff  cmp     rcx, [rdi+1E8h]
0x180024006  jb      loc_1800240D8
0x18002400c  mov     rax, [rdi+1C8h]
0x180024013  mov     [rcx], rax
0x180024016  mov     [rdi+1C8h], rcx
0x18002401d  jmp     loc_180023C4E
0x180024022  cmp     [rbp+308h], r15
0x180024029  jz      short loc_180024087
0x18002402b  mov     rdx, rcx
0x18002402e  mov     rcx, rbp
0x180024031  call    measureAllocationSize
0x180024036  jmp     loc_180023F65
0x18002403b  cmp     [rdi+308h], r15
0x180024042  jz      short loc_180024091
0x180024044  mov     rdx, rcx
0x180024047  mov     rcx, rdi
0x18002404a  call    measureAllocationSize
0x18002404f  jmp     loc_180023D40
0x180024054  mov     rcx, rdi
0x180024057  call    sqlite3DbNNFreeNN
0x18002405c  jmp     loc_180023C3E
0x180024061  cmp     [rdi+308h], r15
0x180024068  jz      short loc_18002409B
0x18002406a  mov     rdx, rbx
0x18002406d  mov     rcx, rdi
0x180024070  call    measureAllocationSize
0x180024075  jmp     loc_180023D09
0x18002407a  mov     rcx, rsi
0x18002407d  call    sqlite3_free
0x180024082  jmp     loc_180023D88
0x180024087  call    sqlite3_free
0x18002408c  jmp     loc_180023F65
0x180024091  call    sqlite3_free
0x180024096  jmp     loc_180023D40
0x18002409b  mov     rcx, rbx
0x18002409e  call    sqlite3_free
0x1800240a3  jmp     loc_180023D09
0x1800240a8  cmp     [rdi+308h], r15
0x1800240af  jz      short loc_1800240CE
0x1800240b1  mov     rdx, rcx
0x1800240b4  mov     rcx, rdi
0x1800240b7  call    measureAllocationSize
0x1800240bc  jmp     loc_180023BFE
0x1800240c1  mov     rcx, rbx
0x1800240c4  call    sqlite3VdbeMemRelease
0x1800240c9  jmp     loc_180023E5B
0x1800240ce  call    sqlite3_free
0x1800240d3  jmp     loc_180023BFE
0x1800240d8  cmp     [rdi+308h], r15
0x1800240df  jz      short loc_1800240FE
0x1800240e1  mov     rdx, rcx
0x1800240e4  mov     rcx, rdi
0x1800240e7  call    measureAllocationSize
0x1800240ec  jmp     loc_180023C4E
0x1800240f1  mov     rcx, rbx
0x1800240f4  call    sqlite3VdbeMemRelease
0x1800240f9  jmp     loc_180023F69
0x1800240fe  call    sqlite3_free
0x180024103  jmp     loc_180023C4E
0x180024108  cmp     [rbx+20h], r15d
0x18002410c  jz      short loc_18002411A
0x18002410e  mov     rdx, [rbx+28h]
0x180024112  mov     rcx, rbp
0x180024115  call    sqlite3DbFree
0x18002411a  add     rbx, 38h ; '8'
0x18002411e  cmp     rbx, r14
0x180024121  jnb     loc_180023C2E
0x180024127  jmp     short loc_180024108
0x180024129  cmp     [rbx+20h], r15d
0x18002412d  jz      short loc_18002413B
  ... truncated ...
```
