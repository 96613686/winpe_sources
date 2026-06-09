# CConnectJob::SetAssociationCompletionOffsetData(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,ulong,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *,DOT11_CONNECTION_INFO *,uchar,uchar,FTMicDataHelpers::FT_MIC_DATA *,ulong *)

- ea: `0x1400b22b0`
- end: `0x1400b292b`
- name: `?SetAssociationCompletionOffsetData@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@KPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@PEAUDOT11_CONNECTION_INFO@@EEPEAUFT_MIC_DATA@FTMicDataHelpers@@PEAK@Z`
- size: `1659`
- prototype: `__int64 __fastcall(CConnectJob *this, struct CBSSEntry *, struct _WDI_ASSOCIATION_RESULT_CONTAINER *, unsigned __int8 *, struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *Src, struct DOT11_CONNECTION_INFO *, char, unsigned __int8, struct FTMicDataHelpers::FT_MIC_DATA *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a5520`

## callees

- `0x140010ce0`
- `0x14001eed0`
- `0x14002bd34`
- `0x1400761f8`
- `0x1400a4850`
- `0x1400a8a5c`
- `0x1400b22b0`
- `0x1400b8120`
- `0x1400dfe00`

## pseudocode

```c
__int64 __fastcall CConnectJob::SetAssociationCompletionOffsetData(
        CConnectJob *this,
        struct CBSSEntry *a2,
        struct _WDI_ASSOCIATION_RESULT_CONTAINER *a3,
        unsigned __int8 *a4,
        struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *Src,
        struct DOT11_CONNECTION_INFO *a6,
        char a7,
        unsigned __int8 a8,
        struct FTMicDataHelpers::FT_MIC_DATA *a9,
        unsigned int *a10)
{
  unsigned int v11; // r12d
  struct _WDI_ASSOCIATION_RESULT_CONTAINER *v12; // r14
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *v13; // rsi
  unsigned int v14; // edi
  unsigned __int8 v15; // bp
  unsigned int *v16; // rcx
  int *v17; // r15
  char v18; // r13
  int v19; // r9d
  int v20; // r9d
  int v21; // ecx
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // ecx
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rcx
  struct DOT11_CONNECTION_INFO *v29; // r13
  struct FTMicDataHelpers::FT_MIC_DATA *v30; // r15
  __int64 v31; // rcx
  int v33; // [rsp+30h] [rbp-88h]
  int v34; // [rsp+40h] [rbp-78h]
  struct CBSSEntry *v35; // [rsp+C8h] [rbp+10h]
  unsigned __int16 v36; // [rsp+D8h] [rbp+20h] BYREF

  v35 = a2;
  v11 = (unsigned int)a4;
  v12 = a3;
  if ( (unsigned int)a4 < 0x74 )
  {
    *a10 = 116;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        104,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        (char)a4,
        116);
    }
    return 1;
  }
  v13 = Src;
  v14 = 116;
  v15 = a8;
  v16 = (unsigned int *)((char *)Src + 24);
  v17 = (int *)((char *)Src + 40);
  if ( !a8 )
  {
    a2 = (struct CBSSEntry *)*((unsigned int *)Src + 26);
    a4 = (unsigned __int8 *)*((unsigned int *)Src + 8);
    LODWORD(a3) = *v16;
    v14 = *v16
        + (_DWORD)a4
        + *v17
        + *((_DWORD *)Src + 17)
        + *((_DWORD *)Src + 21)
        + *((_DWORD *)Src + 28)
        + (_DWORD)a2
        + 116;
    if ( v11 < v14 )
    {
      *a10 = v14;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDddddddddd(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)a2, (_DWORD)a3, (_DWORD)a4);
      return 1;
    }
  }
  v18 = a7;
  if ( (*(_DWORD *)v12 & 1) != 0 )
  {
    if ( a8 )
    {
      *((_DWORD *)Src + 5) = v14;
      a2 = (struct CBSSEntry *)*((unsigned int *)v12 + 16);
      *v16 = (unsigned int)a2;
      if ( (unsigned int)a2 + v14 < v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v19 = 106;
        LOBYTE(v34) = (_BYTE)a2;
LABEL_83:
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          (_DWORD)a3,
          v19,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          -1,
          v34);
        return 1;
      }
      v14 += (unsigned int)a2;
    }
    else
    {
      a2 = (struct CBSSEntry *)*((unsigned int *)Src + 5);
      if ( v11 < *v16 + (unsigned int)a2 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v20 = 107;
        goto LABEL_17;
      }
      CopyMgmtFrameFromNetwork(0, a7, (__int16 *)((char *)a2 + (_QWORD)Src), *((const void **)v12 + 9), *v16);
    }
  }
  if ( (*(_DWORD *)v12 & 2) != 0 )
  {
    if ( v15 )
    {
      *((_DWORD *)v13 + 7) = v14;
      v21 = *((_DWORD *)v12 + 22);
      *((_DWORD *)v13 + 8) = v21;
      if ( v21 + v14 < v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v19 = 108;
        goto LABEL_80;
      }
      v14 += v21;
    }
    else
    {
      v22 = *((unsigned int *)v13 + 7);
      LODWORD(a2) = *((_DWORD *)v13 + 8);
      if ( v11 < (int)a2 + (int)v22 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v20 = 109;
        goto LABEL_17;
      }
      CopyMgmtFrameFromNetwork(1, v18, (__int16 *)((char *)v13 + v22), *((const void **)v12 + 12), *((_DWORD *)v13 + 8));
    }
  }
  if ( (*(_DWORD *)v12 & 8) != 0 )
  {
    if ( v15 )
    {
      *((_DWORD *)v13 + 9) = v14;
      v21 = *((_DWORD *)v12 + 34);
      *((_DWORD *)v13 + 10) = v21;
      v23 = v21 + v14;
      if ( v21 + v14 < v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v19 = 110;
        goto LABEL_80;
      }
LABEL_32:
      v14 = v23;
      goto LABEL_49;
    }
    v24 = *((unsigned int *)v13 + 9);
    LODWORD(a2) = *((_DWORD *)v13 + 10);
    if ( v11 < (int)a2 + (int)v24 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 1;
      v20 = 111;
      goto LABEL_17;
    }
    CopyMgmtFrameFromNetwork(5, v18, (__int16 *)((char *)v13 + v24), *((const void **)v12 + 18), *((_DWORD *)v13 + 10));
  }
  else
  {
    Src = 0;
    v36 = 0;
    LOBYTE(a2) = 1;
    CBSSEntry::GetBeaconOrProbeFrame(v35, a2, &Src, &v36);
    LODWORD(a2) = (_DWORD)Src;
    if ( !Src )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 1;
      v20 = (_DWORD)Src + 112;
      goto LABEL_17;
    }
    if ( v15 )
    {
      v21 = v36;
      *((_DWORD *)v13 + 9) = v14;
      *v17 = v21;
      v23 = v21 + v14;
      if ( v21 + v14 < v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v19 = 113;
        goto LABEL_80;
      }
      goto LABEL_32;
    }
    v25 = *v17;
    if ( v36 > (unsigned int)*v17 || (v26 = *((unsigned int *)v13 + 9), v11 < (unsigned int)v26 + v25) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 1;
      v20 = 114;
      v33 = *((_DWORD *)this + 4);
LABEL_94:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        v20,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        v33);
      return 1;
    }
    memmove((char *)v13 + v26, Src, v25);
  }
LABEL_49:
  if ( (*(_DWORD *)v12 & 0x10) != 0 )
  {
    if ( v15 )
    {
      *((_DWORD *)v13 + 20) = v14;
      v21 = *((_DWORD *)v12 + 40);
      *((_DWORD *)v13 + 21) = v21;
      if ( v21 + v14 < v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v19 = 115;
        goto LABEL_80;
      }
      v14 += v21;
    }
    else
    {
      v27 = *((unsigned int *)v13 + 20);
      LODWORD(a2) = *((_DWORD *)v13 + 21);
      if ( v11 < (int)a2 + (int)v27 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v20 = 116;
        goto LABEL_17;
      }
      memmove((char *)v13 + v27, *((const void **)v12 + 21), *((unsigned int *)v13 + 21));
    }
  }
  if ( *((_DWORD *)v12 + 46) )
  {
    if ( v15 )
    {
      *((_DWORD *)v13 + 16) = v14;
      v21 = 4 * *((_DWORD *)v12 + 46);
      *((_DWORD *)v13 + 17) = v21;
      if ( v21 + v14 >= v14 )
      {
        v14 += v21;
        goto LABEL_69;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 1;
      v19 = 117;
LABEL_80:
      LOBYTE(v34) = v21;
      goto LABEL_83;
    }
    v28 = *((unsigned int *)v13 + 16);
    LODWORD(a2) = *((_DWORD *)v13 + 17);
    if ( v11 < (int)a2 + (int)v28 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 1;
      v20 = 118;
      goto LABEL_17;
    }
    memmove((char *)v13 + v28, *((const void **)v12 + 24), *((unsigned int *)v13 + 17));
  }
LABEL_69:
  v29 = a6;
  if ( a6 && v15 )
  {
    *((_DWORD *)v13 + 25) = v14;
    *((_DWORD *)v13 + 26) = *(_DWORD *)v29;
    v21 = *(_DWORD *)v29;
    if ( *(_DWORD *)v29 + v14 >= v14 )
    {
      v14 += *(_DWORD *)v29;
      goto LABEL_73;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 1;
    v19 = 119;
    goto LABEL_80;
  }
LABEL_73:
  v30 = a9;
  if ( !a9 )
  {
    if ( v15 )
      goto LABEL_90;
    return 0;
  }
  if ( !v15 )
  {
    a2 = (struct CBSSEntry *)*((unsigned int *)v13 + 28);
    if ( (_DWORD)a2 )
    {
      v31 = *((unsigned int *)v13 + 27);
      if ( v11 >= (int)v31 + (int)a2 )
        return FTMicDataHelpers::CopyFTRoamCompletionMicData(a9, a2, (__int64)v13 + v31, a4);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 1;
      v20 = 121;
LABEL_17:
      v33 = *((_DWORD *)this + 4);
      goto LABEL_94;
    }
    return 0;
  }
  if ( FTMicDataHelpers::GetFTRoamCompletionMicData(v12, v29, a9, (struct FTMicDataHelpers::FT_MIC_DATA *)a4) )
  {
LABEL_90:
    *a10 = v14;
    return 0;
  }
  *((_DWORD *)v13 + 28) = *(_DWORD *)v30;
  *((_DWORD *)v13 + 27) = v14;
  if ( v14 + *(_DWORD *)v30 >= v14 )
  {
    v14 += *(_DWORD *)v30;
    goto LABEL_90;
  }
  *(_QWORD *)((char *)v13 + 108) = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v19 = 120;
    v34 = *(_DWORD *)v29;
    goto LABEL_83;
  }
  return 1;
}

```

## disassembly

```asm
0x1400b22b0  mov     [rsp+arg_0], rbx
0x1400b22b5  mov     [rsp+arg_8], rdx
0x1400b22ba  push    rbp
0x1400b22bb  push    rsi
0x1400b22bc  push    rdi
0x1400b22bd  push    r12
0x1400b22bf  push    r13
0x1400b22c1  push    r14
0x1400b22c3  push    r15
0x1400b22c5  sub     rsp, 80h
0x1400b22cc  mov     rbx, rcx
0x1400b22cf  mov     r12d, r9d
0x1400b22d2  mov     ecx, 74h ; 't'
0x1400b22d7  mov     r14, r8
0x1400b22da  cmp     r9d, ecx
0x1400b22dd  jnb     short loc_1400B2339
0x1400b22df  mov     rax, [rsp+0B8h+arg_48]
0x1400b22e7  mov     [rax], ecx
0x1400b22e9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b22f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b22f7  jz      loc_1400B290A
0x1400b22fd  mov     eax, [rbx+10h]
0x1400b2300  lea     r9d, [rcx-0Ch]
0x1400b2304  mov     [rsp+0B8h+var_78], ecx
0x1400b2308  mov     dl, 2
0x1400b230a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2311  mov     [rsp+0B8h+var_80], r12d
0x1400b2316  mov     [rsp+0B8h+var_88], eax
0x1400b231a  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b2321  mov     [rsp+0B8h+var_90], rbx
0x1400b2326  mov     rcx, [rcx+40h]
0x1400b232a  mov     [rsp+0B8h+var_98], rax
0x1400b232f  call    WPP_RECORDER_SF_qDdd
0x1400b2334  jmp     loc_1400B290A
0x1400b2339  mov     rsi, [rsp+0B8h+Src]
0x1400b2341  mov     edi, ecx
0x1400b2343  mov     bpl, [rsp+0B8h+arg_38]
0x1400b234b  lea     rcx, [rsi+18h]
0x1400b234f  lea     r15, [rsi+28h]
0x1400b2353  test    bpl, bpl
0x1400b2356  jnz     loc_1400B23F2
0x1400b235c  mov     eax, [rsi+70h]
0x1400b235f  mov     r13d, [rsi+54h]
0x1400b2363  add     eax, r13d
0x1400b2366  mov     r11d, [rsi+44h]
0x1400b236a  add     eax, r11d
0x1400b236d  mov     edx, [rsi+68h]
0x1400b2370  mov     r10d, [r15]
0x1400b2373  add     eax, r10d
0x1400b2376  mov     r9d, [rsi+20h]
0x1400b237a  add     eax, r9d
0x1400b237d  mov     r8d, [rcx]
0x1400b2380  add     eax, r8d
0x1400b2383  lea     edi, [rdx+74h]
0x1400b2386  add     edi, eax
0x1400b2388  cmp     r12d, edi
0x1400b238b  jnb     short loc_1400B23F2
0x1400b238d  mov     rax, [rsp+0B8h+arg_48]
0x1400b2395  mov     [rax], edi
0x1400b2397  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b239e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b23a5  jz      loc_1400B290A
0x1400b23ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b23b2  mov     eax, [rbx+10h]
0x1400b23b5  mov     [rsp+0B8h+var_40], edx
0x1400b23b9  mov     [rsp+0B8h+var_48], r11d
0x1400b23be  mov     rcx, [rcx+40h]
0x1400b23c2  mov     [rsp+0B8h+var_50], r13d
0x1400b23c7  mov     [rsp+0B8h+var_58], r10d
0x1400b23cc  mov     [rsp+0B8h+var_60], r9d
0x1400b23d1  mov     [rsp+0B8h+var_68], r8d
0x1400b23d6  mov     [rsp+0B8h+var_78], edi
0x1400b23da  mov     [rsp+0B8h+var_80], r12d
0x1400b23df  mov     [rsp+0B8h+var_88], eax
0x1400b23e3  mov     [rsp+0B8h+var_90], rbx
0x1400b23e8  call    WPP_RECORDER_SF_qDddddddddd
0x1400b23ed  jmp     loc_1400B290A
0x1400b23f2  mov     eax, [r14]
0x1400b23f5  mov     r13b, [rsp+0B8h+arg_30]
0x1400b23fd  test    al, 1
0x1400b23ff  jz      loc_1400B248D
0x1400b2405  test    bpl, bpl
0x1400b2408  jz      short loc_1400B2441
0x1400b240a  mov     [rsi+14h], edi
0x1400b240d  mov     edx, [r14+40h]
0x1400b2411  mov     [rcx], edx
0x1400b2413  lea     eax, [rdx+rdi]
0x1400b2416  cmp     eax, edi
0x1400b2418  jb      short loc_1400B241E
0x1400b241a  mov     edi, eax
0x1400b241c  jmp     short loc_1400B248D
0x1400b241e  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b2425  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b242c  jz      loc_1400B290A
0x1400b2432  mov     r9d, 6Ah ; 'j'
0x1400b2438  mov     [rsp+0B8h+var_78], edx
0x1400b243c  jmp     loc_1400B2845
0x1400b2441  mov     edx, [rsi+14h]
0x1400b2444  mov     r9d, [rcx]
0x1400b2447  lea     eax, [r9+rdx]
0x1400b244b  cmp     r12d, eax
0x1400b244e  jnb     short loc_1400B2476
0x1400b2450  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b2457  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b245e  jz      loc_1400B290A
0x1400b2464  mov     r9d, 6Bh ; 'k'
0x1400b246a  mov     eax, [rbx+10h]
0x1400b246d  mov     [rsp+0B8h+var_88], eax
0x1400b2471  jmp     loc_1400B28E7
0x1400b2476  lea     r8, [rsi+rdx]
0x1400b247a  mov     dword ptr [rsp+0B8h+var_98], r9d
0x1400b247f  mov     r9, [r14+48h]
0x1400b2483  mov     dl, r13b
0x1400b2486  xor     ecx, ecx
0x1400b2488  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400b248d  mov     eax, [r14]
0x1400b2490  test    al, 2
0x1400b2492  jz      short loc_1400B2513
0x1400b2494  test    bpl, bpl
0x1400b2497  jz      short loc_1400B24CD
0x1400b2499  mov     [rsi+1Ch], edi
0x1400b249c  mov     ecx, [r14+58h]
0x1400b24a0  mov     [rsi+20h], ecx
0x1400b24a3  lea     eax, [rcx+rdi]
0x1400b24a6  cmp     eax, edi
0x1400b24a8  jb      short loc_1400B24AE
0x1400b24aa  mov     edi, eax
0x1400b24ac  jmp     short loc_1400B2513
0x1400b24ae  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b24b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b24bc  jz      loc_1400B290A
0x1400b24c2  mov     r9d, 6Ch ; 'l'
0x1400b24c8  jmp     loc_1400B2815
0x1400b24cd  mov     ecx, [rsi+1Ch]
0x1400b24d0  mov     edx, [rsi+20h]
0x1400b24d3  lea     eax, [rdx+rcx]
0x1400b24d6  cmp     r12d, eax
0x1400b24d9  jnb     short loc_1400B24FA
0x1400b24db  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b24e2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b24e9  jz      loc_1400B290A
0x1400b24ef  mov     r9d, 6Dh ; 'm'
0x1400b24f5  jmp     loc_1400B246A
0x1400b24fa  mov     r9, [r14+60h]
0x1400b24fe  lea     r8, [rsi+rcx]
0x1400b2502  mov     dword ptr [rsp+0B8h+var_98], edx
0x1400b2506  mov     ecx, 1
0x1400b250b  mov     dl, r13b
0x1400b250e  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400b2513  mov     eax, [r14]
0x1400b2516  test    al, 8
0x1400b2518  jz      loc_1400B25AB
0x1400b251e  test    bpl, bpl
0x1400b2521  jz      short loc_1400B255D
0x1400b2523  mov     [rsi+24h], edi
0x1400b2526  mov     ecx, [r14+88h]
0x1400b252d  mov     [rsi+28h], ecx
0x1400b2530  lea     eax, [rcx+rdi]
0x1400b2533  cmp     eax, edi
0x1400b2535  jb      short loc_1400B253E
0x1400b2537  mov     edi, eax
0x1400b2539  jmp     loc_1400B2677
0x1400b253e  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b2545  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b254c  jz      loc_1400B290A
0x1400b2552  mov     r9d, 6Eh ; 'n'
0x1400b2558  jmp     loc_1400B2815
0x1400b255d  mov     ecx, [rsi+24h]
0x1400b2560  mov     edx, [rsi+28h]
0x1400b2563  lea     eax, [rdx+rcx]
0x1400b2566  cmp     r12d, eax
0x1400b2569  jnb     short loc_1400B258A
0x1400b256b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b2572  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b2579  jz      loc_1400B290A
0x1400b257f  mov     r9d, 6Fh ; 'o'
0x1400b2585  jmp     loc_1400B246A
0x1400b258a  mov     r9, [r14+90h]
0x1400b2591  lea     r8, [rsi+rcx]
0x1400b2595  mov     dword ptr [rsp+0B8h+var_98], edx
0x1400b2599  mov     ecx, 5
0x1400b259e  mov     dl, r13b
0x1400b25a1  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400b25a6  jmp     loc_1400B2677
0x1400b25ab  mov     rcx, [rsp+0B8h+arg_8]
0x1400b25b3  lea     r9, [rsp+0B8h+arg_18]
0x1400b25bb  xor     eax, eax
0x1400b25bd  mov     [rsp+0B8h+Src], 0
0x1400b25c9  lea     r8, [rsp+0B8h+Src]
0x1400b25d1  mov     [rsp+0B8h+arg_18], ax
0x1400b25d9  mov     dl, 1
0x1400b25db  call    ?GetBeaconOrProbeFrame@CBSSEntry@@QEAA?AW4_WFC_BSS_ENTRY_FRAME_TYPE@@_NPEAPEAUDOT11_BEACON_FRAME@@PEAG@Z; CBSSEntry::GetBeaconOrProbeFrame(bool,DOT11_BEACON_FRAME * *,ushort *)
0x1400b25e0  mov     rdx, [rsp+0B8h+Src]; Src
0x1400b25e8  test    rdx, rdx
0x1400b25eb  jnz     short loc_1400B260A
0x1400b25ed  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b25f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b25fb  jz      loc_1400B290A
0x1400b2601  lea     r9d, [rdx+70h]
0x1400b2605  jmp     loc_1400B246A
0x1400b260a  test    bpl, bpl
0x1400b260d  jz      short loc_1400B2647
0x1400b260f  movzx   ecx, [rsp+0B8h+arg_18]
0x1400b2617  mov     [rsi+24h], edi
0x1400b261a  mov     [r15], ecx
0x1400b261d  lea     eax, [rcx+rdi]
0x1400b2620  cmp     eax, edi
0x1400b2622  jnb     loc_1400B2537
0x1400b2628  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b262f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b2636  jz      loc_1400B290A
0x1400b263c  mov     r9d, 71h ; 'q'
0x1400b2642  jmp     loc_1400B2815
0x1400b2647  mov     ecx, [r15]
0x1400b264a  movzx   eax, [rsp+0B8h+arg_18]
0x1400b2652  cmp     eax, ecx
0x1400b2654  ja      loc_1400B28CA
0x1400b265a  mov     r9d, [rsi+24h]
0x1400b265e  lea     eax, [r9+rcx]
0x1400b2662  cmp     r12d, eax
0x1400b2665  jb      loc_1400B28CA
0x1400b266b  mov     r8d, ecx; Size
0x1400b266e  lea     rcx, [rsi+r9]; void *
0x1400b2672  call    memmove
0x1400b2677  mov     eax, [r14]
0x1400b267a  test    al, 10h
0x1400b267c  jz      short loc_1400B26F9
0x1400b267e  test    bpl, bpl
0x1400b2681  jz      short loc_1400B26BA
0x1400b2683  mov     [rsi+50h], edi
0x1400b2686  mov     ecx, [r14+0A0h]
0x1400b268d  mov     [rsi+54h], ecx
0x1400b2690  lea     eax, [rcx+rdi]
0x1400b2693  cmp     eax, edi
0x1400b2695  jb      short loc_1400B269B
0x1400b2697  mov     edi, eax
0x1400b2699  jmp     short loc_1400B26F9
0x1400b269b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b26a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b26a9  jz      loc_1400B290A
0x1400b26af  mov     r9d, 73h ; 's'
0x1400b26b5  jmp     loc_1400B2815
0x1400b26ba  mov     ecx, [rsi+50h]
0x1400b26bd  mov     edx, [rsi+54h]
0x1400b26c0  lea     eax, [rdx+rcx]
0x1400b26c3  cmp     r12d, eax
0x1400b26c6  jnb     short loc_1400B26E7
0x1400b26c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b26cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b26d6  jz      loc_1400B290A
0x1400b26dc  mov     r9d, 74h ; 't'
0x1400b26e2  jmp     loc_1400B246A
0x1400b26e7  mov     r8, rdx; Size
0x1400b26ea  add     rcx, rsi; void *
0x1400b26ed  mov     rdx, [r14+0A8h]; Src
0x1400b26f4  call    memmove
0x1400b26f9  cmp     dword ptr [r14+0B8h], 0
0x1400b2701  jz      loc_1400B2789
0x1400b2707  test    bpl, bpl
0x1400b270a  jz      short loc_1400B274A
0x1400b270c  mov     [rsi+40h], edi
0x1400b270f  mov     eax, [r14+0B8h]
0x1400b2716  lea     ecx, ds:0[rax*4]
0x1400b271d  lea     eax, [rcx+rdi]
0x1400b2720  mov     [rsi+44h], ecx
0x1400b2723  cmp     eax, edi
0x1400b2725  jb      short loc_1400B272B
0x1400b2727  mov     edi, eax
0x1400b2729  jmp     short loc_1400B2789
0x1400b272b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b2732  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b2739  jz      loc_1400B290A
0x1400b273f  mov     r9d, 75h ; 'u'
0x1400b2745  jmp     loc_1400B2815
0x1400b274a  mov     ecx, [rsi+40h]
0x1400b274d  mov     edx, [rsi+44h]
0x1400b2750  lea     eax, [rdx+rcx]
0x1400b2753  cmp     r12d, eax
0x1400b2756  jnb     short loc_1400B2777
0x1400b2758  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b275f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b2766  jz      loc_1400B290A
0x1400b276c  mov     r9d, 76h ; 'v'
0x1400b2772  jmp     loc_1400B246A
0x1400b2777  mov     r8, rdx; Size
0x1400b277a  add     rcx, rsi; void *
0x1400b277d  mov     rdx, [r14+0C0h]; Src
0x1400b2784  call    memmove
0x1400b2789  mov     r13, [rsp+0B8h+arg_28]
0x1400b2791  test    r13, r13
0x1400b2794  jz      short loc_1400B27B2
0x1400b2796  test    bpl, bpl
0x1400b2799  jz      short loc_1400B27B2
0x1400b279b  mov     [rsi+64h], edi
0x1400b279e  mov     eax, [r13+0]
0x1400b27a2  mov     [rsi+68h], eax
0x1400b27a5  mov     ecx, [r13+0]
0x1400b27a9  lea     eax, [rcx+rdi]
0x1400b27ac  cmp     eax, edi
0x1400b27ae  jb      short loc_1400B27FB
  ... truncated ...
```
