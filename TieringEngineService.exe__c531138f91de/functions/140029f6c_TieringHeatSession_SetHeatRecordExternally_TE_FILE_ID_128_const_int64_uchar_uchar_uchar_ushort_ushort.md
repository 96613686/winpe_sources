# TieringHeatSession::SetHeatRecordExternally(TE_FILE_ID_128 const *,__int64,uchar,uchar,uchar,ushort,ushort *)

- ea: `0x140029f6c`
- end: `0x14002a866`
- name: `?SetHeatRecordExternally@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JEEEGPEAG@Z`
- size: `2298`
- prototype: `__int64 __fastcall(TieringHeatSession *this, const struct TE_FILE_ID_128 *, __int64, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int16, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003f4d8`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140021018`
- `0x1400210c8`
- `0x14002866c`
- `0x140029dec`
- `0x140029f6c`
- `0x14002bc8c`
- `0x14002bd3c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x140029fda`
- `ntdll!RtlCompareMemory` at `0x14002a43e`
- `ntdll!RtlCompareMemory` at `0x140029fda`
- `ntdll!RtlCompareMemory` at `0x14002a43e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002a7e5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002a7e5`
- `ESENT!JetPrepareUpdate` at `0x14002a2ba`
- `ESENT!JetPrepareUpdate` at `0x14002a2d7`
- `ESENT!JetPrepareUpdate` at `0x14002a2eb`
- `ESENT!JetPrepareUpdate` at `0x14002a552`
- `ESENT!JetPrepareUpdate` at `0x14002a56f`
- `ESENT!JetPrepareUpdate` at `0x14002a580`
- `ESENT!JetPrepareUpdate` at `0x14002a6f5`
- `ESENT!JetPrepareUpdate` at `0x14002a7c6`
- `ESENT!JetPrepareUpdate` at `0x14002a2ba`
- `ESENT!JetPrepareUpdate` at `0x14002a2d7`
- `ESENT!JetPrepareUpdate` at `0x14002a2eb`
- `ESENT!JetPrepareUpdate` at `0x14002a552`
- `ESENT!JetPrepareUpdate` at `0x14002a56f`
- `ESENT!JetPrepareUpdate` at `0x14002a580`
- `ESENT!JetPrepareUpdate` at `0x14002a6f5`
- `ESENT!JetPrepareUpdate` at `0x14002a7c6`
- `ESENT!JetUpdate` at `0x14002a713`
- `ESENT!JetUpdate` at `0x14002a713`
- `ESENT!JetMakeKey` at `0x14002a077`
- `ESENT!JetMakeKey` at `0x14002a147`
- `ESENT!JetMakeKey` at `0x14002a077`
- `ESENT!JetMakeKey` at `0x14002a147`
- `ESENT!JetSeek` at `0x14002a1dc`
- `ESENT!JetSeek` at `0x14002a1dc`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::SetHeatRecordExternally(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *a2,
        __int64 a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        unsigned __int8 a6,
        unsigned __int16 a7,
        unsigned __int16 *a8)
{
  PVOID ThreadLocalStoragePointer; // rax
  int v11; // r8d
  int v12; // edi
  JET_ERR v13; // ebx
  _QWORD *v14; // r10
  JET_ERR Key; // eax
  int v16; // eax
  int v17; // edx
  JET_ERR v18; // eax
  int v19; // eax
  JET_ERR v20; // eax
  int v21; // eax
  int v22; // eax
  JET_ERR CurrentHeatRecord; // eax
  int v24; // eax
  _QWORD *v25; // rcx
  int v26; // edx
  int v27; // eax
  JET_ERR v28; // eax
  int v29; // eax
  JET_ERR v30; // eax
  int v31; // eax
  unsigned __int8 v33[8]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v34[8]; // [rsp+58h] [rbp-41h] BYREF
  int v35; // [rsp+60h] [rbp-39h]
  __int64 pvData; // [rsp+68h] [rbp-31h] BYREF
  __int64 v37; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v38; // [rsp+78h] [rbp-21h]
  __int128 Source1; // [rsp+80h] [rbp-19h] BYREF

  v38 = a8;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  pvData = a3;
  v33[0] = a4;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::SetHeatRecordExternally";
  CHResultImp::CHResultImp((CHResultImp *)v34);
  if ( RtlCompareMemory(a2, &NullGuid, 0x10u) == 16 )
  {
    v12 = -2138898428;
    v35 = -2138898428;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, 2156068868LL);
    }
  }
  else
  {
    v12 = v35;
    v13 = -1102;
LABEL_7:
    v14 = WPP_GLOBAL_Control;
    while ( v13 == -1102 || v13 == -1605 )
    {
      Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), a2, 0x10u, 1u);
      v12 = 0;
      v13 = Key;
      if ( Key )
      {
        if ( Key == -529 || Key == -1092 || Key == -1808 )
        {
          v12 = ATL::AtlHresultFromWin32(112);
        }
        else if ( Key == -1011 )
        {
          v12 = -2147024882;
        }
        else
        {
          v16 = -Key;
          if ( v16 < 0 )
            LOWORD(v16) = v13;
          v12 = v13 & 0x8E5E0000 | (unsigned __int16)v16 | 0xE5E0000;
        }
        v35 = v12;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = 99;
LABEL_24:
          WPP_SF_iiSd(
            v14[2],
            v17,
            (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
            *((_QWORD *)a2 + 1),
            *(_QWORD *)a2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v13);
          goto LABEL_7;
        }
      }
      else
      {
        v18 = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), &pvData, 8u, 0);
        v13 = v18;
        if ( v18 )
        {
          if ( v18 == -529 || v18 == -1092 || v18 == -1808 )
          {
            v12 = ATL::AtlHresultFromWin32(112);
          }
          else if ( v18 == -1011 )
          {
            v12 = -2147024882;
          }
          else
          {
            v19 = -v18;
            if ( v19 < 0 )
              LOWORD(v19) = v13;
            v12 = v13 & 0x8E5E0000 | (unsigned __int16)v19 | 0xE5E0000;
          }
          v35 = v12;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = 100;
            goto LABEL_24;
          }
        }
        else
        {
          v20 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1u);
          v13 = v20;
          if ( v20 == -1601 || v20 == 1039 )
          {
            v13 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
            if ( v13 == -1607 )
            {
              JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
              v13 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0);
            }
            switch ( v13 )
            {
              case 0:
                goto LABEL_111;
              case -529:
              case -1092:
              case -1808:
                v12 = ATL::AtlHresultFromWin32(112);
                break;
              case -1011:
                v12 = -2147024882;
                break;
              default:
                v27 = -v13;
                if ( v13 > 0 )
                  LOWORD(v27) = v13;
                v12 = v13 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
                break;
            }
            v35 = v12;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = 101;
              goto LABEL_24;
            }
          }
          else if ( v20 )
          {
            if ( v20 == -529 || v20 == -1092 || v20 == -1808 )
            {
              v12 = ATL::AtlHresultFromWin32(112);
            }
            else if ( v20 == -1011 )
            {
              v12 = -2147024882;
            }
            else
            {
              v21 = -v20;
              if ( v21 < 0 )
                LOWORD(v21) = v13;
              v12 = v13 & 0x8E5E0000 | (unsigned __int16)v21 | 0xE5E0000;
            }
            v35 = v12;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiiSL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                102,
                v11,
                *((_QWORD *)a2 + 1),
                *(_QWORD *)a2,
                pvData,
                *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                v13);
              goto LABEL_7;
            }
          }
          else
          {
            v13 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
            if ( v13 == -1607 )
            {
              JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
              v13 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
            }
            switch ( v13 )
            {
              case 0:
                Source1 = 0;
                v37 = 0;
                CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                                      this,
                                      1u,
                                      (struct TE_FILE_ID_128 *)&Source1,
                                      &v37,
                                      0,
                                      0,
                                      0,
                                      0,
                                      0);
                v13 = CurrentHeatRecord;
                if ( CurrentHeatRecord )
                {
                  if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
                  {
                    v12 = ATL::AtlHresultFromWin32(112);
                  }
                  else if ( CurrentHeatRecord == -1011 )
                  {
                    v12 = -2147024882;
                  }
                  else
                  {
                    v24 = -CurrentHeatRecord;
                    if ( v24 < 0 )
                      LOWORD(v24) = v13;
                    v12 = v13 & 0x8E5E0000 | (unsigned __int16)v24 | 0xE5E0000;
                  }
                  v35 = v12;
                  v25 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v26 = 104;
                    goto LABEL_125;
                  }
                  goto LABEL_126;
                }
                if ( RtlCompareMemory(&Source1, a2, 0x10u) != 16 )
                {
                  v12 = -2147220986;
                  v35 = -2147220986;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_iiiiSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      105,
                      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                      *((_QWORD *)a2 + 1),
                      *(_QWORD *)a2,
                      SBYTE8(Source1),
                      Source1,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                      0);
                  }
                  goto LABEL_126;
                }
                if ( v37 != pvData )
                {
                  v12 = -2147220986;
                  v35 = -2147220986;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_iiiiSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      106,
                      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                      *((_QWORD *)a2 + 1),
                      *(_QWORD *)a2,
                      pvData,
                      v37,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                      6);
                  }
                  goto LABEL_126;
                }
LABEL_111:
                v28 = TieringHeatSession::SetCurrentHeatRecord(this, a2, &pvData, v33, &a5, &a6, &a7, v38);
                v13 = v28;
                if ( v28 )
                {
                  if ( v28 == -529 || v28 == -1092 || v28 == -1808 )
                  {
                    v12 = ATL::AtlHresultFromWin32(112);
                  }
                  else if ( v28 == -1011 )
                  {
                    v12 = -2147024882;
                  }
                  else
                  {
                    v29 = -v28;
                    if ( v29 < 0 )
                      LOWORD(v29) = v13;
                    v12 = v13 & 0x8E5E0000 | (unsigned __int16)v29 | 0xE5E0000;
                  }
                  v35 = v12;
                  v25 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v26 = 107;
LABEL_125:
                    WPP_SF_iiSd(
                      v25[2],
                      v26,
                      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                      *((_QWORD *)a2 + 1),
                      *(_QWORD *)a2,
                      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                      v13);
                  }
LABEL_126:
                  JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
                }
                else
                {
                  v30 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
                  v13 = v30;
                  if ( v30 )
                  {
                    if ( v30 == -529 || v30 == -1092 || v30 == -1808 )
                    {
                      v12 = ATL::AtlHresultFromWin32(112);
                    }
                    else if ( v30 == -1011 )
                    {
                      v12 = -2147024882;
                    }
                    else
                    {
                      v31 = -v30;
                      if ( v31 < 0 )
                        LOWORD(v31) = v13;
                      v12 = v13 & 0x8E5E0000 | (unsigned __int16)v31 | 0xE5E0000;
                    }
                    v35 = v12;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_iiSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        108,
                        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                        *((_QWORD *)a2 + 1),
                        *(_QWORD *)a2,
                        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                        v13);
                    }
                    JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
                    if ( v13 == -1102 || v13 == -1605 )
                      Sleep(0x64u);
                  }
                  else
                  {
                    v35 = 0;
                  }
                }
                goto LABEL_7;
              case -529:
              case -1092:
              case -1808:
                v12 = ATL::AtlHresultFromWin32(112);
                break;
              case -1011:
                v12 = -2147024882;
                break;
              default:
                v22 = -v13;
                if ( v13 > 0 )
                  LOWORD(v22) = v13;
                v12 = v13 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
                break;
            }
            v35 = v12;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = 103;
              goto LABEL_24;
            }
          }
        }
      }
    }
    if ( v12 >= 0 && v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
      WPP_SF_iiiS(
        v14[2],
        109,
        v11,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        pvData,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  }
  CHResultImp::~CHResultImp((CHResultImp *)v34);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140029f6c  push    rbp
0x140029f6e  push    rbx
0x140029f6f  push    rsi
0x140029f70  push    rdi
0x140029f71  push    r13
0x140029f73  push    r15
0x140029f75  lea     rbp, [rsp-0Fh]
0x140029f7a  sub     rsp, 0A8h
0x140029f81  mov     rax, cs:__security_cookie
0x140029f88  xor     rax, rsp
0x140029f8b  mov     [rbp+37h+var_40], rax
0x140029f8f  mov     rax, [rbp+37h+arg_38]
0x140029f93  mov     rsi, rcx
0x140029f96  mov     [rbp+37h+var_58], rax
0x140029f9a  mov     r15, rdx
0x140029f9d  mov     rax, gs:58h
0x140029fa6  mov     ecx, 8
0x140029fab  mov     [rbp+37h+pvData], r8
0x140029faf  mov     [rbp+37h+var_80], r9b
0x140029fb3  mov     rdx, [rax]
0x140029fb6  lea     rax, aTieringheatses_1; "TieringHeatSession::SetHeatRecordExtern"...
0x140029fbd  mov     [rcx+rdx], rax
0x140029fc1  lea     rcx, [rbp+37h+var_78]; this
0x140029fc5  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140029fca  mov     r8d, 10h; Length
0x140029fd0  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x140029fd7  mov     rcx, r15; Source1
0x140029fda  call    cs:__imp_RtlCompareMemory
0x140029fe0  cmp     rax, 10h
0x140029fe4  jnz     short loc_14002A034
0x140029fe6  mov     edi, 80830004h
0x140029feb  mov     [rbp+37h+var_70], edi
0x140029fee  mov     rcx, cs:WPP_GLOBAL_Control
0x140029ff5  lea     r13, WPP_GLOBAL_Control
0x140029ffc  cmp     rcx, r13
0x140029fff  jz      loc_14002A83F
0x14002a005  test    byte ptr [rcx+1Ch], 1
0x14002a009  jz      loc_14002A83F
0x14002a00f  cmp     byte ptr [rcx+19h], 2
0x14002a013  jb      loc_14002A83F
0x14002a019  mov     rcx, [rcx+10h]
0x14002a01d  lea     edx, [rax+52h]
0x14002a020  mov     r9d, edi
0x14002a023  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002a02a  call    WPP_SF_d
0x14002a02f  jmp     loc_14002A83F
0x14002a034  mov     edi, [rbp+37h+var_70]
0x14002a037  lea     r13, WPP_GLOBAL_Control
0x14002a03e  mov     ebx, 0FFFFFBB2h
0x14002a043  mov     r10, cs:WPP_GLOBAL_Control
0x14002a04a  cmp     ebx, 0FFFFFBB2h
0x14002a050  jz      short loc_14002A05E
0x14002a052  cmp     ebx, 0FFFFF9BBh
0x14002a058  jnz     loc_14002A7F8
0x14002a05e  mov     rdx, [rsi+18h]; tableid
0x14002a062  mov     r9d, 10h; cbData
0x14002a068  mov     rcx, [rsi+8]; sesid
0x14002a06c  mov     r8, r15; pvData
0x14002a06f  mov     [rsp+0D0h+grbit], 1; grbit
0x14002a077  call    cs:__imp_JetMakeKey
0x14002a07d  xor     edi, edi
0x14002a07f  mov     ebx, eax
0x14002a081  test    eax, eax
0x14002a083  jz      loc_14002A131
0x14002a089  cmp     eax, 0FFFFFDEFh
0x14002a08e  jz      short loc_14002A0C5
0x14002a090  cmp     eax, 0FFFFFBBCh
0x14002a095  jz      short loc_14002A0C5
0x14002a097  cmp     eax, 0FFFFF8F0h
0x14002a09c  jz      short loc_14002A0C5
0x14002a09e  cmp     eax, 0FFFFFC0Dh
0x14002a0a3  jnz     short loc_14002A0AC
0x14002a0a5  mov     edi, 8007000Eh
0x14002a0aa  jmp     short loc_14002A0D1
0x14002a0ac  neg     eax
0x14002a0ae  cmovs   eax, ebx
0x14002a0b1  movzx   edi, ax
0x14002a0b4  mov     eax, ebx
0x14002a0b6  and     eax, 8E5E0000h
0x14002a0bb  or      edi, eax
0x14002a0bd  or      edi, 0E5E0000h
0x14002a0c3  jmp     short loc_14002A0D1
0x14002a0c5  mov     ecx, 70h ; 'p'; unsigned int
0x14002a0ca  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002a0cf  mov     edi, eax
0x14002a0d1  mov     [rbp+37h+var_70], edi
0x14002a0d4  mov     r10, cs:WPP_GLOBAL_Control
0x14002a0db  cmp     r10, r13
0x14002a0de  jz      loc_14002A04A
0x14002a0e4  test    byte ptr [r10+1Ch], 1
0x14002a0e9  jz      loc_14002A04A
0x14002a0ef  cmp     byte ptr [r10+19h], 2
0x14002a0f4  jb      loc_14002A04A
0x14002a0fa  mov     edx, 63h ; 'c'
0x14002a0ff  mov     rax, [rsi+28h]
0x14002a103  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002a10a  mov     r9, [r15+8]
0x14002a10e  mov     rcx, [r10+10h]
0x14002a112  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x14002a116  mov     rax, [rax+70h]
0x14002a11a  mov     [rsp+0D0h+var_A8], rax
0x14002a11f  mov     rax, [r15]
0x14002a122  mov     qword ptr [rsp+0D0h+grbit], rax
0x14002a127  call    WPP_SF_iiSd
0x14002a12c  jmp     loc_14002A043
0x14002a131  mov     rdx, [rsi+18h]; tableid
0x14002a135  lea     r8, [rbp+37h+pvData]; pvData
0x14002a139  mov     rcx, [rsi+8]; sesid
0x14002a13d  mov     r9d, 8; cbData
0x14002a143  mov     [rsp+0D0h+grbit], edi; grbit
0x14002a147  call    cs:__imp_JetMakeKey
0x14002a14d  mov     ebx, eax
0x14002a14f  test    eax, eax
0x14002a151  jz      short loc_14002A1CE
0x14002a153  cmp     eax, 0FFFFFDEFh
0x14002a158  jz      short loc_14002A18F
0x14002a15a  cmp     eax, 0FFFFFBBCh
0x14002a15f  jz      short loc_14002A18F
0x14002a161  cmp     eax, 0FFFFF8F0h
0x14002a166  jz      short loc_14002A18F
0x14002a168  cmp     eax, 0FFFFFC0Dh
0x14002a16d  jnz     short loc_14002A176
0x14002a16f  mov     edi, 8007000Eh
0x14002a174  jmp     short loc_14002A19B
0x14002a176  neg     eax
0x14002a178  cmovs   eax, ebx
0x14002a17b  movzx   edi, ax
0x14002a17e  mov     eax, ebx
0x14002a180  and     eax, 8E5E0000h
0x14002a185  or      edi, eax
0x14002a187  or      edi, 0E5E0000h
0x14002a18d  jmp     short loc_14002A19B
0x14002a18f  mov     ecx, 70h ; 'p'; unsigned int
0x14002a194  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002a199  mov     edi, eax
0x14002a19b  mov     [rbp+37h+var_70], edi
0x14002a19e  mov     r10, cs:WPP_GLOBAL_Control
0x14002a1a5  cmp     r10, r13
0x14002a1a8  jz      loc_14002A04A
0x14002a1ae  test    byte ptr [r10+1Ch], 1
0x14002a1b3  jz      loc_14002A04A
0x14002a1b9  cmp     byte ptr [r10+19h], 2
0x14002a1be  jb      loc_14002A04A
0x14002a1c4  mov     edx, 64h ; 'd'
0x14002a1c9  jmp     loc_14002A0FF
0x14002a1ce  mov     rdx, [rsi+18h]; tableid
0x14002a1d2  mov     r8d, 1; grbit
0x14002a1d8  mov     rcx, [rsi+8]; sesid
0x14002a1dc  call    cs:__imp_JetSeek
0x14002a1e2  mov     ebx, eax
0x14002a1e4  cmp     eax, 0FFFFF9BFh
0x14002a1e9  jz      loc_14002A547
0x14002a1ef  cmp     eax, 40Fh
0x14002a1f4  jz      loc_14002A547
0x14002a1fa  test    eax, eax
0x14002a1fc  jz      loc_14002A2AC
0x14002a202  cmp     eax, 0FFFFFDEFh
0x14002a207  jz      short loc_14002A23E
0x14002a209  cmp     eax, 0FFFFFBBCh
0x14002a20e  jz      short loc_14002A23E
0x14002a210  cmp     eax, 0FFFFF8F0h
0x14002a215  jz      short loc_14002A23E
0x14002a217  cmp     eax, 0FFFFFC0Dh
0x14002a21c  jnz     short loc_14002A225
0x14002a21e  mov     edi, 8007000Eh
0x14002a223  jmp     short loc_14002A24A
0x14002a225  neg     eax
0x14002a227  cmovs   eax, ebx
0x14002a22a  movzx   edi, ax
0x14002a22d  mov     eax, ebx
0x14002a22f  and     eax, 8E5E0000h
0x14002a234  or      edi, eax
0x14002a236  or      edi, 0E5E0000h
0x14002a23c  jmp     short loc_14002A24A
0x14002a23e  mov     ecx, 70h ; 'p'; unsigned int
0x14002a243  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002a248  mov     edi, eax
0x14002a24a  mov     [rbp+37h+var_70], edi
0x14002a24d  mov     r10, cs:WPP_GLOBAL_Control
0x14002a254  cmp     r10, r13
0x14002a257  jz      loc_14002A04A
0x14002a25d  test    byte ptr [r10+1Ch], 1
0x14002a262  jz      loc_14002A04A
0x14002a268  cmp     byte ptr [r10+19h], 2
0x14002a26d  jb      loc_14002A04A
0x14002a273  mov     rax, [rsi+28h]
0x14002a277  mov     edx, 66h ; 'f'
0x14002a27c  mov     r9, [r15+8]
0x14002a280  mov     rcx, [r10+10h]
0x14002a284  mov     dword ptr [rsp+0D0h+var_98], ebx
0x14002a288  mov     rax, [rax+70h]
0x14002a28c  mov     [rsp+0D0h+var_A0], rax
0x14002a291  mov     rax, [rbp+37h+pvData]
0x14002a295  mov     [rsp+0D0h+var_A8], rax
0x14002a29a  mov     rax, [r15]
0x14002a29d  mov     qword ptr [rsp+0D0h+grbit], rax
0x14002a2a2  call    WPP_SF_iiiSL
0x14002a2a7  jmp     loc_14002A043
0x14002a2ac  mov     rdx, [rsi+18h]; tableid
0x14002a2b0  mov     r8d, 2; prep
0x14002a2b6  mov     rcx, [rsi+8]; sesid
0x14002a2ba  call    cs:__imp_JetPrepareUpdate
0x14002a2c0  mov     ebx, eax
0x14002a2c2  cmp     eax, 0FFFFF9B9h
0x14002a2c7  jnz     short loc_14002A2F3
0x14002a2c9  mov     rdx, [rsi+18h]; tableid
0x14002a2cd  mov     r8d, 3; prep
0x14002a2d3  mov     rcx, [rsi+8]; sesid
0x14002a2d7  call    cs:__imp_JetPrepareUpdate
0x14002a2dd  mov     rdx, [rsi+18h]; tableid
0x14002a2e1  mov     r8d, 2; prep
0x14002a2e7  mov     rcx, [rsi+8]; sesid
0x14002a2eb  call    cs:__imp_JetPrepareUpdate
0x14002a2f1  mov     ebx, eax
0x14002a2f3  test    ebx, ebx
0x14002a2f5  jz      loc_14002A37C
0x14002a2fb  cmp     ebx, 0FFFFFDEFh
0x14002a301  jz      short loc_14002A33D
0x14002a303  cmp     ebx, 0FFFFFBBCh
0x14002a309  jz      short loc_14002A33D
0x14002a30b  cmp     ebx, 0FFFFF8F0h
0x14002a311  jz      short loc_14002A33D
0x14002a313  cmp     ebx, 0FFFFFC0Dh
0x14002a319  jnz     short loc_14002A322
0x14002a31b  mov     edi, 8007000Eh
0x14002a320  jmp     short loc_14002A349
0x14002a322  mov     eax, ebx
0x14002a324  neg     eax
0x14002a326  cmovs   eax, ebx
0x14002a329  movzx   edi, ax
0x14002a32c  mov     eax, ebx
0x14002a32e  and     eax, 8E5E0000h
0x14002a333  or      edi, eax
0x14002a335  or      edi, 0E5E0000h
0x14002a33b  jmp     short loc_14002A349
0x14002a33d  mov     ecx, 70h ; 'p'; unsigned int
0x14002a342  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002a347  mov     edi, eax
0x14002a349  mov     [rbp+37h+var_70], edi
0x14002a34c  mov     r10, cs:WPP_GLOBAL_Control
0x14002a353  cmp     r10, r13
0x14002a356  jz      loc_14002A04A
0x14002a35c  test    byte ptr [r10+1Ch], 1
0x14002a361  jz      loc_14002A04A
0x14002a367  cmp     byte ptr [r10+19h], 2
0x14002a36c  jb      loc_14002A04A
0x14002a372  mov     edx, 67h ; 'g'
0x14002a377  jmp     loc_14002A0FF
0x14002a37c  mov     [rsp+0D0h+var_90], rdi; unsigned __int16 *
0x14002a381  lea     r9, [rbp+37h+var_60]; __int64 *
0x14002a385  mov     [rsp+0D0h+var_98], rdi; unsigned __int16 *
0x14002a38a  lea     r8, [rbp+37h+Source1]; struct TE_FILE_ID_128 *
0x14002a38e  mov     [rsp+0D0h+var_A0], rdi; unsigned __int8 *
0x14002a393  xorps   xmm0, xmm0
0x14002a396  mov     [rsp+0D0h+var_A8], rdi; unsigned __int8 *
0x14002a39b  mov     dl, 1; bool
0x14002a39d  mov     rcx, rsi; this
0x14002a3a0  mov     qword ptr [rsp+0D0h+grbit], rdi; unsigned __int8 *
0x14002a3a5  movups  [rbp+37h+Source1], xmm0
0x14002a3a9  mov     [rbp+37h+var_60], rdi
0x14002a3ad  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002a3b2  mov     ebx, eax
0x14002a3b4  test    eax, eax
0x14002a3b6  jz      short loc_14002A431
0x14002a3b8  cmp     eax, 0FFFFFDEFh
0x14002a3bd  jz      short loc_14002A3F4
0x14002a3bf  cmp     eax, 0FFFFFBBCh
0x14002a3c4  jz      short loc_14002A3F4
0x14002a3c6  cmp     eax, 0FFFFF8F0h
0x14002a3cb  jz      short loc_14002A3F4
0x14002a3cd  cmp     eax, 0FFFFFC0Dh
0x14002a3d2  jnz     short loc_14002A3DB
0x14002a3d4  mov     edi, 8007000Eh
0x14002a3d9  jmp     short loc_14002A400
0x14002a3db  neg     eax
0x14002a3dd  cmovs   eax, ebx
0x14002a3e0  movzx   edi, ax
0x14002a3e3  mov     eax, ebx
0x14002a3e5  and     eax, 8E5E0000h
0x14002a3ea  or      edi, eax
0x14002a3ec  or      edi, 0E5E0000h
0x14002a3f2  jmp     short loc_14002A400
0x14002a3f4  mov     ecx, 70h ; 'p'; unsigned int
0x14002a3f9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002a3fe  mov     edi, eax
0x14002a400  mov     [rbp+37h+var_70], edi
0x14002a403  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a40a  cmp     rcx, r13
0x14002a40d  jz      loc_14002A6E7
0x14002a413  test    byte ptr [rcx+1Ch], 1
0x14002a417  jz      loc_14002A6E7
0x14002a41d  cmp     byte ptr [rcx+19h], 2
0x14002a421  jb      loc_14002A6E7
0x14002a427  mov     edx, 68h ; 'h'
0x14002a42c  jmp     loc_14002A6BA
0x14002a431  mov     r8d, 10h; Length
0x14002a437  lea     rcx, [rbp+37h+Source1]; Source1
0x14002a43b  mov     rdx, r15; Source2
0x14002a43e  call    cs:__imp_RtlCompareMemory
0x14002a444  cmp     rax, 10h
  ... truncated ...
```
