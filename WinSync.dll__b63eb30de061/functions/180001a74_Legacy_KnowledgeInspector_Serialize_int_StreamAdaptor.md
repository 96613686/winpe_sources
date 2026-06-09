# Legacy::KnowledgeInspector::Serialize(int,StreamAdaptor &)

- ea: `0x180001a74`
- end: `0x1800028d2`
- name: `?Serialize@KnowledgeInspector@Legacy@@AEAAJHAEAVStreamAdaptor@@@Z`
- size: `3678`
- prototype: `int(Legacy::KnowledgeInspector *__hidden this, int, struct StreamAdaptor *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180003254`

## callees

- `0x1800016b8`
- `0x180001950`
- `0x180001a74`
- `0x1800028e0`
- `0x180002910`
- `0x180005e8c`
- `0x180007584`
- `0x1800084ec`
- `0x18000a0f0`
- `0x18000f810`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x180093232`
- `0x180094010`

## string_xrefs

- `0x180002886`: `Legacy::KnowledgeInspector::SerializeItemOverride`
- `0x1800028b1`: `Legacy::KnowledgeInspector::SerializeItemOverride`

## pseudocode

```c
__int64 __fastcall Legacy::KnowledgeInspector::Serialize(
        Legacy::KnowledgeInspector *this,
        int a2,
        struct StreamAdaptor *a3)
{
  Legacy::KnowledgeInspector *v5; // r13
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  signed int v10; // esi
  __int64 v11; // rax
  void *v12; // rbx
  int v13; // esi
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 *v16; // r15
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // r9d
  __int64 v20; // rcx
  __int64 i; // r12
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  size_t v27; // rbx
  unsigned __int16 v28; // ax
  __int64 v29; // r9
  unsigned int v30; // r10d
  char *v31; // rdx
  unsigned int v32; // esi
  unsigned int v33; // eax
  size_t v34; // r8
  unsigned int v35; // r9d
  unsigned int v36; // r10d
  char *v37; // rdx
  unsigned int v38; // esi
  size_t v39; // r8
  __int64 v40; // rcx
  size_t v41; // rcx
  void (__fastcall *v42)(size_t); // rax
  unsigned int *v44; // r12
  unsigned int *v45; // r11
  int v46; // ebx
  __int64 v47; // r8
  unsigned int v48; // r9d
  __int64 v49; // rcx
  unsigned int v50; // edx
  __int64 v51; // r9
  __int64 v52; // r10
  __int64 v53; // rdx
  _BYTE *v54; // r9
  __int64 v55; // rdx
  Legacy::KnowledgeInspector *v56; // rax
  __int64 v57; // r13
  __int64 v58; // r8
  __int64 v59; // rcx
  int v60; // r9d
  __int64 v61; // r15
  unsigned int v62; // r12d
  unsigned int v63; // eax
  __int64 v64; // r8
  unsigned int v65; // r9d
  __int64 v66; // rcx
  unsigned int v67; // edx
  __int64 v68; // r8
  unsigned int v69; // r9d
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // r13
  int v73; // esi
  volatile signed __int32 *v74; // rbx
  __int64 v75; // r9
  unsigned int v76; // eax
  int v77; // r10d
  __int64 v78; // rcx
  __int64 v79; // r10
  __int64 v80; // rcx
  SyncId *NextElement; // rax
  SyncId *v82; // rbx
  __int64 v83; // r8
  int v84; // r9d
  __int64 v85; // rcx
  volatile signed __int32 *v86; // rdx
  int v87; // esi
  int v88; // r9d
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // r8
  int v94; // r9d
  __int64 v95; // rcx
  __int64 v96; // rbx
  __int64 v97; // r8
  unsigned int v98; // r10d
  __int64 v99; // rcx
  int v100; // eax
  __int64 v101; // r8
  int v102; // r9d
  __int64 v103; // rcx
  int v104; // edx
  __int64 v105; // rcx
  unsigned int v106; // esi
  unsigned int v107; // eax
  __int64 v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // rdx
  _QWORD v112[2]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v113[4]; // [rsp+40h] [rbp-10h] BYREF
  int v114; // [rsp+44h] [rbp-Ch]
  volatile signed __int32 *v115; // [rsp+48h] [rbp-8h]
  size_t Size; // [rsp+A0h] [rbp+50h] BYREF
  void *v118; // [rsp+A8h] [rbp+58h]

  v5 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      "Legacy::KnowledgeInspector::Serialize");
  }
  v6 = *((unsigned int *)a3 + 4);
  if ( v6 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v6 + 4 < (unsigned int)v6 )
  {
    v10 = -2147024809;
    goto LABEL_54;
  }
  v7 = v6 + *((_QWORD *)a3 + 1);
  *(_BYTE *)v7 = 0;
  *(_WORD *)(v7 + 1) = 0;
  *(_BYTE *)(v7 + 3) = 3;
  *((_DWORD *)a3 + 4) += 4;
  v8 = *((unsigned int *)a3 + 4);
  if ( v8 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v8 + 4 < (unsigned int)v8 )
  {
    v10 = -2147024809;
  }
  else
  {
    v9 = v8 + *((_QWORD *)a3 + 1);
    *(_BYTE *)v9 = 0;
    *(_WORD *)(v9 + 1) = 0;
    *(_BYTE *)(v9 + 3) = 0;
    *((_DWORD *)a3 + 4) += 4;
    v10 = 0;
  }
  if ( !v10 )
  {
    if ( !a2 )
      goto LABEL_19;
    v11 = *(_QWORD *)v5;
    LODWORD(Size) = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, size_t *))(**(_QWORD **)(v11 + 272) + 40LL))(
            *(_QWORD *)(v11 + 272),
            0,
            &Size);
    if ( v10 == -2147024662 )
    {
      v10 = 0;
    }
    else if ( v10 >= 0 )
    {
      v10 = -2147217407;
    }
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    if ( v10 )
    {
      v12 = v118;
    }
    else
    {
      v12 = SeAlloc((unsigned int)Size);
      SeFree(v118);
      v10 = v12 == 0 ? 0x8007000E : 0;
      if ( v12 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, void *, size_t *))(**(_QWORD **)(*(_QWORD *)v5 + 272LL) + 40LL))(
                *(_QWORD *)(*(_QWORD *)v5 + 272LL),
                v12,
                &Size);
        if ( !v10 )
        {
          v13 = Size;
          v14 = *((_DWORD *)a3 + 4);
          if ( v14 + (unsigned int)Size > *((_DWORD *)a3 + 5) || v14 + (unsigned int)Size < v14 )
          {
            v10 = -2147024809;
          }
          else
          {
            memcpy_0((void *)(*((_QWORD *)a3 + 1) + v14), v12, (unsigned int)Size);
            *((_DWORD *)a3 + 4) += v13;
            v10 = 0;
          }
        }
      }
    }
    SeFree(v12);
    if ( !v10 )
    {
LABEL_19:
      v10 = IdFormat::Serialize((IdFormat *)(*(_QWORD *)v5 + 64LL), a3);
      if ( !v10 )
      {
        v10 = IdFormat::Serialize((IdFormat *)(*(_QWORD *)v5 + 72LL), a3);
        if ( !v10 )
        {
          v10 = ClockVector::Serialize(*((ClockVector **)v5 + 1), a3);
          if ( !v10 )
          {
            v15 = *((unsigned int *)a3 + 4);
            if ( v15 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) )
              goto LABEL_130;
            if ( (int)v15 + 4 < (unsigned int)v15 )
              goto LABEL_130;
            v16 = (__int64 *)((char *)a3 + 8);
            v17 = v15 + *((_QWORD *)a3 + 1);
            *(_BYTE *)v17 = v10;
            *(_WORD *)(v17 + 1) = v10;
            *(_BYTE *)(v17 + 3) = 3;
            *((_DWORD *)a3 + 4) += 4;
            v18 = *((unsigned int *)a3 + 4);
            if ( v18 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v18 + 4 < (unsigned int)v18 )
              goto LABEL_130;
            v19 = *((_DWORD *)v5 + 56);
            v20 = *v16;
            *(_BYTE *)(v18 + v20) = HIBYTE(v19);
            *(_BYTE *)(v18 + v20 + 2) = BYTE1(v19);
            *(_BYTE *)(v18 + v20 + 1) = BYTE2(v19);
            *(_BYTE *)(v18 + v20 + 3) = v19;
            *((_DWORD *)a3 + 4) += 4;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v22 = *((unsigned int *)a3 + 4);
              v23 = *((unsigned int *)a3 + 5);
              v24 = v22 + 4;
              if ( (unsigned int)i >= *((_DWORD *)v5 + 56) )
                break;
              if ( v24 > v23 || (int)v22 + 4 < (unsigned int)v22 )
                goto LABEL_130;
              v25 = *v16;
              *(_BYTE *)(v25 + v22) = 0;
              v26 = v25 + v22;
              *(_WORD *)(v26 + 1) = 0;
              *(_BYTE *)(v26 + 3) = 2;
              *((_DWORD *)a3 + 4) += 4;
              v27 = *(_QWORD *)(*((_QWORD *)v5 + 30) + 8 * i);
              Size = v27;
              if ( v27 )
                (*(void (__fastcall **)(size_t))(*(_QWORD *)v27 + 8LL))(v27);
              v28 = SyncId::GetSize((SyncId *)(v27 + 48));
              v29 = *((unsigned int *)a3 + 4);
              v30 = v28;
              if ( (*(_DWORD *)(v27 + 52) & 0x10000) != 0 )
              {
                if ( v29 + 2 <= (unsigned __int64)*((unsigned int *)a3 + 5) && (int)v29 + 2 >= (unsigned int)v29 )
                {
                  v108 = *v16;
                  *(_BYTE *)(v108 + v29) = HIBYTE(v28);
                  *(_BYTE *)(v108 + v29 + 1) = v28;
                  *((_DWORD *)a3 + 4) += 2;
                  v109 = *(_QWORD *)(v27 + 56);
                  v29 = *((unsigned int *)a3 + 4);
                  if ( (*(_DWORD *)(v27 + 52) & 0x20000) == 0 )
                    v109 += 4;
                  v32 = v28 - 2;
                  if ( v32 + (unsigned int)v29 <= *((_DWORD *)a3 + 5)
                    && v28 - 2 + (unsigned int)v29 >= (unsigned int)v29 )
                  {
                    v34 = v32;
                    v31 = (char *)(v109 + 2);
                    goto LABEL_38;
                  }
                }
              }
              else
              {
                v31 = *(char **)(v27 + 56);
                v32 = v28;
                if ( (*(_DWORD *)(v27 + 52) & 0x20000) == 0 )
                  v31 += 4;
                v33 = v29 + v28;
                if ( (unsigned int)v29 + v30 <= *((_DWORD *)a3 + 5) && v33 >= (unsigned int)v29 )
                {
                  v34 = v30;
LABEL_38:
                  memcpy_0((void *)(*v16 + v29), v31, v34);
                  *((_DWORD *)a3 + 4) += v32;
                  v10 = 0;
                  goto LABEL_39;
                }
              }
              v10 = -2147024809;
LABEL_39:
              if ( v10 )
              {
                SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&Size);
                goto LABEL_54;
              }
              v36 = SyncId::GetSize((SyncId *)(v27 + 64));
              if ( (*(_DWORD *)(v27 + 68) & 0x10000) != 0 )
              {
                if ( (unsigned __int64)v35 + 2 <= *((unsigned int *)a3 + 5) && v35 + 2 >= v35 )
                {
                  v110 = *v16;
                  *(_BYTE *)(v110 + v35) = BYTE1(v36);
                  *(_BYTE *)(v110 + v35 + 1) = v36;
                  *((_DWORD *)a3 + 4) += 2;
                  v111 = *(_QWORD *)(v27 + 72);
                  v40 = *((unsigned int *)a3 + 4);
                  if ( (*(_DWORD *)(v27 + 68) & 0x20000) == 0 )
                    v111 += 4;
                  v38 = v36 - 2;
                  if ( v36 - 2 + (unsigned int)v40 <= *((_DWORD *)a3 + 5)
                    && v36 - 2 + (unsigned int)v40 >= (unsigned int)v40 )
                  {
                    v39 = v38;
                    v37 = (char *)(v111 + 2);
                    goto LABEL_46;
                  }
                }
              }
              else
              {
                v37 = *(char **)(v27 + 72);
                v38 = v36;
                if ( (*(_DWORD *)(v27 + 68) & 0x20000) == 0 )
                  v37 += 4;
                if ( v35 + v36 <= *((_DWORD *)a3 + 5) && v35 + v36 >= v35 )
                {
                  v39 = v36;
                  v40 = v35;
LABEL_46:
                  memcpy_0((void *)(*v16 + v40), v37, v39);
                  *((_DWORD *)a3 + 4) += v38;
                  v10 = 0;
                  goto LABEL_47;
                }
              }
              v10 = -2147024809;
LABEL_47:
              if ( v10 )
              {
                if ( v27 )
                {
                  v41 = v27;
                  v42 = *(void (__fastcall **)(size_t))(*(_QWORD *)v27 + 16LL);
LABEL_52:
                  v42(v41);
                }
                goto LABEL_54;
              }
              v10 = ClockVector::Serialize(*(ClockVector **)(v27 + 80), a3);
              v41 = v27;
              v42 = *(void (__fastcall **)(size_t))(*(_QWORD *)v27 + 16LL);
              if ( v10 )
                goto LABEL_52;
              v42(v27);
            }
            if ( v24 > v23 )
              goto LABEL_130;
            if ( (int)v22 + 4 < (unsigned int)v22 )
              goto LABEL_130;
            v90 = *v16 + v22;
            *(_BYTE *)v90 = 0;
            *(_WORD *)(v90 + 1) = 0;
            *(_BYTE *)(v90 + 3) = 6;
            *((_DWORD *)a3 + 4) += 4;
            v91 = *((unsigned int *)a3 + 4);
            if ( v91 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5)
              || (int)v91 + 4 < (unsigned int)v91
              || (v92 = *v16 + v91,
                  *(_BYTE *)v92 = 0,
                  *(_WORD *)(v92 + 1) = 0,
                  *(_BYTE *)(v92 + 3) = 4,
                  *((_DWORD *)a3 + 4) += 4,
                  v93 = *((unsigned int *)a3 + 4),
                  v93 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5))
              || (int)v93 + 4 < (unsigned int)v93 )
            {
LABEL_130:
              v10 = -2147024809;
              goto LABEL_54;
            }
            v94 = *((_DWORD *)v5 + 68);
            v95 = *v16;
            v57 = 0;
            *(_BYTE *)(v95 + v93) = HIBYTE(v94);
            *(_BYTE *)(v93 + v95 + 2) = BYTE1(v94);
            v56 = this;
            *(_BYTE *)(v93 + v95 + 1) = BYTE2(v94);
            *(_BYTE *)(v93 + v95 + 3) = v94;
            *((_DWORD *)a3 + 4) += 4;
            if ( *((_DWORD *)this + 68) )
            {
              while ( 1 )
              {
                v96 = *(_QWORD *)(*((_QWORD *)v56 + 36) + 8 * v57);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    32,
                    WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
                    "ClockVector::Serialize");
                }
                v97 = *((unsigned int *)a3 + 4);
                if ( v97 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v97 + 4 < (unsigned int)v97 )
                  goto LABEL_88;
                v98 = *(_DWORD *)(v96 + 36);
                v99 = *v16;
                v100 = (v98 >> 1) & 1;
                LODWORD(Size) = v98;
                *(_BYTE *)(v97 + v99 + 3) = 8 * ((v98 & 2) != 0) + 1;
                *(_BYTE *)(v97 + v99 + 1) = (unsigned int)(8 * v100 + 1) >> 16;
                *(_BYTE *)(v99 + v97) = (unsigned int)(8 * v100 + 1) >> 24;
                *(_BYTE *)(v97 + v99 + 2) = (unsigned __int16)(8 * v100 + 1) >> 8;
                *((_DWORD *)a3 + 4) += 4;
                v101 = *((unsigned int *)a3 + 4);
                if ( v101 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v101 + 4 < (unsigned int)v101 )
                {
                  v10 = -2147024809;
                  LODWORD(v55) = *((_DWORD *)a3 + 4);
                }
                else
                {
                  v102 = *(_DWORD *)(v96 + 28);
                  v103 = *v16;
                  *(_BYTE *)(v103 + v101) = HIBYTE(v102);
                  *(_BYTE *)(v101 + v103 + 2) = BYTE1(v102);
                  *(_BYTE *)(v101 + v103 + 1) = BYTE2(v102);
                  *(_BYTE *)(v101 + v103 + 3) = v102;
                  *((_DWORD *)a3 + 4) += 4;
                  LODWORD(v55) = *((_DWORD *)a3 + 4);
                  v10 = 0;
                }
                if ( !v10 )
                {
                  if ( (v98 & 2) == 0 )
                    goto LABEL_62;
                  if ( (unsigned __int64)(unsigned int)v55 + 4 > *((unsigned int *)a3 + 5)
                    || (int)v55 + 4 < (unsigned int)v55 )
                  {
                    v10 = -2147024809;
                  }
                  else
                  {
                    v88 = *(_DWORD *)(v96 + 32);
                    v89 = *v16;
                    *(_BYTE *)(v89 + (unsigned int)v55) = HIBYTE(v88);
                    *(_BYTE *)((unsigned int)v55 + v89 + 2) = BYTE1(v88);
                    *(_BYTE *)((unsigned int)v55 + v89 + 1) = BYTE2(v88);
                    *(_BYTE *)((unsigned int)v55 + v89 + 3) = v88;
                    *((_DWORD *)a3 + 4) += 4;
                    LODWORD(v55) = *((_DWORD *)a3 + 4);
                    v10 = 0;
                  }
                  if ( !v10 )
                  {
                    if ( (unsigned __int64)(unsigned int)v55 + 1 > *((unsigned int *)a3 + 5)
                      || (int)v55 + 1 < (unsigned int)v55 )
                    {
                      v10 = -2147024809;
                    }
                    else
                    {
                      *(_BYTE *)((unsigned int)v55 + *v16) = (*(_DWORD *)(v96 + 36) & 4) != 0;
                      LODWORD(v55) = ++*((_DWORD *)a3 + 4);
                      v10 = 0;
                    }
                    if ( !v10 )
                    {
LABEL_62:
                      v44 = *(unsigned int **)(v96 + 40);
                      v45 = *(unsigned int **)(v96 + 48);
                      v46 = *(_DWORD *)(v96 + 28);
                      if ( v46 )
                        break;
                    }
                  }
                }
LABEL_69:
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_sD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    33,
                    (unsigned int)WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
                    (unsigned int)"ClockVector::Serialize",
                    v10);
                }
                if ( v10 )
                  goto LABEL_91;
                v56 = this;
                v57 = (unsigned int)(v57 + 1);
                if ( (unsigned int)v57 >= *((_DWORD *)this + 68) )
                  goto LABEL_72;
              }
              while ( 1 )
              {
                v47 = (unsigned int)v55;
                if ( (unsigned __int64)(unsigned int)v55 + 4 > *((unsigned int *)a3 + 5) )
                  break;
                if ( (int)v55 + 4 < (unsigned int)v55 )
                  break;
                v48 = *v44;
                v49 = *v16;
                v50 = HIWORD(*v44);
                *(_BYTE *)(v49 + v47) = HIBYTE(*v44);
                *(_BYTE *)(v47 + v49 + 1) = v50;
                *(_BYTE *)(v47 + v49 + 3) = v48;
                *(_BYTE *)(v47 + v49 + 2) = BYTE1(v48);
                *((_DWORD *)a3 + 4) += 4;
                v51 = *((unsigned int *)a3 + 4);
                if ( v51 + 8 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v51 + 8 < (unsigned int)v51 )
                  break;
                v52 = *((_QWORD *)v44 + 1);
                v53 = *v16;
                *(_BYTE *)(v53 + v51) = HIBYTE(v52);
                v54 = (_BYTE *)(v53 + v51);
                v54[2] = BYTE5(v52);
                v54[1] = BYTE6(v52);
                v54[3] = BYTE4(v52);
                v54[4] = BYTE3(v52);
                v54[6] = BYTE1(v52);
                v54[5] = BYTE2(v52);
                v54[7] = v52;
                *((_DWORD *)a3 + 4) += 8;
                v55 = *((unsigned int *)a3 + 4);
                if ( (Size & 2) != 0 )
                {
                  v64 = *((unsigned int *)a3 + 4);
                  if ( v55 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) )
                    break;
                  if ( (int)v55 + 4 < (unsigned int)v55 )
                    break;
                  v65 = *v45;
                  v66 = *v16;
                  v67 = HIWORD(*v45);
                  *(_BYTE *)(v66 + v64) = HIBYTE(*v45);
                  *(_BYTE *)(v64 + v66 + 1) = v67;
                  *(_BYTE *)(v64 + v66 + 3) = v65;
                  *(_BYTE *)(v64 + v66 + 2) = BYTE1(v65);
                  *((_DWORD *)a3 + 4) += 4;
                  v68 = *((unsigned int *)a3 + 4);
                  if ( v68 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) )
                    break;
                  if ( (int)v68 + 4 < (unsigned int)v68 )
                    break;
                  v69 = v45[1];
                  v70 = *v16;
                  *(_BYTE *)(v70 + v68) = HIBYTE(v69);
                  *(_BYTE *)(v68 + v70 + 1) = BYTE2(v69);
                  *(_BYTE *)(v68 + v70 + 3) = v69;
                  *(_BYTE *)(v68 + v70 + 2) = BYTE1(v69);
                  *((_DWORD *)a3 + 4) += 4;
                  v55 = *((unsigned int *)a3 + 4);
                  if ( v55 + 1 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v55 + 1 < (unsigned int)v55 )
                    break;
                  *(_BYTE *)(v55 + *v16) = *((_BYTE *)v45 + 8);
                  LODWORD(v55) = ++*((_DWORD *)a3 + 4);
                  v45 += 3;
                }
                v10 = 0;
                if ( !--v46 )
                  goto LABEL_69;
                v44 += 4;
              }
LABEL_88:
              v10 = -2147024809;
              goto LABEL_69;
            }
LABEL_72:
            v58 = *((unsigned int *)a3 + 4);
            if ( v58 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v58 + 4 < (unsigned int)v58 )
            {
              v10 = -2147024809;
LABEL_91:
              v5 = this;
            }
            else
            {
              v59 = *v16;
              v5 = this;
              v60 = *((_DWORD *)this + 88);
              *(_BYTE *)(v58 + v59 + 1) = BYTE2(v60);
              *(_BYTE *)(v59 + v58) = HIBYTE(v60);
              *(_BYTE *)(v58 + v59 + 2) = BYTE1(v60);
              *(_BYTE *)(v58 + v59 + 3) = v60;
              *((_DWORD *)a3 + 4) += 4;
              v10 = 0;
            }
          }
        }
      }
      if ( v10 )
        goto LABEL_54;
      v61 = 0;
      v62 = 0;
      while ( 2 )
      {
        v63 = *((_DWORD *)v5 + 88);
        if ( !v63 || v62 >= v63 )
          break;
        while ( 1 )
        {
          if ( (unsigned int)v61 >= *((_DWORD *)v5 + 84) )
            goto LABEL_54;
          v71 = 5 * v61;
          v61 = (unsigned int)(v61 + 1);
          v72 = *((_QWORD *)v5 + 43) + 8 * v71;
          if ( (*(_BYTE *)(v72 + 32) & 1) != 0 )
            break;
          v5 = this;
        }
        if ( !v72 )
          break;
        ++v62;
        v73 = *(_DWORD *)(v72 + 4);
        v74 = *(volatile signed __int32 **)(v72 + 8);
        LODWORD(v118) = *(_DWORD *)(v72 + 16);
        v114 = v73;
        v115 = v74;
        if ( v74 )
          _InterlockedIncrement(v74);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
            "Legacy::KnowledgeInspector::SerializeItemOverride");
        }
        if ( (v73 & 0x10000) != 0 )
        {
          v86 = v74;
          v87 = v73 & 0x20000;
          if ( !v87 )
            v86 = v74 + 1;
          v75 = *((unsigned int *)a3 + 4);
          if ( v75 + 2 <= (unsigned __int64)*((unsigned int *)a3 + 5) && (int)v75 + 2 >= (unsigned int)v75 )
          {
            v104 = *(unsigned __int16 *)v86;
            v105 = *((_QWORD *)a3 + 1);
            *(_BYTE *)(v75 + v105) = BYTE1(v104);
            *(_BYTE *)(v75 + v105 + 1) = v104;
            *((_DWORD *)a3 + 4) += 2;
            v75 = *((unsigned int *)a3 + 4);
            if ( !v87 )
              ++v74;
            v106 = v104 - 2;
            v107 = v104 - 2 + v75;
            if ( v107 <= *((_DWORD *)a3 + 5) && v107 >= (unsigned int)v75 )
            {
              memcpy_0((void *)(*((_QWORD *)a3 + 1) + v75), (char *)v74 + 2, v106);
              *((_DWORD *)a3 + 4) += v106;
              goto LABEL_106;
            }
          }
        }
        else
        {
          if ( (v73 & 0x20000) == 0 )
            ++v74;
          LODWORD(v75) = *((_DWORD *)a3 + 4);
          LODWORD(Size) = (unsigned __int16)v73;
          v76 = v75 + (unsigned __int16)v73;
          if ( v76 <= *((_DWORD *)a3 + 5) && v76 >= (unsigned int)v75 )
          {
            memcpy_0((void *)(*((_QWORD *)a3 + 1) + (unsigned int)v75), (const void *)v74, (unsigned __int16)v73);
            *((_DWORD *)a3 + 4) += Size;
LABEL_106:
            LODWORD(v75) = *((_DWORD *)a3 + 4);
            v10 = 0;
            goto LABEL_107;
          }
        }
        v10 = -2147024809;
LABEL_107:
        if ( !v10 )
        {
          v77 = -1;
          if ( (_DWORD)v118 != -1 )
            v77 = (int)v118;
          if ( (unsigned __int64)(unsigned int)v75 + 4 > *((unsigned int *)a3 + 5) || (int)v75 + 4 < (unsigned int)v75 )
          {
            v10 = -2147024809;
          }
          else
          {
            v78 = *((_QWORD *)a3 + 1);
            *(_BYTE *)(v78 + (unsigned int)v75) = HIBYTE(v77);
            *(_BYTE *)((unsigned int)v75 + v78 + 2) = BYTE1(v77);
            *(_BYTE *)((unsigned int)v75 + v78 + 1) = BYTE2(v77);
            *(_BYTE *)((unsigned int)v75 + v78 + 3) = v77;
            *((_DWORD *)a3 + 4) += 4;
            LODWORD(v75) = *((_DWORD *)a3 + 4);
          }
          if ( !v10 )
          {
            v79 = *(_QWORD *)(v72 + 24);
            if ( v79 )
              LODWORD(v79) = *(_DWORD *)(v79 + 16);
            if ( (unsigned __int64)(unsigned int)v75 + 4 > *((unsigned int *)a3 + 5) || (int)v75 + 4 < (unsigned int)v75 )
            {
LABEL_125:
              v10 = -2147024809;
            }
            else
            {
              v80 = *((_QWORD *)a3 + 1);
              v10 = 0;
              *(_BYTE *)(v80 + (unsigned int)v75) = BYTE3(v79);
              *(_BYTE *)((unsigned int)v75 + v80 + 2) = BYTE1(v79);
              *(_BYTE *)((unsigned int)v75 + v80 + 1) = BYTE2(v79);
              *(_BYTE *)((unsigned int)v75 + v80 + 3) = v79;
              *((_DWORD *)a3 + 4) += 4;
              if ( *(_QWORD *)(v72 + 24) )
              {
                v112[0] = *(_QWORD *)(v72 + 24);
                v112[1] = 0;
                while ( 1 )
                {
                  NextElement = (SyncId *)TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(v112);
                  v82 = NextElement;
                  if ( !NextElement )
                    break;
                  v10 = SyncId::Serialize(NextElement, a3);
                  if ( v10 )
                    break;
                  v83 = *((unsigned int *)a3 + 4);
                  if ( v83 + 4 > (unsigned __int64)*((unsigned int *)a3 + 5) || (int)v83 + 4 < (unsigned int)v83 )
                    goto LABEL_125;
                  v84 = *((_DWORD *)v82 + 4);
                  v85 = *((_QWORD *)a3 + 1);
                  *(_BYTE *)(v85 + v83) = HIBYTE(v84);
                  *(_BYTE *)(v83 + v85 + 2) = BYTE1(v84);
                  *(_BYTE *)(v83 + v85 + 1) = BYTE2(v84);
                  *(_BYTE *)(v83 + v85 + 3) = v84;
                  *((_DWORD *)a3 + 4) += 4;
                }
              }
            }
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
            (unsigned int)"Legacy::KnowledgeInspector::SerializeItemOverride",
            v10);
        }
        SyncId::~SyncId((SyncId *)v113);
        v5 = this;
        continue;
      }
    }
  }
LABEL_54:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      (unsigned int)"Legacy::KnowledgeInspector::Serialize",
      v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180001a74  mov     [rsp-38h+arg_8], rbx
0x180001a79  mov     [rsp-38h+arg_0], rcx
0x180001a7e  push    rbp
0x180001a7f  push    rsi
0x180001a80  push    rdi
0x180001a81  push    r12
0x180001a83  push    r13
0x180001a85  push    r14
0x180001a87  push    r15
0x180001a89  mov     rbp, rsp
0x180001a8c  sub     rsp, 50h
0x180001a90  mov     rdi, r8
0x180001a93  mov     ebx, edx
0x180001a95  mov     r13, rcx
0x180001a98  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a9f  lea     rax, WPP_GLOBAL_Control
0x180001aa6  cmp     rcx, rax
0x180001aa9  jnz     loc_180001EAF
0x180001aaf  mov     edx, [rdi+10h]
0x180001ab2  mov     eax, [rdi+14h]
0x180001ab5  lea     rcx, [rdx+4]
0x180001ab9  cmp     rcx, rax
0x180001abc  ja      loc_180001E4F
0x180001ac2  lea     eax, [rdx+4]
0x180001ac5  cmp     eax, edx
0x180001ac7  jb      loc_180001E4F
0x180001acd  mov     rax, [rdi+8]
0x180001ad1  mov     r14d, 80070057h
0x180001ad7  lea     rcx, [rdx+rax]
0x180001adb  mov     byte ptr [rdx+rax], 0
0x180001adf  mov     word ptr [rcx+1], 0
0x180001ae5  mov     byte ptr [rcx+3], 3
0x180001ae9  add     dword ptr [rdi+10h], 4
0x180001aed  mov     edx, [rdi+10h]
0x180001af0  mov     eax, [rdi+14h]
0x180001af3  lea     rcx, [rdx+4]
0x180001af7  cmp     rcx, rax
0x180001afa  ja      loc_180002418
0x180001b00  lea     eax, [rdx+4]
0x180001b03  cmp     eax, edx
0x180001b05  jb      loc_180002418
0x180001b0b  mov     rax, [rdi+8]
0x180001b0f  lea     rcx, [rdx+rax]
0x180001b13  mov     byte ptr [rdx+rax], 0
0x180001b17  mov     word ptr [rcx+1], 0
0x180001b1d  mov     byte ptr [rcx+3], 0
0x180001b21  add     dword ptr [rdi+10h], 4
0x180001b25  xor     esi, esi
0x180001b27  test    esi, esi
0x180001b29  jnz     loc_180001E54
0x180001b2f  test    ebx, ebx
0x180001b31  jz      loc_180001C06
0x180001b37  mov     rax, [r13+0]
0x180001b3b  lea     r8, [rbp+Size]
0x180001b3f  mov     dword ptr [rbp+Size], esi
0x180001b42  xor     edx, edx
0x180001b44  mov     rcx, [rax+110h]
0x180001b4b  mov     rax, [rcx]
0x180001b4e  mov     rax, [rax+28h]
0x180001b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b57  mov     esi, eax
0x180001b59  cmp     eax, 800700EAh
0x180001b5e  jnz     loc_1800027DC
0x180001b64  xor     esi, esi
0x180001b66  lea     rcx, [rbp+arg_18]
0x180001b6a  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180001b6f  test    esi, esi
0x180001b71  jz      short loc_180001B79
0x180001b73  mov     rbx, [rbp+arg_18]
0x180001b77  jmp     short loc_180001BF6
0x180001b79  mov     ecx, dword ptr [rbp+Size]; unsigned __int64
0x180001b7c  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180001b81  mov     rcx, [rbp+arg_18]; void *
0x180001b85  mov     rbx, rax
0x180001b88  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x180001b8d  mov     rax, rbx
0x180001b90  neg     rax
0x180001b93  sbb     esi, esi
0x180001b95  not     esi
0x180001b97  and     esi, 8007000Eh
0x180001b9d  test    rbx, rbx
0x180001ba0  jz      short loc_180001BF6
0x180001ba2  mov     rax, [r13+0]
0x180001ba6  lea     r8, [rbp+Size]
0x180001baa  mov     rdx, rbx
0x180001bad  mov     rcx, [rax+110h]
0x180001bb4  mov     rax, [rcx]
0x180001bb7  mov     rax, [rax+28h]
0x180001bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bc0  mov     esi, eax
0x180001bc2  test    eax, eax
0x180001bc4  jnz     short loc_180001BF6
0x180001bc6  mov     esi, dword ptr [rbp+Size]
0x180001bc9  mov     eax, [rdi+10h]
0x180001bcc  lea     ecx, [rax+rsi]
0x180001bcf  cmp     ecx, [rdi+14h]
0x180001bd2  ja      loc_1800027EB
0x180001bd8  cmp     ecx, eax
0x180001bda  jb      loc_1800027EB
0x180001be0  mov     ecx, eax
0x180001be2  mov     r8d, esi; Size
0x180001be5  add     rcx, [rdi+8]; void *
0x180001be9  mov     rdx, rbx; Src
0x180001bec  call    memcpy_0
0x180001bf1  add     [rdi+10h], esi
0x180001bf4  xor     esi, esi
0x180001bf6  mov     rcx, rbx; void *
0x180001bf9  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x180001bfe  test    esi, esi
0x180001c00  jnz     loc_180001E54
0x180001c06  mov     rcx, [r13+0]
0x180001c0a  mov     rdx, rdi; struct StreamAdaptor *
0x180001c0d  add     rcx, 40h ; '@'; this
0x180001c11  call    ?Serialize@IdFormat@@QEBAJAEAVStreamAdaptor@@@Z; IdFormat::Serialize(StreamAdaptor &)
0x180001c16  mov     esi, eax
0x180001c18  test    eax, eax
0x180001c1a  jnz     loc_180002074
0x180001c20  mov     rcx, [r13+0]
0x180001c24  mov     rdx, rdi; struct StreamAdaptor *
0x180001c27  add     rcx, 48h ; 'H'; this
0x180001c2b  call    ?Serialize@IdFormat@@QEBAJAEAVStreamAdaptor@@@Z; IdFormat::Serialize(StreamAdaptor &)
0x180001c30  mov     esi, eax
0x180001c32  test    eax, eax
0x180001c34  jnz     loc_180002074
0x180001c3a  mov     rcx, [r13+8]; this
0x180001c3e  mov     rdx, rdi; struct StreamAdaptor *
0x180001c41  call    ?Serialize@ClockVector@@QEBAJAEAVStreamAdaptor@@@Z; ClockVector::Serialize(StreamAdaptor &)
0x180001c46  mov     esi, eax
0x180001c48  test    eax, eax
0x180001c4a  jnz     loc_180002074
0x180001c50  mov     edx, [rdi+10h]
0x180001c53  mov     eax, [rdi+14h]
0x180001c56  lea     rcx, [rdx+4]
0x180001c5a  cmp     rcx, rax
0x180001c5d  ja      loc_180002410
0x180001c63  lea     eax, [rdx+4]
0x180001c66  cmp     eax, edx
0x180001c68  jb      loc_180002410
0x180001c6e  lea     r15, [rdi+8]
0x180001c72  mov     rax, [r15]
0x180001c75  lea     rcx, [rdx+rax]
0x180001c79  mov     [rdx+rax], sil
0x180001c7d  mov     [rcx+1], si
0x180001c81  mov     byte ptr [rcx+3], 3
0x180001c85  add     dword ptr [rdi+10h], 4
0x180001c89  mov     r8d, [rdi+10h]
0x180001c8d  mov     eax, [rdi+14h]
0x180001c90  lea     rcx, [r8+4]
0x180001c94  cmp     rcx, rax
0x180001c97  ja      loc_180002410
0x180001c9d  lea     eax, [r8+4]
0x180001ca1  cmp     eax, r8d
0x180001ca4  jb      loc_180002410
0x180001caa  mov     r9d, [r13+0E0h]
0x180001cb1  mov     edx, r9d
0x180001cb4  mov     rcx, [r15]
0x180001cb7  shr     edx, 10h
0x180001cba  movzx   eax, dx
0x180001cbd  shr     ax, 8
0x180001cc1  mov     [r8+rcx], al
0x180001cc5  movzx   eax, r9w
0x180001cc9  shr     ax, 8
0x180001ccd  mov     [r8+rcx+2], al
0x180001cd2  mov     [r8+rcx+1], dl
0x180001cd7  mov     [r8+rcx+3], r9b
0x180001cdc  add     dword ptr [rdi+10h], 4
0x180001ce0  xor     r12d, r12d
0x180001ce3  mov     edx, [rdi+10h]
0x180001ce6  mov     eax, [rdi+14h]
0x180001ce9  lea     rcx, [rdx+4]
0x180001ced  cmp     r12d, [r13+0E0h]
0x180001cf4  jnb     loc_1800024C2
0x180001cfa  cmp     rcx, rax
0x180001cfd  ja      loc_180002410
0x180001d03  lea     eax, [rdx+4]
0x180001d06  cmp     eax, edx
0x180001d08  jb      loc_180002410
0x180001d0e  mov     rax, [r15]
0x180001d11  mov     byte ptr [rax+rdx], 0
0x180001d15  lea     rcx, [rax+rdx]
0x180001d19  mov     word ptr [rcx+1], 0
0x180001d1f  mov     byte ptr [rcx+3], 2
0x180001d23  add     dword ptr [rdi+10h], 4
0x180001d27  mov     rbx, [r13+0F0h]
0x180001d2e  mov     rbx, [rbx+r12*8]
0x180001d32  mov     [rbp+Size], rbx
0x180001d36  test    rbx, rbx
0x180001d39  jz      short loc_180001D4A
0x180001d3b  mov     rax, [rbx]
0x180001d3e  mov     rcx, rbx
0x180001d41  mov     rax, [rax+8]
0x180001d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d4a  lea     rcx, [rbx+30h]; this
0x180001d4e  call    ?GetSize@SyncId@@QEBAGXZ; SyncId::GetSize(void)
0x180001d53  test    dword ptr [rbx+34h], 10000h
0x180001d5a  mov     r9d, [rdi+10h]
0x180001d5e  movzx   r10d, ax
0x180001d62  jnz     loc_180002704
0x180001d68  mov     rdx, [rbx+38h]
0x180001d6c  mov     esi, r10d
0x180001d6f  test    dword ptr [rbx+34h], 20000h
0x180001d76  lea     rax, [rdx+4]
0x180001d7a  cmovz   rdx, rax; Src
0x180001d7e  lea     eax, [r9+r10]
0x180001d82  cmp     eax, [rdi+14h]
0x180001d85  ja      loc_180002719
0x180001d8b  cmp     eax, r9d
0x180001d8e  jb      loc_180002719
0x180001d94  mov     r8d, r10d; Size
0x180001d97  mov     rcx, r9
0x180001d9a  add     rcx, [r15]; void *
0x180001d9d  call    memcpy_0
0x180001da2  add     [rdi+10h], esi
0x180001da5  mov     r9d, [rdi+10h]
0x180001da9  xor     esi, esi
0x180001dab  test    esi, esi
0x180001dad  jnz     loc_1800027F3
0x180001db3  lea     rcx, [rbx+40h]; this
0x180001db7  call    ?GetSize@SyncId@@QEBAGXZ; SyncId::GetSize(void)
0x180001dbc  test    dword ptr [rbx+44h], 10000h
0x180001dc3  movzx   r10d, ax
0x180001dc7  jnz     loc_180002770
0x180001dcd  mov     rdx, [rbx+48h]
0x180001dd1  mov     esi, r10d
0x180001dd4  test    dword ptr [rbx+44h], 20000h
0x180001ddb  lea     rax, [rdx+4]
0x180001ddf  cmovz   rdx, rax; Src
0x180001de3  lea     eax, [r9+r10]
0x180001de7  cmp     eax, [rdi+14h]
0x180001dea  ja      loc_180002788
0x180001df0  cmp     eax, r9d
0x180001df3  jb      loc_180002788
0x180001df9  mov     r8d, r10d; Size
0x180001dfc  mov     ecx, r9d
0x180001dff  add     rcx, [r15]; void *
0x180001e02  call    memcpy_0
0x180001e07  add     [rdi+10h], esi
0x180001e0a  xor     esi, esi
0x180001e0c  test    esi, esi
0x180001e0e  jnz     short loc_180001E39
0x180001e10  mov     rcx, [rbx+50h]; this
0x180001e14  mov     rdx, rdi; struct StreamAdaptor *
0x180001e17  call    ?Serialize@ClockVector@@QEBAJAEAVStreamAdaptor@@@Z; ClockVector::Serialize(StreamAdaptor &)
0x180001e1c  mov     esi, eax
0x180001e1e  test    eax, eax
0x180001e20  mov     rax, [rbx]
0x180001e23  mov     rcx, rbx
0x180001e26  mov     rax, [rax+10h]
0x180001e2a  jnz     short loc_180001E48
0x180001e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e31  inc     r12d
0x180001e34  jmp     loc_180001CE3
0x180001e39  test    rbx, rbx
0x180001e3c  jz      short loc_180001E54
0x180001e3e  mov     rax, [rbx]
0x180001e41  mov     rcx, rbx
0x180001e44  mov     rax, [rax+10h]
0x180001e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e4d  jmp     short loc_180001E54
0x180001e4f  mov     esi, 80070057h
0x180001e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e5b  lea     rax, WPP_GLOBAL_Control
0x180001e62  cmp     rcx, rax
0x180001e65  jnz     short loc_180001E81
0x180001e67  mov     rbx, [rsp+50h+arg_8]
0x180001e6f  mov     eax, esi
0x180001e71  add     rsp, 50h
0x180001e75  pop     r15
0x180001e77  pop     r14
0x180001e79  pop     r13
0x180001e7b  pop     r12
0x180001e7d  pop     rdi
0x180001e7e  pop     rsi
0x180001e7f  pop     rbp
0x180001e80  retn
0x180001e81  test    byte ptr [rcx+1Ch], 40h
0x180001e85  jz      short loc_180001E67
0x180001e87  cmp     byte ptr [rcx+19h], 5
0x180001e8b  jb      short loc_180001E67
0x180001e8d  mov     rcx, [rcx+10h]
0x180001e91  lea     r9, aLegacyKnowledg_12; "Legacy::KnowledgeInspector::Serialize"
0x180001e98  mov     edx, 1Bh
0x180001e9d  mov     [rsp+50h+var_30], esi
0x180001ea1  lea     r8, WPP_48b71e9a06de38317ed143d1f750f029_Traceguids
0x180001ea8  call    WPP_SF_sD
0x180001ead  jmp     short loc_180001E67
0x180001eaf  test    byte ptr [rcx+1Ch], 40h
0x180001eb3  jz      loc_180001AAF
0x180001eb9  cmp     byte ptr [rcx+19h], 5
0x180001ebd  jb      loc_180001AAF
0x180001ec3  mov     rcx, [rcx+10h]
0x180001ec7  lea     r9, aLegacyKnowledg_12; "Legacy::KnowledgeInspector::Serialize"
0x180001ece  mov     edx, 1Ah
0x180001ed3  lea     r8, WPP_48b71e9a06de38317ed143d1f750f029_Traceguids
0x180001eda  call    WPP_SF_s
0x180001edf  jmp     loc_180001AAF
0x180001ee4  mov     r12, [rbx+28h]
0x180001ee8  mov     r11, [rbx+30h]
0x180001eec  mov     ebx, [rbx+1Ch]
0x180001eef  test    ebx, ebx
  ... truncated ...
```
