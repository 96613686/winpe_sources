# CSyncChange::Deserialize(IdParameters *,IProviderSyncServices *,uchar const *,long,ChangeGroup * *,ulong,IForgottenKnowledge *,ISyncFilterInfo *,int,__MIDL___MIDL_itf_winsync_0000_0000_0007 &,CSyncChange * *)

- ea: `0x180055ed8`
- end: `0x180056a6d`
- name: `?Deserialize@CSyncChange@@SAJPEAVIdParameters@@PEAUIProviderSyncServices@@PEBEJPEAPEAVChangeGroup@@KPEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HAEAW4__MIDL___MIDL_itf_winsync_0000_0000_0007@@PEAPEAV1@@Z`
- size: `2965`
- prototype: `__int64 __fastcall(struct IdParameters *this, struct IProviderSyncServices *, const unsigned __int8 *, int, struct ChangeGroup **, unsigned int, struct IForgottenKnowledge *, struct ISyncFilterInfo *, int, enum __MIDL___MIDL_itf_winsync_0000_0000_0007 *, struct CSyncChange **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18004e754`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x18004b2a0`
- `0x18004f4a8`
- `0x1800553ac`
- `0x18005555c`
- `0x180055ed8`
- `0x180059370`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x180055f57`: `CSyncChange::Deserialize`
- `0x1800569f3`: `CSyncChange::Deserialize`

## pseudocode

```c
__int64 __fastcall CSyncChange::Deserialize(
        struct IdParameters *this,
        struct IProviderSyncServices *a2,
        const unsigned __int8 *a3,
        int a4,
        struct ChangeGroup **a5,
        unsigned int a6,
        struct IForgottenKnowledge *a7,
        struct ISyncFilterInfo *a8,
        int a9,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0007 *a10,
        struct CSyncChange **a11)
{
  struct CSyncChange **v13; // rax
  __int64 v14; // rsi
  PVOID *v15; // rcx
  int v16; // ebx
  const unsigned __int8 *v17; // r14
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  CSyncChange *v20; // rsi
  unsigned int v21; // edi
  unsigned int v22; // r13d
  struct ChangeGroup *v23; // r12
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int8 *v26; // rax
  unsigned __int8 *v27; // r15
  int v28; // eax
  unsigned __int8 *v29; // r8
  int v30; // eax
  const unsigned __int8 *v31; // rax
  int v32; // ecx
  __int64 v33; // rcx
  CSyncChange *v34; // rax
  BOOL v35; // ecx
  int v36; // eax
  bool v37; // sf
  unsigned __int8 *v38; // rdi
  int v39; // r13d
  int v40; // eax
  int v41; // r13d
  int v42; // r15d
  unsigned int v43; // r13d
  IdParameterPair *v44; // rax
  unsigned __int8 *v45; // r8
  unsigned __int8 *v46; // r9
  int v47; // ecx
  int v48; // eax
  int v49; // ecx
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rdx
  __int64 v53; // rax
  unsigned __int64 v54; // rcx
  unsigned __int8 *v55; // r8
  int v56; // ecx
  int v57; // eax
  int v58; // ecx
  unsigned __int8 *v59; // r9
  __int64 v60; // rcx
  unsigned __int64 v61; // rdx
  unsigned __int64 v62; // r15
  unsigned __int8 *v63; // r13
  unsigned int v64; // r15d
  unsigned __int8 *v65; // rax
  unsigned int v66; // edi
  DWORD dwLastUpdatingReplicaKey; // eax
  unsigned __int8 *v68; // r13
  unsigned __int64 v69; // rdx
  __int64 v70; // rax
  unsigned __int64 v71; // rcx
  unsigned __int64 v72; // rdx
  __int64 v73; // rax
  int v74; // eax
  unsigned __int8 *v76; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v77; // [rsp+88h] [rbp-78h] BYREF
  struct IdParameters *v78; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v79; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 *v80; // [rsp+A0h] [rbp-60h] BYREF
  struct ChangeGroup **v81; // [rsp+A8h] [rbp-58h]
  struct _SYNC_VERSION v82; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v83; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v84; // [rsp+C8h] [rbp-38h]
  struct CSyncChange **v85; // [rsp+D0h] [rbp-30h]
  enum __MIDL___MIDL_itf_winsync_0000_0000_0007 *v86; // [rsp+D8h] [rbp-28h]
  struct IProviderSyncServices *v87; // [rsp+E0h] [rbp-20h]
  struct _SYNC_VERSION v88; // [rsp+E8h] [rbp-18h] BYREF
  struct _SYNC_VERSION v89; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v90; // [rsp+108h] [rbp+8h]

  v81 = a5;
  v86 = a10;
  v13 = a11;
  v85 = a11;
  v14 = a4;
  v87 = a2;
  v78 = this;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      "CSyncChange::Deserialize");
    v15 = (PVOID *)WPP_GLOBAL_Control;
    v13 = v85;
  }
  v16 = -2147467261;
  if ( a3 )
  {
    if ( v13 )
    {
      v17 = &a3[v14];
      v16 = -2147217396;
      if ( a3 < &a3[v14] )
      {
        v79 = 0;
        v80 = 0;
        v83 = 0;
        *v13 = 0;
        v89 = 0;
        v82 = 0;
        v88 = 0;
        if ( a3 + 8 < a3 )
          goto LABEL_115;
        if ( a3 + 8 > v17 )
          goto LABEL_115;
        v18 = (unsigned __int64)a3[4] << 8;
        v19 = a3[2] | ((a3[1] | ((unsigned __int64)*a3 << 8)) << 8);
        v76 = (unsigned __int8 *)(a3 + 8);
        v84 = ((a3[3] | (v19 << 8)) << 32) + (((a3[6] | ((a3[5] | v18) << 8)) << 8) | a3[7]);
        if ( ((v84 - 5) & 0xFFFFFFFFFFFFFFFDuLL) != 0 )
          goto LABEL_115;
        v20 = 0;
        LODWORD(v77) = 0;
        v21 = 0;
        v22 = 0;
        v23 = 0;
        v16 = IdParameterPair::DeserializeId(this, (unsigned __int16 **)&v76, v17, &v79);
        if ( v16 < 0 )
          goto LABEL_60;
        if ( v76 + 4 < v76 )
          goto LABEL_29;
        if ( v76 + 4 > v17 )
          goto LABEL_29;
        v89.dwLastUpdatingReplicaKey = v76[3] | ((v76[2] | ((v76[1] | (*v76 << 8)) << 8)) << 8);
        if ( v76 + 12 < v76 + 4 )
          goto LABEL_29;
        if ( v76 + 12 > v17 )
          goto LABEL_29;
        v89.ullTickCount = (v76[11] | ((v76[10] | ((((unsigned __int64)v76[8] << 8) | v76[9]) << 8)) << 8))
                         + ((v76[7] | ((v76[6] | ((((unsigned __int64)v76[4] << 8) | v76[5]) << 8)) << 8)) << 32);
        if ( v76 + 16 < v76 + 12 )
          goto LABEL_29;
        if ( v76 + 16 > v17 )
          goto LABEL_29;
        v82.dwLastUpdatingReplicaKey = v76[15] | ((v76[14] | ((v76[13] | (v76[12] << 8)) << 8)) << 8);
        if ( v76 + 24 < v76 + 16 )
          goto LABEL_29;
        if ( v76 + 24 > v17 )
          goto LABEL_29;
        v82.ullTickCount = (v76[23] | ((v76[22] | ((v76[21] | ((unsigned __int64)v76[20] << 8)) << 8)) << 8))
                         + ((v76[19] | ((v76[18] | ((v76[17] | ((unsigned __int64)v76[16] << 8)) << 8)) << 8)) << 32);
        if ( v76 + 28 < v76 + 24 )
          goto LABEL_29;
        if ( v76 + 28 > v17 )
          goto LABEL_29;
        v88.dwLastUpdatingReplicaKey = v76[27] | ((v76[26] | ((v76[25] | (v76[24] << 8)) << 8)) << 8);
        if ( v76 + 36 < v76 + 28 || v76 + 36 > v17 )
          goto LABEL_29;
        v24 = (v76[31] | ((v76[30] | ((v76[29] | ((unsigned __int64)v76[28] << 8)) << 8)) << 8)) << 32;
        v25 = v76[35] | ((v76[34] | ((((unsigned __int64)v76[32] << 8) | v76[33]) << 8)) << 8);
        v76 += 36;
        v88.ullTickCount = v25 + v24;
        v16 = IdParameterPair::DeserializeId(
                (struct IdParameters *)((char *)this + 16),
                (unsigned __int16 **)&v76,
                v17,
                &v80);
        if ( v16 < 0 )
        {
LABEL_60:
          v27 = v76;
          goto LABEL_61;
        }
        if ( v84 < 7 )
        {
          v27 = v76;
        }
        else
        {
          v26 = v76;
          v27 = v76 + 1;
          if ( v76 + 1 < v76 || v27 > v17 || *v76 >= 2u )
            goto LABEL_29;
          ++v76;
          if ( *v26 )
          {
            v28 = IdParameterPair::DeserializeId(
                    (struct IdParameters *)((char *)v78 + 16),
                    (unsigned __int16 **)&v76,
                    v17,
                    &v83);
            v27 = v76;
            v16 = v28;
            if ( v28 < 0 )
              goto LABEL_61;
          }
          if ( *(int *)v86 < 5 )
            *v86 = SYNC_SERIALIZATION_VERSION_V3;
        }
        v29 = v27 + 4;
        if ( v27 + 4 >= v27 && v29 <= v17 )
        {
          if ( v16 < 0 )
            goto LABEL_61;
          v30 = v27[3];
          v21 = v30 | ((v27[2] | ((v27[1] | (*v27 << 8)) << 8)) << 8);
          if ( ((v30 & 1) == 0 || (v30 & 6) == 0) && ((v30 & 2) == 0 || (v30 & 5) == 0) )
          {
            v31 = v27 + 8;
            if ( v27 + 8 >= v27 + 4 && v31 <= v17 && v27 + 11 >= v27 + 8 && v27 + 11 <= v17 )
            {
              v32 = *v29;
              if ( *v31 <= 1u && v27[9] < 2u && v27[10] < 2u )
              {
                LODWORD(v77) = v27[10] != 0;
                if ( v27 + 15 >= v27 + 11 && v27 + 15 <= v17 )
                {
                  v22 = v27[7] | ((v27[6] | (((v32 << 8) | v27[5]) << 8)) << 8);
                  v27 += 15;
                  v33 = v29[10] | ((v29[9] | ((v29[8] | (v29[7] << 8)) << 8)) << 8);
                  if ( v81 && a6 )
                  {
                    if ( (unsigned int)v33 >= a6 )
                    {
                      if ( (_DWORD)v33 != a6 )
                        v16 = -2147217396;
                    }
                    else
                    {
                      _mm_lfence();
                      v23 = v81[v33];
                      (*(void (__fastcall **)(struct ChangeGroup *))(*(_QWORD *)v23 + 8LL))(v23);
                    }
                    if ( v16 < 0 )
                      goto LABEL_61;
                    goto LABEL_57;
                  }
                  if ( !(_DWORD)v33 )
                  {
LABEL_57:
                    v34 = (CSyncChange *)SeAlloc(0x110u);
                    if ( !v34 || (v20 = CSyncChange::CSyncChange(v34, v78)) == 0 )
                    {
                      v16 = -2147024882;
                      goto LABEL_111;
                    }
LABEL_61:
                    if ( v16 >= 0 )
                    {
                      v35 = 0;
                      if ( (_DWORD)v77 )
                        v35 = a9 == 0;
                      v36 = CSyncChange::Init(
                              v20,
                              v79,
                              v83,
                              &v89,
                              &v82,
                              &v88,
                              v80,
                              v21,
                              v22,
                              (int)v77,
                              v35,
                              v23,
                              0,
                              a7,
                              0,
                              a8);
                      v16 = v36;
                      v37 = v36 < 0;
                      if ( v36 )
                      {
                        if ( v36 != -2147024882 )
                        {
LABEL_110:
                          v16 = -2147217396;
                          goto LABEL_111;
                        }
                        v37 = 1;
                      }
                      if ( !v37 )
                      {
                        v38 = v27 + 4;
                        if ( v27 + 4 < v27 || v38 > v17 )
                          goto LABEL_110;
                        v39 = v27[1] | (*v27 << 8);
                        v76 = v27 + 4;
                        v40 = v27[3];
                        v41 = (v27[2] | (v39 << 8)) << 8;
                        v42 = 0;
                        v43 = v40 | v41;
                        if ( v43 )
                        {
                          v44 = (struct IdParameters *)((char *)v78 + 32);
                          v81 = (struct ChangeGroup **)((char *)v78 + 32);
                          do
                          {
                            v77 = 0;
                            v82 = 0;
                            v89 = 0;
                            v16 = IdParameterPair::DeserializeId(v44, (unsigned __int16 **)&v76, v17, &v77);
                            if ( v16 < 0 )
                              goto LABEL_111;
                            v38 = v76;
                            v45 = v76 + 4;
                            if ( v76 + 4 < v76 )
                              goto LABEL_82;
                            if ( v45 > v17 )
                              goto LABEL_82;
                            v46 = v76 + 12;
                            v47 = v76[1] | (*v76 << 8);
                            v76 += 4;
                            v48 = v38[3];
                            v49 = (v38[2] | (v47 << 8)) << 8;
                            v38 = v45;
                            v82.dwLastUpdatingReplicaKey = v48 | v49;
                            if ( v45 + 8 < v45 )
                              goto LABEL_82;
                            if ( v46 > v17 )
                              goto LABEL_82;
                            v38 = v45 + 8;
                            v50 = (unsigned __int64)v45[4] << 8;
                            v51 = v45[2] | ((((unsigned __int64)*v45 << 8) | v45[1]) << 8);
                            v76 = v45 + 8;
                            v52 = (v45[3] | (v51 << 8)) << 32;
                            v53 = v45[7];
                            v54 = (v45[6] | ((v45[5] | v50) << 8)) << 8;
                            v55 = v45 + 12;
                            v82.ullTickCount = (v53 | v54) + v52;
                            if ( v46 + 4 < v46
                              || v55 > v17
                              || (v38 = v46 + 4,
                                  v56 = v46[1] | (*v46 << 8),
                                  v76 = v46 + 4,
                                  v57 = v46[3],
                                  v58 = (v46[2] | (v56 << 8)) << 8,
                                  v59 = v46 + 12,
                                  v89.dwLastUpdatingReplicaKey = v57 | v58,
                                  v55 + 8 < v55)
                              || v59 > v17 )
                            {
LABEL_82:
                              v16 = -2147217396;
                            }
                            else
                            {
                              v38 = v55 + 8;
                              v60 = v55[5];
                              v61 = v55[1] | ((unsigned __int64)*v55 << 8);
                              v76 = v55 + 8;
                              v89.ullTickCount = (v55[7]
                                                | ((v55[6] | ((((unsigned __int64)v55[4] << 8) | v60) << 8)) << 8))
                                               + ((v55[3] | ((v55[2] | (v61 << 8)) << 8)) << 32);
                              v16 = CSyncChange::AddChangeUnit(v20, v77, &v82, &v89);
                            }
                            IdParameters::FreeId(v77);
                            if ( v16 < 0 )
                              goto LABEL_111;
                            v44 = (IdParameterPair *)v81;
                          }
                          while ( ++v42 < v43 );
                        }
                        v62 = v84;
                        if ( v84 < 7 )
                          goto LABEL_122;
                        if ( v38 + 4 < v38 || v38 + 4 > v17 )
                          goto LABEL_110;
                        if ( v16 < 0 )
                          goto LABEL_111;
                        v16 = CSyncChangeBatch::DeserializeKnowledge(
                                v87,
                                v78,
                                (const unsigned __int8 **)&v76,
                                v17,
                                (struct ISyncKnowledge **)v20 + 23);
                        if ( v16 < 0 )
                          goto LABEL_111;
                        if ( v62 < 7 )
                          goto LABEL_122;
                        v63 = v76 + 4;
                        if ( v76 + 4 < v76 || v63 > v17 )
                          goto LABEL_110;
                        v64 = v76[3] | ((v76[2] | ((v76[1] | (*v76 << 8)) << 8)) << 8);
                        v65 = &v63[13 * v64];
                        if ( v65 < v63 || v65 > v17 )
                        {
LABEL_104:
                          v16 = -2147217396;
                        }
                        else
                        {
                          v66 = 0;
                          while ( v66 < v64 )
                          {
                            v89 = 0;
                            v90 = 0;
                            if ( *v63 > 1u )
                              goto LABEL_104;
                            dwLastUpdatingReplicaKey = v89.dwLastUpdatingReplicaKey;
                            if ( *v63 )
                              dwLastUpdatingReplicaKey = 1;
                            v68 = v63 + 1;
                            v89.dwLastUpdatingReplicaKey = dwLastUpdatingReplicaKey;
                            LODWORD(v89.ullTickCount) = v68[3] | ((v68[2] | (((*v68 << 8) | v68[1]) << 8)) << 8);
                            v69 = (v68[7] | ((v68[6] | ((v68[5] | ((unsigned __int64)v68[4] << 8)) << 8)) << 8)) << 32;
                            v70 = v68[11];
                            v71 = (v68[10] | ((v68[9] | ((unsigned __int64)v68[8] << 8)) << 8)) << 8;
                            v63 = v68 + 12;
                            v72 = (v70 | v71) + v69;
                            v73 = *((_QWORD *)v20 + 6);
                            v90 = v72;
                            v74 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _SYNC_VERSION *))(v73 + 24))(
                                    (__int64)v20 + 48,
                                    v66,
                                    &v89);
                            v16 = v74;
                            if ( v74 )
                            {
                              if ( v74 != -2147024882 )
                                goto LABEL_104;
                            }
                            ++v66;
                            if ( v74 < 0 )
                              break;
                          }
                        }
                        if ( v63 + 1 < v63 || v63 + 1 > v17 )
                          goto LABEL_110;
                        if ( v16 >= 0 )
                        {
                          if ( *v63 == 1 )
                          {
                            v16 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v20 + 6) + 32LL))((__int64)v20 + 48);
                            if ( v16 < 0 )
                              goto LABEL_111;
                          }
                          else if ( *v63 )
                          {
                            goto LABEL_110;
                          }
LABEL_122:
                          (*(void (__fastcall **)(CSyncChange *))(*(_QWORD *)v20 + 8LL))(v20);
                          *v85 = v20;
                        }
                      }
                    }
LABEL_111:
                    if ( v23 )
                      (*(void (__fastcall **)(struct ChangeGroup *))(*(_QWORD *)v23 + 16LL))(v23);
                    if ( v20 )
                      (*(void (__fastcall **)(CSyncChange *))(*(_QWORD *)v20 + 16LL))(v20);
                    goto LABEL_115;
                  }
                }
              }
            }
          }
        }
LABEL_29:
        v16 = -2147217396;
LABEL_115:
        IdParameters::FreeId(v79);
        IdParameters::FreeId(v80);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x20) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v15[2],
      92,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange::Deserialize",
      v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180055ed8  mov     [rsp-8+arg_18], rbx
0x180055edd  push    rbp
0x180055ede  push    rsi
0x180055edf  push    rdi
0x180055ee0  push    r12
0x180055ee2  push    r13
0x180055ee4  push    r14
0x180055ee6  push    r15
0x180055ee8  lea     rbp, [rsp-20h]
0x180055eed  sub     rsp, 120h
0x180055ef4  mov     rax, cs:__security_cookie
0x180055efb  xor     rax, rsp
0x180055efe  mov     [rbp+50h+var_40], rax
0x180055f02  mov     rax, [rbp+50h+arg_20]
0x180055f09  mov     rdi, r8
0x180055f0c  mov     [rbp+50h+var_A8], rax
0x180055f10  mov     r15, rcx
0x180055f13  mov     rax, [rbp+50h+arg_48]
0x180055f1a  mov     [rbp+50h+var_78], rax
0x180055f1e  mov     rax, [rbp+50h+arg_50]
0x180055f25  mov     [rbp+50h+var_80], rax
0x180055f29  movsxd  rsi, r9d
0x180055f2c  mov     [rbp+50h+var_70], rdx
0x180055f30  mov     [rbp+50h+var_C0], rcx
0x180055f34  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f3b  lea     r12, WPP_GLOBAL_Control
0x180055f42  cmp     rcx, r12
0x180055f45  jz      short loc_180055F7A
0x180055f47  test    byte ptr [rcx+1Ch], 20h
0x180055f4b  jz      short loc_180055F7A
0x180055f4d  cmp     byte ptr [rcx+19h], 5
0x180055f51  jb      short loc_180055F7A
0x180055f53  mov     rcx, [rcx+10h]
0x180055f57  lea     r9, aCsyncchangeDes; "CSyncChange::Deserialize"
0x180055f5e  mov     edx, 5Bh ; '['
0x180055f63  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180055f6a  call    WPP_SF_s
0x180055f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f76  mov     rax, [rbp+50h+var_80]
0x180055f7a  xor     r9d, r9d
0x180055f7d  mov     ebx, 80004003h
0x180055f82  test    rdi, rdi
0x180055f85  jz      loc_1800569DE
0x180055f8b  test    rax, rax
0x180055f8e  jz      loc_1800569DE
0x180055f94  lea     r14, [rdi+rsi]
0x180055f98  mov     r10d, 8004100Ch
0x180055f9e  mov     ebx, r10d
0x180055fa1  cmp     rdi, r14
0x180055fa4  jnb     loc_1800569DE
0x180055faa  xorps   xmm0, xmm0
0x180055fad  mov     [rbp+50h+var_B8], r9
0x180055fb1  lea     r8, [rdi+8]
0x180055fb5  mov     [rbp+50h+var_B0], r9
0x180055fb9  mov     [rbp+50h+var_90], r9
0x180055fbd  xorps   xmm1, xmm1
0x180055fc0  mov     [rax], r9
0x180055fc3  movups  xmmword ptr [rbp+50h+var_58.dwLastUpdatingReplicaKey], xmm0
0x180055fc7  movups  xmmword ptr [rbp+50h+var_A0.dwLastUpdatingReplicaKey], xmm1
0x180055fcb  movups  xmmword ptr [rbp+50h+var_68.dwLastUpdatingReplicaKey], xmm0
0x180055fcf  cmp     r8, rdi
0x180055fd2  jb      loc_1800569C5
0x180055fd8  cmp     r8, r14
0x180055fdb  ja      loc_1800569C5
0x180055fe1  movzx   eax, byte ptr [rdi+1]
0x180055fe5  movzx   edx, byte ptr [rdi]
0x180055fe8  movzx   ecx, byte ptr [rdi+4]
0x180055fec  shl     rdx, 8
0x180055ff0  or      rdx, rax
0x180055ff3  shl     rcx, 8
0x180055ff7  movzx   eax, byte ptr [rdi+2]
0x180055ffb  shl     rdx, 8
0x180055fff  or      rdx, rax
0x180056002  mov     [rbp+50h+var_D0], r8
0x180056006  movzx   eax, byte ptr [rdi+3]
0x18005600a  shl     rdx, 8
0x18005600e  or      rdx, rax
0x180056011  movzx   eax, byte ptr [rdi+5]
0x180056015  or      rcx, rax
0x180056018  shl     rdx, 20h
0x18005601c  movzx   eax, byte ptr [rdi+6]
0x180056020  shl     rcx, 8
0x180056024  or      rcx, rax
0x180056027  movzx   eax, byte ptr [rdi+7]
0x18005602b  shl     rcx, 8
0x18005602f  or      rax, rcx
0x180056032  add     rax, rdx
0x180056035  mov     [rbp+50h+var_88], rax
0x180056039  add     rax, 0FFFFFFFFFFFFFFFBh
0x18005603d  test    rax, 0FFFFFFFFFFFFFFFDh
0x180056043  jnz     loc_1800569C5
0x180056049  mov     esi, r9d
0x18005604c  mov     dword ptr [rbp+50h+var_C8], r9d
0x180056050  mov     edi, r9d
0x180056053  lea     rdx, [rbp+50h+var_D0]; unsigned __int8 **
0x180056057  mov     r13d, r9d
0x18005605a  mov     r12d, r9d
0x18005605d  lea     r9, [rbp+50h+var_B8]; unsigned __int8 **
0x180056061  mov     r8, r14; unsigned __int8 *
0x180056064  mov     rcx, r15; this
0x180056067  call    ?DeserializeId@IdParameterPair@@QEAAJPEAPEBEPEBEPEAPEAEH@Z; IdParameterPair::DeserializeId(uchar const * *,uchar const *,uchar * *,int)
0x18005606c  mov     ebx, eax
0x18005606e  lea     eax, [r12+1]
0x180056073  test    ebx, ebx
0x180056075  js      loc_1800564CC
0x18005607b  mov     rdx, [rbp+50h+var_D0]
0x18005607f  lea     r8, [rdx+4]
0x180056083  cmp     r8, rdx
0x180056086  jb      loc_1800562DB
0x18005608c  cmp     r8, r14
0x18005608f  ja      loc_1800562DB
0x180056095  movzx   eax, byte ptr [rdx+1]
0x180056099  movzx   ecx, byte ptr [rdx]
0x18005609c  shl     ecx, 8
0x18005609f  or      ecx, eax
0x1800560a1  movzx   eax, byte ptr [rdx+2]
0x1800560a5  shl     ecx, 8
0x1800560a8  or      ecx, eax
0x1800560aa  movzx   eax, byte ptr [rdx+3]
0x1800560ae  shl     ecx, 8
0x1800560b1  or      ecx, eax
0x1800560b3  lea     rax, [r8+8]
0x1800560b7  mov     [rbp+50h+var_58.dwLastUpdatingReplicaKey], ecx
0x1800560ba  cmp     rax, r8
0x1800560bd  jb      loc_1800562DB
0x1800560c3  cmp     rax, r14
0x1800560c6  ja      loc_1800562DB
0x1800560cc  movzx   eax, byte ptr [r8]
0x1800560d0  movzx   edx, byte ptr [r8+1]
0x1800560d5  movzx   ecx, byte ptr [r8+5]
0x1800560da  shl     rax, 8
0x1800560de  or      rdx, rax
0x1800560e1  movzx   eax, byte ptr [r8+2]
0x1800560e6  shl     rdx, 8
0x1800560ea  or      rdx, rax
0x1800560ed  movzx   eax, byte ptr [r8+3]
0x1800560f2  shl     rdx, 8
0x1800560f6  or      rdx, rax
0x1800560f9  movzx   eax, byte ptr [r8+4]
0x1800560fe  shl     rax, 8
0x180056102  or      rcx, rax
0x180056105  shl     rdx, 20h
0x180056109  movzx   eax, byte ptr [r8+6]
0x18005610e  shl     rcx, 8
0x180056112  or      rcx, rax
0x180056115  movzx   eax, byte ptr [r8+7]
0x18005611a  add     r8, 8
0x18005611e  shl     rcx, 8
0x180056122  or      rcx, rax
0x180056125  add     rdx, rcx
0x180056128  mov     [rbp+50h+var_58.ullTickCount], rdx
0x18005612c  lea     rax, [r8+4]
0x180056130  cmp     rax, r8
0x180056133  jb      loc_1800562DB
0x180056139  cmp     rax, r14
0x18005613c  ja      loc_1800562DB
0x180056142  movzx   eax, byte ptr [r8+1]
0x180056147  movzx   ecx, byte ptr [r8]
0x18005614b  shl     ecx, 8
0x18005614e  or      ecx, eax
0x180056150  movzx   eax, byte ptr [r8+2]
0x180056155  shl     ecx, 8
0x180056158  or      ecx, eax
0x18005615a  movzx   eax, byte ptr [r8+3]
0x18005615f  add     r8, 4
0x180056163  shl     ecx, 8
0x180056166  or      ecx, eax
0x180056168  mov     [rbp+50h+var_A0.dwLastUpdatingReplicaKey], ecx
0x18005616b  lea     rax, [r8+8]
0x18005616f  cmp     rax, r8
0x180056172  jb      loc_1800562DB
0x180056178  cmp     rax, r14
0x18005617b  ja      loc_1800562DB
0x180056181  movzx   eax, byte ptr [r8+1]
0x180056186  movzx   edx, byte ptr [r8]
0x18005618a  movzx   ecx, byte ptr [r8+4]
0x18005618f  shl     rdx, 8
0x180056193  or      rdx, rax
0x180056196  shl     rcx, 8
0x18005619a  movzx   eax, byte ptr [r8+2]
0x18005619f  shl     rdx, 8
0x1800561a3  or      rdx, rax
0x1800561a6  movzx   eax, byte ptr [r8+3]
0x1800561ab  shl     rdx, 8
0x1800561af  or      rdx, rax
0x1800561b2  movzx   eax, byte ptr [r8+5]
0x1800561b7  or      rcx, rax
0x1800561ba  shl     rdx, 20h
0x1800561be  movzx   eax, byte ptr [r8+6]
0x1800561c3  shl     rcx, 8
0x1800561c7  or      rcx, rax
0x1800561ca  movzx   eax, byte ptr [r8+7]
0x1800561cf  add     r8, 8
0x1800561d3  shl     rcx, 8
0x1800561d7  or      rcx, rax
0x1800561da  add     rdx, rcx
0x1800561dd  mov     [rbp+50h+var_A0.ullTickCount], rdx
0x1800561e1  lea     rax, [r8+4]
0x1800561e5  cmp     rax, r8
0x1800561e8  jb      loc_1800562DB
0x1800561ee  cmp     rax, r14
0x1800561f1  ja      loc_1800562DB
0x1800561f7  movzx   eax, byte ptr [r8+1]
0x1800561fc  movzx   ecx, byte ptr [r8]
0x180056200  shl     ecx, 8
0x180056203  or      ecx, eax
0x180056205  movzx   eax, byte ptr [r8+2]
0x18005620a  shl     ecx, 8
0x18005620d  or      ecx, eax
0x18005620f  movzx   eax, byte ptr [r8+3]
0x180056214  add     r8, 4
0x180056218  shl     ecx, 8
0x18005621b  or      ecx, eax
0x18005621d  mov     [rbp+50h+var_68.dwLastUpdatingReplicaKey], ecx
0x180056220  lea     rax, [r8+8]
0x180056224  cmp     rax, r8
0x180056227  jb      loc_1800562DB
0x18005622d  cmp     rax, r14
0x180056230  ja      loc_1800562DB
0x180056236  movzx   eax, byte ptr [r8+1]
0x18005623b  lea     r9, [rbp+50h+var_B0]; unsigned __int8 **
0x18005623f  movzx   edx, byte ptr [r8]
0x180056243  movzx   ecx, byte ptr [r8+5]
0x180056248  shl     rdx, 8
0x18005624c  or      rdx, rax
0x18005624f  movzx   eax, byte ptr [r8+2]
0x180056254  shl     rdx, 8
0x180056258  or      rdx, rax
0x18005625b  movzx   eax, byte ptr [r8+3]
0x180056260  shl     rdx, 8
0x180056264  or      rdx, rax
0x180056267  movzx   eax, byte ptr [r8+4]
0x18005626c  shl     rax, 8
0x180056270  or      rcx, rax
0x180056273  shl     rdx, 20h
0x180056277  movzx   eax, byte ptr [r8+6]
0x18005627c  shl     rcx, 8
0x180056280  or      rcx, rax
0x180056283  movzx   eax, byte ptr [r8+7]
0x180056288  shl     rcx, 8
0x18005628c  or      rcx, rax
0x18005628f  lea     rax, [r8+8]
0x180056293  add     rdx, rcx
0x180056296  mov     [rbp+50h+var_D0], rax
0x18005629a  mov     [rbp+50h+var_68.ullTickCount], rdx
0x18005629e  lea     rcx, [r15+10h]; this
0x1800562a2  lea     rdx, [rbp+50h+var_D0]; unsigned __int8 **
0x1800562a6  mov     r8, r14; unsigned __int8 *
0x1800562a9  call    ?DeserializeId@IdParameterPair@@QEAAJPEAPEBEPEBEPEAPEAEH@Z; IdParameterPair::DeserializeId(uchar const * *,uchar const *,uchar * *,int)
0x1800562ae  mov     ebx, eax
0x1800562b0  test    eax, eax
0x1800562b2  js      loc_1800564C7
0x1800562b8  cmp     [rbp+50h+var_88], 7
0x1800562bd  jb      short loc_180056325
0x1800562bf  mov     rax, [rbp+50h+var_D0]
0x1800562c3  lea     r15, [rax+1]
0x1800562c7  cmp     r15, rax
0x1800562ca  jb      short loc_1800562DB
0x1800562cc  cmp     r15, r14
0x1800562cf  ja      short loc_1800562DB
0x1800562d1  cmp     byte ptr [rax], 1
0x1800562d4  jz      short loc_1800562E5
0x1800562d6  cmp     [rax], sil
0x1800562d9  jz      short loc_1800562E5
0x1800562db  mov     ebx, 8004100Ch
0x1800562e0  jmp     loc_1800569BE
0x1800562e5  mov     [rbp+50h+var_D0], r15
0x1800562e9  cmp     [rax], sil
0x1800562ec  jz      short loc_180056314
0x1800562ee  mov     rcx, [rbp+50h+var_C0]
0x1800562f2  lea     r9, [rbp+50h+var_90]; unsigned __int8 **
0x1800562f6  add     rcx, 10h; this
0x1800562fa  lea     rdx, [rbp+50h+var_D0]; unsigned __int8 **
0x1800562fe  mov     r8, r14; unsigned __int8 *
0x180056301  call    ?DeserializeId@IdParameterPair@@QEAAJPEAPEBEPEBEPEAPEAEH@Z; IdParameterPair::DeserializeId(uchar const * *,uchar const *,uchar * *,int)
0x180056306  mov     r15, [rbp+50h+var_D0]
0x18005630a  mov     ebx, eax
0x18005630c  test    eax, eax
0x18005630e  js      loc_18005648B
0x180056314  mov     rax, [rbp+50h+var_78]
0x180056318  cmp     dword ptr [rax], 5
0x18005631b  jge     short loc_180056329
0x18005631d  mov     dword ptr [rax], 5
0x180056323  jmp     short loc_180056329
0x180056325  mov     r15, [rbp+50h+var_D0]
0x180056329  lea     r8, [r15+4]
0x18005632d  cmp     r8, r15
0x180056330  jb      short loc_1800562DB
0x180056332  cmp     r8, r14
0x180056335  ja      short loc_1800562DB
0x180056337  test    ebx, ebx
0x180056339  js      loc_18005648B
0x18005633f  movzx   eax, byte ptr [r15+1]
0x180056344  mov     r9b, 2
0x180056347  movzx   edi, byte ptr [r15]
0x18005634b  mov     r10d, 1
0x180056351  shl     edi, 8
0x180056354  or      edi, eax
0x180056356  movzx   eax, byte ptr [r15+2]
0x18005635b  shl     edi, 8
  ... truncated ...
```
