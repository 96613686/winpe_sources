# VsmUtils::GetPolicy(ushort const *,uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x1400575dc`
- end: `0x140057c8b`
- name: `?GetPolicy@VsmUtils@@YAJPEBGPEAEI1I1I@Z`
- size: `1711`
- prototype: `int(VsmUtils *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `5`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003d41c`
- `0x14003d61c`
- `0x140047bb8`
- `0x140048110`
- `0x140048634`

## callees

- `0x14000e034`
- `0x1400104fc`
- `0x1400389ec`
- `0x1400552dc`
- `0x140056a48`
- `0x1400575dc`
- `0x14005ad84`
- `0x14005b484`
- `0x14005c5c4`
- `0x140061fb0`
- `0x140064304`
- `0x140065c28`
- `0x140068060`
- `0x140068160`
- `0x140069c84`
- `0x140069d98`
- `0x14006a038`
- `0x14006a0b0`

## string_xrefs

- `0x140057699`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057706`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057742`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057772`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400577ae`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400577e9`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057860`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400578ba`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057914`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005796e`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400579af`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057a09`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057a4e`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057aa8`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057af5`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057b4f`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057b84`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057bde`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057c52`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall VsmUtils::GetPolicy(
        VsmUtils *this,
        VsmUtils *a2,
        unsigned __int8 *a3,
        void *a4,
        unsigned __int8 *a5,
        _OWORD *a6,
        unsigned __int8 *a7)
{
  unsigned int v9; // eax
  int v10; // edx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  VsmUtils *TbsHandle; // rax
  unsigned int v15; // eax
  int v16; // edx
  int v17; // eax
  unsigned int v18; // r8d
  int v19; // eax
  unsigned int v20; // r8d
  int v21; // eax
  _OWORD *v22; // rcx
  unsigned int v23; // r8d
  _OWORD *v24; // rax
  unsigned int v25; // eax
  int v26; // edx
  int v27; // eax
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // eax
  int v31; // edx
  int v32; // eax
  unsigned int v33; // r9d
  unsigned int v34; // r8d
  int v35; // eax
  int v36; // eax
  unsigned int v37; // r8d
  int v38; // eax
  unsigned int v39; // eax
  int v40; // edx
  int v41; // eax
  unsigned int v42; // r8d
  int v43; // eax
  unsigned int v44; // eax
  int v45; // edx
  int v46; // eax
  unsigned int v47; // r8d
  int v48; // eax
  int v49; // eax
  unsigned int v50; // r8d
  int v51; // eax
  int v53; // [rsp+28h] [rbp-E0h]
  int v54; // [rsp+28h] [rbp-E0h]
  int v55; // [rsp+28h] [rbp-E0h]
  int v56; // [rsp+28h] [rbp-E0h]
  int v57; // [rsp+28h] [rbp-E0h]
  int v58; // [rsp+28h] [rbp-E0h]
  int v59; // [rsp+28h] [rbp-E0h]
  int v60; // [rsp+28h] [rbp-E0h]
  int v61; // [rsp+28h] [rbp-E0h]
  struct tpm12class::TPMW82B_BUFFER *v62; // [rsp+30h] [rbp-D8h]
  unsigned int v63[48]; // [rsp+38h] [rbp-D0h] BYREF
  int v64; // [rsp+F8h] [rbp-10h]
  VsmUtils **v65; // [rsp+108h] [rbp+0h]
  unsigned __int8 **v66; // [rsp+110h] [rbp+8h]
  char v67; // [rsp+118h] [rbp+10h]
  _BYTE v68[192]; // [rsp+128h] [rbp+20h] BYREF
  int v69; // [rsp+1E8h] [rbp+E0h]
  unsigned __int16 v70; // [rsp+228h] [rbp+120h]
  void *Src; // [rsp+230h] [rbp+128h]
  _BYTE v72[200]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v73[72]; // [rsp+300h] [rbp+1F8h] BYREF
  char v74; // [rsp+348h] [rbp+240h]
  __int16 v75; // [rsp+3E0h] [rbp+2D8h]
  struct tpm12class::TPMW82B_BUFFER *v76; // [rsp+3E4h] [rbp+2DCh]
  wil::details::in1diag3 *retaddr; // [rsp+460h] [rbp+358h]
  VsmUtils *v78; // [rsp+470h] [rbp+368h] BYREF
  unsigned __int8 *v79; // [rsp+478h] [rbp+370h] BYREF

  LODWORD(v79) = (_DWORD)a3;
  v78 = a2;
  tpm12class::TPMW8_StartAuthSession::TPMW8_StartAuthSession((tpm12class::TPMW8_StartAuthSession *)v72);
  tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v73, 0x20u);
  v75 = 11;
  v74 = 3;
  v9 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v72, 0);
  v11 = VsmUtils::MapTpmError((VsmUtils *)v9, v10);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 720;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)(unsigned int)v11,
      v53);
    goto LABEL_46;
  }
  TbsHandle = (VsmUtils *)GetTbsHandle();
  LODWORD(v62) = (_DWORD)v76;
  v11 = VsmUtils::AuthorizePolicySecret(
          TbsHandle,
          (unsigned __int64)this,
          (const unsigned __int16 *)v78,
          (unsigned __int8 *)(unsigned int)v79,
          0,
          v62,
          v63[0]);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 727;
    goto LABEL_5;
  }
  v65 = &v78;
  v66 = &v79;
  v67 = 1;
  tpm12class::TPMW8_PolicyGetDigest::TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
  v69 = (int)v76;
  v15 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v68, 0);
  v17 = VsmUtils::MapTpmError((VsmUtils *)v15, v16);
  v12 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E0,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)(unsigned int)v17,
      v53);
    tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
    v19 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v18);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2DB,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v19,
        v54);
    goto LABEL_46;
  }
  if ( v70 != 32 )
  {
    v12 = -2146893819;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E2,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)0x80090005LL,
      v53);
    tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
    v21 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v20);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2DB,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v21,
        v55);
    goto LABEL_46;
  }
  v22 = a6;
  if ( a6 )
  {
    if ( (unsigned int)a7 < 0x20 )
    {
      v12 = -2146893784;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E7,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)0x80090028LL,
        v53);
      tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
      goto LABEL_40;
    }
    v24 = Src;
    *a6 = *(_OWORD *)Src;
    v22[1] = v24[1];
  }
  tpm12class::TPMW8_FlushContext::TPMW8_FlushContext((tpm12class::TPMW8_FlushContext *)v63);
  v64 = (int)v76;
  LODWORD(v76) = 0;
  v25 = tpm12class::TPMW8_FlushContext::Execute((tpm12class::TPMW8_FlushContext *)v63, 0);
  v27 = VsmUtils::MapTpmError((VsmUtils *)v25, v26);
  v12 = v27;
  if ( v27 >= 0 )
  {
    tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v73, 0x20u);
    v75 = 11;
    v74 = 3;
    v30 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v72, 0);
    v32 = VsmUtils::MapTpmError((VsmUtils *)v30, v31);
    v12 = v32;
    if ( v32 >= 0 )
    {
      v36 = VsmUtils::ExecutePolicyOr((VsmUtils *)Src, (unsigned __int8 *)v70, (unsigned int)v76, v33);
      v12 = v36;
      if ( v36 >= 0 )
      {
        v69 = (int)v76;
        v39 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v68, 0);
        v41 = VsmUtils::MapTpmError((VsmUtils *)v39, v40);
        v12 = v41;
        if ( v41 >= 0 )
        {
          v64 = (int)v76;
          LODWORD(v76) = 0;
          v44 = tpm12class::TPMW8_FlushContext::Execute((tpm12class::TPMW8_FlushContext *)v63, 0);
          v46 = VsmUtils::MapTpmError((VsmUtils *)v44, v45);
          v12 = v46;
          if ( v46 >= 0 )
          {
            if ( (unsigned int)a5 < v70 )
            {
              v12 = -2146893784;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x304,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)0x80090028LL,
                v53);
              *(_QWORD *)v63 = &tpm12class::TPMW8_FlushContext::`vftable';
              v64 = 1073741831;
              tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v63);
              tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
LABEL_40:
              v49 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v23);
              if ( v49 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x2DB,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                  (const char *)(unsigned int)v49,
                  v56);
              goto LABEL_46;
            }
            memcpy_0(a4, Src, v70);
            *(_QWORD *)v63 = &tpm12class::TPMW8_FlushContext::`vftable';
            v64 = 1073741831;
            tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v63);
            tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
            v51 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v50);
            if ( v51 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2DB,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)(unsigned int)v51,
                v53);
            v12 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x301,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)(unsigned int)v46,
              v53);
            *(_QWORD *)v63 = &tpm12class::TPMW8_FlushContext::`vftable';
            v64 = 1073741831;
            tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v63);
            tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
            v48 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v47);
            if ( v48 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2DB,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)(unsigned int)v48,
                v61);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2FD,
            (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
            (const char *)(unsigned int)v41,
            v53);
          *(_QWORD *)v63 = &tpm12class::TPMW8_FlushContext::`vftable';
          v64 = 1073741831;
          tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v63);
          tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
          v43 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v42);
          if ( v43 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2DB,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)(unsigned int)v43,
              v60);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2FA,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
          (const char *)(unsigned int)v36,
          v53);
        *(_QWORD *)v63 = &tpm12class::TPMW8_FlushContext::`vftable';
        v64 = 1073741831;
        tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v63);
        tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
        v38 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v37);
        if ( v38 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2DB,
            (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
            (const char *)(unsigned int)v38,
            v59);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F7,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v32,
        v53);
      *(_QWORD *)v63 = &tpm12class::TPMW8_FlushContext::`vftable';
      v64 = 1073741831;
      tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v63);
      tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
      v35 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v34);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2DB,
          (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
          (const char *)(unsigned int)v35,
          v58);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)(unsigned int)v27,
      v53);
    *(_QWORD *)v63 = &tpm12class::TPMW8_FlushContext::`vftable';
    v64 = 1073741831;
    tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v63);
    tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest((tpm12class::TPMW8_PolicyGetDigest *)v68);
    v29 = VsmUtils::CloseVtl1AuthBlob(v78, (unsigned __int8 *)(unsigned int)v79, v28);
    if ( v29 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2DB,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
        (const char *)(unsigned int)v29,
        v57);
  }
LABEL_46:
  tpm12class::TPMW8_StartAuthSession::~TPMW8_StartAuthSession((tpm12class::TPMW8_StartAuthSession *)v72);
  return v12;
}

```

## disassembly

```asm
0x1400575dc  mov     rax, rsp
0x1400575df  mov     [rax+8], rbx
0x1400575e3  mov     [rax+18h], r8d
0x1400575e7  mov     [rax+10h], rdx
0x1400575eb  push    rbp
0x1400575ec  push    rsi
0x1400575ed  push    rdi
0x1400575ee  push    r12
0x1400575f0  push    r15
0x1400575f2  lea     rbp, [rax-358h]
0x1400575f9  sub     rsp, 430h
0x140057600  mov     rsi, r9
0x140057603  mov     rdi, rcx
0x140057606  lea     rcx, [rbp+350h+var_220]; this
0x14005760d  call    ??0TPMW8_StartAuthSession@tpm12class@@QEAA@XZ; tpm12class::TPMW8_StartAuthSession::TPMW8_StartAuthSession(void)
0x140057612  nop
0x140057613  mov     r15d, 20h ; ' '
0x140057619  mov     edx, r15d; unsigned __int64
0x14005761c  lea     rcx, [rbp+350h+var_158]; this
0x140057623  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x140057628  lea     r12d, [r15-15h]
0x14005762c  mov     [rbp+350h+var_78], r12w
0x140057634  mov     [rbp+350h+var_110], 3
0x14005763b  xor     edx, edx; void *
0x14005763d  lea     rcx, [rbp+350h+var_220]; this
0x140057644  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x140057649  mov     ecx, eax; this
0x14005764b  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140057650  mov     ebx, eax
0x140057652  test    eax, eax
0x140057654  jns     short loc_14005765D
0x140057656  mov     edx, 2D0h
0x14005765b  jmp     short loc_140057699
0x14005765d  call    ?GetTbsHandle@@YA_KXZ; GetTbsHandle(void)
0x140057662  mov     ecx, dword ptr [rbp+350h+var_74]
0x140057668  mov     dword ptr [rsp+450h+var_428], ecx; struct tpm12class::TPMW82B_BUFFER *
0x14005766c  mov     [rsp+450h+var_430], 0; int
0x140057675  mov     r9d, dword ptr [rbp+350h+arg_10]; unsigned __int8 *
0x14005767c  mov     r8, [rbp+350h+arg_8]; unsigned __int16 *
0x140057683  mov     rdx, rdi; unsigned __int64
0x140057686  mov     rcx, rax; this
0x140057689  call    ?AuthorizePolicySecret@VsmUtils@@YAJ_KPEBGPEAEIPEAVTPMW82B_BUFFER@tpm12class@@I@Z; VsmUtils::AuthorizePolicySecret(unsigned __int64,ushort const *,uchar *,uint,tpm12class::TPMW82B_BUFFER *,uint)
0x14005768e  mov     ebx, eax
0x140057690  test    eax, eax
0x140057692  jns     short loc_1400576B4
0x140057694  mov     edx, 2D7h; void *
0x140057699  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400576a0  mov     r9d, eax; char *
0x1400576a3  mov     rcx, [rbp+358h]; this
0x1400576aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400576af  jmp     loc_140057C66
0x1400576b4  lea     rax, [rbp+350h+arg_8]
0x1400576bb  mov     [rbp+350h+var_350], rax
0x1400576bf  lea     rax, [rbp+350h+arg_10]
0x1400576c6  mov     [rbp+350h+var_348], rax
0x1400576ca  mov     [rbp+350h+var_340], 1
0x1400576ce  lea     rcx, [rbp+350h+var_330]; this
0x1400576d2  call    ??0TPMW8_PolicyGetDigest@tpm12class@@QEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::TPMW8_PolicyGetDigest(void)
0x1400576d7  nop
0x1400576d8  mov     eax, dword ptr [rbp+350h+var_74]
0x1400576de  mov     [rbp+350h+var_270], eax
0x1400576e4  xor     edx, edx; void *
0x1400576e6  lea     rcx, [rbp+350h+var_330]; this
0x1400576ea  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1400576ef  mov     ecx, eax; this
0x1400576f1  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x1400576f6  mov     ebx, eax
0x1400576f8  test    eax, eax
0x1400576fa  jns     short loc_140057759
0x1400576fc  mov     rcx, [rbp+358h]; this
0x140057703  mov     r9d, eax; char *
0x140057706  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005770d  mov     edx, 2E0h; void *
0x140057712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057717  nop
0x140057718  lea     rcx, [rbp+350h+var_330]; this
0x14005771c  call    ??1TPMW8_PolicyGetDigest@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest(void)
0x140057721  nop
0x140057722  mov     edx, dword ptr [rbp+350h+arg_10]; unsigned __int8 *
0x140057728  mov     rcx, [rbp+350h+arg_8]; this
0x14005772f  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x140057734  mov     rcx, [rbp+358h]; this
0x14005773b  test    eax, eax
0x14005773d  jns     short loc_140057754
0x14005773f  mov     r9d, eax; char *
0x140057742  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057749  mov     edx, 2DBh; void *
0x14005774e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140057753  nop
0x140057754  jmp     loc_140057C66
0x140057759  cmp     r15w, [rbp+350h+var_230]
0x140057761  jz      short loc_1400577C5
0x140057763  mov     rcx, [rbp+358h]; this
0x14005776a  mov     ebx, 80090005h
0x14005776f  mov     r9d, ebx; char *
0x140057772  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057779  mov     edx, 2E2h; void *
0x14005777e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057783  nop
0x140057784  lea     rcx, [rbp+350h+var_330]; this
0x140057788  call    ??1TPMW8_PolicyGetDigest@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest(void)
0x14005778d  nop
0x14005778e  mov     edx, dword ptr [rbp+350h+arg_10]; unsigned __int8 *
0x140057794  mov     rcx, [rbp+350h+arg_8]; this
0x14005779b  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x1400577a0  mov     rcx, [rbp+358h]; this
0x1400577a7  test    eax, eax
0x1400577a9  jns     short loc_1400577C0
0x1400577ab  mov     r9d, eax; char *
0x1400577ae  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400577b5  mov     edx, 2DBh; void *
0x1400577ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400577bf  nop
0x1400577c0  jmp     loc_140057C66
0x1400577c5  mov     rcx, [rbp+350h+arg_28]
0x1400577cc  test    rcx, rcx
0x1400577cf  jz      short loc_14005781F
0x1400577d1  cmp     dword ptr [rbp+350h+arg_30], r15d
0x1400577d8  jnb     short loc_14005780A
0x1400577da  mov     rcx, [rbp+358h]; this
0x1400577e1  mov     ebx, 80090028h
0x1400577e6  mov     r9d, ebx; char *
0x1400577e9  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400577f0  mov     edx, 2E7h; void *
0x1400577f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400577fa  nop
0x1400577fb  lea     rcx, [rbp+350h+var_330]; this
0x1400577ff  call    ??1TPMW8_PolicyGetDigest@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest(void)
0x140057804  nop
0x140057805  jmp     loc_140057BBE
0x14005780a  mov     rax, [rbp+350h+Src]
0x140057811  movups  xmm0, xmmword ptr [rax]
0x140057814  movups  xmmword ptr [rcx], xmm0
0x140057817  movups  xmm1, xmmword ptr [rax+10h]
0x14005781b  movups  xmmword ptr [rcx+10h], xmm1
0x14005781f  lea     rcx, [rsp+450h+var_420]; this
0x140057824  call    ??0TPMW8_FlushContext@tpm12class@@QEAA@XZ; tpm12class::TPMW8_FlushContext::TPMW8_FlushContext(void)
0x140057829  nop
0x14005782a  mov     eax, dword ptr [rbp+350h+var_74]
0x140057830  mov     [rbp+350h+var_360], eax
0x140057833  mov     dword ptr [rbp+350h+var_74], 0
0x14005783d  xor     edx, edx; void *
0x14005783f  lea     rcx, [rsp+450h+var_420]; this
0x140057844  call    ?Execute@TPMW8_FlushContext@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_FlushContext::Execute(void *)
0x140057849  mov     ecx, eax; this
0x14005784b  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140057850  mov     ebx, eax
0x140057852  test    eax, eax
0x140057854  jns     short loc_1400578D1
0x140057856  mov     rcx, [rbp+358h]; this
0x14005785d  mov     r9d, eax; char *
0x140057860  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057867  mov     edx, 2F2h; void *
0x14005786c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057871  nop
0x140057872  lea     rax, ??_7TPMW8_FlushContext@tpm12class@@6B@; const tpm12class::TPMW8_FlushContext::`vftable'
0x140057879  mov     qword ptr [rsp+450h+var_420], rax
0x14005787e  mov     [rbp+350h+var_360], 40000007h
0x140057885  lea     rcx, [rsp+450h+var_420]; this
0x14005788a  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x14005788f  nop
0x140057890  lea     rcx, [rbp+350h+var_330]; this
0x140057894  call    ??1TPMW8_PolicyGetDigest@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest(void)
0x140057899  nop
0x14005789a  mov     edx, dword ptr [rbp+350h+arg_10]; unsigned __int8 *
0x1400578a0  mov     rcx, [rbp+350h+arg_8]; this
0x1400578a7  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x1400578ac  mov     rcx, [rbp+358h]; this
0x1400578b3  test    eax, eax
0x1400578b5  jns     short loc_1400578CC
0x1400578b7  mov     r9d, eax; char *
0x1400578ba  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400578c1  mov     edx, 2DBh; void *
0x1400578c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400578cb  nop
0x1400578cc  jmp     loc_140057C66
0x1400578d1  mov     rdx, r15; unsigned __int64
0x1400578d4  lea     rcx, [rbp+350h+var_158]; this
0x1400578db  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x1400578e0  mov     [rbp+350h+var_78], r12w
0x1400578e8  mov     [rbp+350h+var_110], 3
0x1400578ef  xor     edx, edx; void *
0x1400578f1  lea     rcx, [rbp+350h+var_220]; this
0x1400578f8  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1400578fd  mov     ecx, eax; this
0x1400578ff  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140057904  mov     ebx, eax
0x140057906  test    eax, eax
0x140057908  jns     short loc_140057985
0x14005790a  mov     rcx, [rbp+358h]; this
0x140057911  mov     r9d, eax; char *
0x140057914  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005791b  mov     edx, 2F7h; void *
0x140057920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057925  nop
0x140057926  lea     rax, ??_7TPMW8_FlushContext@tpm12class@@6B@; const tpm12class::TPMW8_FlushContext::`vftable'
0x14005792d  mov     qword ptr [rsp+450h+var_420], rax
0x140057932  mov     [rbp+350h+var_360], 40000007h
0x140057939  lea     rcx, [rsp+450h+var_420]; this
0x14005793e  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x140057943  nop
0x140057944  lea     rcx, [rbp+350h+var_330]; this
0x140057948  call    ??1TPMW8_PolicyGetDigest@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest(void)
0x14005794d  nop
0x14005794e  mov     edx, dword ptr [rbp+350h+arg_10]; unsigned __int8 *
0x140057954  mov     rcx, [rbp+350h+arg_8]; this
0x14005795b  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x140057960  mov     rcx, [rbp+358h]; this
0x140057967  test    eax, eax
0x140057969  jns     short loc_140057980
0x14005796b  mov     r9d, eax; char *
0x14005796e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057975  mov     edx, 2DBh; void *
0x14005797a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005797f  nop
0x140057980  jmp     loc_140057C66
0x140057985  movzx   edx, [rbp+350h+var_230]; unsigned __int8 *
0x14005798c  mov     r8d, dword ptr [rbp+350h+var_74]; unsigned int
0x140057993  mov     rcx, [rbp+350h+Src]; this
0x14005799a  call    ?ExecutePolicyOr@VsmUtils@@YAJPEAEII@Z; VsmUtils::ExecutePolicyOr(uchar *,uint,uint)
0x14005799f  mov     ebx, eax
0x1400579a1  test    eax, eax
0x1400579a3  jns     short loc_140057A20
0x1400579a5  mov     rcx, [rbp+358h]; this
0x1400579ac  mov     r9d, eax; char *
0x1400579af  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400579b6  mov     edx, 2FAh; void *
0x1400579bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400579c0  nop
0x1400579c1  lea     rax, ??_7TPMW8_FlushContext@tpm12class@@6B@; const tpm12class::TPMW8_FlushContext::`vftable'
0x1400579c8  mov     qword ptr [rsp+450h+var_420], rax
0x1400579cd  mov     [rbp+350h+var_360], 40000007h
0x1400579d4  lea     rcx, [rsp+450h+var_420]; this
0x1400579d9  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x1400579de  nop
0x1400579df  lea     rcx, [rbp+350h+var_330]; this
0x1400579e3  call    ??1TPMW8_PolicyGetDigest@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest(void)
0x1400579e8  nop
0x1400579e9  mov     edx, dword ptr [rbp+350h+arg_10]; unsigned __int8 *
0x1400579ef  mov     rcx, [rbp+350h+arg_8]; this
0x1400579f6  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x1400579fb  mov     rcx, [rbp+358h]; this
0x140057a02  test    eax, eax
0x140057a04  jns     short loc_140057A1B
0x140057a06  mov     r9d, eax; char *
0x140057a09  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057a10  mov     edx, 2DBh; void *
0x140057a15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140057a1a  nop
0x140057a1b  jmp     loc_140057C66
0x140057a20  mov     eax, dword ptr [rbp+350h+var_74]
0x140057a26  mov     [rbp+350h+var_270], eax
0x140057a2c  xor     edx, edx; void *
0x140057a2e  lea     rcx, [rbp+350h+var_330]; this
0x140057a32  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x140057a37  mov     ecx, eax; this
0x140057a39  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140057a3e  mov     ebx, eax
0x140057a40  test    eax, eax
0x140057a42  jns     short loc_140057ABF
0x140057a44  mov     rcx, [rbp+358h]; this
0x140057a4b  mov     r9d, eax; char *
0x140057a4e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057a55  mov     edx, 2FDh; void *
0x140057a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057a5f  nop
0x140057a60  lea     rax, ??_7TPMW8_FlushContext@tpm12class@@6B@; const tpm12class::TPMW8_FlushContext::`vftable'
0x140057a67  mov     qword ptr [rsp+450h+var_420], rax
0x140057a6c  mov     [rbp+350h+var_360], 40000007h
0x140057a73  lea     rcx, [rsp+450h+var_420]; this
0x140057a78  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x140057a7d  nop
0x140057a7e  lea     rcx, [rbp+350h+var_330]; this
0x140057a82  call    ??1TPMW8_PolicyGetDigest@tpm12class@@UEAA@XZ; tpm12class::TPMW8_PolicyGetDigest::~TPMW8_PolicyGetDigest(void)
0x140057a87  nop
0x140057a88  mov     edx, dword ptr [rbp+350h+arg_10]; unsigned __int8 *
0x140057a8e  mov     rcx, [rbp+350h+arg_8]; this
0x140057a95  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x140057a9a  mov     rcx, [rbp+358h]; this
0x140057aa1  test    eax, eax
0x140057aa3  jns     short loc_140057ABA
0x140057aa5  mov     r9d, eax; char *
0x140057aa8  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057aaf  mov     edx, 2DBh; void *
0x140057ab4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140057ab9  nop
0x140057aba  jmp     loc_140057C66
0x140057abf  mov     eax, dword ptr [rbp+350h+var_74]
0x140057ac5  mov     [rbp+350h+var_360], eax
0x140057ac8  mov     dword ptr [rbp+350h+var_74], 0
0x140057ad2  xor     edx, edx; void *
0x140057ad4  lea     rcx, [rsp+450h+var_420]; this
0x140057ad9  call    ?Execute@TPMW8_FlushContext@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_FlushContext::Execute(void *)
0x140057ade  mov     ecx, eax; this
0x140057ae0  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x140057ae5  mov     ebx, eax
0x140057ae7  test    eax, eax
0x140057ae9  jns     short loc_140057B66
0x140057aeb  mov     rcx, [rbp+358h]; this
0x140057af2  mov     r9d, eax; char *
  ... truncated ...
```
