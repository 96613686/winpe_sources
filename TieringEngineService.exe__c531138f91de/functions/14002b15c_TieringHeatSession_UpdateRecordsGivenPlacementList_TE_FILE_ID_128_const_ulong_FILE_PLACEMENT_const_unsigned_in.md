# TieringHeatSession::UpdateRecordsGivenPlacementList(TE_FILE_ID_128 const *,ulong,_FILE_PLACEMENT const *,unsigned __int64,int,int,int)

- ea: `0x14002b15c`
- end: `0x14002b75d`
- name: `?UpdateRecordsGivenPlacementList@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@KPEBU_FILE_PLACEMENT@@_KHHH@Z`
- size: `1537`
- prototype: `__int64 __fastcall(TieringHeatSession *this, const struct TE_FILE_ID_128 *, unsigned int, const struct _FILE_PLACEMENT *, unsigned __int64, int, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002fd94`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140020e1c`
- `0x140021018`
- `0x14002866c`
- `0x14002a8e4`
- `0x14002b15c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14002b3f3`
- `ntdll!RtlCompareMemory` at `0x14002b3f3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002b4f7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14002b4f7`
- `ESENT!JetMove` at `0x14002b529`
- `ESENT!JetMove` at `0x14002b529`
- `ESENT!JetMakeKey` at `0x14002b1e1`
- `ESENT!JetMakeKey` at `0x14002b1e1`
- `ESENT!JetSeek` at `0x14002b282`
- `ESENT!JetSeek` at `0x14002b282`

## string_xrefs

- `0x14002b1a1`: `TieringHeatSession::UpdateRecordsGivenPlacementList`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::UpdateRecordsGivenPlacementList(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *a2,
        unsigned int a3,
        const struct _FILE_PLACEMENT *a4,
        unsigned __int64 a5,
        int a6,
        int a7,
        int a8)
{
  PVOID ThreadLocalStoragePointer; // rax
  JET_ERR Key; // eax
  JET_ERR v12; // r8d
  unsigned int v13; // ebx
  int v14; // eax
  _QWORD *v15; // rcx
  int v16; // edx
  JET_ERR v17; // eax
  int v18; // eax
  JET_ERR CurrentHeatRecord; // eax
  JET_ERR v21; // edi
  int updated; // eax
  int v23; // edi
  int v24; // ecx
  int v25; // eax
  JET_ERR v26; // eax
  JET_ERR v27; // r8d
  int v28; // eax
  int v29; // eax
  _QWORD *v30; // r10
  unsigned __int8 v31[4]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 v32; // [rsp+64h] [rbp-35h] BYREF
  int v33; // [rsp+68h] [rbp-31h]
  _BYTE v34[8]; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v35; // [rsp+78h] [rbp-21h]
  unsigned int v36; // [rsp+80h] [rbp-19h]
  __int64 v37; // [rsp+88h] [rbp-11h] BYREF
  struct _FILE_PLACEMENT *v38; // [rsp+90h] [rbp-9h]
  __int128 Source1; // [rsp+98h] [rbp-1h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v38 = a4;
  v36 = a3;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::UpdateRecordsGivenPlacementList";
  CHResultImp::CHResultImp((CHResultImp *)v34);
  if ( a8 )
    ++*(_DWORD *)(**((_QWORD **)this + 5) + 312LL);
  Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), a2, 0x10u, 1u);
  v12 = Key;
  if ( Key )
  {
    if ( Key == -529 || Key == -1092 || Key == -1808 )
    {
      v13 = ATL::AtlHresultFromWin32(112);
    }
    else if ( Key == -1011 )
    {
      v13 = -2147024882;
    }
    else
    {
      v14 = -Key;
      if ( v14 < 0 )
        LOWORD(v14) = v12;
      v13 = v12 & 0x8E5E0000 | (unsigned __int16)v14 | 0xE5E0000;
    }
    v35 = v13;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v16 = 78;
    goto LABEL_34;
  }
  v17 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 8u);
  v12 = v17;
  if ( ((v17 + 1603) & 0xFFFFFFFD) != 0 )
  {
    switch ( v17 )
    {
      case 0:
      case 1039:
      case -1017:
        v33 = 0;
        v13 = -2147024882;
        while ( 2 )
        {
          v37 = 0;
          v31[0] = 0;
          Source1 = 0;
          v32 = 0;
          while ( 1 )
          {
            CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                                  this,
                                  1u,
                                  (struct TE_FILE_ID_128 *)&Source1,
                                  &v37,
                                  0,
                                  v31,
                                  0,
                                  &v32,
                                  0);
            v21 = CurrentHeatRecord;
            if ( CurrentHeatRecord == -1017 )
              goto LABEL_59;
            if ( CurrentHeatRecord )
            {
              if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
              {
                v13 = ATL::AtlHresultFromWin32(112);
              }
              else if ( CurrentHeatRecord != -1011 )
              {
                v29 = -CurrentHeatRecord;
                if ( v29 < 0 )
                  LOWORD(v29) = v21;
                v13 = v21 & 0x8E5E0000 | (unsigned __int16)v29 | 0xE5E0000;
              }
              v35 = v13;
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_iiSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    81,
                    (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                    *((_QWORD *)a2 + 1),
                    *(_QWORD *)a2,
                    *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                    v21);
                  goto LABEL_87;
                }
                goto LABEL_88;
              }
              goto LABEL_35;
            }
            if ( RtlCompareMemory(&Source1, a2, 0x10u) != 16 )
              goto LABEL_86;
            updated = TieringHeatSession::UpdateCurrentRecordGivenPlacementList(
                        this,
                        a2,
                        v37,
                        v36,
                        v38,
                        a5,
                        1,
                        a7,
                        a8,
                        v31[0],
                        v32);
            v23 = updated;
            if ( !updated )
              break;
            if ( updated == -529 || updated == -1092 || updated == -1808 )
            {
              v24 = ATL::AtlHresultFromWin32(112);
            }
            else if ( updated == -1011 )
            {
              v24 = -2147024882;
            }
            else
            {
              v25 = -updated;
              if ( v25 < 0 )
                LOWORD(v25) = v23;
              v24 = v23 & 0x8E5E0000 | (unsigned __int16)v25 | 0xE5E0000;
            }
            v35 = v24;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                82,
                (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                *((_QWORD *)a2 + 1),
                *(_QWORD *)a2,
                *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                v23);
            }
            if ( v23 != -1102 )
              goto LABEL_59;
            Sleep(0x64u);
          }
          ++v33;
          v35 = 0;
LABEL_59:
          v26 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
          v27 = v26;
          switch ( v26 )
          {
            case -1603:
LABEL_86:
              v13 = 0;
              v35 = 0;
LABEL_87:
              v30 = WPP_GLOBAL_Control;
LABEL_88:
              if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 && *((_BYTE *)v30 + 25) >= 5u )
                WPP_SF_iiDS(
                  v30[2],
                  84,
                  (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                  *((_QWORD *)a2 + 1),
                  *(_QWORD *)a2,
                  v33,
                  *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
              goto LABEL_35;
            case 0:
            case -1017:
              continue;
            case -529:
            case -1092:
            case -1808:
              v13 = ATL::AtlHresultFromWin32(112);
              break;
            default:
              if ( v26 != -1011 )
              {
                v28 = -v26;
                if ( v28 < 0 )
                  LOWORD(v28) = v27;
                v13 = v27 & 0x8E5E0000 | (unsigned __int16)v28 | 0xE5E0000;
              }
              break;
          }
          break;
        }
        v35 = v13;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              83,
              (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
              *((_QWORD *)a2 + 1),
              *(_QWORD *)a2,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
              v27);
            goto LABEL_87;
          }
          goto LABEL_88;
        }
        goto LABEL_35;
      case -529:
      case -1092:
      case -1808:
        v13 = ATL::AtlHresultFromWin32(112);
        break;
      case -1011:
        v13 = -2147024882;
        break;
      default:
        v18 = -v17;
        if ( v18 < 0 )
          LOWORD(v18) = v12;
        v13 = v12 & 0x8E5E0000 | (unsigned __int16)v18 | 0xE5E0000;
        break;
    }
    v35 = v13;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_35:
      CHResultImp::~CHResultImp((CHResultImp *)v34);
      return v13;
    }
    v16 = 80;
LABEL_34:
    WPP_SF_iiSd(
      v15[2],
      v16,
      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v12);
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_iiSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
      *((_QWORD *)a2 + 1),
      *(_QWORD *)a2,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v17);
  }
  v35 = 0;
  CHResultImp::~CHResultImp((CHResultImp *)v34);
  return 0;
}

```

## disassembly

```asm
0x14002b15c  mov     [rsp-8+arg_10], rbx
0x14002b161  push    rbp
0x14002b162  push    rsi
0x14002b163  push    rdi
0x14002b164  push    r14
0x14002b166  push    r15
0x14002b168  lea     rbp, [rsp-17h]
0x14002b16d  sub     rsp, 0B0h
0x14002b174  mov     rax, cs:__security_cookie
0x14002b17b  xor     rax, rsp
0x14002b17e  mov     [rbp+37h+var_28], rax
0x14002b182  mov     rax, gs:58h
0x14002b18b  mov     r14, rcx
0x14002b18e  mov     rsi, rdx
0x14002b191  mov     ecx, 8
0x14002b196  mov     [rbp+37h+var_40], r9
0x14002b19a  mov     [rbp+37h+var_50], r8d
0x14002b19e  mov     rdx, [rax]
0x14002b1a1  lea     rax, aTieringheatses_3; "TieringHeatSession::UpdateRecordsGivenP"...
0x14002b1a8  mov     [rcx+rdx], rax
0x14002b1ac  lea     rcx, [rbp+37h+var_60]; this
0x14002b1b0  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002b1b5  cmp     [rbp+37h+arg_38], 0
0x14002b1b9  jz      short loc_14002B1C8
0x14002b1bb  mov     rax, [r14+28h]
0x14002b1bf  mov     rcx, [rax]
0x14002b1c2  inc     dword ptr [rcx+138h]
0x14002b1c8  mov     rdx, [r14+18h]; tableid
0x14002b1cc  mov     r9d, 10h; cbData
0x14002b1d2  mov     rcx, [r14+8]; sesid
0x14002b1d6  mov     r8, rsi; pvData
0x14002b1d9  mov     [rsp+0D0h+grbit], 1; grbit
0x14002b1e1  call    cs:__imp_JetMakeKey
0x14002b1e7  mov     r8d, eax
0x14002b1ea  test    eax, eax
0x14002b1ec  jz      loc_14002B274
0x14002b1f2  cmp     eax, 0FFFFFDEFh
0x14002b1f7  jz      short loc_14002B230
0x14002b1f9  cmp     eax, 0FFFFFBBCh
0x14002b1fe  jz      short loc_14002B230
0x14002b200  cmp     eax, 0FFFFF8F0h
0x14002b205  jz      short loc_14002B230
0x14002b207  cmp     eax, 0FFFFFC0Dh
0x14002b20c  jnz     short loc_14002B215
0x14002b20e  mov     ebx, 8007000Eh
0x14002b213  jmp     short loc_14002B23C
0x14002b215  neg     eax
0x14002b217  cmovs   eax, r8d
0x14002b21b  movzx   ebx, ax
0x14002b21e  mov     eax, r8d
0x14002b221  and     eax, 8E5E0000h
0x14002b226  or      ebx, eax
0x14002b228  or      ebx, 0E5E0000h
0x14002b22e  jmp     short loc_14002B23C
0x14002b230  mov     ecx, 70h ; 'p'; unsigned int
0x14002b235  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002b23a  mov     ebx, eax
0x14002b23c  mov     [rbp+37h+var_58], ebx
0x14002b23f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b246  lea     r15, WPP_GLOBAL_Control
0x14002b24d  cmp     rcx, r15
0x14002b250  jz      loc_14002B35A
0x14002b256  test    byte ptr [rcx+1Ch], 1
0x14002b25a  jz      loc_14002B35A
0x14002b260  cmp     byte ptr [rcx+19h], 2
0x14002b264  jb      loc_14002B35A
0x14002b26a  mov     edx, 4Eh ; 'N'
0x14002b26f  jmp     loc_14002B32C
0x14002b274  mov     rdx, [r14+18h]; tableid
0x14002b278  mov     r8d, 8; grbit
0x14002b27e  mov     rcx, [r14+8]; sesid
0x14002b282  call    cs:__imp_JetSeek
0x14002b288  mov     r8d, eax
0x14002b28b  lea     ecx, [rax+643h]
0x14002b291  test    ecx, 0FFFFFFFDh
0x14002b297  jz      loc_14002B6D6
0x14002b29d  test    eax, eax
0x14002b29f  jz      loc_14002B36A
0x14002b2a5  cmp     eax, 40Fh
0x14002b2aa  jz      loc_14002B36A
0x14002b2b0  cmp     eax, 0FFFFFC07h
0x14002b2b5  jz      loc_14002B36A
0x14002b2bb  cmp     eax, 0FFFFFDEFh
0x14002b2c0  jz      short loc_14002B2F9
0x14002b2c2  cmp     eax, 0FFFFFBBCh
0x14002b2c7  jz      short loc_14002B2F9
0x14002b2c9  cmp     eax, 0FFFFF8F0h
0x14002b2ce  jz      short loc_14002B2F9
0x14002b2d0  cmp     eax, 0FFFFFC0Dh
0x14002b2d5  jnz     short loc_14002B2DE
0x14002b2d7  mov     ebx, 8007000Eh
0x14002b2dc  jmp     short loc_14002B305
0x14002b2de  neg     eax
0x14002b2e0  cmovs   eax, r8d
0x14002b2e4  movzx   ebx, ax
0x14002b2e7  mov     eax, r8d
0x14002b2ea  and     eax, 8E5E0000h
0x14002b2ef  or      ebx, eax
0x14002b2f1  or      ebx, 0E5E0000h
0x14002b2f7  jmp     short loc_14002B305
0x14002b2f9  mov     ecx, 70h ; 'p'; unsigned int
0x14002b2fe  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002b303  mov     ebx, eax
0x14002b305  mov     [rbp+37h+var_58], ebx
0x14002b308  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b30f  lea     r15, WPP_GLOBAL_Control
0x14002b316  cmp     rcx, r15
0x14002b319  jz      short loc_14002B35A
0x14002b31b  test    byte ptr [rcx+1Ch], 1
0x14002b31f  jz      short loc_14002B35A
0x14002b321  cmp     byte ptr [rcx+19h], 2
0x14002b325  jb      short loc_14002B35A
0x14002b327  mov     edx, 50h ; 'P'
0x14002b32c  mov     rax, [r14+28h]
0x14002b330  mov     r9, [rsi+8]
0x14002b334  mov     rcx, [rcx+10h]
0x14002b338  mov     dword ptr [rsp+0D0h+var_A0], r8d
0x14002b33d  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002b344  mov     rax, [rax+70h]
0x14002b348  mov     [rsp+0D0h+var_A8], rax
0x14002b34d  mov     rax, [rsi]
0x14002b350  mov     qword ptr [rsp+0D0h+grbit], rax
0x14002b355  call    WPP_SF_iiSd
0x14002b35a  lea     rcx, [rbp+37h+var_60]; this
0x14002b35e  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14002b363  mov     eax, ebx
0x14002b365  jmp     loc_14002B73A
0x14002b36a  xor     eax, eax
0x14002b36c  lea     r15, WPP_GLOBAL_Control
0x14002b373  mov     [rbp+37h+var_68], eax
0x14002b376  mov     ebx, 8007000Eh
0x14002b37b  xorps   xmm0, xmm0
0x14002b37e  mov     [rbp+37h+var_48], 0
0x14002b386  xor     eax, eax
0x14002b388  mov     [rbp+37h+var_70], 0
0x14002b38c  movups  [rbp+37h+Source1], xmm0
0x14002b390  mov     [rbp+37h+var_6C], ax
0x14002b394  mov     [rsp+0D0h+var_90], 0; unsigned __int16 *
0x14002b39d  lea     rax, [rbp+37h+var_6C]
0x14002b3a1  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x14002b3a6  lea     r9, [rbp+37h+var_48]; __int64 *
0x14002b3aa  lea     rax, [rbp+37h+var_70]
0x14002b3ae  mov     [rsp+0D0h+var_A0], 0; unsigned __int8 *
0x14002b3b7  mov     [rsp+0D0h+var_A8], rax; unsigned __int8 *
0x14002b3bc  lea     r8, [rbp+37h+Source1]; struct TE_FILE_ID_128 *
0x14002b3c0  mov     dl, 1; bool
0x14002b3c2  mov     qword ptr [rsp+0D0h+grbit], 0; unsigned __int8 *
0x14002b3cb  mov     rcx, r14; this
0x14002b3ce  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002b3d3  mov     edi, eax
0x14002b3d5  cmp     eax, 0FFFFFC07h
0x14002b3da  jz      loc_14002B502
0x14002b3e0  test    eax, eax
0x14002b3e2  jnz     loc_14002B59A
0x14002b3e8  lea     r8d, [rax+10h]; Length
0x14002b3ec  mov     rdx, rsi; Source2
0x14002b3ef  lea     rcx, [rbp+37h+Source1]; Source1
0x14002b3f3  call    cs:__imp_RtlCompareMemory
0x14002b3f9  cmp     rax, 10h
0x14002b3fd  jnz     loc_14002B671
0x14002b403  movzx   eax, [rbp+37h+var_6C]
0x14002b407  mov     rdx, rsi; struct TE_FILE_ID_128 *
0x14002b40a  mov     r9d, [rbp+37h+var_50]; unsigned int
0x14002b40e  mov     rcx, r14; this
0x14002b411  mov     r8, [rbp+37h+var_48]; __int64
0x14002b415  mov     [rsp+0D0h+var_80], ax; unsigned __int16
0x14002b41a  mov     al, [rbp+37h+var_70]
0x14002b41d  mov     [rsp+0D0h+var_88], al; unsigned __int8
0x14002b421  mov     eax, [rbp+37h+arg_38]
0x14002b424  mov     dword ptr [rsp+0D0h+var_90], eax; int
0x14002b428  mov     eax, [rbp+37h+arg_30]
0x14002b42b  mov     dword ptr [rsp+0D0h+var_98], eax; int
0x14002b42f  mov     rax, [rbp+37h+arg_20]
0x14002b433  mov     dword ptr [rsp+0D0h+var_A0], 1; int
0x14002b43b  mov     [rsp+0D0h+var_A8], rax; unsigned __int64
0x14002b440  mov     rax, [rbp+37h+var_40]
0x14002b444  mov     qword ptr [rsp+0D0h+grbit], rax; struct _FILE_PLACEMENT *
0x14002b449  call    ?UpdateCurrentRecordGivenPlacementList@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JKPEBU_FILE_PLACEMENT@@_KHHHEG@Z; TieringHeatSession::UpdateCurrentRecordGivenPlacementList(TE_FILE_ID_128 const *,__int64,ulong,_FILE_PLACEMENT const *,unsigned __int64,int,int,int,uchar,ushort)
0x14002b44e  mov     edi, eax
0x14002b450  test    eax, eax
0x14002b452  jz      loc_14002B510
0x14002b458  cmp     eax, 0FFFFFDEFh
0x14002b45d  jz      short loc_14002B491
0x14002b45f  cmp     eax, 0FFFFFBBCh
0x14002b464  jz      short loc_14002B491
0x14002b466  cmp     eax, 0FFFFF8F0h
0x14002b46b  jz      short loc_14002B491
0x14002b46d  cmp     eax, 0FFFFFC0Dh
0x14002b472  jnz     short loc_14002B478
0x14002b474  mov     ecx, ebx
0x14002b476  jmp     short loc_14002B49D
0x14002b478  neg     eax
0x14002b47a  cmovs   eax, edi
0x14002b47d  movzx   ecx, ax
0x14002b480  mov     eax, edi
0x14002b482  and     eax, 8E5E0000h
0x14002b487  or      ecx, eax
0x14002b489  or      ecx, 0E5E0000h
0x14002b48f  jmp     short loc_14002B49D
0x14002b491  mov     ecx, 70h ; 'p'; unsigned int
0x14002b496  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002b49b  mov     ecx, eax
0x14002b49d  mov     [rbp+37h+var_58], ecx
0x14002b4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b4a7  cmp     rcx, r15
0x14002b4aa  jz      short loc_14002B4EA
0x14002b4ac  test    byte ptr [rcx+1Ch], 1
0x14002b4b0  jz      short loc_14002B4EA
0x14002b4b2  cmp     byte ptr [rcx+19h], 2
0x14002b4b6  jb      short loc_14002B4EA
0x14002b4b8  mov     rax, [r14+28h]
0x14002b4bc  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002b4c3  mov     r9, [rsi+8]
0x14002b4c7  mov     edx, 52h ; 'R'
0x14002b4cc  mov     rcx, [rcx+10h]
0x14002b4d0  mov     dword ptr [rsp+0D0h+var_A0], edi
0x14002b4d4  mov     rax, [rax+70h]
0x14002b4d8  mov     [rsp+0D0h+var_A8], rax
0x14002b4dd  mov     rax, [rsi]
0x14002b4e0  mov     qword ptr [rsp+0D0h+grbit], rax
0x14002b4e5  call    WPP_SF_iiSd
0x14002b4ea  cmp     edi, 0FFFFFBB2h
0x14002b4f0  jnz     short loc_14002B51A
0x14002b4f2  mov     ecx, 64h ; 'd'; dwMilliseconds
0x14002b4f7  call    cs:__imp_Sleep
0x14002b4fd  jmp     loc_14002B394
0x14002b502  cmp     edi, 0FFFFFBB2h
0x14002b508  jz      loc_14002B394
0x14002b50e  jmp     short loc_14002B51A
0x14002b510  inc     [rbp+37h+var_68]
0x14002b513  mov     [rbp+37h+var_58], 0
0x14002b51a  mov     rdx, [r14+18h]; tableid
0x14002b51e  xor     r9d, r9d; grbit
0x14002b521  mov     rcx, [r14+8]; sesid
0x14002b525  lea     r8d, [r9+1]; cRow
0x14002b529  call    cs:__imp_JetMove
0x14002b52f  mov     r8d, eax
0x14002b532  cmp     eax, 0FFFFF9BDh
0x14002b537  jz      loc_14002B671
0x14002b53d  test    eax, eax
0x14002b53f  jz      loc_14002B37B
0x14002b545  cmp     eax, 0FFFFFC07h
0x14002b54a  jz      loc_14002B37B
0x14002b550  cmp     eax, 0FFFFFDEFh
0x14002b555  jz      loc_14002B638
0x14002b55b  cmp     eax, 0FFFFFBBCh
0x14002b560  jz      loc_14002B638
0x14002b566  cmp     eax, 0FFFFF8F0h
0x14002b56b  jz      loc_14002B638
0x14002b571  cmp     eax, 0FFFFFC0Dh
0x14002b576  jz      loc_14002B644
0x14002b57c  neg     eax
0x14002b57e  cmovs   eax, r8d
0x14002b582  movzx   ebx, ax
0x14002b585  mov     eax, r8d
0x14002b588  and     eax, 8E5E0000h
0x14002b58d  or      ebx, eax
0x14002b58f  or      ebx, 0E5E0000h
0x14002b595  jmp     loc_14002B644
0x14002b59a  cmp     edi, 0FFFFFDEFh
0x14002b5a0  jz      short loc_14002B5D3
0x14002b5a2  cmp     edi, 0FFFFFBBCh
0x14002b5a8  jz      short loc_14002B5D3
0x14002b5aa  cmp     edi, 0FFFFF8F0h
0x14002b5b0  jz      short loc_14002B5D3
0x14002b5b2  cmp     edi, 0FFFFFC0Dh
0x14002b5b8  jz      short loc_14002B5DF
0x14002b5ba  neg     eax
0x14002b5bc  cmovs   eax, edi
0x14002b5bf  movzx   ebx, ax
0x14002b5c2  mov     eax, edi
0x14002b5c4  and     eax, 8E5E0000h
0x14002b5c9  or      ebx, eax
0x14002b5cb  or      ebx, 0E5E0000h
0x14002b5d1  jmp     short loc_14002B5DF
0x14002b5d3  mov     ecx, 70h ; 'p'; unsigned int
0x14002b5d8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002b5dd  mov     ebx, eax
0x14002b5df  mov     [rbp+37h+var_58], ebx
0x14002b5e2  mov     r10, cs:WPP_GLOBAL_Control
0x14002b5e9  cmp     r10, r15
0x14002b5ec  jz      loc_14002B35A
0x14002b5f2  test    byte ptr [r10+1Ch], 1
0x14002b5f7  jz      loc_14002B67D
0x14002b5fd  cmp     byte ptr [r10+19h], 2
0x14002b602  jb      short loc_14002B67D
0x14002b604  mov     edx, 51h ; 'Q'
0x14002b609  mov     dword ptr [rsp+0D0h+var_A0], edi
0x14002b60d  mov     rax, [r14+28h]
0x14002b611  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002b618  mov     r9, [rsi+8]
0x14002b61c  mov     rcx, [r10+10h]
0x14002b620  mov     rax, [rax+70h]
0x14002b624  mov     [rsp+0D0h+var_A8], rax
0x14002b629  mov     rax, [rsi]
0x14002b62c  mov     qword ptr [rsp+0D0h+grbit], rax
0x14002b631  call    WPP_SF_iiSd
0x14002b636  jmp     short loc_14002B676
0x14002b638  mov     ecx, 70h ; 'p'; unsigned int
0x14002b63d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
  ... truncated ...
```
