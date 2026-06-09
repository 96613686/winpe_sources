# CCacheStore::GetPartitionTableInfo(CWxCallerIdentity *,PartitionType,int,int,ushort const *,int,unsigned __int64 *,CWxString *,int *)

- ea: `0x1800259c0`
- end: `0x180026586`
- name: `?GetPartitionTableInfo@CCacheStore@@QEAAJPEAVCWxCallerIdentity@@W4PartitionType@@HHPEBGHPEA_KPEAVCWxString@@PEAH@Z`
- size: `3014`
- prototype: ``
- caller_count: `5`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800420f8`
- `0x1800aa494`
- `0x1800b1c7c`
- `0x18012b9b4`
- `0x1801adc6c`

## callees

- `0x1800201e8`
- `0x1800204f8`
- `0x180025514`
- `0x1800259c0`
- `0x180027ec0`
- `0x180046a1c`
- `0x18007ec9c`
- `0x18007ee10`
- `0x180083dc4`
- `0x180085898`
- `0x180086aa4`
- `0x180097e10`
- `0x1800acab8`
- `0x1800af554`
- `0x1800e28e0`
- `0x1800ee168`
- `0x1800fa844`
- `0x180127514`
- `0x180127544`
- `0x18014a7a0`
- `0x1801aad40`
- `0x1801bc3d0`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e1b60`
- `0x1801e241c`
- `0x1801e25fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025d1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025d1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025f8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025f8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025edb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025edb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025ea3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025ea3`
- `ESENT!JetSetCurrentIndex2W` at `0x180025f39`
- `ESENT!JetSetCurrentIndex2W` at `0x180025f39`
- `ESENT!JetRetrieveColumn` at `0x180025c96`
- `ESENT!JetRetrieveColumn` at `0x18002606c`
- `ESENT!JetRetrieveColumn` at `0x180025c96`
- `ESENT!JetRetrieveColumn` at `0x18002606c`
- `ESENT!JetCommitTransaction` at `0x180025d39`
- `ESENT!JetCommitTransaction` at `0x180025d39`
- `ESENT!JetUpdate` at `0x1800262b7`
- `ESENT!JetUpdate` at `0x18002642b`
- `ESENT!JetUpdate` at `0x1800264fe`
- `ESENT!JetUpdate` at `0x1800262b7`
- `ESENT!JetUpdate` at `0x18002642b`
- `ESENT!JetUpdate` at `0x1800264fe`
- `ESENT!JetPrepareUpdate` at `0x1800261e5`
- `ESENT!JetPrepareUpdate` at `0x1800263db`
- `ESENT!JetPrepareUpdate` at `0x1800264b1`
- `ESENT!JetPrepareUpdate` at `0x180026528`
- `ESENT!JetPrepareUpdate` at `0x1800261e5`
- `ESENT!JetPrepareUpdate` at `0x1800263db`
- `ESENT!JetPrepareUpdate` at `0x1800264b1`
- `ESENT!JetPrepareUpdate` at `0x180026528`
- `ESENT!JetRollback` at `0x180025f07`
- `ESENT!JetRollback` at `0x180025f07`
- `ESENT!JetBeginTransaction` at `0x180025bdd`
- `ESENT!JetBeginTransaction` at `0x180025bdd`

## pseudocode

```c
__int64 __fastcall CCacheStore::GetPartitionTableInfo(
        CCacheStore *a1,
        struct CWxCallerIdentity *a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        int a7,
        unsigned __int16 *a8,
        struct CWxString *a9,
        _DWORD *a10)
{
  _DWORD *v10; // rax
  unsigned __int16 *v11; // rsi
  CCacheStore *v13; // r9
  struct CWxString *v14; // rcx
  const unsigned __int16 *v15; // r13
  const WCHAR *v16; // rdi
  int SecureSubDirectory; // ebx
  int v18; // eax
  int v19; // edx
  int v20; // ecx
  int v21; // r8d
  CJetContext *v22; // rdi
  JET_ERR v23; // eax
  int v24; // eax
  JET_ERR v25; // eax
  struct CWxCallerIdentity *v26; // r12
  JET_ERR v27; // eax
  CCacheStore *v28; // rsi
  __int64 v29; // rsi
  int v31; // r15d
  JET_TABLEID v32; // rdx
  JET_SESID v33; // rcx
  JET_ERR v34; // eax
  __int64 v35; // rax
  JET_ERR v36; // eax
  JET_ERR v37; // eax
  JET_ERR v38; // eax
  unsigned __int16 v39; // dx
  int v40; // eax
  JET_ERR v41; // eax
  JET_ERR v42; // eax
  JET_ERR v43; // eax
  JET_ERR v44; // eax
  const unsigned __int16 *cbData; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *cbDataa; // [rsp+20h] [rbp-E0h]
  unsigned int *pcbActual; // [rsp+28h] [rbp-D8h]
  unsigned int *pcbActuala; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *grbit; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *grbita; // [rsp+30h] [rbp-D0h]
  JET_RETINFO *pretinfo; // [rsp+38h] [rbp-C8h]
  JET_RETINFO *pretinfoa; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v53; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v54; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v55; // [rsp+50h] [rbp-B0h]
  int v56; // [rsp+60h] [rbp-A0h] BYREF
  int v57; // [rsp+64h] [rbp-9Ch]
  CCacheStore *v58; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v59; // [rsp+70h] [rbp-90h] BYREF
  struct CWxCallerIdentity *v60; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v61[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v62[2]; // [rsp+90h] [rbp-70h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-58h]
  struct CWxString *v65; // [rsp+B0h] [rbp-50h]
  _DWORD *v66; // [rsp+B8h] [rbp-48h]
  int v67; // [rsp+C4h] [rbp-3Ch]
  unsigned __int16 v68[4]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v69; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v70; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E8h] [rbp-18h] BYREF
  CJetContext *v73; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 pvData; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v75; // [rsp+100h] [rbp+0h] BYREF
  __int64 v76; // [rsp+108h] [rbp+8h]
  unsigned int v77; // [rsp+110h] [rbp+10h] BYREF
  __int64 v78; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 v79[8]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v80; // [rsp+130h] [rbp+30h]

  v10 = a10;
  v11 = a6;
  v80 = 0;
  v13 = a1;
  v58 = a1;
  v14 = a9;
  v69 = a3;
  v15 = &Data;
  v70 = (unsigned __int16 *)&Data;
  v16 = &Data;
  v62[0] = (unsigned __int16 *)&Data;
  v75 = (unsigned __int16 *)&Data;
  v61[0] = (unsigned __int16 *)&Data;
  v60 = a2;
  v59 = a8;
  v65 = a9;
  v66 = a10;
  v57 = 0;
  pvData = 0;
  v77 = 0;
  v73 = 0;
  *(_DWORD *)v68 = 0;
  v72 = 0;
  v64 = 0;
  lpCriticalSection = 0;
  v78 = 0;
  *(_OWORD *)v79 = 0;
  v71 = 0;
  v62[1] = 0;
  v76 = 0;
  v61[1] = 0;
  v56 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_qqdllSlqq(
      (_DWORD)a9,
      (_DWORD)a2,
      a3,
      (_DWORD)v13,
      (__int64)a2,
      a3,
      a4,
      a5,
      (__int64)a6,
      a7,
      (__int64)a8,
      (__int64)a9);
    v10 = v66;
    v14 = v65;
    v13 = v58;
  }
  if ( a8 )
    *(_QWORD *)a8 = 0;
  if ( v10 )
    *v10 = 0;
  if ( !a8 )
  {
    SecureSubDirectory = -2147024809;
    v57 = 3800;
    goto LABEL_49;
  }
  if ( !a6 )
  {
    SecureSubDirectory = -2147024809;
    v57 = 3801;
    goto LABEL_49;
  }
  if ( a5 && !v14 )
  {
    SecureSubDirectory = -2147024809;
    v57 = 3802;
    goto LABEL_49;
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(*((_QWORD *)v13 + 56) + 24LL);
  if ( !*a6 || !a7 )
  {
LABEL_14:
    v18 = CJetContextList::AcquireContext(*((CJetContextList **)v13 + 55), &v73, 0);
    v22 = v73;
    SecureSubDirectory = v18;
    if ( v18 < 0 )
    {
      v57 = 3816;
      goto LABEL_77;
    }
    v67 = 0;
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_qdSD(v20, v19, v21, (_DWORD)v73, 1, (__int64)L"PartitionIndex", 0);
    if ( *((_DWORD *)v22 + 12) == 1 )
    {
      SecureSubDirectory = 0;
    }
    else
    {
      v32 = *((_QWORD *)v22 + 4);
      v33 = *((_QWORD *)v22 + 2);
      *((_DWORD *)v22 + 12) = -1;
      v34 = JetSetCurrentIndex2W(v33, v32, L"PartitionIndex", 0);
      SecureSubDirectory = HRESULTFromJET_ERR(v34, 1);
      if ( SecureSubDirectory >= 0 )
        *((_DWORD *)v22 + 12) = 1;
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_d(1036, 14, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)SecureSubDirectory);
    if ( SecureSubDirectory < 0 )
    {
      v57 = 3817;
      goto LABEL_77;
    }
    if ( !v69 )
      AutoCritSec::Lock((AutoCritSec *)&lpCriticalSection);
    v23 = JetBeginTransaction(*((_QWORD *)v22 + 2));
    SecureSubDirectory = HRESULTFromJET_ERR(v23, 1);
    if ( SecureSubDirectory < 0 )
      goto LABEL_77;
    v24 = CCacheStore::SeekToPartition(v22, v60, v69);
    SecureSubDirectory = v24;
    if ( v24 < 0 )
    {
      v57 = 3827;
      goto LABEL_76;
    }
    if ( v24 == 1 )
    {
      if ( !a7 )
      {
        SecureSubDirectory = -2147024894;
        v57 = 3833;
        goto LABEL_76;
      }
      if ( a5 )
      {
        SecureSubDirectory = CreateSecureSubDirectory(a6, v79, (unsigned __int16 *)1);
        if ( SecureSubDirectory < 0 )
        {
          v57 = 3844;
          goto LABEL_76;
        }
        SecureSubDirectory = CWxString::SetPath(
                               (CWxString *)&v70,
                               a6,
                               v79,
                               0,
                               cbData,
                               (const unsigned __int16 *)pcbActual,
                               grbit,
                               (const unsigned __int16 *)pretinfo,
                               v53,
                               v54,
                               v55);
        if ( SecureSubDirectory < 0 )
        {
          v57 = 3845;
          goto LABEL_76;
        }
        SecureSubDirectory = ValidateContainerDirectory(v70, v68);
        if ( SecureSubDirectory < 0 )
        {
          v57 = 3846;
          goto LABEL_76;
        }
        v11 = v70;
      }
      v26 = v60;
      *(_DWORD *)v68 = 0;
      SecureSubDirectory = CWxString::Set((CWxString *)v61, *((const unsigned __int16 **)v60 + 1));
      if ( SecureSubDirectory < 0 )
      {
        v57 = 3852;
        goto LABEL_76;
      }
      v37 = JetPrepareUpdate(*((_QWORD *)v22 + 2), *((_QWORD *)v22 + 4), 0);
      SecureSubDirectory = HRESULTFromJET_ERR(v37, 1);
      if ( SecureSubDirectory < 0 )
        goto LABEL_76;
      if ( *((_DWORD *)v60 + 1) == 1 && !a4 )
        v72 = 1;
      v36 = JetRetrieveColumn(
              *((_QWORD *)v22 + 2),
              *((_QWORD *)v22 + 4),
              **(_DWORD **)(*((_QWORD *)v22 + 5) + 8LL),
              &pvData,
              8u,
              &v77,
              1u,
              0);
      SecureSubDirectory = HRESULTFromJET_ERR(v36, 1);
      if ( SecureSubDirectory >= 0 )
      {
        SecureSubDirectory = CJetContext::SetStringColumn(v22, 1u, v61[0]);
        if ( SecureSubDirectory >= 0 )
        {
          SecureSubDirectory = CJetContext::SetBasicColumn(v22, 2u, &v69, 4u);
          if ( SecureSubDirectory >= 0 )
          {
            SecureSubDirectory = CJetContext::SetBasicColumn(v22, 3u, &v72, 4u);
            if ( SecureSubDirectory >= 0 )
            {
              SecureSubDirectory = CJetContext::SetStringColumn(v22, 4u, v11);
              if ( SecureSubDirectory >= 0 )
              {
                SecureSubDirectory = CJetContext::SetBasicColumn(v22, 5u, &v78, 8u);
                if ( SecureSubDirectory >= 0 )
                {
                  v38 = JetUpdate(*((_QWORD *)v22 + 2), *((_QWORD *)v22 + 4), 0, 0, 0);
                  SecureSubDirectory = HRESULTFromJET_ERR(v38, 1);
                  if ( SecureSubDirectory >= 0 )
                  {
LABEL_39:
                    v27 = JetCommitTransaction(*((_QWORD *)v22 + 2), 1u);
                    SecureSubDirectory = HRESULTFromJET_ERR(v27, 1);
                    if ( SecureSubDirectory >= 0 )
                    {
                      if ( v69 )
                      {
                        v28 = v58;
                      }
                      else
                      {
                        AutoCritSec::Unlock((AutoCritSec *)&lpCriticalSection);
                        v28 = v58;
                        if ( *(_DWORD *)v68 )
                        {
                          SecureSubDirectory = CCacheStore::PurgeAppCachePartition(v58, pvData, v26, 0);
                          if ( SecureSubDirectory < 0 )
                          {
                            v57 = 4037;
                            goto LABEL_46;
                          }
                        }
                      }
                      *(_QWORD *)v59 = pvData;
                      if ( a5 )
                        CWxString::Transfer((CWxString *)&v70, v65);
                      if ( v66 )
                        *v66 = *(_DWORD *)v68;
LABEL_46:
                      if ( v22 )
                      {
                        v29 = *((_QWORD *)v28 + 55);
                        CCacheStore::EndActivity(*(CCacheStore **)(v29 + 80));
                        *((_QWORD *)v22 + 1) = 0;
                        v31 = 0;
                        if ( v29 != -8 )
                        {
                          EnterCriticalSection((LPCRITICAL_SECTION)(v29 + 8));
                          v31 = 1;
                        }
                        --*(_DWORD *)(v29 + 60);
                        if ( (unsigned int)(*(_DWORD *)(v29 + 56) - *(_DWORD *)(v29 + 60)) <= *(_DWORD *)(v29 + 64) )
                        {
                          *((_QWORD *)v22 + 1) = *(_QWORD *)(v29 + 48);
                          *(_QWORD *)(v29 + 48) = v22;
                          if ( !v31 )
                          {
LABEL_73:
                            v16 = v61[0];
                            goto LABEL_49;
                          }
LABEL_71:
                          if ( v29 != -8 )
                            LeaveCriticalSection((LPCRITICAL_SECTION)(v29 + 8));
                          goto LABEL_73;
                        }
                        --*(_DWORD *)(v29 + 56);
                        CJetContext::Release(v22);
                        if ( v31 )
                          goto LABEL_71;
                      }
                      v16 = v61[0];
                      goto LABEL_49;
                    }
                    goto LABEL_76;
                  }
                }
                else
                {
                  v57 = 3904;
                }
              }
              else
              {
                v57 = 3900;
              }
            }
            else
            {
              v57 = 3897;
            }
          }
          else
          {
            v57 = 3893;
          }
        }
        else
        {
          v57 = 3889;
        }
      }
      goto LABEL_160;
    }
    v67 = 0;
    LODWORD(v73) = 0;
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 0, (__int64)&pvData);
    v25 = JetRetrieveColumn(
            *((_QWORD *)v22 + 2),
            *((_QWORD *)v22 + 4),
            **(_DWORD **)(*((_QWORD *)v22 + 5) + 8LL),
            &pvData,
            8u,
            (unsigned int *)&v73,
            0,
            0);
    SecureSubDirectory = HRESULTFromJET_ERR(v25, 1);
    if ( SecureSubDirectory >= 0 )
    {
      if ( (_DWORD)v73 == 8 )
      {
        SecureSubDirectory = 0;
      }
      else
      {
        SecureSubDirectory = -2147418113;
        v67 = 214;
      }
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)SecureSubDirectory);
    if ( SecureSubDirectory < 0 )
    {
      v57 = 3915;
      goto LABEL_76;
    }
    if ( !a5 )
    {
      SecureSubDirectory = CJetContext::GetStringColumn(v22, 4u, (struct CWxString *)&v75);
      if ( SecureSubDirectory < 0 )
      {
        v57 = 3993;
        goto LABEL_76;
      }
      if ( !(unsigned int)_o__wcsicmp(v75, a6) )
      {
LABEL_38:
        v26 = v60;
        goto LABEL_39;
      }
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_S(1036, 74, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, v75);
      if ( *(_DWORD *)v68 && (_DWORD)v76 )
      {
        SecureSubDirectory = DoesCanaryFileExist(v75, &v56);
        if ( SecureSubDirectory < 0 )
        {
          v57 = 4009;
          goto LABEL_76;
        }
        if ( v56 )
          *(_DWORD *)v68 = 0;
      }
      v43 = JetPrepareUpdate(*((_QWORD *)v22 + 2), *((_QWORD *)v22 + 4), 2u);
      SecureSubDirectory = HRESULTFromJET_ERR(v43, 1);
      if ( SecureSubDirectory < 0 )
        goto LABEL_76;
      SecureSubDirectory = CJetContext::SetStringColumn(v22, 4u, a6);
      if ( SecureSubDirectory >= 0 )
      {
        v44 = JetUpdate(*((_QWORD *)v22 + 2), *((_QWORD *)v22 + 4), 0, 0, 0);
        SecureSubDirectory = HRESULTFromJET_ERR(v44, 1);
        if ( SecureSubDirectory >= 0 )
          goto LABEL_38;
      }
      else
      {
        v57 = 4020;
      }
LABEL_160:
      JetPrepareUpdate(*((_QWORD *)v22 + 2), *((_QWORD *)v22 + 4), 3u);
      goto LABEL_76;
    }
    SecureSubDirectory = CJetContext::GetStringColumn(v22, 4u, (struct CWxString *)&v70);
    if ( SecureSubDirectory < 0 )
    {
      v57 = 3923;
      goto LABEL_76;
    }
    v35 = -1;
    do
      ++v35;
    while ( a6[v35] );
    if ( !(unsigned int)_o__wcsnicmp(v70, a6, (unsigned int)v35) )
    {
      if ( !a7 )
        goto LABEL_38;
      SecureSubDirectory = ValidateContainerDirectory(v70, v68);
      if ( SecureSubDirectory >= 0 )
        goto LABEL_38;
      v57 = 3988;
LABEL_76:
      JetRollback(*((_QWORD *)v22 + 2), 0);
LABEL_77:
      v28 = v58;
      goto LABEL_46;
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_S(1036, 73, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, v70);
    CWxString::UnTrailing((CWxString *)&v70, 0x5Cu);
    v40 = CWxString::ReverseFind((CWxString *)&v70, v39);
    if ( v40 == -1 )
    {
      SecureSubDirectory = CreateSecureSubDirectory(a6, v79, (unsigned __int16 *)1);
      if ( SecureSubDirectory < 0 )
      {
        v57 = 3955;
        goto LABEL_76;
      }
      SecureSubDirectory = CWxString::SetPath(
                             (CWxString *)v62,
                             a6,
                             v79,
                             0,
                             cbDataa,
                             (const unsigned __int16 *)pcbActuala,
                             grbita,
                             (const unsigned __int16 *)pretinfoa,
                             v53,
                             v54,
                             v55);
      if ( SecureSubDirectory < 0 )
      {
        v57 = 3957;
LABEL_140:
        v15 = v62[0];
        goto LABEL_76;
      }
    }
    else
    {
      SecureSubDirectory = CWxString::SetPath(
                             (CWxString *)v62,
                             a6,
                             &v70[v40 + 1],
                             0,
                             cbDataa,
                             (const unsigned __int16 *)pcbActuala,
                             grbita,
                             (const unsigned __int16 *)pretinfoa,
                             v53,
                             v54,
                             v55);
      if ( SecureSubDirectory < 0 )
      {
        v57 = 3965;
        goto LABEL_140;
      }
    }
    v15 = v62[0];
    SecureSubDirectory = ValidateContainerDirectory(v62[0], v68);
    if ( SecureSubDirectory < 0 )
    {
      v57 = 3972;
      goto LABEL_76;
    }
    v41 = JetPrepareUpdate(*((_QWORD *)v22 + 2), *((_QWORD *)v22 + 4), 2u);
    SecureSubDirectory = HRESULTFromJET_ERR(v41, 1);
    if ( SecureSubDirectory < 0 )
      goto LABEL_76;
    SecureSubDirectory = CJetContext::SetStringColumn(v22, 4u, v15);
    if ( SecureSubDirectory >= 0 )
    {
      v42 = JetUpdate(*((_QWORD *)v22 + 2), *((_QWORD *)v22 + 4), 0, 0, 0);
      SecureSubDirectory = HRESULTFromJET_ERR(v42, 1);
      if ( SecureSubDirectory >= 0 )
      {
        CWxString::Transfer((CWxString *)v62, (struct CWxString *)&v70);
        v15 = v62[0];
        goto LABEL_38;
      }
    }
    else
    {
      v57 = 3978;
    }
    goto LABEL_160;
  }
  SecureSubDirectory = ValidateContainerDirectory(a6, v68);
  if ( SecureSubDirectory >= 0 )
  {
    v13 = v58;
    goto LABEL_14;
  }
  v57 = 3813;
LABEL_49:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 75, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)SecureSubDirectory);
  v59 = (unsigned __int16 *)v16;
  if ( v16 != &Data && v16 )
    WxFreeHeapEx(&v59);
  v59 = v75;
  if ( v75 != &Data && v75 )
    WxFreeHeapEx(&v59);
  v75 = (unsigned __int16 *)&Data;
  v76 = 0;
  v59 = (unsigned __int16 *)v15;
  if ( v15 != &Data && v15 )
    WxFreeHeapEx(&v59);
  v59 = v70;
  if ( v70 != &Data && v70 )
    WxFreeHeapEx(&v59);
  v70 = (unsigned __int16 *)&Data;
  v71 = 0;
  if ( (_DWORD)v64 && lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)SecureSubDirectory;
}

```

## disassembly

```asm
0x1800259c0  mov     [rsp-8+arg_18], rbx
0x1800259c5  push    rbp
0x1800259c6  push    rsi
0x1800259c7  push    rdi
0x1800259c8  push    r12
0x1800259ca  push    r13
0x1800259cc  push    r14
0x1800259ce  push    r15
0x1800259d0  lea     rbp, [rsp-40h]
0x1800259d5  sub     rsp, 140h
0x1800259dc  mov     rax, cs:__security_cookie
0x1800259e3  xor     rax, rsp
0x1800259e6  mov     [rbp+70h+var_38], rax
0x1800259ea  mov     rbx, [rbp+70h+arg_38]
0x1800259f1  xor     r11d, r11d
0x1800259f4  mov     rax, [rbp+70h+arg_48]
0x1800259fb  xor     r10d, r10d
0x1800259fe  mov     rsi, [rbp+70h+arg_28]
0x180025a05  mov     r14d, r9d
0x180025a08  mov     [rbp+70h+var_40], r10w
0x180025a0d  mov     r9, rcx
0x180025a10  lea     r10, Data
0x180025a17  mov     [rsp+170h+var_108], rcx
0x180025a1c  mov     rcx, [rbp+70h+arg_40]
0x180025a23  xorps   xmm0, xmm0
0x180025a26  mov     [rbp+70h+var_A0], r8d
0x180025a2a  mov     r13, r10
0x180025a2d  mov     [rbp+70h+var_98], r10
0x180025a31  mov     rdi, r10
0x180025a34  mov     [rbp+70h+var_E0], r10
0x180025a38  mov     [rbp+70h+var_70], r10
0x180025a3c  mov     [rbp+70h+var_F0], r10
0x180025a40  mov     [rsp+170h+var_F8], rdx
0x180025a45  mov     [rsp+170h+var_100], rbx
0x180025a4a  mov     [rbp+70h+var_C0], rcx
0x180025a4e  mov     [rbp+70h+var_B8], rax
0x180025a52  mov     [rsp+170h+var_10C], r11d
0x180025a57  mov     [rbp+70h+pvData], r11
0x180025a5b  mov     [rbp+70h+var_60], r11d
0x180025a5f  mov     [rbp+70h+var_80], r11
0x180025a63  mov     dword ptr [rbp+70h+var_A8], r11d
0x180025a67  mov     [rbp+70h+var_88], r11d
0x180025a6b  mov     [rbp+70h+var_C8], r11
0x180025a6f  mov     [rbp+70h+lpCriticalSection], r11
0x180025a73  mov     [rbp+70h+var_58], r11
0x180025a77  movups  xmmword ptr [rbp+70h+var_50], xmm0
0x180025a7b  mov     [rbp+70h+var_90], r11
0x180025a7f  mov     [rbp+70h+var_D8], r11
0x180025a83  mov     [rbp+70h+var_68], r11
0x180025a87  mov     [rbp+70h+var_E8], r11
0x180025a8b  mov     [rsp+170h+var_110], r11d
0x180025a90  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180025a97  mov     r12d, dword ptr [rbp+70h+arg_30]
0x180025a9e  mov     r15d, dword ptr [rbp+70h+arg_20]
0x180025aa5  jz      short loc_180025AE4
0x180025aa7  mov     [rsp+170h+var_118], rcx
0x180025aac  mov     [rsp+170h+var_120], rbx; unsigned __int16 *
0x180025ab1  mov     dword ptr [rsp+170h+var_128], r12d; unsigned __int16 *
0x180025ab6  mov     [rsp+170h+var_130], rsi; unsigned __int16 *
0x180025abb  mov     dword ptr [rsp+170h+pretinfo], r15d; unsigned __int16 *
0x180025ac0  mov     dword ptr [rsp+170h+grbit], r14d
0x180025ac5  mov     dword ptr [rsp+170h+pcbActual], r8d
0x180025aca  mov     qword ptr [rsp+170h+cbData], rdx
0x180025acf  call    WPP_SF_qqdllSlqq
0x180025ad4  mov     rax, [rbp+70h+var_B8]
0x180025ad8  xor     r11d, r11d
0x180025adb  mov     rcx, [rbp+70h+var_C0]
0x180025adf  mov     r9, [rsp+170h+var_108]
0x180025ae4  test    rbx, rbx
0x180025ae7  jz      short loc_180025AEC
0x180025ae9  mov     [rbx], r11
0x180025aec  test    rax, rax
0x180025aef  jz      short loc_180025AF4
0x180025af1  mov     [rax], r11d
0x180025af4  test    rbx, rbx
0x180025af7  jz      loc_1800260DB
0x180025afd  test    rsi, rsi
0x180025b00  jz      loc_1800260ED
0x180025b06  test    r15d, r15d
0x180025b09  jnz     loc_1800260FF
0x180025b0f  mov     rax, [r9+1C0h]
0x180025b16  add     rax, 18h
0x180025b1a  mov     [rbp+70h+lpCriticalSection], rax
0x180025b1e  cmp     [rsi], r11w
0x180025b22  jz      short loc_180025B44
0x180025b24  test    r12d, r12d
0x180025b27  jz      short loc_180025B44
0x180025b29  lea     rdx, [rbp+70h+var_A8]; unsigned __int16 *
0x180025b2d  mov     rcx, rsi; unsigned __int16 *
0x180025b30  call    ?ValidateContainerDirectory@@YAJPEBGPEAH@Z; ValidateContainerDirectory(ushort const *,int *)
0x180025b35  mov     ebx, eax
0x180025b37  test    eax, eax
0x180025b39  js      loc_18002611A
0x180025b3f  mov     r9, [rsp+170h+var_108]
0x180025b44  mov     rcx, [r9+1B8h]; this
0x180025b4b  lea     rdx, [rbp+70h+var_80]; struct CJetContext **
0x180025b4f  xor     r8d, r8d; int *
0x180025b52  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x180025b57  mov     rdi, [rbp+70h+var_80]
0x180025b5b  mov     ebx, eax
0x180025b5d  test    eax, eax
0x180025b5f  js      loc_180025F1A
0x180025b65  mov     [rbp+70h+var_AC], 0
0x180025b6c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180025b73  lea     rbx, szIndexName; "PartitionIndex"
0x180025b7a  jz      short loc_180025B99
0x180025b7c  mov     dword ptr [rsp+170h+grbit], 0; unsigned __int16 *
0x180025b84  mov     r9, rdi
0x180025b87  mov     [rsp+170h+pcbActual], rbx; unsigned __int16 *
0x180025b8c  mov     [rsp+170h+cbData], 1; unsigned __int16 *
0x180025b94  call    WPP_SF_qdSD
0x180025b99  cmp     dword ptr [rdi+30h], 1
0x180025b9d  jnz     loc_180025F24
0x180025ba3  xor     ebx, ebx
0x180025ba5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180025bac  jz      short loc_180025BC7
0x180025bae  mov     edx, 0Eh
0x180025bb3  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180025bba  mov     ecx, 40Ch
0x180025bbf  mov     r9d, ebx
0x180025bc2  call    WPP_SF_d
0x180025bc7  test    ebx, ebx
0x180025bc9  js      loc_180026127
0x180025bcf  cmp     [rbp+70h+var_A0], 0
0x180025bd3  jz      loc_180026134
0x180025bd9  mov     rcx, [rdi+10h]; sesid
0x180025bdd  call    cs:__imp_JetBeginTransaction
0x180025be3  mov     ecx, eax; int
0x180025be5  mov     edx, 1; int
0x180025bea  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180025bef  mov     ebx, eax
0x180025bf1  test    eax, eax
0x180025bf3  js      loc_180025F0D
0x180025bf9  mov     r8d, [rbp+70h+var_A0]
0x180025bfd  mov     rcx, rdi
0x180025c00  mov     rdx, [rsp+170h+var_F8]
0x180025c05  call    ?SeekToPartition@CCacheStore@@SAJPEAVCJetContext@@PEAVCWxCallerIdentity@@W4PartitionType@@@Z; CCacheStore::SeekToPartition(CJetContext *,CWxCallerIdentity *,PartitionType)
0x180025c0a  mov     ebx, eax
0x180025c0c  test    eax, eax
0x180025c0e  js      loc_180026142
0x180025c14  cmp     eax, 1
0x180025c17  jz      loc_180025FC7
0x180025c1d  mov     [rbp+70h+var_AC], 0
0x180025c24  mov     dword ptr [rbp+70h+var_80], 0
0x180025c2b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180025c32  mov     r14d, 8
0x180025c38  jz      short loc_180025C60
0x180025c3a  lea     rax, [rbp+70h+pvData]
0x180025c3e  mov     dword ptr [rsp+170h+pcbActual], r14d
0x180025c43  lea     edx, [r14+9]
0x180025c47  mov     qword ptr [rsp+170h+cbData], rax
0x180025c4c  mov     ecx, 40Ch
0x180025c51  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180025c58  xor     r9d, r9d
0x180025c5b  call    WPP_SF_dqd
0x180025c60  mov     rax, [rdi+28h]
0x180025c64  lea     r9, [rbp+70h+pvData]; pvData
0x180025c68  mov     rdx, [rdi+20h]; tableid
0x180025c6c  mov     rcx, [rdi+10h]; sesid
0x180025c70  mov     [rsp+170h+pretinfo], 0; unsigned __int16 *
0x180025c79  mov     r8, [rax+8]
0x180025c7d  lea     rax, [rbp+70h+var_80]
0x180025c81  mov     dword ptr [rsp+170h+grbit], 0; unsigned __int16 *
0x180025c89  mov     [rsp+170h+pcbActual], rax; unsigned __int16 *
0x180025c8e  mov     [rsp+170h+cbData], r14d; unsigned __int16 *
0x180025c93  mov     r8d, [r8]; columnid
0x180025c96  call    cs:__imp_JetRetrieveColumn
0x180025c9c  mov     ecx, eax; int
0x180025c9e  mov     edx, 1; int
0x180025ca3  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180025ca8  mov     ebx, eax
0x180025caa  test    eax, eax
0x180025cac  js      loc_180025EF9
0x180025cb2  cmp     dword ptr [rbp+70h+var_80], r14d
0x180025cb6  jnz     loc_180025EED
0x180025cbc  xor     r14d, r14d
0x180025cbf  mov     ebx, r14d
0x180025cc2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180025cc9  jz      short loc_180025CE4
0x180025ccb  mov     edx, 12h
0x180025cd0  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180025cd7  mov     ecx, 40Ch
0x180025cdc  mov     r9d, ebx
0x180025cdf  call    WPP_SF_d
0x180025ce4  test    ebx, ebx
0x180025ce6  js      loc_1800262D8
0x180025cec  test    r15d, r15d
0x180025cef  mov     rcx, rdi; this
0x180025cf2  mov     r15d, 4
0x180025cf8  mov     edx, r15d; unsigned int
0x180025cfb  jnz     loc_180025F61
0x180025d01  lea     r8, [rbp+70h+var_70]; struct CWxString *
0x180025d05  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x180025d0a  mov     ebx, eax
0x180025d0c  test    eax, eax
0x180025d0e  js      loc_18002645D
0x180025d14  mov     rcx, [rbp+70h+var_70]
0x180025d18  mov     rdx, rsi
0x180025d1b  call    cs:__imp__o__wcsicmp
0x180025d21  test    eax, eax
0x180025d23  jnz     loc_18002646A
0x180025d29  mov     r12, [rsp+170h+var_F8]
0x180025d2e  mov     rcx, [rdi+10h]; sesid
0x180025d32  mov     ebx, 1
0x180025d37  mov     edx, ebx; grbit
0x180025d39  call    cs:__imp_JetCommitTransaction
0x180025d3f  mov     ecx, eax; int
0x180025d41  mov     edx, ebx; int
0x180025d43  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180025d48  mov     ebx, eax
0x180025d4a  test    eax, eax
0x180025d4c  js      loc_180025F01
0x180025d52  cmp     [rbp+70h+var_A0], r14d
0x180025d56  jz      loc_180026533
0x180025d5c  mov     rsi, [rsp+170h+var_108]
0x180025d61  mov     rcx, [rsp+170h+var_100]
0x180025d66  mov     rax, [rbp+70h+pvData]
0x180025d6a  mov     [rcx], rax
0x180025d6d  cmp     dword ptr [rbp+70h+arg_20], r14d
0x180025d74  jnz     loc_180026574
0x180025d7a  mov     rcx, [rbp+70h+var_B8]
0x180025d7e  test    rcx, rcx
0x180025d81  jz      short loc_180025D88
0x180025d83  mov     eax, dword ptr [rbp+70h+var_A8]
0x180025d86  mov     [rcx], eax
0x180025d88  test    rdi, rdi
0x180025d8b  jz      short loc_180025DA6
0x180025d8d  mov     rsi, [rsi+1B8h]
0x180025d94  mov     rcx, [rsi+50h]; this
0x180025d98  call    ?EndActivity@CCacheStore@@QEAAXXZ; CCacheStore::EndActivity(void)
0x180025d9d  test    rdi, rdi
0x180025da0  jnz     loc_180025E8D
0x180025da6  mov     rdi, [rbp+70h+var_F0]
0x180025daa  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180025db1  jz      short loc_180025DCC
0x180025db3  mov     edx, 4Bh ; 'K'
0x180025db8  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x180025dbf  mov     ecx, 40Ch
0x180025dc4  mov     r9d, ebx
0x180025dc7  call    WPP_SF_d
0x180025dcc  lea     rsi, Data
0x180025dd3  mov     [rsp+170h+var_100], rdi
0x180025dd8  cmp     rdi, rsi
0x180025ddb  jz      short loc_180025DEC
0x180025ddd  test    rdi, rdi
0x180025de0  jz      short loc_180025DEC
0x180025de2  lea     rcx, [rsp+170h+var_100]
0x180025de7  call    WxFreeHeapEx
0x180025dec  mov     rax, [rbp+70h+var_70]
0x180025df0  mov     [rsp+170h+var_100], rax
0x180025df5  cmp     rax, rsi
0x180025df8  jz      short loc_180025E09
0x180025dfa  test    rax, rax
0x180025dfd  jz      short loc_180025E09
0x180025dff  lea     rcx, [rsp+170h+var_100]
0x180025e04  call    WxFreeHeapEx
0x180025e09  mov     [rbp+70h+var_70], rsi
0x180025e0d  mov     [rbp+70h+var_68], r14
0x180025e11  mov     [rsp+170h+var_100], r13
0x180025e16  cmp     r13, rsi
0x180025e19  jz      short loc_180025E2A
0x180025e1b  test    r13, r13
0x180025e1e  jz      short loc_180025E2A
0x180025e20  lea     rcx, [rsp+170h+var_100]
0x180025e25  call    WxFreeHeapEx
0x180025e2a  mov     rax, [rbp+70h+var_98]
0x180025e2e  mov     [rsp+170h+var_100], rax
0x180025e33  cmp     rax, rsi
0x180025e36  jz      short loc_180025E47
0x180025e38  test    rax, rax
0x180025e3b  jz      short loc_180025E47
0x180025e3d  lea     rcx, [rsp+170h+var_100]
0x180025e42  call    WxFreeHeapEx
0x180025e47  mov     [rbp+70h+var_98], rsi
0x180025e4b  mov     [rbp+70h+var_90], r14
0x180025e4f  cmp     dword ptr [rbp+70h+var_C8], r14d
0x180025e53  jz      short loc_180025E64
0x180025e55  mov     rcx, [rbp+70h+lpCriticalSection]; lpCriticalSection
0x180025e59  test    rcx, rcx
0x180025e5c  jz      short loc_180025E64
0x180025e5e  call    cs:__imp_LeaveCriticalSection
0x180025e64  mov     eax, ebx
0x180025e66  mov     rcx, [rbp+70h+var_38]
0x180025e6a  xor     rcx, rsp; StackCookie
0x180025e6d  call    __security_check_cookie
0x180025e72  mov     rbx, [rsp+170h+arg_18]
0x180025e7a  add     rsp, 140h
0x180025e81  pop     r15
0x180025e83  pop     r14
0x180025e85  pop     r13
0x180025e87  pop     r12
0x180025e89  pop     rdi
0x180025e8a  pop     rsi
0x180025e8b  pop     rbp
0x180025e8c  retn
0x180025e8d  xor     r12d, r12d
0x180025e90  lea     r14, [rsi+8]
0x180025e94  mov     [rdi+8], r12
0x180025e98  mov     r15d, r12d
0x180025e9b  test    r14, r14
  ... truncated ...
```
