# renameTableFunc

- ea: `0x18008d8d0`
- end: `0x18008dd33`
- name: `renameTableFunc`
- size: `1123`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x18000509c`
- `0x18000a180`
- `0x180018f60`
- `0x180018fd0`
- `0x1800191d0`
- `0x18001fe1c`
- `0x1800208bc`
- `0x180024b60`
- `0x180053f60`
- `0x1800543d0`
- `0x180070500`
- `0x1800777a0`
- `0x180077a24`
- `0x180077ac4`
- `0x180078968`
- `0x1800789c0`
- `0x18008d078`
- `0x18008d3e4`
- `0x18008d5b0`
- `0x18008d8d0`
- `0x18008de34`
- `0x18008de78`
- `0x18008dff0`
- `0x18009d8b0`

## pseudocode

```c
__int64 __fastcall renameTableFunc(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r15
  __int64 v8; // rax
  __int64 v9; // rdx
  _BYTE *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  unsigned __int8 *v15; // r12
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rsi
  __int64 result; // rax
  int v20; // edi
  unsigned int v21; // ebx
  _QWORD *v22; // rdi
  int v23; // esi
  __int64 v24; // rax
  __int64 j; // r14
  _QWORD *v26; // rdi
  _QWORD *i; // rbx
  __int64 v28; // rdi
  int *v29; // rdx
  int v30; // edi
  __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // [rsp+30h] [rbp-D0h]
  __int128 v34; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+48h] [rbp-B8h]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h]
  _QWORD v39[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+88h] [rbp-78h]
  __int128 *v41; // [rsp+98h] [rbp-68h]
  _OWORD v42[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  char v44[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+E8h] [rbp-18h]
  unsigned int v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+240h] [rbp+140h]
  _QWORD *v49; // [rsp+248h] [rbp+148h]
  _QWORD *v50; // [rsp+250h] [rbp+150h]

  v36 = a1;
  v4 = a1;
  v5 = sqlite3_context_db_handle(a1);
  LOBYTE(v6) = 1;
  v7 = v5;
  v8 = sqlite3ValueText(*a3, v6);
  LOBYTE(v9) = 1;
  v10 = (_BYTE *)v8;
  v11 = sqlite3ValueText(a3[3], v9);
  LOBYTE(v12) = 1;
  v33 = v11;
  v13 = sqlite3ValueText(a3[4], v12);
  LOBYTE(v14) = 1;
  v15 = (unsigned __int8 *)v13;
  v16 = sqlite3ValueText(a3[5], v14);
  v17 = a3[6];
  v18 = v16;
  v37 = v16;
  result = sqlite3VdbeIntValue(v17);
  v20 = result;
  if ( v33 && v15 && v18 )
  {
    memset_0(v44, 0, 0x1A8u);
    v38 = *(_QWORD *)(v7 + 512);
    *(_QWORD *)(v7 + 512) = 0;
    sqlite3BtreeEnterAll(v7);
    v34 = 0;
    v35 = 0;
    *(_QWORD *)&v35 = sqlite3FindTable(v7, v15, v10);
    v39[0] = v44;
    v39[1] = renameTableExprCb;
    v39[2] = renameTableSelectCb;
    v41 = &v34;
    v40 = 0;
    v21 = renameParseSql((__int64)v44, (__int64)v10, v7, v33, v20);
    if ( v21 )
      goto LABEL_47;
    v22 = (_QWORD *)v48;
    v23 = *(_DWORD *)(v7 + 48) & 0x4000000;
    if ( !v48 )
    {
      if ( v49 )
      {
        renameTokenFind(v44, &v34, *v49);
        if ( !v23 )
          sqlite3WalkExpr(v39, v49[9]);
      }
      else
      {
        v26 = v50;
        if ( !(unsigned int)sqlite3_stricmp(v50[1], v15) && *(_QWORD *)(v35 + 96) == v26[6] )
          renameTokenFind(v44, &v34, v26[1]);
        if ( !v23 )
        {
          v21 = renameResolveTrigger(v44);
          if ( v21 )
            goto LABEL_47;
          renameWalkTrigger(v39);
          for ( i = (_QWORD *)v26[7]; i; i = (_QWORD *)i[10] )
          {
            v28 = i[3];
            if ( v28 && !(unsigned int)sqlite3_stricmp(i[3], v15) )
              renameTokenFind(v44, &v34, v28);
            v29 = (int *)i[4];
            if ( v29 && *v29 > 0 )
            {
              v30 = 0;
              do
              {
                v31 = *(_QWORD *)&v29[26 * v30 + 6];
                if ( !(unsigned int)sqlite3_stricmp(v31, v15) )
                  renameTokenFind(v44, &v34, v31);
                v29 = (int *)i[4];
                ++v30;
              }
              while ( v30 < *v29 );
            }
          }
        }
      }
      goto LABEL_46;
    }
    if ( *(_BYTE *)(v48 + 63) == 2 )
    {
      if ( !v23 )
      {
        v43 = 0;
        v42[0] = (unsigned __int64)v44;
        v24 = *(_QWORD *)(v48 + 64);
        memset(&v42[1], 0, 32);
        *(_DWORD *)(v24 + 4) &= ~0x200000u;
        sqlite3SelectPrep(v44, v22[8], v42);
        if ( v47 )
          v21 = v46;
        else
          sqlite3WalkSelect(v39, v22[8]);
        goto LABEL_24;
      }
    }
    else
    {
      if ( (!v23 || (*(_DWORD *)(v7 + 48) & 0x4000LL) != 0) && *(_BYTE *)(v48 + 63) != 1 )
      {
        for ( j = *(_QWORD *)(v48 + 72); j; j = *(_QWORD *)(j + 8) )
        {
          if ( !(unsigned int)sqlite3_stricmp(*(_QWORD *)(j + 16), v15) )
            renameTokenFind(v44, &v34, *(_QWORD *)(j + 16));
        }
        v4 = v36;
      }
      if ( !(unsigned int)sqlite3_stricmp(v15, *v22) )
      {
        *(_QWORD *)&v35 = v22;
        if ( !v23 )
          sqlite3WalkExprList(v39, v22[4]);
        renameTokenFind(v44, &v34, *v22);
LABEL_24:
        if ( v21 )
          goto LABEL_47;
      }
    }
LABEL_46:
    v21 = renameEditSql(v4, (unsigned int)&v34, v33, v37, 1);
    if ( !v21 )
    {
LABEL_53:
      renameParseCleanup(v44, v32);
      renameTokenFree(v7, v34);
      sqlite3BtreeLeaveAll(v7);
      result = v38;
      *(_QWORD *)(v7 + 512) = v38;
      return result;
    }
LABEL_47:
    if ( v21 == 1 && (*(_DWORD *)(v7 + 48) & 0x10000001) == 1 )
    {
      sqlite3_result_value(v4, a3[3]);
    }
    else if ( v45 )
    {
      renameColumnParseError(v4, (unsigned int)&Src, a3[1], a3[2], (__int64)v44);
    }
    else
    {
      sqlite3_result_error_code(v4, v21);
    }
    goto LABEL_53;
  }
  return result;
}

```

## disassembly

```asm
0x18008d8d0  mov     [rsp-8+arg_8], rbx
0x18008d8d5  push    rbp
0x18008d8d6  push    rsi
0x18008d8d7  push    rdi
0x18008d8d8  push    r12
0x18008d8da  push    r13
0x18008d8dc  push    r14
0x18008d8de  push    r15
0x18008d8e0  lea     rbp, [rsp-1A0h]
0x18008d8e8  sub     rsp, 2A0h
0x18008d8ef  mov     rax, cs:__security_cookie
0x18008d8f6  xor     rax, rsp
0x18008d8f9  mov     [rbp+1D0h+var_40], rax
0x18008d900  mov     r13, r8
0x18008d903  mov     [rsp+2D0h+var_278], rcx
0x18008d908  mov     r14, rcx
0x18008d90b  call    sqlite3_context_db_handle
0x18008d910  mov     rcx, [r13+0]
0x18008d914  mov     dl, 1
0x18008d916  mov     r15, rax
0x18008d919  call    sqlite3ValueText
0x18008d91e  mov     rcx, [r13+18h]
0x18008d922  mov     dl, 1
0x18008d924  mov     rbx, rax
0x18008d927  call    sqlite3ValueText
0x18008d92c  mov     rcx, [r13+20h]
0x18008d930  mov     dl, 1
0x18008d932  mov     [rsp+2D0h+var_2A0], rax
0x18008d937  call    sqlite3ValueText
0x18008d93c  mov     rcx, [r13+28h]
0x18008d940  mov     dl, 1
0x18008d942  mov     r12, rax
0x18008d945  call    sqlite3ValueText
0x18008d94a  mov     rcx, [r13+30h]
0x18008d94e  mov     rsi, rax
0x18008d951  mov     [rsp+2D0h+var_270], rax
0x18008d956  call    sqlite3VdbeIntValue
0x18008d95b  cmp     [rsp+2D0h+var_2A0], 0
0x18008d961  mov     rdi, rax
0x18008d964  jz      loc_18008DD09
0x18008d96a  test    r12, r12
0x18008d96d  jz      loc_18008DD09
0x18008d973  test    rsi, rsi
0x18008d976  jz      loc_18008DD09
0x18008d97c  xor     edx, edx; Val
0x18008d97e  lea     rcx, [rbp+1D0h+var_1F0]; void *
0x18008d982  mov     r8d, 1A8h; Size
0x18008d988  call    memset_0
0x18008d98d  mov     rax, [r15+200h]
0x18008d994  xorps   xmm1, xmm1
0x18008d997  xorps   xmm0, xmm0
0x18008d99a  mov     [rsp+2D0h+var_268], rax
0x18008d99f  mov     rcx, r15
0x18008d9a2  mov     qword ptr [r15+200h], 0
0x18008d9ad  movups  [rsp+2D0h+var_298], xmm0
0x18008d9b2  movups  [rsp+2D0h+var_288], xmm0
0x18008d9b7  movups  [rsp+2D0h+var_260], xmm1
0x18008d9bc  movups  [rbp+1D0h+var_250], xmm1
0x18008d9c0  movups  [rbp+1D0h+var_240], xmm1
0x18008d9c4  call    sqlite3BtreeEnterAll
0x18008d9c9  xorps   xmm0, xmm0
0x18008d9cc  mov     r8, rbx
0x18008d9cf  mov     rdx, r12
0x18008d9d2  mov     rcx, r15
0x18008d9d5  movups  [rsp+2D0h+var_298], xmm0
0x18008d9da  movups  [rsp+2D0h+var_288], xmm0
0x18008d9df  call    sqlite3FindTable
0x18008d9e4  mov     r9, [rsp+2D0h+var_2A0]
0x18008d9e9  lea     rcx, [rbp+1D0h+var_1F0]
0x18008d9ed  mov     qword ptr [rsp+2D0h+var_288], rax
0x18008d9f2  mov     r8, r15
0x18008d9f5  lea     rax, [rbp+1D0h+var_1F0]
0x18008d9f9  mov     dword ptr [rsp+2D0h+var_2B0], edi
0x18008d9fd  mov     qword ptr [rsp+2D0h+var_260], rax
0x18008da02  mov     rdx, rbx
0x18008da05  lea     rax, renameTableExprCb
0x18008da0c  mov     qword ptr [rsp+2D0h+var_260+8], rax
0x18008da11  lea     rax, renameTableSelectCb
0x18008da18  mov     qword ptr [rbp+1D0h+var_250], rax
0x18008da1c  lea     rax, [rsp+2D0h+var_298]
0x18008da21  mov     qword ptr [rbp+1D0h+var_240+8], rax
0x18008da25  movdqu  [rbp+1D0h+var_250+8], xmm0
0x18008da2a  call    renameParseSql
0x18008da2f  mov     ebx, eax
0x18008da31  test    eax, eax
0x18008da33  jnz     loc_18008DC8D
0x18008da39  mov     esi, [r15+30h]
0x18008da3d  mov     rdi, [rbp+1D0h+var_90]
0x18008da44  and     esi, 4000000h
0x18008da4a  test    rdi, rdi
0x18008da4d  jz      loc_18008DB4B
0x18008da53  cmp     byte ptr [rdi+3Fh], 2
0x18008da57  jnz     short loc_18008DAB8
0x18008da59  test    esi, esi
0x18008da5b  jnz     loc_18008DC68
0x18008da61  xor     eax, eax
0x18008da63  lea     r8, [rbp+1D0h+var_230]
0x18008da67  mov     [rbp+1D0h+var_200], rax
0x18008da6b  lea     rcx, [rbp+1D0h+var_1F0]
0x18008da6f  xorps   xmm0, xmm0
0x18008da72  lea     rax, [rbp+1D0h+var_1F0]
0x18008da76  movups  [rbp+1D0h+var_230], xmm0
0x18008da7a  mov     qword ptr [rbp+1D0h+var_230], rax
0x18008da7e  mov     rax, [rdi+40h]
0x18008da82  movups  [rbp+1D0h+var_220], xmm0
0x18008da86  movups  [rbp+1D0h+var_210], xmm0
0x18008da8a  btr     dword ptr [rax+4], 15h
0x18008da8f  mov     rdx, [rdi+40h]
0x18008da93  call    sqlite3SelectPrep
0x18008da98  cmp     [rbp+1D0h+var_1C0], esi
0x18008da9b  jz      short loc_18008DAA5
0x18008da9d  mov     ebx, [rbp+1D0h+var_1D8]
0x18008daa0  jmp     loc_18008DB3E
0x18008daa5  mov     rdx, [rdi+40h]
0x18008daa9  lea     rcx, [rsp+2D0h+var_260]
0x18008daae  call    sqlite3WalkSelect
0x18008dab3  jmp     loc_18008DB3E
0x18008dab8  test    esi, esi
0x18008daba  jz      short loc_18008DAC7
0x18008dabc  mov     eax, [r15+30h]
0x18008dac0  bt      rax, 0Eh
0x18008dac5  jnb     short loc_18008DB03
0x18008dac7  cmp     byte ptr [rdi+3Fh], 1
0x18008dacb  jz      short loc_18008DB03
0x18008dacd  mov     r14, [rdi+48h]
0x18008dad1  test    r14, r14
0x18008dad4  jz      short loc_18008DAFE
0x18008dad6  mov     rcx, [r14+10h]
0x18008dada  mov     rdx, r12
0x18008dadd  call    sqlite3_stricmp
0x18008dae2  test    eax, eax
0x18008dae4  jnz     short loc_18008DAF8
0x18008dae6  mov     r8, [r14+10h]
0x18008daea  lea     rdx, [rsp+2D0h+var_298]
0x18008daef  lea     rcx, [rbp+1D0h+var_1F0]
0x18008daf3  call    renameTokenFind
0x18008daf8  mov     r14, [r14+8]
0x18008dafc  jmp     short loc_18008DAD1
0x18008dafe  mov     r14, [rsp+2D0h+var_278]
0x18008db03  mov     rdx, [rdi]
0x18008db06  mov     rcx, r12
0x18008db09  call    sqlite3_stricmp
0x18008db0e  test    eax, eax
0x18008db10  jnz     loc_18008DC68
0x18008db16  mov     qword ptr [rsp+2D0h+var_288], rdi
0x18008db1b  test    esi, esi
0x18008db1d  jnz     short loc_18008DB2D
0x18008db1f  mov     rdx, [rdi+20h]
0x18008db23  lea     rcx, [rsp+2D0h+var_260]
0x18008db28  call    sqlite3WalkExprList
0x18008db2d  mov     r8, [rdi]
0x18008db30  lea     rdx, [rsp+2D0h+var_298]
0x18008db35  lea     rcx, [rbp+1D0h+var_1F0]
0x18008db39  call    renameTokenFind
0x18008db3e  test    ebx, ebx
0x18008db40  jz      loc_18008DC68
0x18008db46  jmp     loc_18008DC8D
0x18008db4b  mov     r8, [rbp+1D0h+var_88]
0x18008db52  test    r8, r8
0x18008db55  jz      short loc_18008DB8A
0x18008db57  mov     r8, [r8]
0x18008db5a  lea     rdx, [rsp+2D0h+var_298]
0x18008db5f  lea     rcx, [rbp+1D0h+var_1F0]
0x18008db63  call    renameTokenFind
0x18008db68  test    esi, esi
0x18008db6a  jnz     loc_18008DC68
0x18008db70  mov     rdx, [rbp+1D0h+var_88]
0x18008db77  lea     rcx, [rsp+2D0h+var_260]
0x18008db7c  mov     rdx, [rdx+48h]
0x18008db80  call    sqlite3WalkExpr
0x18008db85  jmp     loc_18008DC68
0x18008db8a  mov     rdi, [rbp+1D0h+var_80]
0x18008db91  mov     rdx, r12
0x18008db94  mov     rcx, [rdi+8]
0x18008db98  call    sqlite3_stricmp
0x18008db9d  test    eax, eax
0x18008db9f  jnz     short loc_18008DBC2
0x18008dba1  mov     rax, qword ptr [rsp+2D0h+var_288]
0x18008dba6  mov     rcx, [rdi+30h]
0x18008dbaa  cmp     [rax+60h], rcx
0x18008dbae  jnz     short loc_18008DBC2
0x18008dbb0  mov     r8, [rdi+8]
0x18008dbb4  lea     rdx, [rsp+2D0h+var_298]
0x18008dbb9  lea     rcx, [rbp+1D0h+var_1F0]
0x18008dbbd  call    renameTokenFind
0x18008dbc2  test    esi, esi
0x18008dbc4  jnz     loc_18008DC68
0x18008dbca  lea     rcx, [rbp+1D0h+var_1F0]
0x18008dbce  call    renameResolveTrigger
0x18008dbd3  mov     ebx, eax
0x18008dbd5  test    eax, eax
0x18008dbd7  jnz     loc_18008DC8D
0x18008dbdd  mov     rdx, rdi
0x18008dbe0  lea     rcx, [rsp+2D0h+var_260]
0x18008dbe5  call    renameWalkTrigger
0x18008dbea  mov     rbx, [rdi+38h]
0x18008dbee  jmp     short loc_18008DC63
0x18008dbf0  mov     rdi, [rbx+18h]
0x18008dbf4  test    rdi, rdi
0x18008dbf7  jz      short loc_18008DC19
0x18008dbf9  mov     rdx, r12
0x18008dbfc  mov     rcx, rdi
0x18008dbff  call    sqlite3_stricmp
0x18008dc04  test    eax, eax
0x18008dc06  jnz     short loc_18008DC19
0x18008dc08  mov     r8, rdi
0x18008dc0b  lea     rdx, [rsp+2D0h+var_298]
0x18008dc10  lea     rcx, [rbp+1D0h+var_1F0]
0x18008dc14  call    renameTokenFind
0x18008dc19  mov     rdx, [rbx+20h]
0x18008dc1d  test    rdx, rdx
0x18008dc20  jz      short loc_18008DC5F
0x18008dc22  cmp     dword ptr [rdx], 0
0x18008dc25  jle     short loc_18008DC5F
0x18008dc27  xor     edi, edi
0x18008dc29  movsxd  rax, edi
0x18008dc2c  imul    rcx, rax, 68h ; 'h'
0x18008dc30  mov     rsi, [rcx+rdx+18h]
0x18008dc35  mov     rdx, r12
0x18008dc38  mov     rcx, rsi
0x18008dc3b  call    sqlite3_stricmp
0x18008dc40  test    eax, eax
0x18008dc42  jnz     short loc_18008DC55
0x18008dc44  mov     r8, rsi
0x18008dc47  lea     rdx, [rsp+2D0h+var_298]
0x18008dc4c  lea     rcx, [rbp+1D0h+var_1F0]
0x18008dc50  call    renameTokenFind
0x18008dc55  mov     rdx, [rbx+20h]
0x18008dc59  inc     edi
0x18008dc5b  cmp     edi, [rdx]
0x18008dc5d  jl      short loc_18008DC29
0x18008dc5f  mov     rbx, [rbx+50h]
0x18008dc63  test    rbx, rbx
0x18008dc66  jnz     short loc_18008DBF0
0x18008dc68  mov     r9, [rsp+2D0h+var_270]
0x18008dc6d  lea     rdx, [rsp+2D0h+var_298]
0x18008dc72  mov     r8, [rsp+2D0h+var_2A0]
0x18008dc77  mov     rcx, r14
0x18008dc7a  mov     dword ptr [rsp+2D0h+var_2B0], 1
0x18008dc82  call    renameEditSql
0x18008dc87  mov     ebx, eax
0x18008dc89  test    eax, eax
0x18008dc8b  jz      short loc_18008DCDF
0x18008dc8d  cmp     ebx, 1
0x18008dc90  jnz     short loc_18008DCAF
0x18008dc92  mov     eax, [r15+30h]
0x18008dc96  and     eax, 10000001h
0x18008dc9b  cmp     rax, 1
0x18008dc9f  jnz     short loc_18008DCAF
0x18008dca1  mov     rdx, [r13+18h]
0x18008dca5  mov     rcx, r14
0x18008dca8  call    sqlite3_result_value
0x18008dcad  jmp     short loc_18008DCDF
0x18008dcaf  cmp     [rbp+1D0h+var_1E8], 0
0x18008dcb4  mov     rcx, r14
0x18008dcb7  jz      short loc_18008DCD8
0x18008dcb9  mov     r9, [r13+10h]
0x18008dcbd  lea     rax, [rbp+1D0h+var_1F0]
0x18008dcc1  mov     r8, [r13+8]
0x18008dcc5  lea     rdx, Src
0x18008dccc  mov     [rsp+2D0h+var_2B0], rax
0x18008dcd1  call    renameColumnParseError
0x18008dcd6  jmp     short loc_18008DCDF
0x18008dcd8  mov     edx, ebx
0x18008dcda  call    sqlite3_result_error_code
0x18008dcdf  lea     rcx, [rbp+1D0h+var_1F0]
0x18008dce3  call    renameParseCleanup
0x18008dce8  mov     rdx, qword ptr [rsp+2D0h+var_298]
0x18008dced  mov     rcx, r15
0x18008dcf0  call    renameTokenFree
0x18008dcf5  mov     rcx, r15
0x18008dcf8  call    sqlite3BtreeLeaveAll
0x18008dcfd  mov     rax, [rsp+2D0h+var_268]
0x18008dd02  mov     [r15+200h], rax
0x18008dd09  mov     rcx, [rbp+1D0h+var_40]
0x18008dd10  xor     rcx, rsp; StackCookie
0x18008dd13  call    __security_check_cookie
0x18008dd18  mov     rbx, [rsp+2D0h+arg_8]
0x18008dd20  add     rsp, 2A0h
0x18008dd27  pop     r15
0x18008dd29  pop     r14
0x18008dd2b  pop     r13
0x18008dd2d  pop     r12
0x18008dd2f  pop     rdi
0x18008dd30  pop     rsi
0x18008dd31  pop     rbp
0x18008dd32  retn
```
