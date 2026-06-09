# Kerb3961::RC4_4757::CommonWrapEncrypted(Kerb3961::MutableBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x180006270`
- end: `0x180006aaf`
- name: `?CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMutableBinary@2@AEBUReadOnlyBinary@2@_KI1_N3PEA_K@Z`
- size: `2111`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x1800047e4`
- `0x180006270`
- `0x180006ee0`
- `0x18000712c`
- `0x180008500`
- `0x1800085cc`
- `0x18000901c`
- `0x180009190`
- `0x18001d360`
- `0x18001e010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800063b8`
- `bcrypt!BCryptGenRandom` at `0x1800063b8`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonWrapEncrypted(
        _QWORD *a1,
        __int64 a2,
        void **a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        char a8,
        int a9,
        _QWORD *a10)
{
  int v12; // ebx
  const unsigned __int16 *v13; // rdx
  int v14; // r8d
  int v15; // r13d
  void *v16; // rcx
  _QWORD *v17; // rsi
  NTSTATUS v18; // eax
  int v19; // r8d
  NTSTATUS v20; // ebx
  int v21; // r8d
  int v22; // ebx
  int v23; // r8d
  int v24; // ebx
  int v25; // r8d
  int v26; // ebx
  void *v27; // rcx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  _BYTE *i; // rbx
  int v31; // r8d
  unsigned int v32; // r14d
  char *v33; // rcx
  __int64 v34; // r14
  void *v35; // rcx
  int v36; // eax
  __int64 v37; // rax
  __int64 *v38; // r9
  __int64 v39; // r14
  void *v40; // rcx
  int v41; // eax
  int v42; // r8d
  int v43; // r14d
  __int64 *v44; // r9
  int v45; // r8d
  int v46; // r14d
  char *v47; // rcx
  void *v48; // rcx
  void **v49; // r14
  int v50; // r8d
  __int64 v51; // r14
  void *v52; // rcx
  int v53; // eax
  int v54; // r14d
  __int64 v55; // r8
  int v56; // r8d
  int v57; // r14d
  char *v58; // rcx
  void *v59; // rcx
  __int64 v60; // r14
  void *v61; // rcx
  int v62; // eax
  void *v63; // rcx
  __int64 v64; // rax
  char v66; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v67; // [rsp+28h] [rbp-D8h] BYREF
  void *v68; // [rsp+30h] [rbp-D0h]
  char *v69; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v70; // [rsp+40h] [rbp-C0h] BYREF
  void *v71; // [rsp+48h] [rbp-B8h]
  char *v72; // [rsp+50h] [rbp-B0h]
  __int64 v73; // [rsp+60h] [rbp-A0h] BYREF
  void *v74; // [rsp+68h] [rbp-98h]
  _BOOL8 v75; // [rsp+70h] [rbp-90h]
  __int64 v76; // [rsp+80h] [rbp-80h] BYREF
  void *v77; // [rsp+88h] [rbp-78h]
  char *v78; // [rsp+90h] [rbp-70h]
  __int64 v79; // [rsp+98h] [rbp-68h] BYREF
  void *v80; // [rsp+A0h] [rbp-60h]
  char *v81; // [rsp+A8h] [rbp-58h]
  char v82[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v83; // [rsp+B8h] [rbp-48h]
  char *v84; // [rsp+C0h] [rbp-40h]
  __int64 v85; // [rsp+C8h] [rbp-38h] BYREF
  char *v86; // [rsp+D0h] [rbp-30h]
  __int64 v87; // [rsp+D8h] [rbp-28h] BYREF
  void *v88; // [rsp+E0h] [rbp-20h]
  char *v89; // [rsp+E8h] [rbp-18h]
  void **v90; // [rsp+F0h] [rbp-10h]
  __int64 v91; // [rsp+F8h] [rbp-8h]
  _QWORD v92[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v93; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v94; // [rsp+118h] [rbp+18h]
  char *v95; // [rsp+120h] [rbp+20h]
  _QWORD v96[2]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v97[2]; // [rsp+138h] [rbp+38h] BYREF
  size_t Size[15]; // [rsp+148h] [rbp+48h] BYREF

  v85 = a4;
  v90 = a3;
  v91 = a7;
  v12 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v12 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v13);
  if ( a6 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"QOP == 0", (const char *)v13);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893046;
    return a2;
  }
  Kerb3961::MakeBuffer(&v93);
  v15 = (int)v95;
  if ( (int)v95 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"headerBuffer",
      (const char *)(unsigned int)v95,
      v14);
    v16 = v94;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v15;
    goto LABEL_108;
  }
  if ( a10 )
    *a10 = 1;
  v17 = v94;
  v66 = 1;
  v94[2] = 0;
  v17[3] = 0;
  v96[1] = v17 + 2;
  *(_DWORD *)v17 = 1114370;
  *((_DWORD *)v17 + 2) = _byteswap_ulong(a5);
  v97[1] = v17 + 1;
  *((_DWORD *)v17 + 3) = (a8 != 0) - 1;
  *((_DWORD *)v17 + 1) = -65520;
  v97[0] = 8;
  v96[0] = 8;
  v92[0] = 8;
  v92[1] = v17 + 3;
  v18 = BCryptGenRandom(0, (PUCHAR)v17 + 24, 8u, 2u);
  v20 = v18;
  if ( v18 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"RandomFill(confounderBuffer)",
      (const char *)(unsigned int)v18,
      v19);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v20;
    goto LABEL_10;
  }
  Kerb3961::RC4_4757::HmacData(
    a1,
    v82,
    a7,
    &__S25__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B);
  v22 = (int)v84;
  if ( (int)v84 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v84, v21);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v22;
    goto LABEL_13;
  }
  v73 = 8;
  v74 = v17;
  Kerb3961::Concatenate(
    &v67,
    &__S26__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B,
    &v73,
    v92);
  v24 = (int)v69;
  if ( (int)v69 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"signBuffer",
      (const char *)(unsigned int)v69,
      v23);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v24;
    goto LABEL_19;
  }
  Kerb3961::CopyBuffer(&v70, a7);
  v26 = (int)v72;
  if ( (int)v72 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Klocal", (const char *)(unsigned int)v72, v25);
    v27 = v71;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v26;
    if ( !v27 )
      goto LABEL_19;
    goto LABEL_23;
  }
  v28 = v70;
  v29 = 0;
  for ( i = v71; v29 < v28; ++v29 )
    i[v29] ^= 0xF0u;
  Kerb3961::RC4_4757::HmacData(
    a1,
    &v76,
    &v70,
    &__S28__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B);
  v32 = (unsigned int)v78;
  if ( (int)v78 < 0 )
    goto LABEL_27;
  v73 = 4;
  v74 = v17 + 1;
  v34 = Kerb3961::RC4_4757::HmacData(a1, &v70, &v76, &v73);
  if ( v77 )
    operator delete(v77, 0);
  v76 = *(_QWORD *)v34;
  v35 = *(void **)(v34 + 8);
  *(_QWORD *)v34 = 0;
  v77 = v35;
  v36 = *(_DWORD *)(v34 + 16);
  *(_QWORD *)(v34 + 8) = 0;
  LODWORD(v78) = v36;
  *(_DWORD *)(v34 + 16) = -1073741823;
  if ( v71 )
    operator delete(v71, 0);
  v32 = (unsigned int)v78;
  if ( (int)v78 < 0 )
  {
LABEL_27:
    v33 = "Kcrypt";
  }
  else
  {
    v37 = v85;
    if ( !*(_QWORD *)(v85 + 8) )
      v37 = (__int64)v90;
    if ( a10 )
    {
      v85 = 1;
      v86 = &v66;
    }
    else
    {
      v73 = 0;
      v74 = 0;
    }
    v38 = &v73;
    if ( a10 )
      v38 = &v85;
    v39 = Kerb3961::Concatenate(&v70, &v67, v37, v38);
    if ( v68 )
      operator delete(v68, 0);
    v67 = *(_QWORD *)v39;
    v40 = *(void **)(v39 + 8);
    *(_QWORD *)v39 = 0;
    v68 = v40;
    v41 = *(_DWORD *)(v39 + 16);
    *(_QWORD *)(v39 + 8) = 0;
    LODWORD(v69) = v41;
    *(_DWORD *)(v39 + 16) = -1073741823;
    if ( v71 )
      operator delete(v71, 0);
    v32 = (unsigned int)v69;
    if ( (int)v69 >= 0 )
    {
      Kerb3961::RC4_4757::HashData(a1, &v79, &v67);
      v43 = (int)v81;
      if ( (int)v81 >= 0 )
      {
        if ( a10 )
        {
          v85 = 1;
          v86 = &v66;
        }
        else
        {
          v73 = 0;
          v74 = 0;
        }
        v44 = &v73;
        if ( a10 )
          v44 = &v85;
        Kerb3961::Concatenate(&v70, v92, v90, v44);
        v46 = (int)v72;
        if ( (int)v72 >= 0 )
        {
          v46 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, &v85, &v76, &v70);
          if ( v46 >= 0 )
          {
            v49 = v90;
            v73 = 8;
            v74 = *v90;
            v75 = a10 != 0;
            Kerb3961::Split<3>(Size, &v70, &v73);
            memcpy_0(v17 + 3, (const void *)Size[1], Size[0]);
            memcpy_0(v49[1], (const void *)Size[3], Size[2]);
            *((_BYTE *)v17 + 32) = *(_BYTE *)Size[5];
            v51 = Kerb3961::RC4_4757::HmacData(a1, &v73, v82, &v79);
            if ( v80 )
              operator delete(v80, 0);
            v79 = *(_QWORD *)v51;
            v52 = *(void **)(v51 + 8);
            *(_QWORD *)v51 = 0;
            v80 = v52;
            v53 = *(_DWORD *)(v51 + 16);
            *(_QWORD *)(v51 + 8) = 0;
            LODWORD(v81) = v53;
            *(_DWORD *)(v51 + 16) = -1073741823;
            if ( v74 )
              operator delete(v74, 0);
            v54 = (int)v81;
            if ( (int)v81 >= 0 )
            {
              v55 = v91;
              v17[2] = *(_QWORD *)v80;
              Kerb3961::RC4_4757::HmacData(
                a1,
                &v87,
                v55,
                &__S28__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B);
              v57 = (int)v89;
              if ( (int)v89 < 0 )
                goto LABEL_85;
              v60 = Kerb3961::RC4_4757::HmacData(a1, &v73, &v87, v96);
              if ( v88 )
                operator delete(v88, 0);
              v87 = *(_QWORD *)v60;
              v61 = *(void **)(v60 + 8);
              *(_QWORD *)v60 = 0;
              v88 = v61;
              v62 = *(_DWORD *)(v60 + 16);
              *(_QWORD *)(v60 + 8) = 0;
              LODWORD(v89) = v62;
              *(_DWORD *)(v60 + 16) = -1073741823;
              if ( v74 )
                operator delete(v74, 0);
              v57 = (int)v89;
              if ( (int)v89 < 0 )
              {
LABEL_85:
                v58 = "Kseq";
              }
              else
              {
                v57 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, &v85, &v87, v97);
                if ( v57 >= 0 )
                {
                  v63 = v88;
                  v64 = v93;
                  *(_DWORD *)(a2 + 16) = v15;
                  *(_QWORD *)a2 = v64;
                  *(_QWORD *)(a2 + 8) = v17;
                  if ( v63 )
                    operator delete(v63, 0);
                  if ( v71 )
                    operator delete(v71, 0);
                  if ( v80 )
                    operator delete(v80, 0);
                  if ( v77 )
                    operator delete(v77, 0);
                  if ( i )
                    operator delete(i, 0);
                  if ( v68 )
                    operator delete(v68, 0);
                  v16 = v83;
LABEL_108:
                  if ( !v16 )
                    return a2;
LABEL_109:
                  operator delete(v16, 0);
                  return a2;
                }
                v58 = "RC4Data(Kseq, sequenceBuffer)";
              }
              Kerb3961::Logging::Verify::StatusFailed(
                (Kerb3961::Logging::Verify *)v58,
                (const char *)(unsigned int)v57,
                v56);
              v59 = v88;
              *(_QWORD *)a2 = 0;
              *(_QWORD *)(a2 + 8) = 0;
              *(_DWORD *)(a2 + 16) = v57;
              if ( v59 )
                operator delete(v59, 0);
            }
            else
            {
              Kerb3961::Logging::Verify::StatusFailed(
                (Kerb3961::Logging::Verify *)"Sgn_Cksum",
                (const char *)(unsigned int)v81,
                v50);
              *(_QWORD *)a2 = 0;
              *(_QWORD *)(a2 + 8) = 0;
              *(_DWORD *)(a2 + 16) = v54;
            }
            if ( v71 )
              operator delete(v71, 0);
            if ( v80 )
              operator delete(v80, 0);
            if ( v77 )
              operator delete(v77, 0);
            if ( i )
              operator delete(i, 0);
            if ( v68 )
              operator delete(v68, 0);
            if ( v83 )
              operator delete(v83, 0);
LABEL_10:
            v16 = v17;
            goto LABEL_109;
          }
          v47 = "RC4Data(Kcrypt, tmp)";
        }
        else
        {
          v47 = "tmp";
        }
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v47, (const char *)(unsigned int)v46, v45);
        v48 = v71;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v46;
        if ( v48 )
          operator delete(v48, 0);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"Sgn_Cksum",
          (const char *)(unsigned int)v81,
          v42);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v43;
      }
      if ( v80 )
        operator delete(v80, 0);
      goto LABEL_29;
    }
    v33 = "signBuffer";
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v33, (const char *)v32, v31);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v32;
LABEL_29:
  if ( v77 )
    operator delete(v77, 0);
  if ( !i )
    goto LABEL_19;
  v27 = i;
LABEL_23:
  operator delete(v27, 0);
LABEL_19:
  if ( v68 )
    operator delete(v68, 0);
LABEL_13:
  if ( v83 )
    operator delete(v83, 0);
  if ( v17 )
    goto LABEL_10;
  return a2;
}

```

## disassembly

```asm
0x180006270  push    rbp
0x180006272  push    rbx
0x180006273  push    rsi
0x180006274  push    rdi
0x180006275  push    r12
0x180006277  push    r13
0x180006279  push    r14
0x18000627b  push    r15
0x18000627d  lea     rbp, [rsp-88h]
0x180006285  sub     rsp, 188h
0x18000628c  mov     r14, [rbp+0C0h+arg_30]
0x180006293  mov     r15, rcx
0x180006296  mov     r12, [rbp+0C0h+arg_48]
0x18000629d  add     rcx, 8
0x1800062a1  mov     [rbp+0C0h+var_F8], r9
0x1800062a5  mov     rdi, rdx
0x1800062a8  mov     [rbp+0C0h+var_D0], r8
0x1800062ac  mov     [rbp+0C0h+var_C8], r14
0x1800062b0  mov     rax, [rcx]
0x1800062b3  mov     rax, [rax+68h]
0x1800062b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062bc  mov     ebx, eax
0x1800062be  mov     rcx, r15
0x1800062c1  mov     rax, [r15]
0x1800062c4  mov     rax, [rax+0E0h]
0x1800062cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d0  cmp     ebx, eax
0x1800062d2  jnz     loc_180006AA2
0x1800062d8  xor     ebx, ebx
0x1800062da  cmp     [rbp+0C0h+arg_28], ebx
0x1800062e0  jz      short loc_180006301
0x1800062e2  lea     rcx, aQop0; "QOP == 0"
0x1800062e9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800062ee  mov     [rdi], rbx
0x1800062f1  mov     [rdi+8], rbx
0x1800062f5  mov     dword ptr [rdi+10h], 8009030Ah
0x1800062fc  jmp     loc_180006A8B
0x180006301  mov     rax, r12
0x180006304  lea     rcx, [rbp+0C0h+var_B0]
0x180006308  neg     rax
0x18000630b  sbb     rdx, rdx
0x18000630e  neg     rdx
0x180006311  add     rdx, 20h ; ' '
0x180006315  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000631a  mov     r13, [rbp+0C0h+var_A0]
0x18000631e  test    r13d, r13d
0x180006321  jns     short loc_180006346
0x180006323  mov     edx, r13d; char *
0x180006326  lea     rcx, aHeaderbuffer; "headerBuffer"
0x18000632d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006332  mov     rcx, [rbp+0C0h+var_A8]
0x180006336  mov     [rdi], rbx
0x180006339  mov     [rdi+8], rbx
0x18000633d  mov     [rdi+10h], r13d
0x180006341  jmp     loc_180006A7F
0x180006346  test    r12, r12
0x180006349  jz      short loc_180006353
0x18000634b  mov     qword ptr [r12], 1
0x180006353  mov     rsi, [rbp+0C0h+var_A8]
0x180006357  mov     r8d, 8; cbBuffer
0x18000635d  neg     [rbp+0C0h+arg_38]
0x180006363  mov     [rsp+1C0h+var_1A0], 1
0x180006368  mov     [rsi+10h], rbx
0x18000636c  lea     rax, [rsi+10h]
0x180006370  mov     [rsi+18h], rbx
0x180006374  lea     rcx, [rsi+8]
0x180006378  mov     [rbp+0C0h+var_90], rax
0x18000637c  lea     rdx, [rsi+18h]; pbBuffer
0x180006380  mov     eax, [rbp+0C0h+arg_20]
0x180006386  lea     r9d, [r8-6]; dwFlags
0x18000638a  bswap   eax
0x18000638c  mov     dword ptr [rsi], 110102h
0x180006392  mov     [rcx], eax
0x180006394  sbb     eax, eax
0x180006396  not     eax
0x180006398  mov     [rbp+0C0h+var_80], rcx
0x18000639c  xor     ecx, ecx; hAlgorithm
0x18000639e  mov     [rsi+0Ch], eax
0x1800063a1  mov     dword ptr [rsi+4], 0FFFF0010h
0x1800063a8  mov     [rbp+0C0h+var_88], r8
0x1800063ac  mov     [rbp+0C0h+var_98], r8
0x1800063b0  mov     [rbp+0C0h+var_C0], r8
0x1800063b4  mov     [rbp+0C0h+var_B8], rdx
0x1800063b8  call    cs:__imp_BCryptGenRandom
0x1800063be  mov     ebx, eax
0x1800063c0  test    eax, eax
0x1800063c2  jns     short loc_1800063EC
0x1800063c4  mov     edx, eax; char *
0x1800063c6  lea     rcx, aRandomfillConf; "RandomFill(confounderBuffer)"
0x1800063cd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800063d2  mov     qword ptr [rdi], 0
0x1800063d9  mov     qword ptr [rdi+8], 0
0x1800063e1  mov     [rdi+10h], ebx
0x1800063e4  mov     rcx, rsi
0x1800063e7  jmp     loc_180006A84
0x1800063ec  lea     r9, ?$S25@?1??CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUMutableBinary@3@AEBUReadOnlyBinary@3@_KI1_N3PEA_K@Z@4U63@B
0x1800063f3  mov     r8, r14
0x1800063f6  lea     rdx, [rbp+0C0h+var_110]
0x1800063fa  mov     rcx, r15
0x1800063fd  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006402  mov     ebx, dword ptr [rbp+0C0h+var_100]
0x180006405  test    ebx, ebx
0x180006407  jns     short loc_180006444
0x180006409  mov     edx, ebx; char *
0x18000640b  lea     rcx, aKsign; "Ksign"
0x180006412  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006417  mov     qword ptr [rdi], 0
0x18000641e  mov     qword ptr [rdi+8], 0
0x180006426  mov     [rdi+10h], ebx
0x180006429  mov     rcx, [rbp+0C0h+var_108]; void *
0x18000642d  test    rcx, rcx
0x180006430  jz      short loc_180006439
0x180006432  xor     edx, edx; struct std::nothrow_t *
0x180006434  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006439  test    rsi, rsi
0x18000643c  jz      loc_180006A8B
0x180006442  jmp     short loc_1800063E4
0x180006444  lea     r9, [rbp+0C0h+var_C0]
0x180006448  mov     [rsp+1C0h+var_160], 8
0x180006451  lea     r8, [rsp+1C0h+var_160]
0x180006456  mov     [rsp+1C0h+var_158], rsi
0x18000645b  lea     rdx, ?$S26@?1??CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUMutableBinary@3@AEBUReadOnlyBinary@3@_KI1_N3PEA_K@Z@4U63@B
0x180006462  lea     rcx, [rsp+1C0h+var_198]
0x180006467  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000646c  mov     ebx, dword ptr [rsp+1C0h+var_188]
0x180006470  test    ebx, ebx
0x180006472  jns     short loc_1800064A7
0x180006474  mov     edx, ebx; char *
0x180006476  lea     rcx, aSignbuffer; "signBuffer"
0x18000647d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006482  mov     qword ptr [rdi], 0
0x180006489  mov     qword ptr [rdi+8], 0
0x180006491  mov     [rdi+10h], ebx
0x180006494  mov     rcx, [rsp+1C0h+var_190]; void *
0x180006499  test    rcx, rcx
0x18000649c  jz      short loc_180006429
0x18000649e  xor     edx, edx; struct std::nothrow_t *
0x1800064a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800064a5  jmp     short loc_180006429
0x1800064a7  mov     rdx, r14
0x1800064aa  lea     rcx, [rsp+1C0h+var_180]
0x1800064af  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x1800064b4  mov     ebx, dword ptr [rsp+1C0h+var_170]
0x1800064b8  test    ebx, ebx
0x1800064ba  jns     short loc_1800064EF
0x1800064bc  mov     edx, ebx; char *
0x1800064be  lea     rcx, aKlocal; "Klocal"
0x1800064c5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800064ca  mov     rcx, [rsp+1C0h+var_178]; void *
0x1800064cf  mov     qword ptr [rdi], 0
0x1800064d6  mov     qword ptr [rdi+8], 0
0x1800064de  mov     [rdi+10h], ebx
0x1800064e1  test    rcx, rcx
0x1800064e4  jz      short loc_180006494
0x1800064e6  xor     edx, edx; struct std::nothrow_t *
0x1800064e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800064ed  jmp     short loc_180006494
0x1800064ef  mov     rcx, [rsp+1C0h+var_180]
0x1800064f4  xor     eax, eax
0x1800064f6  mov     rbx, [rsp+1C0h+var_178]
0x1800064fb  test    rcx, rcx
0x1800064fe  jz      short loc_18000650C
0x180006500  xor     byte ptr [rbx+rax], 0F0h
0x180006504  inc     rax
0x180006507  cmp     rax, rcx
0x18000650a  jb      short loc_180006500
0x18000650c  lea     r9, ?$S28@?1??CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUMutableBinary@3@AEBUReadOnlyBinary@3@_KI1_N3PEA_K@Z@4U63@B
0x180006513  mov     rcx, r15
0x180006516  lea     r8, [rsp+1C0h+var_180]
0x18000651b  lea     rdx, [rbp+0C0h+var_140]
0x18000651f  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006524  mov     r14d, dword ptr [rbp+0C0h+var_130]
0x180006528  test    r14d, r14d
0x18000652b  jns     short loc_180006570
0x18000652d  lea     rcx, aKcrypt; "Kcrypt"
0x180006534  mov     edx, r14d; char *
0x180006537  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000653c  mov     qword ptr [rdi], 0
0x180006543  mov     qword ptr [rdi+8], 0
0x18000654b  mov     [rdi+10h], r14d
0x18000654f  mov     rcx, [rbp+0C0h+var_138]; void *
0x180006553  test    rcx, rcx
0x180006556  jz      short loc_18000655F
0x180006558  xor     edx, edx; struct std::nothrow_t *
0x18000655a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000655f  test    rbx, rbx
0x180006562  jz      loc_180006494
0x180006568  mov     rcx, rbx
0x18000656b  jmp     loc_1800064E6
0x180006570  lea     rax, [rsi+8]
0x180006574  mov     [rsp+1C0h+var_160], 4
0x18000657d  lea     r9, [rsp+1C0h+var_160]
0x180006582  mov     [rsp+1C0h+var_158], rax
0x180006587  lea     r8, [rbp+0C0h+var_140]
0x18000658b  mov     rcx, r15
0x18000658e  lea     rdx, [rsp+1C0h+var_180]
0x180006593  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006598  mov     rcx, [rbp+0C0h+var_138]; void *
0x18000659c  mov     r14, rax
0x18000659f  test    rcx, rcx
0x1800065a2  jz      short loc_1800065AB
0x1800065a4  xor     edx, edx; struct std::nothrow_t *
0x1800065a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800065ab  mov     rcx, [r14]
0x1800065ae  mov     [rbp+0C0h+var_140], rcx
0x1800065b2  mov     rcx, [r14+8]
0x1800065b6  mov     qword ptr [r14], 0
0x1800065bd  mov     [rbp+0C0h+var_138], rcx
0x1800065c1  mov     eax, [r14+10h]
0x1800065c5  mov     qword ptr [r14+8], 0
0x1800065cd  mov     dword ptr [rbp+0C0h+var_130], eax
0x1800065d0  mov     dword ptr [r14+10h], 0C0000001h
0x1800065d8  mov     rcx, [rsp+1C0h+var_178]; void *
0x1800065dd  test    rcx, rcx
0x1800065e0  jz      short loc_1800065E9
0x1800065e2  xor     edx, edx; struct std::nothrow_t *
0x1800065e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800065e9  mov     r14d, dword ptr [rbp+0C0h+var_130]
0x1800065ed  test    r14d, r14d
0x1800065f0  js      loc_18000652D
0x1800065f6  mov     rax, [rbp+0C0h+var_F8]
0x1800065fa  cmp     qword ptr [rax+8], 0
0x1800065ff  cmovz   rax, [rbp+0C0h+var_D0]
0x180006604  test    r12, r12
0x180006607  jz      short loc_18000661C
0x180006609  lea     rcx, [rsp+1C0h+var_1A0]
0x18000660e  mov     [rbp+0C0h+var_F8], 1
0x180006616  mov     [rbp+0C0h+var_F0], rcx
0x18000661a  jmp     short loc_18000662E
0x18000661c  mov     [rsp+1C0h+var_160], 0
0x180006625  mov     [rsp+1C0h+var_158], 0
0x18000662e  lea     rcx, [rbp+0C0h+var_F8]
0x180006632  test    r12, r12
0x180006635  lea     r9, [rsp+1C0h+var_160]
0x18000663a  mov     r8, rax
0x18000663d  cmovnz  r9, rcx
0x180006641  lea     rdx, [rsp+1C0h+var_198]
0x180006646  lea     rcx, [rsp+1C0h+var_180]
0x18000664b  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006650  mov     rcx, [rsp+1C0h+var_190]; void *
0x180006655  mov     r14, rax
0x180006658  test    rcx, rcx
0x18000665b  jz      short loc_180006664
0x18000665d  xor     edx, edx; struct std::nothrow_t *
0x18000665f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006664  mov     rcx, [r14]
0x180006667  mov     [rsp+1C0h+var_198], rcx
0x18000666c  mov     rcx, [r14+8]
0x180006670  mov     qword ptr [r14], 0
0x180006677  mov     [rsp+1C0h+var_190], rcx
0x18000667c  mov     eax, [r14+10h]
0x180006680  mov     qword ptr [r14+8], 0
0x180006688  mov     dword ptr [rsp+1C0h+var_188], eax
0x18000668c  mov     dword ptr [r14+10h], 0C0000001h
0x180006694  mov     rcx, [rsp+1C0h+var_178]; void *
0x180006699  test    rcx, rcx
0x18000669c  jz      short loc_1800066A5
0x18000669e  xor     edx, edx; struct std::nothrow_t *
0x1800066a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800066a5  mov     r14d, dword ptr [rsp+1C0h+var_188]
0x1800066aa  test    r14d, r14d
0x1800066ad  jns     short loc_1800066BB
0x1800066af  lea     rcx, aSignbuffer; "signBuffer"
0x1800066b6  jmp     loc_180006534
0x1800066bb  lea     r8, [rsp+1C0h+var_198]
0x1800066c0  mov     rcx, r15
0x1800066c3  lea     rdx, [rbp+0C0h+var_128]
0x1800066c7  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x1800066cc  mov     r14d, dword ptr [rbp+0C0h+var_118]
0x1800066d0  test    r14d, r14d
0x1800066d3  jns     short loc_180006710
0x1800066d5  mov     edx, r14d; char *
0x1800066d8  lea     rcx, aSgnCksum; "Sgn_Cksum"
0x1800066df  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800066e4  mov     qword ptr [rdi], 0
0x1800066eb  mov     qword ptr [rdi+8], 0
0x1800066f3  mov     [rdi+10h], r14d
0x1800066f7  mov     rcx, [rbp+0C0h+var_120]; void *
0x1800066fb  test    rcx, rcx
0x1800066fe  jz      loc_18000654F
0x180006704  xor     edx, edx; struct std::nothrow_t *
0x180006706  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000670b  jmp     loc_18000654F
0x180006710  test    r12, r12
0x180006713  jz      short loc_180006728
0x180006715  lea     rax, [rsp+1C0h+var_1A0]
0x18000671a  mov     [rbp+0C0h+var_F8], 1
0x180006722  mov     [rbp+0C0h+var_F0], rax
0x180006726  jmp     short loc_18000673A
0x180006728  mov     [rsp+1C0h+var_160], 0
0x180006731  mov     [rsp+1C0h+var_158], 0
0x18000673a  mov     r8, [rbp+0C0h+var_D0]
0x18000673e  lea     rax, [rbp+0C0h+var_F8]
0x180006742  test    r12, r12
0x180006745  lea     r9, [rsp+1C0h+var_160]
0x18000674a  lea     rdx, [rbp+0C0h+var_C0]
0x18000674e  cmovnz  r9, rax
0x180006752  lea     rcx, [rsp+1C0h+var_180]
0x180006757  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000675c  mov     r14d, dword ptr [rsp+1C0h+var_170]
  ... truncated ...
```
