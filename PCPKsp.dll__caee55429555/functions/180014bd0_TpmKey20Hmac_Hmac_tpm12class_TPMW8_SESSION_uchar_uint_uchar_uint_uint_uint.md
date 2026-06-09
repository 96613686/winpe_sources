# TpmKey20Hmac::Hmac(tpm12class::TPMW8_SESSION *,uchar *,uint,uchar *,uint,uint *,uint)

- ea: `0x180014bd0`
- end: `0x180015657`
- name: `?Hmac@TpmKey20Hmac@@QEAAJPEAVTPMW8_SESSION@tpm12class@@PEAEI1IPEAII@Z`
- size: `2695`
- prototype: `__int64 __usercall@<rax>(TpmKey20Hmac *__hidden this@<rcx>, struct tpm12class::TPMW8_SESSION *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800116d0`
- `0x18006f330`
- `0x180070ca0`

## callees

- `0x18000d2fc`
- `0x18000dc90`
- `0x18000ea60`
- `0x180010c90`
- `0x1800133c4`
- `0x180014830`
- `0x180014a60`
- `0x180014bd0`
- `0x1800157c0`
- `0x180043260`
- `0x18005bfc0`
- `0x1800769e0`
- `0x180076e70`
- `0x180076fca`
- `0x180077034`
- `0x18007704c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014c74`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001536a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014c74`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001536a`

## string_xrefs

- `0x180014d2f`: `HmacWithHmacCommand`
- `0x1800153fb`: `HmacWithHmacStartCommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TpmKey20Hmac::Hmac(
        TpmKey20Hmac *this,
        struct tpm12class::TPMW8_SESSION *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int Size,
        unsigned int *a7,
        unsigned int a8)
{
  unsigned __int64 v8; // r15
  int v13; // ebx
  int KeyInTpm; // eax
  unsigned int v15; // edi
  KspFlowLogger *v16; // r13
  char *v17; // rdi
  KspFlowLogger *v18; // rcx
  int v19; // r14d
  _QWORD *v20; // rbx
  tpm12class::TPMW8_AUTH_PROVIDER *v21; // rax
  __int64 v22; // rax
  size_t v23; // rsi
  const void *v24; // r14
  int v25; // eax
  unsigned __int64 v26; // rbx
  void *v27; // rdi
  __int64 v28; // rdx
  unsigned __int64 v29; // r9
  size_t v30; // rcx
  char *i; // rax
  unsigned __int64 v32; // rdx
  char *j; // rcx
  void *v34; // rdi
  void *v35; // rdi
  unsigned int v36; // [rsp+20h] [rbp-E0h]
  unsigned int v37; // [rsp+40h] [rbp-C0h]
  int *v38[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v39[3]; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+88h] [rbp-78h]
  __int64 v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+98h] [rbp-68h]
  char v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A8h] [rbp-58h]
  __int64 v45; // [rsp+ACh] [rbp-54h]
  __int64 v46; // [rsp+B4h] [rbp-4Ch]
  __int64 v47; // [rsp+BCh] [rbp-44h]
  int v48; // [rsp+C4h] [rbp-3Ch]
  const int *v49; // [rsp+C8h] [rbp-38h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  int v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+E8h] [rbp-18h]
  __int64 v54; // [rsp+F0h] [rbp-10h]
  char v55; // [rsp+F8h] [rbp-8h]
  __int16 v56; // [rsp+100h] [rbp+0h]
  __int64 v57; // [rsp+108h] [rbp+8h]
  __int64 v58; // [rsp+110h] [rbp+10h]
  struct tpm12class::TPMW8_SESSION *v59; // [rsp+118h] [rbp+18h]
  __int128 v60; // [rsp+120h] [rbp+20h]
  int v61; // [rsp+130h] [rbp+30h]
  _QWORD v62[3]; // [rsp+138h] [rbp+38h] BYREF
  int v63; // [rsp+150h] [rbp+50h]
  __int64 v64; // [rsp+158h] [rbp+58h]
  __int64 v65; // [rsp+160h] [rbp+60h]
  char v66; // [rsp+168h] [rbp+68h]
  unsigned __int16 v67; // [rsp+170h] [rbp+70h]
  void *Block; // [rsp+178h] [rbp+78h]
  _QWORD v69[3]; // [rsp+180h] [rbp+80h] BYREF
  int v70; // [rsp+198h] [rbp+98h]
  __int64 v71; // [rsp+1A0h] [rbp+A0h]
  __int64 v72; // [rsp+1A8h] [rbp+A8h]
  char v73; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 v74; // [rsp+1B8h] [rbp+B8h]
  void *v75; // [rsp+1C0h] [rbp+C0h]
  __int16 v76; // [rsp+1C8h] [rbp+C8h]
  const int *v77; // [rsp+1D0h] [rbp+D0h]
  __int64 v78; // [rsp+1D8h] [rbp+D8h]
  __int64 v79; // [rsp+1E0h] [rbp+E0h]
  int v80; // [rsp+1E8h] [rbp+E8h]
  __int64 v81; // [rsp+1F0h] [rbp+F0h]
  __int64 v82; // [rsp+1F8h] [rbp+F8h]
  char v83; // [rsp+200h] [rbp+100h]
  unsigned __int16 v84; // [rsp+208h] [rbp+108h]
  void *v85; // [rsp+210h] [rbp+110h]
  char v86; // [rsp+218h] [rbp+118h]
  int *v87[12]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v8 = a4;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v38, L"TpmKey20Hmac::Hmac", 1);
  if ( (Size == 0) != (a5 == 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)0x80290406LL,
      v36);
    KspFunctionLogger::~KspFunctionLogger(v38);
    return 2150171654LL;
  }
  if ( !a3 || (unsigned int)v8 > 0x400 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)0x80290403LL,
      v36);
    KspFunctionLogger::~KspFunctionLogger(v38);
    return 2150171651LL;
  }
  if ( a8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)0x80290404LL,
      v36);
    KspFunctionLogger::~KspFunctionLogger(v38);
    return 2150171652LL;
  }
  if ( !a5 )
  {
    if ( a7 )
      *a7 = 32;
    goto LABEL_10;
  }
  KeyInTpm = TpmKey20::LoadKeyInTpm(this);
  v15 = KeyInTpm;
  if ( KeyInTpm < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)(unsigned int)KeyInTpm,
      v36);
    KspFunctionLogger::~KspFunctionLogger(v38);
    return v15;
  }
  if ( *((_QWORD *)this + 12) && *((_DWORD *)this + 120) && !*((_DWORD *)this + 140) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
      (const char *)0x80290408LL,
      v36);
    KspFunctionLogger::~KspFunctionLogger(v38);
    return 2150171656LL;
  }
  v16 = (TpmKey20Hmac *)((char *)this + 56);
  v17 = (char *)this + 320;
  v18 = (TpmKey20Hmac *)((char *)this + 56);
  if ( !*((_BYTE *)this + 1024) )
  {
    KspFlowLogger::LogTransition(v18, "HmacWithHmacStartCommand", 0, 0);
    *((_BYTE *)this + 81) = 0;
    v13 = HmacWithTpm2HmacStart(
            *((_DWORD *)this + 116),
            (TpmKey20Hmac *)((char *)this + 320),
            a2,
            a3,
            v8,
            a5,
            Size,
            a7,
            v37);
    goto LABEL_9;
  }
  KspFlowLogger::LogTransition(v18, "HmacWithHmacCommand", 0, 0);
  *((_BYTE *)this + 81) = 0;
  v19 = *((_DWORD *)this + 116);
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v87, L"HmacWithTpm2Hmac", 1);
  if ( a7 )
    *a7 = 32;
  v39[1] = 0;
  v39[2] = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v49 = &tpm12class::TPMW82B_BUFFER::`vftable';
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v60 = 0;
  v45 = 0;
  v58 = 0;
  v44 = -2147450878;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v39[0] = &tpm12class::TPMW8_HMAC::`vftable';
  v62[1] = 0;
  v62[2] = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v62[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v67 = 0;
  Block = 0;
  v69[1] = 0;
  v69[2] = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v69[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  v74 = 0;
  v75 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v77 = &tpm12class::TPMW82B_BUFFER::`vftable';
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v20 = operator new(0x318u);
  *v20 = &tpm12class::TPMW8_SESSION::`vftable';
  v20[4] = 0;
  v20[5] = 0;
  *((_DWORD *)v20 + 12) = 0;
  v20[7] = 0;
  v20[8] = 0;
  *((_BYTE *)v20 + 72) = 0;
  v20[3] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 40) = 0;
  v20[11] = 0;
  v20[13] = 0;
  v20[14] = 0;
  *((_DWORD *)v20 + 30) = 0;
  v20[16] = 0;
  v20[17] = 0;
  *((_BYTE *)v20 + 144) = 0;
  v20[12] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 76) = 0;
  v20[20] = 0;
  v20[22] = 0;
  v20[23] = 0;
  *((_DWORD *)v20 + 48) = 0;
  v20[25] = 0;
  v20[26] = 0;
  *((_BYTE *)v20 + 216) = 0;
  v20[21] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 112) = 0;
  v20[29] = 0;
  v20[31] = 0;
  v20[32] = 0;
  *((_DWORD *)v20 + 66) = 0;
  v20[34] = 0;
  v20[35] = 0;
  *((_BYTE *)v20 + 288) = 0;
  v20[30] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 148) = 0;
  v20[38] = 0;
  v20[40] = 0;
  v20[41] = 0;
  *((_DWORD *)v20 + 84) = 0;
  v20[43] = 0;
  v20[44] = 0;
  *((_BYTE *)v20 + 360) = 0;
  v20[39] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 184) = 0;
  v20[47] = 0;
  v20[49] = 0;
  v20[50] = 0;
  *((_DWORD *)v20 + 102) = 0;
  v20[52] = 0;
  v20[53] = 0;
  *((_BYTE *)v20 + 432) = 0;
  v20[48] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 220) = 0;
  v20[56] = 0;
  v20[58] = 0;
  v20[59] = 0;
  *((_DWORD *)v20 + 120) = 0;
  v20[61] = 0;
  v20[62] = 0;
  *((_BYTE *)v20 + 504) = 0;
  v20[57] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 256) = 0;
  v20[65] = 0;
  v20[67] = 0;
  v20[68] = 0;
  *((_DWORD *)v20 + 138) = 0;
  v20[70] = 0;
  v20[71] = 0;
  *((_BYTE *)v20 + 576) = 0;
  v20[66] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 292) = 0;
  v20[74] = 0;
  v20[77] = 0;
  v20[78] = 0;
  *((_DWORD *)v20 + 158) = 0;
  v20[80] = 0;
  v20[81] = 0;
  *((_BYTE *)v20 + 656) = 0;
  v20[76] = &tpm12class::TPMW82B_BUFFER::`vftable';
  *((_WORD *)v20 + 332) = 0;
  v20[84] = 0;
  v20[86] = 0;
  v20[87] = 0;
  *((_DWORD *)v20 + 176) = 0;
  v20[89] = 0;
  v20[90] = 0;
  *((_BYTE *)v20 + 728) = 0;
  v20[85] = &tpm12class::TPMW8T_SYM_DEF::`vftable';
  *((_DWORD *)v20 + 184) = 16;
  *((_DWORD *)v20 + 185) = 1048592;
  *((_WORD *)v20 + 372) = 16;
  v20[97] = 0;
  v20[1] = 0;
  v20[94] = 0;
  *((_DWORD *)v20 + 190) = 720896;
  *((_DWORD *)v20 + 4) = 0;
  *((_DWORD *)v20 + 151) = 1073741831;
  *((_DWORD *)v20 + 192) = 1073741831;
  *((_BYTE *)v20 + 764) = 0;
  *((_BYTE *)v20 + 784) = 0;
  v21 = (tpm12class::TPMW8_AUTH_PROVIDER *)operator new(0x178u);
  v22 = tpm12class::TPMW8_AUTH_PROVIDER::TPMW8_AUTH_PROVIDER(v21);
  v20[97] = v22;
  if ( v22 )
    *(_WORD *)(v22 + 370) = *((_WORD *)v20 + 381);
  v59 = (struct tpm12class::TPMW8_SESSION *)v20;
  LODWORD(v58) = 341;
  if ( a2 )
  {
    v59 = a2;
    v86 = 1;
  }
  v61 = v19;
  if ( !v17 )
  {
    v13 = -2147024809;
    goto LABEL_48;
  }
  v23 = *((unsigned __int16 *)v17 + 28);
  v24 = (const void *)*((_QWORD *)v17 + 8);
  if ( !Block )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(v62[0] + 24LL))(v62, 0);
    if ( v13 < 0 )
      goto LABEL_30;
    if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
    Block = operator new(v23);
    memset_0(Block, 0, v23);
    goto LABEL_29;
  }
  if ( v23 > v67 )
  {
    v34 = operator new(*((unsigned __int16 *)v17 + 28));
    memset_0(v34, 0, v23);
    memcpy_0(v34, Block, v67);
    v13 = tpm12class::TPMW82B_BUFFER::Empty((tpm12class::TPMW82B_BUFFER *)v62);
    if ( v13 < 0 )
    {
LABEL_30:
      if ( v13 >= 0 )
        goto LABEL_31;
LABEL_48:
      v28 = 686;
      goto LABEL_49;
    }
    Block = v34;
LABEL_29:
    v67 = v23;
    goto LABEL_30;
  }
  v30 = v67 - v23;
  for ( i = (char *)Block + v23; v30; --v30 )
    *i++ = 0;
  v67 = v23;
LABEL_31:
  memcpy_0(Block, v24, v67);
  if ( !v75 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(v69[0] + 24LL))(v69, 0);
    if ( v13 < 0 )
    {
LABEL_37:
      if ( v13 >= 0 )
        goto LABEL_38;
      v28 = 687;
LABEL_49:
      v29 = (unsigned int)v13;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
        (const char *)v29,
        v36);
      tpm12class::TPMW8_HMAC::~TPMW8_HMAC((tpm12class::TPMW8_HMAC *)v39);
      goto LABEL_8;
    }
    if ( v75 )
    {
      operator delete(v75);
      v75 = 0;
    }
    v75 = operator new(v8);
    memset_0(v75, 0, v8);
LABEL_36:
    v74 = v8;
    goto LABEL_37;
  }
  if ( v8 > v74 )
  {
    v35 = operator new(v8);
    memset_0(v35, 0, v8);
    memcpy_0(v35, v75, v74);
    v13 = tpm12class::TPMW82B_BUFFER::Empty((tpm12class::TPMW82B_BUFFER *)v69);
    if ( v13 < 0 )
      goto LABEL_37;
    v75 = v35;
    goto LABEL_36;
  }
  v32 = v74 - v8;
  for ( j = (char *)v75 + v8; v32; --v32 )
    *j++ = 0;
  v74 = v8;
LABEL_38:
  memcpy_0(v75, a3, v74);
  v76 = 11;
  v25 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v39, 0);
  v13 = v25;
  if ( v25 < 0 )
  {
    v29 = (unsigned int)v25;
    v28 = 689;
    goto LABEL_50;
  }
  v26 = v84;
  if ( !v84 )
    goto LABEL_7;
  v27 = v85;
  if ( v85 && Size >= (unsigned __int64)v84 )
  {
    memcpy_0(a5, v85, v84);
    goto LABEL_7;
  }
  memset_0(a5, 0, Size);
  if ( !v27 )
  {
    *(_DWORD *)_o__errno() = 22;
    goto LABEL_6;
  }
  if ( Size < v26 )
  {
    *(_DWORD *)_o__errno() = 34;
LABEL_6:
    invalid_parameter_noinfo();
  }
LABEL_7:
  tpm12class::TPMW8_HMAC::~TPMW8_HMAC((tpm12class::TPMW8_HMAC *)v39);
  v13 = 0;
LABEL_8:
  KspFunctionLogger::~KspFunctionLogger(v87);
LABEL_9:
  if ( v13 >= 0 )
  {
LABEL_10:
    KspFunctionLogger::~KspFunctionLogger(v38);
    return 0;
  }
  KspFlowLogger::LogTransition(v16, "FailedToHmac", 255, v13);
  *((_BYTE *)v16 + 25) = 1;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x324,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20hmac.cpp",
    (const char *)(unsigned int)v13,
    v36);
  KspFunctionLogger::~KspFunctionLogger(v38);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180014bd0  mov     [rsp-8+Src], r8
0x180014bd5  push    rbp
0x180014bd6  push    rbx
0x180014bd7  push    rsi
0x180014bd8  push    rdi
0x180014bd9  push    r12
0x180014bdb  push    r13
0x180014bdd  push    r14
0x180014bdf  push    r15
0x180014be1  lea     rbp, [rsp-148h]
0x180014be9  sub     rsp, 248h
0x180014bf0  mov     r15d, r9d
0x180014bf3  mov     r14, r8
0x180014bf6  mov     rsi, rdx
0x180014bf9  mov     rbx, rcx
0x180014bfc  mov     r8b, 1; bool
0x180014bff  lea     rdx, aTpmkey20hmacHm; "TpmKey20Hmac::Hmac"
0x180014c06  lea     rcx, [rsp+280h+var_230]; this
0x180014c0b  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180014c10  nop
0x180014c11  xor     r10d, r10d
0x180014c14  mov     r12, [rbp+180h+arg_20]
0x180014c1b  test    r12, r12
0x180014c1e  setz    r10b
0x180014c22  xor     eax, eax
0x180014c24  cmp     dword ptr [rbp+180h+Size], eax
0x180014c2a  setz    al
0x180014c2d  cmp     eax, r10d
0x180014c30  jnz     loc_1800153AD
0x180014c36  test    r14, r14
0x180014c39  jnz     loc_180014CCE
0x180014c3f  mov     rcx, [rbp+188h]; this
0x180014c46  mov     r9d, 80290403h; char *
0x180014c4c  lea     r8, aOnecoreBaseNgs_29; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180014c53  mov     edx, 2F0h; void *
0x180014c58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c5d  nop
0x180014c5e  lea     rcx, [rsp+280h+var_230]; this
0x180014c63  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180014c68  mov     eax, 80290403h
0x180014c6d  jmp     short loc_180014CB9
0x180014c6f  cmp     rsi, rbx
0x180014c72  jnb     short loc_180014C8C
0x180014c74  call    cs:__imp__o__errno
0x180014c7b  nop     dword ptr [rax+rax+00h]
0x180014c80  mov     dword ptr [rax], 22h ; '"'
0x180014c86  call    _invalid_parameter_noinfo
0x180014c8b  nop
0x180014c8c  lea     rcx, [rsp+280h+var_210]; this
0x180014c91  call    ??1TPMW8_HMAC@tpm12class@@UEAA@XZ; tpm12class::TPMW8_HMAC::~TPMW8_HMAC(void)
0x180014c96  nop
0x180014c97  xor     ebx, ebx
0x180014c99  lea     rcx, [rbp+180h+var_60]; this
0x180014ca0  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180014ca5  test    ebx, ebx
0x180014ca7  js      loc_180015610
0x180014cad  lea     rcx, [rsp+280h+var_230]; this
0x180014cb2  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180014cb7  xor     eax, eax
0x180014cb9  add     rsp, 248h
0x180014cc0  pop     r15
0x180014cc2  pop     r14
0x180014cc4  pop     r13
0x180014cc6  pop     r12
0x180014cc8  pop     rdi
0x180014cc9  pop     rsi
0x180014cca  pop     rbx
0x180014ccb  pop     rbp
0x180014ccc  retn
0x180014cce  cmp     r15d, 400h
0x180014cd5  ja      loc_180014C3F
0x180014cdb  cmp     [rbp+180h+arg_38], 0
0x180014ce2  jnz     loc_1800154EA
0x180014ce8  test    r12, r12
0x180014ceb  jz      loc_1800153E0
0x180014cf1  mov     rcx, rbx; this
0x180014cf4  call    ?LoadKeyInTpm@TpmKey20@@IEAAJXZ; TpmKey20::LoadKeyInTpm(void)
0x180014cf9  mov     edi, eax
0x180014cfb  test    eax, eax
0x180014cfd  js      loc_180015479
0x180014d03  cmp     qword ptr [rbx+60h], 0
0x180014d08  jnz     loc_180015307
0x180014d0e  lea     r13, [rbx+38h]
0x180014d12  lea     rdi, [rbx+140h]
0x180014d19  xor     r9d, r9d; int
0x180014d1c  xor     r8d, r8d; signed __int8
0x180014d1f  mov     rcx, r13; this
0x180014d22  cmp     [rbx+400h], r8b
0x180014d29  jz      loc_1800153FB
0x180014d2f  lea     rdx, aHmacwithhmacco; "HmacWithHmacCommand"
0x180014d36  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180014d3b  mov     byte ptr [r13+19h], 0
0x180014d40  mov     r14d, [rbx+1D0h]
0x180014d47  mov     r8b, 1; bool
0x180014d4a  lea     rdx, aHmacwithtpm2hm_0; "HmacWithTpm2Hmac"
0x180014d51  lea     rcx, [rbp+180h+var_60]; this
0x180014d58  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180014d5d  nop
0x180014d5e  mov     rax, [rbp+180h+arg_30]
0x180014d65  test    rax, rax
0x180014d68  jz      short loc_180014D70
0x180014d6a  mov     dword ptr [rax], 20h ; ' '
0x180014d70  xor     edx, edx
0x180014d72  mov     [rsp+280h+var_208], rdx
0x180014d77  mov     [rbp+180h+var_200], rdx
0x180014d7b  mov     [rbp+180h+var_1F8], edx
0x180014d7e  mov     [rbp+180h+var_1F0], rdx
0x180014d82  mov     [rbp+180h+var_1E8], rdx
0x180014d86  mov     [rbp+180h+var_1E0], dl
0x180014d89  mov     [rbp+180h+var_1B0], rdx
0x180014d8d  mov     [rbp+180h+var_1A8], rdx
0x180014d91  mov     [rbp+180h+var_1A0], edx
0x180014d94  mov     [rbp+180h+var_198], rdx
0x180014d98  mov     [rbp+180h+var_190], rdx
0x180014d9c  mov     [rbp+180h+var_188], dl
0x180014d9f  lea     rcx, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x180014da6  mov     [rbp+180h+var_1B8], rcx
0x180014daa  mov     [rbp+180h+var_180], dx
0x180014dae  mov     [rbp+180h+var_178], rdx
0x180014db2  mov     [rbp+180h+var_168], rdx
0x180014db6  xorps   xmm0, xmm0
0x180014db9  movdqa  [rbp+180h+var_160], xmm0
0x180014dbe  mov     [rbp+180h+var_1D4], rdx
0x180014dc2  mov     [rbp+180h+var_170], rdx
0x180014dc6  mov     [rbp+180h+var_1D8], 80008002h
0x180014dcd  mov     [rbp+180h+var_1CC], rdx
0x180014dd1  mov     [rbp+180h+var_1C4], rdx
0x180014dd5  mov     [rbp+180h+var_1BC], edx
0x180014dd8  lea     rax, ??_7TPMW8_HMAC@tpm12class@@6B@; const tpm12class::TPMW8_HMAC::`vftable'
0x180014ddf  mov     [rsp+280h+var_210], rax
0x180014de4  mov     [rbp+180h+var_140], rdx
0x180014de8  mov     [rbp+180h+var_138], rdx
0x180014dec  mov     [rbp+180h+var_130], edx
0x180014def  mov     [rbp+180h+var_128], rdx
0x180014df3  mov     [rbp+180h+var_120], rdx
0x180014df7  mov     [rbp+180h+var_118], dl
0x180014dfa  mov     [rbp+180h+var_148], rcx
0x180014dfe  mov     [rbp+180h+var_110], dx
0x180014e02  mov     [rbp+180h+Block], rdx
0x180014e06  mov     [rbp+180h+var_F8], rdx
0x180014e0d  mov     [rbp+180h+var_F0], rdx
0x180014e14  mov     [rbp+180h+var_E8], edx
0x180014e1a  mov     [rbp+180h+var_E0], rdx
0x180014e21  mov     [rbp+180h+var_D8], rdx
0x180014e28  mov     [rbp+180h+var_D0], dl
0x180014e2e  mov     [rbp+180h+var_100], rcx
0x180014e35  mov     [rbp+180h+var_C8], dx
0x180014e3c  mov     [rbp+180h+var_C0], rdx
0x180014e43  mov     [rbp+180h+var_A8], rdx
0x180014e4a  mov     [rbp+180h+var_A0], rdx
0x180014e51  mov     [rbp+180h+var_98], edx
0x180014e57  mov     [rbp+180h+var_90], rdx
0x180014e5e  mov     [rbp+180h+var_88], rdx
0x180014e65  mov     [rbp+180h+var_80], dl
0x180014e6b  mov     [rbp+180h+var_B0], rcx
0x180014e72  mov     [rbp+180h+var_78], dx
0x180014e79  mov     [rbp+180h+var_70], rdx
0x180014e80  mov     [rbp+180h+var_68], dl
0x180014e86  mov     ecx, 318h; Size
0x180014e8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014e90  mov     rbx, rax
0x180014e93  lea     rax, ??_7TPMW8_SESSION@tpm12class@@6B@; const tpm12class::TPMW8_SESSION::`vftable'
0x180014e9a  mov     [rbx], rax
0x180014e9d  xor     r8d, r8d
0x180014ea0  mov     [rbx+20h], r8
0x180014ea4  mov     [rbx+28h], r8
0x180014ea8  mov     [rbx+30h], r8d
0x180014eac  mov     [rbx+38h], r8
0x180014eb0  mov     [rbx+40h], r8
0x180014eb4  mov     [rbx+48h], r8b
0x180014eb8  lea     rdx, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x180014ebf  mov     [rbx+18h], rdx
0x180014ec3  mov     [rbx+50h], r8w
0x180014ec8  mov     [rbx+58h], r8
0x180014ecc  mov     [rbx+68h], r8
0x180014ed0  mov     [rbx+70h], r8
0x180014ed4  mov     [rbx+78h], r8d
0x180014ed8  mov     [rbx+80h], r8
0x180014edf  mov     [rbx+88h], r8
0x180014ee6  mov     [rbx+90h], r8b
0x180014eed  mov     [rbx+60h], rdx
0x180014ef1  mov     [rbx+98h], r8w
0x180014ef9  mov     [rbx+0A0h], r8
0x180014f00  mov     [rbx+0B0h], r8
0x180014f07  mov     [rbx+0B8h], r8
0x180014f0e  mov     [rbx+0C0h], r8d
0x180014f15  mov     [rbx+0C8h], r8
0x180014f1c  mov     [rbx+0D0h], r8
0x180014f23  mov     [rbx+0D8h], r8b
0x180014f2a  mov     [rbx+0A8h], rdx
0x180014f31  mov     [rbx+0E0h], r8w
0x180014f39  mov     [rbx+0E8h], r8
0x180014f40  mov     [rbx+0F8h], r8
0x180014f47  mov     [rbx+100h], r8
0x180014f4e  mov     [rbx+108h], r8d
0x180014f55  mov     [rbx+110h], r8
0x180014f5c  mov     [rbx+118h], r8
0x180014f63  mov     [rbx+120h], r8b
0x180014f6a  mov     [rbx+0F0h], rdx
0x180014f71  mov     [rbx+128h], r8w
0x180014f79  mov     [rbx+130h], r8
0x180014f80  mov     [rbx+140h], r8
0x180014f87  mov     [rbx+148h], r8
0x180014f8e  mov     [rbx+150h], r8d
0x180014f95  mov     [rbx+158h], r8
0x180014f9c  mov     [rbx+160h], r8
0x180014fa3  mov     [rbx+168h], r8b
0x180014faa  mov     [rbx+138h], rdx
0x180014fb1  mov     [rbx+170h], r8w
0x180014fb9  mov     [rbx+178h], r8
0x180014fc0  mov     [rbx+188h], r8
0x180014fc7  mov     [rbx+190h], r8
0x180014fce  mov     [rbx+198h], r8d
0x180014fd5  mov     [rbx+1A0h], r8
0x180014fdc  mov     [rbx+1A8h], r8
0x180014fe3  mov     [rbx+1B0h], r8b
0x180014fea  mov     [rbx+180h], rdx
0x180014ff1  mov     [rbx+1B8h], r8w
0x180014ff9  mov     [rbx+1C0h], r8
0x180015000  mov     [rbx+1D0h], r8
0x180015007  mov     [rbx+1D8h], r8
0x18001500e  mov     [rbx+1E0h], r8d
0x180015015  mov     [rbx+1E8h], r8
0x18001501c  mov     [rbx+1F0h], r8
0x180015023  mov     [rbx+1F8h], r8b
0x18001502a  mov     [rbx+1C8h], rdx
0x180015031  mov     [rbx+200h], r8w
0x180015039  mov     [rbx+208h], r8
0x180015040  mov     [rbx+218h], r8
0x180015047  mov     [rbx+220h], r8
0x18001504e  mov     [rbx+228h], r8d
0x180015055  mov     [rbx+230h], r8
0x18001505c  mov     [rbx+238h], r8
0x180015063  mov     [rbx+240h], r8b
0x18001506a  mov     [rbx+210h], rdx
0x180015071  mov     [rbx+248h], r8w
0x180015079  mov     [rbx+250h], r8
0x180015080  mov     [rbx+268h], r8
0x180015087  mov     [rbx+270h], r8
0x18001508e  mov     [rbx+278h], r8d
0x180015095  mov     [rbx+280h], r8
0x18001509c  mov     [rbx+288h], r8
0x1800150a3  mov     [rbx+290h], r8b
0x1800150aa  mov     [rbx+260h], rdx
0x1800150b1  mov     [rbx+298h], r8w
0x1800150b9  mov     [rbx+2A0h], r8
0x1800150c0  mov     [rbx+2B0h], r8
0x1800150c7  mov     [rbx+2B8h], r8
0x1800150ce  mov     [rbx+2C0h], r8d
0x1800150d5  mov     [rbx+2C8h], r8
0x1800150dc  mov     [rbx+2D0h], r8
0x1800150e3  mov     [rbx+2D8h], r8b
0x1800150ea  lea     rax, ??_7TPMW8T_SYM_DEF@tpm12class@@6B@; const tpm12class::TPMW8T_SYM_DEF::`vftable'
0x1800150f1  mov     [rbx+2A8h], rax
0x1800150f8  mov     ecx, 10h
0x1800150fd  mov     [rbx+2E0h], ecx
0x180015103  mov     dword ptr [rbx+2E4h], 100010h
0x18001510d  mov     [rbx+2E8h], cx
0x180015114  mov     [rbx+308h], r8
0x18001511b  mov     [rbx+8], r8
0x18001511f  mov     [rbx+2F0h], r8
0x180015126  mov     dword ptr [rbx+2F8h], 0B0000h
0x180015130  mov     [rbx+10h], r8d
0x180015134  mov     dword ptr [rbx+25Ch], 40000007h
0x18001513e  mov     dword ptr [rbx+300h], 40000007h
0x180015148  mov     [rbx+2FCh], r8b
0x18001514f  mov     [rbx+310h], r8b
0x180015156  mov     ecx, 178h; Size
0x18001515b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015160  mov     rcx, rax; this
0x180015163  call    ??0TPMW8_AUTH_PROVIDER@tpm12class@@QEAA@XZ; tpm12class::TPMW8_AUTH_PROVIDER::TPMW8_AUTH_PROVIDER(void)
0x180015168  mov     [rbx+308h], rax
0x18001516f  test    rax, rax
0x180015172  jz      short loc_180015182
0x180015174  movzx   ecx, word ptr [rbx+2FAh]
0x18001517b  mov     [rax+172h], cx
0x180015182  mov     [rbp+180h+var_168], rbx
0x180015186  mov     dword ptr [rbp+180h+var_170], 155h
0x18001518d  test    rsi, rsi
0x180015190  jnz     loc_18001551D
0x180015196  mov     [rbp+180h+var_150], r14d
0x18001519a  test    rdi, rdi
0x18001519d  jz      loc_18001552D
0x1800151a3  movzx   esi, word ptr [rdi+38h]
0x1800151a7  mov     r14, [rdi+40h]
0x1800151ab  cmp     [rbp+180h+Block], 0
0x1800151b0  jnz     loc_180015447
0x1800151b6  mov     rax, [rbp+180h+var_148]
0x1800151ba  xor     edx, edx
0x1800151bc  lea     rcx, [rbp+180h+var_148]
0x1800151c0  mov     rax, [rax+18h]
0x1800151c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151c9  mov     ebx, eax
0x1800151cb  test    eax, eax
0x1800151cd  js      short loc_1800151F9
0x1800151cf  mov     rcx, [rbp+180h+Block]; Block
0x1800151d3  test    rcx, rcx
0x1800151d6  jnz     loc_180015537
0x1800151dc  mov     rcx, rsi; Size
0x1800151df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
  ... truncated ...
```
