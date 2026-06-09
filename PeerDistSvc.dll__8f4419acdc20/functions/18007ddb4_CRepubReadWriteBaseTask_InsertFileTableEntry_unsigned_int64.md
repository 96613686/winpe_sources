# CRepubReadWriteBaseTask::InsertFileTableEntry(unsigned __int64)

- ea: `0x18007ddb4`
- end: `0x18007e399`
- name: `?InsertFileTableEntry@CRepubReadWriteBaseTask@@IEAAK_K@Z`
- size: `1509`
- prototype: `unsigned int __fastcall(CRepubReadWriteBaseTask *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x18007c658`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x18001fc30`
- `0x1800450b0`
- `0x180069f3c`
- `0x18006bd44`
- `0x18007ddb4`
- `0x180093440`
- `0x1800946b0`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18007df95`
- `ESENT!JetPrepareUpdate` at `0x18007e15c`
- `ESENT!JetPrepareUpdate` at `0x18007e1db`
- `ESENT!JetPrepareUpdate` at `0x18007df95`
- `ESENT!JetPrepareUpdate` at `0x18007e15c`
- `ESENT!JetPrepareUpdate` at `0x18007e1db`
- `ESENT!JetSetColumns` at `0x18007e187`
- `ESENT!JetSetColumns` at `0x18007e187`
- `ESENT!JetRetrieveColumns` at `0x18007df35`
- `ESENT!JetRetrieveColumns` at `0x18007df35`
- `ESENT!JetUpdate` at `0x18007e1b4`
- `ESENT!JetUpdate` at `0x18007e1b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepubReadWriteBaseTask::InsertFileTableEntry(CRepubReadWriteBaseTask *this, __int64 a2)
{
  char v3; // r15
  unsigned int First; // eax
  unsigned int SpaceInCatalogDatabase; // edi
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // edx
  __int64 v10; // rax
  unsigned int Columns; // esi
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  int v14; // ecx
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  unsigned int i; // r14d
  unsigned int v19; // edi
  __int64 v20; // rdx
  _QWORD v22[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v23; // [rsp+90h] [rbp+40h] BYREF
  __int64 v24; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int64 LRUHint; // [rsp+A0h] [rbp+50h] BYREF

  v24 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
  }
  LRUHint = 0;
  v3 = 1;
  v22[0] = &CFileTableLRUOrderIterator::`vftable';
  v22[1] = *((_QWORD *)this + 47);
  v22[2] = *((_QWORD *)this + 77);
  First = CFileTableLRUOrderIterator::FindFirst((CFileTableLRUOrderIterator *)v22);
  SpaceInCatalogDatabase = First;
  if ( First == 1168 )
  {
LABEL_36:
    SpaceInCatalogDatabase = 0;
LABEL_44:
    LRUHint = CRepubCacheBackingStore::GetLRUHint(*((CRepubCacheBackingStore **)this + 1));
    v14 = *(_DWORD *)(*((_QWORD *)this + 75) + 632LL);
    v15 = *((_QWORD *)this + 50);
    *(_DWORD *)(v15 + 4) = 0;
    *(_QWORD *)(v15 + 20) = 0;
    *(_QWORD *)(v15 + 32) = 0;
    *(_DWORD *)v15 = v14;
    *(_DWORD *)(v15 + 16) = 8;
    *(_QWORD *)(v15 + 8) = &v24;
    *(_DWORD *)(v15 + 28) = 1;
    v16 = *(_DWORD *)(*((_QWORD *)this + 75) + 636LL);
    v17 = *((_QWORD *)this + 50);
    *(_DWORD *)(v17 + 44) = 0;
    *(_QWORD *)(v17 + 60) = 0;
    *(_QWORD *)(v17 + 72) = 0;
    *(_DWORD *)(v17 + 40) = v16;
    *(_DWORD *)(v17 + 56) = 8;
    *(_QWORD *)(v17 + 48) = &LRUHint;
    *(_DWORD *)(v17 + 68) = 1;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v24, LRUHint);
    }
    for ( i = 0; i < 4; ++i )
    {
      if ( v3 )
      {
        Columns = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 77), 0);
        if ( Columns )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v13 = 45;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
      }
      Columns = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 77), *((JET_SETCOLUMN **)this + 50), 2u);
      if ( Columns )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v13 = 46;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      Columns = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 77), 0, 0, 0);
      if ( Columns != -1012 )
      {
        if ( !Columns )
          return SpaceInCatalogDatabase;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v13 = 50;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      v19 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 77), 3u);
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 47, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v19);
        }
        v20 = v19;
        return (*(unsigned int (__fastcall **)(CRepubReadWriteBaseTask *, __int64))(*(_QWORD *)this + 48LL))(this, v20);
      }
      SpaceInCatalogDatabase = CRepubCatalogLRUTask::MakeSpaceInCatalogDatabase(this);
      if ( SpaceInCatalogDatabase )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v7 = 48;
          v8 = SpaceInCatalogDatabase;
          goto LABEL_12;
        }
        return SpaceInCatalogDatabase;
      }
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          SpaceInCatalogDatabase + 49,
          WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
      }
    }
  }
  else
  {
    if ( First )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return SpaceInCatalogDatabase;
      }
      v7 = 37;
LABEL_11:
      v8 = First;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v6 + 12), v7, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v8);
      return SpaceInCatalogDatabase;
    }
    v23 = 0;
    First = CRepubCatalogLRUTask::GetBlockDatabaseIndex(this, &v23);
    SpaceInCatalogDatabase = First;
    if ( First )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return SpaceInCatalogDatabase;
      }
      v7 = 38;
      goto LABEL_11;
    }
    v9 = *(_DWORD *)(768LL * v23 + *((_QWORD *)this + 52) + 636);
    v10 = *((_QWORD *)this + 49);
    *(_OWORD *)v10 = 0;
    *(_OWORD *)(v10 + 16) = 0;
    *(_OWORD *)(v10 + 32) = 0;
    *(_DWORD *)v10 = v9;
    *(_DWORD *)(v10 + 16) = 8;
    *(_QWORD *)(v10 + 8) = &LRUHint;
    *(_DWORD *)(v10 + 32) = 1;
    do
    {
      Columns = JetRetrieveColumns(
                  *((_QWORD *)this + 47),
                  *((_QWORD *)this + 77),
                  *((JET_RETRIEVECOLUMN **)this + 49),
                  1u);
      if ( Columns )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v13 = 39;
LABEL_86:
          WPP_SF_d(*((_QWORD *)v12 + 12), v13, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, Columns);
        }
LABEL_87:
        v20 = Columns;
        return (*(unsigned int (__fastcall **)(CRepubReadWriteBaseTask *, __int64))(*(_QWORD *)this + 48LL))(this, v20);
      }
      if ( LRUHint != 1 )
      {
        v3 = 1;
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), Columns + 40, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
      }
      Columns = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 77), 2u);
      if ( Columns != -1102 )
      {
        if ( !Columns )
        {
          v3 = 0;
          goto LABEL_44;
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v13 = 42;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          41,
          WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
          4294966194LL);
      }
      First = CFileTableLRUOrderIterator::FindNext((CFileTableLRUOrderIterator *)v22);
      SpaceInCatalogDatabase = First;
      if ( First == 4053 )
        goto LABEL_36;
    }
    while ( !First );
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v7 = 43;
      goto LABEL_11;
    }
  }
  return SpaceInCatalogDatabase;
}

```

## disassembly

```asm
0x18007ddb4  mov     [rsp-38h+arg_8], rdx
0x18007ddb9  push    rbp
0x18007ddba  push    rbx
0x18007ddbb  push    rsi
0x18007ddbc  push    rdi
0x18007ddbd  push    r12
0x18007ddbf  push    r14
0x18007ddc1  push    r15
0x18007ddc3  mov     rbp, rsp
0x18007ddc6  sub     rsp, 50h
0x18007ddca  mov     r9, rdx
0x18007ddcd  mov     rbx, rcx
0x18007ddd0  lea     rsi, WPP_GLOBAL_Control
0x18007ddd7  mov     r12d, 4
0x18007dddd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dde4  cmp     rcx, rsi
0x18007dde7  jz      short loc_18007DE0A
0x18007dde9  test    [rcx+6Ch], r12b
0x18007dded  jz      short loc_18007DE0A
0x18007ddef  cmp     [rcx+69h], r12b
0x18007ddf3  jb      short loc_18007DE0A
0x18007ddf5  lea     edx, [r12+20h]
0x18007ddfa  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007de01  mov     rcx, [rcx+60h]
0x18007de05  call    WPP_SF_q
0x18007de0a  mov     [rbp+arg_10], 0
0x18007de12  mov     r14d, 1
0x18007de18  mov     r15b, r14b
0x18007de1b  lea     rax, ??_7CFileTableLRUOrderIterator@@6B@; const CFileTableLRUOrderIterator::`vftable'
0x18007de22  mov     [rbp+var_20], rax
0x18007de26  mov     rax, [rbx+178h]
0x18007de2d  mov     [rbp+var_18], rax
0x18007de31  mov     rax, [rbx+268h]
0x18007de38  mov     [rbp+var_10], rax
0x18007de3c  lea     rcx, [rbp+var_20]; this
0x18007de40  call    ?FindFirst@CFileTableLRUOrderIterator@@UEAAKXZ; CFileTableLRUOrderIterator::FindFirst(void)
0x18007de45  mov     edi, eax
0x18007de47  cmp     eax, 490h
0x18007de4c  jz      loc_18007E029
0x18007de52  test    eax, eax
0x18007de54  jz      short loc_18007DE96
0x18007de56  mov     rcx, cs:WPP_GLOBAL_Control
0x18007de5d  cmp     rcx, rsi
0x18007de60  jz      loc_18007E388
0x18007de66  test    [rcx+6Ch], r12b
0x18007de6a  jz      loc_18007E388
0x18007de70  cmp     [rcx+69h], r14b
0x18007de74  jb      loc_18007E388
0x18007de7a  lea     edx, [r14+24h]
0x18007de7e  mov     r9d, eax
0x18007de81  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007de88  mov     rcx, [rcx+60h]
0x18007de8c  call    WPP_SF_d
0x18007de91  jmp     loc_18007E388
0x18007de96  mov     [rbp+arg_0], 0
0x18007de9d  lea     rdx, [rbp+arg_0]; unsigned int *
0x18007dea1  mov     rcx, rbx; this
0x18007dea4  call    ?GetBlockDatabaseIndex@CRepubCatalogLRUTask@@IEAAKPEAK@Z; CRepubCatalogLRUTask::GetBlockDatabaseIndex(ulong *)
0x18007dea9  mov     edi, eax
0x18007deab  test    eax, eax
0x18007dead  jz      short loc_18007DEDA
0x18007deaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007deb6  cmp     rcx, rsi
0x18007deb9  jz      loc_18007E388
0x18007debf  test    [rcx+6Ch], r12b
0x18007dec3  jz      loc_18007E388
0x18007dec9  cmp     [rcx+69h], r14b
0x18007decd  jb      loc_18007E388
0x18007ded3  mov     edx, 26h ; '&'
0x18007ded8  jmp     short loc_18007DE7E
0x18007deda  mov     eax, [rbp+arg_0]
0x18007dedd  lea     rcx, [rax+rax*2]
0x18007dee1  shl     rcx, 8
0x18007dee5  mov     rax, [rbx+1A0h]
0x18007deec  mov     edx, [rcx+rax+27Ch]
0x18007def3  mov     rax, [rbx+188h]
0x18007defa  xorps   xmm0, xmm0
0x18007defd  movups  xmmword ptr [rax], xmm0
0x18007df00  movups  xmmword ptr [rax+10h], xmm0
0x18007df04  movups  xmmword ptr [rax+20h], xmm0
0x18007df08  mov     [rax], edx
0x18007df0a  mov     dword ptr [rax+10h], 8
0x18007df11  lea     rcx, [rbp+arg_10]
0x18007df15  mov     [rax+8], rcx
0x18007df19  mov     [rax+20h], r14d
0x18007df1d  mov     r9d, r14d; cretrievecolumn
0x18007df20  mov     r8, [rbx+188h]; pretrievecolumn
0x18007df27  mov     rdx, [rbx+268h]; tableid
0x18007df2e  mov     rcx, [rbx+178h]; sesid
0x18007df35  call    cs:__imp_JetRetrieveColumns
0x18007df3b  mov     esi, eax
0x18007df3d  test    eax, eax
0x18007df3f  jnz     loc_18007E33E
0x18007df45  cmp     [rbp+arg_10], r14
0x18007df49  jnz     loc_18007E06B
0x18007df4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007df56  lea     rax, WPP_GLOBAL_Control
0x18007df5d  cmp     rcx, rax
0x18007df60  jz      short loc_18007DF81
0x18007df62  test    [rcx+6Ch], r12b
0x18007df66  jz      short loc_18007DF81
0x18007df68  cmp     [rcx+69h], r12b
0x18007df6c  jb      short loc_18007DF81
0x18007df6e  lea     edx, [rsi+28h]
0x18007df71  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007df78  mov     rcx, [rcx+60h]
0x18007df7c  call    WPP_SF_
0x18007df81  mov     r8d, 2; prep
0x18007df87  mov     rdx, [rbx+268h]; tableid
0x18007df8e  mov     rcx, [rbx+178h]; sesid
0x18007df95  call    cs:__imp_JetPrepareUpdate
0x18007df9b  mov     esi, eax
0x18007df9d  mov     eax, 0FFFFFBB2h
0x18007dfa2  cmp     esi, eax
0x18007dfa4  jnz     loc_18007E02D
0x18007dfaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dfb1  lea     rsi, WPP_GLOBAL_Control
0x18007dfb8  cmp     rcx, rsi
0x18007dfbb  jz      short loc_18007DFE1
0x18007dfbd  test    [rcx+6Ch], r12b
0x18007dfc1  jz      short loc_18007DFE1
0x18007dfc3  cmp     [rcx+69h], r12b
0x18007dfc7  jb      short loc_18007DFE1
0x18007dfc9  mov     edx, 29h ; ')'
0x18007dfce  mov     r9d, eax
0x18007dfd1  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007dfd8  mov     rcx, [rcx+60h]
0x18007dfdc  call    WPP_SF_d
0x18007dfe1  lea     rcx, [rbp+var_20]; this
0x18007dfe5  call    ?FindNext@CFileTableLRUOrderIterator@@UEAAKXZ; CFileTableLRUOrderIterator::FindNext(void)
0x18007dfea  mov     edi, eax
0x18007dfec  cmp     eax, 0FD5h
0x18007dff1  jz      short loc_18007E029
0x18007dff3  test    eax, eax
0x18007dff5  jz      loc_18007DF1D
0x18007dffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e002  cmp     rcx, rsi
0x18007e005  jz      loc_18007E388
0x18007e00b  test    [rcx+6Ch], r12b
0x18007e00f  jz      loc_18007E388
0x18007e015  cmp     [rcx+69h], r14b
0x18007e019  jb      loc_18007E388
0x18007e01f  mov     edx, 2Bh ; '+'
0x18007e024  jmp     loc_18007DE7E
0x18007e029  xor     edi, edi
0x18007e02b  jmp     short loc_18007E075
0x18007e02d  test    esi, esi
0x18007e02f  jz      short loc_18007E066
0x18007e031  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e038  lea     rax, WPP_GLOBAL_Control
0x18007e03f  cmp     rcx, rax
0x18007e042  jz      loc_18007E375
0x18007e048  test    [rcx+6Ch], r12b
0x18007e04c  jz      loc_18007E375
0x18007e052  cmp     [rcx+69h], r14b
0x18007e056  jb      loc_18007E375
0x18007e05c  mov     edx, 2Ah ; '*'
0x18007e061  jmp     loc_18007E362
0x18007e066  xor     r15b, r15b
0x18007e069  jmp     short loc_18007E06E
0x18007e06b  mov     r15b, r14b
0x18007e06e  lea     rsi, WPP_GLOBAL_Control
0x18007e075  mov     rcx, [rbx+8]; this
0x18007e079  call    ?GetLRUHint@CRepubCacheBackingStore@@QEAA_KXZ; CRepubCacheBackingStore::GetLRUHint(void)
0x18007e07e  mov     [rbp+arg_10], rax
0x18007e082  mov     rax, [rbx+258h]
0x18007e089  mov     ecx, [rax+278h]
0x18007e08f  mov     rax, [rbx+190h]
0x18007e096  mov     dword ptr [rax+4], 0
0x18007e09d  mov     qword ptr [rax+14h], 0
0x18007e0a5  mov     qword ptr [rax+20h], 0
0x18007e0ad  mov     [rax], ecx
0x18007e0af  mov     edx, 8
0x18007e0b4  mov     [rax+10h], edx
0x18007e0b7  lea     rcx, [rbp+arg_8]
0x18007e0bb  mov     [rax+8], rcx
0x18007e0bf  mov     [rax+1Ch], r14d
0x18007e0c3  mov     rax, [rbx+258h]
0x18007e0ca  mov     ecx, [rax+27Ch]
0x18007e0d0  mov     rax, [rbx+190h]
0x18007e0d7  mov     dword ptr [rax+2Ch], 0
0x18007e0de  mov     qword ptr [rax+3Ch], 0
0x18007e0e6  mov     qword ptr [rax+48h], 0
0x18007e0ee  mov     [rax+28h], ecx
0x18007e0f1  mov     [rax+38h], edx
0x18007e0f4  lea     rcx, [rbp+arg_10]
0x18007e0f8  mov     [rax+30h], rcx
0x18007e0fc  mov     [rax+44h], r14d
0x18007e100  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e107  cmp     rcx, rsi
0x18007e10a  jz      short loc_18007E13A
0x18007e10c  test    [rcx+6Ch], r12b
0x18007e110  jz      short loc_18007E13A
0x18007e112  cmp     [rcx+69h], r12b
0x18007e116  jb      short loc_18007E13A
0x18007e118  mov     edx, 2Ch ; ','
0x18007e11d  mov     rax, [rbp+arg_10]
0x18007e121  mov     [rsp+50h+pcbActual], rax
0x18007e126  mov     r9, [rbp+arg_8]
0x18007e12a  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e131  mov     rcx, [rcx+60h]
0x18007e135  call    WPP_SF_qq
0x18007e13a  xor     r14d, r14d
0x18007e13d  cmp     r14d, r12d
0x18007e140  jnb     loc_18007E388
0x18007e146  test    r15b, r15b
0x18007e149  jz      short loc_18007E16C
0x18007e14b  xor     r8d, r8d; prep
0x18007e14e  mov     rdx, [rbx+268h]; tableid
0x18007e155  mov     rcx, [rbx+178h]; sesid
0x18007e15c  call    cs:__imp_JetPrepareUpdate
0x18007e162  mov     esi, eax
0x18007e164  test    eax, eax
0x18007e166  jnz     loc_18007E23F
0x18007e16c  mov     r9d, 2; csetcolumn
0x18007e172  mov     r8, [rbx+190h]; psetcolumn
0x18007e179  mov     rdx, [rbx+268h]; tableid
0x18007e180  mov     rcx, [rbx+178h]; sesid
0x18007e187  call    cs:__imp_JetSetColumns
0x18007e18d  mov     esi, eax
0x18007e18f  test    eax, eax
0x18007e191  jnz     loc_18007E318
0x18007e197  mov     [rsp+50h+pcbActual], 0; pcbActual
0x18007e1a0  xor     r9d, r9d; cbBookmark
0x18007e1a3  xor     r8d, r8d; pvBookmark
0x18007e1a6  mov     rdx, [rbx+268h]; tableid
0x18007e1ad  mov     rcx, [rbx+178h]; sesid
0x18007e1b4  call    cs:__imp_JetUpdate
0x18007e1ba  mov     esi, eax
0x18007e1bc  cmp     eax, 0FFFFFC0Ch
0x18007e1c1  jnz     loc_18007E2EA
0x18007e1c7  mov     r8d, 3; prep
0x18007e1cd  mov     rdx, [rbx+268h]; tableid
0x18007e1d4  mov     rcx, [rbx+178h]; sesid
0x18007e1db  call    cs:__imp_JetPrepareUpdate
0x18007e1e1  mov     edi, eax
0x18007e1e3  test    eax, eax
0x18007e1e5  jnz     loc_18007E2AC
0x18007e1eb  mov     rcx, rbx; this
0x18007e1ee  call    ?MakeSpaceInCatalogDatabase@CRepubCatalogLRUTask@@IEAAKXZ; CRepubCatalogLRUTask::MakeSpaceInCatalogDatabase(void)
0x18007e1f3  mov     edi, eax
0x18007e1f5  test    eax, eax
0x18007e1f7  jnz     short loc_18007E274
0x18007e1f9  inc     r14d
0x18007e1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e203  lea     rax, WPP_GLOBAL_Control
0x18007e20a  cmp     rcx, rax
0x18007e20d  jz      loc_18007E13D
0x18007e213  test    [rcx+6Ch], r12b
0x18007e217  jz      loc_18007E13D
0x18007e21d  cmp     [rcx+69h], r12b
0x18007e221  jb      loc_18007E13D
0x18007e227  lea     edx, [rdi+31h]
0x18007e22a  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e231  mov     rcx, [rcx+60h]
0x18007e235  call    WPP_SF_
0x18007e23a  jmp     loc_18007E13D
0x18007e23f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e246  lea     rax, WPP_GLOBAL_Control
0x18007e24d  cmp     rcx, rax
0x18007e250  jz      loc_18007E375
0x18007e256  test    [rcx+6Ch], r12b
0x18007e25a  jz      loc_18007E375
0x18007e260  cmp     byte ptr [rcx+69h], 1
0x18007e264  jb      loc_18007E375
0x18007e26a  mov     edx, 2Dh ; '-'
0x18007e26f  jmp     loc_18007E362
0x18007e274  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e27b  lea     rax, WPP_GLOBAL_Control
0x18007e282  cmp     rcx, rax
0x18007e285  jz      loc_18007E388
0x18007e28b  test    [rcx+6Ch], r12b
0x18007e28f  jz      loc_18007E388
0x18007e295  cmp     byte ptr [rcx+69h], 1
0x18007e299  jb      loc_18007E388
0x18007e29f  mov     edx, 30h ; '0'
0x18007e2a4  mov     r9d, edi
0x18007e2a7  jmp     loc_18007DE81
0x18007e2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e2b3  lea     rax, WPP_GLOBAL_Control
0x18007e2ba  cmp     rcx, rax
0x18007e2bd  jz      short loc_18007E2E3
0x18007e2bf  test    [rcx+6Ch], r12b
0x18007e2c3  jz      short loc_18007E2E3
0x18007e2c5  cmp     byte ptr [rcx+69h], 1
0x18007e2c9  jb      short loc_18007E2E3
0x18007e2cb  mov     edx, 2Fh ; '/'
0x18007e2d0  mov     r9d, edi
0x18007e2d3  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e2da  mov     rcx, [rcx+60h]
0x18007e2de  call    WPP_SF_d
0x18007e2e3  mov     edx, edi
0x18007e2e5  jmp     loc_18007E377
0x18007e2ea  test    esi, esi
0x18007e2ec  jz      loc_18007E388
0x18007e2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e2f9  lea     rax, WPP_GLOBAL_Control
0x18007e300  cmp     rcx, rax
0x18007e303  jz      short loc_18007E375
0x18007e305  test    [rcx+6Ch], r12b
  ... truncated ...
```
