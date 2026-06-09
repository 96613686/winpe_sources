# TieringHeatSession::AddOrUpdateHeatRecord(TE_FILE_ID_128 const *,__int64,ulong,bool)

- ea: `0x140026e90`
- end: `0x140027900`
- name: `?AddOrUpdateHeatRecord@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JK_N@Z`
- size: `2672`
- prototype: `__int64 __fastcall(TieringHeatSession *this, const struct TE_FILE_ID_128 *, __int64, unsigned int, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140010d1c`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140021018`
- `0x1400210c8`
- `0x1400261c8`
- `0x14002670c`
- `0x140026e90`
- `0x14002866c`
- `0x140029dec`
- `0x14002bd3c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14002734e`
- `ntdll!RtlCompareMemory` at `0x14002734e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140027881`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140027881`
- `ESENT!JetPrepareUpdate` at `0x1400271a8`
- `ESENT!JetPrepareUpdate` at `0x1400271c5`
- `ESENT!JetPrepareUpdate` at `0x1400271d9`
- `ESENT!JetPrepareUpdate` at `0x14002759d`
- `ESENT!JetPrepareUpdate` at `0x1400275b3`
- `ESENT!JetPrepareUpdate` at `0x1400275d0`
- `ESENT!JetPrepareUpdate` at `0x1400275e1`
- `ESENT!JetPrepareUpdate` at `0x140027862`
- `ESENT!JetPrepareUpdate` at `0x1400271a8`
- `ESENT!JetPrepareUpdate` at `0x1400271c5`
- `ESENT!JetPrepareUpdate` at `0x1400271d9`
- `ESENT!JetPrepareUpdate` at `0x14002759d`
- `ESENT!JetPrepareUpdate` at `0x1400275b3`
- `ESENT!JetPrepareUpdate` at `0x1400275d0`
- `ESENT!JetPrepareUpdate` at `0x1400275e1`
- `ESENT!JetPrepareUpdate` at `0x140027862`
- `ESENT!JetUpdate` at `0x1400277b2`
- `ESENT!JetUpdate` at `0x1400277b2`
- `ESENT!JetMakeKey` at `0x140026f74`
- `ESENT!JetMakeKey` at `0x140027040`
- `ESENT!JetMakeKey` at `0x140026f74`
- `ESENT!JetMakeKey` at `0x140027040`
- `ESENT!JetSeek` at `0x1400270ce`
- `ESENT!JetSeek` at `0x1400270ce`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::AddOrUpdateHeatRecord(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *a2,
        __int64 a3,
        unsigned int a4,
        bool a5)
{
  bool v7; // zf
  signed int v9; // ebx
  JET_ERR v10; // edi
  _QWORD *v11; // r10
  JET_ERR Key; // eax
  int v13; // eax
  int v14; // edx
  JET_ERR v15; // eax
  int v16; // eax
  JET_ERR v17; // eax
  int v18; // r8d
  int v19; // eax
  int v20; // eax
  JET_ERR CurrentHeatRecord; // eax
  int v22; // eax
  _QWORD *v23; // rcx
  int v24; // edx
  unsigned __int8 v25; // al
  JET_ERR v26; // eax
  int v27; // eax
  int v28; // eax
  unsigned __int16 v29; // r8
  unsigned __int16 *v30; // rdi
  __int64 i; // rcx
  __int64 v32; // rax
  JET_ERR v33; // eax
  int v34; // eax
  JET_ERR v35; // eax
  int v36; // eax
  char v37; // [rsp+60h] [rbp-31h] BYREF
  char v38; // [rsp+61h] [rbp-30h] BYREF
  char v39[2]; // [rsp+62h] [rbp-2Fh] BYREF
  unsigned __int16 v40; // [rsp+64h] [rbp-2Dh] BYREF
  unsigned int v41; // [rsp+68h] [rbp-29h]
  __int64 pvData; // [rsp+70h] [rbp-21h] BYREF
  int v43; // [rsp+78h] [rbp-19h] BYREF
  __int64 v44; // [rsp+80h] [rbp-11h] BYREF
  __int128 Source1; // [rsp+88h] [rbp-9h] BYREF
  unsigned __int16 v46[4]; // [rsp+98h] [rbp+7h] BYREF
  int v47; // [rsp+A0h] [rbp+Fh]
  __int16 v48; // [rsp+A4h] [rbp+13h]

  v41 = a4;
  *(_QWORD *)v46 = 0;
  v47 = 0;
  v48 = 0;
  v7 = *(_QWORD *)a2 == *(_QWORD *)&NullGuid.Data1;
  pvData = a3;
  if ( v7 && *((_QWORD *)a2 + 1) == *(_QWORD *)NullGuid.Data4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, 2156068868LL);
    }
    return 2156068868LL;
  }
  else
  {
    v9 = 0;
    v10 = -1102;
LABEL_9:
    v11 = WPP_GLOBAL_Control;
    while ( v10 == -1102 || v10 == -1605 )
    {
      Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), a2, 0x10u, 1u);
      v9 = 0;
      v10 = Key;
      if ( Key )
      {
        if ( Key == -529 || Key == -1092 || Key == -1808 )
        {
          v9 = ATL::AtlHresultFromWin32(0x70u);
        }
        else if ( Key == -1011 )
        {
          v9 = -2147024882;
        }
        else
        {
          v13 = -Key;
          if ( v13 < 0 )
            LOWORD(v13) = v10;
          v9 = v10 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 19;
LABEL_26:
          WPP_SF_iiSd(
            v11[2],
            v14,
            (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v10);
          goto LABEL_9;
        }
      }
      else
      {
        v15 = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), &pvData, 8u, 0);
        v10 = v15;
        if ( v15 )
        {
          if ( v15 == -529 || v15 == -1092 || v15 == -1808 )
          {
            v9 = ATL::AtlHresultFromWin32(0x70u);
          }
          else if ( v15 == -1011 )
          {
            v9 = -2147024882;
          }
          else
          {
            v16 = -v15;
            if ( v16 < 0 )
              LOWORD(v16) = v10;
            v9 = v10 & 0x8E5E0000 | (unsigned __int16)v16 | 0xE5E0000;
          }
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 20;
            goto LABEL_26;
          }
        }
        else
        {
          v17 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1u);
          v10 = v17;
          if ( v17 == -1601 || v17 == 1039 )
          {
            v10 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
            if ( v10 == -1607 )
            {
              JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
              v10 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
            }
            switch ( v10 )
            {
              case 0:
                v29 = v41;
                if ( v41 > 0x2D0 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_iiiDS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      22,
                      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                      *((_QWORD *)a2 + 1),
                      *(_QWORD *)a2,
                      pvData,
                      v41,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
                  }
                  v29 = 720;
                  v41 = 720;
                }
                v30 = &v46[1];
                for ( i = 6; i; --i )
                  *v30++ = -1;
                v32 = *((_QWORD *)this + 5);
                v46[0] = v29;
                v33 = TieringHeatSession::SetCurrentHeatRecord(
                        this,
                        a2,
                        &pvData,
                        0,
                        0,
                        (unsigned __int8 *)(*(_QWORD *)v32 + 328LL),
                        0,
                        v46);
                v10 = v33;
                switch ( v33 )
                {
                  case 0:
                    goto LABEL_154;
                  case -529:
                  case -1092:
                  case -1808:
                    v9 = ATL::AtlHresultFromWin32(0x70u);
                    break;
                  case -1011:
                    v9 = -2147024882;
                    break;
                  default:
                    v34 = -v33;
                    if ( v34 < 0 )
                      LOWORD(v34) = v10;
                    v9 = v10 & 0x8E5E0000 | (unsigned __int16)v34 | 0xE5E0000;
                    break;
                }
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v24 = 23;
LABEL_113:
                  WPP_SF_iiSd(
                    v23[2],
                    v24,
                    (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                    *((_QWORD *)a2 + 1),
                    *(_QWORD *)a2,
                    *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                    v10);
                }
LABEL_114:
                JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
                goto LABEL_9;
              case -529:
              case -1092:
              case -1808:
                v9 = ATL::AtlHresultFromWin32(0x70u);
                break;
              case -1011:
                v9 = -2147024882;
                break;
              default:
                v28 = -v10;
                if ( v10 > 0 )
                  LOWORD(v28) = v10;
                v9 = v10 & 0x8E5E0000 | (unsigned __int16)v28 | 0xE5E0000;
                break;
            }
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = 21;
              goto LABEL_26;
            }
          }
          else if ( v17 )
          {
            if ( v17 == -529 || v17 == -1092 || v17 == -1808 )
            {
              v9 = ATL::AtlHresultFromWin32(0x70u);
            }
            else if ( v17 == -1011 )
            {
              v9 = -2147024882;
            }
            else
            {
              v19 = -v17;
              if ( v19 < 0 )
                LOWORD(v19) = v10;
              v9 = v10 & 0x8E5E0000 | (unsigned __int16)v19 | 0xE5E0000;
            }
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiiSL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                v18,
                *((_QWORD *)a2 + 1),
                *(_QWORD *)a2,
                pvData,
                *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                v10);
              goto LABEL_9;
            }
          }
          else
          {
            v10 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
            if ( v10 == -1607 )
            {
              JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
              v10 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
            }
            switch ( v10 )
            {
              case 0:
                v44 = 0;
                v39[0] = 0;
                v40 = 0;
                v38 = 0;
                v37 = 0;
                Source1 = 0;
                CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                                      this,
                                      1,
                                      (struct TE_FILE_ID_128 *)&Source1,
                                      &v44,
                                      (unsigned __int8 *)((unsigned __int64)&v38 & -(__int64)a5),
                                      (unsigned __int8 *)&v37,
                                      (unsigned __int8 *)v39,
                                      &v40,
                                      v46);
                v10 = CurrentHeatRecord;
                if ( CurrentHeatRecord )
                {
                  if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
                  {
                    v9 = ATL::AtlHresultFromWin32(0x70u);
                  }
                  else if ( CurrentHeatRecord == -1011 )
                  {
                    v9 = -2147024882;
                  }
                  else
                  {
                    v22 = -CurrentHeatRecord;
                    if ( v22 < 0 )
                      LOWORD(v22) = v10;
                    v9 = v10 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
                  }
                  v23 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v24 = 26;
                    goto LABEL_113;
                  }
                  goto LABEL_114;
                }
                if ( RtlCompareMemory(&Source1, a2, 0x10u) != 16 )
                {
                  v9 = -2147220986;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_iiiiSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      27,
                      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                      *((_QWORD *)a2 + 1),
                      *(_QWORD *)a2,
                      SBYTE8(Source1),
                      Source1,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                      0);
                  }
                  goto LABEL_114;
                }
                if ( v44 != pvData )
                {
                  v9 = -2147220986;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_iiiiSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      28,
                      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                      *((_QWORD *)a2 + 1),
                      *(_QWORD *)a2,
                      pvData,
                      v44,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                      6);
                  }
                  goto LABEL_114;
                }
                v25 = v37;
                v43 = 0;
                if ( a5 )
                {
                  v38 &= 0xFu;
                  v25 = v37 & 0xDF;
                  v37 &= ~0x20u;
                }
                TieringHeatSession::AddCurrentCountAndAgeHistory(
                  this,
                  a2,
                  pvData,
                  v41,
                  v39[0],
                  v40,
                  v25,
                  v46,
                  &v43,
                  0,
                  0);
                v26 = TieringHeatSession::SetCurrentHeatRecord(
                        this,
                        0,
                        0,
                        (unsigned __int8 *)((unsigned __int64)&v38 & -(__int64)a5),
                        (unsigned __int8 *)((unsigned __int64)&v37 & -(__int64)a5),
                        (unsigned __int8 *)(**((_QWORD **)this + 5) + 328LL),
                        0,
                        v46);
                v9 = 0;
                v10 = v26;
                if ( v26 )
                {
                  if ( v26 == -529 || v26 == -1092 || v26 == -1808 )
                  {
                    v9 = ATL::AtlHresultFromWin32(0x70u);
                  }
                  else if ( v26 == -1011 )
                  {
                    v9 = -2147024882;
                  }
                  else
                  {
                    v27 = -v26;
                    if ( v27 < 0 )
                      LOWORD(v27) = v10;
                    v9 = v10 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
                  }
                  v23 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v24 = 29;
                    goto LABEL_113;
                  }
                  goto LABEL_114;
                }
LABEL_154:
                v35 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
                v10 = v35;
                if ( v35 )
                {
                  if ( v35 == -529 || v35 == -1092 || v35 == -1808 )
                  {
                    v9 = ATL::AtlHresultFromWin32(0x70u);
                  }
                  else if ( v35 == -1011 )
                  {
                    v9 = -2147024882;
                  }
                  else
                  {
                    v36 = -v35;
                    if ( v36 < 0 )
                      LOWORD(v36) = v10;
                    v9 = v10 & 0x8E5E0000 | (unsigned __int16)v36 | 0xE5E0000;
                  }
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_iiSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      30,
                      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                      *((_QWORD *)a2 + 1),
                      *(_QWORD *)a2,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                      v10);
                  }
                  JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
                  if ( v10 == -1102 || v10 == -1605 )
                    Sleep(0x64u);
                }
                goto LABEL_9;
              case -529:
              case -1092:
              case -1808:
                v9 = ATL::AtlHresultFromWin32(0x70u);
                break;
              case -1011:
                v9 = -2147024882;
                break;
              default:
                v20 = -v10;
                if ( v10 > 0 )
                  LOWORD(v20) = v10;
                v9 = v10 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
                break;
            }
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = 25;
              goto LABEL_26;
            }
          }
        }
      }
    }
    if ( v9 >= 0 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      WPP_SF_iiiDS(
        v11[2],
        31,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        pvData,
        v41,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x140026e90  push    rbp
0x140026e92  push    rbx
0x140026e93  push    rsi
0x140026e94  push    rdi
0x140026e95  push    r12
0x140026e97  push    r14
0x140026e99  push    r15
0x140026e9b  lea     rbp, [rsp-1Fh]
0x140026ea0  sub     rsp, 0B0h
0x140026ea7  mov     rax, cs:__security_cookie
0x140026eae  xor     rax, rsp
0x140026eb1  mov     [rbp+4Fh+var_38], rax
0x140026eb5  xor     eax, eax
0x140026eb7  mov     [rbp+4Fh+var_78], r9d
0x140026ebb  mov     qword ptr [rbp+4Fh+var_48], rax
0x140026ebf  mov     r14, rdx
0x140026ec2  mov     [rbp+4Fh+var_40], eax
0x140026ec5  mov     rsi, rcx
0x140026ec8  mov     [rbp+4Fh+var_3C], ax
0x140026ecc  mov     rax, [rdx]
0x140026ecf  cmp     rax, qword ptr cs:?NullGuid@@3U_GUID@@A.Data1; _GUID NullGuid ...
0x140026ed6  mov     [rbp+4Fh+pvData], r8
0x140026eda  jnz     short loc_140026F31
0x140026edc  mov     rax, [rdx+8]
0x140026ee0  cmp     rax, qword ptr cs:?NullGuid@@3U_GUID@@A.Data4; _GUID NullGuid ...
0x140026ee7  jnz     short loc_140026F31
0x140026ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ef0  lea     r12, WPP_GLOBAL_Control
0x140026ef7  mov     edi, 80830004h
0x140026efc  cmp     rcx, r12
0x140026eff  jz      short loc_140026F2A
0x140026f01  mov     r15d, 1
0x140026f07  test    [rcx+1Ch], r15b
0x140026f0b  jz      short loc_140026F2A
0x140026f0d  cmp     byte ptr [rcx+19h], 2
0x140026f11  jb      short loc_140026F2A
0x140026f13  mov     rcx, [rcx+10h]
0x140026f17  lea     edx, [r15+11h]
0x140026f1b  mov     r9d, edi
0x140026f1e  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140026f25  call    WPP_SF_d
0x140026f2a  mov     eax, edi
0x140026f2c  jmp     loc_1400278E2
0x140026f31  xor     ebx, ebx
0x140026f33  lea     r12, WPP_GLOBAL_Control
0x140026f3a  mov     edi, 0FFFFFBB2h
0x140026f3f  lea     r15d, [rbx+1]
0x140026f43  mov     r10, cs:WPP_GLOBAL_Control
0x140026f4a  cmp     edi, 0FFFFFBB2h
0x140026f50  jz      short loc_140026F5E
0x140026f52  cmp     edi, 0FFFFF9BBh
0x140026f58  jnz     loc_14002788C
0x140026f5e  mov     rdx, [rsi+18h]; tableid
0x140026f62  mov     r9d, 10h; cbData
0x140026f68  mov     rcx, [rsi+8]; sesid
0x140026f6c  mov     r8, r14; pvData
0x140026f6f  mov     [rsp+0E0h+grbit], r15d; grbit
0x140026f74  call    cs:__imp_JetMakeKey
0x140026f7a  xor     ebx, ebx
0x140026f7c  mov     edi, eax
0x140026f7e  test    eax, eax
0x140026f80  jz      loc_14002702A
0x140026f86  cmp     eax, 0FFFFFDEFh
0x140026f8b  jz      short loc_140026FC2
0x140026f8d  cmp     eax, 0FFFFFBBCh
0x140026f92  jz      short loc_140026FC2
0x140026f94  cmp     eax, 0FFFFF8F0h
0x140026f99  jz      short loc_140026FC2
0x140026f9b  cmp     eax, 0FFFFFC0Dh
0x140026fa0  jnz     short loc_140026FA9
0x140026fa2  mov     ebx, 8007000Eh
0x140026fa7  jmp     short loc_140026FCE
0x140026fa9  neg     eax
0x140026fab  cmovs   eax, edi
0x140026fae  movzx   ebx, ax
0x140026fb1  mov     eax, edi
0x140026fb3  and     eax, 8E5E0000h
0x140026fb8  or      ebx, eax
0x140026fba  or      ebx, 0E5E0000h
0x140026fc0  jmp     short loc_140026FCE
0x140026fc2  mov     ecx, 70h ; 'p'; unsigned int
0x140026fc7  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140026fcc  mov     ebx, eax
0x140026fce  mov     r10, cs:WPP_GLOBAL_Control
0x140026fd5  cmp     r10, r12
0x140026fd8  jz      loc_140026F4A
0x140026fde  test    [r10+1Ch], r15b
0x140026fe2  jz      loc_140026F4A
0x140026fe8  cmp     byte ptr [r10+19h], 2
0x140026fed  jb      loc_140026F4A
0x140026ff3  mov     edx, 13h
0x140026ff8  mov     rax, [rsi+28h]
0x140026ffc  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140027003  mov     r9, [r14+8]
0x140027007  mov     rcx, [r10+10h]
0x14002700b  mov     dword ptr [rsp+0E0h+var_B0], edi
0x14002700f  mov     rax, [rax+70h]
0x140027013  mov     [rsp+0E0h+var_B8], rax
0x140027018  mov     rax, [r14]
0x14002701b  mov     qword ptr [rsp+0E0h+grbit], rax
0x140027020  call    WPP_SF_iiSd
0x140027025  jmp     loc_140026F43
0x14002702a  mov     rdx, [rsi+18h]; tableid
0x14002702e  lea     r8, [rbp+4Fh+pvData]; pvData
0x140027032  mov     rcx, [rsi+8]; sesid
0x140027036  mov     r9d, 8; cbData
0x14002703c  mov     [rsp+0E0h+grbit], ebx; grbit
0x140027040  call    cs:__imp_JetMakeKey
0x140027046  mov     edi, eax
0x140027048  test    eax, eax
0x14002704a  jz      short loc_1400270C3
0x14002704c  cmp     eax, 0FFFFFDEFh
0x140027051  jz      short loc_140027088
0x140027053  cmp     eax, 0FFFFFBBCh
0x140027058  jz      short loc_140027088
0x14002705a  cmp     eax, 0FFFFF8F0h
0x14002705f  jz      short loc_140027088
0x140027061  cmp     eax, 0FFFFFC0Dh
0x140027066  jnz     short loc_14002706F
0x140027068  mov     ebx, 8007000Eh
0x14002706d  jmp     short loc_140027094
0x14002706f  neg     eax
0x140027071  cmovs   eax, edi
0x140027074  movzx   ebx, ax
0x140027077  mov     eax, edi
0x140027079  and     eax, 8E5E0000h
0x14002707e  or      ebx, eax
0x140027080  or      ebx, 0E5E0000h
0x140027086  jmp     short loc_140027094
0x140027088  mov     ecx, 70h ; 'p'; unsigned int
0x14002708d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140027092  mov     ebx, eax
0x140027094  mov     r10, cs:WPP_GLOBAL_Control
0x14002709b  cmp     r10, r12
0x14002709e  jz      loc_140026F4A
0x1400270a4  test    [r10+1Ch], r15b
0x1400270a8  jz      loc_140026F4A
0x1400270ae  cmp     byte ptr [r10+19h], 2
0x1400270b3  jb      loc_140026F4A
0x1400270b9  mov     edx, 14h
0x1400270be  jmp     loc_140026FF8
0x1400270c3  mov     rdx, [rsi+18h]; tableid
0x1400270c7  mov     r8d, r15d; grbit
0x1400270ca  mov     rcx, [rsi+8]; sesid
0x1400270ce  call    cs:__imp_JetSeek
0x1400270d4  mov     edi, eax
0x1400270d6  cmp     eax, 0FFFFF9BFh
0x1400270db  jz      loc_1400275A8
0x1400270e1  cmp     eax, 40Fh
0x1400270e6  jz      loc_1400275A8
0x1400270ec  test    eax, eax
0x1400270ee  jz      loc_14002719A
0x1400270f4  cmp     eax, 0FFFFFDEFh
0x1400270f9  jz      short loc_140027130
0x1400270fb  cmp     eax, 0FFFFFBBCh
0x140027100  jz      short loc_140027130
0x140027102  cmp     eax, 0FFFFF8F0h
0x140027107  jz      short loc_140027130
0x140027109  cmp     eax, 0FFFFFC0Dh
0x14002710e  jnz     short loc_140027117
0x140027110  mov     ebx, 8007000Eh
0x140027115  jmp     short loc_14002713C
0x140027117  neg     eax
0x140027119  cmovs   eax, edi
0x14002711c  movzx   ebx, ax
0x14002711f  mov     eax, edi
0x140027121  and     eax, 8E5E0000h
0x140027126  or      ebx, eax
0x140027128  or      ebx, 0E5E0000h
0x14002712e  jmp     short loc_14002713C
0x140027130  mov     ecx, 70h ; 'p'; unsigned int
0x140027135  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002713a  mov     ebx, eax
0x14002713c  mov     r10, cs:WPP_GLOBAL_Control
0x140027143  cmp     r10, r12
0x140027146  jz      loc_140026F4A
0x14002714c  test    [r10+1Ch], r15b
0x140027150  jz      loc_140026F4A
0x140027156  cmp     byte ptr [r10+19h], 2
0x14002715b  jb      loc_140026F4A
0x140027161  mov     rax, [rsi+28h]
0x140027165  mov     edx, 18h
0x14002716a  mov     r9, [r14+8]
0x14002716e  mov     rcx, [r10+10h]
0x140027172  mov     dword ptr [rsp+0E0h+var_A8], edi
0x140027176  mov     rax, [rax+70h]
0x14002717a  mov     [rsp+0E0h+var_B0], rax
0x14002717f  mov     rax, [rbp+4Fh+pvData]
0x140027183  mov     [rsp+0E0h+var_B8], rax
0x140027188  mov     rax, [r14]
0x14002718b  mov     qword ptr [rsp+0E0h+grbit], rax
0x140027190  call    WPP_SF_iiiSL
0x140027195  jmp     loc_140026F43
0x14002719a  mov     rdx, [rsi+18h]; tableid
0x14002719e  mov     r8d, 2; prep
0x1400271a4  mov     rcx, [rsi+8]; sesid
0x1400271a8  call    cs:__imp_JetPrepareUpdate
0x1400271ae  mov     edi, eax
0x1400271b0  cmp     eax, 0FFFFF9B9h
0x1400271b5  jnz     short loc_1400271E1
0x1400271b7  mov     rdx, [rsi+18h]; tableid
0x1400271bb  mov     r8d, 3; prep
0x1400271c1  mov     rcx, [rsi+8]; sesid
0x1400271c5  call    cs:__imp_JetPrepareUpdate
0x1400271cb  mov     rdx, [rsi+18h]; tableid
0x1400271cf  mov     r8d, 2; prep
0x1400271d5  mov     rcx, [rsi+8]; sesid
0x1400271d9  call    cs:__imp_JetPrepareUpdate
0x1400271df  mov     edi, eax
0x1400271e1  test    edi, edi
0x1400271e3  jz      short loc_140027262
0x1400271e5  cmp     edi, 0FFFFFDEFh
0x1400271eb  jz      short loc_140027227
0x1400271ed  cmp     edi, 0FFFFFBBCh
0x1400271f3  jz      short loc_140027227
0x1400271f5  cmp     edi, 0FFFFF8F0h
0x1400271fb  jz      short loc_140027227
0x1400271fd  cmp     edi, 0FFFFFC0Dh
0x140027203  jnz     short loc_14002720C
0x140027205  mov     ebx, 8007000Eh
0x14002720a  jmp     short loc_140027233
0x14002720c  mov     eax, edi
0x14002720e  neg     eax
0x140027210  cmovs   eax, edi
0x140027213  movzx   ebx, ax
0x140027216  mov     eax, edi
0x140027218  and     eax, 8E5E0000h
0x14002721d  or      ebx, eax
0x14002721f  or      ebx, 0E5E0000h
0x140027225  jmp     short loc_140027233
0x140027227  mov     ecx, 70h ; 'p'; unsigned int
0x14002722c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140027231  mov     ebx, eax
0x140027233  mov     r10, cs:WPP_GLOBAL_Control
0x14002723a  cmp     r10, r12
0x14002723d  jz      loc_140026F4A
0x140027243  test    [r10+1Ch], r15b
0x140027247  jz      loc_140026F4A
0x14002724d  cmp     byte ptr [r10+19h], 2
0x140027252  jb      loc_140026F4A
0x140027258  mov     edx, 19h
0x14002725d  jmp     loc_140026FF8
0x140027262  mov     al, [rbp+4Fh+arg_20]
0x140027265  lea     r9, [rbp+4Fh+var_60]; __int64 *
0x140027269  neg     al
0x14002726b  mov     [rbp+4Fh+var_60], rbx
0x14002726f  mov     [rbp+4Fh+var_7E], bl
0x140027272  lea     rax, [rbp+4Fh+var_7F]
0x140027276  mov     [rbp+4Fh+var_7C], bx
0x14002727a  lea     r8, [rbp+4Fh+Source1]; struct TE_FILE_ID_128 *
0x14002727e  mov     [rbp+4Fh+var_7F], bl
0x140027281  xorps   xmm0, xmm0
0x140027284  mov     [rbp+4Fh+var_80], bl
0x140027287  mov     dl, r15b; bool
0x14002728a  sbb     rbx, rbx
0x14002728d  mov     rcx, rsi; this
0x140027290  and     rbx, rax
0x140027293  lea     rax, [rbp+4Fh+var_48]
0x140027297  mov     [rsp+0E0h+var_A0], rax; unsigned __int16 *
0x14002729c  lea     rax, [rbp+4Fh+var_7C]
0x1400272a0  mov     [rsp+0E0h+var_A8], rax; unsigned __int16 *
0x1400272a5  lea     rax, [rbp+4Fh+var_7E]
0x1400272a9  mov     [rsp+0E0h+var_B0], rax; unsigned __int8 *
0x1400272ae  lea     rax, [rbp+4Fh+var_80]
0x1400272b2  mov     [rsp+0E0h+var_B8], rax; unsigned __int8 *
0x1400272b7  mov     qword ptr [rsp+0E0h+grbit], rbx; unsigned __int8 *
0x1400272bc  movups  [rbp+4Fh+Source1], xmm0
0x1400272c0  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x1400272c5  mov     edi, eax
0x1400272c7  test    eax, eax
0x1400272c9  jz      short loc_140027341
0x1400272cb  cmp     eax, 0FFFFFDEFh
0x1400272d0  jz      short loc_140027307
0x1400272d2  cmp     eax, 0FFFFFBBCh
0x1400272d7  jz      short loc_140027307
0x1400272d9  cmp     eax, 0FFFFF8F0h
0x1400272de  jz      short loc_140027307
0x1400272e0  cmp     eax, 0FFFFFC0Dh
0x1400272e5  jnz     short loc_1400272EE
0x1400272e7  mov     ebx, 8007000Eh
0x1400272ec  jmp     short loc_140027313
0x1400272ee  neg     eax
0x1400272f0  cmovs   eax, edi
0x1400272f3  movzx   ebx, ax
0x1400272f6  mov     eax, edi
0x1400272f8  and     eax, 8E5E0000h
0x1400272fd  or      ebx, eax
0x1400272ff  or      ebx, 0E5E0000h
0x140027305  jmp     short loc_140027313
0x140027307  mov     ecx, 70h ; 'p'; unsigned int
0x14002730c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140027311  mov     ebx, eax
0x140027313  mov     rcx, cs:WPP_GLOBAL_Control
0x14002731a  cmp     rcx, r12
0x14002731d  jz      loc_14002758F
0x140027323  test    [rcx+1Ch], r15b
0x140027327  jz      loc_14002758F
0x14002732d  cmp     byte ptr [rcx+19h], 2
0x140027331  jb      loc_14002758F
0x140027337  mov     edx, 1Ah
  ... truncated ...
```
