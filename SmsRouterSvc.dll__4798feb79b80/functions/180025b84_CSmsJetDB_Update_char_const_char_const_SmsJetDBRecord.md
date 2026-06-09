# CSmsJetDB::Update(char const *,char const *,SmsJetDBRecord *)

- ea: `0x180025b84`
- end: `0x18002604e`
- name: `?Update@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z`
- size: `1226`
- prototype: `int(CSmsJetDB *__hidden this, const char *, const char *, struct SmsJetDBRecord *)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001bbbc`
- `0x18001eec0`
- `0x18001f194`
- `0x18001f378`

## callees

- `0x180003a90`
- `0x180004974`
- `0x18000b07c`
- `0x18000ba3c`
- `0x180018f40`
- `0x1800205b8`
- `0x180022484`
- `0x180022678`
- `0x180022b9c`
- `0x180023a58`
- `0x180023b2c`
- `0x180023c24`
- `0x180023f9c`
- `0x180025b84`
- `0x1800261a0`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x180025c81`
- `ESENT!JetSetCurrentIndexA` at `0x180025c81`
- `ESENT!JetPrepareUpdate` at `0x180025f51`
- `ESENT!JetPrepareUpdate` at `0x180025f51`
- `ESENT!JetSeek` at `0x180025d9c`
- `ESENT!JetSeek` at `0x180025d9c`
- `ESENT!JetMove` at `0x180025cb5`
- `ESENT!JetMove` at `0x180025cb5`
- `ESENT!JetSetColumns` at `0x180025f87`
- `ESENT!JetSetColumns` at `0x180025f87`
- `ESENT!JetMakeKey` at `0x180025d41`
- `ESENT!JetMakeKey` at `0x180025d41`
- `ESENT!JetUpdate` at `0x180025faf`
- `ESENT!JetUpdate` at `0x180025faf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSmsJetDB::Update(JET_SESID *this, const char *a2, const char *a3, struct SmsJetDBRecord *a4)
{
  unsigned int TableIndex; // eax
  unsigned __int64 v8; // rdi
  __int64 IndexIndex; // rsi
  _QWORD *v10; // rax
  JET_ERR Key; // eax
  JET_ERR v12; // ecx
  unsigned int v13; // ebx
  unsigned int v14; // r14d
  __int64 v15; // rdx
  __int64 v16; // r12
  __int64 v17; // rax
  _QWORD *v18; // rsi
  __int64 v19; // r15
  const char *v20; // rdx
  int v21; // eax
  unsigned int v22; // r8d
  JET_SESID v23; // rdx
  __int64 v24; // r14
  _QWORD *v25; // rsi
  __int64 v26; // r13
  _QWORD *v27; // rdx
  size_t v28; // r12
  size_t v29; // r15
  size_t v30; // r8
  int v31; // eax
  __int64 v32; // rsi
  __int64 v33; // r14
  __int64 v34; // rdx
  JET_SETCOLUMN *v35; // rdx
  JET_ERR v36; // eax
  JET_ERR v37; // ecx
  int v38; // eax
  JET_SETCOLUMN *psetcolumn[2]; // [rsp+30h] [rbp-69h] BYREF
  JET_SETCOLUMN *v41; // [rsp+40h] [rbp-59h]
  _QWORD v42[2]; // [rsp+48h] [rbp-51h] BYREF
  __int128 v43; // [rsp+58h] [rbp-41h] BYREF
  __int64 v44; // [rsp+68h] [rbp-31h]
  __int128 v45; // [rsp+70h] [rbp-29h] BYREF
  __int128 v46; // [rsp+80h] [rbp-19h]
  __int64 v47; // [rsp+90h] [rbp-9h]
  _QWORD v48[3]; // [rsp+98h] [rbp-1h] BYREF
  __int64 v49[8]; // [rsp+B0h] [rbp+17h] BYREF
  unsigned int v50; // [rsp+100h] [rbp+67h]

  TableIndex = CSmsJetDB::GetTableIndex((CSmsJetDB *)this, a2);
  if ( TableIndex == this[5] )
    return 2147943568LL;
  v8 = (unsigned __int64)TableIndex << 7;
  IndexIndex = TableDefinition::GetIndexIndex((TableDefinition *)(v8 + this[1]), a3);
  if ( IndexIndex == (__int64)(*(_QWORD *)(v8 + this[1] + 72) - *(_QWORD *)(v8 + this[1] + 64)) >> 6 )
    return 2147943568LL;
  v43 = 0;
  v44 = 0;
  v42[1] = 0;
  v10 = operator new(0x40u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  v42[0] = v10;
  IndexDefinition::GetKeyColumns(*(_QWORD *)(v8 + this[1] + 64) + (IndexIndex << 6), &v43);
  std::vector<SmsJetDBValue>::vector<SmsJetDBValue>(
    v48,
    0x6DB6DB6DB6DB6DB7LL * ((__int64)(*(_QWORD *)(v8 + this[1] + 48) - *(_QWORD *)(v8 + this[1] + 40)) >> 3));
  Key = JetSetCurrentIndexA(this[6], *(_QWORD *)(v8 + this[1] + 88), a3);
  v12 = Key;
  if ( Key < 0 || (Key = JetMove(this[6], *(_QWORD *)(v8 + this[1] + 88), 0x80000000, 0), v12 = Key, Key < 0) )
  {
LABEL_4:
    if ( v12 == -1011 )
    {
      v13 = -2147024882;
    }
    else
    {
      v21 = -Key;
      if ( v21 < 0 )
        LOWORD(v21) = v12;
      v13 = (unsigned __int16)v21 | 0x8E5E0000;
    }
    goto LABEL_48;
  }
  v14 = 0;
  v15 = v43;
  if ( (__int64)(*((_QWORD *)&v43 + 1) - v43) >> 5 )
  {
    v16 = v48[0];
    do
    {
      v17 = 32LL * v14;
      v18 = (_QWORD *)(v17 + v15);
      v19 = v17 + v16;
      v20 = (const char *)(*(_QWORD *)(v17 + v15 + 24) <= 0xFu ? v17 + v15 : *v18);
      SmsJetDBRecord::GetFieldValue(a4, v20, (struct SmsJetDBValue *)(v17 + v16));
      Key = JetMakeKey(
              this[6],
              *(_QWORD *)(this[1] + v8 + 88),
              *(const void **)(v19 + 8),
              *(_DWORD *)(v19 + 16) - *(_DWORD *)(v19 + 8),
              v14 == 0);
      v12 = Key;
      if ( Key < 0 )
        goto LABEL_4;
      std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::insert<0,0>(
        v42,
        v49,
        v18);
      ++v14;
      v15 = v43;
    }
    while ( v14 < (unsigned __int64)((__int64)(*((_QWORD *)&v43 + 1) - v43) >> 5) );
  }
  if ( JetSeek(this[6], *(_QWORD *)(v8 + this[1] + 88), 0x21u) )
  {
    v13 = -1906440639;
LABEL_48:
    std::vector<SmsJetDBValue>::_Tidy(v48);
    std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(v42);
    std::vector<std::string>::_Tidy(&v43);
    return v13;
  }
  *(_OWORD *)psetcolumn = 0;
  v41 = 0;
  v22 = 0;
  v50 = 0;
  v23 = this[1];
  if ( 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*(_QWORD *)(v23 + v8 + 48) - *(_QWORD *)(v23 + v8 + 40)) >> 3) )
  {
    while ( 1 )
    {
      v24 = v22;
      v49[0] = 56LL * v22;
      v25 = (_QWORD *)(*(_QWORD *)(v23 + v8 + 40) + v49[0] + 8);
      std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Find_lower_bound<std::string>(
        v42,
        &v45,
        v25);
      v26 = v46;
      if ( *(_BYTE *)(v46 + 25) )
        break;
      v27 = (_QWORD *)(v46 + 32);
      v28 = *(_QWORD *)(v46 + 48);
      if ( *(_QWORD *)(v46 + 56) > 0xFu )
        v27 = (_QWORD *)*v27;
      v29 = v25[2];
      if ( v25[3] > 0xFu )
        v25 = (_QWORD *)*v25;
      v30 = v29;
      if ( v28 < v29 )
        v30 = *(_QWORD *)(v46 + 48);
      v31 = memcmp_0(v25, v27, v30);
      if ( v31 )
      {
        if ( v31 < 0 )
          break;
      }
      else if ( v29 < v28 )
      {
        break;
      }
      if ( v26 == v42[0] )
        break;
LABEL_38:
      v22 = v50 + 1;
      v50 = v22;
      v23 = this[1];
      if ( v22 >= (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL
                                   * ((__int64)(*(_QWORD *)(v23 + v8 + 48) - *(_QWORD *)(v23 + v8 + 40)) >> 3)) )
        goto LABEL_39;
    }
    v32 = 32 * v24 + v48[0];
    v33 = v49[0];
    v34 = *(_QWORD *)(v8 + this[1] + 40) + v49[0] + 8;
    if ( *(_QWORD *)(v34 + 24) > 0xFu )
      v34 = *(_QWORD *)v34;
    if ( (unsigned int)SmsJetDBRecord::GetFieldValue(a4, (const char *)v34, (struct SmsJetDBValue *)v32) )
    {
      DWORD1(v45) = 0;
      *(_QWORD *)((char *)&v46 + 4) = 0;
      v47 = 0;
      LODWORD(v45) = *(_DWORD *)(*(_QWORD *)(v8 + this[1] + 40) + v33 + 48);
      *((_QWORD *)&v45 + 1) = *(_QWORD *)(v32 + 8);
      LODWORD(v46) = *(_DWORD *)(v32 + 16) - *(_DWORD *)(v32 + 8);
      HIDWORD(v46) = 1;
      v35 = psetcolumn[1];
      if ( psetcolumn[1] == v41 )
      {
        std::vector<JET_SETCOLUMN>::_Emplace_reallocate<JET_SETCOLUMN const &>(psetcolumn, psetcolumn[1], &v45);
      }
      else
      {
        *(_OWORD *)psetcolumn[1] = v45;
        *(_OWORD *)&v35->cbData = v46;
        *(_QWORD *)&v35->err = v47;
        ++psetcolumn[1];
      }
    }
    goto LABEL_38;
  }
LABEL_39:
  v36 = JetPrepareUpdate(this[6], *(_QWORD *)(v8 + v23 + 88), 2u);
  v37 = v36;
  if ( v36 < 0
    || (v36 = JetSetColumns(
                this[6],
                *(_QWORD *)(v8 + this[1] + 88),
                psetcolumn[0],
                -858993459 * (((char *)psetcolumn[1] - (char *)psetcolumn[0]) >> 3)),
        v37 = v36,
        v36 < 0)
    || (v36 = JetUpdate(this[6], *(_QWORD *)(v8 + this[1] + 88), 0, 0, 0), v37 = v36, v36 < 0) )
  {
    if ( v37 == -1011 )
    {
      v13 = -2147024882;
    }
    else
    {
      v38 = -v36;
      if ( v38 < 0 )
        LOWORD(v38) = v37;
      v13 = (unsigned __int16)v38 | 0x8E5E0000;
    }
    std::vector<JET_SETCOLUMN>::~vector<JET_SETCOLUMN>(psetcolumn);
    goto LABEL_48;
  }
  std::vector<JET_SETCOLUMN>::~vector<JET_SETCOLUMN>(psetcolumn);
  std::vector<SmsJetDBValue>::_Tidy(v48);
  std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(v42);
  std::vector<std::string>::_Tidy(&v43);
  return 0;
}

```

## disassembly

```asm
0x180025b84  mov     [rsp-8+arg_8], rbx
0x180025b89  mov     [rsp-8+arg_18], r9
0x180025b8e  push    rbp
0x180025b8f  push    rsi
0x180025b90  push    rdi
0x180025b91  push    r12
0x180025b93  push    r13
0x180025b95  push    r14
0x180025b97  push    r15
0x180025b99  lea     rbp, [rsp-27h]
0x180025b9e  sub     rsp, 0C0h
0x180025ba5  mov     r13, r9
0x180025ba8  mov     r14, r8
0x180025bab  mov     rbx, rcx
0x180025bae  call    ?GetTableIndex@CSmsJetDB@@AEAAKPEBD@Z; CSmsJetDB::GetTableIndex(char const *)
0x180025bb3  mov     edi, eax
0x180025bb5  cmp     rdi, [rbx+28h]
0x180025bb9  jz      loc_18002602E
0x180025bbf  shl     rdi, 7
0x180025bc3  mov     rcx, [rbx+8]
0x180025bc7  add     rcx, rdi; this
0x180025bca  mov     rdx, r14; char *
0x180025bcd  call    ?GetIndexIndex@TableDefinition@@QEAAKPEBD@Z; TableDefinition::GetIndexIndex(char const *)
0x180025bd2  mov     rcx, [rbx+8]
0x180025bd6  mov     esi, eax
0x180025bd8  mov     rax, [rdi+rcx+48h]
0x180025bdd  sub     rax, [rdi+rcx+40h]
0x180025be2  sar     rax, 6
0x180025be6  cmp     rsi, rax
0x180025be9  jz      loc_18002602E
0x180025bef  xorps   xmm0, xmm0
0x180025bf2  movdqu  [rbp+57h+var_98], xmm0
0x180025bf7  mov     [rbp+57h+var_88], 0
0x180025bff  mov     [rbp+57h+var_A8], 0
0x180025c07  mov     [rbp+57h+var_A0], 0
0x180025c0f  mov     ecx, 40h ; '@'; Size
0x180025c14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025c19  mov     [rax], rax
0x180025c1c  mov     [rax+8], rax
0x180025c20  mov     [rax+10h], rax
0x180025c24  mov     word ptr [rax+18h], 101h
0x180025c2a  mov     [rbp+57h+var_A8], rax
0x180025c2e  mov     rax, [rbx+8]
0x180025c32  shl     rsi, 6
0x180025c36  add     rsi, [rdi+rax+40h]
0x180025c3b  lea     rdx, [rbp+57h+var_98]
0x180025c3f  mov     rcx, rsi
0x180025c42  call    ?GetKeyColumns@IndexDefinition@@QEAAXAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z; IndexDefinition::GetKeyColumns(std::vector<std::string> &)
0x180025c47  mov     rax, [rbx+8]
0x180025c4b  mov     rdx, [rdi+rax+30h]
0x180025c50  sub     rdx, [rdi+rax+28h]
0x180025c55  sar     rdx, 3
0x180025c59  mov     rsi, 6DB6DB6DB6DB6DB7h
0x180025c63  imul    rdx, rsi
0x180025c67  lea     rcx, [rbp+57h+var_58]
0x180025c6b  call    ??0?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@QEAA@_KAEBV?$allocator@VSmsJetDBValue@@@1@@Z; std::vector<SmsJetDBValue>::vector<SmsJetDBValue>(unsigned __int64,std::allocator<SmsJetDBValue> const &)
0x180025c70  nop
0x180025c71  mov     rdx, [rbx+8]
0x180025c75  mov     r8, r14; szIndexName
0x180025c78  mov     rdx, [rdi+rdx+58h]; tableid
0x180025c7d  mov     rcx, [rbx+30h]; sesid
0x180025c81  call    cs:__imp_JetSetCurrentIndexA
0x180025c87  mov     ecx, eax
0x180025c89  test    eax, eax
0x180025c8b  jns     short loc_180025C9F
0x180025c8d  cmp     ecx, 0FFFFFC0Dh
0x180025c93  jnz     short loc_180025CFB
0x180025c95  mov     ebx, 8007000Eh
0x180025c9a  jmp     loc_180025FE2
0x180025c9f  mov     rdx, [rbx+8]
0x180025ca3  xor     r9d, r9d; grbit
0x180025ca6  mov     r8d, 80000000h; cRow
0x180025cac  mov     rdx, [rdi+rdx+58h]; tableid
0x180025cb1  mov     rcx, [rbx+30h]; sesid
0x180025cb5  call    cs:__imp_JetMove
0x180025cbb  mov     ecx, eax
0x180025cbd  test    eax, eax
0x180025cbf  js      short loc_180025C8D
0x180025cc1  xor     r14d, r14d
0x180025cc4  mov     rax, qword ptr [rbp+57h+var_98+8]
0x180025cc8  mov     rdx, qword ptr [rbp+57h+var_98]
0x180025ccc  sub     rax, rdx
0x180025ccf  sar     rax, 5
0x180025cd3  test    rax, rax
0x180025cd6  jz      loc_180025D89
0x180025cdc  mov     r12, [rbp+57h+var_58]
0x180025ce0  mov     eax, r14d
0x180025ce3  shl     rax, 5
0x180025ce7  lea     rsi, [rax+rdx]
0x180025ceb  lea     r15, [rax+r12]
0x180025cef  cmp     qword ptr [rsi+18h], 0Fh
0x180025cf4  jbe     short loc_180025D0E
0x180025cf6  mov     rdx, [rsi]
0x180025cf9  jmp     short loc_180025D11
0x180025cfb  neg     eax
0x180025cfd  cmovs   eax, ecx
0x180025d00  movzx   ebx, ax
0x180025d03  or      ebx, 8E5E0000h
0x180025d09  jmp     loc_180025FE2
0x180025d0e  mov     rdx, rsi; char *
0x180025d11  mov     r8, r15; struct SmsJetDBValue *
0x180025d14  mov     rcx, r13; this
0x180025d17  call    ?GetFieldValue@SmsJetDBRecord@@QEAAHPEBDPEAVSmsJetDBValue@@@Z; SmsJetDBRecord::GetFieldValue(char const *,SmsJetDBValue *)
0x180025d1c  xor     eax, eax
0x180025d1e  test    r14d, r14d
0x180025d21  setz    al
0x180025d24  mov     r9d, [r15+10h]
0x180025d28  sub     r9d, [r15+8]; cbData
0x180025d2c  mov     rdx, [rbx+8]
0x180025d30  mov     [rsp+0F0h+grbit], eax; grbit
0x180025d34  mov     r8, [r15+8]; pvData
0x180025d38  mov     rdx, [rdx+rdi+58h]; tableid
0x180025d3d  mov     rcx, [rbx+30h]; sesid
0x180025d41  call    cs:__imp_JetMakeKey
0x180025d47  mov     ecx, eax
0x180025d49  test    eax, eax
0x180025d4b  js      loc_180025C8D
0x180025d51  mov     r8, rsi
0x180025d54  lea     rdx, [rbp+57h+var_40]
0x180025d58  lea     rcx, [rbp+57h+var_A8]
0x180025d5c  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::insert<0,0>(std::string const &)
0x180025d61  inc     r14d
0x180025d64  mov     rcx, qword ptr [rbp+57h+var_98+8]
0x180025d68  mov     rdx, qword ptr [rbp+57h+var_98]
0x180025d6c  sub     rcx, rdx
0x180025d6f  sar     rcx, 5
0x180025d73  mov     eax, r14d
0x180025d76  cmp     rax, rcx
0x180025d79  jb      loc_180025CE0
0x180025d7f  mov     rsi, 6DB6DB6DB6DB6DB7h
0x180025d89  mov     rdx, [rbx+8]
0x180025d8d  mov     r8d, 21h ; '!'; grbit
0x180025d93  mov     rdx, [rdi+rdx+58h]; tableid
0x180025d98  mov     rcx, [rbx+30h]; sesid
0x180025d9c  call    cs:__imp_JetSeek
0x180025da2  test    eax, eax
0x180025da4  jz      short loc_180025DB0
0x180025da6  mov     ebx, 8E5E0641h
0x180025dab  jmp     loc_180025FE2
0x180025db0  xorps   xmm0, xmm0
0x180025db3  movdqu  xmmword ptr [rbp+57h+psetcolumn], xmm0
0x180025db8  mov     [rbp+57h+var_B0], 0
0x180025dc0  xor     r8d, r8d
0x180025dc3  mov     [rbp+57h+arg_0], r8d
0x180025dc7  mov     rdx, [rbx+8]
0x180025dcb  mov     rax, [rdx+rdi+30h]
0x180025dd0  sub     rax, [rdx+rdi+28h]
0x180025dd5  sar     rax, 3
0x180025dd9  imul    rax, rsi
0x180025ddd  test    rax, rax
0x180025de0  jz      loc_180025F42
0x180025de6  mov     r14d, r8d
0x180025de9  imul    rcx, r14, 38h ; '8'
0x180025ded  mov     [rbp+57h+var_40], rcx
0x180025df1  lea     rsi, [rcx+8]
0x180025df5  add     rsi, [rdx+rdi+28h]
0x180025dfa  mov     r8, rsi
0x180025dfd  lea     rdx, [rbp+57h+var_80]
0x180025e01  lea     rcx, [rbp+57h+var_A8]
0x180025e05  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x180025e0a  mov     r13, qword ptr [rbp+57h+var_70]
0x180025e0e  cmp     byte ptr [r13+19h], 0
0x180025e13  jnz     short loc_180025E5E
0x180025e15  lea     rdx, [r13+20h]
0x180025e19  mov     r12, [rdx+10h]
0x180025e1d  cmp     qword ptr [rdx+18h], 0Fh
0x180025e22  jbe     short loc_180025E27
0x180025e24  mov     rdx, [rdx]; Buf2
0x180025e27  mov     r15, [rsi+10h]
0x180025e2b  cmp     qword ptr [rsi+18h], 0Fh
0x180025e30  jbe     short loc_180025E35
0x180025e32  mov     rsi, [rsi]
0x180025e35  mov     r8, r15
0x180025e38  cmp     r12, r15
0x180025e3b  cmovb   r8, r12; Size
0x180025e3f  mov     rcx, rsi; Buf1
0x180025e42  call    memcmp_0
0x180025e47  test    eax, eax
0x180025e49  jz      short loc_180025E4F
0x180025e4b  jns     short loc_180025E54
0x180025e4d  jmp     short loc_180025E5E
0x180025e4f  cmp     r15, r12
0x180025e52  jb      short loc_180025E5E
0x180025e54  cmp     r13, [rbp+57h+var_A8]
0x180025e58  jnz     loc_180025F0B
0x180025e5e  shl     r14, 5
0x180025e62  mov     rsi, [rbp+57h+var_58]
0x180025e66  add     rsi, r14
0x180025e69  mov     rax, [rbx+8]
0x180025e6d  mov     r14, [rbp+57h+var_40]
0x180025e71  lea     rdx, [r14+8]
0x180025e75  add     rdx, [rdi+rax+28h]
0x180025e7a  cmp     qword ptr [rdx+18h], 0Fh
0x180025e7f  jbe     short loc_180025E84
0x180025e81  mov     rdx, [rdx]; char *
0x180025e84  mov     r8, rsi; struct SmsJetDBValue *
0x180025e87  mov     rcx, [rbp+57h+arg_18]; this
0x180025e8b  call    ?GetFieldValue@SmsJetDBRecord@@QEAAHPEBDPEAVSmsJetDBValue@@@Z; SmsJetDBRecord::GetFieldValue(char const *,SmsJetDBValue *)
0x180025e90  test    eax, eax
0x180025e92  jz      short loc_180025F0B
0x180025e94  mov     dword ptr [rbp+57h+var_80+4], 0
0x180025e9b  mov     qword ptr [rbp+57h+var_70+4], 0
0x180025ea3  mov     [rbp+57h+var_60], 0
0x180025eab  mov     rax, [rbx+8]
0x180025eaf  mov     rcx, [rdi+rax+28h]
0x180025eb4  mov     eax, [rcx+r14+30h]
0x180025eb9  mov     dword ptr [rbp+57h+var_80], eax
0x180025ebc  mov     rax, [rsi+8]
0x180025ec0  mov     qword ptr [rbp+57h+var_80+8], rax
0x180025ec4  mov     eax, [rsi+10h]
0x180025ec7  sub     eax, [rsi+8]
0x180025eca  mov     dword ptr [rbp+57h+var_70], eax
0x180025ecd  mov     dword ptr [rbp+57h+var_70+0Ch], 1
0x180025ed4  mov     rdx, [rbp+57h+psetcolumn+8]
0x180025ed8  cmp     rdx, [rbp+57h+var_B0]
0x180025edc  jz      short loc_180025EFE
0x180025ede  movups  xmm0, [rbp+57h+var_80]
0x180025ee2  movups  xmmword ptr [rdx], xmm0
0x180025ee5  movups  xmm1, [rbp+57h+var_70]
0x180025ee9  movups  xmmword ptr [rdx+10h], xmm1
0x180025eed  movsd   xmm0, [rbp+57h+var_60]
0x180025ef2  movsd   qword ptr [rdx+20h], xmm0
0x180025ef7  add     [rbp+57h+psetcolumn+8], 28h ; '('
0x180025efc  jmp     short loc_180025F0B
0x180025efe  lea     r8, [rbp+57h+var_80]
0x180025f02  lea     rcx, [rbp+57h+psetcolumn]
0x180025f06  call    ??$_Emplace_reallocate@AEBUJET_SETCOLUMN@@@?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@std@@@std@@AEAAPEAUJET_SETCOLUMN@@QEAU2@AEBU2@@Z; std::vector<JET_SETCOLUMN>::_Emplace_reallocate<JET_SETCOLUMN const &>(JET_SETCOLUMN * const,JET_SETCOLUMN const &)
0x180025f0b  mov     r8d, [rbp+57h+arg_0]
0x180025f0f  inc     r8d
0x180025f12  mov     [rbp+57h+arg_0], r8d
0x180025f16  mov     rdx, [rbx+8]
0x180025f1a  mov     rcx, [rdx+rdi+30h]
0x180025f1f  sub     rcx, [rdx+rdi+28h]
0x180025f24  sar     rcx, 3
0x180025f28  mov     rax, 6DB6DB6DB6DB6DB7h
0x180025f32  imul    rcx, rax
0x180025f36  mov     eax, r8d
0x180025f39  cmp     rax, rcx
0x180025f3c  jb      loc_180025DE6
0x180025f42  mov     r8d, 2; prep
0x180025f48  mov     rdx, [rdi+rdx+58h]; tableid
0x180025f4d  mov     rcx, [rbx+30h]; sesid
0x180025f51  call    cs:__imp_JetPrepareUpdate
0x180025f57  mov     ecx, eax
0x180025f59  test    eax, eax
0x180025f5b  js      short loc_180025FBB
0x180025f5d  mov     r8, [rbp+57h+psetcolumn]; psetcolumn
0x180025f61  mov     r9, [rbp+57h+psetcolumn+8]
0x180025f65  sub     r9, r8
0x180025f68  sar     r9, 3
0x180025f6c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025f76  imul    r9, rax; csetcolumn
0x180025f7a  mov     rdx, [rbx+8]
0x180025f7e  mov     rdx, [rdi+rdx+58h]; tableid
0x180025f83  mov     rcx, [rbx+30h]; sesid
0x180025f87  call    cs:__imp_JetSetColumns
0x180025f8d  mov     ecx, eax
0x180025f8f  test    eax, eax
0x180025f91  js      short loc_180025FBB
0x180025f93  mov     rdx, [rbx+8]
0x180025f97  mov     qword ptr [rsp+0F0h+grbit], 0; pcbActual
0x180025fa0  xor     r9d, r9d; cbBookmark
0x180025fa3  xor     r8d, r8d; pvBookmark
0x180025fa6  mov     rdx, [rdi+rdx+58h]; tableid
0x180025fab  mov     rcx, [rbx+30h]; sesid
0x180025faf  call    cs:__imp_JetUpdate
0x180025fb5  mov     ecx, eax
0x180025fb7  test    eax, eax
0x180025fb9  jns     short loc_180026003
0x180025fbb  cmp     ecx, 0FFFFFC0Dh
0x180025fc1  jnz     short loc_180025FCA
0x180025fc3  mov     ebx, 8007000Eh
0x180025fc8  jmp     short loc_180025FD8
0x180025fca  neg     eax
0x180025fcc  cmovs   eax, ecx
0x180025fcf  movzx   ebx, ax
0x180025fd2  or      ebx, 8E5E0000h
0x180025fd8  lea     rcx, [rbp+57h+psetcolumn]
0x180025fdc  call    ??1?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@std@@@std@@QEAA@XZ; std::vector<JET_SETCOLUMN>::~vector<JET_SETCOLUMN>(void)
0x180025fe1  nop
0x180025fe2  lea     rcx, [rbp+57h+var_58]
0x180025fe6  call    ?_Tidy@?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@AEAAXXZ; std::vector<SmsJetDBValue>::_Tidy(void)
0x180025feb  nop
0x180025fec  lea     rcx, [rbp+57h+var_A8]
0x180025ff0  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(void)
0x180025ff5  nop
0x180025ff6  lea     rcx, [rbp+57h+var_98]
0x180025ffa  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180025fff  mov     eax, ebx
0x180026001  jmp     short loc_180026033
0x180026003  lea     rcx, [rbp+57h+psetcolumn]
0x180026007  call    ??1?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@std@@@std@@QEAA@XZ; std::vector<JET_SETCOLUMN>::~vector<JET_SETCOLUMN>(void)
0x18002600c  nop
0x18002600d  lea     rcx, [rbp+57h+var_58]
0x180026011  call    ?_Tidy@?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@AEAAXXZ; std::vector<SmsJetDBValue>::_Tidy(void)
0x180026016  nop
0x180026017  lea     rcx, [rbp+57h+var_A8]
0x18002601b  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(void)
0x180026020  nop
0x180026021  lea     rcx, [rbp+57h+var_98]
  ... truncated ...
```
