# TieringHeatSession::DeleteRecordsWithGivenFileId(TE_FILE_ID_128 const *,ulong *)

- ea: `0x1400280bc`
- end: `0x140028665`
- name: `?DeleteRecordsWithGivenFileId@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@PEAK@Z`
- size: `1449`
- prototype: `__int64 __fastcall(JET_SESID *this, const struct TE_FILE_ID_128 *Source2, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140010d1c`
- `0x14002fd94`
- `0x14003eba8`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140020e1c`
- `0x140021018`
- `0x1400280bc`
- `0x14002a86c`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14002812e`
- `ntdll!RtlCompareMemory` at `0x14002837d`
- `ntdll!RtlCompareMemory` at `0x14002812e`
- `ntdll!RtlCompareMemory` at `0x14002837d`
- `ESENT!JetDelete` at `0x140028395`
- `ESENT!JetDelete` at `0x140028395`
- `ESENT!JetMove` at `0x1400283b4`
- `ESENT!JetMove` at `0x1400283b4`
- `ESENT!JetMakeKey` at `0x1400281a1`
- `ESENT!JetMakeKey` at `0x1400281a1`
- `ESENT!JetSeek` at `0x140028242`
- `ESENT!JetSeek` at `0x140028242`
- `ESENT!JetRetrieveColumn` at `0x140028353`
- `ESENT!JetRetrieveColumn` at `0x140028353`

## string_xrefs

- `0x1400280f7`: `TieringHeatSession::DeleteRecordsWithGivenFileId`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::DeleteRecordsWithGivenFileId(
        JET_SESID *this,
        const struct TE_FILE_ID_128 *Source2,
        unsigned int *a3)
{
  unsigned int v6; // ebx
  JET_ERR Key; // eax
  JET_ERR v8; // r8d
  int v9; // eax
  _QWORD *v10; // rcx
  int v11; // edx
  JET_ERR v12; // eax
  int v13; // eax
  unsigned int v15; // r13d
  JET_COLUMNID v16; // r8d
  JET_TABLEID v17; // rdx
  JET_SESID v18; // rcx
  JET_ERR v19; // eax
  JET_ERR v20; // r8d
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  int v23; // eax
  _QWORD *v24; // rcx
  int v25; // edx
  int v26; // eax
  int v27; // eax
  _BYTE v28[8]; // [rsp+40h] [rbp-30h] BYREF
  int v29; // [rsp+48h] [rbp-28h]
  __int128 pvData; // [rsp+50h] [rbp-20h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::DeleteRecordsWithGivenFileId";
  CHResultImp::CHResultImp((CHResultImp *)v28);
  TieringHeatSession::SetupColumnIds((TieringHeatSession *)this);
  if ( a3 )
    *a3 = 0;
  if ( RtlCompareMemory(Source2, &NullGuid, 0x10u) == 16 )
  {
    v6 = -2138898428;
    v29 = -2138898428;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, 2156068868LL);
    }
    goto LABEL_39;
  }
  Key = JetMakeKey(this[1], this[3], Source2, 0x10u, 1u);
  v8 = Key;
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
      v9 = -Key;
      if ( v9 < 0 )
        LOWORD(v9) = v8;
      v6 = v8 & 0x8E5E0000 | (unsigned __int16)v9 | 0xE5E0000;
    }
    v29 = v6;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v11 = 11;
    goto LABEL_38;
  }
  v12 = JetSeek(this[1], this[3], 8u);
  v8 = v12;
  if ( ((v12 + 1603) & 0xFFFFFFFD) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        *(_QWORD *)(this[5] + 112),
        v12);
    }
    v29 = 0;
    CHResultImp::~CHResultImp((CHResultImp *)v28);
    return 0;
  }
  if ( v12 && v12 != 1039 )
  {
    if ( v12 == -529 || v12 == -1092 || v12 == -1808 )
    {
      v6 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v12 == -1011 )
    {
      v6 = -2147024882;
    }
    else
    {
      v13 = -v12;
      if ( v13 < 0 )
        LOWORD(v13) = v8;
      v6 = v8 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
    }
    v29 = v6;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v11 = 13;
LABEL_38:
    WPP_SF_iiSd(
      v10[2],
      v11,
      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
      *((_QWORD *)Source2 + 1),
      *(_QWORD *)Source2,
      *(_QWORD *)(this[5] + 112),
      v8);
    goto LABEL_39;
  }
  v15 = 0;
  while ( 1 )
  {
    v16 = *((_DWORD *)this + 13);
    v17 = this[3];
    v18 = this[1];
    pvData = 0;
    v19 = JetRetrieveColumn(v18, v17, v16, &pvData, 0x10u, 0, 2u, 0);
    v20 = v19;
    if ( v19 != -1017 )
      break;
LABEL_46:
    v22 = JetMove(this[1], this[3], 1, 0);
    v20 = v22;
    if ( v22 == -1603 )
    {
LABEL_89:
      v6 = v29;
      goto LABEL_90;
    }
    if ( v22 && v22 != -1017 )
    {
      if ( v22 == -529 || v22 == -1092 || v22 == -1808 )
      {
        v6 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v22 == -1011 )
      {
        v6 = -2147024882;
      }
      else
      {
        v27 = -v22;
        if ( v27 < 0 )
          LOWORD(v27) = v20;
        v6 = v20 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
      }
      v29 = v6;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_95;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_91;
      v25 = 16;
LABEL_67:
      WPP_SF_iiSd(
        v24[2],
        v25,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        *(_QWORD *)(this[5] + 112),
        v20);
LABEL_90:
      v24 = WPP_GLOBAL_Control;
      goto LABEL_91;
    }
  }
  if ( v19 )
  {
    if ( v19 == -529 || v19 == -1092 || v19 == -1808 )
    {
      v6 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v19 == -1011 )
    {
      v6 = -2147024882;
    }
    else
    {
      v26 = -v19;
      if ( v26 < 0 )
        LOWORD(v26) = v20;
      v6 = v20 & 0x8E5E0000 | (unsigned __int16)v26 | 0xE5E0000;
    }
    v29 = v6;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_95;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_91;
    v25 = 14;
    goto LABEL_67;
  }
  if ( RtlCompareMemory(&pvData, Source2, 0x10u) != 16 )
    goto LABEL_89;
  v21 = JetDelete(this[1], this[3]);
  v20 = v21;
  switch ( v21 )
  {
    case 0:
      ++v15;
      goto LABEL_46;
    case -529:
    case -1092:
    case -1808:
      v6 = ATL::AtlHresultFromWin32(112);
      break;
    case -1011:
      v6 = -2147024882;
      break;
    default:
      v23 = -v21;
      if ( v23 < 0 )
        LOWORD(v23) = v20;
      v6 = v20 & 0x8E5E0000 | (unsigned __int16)v23 | 0xE5E0000;
      break;
  }
  v29 = v6;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = 15;
      goto LABEL_67;
    }
LABEL_91:
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 5u )
      WPP_SF_iiDS(
        v24[2],
        17,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        v15,
        *(_QWORD *)(this[5] + 112));
  }
LABEL_95:
  if ( a3 )
    *a3 = v15;
LABEL_39:
  CHResultImp::~CHResultImp((CHResultImp *)v28);
  return v6;
}

```

## disassembly

```asm
0x1400280bc  push    rbp
0x1400280be  push    rbx
0x1400280bf  push    rdi
0x1400280c0  push    r12
0x1400280c2  push    r13
0x1400280c4  push    r14
0x1400280c6  push    r15
0x1400280c8  mov     rbp, rsp
0x1400280cb  sub     rsp, 70h
0x1400280cf  mov     rax, cs:__security_cookie
0x1400280d6  xor     rax, rsp
0x1400280d9  mov     [rbp+var_10], rax
0x1400280dd  mov     rax, gs:58h
0x1400280e6  mov     r15, rcx
0x1400280e9  mov     r14, rdx
0x1400280ec  mov     ecx, 8
0x1400280f1  mov     r12, r8
0x1400280f4  mov     rdx, [rax]
0x1400280f7  lea     rax, aTieringheatses_9; "TieringHeatSession::DeleteRecordsWithGi"...
0x1400280fe  mov     [rcx+rdx], rax
0x140028102  lea     rcx, [rbp+var_30]; this
0x140028106  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002810b  mov     rcx, r15; this
0x14002810e  call    ?SetupColumnIds@TieringHeatSession@@QEAAXXZ; TieringHeatSession::SetupColumnIds(void)
0x140028113  xor     ebx, ebx
0x140028115  test    r12, r12
0x140028118  jz      short loc_14002811E
0x14002811a  mov     [r12], ebx
0x14002811e  mov     r8d, 10h; Length
0x140028124  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14002812b  mov     rcx, r14; Source1
0x14002812e  call    cs:__imp_RtlCompareMemory
0x140028134  cmp     rax, 10h
0x140028138  jnz     short loc_140028188
0x14002813a  mov     ebx, 80830004h
0x14002813f  mov     [rbp+var_28], ebx
0x140028142  mov     rcx, cs:WPP_GLOBAL_Control
0x140028149  lea     rdi, WPP_GLOBAL_Control
0x140028150  cmp     rcx, rdi
0x140028153  jz      loc_14002830F
0x140028159  test    byte ptr [rcx+1Ch], 1
0x14002815d  jz      loc_14002830F
0x140028163  cmp     byte ptr [rcx+19h], 2
0x140028167  jb      loc_14002830F
0x14002816d  mov     rcx, [rcx+10h]
0x140028171  lea     edx, [rax-6]
0x140028174  mov     r9d, ebx
0x140028177  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002817e  call    WPP_SF_d
0x140028183  jmp     loc_14002830F
0x140028188  mov     rdx, [r15+18h]; tableid
0x14002818c  mov     r9d, 10h; cbData
0x140028192  mov     rcx, [r15+8]; sesid
0x140028196  mov     r8, r14; pvData
0x140028199  mov     [rsp+70h+grbit], 1; grbit
0x1400281a1  call    cs:__imp_JetMakeKey
0x1400281a7  mov     r8d, eax
0x1400281aa  test    eax, eax
0x1400281ac  jz      loc_140028234
0x1400281b2  cmp     eax, 0FFFFFDEFh
0x1400281b7  jz      short loc_1400281F0
0x1400281b9  cmp     eax, 0FFFFFBBCh
0x1400281be  jz      short loc_1400281F0
0x1400281c0  cmp     eax, 0FFFFF8F0h
0x1400281c5  jz      short loc_1400281F0
0x1400281c7  cmp     eax, 0FFFFFC0Dh
0x1400281cc  jnz     short loc_1400281D5
0x1400281ce  mov     ebx, 8007000Eh
0x1400281d3  jmp     short loc_1400281FC
0x1400281d5  neg     eax
0x1400281d7  cmovs   eax, r8d
0x1400281db  movzx   ebx, ax
0x1400281de  mov     eax, r8d
0x1400281e1  and     eax, 8E5E0000h
0x1400281e6  or      ebx, eax
0x1400281e8  or      ebx, 0E5E0000h
0x1400281ee  jmp     short loc_1400281FC
0x1400281f0  mov     ecx, 70h ; 'p'; unsigned int
0x1400281f5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400281fa  mov     ebx, eax
0x1400281fc  mov     [rbp+var_28], ebx
0x1400281ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140028206  lea     rdi, WPP_GLOBAL_Control
0x14002820d  cmp     rcx, rdi
0x140028210  jz      loc_14002830F
0x140028216  test    byte ptr [rcx+1Ch], 1
0x14002821a  jz      loc_14002830F
0x140028220  cmp     byte ptr [rcx+19h], 2
0x140028224  jb      loc_14002830F
0x14002822a  mov     edx, 0Bh
0x14002822f  jmp     loc_1400282E1
0x140028234  mov     rdx, [r15+18h]; tableid
0x140028238  mov     r8d, 8; grbit
0x14002823e  mov     rcx, [r15+8]; sesid
0x140028242  call    cs:__imp_JetSeek
0x140028248  mov     r8d, eax
0x14002824b  lea     ecx, [rax+643h]
0x140028251  test    ecx, 0FFFFFFFDh
0x140028257  jz      loc_1400285E9
0x14002825d  test    eax, eax
0x14002825f  jz      loc_14002831F
0x140028265  cmp     eax, 40Fh
0x14002826a  jz      loc_14002831F
0x140028270  cmp     eax, 0FFFFFDEFh
0x140028275  jz      short loc_1400282AE
0x140028277  cmp     eax, 0FFFFFBBCh
0x14002827c  jz      short loc_1400282AE
0x14002827e  cmp     eax, 0FFFFF8F0h
0x140028283  jz      short loc_1400282AE
0x140028285  cmp     eax, 0FFFFFC0Dh
0x14002828a  jnz     short loc_140028293
0x14002828c  mov     ebx, 8007000Eh
0x140028291  jmp     short loc_1400282BA
0x140028293  neg     eax
0x140028295  cmovs   eax, r8d
0x140028299  movzx   ebx, ax
0x14002829c  mov     eax, r8d
0x14002829f  and     eax, 8E5E0000h
0x1400282a4  or      ebx, eax
0x1400282a6  or      ebx, 0E5E0000h
0x1400282ac  jmp     short loc_1400282BA
0x1400282ae  mov     ecx, 70h ; 'p'; unsigned int
0x1400282b3  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400282b8  mov     ebx, eax
0x1400282ba  mov     [rbp+var_28], ebx
0x1400282bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400282c4  lea     rdi, WPP_GLOBAL_Control
0x1400282cb  cmp     rcx, rdi
0x1400282ce  jz      short loc_14002830F
0x1400282d0  test    byte ptr [rcx+1Ch], 1
0x1400282d4  jz      short loc_14002830F
0x1400282d6  cmp     byte ptr [rcx+19h], 2
0x1400282da  jb      short loc_14002830F
0x1400282dc  mov     edx, 0Dh
0x1400282e1  mov     rax, [r15+28h]
0x1400282e5  mov     r9, [r14+8]
0x1400282e9  mov     rcx, [rcx+10h]
0x1400282ed  mov     [rsp+70h+var_40], r8d
0x1400282f2  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x1400282f9  mov     rax, [rax+70h]
0x1400282fd  mov     [rsp+70h+pcbActual], rax
0x140028302  mov     rax, [r14]
0x140028305  mov     qword ptr [rsp+70h+grbit], rax
0x14002830a  call    WPP_SF_iiSd
0x14002830f  lea     rcx, [rbp+var_30]; this
0x140028313  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140028318  mov     eax, ebx
0x14002831a  jmp     loc_140028649
0x14002831f  mov     r13d, ebx
0x140028322  mov     r8d, [r15+34h]; columnid
0x140028326  lea     r9, [rbp+pvData]; pvData
0x14002832a  mov     rdx, [r15+18h]; tableid
0x14002832e  xorps   xmm0, xmm0
0x140028331  mov     rcx, [r15+8]; sesid
0x140028335  mov     [rsp+70h+pretinfo], rbx; pretinfo
0x14002833a  mov     [rsp+70h+var_40], 2; grbit
0x140028342  mov     [rsp+70h+pcbActual], rbx; pcbActual
0x140028347  mov     [rsp+70h+grbit], 10h; cbData
0x14002834f  movups  [rbp+pvData], xmm0
0x140028353  call    cs:__imp_JetRetrieveColumn
0x140028359  lea     rdi, WPP_GLOBAL_Control
0x140028360  mov     r8d, eax
0x140028363  cmp     eax, 0FFFFFC07h
0x140028368  jz      short loc_1400283A5
0x14002836a  test    eax, eax
0x14002836c  jnz     loc_1400284C2
0x140028372  lea     r8d, [rax+10h]; Length
0x140028376  mov     rdx, r14; Source2
0x140028379  lea     rcx, [rbp+pvData]; Source1
0x14002837d  call    cs:__imp_RtlCompareMemory
0x140028383  cmp     rax, 10h
0x140028387  jnz     loc_140028589
0x14002838d  mov     rdx, [r15+18h]; tableid
0x140028391  mov     rcx, [r15+8]; sesid
0x140028395  call    cs:__imp_JetDelete
0x14002839b  mov     r8d, eax
0x14002839e  test    eax, eax
0x1400283a0  jnz     short loc_140028411
0x1400283a2  inc     r13d
0x1400283a5  mov     rdx, [r15+18h]; tableid
0x1400283a9  xor     r9d, r9d; grbit
0x1400283ac  mov     rcx, [r15+8]; sesid
0x1400283b0  lea     r8d, [r9+1]; cRow
0x1400283b4  call    cs:__imp_JetMove
0x1400283ba  mov     r8d, eax
0x1400283bd  cmp     eax, 0FFFFF9BDh
0x1400283c2  jz      loc_140028589
0x1400283c8  test    eax, eax
0x1400283ca  jz      loc_140028322
0x1400283d0  cmp     eax, 0FFFFFC07h
0x1400283d5  jz      loc_140028322
0x1400283db  cmp     eax, 0FFFFFDEFh
0x1400283e0  jz      loc_140028558
0x1400283e6  cmp     eax, 0FFFFFBBCh
0x1400283eb  jz      loc_140028558
0x1400283f1  cmp     eax, 0FFFFF8F0h
0x1400283f6  jz      loc_140028558
0x1400283fc  cmp     eax, 0FFFFFC0Dh
0x140028401  jnz     loc_14002853D
0x140028407  mov     ebx, 8007000Eh
0x14002840c  jmp     loc_140028564
0x140028411  cmp     r8d, 0FFFFFDEFh
0x140028418  jz      short loc_140028457
0x14002841a  cmp     r8d, 0FFFFFBBCh
0x140028421  jz      short loc_140028457
0x140028423  cmp     r8d, 0FFFFF8F0h
0x14002842a  jz      short loc_140028457
0x14002842c  cmp     r8d, 0FFFFFC0Dh
0x140028433  jnz     short loc_14002843C
0x140028435  mov     ebx, 8007000Eh
0x14002843a  jmp     short loc_140028463
0x14002843c  neg     eax
0x14002843e  cmovs   eax, r8d
0x140028442  movzx   ebx, ax
0x140028445  mov     eax, r8d
0x140028448  and     eax, 8E5E0000h
0x14002844d  or      ebx, eax
0x14002844f  or      ebx, 0E5E0000h
0x140028455  jmp     short loc_140028463
0x140028457  mov     ecx, 70h ; 'p'; unsigned int
0x14002845c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140028461  mov     ebx, eax
0x140028463  mov     [rbp+var_28], ebx
0x140028466  mov     rcx, cs:WPP_GLOBAL_Control
0x14002846d  cmp     rcx, rdi
0x140028470  jz      loc_1400285D7
0x140028476  test    byte ptr [rcx+1Ch], 1
0x14002847a  jz      loc_140028593
0x140028480  cmp     byte ptr [rcx+19h], 2
0x140028484  jb      loc_140028593
0x14002848a  mov     edx, 0Fh
0x14002848f  mov     rax, [r15+28h]
0x140028493  mov     r9, [r14+8]
0x140028497  mov     rcx, [rcx+10h]
0x14002849b  mov     [rsp+70h+var_40], r8d
0x1400284a0  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x1400284a7  mov     rax, [rax+70h]
0x1400284ab  mov     [rsp+70h+pcbActual], rax
0x1400284b0  mov     rax, [r14]
0x1400284b3  mov     qword ptr [rsp+70h+grbit], rax
0x1400284b8  call    WPP_SF_iiSd
0x1400284bd  jmp     loc_14002858C
0x1400284c2  cmp     r8d, 0FFFFFDEFh
0x1400284c9  jz      short loc_140028508
0x1400284cb  cmp     r8d, 0FFFFFBBCh
0x1400284d2  jz      short loc_140028508
0x1400284d4  cmp     r8d, 0FFFFF8F0h
0x1400284db  jz      short loc_140028508
0x1400284dd  cmp     r8d, 0FFFFFC0Dh
0x1400284e4  jnz     short loc_1400284ED
0x1400284e6  mov     ebx, 8007000Eh
0x1400284eb  jmp     short loc_140028514
0x1400284ed  neg     eax
0x1400284ef  cmovs   eax, r8d
0x1400284f3  movzx   ebx, ax
0x1400284f6  mov     eax, r8d
0x1400284f9  and     eax, 8E5E0000h
0x1400284fe  or      ebx, eax
0x140028500  or      ebx, 0E5E0000h
0x140028506  jmp     short loc_140028514
0x140028508  mov     ecx, 70h ; 'p'; unsigned int
0x14002850d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140028512  mov     ebx, eax
0x140028514  mov     [rbp+var_28], ebx
0x140028517  mov     rcx, cs:WPP_GLOBAL_Control
0x14002851e  cmp     rcx, rdi
0x140028521  jz      loc_1400285D7
0x140028527  test    byte ptr [rcx+1Ch], 1
0x14002852b  jz      short loc_140028593
0x14002852d  cmp     byte ptr [rcx+19h], 2
0x140028531  jb      short loc_140028593
0x140028533  mov     edx, 0Eh
0x140028538  jmp     loc_14002848F
0x14002853d  neg     eax
0x14002853f  cmovs   eax, r8d
0x140028543  movzx   ebx, ax
0x140028546  mov     eax, r8d
0x140028549  and     eax, 8E5E0000h
0x14002854e  or      ebx, eax
0x140028550  or      ebx, 0E5E0000h
0x140028556  jmp     short loc_140028564
0x140028558  mov     ecx, 70h ; 'p'; unsigned int
0x14002855d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140028562  mov     ebx, eax
0x140028564  mov     [rbp+var_28], ebx
0x140028567  mov     rcx, cs:WPP_GLOBAL_Control
0x14002856e  cmp     rcx, rdi
0x140028571  jz      short loc_1400285D7
0x140028573  test    byte ptr [rcx+1Ch], 1
0x140028577  jz      short loc_140028593
0x140028579  cmp     byte ptr [rcx+19h], 2
0x14002857d  jb      short loc_140028593
0x14002857f  mov     edx, 10h
0x140028584  jmp     loc_14002848F
0x140028589  mov     ebx, [rbp+var_28]
0x14002858c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028593  cmp     rcx, rdi
0x140028596  jz      short loc_1400285D7
0x140028598  test    byte ptr [rcx+1Ch], 1
0x14002859c  jz      short loc_1400285D7
  ... truncated ...
```
