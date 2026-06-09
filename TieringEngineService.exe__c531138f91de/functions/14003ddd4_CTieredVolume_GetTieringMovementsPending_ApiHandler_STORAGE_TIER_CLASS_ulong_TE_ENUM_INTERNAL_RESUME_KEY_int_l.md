# CTieredVolume::GetTieringMovementsPending_ApiHandler(_STORAGE_TIER_CLASS,ulong,_TE_ENUM_INTERNAL_RESUME_KEY *,int *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 * *)

- ea: `0x14003ddd4`
- end: `0x14003e34f`
- name: `?GetTieringMovementsPending_ApiHandler@CTieredVolume@@QEAAJW4_STORAGE_TIER_CLASS@@KPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEAHPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z`
- size: `1403`
- prototype: `__int64 __fastcall(CTieredVolume *this, enum _STORAGE_TIER_CLASS, unsigned int, struct _TE_ENUM_INTERNAL_RESUME_KEY *, int *, int *, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140039b10`

## callees

- `0x140001a00`
- `0x140002db0`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14000bee8`
- `0x14000ccc0`
- `0x14000e9a4`
- `0x1400127dc`
- `0x1400188b8`
- `0x1400197b0`
- `0x14001a1d4`
- `0x14001b328`
- `0x14001d534`
- `0x140021a28`
- `0x140022878`
- `0x14003ddd4`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14003df5f`
- `ntdll!RtlCompareMemory` at `0x14003df5f`

## string_xrefs

- `0x14003de41`: `CTieredVolume::GetTieringMovementsPending_ApiHandler`

## pseudocode

```c
__int64 __fastcall CTieredVolume::GetTieringMovementsPending_ApiHandler(
        CTieredVolume *this,
        enum _STORAGE_TIER_CLASS a2,
        unsigned int a3,
        struct _TE_ENUM_INTERNAL_RESUME_KEY *a4,
        int *a5,
        int *a6,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **a7)
{
  CTieredVolume::CSmartTieringMovementSession *MovementSession; // r13
  int v10; // eax
  int v11; // ebx
  int *v12; // rcx
  int MovementsListForDiskOptimizer; // eax
  _QWORD *v14; // rcx
  int v15; // edx
  int PinnedFilesListForDiskOptimizer; // eax
  int v17; // eax
  int v18; // eax
  _BYTE v22[8]; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h]
  int *v24; // [rsp+58h] [rbp-A8h]
  int *v25; // [rsp+60h] [rbp-A0h]
  struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **v26; // [rsp+68h] [rbp-98h]
  struct _TE_ENUM_INTERNAL_RESUME_KEY *v27; // [rsp+70h] [rbp-90h]
  _BYTE v28[32]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v29; // [rsp+A0h] [rbp-60h]
  char v30; // [rsp+A2h] [rbp-5Eh]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  char v32; // [rsp+B0h] [rbp-50h]
  CTieredVolume::CSmartTieringMovementSession *v33; // [rsp+C0h] [rbp-40h]
  _BYTE v34[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v35; // [rsp+F0h] [rbp-10h]
  char v36; // [rsp+F2h] [rbp-Eh]
  __int64 v37; // [rsp+F8h] [rbp-8h]
  char v38; // [rsp+100h] [rbp+0h]
  __int128 Source1; // [rsp+130h] [rbp+30h] BYREF
  __int128 v40; // [rsp+140h] [rbp+40h]
  __int64 v41; // [rsp+150h] [rbp+50h]

  v27 = a4;
  v25 = a5;
  v24 = a6;
  v26 = a7;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::GetTieringMovementsPending_ApiHandler";
  CHResultImp::CHResultImp((CHResultImp *)v22);
  Source1 = 0;
  v40 = 0;
  v41 = 0;
  v34[0] = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v28[0] = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  MovementSession = CTieredVolume::GetMovementSession((JET_API_PTR)this);
  v33 = MovementSession;
  v10 = CTieredVolume::ReferenceVolume(this, 0);
  v11 = v10;
  v23 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
        *((unsigned int *)this + 32),
        v10);
    }
LABEL_70:
    if ( MovementSession )
    {
      CTieredVolume::CSmartTieringMovementSession::~CSmartTieringMovementSession(MovementSession);
      operator delete(MovementSession);
    }
    goto LABEL_72;
  }
  if ( !a4 || !v24 || (v12 = v25) == 0 )
  {
    MovementsListForDiskOptimizer = ATL::AtlHresultFromWin32(87);
    v11 = MovementsListForDiskOptimizer;
    v23 = MovementsListForDiskOptimizer;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 41;
      goto LABEL_58;
    }
    goto LABEL_59;
  }
  Source1 = *(_OWORD *)a4;
  v40 = *((_OWORD *)a4 + 1);
  v41 = *((_QWORD *)a4 + 4);
  *v24 = 0;
  *v12 = 0;
  if ( RtlCompareMemory((char *)&Source1 + 8, &NullGuid, 0x10u) != 16 && !(_DWORD)v41 )
    goto LABEL_27;
  MovementsListForDiskOptimizer = TieringJetSession::Initialize(
                                    (TieringJetSession *)v28,
                                    (CTieredVolume *)((char *)this + (*((_BYTE *)this + 729) != 0 ? 1504LL : 1344LL)));
  v11 = MovementsListForDiskOptimizer;
  v23 = MovementsListForDiskOptimizer;
  if ( MovementsListForDiskOptimizer < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 42;
LABEL_58:
      WPP_SF_Zd(
        v14[2],
        v15,
        (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
        (_DWORD)this + 672,
        MovementsListForDiskOptimizer);
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  MovementsListForDiskOptimizer = TieringJetSession::OpenJetTable((TieringJetSession *)v28, 0);
  v11 = MovementsListForDiskOptimizer;
  v23 = MovementsListForDiskOptimizer;
  if ( MovementsListForDiskOptimizer >= 0 )
  {
    PinnedFilesListForDiskOptimizer = TieringPinnedSession::GetPinnedFilesListForDiskOptimizer(
                                        (TieringPinnedSession *)v28,
                                        a2,
                                        a3,
                                        v27,
                                        v25,
                                        v24,
                                        v26);
    v11 = PinnedFilesListForDiskOptimizer;
    v23 = PinnedFilesListForDiskOptimizer;
    if ( PinnedFilesListForDiskOptimizer < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_28:
        if ( !*v24 )
        {
          if ( MovementSession )
          {
            MovementsListForDiskOptimizer = TieringJetSession::Initialize(
                                              (TieringJetSession *)v34,
                                              (CTieredVolume *)((char *)this + 1184));
            v11 = MovementsListForDiskOptimizer;
            v23 = MovementsListForDiskOptimizer;
            if ( MovementsListForDiskOptimizer >= 0 )
            {
              MovementsListForDiskOptimizer = TieringJetSession::OpenJetTable((TieringJetSession *)v34, 0);
              v11 = MovementsListForDiskOptimizer;
              v23 = MovementsListForDiskOptimizer;
              if ( MovementsListForDiskOptimizer >= 0 )
              {
                if ( TieringMovementSession::AreMovementTablesPresent(*(TieringMovementSession **)MovementSession) )
                {
                  MovementsListForDiskOptimizer = TieringHeatSession::GetMovementsListForDiskOptimizer(
                                                    (TieringHeatSession *)v34,
                                                    a2,
                                                    a3,
                                                    *(struct TieringMovementSession **)MovementSession,
                                                    v27,
                                                    v25,
                                                    v24,
                                                    v26);
                  v11 = MovementsListForDiskOptimizer;
                  v23 = MovementsListForDiskOptimizer;
                  if ( MovementsListForDiskOptimizer < 0 )
                  {
                    v14 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v15 = 49;
                      goto LABEL_58;
                    }
                  }
                }
                else
                {
                  LOBYTE(MovementsListForDiskOptimizer) = -97;
                  v11 = -2147019873;
                  v23 = -2147019873;
                  v14 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v15 = 48;
                    goto LABEL_58;
                  }
                }
              }
              else
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = 47;
                  goto LABEL_58;
                }
              }
            }
            else
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v15 = 46;
                goto LABEL_58;
              }
            }
          }
          else
          {
            LOBYTE(MovementsListForDiskOptimizer) = -97;
            v11 = -2147019873;
            v23 = -2147019873;
            if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
            {
              v15 = 45;
              goto LABEL_58;
            }
          }
        }
        goto LABEL_59;
      }
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
        (_DWORD)this + 672,
        PinnedFilesListForDiskOptimizer);
    }
LABEL_27:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 43;
    goto LABEL_58;
  }
LABEL_59:
  v17 = TieringJetSession::CloseJetTable((TieringJetSession *)v34, v11 < 0);
  if ( v17 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
      (_DWORD)this + 672,
      v17);
  }
  v18 = TieringJetSession::CloseJetTable((TieringJetSession *)v28, v11 < 0);
  if ( v18 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
      (_DWORD)this + 672,
      v18);
  }
  CTieredVolume::DereferenceVolume((RTL_SRWLOCK *)this);
  if ( MovementSession )
    goto LABEL_70;
LABEL_72:
  TieringJetSession::~TieringJetSession((TieringJetSession *)v28);
  TieringJetSession::~TieringJetSession((TieringJetSession *)v34);
  CHResultImp::~CHResultImp((CHResultImp *)v22);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14003ddd4  push    rbp
0x14003ddd6  push    rbx
0x14003ddd7  push    rdi
0x14003ddd8  push    r12
0x14003ddda  push    r13
0x14003dddc  push    r14
0x14003ddde  lea     rbp, [rsp-68h]
0x14003dde3  sub     rsp, 168h
0x14003ddea  mov     rax, cs:__security_cookie
0x14003ddf1  xor     rax, rsp
0x14003ddf4  mov     [rbp+90h+var_38], rax
0x14003ddf8  mov     rdi, r9
0x14003ddfb  mov     [rsp+190h+var_120], r9
0x14003de00  mov     [rsp+190h+var_14C], r8d
0x14003de05  mov     [rsp+190h+var_150], edx
0x14003de09  mov     r14, rcx
0x14003de0c  mov     rax, [rbp+90h+arg_20]
0x14003de13  mov     [rsp+190h+var_130], rax
0x14003de18  mov     rax, [rbp+90h+arg_28]
0x14003de1f  mov     [rsp+190h+var_138], rax
0x14003de24  mov     rax, [rbp+90h+arg_30]
0x14003de2b  mov     [rsp+190h+var_128], rax
0x14003de30  mov     edx, 8
0x14003de35  mov     rax, gs:58h
0x14003de3e  mov     rcx, [rax]
0x14003de41  lea     rax, aCtieredvolumeG_2; "CTieredVolume::GetTieringMovementsPendi"...
0x14003de48  mov     [rdx+rcx], rax
0x14003de4c  lea     rcx, [rsp+190h+var_148]; this
0x14003de51  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14003de56  nop
0x14003de57  xorps   xmm0, xmm0
0x14003de5a  xor     eax, eax
0x14003de5c  movups  [rbp+90h+Source1], xmm0
0x14003de60  movups  [rbp+90h+var_50], xmm0
0x14003de64  mov     [rbp+90h+var_40], rax
0x14003de68  xor     r12d, r12d
0x14003de6b  mov     [rbp+90h+var_C0], r12b
0x14003de6f  mov     [rbp+90h+var_A0], r12w
0x14003de74  mov     [rbp+90h+var_9E], r12b
0x14003de78  mov     [rbp+90h+var_98], r12
0x14003de7c  mov     [rbp+90h+var_90], r12b
0x14003de80  mov     [rbp+90h+var_110], r12b
0x14003de84  mov     [rbp+90h+var_F0], r12w
0x14003de89  mov     [rbp+90h+var_EE], r12b
0x14003de8d  mov     [rbp+90h+var_E8], r12
0x14003de91  mov     [rbp+90h+var_E0], r12b
0x14003de95  mov     rcx, r14; ulContext
0x14003de98  call    ?GetMovementSession@CTieredVolume@@QEAAPEAVCSmartTieringMovementSession@1@XZ; CTieredVolume::GetMovementSession(void)
0x14003de9d  mov     r13, rax
0x14003dea0  mov     [rbp+90h+var_D0], rax
0x14003dea4  xor     edx, edx; bool
0x14003dea6  mov     rcx, r14; this
0x14003dea9  call    ?ReferenceVolume@CTieredVolume@@QEAAJ_N@Z; CTieredVolume::ReferenceVolume(bool)
0x14003deae  mov     ebx, eax
0x14003deb0  mov     [rsp+190h+var_140], eax
0x14003deb4  test    eax, eax
0x14003deb6  jns     short loc_14003DEFD
0x14003deb8  lea     rdi, WPP_GLOBAL_Control
0x14003debf  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dec6  cmp     rcx, rdi
0x14003dec9  jz      short loc_14003DEF8
0x14003decb  test    byte ptr [rcx+1Ch], 1
0x14003decf  jz      short loc_14003DEF8
0x14003ded1  cmp     byte ptr [rcx+19h], 2
0x14003ded5  jb      short loc_14003DEF8
0x14003ded7  lea     edx, [r12+28h]
0x14003dedc  mov     dword ptr [rsp+190h+var_170], eax
0x14003dee0  mov     r9d, [r14+80h]
0x14003dee7  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003deee  mov     rcx, [rcx+10h]
0x14003def2  call    WPP_SF_Dd
0x14003def7  nop
0x14003def8  jmp     loc_14003E2FC
0x14003defd  lea     r12, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003df04  test    rdi, rdi
0x14003df07  jz      loc_14003E212
0x14003df0d  mov     rax, [rsp+190h+var_138]
0x14003df12  test    rax, rax
0x14003df15  jz      loc_14003E212
0x14003df1b  mov     rcx, [rsp+190h+var_130]
0x14003df20  test    rcx, rcx
0x14003df23  jz      loc_14003E212
0x14003df29  movups  xmm0, xmmword ptr [rdi]
0x14003df2c  movups  [rbp+90h+Source1], xmm0
0x14003df30  movups  xmm1, xmmword ptr [rdi+10h]
0x14003df34  movups  [rbp+90h+var_50], xmm1
0x14003df38  movsd   xmm0, qword ptr [rdi+20h]
0x14003df3d  movsd   [rbp+90h+var_40], xmm0
0x14003df42  mov     dword ptr [rax], 0
0x14003df48  mov     dword ptr [rcx], 0
0x14003df4e  mov     r8d, 10h; Length
0x14003df54  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14003df5b  lea     rcx, [rbp+90h+Source1+8]; Source1
0x14003df5f  call    cs:__imp_RtlCompareMemory
0x14003df65  lea     rdi, WPP_GLOBAL_Control
0x14003df6c  cmp     rax, 10h
0x14003df70  jz      short loc_14003DF7C
0x14003df72  cmp     dword ptr [rbp+90h+var_40], 0
0x14003df76  jz      loc_14003E08F
0x14003df7c  mov     al, [r14+2D9h]
0x14003df83  neg     al
0x14003df85  sbb     rdx, rdx
0x14003df88  and     edx, 0A0h
0x14003df8e  add     rdx, 540h
0x14003df95  add     rdx, r14; struct TieringJetDatabase *
0x14003df98  lea     rcx, [rbp+90h+var_110]; this
0x14003df9c  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x14003dfa1  mov     ebx, eax
0x14003dfa3  mov     [rsp+190h+var_140], eax
0x14003dfa7  test    eax, eax
0x14003dfa9  jns     short loc_14003DFD9
0x14003dfab  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dfb2  cmp     rcx, rdi
0x14003dfb5  jz      loc_14003E25D
0x14003dfbb  test    byte ptr [rcx+1Ch], 1
0x14003dfbf  jz      loc_14003E25D
0x14003dfc5  cmp     byte ptr [rcx+19h], 2
0x14003dfc9  jb      loc_14003E25D
0x14003dfcf  mov     edx, 2Ah ; '*'
0x14003dfd4  jmp     loc_14003E246
0x14003dfd9  xor     edx, edx; bool
0x14003dfdb  lea     rcx, [rbp+90h+var_110]; this
0x14003dfdf  call    ?OpenJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::OpenJetTable(bool)
0x14003dfe4  mov     ebx, eax
0x14003dfe6  mov     [rsp+190h+var_140], eax
0x14003dfea  test    eax, eax
0x14003dfec  jns     short loc_14003E01C
0x14003dfee  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dff5  cmp     rcx, rdi
0x14003dff8  jz      loc_14003E25D
0x14003dffe  test    byte ptr [rcx+1Ch], 1
0x14003e002  jz      loc_14003E25D
0x14003e008  cmp     byte ptr [rcx+19h], 2
0x14003e00c  jb      loc_14003E25D
0x14003e012  mov     edx, 2Bh ; '+'
0x14003e017  jmp     loc_14003E246
0x14003e01c  mov     rax, [rsp+190h+var_128]
0x14003e021  mov     [rsp+190h+var_160], rax; struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **
0x14003e026  mov     rax, [rsp+190h+var_138]
0x14003e02b  mov     [rsp+190h+var_168], rax; int *
0x14003e030  mov     rax, [rsp+190h+var_130]
0x14003e035  mov     [rsp+190h+var_170], rax; int *
0x14003e03a  mov     r9, [rsp+190h+var_120]; struct _TE_ENUM_INTERNAL_RESUME_KEY *
0x14003e03f  mov     r8d, [rsp+190h+var_14C]; unsigned int
0x14003e044  mov     edx, [rsp+190h+var_150]; enum _STORAGE_TIER_CLASS
0x14003e048  lea     rcx, [rbp+90h+var_110]; this
0x14003e04c  call    ?GetPinnedFilesListForDiskOptimizer@TieringPinnedSession@@QEAAJW4_STORAGE_TIER_CLASS@@KPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEAHPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z; TieringPinnedSession::GetPinnedFilesListForDiskOptimizer(_STORAGE_TIER_CLASS,ulong,_TE_ENUM_INTERNAL_RESUME_KEY *,int *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 * *)
0x14003e051  mov     ebx, eax
0x14003e053  mov     [rsp+190h+var_140], eax
0x14003e057  test    eax, eax
0x14003e059  jns     short loc_14003E08F
0x14003e05b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e062  cmp     rcx, rdi
0x14003e065  jz      short loc_14003E096
0x14003e067  test    byte ptr [rcx+1Ch], 1
0x14003e06b  jz      short loc_14003E096
0x14003e06d  cmp     byte ptr [rcx+19h], 2
0x14003e071  jb      short loc_14003E096
0x14003e073  lea     r9, [r14+2A0h]
0x14003e07a  mov     edx, 2Ch ; ','
0x14003e07f  mov     dword ptr [rsp+190h+var_170], eax
0x14003e083  mov     r8, r12
0x14003e086  mov     rcx, [rcx+10h]
0x14003e08a  call    WPP_SF_Zd
0x14003e08f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e096  mov     rax, [rsp+190h+var_138]
0x14003e09b  cmp     dword ptr [rax], 0
0x14003e09e  jnz     loc_14003E25D
0x14003e0a4  test    r13, r13
0x14003e0a7  jnz     short loc_14003E0DA
0x14003e0a9  mov     eax, 8007139Fh
0x14003e0ae  mov     ebx, eax
0x14003e0b0  mov     [rsp+190h+var_140], eax
0x14003e0b4  cmp     rcx, rdi
0x14003e0b7  jz      loc_14003E25D
0x14003e0bd  test    byte ptr [rcx+1Ch], 1
0x14003e0c1  jz      loc_14003E25D
0x14003e0c7  cmp     byte ptr [rcx+19h], 2
0x14003e0cb  jb      loc_14003E25D
0x14003e0d1  lea     edx, [r13+2Dh]
0x14003e0d5  jmp     loc_14003E246
0x14003e0da  lea     rdx, [r14+4A0h]; struct TieringJetDatabase *
0x14003e0e1  lea     rcx, [rbp+90h+var_C0]; this
0x14003e0e5  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x14003e0ea  mov     ebx, eax
0x14003e0ec  mov     [rsp+190h+var_140], eax
0x14003e0f0  test    eax, eax
0x14003e0f2  jns     short loc_14003E122
0x14003e0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e0fb  cmp     rcx, rdi
0x14003e0fe  jz      loc_14003E25D
0x14003e104  test    byte ptr [rcx+1Ch], 1
0x14003e108  jz      loc_14003E25D
0x14003e10e  cmp     byte ptr [rcx+19h], 2
0x14003e112  jb      loc_14003E25D
0x14003e118  mov     edx, 2Eh ; '.'
0x14003e11d  jmp     loc_14003E246
0x14003e122  xor     edx, edx; bool
0x14003e124  lea     rcx, [rbp+90h+var_C0]; this
0x14003e128  call    ?OpenJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::OpenJetTable(bool)
0x14003e12d  mov     ebx, eax
0x14003e12f  mov     [rsp+190h+var_140], eax
0x14003e133  test    eax, eax
0x14003e135  jns     short loc_14003E165
0x14003e137  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e13e  cmp     rcx, rdi
0x14003e141  jz      loc_14003E25D
0x14003e147  test    byte ptr [rcx+1Ch], 1
0x14003e14b  jz      loc_14003E25D
0x14003e151  cmp     byte ptr [rcx+19h], 2
0x14003e155  jb      loc_14003E25D
0x14003e15b  mov     edx, 2Fh ; '/'
0x14003e160  jmp     loc_14003E246
0x14003e165  mov     rcx, [r13+0]; this
0x14003e169  call    ?AreMovementTablesPresent@TieringMovementSession@@QEAA_NXZ; TieringMovementSession::AreMovementTablesPresent(void)
0x14003e16e  test    al, al
0x14003e170  jnz     short loc_14003E1AB
0x14003e172  mov     eax, 8007139Fh
0x14003e177  mov     ebx, eax
0x14003e179  mov     [rsp+190h+var_140], eax
0x14003e17d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e184  cmp     rcx, rdi
0x14003e187  jz      loc_14003E25D
0x14003e18d  test    byte ptr [rcx+1Ch], 1
0x14003e191  jz      loc_14003E25D
0x14003e197  cmp     byte ptr [rcx+19h], 2
0x14003e19b  jb      loc_14003E25D
0x14003e1a1  mov     edx, 30h ; '0'
0x14003e1a6  jmp     loc_14003E246
0x14003e1ab  mov     rax, [rsp+190h+var_128]
0x14003e1b0  mov     [rsp+190h+var_158], rax; struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **
0x14003e1b5  mov     rax, [rsp+190h+var_138]
0x14003e1ba  mov     [rsp+190h+var_160], rax; int *
0x14003e1bf  mov     rax, [rsp+190h+var_130]
0x14003e1c4  mov     [rsp+190h+var_168], rax; int *
0x14003e1c9  mov     rax, [rsp+190h+var_120]
0x14003e1ce  mov     [rsp+190h+var_170], rax; struct _TE_ENUM_INTERNAL_RESUME_KEY *
0x14003e1d3  mov     r9, [r13+0]; struct TieringMovementSession *
0x14003e1d7  mov     r8d, [rsp+190h+var_14C]; unsigned int
0x14003e1dc  mov     edx, [rsp+190h+var_150]; enum _STORAGE_TIER_CLASS
0x14003e1e0  lea     rcx, [rbp+90h+var_C0]; this
0x14003e1e4  call    ?GetMovementsListForDiskOptimizer@TieringHeatSession@@QEAAJW4_STORAGE_TIER_CLASS@@KPEAVTieringMovementSession@@PEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEAHPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z; TieringHeatSession::GetMovementsListForDiskOptimizer(_STORAGE_TIER_CLASS,ulong,TieringMovementSession *,_TE_ENUM_INTERNAL_RESUME_KEY *,int *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 * *)
0x14003e1e9  mov     ebx, eax
0x14003e1eb  mov     [rsp+190h+var_140], eax
0x14003e1ef  test    eax, eax
0x14003e1f1  jns     short loc_14003E25D
0x14003e1f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e1fa  cmp     rcx, rdi
0x14003e1fd  jz      short loc_14003E25D
0x14003e1ff  test    byte ptr [rcx+1Ch], 1
0x14003e203  jz      short loc_14003E25D
0x14003e205  cmp     byte ptr [rcx+19h], 2
0x14003e209  jb      short loc_14003E25D
0x14003e20b  mov     edx, 31h ; '1'
0x14003e210  jmp     short loc_14003E246
0x14003e212  mov     ecx, 57h ; 'W'; unsigned int
0x14003e217  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14003e21c  mov     ebx, eax
0x14003e21e  mov     [rsp+190h+var_140], eax
0x14003e222  lea     rdi, WPP_GLOBAL_Control
0x14003e229  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e230  cmp     rcx, rdi
0x14003e233  jz      short loc_14003E25D
0x14003e235  test    byte ptr [rcx+1Ch], 1
0x14003e239  jz      short loc_14003E25D
0x14003e23b  cmp     byte ptr [rcx+19h], 2
0x14003e23f  jb      short loc_14003E25D
0x14003e241  mov     edx, 29h ; ')'
0x14003e246  mov     dword ptr [rsp+190h+var_170], eax
0x14003e24a  lea     r9, [r14+2A0h]
0x14003e251  mov     r8, r12
0x14003e254  mov     rcx, [rcx+10h]
0x14003e258  call    WPP_SF_Zd
0x14003e25d  mov     eax, ebx
0x14003e25f  shr     eax, 1Fh
0x14003e262  mov     [rsp+190h+var_150], eax
0x14003e266  mov     dl, al; bool
0x14003e268  lea     rcx, [rbp+90h+var_C0]; this
0x14003e26c  call    ?CloseJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::CloseJetTable(bool)
0x14003e271  test    eax, eax
0x14003e273  jns     short loc_14003E2A9
0x14003e275  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e27c  cmp     rcx, rdi
0x14003e27f  jz      short loc_14003E2A9
0x14003e281  test    byte ptr [rcx+1Ch], 1
0x14003e285  jz      short loc_14003E2A9
0x14003e287  cmp     byte ptr [rcx+19h], 2
0x14003e28b  jb      short loc_14003E2A9
0x14003e28d  lea     r9, [r14+2A0h]
0x14003e294  mov     edx, 32h ; '2'
0x14003e299  mov     dword ptr [rsp+190h+var_170], eax
0x14003e29d  mov     r8, r12
0x14003e2a0  mov     rcx, [rcx+10h]
0x14003e2a4  call    WPP_SF_Zd
0x14003e2a9  mov     dl, byte ptr [rsp+190h+var_150]; bool
0x14003e2ad  lea     rcx, [rbp+90h+var_110]; this
0x14003e2b1  call    ?CloseJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::CloseJetTable(bool)
0x14003e2b6  test    eax, eax
0x14003e2b8  jns     short loc_14003E2EE
0x14003e2ba  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
