# CSoftLandingXmlParser::BuildQueryList(IStream *,IObjectCollection *)

- ea: `0x180119450`
- end: `0x180119eca`
- name: `?BuildQueryList@CSoftLandingXmlParser@@UEAAJPEAUIStream@@PEAUIObjectCollection@@@Z`
- size: `2682`
- prototype: `__int64 __fastcall(CSoftLandingXmlParser *__hidden this, struct IStream *, struct IObjectCollection *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009dd0`
- `0x1800378dc`
- `0x18003a2c0`
- `0x180055128`
- `0x180119450`
- `0x180119ed0`
- `0x180119f18`
- `0x180119f78`
- `0x180119fc0`
- `0x180142e10`
- `0x180330580`
- `0x180339734`
- `0x180343a1c`
- `0x180343b08`
- `0x180343bcc`
- `0x180343d0c`
- `0x18034400c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801197f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011989d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801198cd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801198fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180119949`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180119983`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801199aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801199cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801199f7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801197f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011989d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801198cd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801198fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180119949`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180119983`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801199aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801199cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801199f7`
- `XmlLite!CreateXmlReader` at `0x18011950b`
- `XmlLite!CreateXmlReader` at `0x18011950b`

## string_xrefs

- `0x18011952b`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x18011959b`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x18011960c`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180119681`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180119bed`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180119c60`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180119d87`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180119df4`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180119488`: `ParseXML`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSoftLandingXmlParser::BuildQueryList(
        CSoftLandingXmlParser *this,
        struct IStream *a2,
        struct IObjectCollection *a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // r14d
  int v10; // esi
  int v11; // eax
  _BYTE *v12; // rdi
  int v13; // eax
  unsigned int (*i)(void); // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // r9
  CSoftLandingXmlParser *v18; // rcx
  __int64 (__fastcall *v19)(_BYTE *, GUID *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-C8h] BYREF
  struct IObjectCollection *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  LPCWCH v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+5Ch] [rbp-A4h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  LPCWCH v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  LPCWCH lpString2; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[4]; // [rsp+88h] [rbp-78h] BYREF
  char v38; // [rsp+A8h] [rbp-58h]
  _QWORD v39[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v26 = a3;
  wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v39);
  v39[0] = &SoftLandingTelemetry::ParseXML::`vftable';
  SoftLandingTelemetry::ParseXML::StartActivity((SoftLandingTelemetry::ParseXML *)v39);
  v24 = -2147467259;
  ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
  v37[1] = &v24;
  v37[2] = &v26;
  v37[3] = v39;
  v38 = 1;
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
  v4 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v5 = v4;
  v24 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v6 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, a2);
  v5 = v6;
  v24 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v8 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 6, 200);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v9 = 0;
  v31 = 0;
  v10 = 0;
  v27 = 0;
  do
  {
    while ( 1 )
    {
LABEL_18:
      if ( v24 < 0 || (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 200LL))(ppvObject) )
        goto LABEL_105;
      v35 = 0;
      v11 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v35);
      v24 = v11;
      if ( v11 < 0 || v11 == 1 || !v35 )
      {
        if ( v9 > 0 && !v10 )
          goto LABEL_106;
        SoftLandingTelemetry::MismatchedElements<int &,int &>(&v31, &v27);
LABEL_105:
        if ( v24 == 1 )
LABEL_106:
          v24 = 0;
        v5 = v24;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
        if ( v24 < 0 )
          ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
        goto LABEL_109;
      }
      v30 = 0;
      if ( v35 == 1 )
        break;
      if ( v35 == 15 )
      {
        v27 = --v10;
        if ( v10 < 0 )
        {
          SoftLandingTelemetry::MismatchedElements<int &,int &>(&v31, &v27);
          v5 = -1072894419;
          v24 = -1072894419;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
          if ( v24 < 0 )
            ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
          goto LABEL_109;
        }
      }
    }
    v31 = ++v9;
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
      v27 = ++v10;
    lpString2 = 0;
  }
  while ( (*(int (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 112LL))(ppvObject, &lpString2, &v30) < 0 );
  Microsoft::WRL::Details::Make<CSoftLandingQueryEntry,>(v37);
  v12 = (_BYTE *)v37[0];
  if ( !v37[0] )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v29 = 0;
  v13 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 192LL))(ppvObject, &v29);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    if ( v12 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  if ( CompareStringOrdinal(L"Root", -1, lpString2, -1, 1) == 2 )
  {
    if ( v29 )
    {
      SoftLandingTelemetry::MultipleRootElements();
      v5 = -1072894419;
      v24 = -1072894419;
      if ( v12 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
      if ( v24 < 0 )
        ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
      goto LABEL_109;
    }
    v12[16] = 1;
  }
  else if ( !v29 )
  {
    SoftLandingTelemetry::NoRootElement();
    v5 = -1072894419;
    v24 = -1072894419;
    if ( v12 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  for ( i = *(unsigned int (**)(void))(*(_QWORD *)ppvObject + 64LL);
        !i();
        i = *(unsigned int (**)(void))(*(_QWORD *)ppvObject + 72LL) )
  {
    v28 = 0;
    v33 = 0;
    if ( (*(int (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 112LL))(ppvObject, &v28, &v30) >= 0
      && (*(int (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 128LL))(ppvObject, &v33, &v30) >= 0 )
    {
      if ( CompareStringOrdinal(L"Id", -1, v28, -1, 1) == 2 )
      {
        v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v12 + 40);
LABEL_45:
        _AllocString<CTCoAllocPolicy>(v16, v15, v33, v17);
        continue;
      }
      if ( CompareStringOrdinal(L"Class", -1, v28, -1, 1) == 2 )
      {
        v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v12 + 32);
        goto LABEL_45;
      }
      if ( CompareStringOrdinal(L"Type", -1, v28, -1, 1) == 2 )
      {
        v32 = -1;
        if ( CSoftLandingXmlParser::_UIAControlStringToValue(v18, v33, &v32) >= 0 )
          *((_DWORD *)v12 + 5) = v32;
      }
      else
      {
        if ( CompareStringOrdinal(L"Name", -1, v28, -1, 1) == 2 )
        {
          v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v12 + 24);
          goto LABEL_45;
        }
        if ( CompareStringOrdinal(L"IgnoreCase", -1, v28, -1, 1) == 2 )
        {
          v12[17] = CompareStringOrdinal(L"true", -1, v33, -1, 1) == 2;
        }
        else
        {
          if ( CompareStringOrdinal(L"UseRegExForId", -1, v28, -1, 1) != 2 )
          {
            SoftLandingTelemetry::UnknownAttribute<unsigned short const * &>(&v28);
            v5 = -1072894419;
            v24 = -1072894419;
            if ( v12 )
              (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
            if ( v24 < 0 )
              ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
            goto LABEL_109;
          }
          v12[18] = CompareStringOrdinal(L"true", -1, v33, -1, 1) == 2;
        }
      }
    }
  }
  if ( v24 < 0 || (*(unsigned __int8 (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 24LL))(v12) )
  {
    SoftLandingTelemetry::EmptyQuery();
    v5 = -1072894419;
    v24 = -1072894419;
    if ( v12 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
  }
  else
  {
    v34 = 0;
    v19 = **(__int64 (__fastcall ***)(_BYTE *, GUID *, __int64 *))v12;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v20 = v19(v12, &GUID_00000000_0000_0000_c000_000000000046, &v34);
    v5 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      if ( v12 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
      if ( v24 < 0 )
        ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    }
    else
    {
      v21 = ((__int64 (__fastcall *)(struct IObjectCollection *, __int64))v26->lpVtbl->AddObject)(v26, v34);
      v5 = v21;
      if ( v21 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        if ( v12 )
        {
          v37[0] = 0;
          (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        goto LABEL_18;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      if ( v12 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
      if ( v24 < 0 )
        ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    }
  }
LABEL_109:
  wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39);
  SoftLandingTelemetry::ParseXML::~ParseXML((SoftLandingTelemetry::ParseXML *)v39);
  return v5;
}

```

## disassembly

```asm
0x180119450  mov     [rsp-8+arg_0], rbx
0x180119455  push    rbp
0x180119456  push    rsi
0x180119457  push    rdi
0x180119458  push    r12
0x18011945a  push    r13
0x18011945c  push    r14
0x18011945e  push    r15
0x180119460  lea     rbp, [rsp-110h]
0x180119468  sub     rsp, 210h
0x18011946f  mov     rax, cs:__security_cookie
0x180119476  xor     rax, rsp
0x180119479  mov     [rbp+140h+var_40], rax
0x180119480  mov     rdi, rdx
0x180119483  mov     [rsp+240h+var_200], r8
0x180119488  lea     rdx, aParsexml; "ParseXML"
0x18011948f  lea     rcx, [rbp+140h+var_190]; struct wil::details::IFailureCallback *
0x180119493  call    ??0?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180119498  lea     rax, ??_7ParseXML@SoftLandingTelemetry@@6B@; const SoftLandingTelemetry::ParseXML::`vftable'
0x18011949f  mov     [rbp+140h+var_190], rax
0x1801194a3  lea     rcx, [rbp+140h+var_190]; this
0x1801194a7  call    ?StartActivity@ParseXML@SoftLandingTelemetry@@QEAAXXZ; SoftLandingTelemetry::ParseXML::StartActivity(void)
0x1801194ac  nop
0x1801194ad  mov     [rsp+240h+var_210], 80004005h
0x1801194b5  mov     rcx, [rsp+240h+var_200]
0x1801194ba  mov     rax, [rcx]
0x1801194bd  mov     rax, [rax+40h]
0x1801194c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801194c6  lea     rax, [rsp+240h+var_210]
0x1801194cb  mov     [rbp+140h+var_1B0], rax
0x1801194cf  lea     rax, [rsp+240h+var_200]
0x1801194d4  mov     [rbp+140h+var_1A8], rax
0x1801194d8  lea     rax, [rbp+140h+var_190]
0x1801194dc  mov     [rbp+140h+var_1A0], rax
0x1801194e0  mov     r13d, 1
0x1801194e6  mov     [rbp+140h+var_198], r13b
0x1801194ea  xor     r15d, r15d
0x1801194ed  mov     [rsp+240h+ppvObject], r15
0x1801194f2  lea     rcx, [rsp+240h+ppvObject]
0x1801194f7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801194fc  xor     r8d, r8d; pMalloc
0x1801194ff  lea     rdx, [rsp+240h+ppvObject]; ppvObject
0x180119504  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18011950b  call    cs:__imp_CreateXmlReader
0x180119512  nop     dword ptr [rax+rax+00h]
0x180119517  mov     ebx, eax
0x180119519  mov     [rsp+240h+var_210], eax
0x18011951d  test    eax, eax
0x18011951f  jns     short loc_180119573
0x180119521  mov     rcx, [rbp+148h]; this
0x180119528  mov     r9d, eax; char *
0x18011952b  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x180119532  lea     edx, [r13+17h]; void *
0x180119536  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011953b  nop
0x18011953c  lea     rcx, [rsp+240h+ppvObject]
0x180119541  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180119546  nop
0x180119547  mov     edx, [rsp+240h+var_210]
0x18011954b  test    edx, edx
0x18011954d  jns     short loc_180119564
0x18011954f  mov     rcx, [rsp+240h+var_200]
0x180119554  mov     rax, [rcx]
0x180119557  mov     rax, [rax+40h]
0x18011955b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119560  mov     edx, [rsp+240h+var_210]
0x180119564  lea     rcx, [rbp+140h+var_190]
0x180119568  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18011956d  nop
0x18011956e  jmp     loc_180119E94
0x180119573  mov     rcx, [rsp+240h+ppvObject]
0x180119578  mov     rax, [rcx]
0x18011957b  mov     rdx, rdi
0x18011957e  mov     rax, [rax+18h]
0x180119582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119587  mov     ebx, eax
0x180119589  mov     [rsp+240h+var_210], eax
0x18011958d  test    eax, eax
0x18011958f  jns     short loc_1801195E4
0x180119591  mov     rcx, [rbp+148h]; this
0x180119598  mov     r9d, eax; char *
0x18011959b  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x1801195a2  mov     edx, 19h; void *
0x1801195a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801195ac  nop
0x1801195ad  lea     rcx, [rsp+240h+ppvObject]
0x1801195b2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801195b7  nop
0x1801195b8  mov     edx, [rsp+240h+var_210]
0x1801195bc  test    edx, edx
0x1801195be  jns     short loc_1801195D5
0x1801195c0  mov     rcx, [rsp+240h+var_200]
0x1801195c5  mov     rax, [rcx]
0x1801195c8  mov     rax, [rax+40h]
0x1801195cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801195d1  mov     edx, [rsp+240h+var_210]
0x1801195d5  lea     rcx, [rbp+140h+var_190]
0x1801195d9  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1801195de  nop
0x1801195df  jmp     loc_180119E94
0x1801195e4  mov     rcx, [rsp+240h+ppvObject]
0x1801195e9  mov     rax, [rcx]
0x1801195ec  xor     r8d, r8d
0x1801195ef  lea     edx, [r8+4]
0x1801195f3  mov     rax, [rax+28h]
0x1801195f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801195fc  mov     ebx, eax
0x1801195fe  test    eax, eax
0x180119600  jns     short loc_180119655
0x180119602  mov     rcx, [rbp+148h]; this
0x180119609  mov     r9d, eax; char *
0x18011960c  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x180119613  mov     edx, 1Ah; void *
0x180119618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011961d  nop
0x18011961e  lea     rcx, [rsp+240h+ppvObject]
0x180119623  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180119628  nop
0x180119629  mov     edx, [rsp+240h+var_210]
0x18011962d  test    edx, edx
0x18011962f  jns     short loc_180119646
0x180119631  mov     rcx, [rsp+240h+var_200]
0x180119636  mov     rax, [rcx]
0x180119639  mov     rax, [rax+40h]
0x18011963d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119642  mov     edx, [rsp+240h+var_210]
0x180119646  lea     rcx, [rbp+140h+var_190]
0x18011964a  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18011964f  nop
0x180119650  jmp     loc_180119E94
0x180119655  mov     rcx, [rsp+240h+ppvObject]
0x18011965a  mov     rax, [rcx]
0x18011965d  mov     edx, 6
0x180119662  mov     r8d, 0C8h
0x180119668  mov     rax, [rax+28h]
0x18011966c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119671  mov     ebx, eax
0x180119673  test    eax, eax
0x180119675  jns     short loc_1801196CA
0x180119677  mov     rcx, [rbp+148h]; this
0x18011967e  mov     r9d, eax; char *
0x180119681  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x180119688  mov     edx, 1Bh; void *
0x18011968d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119692  nop
0x180119693  lea     rcx, [rsp+240h+ppvObject]
0x180119698  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011969d  nop
0x18011969e  mov     edx, [rsp+240h+var_210]
0x1801196a2  test    edx, edx
0x1801196a4  jns     short loc_1801196BB
0x1801196a6  mov     rcx, [rsp+240h+var_200]
0x1801196ab  mov     rax, [rcx]
0x1801196ae  mov     rax, [rax+40h]
0x1801196b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801196b7  mov     edx, [rsp+240h+var_210]
0x1801196bb  lea     rcx, [rbp+140h+var_190]
0x1801196bf  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1801196c4  nop
0x1801196c5  jmp     loc_180119E94
0x1801196ca  mov     r14d, r15d
0x1801196cd  mov     [rsp+240h+var_1E0], r15d
0x1801196d2  mov     esi, r15d
0x1801196d5  mov     [rsp+240h+var_1F8], r15d
0x1801196da  or      r12d, 0FFFFFFFFh
0x1801196de  cmp     [rsp+240h+var_210], r15d
0x1801196e3  jl      loc_180119E52
0x1801196e9  mov     rcx, [rsp+240h+ppvObject]
0x1801196ee  mov     rax, [rcx]
0x1801196f1  mov     rax, [rax+0C8h]
0x1801196f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801196fd  test    eax, eax
0x1801196ff  jnz     loc_180119E52
0x180119705  mov     [rsp+240h+var_1C8], r15d
0x18011970a  mov     rcx, [rsp+240h+ppvObject]
0x18011970f  mov     rax, [rcx]
0x180119712  lea     rdx, [rsp+240h+var_1C8]
0x180119717  mov     rax, [rax+30h]
0x18011971b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119720  mov     [rsp+240h+var_210], eax
0x180119724  test    eax, eax
0x180119726  js      loc_180119E3A
0x18011972c  cmp     eax, r13d
0x18011972f  jz      loc_180119E3A
0x180119735  mov     eax, [rsp+240h+var_1C8]
0x180119739  test    eax, eax
0x18011973b  jz      loc_180119E3A
0x180119741  mov     [rsp+240h+var_1E4], r15d
0x180119746  cmp     eax, r13d
0x180119749  jnz     loc_180119AC5
0x18011974f  add     r14d, r13d
0x180119752  mov     [rsp+240h+var_1E0], r14d
0x180119757  mov     rcx, [rsp+240h+ppvObject]
0x18011975c  mov     rax, [rcx]
0x18011975f  mov     rax, [rax+0A0h]
0x180119766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011976b  test    eax, eax
0x18011976d  jnz     short loc_180119776
0x18011976f  add     esi, r13d
0x180119772  mov     [rsp+240h+var_1F8], esi
0x180119776  mov     [rbp+140h+lpString2], r15
0x18011977a  mov     rcx, [rsp+240h+ppvObject]
0x18011977f  mov     rax, [rcx]
0x180119782  lea     r8, [rsp+240h+var_1E4]
0x180119787  lea     rdx, [rbp+140h+lpString2]
0x18011978b  mov     rax, [rax+70h]
0x18011978f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119794  test    eax, eax
0x180119796  js      loc_1801196DE
0x18011979c  lea     rcx, [rbp+140h+var_1B8]
0x1801197a0  call    ??$Make@VCSoftLandingQueryEntry@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCSoftLandingQueryEntry@@@12@XZ; Microsoft::WRL::Details::Make<CSoftLandingQueryEntry,>(void)
0x1801197a5  nop
0x1801197a6  mov     rdi, [rbp+140h+var_1B8]
0x1801197aa  test    rdi, rdi
0x1801197ad  jz      loc_180119DE5
0x1801197b3  mov     [rsp+240h+var_1E8], r15d
0x1801197b8  mov     rcx, [rsp+240h+ppvObject]
0x1801197bd  mov     rax, [rcx]
0x1801197c0  lea     rdx, [rsp+240h+var_1E8]
0x1801197c5  mov     rax, [rax+0C0h]
0x1801197cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801197d1  mov     ebx, eax
0x1801197d3  test    eax, eax
0x1801197d5  js      loc_180119D7D
0x1801197db  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x1801197e0  mov     r9d, r12d; cchCount2
0x1801197e3  mov     r8, [rbp+140h+lpString2]; lpString2
0x1801197e7  mov     edx, r12d; cchCount1
0x1801197ea  lea     rcx, String1; "Root"
0x1801197f1  call    cs:__imp_CompareStringOrdinal
0x1801197f8  nop     dword ptr [rax+rax+00h]
0x1801197fd  mov     ebx, 2
0x180119802  cmp     eax, ebx
0x180119804  jnz     short loc_180119817
0x180119806  cmp     [rsp+240h+var_1E8], r15d
0x18011980b  ja      loc_180119B2A
0x180119811  mov     [rdi+10h], r13b
0x180119815  jmp     short loc_180119822
0x180119817  cmp     [rsp+240h+var_1E8], r15d
0x18011981c  jz      loc_180119D23
0x180119822  mov     rcx, [rsp+240h+ppvObject]
0x180119827  mov     rax, [rcx]
0x18011982a  mov     rax, [rax+40h]
0x18011982e  jmp     loc_180119A17
0x180119833  mov     [rsp+240h+var_1F0], r15
0x180119838  mov     [rsp+240h+var_1D8], r15
0x18011983d  mov     rcx, [rsp+240h+ppvObject]
0x180119842  mov     rax, [rcx]
0x180119845  lea     r8, [rsp+240h+var_1E4]
0x18011984a  lea     rdx, [rsp+240h+var_1F0]
0x18011984f  mov     rax, [rax+70h]
0x180119853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119858  test    eax, eax
0x18011985a  js      loc_180119A0B
0x180119860  mov     rcx, [rsp+240h+ppvObject]
0x180119865  mov     rax, [rcx]
0x180119868  lea     r8, [rsp+240h+var_1E4]
0x18011986d  lea     rdx, [rsp+240h+var_1D8]
0x180119872  mov     rax, [rax+80h]
0x180119879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011987e  test    eax, eax
0x180119880  js      loc_180119A0B
0x180119886  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x18011988b  mov     r9d, r12d; cchCount2
0x18011988e  mov     r8, [rsp+240h+var_1F0]; lpString2
0x180119893  mov     edx, r12d; cchCount1
0x180119896  lea     rcx, aId; "Id"
0x18011989d  call    cs:__imp_CompareStringOrdinal
0x1801198a4  nop     dword ptr [rax+rax+00h]
0x1801198a9  cmp     eax, ebx
0x1801198ab  jnz     short loc_1801198B6
0x1801198ad  lea     r9, [rdi+28h]
0x1801198b1  jmp     loc_18011995D
0x1801198b6  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x1801198bb  mov     r9d, r12d; cchCount2
0x1801198be  mov     r8, [rsp+240h+var_1F0]; lpString2
0x1801198c3  mov     edx, r12d; cchCount1
0x1801198c6  lea     rcx, aClass; "Class"
0x1801198cd  call    cs:__imp_CompareStringOrdinal
0x1801198d4  nop     dword ptr [rax+rax+00h]
0x1801198d9  cmp     eax, ebx
0x1801198db  jnz     short loc_1801198E3
0x1801198dd  lea     r9, [rdi+20h]
0x1801198e1  jmp     short loc_18011995D
0x1801198e3  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x1801198e8  mov     r9d, r12d; cchCount2
0x1801198eb  mov     r8, [rsp+240h+var_1F0]; lpString2
0x1801198f0  mov     edx, r12d; cchCount1
0x1801198f3  lea     rcx, aType; "Type"
0x1801198fa  call    cs:__imp_CompareStringOrdinal
0x180119901  nop     dword ptr [rax+rax+00h]
0x180119906  cmp     eax, ebx
0x180119908  jnz     short loc_180119932
0x18011990a  mov     [rsp+240h+var_1DC], r12d
0x18011990f  lea     r8, [rsp+240h+var_1DC]; int *
0x180119914  mov     rdx, [rsp+240h+var_1D8]; unsigned __int16 *
0x180119919  call    ?_UIAControlStringToValue@CSoftLandingXmlParser@@AEAAJPEBGPEAH@Z; CSoftLandingXmlParser::_UIAControlStringToValue(ushort const *,int *)
0x18011991e  test    eax, eax
0x180119920  js      loc_180119A0B
0x180119926  mov     eax, [rsp+240h+var_1DC]
  ... truncated ...
```
