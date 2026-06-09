# CConnectJob::FillAssociationCompletionParams(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,DOT11_CONNECTION_INFO *,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS * *,ulong *,uchar *)

- ea: `0x1400a5520`
- end: `0x1400a5b13`
- name: `?FillAssociationCompletionParams@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEAUDOT11_CONNECTION_INFO@@PEAPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@PEAKPEAE@Z`
- size: `1523`
- prototype: `__int64 __fastcall(CConnectJob *this, struct CBSSEntry *, struct _WDI_ASSOCIATION_RESULT_CONTAINER *, struct DOT11_CONNECTION_INFO *, struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS **, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400ab718`

## callees

- `0x140009420`
- `0x140017130`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140023ef4`
- `0x14002bcc8`
- `0x140071720`
- `0x140073fdc`
- `0x140074224`
- `0x1400742b4`
- `0x1400a5520`
- `0x1400ab50c`
- `0x1400b22b0`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400dfe00`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillAssociationCompletionParams(
        CConnectJob *this,
        struct CBSSEntry *a2,
        struct _WDI_ASSOCIATION_RESULT_CONTAINER *a3,
        struct DOT11_CONNECTION_INFO *a4,
        struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS **a5,
        unsigned int *a6,
        unsigned __int8 *a7)
{
  int v7; // ebx
  char v9; // si
  _OWORD *v12; // r12
  bool v14; // zf
  CPropertyCache *v15; // rax
  unsigned __int8 v16; // r15
  CPropertyCache *PortPropertyCache; // rax
  int v18; // edx
  unsigned int v19; // esi
  int v20; // r8d
  int v21; // edx
  _OWORD *v22; // rbx
  int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // r8
  struct CBSSEntry *v26; // r12
  int v27; // edx
  int v28; // r8d
  void *v29; // r9
  int v30; // eax
  size_t v31; // r8
  unsigned int v32; // eax
  __int64 v33; // rcx
  CPropertyCache *v34; // rax
  int v35; // edx
  int v36; // r8d
  bool v37; // cf
  __int16 v38; // ax
  __int64 v40; // [rsp+38h] [rbp-C8h]
  unsigned __int8 v41; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v42[3]; // [rsp+51h] [rbp-AFh] BYREF
  unsigned int Size; // [rsp+54h] [rbp-ACh] BYREF
  int Size_4; // [rsp+58h] [rbp-A8h]
  struct CBSSEntry *v45; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v46; // [rsp+68h] [rbp-98h]
  unsigned int *v47; // [rsp+70h] [rbp-90h]
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS **v48; // [rsp+78h] [rbp-88h]
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  int v50; // [rsp+88h] [rbp-78h]
  __int16 v51; // [rsp+8Ch] [rbp-74h]
  int v52; // [rsp+8Eh] [rbp-72h]
  __int16 v53; // [rsp+92h] [rbp-6Eh]
  int v54; // [rsp+94h] [rbp-6Ch]
  __int128 v55; // [rsp+98h] [rbp-68h]
  __int128 v56; // [rsp+A8h] [rbp-58h]
  __int64 v57; // [rsp+B8h] [rbp-48h]
  _BYTE v58[128]; // [rsp+C0h] [rbp-40h] BYREF

  v9 = 0;
  v45 = a2;
  *a7 = 0;
  v12 = (_OWORD *)((char *)this + 1380);
  v48 = a5;
  v47 = a6;
  *a6 = 0;
  *a5 = 0;
  v46 = a7;
  memset((char *)this + 1380, 0, 0x74u);
  v14 = *((_DWORD *)a3 + 13) == 3;
  LOBYTE(v7) = 0;
  Size_4 = v7;
  v42[0] = 0;
  if ( v14 )
  {
    v15 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67) + 8LL) + 8LL))(*((_QWORD *)this + 67) + 8LL);
    CPropertyCache::GetPropertyBoolean(v15, 0x87u, v42);
    v9 = v42[0];
    if ( v42[0] )
      Size_4 = (*((_BYTE *)a2 + 797) & 3) == 2;
  }
  v16 = 0;
  v41 = 0;
  if ( *((_BYTE *)this + 5518) )
  {
    if ( a4 )
    {
      PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
      CPropertyCache::GetPropertyBoolean(PortPropertyCache, 0x14u, &v41);
      v16 = v41;
      if ( !v41
        || (unsigned __int8)CConnectHelpers::IsIMDAssocForFTRoamRequired(
                              *((unsigned int *)this + 156),
                              *((unsigned int *)this + 158)) )
      {
        v16 = 0;
      }
    }
  }
  Size = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v57 = 0;
  v56 = 0;
  memset(v58, 0, 0x78u);
  `vector constructor iterator'(
    v58,
    0x18u,
    5u,
    (void *(*)(void *))FTMicDataHelpers::FT_PER_LINK_MIC_DATA::FT_PER_LINK_MIC_DATA);
  v19 = CConnectJob::SetAssociationCompletionOffsetData(
          this,
          v45,
          a3,
          (unsigned __int8 *)0x74,
          (CConnectJob *)((char *)this + 1380),
          a4,
          v9,
          1u,
          (struct FTMicDataHelpers::FT_MIC_DATA *)((unsigned __int64)&v49 & -(__int64)(v16 != 0)),
          &Size);
  if ( v19 )
  {
    v22 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 2;
      LODWORD(v40) = v19;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        v20,
        123,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v40);
      goto LABEL_15;
    }
  }
  else
  {
    v22 = operator new(Size);
    if ( !v22 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v40) = Size;
        LOBYTE(v21) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          v23,
          122,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v40);
      }
      v19 = 10;
    }
  }
  if ( v19 )
  {
LABEL_15:
    Size = 116;
    v22 = (_OWORD *)((char *)this + 1380);
    memset((char *)this + 1380, 0, 0x74u);
    v26 = v45;
    goto LABEL_16;
  }
  v31 = Size;
  *v46 = 1;
  memset(v22, 0, v31);
  *v22 = *v12;
  v22[1] = *(_OWORD *)((char *)this + 1396);
  v22[2] = *(_OWORD *)((char *)this + 1412);
  v22[3] = *(_OWORD *)((char *)this + 1428);
  v22[4] = *(_OWORD *)((char *)this + 1444);
  v22[5] = *(_OWORD *)((char *)this + 1460);
  v22[6] = *(_OWORD *)((char *)this + 1476);
  v26 = v45;
  *((_DWORD *)v22 + 28) = *((_DWORD *)this + 373);
  v32 = CConnectJob::SetAssociationCompletionOffsetData(
          this,
          v26,
          a3,
          (unsigned __int8 *)Size,
          (struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)v22,
          a4,
          v42[0],
          0,
          (struct FTMicDataHelpers::FT_MIC_DATA *)((unsigned __int64)&v49 & -(__int64)(v16 != 0)),
          &Size);
  v19 = v32;
  if ( v32 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v40) = v32;
    LOBYTE(v24) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v24,
      v25,
      124,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v40);
  }
LABEL_16:
  *((_DWORD *)v22 + 1) = *((_DWORD *)this + 332);
  *((_WORD *)v22 + 4) = *((_WORD *)this + 666);
  *((_BYTE *)v22 + 16) = *((_BYTE *)a3 + 20);
  *((_BYTE *)v22 + 17) = *((_BYTE *)a3 + 20);
  *((_DWORD *)v22 + 13) = CDot11ToWabiConverter::MapAuthAlgorithm(
                            *((unsigned int *)a3 + 6),
                            v24,
                            v25,
                            &WPP_RECORDER_INITIALIZED);
  *((_DWORD *)v22 + 14) = CDot11ToWabiConverter::MapCipherAlgorithm(*((unsigned int *)a3 + 7));
  *((_DWORD *)v22 + 15) = CDot11ToWabiConverter::MapCipherAlgorithm(*((unsigned int *)a3 + 8));
  *((_DWORD *)v22 + 22) = CDot11ToWabiConverter::MapCipherAlgorithm(*((unsigned int *)a3 + 9));
  *((_BYTE *)v22 + 72) = *((_BYTE *)a3 + 40);
  *((_BYTE *)v22 + 73) = *((_BYTE *)a3 + 41);
  *((_BYTE *)v22 + 74) = *((_BYTE *)a3 + 42) != 0;
  if ( *((_DWORD *)a3 + 11) == 1 )
  {
    v30 = 0;
  }
  else if ( *((_DWORD *)a3 + 11) == 2 )
  {
    v30 = 1;
  }
  else
  {
    v30 = 2;
  }
  *((_DWORD *)v22 + 19) = v30;
  *((_DWORD *)v22 + 23) = *((_DWORD *)a3 + 12);
  v33 = *((unsigned int *)a3 + 3);
  if ( (_DWORD)v33 || !v19 )
  {
    v19 = CWabiToDot11Converter::MapAssocStatus(v33, *((unsigned __int16 *)a3 + 8), 0);
  }
  else if ( WPP_RECORDER_INITIALIZED != v29 )
  {
    LOBYTE(v27) = 2;
    LODWORD(v40) = v19;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v27,
      v28,
      125,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v40);
  }
  *((_DWORD *)v22 + 3) = v19;
  v41 = 0;
  v34 = COidJobBase::GetPortPropertyCache(this);
  CPropertyCache::GetPropertyBoolean(v34, 0x14u, &v41);
  if ( *((_BYTE *)this + 5518)
    && v41
    && !(unsigned __int8)CConnectHelpers::IsIMDAssocForFTRoamRequired(
                           *((unsigned int *)this + 156),
                           *((unsigned int *)this + 158)) )
  {
    *((_DWORD *)v22 + 24) = 1;
  }
  else
  {
    v37 = (_BYTE)Size_4 != 0;
    LOBYTE(Size_4) = -(char)Size_4;
    *((_DWORD *)v22 + 24) = v37 ? 2 : 0;
  }
  if ( a4 )
  {
    if ( Size < *((_DWORD *)v22 + 26) + *((_DWORD *)v22 + 25) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v35) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v35,
          v36,
          126,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
    }
    else
    {
      *((_DWORD *)a4 + 14) = *((_DWORD *)v22 + 13);
      *((_DWORD *)a4 + 15) = *((_DWORD *)v22 + 14);
      *((_DWORD *)a4 + 16) = *((_DWORD *)v22 + 15);
      *((_DWORD *)a4 + 17) = *((_DWORD *)v22 + 22);
      if ( v26 && *((_DWORD *)v22 + 13) == 9 )
        v38 = *((_WORD *)v26 + 23);
      else
        v38 = 0;
      *((_WORD *)a4 + 36) = v38;
      memmove((char *)v22 + *((unsigned int *)v22 + 25), a4, *((unsigned int *)v22 + 26));
    }
  }
  *v47 = Size;
  *v48 = (struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)v22;
  `vector destructor iterator'(
    v58,
    0x18u,
    5u,
    (void (*)(void *))FTMicDataHelpers::FT_PER_LINK_MIC_DATA::~FT_PER_LINK_MIC_DATA);
  return v19;
}

```

## disassembly

```asm
0x1400a5520  push    rbp
0x1400a5522  push    rbx
0x1400a5523  push    rsi
0x1400a5524  push    rdi
0x1400a5525  push    r12
0x1400a5527  push    r13
0x1400a5529  push    r14
0x1400a552b  push    r15
0x1400a552d  lea     rbp, [rsp-58h]
0x1400a5532  sub     rsp, 158h
0x1400a5539  mov     rax, cs:__security_cookie
0x1400a5540  xor     rax, rsp
0x1400a5543  mov     [rbp+90h+var_50], rax
0x1400a5547  mov     rax, [rbp+90h+arg_30]
0x1400a554e  mov     rdi, rcx
0x1400a5551  mov     rcx, [rbp+90h+arg_20]
0x1400a5558  xor     esi, esi
0x1400a555a  mov     r15, rdx
0x1400a555d  mov     [rsp+190h+var_130], rdx
0x1400a5562  mov     rdx, [rbp+90h+arg_28]
0x1400a5569  mov     r13, r8
0x1400a556c  mov     [rax], sil
0x1400a556f  lea     r12, [rdi+564h]
0x1400a5576  mov     [rsp+190h+var_118], rcx
0x1400a557b  lea     r8d, [rsi+74h]; Size
0x1400a557f  mov     [rsp+190h+var_120], rdx
0x1400a5584  mov     r14, r9
0x1400a5587  mov     [rdx], esi
0x1400a5589  xor     edx, edx; Val
0x1400a558b  mov     [rcx], rsi
0x1400a558e  mov     rcx, r12; void *
0x1400a5591  mov     [rsp+190h+var_128], rax
0x1400a5596  call    memset
0x1400a559b  cmp     dword ptr [r13+34h], 3
0x1400a55a0  mov     bl, sil
0x1400a55a3  mov     dword ptr [rsp+190h+Size+4], ebx
0x1400a55a7  mov     [rsp+190h+var_13F], sil
0x1400a55ac  jnz     short loc_1400A55FB
0x1400a55ae  mov     rcx, [rdi+218h]
0x1400a55b5  add     rcx, 8
0x1400a55b9  mov     rax, [rcx]
0x1400a55bc  mov     rax, [rax+8]
0x1400a55c0  call    _guard_dispatch_icall
0x1400a55c5  lea     r8, [rsp+190h+var_13F]; unsigned __int8 *
0x1400a55ca  mov     edx, 87h; unsigned int
0x1400a55cf  mov     rcx, rax; this
0x1400a55d2  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400a55d7  mov     sil, [rsp+190h+var_13F]
0x1400a55dc  test    sil, sil
0x1400a55df  jz      short loc_1400A55FB
0x1400a55e1  mov     al, [r15+31Dh]
0x1400a55e8  mov     ecx, 1
0x1400a55ed  and     al, 3
0x1400a55ef  movzx   ebx, bl
0x1400a55f2  cmp     al, 2
0x1400a55f4  cmovz   ebx, ecx
0x1400a55f7  mov     dword ptr [rsp+190h+Size+4], ebx
0x1400a55fb  xor     r15b, r15b
0x1400a55fe  mov     [rsp+190h+var_140], r15b
0x1400a5603  cmp     [rdi+158Eh], r15b
0x1400a560a  jz      short loc_1400A564D
0x1400a560c  test    r14, r14
0x1400a560f  jz      short loc_1400A564D
0x1400a5611  mov     rcx, rdi; this
0x1400a5614  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400a5619  lea     r8, [rsp+190h+var_140]; unsigned __int8 *
0x1400a561e  mov     edx, 14h; unsigned int
0x1400a5623  mov     rcx, rax; this
0x1400a5626  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400a562b  mov     r15b, [rsp+190h+var_140]
0x1400a5630  test    r15b, r15b
0x1400a5633  jz      short loc_1400A564A
0x1400a5635  mov     edx, [rdi+278h]
0x1400a563b  mov     ecx, [rdi+270h]
0x1400a5641  call    ?IsIMDAssocForFTRoamRequired@CConnectHelpers@@YA_NW4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z; CConnectHelpers::IsIMDAssocForFTRoamRequired(_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS)
0x1400a5646  test    al, al
0x1400a5648  jz      short loc_1400A564D
0x1400a564a  xor     r15b, r15b
0x1400a564d  xor     eax, eax
0x1400a564f  mov     dword ptr [rsp+190h+Size], 0
0x1400a5657  xorps   xmm0, xmm0
0x1400a565a  mov     [rbp+90h+var_110], rax
0x1400a565e  xor     edx, edx; Val
0x1400a5660  mov     [rbp+90h+var_108], eax
0x1400a5663  lea     rcx, [rbp+90h+var_D0]; void *
0x1400a5667  mov     [rbp+90h+var_104], ax
0x1400a566b  lea     r8d, [rax+78h]; Size
0x1400a566f  mov     [rbp+90h+var_102], eax
0x1400a5672  mov     [rbp+90h+var_FE], ax
0x1400a5676  mov     [rbp+90h+var_FC], eax
0x1400a5679  movups  [rbp+90h+var_F8], xmm0
0x1400a567d  mov     [rbp+90h+var_D8], rax
0x1400a5681  movups  [rbp+90h+var_E8], xmm0
0x1400a5685  call    memset
0x1400a568a  mov     edx, 18h; unsigned __int64
0x1400a568f  lea     r9, ??0FT_PER_LINK_MIC_DATA@FTMicDataHelpers@@QEAA@XZ; void *(*)(void *)
0x1400a5696  lea     rcx, [rbp+90h+var_D0]; void *
0x1400a569a  lea     r8d, [rdx-13h]; unsigned __int64
0x1400a569e  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400a56a3  mov     rdx, [rsp+190h+var_130]; struct CBSSEntry *
0x1400a56a8  mov     al, r15b
0x1400a56ab  neg     al
0x1400a56ad  mov     r9d, 74h ; 't'; unsigned int
0x1400a56b3  lea     rax, [rbp+90h+var_110]
0x1400a56b7  mov     r8, r13; struct _WDI_ASSOCIATION_RESULT_CONTAINER *
0x1400a56ba  sbb     rcx, rcx
0x1400a56bd  and     rcx, rax
0x1400a56c0  lea     rax, [rsp+190h+Size]
0x1400a56c5  mov     [rsp+190h+var_148], rax; unsigned int *
0x1400a56ca  mov     [rsp+190h+var_150], rcx; struct FTMicDataHelpers::FT_MIC_DATA *
0x1400a56cf  mov     rcx, rdi; this
0x1400a56d2  mov     [rsp+190h+var_158], 1; unsigned __int8
0x1400a56d7  mov     [rsp+190h+var_160], sil; unsigned __int8
0x1400a56dc  mov     [rsp+190h+var_168], r14; struct DOT11_CONNECTION_INFO *
0x1400a56e1  mov     [rsp+190h+var_170], r12; struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *
0x1400a56e6  call    ?SetAssociationCompletionOffsetData@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@KPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@PEAUDOT11_CONNECTION_INFO@@EEPEAUFT_MIC_DATA@FTMicDataHelpers@@PEAK@Z; CConnectJob::SetAssociationCompletionOffsetData(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,ulong,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *,DOT11_CONNECTION_INFO *,uchar,uchar,FTMicDataHelpers::FT_MIC_DATA *,ulong *)
0x1400a56eb  mov     esi, eax
0x1400a56ed  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a56f4  test    esi, esi
0x1400a56f6  jnz     loc_1400A5817
0x1400a56fc  mov     ecx, dword ptr [rsp+190h+Size]; unsigned __int64
0x1400a5700  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400a5705  mov     rbx, rax
0x1400a5708  test    rax, rax
0x1400a570b  jnz     short loc_1400A5758
0x1400a570d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a5714  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a571b  jz      short loc_1400A5753
0x1400a571d  mov     ecx, dword ptr [rsp+190h+Size]
0x1400a5721  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a5728  mov     dword ptr [rsp+190h+var_158], ecx
0x1400a572c  lea     r9d, [rsi+7Ah]
0x1400a5730  mov     ecx, [rdi+10h]
0x1400a5733  mov     dl, 2
0x1400a5735  mov     dword ptr [rsp+190h+var_160], ecx
0x1400a5739  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5740  mov     [rsp+190h+var_168], rdi
0x1400a5745  mov     [rsp+190h+var_170], rax
0x1400a574a  mov     rcx, [rcx+40h]
0x1400a574e  call    WPP_RECORDER_SF_qDD
0x1400a5753  mov     esi, 0Ah
0x1400a5758  test    esi, esi
0x1400a575a  jz      loc_1400A585D
0x1400a5760  mov     eax, 74h ; 't'
0x1400a5765  xor     edx, edx; Val
0x1400a5767  mov     r8d, eax; Size
0x1400a576a  mov     dword ptr [rsp+190h+Size], eax
0x1400a576e  mov     rcx, r12; void *
0x1400a5771  mov     rbx, r12
0x1400a5774  call    memset
0x1400a5779  mov     r12, [rsp+190h+var_130]
0x1400a577e  lea     r9, WPP_RECORDER_INITIALIZED
0x1400a5785  lea     r15, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a578c  mov     eax, [rdi+530h]
0x1400a5792  mov     [rbx+4], eax
0x1400a5795  movzx   eax, word ptr [rdi+534h]
0x1400a579c  mov     [rbx+8], ax
0x1400a57a0  mov     al, [r13+14h]
0x1400a57a4  mov     [rbx+10h], al
0x1400a57a7  mov     al, [r13+14h]
0x1400a57ab  mov     [rbx+11h], al
0x1400a57ae  mov     ecx, [r13+18h]
0x1400a57b2  call    ?MapAuthAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_AUTH_ALGORITHM@@W4_DOT11_AUTH_ALGORITHM@@@Z; CDot11ToWabiConverter::MapAuthAlgorithm(_DOT11_AUTH_ALGORITHM)
0x1400a57b7  mov     [rbx+34h], eax
0x1400a57ba  mov     ecx, [r13+1Ch]
0x1400a57be  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x1400a57c3  mov     [rbx+38h], eax
0x1400a57c6  mov     ecx, [r13+20h]
0x1400a57ca  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x1400a57cf  mov     [rbx+3Ch], eax
0x1400a57d2  mov     ecx, [r13+24h]
0x1400a57d6  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x1400a57db  mov     [rbx+58h], eax
0x1400a57de  mov     al, [r13+28h]
0x1400a57e2  mov     [rbx+48h], al
0x1400a57e5  mov     al, [r13+29h]
0x1400a57e9  mov     [rbx+49h], al
0x1400a57ec  cmp     byte ptr [r13+2Ah], 0
0x1400a57f1  setnz   al
0x1400a57f4  mov     [rbx+4Ah], al
0x1400a57f7  mov     ecx, [r13+2Ch]
0x1400a57fb  sub     ecx, 1
0x1400a57fe  jz      loc_1400A5970
0x1400a5804  sub     ecx, 1
0x1400a5807  jz      loc_1400A5969
0x1400a580d  mov     eax, 2
0x1400a5812  jmp     loc_1400A5972
0x1400a5817  xor     ebx, ebx
0x1400a5819  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a5820  jz      loc_1400A5758
0x1400a5826  mov     eax, [rdi+10h]
0x1400a5829  lea     r9d, [rbx+7Bh]
0x1400a582d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5834  mov     dl, 2
0x1400a5836  mov     dword ptr [rsp+190h+var_158], esi
0x1400a583a  mov     dword ptr [rsp+190h+var_160], eax
0x1400a583e  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a5845  mov     [rsp+190h+var_168], rdi
0x1400a584a  mov     rcx, [rcx+40h]
0x1400a584e  mov     [rsp+190h+var_170], rax
0x1400a5853  call    WPP_RECORDER_SF_qDD
0x1400a5858  jmp     loc_1400A5760
0x1400a585d  mov     rax, [rsp+190h+var_128]
0x1400a5862  xor     edx, edx; Val
0x1400a5864  mov     r8d, dword ptr [rsp+190h+Size]; Size
0x1400a5869  mov     rcx, rbx; void *
0x1400a586c  mov     byte ptr [rax], 1
0x1400a586f  call    memset
0x1400a5874  movups  xmm0, xmmword ptr [r12]
0x1400a5879  lea     rcx, [rbp+90h+var_110]
0x1400a587d  neg     r15b
0x1400a5880  mov     r8, r13; struct _WDI_ASSOCIATION_RESULT_CONTAINER *
0x1400a5883  movups  xmmword ptr [rbx], xmm0
0x1400a5886  movups  xmm1, xmmword ptr [r12+10h]
0x1400a588c  movups  xmmword ptr [rbx+10h], xmm1
0x1400a5890  movups  xmm0, xmmword ptr [r12+20h]
0x1400a5896  movups  xmmword ptr [rbx+20h], xmm0
0x1400a589a  movups  xmm1, xmmword ptr [r12+30h]
0x1400a58a0  movups  xmmword ptr [rbx+30h], xmm1
0x1400a58a4  movups  xmm0, xmmword ptr [r12+40h]
0x1400a58aa  movups  xmmword ptr [rbx+40h], xmm0
0x1400a58ae  movups  xmm1, xmmword ptr [r12+50h]
0x1400a58b4  movups  xmmword ptr [rbx+50h], xmm1
0x1400a58b8  movups  xmm0, xmmword ptr [r12+60h]
0x1400a58be  movups  xmmword ptr [rbx+60h], xmm0
0x1400a58c2  mov     eax, [r12+70h]
0x1400a58c7  mov     r12, [rsp+190h+var_130]
0x1400a58cc  mov     [rbx+70h], eax
0x1400a58cf  mov     rdx, r12; struct CBSSEntry *
0x1400a58d2  mov     r9d, dword ptr [rsp+190h+Size]; unsigned int
0x1400a58d7  sbb     rax, rax
0x1400a58da  and     rax, rcx
0x1400a58dd  lea     rcx, [rsp+190h+Size]
0x1400a58e2  mov     [rsp+190h+var_148], rcx; unsigned int *
0x1400a58e7  mov     rcx, rdi; this
0x1400a58ea  mov     [rsp+190h+var_150], rax; struct FTMicDataHelpers::FT_MIC_DATA *
0x1400a58ef  mov     al, [rsp+190h+var_13F]
0x1400a58f3  mov     [rsp+190h+var_158], 0; unsigned __int8
0x1400a58f8  mov     [rsp+190h+var_160], al; unsigned __int8
0x1400a58fc  mov     [rsp+190h+var_168], r14; struct DOT11_CONNECTION_INFO *
0x1400a5901  mov     [rsp+190h+var_170], rbx; struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *
0x1400a5906  call    ?SetAssociationCompletionOffsetData@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@KPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@PEAUDOT11_CONNECTION_INFO@@EEPEAUFT_MIC_DATA@FTMicDataHelpers@@PEAK@Z; CConnectJob::SetAssociationCompletionOffsetData(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,ulong,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *,DOT11_CONNECTION_INFO *,uchar,uchar,FTMicDataHelpers::FT_MIC_DATA *,ulong *)
0x1400a590b  mov     esi, eax
0x1400a590d  test    eax, eax
0x1400a590f  jz      loc_1400A577E
0x1400a5915  lea     r9, WPP_RECORDER_INITIALIZED
0x1400a591c  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1400a5923  jz      loc_1400A5785
0x1400a5929  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5930  lea     r15, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a5937  mov     dword ptr [rsp+190h+var_158], eax
0x1400a593b  mov     r9d, 7Ch ; '|'
0x1400a5941  mov     eax, [rdi+10h]
0x1400a5944  mov     dl, 2
0x1400a5946  mov     dword ptr [rsp+190h+var_160], eax
0x1400a594a  mov     rcx, [rcx+40h]
0x1400a594e  mov     [rsp+190h+var_168], rdi
0x1400a5953  mov     [rsp+190h+var_170], r15
0x1400a5958  call    WPP_RECORDER_SF_qDD
0x1400a595d  lea     r9, WPP_RECORDER_INITIALIZED
0x1400a5964  jmp     loc_1400A578C
0x1400a5969  mov     eax, 1
0x1400a596e  jmp     short loc_1400A5972
0x1400a5970  xor     eax, eax
0x1400a5972  mov     [rbx+4Ch], eax
0x1400a5975  mov     eax, [r13+30h]
0x1400a5979  mov     [rbx+5Ch], eax
0x1400a597c  mov     ecx, [r13+0Ch]
0x1400a5980  test    ecx, ecx
0x1400a5982  jnz     short loc_1400A59BE
0x1400a5984  test    esi, esi
0x1400a5986  jz      short loc_1400A59BE
0x1400a5988  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1400a598f  jz      short loc_1400A59CD
0x1400a5991  mov     eax, [rdi+10h]
0x1400a5994  lea     r9d, [rcx+7Dh]
0x1400a5998  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a599f  mov     dl, 2
0x1400a59a1  mov     dword ptr [rsp+190h+var_158], esi
0x1400a59a5  mov     dword ptr [rsp+190h+var_160], eax
0x1400a59a9  mov     [rsp+190h+var_168], rdi
0x1400a59ae  mov     rcx, [rcx+40h]
0x1400a59b2  mov     [rsp+190h+var_170], r15
0x1400a59b7  call    WPP_RECORDER_SF_qDD
0x1400a59bc  jmp     short loc_1400A59CD
0x1400a59be  movzx   edx, word ptr [r13+10h]
0x1400a59c3  xor     r8d, r8d
0x1400a59c6  call    ?MapAssocStatus@CWabiToDot11Converter@@SAKW4_WDI_ASSOC_STATUS@@G_N@Z; CWabiToDot11Converter::MapAssocStatus(_WDI_ASSOC_STATUS,ushort,bool)
0x1400a59cb  mov     esi, eax
0x1400a59cd  xor     r13d, r13d
0x1400a59d0  mov     [rbx+0Ch], esi
0x1400a59d3  mov     rcx, rdi; this
0x1400a59d6  mov     [rsp+190h+var_140], r13b
0x1400a59db  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400a59e0  lea     r8, [rsp+190h+var_140]; unsigned __int8 *
0x1400a59e5  mov     rcx, rax; this
0x1400a59e8  lea     edx, [r13+14h]; unsigned int
0x1400a59ec  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400a59f1  cmp     [rdi+158Eh], r13b
0x1400a59f8  jz      short loc_1400A5A1F
  ... truncated ...
```
