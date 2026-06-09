# TieringHeatSession::ClearPinnedFlagForFileId(TE_FILE_ID_128 const *)

- ea: `0x140027908`
- end: `0x1400280b6`
- name: `?ClearPinnedFlagForFileId@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@@Z`
- size: `1966`
- prototype: `__int64 __fastcall(TieringHeatSession *__hidden this, const struct TE_FILE_ID_128 *Source2)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c648`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140020e1c`
- `0x140021018`
- `0x140027908`
- `0x14002866c`
- `0x140029dec`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x140027d31`
- `ntdll!RtlCompareMemory` at `0x140027d31`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140027ea2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140027ea2`
- `ESENT!JetPrepareUpdate` at `0x140027b28`
- `ESENT!JetPrepareUpdate` at `0x140027b45`
- `ESENT!JetPrepareUpdate` at `0x140027b59`
- `ESENT!JetPrepareUpdate` at `0x140027d02`
- `ESENT!JetPrepareUpdate` at `0x140027e8b`
- `ESENT!JetPrepareUpdate` at `0x140027ec3`
- `ESENT!JetPrepareUpdate` at `0x140027f3e`
- `ESENT!JetPrepareUpdate` at `0x140027b28`
- `ESENT!JetPrepareUpdate` at `0x140027b45`
- `ESENT!JetPrepareUpdate` at `0x140027b59`
- `ESENT!JetPrepareUpdate` at `0x140027d02`
- `ESENT!JetPrepareUpdate` at `0x140027e8b`
- `ESENT!JetPrepareUpdate` at `0x140027ec3`
- `ESENT!JetPrepareUpdate` at `0x140027f3e`
- `ESENT!JetUpdate` at `0x140027dd9`
- `ESENT!JetUpdate` at `0x140027dd9`
- `ESENT!JetMove` at `0x140027ee9`
- `ESENT!JetMove` at `0x140027ee9`
- `ESENT!JetMakeKey` at `0x140027974`
- `ESENT!JetMakeKey` at `0x140027974`
- `ESENT!JetSeek` at `0x140027a15`
- `ESENT!JetSeek` at `0x140027a15`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::ClearPinnedFlagForFileId(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *Source2)
{
  JET_ERR Key; // eax
  JET_ERR v5; // r8d
  unsigned int v6; // edi
  int v7; // eax
  _QWORD *v8; // rcx
  int v9; // edx
  JET_ERR v10; // eax
  int v11; // eax
  unsigned int v13; // ebx
  char v14; // r15
  JET_ERR v15; // esi
  int v16; // eax
  _QWORD *v17; // r10
  JET_ERR CurrentHeatRecord; // eax
  int v19; // eax
  int v20; // eax
  JET_ERR v21; // eax
  int v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // r8d
  int v25; // eax
  unsigned __int8 v26; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int8 v27; // [rsp+51h] [rbp-2Fh] BYREF
  char v28; // [rsp+52h] [rbp-2Eh]
  _BYTE v29[8]; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-20h]
  __int128 Source1; // [rsp+68h] [rbp-18h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::ClearPinnedFlagForFileId";
  CHResultImp::CHResultImp((CHResultImp *)v29);
  Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), Source2, 0x10u, 1u);
  v5 = Key;
  if ( Key )
  {
    if ( Key == -529 || Key == -1092 || Key == -1808 )
    {
      v6 = ATL::AtlHresultFromWin32(112);
    }
    else if ( Key == -1011 )
    {
      v6 = -2147024882;
    }
    else
    {
      v7 = -Key;
      if ( v7 < 0 )
        LOWORD(v7) = v5;
      v6 = v5 & 0x8E5E0000 | (unsigned __int16)v7 | 0xE5E0000;
    }
    v30 = v6;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v9 = 89;
LABEL_31:
    WPP_SF_iiSd(
      v8[2],
      v9,
      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
      *((_QWORD *)Source2 + 1),
      *(_QWORD *)Source2,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v5);
LABEL_32:
    CHResultImp::~CHResultImp((CHResultImp *)v29);
    return v6;
  }
  v10 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 8u);
  v5 = v10;
  if ( ((v10 + 1603) & 0xFFFFFFFD) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v10);
    }
    v30 = 0;
    CHResultImp::~CHResultImp((CHResultImp *)v29);
    return 0;
  }
  if ( v10 && v10 != 1039 )
  {
    if ( v10 == -529 || v10 == -1092 || v10 == -1808 )
    {
      v6 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v10 == -1011 )
    {
      v6 = -2147024882;
    }
    else
    {
      v11 = -v10;
      if ( v11 < 0 )
        LOWORD(v11) = v5;
      v6 = v5 & 0x8E5E0000 | (unsigned __int16)v11 | 0xE5E0000;
    }
    v30 = v6;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v9 = 91;
    goto LABEL_31;
  }
  v13 = v30;
  v14 = 0;
  v28 = 0;
  while ( 2 )
  {
    v26 = 0;
    Source1 = 0;
    v27 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v15 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
        if ( v15 == -1607 )
        {
          JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
          v15 = JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 2u);
        }
        if ( v15 )
        {
          if ( v15 == -529 || v15 == -1092 || v15 == -1808 )
          {
            v13 = ATL::AtlHresultFromWin32(112);
          }
          else if ( v15 == -1011 )
          {
            v13 = -2147024882;
          }
          else
          {
            v16 = -v15;
            if ( v15 > 0 )
              LOWORD(v16) = v15;
            v13 = v15 & 0x8E5E0000 | (unsigned __int16)v16 | 0xE5E0000;
          }
          v30 = v13;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              92,
              (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
              *((_QWORD *)Source2 + 1),
              *(_QWORD *)Source2,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
              v15);
            v17 = WPP_GLOBAL_Control;
          }
          v28 = 1;
          goto LABEL_69;
        }
        CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                              this,
                              1,
                              (struct TE_FILE_ID_128 *)&Source1,
                              0,
                              &v27,
                              &v26,
                              0,
                              0,
                              0);
        v15 = CurrentHeatRecord;
        if ( CurrentHeatRecord == -1017 )
        {
          JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
          goto LABEL_95;
        }
        v13 = 0;
        if ( !CurrentHeatRecord )
          break;
        if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
        {
          v13 = ATL::AtlHresultFromWin32(112);
        }
        else if ( CurrentHeatRecord == -1011 )
        {
          v13 = -2147024882;
        }
        else
        {
          v19 = -CurrentHeatRecord;
          if ( v19 < 0 )
            LOWORD(v19) = v15;
          v13 = v15 & 0x8E5E0000 | (unsigned __int16)v19 | 0xE5E0000;
        }
        v30 = v13;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            93,
            (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
            *((_QWORD *)Source2 + 1),
            *(_QWORD *)Source2,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v15);
        }
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        v28 = 1;
LABEL_68:
        v17 = WPP_GLOBAL_Control;
LABEL_69:
        if ( v15 != -1102 )
          goto LABEL_96;
      }
      if ( RtlCompareMemory(&Source1, Source2, 0x10u) != 16 )
      {
        JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
        goto LABEL_115;
      }
      v27 &= 0xFu;
      v26 &= 0xF3u;
      v20 = TieringHeatSession::SetCurrentHeatRecord(this, 0, 0, &v27, &v26, 0, 0, 0);
      if ( v20
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
          *((_QWORD *)Source2 + 1),
          *(_QWORD *)Source2,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v20);
      }
      v21 = JetUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 0, 0, 0);
      v15 = v21;
      if ( !v21 )
        break;
      if ( v21 == -529 || v21 == -1092 || v21 == -1808 )
      {
        v13 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v21 == -1011 )
      {
        v13 = -2147024882;
      }
      else
      {
        v22 = -v21;
        if ( v22 < 0 )
          LOWORD(v22) = v15;
        v13 = v15 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
      }
      v30 = v13;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
          *((_QWORD *)Source2 + 1),
          *(_QWORD *)Source2,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v15);
      }
      JetPrepareUpdate(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 3u);
      if ( v15 != -1102 )
        goto LABEL_68;
      Sleep(0x64u);
    }
    v30 = 0;
    ++v14;
LABEL_95:
    v17 = WPP_GLOBAL_Control;
LABEL_96:
    if ( v28 )
      goto LABEL_117;
    v23 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
    v24 = v23;
    switch ( v23 )
    {
      case -1603:
        v13 = 0;
LABEL_115:
        v30 = 0;
LABEL_116:
        v17 = WPP_GLOBAL_Control;
LABEL_117:
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 5u )
          WPP_SF_iiDS(
            v17[2],
            97,
            (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
            *((_QWORD *)Source2 + 1),
            *(_QWORD *)Source2,
            v14,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        goto LABEL_121;
      case 0:
      case -1017:
        continue;
      case -529:
      case -1092:
      case -1808:
        v13 = ATL::AtlHresultFromWin32(112);
        break;
      case -1011:
        v13 = -2147024882;
        break;
      default:
        v25 = -v23;
        if ( v25 < 0 )
          LOWORD(v25) = v24;
        v13 = v24 & 0x8E5E0000 | (unsigned __int16)v25 | 0xE5E0000;
        break;
    }
    break;
  }
  v30 = v13;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v24);
      goto LABEL_116;
    }
    goto LABEL_117;
  }
LABEL_121:
  CHResultImp::~CHResultImp((CHResultImp *)v29);
  return v13;
}

```

## disassembly

```asm
0x140027908  mov     [rsp-38h+arg_10], rbx
0x14002790d  push    rbp
0x14002790e  push    rsi
0x14002790f  push    rdi
0x140027910  push    r12
0x140027912  push    r13
0x140027914  push    r14
0x140027916  push    r15
0x140027918  mov     rbp, rsp
0x14002791b  sub     rsp, 80h
0x140027922  mov     rax, cs:__security_cookie
0x140027929  xor     rax, rsp
0x14002792c  mov     [rbp+var_8], rax
0x140027930  mov     rax, gs:58h
0x140027939  mov     r14, rcx
0x14002793c  mov     r12, rdx
0x14002793f  mov     ecx, 8
0x140027944  mov     rdx, [rax]
0x140027947  lea     rax, aTieringheatses_2; "TieringHeatSession::ClearPinnedFlagForF"...
0x14002794e  mov     [rcx+rdx], rax
0x140027952  lea     rcx, [rbp+var_28]; this
0x140027956  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002795b  mov     rdx, [r14+18h]; tableid
0x14002795f  mov     r9d, 10h; cbData
0x140027965  mov     rcx, [r14+8]; sesid
0x140027969  mov     r8, r12; pvData
0x14002796c  mov     [rsp+80h+grbit], 1; grbit
0x140027974  call    cs:__imp_JetMakeKey
0x14002797a  mov     r8d, eax
0x14002797d  test    eax, eax
0x14002797f  jz      loc_140027A07
0x140027985  cmp     eax, 0FFFFFDEFh
0x14002798a  jz      short loc_1400279C3
0x14002798c  cmp     eax, 0FFFFFBBCh
0x140027991  jz      short loc_1400279C3
0x140027993  cmp     eax, 0FFFFF8F0h
0x140027998  jz      short loc_1400279C3
0x14002799a  cmp     eax, 0FFFFFC0Dh
0x14002799f  jnz     short loc_1400279A8
0x1400279a1  mov     edi, 8007000Eh
0x1400279a6  jmp     short loc_1400279CF
0x1400279a8  neg     eax
0x1400279aa  cmovs   eax, r8d
0x1400279ae  movzx   edi, ax
0x1400279b1  mov     eax, r8d
0x1400279b4  and     eax, 8E5E0000h
0x1400279b9  or      edi, eax
0x1400279bb  or      edi, 0E5E0000h
0x1400279c1  jmp     short loc_1400279CF
0x1400279c3  mov     ecx, 70h ; 'p'; unsigned int
0x1400279c8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400279cd  mov     edi, eax
0x1400279cf  mov     [rbp+var_20], edi
0x1400279d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400279d9  lea     r13, WPP_GLOBAL_Control
0x1400279e0  cmp     rcx, r13
0x1400279e3  jz      loc_140027AE4
0x1400279e9  test    byte ptr [rcx+1Ch], 1
0x1400279ed  jz      loc_140027AE4
0x1400279f3  cmp     byte ptr [rcx+19h], 2
0x1400279f7  jb      loc_140027AE4
0x1400279fd  mov     edx, 59h ; 'Y'
0x140027a02  jmp     loc_140027AB4
0x140027a07  mov     rdx, [r14+18h]; tableid
0x140027a0b  mov     r8d, 8; grbit
0x140027a11  mov     rcx, [r14+8]; sesid
0x140027a15  call    cs:__imp_JetSeek
0x140027a1b  mov     r8d, eax
0x140027a1e  lea     ecx, [rax+643h]
0x140027a24  test    ecx, 0FFFFFFFDh
0x140027a2a  jz      loc_140028029
0x140027a30  test    eax, eax
0x140027a32  jz      loc_140027AF4
0x140027a38  cmp     eax, 40Fh
0x140027a3d  jz      loc_140027AF4
0x140027a43  cmp     eax, 0FFFFFDEFh
0x140027a48  jz      short loc_140027A81
0x140027a4a  cmp     eax, 0FFFFFBBCh
0x140027a4f  jz      short loc_140027A81
0x140027a51  cmp     eax, 0FFFFF8F0h
0x140027a56  jz      short loc_140027A81
0x140027a58  cmp     eax, 0FFFFFC0Dh
0x140027a5d  jnz     short loc_140027A66
0x140027a5f  mov     edi, 8007000Eh
0x140027a64  jmp     short loc_140027A8D
0x140027a66  neg     eax
0x140027a68  cmovs   eax, r8d
0x140027a6c  movzx   edi, ax
0x140027a6f  mov     eax, r8d
0x140027a72  and     eax, 8E5E0000h
0x140027a77  or      edi, eax
0x140027a79  or      edi, 0E5E0000h
0x140027a7f  jmp     short loc_140027A8D
0x140027a81  mov     ecx, 70h ; 'p'; unsigned int
0x140027a86  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140027a8b  mov     edi, eax
0x140027a8d  mov     [rbp+var_20], edi
0x140027a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a97  lea     r13, WPP_GLOBAL_Control
0x140027a9e  cmp     rcx, r13
0x140027aa1  jz      short loc_140027AE4
0x140027aa3  test    byte ptr [rcx+1Ch], 1
0x140027aa7  jz      short loc_140027AE4
0x140027aa9  cmp     byte ptr [rcx+19h], 2
0x140027aad  jb      short loc_140027AE4
0x140027aaf  mov     edx, 5Bh ; '['
0x140027ab4  mov     rax, [r14+28h]
0x140027ab8  mov     r9, [r12+8]
0x140027abd  mov     rcx, [rcx+10h]
0x140027ac1  mov     dword ptr [rsp+80h+var_50], r8d
0x140027ac6  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140027acd  mov     rax, [rax+70h]
0x140027ad1  mov     [rsp+80h+var_58], rax
0x140027ad6  mov     rax, [r12]
0x140027ada  mov     qword ptr [rsp+80h+grbit], rax
0x140027adf  call    WPP_SF_iiSd
0x140027ae4  lea     rcx, [rbp+var_28]; this
0x140027ae8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140027aed  mov     eax, edi
0x140027aef  jmp     loc_14002808F
0x140027af4  mov     ebx, [rbp+var_20]
0x140027af7  lea     r13, WPP_GLOBAL_Control
0x140027afe  xor     r15d, r15d
0x140027b01  mov     edi, 8007000Eh
0x140027b06  xor     al, al
0x140027b08  mov     [rbp+var_2E], al
0x140027b0b  xorps   xmm0, xmm0
0x140027b0e  mov     [rbp+var_30], 0
0x140027b12  movups  [rbp+Source1], xmm0
0x140027b16  mov     [rbp+var_2F], 0
0x140027b1a  mov     rdx, [r14+18h]; tableid
0x140027b1e  mov     r8d, 2; prep
0x140027b24  mov     rcx, [r14+8]; sesid
0x140027b28  call    cs:__imp_JetPrepareUpdate
0x140027b2e  mov     esi, eax
0x140027b30  cmp     eax, 0FFFFF9B9h
0x140027b35  jnz     short loc_140027B61
0x140027b37  mov     rdx, [r14+18h]; tableid
0x140027b3b  mov     r8d, 3; prep
0x140027b41  mov     rcx, [r14+8]; sesid
0x140027b45  call    cs:__imp_JetPrepareUpdate
0x140027b4b  mov     rdx, [r14+18h]; tableid
0x140027b4f  mov     r8d, 2; prep
0x140027b55  mov     rcx, [r14+8]; sesid
0x140027b59  call    cs:__imp_JetPrepareUpdate
0x140027b5f  mov     esi, eax
0x140027b61  xor     eax, eax
0x140027b63  test    esi, esi
0x140027b65  jz      loc_140027C17
0x140027b6b  cmp     esi, 0FFFFFDEFh
0x140027b71  jz      short loc_140027BAA
0x140027b73  cmp     esi, 0FFFFFBBCh
0x140027b79  jz      short loc_140027BAA
0x140027b7b  cmp     esi, 0FFFFF8F0h
0x140027b81  jz      short loc_140027BAA
0x140027b83  cmp     esi, 0FFFFFC0Dh
0x140027b89  jnz     short loc_140027B8F
0x140027b8b  mov     ebx, edi
0x140027b8d  jmp     short loc_140027BB6
0x140027b8f  mov     eax, esi
0x140027b91  neg     eax
0x140027b93  cmovs   eax, esi
0x140027b96  movzx   ebx, ax
0x140027b99  mov     eax, esi
0x140027b9b  and     eax, 8E5E0000h
0x140027ba0  or      ebx, eax
0x140027ba2  or      ebx, 0E5E0000h
0x140027ba8  jmp     short loc_140027BB6
0x140027baa  mov     ecx, 70h ; 'p'; unsigned int
0x140027baf  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140027bb4  mov     ebx, eax
0x140027bb6  mov     [rbp+var_20], ebx
0x140027bb9  mov     r10, cs:WPP_GLOBAL_Control
0x140027bc0  cmp     r10, r13
0x140027bc3  jz      short loc_140027C0E
0x140027bc5  test    byte ptr [r10+1Ch], 1
0x140027bca  jz      short loc_140027C0E
0x140027bcc  cmp     byte ptr [r10+19h], 2
0x140027bd1  jb      short loc_140027C0E
0x140027bd3  mov     rax, [r14+28h]
0x140027bd7  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140027bde  mov     r9, [r12+8]
0x140027be3  mov     edx, 5Ch ; '\'
0x140027be8  mov     rcx, [r10+10h]
0x140027bec  mov     dword ptr [rsp+80h+var_50], esi
0x140027bf0  mov     rax, [rax+70h]
0x140027bf4  mov     [rsp+80h+var_58], rax
0x140027bf9  mov     rax, [r12]
0x140027bfd  mov     qword ptr [rsp+80h+grbit], rax
0x140027c02  call    WPP_SF_iiSd
0x140027c07  mov     r10, cs:WPP_GLOBAL_Control
0x140027c0e  mov     [rbp+var_2E], 1
0x140027c12  jmp     loc_140027D13
0x140027c17  mov     [rsp+80h+var_40], rax; unsigned __int16 *
0x140027c1c  lea     r8, [rbp+Source1]; struct TE_FILE_ID_128 *
0x140027c20  mov     [rsp+80h+var_48], rax; unsigned __int16 *
0x140027c25  xor     r9d, r9d; __int64 *
0x140027c28  mov     [rsp+80h+var_50], rax; unsigned __int8 *
0x140027c2d  mov     dl, 1; bool
0x140027c2f  lea     rax, [rbp+var_30]
0x140027c33  mov     rcx, r14; this
0x140027c36  mov     [rsp+80h+var_58], rax; unsigned __int8 *
0x140027c3b  lea     rax, [rbp+var_2F]
0x140027c3f  mov     qword ptr [rsp+80h+grbit], rax; unsigned __int8 *
0x140027c44  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x140027c49  mov     esi, eax
0x140027c4b  cmp     eax, 0FFFFFC07h
0x140027c50  jz      loc_140027EB5
0x140027c56  xor     ebx, ebx
0x140027c58  test    eax, eax
0x140027c5a  jz      loc_140027D24
0x140027c60  cmp     eax, 0FFFFFDEFh
0x140027c65  jz      short loc_140027C99
0x140027c67  cmp     eax, 0FFFFFBBCh
0x140027c6c  jz      short loc_140027C99
0x140027c6e  cmp     eax, 0FFFFF8F0h
0x140027c73  jz      short loc_140027C99
0x140027c75  cmp     eax, 0FFFFFC0Dh
0x140027c7a  jnz     short loc_140027C80
0x140027c7c  mov     ebx, edi
0x140027c7e  jmp     short loc_140027CA5
0x140027c80  neg     eax
0x140027c82  cmovs   eax, esi
0x140027c85  movzx   ebx, ax
0x140027c88  mov     eax, esi
0x140027c8a  and     eax, 8E5E0000h
0x140027c8f  or      ebx, eax
0x140027c91  or      ebx, 0E5E0000h
0x140027c97  jmp     short loc_140027CA5
0x140027c99  mov     ecx, 70h ; 'p'; unsigned int
0x140027c9e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140027ca3  mov     ebx, eax
0x140027ca5  mov     [rbp+var_20], ebx
0x140027ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x140027caf  cmp     rcx, r13
0x140027cb2  jz      short loc_140027CF4
0x140027cb4  test    byte ptr [rcx+1Ch], 1
0x140027cb8  jz      short loc_140027CF4
0x140027cba  cmp     byte ptr [rcx+19h], 2
0x140027cbe  jb      short loc_140027CF4
0x140027cc0  mov     rax, [r14+28h]
0x140027cc4  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140027ccb  mov     r9, [r12+8]
0x140027cd0  mov     edx, 5Dh ; ']'
0x140027cd5  mov     rcx, [rcx+10h]
0x140027cd9  mov     dword ptr [rsp+80h+var_50], esi
0x140027cdd  mov     rax, [rax+70h]
0x140027ce1  mov     [rsp+80h+var_58], rax
0x140027ce6  mov     rax, [r12]
0x140027cea  mov     qword ptr [rsp+80h+grbit], rax
0x140027cef  call    WPP_SF_iiSd
0x140027cf4  mov     rdx, [r14+18h]; tableid
0x140027cf8  mov     r8d, 3; prep
0x140027cfe  mov     rcx, [r14+8]; sesid
0x140027d02  call    cs:__imp_JetPrepareUpdate
0x140027d08  mov     [rbp+var_2E], 1
0x140027d0c  mov     r10, cs:WPP_GLOBAL_Control
0x140027d13  cmp     esi, 0FFFFFBB2h
0x140027d19  jz      loc_140027B1A
0x140027d1f  jmp     loc_140027ED0
0x140027d24  mov     r8d, 10h; Length
0x140027d2a  lea     rcx, [rbp+Source1]; Source1
0x140027d2e  mov     rdx, r12; Source2
0x140027d31  call    cs:__imp_RtlCompareMemory
0x140027d37  cmp     rax, 10h
0x140027d3b  jnz     loc_140027F30
0x140027d41  and     [rbp+var_2F], 0Fh
0x140027d45  lea     rax, [rbp+var_30]
0x140027d49  and     [rbp+var_30], 0F3h
0x140027d4d  lea     r9, [rbp+var_2F]; unsigned __int8 *
0x140027d51  mov     [rsp+80h+var_48], rbx; unsigned __int16 *
0x140027d56  xor     r8d, r8d; __int64 *
0x140027d59  mov     [rsp+80h+var_50], rbx; unsigned __int16 *
0x140027d5e  xor     edx, edx; struct TE_FILE_ID_128 *
0x140027d60  mov     [rsp+80h+var_58], rbx; unsigned __int8 *
0x140027d65  mov     rcx, r14; this
0x140027d68  mov     qword ptr [rsp+80h+grbit], rax; unsigned __int8 *
0x140027d6d  call    ?SetCurrentHeatRecord@TieringHeatSession@@QEAAJPEAUTE_FILE_ID_128@@PEA_JPEAE22PEAG3@Z; TieringHeatSession::SetCurrentHeatRecord(TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x140027d72  mov     r8d, eax
0x140027d75  test    eax, eax
0x140027d77  jz      short loc_140027DC6
0x140027d79  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d80  cmp     rcx, r13
0x140027d83  jz      short loc_140027DC6
0x140027d85  test    byte ptr [rcx+1Ch], 1
0x140027d89  jz      short loc_140027DC6
0x140027d8b  cmp     byte ptr [rcx+19h], 2
0x140027d8f  jb      short loc_140027DC6
0x140027d91  mov     rax, [r14+28h]
0x140027d95  mov     edx, 5Eh ; '^'
0x140027d9a  mov     r9, [r12+8]
0x140027d9f  mov     rcx, [rcx+10h]
0x140027da3  mov     dword ptr [rsp+80h+var_50], r8d
0x140027da8  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140027daf  mov     rax, [rax+70h]
0x140027db3  mov     [rsp+80h+var_58], rax
0x140027db8  mov     rax, [r12]
0x140027dbc  mov     qword ptr [rsp+80h+grbit], rax
0x140027dc1  call    WPP_SF_iiSd
0x140027dc6  mov     rdx, [r14+18h]; tableid
  ... truncated ...
```
