# CSyncChangeBatch::Deserialize(ISyncFilterDeserializer *,IdParameters *,IProviderSyncServices *,uchar const *,long,CSyncChangeBatch * *)

- ea: `0x18004e754`
- end: `0x18004f4a0`
- name: `?Deserialize@CSyncChangeBatch@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEAUIProviderSyncServices@@PEBEJPEAPEAV1@@Z`
- size: `3404`
- prototype: `__int64 __fastcall(struct ISyncFilterDeserializer *, unsigned __int64, struct IProviderSyncServices *, const unsigned __int8 *, unsigned int, struct CSyncChangeBatch **)`
- caller_count: `4`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002c9a0`
- `0x18002caf0`
- `0x18002ce70`
- `0x18002cfc0`

## callees

- `0x1800089d0`
- `0x18000a0f0`
- `0x18000f810`
- `0x18001a038`
- `0x18001ae20`
- `0x180031fa4`
- `0x18004b2a0`
- `0x18004b9fc`
- `0x18004beec`
- `0x18004c080`
- `0x18004e754`
- `0x18004f4a8`
- `0x18005228c`
- `0x180053dc0`
- `0x180055ed8`
- `0x180057d80`
- `0x18005a984`
- `0x18005ab24`
- `0x18005f1c8`
- `0x1800795c0`
- `0x180079e70`
- `0x180079f68`
- `0x18007a0c4`
- `0x18009323e`
- `0x180094010`

## string_xrefs

- `0x18004e7a8`: `CSyncChangeBatch::Deserialize`
- `0x18004f467`: `CSyncChangeBatch::Deserialize`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatch::Deserialize(
        struct ISyncFilterDeserializer *a1,
        unsigned __int64 a2,
        struct IProviderSyncServices *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        struct CSyncChangeBatch **a6)
{
  struct IProviderSyncServices *v7; // r14
  struct IdParameters *v8; // r10
  const unsigned __int8 *v10; // r8
  int FlagsPrivate; // ebx
  const unsigned __int8 *v12; // r15
  unsigned __int8 *v13; // rdi
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // r13
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // r13
  const unsigned __int8 *v20; // rsi
  int v21; // r14d
  int v22; // eax
  int v23; // r14d
  __int64 v24; // r14
  int v25; // eax
  int v26; // eax
  const unsigned __int8 *v27; // rcx
  struct IdParameters *v28; // r13
  struct IFilterKeyMap *v29; // rcx
  _QWORD *v30; // rsi
  unsigned int v31; // r14d
  __int64 v32; // r12
  unsigned __int8 *v33; // rax
  ChangeGroup *v34; // rax
  int v35; // ecx
  int v36; // eax
  int v37; // ecx
  __int64 v38; // rcx
  unsigned __int8 *v39; // rsi
  int v40; // eax
  int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // r12d
  __int64 v44; // rsi
  struct ChangeGroup **v45; // rax
  struct ChangeGroup **v46; // r14
  unsigned int v47; // edi
  unsigned __int8 v48; // cl
  int v49; // r14d
  int v50; // r12d
  int v51; // r13d
  int v52; // eax
  int v53; // r13d
  __int64 v54; // r9
  __int64 v55; // r12
  CSyncChange *v56; // rcx
  int v57; // ecx
  unsigned int v58; // ecx
  char *v59; // rcx
  const unsigned __int8 *v60; // rax
  const unsigned __int8 *v61; // rcx
  int v62; // r12d
  bool v63; // zf
  const unsigned __int8 *v64; // rcx
  BOOL v65; // edi
  int v66; // ebx
  int v67; // r13d
  char v68; // dl
  void *v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdi
  __int64 v72; // r15
  int v73; // eax
  unsigned __int64 *v74; // r13
  __int64 v75; // r15
  struct ChangeGroup **v76; // rbx
  unsigned __int64 v77; // rcx
  unsigned int v78; // r15d
  __int64 v79; // rax
  Lock *v80; // rax
  int v81; // r12d
  _QWORD *v82; // r14
  unsigned int v83; // r15d
  __int64 i; // rdi
  struct ChangeGroup *v85; // rcx
  enum __MIDL___MIDL_itf_winsync_0000_0000_0007 v87; // [rsp+68h] [rbp-69h] BYREF
  struct IFilterKeyMap *v88; // [rsp+70h] [rbp-61h]
  int v89; // [rsp+78h] [rbp-59h] BYREF
  struct ChangeGroup **v90; // [rsp+80h] [rbp-51h]
  unsigned __int8 v91; // [rsp+88h] [rbp-49h]
  char v92; // [rsp+89h] [rbp-48h]
  unsigned int v93[2]; // [rsp+90h] [rbp-41h]
  unsigned int v94; // [rsp+98h] [rbp-39h] BYREF
  struct IFilterKeyMap *v95; // [rsp+A0h] [rbp-31h] BYREF
  struct ISyncKnowledge *v96; // [rsp+A8h] [rbp-29h] BYREF
  int v97; // [rsp+B0h] [rbp-21h]
  struct ISyncKnowledge *v98; // [rsp+B8h] [rbp-19h] BYREF
  struct ISyncFilterInfo *v99; // [rsp+C0h] [rbp-11h] BYREF
  int v100; // [rsp+C8h] [rbp-9h]
  struct ISyncKnowledge *v101; // [rsp+D0h] [rbp-1h] BYREF
  unsigned __int8 *v102; // [rsp+D8h] [rbp+7h] BYREF
  struct IdParameters *v103; // [rsp+130h] [rbp+5Fh]
  struct CSyncChange *v105; // [rsp+140h] [rbp+6Fh] BYREF

  v103 = (struct IdParameters *)a2;
  v7 = a3;
  v8 = (struct IdParameters *)a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      "CSyncChangeBatch::Deserialize");
    v8 = v103;
  }
  v10 = 0;
  FlagsPrivate = -2147467261;
  v101 = 0;
  v88 = 0;
  v95 = 0;
  v98 = 0;
  v99 = 0;
  v102 = 0;
  v89 = 0;
  if ( !a4 )
    goto LABEL_198;
  if ( !a6 )
    goto LABEL_198;
  FlagsPrivate = -2147217396;
  v12 = &a4[a5];
  if ( a4 > v12 )
    goto LABEL_198;
  v13 = (unsigned __int8 *)(a4 + 8);
  *a6 = 0;
  if ( a4 + 8 < a4 || v13 > v12 )
    goto LABEL_198;
  FlagsPrivate = 0;
  v14 = (unsigned __int64)a4[4] << 8;
  v15 = a4[2] | ((a4[1] | ((unsigned __int64)*a4 << 8)) << 8);
  v90 = 0;
  v16 = a4[3] | (v15 << 8);
  v93[0] = 0;
  v17 = a4[6] | ((a4[5] | v14) << 8);
  v97 = 0;
  v18 = a4[7] | (v17 << 8);
  v105 = (struct CSyncChange *)(a4 + 8);
  v19 = v18 + (v16 << 32);
  if ( v19 - 4 <= 1 )
  {
    v20 = a4 + 12;
    if ( v13 + 4 < v13 || v20 > v12 )
      goto LABEL_36;
    v21 = (*v13 << 8) | v13[1];
    v105 = (struct CSyncChange *)(v13 + 4);
    v22 = v13[3];
    v23 = (v13[2] | (v21 << 8)) << 8;
    v13 += 4;
    v24 = v22 | (unsigned int)v23;
    if ( (_DWORD)v24 )
    {
      v25 = FilterInfo::Deserialize(a1, v8, v20, v24, &v99);
      v10 = 0;
      v13 = (unsigned __int8 *)&v20[(unsigned int)v24];
      v105 = (struct CSyncChange *)v13;
      FlagsPrivate = v25;
      if ( v25 < 0 )
        goto LABEL_37;
      if ( v99 )
      {
        v96 = 0;
        v26 = ((__int64 (__fastcall *)(struct ISyncFilterInfo *, GUID *, struct ISyncKnowledge **))v99->lpVtbl->QueryInterface)(
                v99,
                &GUID_19b394ba_e3d0_468c_934d_321968b2ab34,
                &v96);
        v10 = 0;
        FlagsPrivate = v26;
        if ( !v26 )
        {
          FlagsPrivate = ((__int64 (__fastcall *)(struct ISyncKnowledge *, int *, _QWORD))v96->lpVtbl->Serialize)(
                           v96,
                           &v89,
                           0);
          ((void (__fastcall *)(struct ISyncKnowledge *))v96->lpVtbl->Release)(v96);
          goto LABEL_20;
        }
        if ( v26 != -2147467262 )
        {
LABEL_20:
          v20 += v24;
          if ( FlagsPrivate < 0 )
            goto LABEL_37;
          goto LABEL_25;
        }
        v89 |= 1u;
        FlagsPrivate = 0;
      }
      v20 += v24;
    }
LABEL_25:
    v7 = a3;
    goto LABEL_26;
  }
  if ( v19 != 3 )
  {
LABEL_36:
    FlagsPrivate = -2147217396;
    goto LABEL_37;
  }
  v20 = a4 + 8;
LABEL_26:
  if ( v20 + 4 < v20 || v20 + 4 > v12 )
    goto LABEL_36;
  if ( FlagsPrivate >= 0 )
  {
    FlagsPrivate = CSyncChangeBatch::DeserializeKnowledge(v7, v103, (const unsigned __int8 **)&v105, v12, &v101);
    if ( FlagsPrivate < 0 )
    {
      v13 = (unsigned __int8 *)v105;
      goto LABEL_37;
    }
    a2 = (unsigned __int64)v105 + 4;
    v27 = (const unsigned __int8 *)(*((unsigned __int8 *)v105 + 3)
                                  | ((*((unsigned __int8 *)v105 + 2)
                                    | ((*((unsigned __int8 *)v105 + 1) | (*(unsigned __int8 *)v105 << 8)) << 8)) << 8));
    v10 = v27;
    v13 = (unsigned __int8 *)v105 + (_QWORD)v27 + 4;
    if ( v13 < (unsigned __int8 *)v105 + 4
      || v13 > v12
      || (_DWORD)v27
      && (FlagsPrivate = (*(__int64 (__fastcall **)(struct IProviderSyncServices *, unsigned __int64, const unsigned __int8 *, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)v7 + 80LL))(
                           v7,
                           a2,
                           v27,
                           0,
                           &v98),
          FlagsPrivate >= 0)
      && (FlagsPrivate = ChangeGroup::ValidateIdFormatOfKnowledge(v103, v98), FlagsPrivate == -2147217408) )
    {
      v105 = (struct CSyncChange *)v13;
      goto LABEL_36;
    }
    v105 = (struct CSyncChange *)v13;
    if ( FlagsPrivate < 0 )
      goto LABEL_37;
    a2 = (unsigned __int64)(v13 + 4);
    if ( v13 + 4 < v13 || a2 > (unsigned __int64)v12 )
      goto LABEL_36;
    if ( v19 < 5 )
    {
      v39 = v13;
    }
    else
    {
      v35 = (*v13 << 8) | v13[1];
      v105 = (struct CSyncChange *)(v13 + 4);
      v36 = v13[3];
      v37 = (v13[2] | (v35 << 8)) << 8;
      v13 += 4;
      v38 = v36 | (unsigned int)v37;
      v39 = (unsigned __int8 *)(v38 + a2);
      if ( v38 + a2 < a2 || v39 > v12 )
        goto LABEL_36;
      if ( (_DWORD)v38 )
      {
        v28 = v103;
        if ( !a1 )
        {
          FlagsPrivate = -2147217396;
          goto LABEL_38;
        }
        FlagsPrivate = FilterKeyMap::Deserialize(a1, v103, (const unsigned __int8 *)a2, v38, &v95);
        if ( FlagsPrivate < 0 )
        {
          v29 = v95;
          v88 = v95;
          goto LABEL_39;
        }
        v88 = v95;
      }
      v13 = v39;
    }
    v40 = *v13;
    v13 = v39 + 4;
    v41 = (v40 << 8) | v39[1];
    v105 = (struct CSyncChange *)(v39 + 4);
    v42 = v39[3] | ((v39[2] | (v41 << 8)) << 8);
    v43 = v42;
    *(_QWORD *)v93 = v42;
    if ( v42 >= 4 )
    {
      a2 = v42;
      v97 = v42;
    }
    else
    {
      a2 = 4;
      v97 = 4;
      if ( !v42 )
        goto LABEL_67;
    }
    if ( v42 > (unsigned __int64)(v12 - v13 + 1) >> 3 )
      goto LABEL_36;
LABEL_67:
    v44 = (unsigned int)a2;
    v45 = (struct ChangeGroup **)SeAlloc(saturated_mul((unsigned int)a2, 8u));
    v90 = v45;
    v46 = v45;
    if ( !v45 )
    {
      FlagsPrivate = -2147024882;
      v94 = 0;
      v87 = SYNC_SERIALIZATION_VERSION_V1;
      goto LABEL_184;
    }
    memset_0(v45, 0, 8 * v44);
  }
LABEL_37:
  v28 = v103;
LABEL_38:
  v29 = v88;
LABEL_39:
  v30 = 0;
  v31 = 0;
  v94 = 0;
  if ( FlagsPrivate >= 0 && v29 )
    FlagsPrivate = ((__int64 (__fastcall *)(struct IFilterKeyMap *, unsigned int *, const unsigned __int8 *))v29->lpVtbl->GetCount)(
                     v29,
                     &v94,
                     v10);
  v32 = 0;
  if ( FlagsPrivate < 0 )
  {
LABEL_93:
    v87 = SYNC_SERIALIZATION_VERSION_V1;
    if ( FlagsPrivate < 0 )
      goto LABEL_180;
    if ( (v89 & 2) != 0 )
    {
      v87 = SYNC_SERIALIZATION_VERSION_V2;
    }
    else if ( (v89 & 0xC) != 0 )
    {
      v87 = SYNC_SERIALIZATION_VERSION_V3;
    }
    v53 = 0;
    if ( v31 )
    {
      do
      {
        v10 = v13 + 4;
        v105 = 0;
        if ( v13 + 4 < v13 )
          goto LABEL_179;
        if ( v10 > v12 )
          goto LABEL_179;
        v54 = v13[3] | ((v13[2] | ((v13[1] | (*v13 << 8)) << 8)) << 8);
        v13 = (unsigned __int8 *)&v10[v54];
        if ( &v10[v54] < v10 || v13 > v12 )
          goto LABEL_179;
        FlagsPrivate = CSyncChange::Deserialize(
                         v103,
                         a3,
                         v10,
                         v54,
                         v90,
                         v93[0],
                         (struct IForgottenKnowledge *)v98,
                         v99,
                         v89 & 1,
                         &v87,
                         &v105);
        if ( FlagsPrivate < 0 )
          goto LABEL_180;
        FlagsPrivate = CollectionManager<CSyncChange>::Add(v30, v105);
        (*(void (__fastcall **)(struct CSyncChange *))(*(_QWORD *)v105 + 16LL))(v105);
        if ( FlagsPrivate < 0 )
          goto LABEL_180;
      }
      while ( ++v53 < v31 );
    }
    v55 = v30[2];
    while ( v55 )
    {
      v56 = *(CSyncChange **)v55;
      a5 = 0;
      FlagsPrivate = CSyncChange::GetFlagsPrivate(v56, &a5);
      if ( FlagsPrivate >= 0 && (a5 & 0xFFFF0000) == 0 )
        FlagsPrivate = CSyncChangeBatch::SetListPosition(v55);
      v55 = *(_QWORD *)(v55 + 8);
      if ( FlagsPrivate < 0 )
        goto LABEL_180;
    }
    a2 = (unsigned __int64)(v13 + 4);
    if ( v13 + 4 >= v13 && a2 <= (unsigned __int64)v12 )
    {
      v57 = v13[1] | (*v13 << 8);
      v105 = (struct CSyncChange *)(v13 + 4);
      v58 = v13[3] | ((v13[2] | (v57 << 8)) << 8);
      if ( v58 )
      {
        v59 = (char *)(a2 + v58);
        if ( (unsigned __int64)v59 < a2 || v59 > (char *)v12 )
          goto LABEL_179;
        FlagsPrivate = IdParameterPair::DeserializeId(
                         (struct IdParameters *)((char *)v103 + 16),
                         (unsigned __int16 **)&v105,
                         v12,
                         &v102);
        if ( FlagsPrivate < 0 )
          goto LABEL_180;
        a2 = (unsigned __int64)v105;
      }
      v60 = (const unsigned __int8 *)(a2 + 4);
      if ( a2 + 4 >= a2 && v60 <= v12 )
      {
        v61 = (const unsigned __int8 *)(a2 + 8);
        if ( a2 + 8 >= a2 + 4 && v61 <= v12 )
        {
          v10 = (const unsigned __int8 *)(a2 + 9);
          if ( a2 + 9 >= a2 + 8 && v10 <= v12 )
          {
            v62 = *v60;
            v63 = *v61 == 1;
            v100 = *(unsigned __int8 *)a2 << 8;
            if ( v63 || !*v61 )
            {
              v63 = *v61 == 0;
              v64 = (const unsigned __int8 *)(a2 + 10);
              LODWORD(v96) = !v63;
              if ( a2 + 10 >= a2 + 9 && v64 <= v12 )
              {
                LOBYTE(v10) = *v10;
                v92 = (char)v10;
                if ( (unsigned __int8)v10 <= 1u )
                {
                  v63 = (_BYTE)v10 == 0;
                  v10 = (const unsigned __int8 *)(a2 + 11);
                  v65 = !v63;
                  if ( a2 + 11 >= a2 + 10 && v10 <= v12 && *v64 <= 1u )
                  {
                    v63 = *v64 == 0;
                    v66 = *(unsigned __int8 *)(a2 + 1);
                    v67 = *(unsigned __int8 *)(a2 + 2);
                    LODWORD(v95) = *(unsigned __int8 *)(a2 + 3);
                    LOBYTE(a5) = *(_BYTE *)(a2 + 5);
                    v68 = *(_BYTE *)(a2 + 6);
                    v91 = v60[3];
                    LOBYTE(v105) = v68;
                    if ( !v63 )
                      v89 |= 1u;
                    v69 = SeAlloc(0x108u);
                    if ( !v69
                      || (v70 = CSyncChangeBatch::CSyncChangeBatch(
                                  (_DWORD)v69,
                                  (_DWORD)v103,
                                  (_DWORD)v30,
                                  (_DWORD)v101,
                                  (__int64)v98,
                                  (__int64)v99,
                                  v65,
                                  0),
                          (v71 = v70) == 0) )
                    {
                      FlagsPrivate = -2147024882;
                      goto LABEL_180;
                    }
                    v72 = v70 + 16;
                    FlagsPrivate = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v70 + 16) + 120LL))(
                                     v70 + 16,
                                     (unsigned int)v95 | ((v67 | ((v100 | v66) << 8)) << 8));
                    if ( FlagsPrivate < 0
                      || (FlagsPrivate = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 112LL))(
                                           v72,
                                           v91
                                         | (((unsigned __int8)v105
                                           | (((v62 << 8) | (unsigned int)(unsigned __int8)a5) << 8)) << 8)),
                          FlagsPrivate < 0)
                      || (v73 = CSyncChangeBatch::InitializePrerequisiteKnowledge((CSyncChangeBatch *)v71),
                          FlagsPrivate = v73,
                          v73 < 0) )
                    {
LABEL_177:
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
                      goto LABEL_180;
                    }
                    v74 = (unsigned __int64 *)(v71 + 240);
                    if ( *(_QWORD *)(v71 + 240) )
                    {
                      v75 = 0;
                      if ( !v73 )
                      {
                        v76 = v90;
                        while ( 1 )
                        {
                          if ( (unsigned int)v75 >= v93[0] )
                            goto LABEL_150;
                          a2 = (unsigned __int64)v76[v75];
                          if ( *(_QWORD *)(a2 + 32) )
                            break;
                          v77 = *v74;
                          if ( !*v74 )
                            break;
                          *(_QWORD *)(a2 + 32) = v77;
                          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v77 + 8LL))(v77);
                          v75 = (unsigned int)(v75 + 1);
                        }
                        FlagsPrivate = -2147217379;
LABEL_176:
                        if ( !v71 )
                          goto LABEL_180;
                        goto LABEL_177;
                      }
                    }
LABEL_150:
                    v78 = v93[0];
                    *(_QWORD *)(v71 + 104) = v90;
                    *(_DWORD *)(v71 + 124) = v97;
                    *(_DWORD *)(v71 + 120) = v78;
                    *(_DWORD *)(v71 + 184) = v89;
                    *(_QWORD *)(v71 + 192) = v88;
                    *(_DWORD *)(v71 + 200) = v94;
                    v79 = *(_QWORD *)v71;
                    v90 = 0;
                    v88 = 0;
                    FlagsPrivate = (*(__int64 (__fastcall **)(__int64))(v79 + 40))(v71);
                    if ( FlagsPrivate < 0 )
                      goto LABEL_176;
                    *(_QWORD *)(v71 + 248) = v102;
                    *(_DWORD *)(v71 + 172) = (_DWORD)v96;
                    *(_DWORD *)(v71 + 208) = 1;
                    v63 = v92 == 0;
                    *(_DWORD *)(v71 + 176) = v31 == 0;
                    *(_DWORD *)(v71 + 180) = v87;
                    if ( !v63 )
                      *(_DWORD *)(v71 + 220) = v78;
                    FlagsPrivate = -2147024882;
                    v80 = (Lock *)SeAlloc(0x30u);
                    if ( v80 )
                      *((_DWORD *)v80 + 10) = 0;
                    *(_QWORD *)(v71 + 224) = v80;
                    if ( !v80 )
                      goto LABEL_176;
                    FlagsPrivate = Lock::Initialize(v80);
                    if ( FlagsPrivate < 0 )
                      goto LABEL_176;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 8LL))(v71);
                    v81 = 0;
                    v82 = (_QWORD *)v30[3];
                    FlagsPrivate = 0;
                    a5 = 0;
                    *a6 = (struct CSyncChangeBatch *)v71;
                    while ( 1 )
                    {
                      if ( !v82 )
                        goto LABEL_176;
                      FlagsPrivate = CSyncChange::GetFlagsPrivate((CSyncChange *)*v82, &a5);
                      if ( FlagsPrivate >= 0 )
                        break;
LABEL_175:
                      v82 = (_QWORD *)v82[2];
                      if ( FlagsPrivate < 0 )
                        goto LABEL_176;
                    }
                    v83 = a5;
                    if ( (a5 & 0xFFFF0000) != 0 )
                    {
                      if ( (a5 & 0x200000) != 0 )
                      {
                        v81 = 1;
                      }
                      else if ( (a5 & 0x120000) != 0 )
                      {
                        v81 = 0;
                      }
                    }
                    else
                    {
                      FlagsPrivate = CSyncChangeBatch::SetListPosition(v82);
                    }
                    if ( (v83 & 0x40000) == 0 )
                    {
                      if ( v81 )
                      {
                        if ( (v83 & 0x80000) != 0 )
                        {
                          CSyncChange::SetSortingInfo(*v82, 1, v82, v71);
                          goto LABEL_172;
                        }
                      }
                      else if ( (v83 & 0x80000) != 0 )
                      {
                        goto LABEL_172;
                      }
                      *(_QWORD *)(*v82 + 248LL) = v71;
                    }
LABEL_172:
                    if ( FlagsPrivate >= 0 )
                    {
                      a2 = *v74;
                      if ( *v74 )
                        FlagsPrivate = CSyncChange::SetPrerequisiteKnowledge(
                                         (CSyncChange *)*v82,
                                         (struct ISyncKnowledge *)a2);
                    }
                    goto LABEL_175;
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_179:
    FlagsPrivate = -2147217396;
LABEL_180:
    if ( v30 )
      (*(void (__fastcall **)(_QWORD *, unsigned __int64, const unsigned __int8 *))(*v30 + 16LL))(v30, a2, v10);
    goto LABEL_182;
  }
  while ( 1 )
  {
    v33 = v13 + 4;
    if ( (unsigned int)v32 >= v93[0] )
    {
      if ( v33 < v13 || v33 > v12 )
      {
LABEL_87:
        FlagsPrivate = -2147217396;
      }
      else
      {
        v48 = v13[3];
        v49 = *v13;
        v50 = v13[1];
        v51 = v13[2];
        v13 += 4;
        LOBYTE(a5) = v48;
        v30 = SeAlloc(0x28u);
        if ( v30 )
        {
          v52 = (unsigned __int8)a5;
          v30[2] = 0;
          v30[3] = 0;
          v31 = v52 | ((v51 | ((v50 | (v49 << 8)) << 8)) << 8);
          *((_DWORD *)v30 + 8) = 0;
          *v30 = &CollectionManager<CSyncChangeUnitWrapper>::`vftable';
          *((_DWORD *)v30 + 2) = 1;
          _InterlockedIncrement(&g_cRefThisDll);
          goto LABEL_93;
        }
        FlagsPrivate = -2147024882;
      }
      v87 = SYNC_SERIALIZATION_VERSION_V1;
LABEL_182:
      v46 = v90;
      goto LABEL_183;
    }
    if ( v33 < v13 || v33 > v12 )
      goto LABEL_87;
    v34 = (ChangeGroup *)SeAlloc(0xC8u);
    if ( v34 )
      v34 = ChangeGroup::ChangeGroup(v34, v28, 0, 0);
    v46 = v90;
    v90[v32] = v34;
    if ( !v34 )
      break;
    FlagsPrivate = ChangeGroup::Initialize(v34, v88);
    if ( FlagsPrivate >= 0 )
    {
      v95 = 0;
      v47 = 0;
      FlagsPrivate = CSyncChangeBatch::DeserializeKnowledge(
                       a3,
                       v28,
                       (const unsigned __int8 **)&v105,
                       v12,
                       (struct ISyncKnowledge **)&v95);
      if ( FlagsPrivate < 0 )
      {
LABEL_78:
        v46 = v90;
      }
      else
      {
        while ( v47 < v94 )
        {
          v96 = 0;
          FlagsPrivate = CSyncChangeBatch::DeserializeKnowledge(a3, v28, (const unsigned __int8 **)&v105, v12, &v96);
          if ( FlagsPrivate >= 0 )
          {
            FlagsPrivate = ChangeGroup::SetFilterForgottenKnowledge(v90[v32], v47, v96);
            ((void (__fastcall *)(struct ISyncKnowledge *))v96->lpVtbl->Release)(v96);
          }
          ++v47;
          if ( FlagsPrivate < 0 )
            goto LABEL_78;
        }
        v46 = v90;
        if ( !v95 )
          goto LABEL_81;
        FlagsPrivate = ChangeGroup::SetMadeWithKnowledge(v90[v32], (struct ISyncKnowledge *)v95);
      }
      if ( v95 )
        ((void (__fastcall *)(struct IFilterKeyMap *))v95->lpVtbl->Release)(v95);
LABEL_81:
      v13 = (unsigned __int8 *)v105;
    }
    v32 = (unsigned int)(v32 + 1);
    if ( FlagsPrivate < 0 )
      goto LABEL_83;
  }
  FlagsPrivate = -2147024882;
LABEL_83:
  v87 = SYNC_SERIALIZATION_VERSION_V1;
LABEL_183:
  v43 = v93[0];
LABEL_184:
  if ( v101 )
    ((void (__fastcall *)(struct ISyncKnowledge *))v101->lpVtbl->Release)(v101);
  if ( v98 )
    ((void (__fastcall *)(struct ISyncKnowledge *))v98->lpVtbl->Release)(v98);
  if ( v88 )
    ((void (__fastcall *)(struct IFilterKeyMap *))v88->lpVtbl->Release)(v88);
  if ( v99 )
    ((void (__fastcall *)(struct ISyncFilterInfo *))v99->lpVtbl->Release)(v99);
  if ( v46 )
  {
    for ( i = 0; (unsigned int)i < v43; i = (unsigned int)(i + 1) )
    {
      v85 = v46[i];
      if ( v85 )
        (*(void (__fastcall **)(struct ChangeGroup *))(*(_QWORD *)v85 + 16LL))(v85);
    }
    SeFree(v46);
  }
LABEL_198:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      (unsigned int)WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      (unsigned int)"CSyncChangeBatch::Deserialize",
      FlagsPrivate);
  }
  return (unsigned int)FlagsPrivate;
}

```

## disassembly

```asm
0x18004e754  mov     rax, rsp
0x18004e757  mov     [rax+8], rbx
0x18004e75b  mov     [rax+18h], r8
0x18004e75f  mov     [rax+10h], rdx
0x18004e763  push    rbp
0x18004e764  push    rsi
0x18004e765  push    rdi
0x18004e766  push    r12
0x18004e768  push    r13
0x18004e76a  push    r14
0x18004e76c  push    r15
0x18004e76e  lea     rbp, [rax-4Fh]
0x18004e772  sub     rsp, 0E0h
0x18004e779  mov     rsi, r9
0x18004e77c  mov     r14, r8
0x18004e77f  mov     r10, rdx
0x18004e782  mov     r12, rcx
0x18004e785  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e78c  lea     rax, WPP_GLOBAL_Control
0x18004e793  cmp     rcx, rax
0x18004e796  jz      short loc_18004E7C4
0x18004e798  test    byte ptr [rcx+1Ch], 10h
0x18004e79c  jz      short loc_18004E7C4
0x18004e79e  cmp     byte ptr [rcx+19h], 5
0x18004e7a2  jb      short loc_18004E7C4
0x18004e7a4  mov     rcx, [rcx+10h]
0x18004e7a8  lea     r9, aCsyncchangebat_21; "CSyncChangeBatch::Deserialize"
0x18004e7af  mov     edx, 42h ; 'B'
0x18004e7b4  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x18004e7bb  call    WPP_SF_s
0x18004e7c0  mov     r10, [rbp+47h+arg_8]
0x18004e7c4  xor     r8d, r8d
0x18004e7c7  mov     ebx, 80004003h
0x18004e7cc  mov     [rbp+47h+var_48], r8
0x18004e7d0  mov     eax, r8d
0x18004e7d3  mov     [rbp+47h+var_A8], rax
0x18004e7d7  mov     [rbp+47h+var_78], rax
0x18004e7db  mov     [rbp+47h+var_60], r8
0x18004e7df  mov     [rbp+47h+var_58], r8
0x18004e7e3  mov     [rbp+47h+var_40], r8
0x18004e7e7  mov     [rbp+47h+var_A0], r8d
0x18004e7eb  test    rsi, rsi
0x18004e7ee  jz      loc_18004F444
0x18004e7f4  mov     rax, [rbp+47h+arg_28]
0x18004e7f8  test    rax, rax
0x18004e7fb  jz      loc_18004F444
0x18004e801  movsxd  r15, [rbp+47h+arg_20]
0x18004e805  mov     ebx, 8004100Ch
0x18004e80a  add     r15, rsi
0x18004e80d  cmp     rsi, r15
0x18004e810  ja      loc_18004F444
0x18004e816  lea     rdi, [rsi+8]
0x18004e81a  mov     [rax], r8
0x18004e81d  cmp     rdi, rsi
0x18004e820  jb      loc_18004F444
0x18004e826  cmp     rdi, r15
0x18004e829  ja      loc_18004F444
0x18004e82f  movzx   eax, byte ptr [rsi+1]
0x18004e833  mov     ebx, r8d
0x18004e836  movzx   r13d, byte ptr [rsi]
0x18004e83a  movzx   ecx, byte ptr [rsi+4]
0x18004e83e  shl     r13, 8
0x18004e842  or      r13, rax
0x18004e845  shl     rcx, 8
0x18004e849  movzx   eax, byte ptr [rsi+2]
0x18004e84d  shl     r13, 8
0x18004e851  or      r13, rax
0x18004e854  mov     [rbp+47h+var_98], r8
0x18004e858  movzx   eax, byte ptr [rsi+3]
0x18004e85c  shl     r13, 8
0x18004e860  or      r13, rax
0x18004e863  mov     [rbp+47h+var_88], r8d
0x18004e867  movzx   eax, byte ptr [rsi+5]
0x18004e86b  or      rcx, rax
0x18004e86e  shl     r13, 20h
0x18004e872  movzx   eax, byte ptr [rsi+6]
0x18004e876  shl     rcx, 8
0x18004e87a  or      rcx, rax
0x18004e87d  mov     [rbp+47h+var_68], r8d
0x18004e881  movzx   eax, byte ptr [rsi+7]
0x18004e885  shl     rcx, 8
0x18004e889  or      rcx, rax
0x18004e88c  mov     [rbp+47h+arg_18], rdi
0x18004e890  add     r13, rcx
0x18004e893  lea     rax, [r13-4]
0x18004e897  cmp     rax, 1
0x18004e89b  jbe     short loc_18004E8AF
0x18004e89d  cmp     r13, 3
0x18004e8a1  jnz     loc_18004EA61
0x18004e8a7  mov     rsi, rdi
0x18004e8aa  jmp     loc_18004E999
0x18004e8af  lea     rsi, [rdi+4]
0x18004e8b3  cmp     rsi, rdi
0x18004e8b6  jb      loc_18004EA61
0x18004e8bc  cmp     rsi, r15
0x18004e8bf  ja      loc_18004EA61
0x18004e8c5  movzx   eax, byte ptr [rdi]
0x18004e8c8  movzx   r14d, byte ptr [rdi+1]
0x18004e8cd  shl     eax, 8
0x18004e8d0  or      r14d, eax
0x18004e8d3  mov     [rbp+47h+arg_18], rsi
0x18004e8d7  movzx   eax, byte ptr [rdi+2]
0x18004e8db  shl     r14d, 8
0x18004e8df  or      r14d, eax
0x18004e8e2  movzx   eax, byte ptr [rdi+3]
0x18004e8e6  shl     r14d, 8
0x18004e8ea  mov     rdi, rsi
0x18004e8ed  or      r14d, eax
0x18004e8f0  jbe     loc_18004E995
0x18004e8f6  lea     rax, [rbp+47h+var_58]
0x18004e8fa  mov     r9d, r14d; unsigned int
0x18004e8fd  mov     r8, rsi; unsigned __int8 *
0x18004e900  mov     [rsp+110h+var_F0], rax; struct ISyncFilterInfo **
0x18004e905  mov     rdx, r10; struct IdParameters *
0x18004e908  mov     rcx, r12; struct ISyncFilterDeserializer *
0x18004e90b  call    ?Deserialize@FilterInfo@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUISyncFilterInfo@@@Z; FilterInfo::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,ISyncFilterInfo * *)
0x18004e910  xor     r8d, r8d
0x18004e913  lea     rdi, [rsi+r14]
0x18004e917  mov     [rbp+47h+arg_18], rdi
0x18004e91b  mov     ebx, eax
0x18004e91d  test    eax, eax
0x18004e91f  js      loc_18004EA66
0x18004e925  mov     rcx, [rbp+47h+var_58]
0x18004e929  test    rcx, rcx
0x18004e92c  jz      short loc_18004E992
0x18004e92e  mov     [rbp+47h+var_70], r8
0x18004e932  lea     rdx, _GUID_19b394ba_e3d0_468c_934d_321968b2ab34
0x18004e939  mov     rax, [rcx]
0x18004e93c  lea     r8, [rbp+47h+var_70]
0x18004e940  mov     rax, [rax]
0x18004e943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e948  xor     r8d, r8d
0x18004e94b  mov     ebx, eax
0x18004e94d  test    eax, eax
0x18004e94f  jnz     short loc_18004E984
0x18004e951  mov     rcx, [rbp+47h+var_70]
0x18004e955  lea     rdx, [rbp+47h+var_A0]
0x18004e959  mov     rax, [rcx]
0x18004e95c  mov     rax, [rax+20h]
0x18004e960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e965  mov     rcx, [rbp+47h+var_70]
0x18004e969  mov     ebx, eax
0x18004e96b  mov     rax, [rcx]
0x18004e96e  mov     rax, [rax+10h]
0x18004e972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e977  mov     rsi, rdi
0x18004e97a  test    ebx, ebx
0x18004e97c  js      loc_18004EA66
0x18004e982  jmp     short loc_18004E995
0x18004e984  cmp     eax, 80004002h
0x18004e989  jnz     short loc_18004E977
0x18004e98b  or      [rbp+47h+var_A0], 1
0x18004e98f  mov     ebx, r8d
0x18004e992  mov     rsi, rdi
0x18004e995  mov     r14, [rbp+47h+arg_10]
0x18004e999  lea     rax, [rsi+4]
0x18004e99d  cmp     rax, rsi
0x18004e9a0  jb      loc_18004EA61
0x18004e9a6  cmp     rax, r15
0x18004e9a9  ja      loc_18004EA61
0x18004e9af  test    ebx, ebx
0x18004e9b1  js      loc_18004EA66
0x18004e9b7  mov     rsi, [rbp+47h+arg_8]
0x18004e9bb  lea     rax, [rbp+47h+var_48]
0x18004e9bf  mov     rdx, rsi; struct IdParameters *
0x18004e9c2  mov     [rsp+110h+var_F0], rax; struct ISyncKnowledge **
0x18004e9c7  mov     r9, r15; unsigned __int8 *
0x18004e9ca  lea     r8, [rbp+47h+arg_18]; unsigned __int8 **
0x18004e9ce  mov     rcx, r14; struct IProviderSyncServices *
0x18004e9d1  call    ?DeserializeKnowledge@CSyncChangeBatch@@SAJPEAUIProviderSyncServices@@PEAVIdParameters@@PEAPEBEPEBEPEAPEAUISyncKnowledge@@@Z; CSyncChangeBatch::DeserializeKnowledge(IProviderSyncServices *,IdParameters *,uchar const * *,uchar const *,ISyncKnowledge * *)
0x18004e9d6  mov     ebx, eax
0x18004e9d8  test    eax, eax
0x18004e9da  js      loc_18004EC58
0x18004e9e0  mov     rdx, [rbp+47h+arg_18]
0x18004e9e4  movzx   ecx, byte ptr [rdx]
0x18004e9e7  movzx   eax, byte ptr [rdx+1]
0x18004e9eb  shl     ecx, 8
0x18004e9ee  or      ecx, eax
0x18004e9f0  movzx   eax, byte ptr [rdx+2]
0x18004e9f4  shl     ecx, 8
0x18004e9f7  or      ecx, eax
0x18004e9f9  movzx   eax, byte ptr [rdx+3]
0x18004e9fd  shl     ecx, 8
0x18004ea00  add     rdx, 4
0x18004ea04  or      ecx, eax
0x18004ea06  mov     r8d, ecx
0x18004ea09  lea     rdi, [rcx+rdx]
0x18004ea0d  cmp     rdi, rdx
0x18004ea10  jb      short loc_18004EA5D
0x18004ea12  cmp     rdi, r15
0x18004ea15  ja      short loc_18004EA5D
0x18004ea17  test    ecx, ecx
0x18004ea19  jz      loc_18004EAE5
0x18004ea1f  mov     rax, [r14]
0x18004ea22  lea     rcx, [rbp+47h+var_60]
0x18004ea26  mov     [rsp+110h+var_F0], rcx
0x18004ea2b  xor     r9d, r9d
0x18004ea2e  mov     rcx, r14
0x18004ea31  mov     rax, [rax+50h]
0x18004ea35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea3a  mov     ebx, eax
0x18004ea3c  test    eax, eax
0x18004ea3e  js      loc_18004EAE5
0x18004ea44  mov     rdx, [rbp+47h+var_60]; struct ISyncKnowledge *
0x18004ea48  mov     rcx, rsi; this
0x18004ea4b  call    ?ValidateIdFormatOfKnowledge@ChangeGroup@@SAJPEAVIdParameters@@PEAUISyncKnowledge@@@Z; ChangeGroup::ValidateIdFormatOfKnowledge(IdParameters *,ISyncKnowledge *)
0x18004ea50  mov     ebx, eax
0x18004ea52  cmp     eax, 80041000h
0x18004ea57  jnz     loc_18004EAE5
0x18004ea5d  mov     [rbp+47h+arg_18], rdi
0x18004ea61  mov     ebx, 8004100Ch
0x18004ea66  mov     r13, [rbp+47h+arg_8]
0x18004ea6a  mov     rcx, [rbp+47h+var_A8]
0x18004ea6e  xor     esi, esi
0x18004ea70  xor     r14d, r14d
0x18004ea73  mov     [rbp+47h+var_80], esi
0x18004ea76  test    ebx, ebx
0x18004ea78  js      short loc_18004EA91
0x18004ea7a  test    rcx, rcx
0x18004ea7d  jz      short loc_18004EA91
0x18004ea7f  mov     rax, [rcx]
0x18004ea82  lea     rdx, [rbp+47h+var_80]
0x18004ea86  mov     rax, [rax+18h]
0x18004ea8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea8f  mov     ebx, eax
0x18004ea91  xor     r12d, r12d
0x18004ea94  test    ebx, ebx
0x18004ea96  js      loc_18004EDED
0x18004ea9c  lea     rax, [rdi+4]
0x18004eaa0  cmp     r12d, [rbp+47h+var_88]
0x18004eaa4  jnb     loc_18004ED72
0x18004eaaa  cmp     rax, rdi
0x18004eaad  jb      loc_18004ED61
0x18004eab3  cmp     rax, r15
0x18004eab6  ja      loc_18004ED61
0x18004eabc  mov     ecx, 0C8h; unsigned __int64
0x18004eac1  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18004eac6  test    rax, rax
0x18004eac9  jz      loc_18004EC61
0x18004eacf  xor     r9d, r9d; struct ISyncKnowledge *
0x18004ead2  xor     r8d, r8d; int
0x18004ead5  mov     rdx, r13; struct IdParameters *
0x18004ead8  mov     rcx, rax; this
0x18004eadb  call    ??0ChangeGroup@@QEAA@PEAVIdParameters@@HPEAUISyncKnowledge@@@Z; ChangeGroup::ChangeGroup(IdParameters *,int,ISyncKnowledge *)
0x18004eae0  jmp     loc_18004EC61
0x18004eae5  mov     [rbp+47h+arg_18], rdi
0x18004eae9  test    ebx, ebx
0x18004eaeb  js      loc_18004EA66
0x18004eaf1  lea     rdx, [rdi+4]
0x18004eaf5  cmp     rdx, rdi
0x18004eaf8  jb      loc_18004EA61
0x18004eafe  cmp     rdx, r15
0x18004eb01  ja      loc_18004EA61
0x18004eb07  cmp     r13, 5
0x18004eb0b  jb      loc_18004EB9D
0x18004eb11  movzx   ecx, byte ptr [rdi+1]
0x18004eb15  movzx   eax, byte ptr [rdi]
0x18004eb18  shl     eax, 8
0x18004eb1b  or      ecx, eax
0x18004eb1d  mov     [rbp+47h+arg_18], rdx
0x18004eb21  movzx   eax, byte ptr [rdi+2]
0x18004eb25  shl     ecx, 8
0x18004eb28  or      ecx, eax
0x18004eb2a  movzx   eax, byte ptr [rdi+3]
0x18004eb2e  shl     ecx, 8
0x18004eb31  mov     rdi, rdx
0x18004eb34  or      ecx, eax
0x18004eb36  mov     r9d, ecx; unsigned int
0x18004eb39  lea     rsi, [rcx+rdx]
0x18004eb3d  cmp     rsi, rdx
0x18004eb40  jb      loc_18004EA61
0x18004eb46  cmp     rsi, r15
0x18004eb49  ja      loc_18004EA61
0x18004eb4f  test    ecx, ecx
0x18004eb51  jz      short loc_18004EB81
0x18004eb53  mov     r13, [rbp+47h+arg_8]
0x18004eb57  test    r12, r12
0x18004eb5a  jz      short loc_18004EB93
0x18004eb5c  lea     rax, [rbp+47h+var_78]
0x18004eb60  mov     r8, rdx; unsigned __int8 *
0x18004eb63  mov     rdx, r13; struct IdParameters *
0x18004eb66  mov     [rsp+110h+var_F0], rax; struct IFilterKeyMap **
0x18004eb6b  mov     rcx, r12; struct ISyncFilterDeserializer *
0x18004eb6e  call    ?Deserialize@FilterKeyMap@@SAJPEAUISyncFilterDeserializer@@PEAVIdParameters@@PEBEKPEAPEAUIFilterKeyMap@@@Z; FilterKeyMap::Deserialize(ISyncFilterDeserializer *,IdParameters *,uchar const *,ulong,IFilterKeyMap * *)
0x18004eb73  mov     ebx, eax
0x18004eb75  test    eax, eax
0x18004eb77  js      short loc_18004EB86
0x18004eb79  mov     rax, [rbp+47h+var_78]
0x18004eb7d  mov     [rbp+47h+var_A8], rax
0x18004eb81  mov     rdi, rsi
0x18004eb84  jmp     short loc_18004EBA0
0x18004eb86  mov     rcx, [rbp+47h+var_78]
0x18004eb8a  mov     [rbp+47h+var_A8], rcx
0x18004eb8e  jmp     loc_18004EA6E
0x18004eb93  mov     ebx, 8004100Ch
0x18004eb98  jmp     loc_18004EA6A
0x18004eb9d  mov     rsi, rdi
0x18004eba0  movzx   eax, byte ptr [rdi]
0x18004eba3  lea     rdi, [rsi+4]
0x18004eba7  movzx   ecx, byte ptr [rsi+1]
  ... truncated ...
```
