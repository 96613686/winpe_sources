# CRepubCacheSegmentWriteDataTask::UpdateCatalogTable(unsigned __int64,ulong,bool,bool)

- ea: `0x180083a2c`
- end: `0x180084721`
- name: `?UpdateCatalogTable@CRepubCacheSegmentWriteDataTask@@AEAAK_KK_N1@Z`
- size: `3317`
- prototype: `unsigned int __fastcall(CRepubCacheSegmentWriteDataTask *__hidden this, unsigned __int64, unsigned int, bool, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180084fe4`

## callees

- `0x1800024f0`
- `0x1800024fc`
- `0x180004374`
- `0x180008290`
- `0x180008310`
- `0x18000873c`
- `0x18000ceac`
- `0x18000cef8`
- `0x180011798`
- `0x180018340`
- `0x1800521d8`
- `0x180061578`
- `0x180063ca0`
- `0x180077bd0`
- `0x18007b048`
- `0x180083a2c`
- `0x180092c40`
- `0x180144882`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x1800844f4`
- `ESENT!JetPrepareUpdate` at `0x1800844f4`
- `ESENT!JetSetColumns` at `0x180084567`
- `ESENT!JetSetColumns` at `0x180084567`
- `ESENT!JetRetrieveColumns` at `0x180083c66`
- `ESENT!JetRetrieveColumns` at `0x180083c66`
- `ESENT!JetUpdate` at `0x1800845d3`
- `ESENT!JetUpdate` at `0x1800845d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubCacheSegmentWriteDataTask::UpdateCatalogTable(
        CRepubCacheSegmentWriteDataTask *this,
        unsigned __int64 a2,
        unsigned int a3,
        char a4,
        bool a5)
{
  const wchar_t *v6; // r9
  void *v7; // rax
  unsigned __int8 *v8; // rbx
  __int64 v9; // rcx
  unsigned int First; // eax
  unsigned int updated; // esi
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rax
  int v18; // ecx
  __int64 v19; // rax
  int v20; // ecx
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rax
  unsigned int Columns; // r15d
  CHostedCacheMsgEncoding *v25; // rcx
  __int64 v26; // rdx
  char v27; // r15
  unsigned __int8 *v28; // r13
  unsigned __int8 *v29; // rsi
  CHostedCacheMsgEncoding *v30; // rcx
  bool v31; // r12
  bool v32; // al
  CHostedCacheMsgEncoding *v33; // rcx
  unsigned __int64 CurrentTimeAsULONGLONG; // rax
  __int64 v35; // r8
  int v36; // edx
  int v37; // ecx
  __int64 v38; // rax
  unsigned int v39; // r13d
  __int64 v40; // r8
  int v41; // edx
  int v42; // ecx
  __int64 v43; // rax
  int v44; // eax
  bool v45; // zf
  unsigned int v46; // r15d
  __int64 v47; // rax
  unsigned int v48; // eax
  unsigned int v49; // ecx
  char v50; // dl
  unsigned int v51; // eax
  int v52; // ecx
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r13
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 v58; // r13
  __int64 v59; // r8
  __int64 v60; // rax
  __int64 v61; // r13
  __int64 v62; // r8
  __int64 v63; // rcx
  __int64 v64; // r13
  __int64 v65; // r8
  __int64 v66; // rcx
  __int64 v67; // r13
  __int64 v68; // r8
  __int64 v69; // rcx
  __int64 v70; // r13
  __int64 v71; // r8
  __int64 v72; // rcx
  __int64 v73; // r13
  __int64 v74; // r9
  __int64 v75; // rdx
  unsigned int v76; // r15d
  unsigned int v77; // r15d
  unsigned int v78; // r9d
  unsigned int v79; // r15d
  unsigned int v80; // r9d
  unsigned int v82; // [rsp+68h] [rbp-61h] BYREF
  bool v83; // [rsp+6Ch] [rbp-5Dh] BYREF
  unsigned int v84; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int8 *v85; // [rsp+78h] [rbp-51h] BYREF
  __int16 v86; // [rsp+80h] [rbp-49h]
  unsigned int v87[2]; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v88; // [rsp+90h] [rbp-39h] BYREF
  void *Block; // [rsp+98h] [rbp-31h] BYREF
  __int64 v90; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int64 v91; // [rsp+A8h] [rbp-21h] BYREF
  _QWORD v92[13]; // [rsp+B0h] [rbp-19h] BYREF
  bool v93; // [rsp+128h] [rbp+5Fh] BYREF
  unsigned __int64 v94; // [rsp+130h] [rbp+67h]
  unsigned int v95; // [rsp+138h] [rbp+6Fh]
  char v96; // [rsp+140h] [rbp+77h]

  v96 = a4;
  v95 = a3;
  v94 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v6 = L"Y";
    if ( !*((_BYTE *)this + 680) )
      v6 = (const wchar_t *)L"N";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 160, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v6);
  }
  Block = 0;
  v7 = operator new[](*((unsigned int *)this + 178));
  std::auto_ptr<unsigned short>::reset(&Block, v7);
  v8 = (unsigned __int8 *)Block;
  memset_0(Block, 0, *((unsigned int *)this + 178));
  v82 = 0;
  v88 = 0;
  v90 = 0;
  v9 = *(_QWORD *)(*((_QWORD *)this + 83) + 24LL);
  v92[0] = &CCatalogTableSegmentIdIterator::`vftable';
  v92[2] = *((_QWORD *)this + 47);
  v92[3] = *((_QWORD *)this + 62);
  v92[1] = v9;
  First = CCatalogTableSegmentIdIterator::FindFirst((CCatalogTableSegmentIdIterator *)v92);
  updated = First;
  if ( First )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v13 = 161;
LABEL_12:
      v14 = First;
LABEL_126:
      WPP_SF_d(*((_QWORD *)v12 + 12), v13, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v14);
      goto LABEL_127;
    }
    goto LABEL_127;
  }
  v15 = *((_DWORD *)this + 178);
  v16 = *(_DWORD *)(*((_QWORD *)this + 51) + 888LL);
  v17 = *((_QWORD *)this + 49);
  *(_OWORD *)v17 = 0;
  *(_OWORD *)(v17 + 16) = 0;
  *(_OWORD *)(v17 + 32) = 0;
  *(_DWORD *)v17 = v16;
  *(_DWORD *)(v17 + 16) = v15;
  *(_QWORD *)(v17 + 8) = v8;
  *(_DWORD *)(v17 + 32) = 1;
  v18 = *(_DWORD *)(*((_QWORD *)this + 51) + 872LL);
  v19 = *((_QWORD *)this + 49);
  *(_OWORD *)(v19 + 48) = 0;
  *(_OWORD *)(v19 + 64) = 0;
  *(_OWORD *)(v19 + 80) = 0;
  *(_DWORD *)(v19 + 48) = v18;
  *(_DWORD *)(v19 + 64) = 4;
  *(_QWORD *)(v19 + 56) = &v82;
  *(_DWORD *)(v19 + 80) = 1;
  v20 = *(_DWORD *)(*((_QWORD *)this + 51) + 852LL);
  v21 = *((_QWORD *)this + 49);
  *(_OWORD *)(v21 + 96) = 0;
  *(_OWORD *)(v21 + 112) = 0;
  *(_OWORD *)(v21 + 128) = 0;
  *(_DWORD *)(v21 + 96) = v20;
  *(_DWORD *)(v21 + 112) = 4;
  *(_QWORD *)(v21 + 104) = &v88;
  *(_DWORD *)(v21 + 128) = 1;
  v22 = *(_DWORD *)(*((_QWORD *)this + 51) + 856LL);
  v23 = *((_QWORD *)this + 49);
  *(_OWORD *)(v23 + 144) = 0;
  *(_OWORD *)(v23 + 160) = 0;
  *(_OWORD *)(v23 + 176) = 0;
  *(_DWORD *)(v23 + 144) = v22;
  *(_DWORD *)(v23 + 160) = 8;
  *(_QWORD *)(v23 + 152) = &v90;
  *(_DWORD *)(v23 + 176) = 1;
  Columns = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), *((JET_RETRIEVECOLUMN **)this + 49), 4u);
  if ( Columns )
  {
    updated = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                this,
                Columns);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_127;
    }
    v26 = 162;
    goto LABEL_18;
  }
  if ( v90 == 0x7FFFFFFFFFFFFFFFLL )
  {
    updated = 4054;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        163,
        WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 83) + 24LL),
        4054);
    }
    goto LABEL_127;
  }
  v27 = 0;
  v28 = (unsigned __int8 *)*((_QWORD *)this + 90);
  v29 = (unsigned __int8 *)*((_QWORD *)this + 91);
  *(_QWORD *)v87 = v29;
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      v85 = (unsigned __int8 *)*((_QWORD *)this + 93);
      v86 = *((_WORD *)this + 356);
      WPP_SF__HEX_(*((_QWORD *)WPP_GLOBAL_Control + 12), 164, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v85);
      v30 = WPP_GLOBAL_Control;
    }
    if ( v30 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v30 + 108) & 4) != 0
      && *((_BYTE *)v30 + 105) >= 3u )
    {
      v85 = v28;
      v86 = *((_WORD *)this + 356);
      WPP_SF__HEX_(*((_QWORD *)v30 + 12), 165, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v85);
      v30 = WPP_GLOBAL_Control;
    }
  }
  v31 = a5;
  if ( *((_BYTE *)this + 680) || a5 )
  {
    if ( v30 == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      goto LABEL_42;
    if ( (*((_BYTE *)v30 + 108) & 4) != 0 && *((_BYTE *)v30 + 105) >= 3u )
    {
      v85 = v29;
      v86 = *((_WORD *)this + 356);
      WPP_SF__HEX_(*((_QWORD *)v30 + 12), 166, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v85);
      v30 = WPP_GLOBAL_Control;
    }
  }
  if ( v30 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v30 + 108) & 4) != 0
    && *((_BYTE *)v30 + 105) >= 3u )
  {
    v85 = v8;
    v86 = *((_WORD *)this + 356);
    WPP_SF__HEX_(*((_QWORD *)v30 + 12), 167, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v85);
  }
LABEL_42:
  if ( (v82 & 0x400) == 0 && *((_BYTE *)this + 644) )
    v27 = 1;
  v93 = 0;
  v83 = 0;
  First = CRepubCacheSegment::UpdateAvailableBlockMasks(
            *((CRepubCacheSegment **)this + 82),
            v94,
            v95,
            *((_DWORD *)this + 178),
            v28,
            v29,
            v8,
            *((unsigned __int8 **)this + 93),
            *((_BYTE *)this + 680),
            &v93,
            (bool *)this + 698,
            &v83);
  updated = First;
  if ( !First )
  {
    v32 = v83;
    if ( *((_BYTE *)this + 697) )
      v32 = 1;
    *((_BYTE *)this + 697) = v32;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      v85 = v28;
      v86 = *((_WORD *)this + 356);
      WPP_SF__HEX_(*((_QWORD *)WPP_GLOBAL_Control + 12), 169, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v85);
      v33 = WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)this + 680) || v31)
      && v33 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v33 + 108) & 4) != 0
      && *((_BYTE *)v33 + 105) >= 3u )
    {
      v85 = *(unsigned __int8 **)v87;
      v86 = *((_WORD *)this + 356);
      WPP_SF__HEX_(*((_QWORD *)v33 + 12), 170, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, &v85);
      v33 = WPP_GLOBAL_Control;
    }
    if ( !v93 && !v96 && !v31 && !v27 )
    {
      if ( v33 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v33 + 108) & 4) != 0
        && *((_BYTE *)v33 + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)v33 + 12), 171, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
      }
      goto LABEL_127;
    }
    CurrentTimeAsULONGLONG = GetCurrentTimeAsULONGLONG();
    v91 = CurrentTimeAsULONGLONG;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        172,
        WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
        v82,
        CurrentTimeAsULONGLONG);
    }
    v35 = *((_QWORD *)this + 90);
    v36 = *((_DWORD *)this + 178);
    v37 = *(_DWORD *)(*((_QWORD *)this + 51) + 880LL);
    v38 = *((_QWORD *)this + 50);
    *(_DWORD *)(v38 + 4) = 0;
    *(_QWORD *)(v38 + 20) = 0;
    *(_QWORD *)(v38 + 32) = 0;
    *(_DWORD *)v38 = v37;
    *(_DWORD *)(v38 + 16) = v36;
    *(_QWORD *)(v38 + 8) = v35;
    *(_DWORD *)(v38 + 28) = 1;
    if ( *((_BYTE *)this + 698) || (v39 = 1, v31) )
    {
      v40 = *((_QWORD *)this + 91);
      v41 = *((_DWORD *)this + 178);
      v42 = *(_DWORD *)(*((_QWORD *)this + 51) + 884LL);
      v43 = *((_QWORD *)this + 50);
      *(_DWORD *)(v43 + 44) = 0;
      *(_QWORD *)(v43 + 60) = 0;
      *(_QWORD *)(v43 + 72) = 0;
      *(_DWORD *)(v43 + 40) = v42;
      *(_DWORD *)(v43 + 56) = v41;
      *(_QWORD *)(v43 + 48) = v40;
      *(_DWORD *)(v43 + 68) = 1;
      v39 = 2;
      v44 = v82;
      if ( (v82 & 4) != 0 )
      {
LABEL_80:
        if ( (v44 & 0x10) == 0 )
        {
          v45 = !CRepubCacheSegment::AllDataBlockBitsSet(
                   *((CRepubCacheSegment **)this + 82),
                   *((_DWORD *)this + 178),
                   *((unsigned __int8 **)this + 90));
          v44 = v82;
          if ( !v45 )
          {
            v44 = v82 | 0x10;
            v82 |= 0x10u;
            *((_BYTE *)this + 702) = 1;
          }
        }
        if ( v27 )
          v82 = v44 | 0x400;
        v46 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 82) + 16LL))(*((_QWORD *)this + 82));
        v87[0] = 0;
        updated = CountAvailableBits(*((_DWORD *)this + 178), *((unsigned __int8 **)this + 90), v46, v87);
        if ( updated )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_127;
          }
          v13 = 173;
          goto LABEL_125;
        }
        v84 = 0;
        v47 = *(_QWORD *)(*((_QWORD *)this + 82) + 24LL);
        if ( v87[0] != v46 )
        {
          v84 = v87[0] * (*(__int64 (**)(void))(v47 + 80))();
          v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 82) + 24LL) + 72LL))(*((_QWORD *)this + 82) + 24LL);
          v49 = v84;
          if ( v84 <= v48 )
            goto LABEL_94;
          v47 = *(_QWORD *)(*((_QWORD *)this + 82) + 24LL);
        }
        v84 = (*(__int64 (**)(void))(v47 + 72))();
        v49 = v84;
LABEL_94:
        if ( v88 <= v49 )
        {
          v50 = 1;
          v51 = v49 - v88;
        }
        else
        {
          v50 = 0;
          v51 = v88 - v49;
        }
        *((_DWORD *)this + 173) = v51;
        *((_BYTE *)this + 696) = v50;
        v52 = *(_DWORD *)(*((_QWORD *)this + 51) + 872LL);
        v53 = 5LL * v39;
        v54 = *((_QWORD *)this + 50);
        *(_DWORD *)(v54 + 8 * v53 + 4) = 0;
        *(_QWORD *)(v54 + 8 * v53 + 20) = 0;
        *(_QWORD *)(v54 + 8 * v53 + 32) = 0;
        *(_DWORD *)(v54 + 8 * v53) = v52;
        *(_DWORD *)(v54 + 8 * v53 + 16) = 4;
        *(_QWORD *)(v54 + 8 * v53 + 8) = &v82;
        *(_DWORD *)(v54 + 8 * v53 + 28) = 1;
        v55 = v39 + 1;
        LODWORD(v53) = *(_DWORD *)(*((_QWORD *)this + 51) + 844LL);
        v56 = 5 * v55;
        v57 = *((_QWORD *)this + 50);
        *(_DWORD *)(v57 + 8 * v56 + 4) = 0;
        *(_QWORD *)(v57 + 8 * v56 + 20) = 0;
        *(_QWORD *)(v57 + 8 * v56 + 32) = 0;
        *(_DWORD *)(v57 + 8 * v56) = v53;
        *(_DWORD *)(v57 + 8 * v56 + 16) = 8;
        *(_QWORD *)(v57 + 8 * v56 + 8) = &v91;
        *(_DWORD *)(v57 + 8 * v56 + 28) = 1;
        v58 = (unsigned int)(v55 + 1);
        LODWORD(v53) = *(_DWORD *)(*((_QWORD *)this + 51) + 852LL);
        v59 = 5 * v58;
        v60 = *((_QWORD *)this + 50);
        *(_DWORD *)(v60 + 8 * v59 + 4) = 0;
        *(_QWORD *)(v60 + 8 * v59 + 20) = 0;
        *(_QWORD *)(v60 + 8 * v59 + 32) = 0;
        *(_DWORD *)(v60 + 8 * v59) = v53;
        *(_DWORD *)(v60 + 8 * v59 + 16) = 4;
        *(_QWORD *)(v60 + 8 * v59 + 8) = &v84;
        *(_DWORD *)(v60 + 8 * v59 + 28) = 1;
        v61 = (unsigned int)(v58 + 1);
        LODWORD(v53) = *(_DWORD *)(*((_QWORD *)this + 51) + 828LL);
        v62 = 5 * v61;
        v63 = *((_QWORD *)this + 50);
        *(_DWORD *)(v63 + 8 * v62 + 4) = 0;
        *(_QWORD *)(v63 + 8 * v62 + 20) = 0;
        *(_QWORD *)(v63 + 8 * v62 + 32) = 0;
        *(_DWORD *)(v63 + 8 * v62) = v53;
        *(_DWORD *)(v63 + 8 * v62 + 16) = 1;
        *(_QWORD *)(v63 + 8 * v62 + 8) = (char *)this + 704;
        *(_DWORD *)(v63 + 8 * v62 + 28) = 1;
        v64 = (unsigned int)(v61 + 1);
        LODWORD(v53) = *(_DWORD *)(*((_QWORD *)this + 51) + 856LL);
        v65 = 5 * v64;
        v66 = *((_QWORD *)this + 50);
        *(_DWORD *)(v66 + 8 * v65 + 4) = 0;
        *(_QWORD *)(v66 + 8 * v65 + 20) = 0;
        *(_QWORD *)(v66 + 8 * v65 + 32) = 0;
        *(_DWORD *)(v66 + 8 * v65) = v53;
        *(_DWORD *)(v66 + 8 * v65 + 16) = 8;
        *(_QWORD *)(v66 + 8 * v65 + 8) = (char *)this + 624;
        *(_DWORD *)(v66 + 8 * v65 + 28) = 1;
        v67 = (unsigned int)(v64 + 1);
        LODWORD(v53) = *(_DWORD *)(*((_QWORD *)this + 51) + 860LL);
        v68 = 5 * v67;
        v69 = *((_QWORD *)this + 50);
        *(_DWORD *)(v69 + 8 * v68 + 4) = 0;
        *(_QWORD *)(v69 + 8 * v68 + 20) = 0;
        *(_QWORD *)(v69 + 8 * v68 + 32) = 0;
        *(_DWORD *)(v69 + 8 * v68) = v53;
        *(_DWORD *)(v69 + 8 * v68 + 16) = 4;
        *(_QWORD *)(v69 + 8 * v68 + 8) = (char *)this + 632;
        *(_DWORD *)(v69 + 8 * v68 + 28) = 1;
        v70 = (unsigned int)(v67 + 1);
        LODWORD(v53) = *(_DWORD *)(*((_QWORD *)this + 51) + 864LL);
        v71 = 5 * v70;
        v72 = *((_QWORD *)this + 50);
        *(_DWORD *)(v72 + 8 * v71 + 4) = 0;
        *(_QWORD *)(v72 + 8 * v71 + 20) = 0;
        *(_QWORD *)(v72 + 8 * v71 + 32) = 0;
        *(_DWORD *)(v72 + 8 * v71) = v53;
        *(_DWORD *)(v72 + 8 * v71 + 16) = 4;
        *(_QWORD *)(v72 + 8 * v71 + 8) = (char *)this + 636;
        *(_DWORD *)(v72 + 8 * v71 + 28) = 1;
        v73 = (unsigned int)(v70 + 1);
        LODWORD(v72) = *(_DWORD *)(*((_QWORD *)this + 51) + 868LL);
        v74 = 5 * v73;
        v75 = *((_QWORD *)this + 50);
        *(_DWORD *)(v75 + 8 * v74 + 4) = 0;
        *(_QWORD *)(v75 + 8 * v74 + 20) = 0;
        *(_QWORD *)(v75 + 8 * v74 + 32) = 0;
        *(_DWORD *)(v75 + 8 * v74) = v72;
        *(_DWORD *)(v75 + 8 * v74 + 16) = 4;
        *(_QWORD *)(v75 + 8 * v74 + 8) = (char *)this + 640;
        *(_DWORD *)(v75 + 8 * v74 + 28) = 1;
        v76 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 2u);
        if ( v76 )
        {
          updated = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                      this,
                      v76);
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_127;
          }
          v26 = 174;
        }
        else
        {
          v77 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), *((JET_SETCOLUMN **)this + 50), v73 + 1);
          if ( v77 )
          {
            updated = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                        this,
                        v77);
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_127;
            }
            v26 = 175;
          }
          else
          {
            v79 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 0, 0, 0);
            if ( !v79 )
            {
              if ( !*((_BYTE *)this + 702) || !v93 && !v96 )
                goto LABEL_127;
              updated = UpdateRepubSegmentCount(
                          *((_QWORD *)this + 47),
                          *((_QWORD *)this + 63),
                          *((const struct _CatalogDatabaseDescriptor **)this + 51),
                          v78,
                          1,
                          1);
              if ( updated )
              {
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_127;
                }
                v13 = 177;
              }
              else
              {
                updated = UpdateRepubSegmentCount(
                            *((_QWORD *)this + 47),
                            *((_QWORD *)this + 63),
                            *((const struct _CatalogDatabaseDescriptor **)this + 51),
                            v80,
                            0,
                            0);
                if ( !updated )
                  goto LABEL_127;
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  goto LABEL_127;
                }
                v13 = 178;
              }
LABEL_125:
              v14 = updated;
              goto LABEL_126;
            }
            updated = (*(__int64 (__fastcall **)(CRepubCacheSegmentWriteDataTask *, _QWORD))(*(_QWORD *)this + 48LL))(
                        this,
                        v79);
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_127;
            }
            v26 = 176;
          }
        }
LABEL_18:
        WPP_SF_Dd(*((_QWORD *)v25 + 12), v26, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
        goto LABEL_127;
      }
      if ( CRepubCacheSegment::AllDataBlockBitsSet(
             *((CRepubCacheSegment **)this + 82),
             *((_DWORD *)this + 178),
             *((unsigned __int8 **)this + 91)) )
      {
        v44 = v82 | 4;
        v82 |= 4u;
        *((_BYTE *)this + 701) = 1;
        goto LABEL_80;
      }
    }
    v44 = v82;
    goto LABEL_80;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v13 = 168;
    goto LABEL_12;
  }
LABEL_127:
  v92[0] = &CBasePubCacheTableIterator::`vftable';
  operator delete(v8);
  return updated;
}

```

## disassembly

```asm
0x180083a2c  mov     rax, rsp
0x180083a2f  mov     [rax+20h], r9b
0x180083a33  mov     [rax+18h], r8d
0x180083a37  mov     [rax+10h], rdx
0x180083a3b  push    rbp
0x180083a3c  push    rbx
0x180083a3d  push    rsi
0x180083a3e  push    rdi
0x180083a3f  push    r12
0x180083a41  push    r13
0x180083a43  push    r14
0x180083a45  push    r15
0x180083a47  lea     rbp, [rax-57h]
0x180083a4b  sub     rsp, 0D8h
0x180083a52  mov     rdi, rcx
0x180083a55  lea     r14, WPP_GLOBAL_Control
0x180083a5c  xor     r12d, r12d
0x180083a5f  lea     r13d, [r12+4]
0x180083a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180083a6b  cmp     rcx, r14
0x180083a6e  jz      short loc_180083AAA
0x180083a70  test    [rcx+6Ch], r13b
0x180083a74  jz      short loc_180083AAA
0x180083a76  cmp     [rcx+69h], r13b
0x180083a7a  jb      short loc_180083AAA
0x180083a7c  lea     rax, aN; "N"
0x180083a83  lea     r9, aY; "Y"
0x180083a8a  cmp     [rdi+2A8h], r12b
0x180083a91  cmovz   r9, rax
0x180083a95  mov     edx, 0A0h
0x180083a9a  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083aa1  mov     rcx, [rcx+60h]
0x180083aa5  call    WPP_SF_S
0x180083aaa  mov     [rbp+4Fh+Block], r12
0x180083aae  mov     ecx, [rdi+2C8h]; unsigned __int64
0x180083ab4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180083ab9  mov     rdx, rax
0x180083abc  lea     rcx, [rbp+4Fh+Block]
0x180083ac0  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x180083ac5  mov     r8d, [rdi+2C8h]; Size
0x180083acc  xor     edx, edx; Val
0x180083ace  mov     rbx, [rbp+4Fh+Block]
0x180083ad2  mov     rcx, rbx; void *
0x180083ad5  call    memset_0
0x180083ada  mov     [rbp+4Fh+var_B0], r12d
0x180083ade  mov     [rbp+4Fh+var_88], r12d
0x180083ae2  mov     [rbp+4Fh+var_78], r12
0x180083ae6  mov     rax, [rdi+298h]
0x180083aed  mov     rcx, [rax+18h]
0x180083af1  lea     rax, ??_7CCatalogTableSegmentIdIterator@@6B@; const CCatalogTableSegmentIdIterator::`vftable'
0x180083af8  mov     [rbp+4Fh+var_68], rax
0x180083afc  mov     rax, [rdi+178h]
0x180083b03  mov     [rbp+4Fh+var_58], rax
0x180083b07  mov     rax, [rdi+1F0h]
0x180083b0e  mov     [rbp+4Fh+var_50], rax
0x180083b12  mov     [rbp+4Fh+var_60], rcx
0x180083b16  lea     rcx, [rbp+4Fh+var_68]; this
0x180083b1a  call    ?FindFirst@CCatalogTableSegmentIdIterator@@UEAAKXZ; CCatalogTableSegmentIdIterator::FindFirst(void)
0x180083b1f  mov     esi, eax
0x180083b21  test    eax, eax
0x180083b23  jz      short loc_180083B5C
0x180083b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180083b2c  cmp     rcx, r14
0x180083b2f  jz      loc_1800846F8
0x180083b35  test    [rcx+6Ch], r13b
0x180083b39  jz      loc_1800846F8
0x180083b3f  mov     r14d, 1
0x180083b45  cmp     [rcx+69h], r14b
0x180083b49  jb      loc_1800846F8
0x180083b4f  mov     edx, 0A1h
0x180083b54  mov     r9d, eax
0x180083b57  jmp     loc_1800846E7
0x180083b5c  mov     edx, [rdi+2C8h]
0x180083b62  mov     rax, [rdi+198h]
0x180083b69  mov     ecx, [rax+378h]
0x180083b6f  mov     rax, [rdi+188h]
0x180083b76  xorps   xmm0, xmm0
0x180083b79  movups  xmmword ptr [rax], xmm0
0x180083b7c  movups  xmmword ptr [rax+10h], xmm0
0x180083b80  movups  xmmword ptr [rax+20h], xmm0
0x180083b84  mov     [rax], ecx
0x180083b86  mov     [rax+10h], edx
0x180083b89  mov     [rax+8], rbx
0x180083b8d  mov     r14d, 1
0x180083b93  mov     [rax+20h], r14d
0x180083b97  mov     rax, [rdi+198h]
0x180083b9e  mov     ecx, [rax+368h]
0x180083ba4  mov     rax, [rdi+188h]
0x180083bab  movups  xmmword ptr [rax+30h], xmm0
0x180083baf  movups  xmmword ptr [rax+40h], xmm0
0x180083bb3  movups  xmmword ptr [rax+50h], xmm0
0x180083bb7  mov     [rax+30h], ecx
0x180083bba  mov     [rax+40h], r13d
0x180083bbe  lea     rcx, [rbp+4Fh+var_B0]
0x180083bc2  mov     [rax+38h], rcx
0x180083bc6  mov     [rax+50h], r14d
0x180083bca  mov     rax, [rdi+198h]
0x180083bd1  mov     ecx, [rax+354h]
0x180083bd7  mov     rax, [rdi+188h]
0x180083bde  movups  xmmword ptr [rax+60h], xmm0
0x180083be2  movups  xmmword ptr [rax+70h], xmm0
0x180083be6  movups  xmmword ptr [rax+80h], xmm0
0x180083bed  mov     [rax+60h], ecx
0x180083bf0  mov     [rax+70h], r13d
0x180083bf4  lea     rcx, [rbp+4Fh+var_88]
0x180083bf8  mov     [rax+68h], rcx
0x180083bfc  mov     [rax+80h], r14d
0x180083c03  mov     rax, [rdi+198h]
0x180083c0a  mov     ecx, [rax+358h]
0x180083c10  mov     rax, [rdi+188h]
0x180083c17  movups  xmmword ptr [rax+90h], xmm0
0x180083c1e  movups  xmmword ptr [rax+0A0h], xmm0
0x180083c25  movups  xmmword ptr [rax+0B0h], xmm0
0x180083c2c  mov     [rax+90h], ecx
0x180083c32  mov     dword ptr [rax+0A0h], 8
0x180083c3c  lea     rcx, [rbp+4Fh+var_78]
0x180083c40  mov     [rax+98h], rcx
0x180083c47  mov     [rax+0B0h], r14d
0x180083c4e  mov     r9d, r13d; cretrievecolumn
0x180083c51  mov     r8, [rdi+188h]; pretrievecolumn
0x180083c58  mov     rdx, [rdi+1F0h]; tableid
0x180083c5f  mov     rcx, [rdi+178h]; sesid
0x180083c66  call    cs:__imp_JetRetrieveColumns
0x180083c6c  mov     r15d, eax
0x180083c6f  test    eax, eax
0x180083c71  jz      short loc_180083CD3
0x180083c73  mov     rcx, [rdi]
0x180083c76  mov     rax, [rcx+30h]
0x180083c7a  mov     edx, r15d
0x180083c7d  mov     rcx, rdi
0x180083c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c85  mov     esi, eax
0x180083c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180083c8e  lea     rdx, WPP_GLOBAL_Control
0x180083c95  cmp     rcx, rdx
0x180083c98  jz      loc_1800846F8
0x180083c9e  test    [rcx+6Ch], r13b
0x180083ca2  jz      loc_1800846F8
0x180083ca8  cmp     [rcx+69h], r14b
0x180083cac  jb      loc_1800846F8
0x180083cb2  mov     edx, 0A2h
0x180083cb7  mov     dword ptr [rsp+110h+pcbActual], eax
0x180083cbb  mov     r9d, r15d
0x180083cbe  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083cc5  mov     rcx, [rcx+60h]
0x180083cc9  call    WPP_SF_Dd
0x180083cce  jmp     loc_1800846F8
0x180083cd3  mov     rax, 7FFFFFFFFFFFFFFFh
0x180083cdd  cmp     [rbp+4Fh+var_78], rax
0x180083ce1  jnz     short loc_180083D3C
0x180083ce3  mov     esi, 0FD6h
0x180083ce8  mov     rcx, cs:WPP_GLOBAL_Control
0x180083cef  lea     rdx, WPP_GLOBAL_Control
0x180083cf6  cmp     rcx, rdx
0x180083cf9  jz      loc_1800846F8
0x180083cff  test    [rcx+6Ch], r13b
0x180083d03  jz      loc_1800846F8
0x180083d09  cmp     [rcx+69h], r14b
0x180083d0d  jb      loc_1800846F8
0x180083d13  mov     r9, [rdi+298h]
0x180083d1a  mov     edx, 0A3h
0x180083d1f  mov     dword ptr [rsp+110h+pcbActual], esi
0x180083d23  mov     r9, [r9+18h]
0x180083d27  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083d2e  mov     rcx, [rcx+60h]
0x180083d32  call    WPP_SF_qD
0x180083d37  jmp     loc_1800846F8
0x180083d3c  movzx   r15d, r12b
0x180083d40  mov     r13, [rdi+2D0h]
0x180083d47  mov     rsi, [rdi+2D8h]
0x180083d4e  mov     qword ptr [rbp+4Fh+var_90], rsi
0x180083d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180083d59  lea     rax, WPP_GLOBAL_Control
0x180083d60  cmp     rcx, rax
0x180083d63  jz      loc_180083DF9
0x180083d69  test    byte ptr [rcx+6Ch], 4
0x180083d6d  jz      short loc_180083DB2
0x180083d6f  cmp     byte ptr [rcx+69h], 3
0x180083d73  jb      short loc_180083DB2
0x180083d75  mov     rax, [rdi+2E8h]
0x180083d7c  mov     [rbp+4Fh+var_A0], rax
0x180083d80  movzx   eax, word ptr [rdi+2C8h]
0x180083d87  mov     [rbp+4Fh+var_98], ax
0x180083d8b  mov     edx, 0A4h
0x180083d90  lea     r9, [rbp+4Fh+var_A0]
0x180083d94  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083d9b  mov     rcx, [rcx+60h]
0x180083d9f  call    WPP_SF__HEX_
0x180083da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180083dab  lea     rax, WPP_GLOBAL_Control
0x180083db2  cmp     rcx, rax
0x180083db5  jz      short loc_180083DF9
0x180083db7  test    byte ptr [rcx+6Ch], 4
0x180083dbb  jz      short loc_180083DF9
0x180083dbd  cmp     byte ptr [rcx+69h], 3
0x180083dc1  jb      short loc_180083DF9
0x180083dc3  mov     [rbp+4Fh+var_A0], r13
0x180083dc7  movzx   eax, word ptr [rdi+2C8h]
0x180083dce  mov     [rbp+4Fh+var_98], ax
0x180083dd2  mov     edx, 0A5h
0x180083dd7  lea     r9, [rbp+4Fh+var_A0]
0x180083ddb  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083de2  mov     rcx, [rcx+60h]
0x180083de6  call    WPP_SF__HEX_
0x180083deb  mov     rcx, cs:WPP_GLOBAL_Control
0x180083df2  lea     rax, WPP_GLOBAL_Control
0x180083df9  mov     r12b, [rbp+4Fh+arg_20]
0x180083dfd  cmp     byte ptr [rdi+2A8h], 0
0x180083e04  jnz     short loc_180083E0B
0x180083e06  test    r12b, r12b
0x180083e09  jz      short loc_180083E52
0x180083e0b  cmp     rcx, rax
0x180083e0e  jz      short loc_180083E8B
0x180083e10  test    byte ptr [rcx+6Ch], 4
0x180083e14  jz      short loc_180083E52
0x180083e16  cmp     byte ptr [rcx+69h], 3
0x180083e1a  jb      short loc_180083E52
0x180083e1c  mov     [rbp+4Fh+var_A0], rsi
0x180083e20  movzx   eax, word ptr [rdi+2C8h]
0x180083e27  mov     [rbp+4Fh+var_98], ax
0x180083e2b  mov     edx, 0A6h
0x180083e30  lea     r9, [rbp+4Fh+var_A0]
0x180083e34  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083e3b  mov     rcx, [rcx+60h]
0x180083e3f  call    WPP_SF__HEX_
0x180083e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e4b  lea     rax, WPP_GLOBAL_Control
0x180083e52  cmp     rcx, rax
0x180083e55  jz      short loc_180083E8B
0x180083e57  test    byte ptr [rcx+6Ch], 4
0x180083e5b  jz      short loc_180083E8B
0x180083e5d  cmp     byte ptr [rcx+69h], 3
0x180083e61  jb      short loc_180083E8B
0x180083e63  mov     [rbp+4Fh+var_A0], rbx
0x180083e67  movzx   eax, word ptr [rdi+2C8h]
0x180083e6e  mov     [rbp+4Fh+var_98], ax
0x180083e72  mov     edx, 0A7h
0x180083e77  lea     r9, [rbp+4Fh+var_A0]
0x180083e7b  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083e82  mov     rcx, [rcx+60h]
0x180083e86  call    WPP_SF__HEX_
0x180083e8b  test    [rbp+4Fh+var_B0], 400h
0x180083e92  jnz     short loc_180083E9F
0x180083e94  cmp     byte ptr [rdi+284h], 0
0x180083e9b  cmovnz  r15d, r14d
0x180083e9f  mov     [rbp+4Fh+arg_0], 0
0x180083ea3  mov     [rbp+4Fh+var_AC], 0
0x180083ea7  lea     rax, [rdi+2BAh]
0x180083eae  lea     rcx, [rbp+4Fh+var_AC]
0x180083eb2  mov     [rsp+58h], rcx; bool *
0x180083eb7  mov     [rsp+110h+var_C0], rax; bool *
0x180083ebc  lea     rax, [rbp+4Fh+arg_0]
0x180083ec0  mov     [rsp+110h+var_C8], rax; bool *
0x180083ec5  mov     al, [rdi+2A8h]
0x180083ecb  mov     [rsp+110h+var_D0], al; bool
0x180083ecf  mov     rax, [rdi+2E8h]
0x180083ed6  mov     [rsp+110h+var_D8], rax; unsigned __int8 *
0x180083edb  mov     [rsp+110h+var_E0], rbx; unsigned __int8 *
0x180083ee0  mov     [rsp+110h+var_E8], rsi; unsigned __int8 *
0x180083ee5  mov     [rsp+110h+pcbActual], r13; unsigned __int8 *
0x180083eea  mov     r9d, [rdi+2C8h]; unsigned int
0x180083ef1  mov     r8d, [rbp+4Fh+arg_10]; unsigned int
0x180083ef5  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int64
0x180083ef9  mov     rcx, [rdi+290h]; this
0x180083f00  call    ?UpdateAvailableBlockMasks@CRepubCacheSegment@@QEAAK_KKKPEAE111_NPEA_N33@Z; CRepubCacheSegment::UpdateAvailableBlockMasks(unsigned __int64,ulong,ulong,uchar *,uchar *,uchar *,uchar *,bool,bool *,bool *,bool *)
0x180083f05  mov     esi, eax
0x180083f07  test    eax, eax
0x180083f09  jz      short loc_180083F40
0x180083f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f12  lea     rdx, WPP_GLOBAL_Control
0x180083f19  cmp     rcx, rdx
0x180083f1c  jz      loc_1800846F8
0x180083f22  test    byte ptr [rcx+6Ch], 4
0x180083f26  jz      loc_1800846F8
0x180083f2c  cmp     [rcx+69h], r14b
0x180083f30  jb      loc_1800846F8
0x180083f36  mov     edx, 0A8h
0x180083f3b  jmp     loc_180083B54
0x180083f40  movzx   eax, [rbp+4Fh+var_AC]
0x180083f44  cmp     byte ptr [rdi+2B9h], 0
0x180083f4b  cmovnz  eax, r14d
0x180083f4f  mov     [rdi+2B9h], al
0x180083f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180083f5c  lea     rax, WPP_GLOBAL_Control
0x180083f63  cmp     rcx, rax
0x180083f66  jz      short loc_180083FAA
0x180083f68  test    byte ptr [rcx+6Ch], 4
0x180083f6c  jz      short loc_180083FAA
0x180083f6e  cmp     byte ptr [rcx+69h], 3
0x180083f72  jb      short loc_180083FAA
0x180083f74  mov     [rbp+4Fh+var_A0], r13
0x180083f78  movzx   eax, word ptr [rdi+2C8h]
0x180083f7f  mov     [rbp+4Fh+var_98], ax
0x180083f83  mov     edx, 0A9h
0x180083f88  lea     r9, [rbp+4Fh+var_A0]
0x180083f8c  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x180083f93  mov     rcx, [rcx+60h]
0x180083f97  call    WPP_SF__HEX_
0x180083f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180083fa3  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
