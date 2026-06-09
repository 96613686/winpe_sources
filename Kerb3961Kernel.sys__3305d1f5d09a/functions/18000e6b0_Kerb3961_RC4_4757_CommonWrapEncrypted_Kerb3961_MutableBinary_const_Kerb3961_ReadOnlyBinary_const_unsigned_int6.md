# Kerb3961::RC4_4757::CommonWrapEncrypted(Kerb3961::MutableBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x18000e6b0`
- end: `0x18000eeba`
- name: `?CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUMutableBinary@2@AEBUReadOnlyBinary@2@_KI1_N3PEA_K@Z`
- size: `2058`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001684`
- `0x1800037e0`
- `0x180003a38`
- `0x180003a54`
- `0x180005b1c`
- `0x18000e6b0`
- `0x18000fd70`
- `0x18000fe44`
- `0x180010290`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`

## import_xrefs

- `cng!BCryptGenRandom` at `0x18000e7f8`
- `cng!BCryptGenRandom` at `0x18000e7f8`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonWrapEncrypted(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
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
  __int64 v16; // rcx
  __int64 v17; // rsi
  NTSTATUS v18; // eax
  int v19; // r8d
  NTSTATUS v20; // ebx
  int v21; // r8d
  int v22; // ebx
  int v23; // r8d
  int v24; // ebx
  int v25; // r8d
  int v26; // ebx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  __int64 i; // rbx
  int v31; // r8d
  unsigned int v32; // r14d
  char *v33; // rcx
  __int64 v34; // r14
  __int64 v35; // rcx
  int v36; // eax
  _QWORD *v37; // rax
  __int64 *v38; // r9
  __int64 v39; // r14
  __int64 v40; // rcx
  int v41; // eax
  int v42; // r8d
  int v43; // r14d
  __int64 *v44; // r9
  int v45; // r8d
  int v46; // r14d
  char *v47; // rcx
  __int64 v48; // rcx
  _QWORD *v49; // r14
  int v50; // r8d
  __int64 v51; // r14
  _QWORD *v52; // rcx
  int v53; // eax
  int v54; // r14d
  __int64 v55; // r8
  int v56; // r8d
  int v57; // r14d
  char *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // r14
  __int64 v61; // rcx
  int v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rax
  char v66; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v67; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v68; // [rsp+30h] [rbp-D0h]
  char *v69; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v70; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v71; // [rsp+48h] [rbp-B8h]
  char *v72; // [rsp+50h] [rbp-B0h]
  __int64 v73; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v74; // [rsp+68h] [rbp-98h]
  _BOOL8 v75; // [rsp+70h] [rbp-90h]
  __int64 v76; // [rsp+80h] [rbp-80h] BYREF
  __int64 v77; // [rsp+88h] [rbp-78h]
  char *v78; // [rsp+90h] [rbp-70h]
  __int64 v79; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v80; // [rsp+A0h] [rbp-60h]
  char *v81; // [rsp+A8h] [rbp-58h]
  _BYTE v82[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-48h]
  char *v84; // [rsp+C0h] [rbp-40h]
  __int64 v85; // [rsp+C8h] [rbp-38h] BYREF
  char *v86; // [rsp+D0h] [rbp-30h]
  __int64 v87; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v88; // [rsp+E0h] [rbp-20h]
  char *v89; // [rsp+E8h] [rbp-18h]
  _QWORD *v90; // [rsp+F0h] [rbp-10h]
  __int64 v91; // [rsp+F8h] [rbp-8h]
  _QWORD v92[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v93; // [rsp+110h] [rbp+10h] BYREF
  __int64 v94; // [rsp+118h] [rbp+18h]
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
  *(_QWORD *)(v94 + 16) = 0;
  *(_QWORD *)(v17 + 24) = 0;
  v96[1] = v17 + 16;
  *(_DWORD *)v17 = 1114370;
  *(_DWORD *)(v17 + 8) = _byteswap_ulong(a5);
  v97[1] = v17 + 8;
  *(_DWORD *)(v17 + 12) = (a8 != 0) - 1;
  *(_DWORD *)(v17 + 4) = -65520;
  v97[0] = 8;
  v96[0] = 8;
  v92[0] = 8;
  v92[1] = v17 + 24;
  v18 = BCryptGenRandom(0, (PUCHAR)(v17 + 24), 8u, 2u);
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
    &__S347__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B);
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
    &__S348__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B,
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
    *(_BYTE *)(i + v29) ^= 0xF0u;
  Kerb3961::RC4_4757::HmacData(
    a1,
    &v76,
    &v70,
    &__S350__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B);
  v32 = (unsigned int)v78;
  if ( (int)v78 < 0 )
    goto LABEL_27;
  v73 = 4;
  v74 = v17 + 8;
  v34 = Kerb3961::RC4_4757::HmacData(a1, &v70, &v76, &v73);
  if ( v77 )
    Kerb3961Free(v77);
  v76 = *(_QWORD *)v34;
  v35 = *(_QWORD *)(v34 + 8);
  *(_QWORD *)v34 = 0;
  v77 = v35;
  v36 = *(_DWORD *)(v34 + 16);
  *(_QWORD *)(v34 + 8) = 0;
  LODWORD(v78) = v36;
  *(_DWORD *)(v34 + 16) = -1073741823;
  if ( v71 )
    Kerb3961Free(v71);
  v32 = (unsigned int)v78;
  if ( (int)v78 < 0 )
  {
LABEL_27:
    v33 = "Kcrypt";
  }
  else
  {
    v37 = (_QWORD *)v85;
    if ( !*(_QWORD *)(v85 + 8) )
      v37 = v90;
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
      Kerb3961Free(v68);
    v67 = *(_QWORD *)v39;
    v40 = *(_QWORD *)(v39 + 8);
    *(_QWORD *)v39 = 0;
    v68 = v40;
    v41 = *(_DWORD *)(v39 + 16);
    *(_QWORD *)(v39 + 8) = 0;
    LODWORD(v69) = v41;
    *(_DWORD *)(v39 + 16) = -1073741823;
    if ( v71 )
      Kerb3961Free(v71);
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
            memmove((void *)(v17 + 24), (const void *)Size[1], Size[0]);
            memmove((void *)v49[1], (const void *)Size[3], Size[2]);
            *(_BYTE *)(v17 + 32) = *(_BYTE *)Size[5];
            v51 = Kerb3961::RC4_4757::HmacData(a1, &v73, v82, &v79);
            if ( v80 )
              Kerb3961Free(v80);
            v79 = *(_QWORD *)v51;
            v52 = *(_QWORD **)(v51 + 8);
            *(_QWORD *)v51 = 0;
            v80 = v52;
            v53 = *(_DWORD *)(v51 + 16);
            *(_QWORD *)(v51 + 8) = 0;
            LODWORD(v81) = v53;
            *(_DWORD *)(v51 + 16) = -1073741823;
            if ( v74 )
              Kerb3961Free(v74);
            v54 = (int)v81;
            if ( (int)v81 >= 0 )
            {
              v55 = v91;
              *(_QWORD *)(v17 + 16) = *v80;
              Kerb3961::RC4_4757::HmacData(
                a1,
                &v87,
                v55,
                &__S350__1__CommonWrapEncrypted_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUMutableBinary_3_AEBUReadOnlyBinary_3__KI1_N3PEA_K_Z_4U63_B);
              v57 = (int)v89;
              if ( (int)v89 < 0 )
                goto LABEL_85;
              v60 = Kerb3961::RC4_4757::HmacData(a1, &v73, &v87, v96);
              if ( v88 )
                Kerb3961Free(v88);
              v87 = *(_QWORD *)v60;
              v61 = *(_QWORD *)(v60 + 8);
              *(_QWORD *)v60 = 0;
              v88 = v61;
              v62 = *(_DWORD *)(v60 + 16);
              *(_QWORD *)(v60 + 8) = 0;
              LODWORD(v89) = v62;
              *(_DWORD *)(v60 + 16) = -1073741823;
              if ( v74 )
                Kerb3961Free(v74);
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
                    Kerb3961Free(v63);
                  if ( v71 )
                    Kerb3961Free(v71);
                  if ( v80 )
                    Kerb3961Free(v80);
                  if ( v77 )
                    Kerb3961Free(v77);
                  if ( i )
                    Kerb3961Free(i);
                  if ( v68 )
                    Kerb3961Free(v68);
                  v16 = v83;
LABEL_108:
                  if ( !v16 )
                    return a2;
LABEL_109:
                  Kerb3961Free(v16);
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
                Kerb3961Free(v59);
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
              Kerb3961Free(v71);
            if ( v80 )
              Kerb3961Free(v80);
            if ( v77 )
              Kerb3961Free(v77);
            if ( i )
              Kerb3961Free(i);
            if ( v68 )
              Kerb3961Free(v68);
            if ( v83 )
              Kerb3961Free(v83);
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
          Kerb3961Free(v48);
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
        Kerb3961Free(v80);
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
    Kerb3961Free(v77);
  if ( !i )
    goto LABEL_19;
  v27 = i;
LABEL_23:
  Kerb3961Free(v27);
LABEL_19:
  if ( v68 )
    Kerb3961Free(v68);
LABEL_13:
  if ( v83 )
    Kerb3961Free(v83);
  if ( v17 )
    goto LABEL_10;
  return a2;
}

```

## disassembly

```asm
0x18000e6b0  push    rbp
0x18000e6b2  push    rbx
0x18000e6b3  push    rsi
0x18000e6b4  push    rdi
0x18000e6b5  push    r12
0x18000e6b7  push    r13
0x18000e6b9  push    r14
0x18000e6bb  push    r15
0x18000e6bd  lea     rbp, [rsp-88h]
0x18000e6c5  sub     rsp, 188h
0x18000e6cc  mov     r14, [rbp+0C0h+arg_30]
0x18000e6d3  mov     r15, rcx
0x18000e6d6  mov     r12, [rbp+0C0h+arg_48]
0x18000e6dd  add     rcx, 8
0x18000e6e1  mov     [rbp+0C0h+var_F8], r9
0x18000e6e5  mov     rdi, rdx
0x18000e6e8  mov     [rbp+0C0h+var_D0], r8
0x18000e6ec  mov     [rbp+0C0h+var_C8], r14
0x18000e6f0  mov     rax, [rcx]
0x18000e6f3  mov     rax, [rax+68h]
0x18000e6f7  call    _guard_dispatch_icall
0x18000e6fc  mov     ebx, eax
0x18000e6fe  mov     rcx, r15
0x18000e701  mov     rax, [r15]
0x18000e704  mov     rax, [rax+0E0h]
0x18000e70b  call    _guard_dispatch_icall
0x18000e710  cmp     ebx, eax
0x18000e712  jnz     loc_18000EEAD
0x18000e718  xor     ebx, ebx
0x18000e71a  cmp     [rbp+0C0h+arg_28], ebx
0x18000e720  jz      short loc_18000E741
0x18000e722  lea     rcx, aQop0; "QOP == 0"
0x18000e729  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000e72e  mov     [rdi], rbx
0x18000e731  mov     [rdi+8], rbx
0x18000e735  mov     dword ptr [rdi+10h], 8009030Ah
0x18000e73c  jmp     loc_18000EE95
0x18000e741  mov     rax, r12
0x18000e744  lea     rcx, [rbp+0C0h+var_B0]
0x18000e748  neg     rax
0x18000e74b  sbb     rdx, rdx
0x18000e74e  neg     rdx
0x18000e751  add     rdx, 20h ; ' '
0x18000e755  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000e75a  mov     r13, [rbp+0C0h+var_A0]
0x18000e75e  test    r13d, r13d
0x18000e761  jns     short loc_18000E786
0x18000e763  mov     edx, r13d; char *
0x18000e766  lea     rcx, aHeaderbuffer; "headerBuffer"
0x18000e76d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e772  mov     rcx, [rbp+0C0h+var_A8]
0x18000e776  mov     [rdi], rbx
0x18000e779  mov     [rdi+8], rbx
0x18000e77d  mov     [rdi+10h], r13d
0x18000e781  jmp     loc_18000EE8B
0x18000e786  test    r12, r12
0x18000e789  jz      short loc_18000E793
0x18000e78b  mov     qword ptr [r12], 1
0x18000e793  mov     rsi, [rbp+0C0h+var_A8]
0x18000e797  mov     r8d, 8; cbBuffer
0x18000e79d  neg     [rbp+0C0h+arg_38]
0x18000e7a3  mov     [rsp+1C0h+var_1A0], 1
0x18000e7a8  mov     [rsi+10h], rbx
0x18000e7ac  lea     rax, [rsi+10h]
0x18000e7b0  mov     [rsi+18h], rbx
0x18000e7b4  lea     rcx, [rsi+8]
0x18000e7b8  mov     [rbp+0C0h+var_90], rax
0x18000e7bc  lea     rdx, [rsi+18h]; pbBuffer
0x18000e7c0  mov     eax, [rbp+0C0h+arg_20]
0x18000e7c6  lea     r9d, [r8-6]; dwFlags
0x18000e7ca  bswap   eax
0x18000e7cc  mov     dword ptr [rsi], 110102h
0x18000e7d2  mov     [rcx], eax
0x18000e7d4  sbb     eax, eax
0x18000e7d6  not     eax
0x18000e7d8  mov     [rbp+0C0h+var_80], rcx
0x18000e7dc  xor     ecx, ecx; hAlgorithm
0x18000e7de  mov     [rsi+0Ch], eax
0x18000e7e1  mov     dword ptr [rsi+4], 0FFFF0010h
0x18000e7e8  mov     [rbp+0C0h+var_88], r8
0x18000e7ec  mov     [rbp+0C0h+var_98], r8
0x18000e7f0  mov     [rbp+0C0h+var_C0], r8
0x18000e7f4  mov     [rbp+0C0h+var_B8], rdx
0x18000e7f8  call    cs:__imp_BCryptGenRandom
0x18000e7ff  nop     dword ptr [rax+rax+00h]
0x18000e804  mov     ebx, eax
0x18000e806  test    eax, eax
0x18000e808  jns     short loc_18000E832
0x18000e80a  mov     edx, eax; char *
0x18000e80c  lea     rcx, aRandomfillConf; "RandomFill(confounderBuffer)"
0x18000e813  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e818  mov     qword ptr [rdi], 0
0x18000e81f  mov     qword ptr [rdi+8], 0
0x18000e827  mov     [rdi+10h], ebx
0x18000e82a  mov     rcx, rsi
0x18000e82d  jmp     loc_18000EE90
0x18000e832  lea     r9, ?$S347@?1??CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUMutableBinary@3@AEBUReadOnlyBinary@3@_KI1_N3PEA_K@Z@4U63@B
0x18000e839  mov     r8, r14
0x18000e83c  lea     rdx, [rbp+0C0h+var_110]
0x18000e840  mov     rcx, r15
0x18000e843  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e848  mov     ebx, dword ptr [rbp+0C0h+var_100]
0x18000e84b  test    ebx, ebx
0x18000e84d  jns     short loc_18000E888
0x18000e84f  mov     edx, ebx; char *
0x18000e851  lea     rcx, aKsign; "Ksign"
0x18000e858  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e85d  mov     qword ptr [rdi], 0
0x18000e864  mov     qword ptr [rdi+8], 0
0x18000e86c  mov     [rdi+10h], ebx
0x18000e86f  mov     rcx, [rbp+0C0h+var_108]
0x18000e873  test    rcx, rcx
0x18000e876  jz      short loc_18000E87D
0x18000e878  call    Kerb3961Free
0x18000e87d  test    rsi, rsi
0x18000e880  jz      loc_18000EE95
0x18000e886  jmp     short loc_18000E82A
0x18000e888  lea     r9, [rbp+0C0h+var_C0]
0x18000e88c  mov     [rsp+1C0h+var_160], 8
0x18000e895  lea     r8, [rsp+1C0h+var_160]
0x18000e89a  mov     [rsp+1C0h+var_158], rsi
0x18000e89f  lea     rdx, ?$S348@?1??CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUMutableBinary@3@AEBUReadOnlyBinary@3@_KI1_N3PEA_K@Z@4U63@B
0x18000e8a6  lea     rcx, [rsp+1C0h+var_198]
0x18000e8ab  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e8b0  mov     ebx, dword ptr [rsp+1C0h+var_188]
0x18000e8b4  test    ebx, ebx
0x18000e8b6  jns     short loc_18000E8E9
0x18000e8b8  mov     edx, ebx; char *
0x18000e8ba  lea     rcx, aSignbuffer; "signBuffer"
0x18000e8c1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e8c6  mov     qword ptr [rdi], 0
0x18000e8cd  mov     qword ptr [rdi+8], 0
0x18000e8d5  mov     [rdi+10h], ebx
0x18000e8d8  mov     rcx, [rsp+1C0h+var_190]
0x18000e8dd  test    rcx, rcx
0x18000e8e0  jz      short loc_18000E86F
0x18000e8e2  call    Kerb3961Free
0x18000e8e7  jmp     short loc_18000E86F
0x18000e8e9  mov     rdx, r14
0x18000e8ec  lea     rcx, [rsp+1C0h+var_180]
0x18000e8f1  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000e8f6  mov     ebx, dword ptr [rsp+1C0h+var_170]
0x18000e8fa  test    ebx, ebx
0x18000e8fc  jns     short loc_18000E92F
0x18000e8fe  mov     edx, ebx; char *
0x18000e900  lea     rcx, aKlocal; "Klocal"
0x18000e907  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e90c  mov     rcx, [rsp+1C0h+var_178]
0x18000e911  mov     qword ptr [rdi], 0
0x18000e918  mov     qword ptr [rdi+8], 0
0x18000e920  mov     [rdi+10h], ebx
0x18000e923  test    rcx, rcx
0x18000e926  jz      short loc_18000E8D8
0x18000e928  call    Kerb3961Free
0x18000e92d  jmp     short loc_18000E8D8
0x18000e92f  mov     rcx, [rsp+1C0h+var_180]
0x18000e934  xor     eax, eax
0x18000e936  mov     rbx, [rsp+1C0h+var_178]
0x18000e93b  test    rcx, rcx
0x18000e93e  jz      short loc_18000E94C
0x18000e940  xor     byte ptr [rbx+rax], 0F0h
0x18000e944  inc     rax
0x18000e947  cmp     rax, rcx
0x18000e94a  jb      short loc_18000E940
0x18000e94c  lea     r9, ?$S350@?1??CommonWrapEncrypted@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUMutableBinary@3@AEBUReadOnlyBinary@3@_KI1_N3PEA_K@Z@4U63@B
0x18000e953  mov     rcx, r15
0x18000e956  lea     r8, [rsp+1C0h+var_180]
0x18000e95b  lea     rdx, [rbp+0C0h+var_140]
0x18000e95f  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e964  mov     r14d, dword ptr [rbp+0C0h+var_130]
0x18000e968  test    r14d, r14d
0x18000e96b  jns     short loc_18000E9AE
0x18000e96d  lea     rcx, aKcrypt; "Kcrypt"
0x18000e974  mov     edx, r14d; char *
0x18000e977  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e97c  mov     qword ptr [rdi], 0
0x18000e983  mov     qword ptr [rdi+8], 0
0x18000e98b  mov     [rdi+10h], r14d
0x18000e98f  mov     rcx, [rbp+0C0h+var_138]
0x18000e993  test    rcx, rcx
0x18000e996  jz      short loc_18000E99D
0x18000e998  call    Kerb3961Free
0x18000e99d  test    rbx, rbx
0x18000e9a0  jz      loc_18000E8D8
0x18000e9a6  mov     rcx, rbx
0x18000e9a9  jmp     loc_18000E928
0x18000e9ae  lea     rax, [rsi+8]
0x18000e9b2  mov     [rsp+1C0h+var_160], 4
0x18000e9bb  lea     r9, [rsp+1C0h+var_160]
0x18000e9c0  mov     [rsp+1C0h+var_158], rax
0x18000e9c5  lea     r8, [rbp+0C0h+var_140]
0x18000e9c9  mov     rcx, r15
0x18000e9cc  lea     rdx, [rsp+1C0h+var_180]
0x18000e9d1  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000e9d6  mov     rcx, [rbp+0C0h+var_138]
0x18000e9da  mov     r14, rax
0x18000e9dd  test    rcx, rcx
0x18000e9e0  jz      short loc_18000E9E7
0x18000e9e2  call    Kerb3961Free
0x18000e9e7  mov     rcx, [r14]
0x18000e9ea  mov     [rbp+0C0h+var_140], rcx
0x18000e9ee  mov     rcx, [r14+8]
0x18000e9f2  mov     qword ptr [r14], 0
0x18000e9f9  mov     [rbp+0C0h+var_138], rcx
0x18000e9fd  mov     eax, [r14+10h]
0x18000ea01  mov     qword ptr [r14+8], 0
0x18000ea09  mov     dword ptr [rbp+0C0h+var_130], eax
0x18000ea0c  mov     dword ptr [r14+10h], 0C0000001h
0x18000ea14  mov     rcx, [rsp+1C0h+var_178]
0x18000ea19  test    rcx, rcx
0x18000ea1c  jz      short loc_18000EA23
0x18000ea1e  call    Kerb3961Free
0x18000ea23  mov     r14d, dword ptr [rbp+0C0h+var_130]
0x18000ea27  test    r14d, r14d
0x18000ea2a  js      loc_18000E96D
0x18000ea30  mov     rax, [rbp+0C0h+var_F8]
0x18000ea34  cmp     qword ptr [rax+8], 0
0x18000ea39  cmovz   rax, [rbp+0C0h+var_D0]
0x18000ea3e  test    r12, r12
0x18000ea41  jz      short loc_18000EA56
0x18000ea43  lea     rcx, [rsp+1C0h+var_1A0]
0x18000ea48  mov     [rbp+0C0h+var_F8], 1
0x18000ea50  mov     [rbp+0C0h+var_F0], rcx
0x18000ea54  jmp     short loc_18000EA68
0x18000ea56  mov     [rsp+1C0h+var_160], 0
0x18000ea5f  mov     [rsp+1C0h+var_158], 0
0x18000ea68  lea     rcx, [rbp+0C0h+var_F8]
0x18000ea6c  test    r12, r12
0x18000ea6f  lea     r9, [rsp+1C0h+var_160]
0x18000ea74  mov     r8, rax
0x18000ea77  cmovnz  r9, rcx
0x18000ea7b  lea     rdx, [rsp+1C0h+var_198]
0x18000ea80  lea     rcx, [rsp+1C0h+var_180]
0x18000ea85  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000ea8a  mov     rcx, [rsp+1C0h+var_190]
0x18000ea8f  mov     r14, rax
0x18000ea92  test    rcx, rcx
0x18000ea95  jz      short loc_18000EA9C
0x18000ea97  call    Kerb3961Free
0x18000ea9c  mov     rcx, [r14]
0x18000ea9f  mov     [rsp+1C0h+var_198], rcx
0x18000eaa4  mov     rcx, [r14+8]
0x18000eaa8  mov     qword ptr [r14], 0
0x18000eaaf  mov     [rsp+1C0h+var_190], rcx
0x18000eab4  mov     eax, [r14+10h]
0x18000eab8  mov     qword ptr [r14+8], 0
0x18000eac0  mov     dword ptr [rsp+1C0h+var_188], eax
0x18000eac4  mov     dword ptr [r14+10h], 0C0000001h
0x18000eacc  mov     rcx, [rsp+1C0h+var_178]
0x18000ead1  test    rcx, rcx
0x18000ead4  jz      short loc_18000EADB
0x18000ead6  call    Kerb3961Free
0x18000eadb  mov     r14d, dword ptr [rsp+1C0h+var_188]
0x18000eae0  test    r14d, r14d
0x18000eae3  jns     short loc_18000EAF1
0x18000eae5  lea     rcx, aSignbuffer; "signBuffer"
0x18000eaec  jmp     loc_18000E974
0x18000eaf1  lea     r8, [rsp+1C0h+var_198]
0x18000eaf6  mov     rcx, r15
0x18000eaf9  lea     rdx, [rbp+0C0h+var_128]
0x18000eafd  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x18000eb02  mov     r14d, dword ptr [rbp+0C0h+var_118]
0x18000eb06  test    r14d, r14d
0x18000eb09  jns     short loc_18000EB44
0x18000eb0b  mov     edx, r14d; char *
0x18000eb0e  lea     rcx, aSgnCksum; "Sgn_Cksum"
0x18000eb15  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000eb1a  mov     qword ptr [rdi], 0
0x18000eb21  mov     qword ptr [rdi+8], 0
0x18000eb29  mov     [rdi+10h], r14d
0x18000eb2d  mov     rcx, [rbp+0C0h+var_120]
0x18000eb31  test    rcx, rcx
0x18000eb34  jz      loc_18000E98F
0x18000eb3a  call    Kerb3961Free
0x18000eb3f  jmp     loc_18000E98F
0x18000eb44  test    r12, r12
0x18000eb47  jz      short loc_18000EB5C
0x18000eb49  lea     rax, [rsp+1C0h+var_1A0]
0x18000eb4e  mov     [rbp+0C0h+var_F8], 1
0x18000eb56  mov     [rbp+0C0h+var_F0], rax
0x18000eb5a  jmp     short loc_18000EB6E
0x18000eb5c  mov     [rsp+1C0h+var_160], 0
0x18000eb65  mov     [rsp+1C0h+var_158], 0
0x18000eb6e  mov     r8, [rbp+0C0h+var_D0]
0x18000eb72  lea     rax, [rbp+0C0h+var_F8]
0x18000eb76  test    r12, r12
0x18000eb79  lea     r9, [rsp+1C0h+var_160]
0x18000eb7e  lea     rdx, [rbp+0C0h+var_C0]
0x18000eb82  cmovnz  r9, rax
0x18000eb86  lea     rcx, [rsp+1C0h+var_180]
0x18000eb8b  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000eb90  mov     r14d, dword ptr [rsp+1C0h+var_170]
0x18000eb95  test    r14d, r14d
0x18000eb98  jns     short loc_18000EBD4
0x18000eb9a  lea     rcx, aTmp; "tmp"
0x18000eba1  mov     edx, r14d; char *
0x18000eba4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000eba9  mov     rcx, [rsp+1C0h+var_178]
0x18000ebae  mov     qword ptr [rdi], 0
0x18000ebb5  mov     qword ptr [rdi+8], 0
  ... truncated ...
```
