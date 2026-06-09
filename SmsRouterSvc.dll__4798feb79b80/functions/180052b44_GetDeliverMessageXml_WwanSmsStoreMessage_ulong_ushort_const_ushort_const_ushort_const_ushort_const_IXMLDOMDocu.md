# GetDeliverMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)

- ea: `0x180052b44`
- end: `0x180053b9e`
- name: `?GetDeliverMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z`
- size: `4186`
- prototype: `int(struct WwanSmsStoreMessage *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d1d8`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000cfe8`
- `0x18000d388`
- `0x18000e05c`
- `0x18000e534`
- `0x18000e7ac`
- `0x180013d40`
- `0x180014d48`
- `0x1800288f4`
- `0x180028bc0`
- `0x18002ac18`
- `0x18002cafc`
- `0x18002f864`
- `0x18003246c`
- `0x180051420`
- `0x180051628`
- `0x180051980`
- `0x180052b44`
- `0x180053c98`
- `0x1800578c4`
- `0x180057ec0`
- `0x180058070`
- `0x180058af8`
- `0x180058e50`
- `0x1800595c4`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180053168`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18005329c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800535cb`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180053168`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18005329c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800535cb`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180052dc2`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180053a84`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180053af0`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180053b38`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180052dc2`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180053a84`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180053af0`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180053b38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052ede`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052ede`
- `wsplib!DecodeWspHeaders` at `0x1800533ec`
- `wsplib!DecodeWspHeaders` at `0x1800533ec`
- `wsplib!FreeWspHeaders` at `0x180053474`
- `wsplib!FreeWspHeaders` at `0x180053474`

## string_xrefs

- `0x1800532cd`: `TeleserviceId`
- `0x180053199`: `ProtocolId`
- `0x180052eab`: `GetDeliverMessageXml`
- `0x180052f1a`: `GetDeliverMessageXml`
- `0x180053ad6`: `GetDeliverMessageXml`
- `0x180052e9f`: `Deliver message decoded with portnumber=%d now generating xml for the message.`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall GetDeliverMessageXml(
        struct WwanSmsStoreMessage *a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct IXMLDOMDocument **a7)
{
  DWORD v10; // r13d
  int v11; // r8d
  char v12; // r14
  HRESULT Instance; // edi
  unsigned int v14; // r15d
  __int64 v15; // rdx
  char v16; // al
  int appended; // eax
  int v18; // r8d
  struct IXMLDOMNode *v19; // rdi
  int v20; // ebx
  struct IXMLDOMNode *v21; // rbx
  int Base64String; // esi
  SYSTEMTIME *v23; // r8
  DWORD v24; // r15d
  SYSTEMTIME *p_SystemTime; // r8
  const unsigned __int16 *v26; // r8
  DWORD v27; // r14d
  SYSTEMTIME *v28; // r8
  SYSTEMTIME *v29; // r8
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // r8
  const unsigned __int16 *v33; // r8
  SYSTEMTIME *v34; // r8
  SYSTEMTIME *v35; // r8
  _BYTE v37[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD SmsDataEncodingType; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbBinary[2]; // [rsp+68h] [rbp-98h] BYREF
  struct IXMLDOMNode *ppv; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *Src; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  BYTE *pbBinary[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h]
  struct IXMLDOMNode *v45; // [rsp+A0h] [rbp-60h] BYREF
  struct IXMLDOMNode *v46; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v47; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v48; // [rsp+B8h] [rbp-48h]
  struct IXMLDOMDocument **v49; // [rsp+C0h] [rbp-40h]
  _BYTE v50[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v51[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v52[128]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v53[104]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v54[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v55[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v56[128]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v57[104]; // [rsp+268h] [rbp+168h] BYREF
  SYSTEMTIME SystemTime; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v59; // [rsp+2E0h] [rbp+1E0h]
  unsigned __int16 *v60[2]; // [rsp+2F0h] [rbp+1F0h] BYREF
  __m128i si128; // [rsp+300h] [rbp+200h]
  unsigned __int16 *v62[2]; // [rsp+310h] [rbp+210h] BYREF
  __int64 v63; // [rsp+320h] [rbp+220h]
  unsigned __int64 v64; // [rsp+328h] [rbp+228h]
  unsigned __int16 *v65[2]; // [rsp+330h] [rbp+230h] BYREF
  __m128i v66; // [rsp+340h] [rbp+240h]
  struct _SYSTEMTIME lpSystemTime; // [rsp+350h] [rbp+250h] BYREF
  char *v68[4]; // [rsp+360h] [rbp+260h] BYREF

  v47 = a3;
  LODWORD(ppv) = a2;
  *(_QWORD *)&SystemTime.wYear = a5;
  v48 = a6;
  v49 = a7;
  v10 = 0;
  SmsDataEncodingType = 0;
  *(_OWORD *)v60 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v60[0]) = 0;
  *(_OWORD *)v65 = 0;
  v66 = si128;
  LOWORD(v65[0]) = 0;
  *(_OWORD *)v62 = 0;
  v63 = 0;
  v64 = 7;
  LOWORD(v62[0]) = 0;
  *(_OWORD *)pbBinary = 0;
  v44 = 0;
  LODWORD(Src) = 0;
  cbBinary[1] = 0;
  LODWORD(v42) = 0;
  cbBinary[0] = 1;
  lpSystemTime = 0;
  v37[0] = 1;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v50);
  v46 = 0;
  v45 = 0;
  if ( !a2 || !a1 )
  {
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v53);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v53);
    std::vector<unsigned char>::~vector<unsigned char>((char **)pbBinary);
    std::wstring::~wstring((char **)v62);
    std::wstring::~wstring((char **)v65);
    std::wstring::~wstring((char **)v60);
    return 2147942487LL;
  }
  v12 = *((_BYTE *)a1 + 4);
  if ( !v12 )
  {
    Instance = CSmsEncodingHelper::DecodeMessageGsm(
                 (char *)a1 + 5,
                 *(unsigned int *)a1,
                 a4,
                 v65,
                 &Src,
                 &SmsDataEncodingType,
                 cbBinary,
                 &lpSystemTime,
                 v37);
LABEL_7:
    v10 = SmsDataEncodingType;
    SmsDataEncodingType = cbBinary[0];
    goto LABEL_10;
  }
  if ( v12 == 1 )
  {
    Instance = CSmsEncodingHelper::DecodeMessageCdma(
                 (int)a1 + 5,
                 *(_DWORD *)a1,
                 v11,
                 (int)v65,
                 (__int64)&v42,
                 (__int64)&SmsDataEncodingType,
                 (__int64)cbBinary,
                 &lpSystemTime,
                 (__int64)v37,
                 (__int64)v62,
                 (__int64)&cbBinary[1]);
    cbBinary[1] = v42;
    goto LABEL_7;
  }
  if ( v12 != 2 )
  {
    Instance = -2147467263;
    goto LABEL_209;
  }
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v54);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, (char *)a1 + 13);
  std::basic_stringbuf<unsigned short>::str(v56, v68);
  std::wstring::operator=(v65, v68);
  std::wstring::~wstring(v68);
  cbBinary[1] = 4098;
  Instance = CSmsEncodingHelper::DecodeCdmaTextTimeStamp((char *)a1 + 63, &lpSystemTime);
  SmsDataEncodingType = GetSmsDataEncodingType(*(unsigned int *)((char *)a1 + 85));
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v57);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v57);
LABEL_10:
  if ( Instance < 0 )
  {
LABEL_209:
    LogSmsRouterError("GetDeliverMessageXml", 0x21Fu, Instance, "Failed to decode the metadata of the pdu.");
    goto LABEL_210;
  }
  v14 = 0;
  if ( !(_DWORD)ppv )
  {
LABEL_20:
    LogSmsRouterInfo(
      "GetDeliverMessageXml",
      0x249u,
      "Deliver message decoded with portnumber=%d now generating xml for the message.",
      v10);
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_DOMDocument60,
                 0,
                 0x17u,
                 &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
    {
      if ( ppv )
        ((void (__fastcall *)(struct IXMLDOMNode *))ppv->lpVtbl->Release)(ppv);
      goto LABEL_210;
    }
    v19 = ppv;
    v46 = ppv;
    v20 = Windows::Sms::Common::CSmsUtil::AddElement(ppv, L"Message", 0, &v45);
    if ( v20 < 0 )
    {
      if ( v45 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v45->lpVtbl->Release)(v45);
      if ( v19 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
      Instance = v20;
      goto LABEL_210;
    }
    v21 = v45;
    Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v45, L"SmsDeviceId", v47, 0);
    if ( Base64String < 0 )
    {
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      if ( v19 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
      goto LABEL_204;
    }
    Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"SimIccId", v48, 0);
    if ( Base64String < 0 )
    {
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      if ( v19 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
      goto LABEL_204;
    }
    Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"Imsi", a4, 0);
    if ( Base64String < 0 )
    {
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      if ( v19 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
      goto LABEL_204;
    }
    if ( *(_QWORD *)&SystemTime.wYear )
    {
      Base64String = Windows::Sms::Common::CSmsUtil::AddElement(
                       v21,
                       L"Receiver",
                       *(const unsigned __int16 **)&SystemTime.wYear,
                       0);
      if ( Base64String < 0 )
      {
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
        if ( v19 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
        goto LABEL_204;
      }
    }
    if ( v12 )
    {
      if ( (unsigned __int8)(v12 - 1) <= 1u )
      {
        Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"CellularClass", L"Cdma", 0);
        if ( Base64String < 0 )
        {
          if ( v21 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          if ( v19 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
          goto LABEL_204;
        }
        SystemTime = 0;
        v59 = 0;
        std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
          v50,
          &SystemTime);
        std::wstring::~wstring((char **)&SystemTime);
        v24 = cbBinary[1];
        std::basic_ostream<unsigned short>::operator<<(v51, cbBinary[1]);
        std::basic_stringbuf<unsigned short>::str(v52, &SystemTime);
        p_SystemTime = &SystemTime;
        if ( *((_QWORD *)&v59 + 1) > 7u )
          p_SystemTime = *(SYSTEMTIME **)&SystemTime.wYear;
        Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"TeleserviceId", &p_SystemTime->wYear, 0);
        std::wstring::~wstring((char **)&SystemTime);
        if ( Base64String < 0 )
        {
          if ( v21 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          if ( v19 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
          goto LABEL_204;
        }
        if ( v63 )
        {
          v26 = (const unsigned __int16 *)v62;
          if ( v64 > 7 )
            v26 = v62[0];
          Windows::Sms::Common::CSmsUtil::AddElement(v21, L"CallbackNumber", v26, 0);
        }
LABEL_92:
        if ( v10 == 2948 )
        {
          v27 = SmsDataEncodingType;
          if ( SmsDataEncodingType == 3 )
          {
            ppv = 0;
            cbBinary[0] = 0;
            Src = 0;
            Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"MessageType", L"Wap", 0);
            if ( Base64String < 0 )
            {
              if ( v21 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
              if ( v19 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
              goto LABEL_204;
            }
            if ( (int)DecodeWspHeaders(
                        pbBinary[0],
                        LODWORD(pbBinary[1]) - LODWORD(pbBinary[0]),
                        (unsigned __int8 **)&ppv,
                        cbBinary,
                        &Src) >= 0 )
            {
              Base64String = AddWapContent(v21, (BYTE *)ppv, cbBinary[0], Src);
              FreeWspHeaders((unsigned __int8 *)ppv, Src);
              if ( Base64String < 0 )
              {
                if ( v21 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                if ( v19 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                goto LABEL_204;
              }
            }
            else
            {
              ppv = 0;
              cbBinary[0] = 0;
              Src = 0;
              Base64String = AddWapContent(v21, pbBinary[0], LODWORD(pbBinary[1]) - LODWORD(pbBinary[0]), 0);
              if ( Base64String < 0 )
              {
                if ( v21 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                if ( v19 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                goto LABEL_204;
              }
            }
LABEL_159:
            v31 = (const unsigned __int16 *)v65;
            if ( v66.m128i_i64[1] > 7uLL )
              v31 = v65[0];
            Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"Sender", v31, 0);
            if ( Base64String < 0 )
            {
              if ( v21 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
              if ( v19 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
              goto LABEL_204;
            }
            if ( v37[0] )
            {
              switch ( v37[0] )
              {
                case 1:
                  v33 = L"1";
                  break;
                case 2:
                  v33 = L"2";
                  break;
                case 3:
                  v33 = L"3";
                  break;
                default:
LABEL_189:
                  SystemTime = lpSystemTime;
                  GetTimeString(&SystemTime);
                  std::basic_stringbuf<unsigned short>::str(v52, &SystemTime);
                  v34 = &SystemTime;
                  if ( *((_QWORD *)&v59 + 1) > 7u )
                    v34 = *(SYSTEMTIME **)&SystemTime.wYear;
                  Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"ReceiveTime", &v34->wYear, 0);
                  std::wstring::~wstring((char **)&SystemTime);
                  if ( Base64String >= 0 )
                  {
                    SystemTime = 0;
                    v59 = 0;
                    std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
                    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                      v50,
                      &SystemTime);
                    std::wstring::~wstring((char **)&SystemTime);
                    GetEncodingString(v27, v50);
                    std::basic_stringbuf<unsigned short>::str(v52, &SystemTime);
                    v35 = &SystemTime;
                    if ( *((_QWORD *)&v59 + 1) > 7u )
                      v35 = *(SYSTEMTIME **)&SystemTime.wYear;
                    Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"Encoding", &v35->wYear, 0);
                    std::wstring::~wstring((char **)&SystemTime);
                    if ( Base64String >= 0 )
                    {
                      *v49 = (struct IXMLDOMDocument *)v19;
                      v46 = 0;
                      if ( v21 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v53);
                      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v53);
                      std::vector<unsigned char>::~vector<unsigned char>((char **)pbBinary);
                      std::wstring::~wstring((char **)v62);
                      std::wstring::~wstring((char **)v65);
                      std::wstring::~wstring((char **)v60);
                      return (unsigned int)Base64String;
                    }
                    if ( v21 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                    if ( v19 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                  }
                  else
                  {
                    if ( v21 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                    if ( v19 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                  }
LABEL_204:
                  Instance = Base64String;
                  goto LABEL_210;
              }
            }
            else
            {
              v33 = L"0";
            }
            Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"MessageClass", v33, 0);
            if ( Base64String < 0 )
            {
              if ( v21 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
              if ( v19 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
              goto LABEL_204;
            }
            goto LABEL_189;
          }
        }
        else
        {
          if ( !v10 && ((unsigned __int8)(v12 - 1) > 1u || ((v24 - 4097) & 0xFFFFFFFA) == 0 && v24 != 4102) )
          {
            Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"MessageType", L"Text", 0);
            if ( Base64String < 0 )
            {
              if ( v21 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
              if ( v19 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
              goto LABEL_204;
            }
            v27 = SmsDataEncodingType;
LABEL_139:
            if ( v27 == 3 )
            {
              SystemTime = 0;
              v59 = 0;
              std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
              std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                v50,
                &SystemTime);
              std::wstring::~wstring((char **)&SystemTime);
              if ( pbBinary[1] != pbBinary[0] )
              {
                Base64String = GetBase64String(pbBinary[0], LODWORD(pbBinary[1]) - LODWORD(pbBinary[0]));
                if ( Base64String < 0 )
                {
                  if ( v21 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                  if ( v19 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                  goto LABEL_204;
                }
              }
              std::basic_stringbuf<unsigned short>::str(v52, &SystemTime);
              v29 = &SystemTime;
              if ( *((_QWORD *)&v59 + 1) > 7u )
                v29 = *(SYSTEMTIME **)&SystemTime.wYear;
              Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"Data", &v29->wYear, 0);
              std::wstring::~wstring((char **)&SystemTime);
              if ( Base64String < 0 )
              {
                if ( v21 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                if ( v19 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                goto LABEL_204;
              }
              v30 = (const unsigned __int16 *)v60;
              if ( si128.m128i_i64[1] > 7uLL )
                v30 = v60[0];
              if ( (int)Windows::Sms::Common::CSmsUtil::AddElement(v21, L"Text", v30, 0) < 0 )
                Windows::Sms::Common::CSmsUtil::DeleteElement(v21, L"Text");
            }
            else
            {
              v32 = (const unsigned __int16 *)v60;
              if ( si128.m128i_i64[1] > 7uLL )
                v32 = v60[0];
              Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"Text", v32, 0);
              if ( Base64String < 0 )
              {
                if ( v21 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                if ( v19 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                goto LABEL_204;
              }
            }
            goto LABEL_159;
          }
          v27 = SmsDataEncodingType;
        }
        Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"MessageType", L"Application", 0);
        if ( Base64String < 0 )
        {
          if ( v21 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          if ( v19 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
          goto LABEL_204;
        }
        SystemTime = 0;
        v59 = 0;
        std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
          v50,
          &SystemTime);
        std::wstring::~wstring((char **)&SystemTime);
        std::basic_ostream<unsigned short>::operator<<(v51, v10);
        std::basic_stringbuf<unsigned short>::str(v52, &SystemTime);
        v28 = &SystemTime;
        if ( *((_QWORD *)&v59 + 1) > 7u )
          v28 = *(SYSTEMTIME **)&SystemTime.wYear;
        Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"Port", &v28->wYear, 0);
        std::wstring::~wstring((char **)&SystemTime);
        if ( Base64String < 0 )
        {
          if ( v21 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          if ( v19 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
          goto LABEL_204;
        }
        goto LABEL_139;
      }
    }
    else
    {
      Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"CellularClass", L"Gsm", 0);
      if ( Base64String < 0 )
      {
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
        if ( v19 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
        goto LABEL_204;
      }
      SystemTime = 0;
      v59 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
        v50,
        &SystemTime);
      std::wstring::~wstring((char **)&SystemTime);
      std::basic_ostream<unsigned short>::operator<<(v51, (unsigned int)Src);
      std::basic_stringbuf<unsigned short>::str(v52, &SystemTime);
      v23 = &SystemTime;
      if ( *((_QWORD *)&v59 + 1) > 7u )
        v23 = *(SYSTEMTIME **)&SystemTime.wYear;
      Base64String = Windows::Sms::Common::CSmsUtil::AddElement(v21, L"ProtocolId", &v23->wYear, 0);
      std::wstring::~wstring((char **)&SystemTime);
      if ( Base64String < 0 )
      {
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
        if ( v19 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
        goto LABEL_204;
      }
    }
    v24 = cbBinary[1];
    goto LABEL_92;
  }
  while ( 1 )
  {
    v15 = 520LL * v14;
    v16 = *((_BYTE *)a1 + v15 + 4);
    if ( !v16 )
    {
      appended = CSmsEncodingHelper::AppendMessageContentsGsm(
                   (char *)a1 + v15 + 5,
                   *(unsigned int *)((char *)a1 + v15),
                   a4,
                   v60,
                   pbBinary);
      goto LABEL_18;
    }
    if ( v16 == 1 )
    {
      appended = CSmsEncodingHelper::AppendMessageContentsCdma(
                   (int)v15 + (int)a1 + 5,
                   *(_DWORD *)((char *)a1 + v15),
                   (_DWORD)a4,
                   (unsigned int)v60,
                   (__int64)pbBinary);
      goto LABEL_18;
    }
    if ( v16 != 2 )
      break;
    GetSmsDataEncodingType(*(unsigned int *)((char *)a1 + 85));
    appended = CSmsEncodingHelper::AppendMessageContentsCdmaText((LPCCH)a1 + 96, v18, a4, 0, v60, (__int64)pbBinary);
LABEL_18:
    Instance = appended;
    if ( appended < 0 )
      goto LABEL_25;
    if ( ++v14 >= (unsigned int)ppv )
      goto LABEL_20;
  }
  Instance = -2147467263;
LABEL_25:
  LogSmsRouterError("GetDeliverMessageXml", 0x244u, Instance, "Failed to decode the text data of the pdu.");
LABEL_210:
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v53);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v53);
  std::vector<unsigned char>::~vector<unsigned char>((char **)pbBinary);
  std::wstring::~wstring((char **)v62);
  std::wstring::~wstring((char **)v65);
  std::wstring::~wstring((char **)v60);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180052b44  mov     [rsp-8+arg_8], rbx
0x180052b49  push    rbp
0x180052b4a  push    rsi
0x180052b4b  push    rdi
0x180052b4c  push    r12
0x180052b4e  push    r13
0x180052b50  push    r14
0x180052b52  push    r15
0x180052b54  lea     rbp, [rsp-290h]
0x180052b5c  sub     rsp, 390h
0x180052b63  mov     rax, cs:__security_cookie
0x180052b6a  xor     rax, rsp
0x180052b6d  mov     [rbp+2C0h+var_40], rax
0x180052b74  mov     r12, r9
0x180052b77  mov     [rbp+2C0h+var_310], r8
0x180052b7b  mov     edi, edx
0x180052b7d  mov     dword ptr [rsp+3C0h+var_350], edx
0x180052b81  mov     rsi, rcx
0x180052b84  mov     rax, [rbp+2C0h+arg_20]
0x180052b8b  mov     qword ptr [rbp+2C0h+SystemTime.wYear], rax
0x180052b92  mov     rax, [rbp+2C0h+arg_28]
0x180052b99  mov     [rbp+2C0h+var_308], rax
0x180052b9d  mov     rax, [rbp+2C0h+arg_30]
0x180052ba4  mov     [rbp+2C0h+var_300], rax
0x180052ba8  xor     r14d, r14d
0x180052bab  mov     r13d, r14d
0x180052bae  mov     dword ptr [rsp+3C0h+var_360+4], r14d
0x180052bb3  xorps   xmm0, xmm0
0x180052bb6  movups  xmmword ptr [rbp+2C0h+var_D0], xmm0
0x180052bbd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180052bc5  movdqu  [rbp+2C0h+var_C0], xmm1
0x180052bcd  mov     word ptr [rbp+2C0h+var_D0], r14w
0x180052bd5  movups  xmmword ptr [rbp+2C0h+var_90], xmm0
0x180052bdc  movdqu  [rbp+2C0h+var_80], xmm1
0x180052be4  mov     word ptr [rbp+2C0h+var_90], r14w
0x180052bec  movups  xmmword ptr [rbp+2C0h+var_B0], xmm0
0x180052bf3  mov     [rbp+2C0h+var_A0], r14
0x180052bfa  mov     [rbp+2C0h+var_98], 7
0x180052c05  mov     word ptr [rbp+2C0h+var_B0], r14w
0x180052c0d  movdqu  xmmword ptr [rbp+2C0h+pbBinary], xmm0
0x180052c12  mov     [rbp+2C0h+var_328], r14
0x180052c16  mov     dword ptr [rsp+3C0h+Src], r14d
0x180052c1b  mov     [rsp+3C0h+cbBinary+4], r14d
0x180052c20  mov     dword ptr [rbp+2C0h+var_340], r14d
0x180052c24  mov     [rsp+3C0h+cbBinary], 1
0x180052c2c  movups  xmmword ptr [rbp+2C0h+var_70.wYear], xmm0
0x180052c33  mov     byte ptr [rsp+3C0h+var_360], 1
0x180052c38  lea     rcx, [rbp+2C0h+var_2F0]
0x180052c3c  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180052c41  nop
0x180052c42  mov     [rbp+2C0h+var_318], r14
0x180052c46  mov     [rbp+2C0h+var_320], r14
0x180052c4a  test    edi, edi
0x180052c4c  jz      loc_180053B2B
0x180052c52  test    rsi, rsi
0x180052c55  jz      loc_180053B2B
0x180052c5b  mov     r14b, [rsi+4]
0x180052c5f  test    r14b, r14b
0x180052c62  jnz     short loc_180052CB1
0x180052c64  lea     rcx, [rsi+5]
0x180052c68  lea     rax, [rsp+3C0h+var_360]
0x180052c6d  mov     [rsp+3C0h+var_380], rax
0x180052c72  lea     rax, [rbp+2C0h+var_70]
0x180052c79  mov     [rsp+3C0h+lpSystemTime], rax
0x180052c7e  lea     rax, [rsp+3C0h+cbBinary]
0x180052c83  mov     [rsp+3C0h+var_390], rax
0x180052c88  lea     rax, [rsp+3C0h+var_360+4]
0x180052c8d  mov     [rsp+3C0h+var_398], rax
0x180052c92  lea     rax, [rsp+3C0h+Src]
0x180052c97  mov     [rsp+3C0h+ppv], rax
0x180052c9c  lea     r9, [rbp+2C0h+var_90]
0x180052ca3  mov     r8, r12
0x180052ca6  mov     edx, [rsi]
0x180052ca8  call    ?DecodeMessageGsm@CSmsEncodingHelper@@SAJPEAEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK3AEAW4SMS_DATA_ENCODING@@AEAU_SYSTEMTIME@@AEAE@Z; CSmsEncodingHelper::DecodeMessageGsm(uchar *,ulong,ushort const *,std::wstring &,ulong &,ulong &,SMS_DATA_ENCODING &,_SYSTEMTIME &,uchar &)
0x180052cad  mov     edi, eax
0x180052caf  jmp     short loc_180052D1B
0x180052cb1  cmp     r14b, 1
0x180052cb5  jnz     short loc_180052D2F
0x180052cb7  lea     rcx, [rsi+5]; int
0x180052cbb  lea     rax, [rsp+3C0h+cbBinary+4]
0x180052cc0  mov     [rsp+3C0h+var_370], rax; __int64
0x180052cc5  lea     rax, [rbp+2C0h+var_B0]
0x180052ccc  mov     [rsp+3C0h+var_378], rax; __int64
0x180052cd1  lea     rax, [rsp+3C0h+var_360]
0x180052cd6  mov     [rsp+3C0h+var_380], rax; __int64
0x180052cdb  lea     rax, [rbp+2C0h+var_70]
0x180052ce2  mov     [rsp+3C0h+lpSystemTime], rax; lpSystemTime
0x180052ce7  lea     rax, [rsp+3C0h+cbBinary]
0x180052cec  mov     [rsp+3C0h+var_390], rax; __int64
0x180052cf1  lea     rax, [rsp+3C0h+var_360+4]
0x180052cf6  mov     [rsp+3C0h+var_398], rax; __int64
0x180052cfb  lea     rax, [rbp+2C0h+var_340]
0x180052cff  mov     [rsp+3C0h+ppv], rax; __int64
0x180052d04  lea     r9, [rbp+2C0h+var_90]; int
0x180052d0b  mov     edx, [rsi]; int
0x180052d0d  call    ?DecodeMessageCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK3AEAW4SMS_DATA_ENCODING@@AEAU_SYSTEMTIME@@AEAE23@Z; CSmsEncodingHelper::DecodeMessageCdma(uchar const *,ulong,ushort const *,std::wstring &,ulong &,ulong &,SMS_DATA_ENCODING &,_SYSTEMTIME &,uchar &,std::wstring &,ulong &)
0x180052d12  mov     edi, eax
0x180052d14  mov     eax, dword ptr [rbp+2C0h+var_340]
0x180052d17  mov     [rsp+3C0h+cbBinary+4], eax
0x180052d1b  mov     r13d, dword ptr [rsp+3C0h+var_360+4]
0x180052d20  mov     r15d, [rsp+3C0h+cbBinary]
0x180052d25  mov     dword ptr [rsp+3C0h+var_360+4], r15d
0x180052d2a  jmp     loc_180052DC8
0x180052d2f  cmp     r14b, 2
0x180052d33  jnz     loc_180053AC2
0x180052d39  lea     rcx, [rbp+2C0h+var_1F0]
0x180052d40  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180052d45  nop
0x180052d46  lea     rdx, [rsi+0Dh]
0x180052d4a  lea     rcx, [rbp+2C0h+var_1E0]
0x180052d51  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180052d56  lea     rdx, [rbp+2C0h+var_60]
0x180052d5d  lea     rcx, [rbp+2C0h+var_1D8]
0x180052d64  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180052d69  lea     rdx, [rbp+2C0h+var_60]
0x180052d70  lea     rcx, [rbp+2C0h+var_90]
0x180052d77  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180052d7c  lea     rcx, [rbp+2C0h+var_60]; void *
0x180052d83  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052d88  mov     eax, 1002h
0x180052d8d  mov     [rsp+3C0h+cbBinary+4], eax
0x180052d91  lea     rcx, [rsi+3Fh]; char *
0x180052d95  lea     rdx, [rbp+2C0h+var_70]; struct _SYSTEMTIME *
0x180052d9c  call    ?DecodeCdmaTextTimeStamp@CSmsEncodingHelper@@SAJPEADAEAU_SYSTEMTIME@@@Z; CSmsEncodingHelper::DecodeCdmaTextTimeStamp(char *,_SYSTEMTIME &)
0x180052da1  mov     edi, eax
0x180052da3  mov     ecx, [rsi+55h]
0x180052da6  call    ?GetSmsDataEncodingType@@YA?AW4SMS_DATA_ENCODING@@W4_WWAN_SMS_CDMA_ENCODING@@@Z; GetSmsDataEncodingType(_WWAN_SMS_CDMA_ENCODING)
0x180052dab  mov     dword ptr [rsp+3C0h+var_360+4], eax
0x180052daf  lea     rcx, [rbp+2C0h+var_158]
0x180052db6  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180052dbb  lea     rcx, [rbp+2C0h+var_158]
0x180052dc2  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180052dc8  test    edi, edi
0x180052dca  js      loc_180053AC7
0x180052dd0  xor     r15d, r15d
0x180052dd3  cmp     dword ptr [rsp+3C0h+var_350], r15d
0x180052dd8  jbe     loc_180052E9C
0x180052dde  mov     eax, r15d
0x180052de1  imul    rdx, rax, 208h
0x180052de8  mov     al, [rdx+rsi+4]
0x180052dec  test    al, al
0x180052dee  jnz     short loc_180052E14
0x180052df0  lea     rcx, [rsi+5]
0x180052df4  add     rcx, rdx
0x180052df7  lea     rax, [rbp+2C0h+pbBinary]
0x180052dfb  mov     [rsp+3C0h+ppv], rax
0x180052e00  lea     r9, [rbp+2C0h+var_D0]
0x180052e07  mov     r8, r12
0x180052e0a  mov     edx, [rdx+rsi]
0x180052e0d  call    ?AppendMessageContentsGsm@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsGsm(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x180052e12  jmp     short loc_180052E88
0x180052e14  cmp     al, 1
0x180052e16  jnz     short loc_180052E3C
0x180052e18  lea     rcx, [rsi+5]
0x180052e1c  add     rcx, rdx
0x180052e1f  lea     rax, [rbp+2C0h+pbBinary]
0x180052e23  mov     [rsp+3C0h+ppv], rax
0x180052e28  lea     r9, [rbp+2C0h+var_D0]
0x180052e2f  mov     r8, r12
0x180052e32  mov     edx, [rdx+rsi]
0x180052e35  call    ?AppendMessageContentsCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsCdma(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x180052e3a  jmp     short loc_180052E88
0x180052e3c  cmp     al, 2
0x180052e3e  jnz     loc_180052F06
0x180052e44  movzx   r8d, byte ptr [rsi+5Fh]
0x180052e49  movzx   r9d, word ptr [rsi+5Dh]
0x180052e4e  mov     ecx, [rsi+55h]
0x180052e51  call    ?GetSmsDataEncodingType@@YA?AW4SMS_DATA_ENCODING@@W4_WWAN_SMS_CDMA_ENCODING@@@Z; GetSmsDataEncodingType(_WWAN_SMS_CDMA_ENCODING)
0x180052e56  mov     edx, eax
0x180052e58  lea     rcx, [rsi+60h]; lpMultiByteStr
0x180052e5c  lea     rax, [rbp+2C0h+pbBinary]
0x180052e60  mov     [rsp+3C0h+var_380], rax; __int64
0x180052e65  lea     rax, [rbp+2C0h+var_D0]
0x180052e6c  mov     [rsp+3C0h+lpSystemTime], rax; Src
0x180052e71  mov     dword ptr [rsp+3C0h+var_390], 0; int
0x180052e79  mov     [rsp+3C0h+var_398], r12; unsigned __int16 *
0x180052e7e  mov     dword ptr [rsp+3C0h+ppv], r8d; int
0x180052e83  call    ?AppendMessageContentsCdmaText@CSmsEncodingHelper@@SAJPEBEW4SMS_DATA_ENCODING@@KKKPEBGKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; CSmsEncodingHelper::AppendMessageContentsCdmaText(uchar const *,SMS_DATA_ENCODING,ulong,ulong,ulong,ushort const *,ulong,std::wstring &,std::vector<uchar> &)
0x180052e88  mov     edi, eax
0x180052e8a  test    eax, eax
0x180052e8c  js      short loc_180052F0B
0x180052e8e  inc     r15d
0x180052e91  cmp     r15d, dword ptr [rsp+3C0h+var_350]
0x180052e96  jb      loc_180052DDE
0x180052e9c  mov     r9d, r13d
0x180052e9f  lea     r8, aDeliverMessage; "Deliver message decoded with portnumber"...
0x180052ea6  mov     edx, 249h; unsigned int
0x180052eab  lea     rcx, aGetdelivermess; "GetDeliverMessageXml"
0x180052eb2  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180052eb7  mov     [rsp+3C0h+var_350], 0
0x180052ec0  lea     rax, [rsp+3C0h+var_350]
0x180052ec5  mov     [rsp+3C0h+ppv], rax; ppv
0x180052eca  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180052ed1  xor     edx, edx; pUnkOuter
0x180052ed3  lea     r8d, [rdx+17h]; dwClsContext
0x180052ed7  lea     rcx, CLSID_DOMDocument60; rclsid
0x180052ede  call    cs:__imp_CoCreateInstance
0x180052ee4  mov     edi, eax
0x180052ee6  test    eax, eax
0x180052ee8  jns     short loc_180052F2C
0x180052eea  mov     rcx, [rsp+3C0h+var_350]
0x180052eef  test    rcx, rcx
0x180052ef2  jz      short loc_180052F01
0x180052ef4  mov     rdx, [rcx]
0x180052ef7  mov     rax, [rdx+10h]
0x180052efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f00  nop
0x180052f01  jmp     loc_180053AE3
0x180052f06  mov     edi, 80004001h
0x180052f0b  lea     r9, aFailedToDecode_2; "Failed to decode the text data of the p"...
0x180052f12  mov     r8d, edi; int
0x180052f15  mov     edx, 244h; unsigned int
0x180052f1a  lea     rcx, aGetdelivermess; "GetDeliverMessageXml"
0x180052f21  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180052f26  nop
0x180052f27  jmp     loc_180053AE3
0x180052f2c  mov     rdi, [rsp+3C0h+var_350]
0x180052f31  mov     [rbp+2C0h+var_318], rdi
0x180052f35  lea     r9, [rbp+2C0h+var_320]; struct IXMLDOMNode **
0x180052f39  xor     r8d, r8d; unsigned __int16 *
0x180052f3c  lea     rdx, aMessage; "Message"
0x180052f43  mov     rcx, rdi; struct IXMLDOMNode *
0x180052f46  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180052f4b  mov     ebx, eax
0x180052f4d  test    eax, eax
0x180052f4f  jns     short loc_180052F83
0x180052f51  mov     rcx, [rbp+2C0h+var_320]
0x180052f55  test    rcx, rcx
0x180052f58  jz      short loc_180052F67
0x180052f5a  mov     rdx, [rcx]
0x180052f5d  mov     rax, [rdx+10h]
0x180052f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f66  nop
0x180052f67  test    rdi, rdi
0x180052f6a  jz      short loc_180052F7C
0x180052f6c  mov     rax, [rdi]
0x180052f6f  mov     rcx, rdi
0x180052f72  mov     rax, [rax+10h]
0x180052f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f7b  nop
0x180052f7c  mov     edi, ebx
0x180052f7e  jmp     loc_180053AE3
0x180052f83  xor     r9d, r9d; struct IXMLDOMNode **
0x180052f86  mov     r8, [rbp+2C0h+var_310]; unsigned __int16 *
0x180052f8a  lea     rdx, aSmsdeviceid; "SmsDeviceId"
0x180052f91  mov     rbx, [rbp+2C0h+var_320]
0x180052f95  mov     rcx, rbx; struct IXMLDOMNode *
0x180052f98  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180052f9d  mov     esi, eax
0x180052f9f  test    eax, eax
0x180052fa1  jns     short loc_180052FD2
0x180052fa3  test    rbx, rbx
0x180052fa6  jz      short loc_180052FB8
0x180052fa8  mov     rcx, [rbx]
0x180052fab  mov     rax, [rcx+10h]
0x180052faf  mov     rcx, rbx
0x180052fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fb7  nop
0x180052fb8  test    rdi, rdi
0x180052fbb  jz      short loc_180052FCD
0x180052fbd  mov     rax, [rdi]
0x180052fc0  mov     rcx, rdi
0x180052fc3  mov     rax, [rax+10h]
0x180052fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fcc  nop
0x180052fcd  jmp     loc_180053A50
0x180052fd2  xor     r9d, r9d; struct IXMLDOMNode **
0x180052fd5  mov     r8, [rbp+2C0h+var_308]; unsigned __int16 *
0x180052fd9  lea     rdx, aSimiccid; "SimIccId"
0x180052fe0  mov     rcx, rbx; struct IXMLDOMNode *
0x180052fe3  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180052fe8  mov     esi, eax
0x180052fea  test    eax, eax
0x180052fec  jns     short loc_18005301D
0x180052fee  test    rbx, rbx
0x180052ff1  jz      short loc_180053003
0x180052ff3  mov     rcx, [rbx]
0x180052ff6  mov     rax, [rcx+10h]
0x180052ffa  mov     rcx, rbx
0x180052ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053002  nop
0x180053003  test    rdi, rdi
0x180053006  jz      short loc_180053018
0x180053008  mov     rax, [rdi]
0x18005300b  mov     rcx, rdi
0x18005300e  mov     rax, [rax+10h]
0x180053012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053017  nop
0x180053018  jmp     loc_180053A50
0x18005301d  xor     r9d, r9d; struct IXMLDOMNode **
0x180053020  mov     r8, r12; unsigned __int16 *
0x180053023  lea     rdx, aImsi; "Imsi"
0x18005302a  mov     rcx, rbx; struct IXMLDOMNode *
0x18005302d  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180053032  mov     esi, eax
0x180053034  xor     r12d, r12d
0x180053037  test    eax, eax
0x180053039  jns     short loc_18005306A
0x18005303b  test    rbx, rbx
0x18005303e  jz      short loc_180053050
  ... truncated ...
```
