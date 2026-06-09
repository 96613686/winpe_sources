# VsmUtils::SignWithEccKey(VsmUtils::Vtl0KeyBlob *,uchar *,uint,ushort const *,VsmUtils::TpmAuthType,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x14005c700`
- end: `0x14005cb43`
- name: `?SignWithEccKey@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEAEIPEBGW4TpmAuthType@1@1I1I1IPEAIK@Z`
- size: `1091`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140059044`

## callees

- `0x14000e034`
- `0x14000f6a0`
- `0x1400154b8`
- `0x1400389ec`
- `0x14005522c`
- `0x140055470`
- `0x140056a48`
- `0x14005afe4`
- `0x14005b484`
- `0x14005bdc0`
- `0x14005c5c4`
- `0x14005c698`
- `0x14005c700`
- `0x1400624d4`
- `0x140065c28`
- `0x14006abb0`
- `0x14006ac88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005c7ad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005c7c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005c7df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005c7ad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005c7c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005c7df`

## string_xrefs

- `0x14005c831`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005c897`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005c95a`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005c98a`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005c9c4`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005c9f4`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005ca31`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005ca61`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005cad9`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`
- `0x14005cb0b`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommandsecc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VsmUtils::SignWithEccKey(
        __int64 a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct tpm12class::TPMW8_Sign *a4,
        __int64 a5,
        VsmUtils *a6,
        unsigned __int8 *a7,
        VsmUtils *a8,
        unsigned __int8 *a9,
        void *a10,
        rsize_t DestinationSize,
        unsigned int *a12,
        int a13)
{
  unsigned __int64 v14; // r13
  unsigned int *v17; // rdi
  __int64 v18; // rdx
  rsize_t v19; // r14
  __int64 v20; // rcx
  unsigned __int16 *v22; // r8
  int HashAlgorithmFromInputSize; // eax
  unsigned int v24; // ebx
  int v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // r9d
  int v28; // eax
  unsigned int v29; // r8d
  int v30; // eax
  unsigned int v31; // eax
  int v32; // edx
  int v33; // eax
  unsigned int v34; // r8d
  int v35; // eax
  unsigned int v36; // ecx
  unsigned int v37; // r8d
  int v38; // eax
  unsigned int v39; // r8d
  int v40; // eax
  unsigned __int8 *v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  unsigned int v45; // [rsp+28h] [rbp-D8h]
  unsigned int v46; // [rsp+30h] [rbp-D0h] BYREF
  VsmUtils *v47; // [rsp+38h] [rbp-C8h] BYREF
  char v48; // [rsp+41h] [rbp-BFh]
  VsmUtils *v49; // [rsp+48h] [rbp-B8h]
  void *Destination; // [rsp+50h] [rbp-B0h]
  VsmUtils **v51; // [rsp+58h] [rbp-A8h]
  unsigned __int8 **v52; // [rsp+60h] [rbp-A0h]
  char v53; // [rsp+68h] [rbp-98h]
  _BYTE v54[168]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v55; // [rsp+118h] [rbp+18h]
  int v56; // [rsp+130h] [rbp+30h]
  char v57[72]; // [rsp+138h] [rbp+38h] BYREF
  char v58[128]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v59; // [rsp+200h] [rbp+100h]
  __int16 v60; // [rsp+202h] [rbp+102h]
  __int16 v61; // [rsp+240h] [rbp+140h]
  int v62; // [rsp+244h] [rbp+144h]
  unsigned __int16 v63; // [rsp+350h] [rbp+250h]
  void *Source; // [rsp+358h] [rbp+258h]
  unsigned __int16 v65; // [rsp+398h] [rbp+298h]
  void *v66; // [rsp+3A0h] [rbp+2A0h]
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  v14 = a3;
  v47 = a6;
  v49 = a8;
  Destination = a10;
  v17 = a12;
  if ( !a1 || !a2 || !a12 )
  {
    v18 = 31;
    goto LABEL_43;
  }
  if ( a13 )
  {
    v18 = 33;
LABEL_43:
    v24 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
      (const char *)0x80070057LL,
      (int)v41);
    return v24;
  }
  v19 = (unsigned int)DestinationSize;
  if ( !a10 && !(_DWORD)DestinationSize )
  {
    if ( (unsigned int)_o__wcsicmp(a4, L"ECDSA_P256") )
    {
      if ( (unsigned int)_o__wcsicmp(a4, L"ECDSA_P384") )
      {
        if ( (unsigned int)_o__wcsicmp(a4, L"ECDSA_P521") )
          return 0;
        v20 = 5;
      }
      else
      {
        v20 = 4;
      }
    }
    else
    {
      v20 = 3;
    }
    *v17 = 2 * (unsigned __int16)VsmUtils::KeySizeBytesFromCurveID<unsigned short>(v20);
    return 0;
  }
  SetTbsHandle(*(_QWORD *)(a1 + 40));
  v48 = 1;
  LOWORD(v46) = 0;
  HashAlgorithmFromInputSize = VsmUtils::GetHashAlgorithmFromInputSize(
                                 (VsmUtils *)(unsigned int)v14,
                                 (unsigned int)&v46,
                                 v22);
  v24 = HashAlgorithmFromInputSize;
  if ( HashAlgorithmFromInputSize >= 0 )
  {
    tpm12class::TPMW8_Sign::TPMW8_Sign((tpm12class::TPMW8_Sign *)v54);
    v56 = *(_DWORD *)(a1 + 48);
    v60 = v46;
    v59 = 24;
    v25 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (tpm12class::TPMW82B_BUFFER *)v57,
            (const unsigned __int8 *)(a1 + 4),
            0x22u);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v61 = -32732;
      v62 = 1073741831;
      v25 = tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v58, a2, v14);
      v24 = v25;
      if ( v25 >= 0 )
      {
        LODWORD(v41) = (_DWORD)a7;
        v25 = VsmUtils::AuthorizeSignCommand(
                (VsmUtils *)a1,
                (struct VsmUtils::Vtl0KeyBlob *)v54,
                a4,
                (const unsigned __int16 *)v47,
                v41,
                v45);
        v24 = v25;
        if ( v25 >= 0 )
        {
          v51 = &v47;
          v52 = &a7;
          v53 = 1;
          v28 = VsmUtils::ExecutePolicyOr(v49, (unsigned __int8 *)(unsigned int)a9, *(_DWORD *)(v55 + 16), v27);
          v24 = v28;
          if ( v28 >= 0 )
          {
            v31 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v54, 0);
            v33 = VsmUtils::MapTpmError((VsmUtils *)v31, v32);
            v24 = v33;
            if ( v33 >= 0 )
            {
              v36 = v63 + v65;
              *v17 = v36;
              if ( v36 <= (unsigned int)v19 )
              {
                memcpy_s_0(Destination, v19, Source, v63);
                memcpy_s_0((char *)Destination + v63, (unsigned int)v19 - v63, v66, v65);
                v40 = VsmUtils::CloseVtl1AuthBlob(v47, (unsigned __int8 *)(unsigned int)a7, v39);
                if ( v40 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x58,
                    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
                    (const char *)(unsigned int)v40,
                    (int)v41);
                tpm12class::TPMW8_Sign::~TPMW8_Sign((tpm12class::TPMW8_Sign *)v54);
                v24 = 0;
                goto LABEL_41;
              }
              v24 = -2146893784;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x63,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
                (const char *)0x80090028LL,
                (int)v41);
              v38 = VsmUtils::CloseVtl1AuthBlob(v47, (unsigned __int8 *)(unsigned int)a7, v37);
              if ( v38 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x58,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
                  (const char *)(unsigned int)v38,
                  v44);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5E,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
                (const char *)(unsigned int)v33,
                (int)v41);
              v35 = VsmUtils::CloseVtl1AuthBlob(v47, (unsigned __int8 *)(unsigned int)a7, v34);
              if ( v35 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x58,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
                  (const char *)(unsigned int)v35,
                  v43);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5C,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
              (const char *)(unsigned int)v28,
              (int)v41);
            v30 = VsmUtils::CloseVtl1AuthBlob(v47, (unsigned __int8 *)(unsigned int)a7, v29);
            if ( v30 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x58,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
                (const char *)(unsigned int)v30,
                v42);
          }
          goto LABEL_21;
        }
        v26 = 80;
      }
      else
      {
        v26 = 75;
      }
    }
    else
    {
      v26 = 69;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
      (const char *)(unsigned int)v25,
      (int)v41);
LABEL_21:
    tpm12class::TPMW8_Sign::~TPMW8_Sign((tpm12class::TPMW8_Sign *)v54);
    goto LABEL_41;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3F,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommandsecc.cpp",
    (const char *)(unsigned int)HashAlgorithmFromInputSize,
    (int)v41);
LABEL_41:
  ClearTbsHandle();
  return v24;
}

```

## disassembly

```asm
0x14005c700  push    rbp
0x14005c702  push    rbx
0x14005c703  push    rsi
0x14005c704  push    rdi
0x14005c705  push    r12
0x14005c707  push    r13
0x14005c709  push    r14
0x14005c70b  push    r15
0x14005c70d  lea     rbp, [rsp-348h]
0x14005c715  sub     rsp, 448h
0x14005c71c  mov     rax, cs:__security_cookie
0x14005c723  xor     rax, rsp
0x14005c726  mov     [rbp+380h+var_50], rax
0x14005c72d  mov     rsi, r9
0x14005c730  mov     r13d, r8d
0x14005c733  mov     r12, rdx
0x14005c736  mov     r15, rcx
0x14005c739  mov     rax, [rbp+380h+arg_28]
0x14005c740  mov     [rsp+480h+var_448], rax
0x14005c745  mov     rax, [rbp+380h+arg_38]
0x14005c74c  mov     [rsp+480h+var_438], rax
0x14005c751  mov     rax, [rbp+380h+arg_48]
0x14005c758  mov     [rsp+480h+Destination], rax
0x14005c75d  mov     rdi, [rbp+380h+arg_58]
0x14005c764  test    rcx, rcx
0x14005c767  jz      loc_14005CAFE
0x14005c76d  test    rdx, rdx
0x14005c770  jz      loc_14005CAFE
0x14005c776  test    rdi, rdi
0x14005c779  jz      loc_14005CAFE
0x14005c77f  cmp     [rbp+380h+arg_60], 0
0x14005c786  jz      short loc_14005C792
0x14005c788  mov     edx, 21h ; '!'
0x14005c78d  jmp     loc_14005CB03
0x14005c792  mov     r14d, dword ptr [rbp+380h+DestinationSize]
0x14005c799  test    rax, rax
0x14005c79c  jnz     short loc_14005C7FF
0x14005c79e  test    r14d, r14d
0x14005c7a1  jnz     short loc_14005C7FF
0x14005c7a3  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x14005c7aa  mov     rcx, rsi
0x14005c7ad  call    cs:__imp__o__wcsicmp
0x14005c7b3  test    eax, eax
0x14005c7b5  jnz     short loc_14005C7BC
0x14005c7b7  lea     ecx, [rax+3]
0x14005c7ba  jmp     short loc_14005C7EC
0x14005c7bc  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x14005c7c3  mov     rcx, rsi
0x14005c7c6  call    cs:__imp__o__wcsicmp
0x14005c7cc  test    eax, eax
0x14005c7ce  jnz     short loc_14005C7D5
0x14005c7d0  lea     ecx, [rax+4]
0x14005c7d3  jmp     short loc_14005C7EC
0x14005c7d5  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x14005c7dc  mov     rcx, rsi
0x14005c7df  call    cs:__imp__o__wcsicmp
0x14005c7e5  test    eax, eax
0x14005c7e7  jnz     short loc_14005C7F8
0x14005c7e9  lea     ecx, [rax+5]
0x14005c7ec  call    ??$KeySizeBytesFromCurveID@G@VsmUtils@@YAGG@Z; VsmUtils::KeySizeBytesFromCurveID<ushort>(ushort)
0x14005c7f1  movzx   eax, ax
0x14005c7f4  add     eax, eax
0x14005c7f6  mov     [rdi], eax
0x14005c7f8  xor     eax, eax
0x14005c7fa  jmp     loc_14005CB20
0x14005c7ff  mov     rcx, [rcx+28h]; unsigned __int64
0x14005c803  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x14005c808  mov     [rsp+480h+var_43F], 1
0x14005c80d  xor     eax, eax
0x14005c80f  mov     word ptr [rsp+480h+var_450], ax
0x14005c814  lea     rdx, [rsp+480h+var_450]; unsigned int
0x14005c819  mov     ecx, r13d; this
0x14005c81c  call    ?GetHashAlgorithmFromInputSize@VsmUtils@@YAJIPEAG@Z; VsmUtils::GetHashAlgorithmFromInputSize(uint,ushort *)
0x14005c821  mov     ebx, eax
0x14005c823  test    eax, eax
0x14005c825  jns     short loc_14005C847
0x14005c827  mov     rcx, [rbp+388h]; this
0x14005c82e  mov     r9d, eax; char *
0x14005c831  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c838  mov     edx, 3Fh ; '?'; void *
0x14005c83d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005c842  jmp     loc_14005CAF7
0x14005c847  lea     rcx, [rsp+480h+var_410]; this
0x14005c84c  call    ??0TPMW8_Sign@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Sign::TPMW8_Sign(void)
0x14005c851  nop
0x14005c852  mov     eax, [r15+30h]
0x14005c856  mov     [rbp+380h+var_350], eax
0x14005c859  movzx   eax, word ptr [rsp+480h+var_450]
0x14005c85e  mov     [rbp+380h+var_27E], ax
0x14005c865  mov     eax, 18h
0x14005c86a  mov     [rbp+380h+var_280], ax
0x14005c871  lea     rdx, [r15+4]; unsigned __int8 *
0x14005c875  lea     r8d, [rax+0Ah]; unsigned __int64
0x14005c879  lea     rcx, [rbp+380h+var_348]; this
0x14005c87d  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005c882  mov     ebx, eax
0x14005c884  test    eax, eax
0x14005c886  jns     short loc_14005C8B3
0x14005c888  mov     edx, 45h ; 'E'; void *
0x14005c88d  mov     rcx, [rbp+388h]; this
0x14005c894  mov     r9d, eax; char *
0x14005c897  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c89e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005c8a3  nop
0x14005c8a4  lea     rcx, [rsp+480h+var_410]; this
0x14005c8a9  call    ??1TPMW8_Sign@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Sign::~TPMW8_Sign(void)
0x14005c8ae  jmp     loc_14005CAF7
0x14005c8b3  mov     eax, 8024h
0x14005c8b8  mov     [rbp+380h+var_240], ax
0x14005c8bf  mov     [rbp+380h+var_23C], 40000007h
0x14005c8c9  mov     r8, r13; unsigned __int64
0x14005c8cc  mov     rdx, r12; unsigned __int8 *
0x14005c8cf  lea     rcx, [rbp+380h+var_300]; this
0x14005c8d6  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005c8db  mov     ebx, eax
0x14005c8dd  test    eax, eax
0x14005c8df  jns     short loc_14005C8E8
0x14005c8e1  mov     edx, 4Bh ; 'K'
0x14005c8e6  jmp     short loc_14005C88D
0x14005c8e8  mov     eax, dword ptr [rbp+380h+arg_30]
0x14005c8ee  mov     dword ptr [rsp+480h+var_460], eax; int
0x14005c8f2  mov     r9, [rsp+480h+var_448]; unsigned __int16 *
0x14005c8f7  mov     r8, rsi; struct tpm12class::TPMW8_Sign *
0x14005c8fa  lea     rdx, [rsp+480h+var_410]; struct VsmUtils::Vtl0KeyBlob *
0x14005c8ff  mov     rcx, r15; this
0x14005c902  call    ?AuthorizeSignCommand@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEAVTPMW8_Sign@tpm12class@@PEBGPEAEI@Z; VsmUtils::AuthorizeSignCommand(VsmUtils::Vtl0KeyBlob *,tpm12class::TPMW8_Sign *,ushort const *,uchar *,uint)
0x14005c907  mov     ebx, eax
0x14005c909  test    eax, eax
0x14005c90b  jns     short loc_14005C917
0x14005c90d  mov     edx, 50h ; 'P'
0x14005c912  jmp     loc_14005C88D
0x14005c917  lea     rax, [rsp+480h+var_448]
0x14005c91c  mov     [rsp+480h+var_428], rax
0x14005c921  lea     rax, [rbp+380h+arg_30]
0x14005c928  mov     [rsp+480h+var_420], rax
0x14005c92d  mov     [rsp+480h+var_418], 1
0x14005c932  mov     r8, [rbp+380h+var_368]
0x14005c936  mov     r8d, [r8+10h]; unsigned int
0x14005c93a  mov     edx, dword ptr [rbp+380h+arg_40]; unsigned __int8 *
0x14005c940  mov     rcx, [rsp+480h+var_438]; this
0x14005c945  call    ?ExecutePolicyOr@VsmUtils@@YAJPEAEII@Z; VsmUtils::ExecutePolicyOr(uchar *,uint,uint)
0x14005c94a  mov     ebx, eax
0x14005c94c  test    eax, eax
0x14005c94e  jns     short loc_14005C9A1
0x14005c950  mov     rcx, [rbp+388h]; this
0x14005c957  mov     r9d, eax; char *
0x14005c95a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c961  mov     edx, 5Ch ; '\'; void *
0x14005c966  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005c96b  nop
0x14005c96c  mov     edx, dword ptr [rbp+380h+arg_30]; unsigned __int8 *
0x14005c972  mov     rcx, [rsp+480h+var_448]; this
0x14005c977  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005c97c  mov     rcx, [rbp+388h]; this
0x14005c983  test    eax, eax
0x14005c985  jns     short loc_14005C99C
0x14005c987  mov     r9d, eax; char *
0x14005c98a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c991  mov     edx, 58h ; 'X'; void *
0x14005c996  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005c99b  nop
0x14005c99c  jmp     loc_14005C8A4
0x14005c9a1  xor     edx, edx; void *
0x14005c9a3  lea     rcx, [rsp+480h+var_410]; this
0x14005c9a8  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x14005c9ad  mov     ecx, eax; this
0x14005c9af  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x14005c9b4  mov     ebx, eax
0x14005c9b6  test    eax, eax
0x14005c9b8  jns     short loc_14005CA0B
0x14005c9ba  mov     rcx, [rbp+388h]; this
0x14005c9c1  mov     r9d, eax; char *
0x14005c9c4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c9cb  mov     edx, 5Eh ; '^'; void *
0x14005c9d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005c9d5  nop
0x14005c9d6  mov     edx, dword ptr [rbp+380h+arg_30]; unsigned __int8 *
0x14005c9dc  mov     rcx, [rsp+480h+var_448]; this
0x14005c9e1  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005c9e6  mov     rcx, [rbp+388h]; this
0x14005c9ed  test    eax, eax
0x14005c9ef  jns     short loc_14005CA06
0x14005c9f1  mov     r9d, eax; char *
0x14005c9f4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005c9fb  mov     edx, 58h ; 'X'; void *
0x14005ca00  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005ca05  nop
0x14005ca06  jmp     loc_14005C8A4
0x14005ca0b  movzx   ecx, [rbp+380h+var_E8]
0x14005ca12  movzx   eax, [rbp+380h+var_130]
0x14005ca19  add     ecx, eax
0x14005ca1b  mov     [rdi], ecx
0x14005ca1d  cmp     ecx, r14d
0x14005ca20  jbe     short loc_14005CA78
0x14005ca22  mov     rcx, [rbp+388h]; this
0x14005ca29  mov     ebx, 80090028h
0x14005ca2e  mov     r9d, ebx; char *
0x14005ca31  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005ca38  mov     edx, 63h ; 'c'; void *
0x14005ca3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005ca42  nop
0x14005ca43  mov     edx, dword ptr [rbp+380h+arg_30]; unsigned __int8 *
0x14005ca49  mov     rcx, [rsp+480h+var_448]; this
0x14005ca4e  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005ca53  mov     rcx, [rbp+388h]; this
0x14005ca5a  test    eax, eax
0x14005ca5c  jns     short loc_14005CA73
0x14005ca5e  mov     r9d, eax; char *
0x14005ca61  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005ca68  mov     edx, 58h ; 'X'; void *
0x14005ca6d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005ca72  nop
0x14005ca73  jmp     loc_14005C8A4
0x14005ca78  movzx   r9d, [rbp+380h+var_130]; SourceSize
0x14005ca80  mov     rdx, r14; DestinationSize
0x14005ca83  mov     r8, [rbp+380h+Source]; Source
0x14005ca8a  mov     rcx, [rsp+480h+Destination]; Destination
0x14005ca8f  call    memcpy_s_0
0x14005ca94  movzx   ecx, [rbp+380h+var_130]
0x14005ca9b  movzx   r9d, [rbp+380h+var_E8]; SourceSize
0x14005caa3  sub     r14d, ecx
0x14005caa6  mov     edx, r14d; DestinationSize
0x14005caa9  add     rcx, [rsp+480h+Destination]; Destination
0x14005caae  mov     r8, [rbp+380h+var_E0]; Source
0x14005cab5  call    memcpy_s_0
0x14005caba  nop
0x14005cabb  mov     edx, dword ptr [rbp+380h+arg_30]; unsigned __int8 *
0x14005cac1  mov     rcx, [rsp+480h+var_448]; this
0x14005cac6  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005cacb  mov     rcx, [rbp+388h]; this
0x14005cad2  test    eax, eax
0x14005cad4  jns     short loc_14005CAEB
0x14005cad6  mov     r9d, eax; char *
0x14005cad9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cae0  mov     edx, 58h ; 'X'; void *
0x14005cae5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005caea  nop
0x14005caeb  lea     rcx, [rsp+480h+var_410]; this
0x14005caf0  call    ??1TPMW8_Sign@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Sign::~TPMW8_Sign(void)
0x14005caf5  xor     ebx, ebx
0x14005caf7  call    ?ClearTbsHandle@@YAXXZ; ClearTbsHandle(void)
0x14005cafc  jmp     short loc_14005CB1E
0x14005cafe  mov     edx, 1Fh; void *
0x14005cb03  mov     ebx, 80070057h
0x14005cb08  mov     r9d, ebx; char *
0x14005cb0b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\trustlet\\utils"...
0x14005cb12  mov     rcx, [rbp+388h]; this
0x14005cb19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005cb1e  mov     eax, ebx
0x14005cb20  mov     rcx, [rbp+380h+var_50]
0x14005cb27  xor     rcx, rsp; StackCookie
0x14005cb2a  call    __security_check_cookie
0x14005cb2f  add     rsp, 448h
0x14005cb36  pop     r15
0x14005cb38  pop     r14
0x14005cb3a  pop     r13
0x14005cb3c  pop     r12
0x14005cb3e  pop     rdi
0x14005cb3f  pop     rsi
0x14005cb40  pop     rbx
0x14005cb41  pop     rbp
0x14005cb42  retn
```
