# VsmUtils::SignWithRsaKey(VsmUtils::Vtl0KeyBlob *,uchar *,uint,void const *,VsmUtils::TpmAuthType,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x14005cb94`
- end: `0x14005d0c8`
- name: `?SignWithRsaKey@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEAEIPEBXW4TpmAuthType@1@1I1I1IPEAIK@Z`
- size: `1332`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140059044`

## callees

- `0x14000e034`
- `0x14000f6a0`
- `0x1400104fc`
- `0x140010514`
- `0x1400389ec`
- `0x140052e88`
- `0x14005522c`
- `0x140055470`
- `0x140056a48`
- `0x140056fb4`
- `0x14005acf4`
- `0x14005afe4`
- `0x14005b484`
- `0x14005c5c4`
- `0x14005cb94`
- `0x1400624d4`
- `0x140065c28`
- `0x14006abb0`
- `0x14006ac88`
- `0x14006b794`

## string_xrefs

- `0x14005cd01`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005cdfd`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005cf16`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005cf46`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005cf7f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005cfaf`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005cfe4`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005d014`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005d05f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`
- `0x14005d091`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsrsa.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VsmUtils::SignWithRsaKey(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        VsmUtils *a6,
        unsigned __int8 *a7,
        VsmUtils *a8,
        unsigned __int8 *a9,
        void *a10,
        unsigned int a11,
        _DWORD *a12,
        int a13)
{
  unsigned __int8 *v15; // r12
  _DWORD *v17; // r14
  unsigned int v18; // r15d
  unsigned __int8 *v20; // r9
  unsigned int v21; // ebx
  __int64 v22; // rdx
  int v23; // eax
  unsigned int v24; // edi
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rdx
  unsigned int v29; // eax
  int v30; // eax
  __int16 v31; // ax
  int v32; // ebx
  int v33; // eax
  unsigned int v34; // r9d
  int v35; // eax
  unsigned int v36; // r8d
  int v37; // eax
  unsigned int v38; // eax
  int v39; // edx
  int v40; // eax
  unsigned int v41; // r8d
  int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // r8d
  int v45; // eax
  unsigned int v46; // r8d
  int v47; // eax
  unsigned __int8 *v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  unsigned int v52; // [rsp+28h] [rbp-D8h]
  VsmUtils *v54; // [rsp+78h] [rbp-88h] BYREF
  char v55; // [rsp+81h] [rbp-7Fh]
  VsmUtils *v56; // [rsp+88h] [rbp-78h]
  void *v57; // [rsp+90h] [rbp-70h]
  VsmUtils **v58; // [rsp+98h] [rbp-68h]
  unsigned __int8 **v59; // [rsp+A0h] [rbp-60h]
  char v60; // [rsp+A8h] [rbp-58h]
  _BYTE v61[168]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v62; // [rsp+158h] [rbp+58h]
  int v63; // [rsp+170h] [rbp+70h]
  _BYTE v64[72]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v65[128]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int16 v66; // [rsp+240h] [rbp+140h]
  __int16 v67; // [rsp+242h] [rbp+142h]
  __int16 v68; // [rsp+280h] [rbp+180h]
  int v69; // [rsp+284h] [rbp+184h]
  unsigned __int16 v70; // [rsp+348h] [rbp+248h]
  void *Src; // [rsp+350h] [rbp+250h]
  unsigned int v72[64]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5B8h] [rbp+4B8h]

  v15 = a2;
  v54 = a6;
  v56 = a8;
  v57 = a10;
  v17 = a12;
  if ( !a1 || !a2 || !a12 )
  {
    v21 = -2147024809;
    v22 = 31;
    goto LABEL_59;
  }
  v18 = a11;
  if ( !a10 && !a11 )
  {
    *a12 = 256;
    return 0;
  }
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl'::`2'::impl,
    a2);
  if ( (a13 & 2) == 0 || !a4 || *(_QWORD *)a4 )
  {
    SetTbsHandle(*(_QWORD *)(a1 + 40));
    v55 = 1;
    tpm12class::TPMW8_Sign::TPMW8_Sign((tpm12class::TPMW8_Sign *)v61);
    v63 = *(_DWORD *)(a1 + 48);
    v25 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)v64,
            (const unsigned __int8 *)(a1 + 4),
            0x22u);
    v21 = v25;
    if ( v25 < 0 )
    {
      v27 = (unsigned int)v25;
      v28 = 105;
      goto LABEL_28;
    }
    LOBYTE(v26) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl'::`2'::impl,
      v26);
    if ( a13 == 2 )
    {
      v66 = 20;
      if ( a4 && !wcscmp_0(*(const wchar_t **)a4, L"SHA256") )
        v67 = 11;
      goto LABEL_21;
    }
    if ( a13 != 8 )
    {
LABEL_21:
      v29 = a3;
      goto LABEL_22;
    }
    if ( !a4 )
    {
      v28 = 120;
      goto LABEL_27;
    }
    v66 = 22;
    if ( !wcscmp_0(*(const wchar_t **)a4, L"SHA256") )
    {
      v31 = 11;
      v32 = 32;
    }
    else if ( !wcscmp_0(*(const wchar_t **)a4, L"SHA384") )
    {
      v31 = 12;
      v32 = 48;
    }
    else
    {
      v32 = 0;
      if ( wcscmp_0(*(const wchar_t **)a4, L"SHA512") )
        goto LABEL_36;
      v31 = 13;
      v32 = 64;
    }
    v67 = v31;
LABEL_36:
    v29 = a3;
    if ( a3 == v32 )
    {
      if ( *(_DWORD *)(a4 + 8) == v32 )
      {
LABEL_22:
        v68 = -32732;
        v69 = 1073741831;
        v30 = tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v65, v15, v29);
        v21 = v30;
        if ( v30 >= 0 )
        {
          LODWORD(v48) = (_DWORD)a7;
          v33 = VsmUtils::AuthorizeSignCommand(
                  (VsmUtils *)a1,
                  (struct VsmUtils::Vtl0KeyBlob *)v61,
                  (struct tpm12class::TPMW8_Sign *)L"RSA",
                  (const unsigned __int16 *)v54,
                  v48,
                  v52);
          v21 = v33;
          if ( v33 >= 0 )
          {
            v58 = &v54;
            v59 = &a7;
            v60 = 1;
            v35 = VsmUtils::ExecutePolicyOr(v56, (unsigned __int8 *)(unsigned int)a9, *(_DWORD *)(v62 + 16), v34);
            v21 = v35;
            if ( v35 >= 0 )
            {
              v38 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v61, 0);
              v40 = VsmUtils::MapTpmError((VsmUtils *)v38, v39);
              v21 = v40;
              if ( v40 >= 0 )
              {
                v43 = v70;
                *v17 = v70;
                if ( v43 <= v18 )
                {
                  memcpy_0(v57, Src, v70);
                  v47 = VsmUtils::CloseVtl1AuthBlob(v54, (unsigned __int8 *)(unsigned int)a7, v46);
                  if ( v47 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0xAE,
                      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
                      (const char *)(unsigned int)v47,
                      (int)v48);
                  v21 = 0;
                }
                else
                {
                  v21 = -2146893784;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xB8,
                    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
                    (const char *)0x80090028LL,
                    (int)v48);
                  v45 = VsmUtils::CloseVtl1AuthBlob(v54, (unsigned __int8 *)(unsigned int)a7, v44);
                  if ( v45 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0xAE,
                      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
                      (const char *)(unsigned int)v45,
                      v51);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB4,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
                  (const char *)(unsigned int)v40,
                  (int)v48);
                v42 = VsmUtils::CloseVtl1AuthBlob(v54, (unsigned __int8 *)(unsigned int)a7, v41);
                if ( v42 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0xAE,
                    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
                    (const char *)(unsigned int)v42,
                    v50);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xB2,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
                (const char *)(unsigned int)v35,
                (int)v48);
              v37 = VsmUtils::CloseVtl1AuthBlob(v54, (unsigned __int8 *)(unsigned int)a7, v36);
              if ( v37 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xAE,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
                  (const char *)(unsigned int)v37,
                  v49);
            }
            goto LABEL_57;
          }
          v27 = (unsigned int)v33;
          v28 = 165;
        }
        else
        {
          v27 = (unsigned int)v30;
          v28 = 160;
        }
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v28,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
          (const char *)v27,
          (int)v48);
LABEL_57:
        tpm12class::TPMW8_Sign::~TPMW8_Sign((tpm12class::TPMW8_Sign *)v61);
        ClearTbsHandle();
        return v21;
      }
      v28 = 140;
    }
    else
    {
      v28 = 139;
    }
LABEL_27:
    v21 = -2147024809;
    v27 = 2147942487LL;
    goto LABEL_28;
  }
  memset_0(v72, 0, sizeof(v72));
  v21 = VsmUtils::ApplyPkcs1Padding((VsmUtils *)v15, a3, (unsigned int)v72, v20, (unsigned int)v48);
  if ( (v21 & 0x80000000) != 0 )
  {
    v22 = 49;
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
      (const char *)v21,
      (int)v48);
    return v21;
  }
  v23 = VsmUtils::Decrypt(a1, v72, 0x100u);
  v24 = v23;
  if ( v23 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsrsa.cpp",
    (const char *)(unsigned int)v23,
    (int)v48);
  return v24;
}

```

## disassembly

```asm
0x14005cb94  push    rbp
0x14005cb96  push    rbx
0x14005cb97  push    rdi
0x14005cb98  push    r12
0x14005cb9a  push    r13
0x14005cb9c  push    r14
0x14005cb9e  push    r15
0x14005cba0  lea     rbp, [rsp-480h]
0x14005cba8  sub     rsp, 580h
0x14005cbaf  mov     rax, cs:__security_cookie
0x14005cbb6  xor     rax, rsp
0x14005cbb9  mov     [rbp+4B0h+var_40], rax
0x14005cbc0  mov     rdi, r9
0x14005cbc3  mov     ebx, r8d
0x14005cbc6  mov     dword ptr [rsp+5B0h+var_540], ebx
0x14005cbca  mov     r12, rdx
0x14005cbcd  mov     r13, rcx
0x14005cbd0  mov     rax, [rbp+4B0h+arg_28]
0x14005cbd7  mov     [rsp+5B0h+var_538], rax
0x14005cbdc  mov     rax, [rbp+4B0h+arg_38]
0x14005cbe3  mov     [rbp+4B0h+var_528], rax
0x14005cbe7  mov     rax, [rbp+4B0h+arg_48]
0x14005cbee  mov     [rbp+4B0h+var_520], rax
0x14005cbf2  mov     r14, [rbp+4B0h+arg_58]
0x14005cbf9  test    rcx, rcx
0x14005cbfc  jz      loc_14005D084
0x14005cc02  test    rdx, rdx
0x14005cc05  jz      loc_14005D084
0x14005cc0b  test    r14, r14
0x14005cc0e  jz      loc_14005D084
0x14005cc14  mov     r15d, [rbp+4B0h+arg_50]
0x14005cc1b  test    rax, rax
0x14005cc1e  jnz     short loc_14005CC33
0x14005cc20  test    r15d, r15d
0x14005cc23  jnz     short loc_14005CC33
0x14005cc25  mov     dword ptr [r14], 100h
0x14005cc2c  xor     eax, eax
0x14005cc2e  jmp     loc_14005D0A6
0x14005cc33  mov     dl, 1
0x14005cc35  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS> `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl(void)'::`2'::impl
0x14005cc3c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14005cc41  test    byte ptr [rbp+4B0h+arg_60], 2
0x14005cc48  jz      loc_14005CD19
0x14005cc4e  test    rdi, rdi
0x14005cc51  jz      loc_14005CD19
0x14005cc57  cmp     qword ptr [rdi], 0
0x14005cc5b  jnz     loc_14005CD19
0x14005cc61  xor     edx, edx; Val
0x14005cc63  mov     r8d, 100h; Size
0x14005cc69  lea     rcx, [rbp+4B0h+var_140]; void *
0x14005cc70  call    memset_0
0x14005cc75  lea     r8, [rbp+4B0h+var_140]; unsigned int
0x14005cc7c  mov     edx, ebx; Size
0x14005cc7e  mov     rcx, r12; this
0x14005cc81  call    ?ApplyPkcs1Padding@VsmUtils@@YAJPEAEI0I@Z; VsmUtils::ApplyPkcs1Padding(uchar *,uint,uchar *,uint)
0x14005cc86  mov     ebx, eax
0x14005cc88  test    eax, eax
0x14005cc8a  jns     short loc_14005CC96
0x14005cc8c  mov     edx, 31h ; '1'
0x14005cc91  jmp     loc_14005D08E
0x14005cc96  mov     [rsp+5B0h+var_550], 0
0x14005cc9e  mov     [rsp+5B0h+var_558], r14
0x14005cca3  mov     [rsp+5B0h+var_560], r15d
0x14005cca8  mov     rcx, [rbp+4B0h+var_520]
0x14005ccac  mov     [rsp+5B0h+var_568], rcx
0x14005ccb1  mov     eax, dword ptr [rbp+4B0h+arg_40]
0x14005ccb7  mov     [rsp+5B0h+var_570], eax
0x14005ccbb  mov     rcx, [rbp+4B0h+var_528]
0x14005ccbf  mov     [rsp+5B0h+var_578], rcx
0x14005ccc4  mov     eax, dword ptr [rbp+4B0h+arg_30]
0x14005ccca  mov     [rsp+5B0h+var_580], eax
0x14005ccce  mov     rax, [rsp+5B0h+var_538]
0x14005ccd3  mov     [rsp+5B0h+var_588], rax
0x14005ccd8  mov     r8d, 100h
0x14005ccde  lea     rdx, [rbp+4B0h+var_140]
0x14005cce5  mov     rcx, r13
0x14005cce8  call    ?Decrypt@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEAEIPEBGW4TpmAuthType@1@1I1I1IPEAIK@Z; VsmUtils::Decrypt(VsmUtils::Vtl0KeyBlob *,uchar *,uint,ushort const *,VsmUtils::TpmAuthType,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x14005cced  mov     edi, eax
0x14005ccef  test    eax, eax
0x14005ccf1  jns     loc_14005CC2C
0x14005ccf7  mov     rcx, [rbp+4B8h]; this
0x14005ccfe  mov     r9d, eax; char *
0x14005cd01  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cd08  mov     edx, 40h ; '@'; void *
0x14005cd0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005cd12  mov     eax, edi
0x14005cd14  jmp     loc_14005D0A6
0x14005cd19  mov     rcx, [r13+28h]; unsigned __int64
0x14005cd1d  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x14005cd22  mov     [rbp+4B0h+var_52F], 1
0x14005cd26  lea     rcx, [rbp+4B0h+var_500]; this
0x14005cd2a  call    ??0TPMW8_Sign@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Sign::TPMW8_Sign(void)
0x14005cd2f  nop
0x14005cd30  mov     eax, [r13+30h]
0x14005cd34  mov     [rbp+4B0h+var_440], eax
0x14005cd37  lea     rdx, [r13+4]; unsigned __int8 *
0x14005cd3b  mov     r8d, 22h ; '"'; unsigned __int64
0x14005cd41  lea     rcx, [rbp+4B0h+var_438]; this
0x14005cd45  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005cd4a  mov     ebx, eax
0x14005cd4c  test    eax, eax
0x14005cd4e  jns     short loc_14005CD5D
0x14005cd50  mov     r9d, eax
0x14005cd53  mov     edx, 69h ; 'i'
0x14005cd58  jmp     loc_14005CDFD
0x14005cd5d  mov     dl, 1
0x14005cd5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS> `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl(void)'::`2'::impl
0x14005cd66  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14005cd6b  cmp     [rbp+4B0h+arg_60], 2
0x14005cd72  jnz     short loc_14005CDE4
0x14005cd74  mov     eax, 14h
0x14005cd79  mov     [rbp+4B0h+var_370], ax
0x14005cd80  test    rdi, rdi
0x14005cd83  jz      short loc_14005CDA4
0x14005cd85  lea     rdx, aSha256; "SHA256"
0x14005cd8c  mov     rcx, [rdi]; String1
0x14005cd8f  call    wcscmp_0
0x14005cd94  test    eax, eax
0x14005cd96  jnz     short loc_14005CDA4
0x14005cd98  mov     eax, 0Bh
0x14005cd9d  mov     [rbp+4B0h+var_36E], ax
0x14005cda4  mov     eax, dword ptr [rsp+5B0h+var_540]
0x14005cda8  mov     ecx, 8024h
0x14005cdad  mov     [rbp+4B0h+var_330], cx
0x14005cdb4  mov     [rbp+4B0h+var_32C], 40000007h
0x14005cdbe  mov     r8d, eax; unsigned __int64
0x14005cdc1  mov     rdx, r12; unsigned __int8 *
0x14005cdc4  lea     rcx, [rbp+4B0h+var_3F0]; this
0x14005cdcb  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005cdd0  mov     ebx, eax
0x14005cdd2  test    eax, eax
0x14005cdd4  jns     loc_14005CEA2
0x14005cdda  mov     r9d, eax
0x14005cddd  mov     edx, 0A0h
0x14005cde2  jmp     short loc_14005CDFD
0x14005cde4  cmp     [rbp+4B0h+arg_60], 8
0x14005cdeb  jnz     short loc_14005CDA4
0x14005cded  test    rdi, rdi
0x14005cdf0  jnz     short loc_14005CE15
0x14005cdf2  lea     edx, [rdi+78h]; void *
0x14005cdf5  mov     ebx, 80070057h
0x14005cdfa  mov     r9d, ebx; char *
0x14005cdfd  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005ce04  mov     rcx, [rbp+4B8h]; this
0x14005ce0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ce10  jmp     loc_14005D073
0x14005ce15  mov     eax, 16h
0x14005ce1a  mov     [rbp+4B0h+var_370], ax
0x14005ce21  lea     rdx, aSha256; "SHA256"
0x14005ce28  mov     rcx, [rdi]; String1
0x14005ce2b  call    wcscmp_0
0x14005ce30  test    eax, eax
0x14005ce32  jnz     short loc_14005CE3E
0x14005ce34  mov     eax, 0Bh
0x14005ce39  lea     ebx, [rax+15h]
0x14005ce3c  jmp     short loc_14005CE76
0x14005ce3e  lea     rdx, aSha384; "SHA384"
0x14005ce45  mov     rcx, [rdi]; String1
0x14005ce48  call    wcscmp_0
0x14005ce4d  test    eax, eax
0x14005ce4f  jnz     short loc_14005CE5B
0x14005ce51  mov     eax, 0Ch
0x14005ce56  lea     ebx, [rax+24h]
0x14005ce59  jmp     short loc_14005CE76
0x14005ce5b  xor     ebx, ebx
0x14005ce5d  lea     rdx, aSha512; "SHA512"
0x14005ce64  mov     rcx, [rdi]; String1
0x14005ce67  call    wcscmp_0
0x14005ce6c  test    eax, eax
0x14005ce6e  jnz     short loc_14005CE7D
0x14005ce70  lea     eax, [rbx+0Dh]
0x14005ce73  lea     ebx, [rax+33h]
0x14005ce76  mov     [rbp+4B0h+var_36E], ax
0x14005ce7d  mov     eax, dword ptr [rsp+5B0h+var_540]
0x14005ce81  cmp     eax, ebx
0x14005ce83  jz      short loc_14005CE8F
0x14005ce85  mov     edx, 8Bh
0x14005ce8a  jmp     loc_14005CDF5
0x14005ce8f  cmp     [rdi+8], ebx
0x14005ce92  jz      loc_14005CDA8
0x14005ce98  mov     edx, 8Ch
0x14005ce9d  jmp     loc_14005CDF5
0x14005cea2  mov     eax, dword ptr [rbp+4B0h+arg_30]
0x14005cea8  mov     dword ptr [rsp+5B0h+var_590], eax; int
0x14005ceac  mov     r9, [rsp+5B0h+var_538]; unsigned __int16 *
0x14005ceb1  lea     r8, aRsa; "RSA"
0x14005ceb8  lea     rdx, [rbp+4B0h+var_500]; struct VsmUtils::Vtl0KeyBlob *
0x14005cebc  mov     rcx, r13; this
0x14005cebf  call    ?AuthorizeSignCommand@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEAVTPMW8_Sign@tpm12class@@PEBGPEAEI@Z; VsmUtils::AuthorizeSignCommand(VsmUtils::Vtl0KeyBlob *,tpm12class::TPMW8_Sign *,ushort const *,uchar *,uint)
0x14005cec4  mov     ebx, eax
0x14005cec6  test    eax, eax
0x14005cec8  jns     short loc_14005CED7
0x14005ceca  mov     r9d, eax
0x14005cecd  mov     edx, 0A5h
0x14005ced2  jmp     loc_14005CDFD
0x14005ced7  lea     rax, [rsp+5B0h+var_538]
0x14005cedc  mov     [rbp+4B0h+var_518], rax
0x14005cee0  lea     rax, [rbp+4B0h+arg_30]
0x14005cee7  mov     [rbp+4B0h+var_510], rax
0x14005ceeb  mov     [rbp+4B0h+var_508], 1
0x14005ceef  mov     r8, [rbp+4B0h+var_458]
0x14005cef3  mov     r8d, [r8+10h]; unsigned int
0x14005cef7  mov     edx, dword ptr [rbp+4B0h+arg_40]; unsigned __int8 *
0x14005cefd  mov     rcx, [rbp+4B0h+var_528]; this
0x14005cf01  call    ?ExecutePolicyOr@VsmUtils@@YAJPEAEII@Z; VsmUtils::ExecutePolicyOr(uchar *,uint,uint)
0x14005cf06  mov     ebx, eax
0x14005cf08  test    eax, eax
0x14005cf0a  jns     short loc_14005CF5D
0x14005cf0c  mov     rcx, [rbp+4B8h]; this
0x14005cf13  mov     r9d, eax; char *
0x14005cf16  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cf1d  mov     edx, 0B2h; void *
0x14005cf22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005cf27  nop
0x14005cf28  mov     edx, dword ptr [rbp+4B0h+arg_30]; unsigned __int8 *
0x14005cf2e  mov     rcx, [rsp+5B0h+var_538]; this
0x14005cf33  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005cf38  mov     rcx, [rbp+4B8h]; this
0x14005cf3f  test    eax, eax
0x14005cf41  jns     short loc_14005CF58
0x14005cf43  mov     r9d, eax; char *
0x14005cf46  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cf4d  mov     edx, 0AEh; void *
0x14005cf52  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005cf57  nop
0x14005cf58  jmp     loc_14005D073
0x14005cf5d  xor     edx, edx; void *
0x14005cf5f  lea     rcx, [rbp+4B0h+var_500]; this
0x14005cf63  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x14005cf68  mov     ecx, eax; this
0x14005cf6a  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x14005cf6f  mov     ebx, eax
0x14005cf71  test    eax, eax
0x14005cf73  jns     short loc_14005CFC6
0x14005cf75  mov     rcx, [rbp+4B8h]; this
0x14005cf7c  mov     r9d, eax; char *
0x14005cf7f  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cf86  mov     edx, 0B4h; void *
0x14005cf8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005cf90  nop
0x14005cf91  mov     edx, dword ptr [rbp+4B0h+arg_30]; unsigned __int8 *
0x14005cf97  mov     rcx, [rsp+5B0h+var_538]; this
0x14005cf9c  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005cfa1  mov     rcx, [rbp+4B8h]; this
0x14005cfa8  test    eax, eax
0x14005cfaa  jns     short loc_14005CFC1
0x14005cfac  mov     r9d, eax; char *
0x14005cfaf  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cfb6  mov     edx, 0AEh; void *
0x14005cfbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005cfc0  nop
0x14005cfc1  jmp     loc_14005D073
0x14005cfc6  movzx   eax, [rbp+4B0h+var_268]
0x14005cfcd  mov     [r14], eax
0x14005cfd0  cmp     eax, r15d
0x14005cfd3  jbe     short loc_14005D028
0x14005cfd5  mov     rcx, [rbp+4B8h]; this
0x14005cfdc  mov     ebx, 80090028h
0x14005cfe1  mov     r9d, ebx; char *
0x14005cfe4  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cfeb  mov     edx, 0B8h; void *
0x14005cff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005cff5  nop
0x14005cff6  mov     edx, dword ptr [rbp+4B0h+arg_30]; unsigned __int8 *
0x14005cffc  mov     rcx, [rsp+5B0h+var_538]; this
0x14005d001  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005d006  mov     rcx, [rbp+4B8h]; this
0x14005d00d  test    eax, eax
0x14005d00f  jns     short loc_14005D026
0x14005d011  mov     r9d, eax; char *
0x14005d014  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005d01b  mov     edx, 0AEh; void *
0x14005d020  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005d025  nop
0x14005d026  jmp     short loc_14005D073
0x14005d028  movzx   r8d, [rbp+4B0h+var_268]; Size
0x14005d030  mov     rdx, [rbp+4B0h+Src]; Src
0x14005d037  mov     rcx, [rbp+4B0h+var_520]; void *
0x14005d03b  call    memcpy_0
0x14005d040  nop
0x14005d041  mov     edx, dword ptr [rbp+4B0h+arg_30]; unsigned __int8 *
0x14005d047  mov     rcx, [rsp+5B0h+var_538]; this
0x14005d04c  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005d051  mov     rcx, [rbp+4B8h]; this
0x14005d058  test    eax, eax
0x14005d05a  jns     short loc_14005D071
0x14005d05c  mov     r9d, eax; char *
0x14005d05f  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\trustlet\\utils"...
0x14005d066  mov     edx, 0AEh; void *
0x14005d06b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005d070  nop
0x14005d071  xor     ebx, ebx
0x14005d073  lea     rcx, [rbp+4B0h+var_500]; this
0x14005d077  call    ??1TPMW8_Sign@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Sign::~TPMW8_Sign(void)
0x14005d07c  nop
0x14005d07d  call    ?ClearTbsHandle@@YAXXZ; ClearTbsHandle(void)
0x14005d082  jmp     short loc_14005D0A4
0x14005d084  mov     ebx, 80070057h
0x14005d089  mov     edx, 1Fh; void *
0x14005d08e  mov     r9d, ebx; char *
  ... truncated ...
```
