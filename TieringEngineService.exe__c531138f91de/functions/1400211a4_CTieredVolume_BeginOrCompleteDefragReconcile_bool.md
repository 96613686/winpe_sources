# CTieredVolume::BeginOrCompleteDefragReconcile(bool)

- ea: `0x1400211a4`
- end: `0x140021a22`
- name: `?BeginOrCompleteDefragReconcile@CTieredVolume@@AEAAJ_N@Z`
- size: `2174`
- prototype: `__int64 __fastcall(HANDLE *this, char)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400237c8`
- `0x1400243e8`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14000ccc0`
- `0x1400127dc`
- `0x140017824`
- `0x140017e78`
- `0x1400188b8`
- `0x1400197b0`
- `0x14001a1d4`
- `0x14001b328`
- `0x14001cd80`
- `0x1400211a4`
- `0x140026370`
- `0x14002866c`
- `0x140029dec`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x140021520`
- `ntdll!RtlCompareMemory` at `0x140021520`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400213cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400213e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400213cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400213e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002186a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002186a`
- `ESENT!JetPrepareUpdate` at `0x140021557`
- `ESENT!JetPrepareUpdate` at `0x140021575`
- `ESENT!JetPrepareUpdate` at `0x140021589`
- `ESENT!JetPrepareUpdate` at `0x140021745`
- `ESENT!JetPrepareUpdate` at `0x140021856`
- `ESENT!JetPrepareUpdate` at `0x140021557`
- `ESENT!JetPrepareUpdate` at `0x140021575`
- `ESENT!JetPrepareUpdate` at `0x140021589`
- `ESENT!JetPrepareUpdate` at `0x140021745`
- `ESENT!JetPrepareUpdate` at `0x140021856`
- `ESENT!JetUpdate` at `0x1400217a7`
- `ESENT!JetUpdate` at `0x1400217a7`
- `ESENT!JetMove` at `0x140021423`
- `ESENT!JetMove` at `0x140021423`

## string_xrefs

- `0x1400211e0`: `CTieredVolume::BeginOrCompleteDefragReconcile`

## pseudocode

```c
__int64 __fastcall CTieredVolume::BeginOrCompleteDefragReconcile(HANDLE *this, char a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  unsigned int v7; // r12d
  char v8; // r14
  _QWORD *v9; // r10
  unsigned int v10; // eax
  __int64 v11; // r9
  int CurrentHeatRecord; // eax
  JET_ERR v14; // r8d
  int v15; // eax
  unsigned __int8 *v16; // r9
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  int v20; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // r14d
  int v23; // eax
  int v24; // eax
  unsigned __int8 v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v27; // [rsp+51h] [rbp-AFh] BYREF
  char v28; // [rsp+52h] [rbp-AEh]
  char v29; // [rsp+53h] [rbp-ADh]
  int v30; // [rsp+54h] [rbp-ACh]
  int cRow; // [rsp+58h] [rbp-A8h]
  _BYTE v32[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[8]; // [rsp+80h] [rbp-80h] BYREF
  JET_SESID sesid; // [rsp+88h] [rbp-78h]
  JET_TABLEID tableid; // [rsp+98h] [rbp-68h]
  __int16 v38; // [rsp+A0h] [rbp-60h]
  char v39; // [rsp+A2h] [rbp-5Eh]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  char v41; // [rsp+B0h] [rbp-50h]
  __int128 Source2; // [rsp+E0h] [rbp-20h] BYREF

  v29 = a2;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::BeginOrCompleteDefragReconcile";
  CHResultImp::CHResultImp((CHResultImp *)v32);
  v35[0] = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v3 = CTieredVolume::ReferenceVolume((CTieredVolume *)this, 0);
  v4 = v3;
  v33 = v3;
  if ( v3 >= 0 )
  {
    v5 = TieringJetSession::Initialize((TieringJetSession *)v35, (struct TieringJetDatabase *)(this + 148));
    v4 = v5;
    v33 = v5;
    if ( v5 >= 0 )
    {
      v6 = TieringJetSession::OpenJetTable((TieringJetSession *)v35, 1);
      v4 = v6;
      v33 = v6;
      if ( v6 >= 0 )
      {
        v7 = 0;
        v30 = 0;
        v8 = 0;
        v28 = 0;
        v27 = 0;
        v26 = 0;
        cRow = 0x80000000;
        v4 = 0;
        v33 = 0;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids, this + 84);
LABEL_20:
          v9 = WPP_GLOBAL_Control;
          goto LABEL_21;
        }
        while ( 1 )
        {
LABEL_21:
          if ( *((_BYTE *)this + 165) || *((_BYTE *)this + 166) )
            goto LABEL_123;
          if ( WaitForSingleObject(this[96], 0) != 258 || WaitForSingleObject(this[95], 0) != 258 )
            break;
          if ( *(_BYTE *)(v40 + 77) && *(_BYTE *)(v40 + 76) )
            goto LABEL_127;
          if ( v8 )
          {
            v8 = 0;
            v28 = 0;
          }
          else
          {
            v10 = JetMove(sesid, tableid, cRow, 0);
            v11 = v10;
            if ( v10 == -1601 || v10 == 1039 || v10 == -1603 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids, v10);
                v9 = WPP_GLOBAL_Control;
              }
              v4 = 0;
              v33 = 0;
              goto LABEL_128;
            }
            cRow = 1;
            if ( v10 == -1017 )
              goto LABEL_103;
            if ( v10 )
            {
              if ( v10 == -529 || v10 == -1092 || v10 == -1808 )
              {
                v4 = ATL::AtlHresultFromWin32(112);
              }
              else if ( v10 == -1011 )
              {
                v4 = -2147024882;
              }
              else
              {
                v24 = -v10;
                if ( v24 < 0 )
                  LOWORD(v24) = v11;
                v4 = v11 & 0x8E5E0000 | (unsigned __int16)v24 | 0xE5E0000;
              }
              v33 = v4;
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    79,
                    &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                    v11);
                  goto LABEL_127;
                }
                goto LABEL_128;
              }
              goto LABEL_132;
            }
            ++v7;
          }
          Source2 = 0;
          v34 = 0;
          CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                                (TieringHeatSession *)v35,
                                0,
                                (struct TE_FILE_ID_128 *)&Source2,
                                &v34,
                                &v27,
                                &v26,
                                0,
                                0,
                                0);
          if ( CurrentHeatRecord )
          {
            if ( CurrentHeatRecord == -1017 )
              goto LABEL_103;
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                v7,
                CurrentHeatRecord);
              goto LABEL_20;
            }
          }
          else
          {
            if ( RtlCompareMemory(&NullGuid, &Source2, 0x10u) == 16 )
              goto LABEL_103;
            if ( v29 ? (v27 & 0x50) == 0 : (v26 & 1) == 0 )
              goto LABEL_103;
            v14 = JetPrepareUpdate(sesid, tableid, 2u);
            if ( v14 == -1607 )
            {
              JetPrepareUpdate(sesid, tableid, 3u);
              v14 = JetPrepareUpdate(sesid, tableid, 2u);
            }
            v4 = 0;
            switch ( v14 )
            {
              case 0:
                if ( v29 )
                {
                  v26 |= 1u;
                  v16 = 0;
                }
                else
                {
                  v26 &= ~1u;
                  if ( (v27 & 0x50) != 0 )
                    v27 = v27 & 0xF | 0x20;
                  v16 = &v27;
                }
                v17 = TieringHeatSession::SetCurrentHeatRecord((TieringHeatSession *)v35, 0, 0, v16, &v26, 0, 0, 0);
                v19 = v17;
                if ( v17 )
                {
                  if ( v17 == -529 || v17 == -1092 || v17 == -1808 )
                  {
                    v4 = ATL::AtlHresultFromWin32(112);
                  }
                  else if ( v17 == -1011 )
                  {
                    v4 = -2147024882;
                  }
                  else
                  {
                    v20 = -v17;
                    if ( v20 < 0 )
                      LOWORD(v20) = v19;
                    v4 = v19 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
                  }
                  v33 = v4;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_DSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      82,
                      (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                      v7,
                      *(_QWORD *)(v40 + 112),
                      v19);
                  }
                  JetPrepareUpdate(sesid, tableid, 3u);
                  goto LABEL_20;
                }
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_iiiZ(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v18,
                    0,
                    DWORD2(Source2),
                    Source2,
                    v34,
                    (__int64)(this + 84));
                }
                v21 = JetUpdate(sesid, tableid, 0, 0, 0);
                v22 = v21;
                if ( v21 )
                {
                  if ( v21 == -529 || v21 == -1092 || v21 == -1808 )
                  {
                    v4 = ATL::AtlHresultFromWin32(112);
                  }
                  else if ( v21 == -1011 )
                  {
                    v4 = -2147024882;
                  }
                  else
                  {
                    v23 = -v21;
                    if ( v23 < 0 )
                      LOWORD(v23) = v22;
                    v4 = v22 & 0x8E5E0000 | (unsigned __int16)v23 | 0xE5E0000;
                  }
                  v33 = v4;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_DSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      84,
                      (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                      v7,
                      *(_QWORD *)(v40 + 112),
                      v22);
                  }
                  JetPrepareUpdate(sesid, tableid, 3u);
                  if ( v22 == -1102 )
                  {
                    Sleep(0x64u);
                    v8 = 1;
                    v28 = 1;
                    goto LABEL_20;
                  }
                }
                else
                {
                  v33 = 0;
                  ++v30;
                }
LABEL_103:
                v8 = v28;
                goto LABEL_20;
              case -529:
              case -1092:
              case -1808:
                v4 = ATL::AtlHresultFromWin32(112);
                break;
              case -1011:
                v4 = -2147024882;
                break;
              default:
                v15 = -v14;
                if ( v14 > 0 )
                  LOWORD(v15) = v14;
                v4 = v14 & 0x8E5E0000 | (unsigned __int16)v15 | 0xE5E0000;
                break;
            }
            v33 = v4;
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_DSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                81,
                (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                v7,
                *(_QWORD *)(v40 + 112),
                v14);
              goto LABEL_20;
            }
          }
        }
        v9 = WPP_GLOBAL_Control;
LABEL_123:
        if ( v9 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 5u )
          {
            WPP_SF_Z(v9[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, this + 84);
LABEL_127:
            v9 = WPP_GLOBAL_Control;
          }
LABEL_128:
          if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
            WPP_SF_DDZ(
              v9[2],
              85,
              (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
              v30,
              v7,
              (__int64)(this + 84));
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
          (_DWORD)this + 672,
          v6);
      }
LABEL_132:
      TieringJetSession::CloseJetTable((TieringJetSession *)v35, 1);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        (_DWORD)this + 672,
        v5);
    }
    CTieredVolume::DereferenceVolume((CTieredVolume *)this);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
      *((unsigned int *)this + 32),
      v3);
  }
  TieringJetSession::~TieringJetSession((TieringJetSession *)v35);
  CHResultImp::~CHResultImp((CHResultImp *)v32);
  return v4;
}

```

## disassembly

```asm
0x1400211a4  push    rbp
0x1400211a6  push    rbx
0x1400211a7  push    rsi
0x1400211a8  push    r12
0x1400211aa  push    r13
0x1400211ac  push    r14
0x1400211ae  lea     rbp, [rsp-8]
0x1400211b3  sub     rsp, 108h
0x1400211ba  mov     rax, cs:__security_cookie
0x1400211c1  xor     rax, rsp
0x1400211c4  mov     [rbp+30h+var_40], rax
0x1400211c8  mov     [rsp+130h+var_DD], dl
0x1400211cc  mov     r13, rcx
0x1400211cf  mov     edx, 8
0x1400211d4  mov     rax, gs:58h
0x1400211dd  mov     rcx, [rax]
0x1400211e0  lea     rax, aCtieredvolumeB; "CTieredVolume::BeginOrCompleteDefragRec"...
0x1400211e7  mov     [rdx+rcx], rax
0x1400211eb  lea     rcx, [rsp+130h+var_D0]; this
0x1400211f0  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x1400211f5  nop
0x1400211f6  xor     esi, esi
0x1400211f8  mov     [rbp+30h+var_B0], sil
0x1400211fc  mov     [rbp+30h+var_90], si
0x140021200  mov     [rbp+30h+var_8E], sil
0x140021204  mov     [rbp+30h+var_88], rsi
0x140021208  mov     [rbp+30h+var_80], sil
0x14002120c  xor     edx, edx; bool
0x14002120e  mov     rcx, r13; this
0x140021211  call    ?ReferenceVolume@CTieredVolume@@QEAAJ_N@Z; CTieredVolume::ReferenceVolume(bool)
0x140021216  mov     ebx, eax
0x140021218  mov     [rsp+130h+var_C8], eax
0x14002121c  test    eax, eax
0x14002121e  jns     short loc_140021270
0x140021220  lea     rsi, WPP_GLOBAL_Control
0x140021227  mov     rcx, cs:WPP_GLOBAL_Control
0x14002122e  cmp     rcx, rsi
0x140021231  jz      loc_1400219EF
0x140021237  test    byte ptr [rcx+1Ch], 1
0x14002123b  jz      loc_1400219EF
0x140021241  cmp     byte ptr [rcx+19h], 2
0x140021245  jb      loc_1400219EF
0x14002124b  mov     edx, 4Ah ; 'J'
0x140021250  mov     dword ptr [rsp+130h+pcbActual], eax
0x140021254  mov     r9d, [r13+80h]
0x14002125b  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140021262  mov     rcx, [rcx+10h]
0x140021266  call    WPP_SF_Dd
0x14002126b  jmp     loc_1400219EF
0x140021270  lea     rdx, [r13+4A0h]; struct TieringJetDatabase *
0x140021277  lea     rcx, [rbp+30h+var_B0]; this
0x14002127b  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x140021280  mov     ebx, eax
0x140021282  mov     [rsp+130h+var_C8], eax
0x140021286  test    eax, eax
0x140021288  jns     short loc_1400212DA
0x14002128a  lea     rsi, WPP_GLOBAL_Control
0x140021291  mov     rcx, cs:WPP_GLOBAL_Control
0x140021298  cmp     rcx, rsi
0x14002129b  jz      loc_1400219E6
0x1400212a1  test    byte ptr [rcx+1Ch], 1
0x1400212a5  jz      loc_1400219E6
0x1400212ab  cmp     byte ptr [rcx+19h], 2
0x1400212af  jb      loc_1400219E6
0x1400212b5  lea     r9, [r13+2A0h]
0x1400212bc  mov     edx, 4Bh ; 'K'
0x1400212c1  mov     dword ptr [rsp+130h+pcbActual], eax
0x1400212c5  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x1400212cc  mov     rcx, [rcx+10h]
0x1400212d0  call    WPP_SF_Zd
0x1400212d5  jmp     loc_1400219E6
0x1400212da  mov     dl, 1; bool
0x1400212dc  lea     rcx, [rbp+30h+var_B0]; this
0x1400212e0  call    ?OpenJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::OpenJetTable(bool)
0x1400212e5  mov     ebx, eax
0x1400212e7  mov     [rsp+130h+var_C8], eax
0x1400212eb  test    eax, eax
0x1400212ed  jns     short loc_14002133F
0x1400212ef  lea     rsi, WPP_GLOBAL_Control
0x1400212f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212fd  cmp     rcx, rsi
0x140021300  jz      loc_1400219DB
0x140021306  test    byte ptr [rcx+1Ch], 1
0x14002130a  jz      loc_1400219DB
0x140021310  cmp     byte ptr [rcx+19h], 2
0x140021314  jb      loc_1400219DB
0x14002131a  lea     r9, [r13+2A0h]
0x140021321  mov     edx, 4Ch ; 'L'
0x140021326  mov     dword ptr [rsp+130h+pcbActual], eax
0x14002132a  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140021331  mov     rcx, [rcx+10h]
0x140021335  call    WPP_SF_Zd
0x14002133a  jmp     loc_1400219DB
0x14002133f  mov     r12d, esi
0x140021342  mov     [rsp+130h+var_DC], esi
0x140021346  mov     r14b, sil
0x140021349  mov     [rsp+130h+var_DE], sil
0x14002134e  mov     [rsp+130h+var_DF], sil
0x140021353  mov     [rsp+130h+var_E0], sil
0x140021358  mov     [rsp+130h+cRow], 80000000h
0x140021360  mov     ebx, esi
0x140021362  mov     [rsp+130h+var_C8], ebx
0x140021366  lea     rsi, WPP_GLOBAL_Control
0x14002136d  mov     r10, cs:WPP_GLOBAL_Control
0x140021374  cmp     r10, rsi
0x140021377  jz      short loc_1400213AA
0x140021379  test    byte ptr [r10+1Ch], 1
0x14002137e  jz      short loc_1400213AA
0x140021380  cmp     byte ptr [r10+19h], 4
0x140021385  jb      short loc_1400213AA
0x140021387  lea     r9, [r13+2A0h]
0x14002138e  mov     edx, 4Dh ; 'M'
0x140021393  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x14002139a  mov     rcx, [r10+10h]
0x14002139e  call    WPP_SF_Z
0x1400213a3  mov     r10, cs:WPP_GLOBAL_Control
0x1400213aa  cmp     byte ptr [r13+0A5h], 0
0x1400213b2  jnz     loc_140021967
0x1400213b8  cmp     byte ptr [r13+0A6h], 0
0x1400213c0  jnz     loc_140021967
0x1400213c6  xor     edx, edx; dwMilliseconds
0x1400213c8  mov     rcx, [r13+300h]; hHandle
0x1400213cf  call    cs:__imp_WaitForSingleObject
0x1400213d5  cmp     eax, 102h
0x1400213da  jnz     loc_140021960
0x1400213e0  xor     edx, edx; dwMilliseconds
0x1400213e2  mov     rcx, [r13+2F8h]; hHandle
0x1400213e9  call    cs:__imp_WaitForSingleObject
0x1400213ef  cmp     eax, 102h
0x1400213f4  jnz     loc_140021960
0x1400213fa  mov     rax, [rbp+30h+var_88]
0x1400213fe  xor     ecx, ecx
0x140021400  cmp     [rax+4Dh], cl
0x140021403  jz      short loc_14002140E
0x140021405  cmp     [rax+4Ch], cl
0x140021408  jnz     loc_140021996
0x14002140e  test    r14b, r14b
0x140021411  jnz     short loc_14002146F
0x140021413  xor     r9d, r9d; grbit
0x140021416  mov     r8d, [rsp+130h+cRow]; cRow
0x14002141b  mov     rdx, [rbp+30h+tableid]; tableid
0x14002141f  mov     rcx, [rbp+30h+sesid]; sesid
0x140021423  call    cs:__imp_JetMove
0x140021429  mov     r9d, eax
0x14002142c  cmp     eax, 0FFFFF9BFh
0x140021431  jz      loc_140021922
0x140021437  cmp     eax, 40Fh
0x14002143c  jz      loc_140021922
0x140021442  cmp     eax, 0FFFFF9BDh
0x140021447  jz      loc_140021922
0x14002144d  mov     [rsp+130h+cRow], 1
0x140021455  cmp     eax, 0FFFFFC07h
0x14002145a  jz      loc_140021885
0x140021460  xor     ecx, ecx
0x140021462  test    eax, eax
0x140021464  jnz     loc_14002188F
0x14002146a  inc     r12d
0x14002146d  jmp     short loc_140021476
0x14002146f  mov     r14b, cl
0x140021472  mov     [rsp+130h+var_DE], cl
0x140021476  xorps   xmm0, xmm0
0x140021479  movups  [rbp+30h+Source2], xmm0
0x14002147d  mov     [rsp+130h+var_C0], rcx
0x140021482  mov     [rsp+130h+var_F0], rcx; unsigned __int16 *
0x140021487  mov     [rsp+130h+var_F8], rcx; unsigned __int16 *
0x14002148c  mov     [rsp+130h+var_100], rcx; unsigned __int8 *
0x140021491  lea     rax, [rsp+130h+var_E0]
0x140021496  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x14002149b  lea     rax, [rsp+130h+var_DF]
0x1400214a0  mov     [rsp+130h+pcbActual], rax; unsigned __int8 *
0x1400214a5  lea     r9, [rsp+130h+var_C0]; __int64 *
0x1400214aa  lea     r8, [rbp+30h+Source2]; struct TE_FILE_ID_128 *
0x1400214ae  xor     edx, edx; bool
0x1400214b0  lea     rcx, [rbp+30h+var_B0]; this
0x1400214b4  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x1400214b9  test    eax, eax
0x1400214bb  jz      short loc_14002150F
0x1400214bd  cmp     eax, 0FFFFFC07h
0x1400214c2  jz      loc_140021885
0x1400214c8  mov     r10, cs:WPP_GLOBAL_Control
0x1400214cf  cmp     r10, rsi
0x1400214d2  jz      loc_1400213AA
0x1400214d8  test    byte ptr [r10+1Ch], 1
0x1400214dd  jz      loc_1400213AA
0x1400214e3  cmp     byte ptr [r10+19h], 2
0x1400214e8  jb      loc_1400213AA
0x1400214ee  mov     edx, 50h ; 'P'
0x1400214f3  mov     dword ptr [rsp+130h+pcbActual], eax
0x1400214f7  mov     r9d, r12d
0x1400214fa  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140021501  mov     rcx, [r10+10h]
0x140021505  call    WPP_SF_Dd
0x14002150a  jmp     loc_1400213A3
0x14002150f  mov     r8d, 10h; Length
0x140021515  lea     rdx, [rbp+30h+Source2]; Source2
0x140021519  lea     rcx, ?NullGuid@@3U_GUID@@A; Source1
0x140021520  call    cs:__imp_RtlCompareMemory
0x140021526  cmp     rax, 10h
0x14002152a  jz      loc_140021885
0x140021530  cmp     [rsp+130h+var_DD], 0
0x140021535  jz      short loc_14002153E
0x140021537  test    [rsp+130h+var_DF], 50h
0x14002153c  jmp     short loc_140021543
0x14002153e  test    [rsp+130h+var_E0], 1
0x140021543  jz      loc_140021885
0x140021549  mov     r8d, 2; prep
0x14002154f  mov     rdx, [rbp+30h+tableid]; tableid
0x140021553  mov     rcx, [rbp+30h+sesid]; sesid
0x140021557  call    cs:__imp_JetPrepareUpdate
0x14002155d  mov     r8d, eax
0x140021560  cmp     eax, 0FFFFF9B9h
0x140021565  jnz     short loc_140021592
0x140021567  mov     r8d, 3; prep
0x14002156d  mov     rdx, [rbp+30h+tableid]; tableid
0x140021571  mov     rcx, [rbp+30h+sesid]; sesid
0x140021575  call    cs:__imp_JetPrepareUpdate
0x14002157b  mov     r8d, 2; prep
0x140021581  mov     rdx, [rbp+30h+tableid]; tableid
0x140021585  mov     rcx, [rbp+30h+sesid]; sesid
0x140021589  call    cs:__imp_JetPrepareUpdate
0x14002158f  mov     r8d, eax
0x140021592  xor     ebx, ebx
0x140021594  test    r8d, r8d
0x140021597  jz      loc_14002164B
0x14002159d  cmp     r8d, 0FFFFFDEFh
0x1400215a4  jz      short loc_1400215E6
0x1400215a6  cmp     r8d, 0FFFFFBBCh
0x1400215ad  jz      short loc_1400215E6
0x1400215af  cmp     r8d, 0FFFFF8F0h
0x1400215b6  jz      short loc_1400215E6
0x1400215b8  cmp     r8d, 0FFFFFC0Dh
0x1400215bf  jnz     short loc_1400215C8
0x1400215c1  mov     ebx, 8007000Eh
0x1400215c6  jmp     short loc_1400215F2
0x1400215c8  mov     eax, r8d
0x1400215cb  neg     eax
0x1400215cd  cmovs   eax, r8d
0x1400215d1  movzx   ebx, ax
0x1400215d4  mov     eax, r8d
0x1400215d7  and     eax, 8E5E0000h
0x1400215dc  or      ebx, eax
0x1400215de  or      ebx, 0E5E0000h
0x1400215e4  jmp     short loc_1400215F2
0x1400215e6  mov     ecx, 70h ; 'p'; unsigned int
0x1400215eb  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400215f0  mov     ebx, eax
0x1400215f2  mov     [rsp+130h+var_C8], ebx
0x1400215f6  mov     r10, cs:WPP_GLOBAL_Control
0x1400215fd  cmp     r10, rsi
0x140021600  jz      loc_1400213AA
0x140021606  test    byte ptr [r10+1Ch], 1
0x14002160b  jz      loc_1400213AA
0x140021611  cmp     byte ptr [r10+19h], 2
0x140021616  jb      loc_1400213AA
0x14002161c  mov     edx, 51h ; 'Q'
0x140021621  mov     dword ptr [rsp+130h+var_108], r8d
0x140021626  mov     rax, [rbp+30h+var_88]
0x14002162a  mov     rcx, [rax+70h]
0x14002162e  mov     [rsp+130h+pcbActual], rcx
0x140021633  mov     r9d, r12d
0x140021636  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x14002163d  mov     rcx, [r10+10h]
0x140021641  call    WPP_SF_DSd
0x140021646  jmp     loc_1400213A3
0x14002164b  cmp     [rsp+130h+var_DD], bl
0x14002164f  jz      short loc_14002165B
0x140021651  or      [rsp+130h+var_E0], 1
0x140021656  mov     r9, rbx
0x140021659  jmp     short loc_140021675
0x14002165b  and     [rsp+130h+var_E0], 0FEh
0x140021660  mov     al, [rsp+130h+var_DF]
0x140021664  test    al, 50h
0x140021666  jz      short loc_140021670
0x140021668  and     al, 0Fh
0x14002166a  or      al, 20h
0x14002166c  mov     [rsp+130h+var_DF], al
0x140021670  lea     r9, [rsp+130h+var_DF]; unsigned __int8 *
0x140021675  mov     [rsp+130h+var_F8], rbx; unsigned __int16 *
0x14002167a  mov     [rsp+130h+var_100], rbx; unsigned __int16 *
0x14002167f  mov     [rsp+130h+var_108], rbx; unsigned __int8 *
0x140021684  lea     rax, [rsp+130h+var_E0]
0x140021689  mov     [rsp+130h+pcbActual], rax; unsigned __int8 *
0x14002168e  xor     r8d, r8d; __int64 *
0x140021691  xor     edx, edx; struct TE_FILE_ID_128 *
0x140021693  lea     rcx, [rbp+30h+var_B0]; this
0x140021697  call    ?SetCurrentHeatRecord@TieringHeatSession@@QEAAJPEAUTE_FILE_ID_128@@PEA_JPEAE22PEAG3@Z; TieringHeatSession::SetCurrentHeatRecord(TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002169c  mov     r8d, eax
0x14002169f  test    eax, eax
0x1400216a1  jz      loc_140021750
0x1400216a7  cmp     eax, 0FFFFFDEFh
0x1400216ac  jz      short loc_1400216E5
0x1400216ae  cmp     eax, 0FFFFFBBCh
0x1400216b3  jz      short loc_1400216E5
0x1400216b5  cmp     eax, 0FFFFF8F0h
0x1400216ba  jz      short loc_1400216E5
0x1400216bc  cmp     eax, 0FFFFFC0Dh
0x1400216c1  jnz     short loc_1400216CA
0x1400216c3  mov     ebx, 8007000Eh
0x1400216c8  jmp     short loc_1400216F1
0x1400216ca  neg     eax
  ... truncated ...
```
