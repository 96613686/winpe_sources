# sqlite3InitOne

- ea: `0x1800845e0`
- end: `0x180084b11`
- name: `sqlite3InitOne`
- size: `1329`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180084210`
- `0x1800a4310`

## callees

- `0x180003060`
- `0x180005980`
- `0x180006cc0`
- `0x180022d00`
- `0x180029fd0`
- `0x18002b330`
- `0x18004dba0`
- `0x180064b60`
- `0x180067910`
- `0x180068560`
- `0x18006a780`
- `0x180071400`
- `0x1800842d0`
- `0x1800845e0`
- `0x180088530`
- `0x180089210`
- `0x1800950a0`
- `0x180095180`
- `0x18009b690`
- `0x18009b7c0`
- `0x1800c1b30`

## string_xrefs

- `0x18008461b`: `sqlite_temp_master`
- `0x180084675`: `CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)`

## pseudocode

```c
__int64 __fastcall sqlite3InitOne(__int64 a1, int a2, char **a3, int a4)
{
  int v4; // edi
  __int64 v6; // r13
  const char *v7; // rax
  unsigned int v9; // edi
  unsigned int v10; // esi
  __int64 v11; // rax
  __int64 v12; // r12
  __int64 v13; // rcx
  __int64 v14; // r14
  __int64 result; // rax
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // edi
  int v21; // edx
  int v22; // ecx
  char v23; // dl
  __int64 v24; // rcx
  int v25; // eax
  bool v26; // zf
  char *v27; // rax
  char *v28; // rdi
  char *v29; // rcx
  __int64 v30; // rax
  char *v31; // rax
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rdi
  _QWORD *v35; // r15
  unsigned int v36; // eax
  __int64 v37; // rcx
  int v38; // [rsp+30h] [rbp-79h]
  __int128 v39; // [rsp+38h] [rbp-71h] BYREF
  int v40; // [rsp+48h] [rbp-61h]
  _QWORD v41[2]; // [rsp+50h] [rbp-59h] BYREF
  int v42; // [rsp+60h] [rbp-49h]
  unsigned int v43; // [rsp+64h] [rbp-45h]
  int v44; // [rsp+68h] [rbp-41h]
  __int64 v45; // [rsp+6Ch] [rbp-3Dh]
  const char *v46; // [rsp+78h] [rbp-31h]
  _QWORD v47[6]; // [rsp+80h] [rbp-29h] BYREF

  v4 = *(_DWORD *)(a1 + 44);
  v47[0] = "table";
  v6 = a2;
  v7 = "sqlite_temp_master";
  *(_BYTE *)(a1 + 197) = 1;
  v41[1] = a3;
  v44 = a4;
  v9 = v4 | 0xFFFFFFBF;
  v41[0] = a1;
  v42 = a2;
  if ( a2 != 1 )
    v7 = "sqlite_master";
  v46 = v7;
  v47[1] = v7;
  v47[2] = v7;
  v47[3] = "1";
  v47[4] = "CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)";
  v47[5] = 0;
  v43 = 0;
  v45 = 0;
  sqlite3InitCallback(v41, 5, v47, 0);
  *(_DWORD *)(a1 + 44) &= v9;
  v10 = v43;
  if ( !v43 )
  {
    v11 = *(_QWORD *)(a1 + 32);
    v12 = 32 * v6;
    v13 = *(_QWORD *)(32 * v6 + v11 + 8);
    v14 = 32 * v6 + v11;
    if ( !v13 )
    {
      *(_WORD *)(*(_QWORD *)(v11 + 56) + 114LL) |= 1u;
      result = 0;
      *(_BYTE *)(a1 + 197) = 0;
      return result;
    }
    if ( *(_BYTE *)(v13 + 17) )
    {
      ++*(_DWORD *)(v13 + 20);
      if ( !*(_BYTE *)(v13 + 18) )
        btreeLockCarefully(v13);
    }
    v16 = *(_QWORD *)(v14 + 8);
    if ( !v16 || (v38 = 0, !*(_BYTE *)(v16 + 16)) )
    {
      if ( *(_BYTE *)(v16 + 17) || !*(_BYTE *)(v16 + 16) )
      {
        v17 = btreeBeginTrans(v16, 0, 0);
        v10 = v17;
        if ( v17 )
        {
          v18 = sqlite3_errstr(v17);
          sqlite3SetString(a3, a1, v18);
          goto LABEL_85;
        }
      }
      v38 = 1;
    }
    v19 = 0;
    do
    {
      v20 = v19 + 1;
      sqlite3BtreeGetMeta(*(_QWORD *)(v14 + 8), (unsigned int)(v19 + 1), (char *)&v39 + 4 * v19);
      v19 = (unsigned int)v20;
    }
    while ( v20 < 5 );
    if ( (*(_DWORD *)(a1 + 48) & 0x2000000) != 0 )
    {
      v21 = 0;
      v39 = 0;
    }
    else
    {
      v21 = v40;
    }
    **(_DWORD **)(v14 + 24) = v39;
    if ( v21 )
    {
      if ( (_DWORD)v6 || (v22 = *(_DWORD *)(a1 + 44), (v22 & 0x40) != 0) )
      {
        if ( (v21 & 3) != *(_BYTE *)(a1 + 100) )
        {
          v27 = (char *)sqlite3DbMallocRawNN(a1, 68);
          v28 = v27;
          if ( v27 )
            strcpy(v27, "attached databases must use the same text encoding as main database");
          v29 = *a3;
          if ( !*a3 )
            goto LABEL_47;
          if ( (unsigned __int64)v29 >= *(_QWORD *)(a1 + 496) )
            goto LABEL_44;
          if ( (unsigned __int64)v29 < *(_QWORD *)(a1 + 480) )
            goto LABEL_42;
          goto LABEL_41;
        }
      }
      else
      {
        v23 = v21 & 3;
        if ( !v23 )
          v23 = 1;
        if ( *(int *)(a1 + 216) > 0 && v23 != *(_BYTE *)(a1 + 100) && (v22 & 4) == 0 )
        {
          v10 = 6;
          goto LABEL_83;
        }
        sqlite3SetTextEncoding(a1);
      }
    }
    *(_BYTE *)(*(_QWORD *)(v14 + 24) + 113LL) = *(_BYTE *)(a1 + 100);
    v24 = *(_QWORD *)(v14 + 24);
    if ( *(_DWORD *)(v24 + 116) )
    {
LABEL_52:
      *(_BYTE *)(*(_QWORD *)(v14 + 24) + 112LL) = BYTE4(v39);
      v30 = *(_QWORD *)(v14 + 24);
      if ( !*(_BYTE *)(v30 + 112) )
        *(_BYTE *)(v30 + 112) = 1;
      if ( *(_BYTE *)(*(_QWORD *)(v14 + 24) + 112LL) > 4u )
      {
        v31 = (char *)sqlite3DbMallocRawNN(a1, 24);
        v28 = v31;
        if ( v31 )
          strcpy(v31, "unsupported file format");
        v29 = *a3;
        if ( !*a3 )
          goto LABEL_47;
        if ( (unsigned __int64)v29 >= *(_QWORD *)(a1 + 496) )
        {
LABEL_44:
          if ( *(_QWORD *)(a1 + 776) )
          {
            measureAllocationSize(a1, v29);
            *a3 = v28;
            v10 = 1;
            goto LABEL_83;
          }
          sqlite3_free(v29);
LABEL_47:
          *a3 = v28;
          v10 = 1;
LABEL_83:
          if ( v38 )
            sqlite3BtreeCommit(*(_QWORD *)(v14 + 8));
LABEL_85:
          v37 = *(_QWORD *)(v14 + 8);
          if ( *(_BYTE *)(v37 + 17) )
          {
            v26 = (*(_DWORD *)(v37 + 20))-- == 1;
            if ( v26 )
              unlockBtreeMutex(v37);
          }
          if ( !v10 )
            goto LABEL_93;
          goto LABEL_89;
        }
        if ( (unsigned __int64)v29 < *(_QWORD *)(a1 + 480) )
        {
LABEL_42:
          if ( (unsigned __int64)v29 >= *(_QWORD *)(a1 + 488) )
          {
            v10 = 1;
            *(_QWORD *)v29 = *(_QWORD *)(a1 + 456);
            *(_QWORD *)(a1 + 456) = v29;
            *a3 = v28;
            goto LABEL_83;
          }
          goto LABEL_44;
        }
LABEL_41:
        v10 = 1;
        *(_QWORD *)v29 = *(_QWORD *)(a1 + 472);
        *(_QWORD *)(a1 + 472) = v29;
        *a3 = v28;
        goto LABEL_83;
      }
      if ( !(_DWORD)v6 && SDWORD1(v39) >= 4 )
        *(_QWORD *)(a1 + 48) &= ~2uLL;
      v32 = *(_QWORD *)(a1 + 32);
      HIDWORD(v45) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 64LL);
      v33 = sqlite3MPrintf(a1, "SELECT*FROM\"%w\".%s ORDER BY rowid", *(_QWORD *)(v32 + 32 * v6), v46);
      v34 = *(_QWORD *)(a1 + 512);
      *(_QWORD *)(a1 + 512) = 0;
      v35 = (_QWORD *)v33;
      v36 = sqlite3_exec(a1, v33, (unsigned int)sqlite3InitCallback, (unsigned int)v41, 0);
      *(_QWORD *)(a1 + 512) = v34;
      v10 = v36;
      if ( !v36 )
        v10 = v43;
      if ( v35 )
      {
        if ( (unsigned __int64)v35 < *(_QWORD *)(a1 + 496) )
        {
          if ( (unsigned __int64)v35 >= *(_QWORD *)(a1 + 480) )
          {
            *v35 = *(_QWORD *)(a1 + 472);
            *(_QWORD *)(a1 + 472) = v35;
            goto LABEL_75;
          }
          if ( (unsigned __int64)v35 >= *(_QWORD *)(a1 + 488) )
          {
            *v35 = *(_QWORD *)(a1 + 456);
            *(_QWORD *)(a1 + 456) = v35;
            goto LABEL_75;
          }
        }
        if ( *(_QWORD *)(a1 + 776) )
          measureAllocationSize(a1, v35);
        else
          sqlite3_free(v35);
      }
LABEL_75:
      if ( !v10 )
        sqlite3AnalysisLoad(a1, (unsigned int)v6);
      if ( *(_BYTE *)(a1 + 103) )
      {
        v10 = 7;
        sqlite3ResetAllSchemasOfConnection(a1);
        v14 = v12 + *(_QWORD *)(a1 + 32);
      }
      else if ( !v10 || (*(_DWORD *)(a1 + 48) & 0x8000000) != 0 && v10 != 7 )
      {
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + v12 + 24) + 114LL) |= 1u;
        v10 = 0;
      }
      goto LABEL_83;
    }
    v25 = DWORD2(v39);
    v26 = DWORD2(v39) == 0;
    if ( SDWORD2(v39) < 0 )
    {
      if ( DWORD2(v39) == 0x80000000 )
      {
        v25 = 0x7FFFFFFF;
LABEL_51:
        *(_DWORD *)(v24 + 116) = v25;
        sqlite3BtreeSetCacheSize(*(_QWORD *)(v14 + 8), *(unsigned int *)(*(_QWORD *)(v14 + 24) + 116LL));
        goto LABEL_52;
      }
      v25 = -DWORD2(v39);
      v26 = DWORD2(v39) == 0;
    }
    if ( v26 )
      v25 = -2000;
    goto LABEL_51;
  }
LABEL_89:
  if ( v10 == 7 || v10 == 3082 )
    sqlite3OomFault(a1);
  sqlite3ResetOneSchema(a1);
LABEL_93:
  result = v10;
  *(_BYTE *)(a1 + 197) = 0;
  return result;
}

```

## disassembly

```asm
0x1800845e0  push    rbp
0x1800845e2  push    rbx
0x1800845e3  push    rsi
0x1800845e4  push    rdi
0x1800845e5  push    r12
0x1800845e7  push    r13
0x1800845e9  push    r14
0x1800845eb  push    r15
0x1800845ed  lea     rbp, [rsp-1Fh]
0x1800845f2  sub     rsp, 0C8h
0x1800845f9  mov     rax, cs:__security_cookie
0x180084600  xor     rax, rsp
0x180084603  mov     [rbp+57h+var_50], rax
0x180084607  mov     edi, [rcx+2Ch]
0x18008460a  lea     rax, aTable; "table"
0x180084611  mov     [rbp+57h+var_80], rax
0x180084615  mov     rbx, rcx
0x180084618  movsxd  r13, edx
0x18008461b  lea     rax, aSqliteTempMast; "sqlite_temp_master"
0x180084622  mov     byte ptr [rcx+0C5h], 1
0x180084629  mov     r15, r8
0x18008462c  lea     rcx, aSqliteMaster; "sqlite_master"
0x180084633  mov     [rbp+57h+var_A8], r8
0x180084637  mov     [rbp+57h+var_98], r9d
0x18008463b  lea     r8, [rbp+57h+var_80]
0x18008463f  or      edi, 0FFFFFFBFh
0x180084642  mov     [rbp+57h+var_B0], rbx
0x180084646  cmp     r13d, 1
0x18008464a  mov     [rbp+57h+var_A0], r13d
0x18008464e  mov     edx, 5
0x180084653  cmovnz  rax, rcx
0x180084657  xor     r9d, r9d
0x18008465a  mov     [rbp+57h+var_88], rax
0x18008465e  lea     rcx, [rbp+57h+var_B0]
0x180084662  mov     [rbp+57h+var_78], rax
0x180084666  mov     [rbp+57h+var_70], rax
0x18008466a  lea     rax, a1; "1"
0x180084671  mov     [rbp+57h+var_68], rax
0x180084675  lea     rax, aCreateTableXTy; "CREATE TABLE x(type text,name text,tbl_"...
0x18008467c  mov     [rbp+57h+var_60], rax
0x180084680  xor     eax, eax
0x180084682  mov     [rbp+57h+var_58], rax
0x180084686  mov     [rbp+57h+var_9C], eax
0x180084689  mov     [rbp+57h+var_94], rax
0x18008468d  call    sqlite3InitCallback
0x180084692  and     [rbx+2Ch], edi
0x180084695  mov     esi, [rbp+57h+var_9C]
0x180084698  test    esi, esi
0x18008469a  jnz     loc_180084AC8
0x1800846a0  mov     rax, [rbx+20h]
0x1800846a4  mov     r12, r13
0x1800846a7  shl     r12, 5
0x1800846ab  mov     rcx, [r12+rax+8]
0x1800846b0  lea     r14, [r12+rax]
0x1800846b4  test    rcx, rcx
0x1800846b7  jnz     short loc_1800846CF
0x1800846b9  mov     rax, [rax+38h]
0x1800846bd  or      word ptr [rax+72h], 1
0x1800846c2  xor     eax, eax
0x1800846c4  mov     [rbx+0C5h], al
0x1800846ca  jmp     loc_180084AF1
0x1800846cf  cmp     byte ptr [rcx+11h], 0
0x1800846d3  jz      short loc_1800846E3
0x1800846d5  inc     dword ptr [rcx+14h]
0x1800846d8  cmp     byte ptr [rcx+12h], 0
0x1800846dc  jnz     short loc_1800846E3
0x1800846de  call    btreeLockCarefully
0x1800846e3  mov     rcx, [r14+8]
0x1800846e7  test    rcx, rcx
0x1800846ea  jz      short loc_1800846F7
0x1800846ec  xor     esi, esi
0x1800846ee  mov     [rbp+57h+var_D0], esi
0x1800846f1  cmp     [rcx+10h], sil
0x1800846f5  jnz     short loc_180084736
0x1800846f7  cmp     byte ptr [rcx+11h], 0
0x1800846fb  jnz     short loc_180084703
0x1800846fd  cmp     byte ptr [rcx+10h], 0
0x180084701  jnz     short loc_18008472D
0x180084703  xor     r8d, r8d
0x180084706  xor     edx, edx
0x180084708  call    btreeBeginTrans
0x18008470d  mov     esi, eax
0x18008470f  test    eax, eax
0x180084711  jz      short loc_18008472D
0x180084713  mov     ecx, eax
0x180084715  call    sqlite3_errstr
0x18008471a  mov     r8, rax
0x18008471d  mov     rdx, rbx
0x180084720  mov     rcx, r15
0x180084723  call    sqlite3SetString
0x180084728  jmp     loc_180084AAF
0x18008472d  mov     [rbp+57h+var_D0], 1
0x180084734  xor     esi, esi
0x180084736  mov     eax, esi
0x180084738  nop     dword ptr [rax+rax+00000000h]
0x180084740  mov     rcx, [r14+8]
0x180084744  lea     edi, [rax+1]
0x180084747  lea     r8, [rbp+57h+var_C8]
0x18008474b  mov     edx, edi
0x18008474d  lea     r8, [r8+rax*4]
0x180084751  call    sqlite3BtreeGetMeta
0x180084756  mov     eax, edi
0x180084758  cmp     edi, 5
0x18008475b  jl      short loc_180084740
0x18008475d  mov     eax, [rbx+30h]
0x180084760  bt      rax, 19h
0x180084765  jnb     short loc_180084772
0x180084767  xorps   xmm0, xmm0
0x18008476a  xor     edx, edx
0x18008476c  movups  [rbp+57h+var_C8], xmm0
0x180084770  jmp     short loc_180084775
0x180084772  mov     edx, [rbp+57h+var_B8]
0x180084775  mov     rcx, [r14+18h]
0x180084779  mov     eax, dword ptr [rbp+57h+var_C8]
0x18008477c  mov     [rcx], eax
0x18008477e  test    edx, edx
0x180084780  jz      short loc_1800847C4
0x180084782  test    r13d, r13d
0x180084785  jnz     short loc_1800847FD
0x180084787  mov     ecx, [rbx+2Ch]
0x18008478a  test    cl, 40h
0x18008478d  jnz     short loc_1800847FD
0x18008478f  movzx   eax, dl
0x180084792  and     al, 3
0x180084794  movzx   edx, al
0x180084797  mov     eax, 1
0x18008479c  cmovz   edx, eax
0x18008479f  cmp     [rbx+0D8h], r13d
0x1800847a6  jle     short loc_1800847BC
0x1800847a8  cmp     dl, [rbx+64h]
0x1800847ab  jz      short loc_1800847BC
0x1800847ad  test    cl, 4
0x1800847b0  jnz     short loc_1800847BC
0x1800847b2  mov     esi, 6
0x1800847b7  jmp     loc_180084AA0
0x1800847bc  mov     rcx, rbx
0x1800847bf  call    sqlite3SetTextEncoding
0x1800847c4  mov     rcx, [r14+18h]
0x1800847c8  movzx   eax, byte ptr [rbx+64h]
0x1800847cc  mov     [rcx+71h], al
0x1800847cf  mov     rcx, [r14+18h]
0x1800847d3  cmp     dword ptr [rcx+74h], 0
0x1800847d7  jnz     loc_1800848FF
0x1800847dd  mov     eax, dword ptr [rbp+57h+var_C8+8]
0x1800847e0  test    eax, eax
0x1800847e2  jns     loc_1800848E5
0x1800847e8  cmp     eax, 80000000h
0x1800847ed  jnz     loc_1800848E1
0x1800847f3  mov     eax, 7FFFFFFFh
0x1800847f8  jmp     loc_1800848EC
0x1800847fd  and     edx, 3
0x180084800  cmp     dl, [rbx+64h]
0x180084803  jz      short loc_1800847C4
0x180084805  mov     edx, 44h ; 'D'
0x18008480a  mov     rcx, rbx
0x18008480d  call    sqlite3DbMallocRawNN
0x180084812  mov     rdi, rax
0x180084815  test    rax, rax
0x180084818  jz      short loc_18008484E
0x18008481a  movaps  xmm0, xmmword ptr cs:aAttachedDataba; "attached databases must use the same te"...
0x180084821  movups  xmmword ptr [rax], xmm0
0x180084824  movaps  xmm1, xmmword ptr cs:aAttachedDataba+10h; "es must use the same text encoding as m"...
0x18008482b  movups  xmmword ptr [rax+10h], xmm1
0x18008482f  movaps  xmm0, xmmword ptr cs:aAttachedDataba+20h; "same text encoding as main database"
0x180084836  movups  xmmword ptr [rax+20h], xmm0
0x18008483a  movaps  xmm1, xmmword ptr cs:aAttachedDataba+30h; "ng as main database"
0x180084841  movups  xmmword ptr [rax+30h], xmm1
0x180084845  mov     eax, dword ptr cs:aAttachedDataba+40h; "ase"
0x18008484b  mov     [rdi+40h], eax
0x18008484e  mov     rcx, [r15]
0x180084851  test    rcx, rcx
0x180084854  jz      short loc_1800848D4
0x180084856  cmp     rcx, [rbx+1F0h]
0x18008485d  jnb     short loc_1800848AD
0x18008485f  cmp     rcx, [rbx+1E0h]
0x180084866  jb      short loc_180084886
0x180084868  mov     rax, [rbx+1D8h]
0x18008486f  mov     esi, 1
0x180084874  mov     [rcx], rax
0x180084877  mov     [rbx+1D8h], rcx
0x18008487e  mov     [r15], rdi
0x180084881  jmp     loc_180084AA0
0x180084886  cmp     rcx, [rbx+1E8h]
0x18008488d  jb      short loc_1800848AD
0x18008488f  mov     rax, [rbx+1C8h]
0x180084896  mov     esi, 1
0x18008489b  mov     [rcx], rax
0x18008489e  mov     [rbx+1C8h], rcx
0x1800848a5  mov     [r15], rdi
0x1800848a8  jmp     loc_180084AA0
0x1800848ad  cmp     qword ptr [rbx+308h], 0
0x1800848b5  jz      short loc_1800848CF
0x1800848b7  mov     rdx, rcx
0x1800848ba  mov     rcx, rbx
0x1800848bd  call    measureAllocationSize
0x1800848c2  mov     [r15], rdi
0x1800848c5  mov     esi, 1
0x1800848ca  jmp     loc_180084AA0
0x1800848cf  call    sqlite3_free
0x1800848d4  mov     [r15], rdi
0x1800848d7  mov     esi, 1
0x1800848dc  jmp     loc_180084AA0
0x1800848e1  neg     eax
0x1800848e3  test    eax, eax
0x1800848e5  jnz     short loc_1800848EC
0x1800848e7  mov     eax, 0FFFFF830h
0x1800848ec  mov     [rcx+74h], eax
0x1800848ef  mov     rdx, [r14+18h]
0x1800848f3  mov     rcx, [r14+8]
0x1800848f7  mov     edx, [rdx+74h]
0x1800848fa  call    sqlite3BtreeSetCacheSize
0x1800848ff  movzx   eax, byte ptr [rbp+57h+var_C8+4]
0x180084903  mov     rcx, [r14+18h]
0x180084907  mov     [rcx+70h], al
0x18008490a  mov     rax, [r14+18h]
0x18008490e  cmp     byte ptr [rax+70h], 0
0x180084912  jnz     short loc_180084918
0x180084914  mov     byte ptr [rax+70h], 1
0x180084918  mov     rax, [r14+18h]
0x18008491c  cmp     byte ptr [rax+70h], 4
0x180084920  jbe     short loc_180084979
0x180084922  mov     edx, 18h
0x180084927  mov     rcx, rbx
0x18008492a  call    sqlite3DbMallocRawNN
0x18008492f  mov     rdi, rax
0x180084932  test    rax, rax
0x180084935  jz      short loc_18008494E
0x180084937  movups  xmm0, xmmword ptr cs:aUnsupportedFil; "unsupported file format"
0x18008493e  movups  xmmword ptr [rax], xmm0
0x180084941  movsd   xmm1, qword ptr cs:aUnsupportedFil+10h; " format"
0x180084949  movsd   qword ptr [rax+10h], xmm1
0x18008494e  mov     rcx, [r15]
0x180084951  test    rcx, rcx
0x180084954  jz      loc_1800848D4
0x18008495a  cmp     rcx, [rbx+1F0h]
0x180084961  jnb     loc_1800848AD
0x180084967  cmp     rcx, [rbx+1E0h]
0x18008496e  jnb     loc_180084868
0x180084974  jmp     loc_180084886
0x180084979  test    r13d, r13d
0x18008497c  jnz     short loc_180084989
0x18008497e  cmp     dword ptr [rbp+57h+var_C8+4], 4
0x180084982  jl      short loc_180084989
0x180084984  and     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFDh
0x180084989  mov     rax, [r14+8]
0x18008498d  lea     rdx, aSelectFromWSOr; "SELECT*FROM\"%w\".%s ORDER BY rowid"
0x180084994  mov     r8, [rbx+20h]
0x180084998  mov     r9, [rbp+57h+var_88]
0x18008499c  mov     rcx, [rax+8]
0x1800849a0  mov     eax, [rcx+40h]
0x1800849a3  mov     rcx, rbx
0x1800849a6  mov     dword ptr [rbp+57h+var_94+4], eax
0x1800849a9  mov     r8, [r8+r12]
0x1800849ad  call    sqlite3MPrintf
0x1800849b2  mov     rdi, [rbx+200h]
0x1800849b9  lea     r9, [rbp+57h+var_B0]
0x1800849bd  lea     r8, sqlite3InitCallback
0x1800849c4  mov     [rbx+200h], rsi
0x1800849cb  mov     rdx, rax
0x1800849ce  mov     [rsp+100h+var_E0], rsi
0x1800849d3  mov     rcx, rbx
0x1800849d6  mov     r15, rax
0x1800849d9  call    sqlite3_exec
0x1800849de  test    eax, eax
0x1800849e0  mov     [rbx+200h], rdi
0x1800849e7  mov     esi, eax
0x1800849e9  cmovz   esi, [rbp+57h+var_9C]
0x1800849ed  test    r15, r15
0x1800849f0  jz      short loc_180084A52
0x1800849f2  cmp     r15, [rbx+1F0h]
0x1800849f9  jnb     short loc_180084A33
0x1800849fb  cmp     r15, [rbx+1E0h]
0x180084a02  jb      short loc_180084A17
0x180084a04  mov     rax, [rbx+1D8h]
0x180084a0b  mov     [r15], rax
0x180084a0e  mov     [rbx+1D8h], r15
0x180084a15  jmp     short loc_180084A52
0x180084a17  cmp     r15, [rbx+1E8h]
0x180084a1e  jb      short loc_180084A33
0x180084a20  mov     rax, [rbx+1C8h]
0x180084a27  mov     [r15], rax
0x180084a2a  mov     [rbx+1C8h], r15
0x180084a31  jmp     short loc_180084A52
0x180084a33  cmp     qword ptr [rbx+308h], 0
0x180084a3b  jz      short loc_180084A4A
0x180084a3d  mov     rdx, r15
0x180084a40  mov     rcx, rbx
0x180084a43  call    measureAllocationSize
0x180084a48  jmp     short loc_180084A52
0x180084a4a  mov     rcx, r15
0x180084a4d  call    sqlite3_free
0x180084a52  test    esi, esi
0x180084a54  jnz     short loc_180084A61
0x180084a56  mov     edx, r13d
0x180084a59  mov     rcx, rbx
0x180084a5c  call    sqlite3AnalysisLoad
0x180084a61  cmp     byte ptr [rbx+67h], 0
0x180084a65  jz      short loc_180084A7D
0x180084a67  mov     rcx, rbx
0x180084a6a  mov     esi, 7
  ... truncated ...
```
