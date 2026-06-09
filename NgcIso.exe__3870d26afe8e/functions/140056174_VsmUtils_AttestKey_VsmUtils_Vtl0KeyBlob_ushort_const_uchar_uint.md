# VsmUtils::AttestKey(VsmUtils::Vtl0KeyBlob *,ushort const *,uchar *,uint)

- ea: `0x140056174`
- end: `0x14005664a`
- name: `?AttestKey@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEBGPEAEI@Z`
- size: `1238`
- prototype: `int(VsmUtils *__hidden this, struct VsmUtils::Vtl0KeyBlob *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003d61c`
- `0x140048634`

## callees

- `0x140007410`
- `0x14000e034`
- `0x14000f6a0`
- `0x14000fc8c`
- `0x1400104f0`
- `0x14002b644`
- `0x14002bdcc`
- `0x140040338`
- `0x140054f54`
- `0x140054f8c`
- `0x14005522c`
- `0x140055470`
- `0x140056174`
- `0x14005ac70`
- `0x14005bc68`
- `0x14005c07c`
- `0x14005c5c4`
- `0x1400624d4`
- `0x140064010`
- `0x140065c28`
- `0x1400698a4`
- `0x140069958`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400563d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400563f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056409`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005641d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056431`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056445`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056459`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400563d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400563f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056409`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005641d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056431`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056445`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140056459`
- `bcrypt!BCryptCreateHash` at `0x14005635b`
- `bcrypt!BCryptCreateHash` at `0x14005635b`
- `bcrypt!BCryptHashData` at `0x1400564d5`
- `bcrypt!BCryptHashData` at `0x140056515`
- `bcrypt!BCryptHashData` at `0x1400564d5`
- `bcrypt!BCryptHashData` at `0x140056515`
- `bcrypt!BCryptFinishHash` at `0x140056549`
- `bcrypt!BCryptFinishHash` at `0x140056549`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140056301`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140056301`

## string_xrefs

- `0x140056315`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005636f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400564a8`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400564ee`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400565d8`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005660c`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall VsmUtils::AttestKey(
        VsmUtils *this,
        struct VsmUtils::Vtl0KeyBlob *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  tpm12class::TPMW8_SESSION *v11; // rax
  struct tpm12class::TPMW8_AUTH_PROVIDER *v12; // rdx
  struct tpm12class::TPMW82B_BUFFER *v13; // r8
  unsigned __int8 v14; // r9
  VsmUtils *v15; // rax
  int v16; // eax
  unsigned int v17; // eax
  int v18; // edx
  int v19; // eax
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  struct tpm12class::TPMW82B_BUFFER *v24; // rdx
  struct tpm12class::TPMW82B_BUFFER *v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rdx
  int RsaSRKQualifiedName; // eax
  NTSTATUS v29; // eax
  __int64 v30; // rdx
  int pbSecret; // [rsp+20h] [rbp-E0h]
  int pbSecreta; // [rsp+20h] [rbp-E0h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-B8h] BYREF
  char v36; // [rsp+51h] [rbp-AFh]
  _QWORD v37[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  char v41; // [rsp+90h] [rbp-70h]
  unsigned __int16 v42; // [rsp+98h] [rbp-68h]
  PUCHAR pbInput; // [rsp+A0h] [rbp-60h]
  tpm12class::TPMW8_SESSION *v44; // [rsp+B0h] [rbp-50h]
  _BYTE v45[168]; // [rsp+C0h] [rbp-40h] BYREF
  VsmUtils *v46; // [rsp+168h] [rbp+68h]
  int v47; // [rsp+184h] [rbp+84h]
  __int64 v48; // [rsp+188h] [rbp+88h]
  _BYTE v49[56]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v50; // [rsp+1C8h] [rbp+C8h]
  PUCHAR v51; // [rsp+1D0h] [rbp+D0h]
  __int16 v52; // [rsp+210h] [rbp+110h]
  __int64 v53; // [rsp+218h] [rbp+118h]
  UCHAR pbOutput[16]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v55; // [rsp+230h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  if ( !this || !a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x318,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)0x80070057LL,
      pbSecret);
    return v8;
  }
  SetTbsHandle(*((_QWORD *)this + 5));
  v36 = 1;
  tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v45);
  v47 = *((_DWORD *)this + 12);
  v7 = tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v49, (const unsigned __int8 *)this + 4, 0x22u);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v10 = 802;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)v9,
      pbSecret);
    goto LABEL_55;
  }
  v11 = (tpm12class::TPMW8_SESSION *)operator new(0x318u, (const struct std::nothrow_t *)std::nothrow);
  v44 = v11;
  if ( v11 )
    v15 = (VsmUtils *)tpm12class::TPMW8_SESSION::TPMW8_SESSION(v11, v12);
  else
    v15 = 0;
  v46 = v15;
  if ( !v15 )
  {
    v8 = -2147024882;
    v10 = 805;
LABEL_53:
    v9 = v8;
    goto LABEL_54;
  }
  LOBYTE(v13) = 64;
  v16 = VsmUtils::AddSecureSession(v15, 0, v13, v14);
  v8 = v16;
  if ( v16 < 0 )
  {
    v9 = (unsigned int)v16;
    v10 = 806;
    goto LABEL_54;
  }
  v17 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v45, 0);
  v19 = VsmUtils::MapTpmError((VsmUtils *)v17, v18);
  v8 = v19;
  if ( v19 < 0 )
  {
    v9 = (unsigned int)v19;
    v10 = 808;
    goto LABEL_54;
  }
  if ( (*(_DWORD *)(v48 + 60) & 0x440) != 0x400 )
  {
    v10 = 813;
LABEL_52:
    v8 = -2146893774;
    goto LABEL_53;
  }
  if ( *(_WORD *)(v48 + 120) != 32 || memcmp_0(a3, *(const void **)(v48 + 128), 0x20u) )
  {
    v10 = 821;
    goto LABEL_52;
  }
  phAlgorithm = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &phAlgorithm,
    0);
  v20 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v20 >= 0 )
  {
    phHash = 0;
    v21 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( v21 < 0 )
    {
      v8 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x33E,
             (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
             (const char *)(unsigned int)v21,
             pbSecreta);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
      goto LABEL_20;
    }
    v37[1] = 0;
    v37[2] = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v37[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
    v42 = 0;
    pbInput = 0;
    LOBYTE(v23) = 3;
    LOBYTE(v22) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
      v22,
      v23);
    if ( (unsigned int)_o__wcsicmp(a2, L"ECDSA_P256")
      && (unsigned int)_o__wcsicmp(a2, L"ECDSA_P384")
      && (unsigned int)_o__wcsicmp(a2, L"ECDSA_P521")
      && (unsigned int)_o__wcsicmp(a2, L"ECDH_P256")
      && (unsigned int)_o__wcsicmp(a2, L"ECDH_P384")
      && (unsigned int)_o__wcsicmp(a2, L"ECDH_P521") )
    {
      if ( (unsigned int)_o__wcsicmp(a2, L"RSA") )
      {
        v8 = -2147024809;
        v26 = 2147942487LL;
        v27 = 845;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
          (const char *)v26,
          pbSecreta);
LABEL_38:
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v37);
        goto LABEL_23;
      }
      RsaSRKQualifiedName = VsmUtils::GetRsaSRKQualifiedName((VsmUtils *)v37, v25);
      v8 = RsaSRKQualifiedName;
      if ( RsaSRKQualifiedName < 0 )
      {
        v27 = 847;
LABEL_36:
        v26 = (unsigned int)RsaSRKQualifiedName;
        goto LABEL_37;
      }
    }
    else
    {
      RsaSRKQualifiedName = VsmUtils::GetEccSRKQualifiedName((VsmUtils *)v37, v24);
      v8 = RsaSRKQualifiedName;
      if ( RsaSRKQualifiedName < 0 )
      {
        v27 = 841;
        goto LABEL_36;
      }
    }
    v29 = BCryptHashData(phHash, pbInput, v42, 0);
    if ( v29 >= 0 )
    {
      v29 = BCryptHashData(phHash, v51, v50, 0);
      if ( v29 >= 0 )
      {
        *(_OWORD *)pbOutput = 0;
        v55 = 0;
        v29 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
        if ( v29 >= 0 )
        {
          if ( v52 == 34 )
          {
            if ( !memcmp_0(pbOutput, (const void *)(v53 + 2), 0x20u) )
            {
              tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v37);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
              v8 = 0;
              goto LABEL_55;
            }
            v8 = -2146893774;
            v26 = 2148073522LL;
            v27 = 866;
          }
          else
          {
            v8 = -2146893774;
            v26 = 2148073522LL;
            v27 = 860;
          }
          goto LABEL_37;
        }
        v30 = 857;
      }
      else
      {
        v30 = 853;
      }
    }
    else
    {
      v30 = 850;
    }
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v30,
           (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
           (const char *)(unsigned int)v29,
           pbSecreta);
    goto LABEL_38;
  }
  v8 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x33B,
         (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
         (const char *)(unsigned int)v20,
         pbSecret);
LABEL_20:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
LABEL_55:
  tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v45);
  ClearTbsHandle();
  return v8;
}

```

## disassembly

```asm
0x140056174  mov     [rsp-8+arg_10], rbx
0x140056179  mov     [rsp-8+arg_18], rsi
0x14005617e  push    rbp
0x14005617f  push    rdi
0x140056180  push    r12
0x140056182  push    r14
0x140056184  push    r15
0x140056186  lea     rbp, [rsp-150h]
0x14005618e  sub     rsp, 250h
0x140056195  mov     rax, cs:__security_cookie
0x14005619c  xor     rax, rsp
0x14005619f  mov     [rbp+170h+var_30], rax
0x1400561a6  mov     rsi, r8
0x1400561a9  mov     rdi, rdx
0x1400561ac  mov     rbx, rcx
0x1400561af  xor     r14d, r14d
0x1400561b2  test    rcx, rcx
0x1400561b5  jz      loc_1400565FD
0x1400561bb  test    r8, r8
0x1400561be  jz      loc_1400565FD
0x1400561c4  mov     rcx, [rcx+28h]; unsigned __int64
0x1400561c8  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x1400561cd  mov     [rsp+270h+var_21F], 1
0x1400561d2  lea     rcx, [rbp+170h+var_1B0]; this
0x1400561d6  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x1400561db  nop
0x1400561dc  mov     eax, [rbx+30h]
0x1400561df  mov     [rbp+170h+var_EC], eax
0x1400561e5  lea     rdx, [rbx+4]; unsigned __int8 *
0x1400561e9  lea     r12d, [r14+22h]
0x1400561ed  mov     r8d, r12d; unsigned __int64
0x1400561f0  lea     rcx, [rbp+170h+var_E0]; this
0x1400561f7  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x1400561fc  mov     ebx, eax
0x1400561fe  test    eax, eax
0x140056200  jns     short loc_14005620F
0x140056202  mov     r9d, eax
0x140056205  mov     edx, 322h
0x14005620a  jmp     loc_1400565D8
0x14005620f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140056216  mov     ecx, 318h; unsigned __int64
0x14005621b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140056220  mov     [rbp+170h+var_1C0], rax
0x140056224  test    rax, rax
0x140056227  jz      short loc_140056233
0x140056229  mov     rcx, rax; this
0x14005622c  call    ??0TPMW8_SESSION@tpm12class@@QEAA@PEAVTPMW8_AUTH_PROVIDER@1@@Z; tpm12class::TPMW8_SESSION::TPMW8_SESSION(tpm12class::TPMW8_AUTH_PROVIDER *)
0x140056231  jmp     short loc_140056236
0x140056233  mov     rax, r14
0x140056236  mov     [rbp+170h+var_108], rax
0x14005623a  test    rax, rax
0x14005623d  jnz     short loc_14005624E
0x14005623f  mov     ebx, 8007000Eh
0x140056244  mov     edx, 325h
0x140056249  jmp     loc_1400565D5
0x14005624e  mov     r8b, 40h ; '@'; struct tpm12class::TPMW82B_BUFFER *
0x140056251  xor     edx, edx; struct tpm12class::TPMW8_SESSION *
0x140056253  mov     rcx, rax; this
0x140056256  call    ?AddSecureSession@VsmUtils@@YAJPEAVTPMW8_SESSION@tpm12class@@PEAVTPMW82B_BUFFER@3@E@Z; VsmUtils::AddSecureSession(tpm12class::TPMW8_SESSION *,tpm12class::TPMW82B_BUFFER *,uchar)
0x14005625b  mov     ebx, eax
0x14005625d  test    eax, eax
0x14005625f  jns     short loc_14005626E
0x140056261  mov     r9d, eax
0x140056264  mov     edx, 326h
0x140056269  jmp     loc_1400565D8
0x14005626e  xor     edx, edx; void *
0x140056270  lea     rcx, [rbp+170h+var_1B0]; this
0x140056274  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x140056279  mov     ecx, eax; this
0x14005627b  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140056280  mov     ebx, eax
0x140056282  test    eax, eax
0x140056284  jns     short loc_140056293
0x140056286  mov     r9d, eax
0x140056289  mov     edx, 328h
0x14005628e  jmp     loc_1400565D8
0x140056293  mov     rdx, [rbp+170h+var_E8]
0x14005629a  mov     eax, [rdx+3Ch]
0x14005629d  and     eax, 440h
0x1400562a2  cmp     eax, 400h
0x1400562a7  jz      short loc_1400562B3
0x1400562a9  mov     edx, 32Dh
0x1400562ae  jmp     loc_1400565D0
0x1400562b3  mov     r15d, 20h ; ' '
0x1400562b9  cmp     [rdx+78h], r15w
0x1400562be  jnz     loc_1400565CB
0x1400562c4  mov     r8d, r15d; Size
0x1400562c7  mov     rdx, [rdx+80h]; Buf2
0x1400562ce  mov     rcx, rsi; Buf1
0x1400562d1  call    memcmp_0
0x1400562d6  test    eax, eax
0x1400562d8  jnz     loc_1400565CB
0x1400562de  mov     [rsp+270h+phAlgorithm], r14
0x1400562e3  xor     edx, edx
0x1400562e5  lea     rcx, [rsp+270h+phAlgorithm]
0x1400562ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400562ef  xor     r9d, r9d; dwFlags
0x1400562f2  xor     r8d, r8d; pszImplementation
0x1400562f5  lea     rdx, aSha256; "SHA256"
0x1400562fc  lea     rcx, [rsp+270h+phAlgorithm]; phAlgorithm
0x140056301  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140056307  test    eax, eax
0x140056309  jns     short loc_140056337
0x14005630b  mov     rcx, [rbp+178h]; this
0x140056312  mov     r9d, eax; char *
0x140056315  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005631c  mov     edx, 33Bh; void *
0x140056321  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140056326  mov     ebx, eax
0x140056328  lea     rcx, [rsp+270h+phAlgorithm]
0x14005632d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140056332  jmp     loc_1400565EC
0x140056337  mov     [rsp+270h+phHash], r14
0x14005633c  mov     [rsp+270h+dwFlags], r14d; dwFlags
0x140056341  mov     [rsp+270h+cbSecret], r14d; cbSecret
0x140056346  mov     [rsp+270h+pbSecret], r14; int
0x14005634b  xor     r9d, r9d; cbHashObject
0x14005634e  xor     r8d, r8d; pbHashObject
0x140056351  lea     rdx, [rsp+270h+phHash]; phHash
0x140056356  mov     rcx, [rsp+270h+phAlgorithm]; hAlgorithm
0x14005635b  call    cs:__imp_BCryptCreateHash
0x140056361  test    eax, eax
0x140056363  jns     short loc_14005638E
0x140056365  mov     rcx, [rbp+178h]; this
0x14005636c  mov     r9d, eax; char *
0x14005636f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140056376  mov     edx, 33Eh; void *
0x14005637b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140056380  mov     ebx, eax
0x140056382  lea     rcx, [rsp+270h+phHash]
0x140056387  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005638c  jmp     short loc_140056328
0x14005638e  mov     [rsp+270h+var_208], r14
0x140056393  mov     [rsp+270h+var_200], r14
0x140056398  mov     [rsp+270h+var_1F8], r14d
0x14005639d  mov     [rbp+170h+var_1F0], r14
0x1400563a1  mov     [rbp+170h+var_1E8], r14
0x1400563a5  mov     [rbp+170h+var_1E0], r14b
0x1400563a9  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x1400563b0  mov     [rsp+270h+var_210], rax
0x1400563b5  mov     [rbp+170h+var_1D8], r14w
0x1400563ba  mov     [rbp+170h+pbInput], r14
0x1400563be  mov     r8b, 3
0x1400563c1  mov     dl, 1
0x1400563c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers> `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl(void)'::`2'::impl
0x1400563ca  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400563cf  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x1400563d6  mov     rcx, rdi
0x1400563d9  call    cs:__imp__o__wcsicmp
0x1400563df  test    eax, eax
0x1400563e1  jz      loc_140056489
0x1400563e7  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x1400563ee  mov     rcx, rdi
0x1400563f1  call    cs:__imp__o__wcsicmp
0x1400563f7  test    eax, eax
0x1400563f9  jz      loc_140056489
0x1400563ff  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x140056406  mov     rcx, rdi
0x140056409  call    cs:__imp__o__wcsicmp
0x14005640f  test    eax, eax
0x140056411  jz      short loc_140056489
0x140056413  lea     rdx, aEcdhP256; "ECDH_P256"
0x14005641a  mov     rcx, rdi
0x14005641d  call    cs:__imp__o__wcsicmp
0x140056423  test    eax, eax
0x140056425  jz      short loc_140056489
0x140056427  lea     rdx, aEcdhP384; "ECDH_P384"
0x14005642e  mov     rcx, rdi
0x140056431  call    cs:__imp__o__wcsicmp
0x140056437  test    eax, eax
0x140056439  jz      short loc_140056489
0x14005643b  lea     rdx, aEcdhP521; "ECDH_P521"
0x140056442  mov     rcx, rdi
0x140056445  call    cs:__imp__o__wcsicmp
0x14005644b  test    eax, eax
0x14005644d  jz      short loc_140056489
0x14005644f  lea     rdx, aRsa; "RSA"
0x140056456  mov     rcx, rdi
0x140056459  call    cs:__imp__o__wcsicmp
0x14005645f  test    eax, eax
0x140056461  jz      short loc_140056472
0x140056463  mov     ebx, 80070057h
0x140056468  mov     r9d, ebx
0x14005646b  mov     edx, 34Dh
0x140056470  jmp     short loc_1400564A1
0x140056472  lea     rcx, [rsp+270h+var_210]; this
0x140056477  call    ?GetRsaSRKQualifiedName@VsmUtils@@YAJPEAVTPMW82B_BUFFER@tpm12class@@@Z; VsmUtils::GetRsaSRKQualifiedName(tpm12class::TPMW82B_BUFFER *)
0x14005647c  mov     ebx, eax
0x14005647e  test    eax, eax
0x140056480  jns     short loc_1400564C4
0x140056482  mov     edx, 34Fh
0x140056487  jmp     short loc_14005649E
0x140056489  lea     rcx, [rsp+270h+var_210]; this
0x14005648e  call    ?GetEccSRKQualifiedName@VsmUtils@@YAJPEAVTPMW82B_BUFFER@tpm12class@@@Z; VsmUtils::GetEccSRKQualifiedName(tpm12class::TPMW82B_BUFFER *)
0x140056493  mov     ebx, eax
0x140056495  test    eax, eax
0x140056497  jns     short loc_1400564C4
0x140056499  mov     edx, 349h; void *
0x14005649e  mov     r9d, eax; char *
0x1400564a1  mov     rcx, [rbp+178h]; this
0x1400564a8  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400564af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400564b4  nop
0x1400564b5  lea     rcx, [rsp+270h+var_210]; this
0x1400564ba  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400564bf  jmp     loc_140056382
0x1400564c4  movzx   r8d, [rbp+170h+var_1D8]; cbInput
0x1400564c9  xor     r9d, r9d; dwFlags
0x1400564cc  mov     rdx, [rbp+170h+pbInput]; pbInput
0x1400564d0  mov     rcx, [rsp+270h+phHash]; hHash
0x1400564d5  call    cs:__imp_BCryptHashData
0x1400564db  test    eax, eax
0x1400564dd  jns     short loc_1400564FE
0x1400564df  mov     edx, 352h; void *
0x1400564e4  mov     rcx, [rbp+178h]; this
0x1400564eb  mov     r9d, eax; char *
0x1400564ee  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400564f5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400564fa  mov     ebx, eax
0x1400564fc  jmp     short loc_1400564B5
0x1400564fe  movzx   r8d, [rbp+170h+var_A8]; cbInput
0x140056506  xor     r9d, r9d; dwFlags
0x140056509  mov     rdx, [rbp+170h+var_A0]; pbInput
0x140056510  mov     rcx, [rsp+270h+phHash]; hHash
0x140056515  call    cs:__imp_BCryptHashData
0x14005651b  test    eax, eax
0x14005651d  jns     short loc_140056526
0x14005651f  mov     edx, 355h
0x140056524  jmp     short loc_1400564E4
0x140056526  xorps   xmm0, xmm0
0x140056529  movups  xmmword ptr [rbp+170h+pbOutput], xmm0
0x140056530  movups  [rbp+170h+var_40], xmm0
0x140056537  xor     r9d, r9d; dwFlags
0x14005653a  mov     r8d, r15d; cbOutput
0x14005653d  lea     rdx, [rbp+170h+pbOutput]; pbOutput
0x140056544  mov     rcx, [rsp+270h+phHash]; hHash
0x140056549  call    cs:__imp_BCryptFinishHash
0x14005654f  test    eax, eax
0x140056551  jns     short loc_14005655A
0x140056553  mov     edx, 359h
0x140056558  jmp     short loc_1400564E4
0x14005655a  cmp     [rbp+170h+var_60], r12w
0x140056562  jz      short loc_140056576
0x140056564  mov     ebx, 80090032h
0x140056569  mov     r9d, ebx
0x14005656c  mov     edx, 35Ch
0x140056571  jmp     loc_1400564A1
0x140056576  mov     rdx, [rbp+170h+var_58]
0x14005657d  add     rdx, 2; Buf2
0x140056581  mov     r8, r15; Size
0x140056584  lea     rcx, [rbp+170h+pbOutput]; Buf1
0x14005658b  call    memcmp_0
0x140056590  test    eax, eax
0x140056592  jz      short loc_1400565A6
0x140056594  mov     ebx, 80090032h
0x140056599  mov     r9d, ebx
0x14005659c  mov     edx, 362h
0x1400565a1  jmp     loc_1400564A1
0x1400565a6  lea     rcx, [rsp+270h+var_210]; this
0x1400565ab  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400565b0  nop
0x1400565b1  lea     rcx, [rsp+270h+phHash]
0x1400565b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400565bb  nop
0x1400565bc  lea     rcx, [rsp+270h+phAlgorithm]
0x1400565c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400565c6  mov     ebx, r14d
0x1400565c9  jmp     short loc_1400565EC
0x1400565cb  mov     edx, 335h; void *
0x1400565d0  mov     ebx, 80090032h
0x1400565d5  mov     r9d, ebx; char *
0x1400565d8  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400565df  mov     rcx, [rbp+178h]; this
0x1400565e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400565eb  nop
0x1400565ec  lea     rcx, [rbp+170h+var_1B0]; this
0x1400565f0  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x1400565f5  nop
0x1400565f6  call    ?ClearTbsHandle@@YAXXZ; ClearTbsHandle(void)
0x1400565fb  jmp     short loc_14005661D
0x1400565fd  mov     rcx, [rbp+178h]; this
0x140056604  mov     ebx, 80070057h
0x140056609  mov     r9d, ebx; char *
0x14005660c  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140056613  mov     edx, 318h; void *
0x140056618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005661d  mov     eax, ebx
0x14005661f  mov     rcx, [rbp+170h+var_30]
0x140056626  xor     rcx, rsp; StackCookie
0x140056629  call    __security_check_cookie
0x14005662e  lea     r11, [rsp+270h+var_20]
0x140056636  mov     rbx, [r11+40h]
0x14005663a  mov     rsi, [r11+48h]
0x14005663e  mov     rsp, r11
0x140056641  pop     r15
0x140056643  pop     r14
0x140056645  pop     r12
0x140056647  pop     rdi
0x140056648  pop     rbp
0x140056649  retn
  ... truncated ...
```
