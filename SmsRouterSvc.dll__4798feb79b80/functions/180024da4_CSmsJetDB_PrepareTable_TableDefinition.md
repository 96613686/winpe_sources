# CSmsJetDB::PrepareTable(TableDefinition *)

- ea: `0x180024da4`
- end: `0x180025427`
- name: `?PrepareTable@CSmsJetDB@@AEAAJPEAUTableDefinition@@@Z`
- size: `1667`
- prototype: `__int64 __fastcall(CSmsJetDB *__hidden this, struct TableDefinition *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024674`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x180003f8c`
- `0x180004998`
- `0x180009898`
- `0x18000bac4`
- `0x18000c4fc`
- `0x180022a50`
- `0x180022adc`
- `0x180022e38`
- `0x180024da4`
- `0x180025b04`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x180025271`
- `ESENT!JetOpenTableA` at `0x1800252d1`
- `ESENT!JetOpenTableA` at `0x180025271`
- `ESENT!JetOpenTableA` at `0x1800252d1`
- `ESENT!JetCreateTableColumnIndexA` at `0x18002528c`
- `ESENT!JetCreateTableColumnIndexA` at `0x18002528c`
- `ESENT!JetGetTableColumnInfoA` at `0x18002535e`
- `ESENT!JetGetTableColumnInfoA` at `0x18002535e`
- `ESENT!JetCloseTable` at `0x1800252a0`
- `ESENT!JetCloseTable` at `0x1800252a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsJetDB::PrepareTable(CSmsJetDB *this, struct TableDefinition *a2)
{
  CSmsJetDB *v3; // r13
  int v4; // edx
  unsigned __int64 v5; // r14
  unsigned int v6; // r12d
  unsigned __int64 v7; // rsi
  _QWORD *v8; // rbx
  void *v9; // rax
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r14
  _QWORD *v12; // rbx
  void *v13; // rax
  unsigned int i; // r8d
  __int64 v15; // rdx
  __int64 v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  void *v19; // r15
  unsigned int v20; // r14d
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned __int64 v23; // r13
  unsigned int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // rsi
  const char *v27; // r8
  int v28; // r14d
  __int64 v29; // rsi
  _QWORD *v30; // rcx
  char *v31; // r8
  JET_ERR TableColumnInfoA; // eax
  JET_ERR v33; // ecx
  unsigned int v34; // ebx
  JET_TABLEID tableid; // rdx
  unsigned int v36; // ebx
  __int64 v37; // rcx
  __int64 v38; // rsi
  __int64 v39; // r8
  int v40; // eax
  char **v42; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v43; // [rsp+48h] [rbp-B8h] BYREF
  char *v44; // [rsp+58h] [rbp-A8h]
  __int128 v45; // [rsp+60h] [rbp-A0h] BYREF
  char *v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  CSmsJetDB *v48; // [rsp+80h] [rbp-80h]
  JET_TABLECREATE_A ptablecreate; // [rsp+90h] [rbp-70h] BYREF
  _DWORD pvResult[8]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = this;
  v48 = this;
  memset_0(&ptablecreate, 0, sizeof(ptablecreate));
  v5 = (__int64)(*((_QWORD *)a2 + 9) - *((_QWORD *)a2 + 8)) >> 6;
  v45 = 0;
  v6 = 0;
  v46 = 0;
  if ( v5 )
  {
    if ( v5 > 0x333333333333333LL )
      std::vector<ATL::CComPtr<ISmsDevice>>::_Xlength();
    v7 = 80 * v5;
    if ( 80 * v5 )
    {
      if ( v7 < 0x1000 )
      {
        v8 = operator new(80 * v5);
      }
      else
      {
        if ( v7 + 39 < v7 )
          __scrt_throw_std_bad_array_new_length();
        v9 = operator new(v7 + 39);
        if ( !v9 )
          __fastfail(5u);
        v8 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v8 - 1) = v9;
      }
    }
    else
    {
      v8 = 0;
    }
    *(_QWORD *)&v45 = v8;
    v46 = (char *)&v8[v7 / 8];
    LOBYTE(v4) = 0;
    memset_0(v8, v4, 80 * v5);
    do
    {
      v8 += 10;
      --v5;
    }
    while ( v5 );
    *((_QWORD *)&v45 + 1) = v8;
    v42 = 0;
    std::_Tidy_guard<std::vector<tagJET_INDEXCREATE_A>>::~_Tidy_guard<std::vector<tagJET_INDEXCREATE_A>>(&v42);
  }
  v10 = 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)a2 + 6) - *((_QWORD *)a2 + 5)) >> 3);
  v43 = 0;
  v44 = 0;
  if ( v10 )
  {
    if ( v10 > 0x492492492492492LL )
      std::vector<ATL::CComPtr<ISmsDevice>>::_Xlength();
    v11 = 56 * v10;
    if ( 56 * v10 )
    {
      if ( v11 < 0x1000 )
      {
        v12 = operator new(56 * v10);
      }
      else
      {
        if ( v11 + 39 < v11 )
          __scrt_throw_std_bad_array_new_length();
        v13 = operator new(v11 + 39);
        if ( !v13 )
          __fastfail(5u);
        v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v12 - 1) = v13;
      }
    }
    else
    {
      v12 = 0;
    }
    *(_QWORD *)&v43 = v12;
    v44 = (char *)&v12[v11 / 8];
    LOBYTE(v4) = 0;
    memset_0(v12, v4, 56 * v10);
    do
    {
      v12 += 7;
      --v10;
    }
    while ( v10 );
    *((_QWORD *)&v43 + 1) = v12;
    v42 = 0;
    std::_Tidy_guard<std::vector<tag_JET_COLUMNCREATE_A>>::~_Tidy_guard<std::vector<tag_JET_COLUMNCREATE_A>>(&v42);
  }
  for ( i = 0; i < -1227133513 * (unsigned int)((__int64)(*((_QWORD *)a2 + 6) - *((_QWORD *)a2 + 5)) >> 3); ++i )
  {
    v15 = 56LL * i;
    v16 = v43;
    *(_OWORD *)(v15 + v43) = 0;
    *(_OWORD *)(v15 + v16 + 16) = 0;
    *(_OWORD *)(v15 + v16 + 32) = 0;
    *(_QWORD *)(v15 + v16 + 48) = 0;
    *(_DWORD *)(v15 + v43) = 56;
    v17 = (_QWORD *)(v15 + *((_QWORD *)a2 + 5) + 8LL);
    if ( v17[3] > 0xFu )
      v17 = (_QWORD *)*v17;
    *(_QWORD *)(v15 + v43 + 8) = v17;
    *(_DWORD *)(v15 + v43 + 16) = *(_DWORD *)(v15 + *((_QWORD *)a2 + 5) + 40);
    *(_DWORD *)(v15 + v43 + 24) = *(_DWORD *)(v15 + *((_QWORD *)a2 + 5) + 44);
    v18 = v43;
    if ( ((*(_DWORD *)(v15 + v43 + 16) - 10) & 0xFFFFFFFD) == 0 )
    {
      *(_DWORD *)(v15 + v43 + 44) = 1200;
      v18 = v43;
    }
    if ( (unsigned int)(*(_DWORD *)(v15 + v18 + 16) - 11) <= 1 )
    {
      *(_DWORD *)(v15 + v18 + 20) = 0x10000;
      v18 = v43;
    }
    *(_DWORD *)(v15 + v18 + 52) = 0;
  }
  v19 = operator new[](0x10000u);
  v20 = 0;
  LODWORD(v42) = 0;
  v21 = *((_QWORD *)a2 + 9);
  v22 = *((_QWORD *)a2 + 8);
  if ( (unsigned int)((v21 - v22) >> 6) )
  {
    do
    {
      memset_0(v19, 0, 0x10000u);
      v23 = (unsigned __int64)v20 << 6;
      v24 = 0;
      v47 = *((_QWORD *)a2 + 8);
      v25 = *(_QWORD *)(v47 + v23 + 32);
      if ( (*(_QWORD *)(v47 + v23 + 40) - v25) >> 5 )
      {
        while ( v24 < 0x10000 )
        {
          v26 = 32LL * v6;
          v27 = (const char *)(v26 + v25);
          if ( *(_QWORD *)(v26 + v25 + 24) > 0xFu )
            v27 = *(const char **)v27;
          if ( (int)StringCchPrintfA((char *)v19 + v24, 0x10000 - v24, v27) < 0 )
          {
            v6 = 0;
            *((_BYTE *)v19 + v24++) = 0;
            goto LABEL_46;
          }
          v25 = *(_QWORD *)(v47 + v23 + 32);
          v24 += *(_DWORD *)(v25 + v26 + 16) + 1;
          if ( ++v6 >= (unsigned __int64)((*(_QWORD *)(v47 + v23 + 40) - v25) >> 5) )
          {
            if ( v24 < 0x10000 )
              goto LABEL_43;
            break;
          }
        }
        v6 = 0;
      }
      else
      {
LABEL_43:
        v6 = 0;
        *((_BYTE *)v19 + v24++) = 0;
      }
LABEL_46:
      v28 = (int)v42;
      v29 = 80LL * (unsigned int)v42;
      memset_0((void *)(v29 + v45), 0, 0x50u);
      *(_DWORD *)(v29 + v45) = 80;
      v30 = (_QWORD *)(v23 + *((_QWORD *)a2 + 8));
      if ( v30[3] > 0xFu )
        v30 = (_QWORD *)*v30;
      *(_QWORD *)(v29 + v45 + 8) = v30;
      *(_QWORD *)(v29 + v45 + 16) = v19;
      *(_DWORD *)(v29 + v45 + 24) = v24;
      *(_DWORD *)(v29 + v45 + 64) = 0;
      *(_DWORD *)(v29 + v45 + 28) = *(_DWORD *)(*((_QWORD *)a2 + 8) + v23 + 56);
      *(_DWORD *)(v29 + v45 + 68) = 0;
      v20 = v28 + 1;
      LODWORD(v42) = v20;
      v21 = *((_QWORD *)a2 + 9);
      v22 = *((_QWORD *)a2 + 8);
    }
    while ( v20 < (unsigned int)((v21 - v22) >> 6) );
    v3 = v48;
  }
  ptablecreate.cbStruct = 80;
  v31 = (char *)a2 + 8;
  if ( *((_QWORD *)a2 + 4) > 0xFu )
    v31 = *(char **)v31;
  ptablecreate.szTableName = v31;
  ptablecreate.rgcolumncreate = (JET_COLUMNCREATE_A *)v43;
  ptablecreate.cColumns = -1227133513 * ((__int64)(*((_QWORD *)a2 + 6) - *((_QWORD *)a2 + 5)) >> 3);
  ptablecreate.rgindexcreate = (JET_INDEXCREATE_A *)v45;
  ptablecreate.cIndexes = (v21 - v22) >> 6;
  ptablecreate.tableid = -1;
  ptablecreate.grbit = 0;
  TableColumnInfoA = JetOpenTableA(*((_QWORD *)v3 + 6), *((_DWORD *)v3 + 16), v31, 0, 0, 0x8048u, &ptablecreate.tableid);
  v33 = TableColumnInfoA;
  if ( TableColumnInfoA == -1305 )
  {
    TableColumnInfoA = JetCreateTableColumnIndexA(*((_QWORD *)v3 + 6), *((_DWORD *)v3 + 16), &ptablecreate);
    v33 = TableColumnInfoA;
    if ( TableColumnInfoA < 0 )
      goto LABEL_56;
    TableColumnInfoA = JetCloseTable(*((_QWORD *)v3 + 6), ptablecreate.tableid);
    v33 = TableColumnInfoA;
    if ( TableColumnInfoA < 0 )
      goto LABEL_56;
    ptablecreate.tableid = -1;
    TableColumnInfoA = JetOpenTableA(
                         *((_QWORD *)v3 + 6),
                         *((_DWORD *)v3 + 16),
                         ptablecreate.szTableName,
                         0,
                         0,
                         0x8048u,
                         &ptablecreate.tableid);
    v33 = TableColumnInfoA;
    if ( TableColumnInfoA < 0 )
      goto LABEL_56;
  }
  else if ( TableColumnInfoA < 0 )
  {
    goto LABEL_56;
  }
  tableid = ptablecreate.tableid;
  *((_QWORD *)a2 + 11) = ptablecreate.tableid;
  memset(pvResult, 0, 28);
  v36 = 0;
  v37 = *((_QWORD *)a2 + 5);
  if ( !(-1227133513 * (unsigned int)((*((_QWORD *)a2 + 6) - v37) >> 3)) )
  {
LABEL_69:
    operator delete(v19);
    std::vector<tag_JET_COLUMNCREATE_A>::~vector<tag_JET_COLUMNCREATE_A>((char **)&v43);
    std::vector<RPC_INTERFACE_TEMPLATEW>::~vector<RPC_INTERFACE_TEMPLATEW>((char **)&v45);
    return 0;
  }
  while ( 1 )
  {
    v38 = 56LL * v36;
    v39 = v38 + v37 + 8;
    if ( *(_QWORD *)(v39 + 24) > 0xFu )
      v39 = *(_QWORD *)v39;
    TableColumnInfoA = JetGetTableColumnInfoA(*((_QWORD *)v3 + 6), tableid, (JET_PCSTR)v39, pvResult, 0x1Cu, 0);
    v33 = TableColumnInfoA;
    if ( TableColumnInfoA < 0 )
      break;
    *(_DWORD *)(v38 + *((_QWORD *)a2 + 5) + 48) = pvResult[1];
    ++v36;
    v37 = *((_QWORD *)a2 + 5);
    if ( v36 >= -1227133513 * (unsigned int)((*((_QWORD *)a2 + 6) - v37) >> 3) )
      goto LABEL_69;
    tableid = ptablecreate.tableid;
  }
LABEL_56:
  if ( v33 == -1011 )
  {
    v34 = -2147024882;
  }
  else
  {
    v40 = -TableColumnInfoA;
    if ( v40 < 0 )
      LOWORD(v40) = v33;
    v34 = (unsigned __int16)v40 | 0x8E5E0000;
  }
  operator delete(v19);
  std::vector<tag_JET_COLUMNCREATE_A>::~vector<tag_JET_COLUMNCREATE_A>((char **)&v43);
  std::vector<RPC_INTERFACE_TEMPLATEW>::~vector<RPC_INTERFACE_TEMPLATEW>((char **)&v45);
  return v34;
}

```

## disassembly

```asm
0x180024da4  mov     [rsp-8+arg_10], rbx
0x180024da9  push    rbp
0x180024daa  push    rsi
0x180024dab  push    rdi
0x180024dac  push    r12
0x180024dae  push    r13
0x180024db0  push    r14
0x180024db2  push    r15
0x180024db4  lea     rbp, [rsp-10h]
0x180024db9  sub     rsp, 110h
0x180024dc0  mov     rax, cs:__security_cookie
0x180024dc7  xor     rax, rsp
0x180024dca  mov     [rbp+40h+var_40], rax
0x180024dce  mov     rdi, rdx
0x180024dd1  mov     r13, rcx
0x180024dd4  mov     [rbp+40h+var_C0], rcx
0x180024dd8  xor     edx, edx; Val
0x180024dda  lea     r8d, [rdx+50h]; Size
0x180024dde  lea     rcx, [rbp+40h+ptablecreate]; void *
0x180024de2  call    memset_0
0x180024de7  mov     r14, [rdi+48h]
0x180024deb  sub     r14, [rdi+40h]
0x180024def  sar     r14, 6
0x180024df3  xorps   xmm0, xmm0
0x180024df6  movdqu  [rsp+140h+var_E0], xmm0
0x180024dfc  xor     r12d, r12d
0x180024dff  mov     [rsp+140h+var_D0], r12
0x180024e04  mov     r15d, 1000h
0x180024e0a  test    r14, r14
0x180024e0d  jz      loc_180024EAC
0x180024e13  mov     rax, 333333333333333h
0x180024e1d  cmp     r14, rax
0x180024e20  ja      loc_180025415
0x180024e26  lea     rsi, [r14+r14*4]
0x180024e2a  shl     rsi, 4
0x180024e2e  test    rsi, rsi
0x180024e31  jnz     short loc_180024E38
0x180024e33  mov     ebx, r12d
0x180024e36  jmp     short loc_180024E72
0x180024e38  cmp     rsi, r15
0x180024e3b  jb      short loc_180024E67
0x180024e3d  lea     rcx, [rsi+27h]; Size
0x180024e41  cmp     rcx, rsi
0x180024e44  jbe     loc_18002541B
0x180024e4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024e4f  test    rax, rax
0x180024e52  jnz     short loc_180024E59
0x180024e54  lea     ecx, [rax+5]
0x180024e57  int     29h; Win8: RtlFailFast(ecx)
0x180024e59  lea     rbx, [rax+27h]
0x180024e5d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180024e61  mov     [rbx-8], rax
0x180024e65  jmp     short loc_180024E72
0x180024e67  mov     rcx, rsi; Size
0x180024e6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024e6f  mov     rbx, rax
0x180024e72  mov     qword ptr [rsp+140h+var_E0], rbx
0x180024e77  lea     rcx, [rbx+rsi]
0x180024e7b  mov     [rsp+140h+var_D0], rcx
0x180024e80  mov     r8, rsi; Size
0x180024e83  xor     dl, dl; Val
0x180024e85  mov     rcx, rbx; void *
0x180024e88  call    memset_0
0x180024e8d  add     rbx, 50h ; 'P'
0x180024e91  sub     r14, 1
0x180024e95  jnz     short loc_180024E8D
0x180024e97  mov     qword ptr [rsp+140h+var_E0+8], rbx
0x180024e9c  mov     [rsp+140h+var_100], r12
0x180024ea1  lea     rcx, [rsp+140h+var_100]
0x180024ea6  call    ??1?$_Tidy_guard@V?$vector@UtagJET_INDEXCREATE_A@@V?$allocator@UtagJET_INDEXCREATE_A@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<tagJET_INDEXCREATE_A>>::~_Tidy_guard<std::vector<tagJET_INDEXCREATE_A>>(void)
0x180024eab  nop
0x180024eac  mov     rsi, [rdi+30h]
0x180024eb0  sub     rsi, [rdi+28h]
0x180024eb4  sar     rsi, 3
0x180024eb8  mov     rbx, 6DB6DB6DB6DB6DB7h
0x180024ec2  imul    rsi, rbx
0x180024ec6  xorps   xmm0, xmm0
0x180024ec9  movdqu  [rsp+140h+var_F8], xmm0
0x180024ecf  mov     [rsp+140h+var_E8], r12
0x180024ed4  test    rsi, rsi
0x180024ed7  jz      loc_180024F7B
0x180024edd  mov     rax, 492492492492492h
0x180024ee7  cmp     rsi, rax
0x180024eea  ja      loc_180025421
0x180024ef0  imul    r14, rsi, 38h ; '8'
0x180024ef4  test    r14, r14
0x180024ef7  jnz     short loc_180024EFE
0x180024ef9  mov     rbx, r12
0x180024efc  jmp     short loc_180024F38
0x180024efe  cmp     r14, r15
0x180024f01  jb      short loc_180024F2D
0x180024f03  lea     rcx, [r14+27h]; Size
0x180024f07  cmp     rcx, r14
0x180024f0a  jbe     loc_18002540F
0x180024f10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024f15  test    rax, rax
0x180024f18  jnz     short loc_180024F1F
0x180024f1a  lea     ecx, [rax+5]
0x180024f1d  int     29h; Win8: RtlFailFast(ecx)
0x180024f1f  lea     rbx, [rax+27h]
0x180024f23  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180024f27  mov     [rbx-8], rax
0x180024f2b  jmp     short loc_180024F38
0x180024f2d  mov     rcx, r14; Size
0x180024f30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024f35  mov     rbx, rax
0x180024f38  mov     qword ptr [rsp+140h+var_F8], rbx
0x180024f3d  lea     rcx, [rbx+r14]
0x180024f41  mov     [rsp+140h+var_E8], rcx
0x180024f46  mov     r8, r14; Size
0x180024f49  xor     dl, dl; Val
0x180024f4b  mov     rcx, rbx; void *
0x180024f4e  call    memset_0
0x180024f53  add     rbx, 38h ; '8'
0x180024f57  sub     rsi, 1
0x180024f5b  jnz     short loc_180024F53
0x180024f5d  mov     qword ptr [rsp+140h+var_F8+8], rbx
0x180024f62  mov     [rsp+140h+var_100], r12
0x180024f67  lea     rcx, [rsp+140h+var_100]
0x180024f6c  call    ??1?$_Tidy_guard@V?$vector@Utag_JET_COLUMNCREATE_A@@V?$allocator@Utag_JET_COLUMNCREATE_A@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<tag_JET_COLUMNCREATE_A>>::~_Tidy_guard<std::vector<tag_JET_COLUMNCREATE_A>>(void)
0x180024f71  mov     rbx, 6DB6DB6DB6DB6DB7h
0x180024f7b  mov     r8d, r12d
0x180024f7e  mov     rax, [rdi+30h]
0x180024f82  sub     rax, [rdi+28h]
0x180024f86  sar     rax, 3
0x180024f8a  imul    rax, rbx
0x180024f8e  test    eax, eax
0x180024f90  jz      loc_180025061
0x180024f96  mov     eax, r8d
0x180024f99  imul    rdx, rax, 38h ; '8'
0x180024f9d  mov     rax, qword ptr [rsp+140h+var_F8]
0x180024fa2  xorps   xmm0, xmm0
0x180024fa5  xor     ecx, ecx
0x180024fa7  movups  xmmword ptr [rdx+rax], xmm0
0x180024fab  movups  xmmword ptr [rdx+rax+10h], xmm0
0x180024fb0  movups  xmmword ptr [rdx+rax+20h], xmm0
0x180024fb5  mov     [rdx+rax+30h], rcx
0x180024fba  mov     rax, qword ptr [rsp+140h+var_F8]
0x180024fbf  mov     dword ptr [rdx+rax], 38h ; '8'
0x180024fc6  mov     rcx, [rdi+28h]
0x180024fca  add     rcx, 8
0x180024fce  add     rcx, rdx
0x180024fd1  cmp     qword ptr [rcx+18h], 0Fh
0x180024fd6  jbe     short loc_180024FDB
0x180024fd8  mov     rcx, [rcx]
0x180024fdb  mov     rax, qword ptr [rsp+140h+var_F8]
0x180024fe0  mov     [rdx+rax+8], rcx
0x180024fe5  mov     rax, [rdi+28h]
0x180024fe9  mov     ecx, [rdx+rax+28h]
0x180024fed  mov     rax, qword ptr [rsp+140h+var_F8]
0x180024ff2  mov     [rdx+rax+10h], ecx
0x180024ff6  mov     rax, [rdi+28h]
0x180024ffa  mov     ecx, [rdx+rax+2Ch]
0x180024ffe  mov     rax, qword ptr [rsp+140h+var_F8]
0x180025003  mov     [rdx+rax+18h], ecx
0x180025007  mov     rcx, qword ptr [rsp+140h+var_F8]
0x18002500c  mov     eax, [rdx+rcx+10h]
0x180025010  sub     eax, 0Ah
0x180025013  test    eax, 0FFFFFFFDh
0x180025018  jnz     short loc_180025027
0x18002501a  mov     dword ptr [rdx+rcx+2Ch], 4B0h
0x180025022  mov     rcx, qword ptr [rsp+140h+var_F8]
0x180025027  mov     eax, [rdx+rcx+10h]
0x18002502b  sub     eax, 0Bh
0x18002502e  cmp     eax, 1
0x180025031  ja      short loc_180025040
0x180025033  mov     dword ptr [rdx+rcx+14h], 10000h
0x18002503b  mov     rcx, qword ptr [rsp+140h+var_F8]
0x180025040  mov     [rdx+rcx+34h], r12d
0x180025045  inc     r8d
0x180025048  mov     rax, [rdi+30h]
0x18002504c  sub     rax, [rdi+28h]
0x180025050  sar     rax, 3
0x180025054  imul    rax, rbx
0x180025058  cmp     r8d, eax
0x18002505b  jb      loc_180024F96
0x180025061  mov     ecx, 10000h; unsigned __int64
0x180025066  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002506b  mov     r15, rax
0x18002506e  mov     r14d, r12d
0x180025071  mov     dword ptr [rsp+140h+var_100], r12d
0x180025076  mov     rdx, [rdi+48h]
0x18002507a  mov     r9, [rdi+40h]
0x18002507e  mov     rcx, rdx
0x180025081  sub     rcx, r9
0x180025084  sar     rcx, 6
0x180025088  test    ecx, ecx
0x18002508a  jz      loc_1800251FB
0x180025090  xor     edx, edx; Val
0x180025092  mov     r8d, 10000h; Size
0x180025098  mov     rcx, r15; void *
0x18002509b  call    memset_0
0x1800250a0  mov     r13d, r14d
0x1800250a3  shl     r13, 6
0x1800250a7  mov     ebx, r12d
0x1800250aa  mov     r8, [rdi+40h]
0x1800250ae  mov     [rsp+140h+var_C8], r8
0x1800250b3  mov     rdx, [r8+r13+20h]
0x1800250b8  mov     rax, [r8+r13+28h]
0x1800250bd  sub     rax, rdx
0x1800250c0  sar     rax, 5
0x1800250c4  test    rax, rax
0x1800250c7  jz      short loc_180025130
0x1800250c9  cmp     ebx, 10000h
0x1800250cf  jnb     short loc_180025147
0x1800250d1  mov     esi, r12d
0x1800250d4  shl     rsi, 5
0x1800250d8  lea     r8, [rsi+rdx]
0x1800250dc  cmp     qword ptr [r8+18h], 0Fh
0x1800250e1  jbe     short loc_1800250E6
0x1800250e3  mov     r8, [r8]; char *
0x1800250e6  mov     r14d, ebx
0x1800250e9  add     r14, r15
0x1800250ec  mov     edx, 10000h
0x1800250f1  sub     edx, ebx; unsigned __int64
0x1800250f3  mov     rcx, r14; char *
0x1800250f6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800250fb  test    eax, eax
0x1800250fd  js      short loc_18002513D
0x1800250ff  mov     rcx, [rsp+140h+var_C8]
0x180025104  mov     rdx, [rcx+r13+20h]
0x180025109  mov     eax, [rdx+rsi+10h]
0x18002510d  inc     eax
0x18002510f  add     ebx, eax
0x180025111  inc     r12d
0x180025114  mov     rcx, [rcx+r13+28h]
0x180025119  sub     rcx, rdx
0x18002511c  sar     rcx, 5
0x180025120  mov     eax, r12d
0x180025123  cmp     rax, rcx
0x180025126  jb      short loc_1800250C9
0x180025128  cmp     ebx, 10000h
0x18002512e  jnb     short loc_180025147
0x180025130  mov     eax, ebx
0x180025132  xor     r12d, r12d
0x180025135  mov     [rax+r15], r12b
0x180025139  inc     ebx
0x18002513b  jmp     short loc_18002514A
0x18002513d  xor     r12d, r12d
0x180025140  mov     [r14], r12b
0x180025143  inc     ebx
0x180025145  jmp     short loc_18002514A
0x180025147  xor     r12d, r12d
0x18002514a  mov     r14d, dword ptr [rsp+140h+var_100]
0x18002514f  lea     rsi, [r14+r14*4]
0x180025153  shl     rsi, 4
0x180025157  mov     rcx, qword ptr [rsp+140h+var_E0]
0x18002515c  add     rcx, rsi; void *
0x18002515f  xor     edx, edx; Val
0x180025161  lea     r8d, [rdx+50h]; Size
0x180025165  call    memset_0
0x18002516a  mov     rax, qword ptr [rsp+140h+var_E0]
0x18002516f  mov     dword ptr [rsi+rax], 50h ; 'P'
0x180025176  mov     rcx, [rdi+40h]
0x18002517a  add     rcx, r13
0x18002517d  cmp     qword ptr [rcx+18h], 0Fh
0x180025182  jbe     short loc_180025187
0x180025184  mov     rcx, [rcx]
0x180025187  mov     rax, qword ptr [rsp+140h+var_E0]
0x18002518c  mov     [rsi+rax+8], rcx
0x180025191  mov     rax, qword ptr [rsp+140h+var_E0]
0x180025196  mov     [rsi+rax+10h], r15
0x18002519b  mov     rax, qword ptr [rsp+140h+var_E0]
0x1800251a0  mov     [rsi+rax+18h], ebx
0x1800251a4  mov     rax, qword ptr [rsp+140h+var_E0]
0x1800251a9  mov     [rsi+rax+40h], r12d
0x1800251ae  mov     rax, [rdi+40h]
0x1800251b2  mov     ecx, [rax+r13+38h]
0x1800251b7  mov     rax, qword ptr [rsp+140h+var_E0]
0x1800251bc  mov     [rsi+rax+1Ch], ecx
0x1800251c0  mov     rax, qword ptr [rsp+140h+var_E0]
0x1800251c5  mov     [rsi+rax+44h], r12d
0x1800251ca  inc     r14d
0x1800251cd  mov     dword ptr [rsp+140h+var_100], r14d
0x1800251d2  mov     rdx, [rdi+48h]
0x1800251d6  mov     r9, [rdi+40h]
0x1800251da  mov     rax, rdx
0x1800251dd  sub     rax, r9
0x1800251e0  sar     rax, 6
0x1800251e4  cmp     r14d, eax
0x1800251e7  jb      loc_180025090
0x1800251ed  mov     r13, [rbp+40h+var_C0]
0x1800251f1  mov     rbx, 6DB6DB6DB6DB6DB7h
0x1800251fb  mov     [rbp+40h+ptablecreate.cbStruct], 50h ; 'P'
0x180025202  lea     r8, [rdi+8]
0x180025206  cmp     qword ptr [r8+18h], 0Fh
0x18002520b  jbe     short loc_180025210
0x18002520d  mov     r8, [r8]; szTableName
0x180025210  mov     [rbp+40h+ptablecreate.szTableName], r8
0x180025214  mov     rax, qword ptr [rsp+140h+var_F8]
0x180025219  mov     [rbp+40h+ptablecreate.rgcolumncreate], rax
0x18002521d  mov     rax, [rdi+30h]
0x180025221  sub     rax, [rdi+28h]
0x180025225  sar     rax, 3
0x180025229  imul    rax, rbx
0x18002522d  mov     [rbp+40h+ptablecreate.cColumns], eax
0x180025230  mov     rax, qword ptr [rsp+140h+var_E0]
0x180025235  mov     [rbp+40h+ptablecreate.rgindexcreate], rax
0x180025239  sub     rdx, r9
0x18002523c  sar     rdx, 6
  ... truncated ...
```
