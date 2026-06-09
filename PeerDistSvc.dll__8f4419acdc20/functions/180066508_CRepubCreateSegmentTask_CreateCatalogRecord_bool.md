# CRepubCreateSegmentTask::CreateCatalogRecord(bool)

- ea: `0x180066508`
- end: `0x180066eb4`
- name: `?CreateCatalogRecord@CRepubCreateSegmentTask@@IEAAK_N@Z`
- size: `2476`
- prototype: `unsigned int __fastcall(CRepubCreateSegmentTask *__hidden this, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18006b590`

## callees

- `0x1800024a4`
- `0x1800024f0`
- `0x1800024fc`
- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x18000873c`
- `0x18000ceac`
- `0x18000e58c`
- `0x180011798`
- `0x18002a878`
- `0x18004d600`
- `0x180066508`
- `0x18006b0b8`
- `0x180092600`
- `0x1800941e0`
- `0x18013902c`
- `0x180144882`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180066640`
- `ESENT!JetPrepareUpdate` at `0x180066781`
- `ESENT!JetPrepareUpdate` at `0x180066d9e`
- `ESENT!JetPrepareUpdate` at `0x180066640`
- `ESENT!JetPrepareUpdate` at `0x180066781`
- `ESENT!JetPrepareUpdate` at `0x180066d9e`
- `ESENT!JetSetColumns` at `0x180066ccf`
- `ESENT!JetSetColumns` at `0x180066ccf`
- `ESENT!JetRetrieveColumns` at `0x180066840`
- `ESENT!JetRetrieveColumns` at `0x180066840`
- `ESENT!JetUpdate` at `0x180066d27`
- `ESENT!JetUpdate` at `0x180066d27`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRepubCreateSegmentTask::CreateCatalogRecord(CRepubCreateSegmentTask *this, unsigned __int8 a2)
{
  int v2; // r12d
  unsigned int v4; // esi
  unsigned __int8 *v5; // rbx
  char v6; // r13
  char v7; // r15
  unsigned int First; // eax
  CHostedCacheMsgEncoding *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  JET_COLUMNID v14; // ecx
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r14
  int *v18; // r15
  int v19; // r9d
  int v20; // r8d
  const struct TnoHash *v21; // r14
  TnoHash *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  TnoHash *v25; // r14
  unsigned __int16 v26; // ax
  void *v27; // rax
  CHostedCacheMsgEncoding *v28; // rcx
  int v30; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int csetcolumn[2]; // [rsp+A8h] [rbp-78h] BYREF
  const struct TnoHash *v32; // [rsp+B0h] [rbp-70h] BYREF
  void *v33; // [rsp+B8h] [rbp-68h] BYREF
  unsigned __int64 v34; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-58h]
  unsigned __int64 CurrentTimeAsULONGLONG; // [rsp+D0h] [rbp-50h] BYREF
  struct peerdist_content_tag_tag *v37; // [rsp+D8h] [rbp-48h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+E0h] [rbp-40h] BYREF
  _QWORD v39[2]; // [rsp+110h] [rbp-10h] BYREF
  __int16 v40; // [rsp+120h] [rbp+0h]
  __int64 v41; // [rsp+128h] [rbp+8h]
  __int64 v42; // [rsp+130h] [rbp+10h]
  unsigned int Size; // [rsp+188h] [rbp+68h]
  unsigned int v44; // [rsp+190h] [rbp+70h] BYREF
  unsigned int v45; // [rsp+198h] [rbp+78h] BYREF

  v2 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 86, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
  }
  v4 = 0;
  memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
  v5 = 0;
  v33 = 0;
  v32 = 0;
  if ( !(_BYTE)v2 )
  {
    v6 = 0;
    v7 = 0;
    v39[0] = &CCatalogTableFileSegmentsIterator::`vftable';
    v41 = *((_QWORD *)this + 47);
    v42 = *((_QWORD *)this + 62);
    v40 = 0;
    v39[1] = 0x7FFFFFFFFFFFFFFFLL;
    First = CCatalogTableFileSegmentsIterator::FindFirst((CCatalogTableFileSegmentsIterator *)v39);
LABEL_7:
    v4 = First;
LABEL_8:
    v9 = WPP_GLOBAL_Control;
    while ( !v7 )
    {
      if ( v4 == 1168 )
      {
        if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)v9 + 108) & 4) != 0
          && *((_BYTE *)v9 + 105) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)v9 + 12), 87, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, 1168);
          v9 = WPP_GLOBAL_Control;
        }
        v4 = 0;
        v7 = 1;
      }
      else
      {
        if ( v4 )
        {
          if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v9 + 108) & 4) != 0
            && *((_BYTE *)v9 + 105) )
          {
            WPP_SF_d(*((_QWORD *)v9 + 12), 88, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v4);
            goto LABEL_36;
          }
          goto LABEL_122;
        }
        v10 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 2u);
        if ( v10 == -1102 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 89, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v10);
          }
          First = CCatalogTableFileSegmentsIterator::FindNext((CCatalogTableFileSegmentsIterator *)v39);
          goto LABEL_7;
        }
        if ( v10 )
        {
          v4 = (*(__int64 (__fastcall **)(CRepubCreateSegmentTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v10);
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 90, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
LABEL_36:
            v9 = WPP_GLOBAL_Control;
            goto LABEL_122;
          }
          goto LABEL_122;
        }
        v7 = 1;
        v6 = 1;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 91, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
          goto LABEL_8;
        }
      }
    }
    if ( v6 )
      goto LABEL_47;
  }
  v11 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 2 * v2);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_45;
    }
    v13 = 92;
LABEL_44:
    WPP_SF_d(*((_QWORD *)v12 + 12), v13, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v11);
LABEL_45:
    v4 = (*(__int64 (__fastcall **)(CRepubCreateSegmentTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v11);
LABEL_46:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_122;
  }
LABEL_47:
  v14 = *(_DWORD *)(*((_QWORD *)this + 51) + 812LL);
  *(&pretrievecolumn.columnid + 1) = 0;
  memset(&pretrievecolumn.cbData, 0, 32);
  pretrievecolumn.columnid = v14;
  pretrievecolumn.cbData = 8;
  pretrievecolumn.pvData = (char *)this + 616;
  pretrievecolumn.itagSequence = 1;
  pretrievecolumn.grbit = (_BYTE)v2 == 0;
  v11 = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), &pretrievecolumn, 1u);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_45;
    }
    v13 = 93;
    goto LABEL_44;
  }
  if ( (unsigned __int64)(*((_QWORD *)this + 77) - 1LL) > 1 )
  {
    v30 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 75) + 88LL))(*((_QWORD *)this + 75), &v30);
    if ( v15 < 0 )
    {
      v4 = (unsigned __int16)v15;
      goto LABEL_46;
    }
    v16 = *((_QWORD *)this + 75);
    v17 = *(_QWORD *)(v16 + 16);
    v35 = v17;
    v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v16 + 24) + 72LL))(v16 + 24);
    Size = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 75) + 24LL) + 88LL))(*((_QWORD *)this + 75) + 24LL);
    v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 75) + 24LL) + 80LL))(*((_QWORD *)this + 75) + 24LL);
    v37 = (struct peerdist_content_tag_tag *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 96LL))(*((_QWORD *)this + 75));
    v34 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 75) + 16LL) + 152LL);
    *((_WORD *)this + 296) = CRepubCacheBackingStore::SelectBlockDatabase(*((CRepubCacheBackingStore **)this + 1));
    CurrentTimeAsULONGLONG = GetCurrentTimeAsULONGLONG();
    v18 = (int *)((char *)this + 664);
    *((_DWORD *)this + 166) = 0;
    v19 = *((_DWORD *)this + 163);
    v20 = 0;
    if ( (v19 & 2) != 0 )
    {
      *v18 = 2;
      v20 = 2;
    }
    if ( (v19 & 1) != 0 )
    {
      if ( (v44 + v45 - 1) / v44 > 1 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 95, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
          v9 = WPP_GLOBAL_Control;
        }
        v4 = 87;
        goto LABEL_122;
      }
      v20 |= 0x40u;
      *v18 = v20;
    }
    v21 = (const struct TnoHash *)(v17 + 48);
    if ( (v19 & 4) != 0 )
    {
      v20 |= 0x100u;
      *v18 = v20;
    }
    if ( !*((_DWORD *)v21 + 2) )
    {
      *((_DWORD *)this + 166) = v20 | 0x80;
      v22 = (TnoHash *)operator new(0x20u);
      v25 = v22;
      *(_QWORD *)csetcolumn = v22;
      if ( v22 )
      {
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 75) + 24LL) + 96LL))(*((_QWORD *)this + 75) + 24LL);
        v22 = TnoHash::TnoHash(v25, v26);
      }
      std::auto_ptr<TnoHashKey>::reset(&v32, v22, v23, v24);
      v21 = v32;
    }
    if ( (*((_BYTE *)this + 652) & 5) == 0 )
    {
      v27 = operator new[](Size);
      std::auto_ptr<unsigned short>::reset(&v33, v27);
      v5 = (unsigned __int8 *)v33;
      memset_0(v33, 0, Size);
    }
    if ( (*((_BYTE *)this + 652) & 8) != 0 )
      *v18 |= 0x200u;
    memset_0(*((void **)this + 84), 0, *((unsigned int *)this + 167));
    memset_0(*((void **)this + 85), 0, *((unsigned int *)this + 167));
    memset_0(*((void **)this + 86), 0, *((unsigned int *)this + 167));
    if ( (*((_BYTE *)this + 652) & 1) != 0 )
      **((_BYTE **)this + 86) = -1;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 96, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
        v28 = WPP_GLOBAL_Control;
      }
      if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v28 + 108) & 4) != 0 && *((_BYTE *)v28 + 105) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)v28 + 12),
            97,
            WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
            (unsigned int)*((__int16 *)this + 296));
          v28 = WPP_GLOBAL_Control;
        }
        if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v28 + 108) & 4) != 0 && *((_BYTE *)v28 + 105) >= 3u )
          {
            WPP_SF_q(*((_QWORD *)v28 + 12), 98, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
            v28 = WPP_GLOBAL_Control;
          }
          if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v28 + 108) & 4) != 0 && *((_BYTE *)v28 + 105) >= 3u )
            {
              WPP_SF_q(*((_QWORD *)v28 + 12), 99, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
              v28 = WPP_GLOBAL_Control;
            }
            if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v28 + 108) & 4) != 0
              && *((_BYTE *)v28 + 105) >= 3u )
            {
              WPP_SF_(*((_QWORD *)v28 + 12), 100, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
            }
          }
        }
      }
    }
    csetcolumn[0] = *((_DWORD *)this + 96);
    CRepubCreateSegmentTask::InitializeCatalogTableSetColumns(
      this,
      (const struct TnoHoHoDk *)(v35 + 16),
      v21,
      &v30,
      v37,
      &v45,
      &v44,
      &v34,
      &CurrentTimeAsULONGLONG,
      (__int16 *)this + 296,
      (unsigned int *)this + 166,
      *((_DWORD *)this + 167),
      *((const unsigned __int8 **)this + 84),
      *((const unsigned __int8 **)this + 85),
      *((const unsigned __int8 **)this + 86),
      Size,
      v5,
      *((struct JET_SETCOLUMN **)this + 50),
      csetcolumn);
    v11 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), *((JET_SETCOLUMN **)this + 50), csetcolumn[0]);
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_45;
      }
      v13 = 101;
    }
    else
    {
      v11 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 0, 0, 0);
      if ( v11 == -1605 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            102,
            WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
            4294965691LL);
        }
        *((_BYTE *)this + 648) = 1;
        v4 = (*(__int64 (__fastcall **)(CRepubCreateSegmentTask *, __int64))(*(_QWORD *)this + 48LL))(
               this,
               4294965691LL);
        v11 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 3u);
        if ( !v11 )
          goto LABEL_46;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_45;
        }
        v13 = 103;
      }
      else
      {
        if ( !v11 )
          goto LABEL_46;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_45;
        }
        v13 = 104;
      }
    }
    goto LABEL_44;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 94, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v4 = 774;
LABEL_122:
  if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v9 + 108) & 4) != 0
    && *((_BYTE *)v9 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v9 + 12), 105, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v4);
  }
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>((__int64 (__fastcall ****)(_QWORD, __int64))&v32);
  operator delete(v5);
  return v4;
}

```

## disassembly

```asm
0x180066508  mov     [rsp-8+arg_0], rbx
0x18006650d  push    rbp
0x18006650e  push    rsi
0x18006650f  push    rdi
0x180066510  push    r12
0x180066512  push    r13
0x180066514  push    r14
0x180066516  push    r15
0x180066518  lea     rbp, [rsp-20h]
0x18006651d  sub     rsp, 140h
0x180066524  movzx   r12d, dl
0x180066528  mov     rdi, rcx
0x18006652b  lea     rax, WPP_GLOBAL_Control
0x180066532  mov     rcx, cs:WPP_GLOBAL_Control
0x180066539  cmp     rcx, rax
0x18006653c  jz      short loc_18006655F
0x18006653e  test    byte ptr [rcx+6Ch], 4
0x180066542  jz      short loc_18006655F
0x180066544  cmp     byte ptr [rcx+69h], 4
0x180066548  jb      short loc_18006655F
0x18006654a  mov     edx, 56h ; 'V'
0x18006654f  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180066556  mov     rcx, [rcx+60h]
0x18006655a  call    WPP_SF_
0x18006655f  xor     esi, esi
0x180066561  xorps   xmm0, xmm0
0x180066564  movups  xmmword ptr [rbp+50h+pretrievecolumn.columnid], xmm0
0x180066568  movups  xmmword ptr [rbp+50h+pretrievecolumn.cbData], xmm0
0x18006656c  movups  xmmword ptr [rbp+50h+pretrievecolumn.itagSequence], xmm0
0x180066570  xor     ebx, ebx
0x180066572  mov     [rbp+50h+var_B8], rbx
0x180066576  mov     [rbp+50h+var_C0], rbx
0x18006657a  test    r12b, r12b
0x18006657d  jnz     loc_18006676D
0x180066583  xor     r13b, r13b
0x180066586  xor     r15b, r15b
0x180066589  lea     rax, ??_7CCatalogTableFileSegmentsIterator@@6B@; const CCatalogTableFileSegmentsIterator::`vftable'
0x180066590  mov     [rbp+50h+var_60], rax
0x180066594  mov     rax, [rdi+178h]
0x18006659b  mov     [rbp+50h+var_48], rax
0x18006659f  mov     rax, [rdi+1F0h]
0x1800665a6  mov     [rbp+50h+var_40], rax
0x1800665aa  xor     eax, eax
0x1800665ac  mov     [rbp+50h+var_50], ax
0x1800665b0  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800665ba  mov     [rbp+50h+var_58], rax
0x1800665be  lea     rcx, [rbp+50h+var_60]; this
0x1800665c2  call    ?FindFirst@CCatalogTableFileSegmentsIterator@@UEAAKXZ; CCatalogTableFileSegmentsIterator::FindFirst(void)
0x1800665c7  mov     esi, eax
0x1800665c9  lea     rax, WPP_GLOBAL_Control
0x1800665d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800665d7  test    r15b, r15b
0x1800665da  jnz     loc_180066768
0x1800665e0  cmp     esi, 490h
0x1800665e6  jnz     short loc_180066626
0x1800665e8  cmp     rcx, rax
0x1800665eb  jz      short loc_18006661F
0x1800665ed  test    byte ptr [rcx+6Ch], 4
0x1800665f1  jz      short loc_18006661F
0x1800665f3  cmp     byte ptr [rcx+69h], 4
0x1800665f7  jb      short loc_18006661F
0x1800665f9  mov     edx, 57h ; 'W'
0x1800665fe  mov     r9d, esi
0x180066601  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180066608  mov     rcx, [rcx+60h]
0x18006660c  call    WPP_SF_d
0x180066611  mov     rcx, cs:WPP_GLOBAL_Control
0x180066618  lea     rax, WPP_GLOBAL_Control
0x18006661f  xor     esi, esi
0x180066621  mov     r15b, 1
0x180066624  jmp     short loc_1800665D7
0x180066626  test    esi, esi
0x180066628  jnz     loc_180066733
0x18006662e  lea     r8d, [rsi+2]; prep
0x180066632  mov     rdx, [rdi+1F0h]; tableid
0x180066639  mov     rcx, [rdi+178h]; sesid
0x180066640  call    cs:__imp_JetPrepareUpdate
0x180066646  mov     r14d, eax
0x180066649  cmp     eax, 0FFFFFBB2h
0x18006664e  jnz     short loc_180066693
0x180066650  mov     rcx, cs:WPP_GLOBAL_Control
0x180066657  lea     rax, WPP_GLOBAL_Control
0x18006665e  cmp     rcx, rax
0x180066661  jz      short loc_180066685
0x180066663  test    byte ptr [rcx+6Ch], 4
0x180066667  jz      short loc_180066685
0x180066669  cmp     byte ptr [rcx+69h], 4
0x18006666d  jb      short loc_180066685
0x18006666f  lea     edx, [rsi+59h]
0x180066672  mov     r9d, r14d
0x180066675  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18006667c  mov     rcx, [rcx+60h]
0x180066680  call    WPP_SF_d
0x180066685  lea     rcx, [rbp+50h+var_60]; this
0x180066689  call    ?FindNext@CCatalogTableFileSegmentsIterator@@UEAAKXZ; CCatalogTableFileSegmentsIterator::FindNext(void)
0x18006668e  jmp     loc_1800665C7
0x180066693  test    r14d, r14d
0x180066696  jnz     short loc_1800666E2
0x180066698  mov     r15b, 1
0x18006669b  mov     r13b, r15b
0x18006669e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800666a5  lea     rax, WPP_GLOBAL_Control
0x1800666ac  cmp     rcx, rax
0x1800666af  jz      loc_1800665D7
0x1800666b5  test    byte ptr [rcx+6Ch], 4
0x1800666b9  jz      loc_1800665D7
0x1800666bf  cmp     byte ptr [rcx+69h], 4
0x1800666c3  jb      loc_1800665D7
0x1800666c9  lea     edx, [r14+5Bh]
0x1800666cd  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800666d4  mov     rcx, [rcx+60h]
0x1800666d8  call    WPP_SF_
0x1800666dd  jmp     loc_1800665C9
0x1800666e2  mov     rax, [rdi]
0x1800666e5  mov     edx, r14d
0x1800666e8  mov     rcx, rdi
0x1800666eb  mov     rax, [rax+30h]
0x1800666ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666f4  mov     esi, eax
0x1800666f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800666fd  lea     rax, WPP_GLOBAL_Control
0x180066704  cmp     rcx, rax
0x180066707  jz      short loc_180066763
0x180066709  test    byte ptr [rcx+6Ch], 4
0x18006670d  jz      short loc_180066763
0x18006670f  cmp     byte ptr [rcx+69h], 1
0x180066713  jb      short loc_180066763
0x180066715  mov     edx, 5Ah ; 'Z'
0x18006671a  mov     dword ptr [rsp+170h+pcbActual], esi
0x18006671e  mov     r9d, r14d
0x180066721  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180066728  mov     rcx, [rcx+60h]
0x18006672c  call    WPP_SF_Dd
0x180066731  jmp     short loc_18006675C
0x180066733  cmp     rcx, rax
0x180066736  jz      short loc_180066763
0x180066738  test    byte ptr [rcx+6Ch], 4
0x18006673c  jz      short loc_180066763
0x18006673e  cmp     byte ptr [rcx+69h], 1
0x180066742  jb      short loc_180066763
0x180066744  mov     edx, 58h ; 'X'
0x180066749  mov     r9d, esi
0x18006674c  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180066753  mov     rcx, [rcx+60h]
0x180066757  call    WPP_SF_d
0x18006675c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066763  jmp     loc_180066E54
0x180066768  test    r13b, r13b
0x18006676b  jnz     short loc_1800667E5
0x18006676d  mov     r8d, r12d
0x180066770  add     r8d, r8d; prep
0x180066773  mov     rdx, [rdi+1F0h]; tableid
0x18006677a  mov     rcx, [rdi+178h]; sesid
0x180066781  call    cs:__imp_JetPrepareUpdate
0x180066787  mov     r14d, eax
0x18006678a  test    eax, eax
0x18006678c  jz      short loc_1800667E5
0x18006678e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066795  lea     rax, WPP_GLOBAL_Control
0x18006679c  cmp     rcx, rax
0x18006679f  jz      short loc_1800667C5
0x1800667a1  test    byte ptr [rcx+6Ch], 4
0x1800667a5  jz      short loc_1800667C5
0x1800667a7  cmp     byte ptr [rcx+69h], 1
0x1800667ab  jb      short loc_1800667C5
0x1800667ad  mov     edx, 5Ch ; '\'
0x1800667b2  mov     r9d, r14d
0x1800667b5  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800667bc  mov     rcx, [rcx+60h]
0x1800667c0  call    WPP_SF_d
0x1800667c5  mov     rax, [rdi]
0x1800667c8  mov     edx, r14d
0x1800667cb  mov     rcx, rdi
0x1800667ce  mov     rax, [rax+30h]
0x1800667d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667d7  mov     esi, eax
0x1800667d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667e0  jmp     loc_180066E54
0x1800667e5  mov     rax, [rdi+198h]
0x1800667ec  mov     ecx, [rax+32Ch]
0x1800667f2  xorps   xmm0, xmm0
0x1800667f5  movups  xmmword ptr [rbp+50h+pretrievecolumn.columnid], xmm0
0x1800667f9  movups  xmmword ptr [rbp+50h+pretrievecolumn.cbData], xmm0
0x1800667fd  movups  xmmword ptr [rbp+50h+pretrievecolumn.itagSequence], xmm0
0x180066801  mov     [rbp+50h+pretrievecolumn.columnid], ecx
0x180066804  mov     [rbp+50h+pretrievecolumn.cbData], 8
0x18006680b  lea     r13, [rdi+268h]
0x180066812  mov     [rbp+50h+pretrievecolumn.pvData], r13
0x180066816  mov     [rbp+50h+pretrievecolumn.itagSequence], 1
0x18006681d  xor     eax, eax
0x18006681f  test    r12b, r12b
0x180066822  setz    al
0x180066825  mov     [rbp+50h+pretrievecolumn.grbit], eax
0x180066828  mov     r9d, 1; cretrievecolumn
0x18006682e  lea     r8, [rbp+50h+pretrievecolumn]; pretrievecolumn
0x180066832  mov     rdx, [rdi+1F0h]; tableid
0x180066839  mov     rcx, [rdi+178h]; sesid
0x180066840  call    cs:__imp_JetRetrieveColumns
0x180066846  mov     r14d, eax
0x180066849  test    eax, eax
0x18006684b  jz      short loc_180066882
0x18006684d  mov     rcx, cs:WPP_GLOBAL_Control
0x180066854  lea     rax, WPP_GLOBAL_Control
0x18006685b  cmp     rcx, rax
0x18006685e  jz      loc_1800667C5
0x180066864  test    byte ptr [rcx+6Ch], 4
0x180066868  jz      loc_1800667C5
0x18006686e  cmp     byte ptr [rcx+69h], 1
0x180066872  jb      loc_1800667C5
0x180066878  mov     edx, 5Dh ; ']'
0x18006687d  jmp     loc_1800667B2
0x180066882  mov     r9, [r13+0]
0x180066886  lea     rax, [r9-1]
0x18006688a  cmp     rax, 1
0x18006688e  jbe     loc_180066E14
0x180066894  mov     [rbp+50h+var_D0], 0
0x18006689b  mov     rcx, [rdi+258h]
0x1800668a2  mov     rax, [rcx]
0x1800668a5  lea     rdx, [rbp+50h+var_D0]
0x1800668a9  mov     rax, [rax+58h]
0x1800668ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668b2  test    eax, eax
0x1800668b4  jns     short loc_1800668BE
0x1800668b6  movzx   esi, ax
0x1800668b9  jmp     loc_1800667D9
0x1800668be  mov     rax, [rdi+258h]
0x1800668c5  mov     r14, [rax+10h]
0x1800668c9  mov     [rbp+50h+var_A8], r14
0x1800668cd  lea     rcx, [rax+18h]
0x1800668d1  mov     rax, [rcx]
0x1800668d4  mov     rax, [rax+48h]
0x1800668d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668dd  mov     [rbp+50h+arg_18], eax
0x1800668e0  mov     rcx, [rdi+258h]
0x1800668e7  add     rcx, 18h
0x1800668eb  mov     rax, [rcx]
0x1800668ee  mov     rax, [rax+58h]
0x1800668f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668f7  mov     dword ptr [rbp+50h+Size], eax
0x1800668fa  mov     rcx, [rdi+258h]
0x180066901  add     rcx, 18h
0x180066905  mov     rdx, [rcx]
0x180066908  mov     rax, [rdx+50h]
0x18006690c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066911  mov     [rbp+50h+arg_10], eax
0x180066914  mov     rcx, [rdi+258h]
0x18006691b  mov     rdx, [rcx]
0x18006691e  mov     rax, [rdx+60h]
0x180066922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066927  mov     [rbp+50h+var_98], rax
0x18006692b  mov     rcx, [rdi+258h]
0x180066932  mov     rdx, [rcx+10h]
0x180066936  mov     rcx, [rdx+98h]
0x18006693d  mov     [rbp+50h+var_B0], rcx
0x180066941  lea     r12, [rdi+250h]
0x180066948  mov     rcx, [rdi+8]; this
0x18006694c  call    ?SelectBlockDatabase@CRepubCacheBackingStore@@QEAAFXZ; CRepubCacheBackingStore::SelectBlockDatabase(void)
0x180066951  mov     [r12], ax
0x180066956  call    ?GetCurrentTimeAsULONGLONG@@YA_KXZ; GetCurrentTimeAsULONGLONG(void)
0x18006695b  mov     [rbp+50h+var_A0], rax
0x18006695f  lea     r15, [rdi+298h]
0x180066966  mov     dword ptr [r15], 0
0x18006696d  mov     r9d, [rdi+28Ch]
0x180066974  xor     r8d, r8d
0x180066977  lea     eax, [r8+2]
0x18006697b  test    al, r9b
0x18006697e  jz      short loc_180066986
0x180066980  mov     [r15], eax
0x180066983  mov     r8d, eax
0x180066986  test    r9b, 1
0x18006698a  jz      short loc_1800669EA
0x18006698c  mov     eax, [rbp+50h+arg_18]
0x18006698f  dec     eax
0x180066991  add     eax, [rbp+50h+arg_10]
0x180066994  xor     edx, edx
0x180066996  div     [rbp+50h+arg_10]
0x180066999  cmp     eax, 1
0x18006699c  jbe     short loc_1800669E3
0x18006699e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800669a5  lea     rax, WPP_GLOBAL_Control
0x1800669ac  cmp     rcx, rax
0x1800669af  jz      short loc_1800669D9
0x1800669b1  test    byte ptr [rcx+6Ch], 4
0x1800669b5  jz      short loc_1800669D9
0x1800669b7  cmp     byte ptr [rcx+69h], 1
0x1800669bb  jb      short loc_1800669D9
0x1800669bd  mov     edx, 5Fh ; '_'
0x1800669c2  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800669c9  mov     rcx, [rcx+60h]
0x1800669cd  call    WPP_SF_
0x1800669d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800669d9  mov     esi, 57h ; 'W'
0x1800669de  jmp     loc_180066E54
0x1800669e3  or      r8d, 40h
0x1800669e7  mov     [r15], r8d
0x1800669ea  add     r14, 30h ; '0'
0x1800669ee  test    r9b, 4
0x1800669f2  jz      short loc_1800669FC
0x1800669f4  bts     r8d, 8
0x1800669f9  mov     [r15], r8d
  ... truncated ...
```
