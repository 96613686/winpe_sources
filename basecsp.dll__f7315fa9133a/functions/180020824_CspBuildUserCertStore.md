# CspBuildUserCertStore

- ea: `0x180020824`
- end: `0x180020cd3`
- name: `CspBuildUserCertStore`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180011da0`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x1800196ac`
- `0x18001ef0c`
- `0x18001f3a4`
- `0x180020204`
- `0x180020394`
- `0x180020824`
- `0x180020cdc`
- `0x180021e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c44`
- `CRYPT32!CertCreateCertificateContext` at `0x180020a87`
- `CRYPT32!CertCreateCertificateContext` at `0x180020a87`
- `CRYPT32!CertFreeCertificateContext` at `0x180020a0d`
- `CRYPT32!CertFreeCertificateContext` at `0x180020c81`
- `CRYPT32!CertFreeCertificateContext` at `0x180020a0d`
- `CRYPT32!CertFreeCertificateContext` at `0x180020c81`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180020b8c`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180020b8c`
- `CRYPT32!CertCloseStore` at `0x180020c5e`
- `CRYPT32!CertCloseStore` at `0x180020c5e`
- `CRYPT32!CertOpenStore` at `0x1800208f5`
- `CRYPT32!CertOpenStore` at `0x1800208f5`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020b09`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020b27`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020b6d`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020b09`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020b27`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020b6d`

## pseudocode

```c
__int64 __fastcall CspBuildUserCertStore(__int64 a1, __int64 a2, int a3, HCERTSTORE *a4)
{
  char *v6; // rsi
  const CERT_CONTEXT *CertificateContext; // r14
  __int64 v8; // r12
  DWORD LastError; // ebx
  int v10; // r9d
  HCERTSTORE v11; // rax
  DWORD v12; // eax
  unsigned __int8 v13; // dl
  __int64 v14; // r8
  __int64 v15; // rcx
  unsigned int i; // r15d
  DWORD v17; // eax
  DWORD UserCertificate; // eax
  int v19; // edx
  int v20; // r8d
  _DWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rcx
  int v25; // edx
  HCERTSTORE *v26; // rdi
  __int64 v28; // [rsp+38h] [rbp-59h] BYREF
  __int128 pvData; // [rsp+40h] [rbp-51h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+50h] [rbp-41h] BYREF
  __int128 v31; // [rsp+60h] [rbp-31h] BYREF
  __int128 v32; // [rsp+70h] [rbp-21h] BYREF
  __int128 v33; // [rsp+80h] [rbp-11h]
  __int128 v34; // [rsp+90h] [rbp-1h]
  char *v35; // [rsp+F8h] [rbp+67h] BYREF
  __int64 v36; // [rsp+100h] [rbp+6Fh] BYREF
  int v37; // [rsp+108h] [rbp+77h]
  HCERTSTORE *v38; // [rsp+110h] [rbp+7Fh]

  v38 = a4;
  v37 = a3;
  v36 = a2;
  v6 = 0;
  CertificateContext = 0;
  v35 = 0;
  v8 = 0;
  v28 = 0;
  LOBYTE(v36) = 0;
  pvData = 0;
  v31 = 0;
  *(_OWORD *)pbCertEncoded = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( !*(_QWORD *)(a1 + 8) )
  {
    LastError = 87;
    WppTraceIndent(a1, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids,
        v10,
        (__int64)"pCardState->pCardData");
    }
    goto LABEL_61;
  }
  v11 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  *a4 = v11;
  if ( !v11 )
  {
LABEL_60:
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_61;
    goto LABEL_63;
  }
  v12 = I_ContainerMapFind(a1, 0, 0, (unsigned int)&v28, (__int64)&v36);
  v8 = v28;
  LastError = v12;
  if ( v12 )
    goto LABEL_61;
  LODWORD(v33) = 1;
  *((_QWORD *)&v32 + 1) = L"Microsoft Base Smart Card Crypto Provider";
  v13 = 0;
  v14 = 256;
  while ( 1 )
  {
    LOBYTE(v37) = v13;
    if ( v13 >= (unsigned __int8)v36 )
      goto LABEL_63;
    v15 = v8 + 86LL * v13;
    v28 = v15;
    if ( (*(_BYTE *)(v15 + 80) & 1) != 0 )
      break;
LABEL_49:
    ++v13;
  }
  *(_QWORD *)&v32 = v8 + 86LL * v13;
  for ( i = 2; ; i = i == 2 )
  {
    if ( !i )
    {
      v13 = v37;
      goto LABEL_49;
    }
    if ( i != 2 )
      break;
    if ( *(_WORD *)(v15 + 82)
      && *(_WORD *)(v15 + 82) != 256
      && *(_WORD *)(v15 + 82) != 384
      && *(_WORD *)(v15 + 82) != 521 )
    {
      goto LABEL_23;
    }
LABEL_47:
    ;
  }
  if ( !*(_WORD *)(v15 + 84)
    || *(_WORD *)(v15 + 84) == 256
    || *(_WORD *)(v15 + 84) == 384
    || *(_WORD *)(v15 + 84) == 521 )
  {
    goto LABEL_47;
  }
LABEL_23:
  if ( pbCertEncoded[1] )
  {
    CspFreeH(pbCertEncoded[1]);
    pbCertEncoded[1] = 0;
  }
  if ( CertificateContext )
  {
    CertFreeCertificateContext(CertificateContext);
    CertificateContext = 0;
  }
  if ( v6 )
  {
    CspFreeH(v6);
    v35 = 0;
  }
  LOBYTE(v14) = v37;
  v17 = CspBuildCertificateFilename(a1, 0, v14, i, &v35);
  v6 = v35;
  LastError = v17;
  if ( v17 )
    goto LABEL_61;
  UserCertificate = CspReadUserCertificate(a1, v35, (unsigned int *)pbCertEncoded);
  LastError = UserCertificate;
  if ( UserCertificate )
  {
    if ( UserCertificate != -2146435028 )
      goto LABEL_61;
    LastError = 0;
LABEL_46:
    v15 = v28;
    v14 = 256;
    goto LABEL_47;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded[1], (DWORD)pbCertEncoded[0]);
  if ( !CertificateContext )
    goto LABEL_60;
  v21 = *(_DWORD **)(a1 + 8);
  DWORD2(v34) = i;
  if ( *v21 < 6u )
  {
LABEL_44:
    if ( !CertSetCertificateContextProperty(CertificateContext, 2u, 0, &v32)
      || !CertAddCertificateContextToStore(*v38, CertificateContext, 4u, 0) )
    {
      goto LABEL_60;
    }
    goto LABEL_46;
  }
  LOBYTE(v19) = v37;
  LastError = GetCachedCardContainerProperty(a1, v19, v20, (unsigned int)&pvData + 8, (__int64)&pvData);
  if ( !LastError )
  {
    if ( (_DWORD)pvData != 4 )
    {
      LastError = -2146893820;
      goto LABEL_61;
    }
    LastError = GetCardPinInfo(a1, (unsigned int)**((_DWORD **)&pvData + 1), (char *)&v31 + 8);
    if ( LastError )
    {
      WppTraceIndent(v23, 2);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = 12;
LABEL_59:
        WPP_SF_sD(
          v24[2],
          v25,
          (unsigned int)&WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError);
        goto LABEL_61;
      }
      goto LABEL_61;
    }
    LODWORD(v31) = 36;
    if ( !CertSetCertificateContextProperty(CertificateContext, 0x5Au, 0x40000000u, &pvData)
      || !CertSetCertificateContextProperty(CertificateContext, LastError + 91, 0x40000000u, &v31) )
    {
      goto LABEL_60;
    }
    if ( *((_QWORD *)&pvData + 1) )
    {
      CspFreeH(*((_QWORD *)&pvData + 1));
      *((_QWORD *)&pvData + 1) = 0;
    }
    if ( *((_QWORD *)&v31 + 1) )
    {
      CspFreeH(*((_QWORD *)&v31 + 1));
      *((_QWORD *)&v31 + 1) = 0;
    }
    goto LABEL_44;
  }
  WppTraceIndent(v22, 2);
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = 11;
    goto LABEL_59;
  }
LABEL_61:
  v26 = v38;
  if ( *v38 )
  {
    CertCloseStore(*v38, 0);
    *v26 = 0;
  }
LABEL_63:
  if ( pbCertEncoded[1] )
    CspFreeH(pbCertEncoded[1]);
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  if ( v6 )
    CspFreeH(v6);
  if ( v8 )
    CspFreeH(v8);
  if ( *((_QWORD *)&pvData + 1) )
    CspFreeH(*((_QWORD *)&pvData + 1));
  if ( *((_QWORD *)&v31 + 1) )
    CspFreeH(*((_QWORD *)&v31 + 1));
  return LastError;
}

```

## disassembly

```asm
0x180020824  mov     rax, rsp
0x180020827  mov     [rax+20h], r9
0x18002082b  mov     [rax+18h], r8d
0x18002082f  mov     [rax+10h], rdx
0x180020833  push    rbp
0x180020834  push    rbx
0x180020835  push    rsi
0x180020836  push    rdi
0x180020837  push    r12
0x180020839  push    r13
0x18002083b  push    r14
0x18002083d  push    r15
0x18002083f  lea     rbp, [rax-5Fh]
0x180020843  sub     rsp, 0A8h
0x18002084a  xor     eax, eax
0x18002084c  xorps   xmm1, xmm1
0x18002084f  xorps   xmm0, xmm0
0x180020852  mov     rbx, r9
0x180020855  mov     r13, rcx
0x180020858  mov     esi, eax
0x18002085a  mov     r14d, eax
0x18002085d  mov     [rbp+57h+arg_0], rax
0x180020861  lea     edi, [rax+2]
0x180020864  mov     r12d, eax
0x180020867  mov     [rbp+57h+var_B0], rax
0x18002086b  mov     byte ptr [rbp+57h+arg_8], al
0x18002086e  movups  [rbp+57h+pvData], xmm0
0x180020872  movups  [rbp+57h+var_88], xmm1
0x180020876  movups  xmmword ptr [rbp+57h+pbCertEncoded], xmm0
0x18002087a  movups  [rbp+57h+var_78], xmm1
0x18002087e  movups  [rbp+57h+var_68], xmm1
0x180020882  movups  [rbp+57h+var_58], xmm1
0x180020886  cmp     [rcx+8], rax
0x18002088a  jnz     short loc_1800208E5
0x18002088c  mov     edx, edi
0x18002088e  lea     ebx, [rax+57h]
0x180020891  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020896  mov     rcx, cs:WPP_GLOBAL_Control
0x18002089d  lea     rax, WPP_GLOBAL_Control
0x1800208a4  cmp     rcx, rax
0x1800208a7  jz      loc_180020C50
0x1800208ad  test    byte ptr [rcx+1Ch], 1
0x1800208b1  jz      loc_180020C50
0x1800208b7  cmp     [rcx+19h], dil
0x1800208bb  jb      loc_180020C50
0x1800208c1  mov     rcx, [rcx+10h]
0x1800208c5  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x1800208cc  lea     edx, [rdi+8]
0x1800208cf  mov     [rsp+20h], rax
0x1800208d4  lea     r8, WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids
0x1800208db  call    WPP_SF_ss
0x1800208e0  jmp     loc_180020C50
0x1800208e5  xor     r9d, r9d; dwFlags
0x1800208e8  mov     [rsp+20h], rax; pvPara
0x1800208ed  xor     r8d, r8d; hCryptProv
0x1800208f0  xor     edx, edx; dwEncodingType
0x1800208f2  mov     rcx, rdi; lpszStoreProvider
0x1800208f5  call    cs:__imp_CertOpenStore
0x1800208fb  mov     [rbx], rax
0x1800208fe  test    rax, rax
0x180020901  jz      loc_180020C44
0x180020907  lea     rax, [rbp+57h+arg_8]
0x18002090b  xor     r8d, r8d
0x18002090e  lea     r9, [rbp+57h+var_B0]
0x180020912  mov     [rsp+20h], rax
0x180020917  xor     edx, edx
0x180020919  mov     rcx, r13
0x18002091c  call    I_ContainerMapFind
0x180020921  mov     r12, [rbp+57h+var_B0]
0x180020925  mov     ebx, eax
0x180020927  test    eax, eax
0x180020929  jnz     loc_180020C50
0x18002092f  lea     rax, aMicrosoftBaseS; "Microsoft Base Smart Card Crypto Provid"...
0x180020936  mov     dword ptr [rbp+57h+var_68], 1
0x18002093d  mov     qword ptr [rbp+57h+var_78+8], rax
0x180020941  xor     dl, dl
0x180020943  mov     r8d, 100h
0x180020949  mov     r9d, 180h
0x18002094f  mov     r10d, 209h
0x180020955  mov     byte ptr [rbp+57h+arg_10], dl
0x180020958  cmp     dl, byte ptr [rbp+57h+arg_8]
0x18002095b  jnb     loc_180020C6B
0x180020961  movzx   eax, dl
0x180020964  imul    rcx, rax, 56h ; 'V'
0x180020968  add     rcx, r12
0x18002096b  mov     [rbp+57h+var_B0], rcx
0x18002096f  test    byte ptr [rcx+50h], 1
0x180020973  jz      loc_180020BC1
0x180020979  mov     qword ptr [rbp+57h+var_78], rcx
0x18002097d  mov     r15d, edi
0x180020980  test    r15d, r15d
0x180020983  jz      loc_180020BBE
0x180020989  cmp     r15d, edi
0x18002098c  jnz     short loc_1800209BC
0x18002098e  xor     eax, eax
0x180020990  cmp     ax, [rcx+52h]
0x180020994  jz      loc_180020BAE
0x18002099a  cmp     [rcx+52h], r8w
0x18002099f  jz      loc_180020BAE
0x1800209a5  cmp     [rcx+52h], r9w
0x1800209aa  jz      loc_180020BAE
0x1800209b0  cmp     [rcx+52h], r10w
0x1800209b5  jnz     short loc_1800209EF
0x1800209b7  jmp     loc_180020BAE
0x1800209bc  cmp     r15d, 1
0x1800209c0  jnz     short loc_1800209EF
0x1800209c2  xor     eax, eax
0x1800209c4  cmp     ax, [rcx+54h]
0x1800209c8  jz      loc_180020BAE
0x1800209ce  cmp     [rcx+54h], r8w
0x1800209d3  jz      loc_180020BAE
0x1800209d9  cmp     [rcx+54h], r9w
0x1800209de  jz      loc_180020BAE
0x1800209e4  cmp     [rcx+54h], r10w
0x1800209e9  jz      loc_180020BAE
0x1800209ef  mov     rcx, [rbp+57h+pbCertEncoded+8]
0x1800209f3  test    rcx, rcx
0x1800209f6  jz      short loc_180020A05
0x1800209f8  call    CspFreeH
0x1800209fd  mov     [rbp+57h+pbCertEncoded+8], 0
0x180020a05  test    r14, r14
0x180020a08  jz      short loc_180020A16
0x180020a0a  mov     rcx, r14; pCertContext
0x180020a0d  call    cs:__imp_CertFreeCertificateContext
0x180020a13  xor     r14d, r14d
0x180020a16  test    rsi, rsi
0x180020a19  jz      short loc_180020A2B
0x180020a1b  mov     rcx, rsi
0x180020a1e  call    CspFreeH
0x180020a23  mov     [rbp+57h+arg_0], 0
0x180020a2b  mov     r8b, byte ptr [rbp+57h+arg_10]
0x180020a2f  lea     rax, [rbp+57h+arg_0]
0x180020a33  mov     r9d, r15d
0x180020a36  mov     [rsp+20h], rax
0x180020a3b  xor     edx, edx
0x180020a3d  mov     rcx, r13
0x180020a40  call    CspBuildCertificateFilename
0x180020a45  mov     rsi, [rbp+57h+arg_0]
0x180020a49  mov     ebx, eax
0x180020a4b  test    eax, eax
0x180020a4d  jnz     loc_180020C50
0x180020a53  lea     r8, [rbp+57h+pbCertEncoded]
0x180020a57  mov     rdx, rsi
0x180020a5a  mov     rcx, r13
0x180020a5d  call    CspReadUserCertificate
0x180020a62  mov     ebx, eax
0x180020a64  test    eax, eax
0x180020a66  jz      short loc_180020A7A
0x180020a68  cmp     eax, 8010002Ch
0x180020a6d  jnz     loc_180020C50
0x180020a73  xor     ebx, ebx
0x180020a75  jmp     loc_180020B9A
0x180020a7a  mov     r8d, dword ptr [rbp+57h+pbCertEncoded]; cbCertEncoded
0x180020a7e  mov     ecx, 10001h; dwCertEncodingType
0x180020a83  mov     rdx, [rbp+57h+pbCertEncoded+8]; pbCertEncoded
0x180020a87  call    cs:__imp_CertCreateCertificateContext
0x180020a8d  mov     r14, rax
0x180020a90  test    rax, rax
0x180020a93  jz      loc_180020C44
0x180020a99  mov     rax, [r13+8]
0x180020a9d  mov     dword ptr [rbp+57h+var_58+8], r15d
0x180020aa1  cmp     dword ptr [rax], 6
0x180020aa4  jb      loc_180020B61
0x180020aaa  mov     dl, byte ptr [rbp+57h+arg_10]
0x180020aad  lea     rax, [rbp+57h+pvData]
0x180020ab1  lea     r9, [rbp+57h+pvData+8]
0x180020ab5  mov     [rsp+20h], rax
0x180020aba  mov     rcx, r13
0x180020abd  call    GetCachedCardContainerProperty
0x180020ac2  mov     ebx, eax
0x180020ac4  test    eax, eax
0x180020ac6  jnz     loc_180020BFC
0x180020acc  cmp     dword ptr [rbp+57h+pvData], 4
0x180020ad0  jnz     loc_180020BF5
0x180020ad6  mov     rdx, qword ptr [rbp+57h+pvData+8]
0x180020ada  lea     r8, [rbp+57h+var_88+8]
0x180020ade  mov     rcx, r13
0x180020ae1  mov     edx, [rdx]
0x180020ae3  call    GetCardPinInfo
0x180020ae8  mov     ebx, eax
0x180020aea  test    eax, eax
0x180020aec  jnz     loc_180020BC8
0x180020af2  lea     r9, [rbp+57h+pvData]; pvData
0x180020af6  mov     dword ptr [rbp+57h+var_88], 24h ; '$'
0x180020afd  lea     edx, [rax+5Ah]; dwPropId
0x180020b00  mov     r8d, 40000000h; dwFlags
0x180020b06  mov     rcx, r14; pCertContext
0x180020b09  call    cs:__imp_CertSetCertificateContextProperty
0x180020b0f  test    eax, eax
0x180020b11  jz      loc_180020C44
0x180020b17  lea     r9, [rbp+57h+var_88]; pvData
0x180020b1b  mov     r8d, 40000000h; dwFlags
0x180020b21  lea     edx, [rbx+5Bh]; dwPropId
0x180020b24  mov     rcx, r14; pCertContext
0x180020b27  call    cs:__imp_CertSetCertificateContextProperty
0x180020b2d  test    eax, eax
0x180020b2f  jz      loc_180020C44
0x180020b35  mov     rcx, qword ptr [rbp+57h+pvData+8]
0x180020b39  test    rcx, rcx
0x180020b3c  jz      short loc_180020B4B
0x180020b3e  call    CspFreeH
0x180020b43  mov     qword ptr [rbp+57h+pvData+8], 0
0x180020b4b  mov     rcx, qword ptr [rbp+57h+var_88+8]
0x180020b4f  test    rcx, rcx
0x180020b52  jz      short loc_180020B61
0x180020b54  call    CspFreeH
0x180020b59  mov     qword ptr [rbp+57h+var_88+8], 0
0x180020b61  lea     r9, [rbp+57h+var_78]; pvData
0x180020b65  xor     r8d, r8d; dwFlags
0x180020b68  mov     edx, edi; dwPropId
0x180020b6a  mov     rcx, r14; pCertContext
0x180020b6d  call    cs:__imp_CertSetCertificateContextProperty
0x180020b73  test    eax, eax
0x180020b75  jz      loc_180020C44
0x180020b7b  mov     rax, [rbp+57h+arg_18]
0x180020b7f  xor     r9d, r9d; ppStoreContext
0x180020b82  mov     rdx, r14; pCertContext
0x180020b85  mov     rcx, [rax]; hCertStore
0x180020b88  lea     r8d, [r9+4]; dwAddDisposition
0x180020b8c  call    cs:__imp_CertAddCertificateContextToStore
0x180020b92  test    eax, eax
0x180020b94  jz      loc_180020C44
0x180020b9a  mov     rcx, [rbp+57h+var_B0]
0x180020b9e  mov     r9d, 180h
0x180020ba4  mov     r10d, 209h
0x180020baa  lea     r8d, [r9-80h]
0x180020bae  xor     eax, eax
0x180020bb0  cmp     r15d, edi
0x180020bb3  setz    al
0x180020bb6  mov     r15d, eax
0x180020bb9  jmp     loc_180020980
0x180020bbe  mov     dl, byte ptr [rbp+57h+arg_10]
0x180020bc1  inc     dl
0x180020bc3  jmp     loc_180020955
0x180020bc8  mov     edx, edi
0x180020bca  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bd6  lea     rax, WPP_GLOBAL_Control
0x180020bdd  cmp     rcx, rax
0x180020be0  jz      short loc_180020C50
0x180020be2  test    byte ptr [rcx+1Ch], 1
0x180020be6  jz      short loc_180020C50
0x180020be8  cmp     [rcx+19h], dil
0x180020bec  jb      short loc_180020C50
0x180020bee  mov     edx, 0Ch
0x180020bf3  jmp     short loc_180020C27
0x180020bf5  mov     ebx, 80090004h
0x180020bfa  jmp     short loc_180020C50
0x180020bfc  mov     edx, edi
0x180020bfe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020c03  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c0a  lea     rax, WPP_GLOBAL_Control
0x180020c11  cmp     rcx, rax
0x180020c14  jz      short loc_180020C50
0x180020c16  test    byte ptr [rcx+1Ch], 1
0x180020c1a  jz      short loc_180020C50
0x180020c1c  cmp     [rcx+19h], dil
0x180020c20  jb      short loc_180020C50
0x180020c22  mov     edx, 0Bh
0x180020c27  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180020c2e  lea     r8, WPP_9990ba7a724b3d1b787a644c0a5cfe6b_Traceguids
0x180020c35  mov     rcx, [rcx+10h]
0x180020c39  mov     [rsp+20h], ebx
0x180020c3d  call    WPP_SF_sD
0x180020c42  jmp     short loc_180020C50
0x180020c44  call    cs:__imp_GetLastError
0x180020c4a  mov     ebx, eax
0x180020c4c  test    eax, eax
0x180020c4e  jz      short loc_180020C6B
0x180020c50  mov     rdi, [rbp+57h+arg_18]
0x180020c54  mov     rcx, [rdi]; hCertStore
0x180020c57  test    rcx, rcx
0x180020c5a  jz      short loc_180020C6B
0x180020c5c  xor     edx, edx; dwFlags
0x180020c5e  call    cs:__imp_CertCloseStore
0x180020c64  mov     qword ptr [rdi], 0
0x180020c6b  mov     rcx, [rbp+57h+pbCertEncoded+8]
0x180020c6f  test    rcx, rcx
0x180020c72  jz      short loc_180020C79
0x180020c74  call    CspFreeH
0x180020c79  test    r14, r14
0x180020c7c  jz      short loc_180020C87
0x180020c7e  mov     rcx, r14; pCertContext
0x180020c81  call    cs:__imp_CertFreeCertificateContext
0x180020c87  test    rsi, rsi
0x180020c8a  jz      short loc_180020C94
0x180020c8c  mov     rcx, rsi
0x180020c8f  call    CspFreeH
0x180020c94  test    r12, r12
0x180020c97  jz      short loc_180020CA1
0x180020c99  mov     rcx, r12
0x180020c9c  call    CspFreeH
0x180020ca1  mov     rcx, qword ptr [rbp+57h+pvData+8]
0x180020ca5  test    rcx, rcx
0x180020ca8  jz      short loc_180020CAF
0x180020caa  call    CspFreeH
0x180020caf  mov     rcx, qword ptr [rbp+57h+var_88+8]
0x180020cb3  test    rcx, rcx
0x180020cb6  jz      short loc_180020CBD
0x180020cb8  call    CspFreeH
  ... truncated ...
```
