# VsmUtils::SecretAgreement(VsmUtils::Vtl0KeyBlob *,ushort const *,uchar *,uint,VsmUtils::TpmAuthType,uchar *,uint,uchar *,uint,unsigned __int64 *,ulong)

- ea: `0x1400589bc`
- end: `0x14005903d`
- name: `?SecretAgreement@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEBGPEAEIW4TpmAuthType@1@2I2IPEA_KK@Z`
- size: `1665`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140048b58`

## callees

- `0x140007410`
- `0x140009be0`
- `0x140009fa0`
- `0x14000e034`
- `0x14000fc48`
- `0x1400106dc`
- `0x1400107c4`
- `0x1400154b8`
- `0x14001cf2c`
- `0x1400389ec`
- `0x140055164`
- `0x14005522c`
- `0x140055470`
- `0x140056a48`
- `0x1400589bc`
- `0x14005ad84`
- `0x14005b484`
- `0x14005c5c4`
- `0x140061fb0`
- `0x1400624d4`
- `0x1400652d4`
- `0x140065c28`
- `0x140066174`
- `0x140068c88`
- `0x140068f20`
- `0x140069014`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140058c11`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140058fe7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140058c11`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140058fe7`

## string_xrefs

- `0x140058a81`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058be8`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058cbf`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058d8a`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058dbc`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058df5`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058e27`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058e5d`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058e8f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058edd`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058f0f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140058fa2`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005900f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall VsmUtils::SecretAgreement(
        __int64 a1,
        void *a2,
        __int64 a3,
        unsigned int a4,
        __int16 a5,
        VsmUtils *a6,
        unsigned __int8 *a7,
        VsmUtils *a8,
        unsigned __int8 *a9,
        _QWORD *a10,
        void **a11)
{
  unsigned __int64 v11; // rsi
  _QWORD *v14; // r12
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rdx
  rsize_t v19; // r15
  int v20; // eax
  char *v21; // rdi
  int v22; // eax
  int SerializedParameters; // eax
  int v24; // eax
  HLOCAL v25; // rcx
  bool v26; // zf
  unsigned int v27; // r8d
  int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // r9d
  int v31; // eax
  unsigned int v32; // r8d
  int v33; // eax
  unsigned int v34; // eax
  int v35; // edx
  int v36; // eax
  unsigned int v37; // r8d
  int v38; // eax
  unsigned int v39; // r8d
  int v40; // eax
  unsigned __int16 v41; // dx
  unsigned int v42; // r8d
  int v43; // eax
  rsize_t v44; // rbx
  unsigned int v45; // r8d
  int v46; // eax
  HLOCAL v47; // rcx
  int v49; // [rsp+20h] [rbp-E0h]
  void **v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  int v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  struct tpm12class::TPMW82B_BUFFER *v56; // [rsp+28h] [rbp-D8h]
  unsigned int v57; // [rsp+30h] [rbp-D0h]
  ULONG v58; // [rsp+38h] [rbp-C8h]
  struct tpm12class::TPMW82B_BUFFER *v59[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v60; // [rsp+58h] [rbp-A8h]
  __int64 v61; // [rsp+60h] [rbp-A0h]
  __int64 v62; // [rsp+68h] [rbp-98h]
  char v63; // [rsp+70h] [rbp-90h]
  __int16 v64; // [rsp+78h] [rbp-88h]
  __int64 v65; // [rsp+80h] [rbp-80h]
  void *Destination[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v67[20]; // [rsp+B0h] [rbp-50h] BYREF
  VsmUtils **v68; // [rsp+100h] [rbp+0h]
  unsigned __int8 **v69; // [rsp+108h] [rbp+8h]
  char v70; // [rsp+110h] [rbp+10h]
  _BYTE v71[168]; // [rsp+120h] [rbp+20h] BYREF
  tpm12class::TPMW8_SESSION *v72; // [rsp+1C8h] [rbp+C8h]
  int v73; // [rsp+1E0h] [rbp+E0h]
  _BYTE v74[72]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v75[56]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v76; // [rsp+268h] [rbp+168h]
  _BYTE *v77; // [rsp+270h] [rbp+170h]
  unsigned __int16 v78; // [rsp+2B0h] [rbp+1B0h]
  unsigned __int16 *v79; // [rsp+2B8h] [rbp+1B8h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]
  _QWORD *v81; // [rsp+300h] [rbp+200h]
  HLOCAL hMem; // [rsp+308h] [rbp+208h] BYREF

  hMem = a2;
  v11 = a4;
  if ( !a1 || !a3 || !a4 || (v14 = a10) == 0 )
  {
    v16 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)0x80070057LL,
      v49);
    return v16;
  }
  SetTbsHandle(*(_QWORD *)(a1 + 40));
  HIBYTE(a5) = 1;
  tpm12class::TPMW8_ECDH_ZGen::TPMW8_ECDH_ZGen((tpm12class::TPMW8_ECDH_ZGen *)v71);
  v73 = *(_DWORD *)(a1 + 48);
  v15 = tpm12class::TPMW82B_BUFFER::CopyFrom(
          (tpm12class::TPMW82B_BUFFER *)v74,
          (const unsigned __int8 *)(a1 + 4),
          0x22u);
  v16 = v15;
  if ( v15 >= 0 )
  {
    if ( v11 < (unsigned __int64)(unsigned int)(2 * *(_DWORD *)(a3 + 4)) + 8 )
    {
      v16 = -2146893785;
      v17 = 2148073511LL;
      v18 = 491;
      goto LABEL_9;
    }
    v19 = *(unsigned __int16 *)(a3 + 4);
    v20 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v75, (unsigned __int16)(2 * (v19 + 2)));
    v16 = v20;
    if ( v20 < 0 )
    {
      v17 = (unsigned int)v20;
      v18 = 498;
      goto LABEL_9;
    }
    v21 = (char *)(a3 + 8);
    *v77 = BYTE1(v19);
    v77[1] = v19;
    memcpy_s_0(v77 + 2, (unsigned int)v76 - 2, v21, v19);
    v77[(unsigned int)(v19 + 2)] = BYTE1(v19);
    v77[(unsigned int)(v19 + 3)] = v19;
    memcpy_s_0(&v77[(unsigned int)(v19 + 4)], (unsigned int)v76 - ((_DWORD)v19 + 4), &v21[v19], v19);
    *((_WORD *)v72 + 381) = 11;
    *((_BYTE *)v72 + 761) = 1;
    v22 = tpm12class::TPMW8_SESSION::Create(v72, 0);
    v16 = v22;
    if ( v22 < 0 )
    {
      v17 = (unsigned int)v22;
      v18 = 518;
      goto LABEL_9;
    }
    LODWORD(a11) = 0;
    SerializedParameters = tpm12class::TPMW8_COMMAND::GetSerializedParameters(
                             (tpm12class::TPMW8_COMMAND *)v71,
                             (unsigned int *)&a11,
                             0);
    v16 = SerializedParameters;
    if ( SerializedParameters < 0 )
    {
      v17 = (unsigned int)SerializedParameters;
      v18 = 523;
      goto LABEL_9;
    }
    wil::make_unique_hlocal<unsigned char [0]>(&hMem, (unsigned int)a11);
    v24 = tpm12class::TPMW8_COMMAND::GetSerializedParameters(
            (tpm12class::TPMW8_COMMAND *)v71,
            (unsigned int *)&a11,
            (unsigned __int8 *)hMem);
    v16 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20E,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v24,
        v49);
      goto LABEL_18;
    }
    `eh vector constructor iterator'(
      v67,
      0x48u,
      1u,
      (void (*)(void *))tpm12class::TPMW82B_BUFFER::TPMW82B_BUFFER,
      (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
    tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v67, (const unsigned __int8 *)(a1 + 4), 0x22u);
    v59[1] = 0;
    v59[2] = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    LODWORD(v50) = (_DWORD)a11;
    v28 = tpm12class::W8_ComputeCpHash(
            (tpm12class *)v59,
            0x154u,
            v27,
            (unsigned int)v67,
            v50,
            (unsigned int)hMem,
            (const unsigned __int8 *)v59,
            v58,
            (struct tpm12class::TPMW82B_BUFFER *)&tpm12class::TPMW82B_BUFFER::`vftable');
    v16 = v28;
    if ( v28 >= 0 )
    {
      LODWORD(v56) = *((_DWORD *)v72 + 4);
      v28 = VsmUtils::AuthorizePolicySecret(
              *(VsmUtils **)(a1 + 40),
              (unsigned __int64)L"ECDH_P256",
              (const unsigned __int16 *)a6,
              (unsigned __int8 *)(unsigned int)a7,
              (struct tpm12class::TPMW82B_BUFFER *)v59,
              v56,
              v57);
      v16 = v28;
      if ( v28 >= 0 )
      {
        v68 = &a6;
        v69 = &a7;
        v70 = 1;
        v31 = VsmUtils::ExecutePolicyOr(a8, (unsigned __int8 *)(unsigned int)a9, *((_DWORD *)v72 + 4), v30);
        v16 = v31;
        if ( v31 >= 0 )
        {
          v34 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v71, 0);
          v36 = VsmUtils::MapTpmError((VsmUtils *)v34, v35);
          v16 = v36;
          if ( v36 >= 0 )
          {
            if ( v78 > 2u )
            {
              v41 = _byteswap_ushort(*v79);
              if ( v78 > (unsigned int)v41 + 2 )
              {
                v44 = v41;
                std::vector<unsigned char>::vector<unsigned char>(Destination, v41);
                memcpy_s_0(Destination[0], v44, v79 + 1, v44);
                v81 = operator new(0x20u);
                std::vector<unsigned char>::vector<unsigned char>(v81, Destination);
                v81[3] = L"ECDH_P256";
                *v14 = v81;
                std::vector<unsigned char>::_Tidy(Destination);
                v46 = VsmUtils::CloseVtl1AuthBlob(a6, (unsigned __int8 *)(unsigned int)a7, v45);
                if ( v46 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x21D,
                    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                    (const char *)(unsigned int)v46,
                    v51);
                tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v59);
                `eh vector destructor iterator'(
                  v67,
                  0x48u,
                  1u,
                  (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
                v47 = hMem;
                hMem = 0;
                if ( v47 )
                  LocalFree(v47);
                v16 = 0;
                goto LABEL_47;
              }
              v16 = -2147467259;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x22B,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)0x80004005LL,
                v51);
              v43 = VsmUtils::CloseVtl1AuthBlob(a6, (unsigned __int8 *)(unsigned int)a7, v42);
              if ( v43 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x21D,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                  (const char *)(unsigned int)v43,
                  v55);
            }
            else
            {
              v16 = -2147467259;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x226,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)0x80004005LL,
                v51);
              v40 = VsmUtils::CloseVtl1AuthBlob(a6, (unsigned __int8 *)(unsigned int)a7, v39);
              if ( v40 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x21D,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                  (const char *)(unsigned int)v40,
                  v54);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x222,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)(unsigned int)v36,
              v51);
            v38 = VsmUtils::CloseVtl1AuthBlob(a6, (unsigned __int8 *)(unsigned int)a7, v37);
            if ( v38 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x21D,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)(unsigned int)v38,
                v53);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x220,
            (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
            (const char *)(unsigned int)v31,
            v51);
          v33 = VsmUtils::CloseVtl1AuthBlob(a6, (unsigned __int8 *)(unsigned int)a7, v32);
          if ( v33 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x21D,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)(unsigned int)v33,
              v52);
        }
        goto LABEL_23;
      }
      v29 = 537;
    }
    else
    {
      v29 = 534;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)(unsigned int)v28,
      v51);
LABEL_23:
    tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v59);
    `eh vector destructor iterator'(v67, 0x48u, 1u, (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
LABEL_18:
    v25 = hMem;
    v26 = hMem == 0;
    hMem = 0;
    if ( !v26 )
      LocalFree(v25);
    goto LABEL_47;
  }
  v17 = (unsigned int)v15;
  v18 = 488;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
    (const char *)v17,
    v49);
LABEL_47:
  tpm12class::TPMW8_ECDH_ZGen::~TPMW8_ECDH_ZGen((tpm12class::TPMW8_ECDH_ZGen *)v71);
  ClearTbsHandle();
  return v16;
}

```

## disassembly

```asm
0x1400589bc  mov     [rsp-8+arg_10], rbx
0x1400589c1  mov     [rsp-8+hMem], rdx
0x1400589c6  push    rbp
0x1400589c7  push    rsi
0x1400589c8  push    rdi
0x1400589c9  push    r12
0x1400589cb  push    r13
0x1400589cd  push    r14
0x1400589cf  push    r15
0x1400589d1  lea     rbp, [rsp-1C0h]
0x1400589d9  sub     rsp, 2C0h
0x1400589e0  mov     esi, r9d
0x1400589e3  mov     rdi, r8
0x1400589e6  mov     r14, rcx
0x1400589e9  test    rcx, rcx
0x1400589ec  jz      loc_140059000
0x1400589f2  test    r8, r8
0x1400589f5  jz      loc_140059000
0x1400589fb  test    r9d, r9d
0x1400589fe  jz      loc_140059000
0x140058a04  mov     r12, [rbp+1F0h+arg_48]
0x140058a0b  test    r12, r12
0x140058a0e  jz      loc_140059000
0x140058a14  mov     rcx, [rcx+28h]; unsigned __int64
0x140058a18  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x140058a1d  mov     [rbp+1F0h+arg_21], 1
0x140058a24  lea     rcx, [rbp+1F0h+var_1D0]; this
0x140058a28  call    ??0TPMW8_ECDH_ZGen@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ECDH_ZGen::TPMW8_ECDH_ZGen(void)
0x140058a2d  nop
0x140058a2e  mov     eax, [r14+30h]
0x140058a32  mov     [rbp+1F0h+var_110], eax
0x140058a38  mov     r8d, 22h ; '"'; unsigned __int64
0x140058a3e  lea     rdx, [r14+4]; unsigned __int8 *
0x140058a42  lea     rcx, [rbp+1F0h+var_108]; this
0x140058a49  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x140058a4e  mov     ebx, eax
0x140058a50  test    eax, eax
0x140058a52  jns     short loc_140058A5E
0x140058a54  mov     r9d, eax
0x140058a57  mov     edx, 1E8h
0x140058a5c  jmp     short loc_140058A7A
0x140058a5e  mov     eax, [rdi+4]
0x140058a61  lea     ecx, [rax+rax]
0x140058a64  add     rcx, 8
0x140058a68  cmp     rsi, rcx
0x140058a6b  jnb     short loc_140058A92
0x140058a6d  mov     ebx, 80090027h
0x140058a72  mov     r9d, ebx; char *
0x140058a75  mov     edx, 1EBh; void *
0x140058a7a  mov     rcx, [rbp+1F8h]; this
0x140058a81  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058a8d  jmp     loc_140058FEF
0x140058a92  movzx   r15d, word ptr [rdi+4]
0x140058a97  mov     eax, 2
0x140058a9c  add     eax, r15d
0x140058a9f  add     ax, ax
0x140058aa2  movzx   edx, ax; unsigned __int64
0x140058aa5  lea     rcx, [rbp+1F0h+var_C0]; this
0x140058aac  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x140058ab1  mov     ebx, eax
0x140058ab3  test    eax, eax
0x140058ab5  jns     short loc_140058AC1
0x140058ab7  mov     r9d, eax
0x140058aba  mov     edx, 1F2h
0x140058abf  jmp     short loc_140058A7A
0x140058ac1  add     rdi, 8
0x140058ac5  movzx   ebx, r15w
0x140058ac9  shr     bx, 8
0x140058acd  mov     rax, [rbp+1F0h+var_80]
0x140058ad4  mov     [rax], bl
0x140058ad6  mov     rax, [rbp+1F0h+var_80]
0x140058add  mov     [rax+1], r15b
0x140058ae1  movzx   edx, [rbp+1F0h+var_88]
0x140058ae8  sub     edx, 2; DestinationSize
0x140058aeb  mov     rcx, [rbp+1F0h+var_80]
0x140058af2  add     rcx, 2; Destination
0x140058af6  mov     r9, r15; SourceSize
0x140058af9  mov     r8, rdi; Source
0x140058afc  call    memcpy_s_0
0x140058b01  lea     edx, [r15+2]
0x140058b05  mov     rax, [rbp+1F0h+var_80]
0x140058b0c  mov     [rdx+rax], bl
0x140058b0f  lea     ecx, [rdx+1]
0x140058b12  mov     rax, [rbp+1F0h+var_80]
0x140058b19  mov     [rcx+rax], r15b
0x140058b1d  lea     ecx, [rdx+2]
0x140058b20  lea     r8, [r15+rdi]; Source
0x140058b24  movzx   edx, [rbp+1F0h+var_88]
0x140058b2b  sub     edx, ecx; DestinationSize
0x140058b2d  add     rcx, [rbp+1F0h+var_80]; Destination
0x140058b34  mov     r9, r15; SourceSize
0x140058b37  call    memcpy_s_0
0x140058b3c  mov     rax, [rbp+1F0h+var_128]
0x140058b43  mov     word ptr [rax+2FAh], 0Bh
0x140058b4c  mov     rax, [rbp+1F0h+var_128]
0x140058b53  mov     esi, 1
0x140058b58  mov     [rax+2F9h], sil
0x140058b5f  xor     edx, edx; void *
0x140058b61  mov     rcx, [rbp+1F0h+var_128]; this
0x140058b68  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x140058b6d  mov     ebx, eax
0x140058b6f  xor     edi, edi
0x140058b71  test    eax, eax
0x140058b73  jns     short loc_140058B82
0x140058b75  mov     r9d, eax
0x140058b78  mov     edx, 206h
0x140058b7d  jmp     loc_140058A7A
0x140058b82  mov     dword ptr [rbp+1F0h+arg_50], edi
0x140058b88  xor     r8d, r8d; unsigned __int8 *
0x140058b8b  lea     rdx, [rbp+1F0h+arg_50]; unsigned int *
0x140058b92  lea     rcx, [rbp+1F0h+var_1D0]; this
0x140058b96  call    ?GetSerializedParameters@TPMW8_COMMAND@tpm12class@@QEAAJPEAIPEAE@Z; tpm12class::TPMW8_COMMAND::GetSerializedParameters(uint *,uchar *)
0x140058b9b  mov     ebx, eax
0x140058b9d  test    eax, eax
0x140058b9f  jns     short loc_140058BAE
0x140058ba1  mov     r9d, eax
0x140058ba4  mov     edx, 20Bh
0x140058ba9  jmp     loc_140058A7A
0x140058bae  mov     edx, dword ptr [rbp+1F0h+arg_50]
0x140058bb4  lea     rcx, [rbp+1F0h+hMem]
0x140058bbb  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x140058bc0  nop
0x140058bc1  mov     r8, [rbp+1F0h+hMem]; unsigned __int8 *
0x140058bc8  lea     rdx, [rbp+1F0h+arg_50]; unsigned int *
0x140058bcf  lea     rcx, [rbp+1F0h+var_1D0]; this
0x140058bd3  call    ?GetSerializedParameters@TPMW8_COMMAND@tpm12class@@QEAAJPEAIPEAE@Z; tpm12class::TPMW8_COMMAND::GetSerializedParameters(uint *,uchar *)
0x140058bd8  mov     ebx, eax
0x140058bda  test    eax, eax
0x140058bdc  jns     short loc_140058C1C
0x140058bde  mov     rcx, [rbp+1F8h]; this
0x140058be5  mov     r9d, eax; char *
0x140058be8  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058bef  mov     edx, 20Eh; void *
0x140058bf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058bf9  nop
0x140058bfa  mov     rcx, [rbp+1F0h+hMem]; hMem
0x140058c01  test    rcx, rcx
0x140058c04  mov     [rbp+1F0h+hMem], rdi
0x140058c0b  jz      loc_140058FEF
0x140058c11  call    cs:__imp_LocalFree
0x140058c17  jmp     loc_140058FEF
0x140058c1c  lea     r15, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140058c23  mov     [rsp+2F0h+var_2D0], r15; void (*)(void *)
0x140058c28  lea     r9, ??0TPMW82B_BUFFER@tpm12class@@QEAA@XZ; void (*)(void *)
0x140058c2f  mov     r8, rsi; unsigned __int64
0x140058c32  mov     edx, 48h ; 'H'; unsigned __int64
0x140058c37  lea     rcx, [rbp+1F0h+var_240]; void *
0x140058c3b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140058c40  nop
0x140058c41  mov     r8d, 22h ; '"'; unsigned __int64
0x140058c47  lea     rdx, [r14+4]; unsigned __int8 *
0x140058c4b  lea     rcx, [rbp+1F0h+var_240]; this
0x140058c4f  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x140058c54  mov     [rsp+2F0h+var_2A8], rdi
0x140058c59  mov     [rsp+2F0h+var_2A0], rdi
0x140058c5e  mov     [rsp+2F0h+var_298], edi
0x140058c62  mov     [rsp+2F0h+var_290], rdi
0x140058c67  mov     [rsp+2F0h+var_288], rdi
0x140058c6c  mov     [rsp+2F0h+var_280], dil
0x140058c71  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x140058c78  mov     [rsp+2F0h+var_2B0], rax; struct tpm12class::TPMW82B_BUFFER *
0x140058c7d  mov     [rsp+2F0h+var_278], di
0x140058c82  mov     [rbp+1F0h+var_270], rdi
0x140058c86  mov     rax, [rbp+1F0h+hMem]
0x140058c8d  lea     rcx, [rsp+2F0h+var_2B0]; this
0x140058c92  mov     [rsp+2F0h+var_2C0], rcx; unsigned int
0x140058c97  mov     [rsp+2F0h+var_2C8], rax; unsigned int
0x140058c9c  mov     eax, dword ptr [rbp+1F0h+arg_50]
0x140058ca2  mov     dword ptr [rsp+2F0h+var_2D0], eax; int
0x140058ca6  lea     r9, [rbp+1F0h+var_240]; unsigned int
0x140058caa  mov     edx, 154h; unsigned __int16
0x140058caf  call    ?W8_ComputeCpHash@tpm12class@@YAJGIIQEAVTPMW82B_BUFFER@1@IPEBEPEAV21@2@Z; tpm12class::W8_ComputeCpHash(ushort,uint,uint,tpm12class::TPMW82B_BUFFER * const,uint,uchar const *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)
0x140058cb4  mov     ebx, eax
0x140058cb6  test    eax, eax
0x140058cb8  jns     short loc_140058CFA
0x140058cba  mov     edx, 216h; void *
0x140058cbf  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058cc6  mov     r9d, eax; char *
0x140058cc9  mov     rcx, [rbp+1F8h]; this
0x140058cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058cd5  nop
0x140058cd6  lea     rcx, [rsp+2F0h+var_2B0]; this
0x140058cdb  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140058ce0  nop
0x140058ce1  mov     r9, r15; void (*)(void *)
0x140058ce4  mov     r8, rsi; unsigned __int64
0x140058ce7  mov     edx, 48h ; 'H'; unsigned __int64
0x140058cec  lea     rcx, [rbp+1F0h+var_240]; void *
0x140058cf0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140058cf5  jmp     loc_140058BFA
0x140058cfa  mov     rax, [rbp+1F0h+var_128]
0x140058d01  mov     ecx, [rax+10h]
0x140058d04  mov     dword ptr [rsp+2F0h+var_2C8], ecx; struct tpm12class::TPMW82B_BUFFER *
0x140058d08  lea     rax, [rsp+2F0h+var_2B0]
0x140058d0d  mov     [rsp+2F0h+var_2D0], rax; int
0x140058d12  mov     r9d, dword ptr [rbp+1F0h+arg_30]; unsigned __int8 *
0x140058d19  mov     r8, [rbp+1F0h+arg_28]; unsigned __int16 *
0x140058d20  lea     r13, aEcdhP256; "ECDH_P256"
0x140058d27  mov     rdx, r13; unsigned __int64
0x140058d2a  mov     rcx, [r14+28h]; this
0x140058d2e  call    ?AuthorizePolicySecret@VsmUtils@@YAJ_KPEBGPEAEIPEAVTPMW82B_BUFFER@tpm12class@@I@Z; VsmUtils::AuthorizePolicySecret(unsigned __int64,ushort const *,uchar *,uint,tpm12class::TPMW82B_BUFFER *,uint)
0x140058d33  mov     ebx, eax
0x140058d35  test    eax, eax
0x140058d37  jns     short loc_140058D43
0x140058d39  mov     edx, 219h
0x140058d3e  jmp     loc_140058CBF
0x140058d43  lea     rax, [rbp+1F0h+arg_28]
0x140058d4a  mov     [rbp+1F0h+var_1F0], rax
0x140058d4e  lea     rax, [rbp+1F0h+arg_30]
0x140058d55  mov     [rbp+1F0h+var_1E8], rax
0x140058d59  mov     [rbp+1F0h+var_1E0], sil
0x140058d5d  mov     r8, [rbp+1F0h+var_128]
0x140058d64  mov     r8d, [r8+10h]; unsigned int
0x140058d68  mov     edx, dword ptr [rbp+1F0h+arg_40]; unsigned __int8 *
0x140058d6e  mov     rcx, [rbp+1F0h+arg_38]; this
0x140058d75  call    ?ExecutePolicyOr@VsmUtils@@YAJPEAEII@Z; VsmUtils::ExecutePolicyOr(uchar *,uint,uint)
0x140058d7a  mov     ebx, eax
0x140058d7c  test    eax, eax
0x140058d7e  jns     short loc_140058DD3
0x140058d80  mov     rcx, [rbp+1F8h]; this
0x140058d87  mov     r9d, eax; char *
0x140058d8a  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058d91  mov     edx, 220h; void *
0x140058d96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058d9b  nop
0x140058d9c  mov     edx, dword ptr [rbp+1F0h+arg_30]; unsigned __int8 *
0x140058da2  mov     rcx, [rbp+1F0h+arg_28]; this
0x140058da9  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x140058dae  mov     rcx, [rbp+1F8h]; this
0x140058db5  test    eax, eax
0x140058db7  jns     short loc_140058DCE
0x140058db9  mov     r9d, eax; char *
0x140058dbc  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058dc3  mov     edx, 21Dh; void *
0x140058dc8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140058dcd  nop
0x140058dce  jmp     loc_140058CD6
0x140058dd3  xor     edx, edx; void *
0x140058dd5  lea     rcx, [rbp+1F0h+var_1D0]; this
0x140058dd9  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x140058dde  mov     ecx, eax; this
0x140058de0  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140058de5  mov     ebx, eax
0x140058de7  test    eax, eax
0x140058de9  jns     short loc_140058E3E
0x140058deb  mov     rcx, [rbp+1F8h]; this
0x140058df2  mov     r9d, eax; char *
0x140058df5  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058dfc  mov     edx, 222h; void *
0x140058e01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058e06  nop
0x140058e07  mov     edx, dword ptr [rbp+1F0h+arg_30]; unsigned __int8 *
0x140058e0d  mov     rcx, [rbp+1F0h+arg_28]; this
0x140058e14  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x140058e19  mov     rcx, [rbp+1F8h]; this
0x140058e20  test    eax, eax
0x140058e22  jns     short loc_140058E39
0x140058e24  mov     r9d, eax; char *
0x140058e27  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058e2e  mov     edx, 21Dh; void *
0x140058e33  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140058e38  nop
0x140058e39  jmp     loc_140058CD6
0x140058e3e  mov     r9d, 2
0x140058e44  cmp     [rbp+1F0h+var_40], r9w
0x140058e4c  ja      short loc_140058EA6
0x140058e4e  mov     rcx, [rbp+1F8h]; this
0x140058e55  mov     ebx, 80004005h
0x140058e5a  mov     r9d, ebx; char *
0x140058e5d  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058e64  mov     edx, 226h; void *
0x140058e69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058e6e  nop
0x140058e6f  mov     edx, dword ptr [rbp+1F0h+arg_30]; unsigned __int8 *
0x140058e75  mov     rcx, [rbp+1F0h+arg_28]; this
0x140058e7c  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x140058e81  mov     rcx, [rbp+1F8h]; this
0x140058e88  test    eax, eax
0x140058e8a  jns     short loc_140058EA1
0x140058e8c  mov     r9d, eax; char *
0x140058e8f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140058e96  mov     edx, 21Dh; void *
0x140058e9b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140058ea0  nop
0x140058ea1  jmp     loc_140058CD6
0x140058ea6  mov     rax, [rbp+1F0h+var_38]
0x140058ead  movzx   edx, byte ptr [rax+1]
0x140058eb1  movzx   ecx, byte ptr [rax]
0x140058eb4  shl     cx, 8
0x140058eb8  or      dx, cx
0x140058ebb  movzx   r8d, dx
0x140058ebf  lea     ecx, [r9+r8]
0x140058ec3  movzx   eax, [rbp+1F0h+var_40]
0x140058eca  cmp     eax, ecx
0x140058ecc  ja      short loc_140058F26
0x140058ece  mov     rcx, [rbp+1F8h]; this
0x140058ed5  mov     ebx, 80004005h
0x140058eda  mov     r9d, ebx; char *
0x140058edd  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
  ... truncated ...
```
