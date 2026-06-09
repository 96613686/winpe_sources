# MIXmlSerializer::GetReferenceValue(MIXmlSerializer::XmlValue &,ushort const * *,_MI_Instance * &)

- ea: `0x18000a294`
- end: `0x18000a999`
- name: `?GetReferenceValue@MIXmlSerializer@@QEAA_NAEAUXmlValue@1@PEAPEBGAEAPEAU_MI_Instance@@@Z`
- size: `1797`
- prototype: `bool __fastcall(MIXmlSerializer *__hidden this, struct MIXmlSerializer::XmlValue *, const unsigned __int16 **, struct _MI_Instance **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b510`
- `0x18000eae0`

## callees

- `0x180005d10`
- `0x1800092a0`
- `0x18000a294`
- `0x18000a9a0`
- `0x18000eae0`
- `0x18000f7a0`
- `0x180035fe0`
- `0x18003a610`
- `0x18003c640`
- `0x180084750`
- `0x180150ec0`
- `0x1801ba176`
- `0x1801ba182`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000a551`
- `msvcrt!wcsrchr` at `0x18000a551`
- `miutils!Instance_SetResourceURI` at `0x18000a5e6`
- `miutils!Instance_SetResourceURI` at `0x18000a5e6`
- `miutils!Instance_InitDynamic` at `0x18000a582`
- `miutils!Instance_InitDynamic` at `0x18000a582`

## string_xrefs

- `0x18000a35c`: `http://schemas.xmlsoap.org/ws/2004/08/addressing`
- `0x18000a3ab`: `http://schemas.xmlsoap.org/ws/2004/08/addressing`
- `0x18000a716`: `http://schemas.xmlsoap.org/ws/2004/08/addressing`
- `0x18000a4a6`: `ResourceURI`
- `0x18000a527`: `ResourceURI`
- `0x18000a327`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000a42b`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000a44e`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000a821`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000a92f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`

## pseudocode

```c
char __fastcall MIXmlSerializer::GetReferenceValue(
        MIXmlSerializer *this,
        struct MIXmlSerializer::XmlValue *a2,
        const unsigned __int16 **a3,
        struct _MI_Instance **a4)
{
  __int64 v9; // rsi
  __int64 v10; // rsi
  __int64 v11; // r8
  const unsigned __int16 *SimpleContentEx2; // r14
  __int64 i; // rax
  __int64 v14; // r15
  int v15; // eax
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
  const wchar_t *v18; // rax
  __int64 v19; // rcx
  int v20; // r12d
  int v21; // r13d
  int v22; // r14d
  __int64 v23; // rsi
  __int64 v24; // r15
  const wchar_t *v25; // rax
  const wchar_t *v26; // rax
  __int64 Child; // r14
  __int64 AttributeValue; // rax
  int v29; // r14d
  const wchar_t *v30; // r15
  int v31; // eax
  struct _MI_Instance *v32; // [rsp+38h] [rbp-41h]
  bool v33; // [rsp+40h] [rbp-39h] BYREF
  bool v34; // [rsp+41h] [rbp-38h] BYREF
  enum _MI_Type v35; // [rsp+44h] [rbp-35h] BYREF
  __int64 v36; // [rsp+48h] [rbp-31h]
  int v37; // [rsp+50h] [rbp-29h] BYREF
  union _MI_Value v38; // [rsp+58h] [rbp-21h] BYREF

  if ( a3 )
    *a3 = 0;
  *a4 = 0;
  if ( (unsigned int)FwXmlNumChildren(*(_QWORD *)a2) != 2 )
    goto LABEL_4;
  v9 = *(_QWORD *)(*(_QWORD *)a2 + 136LL);
  if ( !v9 )
    goto LABEL_7;
  if ( !(unsigned int)FwXmlCompareName(*(_QWORD *)(*(_QWORD *)a2 + 136LL), 7, L"Address", 0)
    || !(unsigned int)FwXmlCompareName(v9 + 48, 48, L"http://schemas.xmlsoap.org/ws/2004/08/addressing", 0) )
  {
    goto LABEL_4;
  }
  v10 = *(_QWORD *)(*(_QWORD *)a2 + 136LL) + 152LL;
  if ( *(_QWORD *)(*(_QWORD *)a2 + 136LL) == -152 )
  {
LABEL_7:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2060, L"2060", 0x80070057, 0);
LABEL_4:
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 33) + 72LL))(*((_QWORD *)this + 33), 2150858817LL);
    return 0;
  }
  if ( !(unsigned int)FwXmlCompareName(v10, 19, L"ReferenceParameters", 0)
    || !(unsigned int)FwXmlCompareName(v10 + 48, 48, L"http://schemas.xmlsoap.org/ws/2004/08/addressing", 0) )
  {
    goto LABEL_4;
  }
  if ( *(_DWORD *)(v10 + 72) )
  {
    v11 = 1077134276;
LABEL_15:
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 33) + 64LL))(
      *((_QWORD *)this + 33),
      2150858817LL,
      v11);
    return 0;
  }
  v36 = 0;
  SimpleContentEx2 = 0;
  for ( i = 0; ; i = (unsigned int)(v35 + 1) )
  {
    v35 = (int)i;
    if ( (unsigned int)i >= *(_DWORD *)(v10 + 128) )
      break;
    v14 = *(_QWORD *)(v10 + 136) + 152 * i;
    if ( v14 )
    {
      if ( (unsigned int)FwXmlCompareName(*(_QWORD *)(v10 + 136) + 152 * i, 11, L"SelectorSet", 0)
        && (unsigned int)FwXmlCompareName(v14 + 48, 46, L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 0) )
      {
        if ( v36 )
        {
          v16 = L"SelectorSet";
LABEL_31:
          (*(void (__fastcall **)(_QWORD, __int64, __int64, const wchar_t *))(**((_QWORD **)this + 33) + 64LL))(
            *((_QWORD *)this + 33),
            2150858817LL,
            1077134278,
            v16);
          return 0;
        }
        v36 = v14;
      }
      else
      {
        v15 = FwXmlCompareName(v14, 11, L"ResourceURI", 0);
        if ( v15 )
          v15 = FwXmlCompareName(v14 + 48, 46, L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 0);
        if ( v15 )
        {
          if ( SimpleContentEx2 )
          {
            v16 = L"ResourceURI";
            goto LABEL_31;
          }
          SimpleContentEx2 = FwXmlGetSimpleContentEx2(v14, &v37, 2);
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2060, L"2060", 0x80070057, 0);
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2060, L"2060", 0x80070057, 0);
    }
  }
  if ( !SimpleContentEx2 )
  {
    v11 = 1077134318;
    goto LABEL_15;
  }
  if ( a3 )
    *a3 = SimpleContentEx2;
  v17 = wcsrchr(SimpleContentEx2, 0x2Fu);
  if ( !v17 )
    goto LABEL_4;
  if ( *((_BYTE *)this + 290) )
    v18 = L"Metadata";
  else
    v18 = v17 + 1;
  if ( (unsigned int)Instance_InitDynamic(a4, v18, 1)
    || ((unsigned int (__fastcall *)(_QWORD, _QWORD))(*a4)->ft->SetServerName)(*a4, *((_QWORD *)this + 28))
    || *((_QWORD *)this + 24) && ((unsigned int (__fastcall *)(_QWORD))(*a4)->ft->SetNameSpace)(*a4)
    || (unsigned int)Instance_SetResourceURI(*a4, SimpleContentEx2) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 24LL))(*((_QWORD *)this + 33));
    return 0;
  }
  if ( !v36 )
    return 1;
  v19 = *(_QWORD *)(v36 + 136);
  v20 = 0;
  v21 = *(_DWORD *)(v36 + 128);
  v22 = 0;
  v36 = v19;
  while ( 2 )
  {
    if ( v20 >= v21 )
      return 1;
    v23 = v19 + 152LL * v20;
    if ( !v23 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2060, L"2060", 0x80070057, 0);
LABEL_77:
      (*(void (__fastcall **)(_QWORD, __int64, __int64, const wchar_t *))(**((_QWORD **)this + 33) + 64LL))(
        *((_QWORD *)this + 33),
        2150858817LL,
        1077134370,
        L"Selector");
      goto LABEL_78;
    }
    if ( !(unsigned int)FwXmlCompareName(v23, 8, L"Selector", 0)
      || !(unsigned int)FwXmlCompareName(v23 + 48, 46, L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 0) )
    {
      goto LABEL_77;
    }
    while ( 1 )
    {
      if ( v22 == *(_DWORD *)(v23 + 112) )
      {
        (*(void (__fastcall **)(_QWORD, __int64, __int64, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 33)
                                                                                           + 64LL))(
          *((_QWORD *)this + 33),
          2150858817LL,
          1077134371,
          L"Selector",
          L"Name");
        ((void (__fastcall *)(_QWORD))(*a4)->ft->Destruct)(*a4);
        *a4 = 0;
        return 0;
      }
      v24 = *(_QWORD *)(v23 + 120) + 104LL * v22;
      if ( v24 == -48 )
      {
LABEL_68:
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
        goto LABEL_69;
      }
      if ( *(_DWORD *)(v24 + 64) == 46 )
      {
        v25 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v24 + 48);
        if ( !wcsncmp_0(v25, L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 0x2Eu) )
        {
          if ( !v24 )
            goto LABEL_68;
          if ( *(_DWORD *)(v24 + 16) == 4 )
          {
            v26 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v24);
            if ( !wcsncmp_0(v26, L"Name", 4u) )
              break;
          }
        }
      }
LABEL_69:
      ++v22;
    }
    v35 = MI_STRING;
    if ( (unsigned int)FwXmlNumChildren(v23) == 1 )
    {
      Child = FwXmlGetChild(v23, 0);
      if ( (unsigned int)FwXmlCompareElementName(
                           Child,
                           L"EndpointReference",
                           L"http://schemas.xmlsoap.org/ws/2004/08/addressing",
                           0) )
      {
        v23 = Child;
        v35 = MI_REFERENCE;
      }
    }
    AttributeValue = FwXmlGetAttributeValue(v24);
    v29 = *((_DWORD *)this + 74);
    v30 = (const wchar_t *)AttributeValue;
    *((_DWORD *)this + 74) = 1;
    v32 = *a4;
    v33 = 0;
    v34 = 0;
    memset(&v38, 0, sizeof(v38));
    if ( !MIXmlSerializer::ConvertXmlPropertyToCim(
            (struct IRequestContext **)this,
            0,
            (struct _FWXML_ELEMENT *)v23,
            &v35,
            (struct _MI_Instance **)&v38,
            &v33,
            &v34,
            v32) )
    {
      ((void (__fastcall *)(_QWORD))(*a4)->ft->Destruct)(*a4);
      *a4 = 0;
      *((_DWORD *)this + 74) = v29;
      return 0;
    }
    *((_DWORD *)this + 74) = v29;
    v22 = 0;
    if ( !v30 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 131, L"131", 0x54Fu, 0);
    if ( !wcscmp_0(v30, L"__cimnamespace") )
      v31 = ((__int64 (__fastcall *)(_QWORD, MI_Uint64))(*a4)->ft->SetNameSpace)(*a4, v38.uint64);
    else
      v31 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, union _MI_Value *))(*a4)->ft->AddElement)(*a4, v30, &v38);
    if ( !v31 )
    {
      v19 = v36;
      ++v20;
      continue;
    }
    break;
  }
  MIXmlSerializer::DiscardCimProperty(v35, &v38);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 24LL))(*((_QWORD *)this + 33));
LABEL_78:
  ((void (__fastcall *)(_QWORD))(*a4)->ft->Destruct)(*a4);
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000a294  push    rbp
0x18000a296  push    rbx
0x18000a297  push    rsi
0x18000a298  push    rdi
0x18000a299  push    r12
0x18000a29b  push    r13
0x18000a29d  push    r14
0x18000a29f  push    r15
0x18000a2a1  lea     rbp, [rsp-1Fh]
0x18000a2a6  sub     rsp, 98h
0x18000a2ad  mov     rax, cs:__security_cookie
0x18000a2b4  xor     rax, rsp
0x18000a2b7  mov     [rbp+57h+var_50], rax
0x18000a2bb  xor     r13d, r13d
0x18000a2be  mov     rdi, r9
0x18000a2c1  mov     r12, r8
0x18000a2c4  mov     r14, rdx
0x18000a2c7  mov     rbx, rcx
0x18000a2ca  test    r8, r8
0x18000a2cd  jz      short loc_18000A2D2
0x18000a2cf  mov     [r8], r13
0x18000a2d2  mov     [r9], r13
0x18000a2d5  mov     rcx, [rdx]
0x18000a2d8  call    FwXmlNumChildren
0x18000a2dd  cmp     eax, 2
0x18000a2e0  jz      short loc_18000A301
0x18000a2e2  mov     rcx, [rbx+108h]
0x18000a2e9  mov     edx, 80338041h
0x18000a2ee  mov     rax, [rcx]
0x18000a2f1  mov     rax, [rax+48h]
0x18000a2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2fa  xor     al, al
0x18000a2fc  jmp     loc_18000A979
0x18000a301  mov     rax, [r14]
0x18000a304  mov     rsi, [rax+88h]
0x18000a30b  test    rsi, rsi
0x18000a30e  jnz     short loc_18000A335
0x18000a310  mov     r9d, 80070057h; unsigned int
0x18000a316  mov     [rsp+0D0h+var_B0], r13; struct IRequestContext *
0x18000a31b  lea     r8, a2060; "2060"
0x18000a322  mov     edx, 80Ch; unsigned int
0x18000a327  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18000a32e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000a333  jmp     short loc_18000A2E2
0x18000a335  xor     r9d, r9d
0x18000a338  lea     r8, aAddress_0; "Address"
0x18000a33f  mov     rcx, rsi
0x18000a342  lea     edx, [r9+7]
0x18000a346  call    FwXmlCompareName
0x18000a34b  mov     r15d, 30h ; '0'
0x18000a351  test    eax, eax
0x18000a353  jz      short loc_18000A2E2
0x18000a355  lea     rcx, [rsi+30h]
0x18000a359  xor     r9d, r9d
0x18000a35c  lea     r8, aHttpSchemasXml_10; "http://schemas.xmlsoap.org/ws/2004/08/a"...
0x18000a363  mov     edx, r15d
0x18000a366  call    FwXmlCompareName
0x18000a36b  test    eax, eax
0x18000a36d  jz      loc_18000A2E2
0x18000a373  mov     rax, [r14]
0x18000a376  mov     rsi, [rax+88h]
0x18000a37d  add     rsi, 98h
0x18000a384  jz      short loc_18000A310
0x18000a386  xor     r9d, r9d
0x18000a389  lea     r8, aReferenceparam; "ReferenceParameters"
0x18000a390  lea     edx, [r15-1Dh]
0x18000a394  mov     rcx, rsi
0x18000a397  call    FwXmlCompareName
0x18000a39c  test    eax, eax
0x18000a39e  jz      loc_18000A2E2
0x18000a3a4  lea     rcx, [rsi+30h]
0x18000a3a8  xor     r9d, r9d
0x18000a3ab  lea     r8, aHttpSchemasXml_10; "http://schemas.xmlsoap.org/ws/2004/08/a"...
0x18000a3b2  mov     edx, r15d
0x18000a3b5  call    FwXmlCompareName
0x18000a3ba  test    eax, eax
0x18000a3bc  jz      loc_18000A2E2
0x18000a3c2  cmp     [rsi+48h], r13d
0x18000a3c6  jbe     short loc_18000A3EB
0x18000a3c8  mov     r8d, 4033C3C4h
0x18000a3ce  mov     rcx, [rbx+108h]
0x18000a3d5  mov     edx, 80338041h
0x18000a3da  mov     rax, [rcx]
0x18000a3dd  mov     rax, [rax+40h]
0x18000a3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e6  jmp     loc_18000A2FA
0x18000a3eb  mov     [rbp+57h+var_88], r13
0x18000a3ef  mov     r14, r13
0x18000a3f2  mov     eax, r13d
0x18000a3f5  mov     [rbp+57h+var_8C], eax
0x18000a3f8  cmp     eax, [rsi+80h]
0x18000a3fe  jnb     loc_18000A530
0x18000a404  imul    r15, rax, 98h
0x18000a40b  add     r15, [rsi+88h]
0x18000a412  jnz     short loc_18000A45F
0x18000a414  mov     r9d, 80070057h; unsigned int
0x18000a41a  mov     [rsp+0D0h+var_B0], r13; struct IRequestContext *
0x18000a41f  lea     r8, a2060; "2060"
0x18000a426  mov     edx, 80Ch; unsigned int
0x18000a42b  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18000a432  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000a437  mov     r9d, 80070057h; unsigned int
0x18000a43d  mov     [rsp+0D0h+var_B0], r13; struct IRequestContext *
0x18000a442  lea     r8, a2060; "2060"
0x18000a449  mov     edx, 80Ch; unsigned int
0x18000a44e  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18000a455  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000a45a  jmp     loc_18000A4F3
0x18000a45f  xor     r9d, r9d
0x18000a462  lea     r8, aSelectorset; "SelectorSet"
0x18000a469  mov     rcx, r15
0x18000a46c  lea     edx, [r9+0Bh]
0x18000a470  call    FwXmlCompareName
0x18000a475  test    eax, eax
0x18000a477  jz      short loc_18000A4A3
0x18000a479  xor     r9d, r9d
0x18000a47c  lea     r8, aHttpSchemasDmt_5; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18000a483  lea     rcx, [r15+30h]
0x18000a487  lea     edx, [r9+2Eh]
0x18000a48b  call    FwXmlCompareName
0x18000a490  test    eax, eax
0x18000a492  jz      short loc_18000A4A3
0x18000a494  xor     r13d, r13d
0x18000a497  cmp     [rbp+57h+var_88], r13
0x18000a49b  jnz     short loc_18000A4FD
0x18000a49d  mov     [rbp+57h+var_88], r15
0x18000a4a1  jmp     short loc_18000A4F3
0x18000a4a3  xor     r9d, r9d
0x18000a4a6  lea     r8, aResourceuri_0; "ResourceURI"
0x18000a4ad  mov     rcx, r15
0x18000a4b0  lea     edx, [r9+0Bh]
0x18000a4b4  call    FwXmlCompareName
0x18000a4b9  test    eax, eax
0x18000a4bb  jz      short loc_18000A4D4
0x18000a4bd  xor     r9d, r9d
0x18000a4c0  lea     r8, aHttpSchemasDmt_5; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18000a4c7  lea     rcx, [r15+30h]
0x18000a4cb  lea     edx, [r9+2Eh]
0x18000a4cf  call    FwXmlCompareName
0x18000a4d4  xor     r13d, r13d
0x18000a4d7  test    eax, eax
0x18000a4d9  jz      short loc_18000A4F3
0x18000a4db  test    r14, r14
0x18000a4de  jnz     short loc_18000A527
0x18000a4e0  lea     r8d, [r13+2]
0x18000a4e4  mov     rcx, r15
0x18000a4e7  lea     rdx, [rbp+57h+var_80]
0x18000a4eb  call    FwXmlGetSimpleContentEx2
0x18000a4f0  mov     r14, rax
0x18000a4f3  mov     eax, [rbp+57h+var_8C]
0x18000a4f6  inc     eax
0x18000a4f8  jmp     loc_18000A3F5
0x18000a4fd  lea     r9, aSelectorset; "SelectorSet"
0x18000a504  mov     rcx, [rbx+108h]
0x18000a50b  mov     edx, 80338041h
0x18000a510  mov     r8d, 4033C3C6h
0x18000a516  mov     rax, [rcx]
0x18000a519  mov     rax, [rax+40h]
0x18000a51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a522  jmp     loc_18000A2FA
0x18000a527  lea     r9, aResourceuri_0; "ResourceURI"
0x18000a52e  jmp     short loc_18000A504
0x18000a530  test    r14, r14
0x18000a533  jnz     short loc_18000A540
0x18000a535  mov     r8d, 4033C3EEh
0x18000a53b  jmp     loc_18000A3CE
0x18000a540  test    r12, r12
0x18000a543  jz      short loc_18000A549
0x18000a545  mov     [r12], r14
0x18000a549  mov     edx, 2Fh ; '/'; Ch
0x18000a54e  mov     rcx, r14; Str
0x18000a551  call    cs:__imp_wcsrchr
0x18000a557  test    rax, rax
0x18000a55a  jz      loc_18000A2E2
0x18000a560  cmp     [rbx+122h], r13b
0x18000a567  jz      short loc_18000A572
0x18000a569  lea     rax, aMetadata; "Metadata"
0x18000a570  jmp     short loc_18000A576
0x18000a572  add     rax, 2
0x18000a576  mov     r8d, 1
0x18000a57c  mov     rdx, rax
0x18000a57f  mov     rcx, rdi
0x18000a582  call    cs:__imp_Instance_InitDynamic
0x18000a588  test    eax, eax
0x18000a58a  jz      short loc_18000A5A4
0x18000a58c  mov     rcx, [rbx+108h]
0x18000a593  mov     rax, [rcx]
0x18000a596  mov     rax, [rax+18h]
0x18000a59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a59f  jmp     loc_18000A2FA
0x18000a5a4  mov     rcx, [rdi]
0x18000a5a7  mov     rdx, [rbx+0E0h]
0x18000a5ae  mov     rax, [rcx]
0x18000a5b1  mov     rax, [rax+80h]
0x18000a5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5bd  test    eax, eax
0x18000a5bf  jnz     short loc_18000A58C
0x18000a5c1  mov     rdx, [rbx+0C0h]
0x18000a5c8  test    rdx, rdx
0x18000a5cb  jz      short loc_18000A5E0
0x18000a5cd  mov     rcx, [rdi]
0x18000a5d0  mov     rax, [rcx]
0x18000a5d3  mov     rax, [rax+28h]
0x18000a5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5dc  test    eax, eax
0x18000a5de  jnz     short loc_18000A58C
0x18000a5e0  mov     rcx, [rdi]
0x18000a5e3  mov     rdx, r14
0x18000a5e6  call    cs:__imp_Instance_SetResourceURI
0x18000a5ec  test    eax, eax
0x18000a5ee  jnz     short loc_18000A58C
0x18000a5f0  mov     r15, [rbp+57h+var_88]
0x18000a5f4  test    r15, r15
0x18000a5f7  jz      loc_18000A977
0x18000a5fd  mov     rcx, [r15+88h]
0x18000a604  mov     r12d, r13d
0x18000a607  mov     r13d, [r15+80h]
0x18000a60e  xor     r14d, r14d
0x18000a611  mov     [rbp+57h+var_88], rcx
0x18000a615  cmp     r12d, r13d
0x18000a618  jge     loc_18000A977
0x18000a61e  movsxd  rax, r12d
0x18000a621  imul    rsi, rax, 98h
0x18000a628  add     rsi, rcx
0x18000a62b  jz      loc_18000A918
0x18000a631  xor     r9d, r9d
0x18000a634  lea     r8, aSelector_0; "Selector"
0x18000a63b  mov     rcx, rsi
0x18000a63e  lea     edx, [r9+8]
0x18000a642  call    FwXmlCompareName
0x18000a647  test    eax, eax
0x18000a649  jz      loc_18000A93B
0x18000a64f  xor     r9d, r9d
0x18000a652  lea     rcx, [rsi+30h]
0x18000a656  lea     r8, aHttpSchemasDmt_5; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18000a65d  lea     edx, [r9+2Eh]
0x18000a661  call    FwXmlCompareName
0x18000a666  test    eax, eax
0x18000a668  jz      loc_18000A93B
0x18000a66e  cmp     r14d, [rsi+70h]
0x18000a672  jz      loc_18000A8CC
0x18000a678  movsxd  rax, r14d
0x18000a67b  imul    r15, rax, 68h ; 'h'
0x18000a67f  add     r15, [rsi+78h]
0x18000a683  lea     rcx, [r15+30h]
0x18000a687  test    rcx, rcx
0x18000a68a  jz      loc_18000A806
0x18000a690  cmp     dword ptr [rcx+10h], 2Eh ; '.'
0x18000a694  jnz     loc_18000A82D
0x18000a69a  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000a69f  mov     rcx, rax; String1
0x18000a6a2  lea     rdx, aHttpSchemasDmt_5; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18000a6a9  mov     r8d, 2Eh ; '.'; MaxCount
0x18000a6af  call    wcsncmp_0
0x18000a6b4  test    eax, eax
0x18000a6b6  jnz     loc_18000A82D
0x18000a6bc  test    r15, r15
0x18000a6bf  jz      loc_18000A806
0x18000a6c5  cmp     dword ptr [r15+10h], 4
0x18000a6ca  jnz     loc_18000A82D
0x18000a6d0  mov     rcx, r15
0x18000a6d3  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000a6d8  mov     rcx, rax; String1
0x18000a6db  lea     rdx, aName; "Name"
0x18000a6e2  mov     r8d, 4; MaxCount
0x18000a6e8  call    wcsncmp_0
0x18000a6ed  test    eax, eax
0x18000a6ef  jnz     loc_18000A82D
0x18000a6f5  mov     rcx, rsi
0x18000a6f8  mov     [rbp+57h+var_8C], 0Dh
0x18000a6ff  call    FwXmlNumChildren
0x18000a704  cmp     eax, 1
0x18000a707  jnz     short loc_18000A73D
0x18000a709  xor     edx, edx
0x18000a70b  mov     rcx, rsi
0x18000a70e  call    FwXmlGetChild
0x18000a713  xor     r9d, r9d
0x18000a716  lea     r8, aHttpSchemasXml_10; "http://schemas.xmlsoap.org/ws/2004/08/a"...
0x18000a71d  lea     rdx, aEndpointrefere; "EndpointReference"
0x18000a724  mov     rcx, rax
0x18000a727  mov     r14, rax
0x18000a72a  call    FwXmlCompareElementName
0x18000a72f  test    eax, eax
0x18000a731  jz      short loc_18000A73D
0x18000a733  mov     rsi, r14
0x18000a736  mov     [rbp+57h+var_8C], 0Eh
0x18000a73d  mov     rcx, r15
0x18000a740  call    FwXmlGetAttributeValue
0x18000a745  mov     r14d, [rbx+128h]
0x18000a74c  lea     r9, [rbp+57h+var_8C]; enum _MI_Type *
0x18000a750  mov     r15, rax
0x18000a753  mov     dword ptr [rbx+128h], 1
0x18000a75d  mov     rcx, [rdi]
0x18000a760  xor     eax, eax
0x18000a762  mov     [rsp+0D0h+var_98], rcx; struct _MI_Instance *
0x18000a767  xorps   xmm0, xmm0
0x18000a76a  mov     qword ptr [rbp+57h+var_78+20h], rax
0x18000a76e  mov     r8, rsi; struct _FWXML_ELEMENT *
0x18000a771  mov     [rbp+57h+var_90], al
0x18000a774  xor     edx, edx; unsigned int
  ... truncated ...
```
