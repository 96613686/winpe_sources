# Kerb3961::RC4_4757::CommonWrapPlain(Kerb3961::ReadOnlyBinary const &,unsigned __int64,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x18000eec0`
- end: `0x18000f2a8`
- name: `?CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_K0_N2@Z`
- size: `1000`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001464`
- `0x180003a38`
- `0x180005b1c`
- `0x18000eec0`
- `0x18000fd70`
- `0x18000fe44`
- `0x180010290`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## import_xrefs

- `cng!BCryptGenRandom` at `0x18000efa6`
- `cng!BCryptGenRandom` at `0x18000efa6`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonWrapPlain(
        _QWORD *a1,
        __int64 a2,
        __int128 *a3,
        unsigned int a4,
        __int64 a5,
        char a6)
{
  int v9; // ebx
  const unsigned __int16 *v10; // rdx
  int v11; // r8d
  int v12; // r15d
  __int64 v13; // rcx
  __int64 v14; // rsi
  bool v15; // cf
  NTSTATUS v16; // eax
  int v17; // r8d
  NTSTATUS v18; // ebx
  int v19; // r8d
  int v20; // ebx
  __int128 v21; // xmm1
  int v22; // r8d
  int v23; // ebx
  int v24; // r8d
  unsigned int v25; // ebx
  __int64 v26; // rbx
  _QWORD *v27; // rcx
  int v28; // eax
  __int64 v29; // r8
  int v30; // r8d
  int v31; // ebx
  char *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v40; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v41; // [rsp+28h] [rbp-D8h]
  char *v42; // [rsp+30h] [rbp-D0h]
  __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h]
  char *v45; // [rsp+48h] [rbp-B8h]
  _BYTE v46[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h]
  char *v48; // [rsp+60h] [rbp-A0h]
  _BYTE v49[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h]
  char *v51; // [rsp+78h] [rbp-88h]
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+88h] [rbp-78h]
  char *v54; // [rsp+90h] [rbp-70h]
  _QWORD v55[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v56[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v57[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v58; // [rsp+C0h] [rbp-40h]
  __int128 v59; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int64 v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  __int128 v64; // [rsp+100h] [rbp+0h]
  char v65; // [rsp+150h] [rbp+50h] BYREF
  __int128 *v66; // [rsp+160h] [rbp+60h]

  v66 = a3;
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v9 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v10);
  Kerb3961::MakeBuffer(&v52);
  v12 = (int)v54;
  if ( (int)v54 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"headerBuffer",
      (const char *)(unsigned int)v54,
      v11);
    v13 = v53;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v12;
    goto LABEL_44;
  }
  v14 = v53;
  v15 = a6 != 0;
  a6 = -a6;
  *(_QWORD *)(v53 + 16) = 0;
  *(_QWORD *)(v14 + 24) = 0;
  *(_DWORD *)v14 = 1114370;
  *(_DWORD *)(v14 + 8) = _byteswap_ulong(a4);
  v56[1] = v14 + 8;
  v55[1] = v14 + 16;
  *(_DWORD *)(v14 + 4) = -1;
  *(_DWORD *)(v14 + 12) = v15 - 1;
  v56[0] = 8;
  v55[0] = 8;
  v16 = BCryptGenRandom(0, (PUCHAR)(v14 + 24), 8u, 2u);
  v18 = v16;
  if ( v16 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"RandomFill(confounderBuffer)",
      (const char *)(unsigned int)v16,
      v17);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v18;
    goto LABEL_6;
  }
  Kerb3961::RC4_4757::HmacData(
    a1,
    v46,
    a5,
    &__S355__1__CommonWrapPlain_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__K0_N2_Z_4U53_B);
  v20 = (int)v48;
  if ( (int)v48 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v48, v19);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v20;
    goto LABEL_9;
  }
  v61 = v14;
  v63 = v14 + 24;
  v21 = *v66;
  v59 = __S356__1__CommonWrapPlain_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__K0_N2_Z_4U53_B;
  v60 = 8;
  v64 = v21;
  v62 = 8;
  Kerb3961::Concatenate<4>(v49, &v59);
  v23 = (int)v51;
  if ( (int)v51 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"signBuffer",
      (const char *)(unsigned int)v51,
      v22);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v23;
LABEL_15:
    if ( v50 )
      Kerb3961Free(v50);
LABEL_9:
    if ( v47 )
      Kerb3961Free(v47);
    if ( !v14 )
      return a2;
LABEL_6:
    v13 = v14;
LABEL_45:
    Kerb3961Free(v13);
    return a2;
  }
  Kerb3961::RC4_4757::HashData(a1, &v40, v49);
  v25 = (unsigned int)v42;
  if ( (int)v42 < 0 )
    goto LABEL_18;
  v26 = Kerb3961::RC4_4757::HmacData(a1, v57, v46, &v40);
  if ( v41 )
    Kerb3961Free(v41);
  v40 = *(_QWORD *)v26;
  v27 = *(_QWORD **)(v26 + 8);
  *(_QWORD *)v26 = 0;
  v41 = v27;
  v28 = *(_DWORD *)(v26 + 16);
  *(_QWORD *)(v26 + 8) = 0;
  LODWORD(v42) = v28;
  *(_DWORD *)(v26 + 16) = -1073741823;
  if ( v58 )
    Kerb3961Free(v58);
  v25 = (unsigned int)v42;
  if ( (int)v42 < 0 )
  {
LABEL_18:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Sgn_Cksum", (const char *)v25, v24);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v25;
LABEL_19:
    if ( v41 )
      Kerb3961Free(v41);
    goto LABEL_15;
  }
  v29 = a5;
  *(_QWORD *)(v14 + 16) = *v41;
  Kerb3961::RC4_4757::HmacData(
    a1,
    &v43,
    v29,
    &__S358__1__CommonWrapPlain_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__K0_N2_Z_4U53_B);
  v31 = (int)v45;
  if ( (int)v45 < 0 )
    goto LABEL_27;
  v34 = Kerb3961::RC4_4757::HmacData(a1, v57, &v43, v55);
  if ( v44 )
    Kerb3961Free(v44);
  v43 = *(_QWORD *)v34;
  v35 = *(_QWORD *)(v34 + 8);
  *(_QWORD *)v34 = 0;
  v44 = v35;
  v36 = *(_DWORD *)(v34 + 16);
  *(_QWORD *)(v34 + 8) = 0;
  LODWORD(v45) = v36;
  *(_DWORD *)(v34 + 16) = -1073741823;
  if ( v58 )
    Kerb3961Free(v58);
  v31 = (int)v45;
  if ( (int)v45 < 0 )
  {
LABEL_27:
    v32 = "Kseq";
    goto LABEL_28;
  }
  v31 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, &v65, &v43, v56);
  if ( v31 < 0 )
  {
    v32 = "RC4Data(Kseq, sequenceBuffer)";
LABEL_28:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v32, (const char *)(unsigned int)v31, v30);
    v33 = v44;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v31;
    if ( v33 )
      Kerb3961Free(v33);
    goto LABEL_19;
  }
  v37 = v44;
  v38 = v52;
  *(_DWORD *)(a2 + 16) = v12;
  *(_QWORD *)a2 = v38;
  *(_QWORD *)(a2 + 8) = v14;
  if ( v37 )
    Kerb3961Free(v37);
  if ( v41 )
    Kerb3961Free(v41);
  if ( v50 )
    Kerb3961Free(v50);
  v13 = v47;
LABEL_44:
  if ( v13 )
    goto LABEL_45;
  return a2;
}

```

## disassembly

```asm
0x18000eec0  mov     [rsp-8+arg_8], rbx
0x18000eec5  mov     [rsp-8+arg_10], r8
0x18000eeca  push    rbp
0x18000eecb  push    rsi
0x18000eecc  push    rdi
0x18000eecd  push    r12
0x18000eecf  push    r13
0x18000eed1  push    r14
0x18000eed3  push    r15
0x18000eed5  lea     rbp, [rsp-10h]
0x18000eeda  sub     rsp, 110h
0x18000eee1  mov     r14, rcx
0x18000eee4  mov     r12, r9
0x18000eee7  add     rcx, 8
0x18000eeeb  mov     rdi, rdx
0x18000eeee  mov     rax, [rcx]
0x18000eef1  mov     rax, [rax+68h]
0x18000eef5  call    _guard_dispatch_icall
0x18000eefa  mov     r10, [r14]
0x18000eefd  mov     ebx, eax
0x18000eeff  mov     rcx, r14
0x18000ef02  mov     rax, [r10+0E0h]
0x18000ef09  call    _guard_dispatch_icall
0x18000ef0e  cmp     ebx, eax
0x18000ef10  jnz     loc_18000F29B
0x18000ef16  mov     edx, 20h ; ' '
0x18000ef1b  lea     rcx, [rbp+40h+var_C0]
0x18000ef1f  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000ef24  mov     r15, [rbp+40h+var_B0]
0x18000ef28  xor     ebx, ebx
0x18000ef2a  test    r15d, r15d
0x18000ef2d  jns     short loc_18000EF52
0x18000ef2f  mov     edx, r15d; char *
0x18000ef32  lea     rcx, aHeaderbuffer; "headerBuffer"
0x18000ef39  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000ef3e  mov     rcx, [rbp+40h+var_B8]
0x18000ef42  mov     [rdi], rbx
0x18000ef45  mov     [rdi+8], rbx
0x18000ef49  mov     [rdi+10h], r15d
0x18000ef4d  jmp     loc_18000F272
0x18000ef52  mov     rsi, [rbp+40h+var_B8]
0x18000ef56  mov     r8d, 8; cbBuffer
0x18000ef5c  neg     [rbp+40h+arg_28]
0x18000ef5f  bswap   r12d
0x18000ef62  mov     [rsi+10h], rbx
0x18000ef66  lea     rax, [rsi+8]
0x18000ef6a  mov     [rsi+18h], rbx
0x18000ef6e  lea     rcx, [rsi+10h]
0x18000ef72  mov     dword ptr [rsi], 110102h
0x18000ef78  lea     r13, [rsi+18h]
0x18000ef7c  mov     [rax], r12d
0x18000ef7f  lea     r9d, [r8-6]; dwFlags
0x18000ef83  mov     [rbp+40h+var_90], rax
0x18000ef87  mov     rdx, r13; pbBuffer
0x18000ef8a  sbb     eax, eax
0x18000ef8c  mov     [rbp+40h+var_A0], rcx
0x18000ef90  not     eax
0x18000ef92  mov     dword ptr [rsi+4], 0FFFFFFFFh
0x18000ef99  xor     ecx, ecx; hAlgorithm
0x18000ef9b  mov     [rsi+0Ch], eax
0x18000ef9e  mov     [rbp+40h+var_98], r8
0x18000efa2  mov     [rbp+40h+var_A8], r8
0x18000efa6  call    cs:__imp_BCryptGenRandom
0x18000efad  nop     dword ptr [rax+rax+00h]
0x18000efb2  xor     r12d, r12d
0x18000efb5  mov     ebx, eax
0x18000efb7  test    eax, eax
0x18000efb9  jns     short loc_18000EFDB
0x18000efbb  mov     edx, eax; char *
0x18000efbd  lea     rcx, aRandomfillConf; "RandomFill(confounderBuffer)"
0x18000efc4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000efc9  mov     [rdi], r12
0x18000efcc  mov     [rdi+8], r12
0x18000efd0  mov     [rdi+10h], ebx
0x18000efd3  mov     rcx, rsi
0x18000efd6  jmp     loc_18000F277
0x18000efdb  mov     r8, [rbp+40h+arg_20]
0x18000efdf  lea     r9, ?$S355@?1??CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_K0_N2@Z@4U53@B
0x18000efe6  lea     rdx, [rsp+140h+var_F0]
0x18000efeb  mov     rcx, r14
0x18000efee  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000eff3  mov     ebx, dword ptr [rsp+140h+var_E0]
0x18000eff7  test    ebx, ebx
0x18000eff9  jns     short loc_18000F02D
0x18000effb  mov     edx, ebx; char *
0x18000effd  lea     rcx, aKsign; "Ksign"
0x18000f004  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f009  mov     [rdi], r12
0x18000f00c  mov     [rdi+8], r12
0x18000f010  mov     [rdi+10h], ebx
0x18000f013  mov     rcx, [rsp+140h+var_E8]
0x18000f018  test    rcx, rcx
0x18000f01b  jz      short loc_18000F022
0x18000f01d  call    Kerb3961Free
0x18000f022  test    rsi, rsi
0x18000f025  jz      loc_18000F27C
0x18000f02b  jmp     short loc_18000EFD3
0x18000f02d  mov     rax, [rbp+40h+arg_10]
0x18000f031  lea     rdx, [rbp+40h+var_70]
0x18000f035  movups  xmm0, xmmword ptr cs:?$S356@?1??CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_K0_N2@Z@4U53@B
0x18000f03c  lea     rcx, [rsp+140h+var_D8]
0x18000f041  mov     [rbp+40h+var_58], rsi
0x18000f045  mov     [rbp+40h+var_48], r13
0x18000f049  movups  xmm1, xmmword ptr [rax]
0x18000f04c  mov     eax, 8
0x18000f051  movdqu  [rbp+40h+var_70], xmm0
0x18000f056  mov     [rbp+40h+var_60], rax
0x18000f05a  movdqu  [rbp+40h+var_40], xmm1
0x18000f05f  mov     [rbp+40h+var_50], rax
0x18000f063  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x18000f068  mov     ebx, dword ptr [rsp+140h+var_C8]
0x18000f06c  test    ebx, ebx
0x18000f06e  jns     short loc_18000F09C
0x18000f070  mov     edx, ebx; char *
0x18000f072  lea     rcx, aSignbuffer; "signBuffer"
0x18000f079  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f07e  mov     [rdi], r12
0x18000f081  mov     [rdi+8], r12
0x18000f085  mov     [rdi+10h], ebx
0x18000f088  mov     rcx, [rsp+140h+var_D0]
0x18000f08d  test    rcx, rcx
0x18000f090  jz      short loc_18000F013
0x18000f092  call    Kerb3961Free
0x18000f097  jmp     loc_18000F013
0x18000f09c  lea     r8, [rsp+140h+var_D8]
0x18000f0a1  mov     rcx, r14
0x18000f0a4  lea     rdx, [rsp+140h+var_120]
0x18000f0a9  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x18000f0ae  mov     ebx, dword ptr [rsp+140h+var_110]
0x18000f0b2  test    ebx, ebx
0x18000f0b4  jns     short loc_18000F0DF
0x18000f0b6  mov     edx, ebx; char *
0x18000f0b8  lea     rcx, aSgnCksum; "Sgn_Cksum"
0x18000f0bf  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f0c4  mov     [rdi], r12
0x18000f0c7  mov     [rdi+8], r12
0x18000f0cb  mov     [rdi+10h], ebx
0x18000f0ce  mov     rcx, [rsp+140h+var_118]
0x18000f0d3  test    rcx, rcx
0x18000f0d6  jz      short loc_18000F088
0x18000f0d8  call    Kerb3961Free
0x18000f0dd  jmp     short loc_18000F088
0x18000f0df  lea     r9, [rsp+140h+var_120]
0x18000f0e4  mov     rcx, r14
0x18000f0e7  lea     r8, [rsp+140h+var_F0]
0x18000f0ec  lea     rdx, [rbp+40h+var_88]
0x18000f0f0  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f0f5  mov     rcx, [rsp+140h+var_118]
0x18000f0fa  mov     rbx, rax
0x18000f0fd  test    rcx, rcx
0x18000f100  jz      short loc_18000F107
0x18000f102  call    Kerb3961Free
0x18000f107  mov     rcx, [rbx]
0x18000f10a  mov     r13d, 0C0000001h
0x18000f110  mov     [rsp+140h+var_120], rcx
0x18000f115  mov     rcx, [rbx+8]
0x18000f119  mov     [rbx], r12
0x18000f11c  mov     [rsp+140h+var_118], rcx
0x18000f121  mov     eax, [rbx+10h]
0x18000f124  mov     [rbx+8], r12
0x18000f128  mov     dword ptr [rsp+140h+var_110], eax
0x18000f12c  mov     [rbx+10h], r13d
0x18000f130  mov     rcx, [rbp+40h+var_80]
0x18000f134  test    rcx, rcx
0x18000f137  jz      short loc_18000F13E
0x18000f139  call    Kerb3961Free
0x18000f13e  mov     ebx, dword ptr [rsp+140h+var_110]
0x18000f142  test    ebx, ebx
0x18000f144  js      loc_18000F0B6
0x18000f14a  mov     rax, [rsp+140h+var_118]
0x18000f14f  lea     r9, ?$S358@?1??CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_K0_N2@Z@4U53@B
0x18000f156  mov     r8, [rbp+40h+arg_20]
0x18000f15a  lea     rdx, [rsp+140h+var_108]
0x18000f15f  mov     rcx, [rax]
0x18000f162  mov     [rsi+10h], rcx
0x18000f166  mov     rcx, r14
0x18000f169  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f16e  mov     ebx, dword ptr [rsp+140h+var_F8]
0x18000f172  test    ebx, ebx
0x18000f174  jns     short loc_18000F1A6
0x18000f176  lea     rcx, aKseq; "Kseq"
0x18000f17d  mov     edx, ebx; char *
0x18000f17f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f184  mov     rcx, [rsp+140h+var_100]
0x18000f189  mov     [rdi], r12
0x18000f18c  mov     [rdi+8], r12
0x18000f190  mov     [rdi+10h], ebx
0x18000f193  test    rcx, rcx
0x18000f196  jz      loc_18000F0CE
0x18000f19c  call    Kerb3961Free
0x18000f1a1  jmp     loc_18000F0CE
0x18000f1a6  lea     r9, [rbp+40h+var_A8]
0x18000f1aa  mov     rcx, r14
0x18000f1ad  lea     r8, [rsp+140h+var_108]
0x18000f1b2  lea     rdx, [rbp+40h+var_88]
0x18000f1b6  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000f1bb  mov     rcx, [rsp+140h+var_100]
0x18000f1c0  mov     rbx, rax
0x18000f1c3  test    rcx, rcx
0x18000f1c6  jz      short loc_18000F1CD
0x18000f1c8  call    Kerb3961Free
0x18000f1cd  mov     rcx, [rbx]
0x18000f1d0  mov     [rsp+140h+var_108], rcx
0x18000f1d5  mov     rcx, [rbx+8]
0x18000f1d9  mov     [rbx], r12
0x18000f1dc  mov     [rsp+140h+var_100], rcx
0x18000f1e1  mov     eax, [rbx+10h]
0x18000f1e4  mov     [rbx+8], r12
0x18000f1e8  mov     dword ptr [rsp+140h+var_F8], eax
0x18000f1ec  mov     [rbx+10h], r13d
0x18000f1f0  mov     rcx, [rbp+40h+var_80]
0x18000f1f4  test    rcx, rcx
0x18000f1f7  jz      short loc_18000F1FE
0x18000f1f9  call    Kerb3961Free
0x18000f1fe  mov     ebx, dword ptr [rsp+140h+var_F8]
0x18000f202  test    ebx, ebx
0x18000f204  js      loc_18000F176
0x18000f20a  lea     r9, [rbp+40h+var_98]
0x18000f20e  mov     rcx, r14
0x18000f211  lea     r8, [rsp+140h+var_108]
0x18000f216  lea     rdx, [rbp+40h+arg_0]
0x18000f21a  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x18000f21f  mov     ebx, [rax]
0x18000f221  test    ebx, ebx
0x18000f223  jns     short loc_18000F231
0x18000f225  lea     rcx, aRc4dataKseqSeq; "RC4Data(Kseq, sequenceBuffer)"
0x18000f22c  jmp     loc_18000F17D
0x18000f231  mov     rcx, [rsp+140h+var_100]
0x18000f236  mov     rax, [rbp+40h+var_C0]
0x18000f23a  mov     [rdi+10h], r15d
0x18000f23e  mov     [rdi], rax
0x18000f241  mov     [rdi+8], rsi
0x18000f245  test    rcx, rcx
0x18000f248  jz      short loc_18000F24F
0x18000f24a  call    Kerb3961Free
0x18000f24f  mov     rcx, [rsp+140h+var_118]
0x18000f254  test    rcx, rcx
0x18000f257  jz      short loc_18000F25E
0x18000f259  call    Kerb3961Free
0x18000f25e  mov     rcx, [rsp+140h+var_D0]
0x18000f263  test    rcx, rcx
0x18000f266  jz      short loc_18000F26D
0x18000f268  call    Kerb3961Free
0x18000f26d  mov     rcx, [rsp+140h+var_E8]
0x18000f272  test    rcx, rcx
0x18000f275  jz      short loc_18000F27C
0x18000f277  call    Kerb3961Free
0x18000f27c  mov     rbx, [rsp+140h+arg_8]
0x18000f284  mov     rax, rdi
0x18000f287  add     rsp, 110h
0x18000f28e  pop     r15
0x18000f290  pop     r14
0x18000f292  pop     r13
0x18000f294  pop     r12
0x18000f296  pop     rdi
0x18000f297  pop     rsi
0x18000f298  pop     rbp
0x18000f299  retn
0x18000f29b  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x18000f2a2  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
