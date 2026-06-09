# PacketParser::ParseHeader(CRequestContext *,_FWXML_ELEMENT *,int,CServiceCommonConfigSettings *)

- ea: `0x18001d5e0`
- end: `0x18001e617`
- name: `?ParseHeader@PacketParser@@AEAAHPEAVCRequestContext@@PEAU_FWXML_ELEMENT@@HPEAVCServiceCommonConfigSettings@@@Z`
- size: `4151`
- prototype: `int __fastcall(PacketParser *this, struct CRequestContext *, struct _FWXML_ELEMENT *, int, struct CServiceCommonConfigSettings *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b960`

## callees

- `0x180005d10`
- `0x180008920`
- `0x1800089e0`
- `0x180008a30`
- `0x1800092f0`
- `0x18000a9a0`
- `0x18000d780`
- `0x18001bce0`
- `0x18001d4f0`
- `0x18001d5e0`
- `0x18003c640`
- `0x1800621e0`
- `0x180082cd0`
- `0x180083650`
- `0x180083af0`
- `0x180084750`
- `0x180084a20`
- `0x180086480`
- `0x1800a1870`
- `0x1800a5150`
- `0x1800b4db0`
- `0x1800b6550`
- `0x1800c09f0`
- `0x1800c4850`
- `0x1800e8310`
- `0x1800eb2d0`
- `0x180112380`
- `0x1801133b0`
- `0x18011b6f0`
- `0x1801243e0`
- `0x180124460`
- `0x180124660`
- `0x180124a60`
- `0x180124d80`
- `0x1801251a0`
- `0x1801ba182`
- `0x1801c2010`

## string_xrefs

- `0x18001d65e`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell`
- `0x18001d700`: `http://schemas.xmlsoap.org/ws/2004/08/addressing`
- `0x18001d833`: `http://schemas.xmlsoap.org/ws/2004/08/addressing`
- `0x18001d644`: `http://schemas.microsoft.com/wbem/wsman/1/wsman.xsd`
- `0x18001d95a`: `http://schemas.microsoft.com/wbem/wsman/1/wsman.xsd`
- `0x18001d91b`: `http://schemas.xmlsoap.org/ws/2004/08/eventing`
- `0x18001db7d`: `ResourceURI`
- `0x18001e126`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e14c`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e16f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e197`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e26b`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e28e`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e2b1`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e2d4`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e2fc`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e31f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e342`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e365`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e388`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e3ab`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e3e6`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e409`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e42c`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e44f`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e472`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e495`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001e4b8`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18001d680`: `CompressionType`
- `0x18001e51d`: `http://schemas.microsoft.com/wbem/wsman/1/machineid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall PacketParser::ParseHeader(
        PacketParser *this,
        struct CRequestContext *a2,
        struct _FWXML_ELEMENT *a3,
        int a4,
        struct CServiceCommonConfigSettings *a5)
{
  struct CServiceCommonConfigSettings *v5; // rbp
  char *v6; // rbx
  int v7; // r12d
  int v12; // esi
  const wchar_t *v13; // rax
  int result; // eax
  _QWORD *v15; // rsi
  const wchar_t *v16; // rcx
  int v17; // ebx
  __int64 v18; // rcx
  const wchar_t *v19; // rcx
  __int64 v20; // rcx
  const wchar_t *v21; // rcx
  int v22; // ebx
  const wchar_t *v23; // rax
  __int64 v24; // rcx
  const wchar_t *v25; // rcx
  __int64 v26; // rcx
  const wchar_t *v27; // rcx
  const wchar_t *v28; // rcx
  const wchar_t *v29; // rax
  const wchar_t *v30; // rcx
  __int64 v31; // rcx
  const wchar_t *v32; // rcx
  int v33; // ebx
  const wchar_t *v34; // rax
  __int64 v35; // rcx
  const wchar_t *v36; // rcx
  __int64 v37; // rcx
  const wchar_t *v38; // rcx
  const wchar_t *v39; // rax
  const wchar_t *v40; // rax
  const wchar_t *v41; // rax
  const wchar_t *v42; // rax
  const wchar_t *v43; // rax
  const wchar_t *v44; // rax
  const wchar_t *v45; // rax
  int v46; // eax
  const wchar_t *v47; // rax
  const wchar_t *v48; // rax
  const wchar_t *v49; // rax
  const wchar_t *v50; // rax
  const wchar_t *v51; // rax
  const wchar_t *v52; // rax
  const wchar_t *v53; // rax
  int v54; // ebx
  const unsigned __int16 *String; // rax
  unsigned int v56; // ecx
  unsigned __int64 v57; // rsi
  _WORD *v58; // r14
  __int64 v59; // rcx
  _WORD *v60; // rdx
  _WORD *v61; // rbx
  _WORD *v62; // rax
  _WORD *SimpleContentEx2; // rax
  unsigned __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 ElementNamespacePrefix; // rbx
  __int64 ElementName; // rsi

  v5 = a5;
  v6 = (char *)a3 + 48;
  v7 = 0;
  if ( !a5 )
  {
    if ( a3 == (struct _FWXML_ELEMENT *)-48LL )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    }
    else
    {
      v15 = (_QWORD *)((char *)a3 + 56);
      if ( *((_DWORD *)a3 + 16) == 51 )
      {
        if ( *v15 == -1 )
          v28 = *(const wchar_t **)v6;
        else
          v28 = *(_QWORD *)v6 ? (const wchar_t *)(**(_QWORD **)v6 + 2LL * *v15) : 0LL;
        if ( !wcsncmp_0(v28, L"http://schemas.microsoft.com/wbem/wsman/1/wsman.xsd", 0x33u) )
        {
          if ( a3 )
          {
            if ( *((_DWORD *)a3 + 4) == 11 )
            {
              v29 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
              if ( !wcsncmp_0(v29, L"OperationID", 0xBu) )
                return PacketParser::ParseOperationId(this, a2, a3, a4);
            }
          }
          else
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
          }
        }
      }
      if ( *((_DWORD *)v6 + 4) == 46 )
      {
        if ( *v15 == -1 )
          v30 = *(const wchar_t **)v6;
        else
          v30 = *(_QWORD *)v6 ? (const wchar_t *)(**(_QWORD **)v6 + 2LL * *v15) : 0LL;
        if ( !wcsncmp_0(v30, L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 0x2Eu)
          && (unsigned int)FwXmlCompareName(a3, 16, L"OperationTimeout", 0) )
        {
          return PacketParser::ParseTimeout(this, a2, a3, a4, 0);
        }
      }
      if ( *((_DWORD *)v6 + 4) != 48 )
        return 1;
      if ( *v15 == -1 )
        v16 = *(const wchar_t **)v6;
      else
        v16 = *(_QWORD *)v6 ? (const wchar_t *)(**(_QWORD **)v6 + 2LL * *v15) : 0LL;
      if ( wcsncmp_0(v16, L"http://schemas.xmlsoap.org/ws/2004/08/addressing", 0x30u) )
        return 1;
      if ( a3 )
      {
        v17 = *((_DWORD *)a3 + 4);
        if ( v17 == 6 )
        {
          v35 = *((_QWORD *)a3 + 1);
          if ( v35 == -1 )
            v36 = *(const wchar_t **)a3;
          else
            v36 = *(_QWORD *)a3 ? (const wchar_t *)(**(_QWORD **)a3 + 2 * v35) : 0LL;
          if ( !wcsncmp_0(v36, L"Action", 6u) )
            return PacketParser::ParseAction(this, a2, a3, 1);
        }
        if ( v17 != 9 )
          return 1;
        v18 = *((_QWORD *)a3 + 1);
        if ( v18 == -1 )
          v19 = *(const wchar_t **)a3;
        else
          v19 = *(_QWORD *)a3 ? (const wchar_t *)(**(_QWORD **)a3 + 2 * v18) : 0LL;
        if ( wcsncmp_0(v19, L"MessageID", 9u) )
          return 1;
        if ( *((_DWORD *)this + 686) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_19bfc108516638e631769676a3097d1e_Traceguids);
          if ( (*(unsigned int (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
            (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858995LL,
              1077134247,
              L"a:MessageId");
          return 0;
        }
        if ( a2 )
        {
          if ( !(unsigned int)FwXmlIsSimpleContent(a3) )
            goto LABEL_28;
          SimpleContentEx2 = (_WORD *)FwXmlGetSimpleContentEx2(a3, &a5, 2);
          v61 = SimpleContentEx2;
          if ( !SimpleContentEx2 )
            goto LABEL_28;
          if ( !*SimpleContentEx2 )
            goto LABEL_28;
          v64 = -1;
          do
            ++v64;
          while ( v61[v64] );
          if ( v64 > 0x800 )
          {
LABEL_28:
            (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858767LL,
              1077134188);
            (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
              a2,
              2150858995LL,
              1077134247,
              L"a:MessageId");
            return 0;
          }
        }
        else
        {
          v61 = 0;
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\soaputils.cpp", 0x51u, L"81", 0x54Fu, 0);
        }
        v65 = -1;
        do
          ++v65;
        while ( v61[v65] );
        v56 = v65 + 1;
        v57 = v56;
        if ( v56 <= 0x2A )
        {
          v58 = (_WORD *)((char *)this + 2768);
LABEL_153:
          if ( v57 )
          {
            if ( v57 > 0x7FFFFFFF )
            {
              *v58 = 0;
            }
            else
            {
              v59 = 2147483646;
              v60 = v58;
              do
              {
                if ( !v59 )
                  break;
                if ( !*v61 )
                  break;
                *v60++ = *v61++;
                --v59;
                --v57;
              }
              while ( v57 );
              v62 = v60 - 1;
              if ( v57 )
                v62 = v60;
              *v62 = 0;
            }
          }
          *((_DWORD *)this + 690) = 0;
          result = 1;
          *((_QWORD *)this + 344) = v58;
          *((_DWORD *)this + 686) = 1;
          *((_DWORD *)this + 687) = 1;
          return result;
        }
        v66 = 2LL * v56;
        if ( !is_mul_ok(v56, 2u) )
          v66 = -1;
        v58 = (_WORD *)WSManMemory::Alloc(v66, 0, 0);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr((char *)this + 2856);
        *((_QWORD *)this + 357) = v58;
        if ( v58 )
          goto LABEL_153;
        (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 14);
        return 0;
      }
    }
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    return 1;
  }
  if ( a3 == (struct _FWXML_ELEMENT *)-48LL )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    goto LABEL_7;
  }
  if ( *((_DWORD *)a3 + 16) == 48 )
  {
    v20 = *((_QWORD *)a3 + 7);
    if ( v20 == -1 )
      v21 = *(const wchar_t **)v6;
    else
      v21 = *(_QWORD *)v6 ? (const wchar_t *)(**(_QWORD **)v6 + 2 * v20) : 0LL;
    if ( !wcsncmp_0(v21, L"http://schemas.xmlsoap.org/ws/2004/08/addressing", 0x30u) )
    {
      if ( a3 )
      {
        v22 = *((_DWORD *)a3 + 4);
        switch ( v22 )
        {
          case 6:
            v52 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
            if ( !wcsncmp_0(v52, L"Action", 6u) )
              return PacketParser::ParseAction(this, a2, a3, 0);
            break;
          case 2:
            v51 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
            if ( !wcsncmp_0(v51, L"To", 2u) )
              return PacketParser::ParseToAddress(this, a2, a3);
LABEL_43:
            if ( v22 == 4 )
            {
              v23 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
              if ( !wcsncmp_0(v23, L"From", 4u) )
                return 1;
            }
            goto LABEL_32;
          case 7:
            v42 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
            if ( !wcsncmp_0(v42, L"ReplyTo", 7u) )
              return PacketParser::ParseReplyTo(this, a2, a3);
            v43 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
            if ( !wcsncmp_0(v43, L"FaultTo", 7u) )
              return PacketParser::ParseFaultTo(this, a2, a3, a4);
            goto LABEL_32;
          case 9:
            v53 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
            if ( !wcsncmp_0(v53, L"MessageID", 9u) )
              return PacketParser::ParseMessageId(this, a2, a3, 0);
            goto LABEL_32;
        }
        goto LABEL_43;
      }
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      goto LABEL_184;
    }
  }
  v12 = *((_DWORD *)v6 + 4);
  if ( v12 != 46 )
  {
    if ( v12 != 51 )
      goto LABEL_7;
    v13 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v6);
    if ( wcsncmp_0(v13, L"http://schemas.microsoft.com/wbem/wsman/1/wsman.xsd", 0x33u) )
      goto LABEL_7;
    if ( !a3 )
    {
LABEL_184:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
LABEL_185:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      goto LABEL_32;
    }
    v46 = *((_DWORD *)a3 + 4);
    if ( v46 == 10 )
    {
      v48 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
      if ( !wcsncmp_0(v48, L"DataLocale", 0xAu) )
        return PacketParser::ParseDataLocale(this, a2, a3, a4);
      v49 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
      if ( !wcsncmp_0(v49, L"ActivityId", 0xAu) )
        return PacketParser::ParseActivityId(this, a2, a3, a4);
      goto LABEL_32;
    }
    if ( v46 == 9 )
    {
      v50 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
      if ( !wcsncmp_0(v50, L"SessionId", 9u) )
        return PacketParser::ParseSessionId(this, a2, a3, a4);
      goto LABEL_32;
    }
    if ( v46 != 11
      || (v47 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3),
          wcsncmp_0(v47, L"OperationID", 0xBu)) )
    {
LABEL_32:
      if ( !a4 )
        return 1;
      ElementNamespacePrefix = FwXmlGetElementNamespacePrefix(a3);
      ElementName = FwXmlGetElementNameEx(a3);
      *((_QWORD *)this + 486) = FwXmlGetElementNamespaceUrl(a3);
      *((_QWORD *)this + 483) = ElementName;
      *((_DWORD *)this + 968) = 0;
      *((_DWORD *)this + 964) = 1;
      *((_DWORD *)this + 965) = 1;
      *((_QWORD *)this + 485) = ElementNamespacePrefix;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_19bfc108516638e631769676a3097d1e_Traceguids, ElementName);
      if ( (*(unsigned int (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
        (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64, __int64))(*(_QWORD *)a2 + 64LL))(
          a2,
          2150858768LL,
          1077134233,
          ElementName);
      return 0;
    }
    return PacketParser::ParseOperationId(this, a2, a3, a4);
  }
  v24 = *((_QWORD *)v6 + 1);
  if ( v24 == -1 )
  {
    v25 = *(const wchar_t **)v6;
  }
  else if ( *(_QWORD *)v6 )
  {
    v25 = (const wchar_t *)(**(_QWORD **)v6 + 2 * v24);
  }
  else
  {
    v25 = 0;
  }
  if ( wcsncmp_0(v25, L"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd", 0x2Eu) )
  {
    v26 = *((_QWORD *)v6 + 1);
    if ( v26 == -1 )
    {
      v27 = *(const wchar_t **)v6;
    }
    else if ( *(_QWORD *)v6 )
    {
      v27 = (const wchar_t *)(**(_QWORD **)v6 + 2 * v26);
    }
    else
    {
      v27 = 0;
    }
    if ( !wcsncmp_0(v27, L"http://schemas.xmlsoap.org/ws/2004/08/eventing", 0x2Eu) )
    {
      if ( a3 )
      {
        if ( *((_DWORD *)a3 + 4) == 10 )
        {
          v31 = *((_QWORD *)a3 + 1);
          if ( v31 == -1 )
            v32 = *(const wchar_t **)a3;
          else
            v32 = *(_QWORD *)a3 ? (const wchar_t *)(**(_QWORD **)a3 + 2 * v31) : 0LL;
          if ( !wcsncmp_0(v32, L"Identifier", 0xAu) )
            return PacketParser::ParseSubscriptionID(this, a2, a3, a4);
        }
        goto LABEL_32;
      }
      goto LABEL_185;
    }
LABEL_7:
    if ( (unsigned int)FwXmlCompareName(v6, 55, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell", 0) )
    {
      if ( (unsigned int)FwXmlCompareName(a3, 15, L"CompressionType", 0) )
        return PacketParser::ParseShellCompression(this, a2, a3, a4);
    }
    else if ( (unsigned int)FwXmlCompareElementNameEx(
                              a3,
                              L"MachineID",
                              9,
                              L"http://schemas.microsoft.com/wbem/wsman/1/machineid",
                              51,
                              0) )
    {
      return PacketParser::ParseMachineID(this, a2, a3);
    }
    goto LABEL_32;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    goto LABEL_82;
  }
  v33 = *((_DWORD *)a3 + 4);
  if ( v33 != 11 )
  {
    switch ( v33 )
    {
      case 16:
        v40 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
        if ( !wcsncmp_0(v40, L"OperationTimeout", 0x10u) )
          return PacketParser::ParseTimeout(this, a2, a3, a4, v5);
        break;
      case 15:
        v41 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
        if ( !wcsncmp_0(v41, L"MaxEnvelopeSize", 0xFu) )
          return PacketParser::ParseMaxEnvelopeSize(this, a2, a3, a4, v5);
LABEL_80:
        if ( v33 == 6 )
        {
          v34 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
          if ( !wcsncmp_0(v34, L"Locale", 6u) )
          {
            v54 = PacketParser::ParseLocale(this, a2, a3, a4);
            String = Locale::GetString((PacketParser *)((char *)this + 3944));
            if ( Locale::SetLocale((struct CRequestContext *)((char *)a2 + 492), 0x400u, String, a2) )
              return v54;
            return 0;
          }
        }
        goto LABEL_82;
      case 9:
        v44 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
        if ( !wcsncmp_0(v44, L"OptionSet", 9u) )
          return PacketParser::ParseOptions(this, a2, a3, a4);
        goto LABEL_82;
    }
    goto LABEL_79;
  }
  v37 = *((_QWORD *)a3 + 1);
  if ( v37 == -1 )
  {
    v38 = *(const wchar_t **)a3;
  }
  else if ( *(_QWORD *)a3 )
  {
    v38 = (const wchar_t *)(**(_QWORD **)a3 + 2 * v37);
  }
  else
  {
    v38 = 0;
  }
  if ( !wcsncmp_0(v38, L"ResourceURI", 0xBu) )
    return PacketParser::ParseResourceUri(this, a2, a3, a4);
  v39 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
  if ( wcsncmp_0(v39, L"SelectorSet", 0xBu) )
  {
LABEL_79:
    if ( v33 != 16 )
      goto LABEL_80;
    v45 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
    if ( !wcsncmp_0(v45, L"FragmentTransfer", 0x10u) )
      return PacketParser::ParseFragment(this, a2, a3, a4);
LABEL_82:
    if ( (unsigned int)FwXmlCompareName(a3, 8, L"Bookmark", 0) )
      return PacketParser::ParseBookmark(this, a2, a3, a4);
    goto LABEL_32;
  }
  if ( *((_DWORD *)this + 924) )
  {
    if ( (*(unsigned int (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
      (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64))(*(_QWORD *)a2 + 64LL))(
        a2,
        2150858767LL,
        1077134259);
  }
  else
  {
    *((_QWORD *)this + 463) = a3;
    v7 = 1;
    *((_DWORD *)this + 928) = a4;
    *((_DWORD *)this + 924) = 1;
    *((_DWORD *)this + 925) = 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18001d5e0  push    rbx
0x18001d5e2  push    rbp
0x18001d5e3  push    rsi
0x18001d5e4  push    rdi
0x18001d5e5  push    r12
0x18001d5e7  push    r13
0x18001d5e9  push    r14
0x18001d5eb  push    r15
0x18001d5ed  sub     rsp, 38h
0x18001d5f1  mov     rbp, [rsp+78h+arg_20]
0x18001d5f9  lea     rbx, [r8+30h]
0x18001d5fd  xor     r12d, r12d
0x18001d600  mov     r14d, r9d
0x18001d603  mov     rdi, r8
0x18001d606  mov     r15, rdx
0x18001d609  mov     r13, rcx
0x18001d60c  test    rbp, rbp
0x18001d60f  jz      loc_18001D6AF
0x18001d615  test    rbx, rbx
0x18001d618  jz      loc_18001E254
0x18001d61e  cmp     dword ptr [rbx+10h], 30h ; '0'
0x18001d622  jz      loc_18001D80C
0x18001d628  mov     esi, [rbx+10h]
0x18001d62b  cmp     esi, 2Eh ; '.'
0x18001d62e  jz      loc_18001D8B0
0x18001d634  cmp     esi, 33h ; '3'
0x18001d637  jnz     short loc_18001D65B
0x18001d639  mov     rcx, rbx
0x18001d63c  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18001d641  mov     rcx, rax; String1
0x18001d644  lea     rdx, aHttpSchemasMic_49; "http://schemas.microsoft.com/wbem/wsman"...
0x18001d64b  mov     r8d, esi; MaxCount
0x18001d64e  call    wcsncmp_0
0x18001d653  test    eax, eax
0x18001d655  jz      loc_18001DD61
0x18001d65b  xor     r9d, r9d
0x18001d65e  lea     r8, aHttpSchemasMic_40; "http://schemas.microsoft.com/wbem/wsman"...
0x18001d665  mov     edx, 37h ; '7'
0x18001d66a  mov     rcx, rbx
0x18001d66d  call    FwXmlCompareName
0x18001d672  mov     rcx, rdi
0x18001d675  test    eax, eax
0x18001d677  jz      loc_18001E518
0x18001d67d  xor     r9d, r9d
0x18001d680  lea     r8, aCompressiontyp; "CompressionType"
0x18001d687  mov     edx, 0Fh
0x18001d68c  call    FwXmlCompareName
0x18001d691  test    eax, eax
0x18001d693  jz      loc_18001D7ED
0x18001d699  mov     r9d, r14d; int
0x18001d69c  mov     r8, rdi; struct _FWXML_ELEMENT *
0x18001d69f  mov     rdx, r15; struct IRequestContext *
0x18001d6a2  mov     rcx, r13; this
0x18001d6a5  call    ?ParseShellCompression@PacketParser@@AEAAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@H@Z; PacketParser::ParseShellCompression(IRequestContext *,_FWXML_ELEMENT *,int)
0x18001d6aa  jmp     loc_18001D7FB
0x18001d6af  test    rbx, rbx
0x18001d6b2  jz      loc_18001E10F
0x18001d6b8  cmp     dword ptr [rbx+10h], 33h ; '3'
0x18001d6bc  lea     rsi, [rbx+8]
0x18001d6c0  jz      loc_18001D934
0x18001d6c6  cmp     dword ptr [rbx+10h], 2Eh ; '.'
0x18001d6ca  jz      loc_18001D9BC
0x18001d6d0  cmp     dword ptr [rbx+10h], 30h ; '0'
0x18001d6d4  jnz     loc_18001D7F6
0x18001d6da  mov     rcx, [rsi]
0x18001d6dd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d6e1  jz      loc_18001DF7C
0x18001d6e7  mov     rax, [rbx]
0x18001d6ea  test    rax, rax
0x18001d6ed  jz      loc_18001DF84
0x18001d6f3  mov     rax, [rax]
0x18001d6f6  lea     rcx, [rax+rcx*2]; String1
0x18001d6fa  mov     r8d, 30h ; '0'; MaxCount
0x18001d700  lea     rdx, aHttpSchemasXml_10; "http://schemas.xmlsoap.org/ws/2004/08/a"...
0x18001d707  call    wcsncmp_0
0x18001d70c  test    eax, eax
0x18001d70e  jnz     loc_18001D7F6
0x18001d714  test    rdi, rdi
0x18001d717  jz      loc_18001E132
0x18001d71d  mov     ebx, [rdi+10h]
0x18001d720  cmp     ebx, 6
0x18001d723  jz      loc_18001DB05
0x18001d729  cmp     ebx, 9
0x18001d72c  jnz     loc_18001D7F6
0x18001d732  mov     rcx, [rdi+8]
0x18001d736  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d73a  jz      loc_18001DFBC
0x18001d740  mov     rax, [rdi]
0x18001d743  test    rax, rax
0x18001d746  jz      loc_18001DFC4
0x18001d74c  mov     rax, [rax]
0x18001d74f  lea     rcx, [rax+rcx*2]; String1
0x18001d753  mov     r8d, 9; MaxCount
0x18001d759  lea     rdx, aMessageid; "MessageID"
0x18001d760  call    wcsncmp_0
0x18001d765  test    eax, eax
0x18001d767  jnz     loc_18001D7F6
0x18001d76d  cmp     [r13+0AB8h], r12d
0x18001d774  jnz     loc_18001DFCC
0x18001d77a  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18001d781  test    r15, r15
0x18001d784  jz      loc_18001E1CF
0x18001d78a  mov     rcx, rdi
0x18001d78d  call    FwXmlIsSimpleContent
0x18001d792  test    eax, eax
0x18001d794  jnz     loc_18001E0A9
0x18001d79a  mov     rax, [r15]
0x18001d79d  mov     edx, 8033800Fh
0x18001d7a2  mov     r8d, 4033C36Ch
0x18001d7a8  mov     rcx, r15
0x18001d7ab  mov     rax, [rax+40h]
0x18001d7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b4  mov     rcx, [r15]
0x18001d7b7  mov     rax, [rcx+40h]
0x18001d7bb  lea     r9, aAMessageid; "a:MessageId"
0x18001d7c2  mov     r8d, 4033C3A7h
0x18001d7c8  mov     edx, 803380F3h
0x18001d7cd  mov     rcx, r15
0x18001d7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d5  mov     eax, r12d
0x18001d7d8  jmp     short loc_18001D7FB
0x18001d7da  test    rdi, rdi
0x18001d7dd  jz      loc_18001E394
0x18001d7e3  cmp     dword ptr [rdi+10h], 0Ah
0x18001d7e7  jz      loc_18001DA1F
0x18001d7ed  test    r14d, r14d
0x18001d7f0  jnz     loc_18001E559
0x18001d7f6  mov     eax, 1
0x18001d7fb  add     rsp, 38h
0x18001d7ff  pop     r15
0x18001d801  pop     r14
0x18001d803  pop     r13
0x18001d805  pop     r12
0x18001d807  pop     rdi
0x18001d808  pop     rsi
0x18001d809  pop     rbp
0x18001d80a  pop     rbx
0x18001d80b  retn
0x18001d80c  mov     rcx, [rbx+8]
0x18001d810  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d814  jz      loc_18001DF3C
0x18001d81a  mov     rax, [rbx]
0x18001d81d  test    rax, rax
0x18001d820  jz      loc_18001DF44
0x18001d826  mov     rax, [rax]
0x18001d829  lea     rcx, [rax+rcx*2]; String1
0x18001d82d  mov     r8d, 30h ; '0'; MaxCount
0x18001d833  lea     rdx, aHttpSchemasXml_10; "http://schemas.xmlsoap.org/ws/2004/08/a"...
0x18001d83a  call    wcsncmp_0
0x18001d83f  test    eax, eax
0x18001d841  jnz     loc_18001D628
0x18001d847  test    rdi, rdi
0x18001d84a  jz      loc_18001E2E5
0x18001d850  mov     ebx, [rdi+10h]
0x18001d853  cmp     ebx, 6
0x18001d856  jz      loc_18001DE81
0x18001d85c  cmp     ebx, 2
0x18001d85f  jz      loc_18001DE49
0x18001d865  cmp     ebx, 7
0x18001d868  jz      loc_18001DC75
0x18001d86e  cmp     ebx, 9
0x18001d871  jz      loc_18001DEBC
0x18001d877  cmp     ebx, 7
0x18001d87a  jz      loc_18001DC9A
0x18001d880  cmp     ebx, 4
0x18001d883  jnz     loc_18001D7ED
0x18001d889  mov     rcx, rdi
0x18001d88c  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18001d891  mov     rcx, rax; String1
0x18001d894  lea     rdx, aFrom; "From"
0x18001d89b  mov     r8d, ebx; MaxCount
0x18001d89e  call    wcsncmp_0
0x18001d8a3  test    eax, eax
0x18001d8a5  jnz     loc_18001D7ED
0x18001d8ab  jmp     loc_18001D7F6
0x18001d8b0  mov     rcx, [rbx+8]
0x18001d8b4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d8b8  jz      loc_18001DF4C
0x18001d8be  mov     rax, [rbx]
0x18001d8c1  test    rax, rax
0x18001d8c4  jz      loc_18001DF54
0x18001d8ca  mov     rax, [rax]
0x18001d8cd  lea     rcx, [rax+rcx*2]; String1
0x18001d8d1  mov     r8d, 2Eh ; '.'; MaxCount
0x18001d8d7  lea     rdx, aHttpSchemasDmt_5; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18001d8de  call    wcsncmp_0
0x18001d8e3  test    eax, eax
0x18001d8e5  jz      loc_18001DA70
0x18001d8eb  cmp     esi, 2Eh ; '.'
0x18001d8ee  jnz     loc_18001D634
0x18001d8f4  mov     rcx, [rbx+8]
0x18001d8f8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d8fc  jz      loc_18001DF8C
0x18001d902  mov     rax, [rbx]
0x18001d905  test    rax, rax
0x18001d908  jz      loc_18001DF9C
0x18001d90e  mov     rax, [rax]
0x18001d911  lea     rcx, [rax+rcx*2]; String1
0x18001d915  mov     r8d, 2Eh ; '.'; MaxCount
0x18001d91b  lea     rdx, aHttpSchemasXml_7; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x18001d922  call    wcsncmp_0
0x18001d927  test    eax, eax
0x18001d929  jnz     loc_18001D65B
0x18001d92f  jmp     loc_18001D7DA
0x18001d934  mov     rcx, [rsi]
0x18001d937  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d93b  jz      loc_18001DF5C
0x18001d941  mov     rax, [rbx]
0x18001d944  test    rax, rax
0x18001d947  jz      loc_18001DF64
0x18001d94d  mov     rax, [rax]
0x18001d950  lea     rcx, [rax+rcx*2]; String1
0x18001d954  mov     r8d, 33h ; '3'; MaxCount
0x18001d95a  lea     rdx, aHttpSchemasMic_49; "http://schemas.microsoft.com/wbem/wsman"...
0x18001d961  call    wcsncmp_0
0x18001d966  test    eax, eax
0x18001d968  jnz     loc_18001D6C6
0x18001d96e  test    rdi, rdi
0x18001d971  jz      loc_18001E180
0x18001d977  cmp     dword ptr [rdi+10h], 0Bh
0x18001d97b  jnz     loc_18001D6C6
0x18001d981  mov     rcx, rdi
0x18001d984  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18001d989  mov     rcx, rax; String1
0x18001d98c  lea     rdx, aOperationid; "OperationID"
0x18001d993  mov     r8d, 0Bh; MaxCount
0x18001d999  call    wcsncmp_0
0x18001d99e  test    eax, eax
0x18001d9a0  jnz     loc_18001D6C6
0x18001d9a6  mov     r9d, r14d; int
0x18001d9a9  mov     r8, rdi; struct _FWXML_ELEMENT *
0x18001d9ac  mov     rdx, r15; struct IRequestContext *
0x18001d9af  mov     rcx, r13; this
0x18001d9b2  call    ?ParseOperationId@PacketParser@@AEAAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@H@Z; PacketParser::ParseOperationId(IRequestContext *,_FWXML_ELEMENT *,int)
0x18001d9b7  jmp     loc_18001D7FB
0x18001d9bc  mov     rcx, [rsi]
0x18001d9bf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d9c3  jz      loc_18001DF6C
0x18001d9c9  mov     rax, [rbx]
0x18001d9cc  test    rax, rax
0x18001d9cf  jz      loc_18001DF74
0x18001d9d5  mov     rax, [rax]
0x18001d9d8  lea     rcx, [rax+rcx*2]; String1
0x18001d9dc  mov     r8d, 2Eh ; '.'; MaxCount
0x18001d9e2  lea     rdx, aHttpSchemasDmt_5; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x18001d9e9  call    wcsncmp_0
0x18001d9ee  test    eax, eax
0x18001d9f0  jnz     loc_18001D6D0
0x18001d9f6  xor     r9d, r9d
0x18001d9f9  lea     r8, aOperationtimeo; "OperationTimeout"
0x18001da00  mov     edx, 10h
0x18001da05  mov     rcx, rdi
0x18001da08  call    FwXmlCompareName
0x18001da0d  test    eax, eax
0x18001da0f  jz      loc_18001D6D0
0x18001da15  mov     [rsp+78h+var_58], r12
0x18001da1a  jmp     loc_18001DC1F
0x18001da1f  mov     rcx, [rdi+8]
0x18001da23  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001da27  jz      loc_18001DFA4
0x18001da2d  mov     rax, [rdi]
0x18001da30  test    rax, rax
0x18001da33  jz      loc_18001DFAC
0x18001da39  mov     rax, [rax]
0x18001da3c  lea     rcx, [rax+rcx*2]; String1
0x18001da40  mov     r8d, 0Ah; MaxCount
0x18001da46  lea     rdx, aIdentifier; "Identifier"
0x18001da4d  call    wcsncmp_0
0x18001da52  test    eax, eax
0x18001da54  jnz     loc_18001D7ED
0x18001da5a  mov     r9d, r14d; int
0x18001da5d  mov     r8, rdi; struct _FWXML_ELEMENT *
0x18001da60  mov     rdx, r15; struct IRequestContext *
0x18001da63  mov     rcx, r13; this
0x18001da66  call    ?ParseSubscriptionID@PacketParser@@AEAAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@H@Z; PacketParser::ParseSubscriptionID(IRequestContext *,_FWXML_ELEMENT *,int)
0x18001da6b  jmp     loc_18001D7FB
0x18001da70  test    rdi, rdi
0x18001da73  jz      loc_18001E3CF
0x18001da79  mov     ebx, [rdi+10h]
0x18001da7c  cmp     ebx, 0Bh
0x18001da7f  jz      loc_18001DB56
0x18001da85  cmp     ebx, 10h
0x18001da88  jz      loc_18001DBF5
0x18001da8e  cmp     ebx, 0Fh
0x18001da91  jz      loc_18001DC35
0x18001da97  cmp     ebx, 9
0x18001da9a  jz      loc_18001DCEB
0x18001daa0  cmp     ebx, 10h
0x18001daa3  jz      loc_18001DD26
0x18001daa9  cmp     ebx, 6
0x18001daac  jnz     short loc_18001DAD0
0x18001daae  mov     rcx, rdi
0x18001dab1  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18001dab6  mov     rcx, rax; String1
0x18001dab9  lea     rdx, aLocale; "Locale"
0x18001dac0  mov     r8d, ebx; MaxCount
0x18001dac3  call    wcsncmp_0
0x18001dac8  test    eax, eax
0x18001daca  jz      loc_18001DEF7
0x18001dad0  xor     r9d, r9d
  ... truncated ...
```
