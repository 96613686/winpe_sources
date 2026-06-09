# GetVoicemailMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)

- ea: `0x1800547d8`
- end: `0x18005543e`
- name: `?GetVoicemailMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z`
- size: `3174`
- prototype: `int(struct WwanSmsStoreMessage *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d1d8`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000d388`
- `0x18000e05c`
- `0x18000e534`
- `0x18000e7ac`
- `0x180013d40`
- `0x180014d48`
- `0x1800288f4`
- `0x18002cafc`
- `0x18002f864`
- `0x18003246c`
- `0x180051628`
- `0x180053c98`
- `0x1800547d8`
- `0x1800578c4`
- `0x180057ec0`
- `0x180058070`
- `0x18005a278`
- `0x18005a67c`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054d5e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054f86`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800550c6`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054d5e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054f86`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800550c6`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18005534f`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800553a0`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800553e9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18005534f`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800553a0`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800553e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054abd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054abd`

## string_xrefs

- `0x1800550f7`: `TeleserviceId`
- `0x180054fb7`: `ProtocolId`
- `0x180054a62`: `GetVoicemailMessageXml`
- `0x180054a8c`: `GetVoicemailMessageXml`
- `0x180054a80`: `Voicemail message decoded now generating xml for the message.`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall GetVoicemailMessageXml(
        struct WwanSmsStoreMessage *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct IXMLDOMDocument **a7)
{
  unsigned int v10; // esi
  int v11; // r8d
  char v12; // al
  int v13; // eax
  HRESULT Instance; // edi
  __int64 v15; // r15
  __int64 v16; // rdx
  char v17; // al
  int appended; // eax
  int v19; // r8d
  struct IXMLDOMNode *v20; // r15
  struct IXMLDOMNode *v21; // rdi
  int v22; // ebx
  struct IXMLDOMNode *v23; // rbx
  int v24; // esi
  SYSTEMTIME *p_SystemTime; // r8
  SYSTEMTIME *v26; // r8
  char v27; // al
  SYSTEMTIME *v28; // r8
  SYSTEMTIME *v29; // r8
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r8
  SYSTEMTIME *v32; // r8
  const unsigned __int16 *v33; // r8
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h]
  unsigned int v39; // [rsp+78h] [rbp-88h] BYREF
  struct IXMLDOMNode *ppv; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMNode *v41; // [rsp+88h] [rbp-78h] BYREF
  struct IXMLDOMNode *v42; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v43; // [rsp+98h] [rbp-68h]
  struct IXMLDOMDocument **v44; // [rsp+A0h] [rbp-60h]
  _BYTE v45[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v46[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v47[128]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v48[104]; // [rsp+148h] [rbp+48h] BYREF
  SYSTEMTIME SystemTime; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v50; // [rsp+1C0h] [rbp+C0h]
  unsigned __int16 *Src[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v52; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v53; // [rsp+1E8h] [rbp+E8h]
  unsigned __int16 *v54[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v55; // [rsp+200h] [rbp+100h]
  unsigned __int64 v56; // [rsp+208h] [rbp+108h]
  unsigned __int16 *v57[2]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v58; // [rsp+220h] [rbp+120h]
  unsigned __int64 v59; // [rsp+228h] [rbp+128h]
  struct _SYSTEMTIME lpSystemTime; // [rsp+230h] [rbp+130h] BYREF

  v43 = a3;
  ppv = (struct IXMLDOMNode *)a5;
  *(_QWORD *)&SystemTime.wYear = a6;
  v44 = a7;
  v10 = 0;
  lpSystemTime = 0;
  *(_OWORD *)Src = 0;
  v52 = 0;
  v53 = 7;
  LOWORD(Src[0]) = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  v56 = 7;
  LOWORD(v54[0]) = 0;
  *(_OWORD *)v57 = 0;
  v58 = 0;
  v59 = 7;
  LOWORD(v57[0]) = 0;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v45);
  v35 = 0x100000000LL;
  v39 = 0;
  LODWORD(v36) = 0;
  v42 = 0;
  v41 = 0;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  if ( !a2 || !a1 )
  {
    std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v48);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v48);
    std::wstring::~wstring((char **)v57);
    std::wstring::~wstring((char **)v54);
    std::wstring::~wstring((char **)Src);
    return 2147942487LL;
  }
  v12 = *((_BYTE *)a1 + 4);
  if ( v12 )
  {
    if ( v12 != 1 )
    {
      Instance = -2147467263;
      goto LABEL_137;
    }
    v13 = CSmsEncodingHelper::DecodeVoicemailCdma(
            (int)a1 + 5,
            *(_DWORD *)a1,
            v11,
            (int)v54,
            (__int64)&v36,
            (__int64)&v35,
            (__int64)&v35 + 4,
            &lpSystemTime,
            (__int64)v57);
  }
  else
  {
    v13 = CSmsEncodingHelper::DecodeVoicemailGsm(
            (char *)a1 + 5,
            *(unsigned int *)a1,
            a4,
            v54,
            &v39,
            &v35,
            (char *)&v35 + 4,
            &lpSystemTime);
  }
  Instance = v13;
  if ( v13 < 0 )
    goto LABEL_137;
  v15 = 0;
  do
  {
    v16 = 520 * v15;
    v17 = *((_BYTE *)a1 + 520 * v15 + 4);
    switch ( v17 )
    {
      case 0:
        appended = CSmsEncodingHelper::AppendMessageContentsGsm(
                     (char *)a1 + v16 + 5,
                     *(unsigned int *)((char *)a1 + v16),
                     a4,
                     Src,
                     v37);
        goto LABEL_15;
      case 1:
        appended = CSmsEncodingHelper::AppendMessageContentsCdma(
                     (int)v16 + (int)a1 + 5,
                     *(_DWORD *)((char *)a1 + v16),
                     (_DWORD)a4,
                     (unsigned int)Src,
                     (__int64)v37);
        goto LABEL_15;
      case 2:
        GetSmsDataEncodingType(*(unsigned int *)((char *)a1 + 85));
        appended = CSmsEncodingHelper::AppendMessageContentsCdmaText((LPCCH)a1 + 96, v19, a4, 0, Src, (__int64)v37);
LABEL_15:
        if ( appended >= 0 )
          goto LABEL_19;
        goto LABEL_18;
    }
    appended = -2147467263;
LABEL_18:
    LogSmsRouterInfo(
      "GetVoicemailMessageXml",
      0x443u,
      "Ignoring Failure (0x%08X) to decode the text data of the voicemail message partindex %d, totalparts %d.",
      appended,
      v10,
      a2);
LABEL_19:
    ++v10;
    ++v15;
  }
  while ( v10 < a2 );
  v20 = ppv;
  LogSmsRouterInfo("GetVoicemailMessageXml", 0x44Cu, "Voicemail message decoded now generating xml for the message.");
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_DOMDocument60,
               0,
               0x17u,
               &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v21 = ppv;
    v42 = ppv;
    v22 = Windows::Sms::Common::CSmsUtil::AddElement(ppv, L"Message", 0, &v41);
    if ( v22 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
      if ( v41 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v41->lpVtbl->Release)(v41);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      Instance = v22;
      goto LABEL_138;
    }
    v23 = v41;
    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v41, L"MessageType", L"Voicemail", 0);
    if ( v24 >= 0 )
    {
      v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"SmsDeviceId", v43, 0);
      if ( v24 >= 0 )
      {
        v24 = Windows::Sms::Common::CSmsUtil::AddElement(
                v23,
                L"SimIccId",
                *(const unsigned __int16 **)&SystemTime.wYear,
                0);
        if ( v24 >= 0 )
        {
          v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Imsi", a4, 0);
          if ( v24 >= 0 )
          {
            if ( v20
              && (v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Receiver", (const unsigned __int16 *)v20, 0),
                  v24 < 0) )
            {
              std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
              if ( v23 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
              if ( v21 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
            }
            else
            {
              SystemTime = 0;
              v50 = 0;
              std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
              std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                v45,
                &SystemTime);
              std::wstring::~wstring((char **)&SystemTime);
              std::basic_ostream<unsigned short>::operator<<(v46, (unsigned int)v35);
              std::basic_stringbuf<unsigned short>::str(v47, &SystemTime);
              p_SystemTime = &SystemTime;
              if ( *((_QWORD *)&v50 + 1) > 7u )
                p_SystemTime = *(SYSTEMTIME **)&SystemTime.wYear;
              v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"NumberOfMessages", &p_SystemTime->wYear, 0);
              std::wstring::~wstring((char **)&SystemTime);
              if ( v24 >= 0 )
              {
                SystemTime = 0;
                v50 = 0;
                std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
                std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                  v45,
                  &SystemTime);
                std::wstring::~wstring((char **)&SystemTime);
                SystemTime = lpSystemTime;
                GetTimeString(&SystemTime);
                std::basic_stringbuf<unsigned short>::str(v47, &SystemTime);
                v26 = &SystemTime;
                if ( *((_QWORD *)&v50 + 1) > 7u )
                  v26 = *(SYSTEMTIME **)&SystemTime.wYear;
                v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"ReceiveTime", &v26->wYear, 0);
                std::wstring::~wstring((char **)&SystemTime);
                if ( v24 >= 0 )
                {
                  v27 = *((_BYTE *)a1 + 4);
                  if ( v27 )
                  {
                    if ( (unsigned __int8)(v27 - 1) <= 1u )
                    {
                      v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"CellularClass", L"Cdma", 0);
                      if ( v24 < 0 )
                      {
                        std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                        if ( v23 )
                          ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                        if ( v21 )
                          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                        goto LABEL_35;
                      }
                      SystemTime = 0;
                      v50 = 0;
                      std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
                      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                        v45,
                        &SystemTime);
                      std::wstring::~wstring((char **)&SystemTime);
                      std::basic_ostream<unsigned short>::operator<<(v46, (unsigned int)v36);
                      std::basic_stringbuf<unsigned short>::str(v47, &SystemTime);
                      v29 = &SystemTime;
                      if ( *((_QWORD *)&v50 + 1) > 7u )
                        v29 = *(SYSTEMTIME **)&SystemTime.wYear;
                      v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"TeleserviceId", &v29->wYear, 0);
                      std::wstring::~wstring((char **)&SystemTime);
                      if ( v24 < 0 )
                      {
                        std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                        if ( v23 )
                          ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                        if ( v21 )
                          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                        goto LABEL_35;
                      }
                      if ( v58 )
                      {
                        v30 = (const unsigned __int16 *)v57;
                        if ( v59 > 7 )
                          v30 = v57[0];
                        Windows::Sms::Common::CSmsUtil::AddElement(v23, L"CallbackNumber", v30, 0);
                      }
                    }
                  }
                  else
                  {
                    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"CellularClass", L"Gsm", 0);
                    if ( v24 < 0 )
                    {
                      std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                      if ( v23 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                      if ( v21 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                      goto LABEL_35;
                    }
                    SystemTime = 0;
                    v50 = 0;
                    std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
                    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                      v45,
                      &SystemTime);
                    std::wstring::~wstring((char **)&SystemTime);
                    std::basic_ostream<unsigned short>::operator<<(v46, v39);
                    std::basic_stringbuf<unsigned short>::str(v47, &SystemTime);
                    v28 = &SystemTime;
                    if ( *((_QWORD *)&v50 + 1) > 7u )
                      v28 = *(SYSTEMTIME **)&SystemTime.wYear;
                    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"ProtocolId", &v28->wYear, 0);
                    std::wstring::~wstring((char **)&SystemTime);
                    if ( v24 < 0 )
                    {
                      std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                      if ( v23 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                      if ( v21 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                      goto LABEL_35;
                    }
                  }
                  if ( !v52 )
                    goto LABEL_142;
                  v31 = (const unsigned __int16 *)Src;
                  if ( v53 > 7 )
                    v31 = Src[0];
                  if ( (int)Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Text", v31, 0) < 0 )
                    Windows::Sms::Common::CSmsUtil::DeleteElement(v23, L"Text");
                  SystemTime = 0;
                  v50 = 0;
                  std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
                  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                    v45,
                    &SystemTime);
                  std::wstring::~wstring((char **)&SystemTime);
                  GetEncodingString(HIDWORD(v35), v45);
                  std::basic_stringbuf<unsigned short>::str(v47, &SystemTime);
                  v32 = &SystemTime;
                  if ( *((_QWORD *)&v50 + 1) > 7u )
                    v32 = *(SYSTEMTIME **)&SystemTime.wYear;
                  v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Encoding", &v32->wYear, 0);
                  std::wstring::~wstring((char **)&SystemTime);
                  if ( v24 < 0 )
                  {
                    std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                    if ( v23 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                    if ( v21 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                  }
                  else
                  {
LABEL_142:
                    if ( !v55 )
                      goto LABEL_133;
                    v33 = (const unsigned __int16 *)v54;
                    if ( v56 > 7 )
                      v33 = v54[0];
                    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Sender", v33, 0);
                    if ( v24 >= 0 )
                    {
LABEL_133:
                      *v44 = (struct IXMLDOMDocument *)v21;
                      v42 = 0;
                      std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                      if ( v23 )
                        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v48);
                      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v48);
                      std::wstring::~wstring((char **)v57);
                      std::wstring::~wstring((char **)v54);
                      std::wstring::~wstring((char **)Src);
                      return (unsigned int)v24;
                    }
                    std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                    if ( v23 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                    if ( v21 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                  }
                }
                else
                {
                  std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                  if ( v23 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                  if ( v21 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
                }
              }
              else
              {
                std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
                if ( v23 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
                if ( v21 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
              }
            }
          }
          else
          {
            std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
            if ( v23 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
            if ( v21 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          }
        }
        else
        {
          std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
          if ( v23 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
          if ( v21 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
        }
      }
      else
      {
        std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
        if ( v23 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      }
    }
    else
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
      if ( v23 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
    }
LABEL_35:
    Instance = v24;
    goto LABEL_138;
  }
  if ( ppv )
    ((void (__fastcall *)(struct IXMLDOMNode *))ppv->lpVtbl->Release)(ppv);
LABEL_137:
  std::vector<unsigned char>::~vector<unsigned char>((char **)v37);
LABEL_138:
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v48);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v48);
  std::wstring::~wstring((char **)v57);
  std::wstring::~wstring((char **)v54);
  std::wstring::~wstring((char **)Src);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800547d8  push    rbp
0x1800547da  push    rbx
0x1800547db  push    rsi
0x1800547dc  push    rdi
0x1800547dd  push    r12
0x1800547df  push    r13
0x1800547e1  push    r14
0x1800547e3  push    r15
0x1800547e5  lea     rbp, [rsp-158h]
0x1800547ed  sub     rsp, 258h
0x1800547f4  mov     rax, cs:__security_cookie
0x1800547fb  xor     rax, rsp
0x1800547fe  mov     [rbp+190h+var_50], rax
0x180054805  mov     r13, r9
0x180054808  mov     [rbp+190h+var_1F8], r8
0x18005480c  mov     r12d, edx
0x18005480f  mov     r14, rcx
0x180054812  mov     r15, [rbp+190h+arg_20]
0x180054819  mov     [rbp+190h+var_210], r15
0x18005481d  mov     rax, [rbp+190h+arg_28]
0x180054824  mov     qword ptr [rbp+190h+SystemTime.wYear], rax
0x18005482b  mov     rax, [rbp+190h+arg_30]
0x180054832  mov     [rbp+190h+var_1F0], rax
0x180054836  xor     esi, esi
0x180054838  xorps   xmm0, xmm0
0x18005483b  movups  xmmword ptr [rbp+190h+var_60.wYear], xmm0
0x180054842  xorps   xmm1, xmm1
0x180054845  movups  xmmword ptr [rbp+190h+Src], xmm1
0x18005484c  mov     [rbp+190h+var_B0], rsi
0x180054853  lea     ecx, [rsi+7]
0x180054856  mov     [rbp+190h+var_A8], rcx
0x18005485d  mov     word ptr [rbp+190h+Src], si
0x180054864  movups  xmmword ptr [rbp+190h+var_A0], xmm0
0x18005486b  mov     [rbp+190h+var_90], rsi
0x180054872  mov     [rbp+190h+var_88], rcx
0x180054879  mov     word ptr [rbp+190h+var_A0], si
0x180054880  movups  xmmword ptr [rbp+190h+var_80], xmm0
0x180054887  mov     [rbp+190h+var_70], rsi
0x18005488e  mov     [rbp+190h+var_68], rcx
0x180054895  mov     word ptr [rbp+190h+var_80], si
0x18005489c  lea     rcx, [rbp+190h+var_1E0]
0x1800548a0  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x1800548a5  nop
0x1800548a6  mov     dword ptr [rsp+290h+var_240], esi
0x1800548aa  mov     [rsp+290h+var_218], esi
0x1800548ae  mov     dword ptr [rsp+290h+var_238], esi
0x1800548b2  mov     [rbp+190h+var_200], rsi
0x1800548b6  mov     [rbp+190h+var_208], rsi
0x1800548ba  mov     dword ptr [rsp+290h+var_240+4], 1
0x1800548c2  xorps   xmm0, xmm0
0x1800548c5  movdqu  xmmword ptr [rsp+290h+var_230], xmm0
0x1800548cb  mov     [rsp+290h+var_220], rsi
0x1800548d0  test    r12d, r12d
0x1800548d3  jz      loc_1800553D1
0x1800548d9  test    r14, r14
0x1800548dc  jz      loc_1800553D1
0x1800548e2  mov     al, [r14+4]
0x1800548e6  test    al, al
0x1800548e8  jnz     short loc_18005492C
0x1800548ea  lea     rcx, [r14+5]
0x1800548ee  lea     rax, [rbp+190h+var_60]
0x1800548f5  mov     [rsp+290h+lpSystemTime], rax
0x1800548fa  lea     rax, [rsp+290h+var_240+4]
0x1800548ff  mov     [rsp+290h+var_260], rax
0x180054904  lea     rax, [rsp+290h+var_240]
0x180054909  mov     [rsp+290h+var_268], rax
0x18005490e  lea     rax, [rsp+290h+var_218]
0x180054913  mov     [rsp+290h+ppv], rax
0x180054918  lea     r9, [rbp+190h+var_A0]
0x18005491f  mov     r8, r13
0x180054922  mov     edx, [r14]
0x180054925  call    ?DecodeVoicemailGsm@CSmsEncodingHelper@@SAJPEAEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK3AEAW4SMS_DATA_ENCODING@@AEAU_SYSTEMTIME@@@Z; CSmsEncodingHelper::DecodeVoicemailGsm(uchar *,ulong,ushort const *,std::wstring &,ulong &,ulong &,SMS_DATA_ENCODING &,_SYSTEMTIME &)
0x18005492a  jmp     short loc_18005497D
0x18005492c  cmp     al, 1
0x18005492e  jnz     loc_180055383
0x180054934  lea     rcx, [r14+5]; int
0x180054938  lea     rax, [rbp+190h+var_80]
0x18005493f  mov     [rsp+290h+var_250], rax; __int64
0x180054944  lea     rax, [rbp+190h+var_60]
0x18005494b  mov     [rsp+290h+lpSystemTime], rax; lpSystemTime
0x180054950  lea     rax, [rsp+290h+var_240+4]
0x180054955  mov     [rsp+290h+var_260], rax; __int64
0x18005495a  lea     rax, [rsp+290h+var_240]
0x18005495f  mov     [rsp+290h+var_268], rax; __int64
0x180054964  lea     rax, [rsp+290h+var_238]
0x180054969  mov     [rsp+290h+ppv], rax; __int64
0x18005496e  lea     r9, [rbp+190h+var_A0]; int
0x180054975  mov     edx, [r14]; int
0x180054978  call    ?DecodeVoicemailCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK3AEAW4SMS_DATA_ENCODING@@AEAU_SYSTEMTIME@@2@Z; CSmsEncodingHelper::DecodeVoicemailCdma(uchar const *,ulong,ushort const *,std::wstring &,ulong &,ulong &,SMS_DATA_ENCODING &,_SYSTEMTIME &,std::wstring &)
0x18005497d  mov     edi, eax
0x18005497f  test    eax, eax
0x180054981  js      loc_180055388
0x180054987  test    r12d, r12d
0x18005498a  jz      loc_180054A80
0x180054990  xor     r15d, r15d
0x180054993  mov     edi, 80004001h
0x180054998  imul    rdx, r15, 208h
0x18005499f  mov     al, [rdx+r14+4]
0x1800549a4  test    al, al
0x1800549a6  jnz     short loc_1800549CE
0x1800549a8  lea     rcx, [r14+5]
0x1800549ac  add     rcx, rdx
0x1800549af  lea     rax, [rsp+290h+var_230]
0x1800549b4  mov     [rsp+290h+ppv], rax
0x1800549b9  lea     r9, [rbp+190h+Src]
0x1800549c0  mov     r8, r13
0x1800549c3  mov     edx, [rdx+r14]
0x1800549c7  call    ?AppendMessageContentsGsm@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsGsm(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x1800549cc  jmp     short loc_180054A42
0x1800549ce  cmp     al, 1
0x1800549d0  jnz     short loc_1800549F8
0x1800549d2  lea     rcx, [r14+5]
0x1800549d6  add     rcx, rdx
0x1800549d9  lea     rax, [rsp+290h+var_230]
0x1800549de  mov     [rsp+290h+ppv], rax
0x1800549e3  lea     r9, [rbp+190h+Src]
0x1800549ea  mov     r8, r13
0x1800549ed  mov     edx, [rdx+r14]
0x1800549f1  call    ?AppendMessageContentsCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsCdma(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x1800549f6  jmp     short loc_180054A42
0x1800549f8  cmp     al, 2
0x1800549fa  jnz     short loc_180054A48
0x1800549fc  movzx   r8d, byte ptr [r14+5Fh]
0x180054a01  movzx   r9d, word ptr [r14+5Dh]
0x180054a06  mov     ecx, [r14+55h]
0x180054a0a  call    ?GetSmsDataEncodingType@@YA?AW4SMS_DATA_ENCODING@@W4_WWAN_SMS_CDMA_ENCODING@@@Z; GetSmsDataEncodingType(_WWAN_SMS_CDMA_ENCODING)
0x180054a0f  mov     edx, eax
0x180054a11  lea     rcx, [r14+60h]; lpMultiByteStr
0x180054a15  lea     rax, [rsp+290h+var_230]
0x180054a1a  mov     [rsp+290h+var_250], rax; __int64
0x180054a1f  lea     rax, [rbp+190h+Src]
0x180054a26  mov     [rsp+290h+lpSystemTime], rax; Src
0x180054a2b  mov     dword ptr [rsp+290h+var_260], 0; int
0x180054a33  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x180054a38  mov     dword ptr [rsp+290h+ppv], r8d; int
0x180054a3d  call    ?AppendMessageContentsCdmaText@CSmsEncodingHelper@@SAJPEBEW4SMS_DATA_ENCODING@@KKKPEBGKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; CSmsEncodingHelper::AppendMessageContentsCdmaText(uchar const *,SMS_DATA_ENCODING,ulong,ulong,ulong,ushort const *,ulong,std::wstring &,std::vector<uchar> &)
0x180054a42  test    eax, eax
0x180054a44  jns     short loc_180054A6E
0x180054a46  jmp     short loc_180054A4A
0x180054a48  mov     eax, edi
0x180054a4a  mov     dword ptr [rsp+290h+var_268], r12d
0x180054a4f  mov     dword ptr [rsp+290h+ppv], esi
0x180054a53  mov     r9d, eax
0x180054a56  lea     r8, aIgnoringFailur_0; "Ignoring Failure (0x%08X) to decode the"...
0x180054a5d  mov     edx, 443h; unsigned int
0x180054a62  lea     rcx, aGetvoicemailme; "GetVoicemailMessageXml"
0x180054a69  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180054a6e  inc     esi
0x180054a70  inc     r15
0x180054a73  cmp     esi, r12d
0x180054a76  jb      loc_180054998
0x180054a7c  mov     r15, [rbp+190h+var_210]
0x180054a80  lea     r8, aVoicemailMessa; "Voicemail message decoded now generatin"...
0x180054a87  mov     edx, 44Ch; unsigned int
0x180054a8c  lea     rcx, aGetvoicemailme; "GetVoicemailMessageXml"
0x180054a93  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180054a98  xor     r12d, r12d
0x180054a9b  mov     [rbp+190h+var_210], r12
0x180054a9f  lea     rax, [rbp+190h+var_210]
0x180054aa3  mov     [rsp+290h+ppv], rax; ppv
0x180054aa8  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180054aaf  xor     edx, edx; pUnkOuter
0x180054ab1  lea     r8d, [r12+17h]; dwClsContext
0x180054ab6  lea     rcx, CLSID_DOMDocument60; rclsid
0x180054abd  call    cs:__imp_CoCreateInstance
0x180054ac3  mov     edi, eax
0x180054ac5  test    eax, eax
0x180054ac7  jns     short loc_180054AEF
0x180054ac9  mov     rcx, [rbp+190h+var_210]
0x180054acd  test    rcx, rcx
0x180054ad0  jz      short loc_180054ADF
0x180054ad2  mov     rdx, [rcx]
0x180054ad5  mov     rax, [rdx+10h]
0x180054ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ade  nop
0x180054adf  lea     rcx, [rsp+290h+var_230]
0x180054ae4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054ae9  nop
0x180054aea  jmp     loc_180055393
0x180054aef  mov     rdi, [rbp+190h+var_210]
0x180054af3  mov     [rbp+190h+var_200], rdi
0x180054af7  lea     r9, [rbp+190h+var_208]; struct IXMLDOMNode **
0x180054afb  xor     r8d, r8d; unsigned __int16 *
0x180054afe  lea     rdx, aMessage; "Message"
0x180054b05  mov     rcx, rdi; struct IXMLDOMNode *
0x180054b08  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054b0d  mov     ebx, eax
0x180054b0f  test    eax, eax
0x180054b11  jns     short loc_180054B50
0x180054b13  lea     rcx, [rsp+290h+var_230]
0x180054b18  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054b1d  nop
0x180054b1e  mov     rcx, [rbp+190h+var_208]
0x180054b22  test    rcx, rcx
0x180054b25  jz      short loc_180054B34
0x180054b27  mov     rdx, [rcx]
0x180054b2a  mov     rax, [rdx+10h]
0x180054b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b33  nop
0x180054b34  test    rdi, rdi
0x180054b37  jz      short loc_180054B49
0x180054b39  mov     rax, [rdi]
0x180054b3c  mov     rcx, rdi
0x180054b3f  mov     rax, [rax+10h]
0x180054b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b48  nop
0x180054b49  mov     edi, ebx
0x180054b4b  jmp     loc_180055393
0x180054b50  xor     r9d, r9d; struct IXMLDOMNode **
0x180054b53  lea     r8, aVoicemail; "Voicemail"
0x180054b5a  lea     rdx, aMessagetype; "MessageType"
0x180054b61  mov     rbx, [rbp+190h+var_208]
0x180054b65  mov     rcx, rbx; struct IXMLDOMNode *
0x180054b68  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054b6d  mov     esi, eax
0x180054b6f  test    eax, eax
0x180054b71  jns     short loc_180054BAF
0x180054b73  lea     rcx, [rsp+290h+var_230]
0x180054b78  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054b7d  nop
0x180054b7e  test    rbx, rbx
0x180054b81  jz      short loc_180054B93
0x180054b83  mov     rcx, [rbx]
0x180054b86  mov     rax, [rcx+10h]
0x180054b8a  mov     rcx, rbx
0x180054b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b92  nop
0x180054b93  test    rdi, rdi
0x180054b96  jz      short loc_180054BA8
0x180054b98  mov     rax, [rdi]
0x180054b9b  mov     rcx, rdi
0x180054b9e  mov     rax, [rax+10h]
0x180054ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ba7  nop
0x180054ba8  mov     edi, esi
0x180054baa  jmp     loc_180055393
0x180054baf  xor     r9d, r9d; struct IXMLDOMNode **
0x180054bb2  mov     r8, [rbp+190h+var_1F8]; unsigned __int16 *
0x180054bb6  lea     rdx, aSmsdeviceid; "SmsDeviceId"
0x180054bbd  mov     rcx, rbx; struct IXMLDOMNode *
0x180054bc0  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054bc5  mov     esi, eax
0x180054bc7  test    eax, eax
0x180054bc9  jns     short loc_180054C02
0x180054bcb  lea     rcx, [rsp+290h+var_230]
0x180054bd0  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054bd5  nop
0x180054bd6  test    rbx, rbx
0x180054bd9  jz      short loc_180054BEB
0x180054bdb  mov     rcx, [rbx]
0x180054bde  mov     rax, [rcx+10h]
0x180054be2  mov     rcx, rbx
0x180054be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bea  nop
0x180054beb  test    rdi, rdi
0x180054bee  jz      short loc_180054C00
0x180054bf0  mov     rax, [rdi]
0x180054bf3  mov     rcx, rdi
0x180054bf6  mov     rax, [rax+10h]
0x180054bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bff  nop
0x180054c00  jmp     short loc_180054BA8
0x180054c02  xor     r9d, r9d; struct IXMLDOMNode **
0x180054c05  mov     r8, qword ptr [rbp+190h+SystemTime.wYear]; unsigned __int16 *
0x180054c0c  lea     rdx, aSimiccid; "SimIccId"
0x180054c13  mov     rcx, rbx; struct IXMLDOMNode *
0x180054c16  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054c1b  mov     esi, eax
0x180054c1d  test    eax, eax
0x180054c1f  jns     short loc_180054C5B
0x180054c21  lea     rcx, [rsp+290h+var_230]
0x180054c26  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054c2b  nop
0x180054c2c  test    rbx, rbx
0x180054c2f  jz      short loc_180054C41
0x180054c31  mov     rcx, [rbx]
0x180054c34  mov     rax, [rcx+10h]
0x180054c38  mov     rcx, rbx
0x180054c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c40  nop
0x180054c41  test    rdi, rdi
0x180054c44  jz      short loc_180054C56
0x180054c46  mov     rax, [rdi]
0x180054c49  mov     rcx, rdi
0x180054c4c  mov     rax, [rax+10h]
0x180054c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c55  nop
0x180054c56  jmp     loc_180054BA8
0x180054c5b  xor     r9d, r9d; struct IXMLDOMNode **
0x180054c5e  mov     r8, r13; unsigned __int16 *
0x180054c61  lea     rdx, aImsi; "Imsi"
0x180054c68  mov     rcx, rbx; struct IXMLDOMNode *
0x180054c6b  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054c70  mov     esi, eax
0x180054c72  test    eax, eax
0x180054c74  jns     short loc_180054CB0
0x180054c76  lea     rcx, [rsp+290h+var_230]
0x180054c7b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054c80  nop
0x180054c81  test    rbx, rbx
  ... truncated ...
```
