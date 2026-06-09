# TieringPinnedSession::GetPinnedFilesListByRow(ulong,_STORAGE_TIER_CLASS,ulong,_QUERY_FILE_LAYOUT_INPUT *,__MIDL___MIDL_itf_tieringengine_0000_0000_0006 *,ulong *)

- ea: `0x14001fca0`
- end: `0x140020389`
- name: `?GetPinnedFilesListByRow@TieringPinnedSession@@QEAAJKW4_STORAGE_TIER_CLASS@@KPEAU_QUERY_FILE_LAYOUT_INPUT@@PEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0006@@PEAK@Z`
- size: `1769`
- prototype: `__int64 __fastcall(TieringPinnedSession *this, int cRow, unsigned int, int, struct _QUERY_FILE_LAYOUT_INPUT *, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0006 *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14000f108`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009904`
- `0x140009a04`
- `0x140009c08`
- `0x14001cd80`
- `0x14001f744`
- `0x14001fca0`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001ff72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001ff72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001fe69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001fe69`
- `ESENT!JetMove` at `0x14001fd66`
- `ESENT!JetMove` at `0x14001fd89`
- `ESENT!JetMove` at `0x1400200d6`
- `ESENT!JetMove` at `0x14001fd66`
- `ESENT!JetMove` at `0x14001fd89`
- `ESENT!JetMove` at `0x1400200d6`

## pseudocode

```c
__int64 __fastcall TieringPinnedSession::GetPinnedFilesListByRow(
        TieringPinnedSession *this,
        int cRow,
        unsigned int a3,
        int a4,
        struct _QUERY_FILE_LAYOUT_INPUT *a5,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0006 *a6,
        unsigned int *a7)
{
  __int64 v11; // rcx
  GUID v12; // xmm6
  int v13; // r15d
  GUID v14; // xmm7
  JET_TABLEID v15; // rdx
  JET_SESID v16; // rcx
  JET_ERR v17; // r10d
  unsigned int v18; // ebx
  int v19; // eax
  int v20; // edi
  RTL_SRWLOCK *v21; // rbx
  _QWORD *i; // r9
  __int64 v23; // rax
  _WORD *v24; // r8
  __int64 v25; // rcx
  _WORD *v26; // rax
  __int64 v27; // rdx
  _WORD *v28; // r8
  __int64 v29; // rcx
  _WORD *v30; // rcx
  unsigned int v31; // edi
  unsigned int *v32; // rbx
  unsigned int v33; // r15d
  JET_ERR CurrentPinnedRecord; // eax
  JET_ERR v35; // r8d
  bool v36; // zf
  _WORD *v37; // r8
  __int64 v38; // rcx
  _WORD *v39; // rax
  __int64 v40; // rdx
  _WORD *v41; // r8
  __int64 v42; // rcx
  _WORD *v43; // rcx
  __int64 v44; // rcx
  JET_ERR v45; // eax
  JET_ERR v46; // r8d
  unsigned int v47; // r11d
  int v48; // eax
  int v49; // eax
  unsigned __int8 v51[8]; // [rsp+38h] [rbp-D0h] BYREF
  int v52; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-C0h]
  __int64 v54; // [rsp+50h] [rbp-B8h]
  _QWORD v55[4]; // [rsp+58h] [rbp-B0h] BYREF
  _WORD v56[256]; // [rsp+78h] [rbp-90h] BYREF
  _WORD v57[256]; // [rsp+278h] [rbp+170h] BYREF

  v11 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  LODWORD(v54) = a4;
  v55[0] = a7;
  *(_QWORD *)(v11 + 8) = "TieringPinnedSession::GetPinnedFilesListByRow";
  CHResultImp::CHResultImp((CHResultImp *)&v52);
  v12 = g_FlashTierTestGuid;
  v13 = 0;
  v14 = g_DiskTierTestGuid;
  *a7 = 0;
  v15 = *((_QWORD *)this + 3);
  v16 = *((_QWORD *)this + 1);
  *(_OWORD *)&v55[1] = 0;
  v56[0] = 0;
  v57[0] = 0;
  v53 = 0;
  v17 = JetMove(v16, v15, 0x80000000, 0);
  if ( v17 )
    goto LABEL_4;
  if ( cRow )
  {
    v17 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), cRow, 0);
LABEL_4:
    if ( ((v17 + 1603) & 0xFFFFFFFD) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
      }
      goto LABEL_112;
    }
    if ( v17 )
    {
      if ( v17 == -529 || v17 == -1092 || v17 == -1808 )
      {
        v18 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v17 == -1011 )
      {
        v18 = -2147024882;
      }
      else
      {
        v19 = -v17;
        if ( v17 > 0 )
          LOWORD(v19) = v17;
        v18 = v17 & 0x8E5E0000 | (unsigned __int16)v19 | 0xE5E0000;
      }
      v53 = v18;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v17);
      }
      goto LABEL_107;
    }
  }
  v20 = 0;
  v21 = (RTL_SRWLOCK *)(**((_QWORD **)this + 5) + 24LL);
  AcquireSRWLockShared(v21);
  for ( i = *(_QWORD **)(**((_QWORD **)this + 5) + 32LL); i; i = (_QWORD *)*i )
  {
    v23 = i[2];
    if ( *(_DWORD *)v23 == 2 )
    {
      if ( ++v20 > 1 )
      {
        v12 = 0;
        v56[0] = 0;
        break;
      }
      v12 = *(GUID *)(v23 + 516);
      v24 = (_WORD *)(v23 + 4);
      v25 = 2147483646;
      v26 = v56;
      v27 = 256;
      do
      {
        if ( !v25 )
          break;
        if ( !*v24 )
          break;
        *v26++ = *v24++;
        --v25;
        --v27;
      }
      while ( v27 );
    }
    else
    {
      if ( *(_DWORD *)v23 != 1 )
        continue;
      if ( ++v13 > 1 )
      {
        v14 = 0;
        v57[0] = 0;
        break;
      }
      v14 = *(GUID *)(v23 + 516);
      v28 = (_WORD *)(v23 + 4);
      v29 = 2147483646;
      v26 = v57;
      v27 = 256;
      do
      {
        if ( !v29 )
          break;
        if ( !*v28 )
          break;
        *v26++ = *v28++;
        --v29;
        --v27;
      }
      while ( v27 );
    }
    v30 = v26 - 1;
    if ( v27 )
      v30 = v26;
    *v30 = 0;
    v53 = v27 == 0 ? 0x8007007A : 0;
  }
  v31 = 0;
  if ( v21 )
    ReleaseSRWLockShared(v21);
  v32 = (unsigned int *)v55[0];
  v33 = v54;
  *(_DWORD *)v55[0] = 0;
  while ( 2 )
  {
    v51[0] = 0;
    CurrentPinnedRecord = TieringPinnedSession::GetCurrentPinnedRecord(this, (struct TE_FILE_ID_128 *)&v55[1], v51, 0);
    v35 = CurrentPinnedRecord;
    if ( CurrentPinnedRecord )
    {
      if ( CurrentPinnedRecord == -529 || CurrentPinnedRecord == -1092 || CurrentPinnedRecord == -1808 )
      {
        v18 = ATL::AtlHresultFromWin32(112);
      }
      else if ( CurrentPinnedRecord == -1011 )
      {
        v18 = -2147024882;
      }
      else
      {
        v49 = -CurrentPinnedRecord;
        if ( v49 < 0 )
          LOWORD(v49) = v35;
        v18 = v35 & 0x8E5E0000 | (unsigned __int16)v49 | 0xE5E0000;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          v31,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          v35);
      }
      if ( v31 )
        v18 = 0;
      goto LABEL_106;
    }
    memset_0((char *)a6 + 16, 0, 0x240u);
    v36 = (v51[0] & 1) == 0;
    *(_OWORD *)a6 = *(_OWORD *)&v55[1];
    if ( !v36 )
    {
      if ( (a3 & 0xFFFFFFFD) == 0 )
      {
        *((GUID *)a6 + 1) = v12;
        *((_DWORD *)a6 + 136) = 2;
        v37 = v56;
        v38 = 2147483646;
        v39 = (_WORD *)((char *)a6 + 32);
        v40 = 256;
        do
        {
          if ( !v38 )
            break;
          if ( !*v37 )
            break;
          *v39++ = *v37++;
          --v38;
          --v40;
        }
        while ( v40 );
        goto LABEL_57;
      }
LABEL_64:
      if ( v31 < v33 )
        continue;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          v31,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
      }
      v53 = 0;
LABEL_112:
      CHResultImp::~CHResultImp((CHResultImp *)&v52);
      return 0;
    }
    break;
  }
  if ( a3 > 1 )
    goto LABEL_64;
  *((GUID *)a6 + 1) = v14;
  *((_DWORD *)a6 + 136) = 1;
  v41 = v57;
  v42 = 2147483646;
  v39 = (_WORD *)((char *)a6 + 32);
  v40 = 256;
  do
  {
    if ( !v42 )
      break;
    if ( !*v41 )
      break;
    *v39++ = *v41++;
    --v42;
    --v40;
  }
  while ( v40 );
LABEL_57:
  v43 = v39 - 1;
  if ( v40 )
    v43 = v39;
  *v43 = 0;
  *(_QWORD *)((char *)a6 + 548) = 0;
  v44 = 2LL * v31;
  v53 = v40 == 0 ? 0x8007007A : 0;
  ++v31;
  *((_QWORD *)a5 + v44 + 2) = *(_QWORD *)a6;
  *((_QWORD *)a5 + v44 + 3) = *(_QWORD *)a6;
  *v32 = v31;
  *(_DWORD *)a5 = v31;
  do
  {
    v45 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
    v46 = v45;
  }
  while ( v45 == -1017 );
  if ( ((v45 + 1603) & 0xFFFFFFFD) != 0 )
  {
    v47 = 0;
    switch ( v45 )
    {
      case 0:
        a6 = (struct __MIDL___MIDL_itf_tieringengine_0000_0000_0006 *)((char *)a6 + 592);
        goto LABEL_64;
      case -529:
      case -1092:
      case -1808:
        v18 = ATL::AtlHresultFromWin32(112);
        break;
      case -1011:
        v18 = -2147024882;
        break;
      default:
        v48 = -v45;
        if ( v48 < 0 )
          LOWORD(v48) = v46;
        v18 = v46 & 0x8E5E0000 | (unsigned __int16)v48 | 0xE5E0000;
        break;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        v31,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v46);
      v47 = 0;
    }
    if ( v31 )
      v18 = v47;
LABEL_106:
    v53 = v18;
    goto LABEL_107;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
      v31,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  }
  v18 = 0;
LABEL_107:
  CHResultImp::~CHResultImp((CHResultImp *)&v52);
  return v18;
}

```

## disassembly

```asm
0x14001fca0  mov     rax, rsp
0x14001fca3  mov     [rax+18h], rbx
0x14001fca7  push    rbp
0x14001fca8  push    rsi
0x14001fca9  push    rdi
0x14001fcaa  push    r12
0x14001fcac  push    r13
0x14001fcae  push    r14
0x14001fcb0  push    r15
0x14001fcb2  lea     rbp, [rax-3D8h]
0x14001fcb9  sub     rsp, 4A0h
0x14001fcc0  movaps  xmmword ptr [rax-48h], xmm6
0x14001fcc4  movaps  xmmword ptr [rax-58h], xmm7
0x14001fcc8  mov     rax, cs:__security_cookie
0x14001fccf  xor     rax, rsp
0x14001fcd2  mov     [rbp+3D0h+var_60], rax
0x14001fcd9  mov     rax, gs:58h
0x14001fce2  mov     rsi, rcx
0x14001fce5  mov     rdi, [rbp+3D0h+arg_30]
0x14001fcec  mov     ebx, edx
0x14001fcee  mov     r12, [rbp+3D0h+arg_20]
0x14001fcf5  mov     r13d, r8d
0x14001fcf8  mov     r14, [rbp+3D0h+arg_28]
0x14001fcff  mov     rcx, [rax]
0x14001fd02  lea     rax, aTieringpinneds_0; "TieringPinnedSession::GetPinnedFilesLis"...
0x14001fd09  mov     edx, 8
0x14001fd0e  mov     dword ptr [rsp+4D0h+var_488], r9d
0x14001fd13  mov     qword ptr [rsp+4D0h+var_480], rdi
0x14001fd18  mov     [rdx+rcx], rax
0x14001fd1c  lea     rcx, [rsp+4D0h+var_498]; this
0x14001fd21  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001fd26  movups  xmm6, xmmword ptr cs:?g_FlashTierTestGuid@@3U_GUID@@A.Data1; _GUID g_FlashTierTestGuid ...
0x14001fd2d  xor     r15d, r15d
0x14001fd30  xor     r9d, r9d; grbit
0x14001fd33  movups  xmm7, xmmword ptr cs:?g_DiskTierTestGuid@@3U_GUID@@A.Data1; _GUID g_DiskTierTestGuid ...
0x14001fd3a  mov     [rdi], r15d
0x14001fd3d  mov     r8d, 80000000h; cRow
0x14001fd43  mov     rdx, [rsi+18h]; tableid
0x14001fd47  xorps   xmm0, xmm0
0x14001fd4a  mov     rcx, [rsi+8]; sesid
0x14001fd4e  movups  xmmword ptr [rsp+4D0h+var_480+8], xmm0
0x14001fd53  mov     [rsp+4D0h+var_460], r15w
0x14001fd59  mov     [rbp+3D0h+var_260], r15w
0x14001fd61  mov     [rsp+4D0h+var_490], r15d
0x14001fd66  call    cs:__imp_JetMove
0x14001fd6c  mov     r10d, eax
0x14001fd6f  test    eax, eax
0x14001fd71  jnz     short loc_14001FD92
0x14001fd73  test    ebx, ebx
0x14001fd75  jz      loc_14001FE58
0x14001fd7b  mov     rdx, [rsi+18h]; tableid
0x14001fd7f  xor     r9d, r9d; grbit
0x14001fd82  mov     rcx, [rsi+8]; sesid
0x14001fd86  mov     r8d, ebx; cRow
0x14001fd89  call    cs:__imp_JetMove
0x14001fd8f  mov     r10d, eax
0x14001fd92  lea     eax, [r10+643h]
0x14001fd99  test    eax, 0FFFFFFFDh
0x14001fd9e  jz      loc_14002030D
0x14001fda4  test    r10d, r10d
0x14001fda7  jz      loc_14001FE58
0x14001fdad  cmp     r10d, 0FFFFFDEFh
0x14001fdb4  jz      short loc_14001FDF6
0x14001fdb6  cmp     r10d, 0FFFFFBBCh
0x14001fdbd  jz      short loc_14001FDF6
0x14001fdbf  cmp     r10d, 0FFFFF8F0h
0x14001fdc6  jz      short loc_14001FDF6
0x14001fdc8  cmp     r10d, 0FFFFFC0Dh
0x14001fdcf  jnz     short loc_14001FDD8
0x14001fdd1  mov     ebx, 8007000Eh
0x14001fdd6  jmp     short loc_14001FE02
0x14001fdd8  mov     eax, r10d
0x14001fddb  neg     eax
0x14001fddd  cmovs   eax, r10d
0x14001fde1  movzx   ebx, ax
0x14001fde4  mov     eax, r10d
0x14001fde7  and     eax, 8E5E0000h
0x14001fdec  or      ebx, eax
0x14001fdee  or      ebx, 0E5E0000h
0x14001fdf4  jmp     short loc_14001FE02
0x14001fdf6  mov     ecx, 70h ; 'p'; unsigned int
0x14001fdfb  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001fe00  mov     ebx, eax
0x14001fe02  mov     [rsp+4D0h+var_490], ebx
0x14001fe06  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe0d  lea     rax, WPP_GLOBAL_Control
0x14001fe14  cmp     rcx, rax
0x14001fe17  jz      loc_1400202FF
0x14001fe1d  test    byte ptr [rcx+1Ch], 1
0x14001fe21  jz      loc_1400202FF
0x14001fe27  cmp     byte ptr [rcx+19h], 2
0x14001fe2b  jb      loc_1400202FF
0x14001fe31  mov     r9, [rsi+28h]
0x14001fe35  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001fe3c  mov     rcx, [rcx+10h]
0x14001fe40  mov     edx, 0Bh
0x14001fe45  mov     [rsp+4D0h+var_4B0], r10d
0x14001fe4a  mov     r9, [r9+70h]
0x14001fe4e  call    WPP_SF_Sd
0x14001fe53  jmp     loc_1400202FF
0x14001fe58  mov     rax, [rsi+28h]
0x14001fe5c  mov     edi, r15d
0x14001fe5f  mov     rbx, [rax]
0x14001fe62  add     rbx, 18h
0x14001fe66  mov     rcx, rbx; SRWLock
0x14001fe69  call    cs:__imp_AcquireSRWLockShared
0x14001fe6f  mov     rax, [rsi+28h]
0x14001fe73  xor     r11d, r11d
0x14001fe76  mov     rcx, [rax]
0x14001fe79  mov     r9, [rcx+20h]
0x14001fe7d  jmp     loc_14001FF46
0x14001fe82  mov     rax, [r9+10h]
0x14001fe86  cmp     dword ptr [rax], 2
0x14001fe89  jnz     short loc_14001FED6
0x14001fe8b  inc     edi
0x14001fe8d  cmp     edi, 1
0x14001fe90  jg      loc_14001FF51
0x14001fe96  movups  xmm6, xmmword ptr [rax+204h]
0x14001fe9d  lea     r8, [rax+4]
0x14001fea1  mov     ecx, 7FFFFFFEh
0x14001fea6  lea     rax, [rsp+4D0h+var_460]
0x14001feab  mov     edx, 100h
0x14001feb0  test    rcx, rcx
0x14001feb3  jz      short loc_14001FF24
0x14001feb5  movzx   r10d, word ptr [r8]
0x14001feb9  test    r10w, r10w
0x14001febd  jz      short loc_14001FF24
0x14001febf  mov     [rax], r10w
0x14001fec3  add     r8, 2
0x14001fec7  add     rax, 2
0x14001fecb  dec     rcx
0x14001fece  sub     rdx, 1
0x14001fed2  jnz     short loc_14001FEB0
0x14001fed4  jmp     short loc_14001FF24
0x14001fed6  cmp     dword ptr [rax], 1
0x14001fed9  jnz     short loc_14001FF43
0x14001fedb  inc     r15d
0x14001fede  cmp     r15d, 1
0x14001fee2  jg      short loc_14001FF5C
0x14001fee4  movups  xmm7, xmmword ptr [rax+204h]
0x14001feeb  lea     r8, [rax+4]
0x14001feef  mov     ecx, 7FFFFFFEh
0x14001fef4  lea     rax, [rbp+3D0h+var_260]
0x14001fefb  mov     edx, 100h
0x14001ff00  test    rcx, rcx
0x14001ff03  jz      short loc_14001FF24
0x14001ff05  movzx   r10d, word ptr [r8]
0x14001ff09  test    r10w, r10w
0x14001ff0d  jz      short loc_14001FF24
0x14001ff0f  mov     [rax], r10w
0x14001ff13  add     r8, 2
0x14001ff17  add     rax, 2
0x14001ff1b  dec     rcx
0x14001ff1e  sub     rdx, 1
0x14001ff22  jnz     short loc_14001FF00
0x14001ff24  lea     rcx, [rax-2]
0x14001ff28  test    rdx, rdx
0x14001ff2b  cmovnz  rcx, rax
0x14001ff2f  neg     rdx
0x14001ff32  sbb     eax, eax
0x14001ff34  not     eax
0x14001ff36  and     eax, 8007007Ah
0x14001ff3b  mov     [rcx], r11w
0x14001ff3f  mov     [rsp+4D0h+var_490], eax
0x14001ff43  mov     r9, [r9]
0x14001ff46  test    r9, r9
0x14001ff49  jnz     loc_14001FE82
0x14001ff4f  jmp     short loc_14001FF67
0x14001ff51  xorps   xmm6, xmm6
0x14001ff54  mov     [rsp+4D0h+var_460], r11w
0x14001ff5a  jmp     short loc_14001FF67
0x14001ff5c  xorps   xmm7, xmm7
0x14001ff5f  mov     [rbp+3D0h+var_260], r11w
0x14001ff67  mov     edi, r11d
0x14001ff6a  test    rbx, rbx
0x14001ff6d  jz      short loc_14001FF7B
0x14001ff6f  mov     rcx, rbx; SRWLock
0x14001ff72  call    cs:__imp_ReleaseSRWLockShared
0x14001ff78  xor     r11d, r11d
0x14001ff7b  mov     rbx, qword ptr [rsp+4D0h+var_480]
0x14001ff80  mov     r15d, dword ptr [rsp+4D0h+var_488]
0x14001ff85  mov     [rbx], r11d
0x14001ff88  xor     r9d, r9d; unsigned __int8 *
0x14001ff8b  mov     [rsp+4D0h+var_4A0], r11b
0x14001ff90  lea     r8, [rsp+4D0h+var_4A0]; unsigned __int8 *
0x14001ff95  mov     rcx, rsi; this
0x14001ff98  lea     rdx, [rsp+4D0h+var_480+8]; struct TE_FILE_ID_128 *
0x14001ff9d  call    ?GetCurrentPinnedRecord@TieringPinnedSession@@QEAAJPEAUTE_FILE_ID_128@@PEAE1@Z; TieringPinnedSession::GetCurrentPinnedRecord(TE_FILE_ID_128 *,uchar *,uchar *)
0x14001ffa2  mov     r8d, eax
0x14001ffa5  test    eax, eax
0x14001ffa7  jnz     loc_140020259
0x14001ffad  lea     rcx, [r14+10h]; void *
0x14001ffb1  xor     edx, edx; Val
0x14001ffb3  mov     r8d, 240h; Size
0x14001ffb9  call    memset_0
0x14001ffbe  test    [rsp+4D0h+var_4A0], 1
0x14001ffc3  movups  xmm0, xmmword ptr [rsp+4D0h+var_480+8]
0x14001ffc8  movdqu  xmmword ptr [r14], xmm0
0x14001ffcd  jz      short loc_140020029
0x14001ffcf  test    r13d, 0FFFFFFFDh
0x14001ffd6  jnz     loc_140020108
0x14001ffdc  movdqu  xmmword ptr [r14+10h], xmm6
0x14001ffe2  mov     dword ptr [r14+220h], 2
0x14001ffed  lea     r8, [rsp+4D0h+var_460]
0x14001fff2  mov     ecx, 7FFFFFFEh
0x14001fff7  lea     rax, [r14+20h]
0x14001fffb  mov     edx, 100h
0x140020000  xor     r10d, r10d
0x140020003  test    rcx, rcx
0x140020006  jz      short loc_140020080
0x140020008  movzx   r9d, word ptr [r8]
0x14002000c  test    r9w, r9w
0x140020010  jz      short loc_140020080
0x140020012  mov     [rax], r9w
0x140020016  add     r8, 2
0x14002001a  add     rax, 2
0x14002001e  dec     rcx
0x140020021  sub     rdx, 1
0x140020025  jnz     short loc_140020003
0x140020027  jmp     short loc_140020080
0x140020029  cmp     r13d, 1
0x14002002d  ja      loc_140020108
0x140020033  movdqu  xmmword ptr [r14+10h], xmm7
0x140020039  mov     dword ptr [r14+220h], 1
0x140020044  lea     r8, [rbp+3D0h+var_260]
0x14002004b  mov     ecx, 7FFFFFFEh
0x140020050  lea     rax, [r14+20h]
0x140020054  mov     edx, 100h
0x140020059  xor     r10d, r10d
0x14002005c  test    rcx, rcx
0x14002005f  jz      short loc_140020080
0x140020061  movzx   r9d, word ptr [r8]
0x140020065  test    r9w, r9w
0x140020069  jz      short loc_140020080
0x14002006b  mov     [rax], r9w
0x14002006f  add     r8, 2
0x140020073  add     rax, 2
0x140020077  dec     rcx
0x14002007a  sub     rdx, 1
0x14002007e  jnz     short loc_14002005C
0x140020080  lea     rcx, [rax-2]
0x140020084  test    rdx, rdx
0x140020087  cmovnz  rcx, rax
0x14002008b  neg     rdx
0x14002008e  sbb     eax, eax
0x140020090  not     eax
0x140020092  mov     [rcx], r10w
0x140020096  and     eax, 8007007Ah
0x14002009b  mov     qword ptr [r14+224h], 0
0x1400200a6  mov     ecx, edi
0x1400200a8  add     rcx, rcx
0x1400200ab  mov     [rsp+4D0h+var_490], eax
0x1400200af  mov     rax, [r14]
0x1400200b2  inc     edi
0x1400200b4  mov     [r12+rcx*8+10h], rax
0x1400200b9  mov     rax, [r14]
0x1400200bc  mov     [r12+rcx*8+18h], rax
0x1400200c1  mov     [rbx], edi
0x1400200c3  mov     [r12], edi
0x1400200c7  mov     rdx, [rsi+18h]; tableid
0x1400200cb  xor     r9d, r9d; grbit
0x1400200ce  mov     rcx, [rsi+8]; sesid
0x1400200d2  lea     r8d, [r9+1]; cRow
0x1400200d6  call    cs:__imp_JetMove
0x1400200dc  mov     r8d, eax
0x1400200df  cmp     eax, 0FFFFFC07h
0x1400200e4  jz      short loc_1400200C7
0x1400200e6  lea     ecx, [rax+643h]
0x1400200ec  test    ecx, 0FFFFFFFDh
0x1400200f2  jz      loc_14002020E
0x1400200f8  xor     r11d, r11d
0x1400200fb  test    eax, eax
0x1400200fd  jnz     short loc_140020165
0x1400200ff  add     r14, 250h
0x140020106  jmp     short loc_14002010B
0x140020108  xor     r11d, r11d
0x14002010b  cmp     edi, r15d
0x14002010e  jb      loc_14001FF88
0x140020114  mov     rcx, cs:WPP_GLOBAL_Control
0x14002011b  lea     rax, WPP_GLOBAL_Control
0x140020122  cmp     rcx, rax
0x140020125  jz      short loc_140020158
0x140020127  test    byte ptr [rcx+1Ch], 1
0x14002012b  jz      short loc_140020158
0x14002012d  cmp     byte ptr [rcx+19h], 4
0x140020131  jb      short loc_140020158
0x140020133  mov     rax, [rsi+28h]
0x140020137  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14002013e  mov     rcx, [rcx+10h]
0x140020142  mov     edx, 0Fh
0x140020147  mov     r9d, edi
0x14002014a  mov     rax, [rax+70h]
0x14002014e  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x140020153  call    WPP_SF_DS
0x140020158  mov     [rsp+4D0h+var_490], 0
0x140020160  jmp     loc_140020349
0x140020165  cmp     r8d, 0FFFFFDEFh
0x14002016c  jz      short loc_1400201AB
0x14002016e  cmp     r8d, 0FFFFFBBCh
0x140020175  jz      short loc_1400201AB
  ... truncated ...
```
