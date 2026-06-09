# TokenInfoSerializeHelper::DeserializeUserInfo(AadContextFunctions *,CJsonObject *,_APPLUGIN_USER_INFO * *)

- ea: `0x1800354b4`
- end: `0x180035bdd`
- name: `?DeserializeUserInfo@TokenInfoSerializeHelper@@CAJPEAVAadContextFunctions@@PEAVCJsonObject@@PEAPEAU_APPLUGIN_USER_INFO@@@Z`
- size: `1833`
- prototype: `__int64 __fastcall(struct AadContextFunctions *this, struct CJsonObject *, struct _APPLUGIN_USER_INFO **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034590`

## callees

- `0x180004a24`
- `0x180007a90`
- `0x180007df8`
- `0x1800090d0`
- `0x18000a300`
- `0x1800354b4`
- `0x18003694c`
- `0x180036b3c`
- `0x180071e14`
- `0x180076228`
- `0x180079fdc`
- `0x18007a070`
- `0x18007a0fc`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035afd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035b14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035afd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035b14`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800355b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800356a4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800355b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800356a4`

## string_xrefs

- `0x18003559d`: `PrimarySid`
- `0x18003560f`: `GroupSids`
- `0x180035985`: `PublicInfoUtcTokenExpiryLow`
- `0x18003599c`: `PublicInfoUtcTokenExpiryHigh`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall TokenInfoSerializeHelper::DeserializeUserInfo(
        struct AadContextFunctions *this,
        struct CJsonObject *a2,
        struct _APPLUGIN_USER_INFO **a3)
{
  char *v6; // r15
  unsigned int v7; // r12d
  _DWORD *v8; // rsi
  double JsonDataAsNumber; // xmm6_8
  signed int LastError; // ebx
  struct CJsonArray *JsonDataAsArray; // rax
  struct CJsonArray *v12; // r13
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // rax
  _DWORD *v16; // rdx
  LPCWSTR *v17; // rcx
  PSID *v18; // rdx
  char v19; // r13
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // ebx
  _DWORD *v25; // rax
  int v26; // ebx
  __int64 v27; // rax
  __int64 i; // r14
  __int64 v30; // [rsp+28h] [rbp-E0h]
  __int64 v31; // [rsp+38h] [rbp-D0h]
  int v32; // [rsp+38h] [rbp-D0h]
  PSID Sid; // [rsp+88h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-78h] BYREF
  __int64 v35; // [rsp+98h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-40h] BYREF
  LPCWSTR StringSid; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-30h] BYREF
  void *Source[2]; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v46; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v47; // [rsp+108h] [rbp+0h] BYREF
  __int64 v48; // [rsp+118h] [rbp+10h]
  __int128 v49; // [rsp+120h] [rbp+18h] BYREF
  __int64 v51; // [rsp+1A0h] [rbp+98h] BYREF

  v47 = 0;
  v48 = 0;
  v46 = 0;
  Sid = 0;
  v6 = 0;
  v7 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&StringSid);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v34);
  v49 = 0;
  v8 = 0;
  *(_OWORD *)Source = 0;
  *a3 = 0;
  JsonDataAsNumber = WebResponseHelper::GetJsonDataAsNumber(a2, L"Version");
  WebResponseHelper::GetJsonDataAsString(a2, L"UniqueId", &v43);
  WebResponseHelper::GetJsonDataAsString(a2, L"PrimarySid", &StringSid);
  if ( *((_DWORD *)StringSid - 4) && !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    LastError = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    if ( LastError < 0 )
    {
      LODWORD(v31) = 1211;
      goto LABEL_46;
    }
  }
  JsonDataAsArray = WebResponseHelper::GetJsonDataAsArray(a2, L"GroupSids");
  v12 = JsonDataAsArray;
  if ( JsonDataAsArray )
  {
    v7 = *((_DWORD *)JsonDataAsArray + 4);
    if ( v7 )
    {
      v6 = (char *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, __int64))(*(_QWORD *)this + 8LL))(
                     this,
                     64,
                     8LL * v7);
      memset_0(v6, 0, 8LL * v7);
      v14 = 0;
      v15 = *(_QWORD *)v12;
      v45 = *(_QWORD *)v12;
      while ( v15 )
      {
        v16 = *(_DWORD **)ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(
                            v13,
                            v15);
        if ( v16 )
        {
          v17 = (LPCWSTR *)(v16 + 2);
          if ( *v16 != 3 )
            v17 = 0;
          if ( v17 )
          {
            v18 = (PSID *)&v6[8 * v14++];
            LODWORD(v51) = v14;
            if ( !ConvertStringSidToSidW(*v17, v18) )
            {
              if ( (int)GetLastError() > 0 )
                LastError = (unsigned __int16)GetLastError() | 0xC0070000;
              else
                LastError = GetLastError();
              if ( LastError < 0 )
              {
                LODWORD(v31) = 1236;
                goto LABEL_46;
              }
              v14 = v51;
            }
          }
        }
        ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v17, &v45);
        v15 = v45;
      }
    }
  }
  v19 = 0;
  WebResponseHelper::GetJsonDataAsString(a2, L"DisplayName", &v41);
  WebResponseHelper::GetJsonDataAsString(a2, L"FirstName", &v40);
  WebResponseHelper::GetJsonDataAsString(a2, L"LastName", &v39);
  WebResponseHelper::GetJsonDataAsString(a2, L"Identity", &v38);
  WebResponseHelper::GetJsonDataAsString(a2, L"DownlevelName", &v37);
  WebResponseHelper::GetJsonDataAsString(a2, L"DomainNetbiosName", &v36);
  WebResponseHelper::GetJsonDataAsString(a2, L"DomainDnsName", &v35);
  v20 = v47;
  if ( *(_DWORD *)(v37 - 16) )
    v20 = v37;
  *(_QWORD *)&v47 = v20;
  v21 = *((_QWORD *)&v47 + 1);
  if ( *(_DWORD *)(v36 - 16) )
    v21 = v36;
  *((_QWORD *)&v47 + 1) = v21;
  v22 = v48;
  if ( *(_DWORD *)(v35 - 16) )
    v22 = v35;
  v48 = v22;
  WebResponseHelper::GetJsonDataAsString(a2, L"PasswordChangeUrl", &v34);
  v23 = v46;
  if ( *(_DWORD *)(v34 - 16) )
    v23 = v34;
  *(_QWORD *)&v46 = v23;
  DWORD2(v46) = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"PasswordExpiryTimeLow");
  HIDWORD(v46) = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"PasswordExpiryTimeHigh");
  LODWORD(v49) = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"PublicInfoPublicKeyType");
  if ( (_DWORD)v49 == 6 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
    WebResponseHelper::GetJsonDataAsString(a2, L"PublicInfoPublicKey", &v51);
    if ( *(_DWORD *)(v51 - 16) )
    {
      v24 = StringUtility::Base64Decode(this, &v51, Source);
      if ( v24 < 0 )
      {
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v24, "serializetokeninfo.cpp", 1291, "HRESULT", &base);
        LastError = v24 & 0xAFFFFFFF | 0x40000000;
LABEL_35:
        CSecureString::~CSecureString((CSecureString *)&v51);
        goto LABEL_47;
      }
      v25 = (_DWORD *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)this + 8LL))(
                        this,
                        64,
                        (unsigned int)(LODWORD(Source[0]) + 20));
      v8 = v25;
      if ( !v25 )
      {
        LastError = -1073741801;
        v32 = 1298;
LABEL_39:
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, LastError, "serializetokeninfo.cpp", v32, "NTSTATUS", &base);
        goto LABEL_35;
      }
      *v25 = LODWORD(Source[0]) + 20;
      v25[3] = 20;
      v25[4] = Source[0];
      v25[1] = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"PublicInfoUtcTokenExpiryLow");
      v8[2] = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"PublicInfoUtcTokenExpiryHigh");
      if ( memcpy_s_0((char *)v8 + (unsigned int)v8[3], (unsigned int)v8[4], Source[1], (unsigned int)v8[4]) )
      {
        LastError = -1073741595;
        v32 = 1313;
        goto LABEL_39;
      }
      *((_QWORD *)&v49 + 1) = v8;
      v19 = 1;
    }
    CSecureString::~CSecureString((CSecureString *)&v51);
  }
  v26 = (int)WebResponseHelper::GetJsonDataAsNumber(a2, L"Flags");
  v27 = (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)this + 48LL))(this);
  LastError = (*(__int64 (__fastcall **)(_QWORD, PSID, _QWORD, char *, __int64, __int64, __int64, __int64, __int64, __int128 *, __int128 *, unsigned __int64, int, struct _APPLUGIN_USER_INFO **))(v27 + 48))(
                (unsigned int)(int)JsonDataAsNumber,
                Sid,
                v7,
                v6,
                v41,
                v43,
                v40,
                v39,
                v38,
                &v47,
                &v46,
                (unsigned __int64)&v49 & -(__int64)(v19 != 0),
                v26,
                a3);
  if ( LastError >= 0 )
    goto LABEL_47;
  LODWORD(v31) = 1338;
LABEL_46:
  LODWORD(v30) = LastError;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v30, "serializetokeninfo.cpp", v31, "NTSTATUS", &base);
LABEL_47:
  if ( Sid )
    LocalFree(Sid);
  if ( v6 )
  {
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      LocalFree(*(HLOCAL *)&v6[8 * i]);
    (*(void (__fastcall **)(struct AadContextFunctions *, char *))(*(_QWORD *)this + 16LL))(this, v6);
  }
  if ( v8 )
    (*(void (__fastcall **)(struct AadContextFunctions *, _DWORD *))(*(_QWORD *)this + 16LL))(this, v8);
  AadContextFunctions::LocalFreeApBlob(this, (struct _AP_BLOB *)Source);
  CSecureString::~CSecureString((CSecureString *)&v34);
  CSecureString::~CSecureString((CSecureString *)&v35);
  CSecureString::~CSecureString((CSecureString *)&v36);
  CSecureString::~CSecureString((CSecureString *)&v37);
  CSecureString::~CSecureString((CSecureString *)&v38);
  CSecureString::~CSecureString((CSecureString *)&v39);
  CSecureString::~CSecureString((CSecureString *)&v40);
  CSecureString::~CSecureString((CSecureString *)&v41);
  CSecureString::~CSecureString((CSecureString *)&StringSid);
  CSecureString::~CSecureString((CSecureString *)&v43);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800354b4  mov     rax, rsp
0x1800354b7  mov     [rax+8], rbx
0x1800354bb  mov     [rax+18h], r8
0x1800354bf  push    rbp
0x1800354c0  push    rsi
0x1800354c1  push    rdi
0x1800354c2  push    r12
0x1800354c4  push    r13
0x1800354c6  push    r14
0x1800354c8  push    r15
0x1800354ca  lea     rbp, [rax-78h]
0x1800354ce  sub     rsp, 140h
0x1800354d5  movaps  xmmword ptr [rax-48h], xmm6
0x1800354d9  mov     rbx, r8
0x1800354dc  mov     r14, rdx
0x1800354df  mov     rdi, rcx
0x1800354e2  xorps   xmm0, xmm0
0x1800354e5  xor     eax, eax
0x1800354e7  movups  [rbp+70h+var_70], xmm0
0x1800354eb  mov     [rbp+70h+var_60], rax
0x1800354ef  movups  [rbp+70h+var_80], xmm0
0x1800354f3  mov     [rbp+70h+Sid], rax
0x1800354f7  xor     r15d, r15d
0x1800354fa  xor     r12d, r12d
0x1800354fd  lea     rcx, [rbp+70h+var_A0]; void *
0x180035501  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035506  nop
0x180035507  lea     rcx, [rbp+70h+StringSid]; void *
0x18003550b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035510  nop
0x180035511  lea     rcx, [rbp+70h+var_B0]; void *
0x180035515  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003551a  nop
0x18003551b  lea     rcx, [rbp+70h+var_B8]; void *
0x18003551f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035524  nop
0x180035525  lea     rcx, [rbp+70h+var_C0]; void *
0x180035529  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003552e  nop
0x18003552f  lea     rcx, [rbp+70h+var_C8]; void *
0x180035533  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035538  nop
0x180035539  lea     rcx, [rbp+70h+var_D0]; void *
0x18003553d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035542  nop
0x180035543  lea     rcx, [rbp+70h+var_D8]; void *
0x180035547  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003554c  nop
0x18003554d  lea     rcx, [rbp+70h+var_E0]; void *
0x180035551  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035556  nop
0x180035557  lea     rcx, [rbp+70h+var_E8]; void *
0x18003555b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035560  nop
0x180035561  xorps   xmm0, xmm0
0x180035564  movups  [rbp+70h+var_58], xmm0
0x180035568  xor     esi, esi
0x18003556a  xorps   xmm1, xmm1
0x18003556d  movups  xmmword ptr [rbp+70h+Source], xmm1
0x180035571  mov     [rbx], rsi
0x180035574  lea     rdx, aVersion_0; "Version"
0x18003557b  mov     rcx, r14; struct CJsonObject *
0x18003557e  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x180035583  movaps  xmm6, xmm0
0x180035586  lea     r8, [rbp+70h+var_A0]
0x18003558a  lea     rdx, aUniqueid; "UniqueId"
0x180035591  mov     rcx, r14
0x180035594  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180035599  lea     r8, [rbp+70h+StringSid]
0x18003559d  lea     rdx, aPrimarysid; "PrimarySid"
0x1800355a4  mov     rcx, r14
0x1800355a7  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800355ac  mov     rcx, [rbp+70h+StringSid]; StringSid
0x1800355b0  cmp     [rcx-10h], esi
0x1800355b3  jz      short loc_18003560F
0x1800355b5  lea     rdx, [rbp+70h+Sid]; Sid
0x1800355b9  call    cs:__imp_ConvertStringSidToSidW
0x1800355bf  test    eax, eax
0x1800355c1  jnz     short loc_18003560F
0x1800355c3  call    cs:__imp_GetLastError
0x1800355c9  test    eax, eax
0x1800355cb  jg      short loc_1800355D7
0x1800355cd  call    cs:__imp_GetLastError
0x1800355d3  mov     ebx, eax
0x1800355d5  jmp     short loc_1800355E6
0x1800355d7  call    cs:__imp_GetLastError
0x1800355dd  movzx   ebx, ax
0x1800355e0  or      ebx, 0C0070000h
0x1800355e6  test    ebx, ebx
0x1800355e8  jns     short loc_18003560F
0x1800355ea  lea     rax, base
0x1800355f1  mov     [rsp+170h+var_130], rax
0x1800355f6  lea     rax, aNtstatus; "NTSTATUS"
0x1800355fd  mov     [rsp+170h+var_138], rax
0x180035602  mov     dword ptr [rsp+170h+var_140], 4BBh
0x18003560a  jmp     loc_180035ACE
0x18003560f  lea     rdx, aGroupsids; "GroupSids"
0x180035616  mov     rcx, r14; struct CJsonObject *
0x180035619  call    ?GetJsonDataAsArray@WebResponseHelper@@SAPEAVCJsonArray@@PEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsArray(CJsonObject *,ushort const *)
0x18003561e  mov     r13, rax
0x180035621  test    rax, rax
0x180035624  jz      loc_1800356F1
0x18003562a  mov     r12d, [rax+10h]
0x18003562e  test    r12d, r12d
0x180035631  jz      loc_1800356F1
0x180035637  mov     ebx, r12d
0x18003563a  shl     rbx, 3
0x18003563e  mov     rcx, [rdi]
0x180035641  mov     rax, [rcx+8]
0x180035645  mov     r8, rbx
0x180035648  mov     edx, 40h ; '@'
0x18003564d  mov     rcx, rdi
0x180035650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035655  mov     r15, rax
0x180035658  mov     r8, rbx; Size
0x18003565b  xor     edx, edx; Val
0x18003565d  mov     rcx, rax; void *
0x180035660  call    memset_0
0x180035665  xor     ebx, ebx
0x180035667  mov     rax, [r13+0]
0x18003566b  mov     [rbp+70h+var_88], rax
0x18003566f  jmp     short loc_1800356EC
0x180035671  mov     rdx, rax
0x180035674  call    ?GetAt@?$CAtlList@V?$CAutoPtr@VCJsonValue@@@ATL@@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@QEBAAEBV?$CAutoPtr@VCJsonValue@@@2@PEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(__POSITION *)
0x180035679  mov     rdx, [rax]
0x18003567c  test    rdx, rdx
0x18003567f  jz      short loc_1800356DF
0x180035681  lea     rcx, [rdx+8]
0x180035685  xor     eax, eax
0x180035687  cmp     dword ptr [rdx], 3
0x18003568a  cmovnz  rcx, rax
0x18003568e  test    rcx, rcx
0x180035691  jz      short loc_1800356DF
0x180035693  mov     eax, ebx
0x180035695  lea     rdx, [r15+rax*8]; Sid
0x180035699  inc     ebx
0x18003569b  mov     dword ptr [rbp+70h+arg_18], ebx
0x1800356a1  mov     rcx, [rcx]; StringSid
0x1800356a4  call    cs:__imp_ConvertStringSidToSidW
0x1800356aa  test    eax, eax
0x1800356ac  jnz     short loc_1800356DF
0x1800356ae  call    cs:__imp_GetLastError
0x1800356b4  test    eax, eax
0x1800356b6  jg      short loc_1800356C2
0x1800356b8  call    cs:__imp_GetLastError
0x1800356be  mov     ebx, eax
0x1800356c0  jmp     short loc_1800356D1
0x1800356c2  call    cs:__imp_GetLastError
0x1800356c8  movzx   ebx, ax
0x1800356cb  or      ebx, 0C0070000h
0x1800356d1  test    ebx, ebx
0x1800356d3  js      loc_1800358D7
0x1800356d9  mov     ebx, dword ptr [rbp+70h+arg_18]
0x1800356df  lea     rdx, [rbp+70h+var_88]
0x1800356e3  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x1800356e8  mov     rax, [rbp+70h+var_88]
0x1800356ec  test    rax, rax
0x1800356ef  jnz     short loc_180035671
0x1800356f1  xor     r13b, r13b
0x1800356f4  lea     r8, [rbp+70h+var_B0]
0x1800356f8  lea     rdx, aDisplayname; "DisplayName"
0x1800356ff  mov     rcx, r14
0x180035702  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180035707  lea     r8, [rbp+70h+var_B8]
0x18003570b  lea     rdx, aFirstname; "FirstName"
0x180035712  mov     rcx, r14
0x180035715  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003571a  lea     r8, [rbp+70h+var_C0]
0x18003571e  lea     rdx, aLastname; "LastName"
0x180035725  mov     rcx, r14
0x180035728  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003572d  lea     r8, [rbp+70h+var_C8]
0x180035731  lea     rdx, aIdentity; "Identity"
0x180035738  mov     rcx, r14
0x18003573b  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180035740  lea     r8, [rbp+70h+var_D0]
0x180035744  lea     rdx, aDownlevelname; "DownlevelName"
0x18003574b  mov     rcx, r14
0x18003574e  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180035753  lea     r8, [rbp+70h+var_D8]
0x180035757  lea     rdx, aDomainnetbiosn; "DomainNetbiosName"
0x18003575e  mov     rcx, r14
0x180035761  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180035766  lea     r8, [rbp+70h+var_E0]
0x18003576a  lea     rdx, aDomaindnsname; "DomainDnsName"
0x180035771  mov     rcx, r14
0x180035774  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180035779  mov     rcx, qword ptr [rbp+70h+var_70]
0x18003577d  mov     rax, [rbp+70h+var_D0]
0x180035781  xor     ebx, ebx
0x180035783  cmp     [rax-10h], ebx
0x180035786  cmovnz  rcx, rax
0x18003578a  mov     qword ptr [rbp+70h+var_70], rcx
0x18003578e  mov     rcx, qword ptr [rbp+70h+var_70+8]
0x180035792  mov     rax, [rbp+70h+var_D8]
0x180035796  cmp     [rax-10h], ebx
0x180035799  cmovnz  rcx, rax
0x18003579d  mov     qword ptr [rbp+70h+var_70+8], rcx
0x1800357a1  mov     rcx, [rbp+70h+var_60]
0x1800357a5  mov     rax, [rbp+70h+var_E0]
0x1800357a9  cmp     [rax-10h], ebx
0x1800357ac  cmovnz  rcx, rax
0x1800357b0  mov     [rbp+70h+var_60], rcx
0x1800357b4  lea     r8, [rbp+70h+var_E8]
0x1800357b8  lea     rdx, aPasswordchange; "PasswordChangeUrl"
0x1800357bf  mov     rcx, r14
0x1800357c2  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800357c7  mov     rcx, qword ptr [rbp+70h+var_80]
0x1800357cb  mov     rax, [rbp+70h+var_E8]
0x1800357cf  cmp     [rax-10h], ebx
0x1800357d2  cmovnz  rcx, rax
0x1800357d6  mov     qword ptr [rbp+70h+var_80], rcx
0x1800357da  lea     rdx, aPasswordexpiry_0; "PasswordExpiryTimeLow"
0x1800357e1  mov     rcx, r14; struct CJsonObject *
0x1800357e4  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x1800357e9  cvttsd2si rax, xmm0
0x1800357ee  mov     dword ptr [rbp+70h+var_80+8], eax
0x1800357f1  lea     rdx, aPasswordexpiry; "PasswordExpiryTimeHigh"
0x1800357f8  mov     rcx, r14; struct CJsonObject *
0x1800357fb  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x180035800  cvttsd2si rax, xmm0
0x180035805  mov     dword ptr [rbp+70h+var_80+0Ch], eax
0x180035808  lea     rdx, aPublicinfopubl; "PublicInfoPublicKeyType"
0x18003580f  mov     rcx, r14; struct CJsonObject *
0x180035812  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x180035817  cvttsd2si rax, xmm0
0x18003581c  mov     dword ptr [rbp+70h+var_58], eax
0x18003581f  cmp     eax, 6
0x180035822  jnz     loc_180035A09
0x180035828  lea     rcx, [rbp+70h+arg_18]; void *
0x18003582f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180035834  nop
0x180035835  lea     r8, [rbp+70h+arg_18]
0x18003583c  lea     rdx, aPublicinfopubl_0; "PublicInfoPublicKey"
0x180035843  mov     rcx, r14
0x180035846  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003584b  mov     rax, [rbp+70h+arg_18]
0x180035852  cmp     [rax-10h], ebx
0x180035855  jz      loc_1800359FD
0x18003585b  lea     r8, [rbp+70h+Source]
0x18003585f  lea     rdx, [rbp+70h+arg_18]
0x180035866  mov     rcx, rdi
0x180035869  call    ?Base64Decode@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@_N@Z; StringUtility::Base64Decode(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,bool)
0x18003586e  mov     ebx, eax
0x180035870  test    eax, eax
0x180035872  jns     loc_1800358FC
0x180035878  lea     rax, base
0x18003587f  mov     [rsp+170h+var_130], rax
0x180035884  lea     rax, aHresult; "HRESULT"
0x18003588b  mov     [rsp+170h+var_138], rax
0x180035890  mov     dword ptr [rsp+170h+var_140], 50Bh
0x180035898  lea     rax, aOnecoreuapDsEx_11+21h; "serializetokeninfo.cpp"
0x18003589f  mov     [rsp+170h+var_148], rax
0x1800358a4  mov     dword ptr [rsp+170h+var_150], ebx
0x1800358a8  mov     ecx, 2
0x1800358ad  mov     r9d, ecx
0x1800358b0  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800358b7  xor     edx, edx
0x1800358b9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800358be  btr     ebx, 1Ch
0x1800358c2  bts     ebx, 1Eh
0x1800358c6  lea     rcx, [rbp+70h+arg_18]; this
0x1800358cd  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1800358d2  jmp     loc_180035AF4
0x1800358d7  lea     rax, base
0x1800358de  mov     [rsp+170h+var_130], rax
0x1800358e3  lea     rax, aNtstatus; "NTSTATUS"
0x1800358ea  mov     [rsp+170h+var_138], rax
0x1800358ef  mov     dword ptr [rsp+170h+var_140], 4D4h
0x1800358f7  jmp     loc_180035ACE
0x1800358fc  mov     rcx, [rdi]
0x1800358ff  mov     r8d, dword ptr [rbp+70h+Source]
0x180035903  add     r8d, 14h
0x180035907  mov     rax, [rcx+8]
0x18003590b  mov     edx, 40h ; '@'
0x180035910  mov     rcx, rdi
0x180035913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035918  mov     rsi, rax
0x18003591b  test    rax, rax
0x18003591e  jnz     short loc_180035970
0x180035920  mov     ebx, 0C0000017h
0x180035925  lea     rax, base
0x18003592c  mov     [rsp+170h+var_130], rax
0x180035931  lea     rax, aNtstatus; "NTSTATUS"
0x180035938  mov     [rsp+170h+var_138], rax
0x18003593d  mov     dword ptr [rsp+170h+var_140], 512h
0x180035945  lea     rax, aOnecoreuapDsEx_11+21h; "serializetokeninfo.cpp"
0x18003594c  mov     [rsp+170h+var_148], rax
0x180035951  mov     dword ptr [rsp+170h+var_150], ebx
0x180035955  mov     ecx, 2
0x18003595a  mov     r9d, ecx
0x18003595d  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180035964  xor     edx, edx
0x180035966  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003596b  jmp     loc_1800358C6
0x180035970  mov     eax, dword ptr [rbp+70h+Source]
0x180035973  add     eax, 14h
0x180035976  mov     [rsi], eax
0x180035978  mov     dword ptr [rsi+0Ch], 14h
0x18003597f  mov     eax, dword ptr [rbp+70h+Source]
  ... truncated ...
```
