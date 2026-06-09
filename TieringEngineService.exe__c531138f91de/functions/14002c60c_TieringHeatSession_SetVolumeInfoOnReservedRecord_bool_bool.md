# TieringHeatSession::SetVolumeInfoOnReservedRecord(bool,bool)

- ea: `0x14002c60c`
- end: `0x14002d134`
- name: `?SetVolumeInfoOnReservedRecord@TieringHeatSession@@QEAAJ_N0@Z`
- size: `2856`
- prototype: `__int64 __fastcall(TieringHeatSession *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140010d1c`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009904`
- `0x140009a04`
- `0x140009c08`
- `0x140021018`
- `0x14002866c`
- `0x140029dec`
- `0x14002c60c`
- `0x14002d294`
- `0x14002d31c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14002cba3`
- `ntdll!RtlCompareMemory` at `0x14002cba3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002d0c5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002d0c5`
- `ESENT!JetPrepareUpdate` at `0x14002c9de`
- `ESENT!JetPrepareUpdate` at `0x14002c9fb`
- `ESENT!JetPrepareUpdate` at `0x14002ca0f`
- `ESENT!JetPrepareUpdate` at `0x14002cdd1`
- `ESENT!JetPrepareUpdate` at `0x14002ce1c`
- `ESENT!JetPrepareUpdate` at `0x14002ce39`
- `ESENT!JetPrepareUpdate` at `0x14002ce4a`
- `ESENT!JetPrepareUpdate` at `0x14002d0aa`
- `ESENT!JetPrepareUpdate` at `0x14002c9de`
- `ESENT!JetPrepareUpdate` at `0x14002c9fb`
- `ESENT!JetPrepareUpdate` at `0x14002ca0f`
- `ESENT!JetPrepareUpdate` at `0x14002cdd1`
- `ESENT!JetPrepareUpdate` at `0x14002ce1c`
- `ESENT!JetPrepareUpdate` at `0x14002ce39`
- `ESENT!JetPrepareUpdate` at `0x14002ce4a`
- `ESENT!JetPrepareUpdate` at `0x14002d0aa`
- `ESENT!JetUpdate` at `0x14002d00b`
- `ESENT!JetUpdate` at `0x14002d00b`
- `ESENT!JetMakeKey` at `0x14002c6e8`
- `ESENT!JetMakeKey` at `0x14002c7ad`
- `ESENT!JetMakeKey` at `0x14002c6e8`
- `ESENT!JetMakeKey` at `0x14002c7ad`
- `ESENT!JetSeek` at `0x14002c927`
- `ESENT!JetSeek` at `0x14002c927`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::SetVolumeInfoOnReservedRecord(TieringHeatSession *this)
{
  int v2; // edi
  JET_ERR v3; // ebx
  __int64 v4; // rax
  int v5; // r13d
  unsigned int v6; // r14d
  unsigned __int16 v7; // r15
  _QWORD *v8; // rcx
  JET_ERR Key; // eax
  int v10; // eax
  int v11; // edx
  JET_ERR v12; // eax
  int v13; // eax
  _QWORD *v14; // rcx
  unsigned int v15; // r14d
  __int64 *v16; // rdx
  __int64 v17; // rax
  JET_TABLEID v18; // rdx
  JET_ERR v19; // eax
  int v20; // eax
  int v21; // edx
  int v22; // eax
  JET_ERR CurrentHeatRecord; // eax
  int v24; // eax
  _QWORD *v25; // rcx
  int v26; // edx
  int v27; // r8d
  unsigned __int16 v28; // dx
  __int64 v29; // rdx
  JET_ERR v30; // eax
  int v31; // eax
  _QWORD *v32; // rcx
  int v33; // edx
  int v34; // eax
  JET_ERR v35; // eax
  int v36; // eax
  JET_ERR v37; // eax
  int v38; // eax
  unsigned int v40; // [rsp+54h] [rbp-55h]
  unsigned __int8 v41; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int8 v42[3]; // [rsp+59h] [rbp-50h] BYREF
  unsigned __int16 v43[2]; // [rsp+5Ch] [rbp-4Dh] BYREF
  __int64 v44; // [rsp+60h] [rbp-49h] BYREF
  __int64 v45; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v46[16]; // [rsp+70h] [rbp-39h] BYREF
  __int128 Source1; // [rsp+80h] [rbp-29h] BYREF
  __int128 pvData; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int16 v49[4]; // [rsp+A0h] [rbp-9h] BYREF
  int v50; // [rsp+A8h] [rbp-1h]
  __int16 v51; // [rsp+ACh] [rbp+3h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::SetVolumeInfoOnReservedRecord";
  CHResultImp::CHResultImp((CHResultImp *)v46);
  v44 = 0;
  v2 = 0;
  *(_QWORD *)v49 = 0;
  v50 = 0;
  v3 = -1102;
  v51 = 0;
  v4 = *((_QWORD *)this + 5);
  pvData = 0;
  v5 = *(_DWORD *)(*(_QWORD *)v4 + 176LL);
  v6 = *(_DWORD *)(*(_QWORD *)v4 + 180LL);
  v7 = v6;
  v40 = v6;
LABEL_2:
  v8 = WPP_GLOBAL_Control;
  while ( v3 == -1102 || v3 == -1605 )
  {
    Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), &pvData, 0x10u, 1u);
    v3 = Key;
    if ( Key )
    {
      if ( Key == -529 || Key == -1092 || Key == -1808 )
      {
        v2 = ATL::AtlHresultFromWin32(112);
      }
      else if ( Key == -1011 )
      {
        v2 = -2147024882;
      }
      else
      {
        v10 = -Key;
        if ( v10 < 0 )
          LOWORD(v10) = v3;
        v2 = v3 & 0x8E5E0000 | (unsigned __int16)v10 | 0xE5E0000;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 20;
LABEL_19:
        WPP_SF_Sd(
          v8[2],
          v11,
          (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v3);
        goto LABEL_2;
      }
    }
    else
    {
      v12 = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), &v44, 8u, 0);
      v3 = v12;
      if ( v12 )
      {
        if ( v12 == -529 || v12 == -1092 || v12 == -1808 )
        {
          v2 = ATL::AtlHresultFromWin32(112);
        }
        else if ( v12 == -1011 )
        {
          v2 = -2147024882;
        }
        else
        {
          v13 = -v12;
          if ( v13 < 0 )
            LOWORD(v13) = v3;
          v2 = v3 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 21;
          goto LABEL_19;
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_GLOBAL_Control,
            v5,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
          v14 = WPP_GLOBAL_Control;
        }
        v15 = HIWORD(v6);
        *(_DWORD *)v49 = v5;
        LOWORD(v50) = 0;
        v49[2] = v7;
        v49[3] = v15;
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
          WPP_SF_S(
            v14[2],
            23,
            &WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        v16 = (__int64 *)*((_QWORD *)this + 5);
        HIWORD(v50) = *(_WORD *)(*v16 + 230);
        v51 = *(_WORD *)(*v16 + 228);
        v42[0] = *(_BYTE *)(*v16 + 227);
        v41 = *(_BYTE *)(*v16 + 226);
        v17 = *v16;
        v18 = *((_QWORD *)this + 3);
        v43[0] = *(_WORD *)(v17 + 224);
        v19 = JetSeek(*((_QWORD *)this + 1), v18, 1u);
        v3 = v19;
        if ( v19 == -1601 || v19 == 1039 )
        {
          v3 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
          if ( v3 == -1607 )
          {
            JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
            v3 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
          }
          switch ( v3 )
          {
            case 0:
              v35 = TieringHeatSession::SetCurrentHeatRecord(
                      this,
                      (struct TE_FILE_ID_128 *)&pvData,
                      &v44,
                      v42,
                      &v41,
                      (unsigned __int8 *)(**((_QWORD **)this + 5) + 328LL),
                      v43,
                      v49);
              v3 = v35;
              switch ( v35 )
              {
                case 0:
                  v32 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    v33 = 26;
LABEL_157:
                    WPP_SF_DS(
                      v32[2],
                      v33,
                      (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
                      *(unsigned __int8 *)(**((_QWORD **)this + 5) + 328LL),
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
                  }
LABEL_158:
                  v37 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
                  v3 = v37;
                  if ( v37 )
                  {
                    if ( v37 == -529 || v37 == -1092 || v37 == -1808 )
                    {
                      v2 = ATL::AtlHresultFromWin32(112);
                    }
                    else if ( v37 == -1011 )
                    {
                      v2 = -2147024882;
                    }
                    else
                    {
                      v38 = -v37;
                      if ( v38 < 0 )
                        LOWORD(v38) = v3;
                      v2 = v3 & 0x8E5E0000 | (unsigned __int16)v38 | 0xE5E0000;
                    }
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_Sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        35,
                        (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
                        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                        v3);
                    }
                    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
                    if ( v3 == -1102 || v3 == -1605 )
                      Sleep(0x64u);
                  }
                  else
                  {
                    v2 = 0;
                  }
                  goto LABEL_176;
                case -529:
                case -1092:
                case -1808:
                  v2 = ATL::AtlHresultFromWin32(112);
                  break;
                case -1011:
                  v2 = -2147024882;
                  break;
                default:
                  v36 = -v35;
                  if ( v36 < 0 )
                    LOWORD(v36) = v3;
                  v2 = v3 & 0x8E5E0000 | (unsigned __int16)v36 | 0xE5E0000;
                  break;
              }
              v25 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v26 = 25;
LABEL_117:
                WPP_SF_Sd(
                  v25[2],
                  v26,
                  (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
                  *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                  v3);
              }
LABEL_118:
              JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
LABEL_176:
              v6 = v40;
              goto LABEL_2;
            case -529:
            case -1092:
            case -1808:
              v2 = ATL::AtlHresultFromWin32(112);
              break;
            case -1011:
              v2 = -2147024882;
              break;
            default:
              v34 = -v3;
              if ( v3 > 0 )
                LOWORD(v34) = v3;
              v2 = v3 & 0x8E5E0000 | (unsigned __int16)v34 | 0xE5E0000;
              break;
          }
          v8 = WPP_GLOBAL_Control;
          v6 = v40;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v21 = 24;
            goto LABEL_74;
          }
        }
        else if ( v19 )
        {
          if ( v19 == -529 || v19 == -1092 || v19 == -1808 )
          {
            v2 = ATL::AtlHresultFromWin32(112);
          }
          else if ( v19 == -1011 )
          {
            v2 = -2147024882;
          }
          else
          {
            v20 = -v19;
            if ( v20 < 0 )
              LOWORD(v20) = v3;
            v2 = v3 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
          }
          v8 = WPP_GLOBAL_Control;
          v6 = v40;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v21 = 27;
LABEL_74:
            WPP_SF_Sd(
              v8[2],
              v21,
              (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
              v3);
            goto LABEL_176;
          }
        }
        else
        {
          v3 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
          if ( v3 == -1607 )
          {
            JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
            v3 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
          }
          switch ( v3 )
          {
            case 0:
              v45 = 0;
              Source1 = 0;
              CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                                    this,
                                    1u,
                                    (struct TE_FILE_ID_128 *)&Source1,
                                    &v45,
                                    0,
                                    0,
                                    0,
                                    0,
                                    v49);
              v3 = CurrentHeatRecord;
              if ( CurrentHeatRecord )
              {
                if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
                {
                  v2 = ATL::AtlHresultFromWin32(112);
                }
                else if ( CurrentHeatRecord == -1011 )
                {
                  v2 = -2147024882;
                }
                else
                {
                  v24 = -CurrentHeatRecord;
                  if ( v24 < 0 )
                    LOWORD(v24) = v3;
                  v2 = v3 & 0x8E5E0000 | (unsigned __int16)v24 | 0xE5E0000;
                }
                v25 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v26 = 29;
                  goto LABEL_117;
                }
                goto LABEL_118;
              }
              if ( RtlCompareMemory(&Source1, &pvData, 0x10u) != 16 )
              {
                v2 = -2147220986;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_iiSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
                    DWORD2(Source1),
                    Source1,
                    *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                    0);
                }
                goto LABEL_118;
              }
              if ( v45 != v44 )
              {
                v2 = -2147220986;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_iSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                    v27,
                    v45,
                    *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
                }
                goto LABEL_118;
              }
              v28 = v50 + 1;
              LOWORD(v50) = v50 + 1;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
                  v28,
                  *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
              }
              v29 = *((_QWORD *)this + 5);
              *(_DWORD *)v49 = v5;
              v49[2] = v7;
              v49[3] = v15;
              HIWORD(v50) = *(_WORD *)(*(_QWORD *)v29 + 230LL);
              v51 = *(_WORD *)(*(_QWORD *)v29 + 228LL);
              v30 = TieringHeatSession::SetCurrentHeatRecord(
                      this,
                      0,
                      0,
                      v42,
                      &v41,
                      (unsigned __int8 *)(*(_QWORD *)v29 + 328LL),
                      v43,
                      v49);
              v3 = v30;
              if ( v30 )
              {
                if ( v30 == -529 || v30 == -1092 || v30 == -1808 )
                {
                  v2 = ATL::AtlHresultFromWin32(112);
                }
                else if ( v30 == -1011 )
                {
                  v2 = -2147024882;
                }
                else
                {
                  v31 = -v30;
                  if ( v31 < 0 )
                    LOWORD(v31) = v3;
                  v2 = v3 & 0x8E5E0000 | (unsigned __int16)v31 | 0xE5E0000;
                }
                v25 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v26 = 33;
                  goto LABEL_117;
                }
                goto LABEL_118;
              }
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v33 = 34;
                goto LABEL_157;
              }
              goto LABEL_158;
            case -529:
            case -1092:
            case -1808:
              v2 = ATL::AtlHresultFromWin32(112);
              break;
            case -1011:
              v2 = -2147024882;
              break;
            default:
              v22 = -v3;
              if ( v3 > 0 )
                LOWORD(v22) = v3;
              v2 = v3 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
              break;
          }
          v8 = WPP_GLOBAL_Control;
          v6 = v40;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v21 = 28;
            goto LABEL_74;
          }
        }
      }
    }
  }
  if ( v2 >= 0 && v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_S(v8[2], 36, &WPP_0be274611bac3644b34e961096a35a4e_Traceguids, *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  CHResultImp::~CHResultImp((CHResultImp *)v46);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002c60c  push    rbp
0x14002c60e  push    rbx
0x14002c60f  push    rsi
0x14002c610  push    rdi
0x14002c611  push    r12
0x14002c613  push    r13
0x14002c615  push    r14
0x14002c617  push    r15
0x14002c619  lea     rbp, [rsp-1Fh]
0x14002c61e  sub     rsp, 0C8h
0x14002c625  mov     rax, cs:__security_cookie
0x14002c62c  xor     rax, rsp
0x14002c62f  mov     [rbp+57h+var_50], rax
0x14002c633  mov     rax, gs:58h
0x14002c63c  mov     rsi, rcx
0x14002c63f  mov     ecx, 8
0x14002c644  mov     rdx, [rax]
0x14002c647  lea     rax, aTieringheatses_6; "TieringHeatSession::SetVolumeInfoOnRese"...
0x14002c64e  mov     [rcx+rdx], rax
0x14002c652  lea     rcx, [rbp+57h+var_90]; this
0x14002c656  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002c65b  mov     [rbp+57h+var_A0], 0
0x14002c663  xor     edi, edi
0x14002c665  xor     eax, eax
0x14002c667  mov     [rbp+57h+var_B0], 0
0x14002c66f  mov     qword ptr [rbp+57h+var_60], rax
0x14002c673  xorps   xmm0, xmm0
0x14002c676  mov     [rbp+57h+var_58], eax
0x14002c679  mov     ebx, 0FFFFFBB2h
0x14002c67e  mov     [rbp+57h+var_54], ax
0x14002c682  mov     rax, [rsi+28h]
0x14002c686  movups  [rbp+57h+pvData], xmm0
0x14002c68a  mov     rcx, [rax]
0x14002c68d  mov     r13d, [rcx+0B0h]
0x14002c694  movzx   r12d, r13w
0x14002c698  mov     r14d, [rcx+0B4h]
0x14002c69f  movzx   r15d, r14w
0x14002c6a3  mov     dword ptr [rbp+57h+var_B0], r13d
0x14002c6a7  mov     dword ptr [rbp+57h+var_B0+4], r14d
0x14002c6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c6b2  lea     rdx, WPP_GLOBAL_Control
0x14002c6b9  mov     eax, 1
0x14002c6be  cmp     ebx, 0FFFFFBB2h
0x14002c6c4  jz      short loc_14002C6D2
0x14002c6c6  cmp     ebx, 0FFFFF9BBh
0x14002c6cc  jnz     loc_14002D0D8
0x14002c6d2  mov     rdx, [rsi+18h]; tableid
0x14002c6d6  lea     r8, [rbp+57h+pvData]; pvData
0x14002c6da  mov     rcx, [rsi+8]; sesid
0x14002c6de  mov     r9d, 10h; cbData
0x14002c6e4  mov     [rsp+100h+grbit], eax; grbit
0x14002c6e8  call    cs:__imp_JetMakeKey
0x14002c6ee  mov     ebx, eax
0x14002c6f0  test    eax, eax
0x14002c6f2  jz      loc_14002C793
0x14002c6f8  cmp     eax, 0FFFFFDEFh
0x14002c6fd  jz      short loc_14002C734
0x14002c6ff  cmp     eax, 0FFFFFBBCh
0x14002c704  jz      short loc_14002C734
0x14002c706  cmp     eax, 0FFFFF8F0h
0x14002c70b  jz      short loc_14002C734
0x14002c70d  cmp     eax, 0FFFFFC0Dh
0x14002c712  jnz     short loc_14002C71B
0x14002c714  mov     edi, 8007000Eh
0x14002c719  jmp     short loc_14002C740
0x14002c71b  neg     eax
0x14002c71d  cmovs   eax, ebx
0x14002c720  movzx   edi, ax
0x14002c723  mov     eax, ebx
0x14002c725  and     eax, 8E5E0000h
0x14002c72a  or      edi, eax
0x14002c72c  or      edi, 0E5E0000h
0x14002c732  jmp     short loc_14002C740
0x14002c734  mov     ecx, 70h ; 'p'; unsigned int
0x14002c739  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002c73e  mov     edi, eax
0x14002c740  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c747  lea     rdx, WPP_GLOBAL_Control
0x14002c74e  mov     eax, 1
0x14002c753  cmp     rcx, rdx
0x14002c756  jz      loc_14002C6BE
0x14002c75c  test    [rcx+1Ch], al
0x14002c75f  jz      loc_14002C6BE
0x14002c765  cmp     byte ptr [rcx+19h], 2
0x14002c769  jb      loc_14002C6BE
0x14002c76f  lea     edx, [rax+13h]
0x14002c772  mov     r9, [rsi+28h]
0x14002c776  lea     r8, WPP_0be274611bac3644b34e961096a35a4e_Traceguids
0x14002c77d  mov     rcx, [rcx+10h]
0x14002c781  mov     [rsp+100h+grbit], ebx
0x14002c785  mov     r9, [r9+70h]
0x14002c789  call    WPP_SF_Sd
0x14002c78e  jmp     loc_14002C6AB
0x14002c793  mov     rdx, [rsi+18h]; tableid
0x14002c797  lea     r8, [rbp+57h+var_A0]; pvData
0x14002c79b  mov     rcx, [rsi+8]; sesid
0x14002c79f  mov     r9d, 8; cbData
0x14002c7a5  mov     [rsp+100h+grbit], 0; grbit
0x14002c7ad  call    cs:__imp_JetMakeKey
0x14002c7b3  mov     ebx, eax
0x14002c7b5  test    eax, eax
0x14002c7b7  jz      short loc_14002C838
0x14002c7b9  cmp     eax, 0FFFFFDEFh
0x14002c7be  jz      short loc_14002C7F5
0x14002c7c0  cmp     eax, 0FFFFFBBCh
0x14002c7c5  jz      short loc_14002C7F5
0x14002c7c7  cmp     eax, 0FFFFF8F0h
0x14002c7cc  jz      short loc_14002C7F5
0x14002c7ce  cmp     eax, 0FFFFFC0Dh
0x14002c7d3  jnz     short loc_14002C7DC
0x14002c7d5  mov     edi, 8007000Eh
0x14002c7da  jmp     short loc_14002C801
0x14002c7dc  neg     eax
0x14002c7de  cmovs   eax, ebx
0x14002c7e1  movzx   edi, ax
0x14002c7e4  mov     eax, ebx
0x14002c7e6  and     eax, 8E5E0000h
0x14002c7eb  or      edi, eax
0x14002c7ed  or      edi, 0E5E0000h
0x14002c7f3  jmp     short loc_14002C801
0x14002c7f5  mov     ecx, 70h ; 'p'; unsigned int
0x14002c7fa  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002c7ff  mov     edi, eax
0x14002c801  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c808  lea     rdx, WPP_GLOBAL_Control
0x14002c80f  mov     eax, 1
0x14002c814  cmp     rcx, rdx
0x14002c817  jz      loc_14002C6BE
0x14002c81d  test    [rcx+1Ch], al
0x14002c820  jz      loc_14002C6BE
0x14002c826  cmp     byte ptr [rcx+19h], 2
0x14002c82a  jb      loc_14002C6BE
0x14002c830  lea     edx, [rax+14h]
0x14002c833  jmp     loc_14002C772
0x14002c838  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c83f  lea     r8, WPP_GLOBAL_Control
0x14002c846  mov     ebx, 1
0x14002c84b  cmp     rcx, r8
0x14002c84e  jz      short loc_14002C87F
0x14002c850  test    [rcx+1Ch], bl
0x14002c853  jz      short loc_14002C87F
0x14002c855  cmp     byte ptr [rcx+19h], 5
0x14002c859  jb      short loc_14002C87F
0x14002c85b  mov     rax, [rsi+28h]
0x14002c85f  lea     edx, [rbx+15h]
0x14002c862  mov     r9, [rbp+57h+var_B0]
0x14002c866  mov     rcx, [rcx+10h]
0x14002c86a  mov     rax, [rax+70h]
0x14002c86e  mov     qword ptr [rsp+100h+grbit], rax
0x14002c873  call    WPP_SF_iS
0x14002c878  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c87f  shr     r14d, 10h
0x14002c883  mov     edi, r13d
0x14002c886  shr     edi, 10h
0x14002c889  xor     eax, eax
0x14002c88b  mov     [rbp+57h+var_60], r12w
0x14002c890  mov     word ptr [rbp+57h+var_58], ax
0x14002c894  mov     [rbp+57h+var_60+2], di
0x14002c898  mov     [rbp+57h+var_60+4], r15w
0x14002c89d  mov     [rbp+57h+var_60+6], r14w
0x14002c8a2  lea     rax, WPP_GLOBAL_Control
0x14002c8a9  cmp     rcx, rax
0x14002c8ac  jz      short loc_14002C8D6
0x14002c8ae  test    [rcx+1Ch], bl
0x14002c8b1  jz      short loc_14002C8D6
0x14002c8b3  cmp     byte ptr [rcx+19h], 5
0x14002c8b7  jb      short loc_14002C8D6
0x14002c8b9  mov     r9, [rsi+28h]
0x14002c8bd  lea     r8, WPP_0be274611bac3644b34e961096a35a4e_Traceguids
0x14002c8c4  mov     rcx, [rcx+10h]
0x14002c8c8  mov     edx, 17h
0x14002c8cd  mov     r9, [r9+70h]
0x14002c8d1  call    WPP_SF_S
0x14002c8d6  mov     rdx, [rsi+28h]
0x14002c8da  mov     r8d, ebx; grbit
0x14002c8dd  mov     rax, [rdx]
0x14002c8e0  movzx   ecx, word ptr [rax+0E6h]
0x14002c8e7  mov     word ptr [rbp+57h+var_58+2], cx
0x14002c8eb  mov     rax, [rdx]
0x14002c8ee  movzx   ecx, word ptr [rax+0E4h]
0x14002c8f5  mov     [rbp+57h+var_54], cx
0x14002c8f9  mov     rax, [rdx]
0x14002c8fc  mov     cl, [rax+0E3h]
0x14002c902  mov     [rbp+57h+var_A7], cl
0x14002c905  mov     rax, [rdx]
0x14002c908  mov     cl, [rax+0E2h]
0x14002c90e  mov     [rbp+57h+var_A8], cl
0x14002c911  mov     rax, [rdx]
0x14002c914  mov     rdx, [rsi+18h]; tableid
0x14002c918  movzx   ecx, word ptr [rax+0E0h]
0x14002c91f  mov     [rbp+57h+var_A4], cx
0x14002c923  mov     rcx, [rsi+8]; sesid
0x14002c927  call    cs:__imp_JetSeek
0x14002c92d  mov     ebx, eax
0x14002c92f  cmp     eax, 0FFFFF9BFh
0x14002c934  jz      loc_14002CE11
0x14002c93a  cmp     eax, 40Fh
0x14002c93f  jz      loc_14002CE11
0x14002c945  test    eax, eax
0x14002c947  jz      loc_14002C9D0
0x14002c94d  cmp     eax, 0FFFFFDEFh
0x14002c952  jz      short loc_14002C989
0x14002c954  cmp     eax, 0FFFFFBBCh
0x14002c959  jz      short loc_14002C989
0x14002c95b  cmp     eax, 0FFFFF8F0h
0x14002c960  jz      short loc_14002C989
0x14002c962  cmp     eax, 0FFFFFC0Dh
0x14002c967  jnz     short loc_14002C970
0x14002c969  mov     edi, 8007000Eh
0x14002c96e  jmp     short loc_14002C995
0x14002c970  neg     eax
0x14002c972  cmovs   eax, ebx
0x14002c975  movzx   edi, ax
0x14002c978  mov     eax, ebx
0x14002c97a  and     eax, 8E5E0000h
0x14002c97f  or      edi, eax
0x14002c981  or      edi, 0E5E0000h
0x14002c987  jmp     short loc_14002C995
0x14002c989  mov     ecx, 70h ; 'p'; unsigned int
0x14002c98e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002c993  mov     edi, eax
0x14002c995  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c99c  lea     rdx, WPP_GLOBAL_Control
0x14002c9a3  mov     r14d, dword ptr [rbp+57h+var_B0+4]
0x14002c9a7  mov     eax, 1
0x14002c9ac  cmp     rcx, rdx
0x14002c9af  jz      loc_14002C6BE
0x14002c9b5  test    [rcx+1Ch], al
0x14002c9b8  jz      loc_14002C6BE
0x14002c9be  cmp     byte ptr [rcx+19h], 2
0x14002c9c2  jb      loc_14002C6BE
0x14002c9c8  lea     edx, [rax+1Ah]
0x14002c9cb  jmp     loc_14002CAA3
0x14002c9d0  mov     rdx, [rsi+18h]; tableid
0x14002c9d4  mov     r8d, 2; prep
0x14002c9da  mov     rcx, [rsi+8]; sesid
0x14002c9de  call    cs:__imp_JetPrepareUpdate
0x14002c9e4  mov     ebx, eax
0x14002c9e6  cmp     eax, 0FFFFF9B9h
0x14002c9eb  jnz     short loc_14002CA17
0x14002c9ed  mov     rdx, [rsi+18h]; tableid
0x14002c9f1  mov     r8d, 3; prep
0x14002c9f7  mov     rcx, [rsi+8]; sesid
0x14002c9fb  call    cs:__imp_JetPrepareUpdate
0x14002ca01  mov     rdx, [rsi+18h]; tableid
0x14002ca05  mov     r8d, 2; prep
0x14002ca0b  mov     rcx, [rsi+8]; sesid
0x14002ca0f  call    cs:__imp_JetPrepareUpdate
0x14002ca15  mov     ebx, eax
0x14002ca17  test    ebx, ebx
0x14002ca19  jz      loc_14002CAC4
0x14002ca1f  cmp     ebx, 0FFFFFDEFh
0x14002ca25  jz      short loc_14002CA61
0x14002ca27  cmp     ebx, 0FFFFFBBCh
0x14002ca2d  jz      short loc_14002CA61
0x14002ca2f  cmp     ebx, 0FFFFF8F0h
0x14002ca35  jz      short loc_14002CA61
0x14002ca37  cmp     ebx, 0FFFFFC0Dh
0x14002ca3d  jnz     short loc_14002CA46
0x14002ca3f  mov     edi, 8007000Eh
0x14002ca44  jmp     short loc_14002CA6D
0x14002ca46  mov     eax, ebx
0x14002ca48  neg     eax
0x14002ca4a  cmovs   eax, ebx
0x14002ca4d  movzx   edi, ax
0x14002ca50  mov     eax, ebx
0x14002ca52  and     eax, 8E5E0000h
0x14002ca57  or      edi, eax
0x14002ca59  or      edi, 0E5E0000h
0x14002ca5f  jmp     short loc_14002CA6D
0x14002ca61  mov     ecx, 70h ; 'p'; unsigned int
0x14002ca66  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002ca6b  mov     edi, eax
0x14002ca6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ca74  lea     rdx, WPP_GLOBAL_Control
0x14002ca7b  mov     r14d, dword ptr [rbp+57h+var_B0+4]
0x14002ca7f  mov     eax, 1
0x14002ca84  cmp     rcx, rdx
0x14002ca87  jz      loc_14002C6BE
0x14002ca8d  test    [rcx+1Ch], al
0x14002ca90  jz      loc_14002C6BE
0x14002ca96  cmp     byte ptr [rcx+19h], 2
0x14002ca9a  jb      loc_14002C6BE
0x14002caa0  lea     edx, [rax+1Bh]
0x14002caa3  mov     r9, [rsi+28h]
0x14002caa7  lea     r8, WPP_0be274611bac3644b34e961096a35a4e_Traceguids
0x14002caae  mov     rcx, [rcx+10h]
0x14002cab2  mov     [rsp+100h+grbit], ebx
0x14002cab6  mov     r9, [r9+70h]
0x14002caba  call    WPP_SF_Sd
0x14002cabf  jmp     loc_14002D0CF
0x14002cac4  lea     rax, [rbp+57h+var_60]
0x14002cac8  mov     [rbp+57h+var_98], 0
0x14002cad0  mov     [rsp+100h+var_C0], rax; unsigned __int16 *
0x14002cad5  lea     r9, [rbp+57h+var_98]; __int64 *
0x14002cad9  mov     [rsp+100h+var_C8], 0; unsigned __int16 *
0x14002cae2  lea     r8, [rbp+57h+Source1]; struct TE_FILE_ID_128 *
0x14002cae6  mov     [rsp+100h+var_D0], 0; unsigned __int8 *
0x14002caef  xorps   xmm0, xmm0
0x14002caf2  mov     [rsp+100h+var_D8], 0; unsigned __int8 *
  ... truncated ...
```
