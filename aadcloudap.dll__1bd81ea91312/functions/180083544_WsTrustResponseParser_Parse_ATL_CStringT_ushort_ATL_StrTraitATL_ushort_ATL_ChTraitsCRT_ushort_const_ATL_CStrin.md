# WsTrustResponseParser::Parse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180083544`
- end: `0x180083b59`
- name: `?Parse@WsTrustResponseParser@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@111@Z`
- size: `1557`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005c560`

## callees

- `0x1800065e8`
- `0x1800067f4`
- `0x18000685c`
- `0x1800090d0`
- `0x18000c7ac`
- `0x18003ad60`
- `0x18004b898`
- `0x180066750`
- `0x180066838`
- `0x180066e24`
- `0x180071e14`
- `0x180082a9c`
- `0x180083544`
- `0x180083ed0`
- `0x180084240`
- `0x1800844ec`
- `0x1800a3520`
- `0x1800a8010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180083672`
- `XmlLite!CreateXmlReader` at `0x180083672`

## string_xrefs

- `0x1800838a5`: `/S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse/trust:RequestedSecurityToken`
- `0x180083934`: `/S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse`
- `0x180083947`: `/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse`
- `0x1800838bc`: `/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse/trust2005:RequestedSecurityToken`
- `0x1800839ca`: `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV2.0`
- `0x180083765`: `/S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse/trust:TokenType`
- `0x1800839a4`: `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`
- `0x18008377c`: `/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse/trust2005:TokenType`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WsTrustResponseParser::Parse(_QWORD *a1, _QWORD *a2, _QWORD *a3, __int64 a4, _QWORD *a5)
{
  __int64 v5; // r14
  HRESULT ElementValue; // edi
  wchar_t *v10; // rbx
  _QWORD *v11; // r15
  int v12; // eax
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  int *v15; // r14
  __int64 v16; // rdi
  __int64 v17; // rdi
  wchar_t *v18; // rbx
  _QWORD *v19; // rcx
  int *v20; // r14
  __int64 v21; // rbx
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  int *v24; // r14
  __int64 v25; // rbx
  int v27; // [rsp+30h] [rbp-50h]
  int v28; // [rsp+30h] [rbp-50h]
  void *ppvObject; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-28h] BYREF
  wchar_t *v31; // [rsp+60h] [rbp-20h] BYREF
  __int64 v32; // [rsp+68h] [rbp-18h] BYREF
  __int64 v33; // [rsp+70h] [rbp-10h] BYREF
  __int64 v34; // [rsp+78h] [rbp-8h] BYREF
  int v35; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v36; // [rsp+D8h] [rbp+58h]

  v36 = a4;
  v5 = a4;
  v35 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&String1);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
  ppvObject = 0;
  v33 = 0;
  v34 = 0;
  if ( !*(_DWORD *)(*a1 - 16LL) )
  {
    ElementValue = -2147024809;
    v27 = 45;
LABEL_3:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ElementValue, "wstrustresponseparser.cpp", v27, "HRESULT", &base);
    v10 = String1;
    goto LABEL_65;
  }
  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a3);
  ATL::CSimpleStringT<unsigned short,0>::Empty(v5);
  v11 = a5;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a5);
  ElementValue = SequentialStream::FromString(a1, &v34);
  if ( ElementValue < 0 )
  {
    v27 = 54;
    goto LABEL_3;
  }
  ATL::CComPtrBase<ISequentialStream>::Attach(&v33, v34);
  ElementValue = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( ElementValue < 0 )
  {
    v27 = 58;
    goto LABEL_3;
  }
  ElementValue = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v33);
  if ( ElementValue < 0 )
  {
    v27 = 59;
    goto LABEL_3;
  }
  ElementValue = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  if ( ElementValue < 0 )
  {
    v27 = 61;
    goto LABEL_3;
  }
LABEL_12:
  v10 = String1;
  while ( 1 )
  {
    while ( 1 )
    {
      ElementValue = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v35);
      if ( ElementValue )
      {
        if ( ElementValue == 1 )
          ElementValue = 0;
        goto LABEL_65;
      }
      if ( v35 == 1 )
        break;
      if ( v35 == 3 )
      {
        if ( !wcscmp_0(
                v10,
                L"/S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse/trust:TokenType")
          || !wcscmp_0(v10, L"/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse/trust2005:TokenType") )
        {
          ElementValue = WsTrustBaseParser<WsTrustResponseParser,1>::GetElementValue(ppvObject, &v31);
          if ( ElementValue < 0 )
          {
            v28 = 131;
            goto LABEL_62;
          }
        }
        else if ( !wcscmp_0(v10, L"/S:Envelope/S:Body/S:Fault/S:Code/S:Subcode/S:Value") )
        {
          ElementValue = WsTrustBaseParser<WsTrustResponseParser,1>::GetElementValue(ppvObject, v11);
          if ( ElementValue < 0 )
          {
            v28 = 135;
            goto LABEL_62;
          }
          v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                  v11,
                  58,
                  0);
          v13 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                             v11,
                             &v34,
                             (unsigned int)(v12 + 1));
          v14 = (_QWORD *)(v13 - 24);
          v15 = (int *)(*v11 - 24LL);
          if ( (int *)(v13 - 24) != v15 )
          {
            if ( v15[4] >= 0 && *v14 == *(_QWORD *)v15 )
            {
              v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v14);
              ATL::CStringData::Release((ATL::CStringData *)v15);
              *v11 = v16 + 24;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(v11, v13, *(unsigned int *)(v13 - 16));
            }
          }
          ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
          v5 = v36;
        }
      }
      else if ( v35 == 15 )
      {
        goto LABEL_37;
      }
    }
    WsTrustBaseParser<WsTrustResponseParser,1>::UpdateCurrentPath(ppvObject, &String1, 1);
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
      goto LABEL_59;
    v10 = String1;
    if ( !wcscmp_0(
            String1,
            L"/S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse/trust:Req"
             "uestedSecurityToken")
      || !wcscmp_0(v10, L"/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse/trust2005:RequestedSecurityToken") )
    {
      break;
    }
    if ( !wcscmp_0(v10, L"/S:Envelope/S:Body/S:Fault/S:Reason") )
    {
      ElementValue = WsTrustBaseParser<WsTrustResponseParser,1>::ReadInnerXml(ppvObject, v5);
      if ( ElementValue < 0 )
      {
        v28 = 87;
        goto LABEL_62;
      }
LABEL_37:
      if ( !wcscmp_0(
              v10,
              L"/S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse")
        || !wcscmp_0(v10, L"/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse") )
      {
        v17 = v32;
        if ( *(_DWORD *)(v32 - 16) )
        {
          v18 = v31;
          if ( *((_DWORD *)v31 - 4)
            || (SamlTokenParser::ParseAssertionType(&v32, &v31), v18 = v31, *((_DWORD *)v31 - 4)) )
          {
            if ( !wcscmp_0(v18, L"urn:oasis:names:tc:SAML:1.0:assertion")
              || !wcscmp_0(v18, L"http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1") )
            {
              v23 = (_QWORD *)(v17 - 24);
              v24 = (int *)(*a2 - 24LL);
              if ( (int *)(v17 - 24) != v24 )
              {
                if ( v24[4] < 0 || *v23 != *(_QWORD *)v24 )
                {
                  v22 = a2;
                  goto LABEL_56;
                }
                v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v23);
                ATL::CStringData::Release((ATL::CStringData *)v24);
                *a2 = v25 + 24;
              }
LABEL_57:
              v5 = v36;
            }
            else if ( !wcscmp_0(v18, L"urn:oasis:names:tc:SAML:2.0:assertion")
                   || !wcscmp_0(v18, L"http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV2.0") )
            {
              v19 = (_QWORD *)(v17 - 24);
              v20 = (int *)(*a3 - 24LL);
              if ( (int *)(v17 - 24) == v20 )
                goto LABEL_57;
              if ( v20[4] >= 0 && *v19 == *(_QWORD *)v20 )
              {
                v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v19);
                ATL::CStringData::Release((ATL::CStringData *)v20);
                *a3 = v21 + 24;
                goto LABEL_57;
              }
              v22 = a3;
LABEL_56:
              ATL::CSimpleStringT<unsigned short,0>::SetString(v22, v17, *(unsigned int *)(v17 - 16));
              goto LABEL_57;
            }
          }
        }
        ATL::CSimpleStringT<unsigned short,0>::Empty(&v32);
        ATL::CSimpleStringT<unsigned short,0>::Empty(&v31);
      }
LABEL_59:
      WsTrustBaseParser<WsTrustResponseParser,1>::UpdateCurrentPath(ppvObject, &String1, 0);
      goto LABEL_12;
    }
  }
  ElementValue = WsTrustBaseParser<WsTrustResponseParser,1>::ReadInnerXml(ppvObject, &v32);
  if ( ElementValue >= 0 )
    goto LABEL_37;
  v28 = 81;
LABEL_62:
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ElementValue, "wstrustresponseparser.cpp", v28, "HRESULT", &base);
LABEL_65:
  ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>(&v33);
  ATL::CComPtrBase<ISequentialStream>::~CComPtrBase<ISequentialStream>((__int64 *)&ppvObject);
  ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v31 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
  return (unsigned int)ElementValue;
}

```

## disassembly

```asm
0x180083544  mov     [rsp-38h+arg_8], rbx
0x180083549  mov     [rsp-38h+arg_18], r9
0x18008354e  push    rbp
0x18008354f  push    rsi
0x180083550  push    rdi
0x180083551  push    r12
0x180083553  push    r13
0x180083555  push    r14
0x180083557  push    r15
0x180083559  mov     rbp, rsp
0x18008355c  sub     rsp, 80h
0x180083563  mov     r14, r9
0x180083566  mov     r12, r8
0x180083569  mov     r13, rdx
0x18008356c  mov     rbx, rcx
0x18008356f  xor     esi, esi
0x180083571  mov     [rbp+arg_0], esi
0x180083574  lea     rcx, [rbp+String1]; void *
0x180083578  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008357d  nop
0x18008357e  lea     rcx, [rbp+var_20]; void *
0x180083582  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180083587  nop
0x180083588  lea     rcx, [rbp+var_18]; void *
0x18008358c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180083591  nop
0x180083592  mov     [rbp+ppvObject], rsi
0x180083596  mov     [rbp+var_10], rsi
0x18008359a  mov     [rbp+var_8], rsi
0x18008359e  mov     rax, [rbx]
0x1800835a1  cmp     [rax-10h], esi
0x1800835a4  jnz     short loc_1800835FC
0x1800835a6  mov     edi, 80070057h
0x1800835ab  lea     rax, base
0x1800835b2  mov     [rsp+80h+var_40], rax
0x1800835b7  lea     rax, aHresult; "HRESULT"
0x1800835be  mov     [rsp+80h+var_48], rax
0x1800835c3  mov     [rsp+80h+var_50], 2Dh ; '-'
0x1800835cb  mov     esi, 2
0x1800835d0  lea     rax, aOnecoreuapDsEx_45+25h; "wstrustresponseparser.cpp"
0x1800835d7  mov     [rsp+80h+var_58], rax
0x1800835dc  mov     [rsp+80h+var_60], edi
0x1800835e0  mov     r9d, esi
0x1800835e3  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800835ea  xor     edx, edx
0x1800835ec  mov     ecx, esi
0x1800835ee  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800835f3  mov     rbx, [rbp+String1]
0x1800835f7  jmp     loc_180083B03
0x1800835fc  mov     rcx, r13
0x1800835ff  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180083604  mov     rcx, r12
0x180083607  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18008360c  mov     rcx, r14
0x18008360f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180083614  mov     r15, [rbp+arg_20]
0x180083618  mov     rcx, r15
0x18008361b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180083620  lea     rdx, [rbp+var_8]
0x180083624  mov     rcx, rbx
0x180083627  call    ?FromString@SequentialStream@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAUISequentialStream@@H@Z; SequentialStream::FromString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ISequentialStream * *,int)
0x18008362c  mov     edi, eax
0x18008362e  test    eax, eax
0x180083630  jns     short loc_180083657
0x180083632  lea     rax, base
0x180083639  mov     [rsp+80h+var_40], rax
0x18008363e  lea     rax, aHresult; "HRESULT"
0x180083645  mov     [rsp+80h+var_48], rax
0x18008364a  mov     [rsp+80h+var_50], 36h ; '6'
0x180083652  jmp     loc_1800835CB
0x180083657  mov     rdx, [rbp+var_8]
0x18008365b  lea     rcx, [rbp+var_10]
0x18008365f  call    ?Attach@?$CComPtrBase@UISequentialStream@@@ATL@@QEAAXPEAUISequentialStream@@@Z; ATL::CComPtrBase<ISequentialStream>::Attach(ISequentialStream *)
0x180083664  xor     r8d, r8d; pMalloc
0x180083667  lea     rdx, [rbp+ppvObject]; ppvObject
0x18008366b  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180083672  call    cs:__imp_CreateXmlReader
0x180083678  mov     edi, eax
0x18008367a  test    eax, eax
0x18008367c  jns     short loc_1800836A3
0x18008367e  lea     rax, base
0x180083685  mov     [rsp+80h+var_40], rax
0x18008368a  lea     rax, aHresult; "HRESULT"
0x180083691  mov     [rsp+80h+var_48], rax
0x180083696  mov     [rsp+80h+var_50], 3Ah ; ':'
0x18008369e  jmp     loc_1800835CB
0x1800836a3  mov     rcx, [rbp+ppvObject]
0x1800836a7  mov     rax, [rcx]
0x1800836aa  mov     rdx, [rbp+var_10]
0x1800836ae  mov     rax, [rax+18h]
0x1800836b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800836b7  mov     edi, eax
0x1800836b9  test    eax, eax
0x1800836bb  jns     short loc_1800836E2
0x1800836bd  lea     rax, base
0x1800836c4  mov     [rsp+80h+var_40], rax
0x1800836c9  lea     rax, aHresult; "HRESULT"
0x1800836d0  mov     [rsp+80h+var_48], rax
0x1800836d5  mov     [rsp+80h+var_50], 3Bh ; ';'
0x1800836dd  jmp     loc_1800835CB
0x1800836e2  mov     rcx, [rbp+ppvObject]
0x1800836e6  mov     rax, [rcx]
0x1800836e9  xor     r8d, r8d
0x1800836ec  lea     edx, [r8+4]
0x1800836f0  mov     rax, [rax+28h]
0x1800836f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800836f9  mov     edi, eax
0x1800836fb  mov     esi, 2
0x180083700  test    eax, eax
0x180083702  jns     short loc_180083729
0x180083704  lea     rax, base
0x18008370b  mov     [rsp+80h+var_40], rax
0x180083710  lea     rax, aHresult; "HRESULT"
0x180083717  mov     [rsp+80h+var_48], rax
0x18008371c  mov     [rsp+80h+var_50], 3Dh ; '='
0x180083724  jmp     loc_1800835D0
0x180083729  mov     rbx, [rbp+String1]
0x18008372d  mov     rcx, [rbp+ppvObject]
0x180083731  mov     rax, [rcx]
0x180083734  lea     rdx, [rbp+arg_0]
0x180083738  mov     rax, [rax+30h]
0x18008373c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083741  mov     edi, eax
0x180083743  test    eax, eax
0x180083745  jnz     loc_180083AFB
0x18008374b  mov     ecx, [rbp+arg_0]
0x18008374e  sub     ecx, 1
0x180083751  jz      loc_180083877
0x180083757  sub     ecx, esi
0x180083759  jz      short loc_180083765
0x18008375b  cmp     ecx, 0Ch
0x18008375e  jnz     short loc_18008372D
0x180083760  jmp     loc_180083934
0x180083765  lea     rdx, aSEnvelopeSBody_0; "/S:Envelope/S:Body/trust:RequestSecurit"...
0x18008376c  mov     rcx, rbx; String1
0x18008376f  call    wcscmp_0
0x180083774  test    eax, eax
0x180083776  jz      loc_18008383B
0x18008377c  lea     rdx, aSEnvelopeSBody_5; "/S:Envelope/S:Body/trust2005:RequestSec"...
0x180083783  mov     rcx, rbx; String1
0x180083786  call    wcscmp_0
0x18008378b  test    eax, eax
0x18008378d  jz      loc_18008383B
0x180083793  lea     rdx, aSEnvelopeSBody_2; "/S:Envelope/S:Body/S:Fault/S:Code/S:Sub"...
0x18008379a  mov     rcx, rbx; String1
0x18008379d  call    wcscmp_0
0x1800837a2  test    eax, eax
0x1800837a4  jnz     short loc_18008372D
0x1800837a6  mov     rdx, r15
0x1800837a9  mov     rcx, [rbp+ppvObject]
0x1800837ad  call    ?GetElementValue@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WsTrustBaseParser<WsTrustResponseParser,1>::GetElementValue(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800837b2  mov     edi, eax
0x1800837b4  test    eax, eax
0x1800837b6  js      loc_180083A94
0x1800837bc  mov     edx, 3Ah ; ':'
0x1800837c1  xor     r8d, r8d
0x1800837c4  mov     rcx, r15
0x1800837c7  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort,int)
0x1800837cc  lea     r8d, [rax+1]
0x1800837d0  lea     rdx, [rbp+var_8]
0x1800837d4  mov     rcx, r15
0x1800837d7  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x1800837dc  nop
0x1800837dd  mov     rdx, [rax]
0x1800837e0  lea     rcx, [rdx-18h]
0x1800837e4  mov     r14, [r15]
0x1800837e7  add     r14, 0FFFFFFFFFFFFFFE8h
0x1800837eb  cmp     rcx, r14
0x1800837ee  jz      short loc_180083825
0x1800837f0  cmp     dword ptr [r14+10h], 0
0x1800837f5  jl      short loc_180083818
0x1800837f7  mov     rax, [r14]
0x1800837fa  cmp     [rcx], rax
0x1800837fd  jnz     short loc_180083818
0x1800837ff  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180083804  mov     rdi, rax
0x180083807  mov     rcx, r14; this
0x18008380a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18008380f  lea     rax, [rdi+18h]
0x180083813  mov     [r15], rax
0x180083816  jmp     short loc_180083825
0x180083818  mov     r8d, [rdx-10h]
0x18008381c  mov     rcx, r15
0x18008381f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180083824  nop
0x180083825  mov     rcx, [rbp+var_8]
0x180083829  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18008382d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180083832  mov     r14, [rbp+arg_18]
0x180083836  jmp     loc_18008372D
0x18008383b  lea     rdx, [rbp+var_20]
0x18008383f  mov     rcx, [rbp+ppvObject]
0x180083843  call    ?GetElementValue@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WsTrustBaseParser<WsTrustResponseParser,1>::GetElementValue(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180083848  mov     edi, eax
0x18008384a  test    eax, eax
0x18008384c  jns     loc_18008372D
0x180083852  lea     rax, base
0x180083859  mov     [rsp+80h+var_40], rax
0x18008385e  lea     rax, aHresult; "HRESULT"
0x180083865  mov     [rsp+80h+var_48], rax
0x18008386a  mov     [rsp+80h+var_50], 83h
0x180083872  jmp     loc_180083AD6
0x180083877  mov     r8d, 1
0x18008387d  lea     rdx, [rbp+String1]
0x180083881  mov     rcx, [rbp+ppvObject]
0x180083885  call    ?UpdateCurrentPath@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; WsTrustBaseParser<WsTrustResponseParser,1>::UpdateCurrentPath(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int)
0x18008388a  mov     rcx, [rbp+ppvObject]
0x18008388e  mov     rax, [rcx]
0x180083891  mov     rax, [rax+0A0h]
0x180083898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008389d  test    eax, eax
0x18008389f  jnz     loc_180083A7F
0x1800838a5  lea     rdx, aSEnvelopeSBody_1; "/S:Envelope/S:Body/trust:RequestSecurit"...
0x1800838ac  mov     rbx, [rbp+String1]
0x1800838b0  mov     rcx, rbx; String1
0x1800838b3  call    wcscmp_0
0x1800838b8  test    eax, eax
0x1800838ba  jz      short loc_18008391D
0x1800838bc  lea     rdx, aSEnvelopeSBody_4; "/S:Envelope/S:Body/trust2005:RequestSec"...
0x1800838c3  mov     rcx, rbx; String1
0x1800838c6  call    wcscmp_0
0x1800838cb  test    eax, eax
0x1800838cd  jz      short loc_18008391D
0x1800838cf  lea     rdx, aSEnvelopeSBody_6; "/S:Envelope/S:Body/S:Fault/S:Reason"
0x1800838d6  mov     rcx, rbx; String1
0x1800838d9  call    wcscmp_0
0x1800838de  test    eax, eax
0x1800838e0  jnz     loc_18008372D
0x1800838e6  mov     rdx, r14
0x1800838e9  mov     rcx, [rbp+ppvObject]
0x1800838ed  call    ?ReadInnerXml@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WsTrustBaseParser<WsTrustResponseParser,1>::ReadInnerXml(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800838f2  mov     edi, eax
0x1800838f4  test    eax, eax
0x1800838f6  jns     short loc_180083934
0x1800838f8  lea     rax, base
0x1800838ff  mov     [rsp+80h+var_40], rax
0x180083904  lea     rax, aHresult; "HRESULT"
0x18008390b  mov     [rsp+80h+var_48], rax
0x180083910  mov     [rsp+80h+var_50], 57h ; 'W'
0x180083918  jmp     loc_180083AD6
0x18008391d  lea     rdx, [rbp+var_18]
0x180083921  mov     rcx, [rbp+ppvObject]
0x180083925  call    ?ReadInnerXml@?$WsTrustBaseParser@VWsTrustResponseParser@@$00@@KAJPEAUIXmlReader@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WsTrustBaseParser<WsTrustResponseParser,1>::ReadInnerXml(IXmlReader *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18008392a  mov     edi, eax
0x18008392c  test    eax, eax
0x18008392e  js      loc_180083AB6
0x180083934  lea     rdx, aSEnvelopeSBody_3; "/S:Envelope/S:Body/trust:RequestSecurit"...
0x18008393b  mov     rcx, rbx; String1
0x18008393e  call    wcscmp_0
0x180083943  test    eax, eax
0x180083945  jz      short loc_18008395E
0x180083947  lea     rdx, aSEnvelopeSBody; "/S:Envelope/S:Body/trust2005:RequestSec"...
0x18008394e  mov     rcx, rbx; String1
0x180083951  call    wcscmp_0
0x180083956  test    eax, eax
0x180083958  jnz     loc_180083A7F
0x18008395e  mov     rdi, [rbp+var_18]
0x180083962  cmp     dword ptr [rdi-10h], 0
0x180083966  jz      loc_180083A6D
0x18008396c  mov     rbx, [rbp+var_20]
0x180083970  cmp     dword ptr [rbx-10h], 0
0x180083974  jnz     short loc_180083991
0x180083976  lea     rdx, [rbp+var_20]
0x18008397a  lea     rcx, [rbp+var_18]
0x18008397e  call    ?ParseAssertionType@SamlTokenParser@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; SamlTokenParser::ParseAssertionType(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180083983  mov     rbx, [rbp+var_20]
0x180083987  cmp     dword ptr [rbx-10h], 0
0x18008398b  jz      loc_180083A6D
0x180083991  lea     rdx, aUrnOasisNamesT; "urn:oasis:names:tc:SAML:1.0:assertion"
0x180083998  mov     rcx, rbx; String1
0x18008399b  call    wcscmp_0
0x1800839a0  test    eax, eax
0x1800839a2  jz      short loc_180083A20
0x1800839a4  lea     rdx, aHttpDocsOasisO_1; "http://docs.oasis-open.org/wss/oasis-ws"...
0x1800839ab  mov     rcx, rbx; String1
0x1800839ae  call    wcscmp_0
0x1800839b3  test    eax, eax
0x1800839b5  jz      short loc_180083A20
0x1800839b7  lea     rdx, aUrnOasisNamesT_0; "urn:oasis:names:tc:SAML:2.0:assertion"
0x1800839be  mov     rcx, rbx; String1
0x1800839c1  call    wcscmp_0
0x1800839c6  test    eax, eax
0x1800839c8  jz      short loc_1800839E1
0x1800839ca  lea     rdx, aHttpDocsOasisO_3; "http://docs.oasis-open.org/wss/oasis-ws"...
0x1800839d1  mov     rcx, rbx; String1
0x1800839d4  call    wcscmp_0
0x1800839d9  test    eax, eax
0x1800839db  jnz     loc_180083A6D
0x1800839e1  lea     rcx, [rdi-18h]
0x1800839e5  mov     r14, [r12]
0x1800839e9  add     r14, 0FFFFFFFFFFFFFFE8h
0x1800839ed  cmp     rcx, r14
0x1800839f0  jz      short loc_180083A69
0x1800839f2  cmp     dword ptr [r14+10h], 0
0x1800839f7  jl      short loc_180083A1B
0x1800839f9  mov     rax, [r14]
0x1800839fc  cmp     [rcx], rax
0x1800839ff  jnz     short loc_180083A1B
0x180083a01  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180083a06  mov     rbx, rax
  ... truncated ...
```
