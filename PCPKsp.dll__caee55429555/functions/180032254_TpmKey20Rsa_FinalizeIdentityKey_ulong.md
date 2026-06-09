# TpmKey20Rsa::FinalizeIdentityKey(ulong)

- ea: `0x180032254`
- end: `0x180033354`
- name: `?FinalizeIdentityKey@TpmKey20Rsa@@IEAAJK@Z`
- size: `4352`
- prototype: `__int64 __fastcall(TpmKey20Rsa *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18008bb60`

## callees

- `0x18000eda0`
- `0x18000fea0`
- `0x180010c90`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800294d4`
- `0x18002a790`
- `0x18002b3d0`
- `0x18002d890`
- `0x18002e380`
- `0x18002f774`
- `0x18002fd90`
- `0x180032110`
- `0x180032254`
- `0x18003335c`
- `0x1800334a0`
- `0x1800335b0`
- `0x1800340bc`
- `0x180034464`
- `0x180041158`
- `0x18004dbe0`
- `0x180056c94`
- `0x18005ba18`
- `0x18005be94`
- `0x180065d78`
- `0x180066960`
- `0x1800764d0`
- `0x1800768a0`
- `0x180076998`
- `0x18007704c`
- `0x1800c8010`

## string_xrefs

- `0x1800322f6`: `TpmKey20::ReadParent`
- `0x180032513`: `TpmKey20::ReadParent`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall TpmKey20Rsa::FinalizeIdentityKey(TpmKey20Rsa *this)
{
  int v2; // edi
  __int64 v3; // rdx
  unsigned __int64 v4; // r9
  int v5; // eax
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // eax
  int v9; // eax
  int Policy; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  tpm12class::TpmDataObject *v16; // rbx
  int v17; // eax
  int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  unsigned int v20; // ebx
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rdi
  int v23; // eax
  __int64 v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  unsigned int v26; // ebx
  unsigned __int8 *v27; // rax
  unsigned __int8 *v28; // rdi
  int v29; // eax
  int v30; // eax
  const struct std::nothrow_t *v31; // rdx
  unsigned int v32; // r14d
  unsigned __int8 *v33; // rax
  unsigned __int8 *v34; // rbx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  unsigned int v41; // eax
  int v42; // eax
  int v43; // eax
  tpm12class::TpmDataObject *v44; // rbx
  int v45; // eax
  int v46; // eax
  int v47; // r14d
  int v48; // eax
  int v49; // r14d
  __int64 v50; // rdx
  int v51; // r14d
  __int64 v52; // rdx
  const struct std::nothrow_t *v53; // rdx
  int v54; // ebx
  unsigned int v55; // edi
  unsigned __int8 *v56; // rax
  unsigned __int8 *v57; // rbx
  int v58; // eax
  int v59; // edx
  __int64 v60; // rbx
  int v61; // eax
  int v62; // edx
  unsigned int v63; // ebx
  int v64; // eax
  int v65; // eax
  int v66; // eax
  __int64 v67; // rcx
  int v69[2]; // [rsp+20h] [rbp-E0h] BYREF
  char v70; // [rsp+28h] [rbp-D8h]
  size_t Size; // [rsp+38h] [rbp-C8h] BYREF
  int v72[49]; // [rsp+40h] [rbp-C0h] BYREF
  int v73; // [rsp+104h] [rbp+4h]
  char v74[72]; // [rsp+108h] [rbp+8h] BYREF
  char v75[72]; // [rsp+150h] [rbp+50h] BYREF
  tpm12class::TpmDataObject *v76; // [rsp+198h] [rbp+98h]
  int v77; // [rsp+1A0h] [rbp+A0h]
  _BYTE v78[72]; // [rsp+1A8h] [rbp+A8h] BYREF
  int *v79[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  int *v80[3]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v81[168]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v82; // [rsp+2C8h] [rbp+1C8h]
  int v83; // [rsp+2E8h] [rbp+1E8h]
  char v84[72]; // [rsp+2F0h] [rbp+1F0h] BYREF
  struct tpm12class::TPMW8S_SENSITIVE_CREATE *v85; // [rsp+338h] [rbp+238h]
  struct tpm12class::TPMW8T_PUBLIC *v86; // [rsp+340h] [rbp+240h]
  char v87[56]; // [rsp+348h] [rbp+248h] BYREF
  unsigned __int16 v88; // [rsp+380h] [rbp+280h]
  void *Destination; // [rsp+388h] [rbp+288h]
  _BYTE v90[72]; // [rsp+3D8h] [rbp+2D8h] BYREF
  tpm12class::TpmDataObject *v91; // [rsp+420h] [rbp+320h]
  tpm12class::TpmDataObject *v92; // [rsp+428h] [rbp+328h]
  _QWORD v93[2]; // [rsp+430h] [rbp+330h] BYREF
  size_t v94; // [rsp+440h] [rbp+340h]
  tpm12class::TpmDataObject *v95; // [rsp+478h] [rbp+378h]
  _BYTE v96[196]; // [rsp+480h] [rbp+380h] BYREF
  int v97; // [rsp+544h] [rbp+444h]
  _BYTE v98[144]; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v99[160]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned int v100; // [rsp+680h] [rbp+580h]
  tpm12class::TPMW8_SESSION *v101; // [rsp+688h] [rbp+588h]
  int v102; // [rsp+6A0h] [rbp+5A0h]
  char v103[72]; // [rsp+6A8h] [rbp+5A8h] BYREF
  int v104; // [rsp+6F0h] [rbp+5F0h]
  char v105[72]; // [rsp+6F8h] [rbp+5F8h] BYREF
  char v106[56]; // [rsp+740h] [rbp+640h] BYREF
  unsigned __int16 v107; // [rsp+778h] [rbp+678h]
  void *v108; // [rsp+780h] [rbp+680h]
  char v109[136]; // [rsp+788h] [rbp+688h] BYREF
  tpm12class::TpmDataObject *v110; // [rsp+810h] [rbp+710h]
  _QWORD v111[2]; // [rsp+818h] [rbp+718h] BYREF
  int v112; // [rsp+828h] [rbp+728h]
  _QWORD v113[2]; // [rsp+860h] [rbp+760h] BYREF
  int v114; // [rsp+870h] [rbp+770h]
  wil::details::in1diag3 *retaddr; // [rsp+A38h] [rbp+938h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v80, L"TpmKey20Rsa::FinalizeIdentityKey", 1);
  tpm12class::TPMW8_Create::TPMW8_Create((tpm12class::TPMW8_Create *)v81);
  if ( !*((_QWORD *)this + 59) )
  {
    if ( *((_DWORD *)this + 260) )
    {
      v2 = -2144795617;
      v3 = 1901;
      goto LABEL_5;
    }
    KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v69, L"TpmKey20::ReadParent", 1);
    if ( *((_QWORD *)this + 59) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBDF,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)0x80090029LL,
        v69[0]);
      v2 = -2146893783;
      goto LABEL_15;
    }
    tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v96);
    v97 = -2130706431;
    v5 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v96, 0);
    v2 = v5;
    if ( v5 >= 0 )
    {
      v83 = -2130706431;
      v5 = tpm12class::TPMW82B_BUFFER::CopyFrom(
             (tpm12class::TPMW82B_BUFFER *)v84,
             (const struct tpm12class::TPMW82B_BUFFER *)v98);
      v2 = v5;
      if ( v5 >= 0 )
      {
        tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v96);
        v2 = 0;
LABEL_15:
        KspFunctionLogger::~KspFunctionLogger((int **)v69);
        if ( v2 < 0 )
        {
          v3 = 1905;
          goto LABEL_5;
        }
        if ( v83 != -2130706431 )
        {
          v2 = -2144795634;
          v3 = 1907;
          goto LABEL_5;
        }
        *(_WORD *)(v82 + 762) = 11;
        v7 = TpmKey20Rsa::SetCommonRsaKeyAttributes(this, v86, v85, 0xBu);
        v2 = v7;
        if ( v7 < 0 )
        {
          v4 = (unsigned int)v7;
          v3 = 1913;
          goto LABEL_6;
        }
        *((_WORD *)v86 + 96) = 16;
        v8 = *((_DWORD *)this + 186);
        if ( v8 )
        {
          v9 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v87, v8);
          v2 = v9;
          if ( v9 < 0 )
          {
            v4 = (unsigned int)v9;
            v3 = 1922;
            goto LABEL_6;
          }
          memcpy_s_3(Destination, v88, *((const void *const *)this + 92), *((unsigned int *)this + 186));
        }
        Policy = TpmKey20::GeneratePolicy(this, v86);
        v2 = Policy;
        if ( Policy < 0 )
        {
          v4 = (unsigned int)Policy;
          v3 = 1932;
          goto LABEL_6;
        }
        v11 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v81, 0);
        v2 = v11;
        if ( v11 < 0 )
        {
          v4 = (unsigned int)v11;
          v3 = 1934;
          goto LABEL_6;
        }
        v12 = TpmKey20Rsa::VerifyPublicKeyStrength(this, v91);
        v2 = v12;
        if ( v12 < 0 )
        {
          v4 = (unsigned int)v12;
          v3 = 1935;
          goto LABEL_6;
        }
        tpm12class::TPMW8_Load::TPMW8_Load((tpm12class::TPMW8_Load *)v72);
        *(_QWORD *)v69 = v72;
        v70 = 1;
        KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v79, L"TpmKey20::ReadParent", 1);
        if ( *((_QWORD *)this + 59) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBDF,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
            (const char *)0x80090029LL,
            v69[0]);
          v2 = -2146893783;
          goto LABEL_39;
        }
        tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v96);
        v97 = -2130706431;
        v13 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v96, 0);
        v2 = v13;
        if ( v13 >= 0 )
        {
          v73 = -2130706431;
          v13 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                  (tpm12class::TPMW82B_BUFFER *)v74,
                  (const struct tpm12class::TPMW82B_BUFFER *)v98);
          v2 = v13;
          if ( v13 >= 0 )
          {
            tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v96);
            v2 = 0;
LABEL_39:
            KspFunctionLogger::~KspFunctionLogger(v79);
            if ( v2 >= 0 )
            {
              if ( v73 == -2130706431 )
              {
                v15 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                        (tpm12class::TPMW82B_BUFFER *)v75,
                        (const struct tpm12class::TPMW82B_BUFFER *)v90);
                v2 = v15;
                if ( v15 >= 0 )
                {
                  v16 = v76;
                  v76 = v91;
                  v17 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v72, 0);
                  v2 = v17;
                  v76 = v16;
                  if ( v17 >= 0 )
                  {
                    LODWORD(Size) = 0;
                    v18 = tpm12class::TpmDataObject::Get(v92, 0, 0, (unsigned int *)&Size);
                    v2 = v18;
                    if ( v18 >= 0 )
                    {
                      *((_DWORD *)this + 198) = 0;
                      operator delete(*((void **)this + 98), v19);
                      *((_QWORD *)this + 98) = 0;
                      v20 = Size;
                      v21 = (unsigned __int8 *)operator new[](
                                                 (unsigned int)Size,
                                                 (const struct std::nothrow_t *)&std::nothrow);
                      v22 = v21;
                      if ( !v21 )
                        goto LABEL_114;
                      memset_0(v21, 0, v20);
                      *((_QWORD *)this + 98) = v22;
                      *((_DWORD *)this + 198) = v20;
                      v23 = tpm12class::TpmDataObject::Get(v92, v22, v20, (unsigned int *)this + 198);
                      v2 = v23;
                      if ( v23 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x7BA,
                          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                          (const char *)(unsigned int)v23,
                          v69[0]);
                        v70 = 0;
                        lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                        goto LABEL_41;
                      }
                      v2 = tpm12class::TpmDataObject::Clear((tpm12class::TpmDataObject *)v93, 0);
                      if ( v2 < 0
                        || (LOBYTE(v24) = 1,
                            v2 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v93[0] + 16LL))(v93, v24),
                            v2 < 0)
                        || (v2 = (*(__int64 (__fastcall **)(_QWORD *))v93[0])(v93), v2 < 0) )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x7BE,
                          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                          (const char *)(unsigned int)v2,
                          v69[0]);
                        v70 = 0;
                        lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                        goto LABEL_41;
                      }
                      v26 = v94;
                      LODWORD(Size) = v94;
                      *((_DWORD *)this + 202) = 0;
                      operator delete(*((void **)this + 100), v25);
                      *((_QWORD *)this + 100) = 0;
                      v27 = (unsigned __int8 *)operator new[](v26, (const struct std::nothrow_t *)&std::nothrow);
                      v28 = v27;
                      if ( !v27 )
                        goto LABEL_114;
                      memset_0(v27, 0, v26);
                      *((_QWORD *)this + 100) = v28;
                      *((_DWORD *)this + 202) = v26;
                      v29 = tpm12class::TpmDataObject::Get(
                              (tpm12class::TpmDataObject *)v93,
                              v28,
                              v26,
                              (unsigned int *)this + 202);
                      v2 = v29;
                      if ( v29 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x7C4,
                          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                          (const char *)(unsigned int)v29,
                          v69[0]);
                        v70 = 0;
                        lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                        goto LABEL_41;
                      }
                      v30 = tpm12class::TpmDataObject::Get(v95, 0, 0, (unsigned int *)&Size);
                      v2 = v30;
                      if ( v30 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x7C8,
                          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                          (const char *)(unsigned int)v30,
                          v69[0]);
                        v70 = 0;
                        lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                        goto LABEL_41;
                      }
                      *((_DWORD *)this + 206) = 0;
                      operator delete(*((void **)this + 102), v31);
                      *((_QWORD *)this + 102) = 0;
                      v32 = Size;
                      v33 = (unsigned __int8 *)operator new[](
                                                 (unsigned int)Size,
                                                 (const struct std::nothrow_t *)&std::nothrow);
                      v34 = v33;
                      if ( v33 )
                      {
                        memset_0(v33, 0, v32);
                        *((_QWORD *)this + 102) = v34;
                        *((_DWORD *)this + 206) = v32;
                        v35 = tpm12class::TpmDataObject::Get(v95, v34, v32, (unsigned int *)this + 206);
                        v2 = v35;
                        if ( v35 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x7CE,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v35,
                            v69[0]);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        tpm12class::TPMW8_CertifyCreation::TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                        if ( *((_DWORD *)this + 140) )
                        {
                          v36 = tpm12class::TPMW8_SESSION::SetAuthProvider(
                                  v101,
                                  (TpmKey20Rsa *)((char *)this + 488),
                                  *((_WORD *)v101 + 381));
                          v2 = v36;
                          if ( v36 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x7D6,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v36,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                        }
                        if ( (*((_DWORD *)v91 + 15) & 0x40) == 0 )
                        {
                          *((_WORD *)v101 + 381) = 11;
                          *((_BYTE *)v101 + 761) = 1;
                          v37 = tpm12class::TPMW8_SESSION::Create(v101, 0);
                          v2 = v37;
                          if ( v37 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x7DE,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v37,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                          v38 = TpmKey20::ExecutePolicy(this, *((_DWORD *)v101 + 4), v100);
                          v2 = v38;
                          if ( v38 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x7E0,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v38,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                        }
                        v102 = v77;
                        v39 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                                (tpm12class::TPMW82B_BUFFER *)v103,
                                (const struct tpm12class::TPMW82B_BUFFER *)v78);
                        v2 = v39;
                        if ( v39 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x7E3,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v39,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        v104 = v77;
                        v40 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                                (tpm12class::TPMW82B_BUFFER *)v105,
                                (const struct tpm12class::TPMW82B_BUFFER *)v78);
                        v2 = v40;
                        if ( v40 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x7E5,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v40,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        v41 = *((_DWORD *)this + 186);
                        if ( v41 )
                        {
                          v42 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)v106, v41);
                          v2 = v42;
                          if ( v42 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x7E8,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v42,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                          memcpy_s_3(v108, v107, *((const void *const *)this + 92), v107);
                        }
                        v43 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                                (tpm12class::TPMW82B_BUFFER *)v109,
                                (const struct tpm12class::TPMW82B_BUFFER *)v93);
                        v2 = v43;
                        if ( v43 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x7EE,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v43,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        v44 = v110;
                        v110 = v95;
                        v45 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v99, 0);
                        v2 = v45;
                        v110 = v44;
                        if ( v45 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x7F6,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v45,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        LODWORD(Size) = 0;
                        v46 = tpm12class::TpmDataObject::Get(v91, 0, 0, (unsigned int *)&Size);
                        v2 = v46;
                        if ( v46 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x7FF,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v46,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        v47 = Size + 4;
                        v48 = tpm12class::TpmDataObject::Get(v92, 0, 0, (unsigned int *)&Size);
                        v2 = v48;
                        if ( v48 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x804,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v48,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        v49 = Size + v47;
                        v2 = tpm12class::TpmDataObject::Clear((tpm12class::TpmDataObject *)v111, 0);
                        if ( v2 < 0
                          || (LOBYTE(v50) = 1,
                              v2 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v111[0] + 16LL))(v111, v50),
                              v2 < 0)
                          || (v2 = (*(__int64 (__fastcall **)(_QWORD *))v111[0])(v111), v2 < 0) )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x809,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v2,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        LODWORD(Size) = v112;
                        v51 = v112 + v49;
                        v2 = tpm12class::TpmDataObject::Clear((tpm12class::TpmDataObject *)v113, 0);
                        if ( v2 < 0
                          || (LOBYTE(v52) = 1,
                              v2 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v113[0] + 16LL))(v113, v52),
                              v2 < 0)
                          || (v2 = (*(__int64 (__fastcall **)(_QWORD *))v113[0])(v113), v2 < 0) )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x80E,
                            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                            (const char *)(unsigned int)v2,
                            v69[0]);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                          goto LABEL_41;
                        }
                        v54 = v114;
                        LODWORD(Size) = v114;
                        v55 = v51 + v114;
                        *((_DWORD *)this + 190) = 0;
                        operator delete(*((void **)this + 94), v53);
                        *((_QWORD *)this + 94) = 0;
                        v56 = (unsigned __int8 *)operator new[](
                                                   (unsigned int)(v51 + v54),
                                                   (const struct std::nothrow_t *)&std::nothrow);
                        v57 = v56;
                        if ( v56 )
                        {
                          memset_0(v56, 0, v55);
                          *((_QWORD *)this + 94) = v57;
                          *((_DWORD *)this + 190) = v55;
                          v58 = tpm12class::TpmDataObject::Get(v91, v57 + 2, v55 - 2, (unsigned int *)&Size);
                          v2 = v58;
                          if ( v58 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x81C,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v58,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                          v59 = Size;
                          **((_BYTE **)this + 94) = BYTE1(Size);
                          *(_BYTE *)(*((_QWORD *)this + 94) + 1LL) = v59;
                          v60 = (unsigned int)(v59 + 4);
                          v61 = tpm12class::TpmDataObject::Get(
                                  v92,
                                  (unsigned __int8 *)((unsigned int)v60 + *((_QWORD *)this + 94)),
                                  *((_DWORD *)this + 190) - v60,
                                  (unsigned int *)&Size);
                          v2 = v61;
                          if ( v61 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x826,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v61,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                          v62 = Size;
                          *(_BYTE *)(v60 + *((_QWORD *)this + 94) - 2) = BYTE1(Size);
                          *(_BYTE *)(v60 + *((_QWORD *)this + 94) - 1) = v62;
                          v63 = v62 + v60;
                          v64 = tpm12class::TpmDataObject::Get(
                                  (tpm12class::TpmDataObject *)v111,
                                  (unsigned __int8 *)(*((_QWORD *)this + 94) + v63),
                                  *((_DWORD *)this + 190) - v63,
                                  (unsigned int *)&Size);
                          v2 = v64;
                          if ( v64 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x82F,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v64,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                          v65 = tpm12class::TpmDataObject::Get(
                                  (tpm12class::TpmDataObject *)v113,
                                  (unsigned __int8 *)(*((_QWORD *)this + 94) + v63 + (unsigned int)Size),
                                  *((_DWORD *)this + 190) - (v63 + Size),
                                  (unsigned int *)&Size);
                          v2 = v65;
                          if ( v65 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x835,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v65,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                          v66 = tpm12class::TPMW82B_BUFFER::CopyFrom(
                                  (TpmKey20Rsa *)((char *)this + 104),
                                  (const struct tpm12class::TPMW82B_BUFFER *)v90);
                          v2 = v66;
                          if ( v66 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x83A,
                              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                              (const char *)(unsigned int)v66,
                              v69[0]);
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            goto LABEL_41;
                          }
                          v67 = *((_QWORD *)this + 12);
                          if ( v67 )
                            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 32LL))(v67, 1);
                          *((_QWORD *)this + 12) = 0;
                          wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(&Size, v91);
                          if ( Size )
                          {
                            *((_QWORD *)this + 12) = Size;
                            tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                            v70 = 0;
                            lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                            tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v72);
                            v2 = 0;
                            goto LABEL_116;
                          }
                          wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
                            &Size,
                            0);
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                        }
                        else
                        {
                          tpm12class::TPMW8_CertifyCreation::~TPMW8_CertifyCreation((tpm12class::TPMW8_CertifyCreation *)v99);
                          v70 = 0;
                          lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                        }
                      }
                      else
                      {
LABEL_114:
                        v70 = 0;
                        lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                      }
                      tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v72);
                      v2 = -2147024888;
                      goto LABEL_116;
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x7B4,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                      (const char *)(unsigned int)v18,
                      v69[0]);
                    v70 = 0;
                    lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x7AB,
                      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                      (const char *)(unsigned int)v17,
                      v69[0]);
                    v70 = 0;
                    lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x7A3,
                    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                    (const char *)(unsigned int)v15,
                    v69[0]);
                  v70 = 0;
                  lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
                }
              }
              else
              {
                v2 = -2144795634;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7A1,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                  (const char *)0x8029040ELL,
                  v69[0]);
                v70 = 0;
                lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x79F,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
                (const char *)(unsigned int)v2,
                v69[0]);
              v70 = 0;
              lambda_54170be0847a6a8274d539ec808565ce_::operator()(v69);
            }
LABEL_41:
            tpm12class::TPMW8_Load::~TPMW8_Load((tpm12class::TPMW8_Load *)v72);
            goto LABEL_116;
          }
          v14 = 3051;
        }
        else
        {
          v14 = 3045;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
          (const char *)(unsigned int)v13,
          v69[0]);
        tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v96);
        goto LABEL_39;
      }
      v6 = 3051;
    }
    else
    {
      v6 = 3045;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
      (const char *)(unsigned int)v5,
      v69[0]);
    tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v96);
    goto LABEL_15;
  }
  v2 = -2144795643;
  v3 = 1899;
LABEL_5:
  v4 = (unsigned int)v2;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20rsa.cpp",
    (const char *)v4,
    v69[0]);
LABEL_116:
  tpm12class::TPMW8_Create::~TPMW8_Create((tpm12class::TPMW8_Create *)v81);
  KspFunctionLogger::~KspFunctionLogger(v80);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180032254  mov     [rsp-8+arg_8], rbx
0x180032259  mov     [rsp-8+arg_10], rsi
0x18003225e  push    rbp
0x18003225f  push    rdi
0x180032260  push    r12
0x180032262  push    r14
0x180032264  push    r15
0x180032266  lea     rbp, [rsp-910h]
0x18003226e  sub     rsp, 0A10h
0x180032275  mov     rax, cs:__security_cookie
0x18003227c  xor     rax, rsp
0x18003227f  mov     [rbp+930h+var_30], rax
0x180032286  mov     rsi, rcx
0x180032289  mov     r8b, 1; bool
0x18003228c  lea     rdx, aTpmkey20rsaFin_0; "TpmKey20Rsa::FinalizeIdentityKey"
0x180032293  lea     rcx, [rbp+930h+var_828]; this
0x18003229a  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18003229f  nop
0x1800322a0  lea     rcx, [rbp+930h+var_810]; this
0x1800322a7  call    ??0TPMW8_Create@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Create::TPMW8_Create(void)
0x1800322ac  nop
0x1800322ad  xor     r12d, r12d
0x1800322b0  cmp     [rsi+1D8h], r12
0x1800322b7  jz      short loc_1800322C5
0x1800322b9  mov     edi, 80290405h
0x1800322be  mov     edx, 76Bh
0x1800322c3  jmp     short loc_1800322D8
0x1800322c5  cmp     [rsi+410h], r12d
0x1800322cc  jz      short loc_1800322F3
0x1800322ce  mov     edi, 8029041Fh
0x1800322d3  mov     edx, 76Dh; void *
0x1800322d8  mov     r9d, edi; char *
0x1800322db  mov     rcx, [rbp+938h]; this
0x1800322e2  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800322e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800322ee  jmp     loc_18003330D
0x1800322f3  mov     r8b, 1; bool
0x1800322f6  lea     rdx, aTpmkey20Readpa; "TpmKey20::ReadParent"
0x1800322fd  lea     rcx, [rsp+0A30h+var_A10]; this
0x180032302  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180032307  nop
0x180032308  mov     ebx, 81000001h
0x18003230d  mov     r15d, 80090029h
0x180032313  lea     r14, aOnecoreBaseNgs_22; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003231a  cmp     [rsi+1D8h], r12
0x180032321  jz      short loc_180032343
0x180032323  mov     rcx, [rbp+938h]; this
0x18003232a  mov     r9d, r15d; char *
0x18003232d  mov     r8, r14; unsigned int
0x180032330  mov     edx, 0BDFh; void *
0x180032335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003233a  nop
0x18003233b  mov     edi, r15d
0x18003233e  jmp     loc_1800323C7
0x180032343  lea     rcx, [rbp+930h+var_5B0]; this
0x18003234a  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x18003234f  nop
0x180032350  mov     [rbp+930h+var_4EC], ebx
0x180032356  xor     edx, edx; void *
0x180032358  lea     rcx, [rbp+930h+var_5B0]; this
0x18003235f  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x180032364  mov     edi, eax
0x180032366  test    eax, eax
0x180032368  jns     short loc_180032391
0x18003236a  mov     edx, 0BE5h; void *
0x18003236f  mov     r8, r14; unsigned int
0x180032372  mov     r9d, eax; char *
0x180032375  mov     rcx, [rbp+938h]; this
0x18003237c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032381  nop
0x180032382  lea     rcx, [rbp+930h+var_5B0]; this
0x180032389  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x18003238e  nop
0x18003238f  jmp     short loc_1800323C7
0x180032391  mov     [rbp+930h+var_748], ebx
0x180032397  lea     rdx, [rbp+930h+var_4E0]; struct tpm12class::TPMW82B_BUFFER *
0x18003239e  lea     rcx, [rbp+930h+var_740]; this
0x1800323a5  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x1800323aa  mov     edi, eax
0x1800323ac  test    eax, eax
0x1800323ae  jns     short loc_1800323B7
0x1800323b0  mov     edx, 0BEBh
0x1800323b5  jmp     short loc_18003236F
0x1800323b7  lea     rcx, [rbp+930h+var_5B0]; this
0x1800323be  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x1800323c3  nop
0x1800323c4  mov     edi, r12d
0x1800323c7  lea     rcx, [rsp+0A30h+var_A10]; this
0x1800323cc  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800323d1  test    edi, edi
0x1800323d3  jns     short loc_1800323DF
0x1800323d5  mov     edx, 771h
0x1800323da  jmp     loc_1800322D8
0x1800323df  cmp     [rbp+930h+var_748], ebx
0x1800323e5  jz      short loc_1800323F6
0x1800323e7  mov     edi, 8029040Eh
0x1800323ec  mov     edx, 773h
0x1800323f1  jmp     loc_1800322D8
0x1800323f6  mov     ecx, 0Bh
0x1800323fb  mov     rax, [rbp+930h+var_768]
0x180032402  mov     [rax+2FAh], cx
0x180032409  mov     r9d, ecx; unsigned __int16
0x18003240c  mov     r8, [rbp+930h+var_6F8]; struct tpm12class::TPMW8S_SENSITIVE_CREATE *
0x180032413  mov     rdx, [rbp+930h+var_6F0]; struct tpm12class::TPMW8T_PUBLIC *
0x18003241a  mov     rcx, rsi; this
0x18003241d  call    ?SetCommonRsaKeyAttributes@TpmKey20Rsa@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@PEAVTPMW8S_SENSITIVE_CREATE@3@G@Z; TpmKey20Rsa::SetCommonRsaKeyAttributes(tpm12class::TPMW8T_PUBLIC *,tpm12class::TPMW8S_SENSITIVE_CREATE *,ushort)
0x180032422  mov     edi, eax
0x180032424  test    eax, eax
0x180032426  jns     short loc_180032435
0x180032428  mov     r9d, eax
0x18003242b  mov     edx, 779h
0x180032430  jmp     loc_1800322DB
0x180032435  mov     rax, [rbp+930h+var_6F0]
0x18003243c  mov     word ptr [rax+0C0h], 10h
0x180032445  mov     eax, [rsi+2E8h]
0x18003244b  test    eax, eax
0x18003244d  jz      short loc_180032491
0x18003244f  mov     edx, eax; unsigned __int64
0x180032451  lea     rcx, [rbp+930h+var_6E8]; this
0x180032458  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x18003245d  mov     edi, eax
0x18003245f  test    eax, eax
0x180032461  jns     short loc_180032470
0x180032463  mov     r9d, eax
0x180032466  mov     edx, 782h
0x18003246b  jmp     loc_1800322DB
0x180032470  mov     r9d, [rsi+2E8h]; SourceSize
0x180032477  movzx   edx, [rbp+930h+var_6B0]; DestinationSize
0x18003247e  mov     r8, [rsi+2E0h]; Source
0x180032485  mov     rcx, [rbp+930h+Destination]; Destination
0x18003248c  call    memcpy_s_3
0x180032491  mov     rdx, [rbp+930h+var_6F0]; struct tpm12class::TPMW8T_PUBLIC *
0x180032498  mov     rcx, rsi; this
0x18003249b  call    ?GeneratePolicy@TpmKey20@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@@Z; TpmKey20::GeneratePolicy(tpm12class::TPMW8T_PUBLIC *)
0x1800324a0  mov     edi, eax
0x1800324a2  test    eax, eax
0x1800324a4  jns     short loc_1800324B3
0x1800324a6  mov     r9d, eax
0x1800324a9  mov     edx, 78Ch
0x1800324ae  jmp     loc_1800322DB
0x1800324b3  xor     edx, edx; void *
0x1800324b5  lea     rcx, [rbp+930h+var_810]; this
0x1800324bc  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1800324c1  mov     edi, eax
0x1800324c3  test    eax, eax
0x1800324c5  jns     short loc_1800324D4
0x1800324c7  mov     r9d, eax
0x1800324ca  mov     edx, 78Eh
0x1800324cf  jmp     loc_1800322DB
0x1800324d4  mov     rdx, [rbp+930h+var_610]; struct tpm12class::TPMW8T_PUBLIC *
0x1800324db  mov     rcx, rsi; this
0x1800324de  call    ?VerifyPublicKeyStrength@TpmKey20Rsa@@IEAAJPEAVTPMW8T_PUBLIC@tpm12class@@@Z; TpmKey20Rsa::VerifyPublicKeyStrength(tpm12class::TPMW8T_PUBLIC *)
0x1800324e3  mov     edi, eax
0x1800324e5  test    eax, eax
0x1800324e7  jns     short loc_1800324F6
0x1800324e9  mov     r9d, eax
0x1800324ec  mov     edx, 78Fh
0x1800324f1  jmp     loc_1800322DB
0x1800324f6  lea     rcx, [rsp+0A30h+var_9F0]; this
0x1800324fb  call    ??0TPMW8_Load@tpm12class@@QEAA@XZ; tpm12class::TPMW8_Load::TPMW8_Load(void)
0x180032500  nop
0x180032501  lea     rax, [rsp+0A30h+var_9F0]
0x180032506  mov     qword ptr [rsp+0A30h+var_A10], rax; int
0x18003250b  mov     [rsp+0A30h+var_A08], 1
0x180032510  mov     r8b, 1; bool
0x180032513  lea     rdx, aTpmkey20Readpa; "TpmKey20::ReadParent"
0x18003251a  lea     rcx, [rbp+930h+var_840]; this
0x180032521  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180032526  nop
0x180032527  cmp     [rsi+1D8h], r12
0x18003252e  jz      short loc_18003254D
0x180032530  mov     rcx, [rbp+938h]; this
0x180032537  mov     r9d, r15d; char *
0x18003253a  mov     r8, r14; unsigned int
0x18003253d  mov     edx, 0BDFh; void *
0x180032542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032547  nop
0x180032548  mov     edi, r15d
0x18003254b  jmp     short loc_1800325CB
0x18003254d  lea     rcx, [rbp+930h+var_5B0]; this
0x180032554  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x180032559  nop
0x18003255a  mov     [rbp+930h+var_4EC], ebx
0x180032560  xor     edx, edx; void *
0x180032562  lea     rcx, [rbp+930h+var_5B0]; this
0x180032569  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x18003256e  mov     edi, eax
0x180032570  test    eax, eax
0x180032572  jns     short loc_18003259B
0x180032574  mov     edx, 0BE5h; void *
0x180032579  mov     r8, r14; unsigned int
0x18003257c  mov     r9d, eax; char *
0x18003257f  mov     rcx, [rbp+938h]; this
0x180032586  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003258b  nop
0x18003258c  lea     rcx, [rbp+930h+var_5B0]; this
0x180032593  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x180032598  nop
0x180032599  jmp     short loc_1800325CB
0x18003259b  mov     [rbp+930h+var_92C], ebx
0x18003259e  lea     rdx, [rbp+930h+var_4E0]; struct tpm12class::TPMW82B_BUFFER *
0x1800325a5  lea     rcx, [rbp+930h+var_928]; this
0x1800325a9  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x1800325ae  mov     edi, eax
0x1800325b0  test    eax, eax
0x1800325b2  jns     short loc_1800325BB
0x1800325b4  mov     edx, 0BEBh
0x1800325b9  jmp     short loc_180032579
0x1800325bb  lea     rcx, [rbp+930h+var_5B0]; this
0x1800325c2  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x1800325c7  nop
0x1800325c8  mov     edi, r12d
0x1800325cb  lea     rcx, [rbp+930h+var_840]; this
0x1800325d2  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800325d7  test    edi, edi
0x1800325d9  jns     short loc_180032616
0x1800325db  mov     rcx, [rbp+938h]; this
0x1800325e2  mov     r9d, edi; char *
0x1800325e5  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800325ec  mov     edx, 79Fh; void *
0x1800325f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800325f6  nop
0x1800325f7  mov     [rsp+0A30h+var_A08], r12b
0x1800325fc  lea     rcx, [rsp+0A30h+var_A10]
0x180032601  call    _lambda_54170be0847a6a8274d539ec808565ce___operator__
0x180032606  nop
0x180032607  lea     rcx, [rsp+0A30h+var_9F0]; this
0x18003260c  call    ??1TPMW8_Load@tpm12class@@UEAA@XZ; tpm12class::TPMW8_Load::~TPMW8_Load(void)
0x180032611  jmp     loc_18003330D
0x180032616  cmp     [rbp+930h+var_92C], ebx
0x180032619  jz      short loc_18003264E
0x18003261b  mov     rcx, [rbp+938h]; this
0x180032622  mov     edi, 8029040Eh
0x180032627  mov     r9d, edi; char *
0x18003262a  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180032631  mov     edx, 7A1h; void *
0x180032636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003263b  nop
0x18003263c  mov     [rsp+0A30h+var_A08], r12b
0x180032641  lea     rcx, [rsp+0A30h+var_A10]
0x180032646  call    _lambda_54170be0847a6a8274d539ec808565ce___operator__
0x18003264b  nop
0x18003264c  jmp     short loc_180032607
0x18003264e  lea     rdx, [rbp+930h+var_658]; struct tpm12class::TPMW82B_BUFFER *
0x180032655  lea     rcx, [rbp+930h+var_8E0]; this
0x180032659  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x18003265e  mov     edi, eax
0x180032660  test    eax, eax
0x180032662  jns     short loc_180032695
0x180032664  mov     rcx, [rbp+938h]; this
0x18003266b  mov     r9d, eax; char *
0x18003266e  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180032675  mov     edx, 7A3h; void *
0x18003267a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003267f  nop
0x180032680  mov     [rsp+0A30h+var_A08], r12b
0x180032685  lea     rcx, [rsp+0A30h+var_A10]
0x18003268a  call    _lambda_54170be0847a6a8274d539ec808565ce___operator__
0x18003268f  nop
0x180032690  jmp     loc_180032607
0x180032695  mov     rbx, [rbp+930h+var_898]
0x18003269c  mov     rax, [rbp+930h+var_610]
0x1800326a3  mov     [rbp+930h+var_898], rax
0x1800326aa  xor     edx, edx; void *
0x1800326ac  lea     rcx, [rsp+0A30h+var_9F0]; this
0x1800326b1  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1800326b6  mov     edi, eax
0x1800326b8  mov     [rbp+930h+var_898], rbx
0x1800326bf  test    eax, eax
0x1800326c1  jns     short loc_1800326F4
0x1800326c3  mov     rcx, [rbp+938h]; this
0x1800326ca  mov     r9d, eax; char *
0x1800326cd  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800326d4  mov     edx, 7ABh; void *
0x1800326d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800326de  nop
0x1800326df  mov     [rsp+0A30h+var_A08], r12b
0x1800326e4  lea     rcx, [rsp+0A30h+var_A10]
0x1800326e9  call    _lambda_54170be0847a6a8274d539ec808565ce___operator__
0x1800326ee  nop
0x1800326ef  jmp     loc_180032607
0x1800326f4  mov     dword ptr [rsp+0A30h+Size], r12d
0x1800326f9  lea     r9, [rsp+0A30h+Size]; unsigned int *
0x1800326fe  xor     r8d, r8d; unsigned int
0x180032701  xor     edx, edx; unsigned __int8 *
0x180032703  mov     rcx, [rbp+930h+var_608]; this
0x18003270a  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x18003270f  mov     edi, eax
0x180032711  test    eax, eax
0x180032713  jns     short loc_180032746
0x180032715  mov     rcx, [rbp+938h]; this
0x18003271c  mov     r9d, eax; char *
0x18003271f  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180032726  mov     edx, 7B4h; void *
0x18003272b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032730  nop
0x180032731  mov     [rsp+0A30h+var_A08], r12b
0x180032736  lea     rcx, [rsp+0A30h+var_A10]
0x18003273b  call    _lambda_54170be0847a6a8274d539ec808565ce___operator__
0x180032740  nop
  ... truncated ...
```
