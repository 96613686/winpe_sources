# VmIPv6Configuration::Apply(ushort const *,ushort)

- ea: `0x18022ef7c`
- end: `0x18022fe02`
- name: `?Apply@VmIPv6Configuration@@QEAAJPEBGG@Z`
- size: `3718`
- prototype: `__int64 __fastcall(VmIPv6Configuration *__hidden this, const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18016ae40`

## callees

- `0x180001b68`
- `0x180001c08`
- `0x180005628`
- `0x18005f0c0`
- `0x180061240`
- `0x1800666b4`
- `0x18006c530`
- `0x180168f58`
- `0x180180c8c`
- `0x18022ef7c`
- `0x18022fe08`
- `0x180230064`
- `0x180230118`
- `0x1802301a4`
- `0x1802302dc`
- `0x18023127c`
- `0x1802313e4`
- `0x1802315d0`
- `0x1802318ec`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022f14d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022f1c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022faa4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022f14d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022f1c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022faa4`
- `OLEAUT32!__imp_SysAllocString` at `0x18022f0e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18022f10d`
- `OLEAUT32!__imp_SysAllocString` at `0x18022f0e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18022f10d`
- `OLEAUT32!__imp_VariantInit` at `0x18022f315`
- `OLEAUT32!__imp_VariantInit` at `0x18022f6b9`
- `OLEAUT32!__imp_VariantInit` at `0x18022fa58`
- `OLEAUT32!__imp_VariantInit` at `0x18022f315`
- `OLEAUT32!__imp_VariantInit` at `0x18022f6b9`
- `OLEAUT32!__imp_VariantInit` at `0x18022fa58`
- `OLEAUT32!__imp_VariantClear` at `0x18022f5cc`
- `OLEAUT32!__imp_VariantClear` at `0x18022f901`
- `OLEAUT32!__imp_VariantClear` at `0x18022fb0d`
- `OLEAUT32!__imp_VariantClear` at `0x18022fbd7`
- `OLEAUT32!__imp_VariantClear` at `0x18022fbe6`
- `OLEAUT32!__imp_VariantClear` at `0x18022f5cc`
- `OLEAUT32!__imp_VariantClear` at `0x18022f901`
- `OLEAUT32!__imp_VariantClear` at `0x18022fb0d`
- `OLEAUT32!__imp_VariantClear` at `0x18022fbd7`
- `OLEAUT32!__imp_VariantClear` at `0x18022fbe6`

## string_xrefs

- `0x18022fc64`: `onecore\vm\common\vml\VmCom.h`
- `0x18022fc8d`: `onecore\vm\common\vml\VmCom.h`
- `0x18022fddb`: `onecore\vm\common\vml\VmCom.h`
- `0x18022fc78`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fca1`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fcb6`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fcf1`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fd05`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fd2b`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fd66`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fd7a`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fda0`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fdef`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022fcdd`: `onecore\vm\common\wmimgmt\VmWbemCore.h`
- `0x18022fd52`: `onecore\vm\common\wmimgmt\VmWbemCore.h`
- `0x18022fdc7`: `onecore\vm\common\wmimgmt\VmWbemCore.h`
- `0x18022fc28`: `onecore\vm\common\vml\VmVariant.h`
- `0x18022fc4f`: `onecore\vm\common\vml\VmVariant.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall VmIPv6Configuration::Apply(
        VmIPv6Configuration *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        int a4)
{
  VmIPv6Configuration *v5; // rsi
  _DWORD *v6; // rcx
  __int64 v7; // rax
  _DWORD *v8; // rcx
  __int64 result; // rax
  unsigned int InterfaceIndex; // ebx
  HRESULT Instance; // eax
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  _DWORD *v18; // rcx
  Vml::VmSharableObject *v19; // rbx
  __int16 v20; // r8
  int v21; // r9d
  unsigned int i; // r15d
  int v23; // eax
  const unsigned __int16 *v24; // r8
  int v25; // eax
  _DWORD *v26; // rcx
  struct IWbemClassObject *v27; // r8
  const char *v28; // r9
  unsigned int j; // r15d
  int v30; // eax
  const unsigned __int16 *v31; // r8
  int v32; // eax
  _DWORD *v33; // rcx
  const char *v34; // r9
  _DWORD *v35; // rcx
  __int64 OneWmiInstance; // rax
  struct IWbemClassObject *v37; // r14
  HRESULT v38; // eax
  int v39; // eax
  _DWORD *v40; // rcx
  const char *v41; // r9
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  int ppv; // [rsp+20h] [rbp-158h]
  int ppva; // [rsp+20h] [rbp-158h]
  int ppvb; // [rsp+20h] [rbp-158h]
  unsigned __int16 **ppvc; // [rsp+20h] [rbp-158h]
  unsigned __int16 **ppvd; // [rsp+20h] [rbp-158h]
  unsigned __int16 **ppve; // [rsp+20h] [rbp-158h]
  _BYTE v55[2]; // [rsp+30h] [rbp-148h] BYREF
  unsigned __int16 v56; // [rsp+32h] [rbp-146h]
  unsigned int v57; // [rsp+34h] [rbp-144h]
  unsigned int v58; // [rsp+38h] [rbp-140h]
  unsigned int v59; // [rsp+3Ch] [rbp-13Ch] BYREF
  unsigned __int16 v60; // [rsp+40h] [rbp-138h] BYREF
  unsigned __int16 v61; // [rsp+48h] [rbp-130h]
  VmIPv6Configuration *v62; // [rsp+50h] [rbp-128h] BYREF
  Vml::VmSharableObject *v63; // [rsp+58h] [rbp-120h] BYREF
  const char *v64; // [rsp+60h] [rbp-118h] BYREF
  unsigned int v65; // [rsp+68h] [rbp-110h]
  struct IWbemClassObject *v66; // [rsp+70h] [rbp-108h] BYREF
  struct IWbemClassObject *v67; // [rsp+78h] [rbp-100h] BYREF
  struct IWbemClassObject *v68; // [rsp+80h] [rbp-F8h] BYREF
  struct IWbemContext *v69; // [rsp+88h] [rbp-F0h] BYREF
  struct IWbemContext *v70; // [rsp+90h] [rbp-E8h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-E0h] BYREF
  VARIANTARG v72; // [rsp+B0h] [rbp-C8h] BYREF
  VARIANTARG v73; // [rsp+C8h] [rbp-B0h] BYREF
  _OWORD Src[2]; // [rsp+E0h] [rbp-98h] BYREF
  VmIPv6Configuration **v75; // [rsp+100h] [rbp-78h]
  __int64 v76; // [rsp+108h] [rbp-70h]
  Vml::VmSharableObject **v77; // [rsp+110h] [rbp-68h]
  __int64 v78; // [rsp+118h] [rbp-60h]
  struct IWbemClassObject **v79; // [rsp+120h] [rbp-58h]
  __int64 v80; // [rsp+128h] [rbp-50h]
  struct IWbemClassObject **v81; // [rsp+130h] [rbp-48h]
  __int64 v82; // [rsp+138h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v56 = a3;
  v5 = this;
  v64 = (const char *)this;
  v62 = this;
  v61 = a3;
  v6 = (_DWORD *)*((_QWORD *)this + 23);
  if ( *v6 > 4u )
  {
    v67 = (struct IWbemClassObject *)v5;
    v68 = (struct IWbemClassObject *)((__int64)(*((_QWORD *)v5 + 20) - *((_QWORD *)v5 + 19)) >> 3);
    v63 = (Vml::VmSharableObject *)((__int64)(*((_QWORD *)v5 + 17) - *((_QWORD *)v5 + 16)) >> 3);
    v81 = &v67;
    v82 = 8;
    v79 = &v68;
    v80 = 8;
    v77 = &v63;
    v78 = 8;
    v75 = (VmIPv6Configuration **)"Apply started";
    v76 = 14;
    tlgWriteTransfer_EventWriteTransfer(v6, byte_180343711, 0, 0, 6, Src);
  }
  v7 = *((_QWORD *)v5 + 17);
  if ( v7 == *((_QWORD *)v5 + 16) )
  {
    v8 = (_DWORD *)*((_QWORD *)v5 + 23);
    if ( *v8 > 4u )
    {
      v64 = (const char *)v5;
      v67 = (struct IWbemClassObject *)"Apply skipped";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v8,
        (unsigned int)&dword_18034376C,
        a3,
        a4,
        (__int64)&v67,
        (__int64)&v64);
    }
    return 0;
  }
  else
  {
    try
    {
      InterfaceIndex = VmIPv6Configuration::GetInterfaceIndex(v5, a2);
      v57 = InterfaceIndex;
      v73.vt = 8;
      v73.llVal = (LONGLONG)SysAllocString(L"ActiveStore");
      if ( !v73.llVal )
      {
        v42 = wil::verify_hresult<long>(2147942414LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3CA,
          (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
          (const char *)v42,
          ppv);
      }
      v72.vt = 8;
      v72.llVal = (LONGLONG)SysAllocString(L"PersistentStore");
      if ( !v72.llVal )
      {
        v43 = wil::verify_hresult<long>(2147942414LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3CA,
          (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
          (const char *)v43,
          ppv);
      }
      v70 = 0;
      Instance = CoCreateInstance(&CLSID_WbemContext, 0, 1u, &GUID_44aca674_e8fc_11d0_a07c_00c04fb68820, (LPVOID *)&v70);
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x95F,
          (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
          (const char *)(unsigned int)Instance,
          ppva);
      v12 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))v70->lpVtbl->SetValue)(
              v70,
              L"PolicyStore",
              0,
              &v73);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x141,
          (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
          (const char *)(unsigned int)v12,
          ppva);
      v69 = 0;
      v13 = CoCreateInstance(&CLSID_WbemContext, 0, 1u, &GUID_44aca674_e8fc_11d0_a07c_00c04fb68820, (LPVOID *)&v69);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x95F,
          (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
          (const char *)(unsigned int)v13,
          ppvb);
      v14 = ((__int64 (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))v69->lpVtbl->SetValue)(
              v69,
              L"PolicyStore",
              0,
              &v72);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
          (const char *)(unsigned int)v14,
          ppvb);
      v63 = 0;
      v15 = VmIPv6Configuration::GetInstance(a2, v56, *((const struct _tlgProvider_t **)v5 + 23), &v63);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
          (const char *)(unsigned int)v15,
          ppvb);
      v65 = InterfaceIndex;
      v18 = (_DWORD *)*((_QWORD *)v5 + 23);
      if ( *v18 > 4u )
      {
        v67 = (struct IWbemClassObject *)"clearing target";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v18,
          (unsigned int)byte_1803437A5,
          v16,
          v17,
          (__int64)&v67);
      }
      v19 = v63;
      VmIPv6Configuration::Clear(v63);
      if ( (__int64)(*((_QWORD *)v5 + 17) - *((_QWORD *)v5 + 16)) >> 3 )
      {
        v67 = 0;
        v68 = 0;
        VmWbemCore::GetWbemObject(*((VmWbemCore **)v5 + 10), L"\\\\.\\root\\standardcimv2:MSFT_NetIPAddress", &v67, v70);
        VmWbemCore::GetWbemObject(*((VmWbemCore **)v5 + 10), L"\\\\.\\root\\standardcimv2:MSFT_NetIPAddress", &v68, v69);
        for ( i = 0; ; ++i )
        {
          v58 = i;
          if ( i >= (unsigned __int64)((__int64)(*((_QWORD *)v5 + 17) - *((_QWORD *)v5 + 16)) >> 3) )
            break;
          v66 = 0;
          VariantInit(&pvarg);
          if ( !(unsigned int)VmWbemCore::GetNullableProperty(
                                *((VmWbemCore **)v5 + 10),
                                *(struct IWbemClassObject **)(*((_QWORD *)v5 + 16) + 8LL * i),
                                L"Store",
                                (struct Vml::VmVariant *)&pvarg) )
          {
            v44 = wil::verify_hresult<long>(2147614725LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA0,
              (unsigned int)"onecore\\vm\\common\\wmimgmt\\VmWbemCore.h",
              (const char *)v44,
              ppvb);
          }
          if ( pvarg.bVal )
          {
            if ( pvarg.bVal != 1 )
            {
              v45 = wil::verify_hresult<long>(2147549183LL);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x17D,
                (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
                (const char *)v45,
                ppvb);
            }
            v25 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v67->lpVtbl->SpawnInstance)(
                    v67,
                    0,
                    &v66);
            if ( v25 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x179,
                (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
                (const char *)(unsigned int)v25,
                ppvb);
          }
          else
          {
            v23 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v68->lpVtbl->SpawnInstance)(
                    v68,
                    0,
                    &v66);
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x175,
                (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
                (const char *)(unsigned int)v23,
                ppvb);
          }
          VmWbemCore::SetProperty(*((VmWbemCore **)v5 + 10), v66, v24, v57);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 16) + 8LL * i),
            L"AddressFamily",
            18);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 16) + 8LL * i),
            L"PrefixOrigin",
            18);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 16) + 8LL * i),
            L"SuffixOrigin",
            18);
          v26 = (_DWORD *)*((_QWORD *)v5 + 23);
          if ( *v26 > 4u )
          {
            v60 = v56;
            v59 = v57;
            v55[0] = pvarg.bVal;
            v81 = (struct IWbemClassObject **)"adding IP";
            v82 = 10;
            v79 = (struct IWbemClassObject **)&v60;
            v80 = 2;
            v77 = (Vml::VmSharableObject **)&v59;
            v78 = 4;
            v75 = (VmIPv6Configuration **)v55;
            v76 = 1;
            tlgWriteTransfer_EventWriteTransfer(v26, &dword_1803436B4, 0, 0, 6, Src);
          }
          v27 = *(struct IWbemClassObject **)(*((_QWORD *)v62 + 16) + 8LL * i);
          if ( v56 == 23 )
            VmIPv6Configuration::CopyPropertyValue(v5, v66, v27, L"IPv6Address", 8);
          else
            VmIPv6Configuration::CopyPropertyValue(v5, v66, v27, L"IPv4Address", 8);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 16) + 8LL * i),
            L"PrefixLength",
            17);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 16) + 8LL * i),
            L"Type",
            17);
          try
          {
            VmWbemCore::PutObject(*((VmWbemCore **)v5 + 10), v66, 2u, 0, ppvc);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x1A8,
              (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
              v28);
            v57 = v65;
            v19 = v63;
            i = v58;
            v5 = (VmIPv6Configuration *)v64;
            v56 = v61;
          }
          VariantClear(&pvarg);
          if ( v66 )
            ((void (__fastcall *)(struct IWbemClassObject *))v66->lpVtbl->Release)(v66);
        }
        if ( v68 )
          ((void (__fastcall *)(struct IWbemClassObject *))v68->lpVtbl->Release)(v68);
        if ( v67 )
          ((void (__fastcall *)(struct IWbemClassObject *))v67->lpVtbl->Release)(v67);
      }
      if ( (__int64)(*((_QWORD *)v5 + 20) - *((_QWORD *)v5 + 19)) >> 3 )
      {
        v68 = 0;
        v67 = 0;
        VmWbemCore::GetWbemObject(*((VmWbemCore **)v5 + 10), L"\\\\.\\root\\standardcimv2:MSFT_NetRoute", &v68, v70);
        VmWbemCore::GetWbemObject(*((VmWbemCore **)v5 + 10), L"\\\\.\\root\\standardcimv2:MSFT_NetRoute", &v67, v69);
        for ( j = 0; ; ++j )
        {
          v58 = j;
          if ( j >= (unsigned __int64)((__int64)(*((_QWORD *)v5 + 20) - *((_QWORD *)v5 + 19)) >> 3) )
            break;
          v66 = 0;
          VariantInit(&pvarg);
          if ( !(unsigned int)VmWbemCore::GetNullableProperty(
                                *((VmWbemCore **)v5 + 10),
                                *(struct IWbemClassObject **)(*((_QWORD *)v5 + 19) + 8LL * j),
                                L"Store",
                                (struct Vml::VmVariant *)&pvarg) )
          {
            v46 = wil::verify_hresult<long>(2147614725LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA0,
              (unsigned int)"onecore\\vm\\common\\wmimgmt\\VmWbemCore.h",
              (const char *)v46,
              ppvb);
          }
          if ( pvarg.bVal )
          {
            if ( pvarg.bVal != 1 )
            {
              v47 = wil::verify_hresult<long>(2147549183LL);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1D3,
                (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
                (const char *)v47,
                ppvb);
            }
            v32 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v68->lpVtbl->SpawnInstance)(
                    v68,
                    0,
                    &v66);
            if ( v32 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1CF,
                (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
                (const char *)(unsigned int)v32,
                ppvb);
          }
          else
          {
            v30 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v67->lpVtbl->SpawnInstance)(
                    v67,
                    0,
                    &v66);
            if ( v30 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1CB,
                (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
                (const char *)(unsigned int)v30,
                ppvb);
          }
          VmWbemCore::SetProperty(*((VmWbemCore **)v5 + 10), v66, v31, v57);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 19) + 8LL * j),
            L"AddressFamily",
            18);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 19) + 8LL * j),
            L"DestinationPrefix",
            8);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 19) + 8LL * j),
            L"NextHop",
            8);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 19) + 8LL * j),
            L"RouteMetric",
            18);
          VmIPv6Configuration::CopyPropertyValue(
            v5,
            v66,
            *(struct IWbemClassObject **)(*((_QWORD *)v5 + 19) + 8LL * j),
            L"TypeOfRoute",
            18);
          v33 = (_DWORD *)*((_QWORD *)v5 + 23);
          if ( *v33 > 4u )
          {
            v55[0] = pvarg.bVal;
            v59 = v57;
            v79 = (struct IWbemClassObject **)"adding gateway";
            v80 = 15;
            v77 = (Vml::VmSharableObject **)v55;
            v78 = 1;
            v75 = (VmIPv6Configuration **)&v59;
            v76 = 4;
            tlgWriteTransfer_EventWriteTransfer(v33, &word_1803435E6, 0, 0, 5, Src);
          }
          try
          {
            VmWbemCore::PutObject(*((VmWbemCore **)v5 + 10), v66, 2u, 0, ppvd);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x1F3,
              (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
              v34);
            v57 = v65;
            v19 = v63;
            j = v58;
            v5 = (VmIPv6Configuration *)v64;
          }
          VariantClear(&pvarg);
          if ( v66 )
            ((void (__fastcall *)(struct IWbemClassObject *))v66->lpVtbl->Release)(v66);
        }
        if ( v67 )
          ((void (__fastcall *)(struct IWbemClassObject *))v67->lpVtbl->Release)(v67);
        if ( v68 )
          ((void (__fastcall *)(struct IWbemClassObject *))v68->lpVtbl->Release)(v68);
      }
      v35 = (_DWORD *)*((_QWORD *)v5 + 23);
      if ( *v35 > 4u )
      {
        v62 = (VmIPv6Configuration *)*((_QWORD *)v5 + 22);
        v77 = (Vml::VmSharableObject **)"adding DNS Server addresses";
        v78 = 28;
        v75 = &v62;
        v76 = 8;
        tlgWriteTransfer_EventWriteTransfer(v35, &dword_180343634, 0, 0, 4, Src);
      }
      if ( *((_QWORD *)v5 + 22) )
      {
        Src[0] = 0;
        Src[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(Src[0]) = 0;
        Vml::FormatString(
          Src,
          (wchar_t *)L"SELECT * FROM MSFT_DNSClientServerAddress WHERE InterfaceIndex = %u AND AddressFamily = %u");
        v62 = 0;
        OneWmiInstance = VmIPv6Configuration::GetOneWmiInstance(v5, Src);
        v37 = (struct IWbemClassObject *)OneWmiInstance;
        if ( OneWmiInstance )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)OneWmiInstance + 8LL))(OneWmiInstance);
        v62 = (VmIPv6Configuration *)v37;
        v66 = 0;
        VariantInit(&pvarg);
        if ( !(unsigned int)VmWbemCore::GetNullableProperty(
                              *((VmWbemCore **)v5 + 10),
                              *((struct IWbemClassObject **)v5 + 22),
                              L"ServerAddresses",
                              (struct Vml::VmVariant *)&pvarg) )
        {
          v48 = wil::verify_hresult<long>(2147614725LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA0,
            (unsigned int)"onecore\\vm\\common\\wmimgmt\\VmWbemCore.h",
            (const char *)v48,
            ppvb);
        }
        v38 = CoCreateInstance(&CLSID_WbemContext, 0, 1u, &GUID_44aca674_e8fc_11d0_a07c_00c04fb68820, (LPVOID *)&v66);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x95F,
            (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
            (const char *)(unsigned int)v38,
            (int)ppve);
        v39 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *))v66->lpVtbl->BeginEnumeration)(
                v66,
                L"ServerAddresses",
                0,
                &pvarg);
        if ( v39 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x218,
            (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
            (const char *)(unsigned int)v39,
            (int)ppve);
        VmWbemCore::PutObject(*((VmWbemCore **)v5 + 10), v37, 1u, (struct IWbemContext *)v66, ppve);
        VariantClear(&pvarg);
        if ( v66 )
          ((void (__fastcall *)(struct IWbemClassObject *))v66->lpVtbl->Release)(v66);
        if ( v37 )
          ((void (__fastcall *)(struct IWbemClassObject *))v37->lpVtbl->Release)(v37);
        std::wstring::~wstring(Src);
      }
      v40 = (_DWORD *)*((_QWORD *)v5 + 23);
      if ( *v40 > 4u )
      {
        v62 = v5;
        v64 = "Apply succeeded";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          (_DWORD)v40,
          (unsigned int)byte_18034367B,
          v20,
          v21,
          (__int64)&v64,
          (__int64)&v62);
      }
      if ( v19 )
        Vml::VmSharableObject::DecrementUserCount(v19);
      if ( v69 )
        ((void (__fastcall *)(struct IWbemContext *))v69->lpVtbl->Release)(v69);
      if ( v70 )
        ((void (__fastcall *)(struct IWbemContext *))v70->lpVtbl->Release)(v70);
      VariantClear(&v72);
      VariantClear(&v73);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x226,
                             (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
                             v41);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18022ef7c  mov     r11, rsp
0x18022ef7f  push    rbx
0x18022ef80  push    rsi
0x18022ef81  push    rdi
0x18022ef82  push    r14
0x18022ef84  push    r15
0x18022ef86  sub     rsp, 150h
0x18022ef8d  mov     rax, cs:__security_cookie
0x18022ef94  xor     rax, rsp
0x18022ef97  mov     [rsp+178h+var_38], rax
0x18022ef9f  movzx   eax, r8w
0x18022efa3  mov     [rsp+178h+var_146], ax
0x18022efa8  mov     r14, rdx
0x18022efab  mov     rsi, rcx
0x18022efae  mov     [rsp+178h+var_118], rcx
0x18022efb3  mov     [rsp+178h+var_128], rcx
0x18022efb8  mov     [rsp+178h+var_130], ax
0x18022efbd  mov     rcx, [rcx+0B8h]
0x18022efc4  mov     eax, [rcx]
0x18022efc6  lea     rbx, [rsi+80h]
0x18022efcd  cmp     eax, 4
0x18022efd0  jbe     loc_18022F070
0x18022efd6  mov     [rsp+178h+var_100], rsi
0x18022efdb  mov     rax, [rsi+0A0h]
0x18022efe2  sub     rax, [rsi+98h]
0x18022efe9  sar     rax, 3
0x18022efed  mov     [r11-0F8h], rax
0x18022eff4  mov     rax, [rbx+8]
0x18022eff8  sub     rax, [rbx]
0x18022effb  sar     rax, 3
0x18022efff  mov     [rsp+178h+var_120], rax
0x18022f004  lea     rax, [rsp+178h+var_100]
0x18022f009  mov     [r11-48h], rax
0x18022f00d  mov     r15d, 8
0x18022f013  mov     [r11-40h], r15
0x18022f017  xor     edi, edi
0x18022f019  lea     rax, [r11-0F8h]
0x18022f020  mov     [r11-58h], rax
0x18022f024  mov     [r11-50h], r15
0x18022f028  lea     rax, [rsp+178h+var_120]
0x18022f02d  mov     [r11-68h], rax
0x18022f031  mov     [r11-60h], r15
0x18022f035  lea     rax, aApplyStarted; "Apply started"
0x18022f03c  mov     [r11-78h], rax
0x18022f040  mov     qword ptr [r11-70h], 0Eh
0x18022f048  lea     rax, [r11-98h]
0x18022f04f  mov     [rsp+178h+var_150], rax
0x18022f054  mov     dword ptr [rsp+178h+ppv], 6
0x18022f05c  xor     r9d, r9d
0x18022f05f  xor     r8d, r8d
0x18022f062  lea     rdx, byte_180343711
0x18022f069  call    _tlgWriteTransfer_EventWriteTransfer
0x18022f06e  jmp     short loc_18022F076
0x18022f070  xor     edi, edi
0x18022f072  lea     r15d, [rdi+8]
0x18022f076  mov     rax, [rbx+8]
0x18022f07a  cmp     rax, [rbx]
0x18022f07d  jnz     short loc_18022F0C5
0x18022f07f  mov     rcx, [rsi+0B8h]
0x18022f086  mov     eax, [rcx]
0x18022f088  cmp     eax, 4
0x18022f08b  jbe     short loc_18022F0BE
0x18022f08d  mov     [rsp+178h+var_118], rsi
0x18022f092  lea     rax, aApplySkipped; "Apply skipped"
0x18022f099  mov     [rsp+178h+var_100], rax
0x18022f09e  lea     rax, [rsp+178h+var_118]
0x18022f0a3  mov     [rsp+178h+var_150], rax
0x18022f0a8  lea     rax, [rsp+178h+var_100]
0x18022f0ad  mov     [rsp+178h+ppv], rax
0x18022f0b2  lea     rdx, dword_18034376C
0x18022f0b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18022f0be  xor     eax, eax
0x18022f0c0  jmp     loc_18022FBF4
0x18022f0c5  mov     rdx, r14; unsigned __int16 *
0x18022f0c8  mov     rcx, rsi; this
0x18022f0cb  call    ?GetInterfaceIndex@VmIPv6Configuration@@AEAAIPEBG@Z; VmIPv6Configuration::GetInterfaceIndex(ushort const *)
0x18022f0d0  mov     ebx, eax
0x18022f0d2  mov     [rsp+178h+var_144], eax
0x18022f0d6  mov     word ptr [rsp+178h+var_B0], r15w
0x18022f0df  lea     rcx, aActivestore; "ActiveStore"
0x18022f0e6  call    cs:__imp_SysAllocString
0x18022f0ec  mov     qword ptr [rsp+178h+var_B0+8], rax
0x18022f0f4  test    rax, rax
0x18022f0f7  jz      loc_18022FC13
0x18022f0fd  mov     word ptr [rsp+178h+var_C8], r15w
0x18022f106  lea     rcx, aPersistentstor; "PersistentStore"
0x18022f10d  call    cs:__imp_SysAllocString
0x18022f113  mov     qword ptr [rsp+178h+var_C8+8], rax
0x18022f11b  test    rax, rax
0x18022f11e  jz      loc_18022FC3A
0x18022f124  mov     [rsp+178h+var_E8], rdi
0x18022f12c  lea     rax, [rsp+178h+var_E8]
0x18022f134  mov     [rsp+178h+ppv], rax; int
0x18022f139  lea     r9, _GUID_44aca674_e8fc_11d0_a07c_00c04fb68820; riid
0x18022f140  xor     edx, edx; pUnkOuter
0x18022f142  lea     r8d, [rdx+1]; dwClsContext
0x18022f146  lea     rcx, CLSID_WbemContext; rclsid
0x18022f14d  call    cs:__imp_CoCreateInstance
0x18022f153  mov     rcx, [rsp+178h]; this
0x18022f15b  test    eax, eax
0x18022f15d  js      loc_18022FC61
0x18022f163  mov     rcx, [rsp+178h+var_E8]
0x18022f16b  mov     rax, [rcx]
0x18022f16e  lea     r9, [rsp+178h+var_B0]
0x18022f176  xor     r8d, r8d
0x18022f179  lea     rdx, aPolicystore; "PolicyStore"
0x18022f180  mov     rax, [rax+40h]
0x18022f184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f189  mov     rcx, [rsp+178h]; this
0x18022f191  test    eax, eax
0x18022f193  js      loc_18022FC75
0x18022f199  mov     [rsp+178h+var_F0], rdi
0x18022f1a1  lea     rax, [rsp+178h+var_F0]
0x18022f1a9  mov     [rsp+178h+ppv], rax; int
0x18022f1ae  lea     r9, _GUID_44aca674_e8fc_11d0_a07c_00c04fb68820; riid
0x18022f1b5  xor     edx, edx; pUnkOuter
0x18022f1b7  lea     r8d, [rdx+1]; dwClsContext
0x18022f1bb  lea     rcx, CLSID_WbemContext; rclsid
0x18022f1c2  call    cs:__imp_CoCreateInstance
0x18022f1c8  mov     rcx, [rsp+178h]; this
0x18022f1d0  test    eax, eax
0x18022f1d2  js      loc_18022FC8A
0x18022f1d8  mov     rcx, [rsp+178h+var_F0]
0x18022f1e0  mov     rax, [rcx]
0x18022f1e3  lea     r9, [rsp+178h+var_C8]
0x18022f1eb  xor     r8d, r8d
0x18022f1ee  lea     rdx, aPolicystore; "PolicyStore"
0x18022f1f5  mov     rax, [rax+40h]
0x18022f1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f1fe  mov     rcx, [rsp+178h]; this
0x18022f206  test    eax, eax
0x18022f208  js      loc_18022FC9E
0x18022f20e  mov     [rsp+178h+var_120], rdi
0x18022f213  lea     r9, [rsp+178h+var_120]; struct VmIPv6Configuration **
0x18022f218  mov     r8, [rsi+0B8h]; struct _tlgProvider_t *
0x18022f21f  movzx   edx, [rsp+178h+var_146]; unsigned __int16
0x18022f224  mov     rcx, r14; unsigned __int16 *
0x18022f227  call    ?GetInstance@VmIPv6Configuration@@SAJPEBGGPEBU_tlgProvider_t@@PEAPEAV1@@Z; VmIPv6Configuration::GetInstance(ushort const *,ushort,_tlgProvider_t const *,VmIPv6Configuration * *)
0x18022f22c  mov     rcx, [rsp+178h]; this
0x18022f234  test    eax, eax
0x18022f236  js      loc_18022FCB3
0x18022f23c  mov     [rsp+178h+var_110], ebx
0x18022f240  mov     rcx, [rsi+0B8h]
0x18022f247  mov     eax, [rcx]
0x18022f249  cmp     eax, 4
0x18022f24c  jbe     short loc_18022F270
0x18022f24e  lea     rax, aClearingTarget; "clearing target"
0x18022f255  mov     [rsp+178h+var_100], rax
0x18022f25a  lea     rax, [rsp+178h+var_100]
0x18022f25f  mov     [rsp+178h+ppv], rax; int
0x18022f264  lea     rdx, byte_1803437A5
0x18022f26b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18022f270  mov     rbx, [rsp+178h+var_120]
0x18022f275  mov     rcx, rbx; this
0x18022f278  call    ?Clear@VmIPv6Configuration@@AEAAXXZ; VmIPv6Configuration::Clear(void)
0x18022f27d  mov     rax, [rsi+88h]
0x18022f284  sub     rax, [rsi+80h]
0x18022f28b  sar     rax, 3
0x18022f28f  test    rax, rax
0x18022f292  jz      loc_18022F621
0x18022f298  mov     [rsp+178h+var_100], rdi
0x18022f29d  mov     [rsp+178h+var_F8], rdi
0x18022f2a5  mov     r9, [rsp+178h+var_E8]; struct IWbemContext *
0x18022f2ad  lea     r8, [rsp+178h+var_100]; struct IWbemClassObject **
0x18022f2b2  lea     rdx, aRootStandardci_1; "\\\\.\\root\\standardcimv2:MSFT_NetIPAd"...
0x18022f2b9  mov     rcx, [rsi+50h]; this
0x18022f2bd  call    ?GetWbemObject@VmWbemCore@@QEBAXPEBGPEAPEAUIWbemClassObject@@PEAUIWbemContext@@@Z; VmWbemCore::GetWbemObject(ushort const *,IWbemClassObject * *,IWbemContext *)
0x18022f2c2  mov     r9, [rsp+178h+var_F0]; struct IWbemContext *
0x18022f2ca  lea     r8, [rsp+178h+var_F8]; struct IWbemClassObject **
0x18022f2d2  lea     rdx, aRootStandardci_1; "\\\\.\\root\\standardcimv2:MSFT_NetIPAd"...
0x18022f2d9  mov     rcx, [rsi+50h]; this
0x18022f2dd  call    ?GetWbemObject@VmWbemCore@@QEBAXPEBGPEAPEAUIWbemClassObject@@PEAUIWbemContext@@@Z; VmWbemCore::GetWbemObject(ushort const *,IWbemClassObject * *,IWbemContext *)
0x18022f2e2  mov     r15d, edi
0x18022f2e5  mov     [rsp+178h+var_140], r15d
0x18022f2ea  mov     r14d, r15d
0x18022f2ed  mov     rax, [rsi+88h]
0x18022f2f4  sub     rax, [rsi+80h]
0x18022f2fb  sar     rax, 3
0x18022f2ff  cmp     r14, rax
0x18022f302  jnb     loc_18022F5F1
0x18022f308  mov     [rsp+178h+var_108], rdi
0x18022f30d  lea     rcx, [rsp+178h+pvarg]; pvarg
0x18022f315  call    cs:__imp_VariantInit
0x18022f31b  nop
0x18022f31c  mov     rdx, [rsi+80h]
0x18022f323  lea     r9, [rsp+178h+pvarg]; struct Vml::VmVariant *
0x18022f32b  lea     r8, aStore; "Store"
0x18022f332  mov     rdx, [rdx+r14*8]; struct IWbemClassObject *
0x18022f336  mov     rcx, [rsi+50h]; this
0x18022f33a  call    ?GetNullableProperty@VmWbemCore@@QEAAHPEAUIWbemClassObject@@PEBGAEAVVmVariant@Vml@@@Z; VmWbemCore::GetNullableProperty(IWbemClassObject *,ushort const *,Vml::VmVariant &)
0x18022f33f  test    eax, eax
0x18022f341  jz      loc_18022FCC8
0x18022f347  cmp     byte ptr [rsp+178h+pvarg+8], dil
0x18022f34f  jnz     short loc_18022F37E
0x18022f351  mov     rcx, [rsp+178h+var_F8]
0x18022f359  mov     rax, [rcx]
0x18022f35c  lea     r8, [rsp+178h+var_108]
0x18022f361  xor     edx, edx
0x18022f363  mov     rax, [rax+78h]
0x18022f367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f36c  mov     rcx, [rsp+178h]; this
0x18022f374  test    eax, eax
0x18022f376  js      loc_18022FCEE
0x18022f37c  jmp     short loc_18022F3B4
0x18022f37e  cmp     byte ptr [rsp+178h+pvarg+8], 1
0x18022f386  jnz     loc_18022FD16
0x18022f38c  mov     rcx, [rsp+178h+var_100]
0x18022f391  mov     rax, [rcx]
0x18022f394  lea     r8, [rsp+178h+var_108]
0x18022f399  xor     edx, edx
0x18022f39b  mov     rax, [rax+78h]
0x18022f39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f3a4  mov     rcx, [rsp+178h]; this
0x18022f3ac  test    eax, eax
0x18022f3ae  js      loc_18022FD02
0x18022f3b4  mov     r9d, [rsp+178h+var_144]; unsigned int
0x18022f3b9  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
0x18022f3be  mov     rcx, [rsi+50h]; this
0x18022f3c2  call    ?SetProperty@VmWbemCore@@QEAAXPEAUIWbemClassObject@@PEBGI@Z; VmWbemCore::SetProperty(IWbemClassObject *,ushort const *,uint)
0x18022f3c7  mov     r8, [rsi+80h]
0x18022f3ce  mov     dword ptr [rsp+178h+ppv], 12h; int
0x18022f3d6  lea     r9, aAddressfamily; "AddressFamily"
0x18022f3dd  mov     r8, [r8+r14*8]; struct IWbemClassObject *
0x18022f3e1  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
0x18022f3e6  mov     rcx, rsi; this
0x18022f3e9  call    ?CopyPropertyValue@VmIPv6Configuration@@AEAAXPEAUIWbemClassObject@@0PEBGJ@Z; VmIPv6Configuration::CopyPropertyValue(IWbemClassObject *,IWbemClassObject *,ushort const *,long)
0x18022f3ee  mov     r8, [rsi+80h]
0x18022f3f5  mov     dword ptr [rsp+178h+ppv], 12h; int
0x18022f3fd  lea     r9, aPrefixorigin; "PrefixOrigin"
0x18022f404  mov     r8, [r8+r14*8]; struct IWbemClassObject *
0x18022f408  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
0x18022f40d  mov     rcx, rsi; this
0x18022f410  call    ?CopyPropertyValue@VmIPv6Configuration@@AEAAXPEAUIWbemClassObject@@0PEBGJ@Z; VmIPv6Configuration::CopyPropertyValue(IWbemClassObject *,IWbemClassObject *,ushort const *,long)
0x18022f415  mov     r8, [rsi+80h]
0x18022f41c  mov     dword ptr [rsp+178h+ppv], 12h; int
0x18022f424  lea     r9, aSuffixorigin; "SuffixOrigin"
0x18022f42b  mov     r8, [r8+r14*8]; struct IWbemClassObject *
0x18022f42f  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
0x18022f434  mov     rcx, rsi; this
0x18022f437  call    ?CopyPropertyValue@VmIPv6Configuration@@AEAAXPEAUIWbemClassObject@@0PEBGJ@Z; VmIPv6Configuration::CopyPropertyValue(IWbemClassObject *,IWbemClassObject *,ushort const *,long)
0x18022f43c  mov     rcx, [rsi+0B8h]
0x18022f443  mov     eax, [rcx]
0x18022f445  cmp     eax, 4
0x18022f448  jbe     loc_18022F4F8
0x18022f44e  movzx   eax, [rsp+178h+var_146]
0x18022f453  mov     [rsp+178h+var_138], ax
0x18022f458  mov     eax, [rsp+178h+var_144]
0x18022f45c  mov     [rsp+178h+var_13C], eax
0x18022f460  mov     al, byte ptr [rsp+178h+pvarg+8]
0x18022f467  mov     [rsp+178h+var_148], al
0x18022f46b  lea     rax, aAddingIp; "adding IP"
0x18022f472  mov     [rsp+178h+var_48], rax
0x18022f47a  mov     [rsp+178h+var_40], 0Ah
0x18022f486  lea     rax, [rsp+178h+var_138]
0x18022f48b  mov     [rsp+178h+var_58], rax
0x18022f493  mov     [rsp+178h+var_50], 2
0x18022f49f  lea     rax, [rsp+178h+var_13C]
0x18022f4a4  mov     [rsp+178h+var_68], rax
0x18022f4ac  mov     [rsp+178h+var_60], 4
0x18022f4b8  lea     rax, [rsp+178h+var_148]
0x18022f4bd  mov     [rsp+178h+var_78], rax
0x18022f4c5  mov     [rsp+178h+var_70], 1
0x18022f4d1  lea     rax, [rsp+178h+Src]
0x18022f4d9  mov     [rsp+178h+var_150], rax
0x18022f4de  mov     dword ptr [rsp+178h+ppv], 6
0x18022f4e6  xor     r9d, r9d
0x18022f4e9  xor     r8d, r8d
0x18022f4ec  lea     rdx, dword_1803436B4
0x18022f4f3  call    _tlgWriteTransfer_EventWriteTransfer
0x18022f4f8  mov     rax, [rsp+178h+var_128]
0x18022f4fd  mov     rax, [rax+80h]
0x18022f504  mov     r8, [rax+r14*8]; struct IWbemClassObject *
0x18022f508  mov     dword ptr [rsp+178h+ppv], 8; int
0x18022f510  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
0x18022f515  mov     rcx, rsi; this
0x18022f518  cmp     [rsp+178h+var_146], 17h
0x18022f51e  jnz     short loc_18022F52E
0x18022f520  lea     r9, aIpv6address; "IPv6Address"
0x18022f527  call    ?CopyPropertyValue@VmIPv6Configuration@@AEAAXPEAUIWbemClassObject@@0PEBGJ@Z; VmIPv6Configuration::CopyPropertyValue(IWbemClassObject *,IWbemClassObject *,ushort const *,long)
0x18022f52c  jmp     short loc_18022F53A
0x18022f52e  lea     r9, aIpv4address; "IPv4Address"
0x18022f535  call    ?CopyPropertyValue@VmIPv6Configuration@@AEAAXPEAUIWbemClassObject@@0PEBGJ@Z; VmIPv6Configuration::CopyPropertyValue(IWbemClassObject *,IWbemClassObject *,ushort const *,long)
0x18022f53a  mov     r8, [rsi+80h]
0x18022f541  mov     dword ptr [rsp+178h+ppv], 11h; int
0x18022f549  lea     r9, aPrefixlength; "PrefixLength"
0x18022f550  mov     r8, [r8+r14*8]; struct IWbemClassObject *
0x18022f554  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
0x18022f559  mov     rcx, rsi; this
0x18022f55c  call    ?CopyPropertyValue@VmIPv6Configuration@@AEAAXPEAUIWbemClassObject@@0PEBGJ@Z; VmIPv6Configuration::CopyPropertyValue(IWbemClassObject *,IWbemClassObject *,ushort const *,long)
0x18022f561  mov     r8, [rsi+80h]
0x18022f568  mov     dword ptr [rsp+178h+ppv], 11h; unsigned __int16 **
0x18022f570  lea     r9, aType; "Type"
0x18022f577  mov     r8, [r8+r14*8]; struct IWbemClassObject *
0x18022f57b  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
0x18022f580  mov     rcx, rsi; this
0x18022f583  call    ?CopyPropertyValue@VmIPv6Configuration@@AEAAXPEAUIWbemClassObject@@0PEBGJ@Z; VmIPv6Configuration::CopyPropertyValue(IWbemClassObject *,IWbemClassObject *,ushort const *,long)
0x18022f588  nop
0x18022f589  xor     r9d, r9d; struct IWbemContext *
0x18022f58c  lea     r8d, [r9+2]; unsigned int
0x18022f590  mov     rdx, [rsp+178h+var_108]; struct IWbemClassObject *
  ... truncated ...
```
