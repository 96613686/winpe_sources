# TieringJetSession::OpenJetTableInternal(bool *,bool,ulong,unsigned __int64,unsigned __int64 *)

- ea: `0x14001c094`
- end: `0x14001ca92`
- name: `?OpenJetTableInternal@TieringJetSession@@AEAAJPEA_N_NK_KPEA_K@Z`
- size: `2558`
- prototype: `__int64 __fastcall(TieringJetSession *this, bool *, unsigned __int8, JET_DBID, JET_SESID sesid, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14001b328`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x140009c08`
- `0x14001c094`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001c3d1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001c7e8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001c3d1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001c7e8`
- `ESENT!JetCreateTableColumnIndex2W` at `0x14001c651`
- `ESENT!JetCreateTableColumnIndex2W` at `0x14001c651`
- `ESENT!JetOpenTableW` at `0x14001c37a`
- `ESENT!JetOpenTableW` at `0x14001c791`
- `ESENT!JetOpenTableW` at `0x14001c37a`
- `ESENT!JetOpenTableW` at `0x14001c791`
- `ESENT!JetDeleteTableW` at `0x14001c26f`
- `ESENT!JetDeleteTableW` at `0x14001c26f`
- `ESENT!JetCloseTable` at `0x14001c1ae`
- `ESENT!JetCloseTable` at `0x14001c71d`
- `ESENT!JetCloseTable` at `0x14001c1ae`
- `ESENT!JetCloseTable` at `0x14001c71d`
- `ESENT!JetGetColumnInfoW` at `0x14001c9e8`
- `ESENT!JetGetColumnInfoW` at `0x14001c9e8`

## string_xrefs

- `0x14001c0e9`: `TieringJetSession::OpenJetTableInternal`

## pseudocode

```c
__int64 __fastcall TieringJetSession::OpenJetTableInternal(
        TieringJetSession *this,
        bool *a2,
        unsigned __int8 a3,
        JET_DBID a4,
        JET_SESID sesid,
        unsigned __int64 *a6)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v10; // rdx
  int v11; // esi
  unsigned int v12; // ebx
  __int64 v13; // rax
  JET_ERR v14; // eax
  JET_ERR v15; // r8d
  int v16; // ecx
  int v17; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // r8d
  int v20; // eax
  _QWORD *v21; // rcx
  int v22; // edx
  JET_TABLEID *ptableid; // rbx
  int v24; // r14d
  JET_GRBIT grbit; // r15d
  JET_ERR v26; // esi
  int v27; // ecx
  _OWORD *v28; // rcx
  const struct tag_JET_COLUMNCREATE_W near *const *v29; // rax
  __int64 v30; // rdx
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  const struct tag_JET_COLUMNCREATE_W near *v38; // rax
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  JET_ERR v43; // eax
  int v44; // eax
  JET_ERR v45; // eax
  JET_TABLEID *v46; // rbx
  int v47; // eax
  _QWORD *v48; // rcx
  int v49; // edx
  int v50; // ecx
  int v51; // ebx
  int v52; // eax
  unsigned __int16 * near **v54; // r14
  int v55; // esi
  __int64 v56; // r8
  __int64 v57; // r15
  JET_ERR ColumnInfoW; // eax
  __int64 v59; // rax
  _BYTE v60[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v61; // [rsp+48h] [rbp-B8h]
  JET_TABLEID *v62; // [rsp+50h] [rbp-B0h]
  JET_TABLECREATE2_W ptablecreate; // [rsp+60h] [rbp-A0h] BYREF
  bool *v64; // [rsp+C0h] [rbp-40h]
  __int128 v65; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v66; // [rsp+E0h] [rbp-20h]
  __int128 v67; // [rsp+F0h] [rbp-10h]
  __int128 v68; // [rsp+100h] [rbp+0h]
  __int128 v69; // [rsp+110h] [rbp+10h]
  _DWORD pvResult[8]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v71[10]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v72; // [rsp+1E0h] [rbp+E0h]

  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v64 = a2;
  v10 = *ThreadLocalStoragePointer;
  v11 = a3;
  v62 = a6;
  *(_QWORD *)(v10 + 8) = "TieringJetSession::OpenJetTableInternal";
  CHResultImp::CHResultImp((CHResultImp *)v60);
  memset_0(&ptablecreate, 0, sizeof(ptablecreate));
  ptablecreate.rgcolumncreate = (JET_COLUMNCREATE_W *)v71;
  v12 = -2147024882;
  ptablecreate.rgindexcreate = (JET_INDEXCREATE_W *)&v65;
  v13 = *((_QWORD *)this + 5);
  if ( *(_BYTE *)(v13 + 148) && *(int *)(v13 + 152) < 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *(_QWORD *)(v13 + 112));
    }
    *(_BYTE *)(*((_QWORD *)this + 5) + 148LL) = 0;
    ++*(_DWORD *)(*((_QWORD *)this + 5) + 152LL);
    if ( *a2 )
    {
      v14 = JetCloseTable(sesid, *a6);
      v15 = v14;
      if ( v14 )
      {
        if ( v14 == -529 || v14 == -1092 || v14 == -1808 )
        {
          v16 = ATL::AtlHresultFromWin32(112);
        }
        else if ( v14 == -1011 )
        {
          v16 = -2147024882;
        }
        else
        {
          v17 = -v14;
          if ( v17 < 0 )
            LOWORD(v17) = v15;
          v16 = v15 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
        }
        v61 = v16;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v15);
        }
      }
      *a2 = 0;
    }
    v18 = JetDeleteTableW(sesid, a4, *(JET_PCWSTR *)(*((_QWORD *)this + 5) + 88LL));
    v19 = v18;
    if ( v18 )
    {
      if ( v18 == -529 || v18 == -1092 || v18 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v18 != -1011 )
      {
        v20 = -v18;
        if ( v20 < 0 )
          LOWORD(v20) = v19;
        v12 = v19 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
      }
      v61 = v12;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      v22 = 107;
      goto LABEL_36;
    }
  }
  else
  {
    *(_BYTE *)(v13 + 148) = 0;
  }
  ptableid = v62;
  v24 = 0;
  grbit = v11 << 15;
  do
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    }
    v26 = JetOpenTableW(sesid, a4, *(JET_PCWSTR *)(*((_QWORD *)this + 5) + 88LL), 0, 0, grbit, ptableid);
    if ( ((v26 + 1304) & 0xFFFFFFFD) != 0 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    }
    Sleep(0x7D0u);
    ++v24;
  }
  while ( v24 < 5 );
  v12 = -2147024882;
  if ( v26 == -1305 )
  {
    v27 = *(_DWORD *)(*((_QWORD *)this + 5) + 96LL);
    if ( v27 == 1 )
    {
      v28 = v71;
      v29 = &g_HeatColumns;
      ptablecreate = g_HeatTableSchema;
      v30 = 3;
      do
      {
        v31 = *((_OWORD *)v29 + 1);
        *v28 = *(_OWORD *)v29;
        v32 = *((_OWORD *)v29 + 2);
        v28[1] = v31;
        v33 = *((_OWORD *)v29 + 3);
        v28[2] = v32;
        v34 = *((_OWORD *)v29 + 4);
        v28[3] = v33;
        v35 = *((_OWORD *)v29 + 5);
        v28[4] = v34;
        v36 = *((_OWORD *)v29 + 6);
        v28[5] = v35;
        v37 = *((_OWORD *)v29 + 7);
        v29 += 16;
        v28[6] = v36;
        v28[7] = v37;
        v28 += 8;
        --v30;
      }
      while ( v30 );
      v38 = *v29;
      v65 = *(_OWORD *)&g_HeatIndexes;
      v67 = xmmword_140042730;
      v39 = xmmword_140042750;
      v66 = *(_OWORD *)&off_140042720;
      v40 = xmmword_140042740;
      *(_QWORD *)v28 = v38;
    }
    else
    {
      if ( v27 == 2 )
      {
        *(_OWORD *)&ptablecreate.cbStruct = *(_OWORD *)&g_PinnedTableSchema.cbStruct;
        *(_OWORD *)&ptablecreate.szTemplateTableName = xmmword_1400426C0;
        *(_OWORD *)&ptablecreate.rgcolumncreate = *(_OWORD *)&off_1400426D0;
        v41 = xmmword_1400426F0;
        *(_OWORD *)&ptablecreate.rgindexcreate = *(_OWORD *)&off_1400426E0;
        v42 = xmmword_140042700;
      }
      else
      {
        if ( v27 != 3 )
          goto LABEL_60;
        *(_OWORD *)&ptablecreate.cbStruct = *(_OWORD *)&g_PinnedCacheTableSchema.cbStruct;
        *(_OWORD *)&ptablecreate.szTemplateTableName = xmmword_140042560;
        *(_OWORD *)&ptablecreate.rgcolumncreate = *(_OWORD *)&off_140042570;
        v41 = xmmword_140042590;
        *(_OWORD *)&ptablecreate.rgindexcreate = *(_OWORD *)&off_140042580;
        v42 = xmmword_1400425A0;
      }
      *(_OWORD *)&ptablecreate.szCallback = v41;
      v71[0] = *(_OWORD *)&g_PinnedColumns;
      v72 = 0;
      *(_OWORD *)&ptablecreate.tableid = v42;
      v71[2] = xmmword_140042620;
      v71[1] = xmmword_140042610;
      v71[4] = *(_OWORD *)&off_140042640;
      v71[3] = xmmword_140042630;
      v71[6] = xmmword_140042660;
      v71[5] = *(_OWORD *)byte_140042650;
      v71[8] = xmmword_140042680;
      v71[7] = *(_OWORD *)byte_140042670;
      v65 = *(_OWORD *)&g_PinnedIndexes;
      v71[9] = *(_OWORD *)&off_140042690;
      v67 = xmmword_1400425D0;
      v39 = xmmword_1400425F0;
      v66 = *(_OWORD *)&off_1400425C0;
      v40 = xmmword_1400425E0;
    }
    v68 = v40;
    v69 = v39;
LABEL_60:
    ptablecreate.rgcolumncreate = (JET_COLUMNCREATE_W *)v71;
    ptablecreate.rgindexcreate = (JET_INDEXCREATE_W *)&v65;
    v43 = JetCreateTableColumnIndex2W(sesid, a4, &ptablecreate);
    v19 = v43;
    if ( v43 )
    {
      if ( v43 == -529 || v43 == -1092 || v43 == -1808 )
      {
        v12 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v43 != -1011 )
      {
        v44 = -v43;
        if ( v44 < 0 )
          LOWORD(v44) = v19;
        v12 = v19 & 0x8E5E0000 | (unsigned __int16)v44 | 0xE5E0000;
      }
      v61 = v12;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      v22 = 110;
LABEL_36:
      WPP_SF_Sd(
        v21[2],
        v22,
        (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v19);
LABEL_123:
      CHResultImp::~CHResultImp((CHResultImp *)v60);
      return v12;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    }
    v45 = JetCloseTable(sesid, ptablecreate.tableid);
    if ( v45 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          115,
          (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v45);
      }
      *v62 = ptablecreate.tableid;
    }
    else
    {
      v46 = v62;
      do
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            112,
            &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        v26 = JetOpenTableW(sesid, a4, *(JET_PCWSTR *)(*((_QWORD *)this + 5) + 88LL), 0, 0, grbit, v46);
        if ( ((v26 + 1304) & 0xFFFFFFFD) != 0 )
          break;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            113,
            &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        Sleep(0x7D0u);
        ++v24;
      }
      while ( v24 < 5 );
      v12 = -2147024882;
      if ( v26 )
      {
        if ( v26 == -529 || v26 == -1092 || v26 == -1808 )
        {
          v12 = ATL::AtlHresultFromWin32(112);
        }
        else if ( v26 != -1011 )
        {
          v47 = -v26;
          if ( v26 > 0 )
            LOWORD(v47) = v26;
          v12 = v26 & 0x8E5E0000 | (unsigned __int16)v47 | 0xE5E0000;
        }
        v61 = v12;
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_123;
        }
        v49 = 114;
        goto LABEL_122;
      }
    }
    goto LABEL_107;
  }
  if ( v26 )
  {
    if ( v26 == -529 || v26 == -1092 || v26 == -1808 )
    {
      v12 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v26 != -1011 )
    {
      v52 = -v26;
      if ( v26 > 0 )
        LOWORD(v52) = v26;
      v12 = v26 & 0x8E5E0000 | (unsigned __int16)v52 | 0xE5E0000;
    }
    v61 = v12;
    v48 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_123;
    }
    v49 = 116;
LABEL_122:
    WPP_SF_Sd(
      v48[2],
      v49,
      (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v26);
    goto LABEL_123;
  }
LABEL_107:
  *v64 = 1;
  v50 = *(_DWORD *)(*((_QWORD *)this + 5) + 96LL);
  if ( (unsigned int)(v50 - 2) > 1 )
  {
    v51 = 7;
LABEL_126:
    v54 = &g_HeatTableColumnArrayNames;
    goto LABEL_128;
  }
  v51 = 3;
  if ( v50 != 2 && v50 != 3 )
    goto LABEL_126;
  v54 = &g_PinnedTableColumnArrayNames;
LABEL_128:
  v55 = 0;
  while ( 1 )
  {
    v56 = *((_QWORD *)this + 5);
    v57 = v55;
    memset(pvResult, 0, 28);
    ColumnInfoW = JetGetColumnInfoW(sesid, a4, *(JET_PCWSTR *)(v56 + 88), (JET_PCWSTR)v54[v55], pvResult, 0x1Cu, 0);
    if ( ColumnInfoW )
      break;
    ++v55;
    *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v57 + 120) = pvResult[1];
    if ( v55 >= v51 )
      goto LABEL_138;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117,
      (unsigned int)&WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      ColumnInfoW);
  }
  v59 = *((_QWORD *)this + 5);
  if ( !*(_DWORD *)(v59 + 152) )
    *(_BYTE *)(v59 + 148) = 1;
LABEL_138:
  CHResultImp::~CHResultImp((CHResultImp *)v60);
  return v61;
}

```

## disassembly

```asm
0x14001c094  mov     [rsp-8+arg_10], rbx
0x14001c099  push    rbp
0x14001c09a  push    rsi
0x14001c09b  push    rdi
0x14001c09c  push    r12
0x14001c09e  push    r13
0x14001c0a0  push    r14
0x14001c0a2  push    r15
0x14001c0a4  lea     rbp, [rsp-1E0h]
0x14001c0ac  sub     rsp, 2E0h
0x14001c0b3  mov     rax, cs:__security_cookie
0x14001c0ba  xor     rax, rsp
0x14001c0bd  mov     [rbp+210h+var_40], rax
0x14001c0c4  mov     rax, gs:58h
0x14001c0cd  mov     rdi, rcx
0x14001c0d0  mov     r14, [rbp+210h+arg_28]
0x14001c0d7  mov     r15, rdx
0x14001c0da  mov     [rbp+210h+var_250], rdx
0x14001c0de  mov     r13d, r9d
0x14001c0e1  mov     ecx, 8
0x14001c0e6  mov     rdx, [rax]
0x14001c0e9  lea     rax, aTieringjetsess_0; "TieringJetSession::OpenJetTableInternal"
0x14001c0f0  movzx   esi, r8b
0x14001c0f4  mov     [rsp+310h+var_2C0], r14
0x14001c0f9  mov     [rcx+rdx], rax
0x14001c0fd  lea     rcx, [rsp+310h+var_2D0]; this
0x14001c102  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001c107  xor     edx, edx; Val
0x14001c109  lea     rcx, [rsp+310h+ptablecreate]; void *
0x14001c10e  lea     r8d, [rdx+60h]; Size
0x14001c112  call    memset_0
0x14001c117  mov     r12, [rbp+210h+sesid]
0x14001c11e  lea     rax, [rbp+210h+var_1D0]
0x14001c122  mov     [rbp+210h+ptablecreate.rgcolumncreate], rax
0x14001c126  lea     rdx, WPP_GLOBAL_Control
0x14001c12d  lea     rax, [rbp+210h+var_240]
0x14001c131  mov     ebx, 8007000Eh
0x14001c136  mov     [rbp+210h+ptablecreate.rgindexcreate], rax
0x14001c13a  mov     rax, [rdi+28h]
0x14001c13e  cmp     byte ptr [rax+94h], 0
0x14001c145  jz      loc_14001C2FA
0x14001c14b  cmp     dword ptr [rax+98h], 1
0x14001c152  jge     loc_14001C2FA
0x14001c158  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c15f  cmp     rcx, rdx
0x14001c162  jz      short loc_14001C189
0x14001c164  test    byte ptr [rcx+1Ch], 1
0x14001c168  jz      short loc_14001C189
0x14001c16a  cmp     byte ptr [rcx+19h], 4
0x14001c16e  jb      short loc_14001C189
0x14001c170  mov     r9, [rax+70h]
0x14001c174  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001c17b  mov     rcx, [rcx+10h]
0x14001c17f  mov     edx, 69h ; 'i'
0x14001c184  call    WPP_SF_S
0x14001c189  mov     rax, [rdi+28h]
0x14001c18d  mov     byte ptr [rax+94h], 0
0x14001c194  mov     rax, [rdi+28h]
0x14001c198  inc     dword ptr [rax+98h]
0x14001c19e  cmp     byte ptr [r15], 0
0x14001c1a2  jz      loc_14001C25A
0x14001c1a8  mov     rdx, [r14]; tableid
0x14001c1ab  mov     rcx, r12; sesid
0x14001c1ae  call    cs:__imp_JetCloseTable
0x14001c1b4  mov     r8d, eax
0x14001c1b7  test    eax, eax
0x14001c1b9  jz      loc_14001C24D
0x14001c1bf  cmp     eax, 0FFFFFDEFh
0x14001c1c4  jz      short loc_14001C1FA
0x14001c1c6  cmp     eax, 0FFFFFBBCh
0x14001c1cb  jz      short loc_14001C1FA
0x14001c1cd  cmp     eax, 0FFFFF8F0h
0x14001c1d2  jz      short loc_14001C1FA
0x14001c1d4  cmp     eax, 0FFFFFC0Dh
0x14001c1d9  jnz     short loc_14001C1DF
0x14001c1db  mov     ecx, ebx
0x14001c1dd  jmp     short loc_14001C206
0x14001c1df  neg     eax
0x14001c1e1  cmovs   eax, r8d
0x14001c1e5  movzx   ecx, ax
0x14001c1e8  mov     eax, r8d
0x14001c1eb  and     eax, 8E5E0000h
0x14001c1f0  or      ecx, eax
0x14001c1f2  or      ecx, 0E5E0000h
0x14001c1f8  jmp     short loc_14001C206
0x14001c1fa  mov     ecx, 70h ; 'p'; unsigned int
0x14001c1ff  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001c204  mov     ecx, eax
0x14001c206  mov     [rsp+310h+var_2C8], ecx
0x14001c20a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c211  lea     r14, WPP_GLOBAL_Control
0x14001c218  cmp     rcx, r14
0x14001c21b  jz      short loc_14001C254
0x14001c21d  test    byte ptr [rcx+1Ch], 1
0x14001c221  jz      short loc_14001C254
0x14001c223  cmp     byte ptr [rcx+19h], 2
0x14001c227  jb      short loc_14001C254
0x14001c229  mov     r9, [rdi+28h]
0x14001c22d  mov     edx, 6Ah ; 'j'
0x14001c232  mov     rcx, [rcx+10h]
0x14001c236  mov     [rsp+310h+cbParameters], r8d
0x14001c23b  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001c242  mov     r9, [r9+70h]
0x14001c246  call    WPP_SF_Sd
0x14001c24b  jmp     short loc_14001C254
0x14001c24d  lea     r14, WPP_GLOBAL_Control
0x14001c254  mov     byte ptr [r15], 0
0x14001c258  jmp     short loc_14001C261
0x14001c25a  lea     r14, WPP_GLOBAL_Control
0x14001c261  mov     r8, [rdi+28h]
0x14001c265  mov     edx, r13d; dbid
0x14001c268  mov     rcx, r12; sesid
0x14001c26b  mov     r8, [r8+58h]; szTableName
0x14001c26f  call    cs:__imp_JetDeleteTableW
0x14001c275  mov     r8d, eax
0x14001c278  test    eax, eax
0x14001c27a  jz      loc_14001C303
0x14001c280  cmp     eax, 0FFFFFDEFh
0x14001c285  jz      short loc_14001C2B7
0x14001c287  cmp     eax, 0FFFFFBBCh
0x14001c28c  jz      short loc_14001C2B7
0x14001c28e  cmp     eax, 0FFFFF8F0h
0x14001c293  jz      short loc_14001C2B7
0x14001c295  cmp     eax, 0FFFFFC0Dh
0x14001c29a  jz      short loc_14001C2C3
0x14001c29c  neg     eax
0x14001c29e  cmovs   eax, r8d
0x14001c2a2  movzx   ebx, ax
0x14001c2a5  mov     eax, r8d
0x14001c2a8  and     eax, 8E5E0000h
0x14001c2ad  or      ebx, eax
0x14001c2af  or      ebx, 0E5E0000h
0x14001c2b5  jmp     short loc_14001C2C3
0x14001c2b7  mov     ecx, 70h ; 'p'; unsigned int
0x14001c2bc  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001c2c1  mov     ebx, eax
0x14001c2c3  mov     [rsp+310h+var_2C8], ebx
0x14001c2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2ce  cmp     rcx, r14
0x14001c2d1  jz      loc_14001C980
0x14001c2d7  test    byte ptr [rcx+1Ch], 1
0x14001c2db  jz      loc_14001C980
0x14001c2e1  cmp     byte ptr [rcx+19h], 2
0x14001c2e5  jb      loc_14001C980
0x14001c2eb  mov     edx, 6Bh ; 'k'
0x14001c2f0  mov     [rsp+310h+cbParameters], r8d
0x14001c2f5  jmp     loc_14001C968
0x14001c2fa  mov     byte ptr [rax+94h], 0
0x14001c301  jmp     short loc_14001C30A
0x14001c303  lea     rdx, WPP_GLOBAL_Control
0x14001c30a  mov     rbx, [rsp+310h+var_2C0]
0x14001c30f  xor     r14d, r14d
0x14001c312  mov     r15d, esi
0x14001c315  shl     r15d, 0Fh
0x14001c319  jmp     short loc_14001C322
0x14001c31b  lea     rdx, WPP_GLOBAL_Control
0x14001c322  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c329  cmp     rcx, rdx
0x14001c32c  jz      short loc_14001C357
0x14001c32e  test    byte ptr [rcx+1Ch], 1
0x14001c332  jz      short loc_14001C357
0x14001c334  cmp     byte ptr [rcx+19h], 5
0x14001c338  jb      short loc_14001C357
0x14001c33a  mov     r9, [rdi+28h]
0x14001c33e  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001c345  mov     rcx, [rcx+10h]
0x14001c349  mov     edx, 6Ch ; 'l'
0x14001c34e  mov     r9, [r9+70h]
0x14001c352  call    WPP_SF_S
0x14001c357  mov     r8, [rdi+28h]
0x14001c35b  xor     r9d, r9d; pvParameters
0x14001c35e  mov     [rsp+310h+ptableid], rbx; ptableid
0x14001c363  mov     edx, r13d; dbid
0x14001c366  mov     [rsp+310h+grbit], r15d; grbit
0x14001c36b  mov     rcx, r12; sesid
0x14001c36e  mov     [rsp+310h+cbParameters], 0; cbParameters
0x14001c376  mov     r8, [r8+58h]; szTableName
0x14001c37a  call    cs:__imp_JetOpenTableW
0x14001c380  mov     esi, eax
0x14001c382  lea     ecx, [rax+518h]
0x14001c388  test    ecx, 0FFFFFFFDh
0x14001c38e  jnz     short loc_14001C3E4
0x14001c390  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c397  lea     rax, WPP_GLOBAL_Control
0x14001c39e  cmp     rcx, rax
0x14001c3a1  jz      short loc_14001C3CC
0x14001c3a3  test    byte ptr [rcx+1Ch], 1
0x14001c3a7  jz      short loc_14001C3CC
0x14001c3a9  cmp     byte ptr [rcx+19h], 4
0x14001c3ad  jb      short loc_14001C3CC
0x14001c3af  mov     r9, [rdi+28h]
0x14001c3b3  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x14001c3ba  mov     rcx, [rcx+10h]
0x14001c3be  mov     edx, 6Dh ; 'm'
0x14001c3c3  mov     r9, [r9+70h]
0x14001c3c7  call    WPP_SF_S
0x14001c3cc  mov     ecx, 7D0h; dwMilliseconds
0x14001c3d1  call    cs:__imp_Sleep
0x14001c3d7  inc     r14d
0x14001c3da  cmp     r14d, 5
0x14001c3de  jl      loc_14001C31B
0x14001c3e4  mov     ebx, 8007000Eh
0x14001c3e9  cmp     esi, 0FFFFFAE7h
0x14001c3ef  jnz     loc_14001C8F1
0x14001c3f5  mov     rax, [rdi+28h]
0x14001c3f9  mov     ecx, [rax+60h]
0x14001c3fc  cmp     ecx, 1
0x14001c3ff  jnz     loc_14001C4E1
0x14001c405  movaps  xmm0, xmmword ptr cs:?g_HeatTableSchema@@3UtagJET_TABLECREATE2_W@@B; tagJET_TABLECREATE2_W const g_HeatTableSchema
0x14001c40c  lea     rcx, [rbp+210h+var_1D0]
0x14001c410  movaps  xmm1, xmmword ptr cs:?g_HeatTableSchema@@3UtagJET_TABLECREATE2_W@@B+10h; tagJET_TABLECREATE2_W const g_HeatTableSchema
0x14001c417  lea     rax, ?g_HeatColumns@@3QBUtag_JET_COLUMNCREATE_W@@B; tag_JET_COLUMNCREATE_W const near * const g_HeatColumns
0x14001c41e  movaps  xmmword ptr [rsp+310h+ptablecreate.cbStruct], xmm0
0x14001c423  mov     edx, 3
0x14001c428  movaps  xmm0, xmmword ptr cs:?g_HeatTableSchema@@3UtagJET_TABLECREATE2_W@@B+20h; tagJET_TABLECREATE2_W const g_HeatTableSchema
0x14001c42f  movaps  xmmword ptr [rsp+310h+ptablecreate.szTemplateTableName], xmm1
0x14001c434  movaps  xmm1, xmmword ptr cs:?g_HeatTableSchema@@3UtagJET_TABLECREATE2_W@@B+30h; tagJET_TABLECREATE2_W const g_HeatTableSchema
0x14001c43b  movaps  xmmword ptr [rbp+210h+ptablecreate.rgcolumncreate], xmm0
0x14001c43f  lea     r8d, [rdx+7Dh]
0x14001c443  movaps  xmm0, xmmword ptr cs:?g_HeatTableSchema@@3UtagJET_TABLECREATE2_W@@B+40h; tagJET_TABLECREATE2_W const g_HeatTableSchema
0x14001c44a  movaps  xmmword ptr [rbp+210h+ptablecreate.rgindexcreate], xmm1
0x14001c44e  movaps  xmm1, xmmword ptr cs:?g_HeatTableSchema@@3UtagJET_TABLECREATE2_W@@B+50h; tagJET_TABLECREATE2_W const g_HeatTableSchema
0x14001c455  movaps  xmmword ptr [rbp+210h+ptablecreate.szCallback], xmm0
0x14001c459  movaps  xmmword ptr [rbp+210h+ptablecreate.tableid], xmm1
0x14001c45d  movups  xmm0, xmmword ptr [rax]
0x14001c460  movups  xmm1, xmmword ptr [rax+10h]
0x14001c464  movups  xmmword ptr [rcx], xmm0
0x14001c467  movups  xmm0, xmmword ptr [rax+20h]
0x14001c46b  movups  xmmword ptr [rcx+10h], xmm1
0x14001c46f  movups  xmm1, xmmword ptr [rax+30h]
0x14001c473  movups  xmmword ptr [rcx+20h], xmm0
0x14001c477  movups  xmm0, xmmword ptr [rax+40h]
0x14001c47b  movups  xmmword ptr [rcx+30h], xmm1
0x14001c47f  movups  xmm1, xmmword ptr [rax+50h]
0x14001c483  movups  xmmword ptr [rcx+40h], xmm0
0x14001c487  movups  xmm0, xmmword ptr [rax+60h]
0x14001c48b  movups  xmmword ptr [rcx+50h], xmm1
0x14001c48f  movups  xmm1, xmmword ptr [rax+70h]
0x14001c493  add     rax, r8
0x14001c496  movups  xmmword ptr [rcx+60h], xmm0
0x14001c49a  movups  xmmword ptr [rcx+70h], xmm1
0x14001c49e  add     rcx, r8
0x14001c4a1  sub     rdx, 1
0x14001c4a5  jnz     short loc_14001C45D
0x14001c4a7  movaps  xmm0, xmmword ptr cs:?g_HeatIndexes@@3QBUtagJET_INDEXCREATE_W@@B; tagJET_INDEXCREATE_W const near * const g_HeatIndexes
0x14001c4ae  movaps  xmm1, xmmword ptr cs:off_140042720; "+FileId"
0x14001c4b5  mov     rax, [rax]
0x14001c4b8  movaps  [rbp+210h+var_240], xmm0
0x14001c4bc  movaps  xmm0, cs:xmmword_140042730
0x14001c4c3  movaps  [rbp+210h+var_220], xmm0
0x14001c4c7  movaps  xmm0, cs:xmmword_140042750
0x14001c4ce  movaps  [rbp+210h+var_230], xmm1
0x14001c4d2  movaps  xmm1, cs:xmmword_140042740
0x14001c4d9  mov     [rcx], rax
0x14001c4dc  jmp     loc_14001C62E
0x14001c4e1  cmp     ecx, 2
0x14001c4e4  jnz     short loc_14001C524
0x14001c4e6  movaps  xmm0, xmmword ptr cs:?g_PinnedTableSchema@@3UtagJET_TABLECREATE2_W@@B; tagJET_TABLECREATE2_W const g_PinnedTableSchema
0x14001c4ed  movaps  xmm1, cs:xmmword_1400426C0
0x14001c4f4  movaps  xmmword ptr [rsp+310h+ptablecreate.cbStruct], xmm0
0x14001c4f9  movaps  xmm0, xmmword ptr cs:off_1400426D0
0x14001c500  movaps  xmmword ptr [rsp+310h+ptablecreate.szTemplateTableName], xmm1
0x14001c505  movaps  xmm1, xmmword ptr cs:off_1400426E0
0x14001c50c  movaps  xmmword ptr [rbp+210h+ptablecreate.rgcolumncreate], xmm0
0x14001c510  movaps  xmm0, cs:xmmword_1400426F0
0x14001c517  movaps  xmmword ptr [rbp+210h+ptablecreate.rgindexcreate], xmm1
0x14001c51b  movaps  xmm1, cs:xmmword_140042700
0x14001c522  jmp     short loc_14001C569
0x14001c524  cmp     ecx, 3
0x14001c527  jnz     loc_14001C636
0x14001c52d  movaps  xmm0, xmmword ptr cs:?g_PinnedCacheTableSchema@@3UtagJET_TABLECREATE2_W@@B; tagJET_TABLECREATE2_W const g_PinnedCacheTableSchema
0x14001c534  movaps  xmm1, cs:xmmword_140042560
0x14001c53b  movaps  xmmword ptr [rsp+310h+ptablecreate.cbStruct], xmm0
0x14001c540  movaps  xmm0, xmmword ptr cs:off_140042570
0x14001c547  movaps  xmmword ptr [rsp+310h+ptablecreate.szTemplateTableName], xmm1
0x14001c54c  movaps  xmm1, xmmword ptr cs:off_140042580
0x14001c553  movaps  xmmword ptr [rbp+210h+ptablecreate.rgcolumncreate], xmm0
0x14001c557  movaps  xmm0, cs:xmmword_140042590
0x14001c55e  movaps  xmmword ptr [rbp+210h+ptablecreate.rgindexcreate], xmm1
0x14001c562  movaps  xmm1, cs:xmmword_1400425A0
0x14001c569  mov     rax, cs:qword_1400426A0
0x14001c570  movaps  xmmword ptr [rbp+210h+ptablecreate.szCallback], xmm0
0x14001c574  movaps  xmm0, xmmword ptr cs:?g_PinnedColumns@@3QBUtag_JET_COLUMNCREATE_W@@B; tag_JET_COLUMNCREATE_W const near * const g_PinnedColumns
0x14001c57b  movups  [rbp+210h+var_1D0], xmm0
0x14001c57f  mov     [rbp+210h+var_130], rax
0x14001c586  movaps  xmm0, cs:xmmword_140042620
0x14001c58d  movaps  xmmword ptr [rbp+210h+ptablecreate.tableid], xmm1
0x14001c591  movaps  xmm1, cs:xmmword_140042610
0x14001c598  movups  [rbp+210h+var_1B0], xmm0
0x14001c59c  movaps  xmm0, xmmword ptr cs:off_140042640; "Placement"
0x14001c5a3  movups  [rbp+210h+var_1C0], xmm1
0x14001c5a7  movaps  xmm1, cs:xmmword_140042630
0x14001c5ae  movups  [rbp+210h+var_190], xmm0
0x14001c5b5  movaps  xmm0, cs:xmmword_140042660
0x14001c5bc  movups  [rbp+210h+var_1A0], xmm1
0x14001c5c0  movaps  xmm1, xmmword ptr cs:byte_140042650
0x14001c5c7  movups  [rbp+210h+var_170], xmm0
0x14001c5ce  movaps  xmm0, cs:xmmword_140042680
0x14001c5d5  movups  [rbp+210h+var_180], xmm1
0x14001c5dc  movaps  xmm1, xmmword ptr cs:byte_140042670
  ... truncated ...
```
