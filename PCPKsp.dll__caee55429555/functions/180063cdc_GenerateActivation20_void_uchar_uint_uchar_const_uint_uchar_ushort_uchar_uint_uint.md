# GenerateActivation20(void *,uchar *,uint,uchar const *,uint,uchar *,ushort,uchar *,uint,uint *)

- ea: `0x180063cdc`
- end: `0x180065aa2`
- name: `?GenerateActivation20@@YAJPEAXPEAEIPEBEI1G1IPEAI@Z`
- size: `7622`
- prototype: `__int64 __usercall@<rax>(BCRYPT_HANDLE hObject@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, const unsigned __int8 *@<r9>, size_t Size, unsigned __int8 *, unsigned __int16, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009948c`
- `0x1800996f0`
- `0x180099c10`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029260`
- `0x18002e7d0`
- `0x180031244`
- `0x180040850`
- `0x18005600c`
- `0x180056fec`
- `0x18005705c`
- `0x180058dac`
- `0x1800592f4`
- `0x180061bac`
- `0x180063c98`
- `0x180063cb8`
- `0x180063cdc`
- `0x18006d024`
- `0x1800764d0`
- `0x180077028`
- `0x18007704c`
- `0x1800924d4`
- `0x180094714`
- `0x180094790`
- `0x1800947cc`
- `0x1800953a0`
- `0x180095494`
- `0x1800954dc`
- `0x180095a40`
- `0x180095f84`
- `0x1800960f4`
- `0x180096504`
- `0x180096f0c`
- `0x180098550`
- `0x1800c2ce0`

## import_xrefs

- `bcrypt!BCryptGenerateKeyPair` at `0x180064daa`
- `bcrypt!BCryptGenerateKeyPair` at `0x180064daa`
- `bcrypt!BCryptGetProperty` at `0x180063dfb`
- `bcrypt!BCryptGetProperty` at `0x180063f02`
- `bcrypt!BCryptGetProperty` at `0x180063f53`
- `bcrypt!BCryptGetProperty` at `0x180064cdc`
- `bcrypt!BCryptGetProperty` at `0x180063dfb`
- `bcrypt!BCryptGetProperty` at `0x180063f02`
- `bcrypt!BCryptGetProperty` at `0x180063f53`
- `bcrypt!BCryptGetProperty` at `0x180064cdc`
- `bcrypt!BCryptEncrypt` at `0x180065860`
- `bcrypt!BCryptEncrypt` at `0x180065860`
- `bcrypt!BCryptVerifySignature` at `0x180064a79`
- `bcrypt!BCryptVerifySignature` at `0x180064a79`
- `bcrypt!BCryptDeriveKey` at `0x18006523f`
- `bcrypt!BCryptDeriveKey` at `0x18006523f`
- `bcrypt!BCryptSecretAgreement` at `0x1800650e5`
- `bcrypt!BCryptSecretAgreement` at `0x1800650e5`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180064e0a`
- `bcrypt!BCryptFinalizeKeyPair` at `0x180064e0a`
- `bcrypt!BCryptSetProperty` at `0x180064d47`
- `bcrypt!BCryptSetProperty` at `0x180064d47`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800642d4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180064c67`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800652ee`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800642d4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180064c67`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800652ee`
- `bcrypt!BCryptExportKey` at `0x180064e88`
- `bcrypt!BCryptExportKey` at `0x180064f53`
- `bcrypt!BCryptExportKey` at `0x180064fd6`
- `bcrypt!BCryptExportKey` at `0x18006506a`
- `bcrypt!BCryptExportKey` at `0x180064e88`
- `bcrypt!BCryptExportKey` at `0x180064f53`
- `bcrypt!BCryptExportKey` at `0x180064fd6`
- `bcrypt!BCryptExportKey` at `0x18006506a`
- `bcrypt!BCryptGenRandom` at `0x18006534f`
- `bcrypt!BCryptGenRandom` at `0x18006534f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GenerateActivation20(
        BCRYPT_HANDLE hObject,
        wchar_t *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        size_t Size,
        unsigned __int8 *a6,
        unsigned __int16 a7,
        unsigned __int8 *a8,
        ULONG a9,
        unsigned int *a10)
{
  int v13; // edx
  NTSTATUS Property; // eax
  __int64 v15; // rdx
  bool v16; // dl
  unsigned __int16 v17; // ax
  ULONG v18; // ebx
  unsigned int v19; // r12d
  __int64 v20; // rdi
  unsigned int v21; // ebx
  unsigned int v22; // edx
  wchar_t *v23; // r8
  ULONG v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  unsigned __int64 v27; // r9
  unsigned int v28; // r14d
  unsigned __int8 *v29; // rsi
  int v30; // eax
  const WCHAR *v31; // r12
  int v32; // eax
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rdx
  NTSTATUS v36; // eax
  int KeyHandleFromPubKeyBlob20; // eax
  __int64 v38; // rdx
  unsigned int v39; // ebx
  int NameFromPublic; // eax
  unsigned __int64 v41; // r9
  __int64 v42; // rdx
  unsigned __int8 *v43; // r13
  unsigned int v44; // esi
  unsigned int v45; // r14d
  unsigned __int8 *v46; // r12
  int v47; // eax
  unsigned int v48; // r10d
  unsigned int v49; // ecx
  int BigEndian; // eax
  int v51; // r10d
  int v52; // eax
  int v53; // eax
  const unsigned __int8 *v54; // rcx
  int v55; // eax
  const unsigned __int8 *v56; // rcx
  int BigEndian2B; // eax
  int v58; // eax
  ULONG v59; // ebx
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // r9
  PUCHAR *v63; // rcx
  const unsigned __int8 *v64; // rcx
  const unsigned __int8 *v65; // rcx
  int v66; // eax
  int v67; // eax
  int v68; // eax
  const unsigned __int8 *v69; // rcx
  int v70; // eax
  int v71; // eax
  unsigned int v72; // r12d
  int v73; // eax
  wchar_t *v74; // r14
  int v75; // eax
  ULONG v76; // ebx
  int v77; // eax
  NTSTATUS v78; // eax
  unsigned __int8 *v79; // rsi
  int v80; // eax
  ULONG v81; // r14d
  int v82; // eax
  unsigned __int16 v83; // r11
  int v84; // eax
  unsigned int v85; // r11d
  unsigned int v86; // r13d
  int v87; // eax
  int v88; // eax
  PUCHAR v89; // rbx
  NTSTATUS v90; // eax
  UCHAR *v91; // rcx
  BCRYPT_HANDLE v92; // rsi
  NTSTATUS v93; // eax
  UCHAR *v94; // rcx
  NTSTATUS v95; // eax
  UCHAR *v96; // rcx
  NTSTATUS KeyPair; // eax
  UCHAR *v98; // rcx
  NTSTATUS v99; // eax
  UCHAR *v100; // rcx
  NTSTATUS v101; // eax
  UCHAR *v102; // rcx
  int v103; // ecx
  __int64 v104; // rax
  NTSTATUS v105; // eax
  UCHAR *v106; // rcx
  NTSTATUS v107; // eax
  UCHAR *v108; // rcx
  NTSTATUS v109; // eax
  UCHAR *v110; // rcx
  NTSTATUS v111; // eax
  UCHAR *v112; // rcx
  __int64 v113; // rax
  NTSTATUS v114; // eax
  UCHAR *v115; // rcx
  BCRYPT_ALG_HANDLE *p_hAlgorithm; // rcx
  NTSTATUS v117; // eax
  UCHAR *v118; // rcx
  NTSTATUS v119; // eax
  UCHAR *v120; // rcx
  int v121; // eax
  unsigned int v122; // r9d
  unsigned int v123; // esi
  UCHAR *v124; // rcx
  ULONG v125; // r14d
  int v126; // eax
  UCHAR *v127; // rcx
  int v128; // eax
  __int64 v129; // rdx
  UCHAR *v130; // rcx
  UCHAR *v131; // rax
  __int64 v132; // r9
  unsigned __int8 *v133; // r14
  int v134; // eax
  __int64 v135; // rdx
  UCHAR *v136; // rcx
  UCHAR *v137; // rax
  ULONG v138; // r13d
  int v139; // eax
  __int64 v140; // rax
  UCHAR *v141; // rcx
  UCHAR *v142; // rax
  __int64 v143; // rcx
  UCHAR *v144; // rax
  UCHAR *v145; // rax
  int v146; // eax
  __int64 v147; // rax
  UCHAR *v148; // rcx
  UCHAR *v149; // rax
  __int64 v150; // rcx
  UCHAR *v151; // rax
  UCHAR *v152; // rax
  NTSTATUS v153; // eax
  __int64 v154; // rdx
  UCHAR *v155; // rcx
  UCHAR *v156; // rax
  int v157; // eax
  __int64 v158; // rax
  UCHAR *v159; // rcx
  UCHAR *v160; // rax
  __int64 v161; // rcx
  UCHAR *v162; // rax
  UCHAR *v163; // rax
  int pcbResult; // [rsp+20h] [rbp-E0h]
  int pcbResulta; // [rsp+20h] [rbp-E0h]
  int pcbResultb; // [rsp+20h] [rbp-E0h]
  int pcbResultc; // [rsp+20h] [rbp-E0h]
  int pcbResultd; // [rsp+20h] [rbp-E0h]
  int pcbResulte; // [rsp+20h] [rbp-E0h]
  int pcbResultf; // [rsp+20h] [rbp-E0h]
  int pcbResultg; // [rsp+20h] [rbp-E0h]
  int pcbResulth; // [rsp+20h] [rbp-E0h]
  int pcbResulti; // [rsp+20h] [rbp-E0h]
  int pcbResultj; // [rsp+20h] [rbp-E0h]
  int pcbResultk; // [rsp+20h] [rbp-E0h]
  int pcbResultl; // [rsp+20h] [rbp-E0h]
  int pcbResultm; // [rsp+20h] [rbp-E0h]
  int pcbResultn; // [rsp+20h] [rbp-E0h]
  int pcbResulto; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v181; // [rsp+30h] [rbp-D0h]
  unsigned __int8 *v182; // [rsp+30h] [rbp-D0h]
  unsigned int cbOutput; // [rsp+38h] [rbp-C8h]
  unsigned int cbOutputa; // [rsp+38h] [rbp-C8h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-A0h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+68h] [rbp-98h] BYREF
  ULONG v187; // [rsp+70h] [rbp-90h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+78h] [rbp-88h] BYREF
  bool v189; // [rsp+80h] [rbp-80h]
  unsigned int v190; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int16 v191[2]; // [rsp+88h] [rbp-78h] BYREF
  ULONG v192[3]; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int8 *v193[3]; // [rsp+98h] [rbp-68h] BYREF
  void *Buf2; // [rsp+B0h] [rbp-50h] BYREF
  UCHAR v195[4]; // [rsp+B8h] [rbp-48h] BYREF
  ULONG v196; // [rsp+BCh] [rbp-44h]
  ULONG cbDerivedKey; // [rsp+C0h] [rbp-40h] BYREF
  ULONG cbSecret; // [rsp+C4h] [rbp-3Ch] BYREF
  ULONG cbSignature; // [rsp+C8h] [rbp-38h] BYREF
  ULONG v200; // [rsp+CCh] [rbp-34h] BYREF
  ULONG v201; // [rsp+D0h] [rbp-30h]
  void *Buf1; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *String1; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v204; // [rsp+E8h] [rbp-18h]
  PUCHAR v205; // [rsp+F0h] [rbp-10h] BYREF
  UCHAR *v206; // [rsp+F8h] [rbp-8h]
  __int64 v207; // [rsp+100h] [rbp+0h]
  BCRYPT_HANDLE hObjecta; // [rsp+108h] [rbp+8h]
  unsigned int *v209; // [rsp+110h] [rbp+10h]
  unsigned __int8 *v210; // [rsp+118h] [rbp+18h]
  PUCHAR v211[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int8 *v212; // [rsp+138h] [rbp+38h] BYREF
  char v213; // [rsp+140h] [rbp+40h]
  ULONG v214; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int8 *v215; // [rsp+150h] [rbp+50h]
  BCryptBufferDesc pPaddingInfo; // [rsp+158h] [rbp+58h] BYREF
  wchar_t *v217; // [rsp+168h] [rbp+68h] BYREF
  const char *v218; // [rsp+170h] [rbp+70h]
  __int64 v219; // [rsp+178h] [rbp+78h]
  wchar_t *v220; // [rsp+180h] [rbp+80h] BYREF
  PUCHAR v221; // [rsp+188h] [rbp+88h] BYREF
  PUCHAR v222[3]; // [rsp+190h] [rbp+90h] BYREF
  PUCHAR pbHash[3]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v224[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v225[56]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int16 v226; // [rsp+218h] [rbp+118h]
  unsigned __int16 v227; // [rsp+258h] [rbp+158h]
  void *v228; // [rsp+260h] [rbp+160h]
  unsigned __int16 v229; // [rsp+2A0h] [rbp+1A0h]
  void *Source; // [rsp+2A8h] [rbp+1A8h]
  unsigned __int16 v231; // [rsp+2E8h] [rbp+1E8h]
  void *v232; // [rsp+2F0h] [rbp+1F0h]
  _DWORD v233[2]; // [rsp+380h] [rbp+280h] BYREF
  wchar_t *v234; // [rsp+388h] [rbp+288h]
  int v235; // [rsp+390h] [rbp+290h]
  int v236; // [rsp+394h] [rbp+294h]
  const char *v237; // [rsp+398h] [rbp+298h]
  int v238; // [rsp+3A0h] [rbp+2A0h]
  int v239; // [rsp+3A4h] [rbp+2A4h]
  PUCHAR v240; // [rsp+3A8h] [rbp+2A8h]
  __int128 v241; // [rsp+3B0h] [rbp+2B0h]
  UCHAR pbDerivedKey[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  UCHAR pbSecret[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int8 v244[16]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int8 v245[16]; // [rsp+450h] [rbp+350h] BYREF
  __int128 v246; // [rsp+460h] [rbp+360h]
  UCHAR Destination[256]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t pbOutput[264]; // [rsp+570h] [rbp+470h] BYREF
  UCHAR pbInput[1024]; // [rsp+780h] [rbp+680h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+BC8h] [rbp+AC8h]

  Buf1 = a4;
  String1 = a2;
  hObjecta = hObject;
  v215 = a6;
  v210 = a8;
  v209 = a10;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v224, L"GenerateActivation20", 1);
  v187 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v205);
  *(_DWORD *)v195 = v13;
  memset_0(Destination, v13, sizeof(Destination));
  v220 = 0;
  *(_OWORD *)v245 = 0;
  v246 = 0;
  v200 = 32;
  if ( !a2 || !a3 )
  {
    v25 = 1009;
    goto LABEL_331;
  }
  if ( !hObject )
  {
    v17 = a7;
    if ( !a6 || !a7 )
    {
      v18 = a9;
      if ( !a8 || !a9 )
      {
        v16 = 0;
        v189 = 0;
        if ( !a10 )
          goto LABEL_15;
      }
    }
LABEL_329:
    v25 = 1039;
    goto LABEL_331;
  }
  memset_0(pbOutput, 0, 0x208u);
  v214 = 0;
  Property = BCryptGetProperty(hObject, L"AlgorithmName", (PUCHAR)pbOutput, 0x208u, &v214, 0);
  if ( Property < 0 )
  {
    v15 = 1021;
LABEL_22:
    v21 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
            (const char *)(unsigned int)Property,
            pcbResult);
LABEL_334:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v205);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v224);
    return v21;
  }
  v16 = wcscmp_0(pbOutput, L"ECDH") == 0;
  v189 = v16;
  if ( !a6 )
    goto LABEL_329;
  v17 = a7;
  if ( !a7 || !a10 )
    goto LABEL_329;
  v18 = a9;
LABEL_15:
  v201 = 0;
  v204 = (wchar_t *)L"SHA256";
  v19 = 32;
  v196 = 32;
  v20 = 64;
  if ( !hObjecta || !v215 || !v17 || !v209 )
    goto LABEL_45;
  if ( v16 )
  {
    Property = BCryptGetProperty(hObjecta, L"KeyLength", v195, 4u, &v187, 0);
    if ( Property < 0 )
    {
      v15 = 1055;
      goto LABEL_22;
    }
    v22 = 2 * ((unsigned int)(*(_DWORD *)v195 + 7) >> 3) + 4;
    *(_DWORD *)v195 = v22;
  }
  else
  {
    Property = BCryptGetProperty(hObjecta, L"BlockLength", v195, 4u, &v187, 0);
    if ( Property < 0 )
    {
      v15 = 1074;
      goto LABEL_22;
    }
    v22 = *(_DWORD *)v195;
  }
  if ( v22 != 68 )
  {
    if ( v22 == 100 )
      goto LABEL_42;
    if ( v22 == 136 )
    {
      v23 = (wchar_t *)L"SHA512";
      v19 = 64;
      v196 = 64;
      goto LABEL_34;
    }
    if ( v22 != 256 && (v22 == 384 || v22 == 512) )
    {
LABEL_42:
      v204 = (wchar_t *)L"SHA384";
      v19 = 48;
      v196 = 48;
      goto LABEL_35;
    }
  }
  v23 = (wchar_t *)L"SHA256";
  v196 = 32;
  v200 = 16;
LABEL_34:
  v204 = v23;
LABEL_35:
  if ( v22 < (v189 ? 68 : 256) || a7 > v19 )
  {
    v25 = 1109;
LABEL_331:
    v21 = -2147024809;
    goto LABEL_332;
  }
  v201 = v19 + a7 + 6;
  v24 = v22 + v201 + 2;
  *v209 = v24;
  if ( !a8 || !v18 )
  {
    v21 = 0;
    goto LABEL_334;
  }
  if ( v18 < v24 )
  {
    v21 = -2146893784;
    v25 = 1123;
LABEL_332:
    v27 = v21;
    goto LABEL_333;
  }
LABEL_45:
  v187 = 0;
  Buf2 = 0;
  LODWORD(hAlgorithm) = 0;
  v26 = ReadBigEndian2B(
          (const unsigned __int8 *)a2,
          a3,
          &v187,
          (unsigned __int16 *)&hAlgorithm,
          (const unsigned __int8 **)&Buf2);
  v21 = v26;
  if ( v26 < 0 )
  {
    v27 = (unsigned int)v26;
    v25 = 1130;
LABEL_333:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)v27,
      pcbResult);
    goto LABEL_334;
  }
  v28 = (unsigned int)hAlgorithm;
  if ( (unsigned int)hAlgorithm < 2 )
  {
    v21 = -2146893785;
    v25 = 1132;
    goto LABEL_332;
  }
  v29 = (unsigned __int8 *)Buf2;
  v30 = ValidateTPublicKeyAttributes((const unsigned __int8 *)Buf2, (unsigned int)hAlgorithm, 1);
  v21 = v30;
  if ( v30 < 0 )
  {
    v27 = (unsigned int)v30;
    v25 = 1134;
    goto LABEL_333;
  }
  if ( (v29[1] | (unsigned __int16)(*(_WORD *)v29 << 8)) == 1 )
  {
    v31 = L"RSA";
    *(_QWORD *)&pPaddingInfo.ulVersion = &v220;
    cbSecret = 2;
  }
  else
  {
    if ( (v29[1] | (unsigned __int16)(*(_WORD *)v29 << 8)) != 0x23 )
    {
      v21 = -2146893783;
      v25 = 1150;
      goto LABEL_332;
    }
    *(_QWORD *)&pPaddingInfo.ulVersion = 0;
    cbSecret = 0;
    v31 = L"ECDSA";
  }
  v221 = 0;
  v192[1] = 0;
  v21 = ReadBigEndian2B(
          (const unsigned __int8 *)String1,
          a3,
          &v187,
          (unsigned __int16 *)&v192[1],
          (const unsigned __int8 **)&v221);
  if ( (v21 & 0x80000000) != 0 )
  {
    v25 = 1156;
    goto LABEL_332;
  }
  Buf2 = 0;
  v190 = 0;
  v32 = ReadBigEndian2B(
          (const unsigned __int8 *)String1,
          a3,
          &v187,
          (unsigned __int16 *)&v190,
          (const unsigned __int8 **)&Buf2);
  v21 = v32;
  if ( v32 < 0 )
  {
    v27 = (unsigned int)v32;
    v25 = 1161;
    goto LABEL_333;
  }
  tpm12class::TPMW8T_SIGNATURE::TPMW8T_SIGNATURE((tpm12class::TPMW8T_SIGNATURE *)v225);
  v33 = tpm12class::TpmDataObject::Set(
          (tpm12class::TpmDataObject *)v225,
          (const unsigned __int8 *)String1 + v187,
          (unsigned __int16)(a3 - v187),
          0,
          0);
  v21 = v33;
  if ( v33 < 0 )
  {
    v34 = (unsigned int)v33;
    v35 = 1165;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)v34,
      pcbResulta);
LABEL_328:
    tpm12class::TPMW8T_SIGNATURE::~TPMW8T_SIGNATURE((tpm12class::TPMW8T_SIGNATURE *)v225);
    goto LABEL_334;
  }
  if ( v226 == 20 )
  {
    if ( memcpy_s(Destination, 0x100u, v228, v227) )
    {
      v21 = -2146893779;
      v34 = 2148073517LL;
      v35 = 1174;
      goto LABEL_62;
    }
    cbSignature = v227;
  }
  else
  {
    if ( v226 != 24 )
    {
      v21 = -2146893783;
      v34 = 2148073513LL;
      v35 = 1193;
      goto LABEL_62;
    }
    if ( memcpy_s(Destination, 0x100u, Source, v229) )
    {
      v21 = -2146893779;
      v34 = 2148073517LL;
      v35 = 1183;
      goto LABEL_62;
    }
    if ( memcpy_s(&Destination[v229], 256LL - v229, v232, v231) )
    {
      v21 = -2146893779;
      v34 = 2148073517LL;
      v35 = 1188;
      goto LABEL_62;
    }
    cbSignature = v229 + v231;
  }
  phAlgorithm = 0;
  v36 = BCryptOpenAlgorithmProvider(&phAlgorithm, v31, 0, 0);
  if ( v36 < 0 )
  {
    v21 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x4B0,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
            (const char *)(unsigned int)v36,
            pcbResulta);
LABEL_327:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    goto LABEL_328;
  }
  v217 = 0;
  hKey = 0;
  KeyHandleFromPubKeyBlob20 = GetKeyHandleFromPubKeyBlob20(
                                v29,
                                v28,
                                phAlgorithm,
                                &hKey,
                                (unsigned int *)&hAlgorithm,
                                (const unsigned __int16 **)&v217);
  v21 = KeyHandleFromPubKeyBlob20;
  if ( KeyHandleFromPubKeyBlob20 < 0 )
  {
    v38 = 1210;
LABEL_78:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)(unsigned int)KeyHandleFromPubKeyBlob20,
      pcbResultb);
LABEL_326:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
    goto LABEL_327;
  }
  String1 = 0;
  v192[0] = 0;
  KeyHandleFromPubKeyBlob20 = GetNameFromPublic(v29, (ULONG)hAlgorithm, (const unsigned __int16 **)&String1, 0, 0, v192);
  v21 = KeyHandleFromPubKeyBlob20;
  if ( KeyHandleFromPubKeyBlob20 < 0 )
  {
    v38 = 1220;
    goto LABEL_78;
  }
  v39 = v192[0];
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    v193,
    v192[0]);
  NameFromPublic = GetNameFromPublic(v29, (ULONG)hAlgorithm, (const unsigned __int16 **)&String1, v193[0], v39, v192);
  v21 = NameFromPublic;
  if ( NameFromPublic < 0 )
  {
    v41 = (unsigned int)NameFromPublic;
    v42 = 1228;
LABEL_324:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)v41,
      pcbResultc);
    goto LABEL_325;
  }
  v43 = (unsigned __int8 *)Buf2;
  v44 = v190;
  if ( !Buf1 )
    goto LABEL_136;
  v190 = 0;
  LODWORD(hAlgorithm) = 0;
  v212 = 0;
  v191[0] = 0;
  v45 = v192[1];
  v46 = v221;
  v47 = ReadBigEndian(v221, v192[1], (unsigned int *)&hAlgorithm, &v190);
  v21 = v47;
  if ( v47 < 0 )
  {
    v41 = (unsigned int)v47;
    v42 = 1238;
    goto LABEL_324;
  }
  v48 = 0;
  v49 = (unsigned int)hAlgorithm;
  while ( v48 < v190 )
  {
    LOBYTE(v192[1]) = 0;
    if ( v49 > v45 || v45 - v49 < 2 )
    {
      v42 = 1244;
      goto LABEL_322;
    }
    LODWORD(hAlgorithm) = v49 + 2;
    BigEndian = ReadBigEndian(v46, v45, (unsigned int *)&hAlgorithm, (unsigned __int8 *)&v192[1]);
    v21 = BigEndian;
    if ( BigEndian < 0 )
    {
      v41 = (unsigned int)BigEndian;
      v42 = 1246;
      goto LABEL_324;
    }
    if ( (unsigned int)hAlgorithm > v45 || LOBYTE(v192[1]) > v45 - (unsigned int)hAlgorithm )
    {
      v42 = 1248;
      goto LABEL_322;
    }
    v49 = LOBYTE(v192[1]) + (_DWORD)hAlgorithm;
    LODWORD(hAlgorithm) = v49;
    v48 = v51 + 1;
  }
  v52 = SkipBigEndian2B(v46, v45, (unsigned int *)&hAlgorithm);
  v21 = v52;
  if ( v52 < 0 )
  {
    v41 = (unsigned int)v52;
    v42 = 1252;
    goto LABEL_324;
  }
  if ( (unsigned int)hAlgorithm >= v45 )
  {
    v42 = 1255;
    goto LABEL_322;
  }
  if ( (int)hAlgorithm + 1 > v45 || v45 - ((_DWORD)hAlgorithm + 1) < 2 )
  {
    v42 = 1258;
    goto LABEL_322;
  }
  LODWORD(hAlgorithm) = (_DWORD)hAlgorithm + 3;
  v53 = SkipBigEndian2B(v46, v45, (unsigned int *)&hAlgorithm);
  v21 = v53;
  if ( v53 < 0 )
  {
    v41 = (unsigned int)v53;
    v42 = 1261;
    goto LABEL_324;
  }
  v55 = SkipBigEndian2B(v54, v45, (unsigned int *)&hAlgorithm);
  v21 = v55;
  if ( v55 < 0 )
  {
    v41 = (unsigned int)v55;
    v42 = 1264;
    goto LABEL_324;
  }
  Buf2 = 0;
  LOWORD(v192[1]) = 0;
  BigEndian2B = ReadBigEndian2B(
                  v56,
                  v45,
                  (unsigned int *)&hAlgorithm,
                  (unsigned __int16 *)&v192[1],
                  (const unsigned __int8 **)&Buf2);
  v21 = BigEndian2B;
  if ( BigEndian2B < 0 )
  {
    v41 = (unsigned int)BigEndian2B;
    v42 = 1273;
    goto LABEL_324;
  }
  if ( (_DWORD)Size != LOWORD(v192[1]) || memcmp_0(Buf1, Buf2, (unsigned int)Size) )
  {
    v42 = 1278;
LABEL_322:
    v21 = -2147024809;
    goto LABEL_323;
  }
  v190 = 0;
  v58 = TpmAttiShaHash(String1, 0, 0, v46, v45, 0, 0, (__int64)&v190);
  v21 = v58;
  if ( v58 < 0 )
  {
    v41 = (unsigned int)v58;
    v42 = 1289;
    goto LABEL_324;
  }
  v59 = v190;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    v211,
    v190);
  v60 = TpmAttiShaHash(String1, 0, 0, v46, v45, v211[0], v59, (__int64)&v190);
  v21 = v60;
  if ( v60 < 0 )
  {
    v61 = 1299;
LABEL_114:
    v62 = (unsigned int)v60;
LABEL_115:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v61,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)v62,
      pcbResultc);
    v63 = v211;
LABEL_116:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v63);
LABEL_325:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v193);
    goto LABEL_326;
  }
  if ( v44 < 4 )
  {
    v21 = -2147024809;
    v62 = 2147942487LL;
    v61 = 1304;
    goto LABEL_115;
  }
  if ( v44 - 4 < 2 )
  {
    v21 = -2147024809;
    v62 = 2147942487LL;
    v61 = 1307;
    goto LABEL_115;
  }
  LODWORD(hAlgorithm) = 6;
  v60 = SkipBigEndian2B(v43, v44, (unsigned int *)&hAlgorithm);
  v21 = v60;
  if ( v60 < 0 )
  {
    v61 = 1310;
    goto LABEL_114;
  }
  v60 = ReadBigEndian2B(
          v64,
          v44,
          (unsigned int *)&hAlgorithm,
          (unsigned __int16 *)&v192[1],
          (const unsigned __int8 **)&Buf2);
  v21 = v60;
  if ( v60 < 0 )
  {
    v61 = 1313;
    goto LABEL_114;
  }
  if ( (_DWORD)Size != LOWORD(v192[1]) || memcmp_0(Buf1, Buf2, (unsigned int)Size) )
  {
    v21 = -2147024809;
    v62 = 2147942487LL;
    v61 = 1318;
    goto LABEL_115;
  }
  if ( (unsigned int)hAlgorithm > v44 || v44 - (unsigned int)hAlgorithm < 0x11 )
  {
    v21 = -2147024809;
    v62 = 2147942487LL;
    v61 = 1323;
    goto LABEL_115;
  }
  if ( (int)hAlgorithm + 17 > v44 || v44 - ((_DWORD)hAlgorithm + 17) < 8 )
  {
    v21 = -2147024809;
    v62 = 2147942487LL;
    v61 = 1326;
    goto LABEL_115;
  }
  LODWORD(hAlgorithm) = (_DWORD)hAlgorithm + 25;
  v60 = SkipBigEndian2B(v43, v44, (unsigned int *)&hAlgorithm);
  v21 = v60;
  if ( v60 < 0 )
  {
    v61 = 1329;
    goto LABEL_114;
  }
  v60 = ReadBigEndian2B(v65, v44, (unsigned int *)&hAlgorithm, v191, (const unsigned __int8 **)&v212);
  v21 = v60;
  if ( v60 < 0 )
  {
    v61 = 1336;
    goto LABEL_114;
  }
  if ( v190 != v191[0] || memcmp_0(v211[0], v212, v190) )
  {
    v21 = -2147024809;
    v62 = 2147942487LL;
    v61 = 1340;
    goto LABEL_115;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v211);
LABEL_136:
  LODWORD(hAlgorithm) = 0;
  v190 = 0;
  v66 = ReadBigEndian(v43, v44, (unsigned int *)&hAlgorithm, &v190);
  v21 = v66;
  if ( v66 < 0 )
  {
    v41 = (unsigned int)v66;
    v42 = 1350;
    goto LABEL_324;
  }
  if ( v190 != -11254969 )
  {
    v42 = 1351;
    goto LABEL_322;
  }
  v191[0] = 0;
  v67 = ReadBigEndian(v43, v44, (unsigned int *)&hAlgorithm, v191);
  v21 = v67;
  if ( v67 < 0 )
  {
    v41 = (unsigned int)v67;
    v42 = 1357;
    goto LABEL_324;
  }
  if ( v191[0] != 0x801A )
  {
    v42 = 1358;
    goto LABEL_322;
  }
  v68 = SkipBigEndian2B(v43, v44, (unsigned int *)&hAlgorithm);
  v21 = v68;
  if ( v68 < 0 )
  {
    v41 = (unsigned int)v68;
    v42 = 1362;
    goto LABEL_324;
  }
  v70 = SkipBigEndian2B(v69, v44, (unsigned int *)&hAlgorithm);
  v21 = v70;
  if ( v70 < 0 )
  {
    v41 = (unsigned int)v70;
    v42 = 1365;
    goto LABEL_324;
  }
  if ( (unsigned int)hAlgorithm > v44 || v44 - (unsigned int)hAlgorithm < 0x11 )
  {
    v42 = 1371;
    goto LABEL_322;
  }
  if ( (int)hAlgorithm + 17 > v44 || v44 - ((_DWORD)hAlgorithm + 17) < 8 )
  {
    v42 = 1374;
    goto LABEL_322;
  }
  LODWORD(hAlgorithm) = (_DWORD)hAlgorithm + 25;
  v212 = 0;
  v191[0] = 0;
  v71 = ReadBigEndian2B(v43, v44, (unsigned int *)&hAlgorithm, v191, (const unsigned __int8 **)&v212);
  v21 = v71;
  if ( v71 < 0 )
  {
    v41 = (unsigned int)v71;
    v42 = 1380;
    goto LABEL_324;
  }
  v72 = v192[0];
  if ( v192[0] != v191[0] || memcmp_0(v193[0], v212, v192[0]) )
  {
    v42 = 1385;
    goto LABEL_322;
  }
  v73 = SkipBigEndian2B(v43, v44, (unsigned int *)&hAlgorithm);
  v21 = v73;
  if ( v73 < 0 )
  {
    v41 = (unsigned int)v73;
    v42 = 1389;
    goto LABEL_324;
  }
  v192[0] = 0;
  v74 = v217;
  v75 = TpmAttiShaHash(v217, 0, 0, v43, v44, 0, 0, (__int64)v192);
  v21 = v75;
  if ( v75 < 0 )
  {
    v41 = (unsigned int)v75;
    v42 = 1401;
    goto LABEL_324;
  }
  v76 = v192[0];
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    pbHash,
    v192[0]);
  v77 = TpmAttiShaHash(v74, 0, 0, v43, v44, pbHash[0], v76, (__int64)v192);
  v21 = v77;
  if ( v77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x583,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)(unsigned int)v77,
      pcbResultd);
LABEL_171:
    v63 = pbHash;
    goto LABEL_116;
  }
  v220 = v74;
  v78 = BCryptVerifySignature(
          hKey,
          *(void **)&pPaddingInfo.ulVersion,
          pbHash[0],
          v192[0],
          Destination,
          cbSignature,
          cbSecret);
  if ( v78 < 0 )
  {
    v21 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x58D,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
            (const char *)(unsigned int)v78,
            pcbResultc);
    goto LABEL_171;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(pbHash);
  if ( !hObjecta || !v215 || !a7 || !v209 )
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v193);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    tpm12class::TPMW8T_SIGNATURE::~TPMW8T_SIGNATURE((tpm12class::TPMW8T_SIGNATURE *)v225);
    v21 = 0;
    goto LABEL_334;
  }
  if ( a9 < v201 )
  {
    v21 = -2146893784;
    v42 = 1434;
LABEL_323:
    v41 = v21;
    goto LABEL_324;
  }
  v187 = 0;
  v79 = v210;
  v80 = WriteBigEndian(v210, a9, &v187, (unsigned __int16)v201 - 2);
  v21 = v80;
  if ( v80 < 0 )
  {
    v41 = (unsigned int)v80;
    v42 = 1441;
    goto LABEL_324;
  }
  v81 = v196;
  v82 = WriteBigEndian(v79, a9, &v187, v196);
  v21 = v82;
  if ( v82 < 0 )
  {
    v41 = (unsigned int)v82;
    v42 = 1444;
    goto LABEL_324;
  }
  if ( v187 > a9 || v81 > a9 - v187 )
  {
    v42 = 1447;
    goto LABEL_322;
  }
  v187 += v81;
  v84 = WriteBigEndian(v79, a9, &v187, v83);
  v21 = v84;
  if ( v84 < 0 )
  {
    v41 = (unsigned int)v84;
    v42 = 1450;
    goto LABEL_324;
  }
  v86 = v85;
  v87 = WriteBigEndian(v79, a9, &v187, v215, v85);
  v21 = v87;
  if ( v87 < 0 )
  {
    v41 = (unsigned int)v87;
    v42 = 1453;
    goto LABEL_324;
  }
  v88 = WriteBigEndian(v79, a9, &v187, v193[0], v72);
  v21 = v88;
  if ( v88 < 0 )
  {
    v41 = (unsigned int)v88;
    v42 = 1457;
    goto LABEL_324;
  }
  memset_0(pbDerivedKey, 0, sizeof(pbDerivedKey));
  v217 = (wchar_t *)pbDerivedKey;
  LOBYTE(v218) = 1;
  cbDerivedKey = v81;
  v89 = 0;
  if ( v189 )
  {
    memset_0(pbInput, 0, sizeof(pbInput));
    cbSignature = 0;
    hAlgorithm = 0;
    v90 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"ECDH", L"Microsoft Primitive Provider", 0);
    if ( v90 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5C5,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v90,
              pcbResultc);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v91 = pbDerivedKey;
      do
      {
        *v91++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v92 = hObjecta;
    v93 = BCryptGetProperty(hObjecta, L"ECCParameters", pbInput, 0x400u, &cbSignature, 0);
    if ( v93 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5CC,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v93,
              pcbResulte);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v94 = pbDerivedKey;
      do
      {
        *v94++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v95 = BCryptSetProperty(hAlgorithm, L"ECCParameters", pbInput, cbSignature, 0);
    if ( v95 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5D2,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v95,
              pcbResultf);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v96 = pbDerivedKey;
      do
      {
        *v96++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    *(_QWORD *)&v192[1] = 0;
    KeyPair = BCryptGenerateKeyPair(hAlgorithm, (BCRYPT_KEY_HANDLE *)&v192[1], 0, 0);
    if ( KeyPair < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5D8,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)KeyPair,
              pcbResultf);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v98 = pbDerivedKey;
      do
      {
        *v98++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v99 = BCryptFinalizeKeyPair(*(BCRYPT_KEY_HANDLE *)&v192[1], 0);
    if ( v99 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5DA,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v99,
              pcbResultf);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v100 = pbDerivedKey;
      do
      {
        *v100++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v190 = 0;
    v101 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)&v192[1], 0, L"ECCPUBLICBLOB", 0, 0, &v190, 0);
    if ( v101 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5E3,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v101,
              pcbResultg);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v102 = pbDerivedKey;
      do
      {
        *v102++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v103 = (int)v206;
    if ( v190 >= (unsigned __int64)(v206 - v205) )
    {
      if ( v190 > (unsigned __int64)(v206 - v205) )
      {
        if ( v190 <= (unsigned __int64)(v207 - (_QWORD)v205) )
        {
          v104 = std::_Uninitialized_value_construct_n<wil::secure_allocator<unsigned char>>(v206, v190 - (v206 - v205));
          v103 = v104;
          v206 = (UCHAR *)v104;
        }
        else
        {
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(&v205);
          v103 = (int)v206;
        }
      }
    }
    else
    {
      v103 = v190 + (_DWORD)v205;
      v206 = &v205[v190];
    }
    v105 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)&v192[1], 0, L"ECCPUBLICBLOB", v205, v103 - (_DWORD)v205, &v190, 0);
    if ( v105 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5EC,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v105,
              pcbResulth);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v106 = pbDerivedKey;
      do
      {
        *v106++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v89 = v205;
    v192[0] = 0;
    v107 = BCryptExportKey(v92, 0, L"ECCPUBLICBLOB", 0, 0, v192, 0);
    if ( v107 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5F6,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v107,
              pcbResulti);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v108 = pbDerivedKey;
      do
      {
        *v108++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      v222,
      v192[0]);
    v109 = BCryptExportKey(v92, 0, L"ECCPUBLICBLOB", v222[0], v192[0], v192, 0);
    if ( v109 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x5FE,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v109,
              pcbResultj);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v222);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v110 = pbDerivedKey;
      do
      {
        *v110++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    Buf1 = 0;
    v111 = BCryptSecretAgreement(*(BCRYPT_KEY_HANDLE *)&v192[1], v92, &Buf1, 0);
    if ( v111 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x604,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v111,
              pcbResultj);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buf1);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v222);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v112 = pbDerivedKey;
      do
      {
        *v112++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v238 = 0;
    v240 = 0;
    v241 = 0;
    v233[1] = 0;
    v234 = v204;
    v113 = -1;
    do
      ++v113;
    while ( v204[v113] );
    v233[0] = 2 * v113 + 2;
    v236 = 8;
    v235 = 9;
    v237 = "IDENTITY";
    v239 = 9;
    v238 = *((_DWORD *)v205 + 1);
    v240 = v205 + 8;
    DWORD1(v241) = 10;
    LODWORD(v241) = *((_DWORD *)v222[0] + 1);
    *((_QWORD *)&v241 + 1) = v222[0] + 8;
    *(_QWORD *)&pPaddingInfo.ulVersion = 0x400000000LL;
    pPaddingInfo.pBuffers = (PBCryptBuffer)v233;
    v114 = BCryptDeriveKey(Buf1, L"SP800_56A_CONCAT", &pPaddingInfo, pbDerivedKey, cbDerivedKey, &cbDerivedKey, 0);
    if ( v114 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x61B,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v114,
              pcbResultk);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buf1);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v222);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hAlgorithm);
      v115 = pbDerivedKey;
      do
      {
        *v115++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroySecret(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buf1);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v222);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v192[1]);
    p_hAlgorithm = &hAlgorithm;
  }
  else
  {
    Buf2 = 0;
    v117 = BCryptOpenAlgorithmProvider(&Buf2, L"RNG", 0, 0);
    if ( v117 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x625,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v117,
              pcbResultc);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Buf2);
      v118 = pbDerivedKey;
      do
      {
        *v118++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v119 = BCryptGenRandom(Buf2, pbDerivedKey, cbDerivedKey, 0);
    if ( v119 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x62A,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v119,
              pcbResultc);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&Buf2);
      v120 = pbDerivedKey;
      do
      {
        *v120++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    p_hAlgorithm = &Buf2;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(p_hAlgorithm);
  v121 = KDFa(v204, pbDerivedKey, cbDerivedKey, "STORAGE", v193[0], v72, v181, cbOutput, 8 * v200, v245, 0x20u, &v200);
  v123 = v121;
  if ( v121 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x639,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)(unsigned int)v121,
      pcbResultl);
    v124 = pbDerivedKey;
    do
    {
      *v124++ = 0;
      --v20;
    }
    while ( v20 );
LABEL_258:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v193);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    tpm12class::TPMW8T_SIGNATURE::~TPMW8T_SIGNATURE((tpm12class::TPMW8T_SIGNATURE *)v225);
    v21 = v123;
    goto LABEL_334;
  }
  v125 = v81 + 4;
  v187 = v125;
  *(_OWORD *)v244 = 0;
  v126 = CFB(v245, v200, v244, v122, &v210[v125], v201 - v125);
  v123 = v126;
  if ( v126 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)(unsigned int)v126,
      pcbResultm);
    v127 = pbDerivedKey;
    do
    {
      *v127++ = 0;
      --v20;
    }
    while ( v20 );
    goto LABEL_258;
  }
  memset_0(pbSecret, 0, sizeof(pbSecret));
  v212 = pbSecret;
  v213 = 1;
  cbSecret = v196;
  v128 = KDFa(
           v204,
           pbDerivedKey,
           cbDerivedKey,
           "INTEGRITY",
           0,
           0,
           v182,
           cbOutputa,
           8 * v196,
           pbSecret,
           0x40u,
           &cbSecret);
  v123 = v128;
  if ( v128 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x659,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)(unsigned int)v128,
      pcbResultn);
    v129 = 64;
    v130 = pbSecret;
    do
    {
      *v130++ = 0;
      --v129;
    }
    while ( v129 );
    v131 = pbDerivedKey;
    do
    {
      *v131++ = 0;
      --v20;
    }
    while ( v20 );
    goto LABEL_258;
  }
  v187 = v125;
  v132 = v125;
  v133 = v210;
  v134 = TpmAttiShaHash(v204, pbSecret, cbSecret, &v210[v132], v86 + v72 + 2, v210 + 4, v196, (__int64)&v187);
  v123 = v134;
  if ( v134 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66A,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)(unsigned int)v134,
      pcbResulto);
    v135 = 64;
    v136 = pbSecret;
    do
    {
      *v136++ = 0;
      --v135;
    }
    while ( v135 );
    v137 = pbDerivedKey;
    do
    {
      *v137++ = 0;
      --v20;
    }
    while ( v20 );
    goto LABEL_258;
  }
  v138 = v201;
  v187 = v201 + 2;
  if ( v189 )
  {
    v139 = WriteBigEndian(v133, a9, &v187, *((_WORD *)v89 + 2));
    v123 = v139;
    if ( v139 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x676,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
        (const char *)(unsigned int)v139,
        pcbResulto);
      v140 = 64;
      v141 = pbSecret;
      do
      {
        *v141++ = 0;
        --v140;
      }
      while ( v140 );
      v142 = pbDerivedKey;
      do
      {
        *v142++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_258;
    }
    if ( memcpy_s(&v133[v187], a9 - v187, v205 + 8, *((unsigned int *)v89 + 1)) )
    {
      v21 = -2146893779;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67B,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
        (const char *)0x8009002DLL,
        pcbResulto);
      v143 = 64;
      v144 = pbSecret;
      do
      {
        *v144++ = 0;
        --v143;
      }
      while ( v143 );
      v145 = pbDerivedKey;
      do
      {
        *v145++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
    v187 += *((_DWORD *)v89 + 1);
    v146 = WriteBigEndian(v133, a9, &v187, *((_WORD *)v89 + 2));
    v123 = v146;
    if ( v146 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67D,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
        (const char *)(unsigned int)v146,
        pcbResulto);
      v147 = 64;
      v148 = pbSecret;
      do
      {
        *v148++ = 0;
        --v147;
      }
      while ( v147 );
      v149 = pbDerivedKey;
      do
      {
        *v149++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_258;
    }
    if ( memcpy_s(&v133[v187], a9 - v187, &v205[*((unsigned int *)v89 + 1) + 8], *((unsigned int *)v89 + 1)) )
    {
      v21 = -2146893779;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x682,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
        (const char *)0x8009002DLL,
        pcbResulto);
      v150 = 64;
      v151 = pbSecret;
      do
      {
        *v151++ = 0;
        --v150;
      }
      while ( v150 );
      v152 = pbDerivedKey;
      do
      {
        *v152++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
  }
  else
  {
    v217 = String1;
    v218 = "IDENTITY";
    v219 = 9;
    v153 = BCryptEncrypt(
             hObjecta,
             pbDerivedKey,
             cbDerivedKey,
             &v217,
             0,
             0,
             &v133[v201 + 2],
             a9 - (v201 + 2),
             (ULONG *)v195,
             4u);
    if ( v153 < 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x698,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
              (const char *)(unsigned int)v153,
              pcbResulto);
      v154 = 64;
      v155 = pbSecret;
      do
      {
        *v155++ = 0;
        --v154;
      }
      while ( v154 );
      v156 = pbDerivedKey;
      do
      {
        *v156++ = 0;
        --v20;
      }
      while ( v20 );
      goto LABEL_325;
    }
  }
  v187 = v138;
  v157 = WriteBigEndian(v133, a9, &v187, *(unsigned __int16 *)v195);
  v21 = v157;
  if ( v157 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\attestation20.cpp",
      (const char *)(unsigned int)v157,
      pcbResulto);
    v158 = 64;
    v159 = pbSecret;
    do
    {
      *v159++ = 0;
      --v158;
    }
    while ( v158 );
    v160 = pbDerivedKey;
    do
    {
      *v160++ = 0;
      --v20;
    }
    while ( v20 );
    goto LABEL_325;
  }
  *v209 = a9;
  v161 = 64;
  v162 = pbSecret;
  do
  {
    *v162++ = 0;
    --v161;
  }
  while ( v161 );
  v163 = pbDerivedKey;
  do
  {
    *v163++ = 0;
    --v20;
  }
  while ( v20 );
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v193);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  tpm12class::TPMW8T_SIGNATURE::~TPMW8T_SIGNATURE((tpm12class::TPMW8T_SIGNATURE *)v225);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v205);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v224);
  return 0;
}

```

## disassembly

```asm
0x180063cdc  mov     [rsp-8+arg_10], rbx
0x180063ce1  push    rbp
0x180063ce2  push    rsi
0x180063ce3  push    rdi
0x180063ce4  push    r12
0x180063ce6  push    r13
0x180063ce8  push    r14
0x180063cea  push    r15
0x180063cec  lea     rbp, [rsp-0A90h]
0x180063cf4  sub     rsp, 0B90h
0x180063cfb  mov     rax, cs:__security_cookie
0x180063d02  xor     rax, rsp
0x180063d05  mov     [rbp+0AC0h+var_40], rax
0x180063d0c  mov     [rbp+0AC0h+Buf1], r9
0x180063d10  mov     r15d, r8d
0x180063d13  mov     rsi, rdx
0x180063d16  mov     [rbp+0AC0h+String1], rdx
0x180063d1a  mov     rbx, rcx
0x180063d1d  mov     [rbp+0AC0h+hObject], rcx
0x180063d21  mov     rdi, [rbp+0AC0h+arg_28]
0x180063d28  mov     [rbp+0AC0h+var_A70], rdi
0x180063d2c  mov     r14, [rbp+0AC0h+arg_38]
0x180063d33  mov     [rbp+0AC0h+var_AA8], r14
0x180063d37  mov     r12, [rbp+0AC0h+arg_48]
0x180063d3e  mov     [rbp+0AC0h+var_AB0], r12
0x180063d42  mov     r8b, 1; bool
0x180063d45  lea     rdx, aGenerateactiva; "GenerateActivation20"
0x180063d4c  lea     rcx, [rbp+0AC0h+var_A00]; this
0x180063d53  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180063d58  nop
0x180063d59  xor     edx, edx
0x180063d5b  mov     [rsp+0BC0h+var_B50], edx
0x180063d5f  lea     rcx, [rbp+0AC0h+var_AD0]
0x180063d63  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180063d68  nop
0x180063d69  mov     dword ptr [rbp+0AC0h+var_B08], edx
0x180063d6c  mov     r13d, 100h
0x180063d72  mov     r8d, r13d; Size
0x180063d75  lea     rcx, [rbp+0AC0h+Destination]; void *
0x180063d7c  call    memset_0
0x180063d81  xor     r9d, r9d
0x180063d84  mov     [rbp+0AC0h+var_A40], r9
0x180063d8b  xorps   xmm0, xmm0
0x180063d8e  movups  xmmword ptr [rbp+0AC0h+var_770], xmm0
0x180063d95  movups  [rbp+0AC0h+var_760], xmm0
0x180063d9c  mov     [rbp+0AC0h+var_AF4], 20h ; ' '
0x180063da3  test    rsi, rsi
0x180063da6  jz      loc_180065A3E
0x180063dac  test    r15d, r15d
0x180063daf  jz      loc_180065A3E
0x180063db5  test    rbx, rbx
0x180063db8  jz      loc_180063E5D
0x180063dbe  xor     edx, edx; Val
0x180063dc0  mov     r8d, 208h; Size
0x180063dc6  lea     rcx, [rbp+0AC0h+pbOutput]; void *
0x180063dcd  call    memset_0
0x180063dd2  xor     eax, eax
0x180063dd4  mov     [rbp+0AC0h+var_A78], eax
0x180063dd7  mov     [rsp+0BC0h+dwFlags], eax; dwFlags
0x180063ddb  lea     rax, [rbp+0AC0h+var_A78]
0x180063ddf  mov     [rsp+0BC0h+pcbResult], rax; pcbResult
0x180063de4  mov     r9d, 208h; cbOutput
0x180063dea  lea     r8, [rbp+0AC0h+pbOutput]; pbOutput
0x180063df1  lea     rdx, aAlgorithmname; "AlgorithmName"
0x180063df8  mov     rcx, rbx; hObject
0x180063dfb  call    cs:__imp_BCryptGetProperty
0x180063e02  nop     dword ptr [rax+rax+00h]
0x180063e07  test    eax, eax
0x180063e09  jns     short loc_180063E15
0x180063e0b  mov     edx, 3FDh
0x180063e10  jmp     loc_180063F1A
0x180063e15  lea     rdx, aEcdh; "ECDH"
0x180063e1c  lea     rcx, [rbp+0AC0h+pbOutput]; String1
0x180063e23  call    wcscmp_0
0x180063e28  xor     r9d, r9d
0x180063e2b  test    eax, eax
0x180063e2d  setz    dl
0x180063e30  mov     [rbp+0AC0h+var_B40], dl
0x180063e33  test    rdi, rdi
0x180063e36  jz      loc_180065A37
0x180063e3c  movzx   eax, [rbp+0AC0h+arg_30]
0x180063e43  test    ax, ax
0x180063e46  jz      loc_180065A37
0x180063e4c  test    r12, r12
0x180063e4f  jz      loc_180065A37
0x180063e55  mov     ebx, [rbp+0AC0h+arg_40]
0x180063e5b  jmp     short loc_180063E94
0x180063e5d  movzx   eax, [rbp+0AC0h+arg_30]
0x180063e64  test    rdi, rdi
0x180063e67  jz      short loc_180063E72
0x180063e69  test    ax, ax
0x180063e6c  jnz     loc_180065A37
0x180063e72  mov     ebx, [rbp+0AC0h+arg_40]
0x180063e78  test    r14, r14
0x180063e7b  jz      short loc_180063E85
0x180063e7d  test    ebx, ebx
0x180063e7f  jnz     loc_180065A37
0x180063e85  mov     dl, r9b
0x180063e88  mov     [rbp+0AC0h+var_B40], dl
0x180063e8b  test    r12, r12
0x180063e8e  jnz     loc_180065A37
0x180063e94  mov     [rbp+0AC0h+var_AF0], r9d
0x180063e98  lea     rcx, aSha256_0; "SHA256"
0x180063e9f  mov     [rbp+0AC0h+var_AD8], rcx
0x180063ea3  mov     r12d, 20h ; ' '
0x180063ea9  mov     [rbp+0AC0h+var_B04], r12d
0x180063ead  lea     edi, [r12+20h]
0x180063eb2  lea     r8d, [r12-1Ch]
0x180063eb7  mov     rcx, [rbp+0AC0h+hObject]; hObject
0x180063ebb  test    rcx, rcx
0x180063ebe  jz      loc_180064035
0x180063ec4  cmp     [rbp+0AC0h+var_A70], r9
0x180063ec8  jz      loc_180064035
0x180063ece  test    ax, ax
0x180063ed1  jz      loc_180064035
0x180063ed7  cmp     [rbp+0AC0h+var_AB0], r9
0x180063edb  jz      loc_180064035
0x180063ee1  mov     [rsp+0BC0h+dwFlags], r9d; dwFlags
0x180063ee6  lea     rax, [rsp+0BC0h+var_B50]
0x180063eeb  mov     r9d, r8d; cbOutput
0x180063eee  mov     [rsp+0BC0h+pcbResult], rax; int
0x180063ef3  lea     r8, [rbp+0AC0h+var_B08]; pbOutput
0x180063ef7  test    dl, dl
0x180063ef9  jz      short loc_180063F4C
0x180063efb  lea     rdx, aKeylength; "KeyLength"
0x180063f02  call    cs:__imp_BCryptGetProperty
0x180063f09  nop     dword ptr [rax+rax+00h]
0x180063f0e  xor     r9d, r9d
0x180063f11  test    eax, eax
0x180063f13  jns     short loc_180063F37
0x180063f15  mov     edx, 41Fh; void *
0x180063f1a  mov     rcx, [rbp+0AC8h]; this
0x180063f21  mov     r9d, eax; char *
0x180063f24  lea     r8, aOnecoreBaseNgs_27; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180063f2b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180063f30  mov     ebx, eax
0x180063f32  jmp     loc_180065A5F
0x180063f37  mov     eax, dword ptr [rbp+0AC0h+var_B08]
0x180063f3a  add     eax, 7
0x180063f3d  shr     eax, 3
0x180063f40  lea     edx, ds:4[rax*2]
0x180063f47  mov     dword ptr [rbp+0AC0h+var_B08], edx
0x180063f4a  jmp     short loc_180063F70
0x180063f4c  lea     rdx, aBlocklength; "BlockLength"
0x180063f53  call    cs:__imp_BCryptGetProperty
0x180063f5a  nop     dword ptr [rax+rax+00h]
0x180063f5f  xor     r9d, r9d
0x180063f62  test    eax, eax
0x180063f64  jns     short loc_180063F6D
0x180063f66  mov     edx, 432h
0x180063f6b  jmp     short loc_180063F1A
0x180063f6d  mov     edx, dword ptr [rbp+0AC0h+var_B08]
0x180063f70  mov     eax, edx
0x180063f72  sub     eax, 44h ; 'D'
0x180063f75  jz      short loc_180063F97
0x180063f77  sub     eax, r12d
0x180063f7a  jz      loc_18006400C
0x180063f80  sub     eax, 24h ; '$'
0x180063f83  jz      short loc_180063FFD
0x180063f85  sub     eax, 78h ; 'x'
0x180063f88  jz      short loc_180063F97
0x180063f8a  mov     ecx, 80h
0x180063f8f  sub     eax, ecx
0x180063f91  jz      short loc_18006400C
0x180063f93  cmp     eax, ecx
0x180063f95  jz      short loc_18006400C
0x180063f97  lea     r8, aSha256_0; "SHA256"
0x180063f9e  mov     [rbp+0AC0h+var_B04], r12d
0x180063fa2  mov     [rbp+0AC0h+var_AF4], 10h
0x180063fa9  mov     [rbp+0AC0h+var_AD8], r8
0x180063fad  mov     al, [rbp+0AC0h+var_B40]
0x180063fb0  neg     al
0x180063fb2  sbb     ecx, ecx
0x180063fb4  and     ecx, 0FFFFFF44h
0x180063fba  add     ecx, r13d
0x180063fbd  cmp     edx, ecx
0x180063fbf  jb      short loc_18006402B
0x180063fc1  movzx   eax, [rbp+0AC0h+arg_30]
0x180063fc8  cmp     eax, r12d
0x180063fcb  ja      short loc_18006402B
0x180063fcd  add     eax, 6
0x180063fd0  add     eax, r12d
0x180063fd3  mov     [rbp+0AC0h+var_AF0], eax
0x180063fd6  add     eax, 2
0x180063fd9  add     eax, edx
0x180063fdb  mov     rcx, [rbp+0AC0h+var_AB0]
0x180063fdf  mov     [rcx], eax
0x180063fe1  test    r14, r14
0x180063fe4  jz      short loc_180064023
0x180063fe6  test    ebx, ebx
0x180063fe8  jz      short loc_180064023
0x180063fea  cmp     ebx, eax
0x180063fec  jnb     short loc_180064035
0x180063fee  mov     ebx, 80090028h
0x180063ff3  mov     edx, 463h
0x180063ff8  jmp     loc_180065A48
0x180063ffd  lea     r8, aSha512; "SHA512"
0x180064004  mov     r12d, edi
0x180064007  mov     [rbp+0AC0h+var_B04], edi
0x18006400a  jmp     short loc_180063FA9
0x18006400c  lea     rax, aSha384; "SHA384"
0x180064013  mov     [rbp+0AC0h+var_AD8], rax
0x180064017  mov     r12d, 30h ; '0'
0x18006401d  mov     [rbp+0AC0h+var_B04], r12d
0x180064021  jmp     short loc_180063FAD
0x180064023  mov     ebx, r9d
0x180064026  jmp     loc_180065A5F
0x18006402b  mov     edx, 455h
0x180064030  jmp     loc_180065A43
0x180064035  mov     [rsp+0BC0h+var_B50], r9d
0x18006403a  mov     [rbp+0AC0h+Buf2], r9
0x18006403e  mov     dword ptr [rsp+0BC0h+hAlgorithm], r9d
0x180064043  lea     rax, [rbp+0AC0h+Buf2]
0x180064047  mov     [rsp+0BC0h+pcbResult], rax; unsigned __int8 **
0x18006404c  lea     r9, [rsp+0BC0h+hAlgorithm]; unsigned __int16 *
0x180064051  lea     r8, [rsp+0BC0h+var_B50]; unsigned int *
0x180064056  mov     edx, r15d; unsigned int
0x180064059  mov     rcx, rsi; unsigned __int8 *
0x18006405c  call    ?ReadBigEndian2B@@YAJPEBEIPEAIPEAGPEAPEBE@Z; ReadBigEndian2B(uchar const *,uint,uint *,ushort *,uchar const * *)
0x180064061  mov     ebx, eax
0x180064063  test    eax, eax
0x180064065  jns     short loc_180064074
0x180064067  mov     r9d, eax
0x18006406a  mov     edx, 46Ah
0x18006406f  jmp     loc_180065A4B
0x180064074  mov     r14d, dword ptr [rsp+0BC0h+hAlgorithm]
0x180064079  cmp     r14d, 2
0x18006407d  jnb     short loc_18006408E
0x18006407f  mov     ebx, 80090027h
0x180064084  mov     edx, 46Ch
0x180064089  jmp     loc_180065A48
0x18006408e  mov     r8b, 1; bool
0x180064091  mov     edx, r14d; unsigned int
0x180064094  mov     rsi, [rbp+0AC0h+Buf2]
0x180064098  mov     rcx, rsi; unsigned __int8 *
0x18006409b  call    ?ValidateTPublicKeyAttributes@@YAJPEBEI_N@Z; ValidateTPublicKeyAttributes(uchar const *,uint,bool)
0x1800640a0  mov     ebx, eax
0x1800640a2  xor     edx, edx
0x1800640a4  test    eax, eax
0x1800640a6  jns     short loc_1800640B5
0x1800640a8  mov     r9d, eax
0x1800640ab  mov     edx, 46Eh
0x1800640b0  jmp     loc_180065A4B
0x1800640b5  movzx   eax, word ptr [rsi]
0x1800640b8  shl     ax, 8
0x1800640bc  movzx   ecx, ax
0x1800640bf  movzx   eax, byte ptr [rsi+1]
0x1800640c3  or      ecx, eax
0x1800640c5  sub     ecx, 1
0x1800640c8  jz      short loc_1800640EE
0x1800640ca  cmp     ecx, 22h ; '"'
0x1800640cd  jz      short loc_1800640DE
0x1800640cf  mov     ebx, 80090029h
0x1800640d4  mov     edx, 47Eh
0x1800640d9  jmp     loc_180065A48
0x1800640de  mov     [rbp+0AC0h+pPaddingInfo], rdx
0x1800640e2  mov     [rbp+0AC0h+cbSecret], edx
0x1800640e5  lea     r12, aEcdsa; "ECDSA"
0x1800640ec  jmp     short loc_180064107
0x1800640ee  lea     r12, aRsa; "RSA"
0x1800640f5  lea     rax, [rbp+0AC0h+var_A40]
0x1800640fc  mov     [rbp+0AC0h+pPaddingInfo], rax
0x180064100  mov     [rbp+0AC0h+cbSecret], 2
0x180064107  mov     [rbp+0AC0h+var_A38], rdx
0x18006410e  mov     dword ptr [rbp+0AC0h+var_B34+4], edx
0x180064111  lea     rax, [rbp+0AC0h+var_A38]
0x180064118  mov     [rsp+0BC0h+pcbResult], rax; unsigned __int8 **
0x18006411d  lea     r9, [rbp+0AC0h+var_B34+4]; unsigned __int16 *
0x180064121  lea     r8, [rsp+0BC0h+var_B50]; unsigned int *
0x180064126  mov     edx, r15d; unsigned int
0x180064129  mov     rcx, [rbp+0AC0h+String1]; unsigned __int8 *
0x18006412d  call    ?ReadBigEndian2B@@YAJPEBEIPEAIPEAGPEAPEBE@Z; ReadBigEndian2B(uchar const *,uint,uint *,ushort *,uchar const * *)
0x180064132  mov     ebx, eax
0x180064134  xor     eax, eax
0x180064136  test    ebx, ebx
0x180064138  jns     short loc_180064144
0x18006413a  mov     edx, 484h
0x18006413f  jmp     loc_180065A48
0x180064144  mov     [rbp+0AC0h+Buf2], rax
0x180064148  mov     dword ptr [rbp+0AC0h+var_B3C], eax
0x18006414b  lea     rax, [rbp+0AC0h+Buf2]
0x18006414f  mov     [rsp+0BC0h+pcbResult], rax; unsigned __int8 **
0x180064154  lea     r9, [rbp+0AC0h+var_B3C]; unsigned __int16 *
0x180064158  lea     r8, [rsp+0BC0h+var_B50]; unsigned int *
0x18006415d  mov     edx, r15d; unsigned int
0x180064160  mov     rcx, [rbp+0AC0h+String1]; unsigned __int8 *
0x180064164  call    ?ReadBigEndian2B@@YAJPEBEIPEAIPEAGPEAPEBE@Z; ReadBigEndian2B(uchar const *,uint,uint *,ushort *,uchar const * *)
0x180064169  mov     ebx, eax
0x18006416b  test    eax, eax
0x18006416d  jns     short loc_18006417C
0x18006416f  mov     r9d, eax
0x180064172  mov     edx, 489h
0x180064177  jmp     loc_180065A4B
0x18006417c  lea     rcx, [rbp+0AC0h+var_9E0]; this
0x180064183  call    ??0TPMW8T_SIGNATURE@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_SIGNATURE::TPMW8T_SIGNATURE(void)
0x180064188  nop
0x180064189  sub     r15w, word ptr [rsp+0BC0h+var_B50]
0x18006418f  movzx   r8d, r15w; unsigned int
0x180064193  mov     edx, [rsp+0BC0h+var_B50]
0x180064197  add     rdx, [rbp+0AC0h+String1]; unsigned __int8 *
  ... truncated ...
```
