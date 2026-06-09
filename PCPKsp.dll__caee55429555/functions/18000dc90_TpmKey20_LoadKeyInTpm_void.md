# TpmKey20::LoadKeyInTpm(void)

- ea: `0x18000dc90`
- end: `0x18000e8e8`
- name: `?LoadKeyInTpm@TpmKey20@@IEAAJXZ`
- size: `3160`
- prototype: `__int64 __fastcall(TpmKey20 *__hidden this)`
- caller_count: `25`
- callee_count: `27`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180014bd0`
- `0x180026e30`
- `0x180027210`
- `0x180027670`
- `0x180029700`
- `0x18002a820`
- `0x18002e900`
- `0x1800357ec`
- `0x1800404e0`
- `0x180047d50`
- `0x180054fb8`
- `0x180056980`
- `0x180066020`
- `0x18006e370`
- `0x18006f6f0`
- `0x180087f30`
- `0x180088280`
- `0x180089590`
- `0x18008adcc`
- `0x18008b0b0`
- `0x18008b5bc`
- `0x18008cd00`
- `0x18008e850`
- `0x18008f560`
- `0x18008fa70`

## callees

- `0x18000c398`
- `0x18000d440`
- `0x18000dc90`
- `0x18000e970`
- `0x18000f000`
- `0x18000f880`
- `0x180010c90`
- `0x1800133c4`
- `0x180014830`
- `0x180014a60`
- `0x1800157c0`
- `0x1800293e0`
- `0x1800294d4`
- `0x180029a20`
- `0x180032110`
- `0x18003335c`
- `0x1800334a0`
- `0x180034464`
- `0x180035540`
- `0x180043260`
- `0x18006a7f0`
- `0x1800768a0`
- `0x1800769e0`
- `0x180076e70`
- `0x180077034`
- `0x18007704c`
- `0x1800c8010`

## string_xrefs

- `0x18000e463`: `CantLoadReadParentError`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TpmKey20::LoadKeyInTpm(TpmKey20 *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  tpm12class::TPMW8_SESSION *v4; // rax
  struct tpm12class::TPMW8_SESSION *v5; // rax
  tpm12class::TPMW8T_PUBLIC *v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  size_t v9; // r14
  const void *v10; // rsi
  int v11; // ebx
  __int64 v12; // rbx
  int v13; // eax
  size_t v14; // r15
  void *v15; // r12
  __int64 v16; // rax
  void *v17; // rcx
  void *v18; // rax
  size_t v20; // rcx
  char *i; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  _BYTE *j; // rax
  unsigned int v25; // edi
  unsigned __int8 *v26; // rdx
  unsigned __int8 *v27; // rax
  unsigned int v28; // edi
  unsigned __int8 *v29; // rdx
  int v30; // eax
  unsigned int v31; // edi
  unsigned __int8 *v32; // rdx
  int v33; // eax
  int v34; // eax
  unsigned int v35; // edi
  KspFlowLogger *v36; // rcx
  wil::details::in1diag3 *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  void *v40; // rdi
  void *v41; // rdi
  int PrimaryAuthSession; // eax
  __int64 v43; // rbx
  int v44; // eax
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  const struct std::nothrow_t *v48; // rdx
  int v49; // eax
  int v50; // eax
  const struct std::nothrow_t *v51; // rdx
  int v52; // eax
  const struct std::nothrow_t *v53; // rdx
  int v54; // [rsp+20h] [rbp-E0h]
  int *v55[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v56[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  char v60; // [rsp+80h] [rbp-80h]
  int v61; // [rsp+88h] [rbp-78h]
  __int64 v62; // [rsp+8Ch] [rbp-74h]
  __int64 v63; // [rsp+94h] [rbp-6Ch]
  __int64 v64; // [rsp+9Ch] [rbp-64h]
  int v65; // [rsp+A4h] [rbp-5Ch]
  const int *v66; // [rsp+A8h] [rbp-58h]
  __int64 v67; // [rsp+B0h] [rbp-50h]
  __int64 v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+C0h] [rbp-40h]
  __int64 v70; // [rsp+C8h] [rbp-38h]
  __int64 v71; // [rsp+D0h] [rbp-30h]
  char v72; // [rsp+D8h] [rbp-28h]
  __int16 v73; // [rsp+E0h] [rbp-20h]
  __int64 v74; // [rsp+E8h] [rbp-18h]
  __int64 v75; // [rsp+F0h] [rbp-10h]
  struct tpm12class::TPMW8_SESSION *v76; // [rsp+F8h] [rbp-8h]
  __int128 v77; // [rsp+100h] [rbp+0h]
  int v78; // [rsp+114h] [rbp+14h] BYREF
  _QWORD v79[3]; // [rsp+118h] [rbp+18h] BYREF
  int v80; // [rsp+130h] [rbp+30h]
  __int64 v81; // [rsp+138h] [rbp+38h]
  __int64 v82; // [rsp+140h] [rbp+40h]
  char v83; // [rsp+148h] [rbp+48h]
  __int16 v84; // [rsp+150h] [rbp+50h]
  __int64 v85; // [rsp+158h] [rbp+58h]
  _QWORD v86[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v87; // [rsp+170h] [rbp+70h]
  int v88; // [rsp+178h] [rbp+78h]
  __int64 v89; // [rsp+180h] [rbp+80h]
  __int64 v90; // [rsp+188h] [rbp+88h]
  char v91; // [rsp+190h] [rbp+90h]
  unsigned __int16 v92; // [rsp+198h] [rbp+98h]
  void *Block; // [rsp+1A0h] [rbp+A0h]
  __int64 v94; // [rsp+1A8h] [rbp+A8h]
  int v95; // [rsp+1B0h] [rbp+B0h]
  _QWORD v96[3]; // [rsp+1B8h] [rbp+B8h] BYREF
  int v97; // [rsp+1D0h] [rbp+D0h]
  __int64 v98; // [rsp+1D8h] [rbp+D8h]
  __int64 v99; // [rsp+1E0h] [rbp+E0h]
  char v100; // [rsp+1E8h] [rbp+E8h]
  unsigned __int16 v101; // [rsp+1F0h] [rbp+F0h]
  void *Src; // [rsp+1F8h] [rbp+F8h]
  int v103; // [rsp+208h] [rbp+108h]
  __int64 v104; // [rsp+210h] [rbp+110h]
  tpm12class::TpmDataObject *v105; // [rsp+218h] [rbp+118h]
  _BYTE v106[72]; // [rsp+220h] [rbp+120h] BYREF
  tpm12class::TpmDataObject *v107; // [rsp+268h] [rbp+168h]
  _BYTE v108[128]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]
  unsigned __int8 *v110; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int8 *v111; // [rsp+308h] [rbp+208h] BYREF

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v55, L"TpmKey20::LoadKeyInTpm", 1);
  if ( *((_DWORD *)this + 116) )
  {
    v2 = TpmKey20::ValidateTpmKeyHandle(this);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E1,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v2,
        v54);
      KspFunctionLogger::~KspFunctionLogger(v55);
      return v3;
    }
    if ( *((_DWORD *)this + 116) )
      goto LABEL_31;
  }
  if ( !*((_QWORD *)this + 12) )
  {
    if ( *((_QWORD *)this + 81) )
    {
      KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "ImportingSoftwareKey", 0, 0);
      *((_BYTE *)this + 81) = 0;
      v34 = (*(__int64 (__fastcall **)(TpmKey20 *))(*(_QWORD *)this + 1224LL))(this);
      v35 = v34;
      v36 = (TpmKey20 *)((char *)this + 56);
      if ( v34 < 0 )
      {
        KspFlowLogger::LogTransition(v36, "FailedToImportSoftwareKey", 255, v34);
        *((_BYTE *)this + 81) = 1;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F3,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
          (const char *)v35,
          v54);
        KspFunctionLogger::~KspFunctionLogger(v55);
        return v35;
      }
      KspFlowLogger::LogTransition(v36, "ImportedSoftwareKey", 0, 0);
      *((_BYTE *)this + 81) = 0;
    }
    if ( !*((_QWORD *)this + 12) )
    {
      KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "CantLoadNoPublicKey", 255, -2146893779);
      *((_BYTE *)this + 81) = 1;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7FD,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)0x8009002DLL,
        v54);
      KspFunctionLogger::~KspFunctionLogger(v55);
      return 2148073517LL;
    }
  }
  if ( *((_DWORD *)this + 121) )
  {
    KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "CantLoadHandleInvalidated", 255, -2144795614);
    *((_BYTE *)this + 81) = 1;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x807,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
      (const char *)0x80290422LL,
      v54);
    KspFunctionLogger::~KspFunctionLogger(v55);
    return 2150171682LL;
  }
  if ( !*((_QWORD *)this + 11) )
  {
    v56[1] = 0;
    v56[2] = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v66 = &tpm12class::TPMW82B_BUFFER::`vftable';
    v73 = 0;
    v74 = 0;
    v76 = 0;
    v77 = 0;
    v62 = 0;
    v61 = -2147450878;
    v75 = 343;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v56[0] = &tpm12class::TPMW8_Load::`vftable';
    v79[1] = 0;
    v79[2] = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v79[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
    v84 = 0;
    v85 = 0;
    v86[1] = 0;
    v87 = 0;
    v88 = 0;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v86[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
    v92 = 0;
    Block = 0;
    v96[1] = 0;
    v96[2] = 0;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v100 = 0;
    v96[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
    v101 = 0;
    Src = 0;
    v94 = 0;
    v78 = 1073741831;
    v95 = 1073741831;
    v4 = (tpm12class::TPMW8_SESSION *)operator new(0x318u);
    v5 = (struct tpm12class::TPMW8_SESSION *)tpm12class::TPMW8_SESSION::TPMW8_SESSION(v4, 0);
    v76 = v5;
    if ( v5 )
    {
      if ( v94 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 32LL))(v94, 1);
        v94 = 0;
      }
      v6 = (tpm12class::TPMW8T_PUBLIC *)operator new(0x340u);
      v94 = tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(v6);
      v5 = v76;
    }
    *((_WORD *)v5 + 381) = 11;
    v7 = (*(__int64 (__fastcall **)(TpmKey20 *, int *, _QWORD *, _QWORD))(*(_QWORD *)this + 1256LL))(this, &v78, v79, 0);
    v8 = v7;
    if ( v7 < 0 )
    {
      KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "CantLoadReadParentError", 255, v7);
      *((_BYTE *)this + 81) = 1;
      v37 = retaddr;
      v38 = 2069;
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        v37,
        (void *)v38,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)v8,
        v54);
      tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v56);
LABEL_62:
      KspFunctionLogger::~KspFunctionLogger(v55);
      return v8;
    }
    if ( this == (TpmKey20 *)-104LL )
    {
      v11 = -2147024809;
      goto LABEL_64;
    }
    v9 = *((unsigned __int16 *)this + 80);
    v10 = (const void *)*((_QWORD *)this + 21);
    if ( Block )
    {
      if ( v9 <= v92 )
      {
        v20 = v92 - v9;
        for ( i = (char *)Block + v9; v20; --v20 )
          *i++ = 0;
        v92 = v9;
        goto LABEL_20;
      }
      v40 = operator new(*((unsigned __int16 *)this + 80));
      memset_0(v40, 0, v9);
      memcpy_0(v40, Block, v92);
      v11 = tpm12class::TPMW82B_BUFFER::Empty((tpm12class::TPMW82B_BUFFER *)v86);
      if ( v11 < 0 )
        goto LABEL_19;
      Block = v40;
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(v86[0] + 24LL))(v86, 0);
      if ( v11 < 0 )
        goto LABEL_19;
      if ( Block )
      {
        operator delete(Block);
        Block = 0;
      }
      Block = operator new(v9);
      memset_0(Block, 0, v9);
    }
    v92 = v9;
LABEL_19:
    if ( v11 >= 0 )
    {
LABEL_20:
      memcpy_0(Block, v10, v92);
      v12 = v94;
      v94 = *((_QWORD *)this + 12);
      v13 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v56, 0);
      v8 = v13;
      v94 = v12;
      if ( v13 >= 0 )
      {
        v14 = v101;
        v15 = Src;
        v16 = *((_QWORD *)this + 48);
        if ( v16 )
        {
          v22 = *((unsigned __int16 *)this + 188);
          if ( v101 <= v22 )
          {
            v23 = v22 - v101;
            for ( j = (_BYTE *)(v101 + v16); v23; --v23 )
              *j++ = 0;
            *((_WORD *)this + 188) = v14;
            goto LABEL_28;
          }
          v41 = operator new(v101);
          memset_0(v41, 0, v14);
          memcpy_0(v41, *((const void **)this + 48), *((unsigned __int16 *)this + 188));
          v11 = tpm12class::TPMW82B_BUFFER::Empty((TpmKey20 *)((char *)this + 320));
          if ( v11 < 0 )
            goto LABEL_27;
          *((_QWORD *)this + 48) = v41;
        }
        else
        {
          v11 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 40) + 24LL))((char *)this + 320, 0);
          if ( v11 < 0 )
          {
LABEL_27:
            if ( v11 >= 0 )
            {
LABEL_28:
              memcpy_0(*((void **)this + 48), v15, *((unsigned __int16 *)this + 188));
              *((_DWORD *)this + 116) = v95;
              v56[0] = &tpm12class::TPMW8_Load::`vftable';
              v78 = 1073741831;
              v95 = 1073741831;
              if ( v94 )
              {
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 32LL))(v94, 1);
                v94 = 0;
              }
              tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v96);
              tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v86);
              tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v79);
              tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND((tpm12class::TPMW8_COMMAND *)v56);
              goto LABEL_31;
            }
            v39 = 2089;
            goto LABEL_68;
          }
          v17 = (void *)*((_QWORD *)this + 48);
          if ( v17 )
          {
            operator delete(v17);
            *((_QWORD *)this + 48) = 0;
          }
          v18 = operator new(v14);
          *((_QWORD *)this + 48) = v18;
          memset_0(v18, 0, v14);
        }
        *((_WORD *)this + 188) = v14;
        goto LABEL_27;
      }
      KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "LoadKeyError", 255, v13);
      *((_BYTE *)this + 81) = 1;
      v37 = retaddr;
      if ( v8 == -2144862207 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x825,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
          (const char *)0x80090010LL,
          v54);
        tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v56);
        KspFunctionLogger::~KspFunctionLogger(v55);
        return 2148073488LL;
      }
      v38 = 2086;
      goto LABEL_60;
    }
LABEL_64:
    v39 = 2072;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
      (const char *)(unsigned int)v11,
      v54);
    tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v56);
    goto LABEL_70;
  }
  tpm12class::TPMW8_CreatePrimary::TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
  LODWORD(v79[0]) = 1073741825;
  PrimaryAuthSession = GetPrimaryAuthSession(v76, 0x40000001u);
  v11 = PrimaryAuthSession;
  if ( PrimaryAuthSession < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x834,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
      (const char *)(unsigned int)PrimaryAuthSession,
      v54);
    tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
    goto LABEL_70;
  }
  v43 = v87;
  v87 = *((_QWORD *)this + 11);
  v44 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v56, 0);
  v8 = v44;
  v87 = v43;
  if ( v44 != -2144862207 )
  {
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83F,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v44,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      goto LABEL_62;
    }
    v45 = tpm12class::TPMW82B_BUFFER::CopyFrom(
            (TpmKey20 *)((char *)this + 320),
            (const struct tpm12class::TPMW82B_BUFFER *)v108);
    v11 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x841,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v45,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      goto LABEL_70;
    }
    v46 = *((_QWORD *)this + 12);
    if ( v46 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 32LL))(v46, 1);
    *((_QWORD *)this + 12) = 0;
    wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(&v110, v104);
    v27 = v110;
    if ( !v110 )
    {
      wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(&v110, 0);
      goto LABEL_42;
    }
    v110 = 0;
    *((_QWORD *)this + 12) = v27;
    wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(&v110, 0);
    *((_DWORD *)this + 116) = v103;
    LODWORD(v110) = 0;
    v47 = tpm12class::TpmDataObject::Get(v105, 0, 0, (unsigned int *)&v110);
    v11 = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84E,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v47,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      goto LABEL_70;
    }
    *((_DWORD *)this + 198) = 0;
    operator delete(*((void **)this + 98), v48);
    *((_QWORD *)this + 98) = 0;
    v25 = (unsigned int)v110;
    wil::make_unique_nothrow<unsigned char [0]>(&v111, (unsigned int)v110);
    v26 = v111;
    if ( !v111 )
      goto LABEL_42;
    *((_QWORD *)this + 98) = v111;
    *((_DWORD *)this + 198) = v25;
    v49 = tpm12class::TpmDataObject::Get(v105, v26, v25, (unsigned int *)this + 198);
    v11 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x854,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v49,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      goto LABEL_70;
    }
    v50 = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v106, 0, 0, (unsigned int *)&v110);
    v11 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x858,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v50,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      goto LABEL_70;
    }
    *((_DWORD *)this + 202) = 0;
    operator delete(*((void **)this + 100), v51);
    *((_QWORD *)this + 100) = 0;
    v28 = (unsigned int)v110;
    wil::make_unique_nothrow<unsigned char [0]>(&v111, (unsigned int)v110);
    v29 = v111;
    if ( !v111 )
      goto LABEL_42;
    *((_QWORD *)this + 100) = v111;
    *((_DWORD *)this + 202) = v28;
    v30 = tpm12class::TpmDataObject::Get((tpm12class::TpmDataObject *)v106, v29, v28, (unsigned int *)this + 202);
    v11 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85E,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v30,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
LABEL_70:
      KspFunctionLogger::~KspFunctionLogger(v55);
      return (unsigned int)v11;
    }
    v52 = tpm12class::TpmDataObject::Get(v107, 0, 0, (unsigned int *)&v110);
    v11 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x862,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v52,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      goto LABEL_70;
    }
    *((_DWORD *)this + 206) = 0;
    operator delete(*((void **)this + 102), v53);
    *((_QWORD *)this + 102) = 0;
    v31 = (unsigned int)v110;
    wil::make_unique_nothrow<unsigned char [0]>(&v110, (unsigned int)v110);
    v32 = v110;
    if ( !v110 )
    {
LABEL_42:
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      KspFunctionLogger::~KspFunctionLogger(v55);
      return 2147942408LL;
    }
    *((_QWORD *)this + 102) = v110;
    *((_DWORD *)this + 206) = v31;
    v33 = tpm12class::TpmDataObject::Get(v107, v32, v31, (unsigned int *)this + 206);
    v11 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x868,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)(unsigned int)v33,
        v54);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
      goto LABEL_70;
    }
    tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
LABEL_31:
    KspFunctionLogger::~KspFunctionLogger(v55);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x83E,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
    (const char *)0x80090010LL,
    v54);
  tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v56);
  KspFunctionLogger::~KspFunctionLogger(v55);
  return 2148073488LL;
}

```

## disassembly

```asm
0x18000dc90  mov     [rsp-8+arg_10], rbx
0x18000dc95  push    rbp
0x18000dc96  push    rsi
0x18000dc97  push    rdi
0x18000dc98  push    r12
0x18000dc9a  push    r13
0x18000dc9c  push    r14
0x18000dc9e  push    r15
0x18000dca0  lea     rbp, [rsp-1C0h]
0x18000dca8  sub     rsp, 2C0h
0x18000dcaf  mov     r13, rcx
0x18000dcb2  mov     r8b, 1; bool
0x18000dcb5  lea     rdx, aTpmkey20Loadke; "TpmKey20::LoadKeyInTpm"
0x18000dcbc  lea     rcx, [rsp+2F0h+var_2C0]; this
0x18000dcc1  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18000dcc6  nop
0x18000dcc7  cmp     dword ptr [r13+1D0h], 0
0x18000dccf  jz      short loc_18000DCF1
0x18000dcd1  mov     rcx, r13; this
0x18000dcd4  call    ?ValidateTpmKeyHandle@TpmKey20@@IEAAJXZ; TpmKey20::ValidateTpmKeyHandle(void)
0x18000dcd9  mov     ebx, eax
0x18000dcdb  test    eax, eax
0x18000dcdd  js      loc_18000E0AC
0x18000dce3  cmp     dword ptr [r13+1D0h], 0
0x18000dceb  jnz     loc_18000E084
0x18000dcf1  cmp     qword ptr [r13+60h], 0
0x18000dcf6  jz      loc_18000E2F2
0x18000dcfc  cmp     dword ptr [r13+1E4h], 0
0x18000dd04  jnz     loc_18000E3EF
0x18000dd0a  cmp     qword ptr [r13+58h], 0
0x18000dd0f  jnz     loc_18000E665
0x18000dd15  xor     r15d, r15d
0x18000dd18  mov     [rsp+2F0h+var_298], r15
0x18000dd1d  mov     [rsp+2F0h+var_290], r15
0x18000dd22  mov     [rsp+2F0h+var_288], r15d
0x18000dd27  mov     [rsp+2F0h+var_280], r15
0x18000dd2c  mov     [rsp+2F0h+var_278], r15
0x18000dd31  mov     [rbp+1F0h+var_270], r15b
0x18000dd35  mov     [rbp+1F0h+var_240], r15
0x18000dd39  mov     [rbp+1F0h+var_238], r15
0x18000dd3d  mov     [rbp+1F0h+var_230], r15d
0x18000dd41  mov     [rbp+1F0h+var_228], r15
0x18000dd45  mov     [rbp+1F0h+var_220], r15
0x18000dd49  mov     [rbp+1F0h+var_218], r15b
0x18000dd4d  lea     rcx, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x18000dd54  mov     [rbp+1F0h+var_248], rcx
0x18000dd58  mov     [rbp+1F0h+var_210], r15w
0x18000dd5d  mov     [rbp+1F0h+var_208], r15
0x18000dd61  mov     [rbp+1F0h+var_1F8], r15
0x18000dd65  xorps   xmm0, xmm0
0x18000dd68  movdqa  [rbp+1F0h+var_1F0], xmm0
0x18000dd6d  mov     [rbp+1F0h+var_264], r15
0x18000dd71  mov     [rbp+1F0h+var_268], 80008002h
0x18000dd78  mov     [rbp+1F0h+var_200], 157h
0x18000dd80  mov     [rbp+1F0h+var_25C], r15
0x18000dd84  mov     [rbp+1F0h+var_254], r15
0x18000dd88  mov     [rbp+1F0h+var_24C], r15d
0x18000dd8c  lea     rax, ??_7TPMW8_Load@tpm12class@@6B@; const tpm12class::TPMW8_Load::`vftable'
0x18000dd93  mov     [rsp+2F0h+var_2A0], rax
0x18000dd98  mov     [rbp+1F0h+var_1D0], r15
0x18000dd9c  mov     [rbp+1F0h+var_1C8], r15
0x18000dda0  mov     [rbp+1F0h+var_1C0], r15d
0x18000dda4  mov     [rbp+1F0h+var_1B8], r15
0x18000dda8  mov     [rbp+1F0h+var_1B0], r15
0x18000ddac  mov     [rbp+1F0h+var_1A8], r15b
0x18000ddb0  mov     [rbp+1F0h+var_1D8], rcx
0x18000ddb4  mov     [rbp+1F0h+var_1A0], r15w
0x18000ddb9  mov     [rbp+1F0h+var_198], r15
0x18000ddbd  mov     [rbp+1F0h+var_188], r15
0x18000ddc1  mov     [rbp+1F0h+var_180], r15
0x18000ddc5  mov     [rbp+1F0h+var_178], r15d
0x18000ddc9  mov     [rbp+1F0h+var_170], r15
0x18000ddd0  mov     [rbp+1F0h+var_168], r15
0x18000ddd7  mov     [rbp+1F0h+var_160], r15b
0x18000ddde  mov     [rbp+1F0h+var_190], rcx
0x18000dde2  mov     [rbp+1F0h+var_158], r15w
0x18000ddea  mov     [rbp+1F0h+Block], r15
0x18000ddf1  mov     [rbp+1F0h+var_130], r15
0x18000ddf8  mov     [rbp+1F0h+var_128], r15
0x18000ddff  mov     [rbp+1F0h+var_120], r15d
0x18000de06  mov     [rbp+1F0h+var_118], r15
0x18000de0d  mov     [rbp+1F0h+var_110], r15
0x18000de14  mov     [rbp+1F0h+var_108], r15b
0x18000de1b  mov     [rbp+1F0h+var_138], rcx
0x18000de22  mov     [rbp+1F0h+var_100], r15w
0x18000de2a  mov     [rbp+1F0h+Src], r15
0x18000de31  mov     [rbp+1F0h+var_148], r15
0x18000de38  mov     [rbp+1F0h+var_1DC], 40000007h
0x18000de3f  mov     [rbp+1F0h+var_140], 40000007h
0x18000de49  mov     ecx, 318h; Size
0x18000de4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000de53  xor     edx, edx; struct tpm12class::TPMW8_AUTH_PROVIDER *
0x18000de55  mov     rcx, rax; this
0x18000de58  call    ??0TPMW8_SESSION@tpm12class@@QEAA@PEAVTPMW8_AUTH_PROVIDER@1@@Z; tpm12class::TPMW8_SESSION::TPMW8_SESSION(tpm12class::TPMW8_AUTH_PROVIDER *)
0x18000de5d  mov     [rbp+1F0h+var_1F8], rax
0x18000de61  test    rax, rax
0x18000de64  jz      short loc_18000DE93
0x18000de66  mov     rcx, [rbp+1F0h+var_148]
0x18000de6d  test    rcx, rcx
0x18000de70  jnz     loc_18000E440
0x18000de76  mov     ecx, 340h; Size
0x18000de7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000de80  mov     rcx, rax; this
0x18000de83  call    ??0TPMW8T_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(void)
0x18000de88  mov     [rbp+1F0h+var_148], rax
0x18000de8f  mov     rax, [rbp+1F0h+var_1F8]
0x18000de93  mov     word ptr [rax+2FAh], 0Bh
0x18000de9c  mov     rax, [r13+0]
0x18000dea0  xor     r9d, r9d
0x18000dea3  lea     r8, [rbp+1F0h+var_1D8]
0x18000dea7  lea     rdx, [rbp+1F0h+var_1DC]
0x18000deab  mov     rcx, r13
0x18000deae  mov     rax, [rax+4E8h]
0x18000deb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deba  mov     edi, eax
0x18000debc  test    eax, eax
0x18000debe  js      loc_18000E45D
0x18000dec4  lea     rax, [r13+68h]
0x18000dec8  test    rax, rax
0x18000decb  jz      loc_18000E4DF
0x18000ded1  movzx   r14d, word ptr [rax+38h]
0x18000ded6  mov     rsi, [rax+40h]
0x18000deda  cmp     [rbp+1F0h+Block], 0
0x18000dee2  jnz     loc_18000E0D6
0x18000dee8  mov     rax, [rbp+1F0h+var_190]
0x18000deec  xor     edx, edx
0x18000deee  lea     rcx, [rbp+1F0h+var_190]
0x18000def2  mov     rax, [rax+18h]
0x18000def6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000defb  mov     ebx, eax
0x18000defd  test    eax, eax
0x18000deff  js      short loc_18000DF35
0x18000df01  mov     rcx, [rbp+1F0h+Block]; Block
0x18000df08  test    rcx, rcx
0x18000df0b  jnz     loc_18000E4EB
0x18000df11  mov     rcx, r14; Size
0x18000df14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000df19  mov     [rbp+1F0h+Block], rax
0x18000df20  mov     r8, r14; Size
0x18000df23  xor     edx, edx; Val
0x18000df25  mov     rcx, rax; void *
0x18000df28  call    memset_0
0x18000df2d  mov     [rbp+1F0h+var_158], r14w
0x18000df35  test    ebx, ebx
0x18000df37  js      loc_18000E4E4
0x18000df3d  movzx   r8d, [rbp+1F0h+var_158]; Size
0x18000df45  mov     rdx, rsi; Src
0x18000df48  mov     rcx, [rbp+1F0h+Block]; void *
0x18000df4f  call    memcpy_0
0x18000df54  test    ebx, ebx
0x18000df56  js      loc_18000E4E4
0x18000df5c  mov     rbx, [rbp+1F0h+var_148]
0x18000df63  mov     rax, [r13+60h]
0x18000df67  mov     [rbp+1F0h+var_148], rax
0x18000df6e  xor     edx, edx; void *
0x18000df70  lea     rcx, [rsp+2F0h+var_2A0]; this
0x18000df75  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x18000df7a  mov     edi, eax
0x18000df7c  mov     [rbp+1F0h+var_148], rbx
0x18000df83  test    eax, eax
0x18000df85  js      loc_18000E5AA
0x18000df8b  lea     rsi, [r13+140h]
0x18000df92  movzx   r15d, [rbp+1F0h+var_100]
0x18000df9a  mov     r12, [rbp+1F0h+Src]
0x18000dfa1  mov     rax, [rsi+40h]
0x18000dfa5  test    rax, rax
0x18000dfa8  jnz     loc_18000E11D
0x18000dfae  mov     rax, [rsi]
0x18000dfb1  xor     edx, edx
0x18000dfb3  mov     rcx, rsi
0x18000dfb6  mov     rax, [rax+18h]
0x18000dfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfbf  mov     ebx, eax
0x18000dfc1  test    eax, eax
0x18000dfc3  js      short loc_18000DFF0
0x18000dfc5  mov     rcx, [rsi+40h]; Block
0x18000dfc9  test    rcx, rcx
0x18000dfcc  jnz     loc_18000E60F
0x18000dfd2  mov     rcx, r15; Size
0x18000dfd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dfda  mov     [rsi+40h], rax
0x18000dfde  mov     r8, r15; Size
0x18000dfe1  xor     edx, edx; Val
0x18000dfe3  mov     rcx, rax; void *
0x18000dfe6  call    memset_0
0x18000dfeb  mov     [rsi+38h], r15w
0x18000dff0  test    ebx, ebx
0x18000dff2  js      loc_18000E54A
0x18000dff8  movzx   r8d, word ptr [rsi+38h]; Size
0x18000dffd  mov     rdx, r12; Src
0x18000e000  mov     rcx, [rsi+40h]; void *
0x18000e004  call    memcpy_0
0x18000e009  mov     eax, [rbp+1F0h+var_140]
0x18000e00f  mov     [r13+1D0h], eax
0x18000e016  lea     rax, ??_7TPMW8_Load@tpm12class@@6B@; const tpm12class::TPMW8_Load::`vftable'
0x18000e01d  mov     [rsp+2F0h+var_2A0], rax
0x18000e022  mov     [rbp+1F0h+var_1DC], 40000007h
0x18000e029  mov     [rbp+1F0h+var_140], 40000007h
0x18000e033  mov     rcx, [rbp+1F0h+var_148]
0x18000e03a  test    rcx, rcx
0x18000e03d  jz      short loc_18000E05B
0x18000e03f  mov     rax, [rcx]
0x18000e042  mov     edx, 1
0x18000e047  mov     rax, [rax+20h]
0x18000e04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e050  mov     [rbp+1F0h+var_148], 0
0x18000e05b  lea     rcx, [rbp+1F0h+var_138]; this
0x18000e062  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x18000e067  lea     rcx, [rbp+1F0h+var_190]; this
0x18000e06b  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x18000e070  lea     rcx, [rbp+1F0h+var_1D8]; this
0x18000e074  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x18000e079  lea     rcx, [rsp+2F0h+var_2A0]; this
0x18000e07e  call    ??1TPMW8_COMMAND@tpm12class@@UEAA@XZ; tpm12class::TPMW8_COMMAND::~TPMW8_COMMAND(void)
0x18000e083  nop
0x18000e084  lea     rcx, [rsp+2F0h+var_2C0]; this
0x18000e089  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18000e08e  xor     eax, eax
0x18000e090  mov     rbx, [rsp+2F0h+arg_10]
0x18000e098  add     rsp, 2C0h
0x18000e09f  pop     r15
0x18000e0a1  pop     r14
0x18000e0a3  pop     r13
0x18000e0a5  pop     r12
0x18000e0a7  pop     rdi
0x18000e0a8  pop     rsi
0x18000e0a9  pop     rbp
0x18000e0aa  retn
0x18000e0ac  mov     rcx, [rbp+1F8h]; this
0x18000e0b3  mov     r9d, ebx; char *
0x18000e0b6  lea     r8, aOnecoreBaseNgs_22; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18000e0bd  mov     edx, 7E1h; void *
0x18000e0c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e0c7  nop
0x18000e0c8  lea     rcx, [rsp+2F0h+var_2C0]; this
0x18000e0cd  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18000e0d2  mov     eax, ebx
0x18000e0d4  jmp     short loc_18000E090
0x18000e0d6  movzx   ecx, [rbp+1F0h+var_158]
0x18000e0dd  cmp     r14, rcx
0x18000e0e0  ja      loc_18000E4FC
0x18000e0e6  sub     rcx, r14
0x18000e0e9  mov     rax, [rbp+1F0h+Block]
0x18000e0f0  lea     rax, [rax+r14]
0x18000e0f4  jz      short loc_18000E10D
0x18000e0f6  nop     word ptr [rax+rax+00000000h]
0x18000e100  mov     byte ptr [rax], 0
0x18000e103  lea     rax, [rax+1]
0x18000e107  sub     rcx, 1
0x18000e10b  jnz     short loc_18000E100
0x18000e10d  mov     [rbp+1F0h+var_158], r14w
0x18000e115  mov     ebx, r15d
0x18000e118  jmp     loc_18000DF3D
0x18000e11d  movzx   ecx, word ptr [rsi+38h]
0x18000e121  cmp     r15, rcx
0x18000e124  ja      loc_18000E621
0x18000e12a  sub     rcx, r15
0x18000e12d  lea     rax, [r15+rax]
0x18000e131  jz      short loc_18000E140
0x18000e133  mov     byte ptr [rax], 0
0x18000e136  lea     rax, [rax+1]
0x18000e13a  sub     rcx, 1
0x18000e13e  jnz     short loc_18000E133
0x18000e140  mov     [rsi+38h], r15w
0x18000e145  jmp     loc_18000DFF8
0x18000e14a  mov     [r13+318h], esi
0x18000e151  mov     rcx, [r13+310h]; void *
0x18000e158  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e15d  mov     [r13+310h], rsi
0x18000e164  mov     edi, dword ptr [rbp+1F0h+arg_0]
0x18000e16a  mov     edx, edi
0x18000e16c  lea     rcx, [rbp+1F0h+arg_8]
0x18000e173  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18000e178  mov     rdx, [rbp+1F0h+arg_8]; unsigned __int8 *
0x18000e17f  test    rdx, rdx
0x18000e182  jnz     loc_18000E7F8
0x18000e188  lea     rcx, [rsp+2F0h+var_2A0]; this
0x18000e18d  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18000e192  nop
0x18000e193  lea     rcx, [rsp+2F0h+var_2C0]; this
0x18000e198  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18000e19d  mov     eax, 80070008h
0x18000e1a2  jmp     loc_18000E090
0x18000e1a7  xor     esi, esi
0x18000e1a9  mov     [r13+60h], rsi
0x18000e1ad  mov     rdx, [rbp+1F0h+var_E0]
0x18000e1b4  lea     rcx, [rbp+1F0h+arg_0]
0x18000e1bb  call    ??$make_unique_nothrow@VTPMW8T_PUBLIC@tpm12class@@AEAV12@@wil@@YA?AV?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@AEAVTPMW8T_PUBLIC@tpm12class@@@Z; wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(tpm12class::TPMW8T_PUBLIC &)
0x18000e1c0  mov     rax, [rbp+1F0h+arg_0]
0x18000e1c7  xor     edx, edx
0x18000e1c9  lea     rcx, [rbp+1F0h+arg_0]
0x18000e1d0  test    rax, rax
0x18000e1d3  jnz     loc_18000E788
0x18000e1d9  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x18000e1de  jmp     short loc_18000E188
0x18000e1e0  mov     [r13+328h], esi
0x18000e1e7  mov     rcx, [r13+320h]; void *
0x18000e1ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e1f3  mov     [r13+320h], rsi
0x18000e1fa  mov     edi, dword ptr [rbp+1F0h+arg_0]
  ... truncated ...
```
