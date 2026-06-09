# TieringPinnedSession::ClearPinnedRecordGivenFileId(TE_FILE_ID_128 const *)

- ea: `0x14001effc`
- end: `0x14001f73e`
- name: `?ClearPinnedRecordGivenFileId@TieringPinnedSession@@QEAAJPEBUTE_FILE_ID_128@@@Z`
- size: `1858`
- prototype: `__int64 __fastcall(TieringPinnedSession *this, const struct TE_FILE_ID_128 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c444`
- `0x140010d1c`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x14001effc`
- `0x140020e1c`
- `0x140021018`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14001f064`
- `ntdll!RtlCompareMemory` at `0x14001f360`
- `ntdll!RtlCompareMemory` at `0x14001f064`
- `ntdll!RtlCompareMemory` at `0x14001f360`
- `ESENT!JetRollback` at `0x14001f655`
- `ESENT!JetRollback` at `0x14001f655`
- `ESENT!JetBeginTransaction` at `0x14001f23b`
- `ESENT!JetBeginTransaction` at `0x14001f23b`
- `ESENT!JetCommitTransaction` at `0x14001f572`
- `ESENT!JetCommitTransaction` at `0x14001f572`
- `ESENT!JetDelete` at `0x14001f378`
- `ESENT!JetDelete` at `0x14001f378`
- `ESENT!JetMove` at `0x14001f397`
- `ESENT!JetMove` at `0x14001f397`
- `ESENT!JetMakeKey` at `0x14001f0e6`
- `ESENT!JetMakeKey` at `0x14001f0e6`
- `ESENT!JetSeek` at `0x14001f187`
- `ESENT!JetSeek` at `0x14001f187`
- `ESENT!JetRetrieveColumn` at `0x14001f331`
- `ESENT!JetRetrieveColumn` at `0x14001f331`

## pseudocode

```c
__int64 __fastcall TieringPinnedSession::ClearPinnedRecordGivenFileId(
        TieringPinnedSession *this,
        const struct TE_FILE_ID_128 *a2)
{
  unsigned int v4; // edi
  unsigned int v5; // ebx
  JET_TABLEID v6; // rdx
  JET_SESID v7; // rcx
  JET_ERR Key; // eax
  JET_ERR v9; // r8d
  int v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  JET_ERR v13; // eax
  int v14; // eax
  JET_ERR v15; // eax
  int v16; // eax
  JET_TABLEID v18; // rdx
  JET_SESID v19; // rcx
  JET_ERR v20; // eax
  JET_ERR v21; // r8d
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  int v24; // eax
  _QWORD *v25; // rcx
  int v26; // edx
  int v27; // eax
  int v28; // eax
  JET_SESID v29; // rcx
  JET_ERR v30; // eax
  JET_ERR v31; // r8d
  int v32; // eax
  _QWORD *v33; // rcx
  int v34; // [rsp+40h] [rbp-40h]
  _BYTE v35[8]; // [rsp+48h] [rbp-38h] BYREF
  int v36; // [rsp+50h] [rbp-30h]
  JET_COLUMNID columnid; // [rsp+58h] [rbp-28h]
  __int128 pvData; // [rsp+60h] [rbp-20h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringPinnedSession::ClearPinnedRecordGivenFileId";
  CHResultImp::CHResultImp((CHResultImp *)v35);
  v4 = 0;
  v36 = 0;
  if ( RtlCompareMemory(a2, &NullGuid, 0x10u) == 16 )
  {
    v5 = -2138898428;
    v36 = -2138898428;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids, 2156068868LL);
    }
    goto LABEL_51;
  }
  v6 = *((_QWORD *)this + 3);
  v7 = *((_QWORD *)this + 1);
  columnid = *(_DWORD *)(*((_QWORD *)this + 5) + 120LL);
  Key = JetMakeKey(v7, v6, a2, 0x10u, 1u);
  v9 = Key;
  if ( Key )
  {
    if ( Key == -529 || Key == -1092 || Key == -1808 )
    {
      v5 = ATL::AtlHresultFromWin32(112);
    }
    else if ( Key == -1011 )
    {
      v5 = -2147024882;
    }
    else
    {
      v10 = -Key;
      if ( v10 < 0 )
        LOWORD(v10) = v9;
      v5 = v9 & 0x8E5E0000 | (unsigned __int16)v10 | 0xE5E0000;
    }
    v36 = v5;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v12 = 28;
    goto LABEL_50;
  }
  v13 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 8u);
  v9 = v13;
  if ( ((v13 + 1603) & 0xFFFFFFFD) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v13);
    }
    CHResultImp::~CHResultImp((CHResultImp *)v35);
    return 0;
  }
  if ( v13 && v13 != 1039 )
  {
    if ( v13 == -529 || v13 == -1092 || v13 == -1808 )
    {
      v5 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v13 == -1011 )
    {
      v5 = -2147024882;
    }
    else
    {
      v14 = -v13;
      if ( v14 < 0 )
        LOWORD(v14) = v9;
      v5 = v9 & 0x8E5E0000 | (unsigned __int16)v14 | 0xE5E0000;
    }
    v36 = v5;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v12 = 30;
    goto LABEL_50;
  }
  v15 = JetBeginTransaction(*((_QWORD *)this + 1));
  v9 = v15;
  if ( v15 )
  {
    if ( v15 == -529 || v15 == -1092 || v15 == -1808 )
    {
      v5 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v15 == -1011 )
    {
      v5 = -2147024882;
    }
    else
    {
      v16 = -v15;
      if ( v16 < 0 )
        LOWORD(v16) = v9;
      v5 = v9 & 0x8E5E0000 | (unsigned __int16)v16 | 0xE5E0000;
    }
    v36 = v5;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v12 = 31;
LABEL_50:
    WPP_SF_iiSd(
      v11[2],
      v12,
      (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v9);
LABEL_51:
    CHResultImp::~CHResultImp((CHResultImp *)v35);
    return v5;
  }
  v34 = 0;
  do
  {
    v18 = *((_QWORD *)this + 3);
    v19 = *((_QWORD *)this + 1);
    pvData = 0;
    v20 = JetRetrieveColumn(v19, v18, columnid, &pvData, 0x10u, 0, 2u, 0);
    v21 = v20;
    if ( v20 == -1017 )
      goto LABEL_58;
    if ( v20 )
    {
      if ( v20 == -529 || v20 == -1092 || v20 == -1808 )
      {
        v4 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v20 == -1011 )
      {
        v4 = -2147024882;
      }
      else
      {
        v27 = -v20;
        if ( v27 < 0 )
          LOWORD(v27) = v21;
        v4 = v21 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
      }
      v36 = v4;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v26 = 32;
LABEL_100:
      WPP_SF_iiSd(
        v25[2],
        v26,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v21);
      goto LABEL_101;
    }
    if ( RtlCompareMemory(&pvData, a2, 0x10u) != 16 )
      goto LABEL_101;
    v22 = JetDelete(*((_QWORD *)this + 1), *((_QWORD *)this + 3));
    v21 = v22;
    if ( v22 )
    {
      if ( v22 == -529 || v22 == -1092 || v22 == -1808 )
      {
        v4 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v22 == -1011 )
      {
        v4 = -2147024882;
      }
      else
      {
        v24 = -v22;
        if ( v24 < 0 )
          LOWORD(v24) = v21;
        v4 = v21 & 0x8E5E0000 | (unsigned __int16)v24 | 0xE5E0000;
      }
      v36 = v4;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v26 = 33;
      goto LABEL_100;
    }
    ++v34;
LABEL_58:
    v23 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
    v21 = v23;
    if ( v23 == -1603 )
      goto LABEL_101;
  }
  while ( !v23 || v23 == -1017 );
  if ( v23 == -529 || v23 == -1092 || v23 == -1808 )
  {
    v4 = ATL::AtlHresultFromWin32(112);
  }
  else if ( v23 == -1011 )
  {
    v4 = -2147024882;
  }
  else
  {
    v28 = -v23;
    if ( v28 < 0 )
      LOWORD(v28) = v21;
    v4 = v21 & 0x8E5E0000 | (unsigned __int16)v28 | 0xE5E0000;
  }
  v36 = v4;
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = 34;
    goto LABEL_100;
  }
LABEL_101:
  v29 = *((_QWORD *)this + 1);
  if ( v34 )
  {
    v30 = JetCommitTransaction(v29, 1u);
    v31 = v30;
    if ( v30 )
    {
      if ( v30 == -529 || v30 == -1092 || v30 == -1808 )
      {
        v4 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v30 == -1011 )
      {
        v4 = -2147024882;
      }
      else
      {
        v32 = -v30;
        if ( v32 < 0 )
          LOWORD(v32) = v31;
        v4 = v31 & 0x8E5E0000 | (unsigned __int16)v32 | 0xE5E0000;
      }
      v36 = v4;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v31);
          v33 = WPP_GLOBAL_Control;
        }
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 5u )
          WPP_SF_S(
            v33[2],
            36,
            &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
      }
      v29 = *((_QWORD *)this + 1);
      goto LABEL_121;
    }
  }
  else
  {
LABEL_121:
    JetRollback(v29, 0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_iiDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      v34,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  }
  CHResultImp::~CHResultImp((CHResultImp *)v35);
  return v4;
}

```

## disassembly

```asm
0x14001effc  mov     [rsp-28h+arg_10], rbx
0x14001f001  mov     [rsp-28h+arg_18], rsi
0x14001f006  push    rbp
0x14001f007  push    rdi
0x14001f008  push    r12
0x14001f00a  push    r14
0x14001f00c  push    r15
0x14001f00e  mov     rbp, rsp
0x14001f011  sub     rsp, 80h
0x14001f018  mov     rax, cs:__security_cookie
0x14001f01f  xor     rax, rsp
0x14001f022  mov     [rbp+var_10], rax
0x14001f026  mov     rax, gs:58h
0x14001f02f  mov     r14, rcx
0x14001f032  mov     r12, rdx
0x14001f035  mov     ecx, 8
0x14001f03a  mov     rdx, [rax]
0x14001f03d  lea     rax, aTieringpinneds_1; "TieringPinnedSession::ClearPinnedRecord"...
0x14001f044  mov     [rcx+rdx], rax
0x14001f048  lea     rcx, [rbp+var_38]; this
0x14001f04c  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001f051  xor     edi, edi
0x14001f053  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14001f05a  mov     rcx, r12; Source1
0x14001f05d  mov     [rbp+var_30], edi
0x14001f060  lea     r8d, [rdi+10h]; Length
0x14001f064  call    cs:__imp_RtlCompareMemory
0x14001f06a  cmp     rax, 10h
0x14001f06e  jnz     short loc_14001F0C2
0x14001f070  mov     ebx, 80830004h
0x14001f075  mov     [rbp+var_30], ebx
0x14001f078  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f07f  lea     rsi, WPP_GLOBAL_Control
0x14001f086  cmp     rcx, rsi
0x14001f089  jz      loc_14001F2ED
0x14001f08f  lea     r15d, [rdi+1]
0x14001f093  test    [rcx+1Ch], r15b
0x14001f097  jz      loc_14001F2ED
0x14001f09d  cmp     byte ptr [rcx+19h], 2
0x14001f0a1  jb      loc_14001F2ED
0x14001f0a7  mov     rcx, [rcx+10h]
0x14001f0ab  lea     edx, [rdi+1Bh]
0x14001f0ae  mov     r9d, ebx
0x14001f0b1  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001f0b8  call    WPP_SF_d
0x14001f0bd  jmp     loc_14001F2ED
0x14001f0c2  mov     rax, [r14+28h]
0x14001f0c6  mov     r15d, 1
0x14001f0cc  mov     rdx, [r14+18h]; tableid
0x14001f0d0  mov     r8, r12; pvData
0x14001f0d3  mov     rcx, [r14+8]; sesid
0x14001f0d7  mov     [rsp+80h+grbit], r15d; grbit
0x14001f0dc  mov     eax, [rax+78h]
0x14001f0df  lea     r9d, [r15+0Fh]; cbData
0x14001f0e3  mov     [rbp+columnid], eax
0x14001f0e6  call    cs:__imp_JetMakeKey
0x14001f0ec  mov     r8d, eax
0x14001f0ef  test    eax, eax
0x14001f0f1  jz      loc_14001F179
0x14001f0f7  cmp     eax, 0FFFFFDEFh
0x14001f0fc  jz      short loc_14001F135
0x14001f0fe  cmp     eax, 0FFFFFBBCh
0x14001f103  jz      short loc_14001F135
0x14001f105  cmp     eax, 0FFFFF8F0h
0x14001f10a  jz      short loc_14001F135
0x14001f10c  cmp     eax, 0FFFFFC0Dh
0x14001f111  jnz     short loc_14001F11A
0x14001f113  mov     ebx, 8007000Eh
0x14001f118  jmp     short loc_14001F141
0x14001f11a  neg     eax
0x14001f11c  cmovs   eax, r8d
0x14001f120  movzx   ebx, ax
0x14001f123  mov     eax, r8d
0x14001f126  and     eax, 8E5E0000h
0x14001f12b  or      ebx, eax
0x14001f12d  or      ebx, 0E5E0000h
0x14001f133  jmp     short loc_14001F141
0x14001f135  mov     ecx, 70h ; 'p'; unsigned int
0x14001f13a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001f13f  mov     ebx, eax
0x14001f141  mov     [rbp+var_30], ebx
0x14001f144  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f14b  lea     rsi, WPP_GLOBAL_Control
0x14001f152  cmp     rcx, rsi
0x14001f155  jz      loc_14001F2ED
0x14001f15b  test    [rcx+1Ch], r15b
0x14001f15f  jz      loc_14001F2ED
0x14001f165  cmp     byte ptr [rcx+19h], 2
0x14001f169  jb      loc_14001F2ED
0x14001f16f  mov     edx, 1Ch
0x14001f174  jmp     loc_14001F2BD
0x14001f179  mov     rdx, [r14+18h]; tableid
0x14001f17d  mov     r8d, 8; grbit
0x14001f183  mov     rcx, [r14+8]; sesid
0x14001f187  call    cs:__imp_JetSeek
0x14001f18d  mov     r8d, eax
0x14001f190  lea     ecx, [rax+643h]
0x14001f196  test    ecx, 0FFFFFFFDh
0x14001f19c  jz      loc_14001F6B7
0x14001f1a2  test    eax, eax
0x14001f1a4  jz      loc_14001F237
0x14001f1aa  cmp     eax, 40Fh
0x14001f1af  jz      loc_14001F237
0x14001f1b5  cmp     eax, 0FFFFFDEFh
0x14001f1ba  jz      short loc_14001F1F3
0x14001f1bc  cmp     eax, 0FFFFFBBCh
0x14001f1c1  jz      short loc_14001F1F3
0x14001f1c3  cmp     eax, 0FFFFF8F0h
0x14001f1c8  jz      short loc_14001F1F3
0x14001f1ca  cmp     eax, 0FFFFFC0Dh
0x14001f1cf  jnz     short loc_14001F1D8
0x14001f1d1  mov     ebx, 8007000Eh
0x14001f1d6  jmp     short loc_14001F1FF
0x14001f1d8  neg     eax
0x14001f1da  cmovs   eax, r8d
0x14001f1de  movzx   ebx, ax
0x14001f1e1  mov     eax, r8d
0x14001f1e4  and     eax, 8E5E0000h
0x14001f1e9  or      ebx, eax
0x14001f1eb  or      ebx, 0E5E0000h
0x14001f1f1  jmp     short loc_14001F1FF
0x14001f1f3  mov     ecx, 70h ; 'p'; unsigned int
0x14001f1f8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001f1fd  mov     ebx, eax
0x14001f1ff  mov     [rbp+var_30], ebx
0x14001f202  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f209  lea     rsi, WPP_GLOBAL_Control
0x14001f210  cmp     rcx, rsi
0x14001f213  jz      loc_14001F2ED
0x14001f219  test    [rcx+1Ch], r15b
0x14001f21d  jz      loc_14001F2ED
0x14001f223  cmp     byte ptr [rcx+19h], 2
0x14001f227  jb      loc_14001F2ED
0x14001f22d  mov     edx, 1Eh
0x14001f232  jmp     loc_14001F2BD
0x14001f237  mov     rcx, [r14+8]; sesid
0x14001f23b  call    cs:__imp_JetBeginTransaction
0x14001f241  mov     r8d, eax
0x14001f244  test    eax, eax
0x14001f246  jz      loc_14001F2FD
0x14001f24c  cmp     eax, 0FFFFFDEFh
0x14001f251  jz      short loc_14001F28A
0x14001f253  cmp     eax, 0FFFFFBBCh
0x14001f258  jz      short loc_14001F28A
0x14001f25a  cmp     eax, 0FFFFF8F0h
0x14001f25f  jz      short loc_14001F28A
0x14001f261  cmp     eax, 0FFFFFC0Dh
0x14001f266  jnz     short loc_14001F26F
0x14001f268  mov     ebx, 8007000Eh
0x14001f26d  jmp     short loc_14001F296
0x14001f26f  neg     eax
0x14001f271  cmovs   eax, r8d
0x14001f275  movzx   ebx, ax
0x14001f278  mov     eax, r8d
0x14001f27b  and     eax, 8E5E0000h
0x14001f280  or      ebx, eax
0x14001f282  or      ebx, 0E5E0000h
0x14001f288  jmp     short loc_14001F296
0x14001f28a  mov     ecx, 70h ; 'p'; unsigned int
0x14001f28f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001f294  mov     ebx, eax
0x14001f296  mov     [rbp+var_30], ebx
0x14001f299  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f2a0  lea     rsi, WPP_GLOBAL_Control
0x14001f2a7  cmp     rcx, rsi
0x14001f2aa  jz      short loc_14001F2ED
0x14001f2ac  test    [rcx+1Ch], r15b
0x14001f2b0  jz      short loc_14001F2ED
0x14001f2b2  cmp     byte ptr [rcx+19h], 2
0x14001f2b6  jb      short loc_14001F2ED
0x14001f2b8  mov     edx, 1Fh
0x14001f2bd  mov     rax, [r14+28h]
0x14001f2c1  mov     r9, [r12+8]
0x14001f2c6  mov     rcx, [rcx+10h]
0x14001f2ca  mov     [rsp+80h+var_50], r8d
0x14001f2cf  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001f2d6  mov     rax, [rax+70h]
0x14001f2da  mov     [rsp+80h+pcbActual], rax
0x14001f2df  mov     rax, [r12]
0x14001f2e3  mov     qword ptr [rsp+80h+grbit], rax
0x14001f2e8  call    WPP_SF_iiSd
0x14001f2ed  lea     rcx, [rbp+var_38]; this
0x14001f2f1  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001f2f6  mov     eax, ebx
0x14001f2f8  jmp     loc_14001F716
0x14001f2fd  mov     [rbp+var_40], edi
0x14001f300  mov     r8d, [rbp+columnid]; columnid
0x14001f304  lea     r9, [rbp+pvData]; pvData
0x14001f308  mov     rdx, [r14+18h]; tableid
0x14001f30c  xorps   xmm0, xmm0
0x14001f30f  mov     rcx, [r14+8]; sesid
0x14001f313  mov     [rsp+80h+pretinfo], rdi; pretinfo
0x14001f318  mov     [rsp+80h+var_50], 2; grbit
0x14001f320  mov     [rsp+80h+pcbActual], rdi; pcbActual
0x14001f325  mov     [rsp+80h+grbit], 10h; cbData
0x14001f32d  movups  [rbp+pvData], xmm0
0x14001f331  call    cs:__imp_JetRetrieveColumn
0x14001f337  lea     rsi, WPP_GLOBAL_Control
0x14001f33e  mov     ebx, 8007000Eh
0x14001f343  mov     r8d, eax
0x14001f346  cmp     eax, 0FFFFFC07h
0x14001f34b  jz      short loc_14001F389
0x14001f34d  test    eax, eax
0x14001f34f  jnz     loc_14001F471
0x14001f355  lea     r8d, [rax+10h]; Length
0x14001f359  mov     rdx, r12; Source2
0x14001f35c  lea     rcx, [rbp+pvData]; Source1
0x14001f360  call    cs:__imp_RtlCompareMemory
0x14001f366  cmp     rax, 10h
0x14001f36a  jnz     loc_14001F561
0x14001f370  mov     rdx, [r14+18h]; tableid
0x14001f374  mov     rcx, [r14+8]; sesid
0x14001f378  call    cs:__imp_JetDelete
0x14001f37e  mov     r8d, eax
0x14001f381  test    eax, eax
0x14001f383  jnz     short loc_14001F3F1
0x14001f385  add     [rbp+var_40], r15d
0x14001f389  mov     rdx, [r14+18h]; tableid
0x14001f38d  xor     r9d, r9d; grbit
0x14001f390  mov     rcx, [r14+8]; sesid
0x14001f394  mov     r8d, r15d; cRow
0x14001f397  call    cs:__imp_JetMove
0x14001f39d  mov     r8d, eax
0x14001f3a0  cmp     eax, 0FFFFF9BDh
0x14001f3a5  jz      loc_14001F561
0x14001f3ab  test    eax, eax
0x14001f3ad  jz      loc_14001F300
0x14001f3b3  cmp     eax, 0FFFFFC07h
0x14001f3b8  jz      loc_14001F300
0x14001f3be  cmp     eax, 0FFFFFDEFh
0x14001f3c3  jz      loc_14001F505
0x14001f3c9  cmp     eax, 0FFFFFBBCh
0x14001f3ce  jz      loc_14001F505
0x14001f3d4  cmp     eax, 0FFFFF8F0h
0x14001f3d9  jz      loc_14001F505
0x14001f3df  cmp     eax, 0FFFFFC0Dh
0x14001f3e4  jnz     loc_14001F4EA
0x14001f3ea  mov     edi, ebx
0x14001f3ec  jmp     loc_14001F511
0x14001f3f1  cmp     r8d, 0FFFFFDEFh
0x14001f3f8  jz      short loc_14001F434
0x14001f3fa  cmp     r8d, 0FFFFFBBCh
0x14001f401  jz      short loc_14001F434
0x14001f403  cmp     r8d, 0FFFFF8F0h
0x14001f40a  jz      short loc_14001F434
0x14001f40c  cmp     r8d, 0FFFFFC0Dh
0x14001f413  jnz     short loc_14001F419
0x14001f415  mov     edi, ebx
0x14001f417  jmp     short loc_14001F440
0x14001f419  neg     eax
0x14001f41b  cmovs   eax, r8d
0x14001f41f  movzx   edi, ax
0x14001f422  mov     eax, r8d
0x14001f425  and     eax, 8E5E0000h
0x14001f42a  or      edi, eax
0x14001f42c  or      edi, 0E5E0000h
0x14001f432  jmp     short loc_14001F440
0x14001f434  mov     ecx, 70h ; 'p'; unsigned int
0x14001f439  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001f43e  mov     edi, eax
0x14001f440  mov     [rbp+var_30], edi
0x14001f443  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f44a  cmp     rcx, rsi
0x14001f44d  jz      loc_14001F561
0x14001f453  test    [rcx+1Ch], r15b
0x14001f457  jz      loc_14001F561
0x14001f45d  cmp     byte ptr [rcx+19h], 2
0x14001f461  jb      loc_14001F561
0x14001f467  mov     edx, 21h ; '!'
0x14001f46c  jmp     loc_14001F531
0x14001f471  cmp     r8d, 0FFFFFDEFh
0x14001f478  jz      short loc_14001F4B4
0x14001f47a  cmp     r8d, 0FFFFFBBCh
0x14001f481  jz      short loc_14001F4B4
0x14001f483  cmp     r8d, 0FFFFF8F0h
0x14001f48a  jz      short loc_14001F4B4
0x14001f48c  cmp     r8d, 0FFFFFC0Dh
0x14001f493  jnz     short loc_14001F499
0x14001f495  mov     edi, ebx
0x14001f497  jmp     short loc_14001F4C0
0x14001f499  neg     eax
0x14001f49b  cmovs   eax, r8d
0x14001f49f  movzx   edi, ax
0x14001f4a2  mov     eax, r8d
0x14001f4a5  and     eax, 8E5E0000h
0x14001f4aa  or      edi, eax
0x14001f4ac  or      edi, 0E5E0000h
0x14001f4b2  jmp     short loc_14001F4C0
0x14001f4b4  mov     ecx, 70h ; 'p'; unsigned int
0x14001f4b9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001f4be  mov     edi, eax
0x14001f4c0  mov     [rbp+var_30], edi
0x14001f4c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f4ca  cmp     rcx, rsi
0x14001f4cd  jz      loc_14001F561
0x14001f4d3  test    [rcx+1Ch], r15b
0x14001f4d7  jz      loc_14001F561
0x14001f4dd  cmp     byte ptr [rcx+19h], 2
0x14001f4e1  jb      short loc_14001F561
0x14001f4e3  mov     edx, 20h ; ' '
  ... truncated ...
```
