# sqlite3InitOne

- ea: `0x18007ded0`
- end: `0x18007e279`
- name: `sqlite3InitOne`
- size: `937`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18007dc18`
- `0x180092f80`

## callees

- `0x180002250`
- `0x18003a024`
- `0x18003ae40`
- `0x1800688dc`
- `0x18006a988`
- `0x18006b458`
- `0x18006d144`
- `0x1800716fc`
- `0x180073a40`
- `0x18007dcb0`
- `0x18007ded0`
- `0x180080b64`
- `0x180081a3c`
- `0x18008a024`
- `0x18008a0b0`
- `0x18008dccc`
- `0x18008dd18`
- `0x1800a90e0`
- `0x1800b2174`

## string_xrefs

- `0x18007df18`: `sqlite_temp_master`
- `0x18007df6f`: `CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)`

## pseudocode

```c
__int64 __fastcall sqlite3InitOne(__int64 a1, int a2, __int64 a3, int a4)
{
  int v4; // ebx
  __int64 v5; // r13
  const char *v8; // rax
  unsigned int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // rax
  __int64 v12; // r15
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // ebx
  int v20; // edx
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  bool v24; // zf
  const char *v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // r12
  unsigned int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v35; // [rsp+30h] [rbp-79h]
  __int128 v36; // [rsp+38h] [rbp-71h] BYREF
  int v37; // [rsp+48h] [rbp-61h]
  _QWORD v38[2]; // [rsp+50h] [rbp-59h] BYREF
  int v39; // [rsp+60h] [rbp-49h]
  unsigned int v40; // [rsp+64h] [rbp-45h]
  int v41; // [rsp+68h] [rbp-41h]
  int v42; // [rsp+6Ch] [rbp-3Dh]
  __int64 v43; // [rsp+70h] [rbp-39h]
  const char *v44; // [rsp+78h] [rbp-31h]
  _QWORD v45[6]; // [rsp+80h] [rbp-29h] BYREF

  v4 = *(_DWORD *)(a1 + 44);
  v5 = a2;
  v45[0] = "table";
  v41 = a4;
  v43 = 0;
  v8 = "sqlite_temp_master";
  v45[5] = 0;
  v9 = v4 | 0xFFFFFFBF;
  v40 = 0;
  *(_BYTE *)(a1 + 197) = 1;
  v42 = 0;
  if ( a2 != 1 )
    v8 = "sqlite_master";
  v38[0] = a1;
  v44 = v8;
  v45[1] = v8;
  v45[2] = v8;
  v39 = a2;
  v45[3] = "1";
  v45[4] = "CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)";
  v38[1] = a3;
  sqlite3InitCallback(v38, 5, v45);
  *(_DWORD *)(a1 + 44) &= v9;
  v10 = v40;
  if ( v40 )
    goto LABEL_68;
  v11 = *(_QWORD *)(a1 + 32);
  v12 = 32 * v5;
  v13 = 32 * v5 + v11;
  v14 = *(_QWORD *)(v13 + 8);
  if ( !v14 )
  {
    v10 = 0;
    *(_WORD *)(*(_QWORD *)(v11 + 56) + 114LL) |= 1u;
    goto LABEL_72;
  }
  v10 = 1;
  if ( *(_BYTE *)(v14 + 17) )
  {
    ++*(_DWORD *)(v14 + 20);
    if ( !*(_BYTE *)(v14 + 18) )
      btreeLockCarefully(v14);
  }
  v15 = *(_QWORD *)(v13 + 8);
  if ( !v15 || (v35 = 0, !*(_BYTE *)(v15 + 16)) )
  {
    if ( *(_BYTE *)(v15 + 17) || !*(_BYTE *)(v15 + 16) )
    {
      v16 = btreeBeginTrans(v15, 0, 0);
      v10 = v16;
      if ( v16 )
      {
        v17 = sqlite3ErrStr(v16);
        sqlite3SetString(a3, a1, v17);
        goto LABEL_64;
      }
      v10 = 1;
    }
    v35 = 1;
  }
  v18 = 0;
  do
  {
    v19 = v18 + 1;
    sqlite3BtreeGetMeta(*(_QWORD *)(v13 + 8), (unsigned int)(v18 + 1), (char *)&v36 + 4 * v18);
    v18 = (unsigned int)v19;
  }
  while ( v19 < 5 );
  if ( (*(_DWORD *)(a1 + 48) & 0x2000000) != 0 )
  {
    v20 = 0;
    v36 = 0;
  }
  else
  {
    v20 = v37;
  }
  **(_DWORD **)(v13 + 24) = v36;
  if ( !v20 )
    goto LABEL_32;
  if ( !(_DWORD)v5 && (*(_BYTE *)(a1 + 44) & 0x40) == 0 )
  {
    v21 = v20 & 3;
    if ( !(_BYTE)v21 )
      v21 = 1;
    if ( *(int *)(a1 + 216) > 0 && (_BYTE)v21 != *(_BYTE *)(a1 + 100) && (*(_BYTE *)(a1 + 44) & 4) == 0 )
    {
      v10 = 6;
      goto LABEL_62;
    }
    sqlite3SetTextEncoding(a1, v21);
LABEL_32:
    *(_BYTE *)(*(_QWORD *)(v13 + 24) + 113LL) = *(_BYTE *)(a1 + 100);
    v22 = *(_QWORD *)(v13 + 24);
    if ( *(_DWORD *)(v22 + 116) )
    {
LABEL_43:
      *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) = BYTE4(v36);
      v26 = *(_QWORD *)(v13 + 24);
      if ( !*(_BYTE *)(v26 + 112) )
        *(_BYTE *)(v26 + 112) = 1;
      if ( *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) <= 4u )
      {
        if ( !(_DWORD)v5 && SDWORD1(v36) >= 4 )
          *(_QWORD *)(a1 + 48) &= ~2uLL;
        v27 = *(_QWORD *)(a1 + 32);
        LODWORD(v43) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 64LL);
        v28 = sqlite3MPrintf(a1, "SELECT*FROM\"%w\".%s ORDER BY rowid", *(_QWORD *)(v12 + v27), v44);
        v29 = *(_QWORD *)(a1 + 512);
        *(_QWORD *)(a1 + 512) = 0;
        v30 = v28;
        v31 = sqlite3_exec(a1, v28, (unsigned int)sqlite3InitCallback, (unsigned int)v38, 0);
        *(_QWORD *)(a1 + 512) = v29;
        v10 = v31;
        if ( !v31 )
          v10 = v40;
        if ( v30 )
          sqlite3DbFreeNN(a1);
        if ( !v10 )
          sqlite3AnalysisLoad(a1, (unsigned int)v5);
        if ( *(_BYTE *)(a1 + 103) )
        {
          v10 = 7;
          sqlite3ResetAllSchemasOfConnection(a1);
          v13 = v12 + *(_QWORD *)(a1 + 32);
        }
        else if ( !v10 || (*(_DWORD *)(a1 + 48) & 0x8000000) != 0 && v10 != 7 )
        {
          v10 = 0;
          v32 = *(_QWORD *)(v12 + *(_QWORD *)(a1 + 32) + 24);
          *(_WORD *)(v32 + 114) |= 1u;
        }
        goto LABEL_62;
      }
      v25 = "unsupported file format";
      goto LABEL_38;
    }
    v23 = DWORD2(v36);
    v24 = DWORD2(v36) == 0;
    if ( SDWORD2(v36) < 0 )
    {
      if ( DWORD2(v36) == 0x80000000 )
      {
        v23 = 0x7FFFFFFF;
LABEL_42:
        *(_DWORD *)(v22 + 116) = v23;
        sqlite3BtreeSetCacheSize(*(_QWORD *)(v13 + 8), *(unsigned int *)(*(_QWORD *)(v13 + 24) + 116LL));
        goto LABEL_43;
      }
      v23 = -DWORD2(v36);
      v24 = DWORD2(v36) == 0;
    }
    if ( v24 )
      v23 = -32000;
    goto LABEL_42;
  }
  if ( (v20 & 3) == *(_BYTE *)(a1 + 100) )
    goto LABEL_32;
  v25 = "attached databases must use the same text encoding as main database";
LABEL_38:
  sqlite3SetString(a3, a1, v25);
LABEL_62:
  if ( v35 )
    sqlite3BtreeCommit(*(_QWORD *)(v13 + 8));
LABEL_64:
  v33 = *(_QWORD *)(v13 + 8);
  if ( *(_BYTE *)(v33 + 17) )
  {
    v24 = (*(_DWORD *)(v33 + 20))-- == 1;
    if ( v24 )
      unlockBtreeMutex();
  }
  if ( v10 )
  {
LABEL_68:
    if ( v10 == 7 || v10 == 3082 )
      sqlite3OomFault(a1);
    sqlite3ResetOneSchema(a1);
  }
LABEL_72:
  *(_BYTE *)(a1 + 197) = 0;
  return v10;
}

```

## disassembly

```asm
0x18007ded0  push    rbp
0x18007ded2  push    rbx
0x18007ded3  push    rsi
0x18007ded4  push    rdi
0x18007ded5  push    r12
0x18007ded7  push    r13
0x18007ded9  push    r14
0x18007dedb  push    r15
0x18007dedd  lea     rbp, [rsp-1Fh]
0x18007dee2  sub     rsp, 0C8h
0x18007dee9  mov     rax, cs:__security_cookie
0x18007def0  xor     rax, rsp
0x18007def3  mov     [rbp+57h+var_50], rax
0x18007def7  mov     ebx, [rcx+2Ch]
0x18007defa  lea     rax, aTable; "table"
0x18007df01  movsxd  r13, edx
0x18007df04  mov     r12, r8
0x18007df07  xor     edx, edx
0x18007df09  mov     [rbp+57h+var_80], rax
0x18007df0d  mov     rdi, rcx
0x18007df10  mov     [rbp+57h+var_98], r9d
0x18007df14  mov     [rbp+57h+var_90], rdx
0x18007df18  lea     rax, aSqliteTempMast; "sqlite_temp_master"
0x18007df1f  mov     [rbp+57h+var_58], rdx
0x18007df23  or      ebx, 0FFFFFFBFh
0x18007df26  lea     r8d, [rdx+1]
0x18007df2a  mov     [rbp+57h+var_9C], edx
0x18007df2d  mov     [rcx+0C5h], r8b
0x18007df34  cmp     r13d, r8d
0x18007df37  lea     rcx, aSqliteMaster; "sqlite_master"
0x18007df3e  mov     [rbp+57h+var_94], edx
0x18007df41  cmovnz  rax, rcx
0x18007df45  mov     [rbp+57h+var_B0], rdi
0x18007df49  mov     [rbp+57h+var_88], rax
0x18007df4d  lea     r8, [rbp+57h+var_80]
0x18007df51  mov     [rbp+57h+var_78], rax
0x18007df55  lea     rcx, [rbp+57h+var_B0]
0x18007df59  mov     [rbp+57h+var_70], rax
0x18007df5d  xor     r9d, r9d
0x18007df60  lea     rax, a1; "1"
0x18007df67  mov     [rbp+57h+var_A0], r13d
0x18007df6b  mov     [rbp+57h+var_68], rax
0x18007df6f  lea     rax, aCreateTableXTy; "CREATE TABLE x(type text,name text,tbl_"...
0x18007df76  mov     [rbp+57h+var_60], rax
0x18007df7a  lea     edx, [r9+5]
0x18007df7e  mov     [rbp+57h+var_A8], r12
0x18007df82  call    sqlite3InitCallback
0x18007df87  and     [rdi+2Ch], ebx
0x18007df8a  xor     ebx, ebx
0x18007df8c  mov     esi, [rbp+57h+var_9C]
0x18007df8f  test    esi, esi
0x18007df91  jnz     loc_18007E231
0x18007df97  mov     rax, [rdi+20h]
0x18007df9b  mov     r15, r13
0x18007df9e  shl     r15, 5
0x18007dfa2  lea     r14, [r15+rax]
0x18007dfa6  mov     rcx, [r14+8]
0x18007dfaa  test    rcx, rcx
0x18007dfad  jnz     short loc_18007DFC1
0x18007dfaf  mov     rax, [rax+38h]
0x18007dfb3  lea     edx, [rsi+1]
0x18007dfb6  mov     esi, ebx
0x18007dfb8  or      [rax+72h], dx
0x18007dfbc  jmp     loc_18007E251
0x18007dfc1  mov     esi, 1
0x18007dfc6  cmp     [rcx+11h], bl
0x18007dfc9  jz      short loc_18007DFD8
0x18007dfcb  add     [rcx+14h], esi
0x18007dfce  cmp     [rcx+12h], bl
0x18007dfd1  jnz     short loc_18007DFD8
0x18007dfd3  call    btreeLockCarefully
0x18007dfd8  mov     rcx, [r14+8]
0x18007dfdc  test    rcx, rcx
0x18007dfdf  jz      short loc_18007DFE9
0x18007dfe1  mov     [rbp+57h+var_D0], ebx
0x18007dfe4  cmp     [rcx+10h], bl
0x18007dfe7  jnz     short loc_18007E025
0x18007dfe9  cmp     [rcx+11h], bl
0x18007dfec  jnz     short loc_18007DFF3
0x18007dfee  cmp     [rcx+10h], bl
0x18007dff1  jnz     short loc_18007E022
0x18007dff3  xor     r8d, r8d
0x18007dff6  xor     edx, edx
0x18007dff8  call    btreeBeginTrans
0x18007dffd  mov     esi, eax
0x18007dfff  test    eax, eax
0x18007e001  jz      short loc_18007E01D
0x18007e003  mov     ecx, eax
0x18007e005  call    sqlite3ErrStr
0x18007e00a  mov     r8, rax
0x18007e00d  mov     rdx, rdi
0x18007e010  mov     rcx, r12
0x18007e013  call    sqlite3SetString
0x18007e018  jmp     loc_18007E219
0x18007e01d  mov     esi, 1
0x18007e022  mov     [rbp+57h+var_D0], esi
0x18007e025  mov     eax, ebx
0x18007e027  mov     rcx, [r14+8]
0x18007e02b  lea     ebx, [rax+1]
0x18007e02e  lea     r8, [rbp+57h+var_C8]
0x18007e032  mov     edx, ebx
0x18007e034  lea     r8, [r8+rax*4]
0x18007e038  call    sqlite3BtreeGetMeta
0x18007e03d  mov     eax, ebx
0x18007e03f  cmp     ebx, 5
0x18007e042  jl      short loc_18007E027
0x18007e044  mov     eax, [rdi+30h]
0x18007e047  bt      rax, 19h
0x18007e04c  jnb     short loc_18007E059
0x18007e04e  xorps   xmm0, xmm0
0x18007e051  xor     edx, edx
0x18007e053  movups  [rbp+57h+var_C8], xmm0
0x18007e057  jmp     short loc_18007E05C
0x18007e059  mov     edx, [rbp+57h+var_B8]
0x18007e05c  mov     rcx, [r14+18h]
0x18007e060  xor     ebx, ebx
0x18007e062  mov     eax, dword ptr [rbp+57h+var_C8]
0x18007e065  mov     [rcx], eax
0x18007e067  test    edx, edx
0x18007e069  jz      short loc_18007E0A3
0x18007e06b  test    r13d, r13d
0x18007e06e  jnz     short loc_18007E0CB
0x18007e070  test    byte ptr [rdi+2Ch], 40h
0x18007e074  jnz     short loc_18007E0CB
0x18007e076  mov     al, dl
0x18007e078  and     al, 3
0x18007e07a  movzx   edx, al
0x18007e07d  cmovz   edx, esi
0x18007e080  cmp     [rdi+0D8h], ebx
0x18007e086  jle     short loc_18007E09B
0x18007e088  cmp     dl, [rdi+64h]
0x18007e08b  jz      short loc_18007E09B
0x18007e08d  test    byte ptr [rdi+2Ch], 4
0x18007e091  jnz     short loc_18007E09B
0x18007e093  lea     esi, [rbx+6]
0x18007e096  jmp     loc_18007E20B
0x18007e09b  mov     rcx, rdi
0x18007e09e  call    sqlite3SetTextEncoding
0x18007e0a3  mov     rcx, [r14+18h]
0x18007e0a7  mov     al, [rdi+64h]
0x18007e0aa  mov     [rcx+71h], al
0x18007e0ad  mov     rcx, [r14+18h]
0x18007e0b1  cmp     [rcx+74h], ebx
0x18007e0b4  jnz     short loc_18007E108
0x18007e0b6  mov     eax, dword ptr [rbp+57h+var_C8+8]
0x18007e0b9  test    eax, eax
0x18007e0bb  jns     short loc_18007E0EE
0x18007e0bd  cmp     eax, 80000000h
0x18007e0c2  jnz     short loc_18007E0EA
0x18007e0c4  mov     eax, 7FFFFFFFh
0x18007e0c9  jmp     short loc_18007E0F5
0x18007e0cb  and     edx, 3
0x18007e0ce  cmp     dl, [rdi+64h]
0x18007e0d1  jz      short loc_18007E0A3
0x18007e0d3  lea     r8, aAttachedDataba; "attached databases must use the same te"...
0x18007e0da  mov     rdx, rdi
0x18007e0dd  mov     rcx, r12
0x18007e0e0  call    sqlite3SetString
0x18007e0e5  jmp     loc_18007E20B
0x18007e0ea  neg     eax
0x18007e0ec  test    eax, eax
0x18007e0ee  jnz     short loc_18007E0F5
0x18007e0f0  mov     eax, 0FFFF8300h
0x18007e0f5  mov     [rcx+74h], eax
0x18007e0f8  mov     rdx, [r14+18h]
0x18007e0fc  mov     rcx, [r14+8]
0x18007e100  mov     edx, [rdx+74h]
0x18007e103  call    sqlite3BtreeSetCacheSize
0x18007e108  mov     al, byte ptr [rbp+57h+var_C8+4]
0x18007e10b  mov     rcx, [r14+18h]
0x18007e10f  mov     [rcx+70h], al
0x18007e112  mov     rax, [r14+18h]
0x18007e116  cmp     [rax+70h], bl
0x18007e119  jnz     short loc_18007E11F
0x18007e11b  mov     [rax+70h], sil
0x18007e11f  mov     rax, [r14+18h]
0x18007e123  cmp     byte ptr [rax+70h], 4
0x18007e127  jbe     short loc_18007E132
0x18007e129  lea     r8, aUnsupportedFil; "unsupported file format"
0x18007e130  jmp     short loc_18007E0DA
0x18007e132  test    r13d, r13d
0x18007e135  jnz     short loc_18007E142
0x18007e137  cmp     dword ptr [rbp+57h+var_C8+4], 4
0x18007e13b  jl      short loc_18007E142
0x18007e13d  and     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFDh
0x18007e142  mov     rax, [r14+8]
0x18007e146  lea     rdx, aSelectFromWSOr; "SELECT*FROM\"%w\".%s ORDER BY rowid"
0x18007e14d  mov     r8, [rdi+20h]
0x18007e151  mov     r9, [rbp+57h+var_88]
0x18007e155  mov     rcx, [rax+8]
0x18007e159  mov     eax, [rcx+40h]
0x18007e15c  mov     rcx, rdi
0x18007e15f  mov     dword ptr [rbp+57h+var_90], eax
0x18007e162  mov     r8, [r15+r8]
0x18007e166  call    sqlite3MPrintf
0x18007e16b  mov     rbx, [rdi+200h]
0x18007e172  lea     r9, [rbp+57h+var_B0]
0x18007e176  xor     edx, edx
0x18007e178  lea     r8, sqlite3InitCallback
0x18007e17f  mov     [rdi+200h], rdx
0x18007e186  mov     rcx, rdi
0x18007e189  mov     [rsp+100h+var_E0], rdx
0x18007e18e  mov     r12, rax
0x18007e191  mov     rdx, rax
0x18007e194  call    sqlite3_exec
0x18007e199  mov     [rdi+200h], rbx
0x18007e1a0  mov     esi, eax
0x18007e1a2  xor     ebx, ebx
0x18007e1a4  test    eax, eax
0x18007e1a6  cmovz   esi, [rbp+57h+var_9C]
0x18007e1aa  test    r12, r12
0x18007e1ad  jz      short loc_18007E1BA
0x18007e1af  mov     rdx, r12
0x18007e1b2  mov     rcx, rdi
0x18007e1b5  call    sqlite3DbFreeNN
0x18007e1ba  test    esi, esi
0x18007e1bc  jnz     short loc_18007E1C9
0x18007e1be  mov     edx, r13d
0x18007e1c1  mov     rcx, rdi
0x18007e1c4  call    sqlite3AnalysisLoad
0x18007e1c9  cmp     [rdi+67h], bl
0x18007e1cc  jz      short loc_18007E1E4
0x18007e1ce  mov     rcx, rdi
0x18007e1d1  mov     esi, 7
0x18007e1d6  call    sqlite3ResetAllSchemasOfConnection
0x18007e1db  mov     r14, [rdi+20h]
0x18007e1df  add     r14, r15
0x18007e1e2  jmp     short loc_18007E20B
0x18007e1e4  test    esi, esi
0x18007e1e6  jz      short loc_18007E1F7
0x18007e1e8  mov     eax, [rdi+30h]
0x18007e1eb  bt      rax, 1Bh
0x18007e1f0  jnb     short loc_18007E20B
0x18007e1f2  cmp     esi, 7
0x18007e1f5  jz      short loc_18007E20B
0x18007e1f7  mov     rax, [rdi+20h]
0x18007e1fb  mov     edx, 1
0x18007e200  mov     esi, ebx
0x18007e202  mov     rcx, [r15+rax+18h]
0x18007e207  or      [rcx+72h], dx
0x18007e20b  cmp     [rbp+57h+var_D0], ebx
0x18007e20e  jz      short loc_18007E219
0x18007e210  mov     rcx, [r14+8]
0x18007e214  call    sqlite3BtreeCommit
0x18007e219  mov     rcx, [r14+8]
0x18007e21d  cmp     [rcx+11h], bl
0x18007e220  jz      short loc_18007E22D
0x18007e222  sub     dword ptr [rcx+14h], 1
0x18007e226  jnz     short loc_18007E22D
0x18007e228  call    unlockBtreeMutex
0x18007e22d  test    esi, esi
0x18007e22f  jz      short loc_18007E251
0x18007e231  cmp     esi, 7
0x18007e234  jz      short loc_18007E23E
0x18007e236  cmp     esi, 0C0Ah
0x18007e23c  jnz     short loc_18007E246
0x18007e23e  mov     rcx, rdi
0x18007e241  call    sqlite3OomFault
0x18007e246  mov     edx, r13d
0x18007e249  mov     rcx, rdi
0x18007e24c  call    sqlite3ResetOneSchema
0x18007e251  mov     [rdi+0C5h], bl
0x18007e257  mov     eax, esi
0x18007e259  mov     rcx, [rbp+57h+var_50]
0x18007e25d  xor     rcx, rsp; StackCookie
0x18007e260  call    __security_check_cookie
0x18007e265  add     rsp, 0C8h
0x18007e26c  pop     r15
0x18007e26e  pop     r14
0x18007e270  pop     r13
0x18007e272  pop     r12
0x18007e274  pop     rdi
0x18007e275  pop     rsi
0x18007e276  pop     rbx
0x18007e277  pop     rbp
0x18007e278  retn
```
