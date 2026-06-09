# Kerb3961::RC4_4757::CommonWrapPlain(Kerb3961::ReadOnlyBinary const &,unsigned __int64,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180006ac0`
- end: `0x180006ebd`
- name: `?CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_K0_N2@Z`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180004118`
- `0x180006ac0`
- `0x180008500`
- `0x1800085cc`
- `0x18000901c`
- `0x180009190`
- `0x18001e010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180006ba6`
- `bcrypt!BCryptGenRandom` at `0x180006ba6`

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
  void *v13; // rcx
  _QWORD *v14; // rsi
  bool v15; // cf
  NTSTATUS v16; // eax
  int v17; // r8d
  NTSTATUS v18; // ebx
  int v19; // r8d
  int v20; // ebx
  int v21; // r8d
  int v22; // ebx
  int v23; // r8d
  unsigned int v24; // ebx
  __int64 v25; // rbx
  void *v26; // rcx
  int v27; // eax
  __int64 v28; // r8
  int v29; // r8d
  int v30; // ebx
  char *v31; // rcx
  void *v32; // rcx
  __int64 v33; // rbx
  void *v34; // rcx
  int v35; // eax
  void *v36; // rcx
  __int64 v37; // rax
  __int64 v39; // [rsp+20h] [rbp-E0h] BYREF
  void *v40; // [rsp+28h] [rbp-D8h]
  char *v41; // [rsp+30h] [rbp-D0h]
  __int64 v42; // [rsp+38h] [rbp-C8h] BYREF
  void *v43; // [rsp+40h] [rbp-C0h]
  char *v44; // [rsp+48h] [rbp-B8h]
  char v45[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v46; // [rsp+58h] [rbp-A8h]
  char *v47; // [rsp+60h] [rbp-A0h]
  char v48[8]; // [rsp+68h] [rbp-98h] BYREF
  void *v49; // [rsp+70h] [rbp-90h]
  char *v50; // [rsp+78h] [rbp-88h]
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v52; // [rsp+88h] [rbp-78h]
  char *v53; // [rsp+90h] [rbp-70h]
  _QWORD v54[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v55[2]; // [rsp+A8h] [rbp-58h] BYREF
  char v56[8]; // [rsp+B8h] [rbp-48h] BYREF
  void *v57; // [rsp+C0h] [rbp-40h]
  __int128 v58; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+E0h] [rbp-20h]
  _QWORD *v60; // [rsp+E8h] [rbp-18h]
  __int64 v61; // [rsp+F0h] [rbp-10h]
  _QWORD *v62; // [rsp+F8h] [rbp-8h]
  __int128 v63; // [rsp+100h] [rbp+0h]
  char v64; // [rsp+150h] [rbp+50h] BYREF
  __int128 *v65; // [rsp+160h] [rbp+60h]

  v65 = a3;
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v9 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v10);
  Kerb3961::MakeBuffer(&v51);
  v12 = (int)v53;
  if ( (int)v53 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"headerBuffer",
      (const char *)(unsigned int)v53,
      v11);
    v13 = v52;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v12;
    goto LABEL_44;
  }
  v14 = v52;
  v15 = a6 != 0;
  a6 = -a6;
  v52[2] = 0;
  v14[3] = 0;
  *(_DWORD *)v14 = 1114370;
  *((_DWORD *)v14 + 2) = _byteswap_ulong(a4);
  v55[1] = v14 + 1;
  v54[1] = v14 + 2;
  *((_DWORD *)v14 + 1) = -1;
  *((_DWORD *)v14 + 3) = v15 - 1;
  v55[0] = 8;
  v54[0] = 8;
  v16 = BCryptGenRandom(0, (PUCHAR)v14 + 24, 8u, 2u);
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
    v45,
    a5,
    &__S33__1__CommonWrapPlain_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__K0_N2_Z_4U53_B);
  v20 = (int)v47;
  if ( (int)v47 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v47, v19);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v20;
    goto LABEL_9;
  }
  v60 = v14;
  v59 = 8;
  v61 = 8;
  v58 = *(_OWORD *)__S34__1__CommonWrapPlain_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__K0_N2_Z_4U53_B;
  v62 = v14 + 3;
  v63 = *v65;
  Kerb3961::Concatenate<4>(v48, &v58);
  v22 = (int)v50;
  if ( (int)v50 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"signBuffer",
      (const char *)(unsigned int)v50,
      v21);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v22;
LABEL_15:
    if ( v49 )
      operator delete(v49, 0);
LABEL_9:
    if ( v46 )
      operator delete(v46, 0);
    if ( !v14 )
      return a2;
LABEL_6:
    v13 = v14;
LABEL_45:
    operator delete(v13, 0);
    return a2;
  }
  Kerb3961::RC4_4757::HashData(a1, &v39, v48);
  v24 = (unsigned int)v41;
  if ( (int)v41 < 0 )
    goto LABEL_18;
  v25 = Kerb3961::RC4_4757::HmacData(a1, v56, v45, &v39);
  if ( v40 )
    operator delete(v40, 0);
  v39 = *(_QWORD *)v25;
  v26 = *(void **)(v25 + 8);
  *(_QWORD *)v25 = 0;
  v40 = v26;
  v27 = *(_DWORD *)(v25 + 16);
  *(_QWORD *)(v25 + 8) = 0;
  LODWORD(v41) = v27;
  *(_DWORD *)(v25 + 16) = -1073741823;
  if ( v57 )
    operator delete(v57, 0);
  v24 = (unsigned int)v41;
  if ( (int)v41 < 0 )
  {
LABEL_18:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Sgn_Cksum", (const char *)v24, v23);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v24;
LABEL_19:
    if ( v40 )
      operator delete(v40, 0);
    goto LABEL_15;
  }
  v28 = a5;
  v14[2] = *(_QWORD *)v40;
  Kerb3961::RC4_4757::HmacData(
    a1,
    &v42,
    v28,
    &__S36__1__CommonWrapPlain_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3__K0_N2_Z_4U53_B);
  v30 = (int)v44;
  if ( (int)v44 < 0 )
    goto LABEL_27;
  v33 = Kerb3961::RC4_4757::HmacData(a1, v56, &v42, v54);
  if ( v43 )
    operator delete(v43, 0);
  v42 = *(_QWORD *)v33;
  v34 = *(void **)(v33 + 8);
  *(_QWORD *)v33 = 0;
  v43 = v34;
  v35 = *(_DWORD *)(v33 + 16);
  *(_QWORD *)(v33 + 8) = 0;
  LODWORD(v44) = v35;
  *(_DWORD *)(v33 + 16) = -1073741823;
  if ( v57 )
    operator delete(v57, 0);
  v30 = (int)v44;
  if ( (int)v44 < 0 )
  {
LABEL_27:
    v31 = "Kseq";
    goto LABEL_28;
  }
  v30 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, &v64, &v42, v55);
  if ( v30 < 0 )
  {
    v31 = "RC4Data(Kseq, sequenceBuffer)";
LABEL_28:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v31, (const char *)(unsigned int)v30, v29);
    v32 = v43;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v30;
    if ( v32 )
      operator delete(v32, 0);
    goto LABEL_19;
  }
  v36 = v43;
  v37 = v51;
  *(_DWORD *)(a2 + 16) = v12;
  *(_QWORD *)a2 = v37;
  *(_QWORD *)(a2 + 8) = v14;
  if ( v36 )
    operator delete(v36, 0);
  if ( v40 )
    operator delete(v40, 0);
  if ( v49 )
    operator delete(v49, 0);
  v13 = v46;
LABEL_44:
  if ( v13 )
    goto LABEL_45;
  return a2;
}

```

## disassembly

```asm
0x180006ac0  mov     [rsp-8+arg_8], rbx
0x180006ac5  mov     [rsp-8+arg_10], r8
0x180006aca  push    rbp
0x180006acb  push    rsi
0x180006acc  push    rdi
0x180006acd  push    r12
0x180006acf  push    r13
0x180006ad1  push    r14
0x180006ad3  push    r15
0x180006ad5  lea     rbp, [rsp-10h]
0x180006ada  sub     rsp, 110h
0x180006ae1  mov     r14, rcx
0x180006ae4  mov     r13, r9
0x180006ae7  add     rcx, 8
0x180006aeb  mov     rdi, rdx
0x180006aee  mov     rax, [rcx]
0x180006af1  mov     rax, [rax+68h]
0x180006af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afa  mov     r10, [r14]
0x180006afd  mov     ebx, eax
0x180006aff  mov     rcx, r14
0x180006b02  mov     rax, [r10+0E0h]
0x180006b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0e  cmp     ebx, eax
0x180006b10  jnz     loc_180006EB0
0x180006b16  mov     edx, 20h ; ' '
0x180006b1b  lea     rcx, [rbp+40h+var_C0]
0x180006b1f  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180006b24  mov     r15, [rbp+40h+var_B0]
0x180006b28  xor     ebx, ebx
0x180006b2a  test    r15d, r15d
0x180006b2d  jns     short loc_180006B52
0x180006b2f  mov     edx, r15d; char *
0x180006b32  lea     rcx, aHeaderbuffer; "headerBuffer"
0x180006b39  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006b3e  mov     rcx, [rbp+40h+var_B8]
0x180006b42  mov     [rdi], rbx
0x180006b45  mov     [rdi+8], rbx
0x180006b49  mov     [rdi+10h], r15d
0x180006b4d  jmp     loc_180006E86
0x180006b52  mov     rsi, [rbp+40h+var_B8]
0x180006b56  mov     r8d, 8; cbBuffer
0x180006b5c  neg     [rbp+40h+arg_28]
0x180006b5f  bswap   r13d
0x180006b62  mov     [rsi+10h], rbx
0x180006b66  lea     rax, [rsi+8]
0x180006b6a  mov     [rsi+18h], rbx
0x180006b6e  lea     rcx, [rsi+10h]
0x180006b72  mov     dword ptr [rsi], 110102h
0x180006b78  lea     r12, [rsi+18h]
0x180006b7c  mov     [rax], r13d
0x180006b7f  lea     r9d, [r8-6]; dwFlags
0x180006b83  mov     [rbp+40h+var_90], rax
0x180006b87  mov     rdx, r12; pbBuffer
0x180006b8a  sbb     eax, eax
0x180006b8c  mov     [rbp+40h+var_A0], rcx
0x180006b90  not     eax
0x180006b92  mov     dword ptr [rsi+4], 0FFFFFFFFh
0x180006b99  xor     ecx, ecx; hAlgorithm
0x180006b9b  mov     [rsi+0Ch], eax
0x180006b9e  mov     [rbp+40h+var_98], r8
0x180006ba2  mov     [rbp+40h+var_A8], r8
0x180006ba6  call    cs:__imp_BCryptGenRandom
0x180006bac  xor     r13d, r13d
0x180006baf  mov     ebx, eax
0x180006bb1  test    eax, eax
0x180006bb3  jns     short loc_180006BD5
0x180006bb5  mov     edx, eax; char *
0x180006bb7  lea     rcx, aRandomfillConf; "RandomFill(confounderBuffer)"
0x180006bbe  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006bc3  mov     [rdi], r13
0x180006bc6  mov     [rdi+8], r13
0x180006bca  mov     [rdi+10h], ebx
0x180006bcd  mov     rcx, rsi
0x180006bd0  jmp     loc_180006E8B
0x180006bd5  mov     r8, [rbp+40h+arg_20]
0x180006bd9  lea     r9, ?$S33@?1??CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_K0_N2@Z@4U53@B
0x180006be0  lea     rdx, [rsp+140h+var_F0]
0x180006be5  mov     rcx, r14
0x180006be8  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006bed  mov     ebx, dword ptr [rsp+140h+var_E0]
0x180006bf1  test    ebx, ebx
0x180006bf3  jns     short loc_180006C29
0x180006bf5  mov     edx, ebx; char *
0x180006bf7  lea     rcx, aKsign; "Ksign"
0x180006bfe  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006c03  mov     [rdi], r13
0x180006c06  mov     [rdi+8], r13
0x180006c0a  mov     [rdi+10h], ebx
0x180006c0d  mov     rcx, [rsp+140h+var_E8]; void *
0x180006c12  test    rcx, rcx
0x180006c15  jz      short loc_180006C1E
0x180006c17  xor     edx, edx; struct std::nothrow_t *
0x180006c19  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006c1e  test    rsi, rsi
0x180006c21  jz      loc_180006E92
0x180006c27  jmp     short loc_180006BCD
0x180006c29  movups  xmm0, xmmword ptr cs:?$S34@?1??CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_K0_N2@Z@4U53@B
0x180006c30  mov     eax, 8
0x180006c35  mov     [rbp+40h+var_58], rsi
0x180006c39  mov     [rbp+40h+var_60], rax
0x180006c3d  lea     rdx, [rbp+40h+var_70]
0x180006c41  mov     [rbp+40h+var_50], rax
0x180006c45  lea     rcx, [rsp+140h+var_D8]
0x180006c4a  mov     rax, [rbp+40h+arg_10]
0x180006c4e  movdqu  [rbp+40h+var_70], xmm0
0x180006c53  mov     [rbp+40h+var_48], r12
0x180006c57  movups  xmm0, xmmword ptr [rax]
0x180006c5a  movdqu  [rbp+40h+var_40], xmm0
0x180006c5f  call    ??$Concatenate@$03@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@0@U?$array@$$CBUReadOnlyBinary@Kerb3961@@$03@utl@@@Z; Kerb3961::Concatenate<4>(utl::array<Kerb3961::ReadOnlyBinary const,4>)
0x180006c64  mov     ebx, dword ptr [rsp+140h+var_C8]
0x180006c68  test    ebx, ebx
0x180006c6a  jns     short loc_180006C9E
0x180006c6c  mov     edx, ebx; char *
0x180006c6e  lea     rcx, aSignbuffer; "signBuffer"
0x180006c75  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006c7a  mov     [rdi], r13
0x180006c7d  mov     [rdi+8], r13
0x180006c81  mov     [rdi+10h], ebx
0x180006c84  mov     rcx, [rsp+140h+var_D0]; void *
0x180006c89  test    rcx, rcx
0x180006c8c  jz      loc_180006C0D
0x180006c92  xor     edx, edx; struct std::nothrow_t *
0x180006c94  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006c99  jmp     loc_180006C0D
0x180006c9e  lea     r8, [rsp+140h+var_D8]
0x180006ca3  mov     rcx, r14
0x180006ca6  lea     rdx, [rsp+140h+var_120]
0x180006cab  call    ?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)
0x180006cb0  mov     ebx, dword ptr [rsp+140h+var_110]
0x180006cb4  test    ebx, ebx
0x180006cb6  jns     short loc_180006CE3
0x180006cb8  mov     edx, ebx; char *
0x180006cba  lea     rcx, aSgnCksum; "Sgn_Cksum"
0x180006cc1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006cc6  mov     [rdi], r13
0x180006cc9  mov     [rdi+8], r13
0x180006ccd  mov     [rdi+10h], ebx
0x180006cd0  mov     rcx, [rsp+140h+var_118]; void *
0x180006cd5  test    rcx, rcx
0x180006cd8  jz      short loc_180006C84
0x180006cda  xor     edx, edx; struct std::nothrow_t *
0x180006cdc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006ce1  jmp     short loc_180006C84
0x180006ce3  lea     r9, [rsp+140h+var_120]
0x180006ce8  mov     rcx, r14
0x180006ceb  lea     r8, [rsp+140h+var_F0]
0x180006cf0  lea     rdx, [rbp+40h+var_88]
0x180006cf4  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006cf9  mov     rcx, [rsp+140h+var_118]; void *
0x180006cfe  mov     rbx, rax
0x180006d01  test    rcx, rcx
0x180006d04  jz      short loc_180006D0D
0x180006d06  xor     edx, edx; struct std::nothrow_t *
0x180006d08  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006d0d  mov     rcx, [rbx]
0x180006d10  mov     r12d, 0C0000001h
0x180006d16  mov     [rsp+140h+var_120], rcx
0x180006d1b  mov     rcx, [rbx+8]
0x180006d1f  mov     [rbx], r13
0x180006d22  mov     [rsp+140h+var_118], rcx
0x180006d27  mov     eax, [rbx+10h]
0x180006d2a  mov     [rbx+8], r13
0x180006d2e  mov     dword ptr [rsp+140h+var_110], eax
0x180006d32  mov     [rbx+10h], r12d
0x180006d36  mov     rcx, [rbp+40h+var_80]; void *
0x180006d3a  test    rcx, rcx
0x180006d3d  jz      short loc_180006D46
0x180006d3f  xor     edx, edx; struct std::nothrow_t *
0x180006d41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006d46  mov     ebx, dword ptr [rsp+140h+var_110]
0x180006d4a  test    ebx, ebx
0x180006d4c  js      loc_180006CB8
0x180006d52  mov     rax, [rsp+140h+var_118]
0x180006d57  lea     r9, ?$S36@?1??CommonWrapPlain@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@_K0_N2@Z@4U53@B
0x180006d5e  mov     r8, [rbp+40h+arg_20]
0x180006d62  lea     rdx, [rsp+140h+var_108]
0x180006d67  mov     rcx, [rax]
0x180006d6a  mov     [rsi+10h], rcx
0x180006d6e  mov     rcx, r14
0x180006d71  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006d76  mov     ebx, dword ptr [rsp+140h+var_F8]
0x180006d7a  test    ebx, ebx
0x180006d7c  jns     short loc_180006DB0
0x180006d7e  lea     rcx, aKseq; "Kseq"
0x180006d85  mov     edx, ebx; char *
0x180006d87  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006d8c  mov     rcx, [rsp+140h+var_100]; void *
0x180006d91  mov     [rdi], r13
0x180006d94  mov     [rdi+8], r13
0x180006d98  mov     [rdi+10h], ebx
0x180006d9b  test    rcx, rcx
0x180006d9e  jz      loc_180006CD0
0x180006da4  xor     edx, edx; struct std::nothrow_t *
0x180006da6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006dab  jmp     loc_180006CD0
0x180006db0  lea     r9, [rbp+40h+var_A8]
0x180006db4  mov     rcx, r14
0x180006db7  lea     r8, [rsp+140h+var_108]
0x180006dbc  lea     rdx, [rbp+40h+var_88]
0x180006dc0  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180006dc5  mov     rcx, [rsp+140h+var_100]; void *
0x180006dca  mov     rbx, rax
0x180006dcd  test    rcx, rcx
0x180006dd0  jz      short loc_180006DD9
0x180006dd2  xor     edx, edx; struct std::nothrow_t *
0x180006dd4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006dd9  mov     rcx, [rbx]
0x180006ddc  mov     [rsp+140h+var_108], rcx
0x180006de1  mov     rcx, [rbx+8]
0x180006de5  mov     [rbx], r13
0x180006de8  mov     [rsp+140h+var_100], rcx
0x180006ded  mov     eax, [rbx+10h]
0x180006df0  mov     [rbx+8], r13
0x180006df4  mov     dword ptr [rsp+140h+var_F8], eax
0x180006df8  mov     [rbx+10h], r12d
0x180006dfc  mov     rcx, [rbp+40h+var_80]; void *
0x180006e00  test    rcx, rcx
0x180006e03  jz      short loc_180006E0C
0x180006e05  xor     edx, edx; struct std::nothrow_t *
0x180006e07  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006e0c  mov     ebx, dword ptr [rsp+140h+var_F8]
0x180006e10  test    ebx, ebx
0x180006e12  js      loc_180006D7E
0x180006e18  lea     r9, [rbp+40h+var_98]
0x180006e1c  mov     rcx, r14
0x180006e1f  lea     r8, [rsp+140h+var_108]
0x180006e24  lea     rdx, [rbp+40h+arg_0]
0x180006e28  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x180006e2d  mov     ebx, [rax]
0x180006e2f  test    ebx, ebx
0x180006e31  jns     short loc_180006E3F
0x180006e33  lea     rcx, aRc4dataKseqSeq; "RC4Data(Kseq, sequenceBuffer)"
0x180006e3a  jmp     loc_180006D85
0x180006e3f  mov     rcx, [rsp+140h+var_100]; void *
0x180006e44  mov     rax, [rbp+40h+var_C0]
0x180006e48  mov     [rdi+10h], r15d
0x180006e4c  mov     [rdi], rax
0x180006e4f  mov     [rdi+8], rsi
0x180006e53  test    rcx, rcx
0x180006e56  jz      short loc_180006E5F
0x180006e58  xor     edx, edx; struct std::nothrow_t *
0x180006e5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006e5f  mov     rcx, [rsp+140h+var_118]; void *
0x180006e64  test    rcx, rcx
0x180006e67  jz      short loc_180006E70
0x180006e69  xor     edx, edx; struct std::nothrow_t *
0x180006e6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006e70  mov     rcx, [rsp+140h+var_D0]; void *
0x180006e75  test    rcx, rcx
0x180006e78  jz      short loc_180006E81
0x180006e7a  xor     edx, edx; struct std::nothrow_t *
0x180006e7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006e81  mov     rcx, [rsp+140h+var_E8]; void *
0x180006e86  test    rcx, rcx
0x180006e89  jz      short loc_180006E92
0x180006e8b  xor     edx, edx; struct std::nothrow_t *
0x180006e8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006e92  mov     rbx, [rsp+140h+arg_8]
0x180006e9a  mov     rax, rdi
0x180006e9d  add     rsp, 110h
0x180006ea4  pop     r15
0x180006ea6  pop     r14
0x180006ea8  pop     r13
0x180006eaa  pop     r12
0x180006eac  pop     rdi
0x180006ead  pop     rsi
0x180006eae  pop     rbp
0x180006eaf  retn
0x180006eb0  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x180006eb7  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
