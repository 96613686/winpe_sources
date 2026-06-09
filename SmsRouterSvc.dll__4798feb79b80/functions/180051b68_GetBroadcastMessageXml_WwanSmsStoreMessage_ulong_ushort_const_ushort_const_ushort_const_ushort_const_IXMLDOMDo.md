# GetBroadcastMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)

- ea: `0x180051b68`
- end: `0x180052a6d`
- name: `?GetBroadcastMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z`
- size: `3845`
- prototype: `__int64 __fastcall(struct WwanSmsStoreMessage *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMDocument **)`
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
- `0x18002c8dc`
- `0x18002cafc`
- `0x18002f864`
- `0x18003246c`
- `0x180051628`
- `0x180051b68`
- `0x180053c98`
- `0x1800578c4`
- `0x180057ec0`
- `0x180058070`
- `0x18005868c`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800520f4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800522b4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18005238a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180052523`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180052661`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800520f4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x1800522b4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18005238a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180052523`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180052661`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180052972`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800529c9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180052a18`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180052972`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800529c9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180052a18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051e9a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051e9a`

## string_xrefs

- `0x180052691`: `TeleserviceId`
- `0x180052553`: `ProtocolId`
- `0x1800523ba`: `UpdateNumber`
- `0x180051e5e`: `Broadcast message decoded now generating xml for the message.`
- `0x180051e3b`: `GetBroadcastMessageXml`
- `0x180051e6a`: `GetBroadcastMessageXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall GetBroadcastMessageXml(
        struct WwanSmsStoreMessage *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct IXMLDOMDocument **a7)
{
  unsigned int v9; // r12d
  int v10; // r8d
  int v11; // eax
  HRESULT Instance; // edi
  int v13; // esi
  unsigned int v14; // r14d
  __int64 v15; // r13
  unsigned int v16; // ebx
  unsigned __int16 *v17; // rsi
  __int64 v18; // rdx
  char v19; // al
  int appended; // eax
  int v21; // r8d
  struct IXMLDOMNode *v22; // rbx
  unsigned int v23; // esi
  struct IXMLDOMNode *v24; // rdi
  int v25; // ebx
  struct IXMLDOMNode *v26; // rbx
  int v27; // r12d
  const unsigned __int16 *v28; // r8
  int v29; // esi
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // r8
  char v33; // al
  const unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // r8
  const unsigned __int16 *v36; // r8
  const unsigned __int16 *v37; // r8
  const unsigned __int16 *v38; // r8
  const unsigned __int16 *v39; // r8
  const unsigned __int16 *v40; // r8
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  struct IXMLDOMNode *ppv; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v48; // [rsp+98h] [rbp-68h]
  struct IXMLDOMNode *v49; // [rsp+A0h] [rbp-60h] BYREF
  struct IXMLDOMNode *v50; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v51; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v52; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v53; // [rsp+C0h] [rbp-40h]
  SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-30h] BYREF
  struct IXMLDOMDocument **v55; // [rsp+E0h] [rbp-20h]
  _BYTE v56[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v57[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v58[128]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v59[104]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int16 *v60[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v61; // [rsp+200h] [rbp+100h]
  unsigned __int16 *v62[2]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v63; // [rsp+220h] [rbp+120h]
  unsigned __int64 v64; // [rsp+228h] [rbp+128h]
  unsigned __int16 *Src[2]; // [rsp+230h] [rbp+130h] BYREF
  __m128i si128; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v67[2]; // [rsp+250h] [rbp+150h] BYREF
  __m128i v68; // [rsp+260h] [rbp+160h]
  struct _SYSTEMTIME lpSystemTime; // [rsp+270h] [rbp+170h] BYREF

  v51 = a4;
  v52 = a3;
  v48 = a2;
  *(_QWORD *)&SystemTime.wYear = a5;
  v53 = a6;
  v55 = a7;
  v9 = 0;
  lpSystemTime = 0;
  *(_OWORD *)Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  *(_OWORD *)v67 = 0;
  v68 = si128;
  LOWORD(v67[0]) = 0;
  *(_OWORD *)v62 = 0;
  v63 = 0;
  v64 = 7;
  LOWORD(v62[0]) = 0;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v56);
  LODWORD(v46) = 0;
  LODWORD(v42) = 0;
  v50 = 0;
  v49 = 0;
  v45 = 1;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  if ( !a2 || !a1 )
  {
    std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v59);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v59);
    std::wstring::~wstring((char **)v62);
    std::wstring::~wstring((char **)v67);
    std::wstring::~wstring((char **)Src);
    return 2147942487LL;
  }
  if ( *((_BYTE *)a1 + 4) != 1 )
  {
    Instance = -2147467263;
LABEL_169:
    std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
    goto LABEL_170;
  }
  v11 = CSmsEncodingHelper::DecodeBroadcastCdma(
          (int)a1 + 5,
          *(_DWORD *)a1,
          v10,
          (int)v67,
          (__int64)&v46,
          (__int64)&v42,
          (__int64)&v45,
          &lpSystemTime,
          (__int64)v62,
          (__int64)&ppv,
          (__int64)&v45 + 4);
  Instance = v11;
  switch ( (_DWORD)v42 )
  {
    case 0x1000:
      v13 = 4370;
      v14 = 1;
      break;
    case 0x1001:
      v13 = 4371;
      v14 = 2;
      break;
    case 0x1002:
      v13 = 4373;
      v14 = 3;
      break;
    case 0x1003:
      v13 = 4379;
      v14 = 4;
      break;
    case 0x1004:
      v13 = 4380;
      v14 = 5;
      break;
    default:
      v13 = 0;
      v14 = 0;
      break;
  }
  LODWORD(v42) = v13;
  if ( v11 < 0 )
    goto LABEL_169;
  v15 = 0;
  v16 = v48;
  v17 = v51;
  do
  {
    v18 = 520 * v15;
    v19 = *((_BYTE *)a1 + 520 * v15 + 4);
    switch ( v19 )
    {
      case 0:
        appended = CSmsEncodingHelper::AppendMessageContentsGsm(
                     (char *)a1 + v18 + 5,
                     *(unsigned int *)((char *)a1 + v18),
                     v17,
                     Src,
                     v43);
        goto LABEL_23;
      case 1:
        appended = CSmsEncodingHelper::AppendMessageContentsCdma(
                     (int)v18 + (int)a1 + 5,
                     *(_DWORD *)((char *)a1 + v18),
                     (_DWORD)v17,
                     (unsigned int)Src,
                     (__int64)v43);
        goto LABEL_23;
      case 2:
        GetSmsDataEncodingType(*(unsigned int *)((char *)a1 + 85));
        appended = CSmsEncodingHelper::AppendMessageContentsCdmaText((LPCCH)a1 + 96, v21, v17, 0, Src, (__int64)v43);
LABEL_23:
        if ( appended >= 0 )
          goto LABEL_27;
        goto LABEL_26;
    }
    appended = -2147467263;
LABEL_26:
    LogSmsRouterInfo(
      "GetBroadcastMessageXml",
      0x554u,
      "Ignoring Failure (0x%08X) to decode the text data of the broadcast message partindex %d, totalparts %d.",
      appended,
      v9,
      v16);
LABEL_27:
    ++v9;
    ++v15;
  }
  while ( v9 < v16 );
  v22 = v50;
  v23 = v42;
  LogSmsRouterInfo("GetBroadcastMessageXml", 0x55Du, "Broadcast message decoded now generating xml for the message.");
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
    std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
    if ( v22 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v22->lpVtbl->Release)(v22);
    goto LABEL_170;
  }
  v24 = ppv;
  v50 = ppv;
  v25 = Windows::Sms::Common::CSmsUtil::AddElement(ppv, L"Message", 0, &v49);
  if ( v25 >= 0 )
  {
    v26 = v49;
    v27 = Windows::Sms::Common::CSmsUtil::AddElement(v49, L"MessageType", L"Broadcast", 0);
    if ( v27 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
      if ( v26 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
LABEL_45:
      Instance = v27;
      goto LABEL_170;
    }
    v27 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"SmsDeviceId", v52, 0);
    if ( v27 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
      if ( v26 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
      goto LABEL_45;
    }
    v27 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"SimIccId", v53, 0);
    if ( v27 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
      if ( v26 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
      goto LABEL_45;
    }
    v27 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"Imsi", v51, 0);
    if ( v27 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
      if ( v26 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
      goto LABEL_45;
    }
    *(_OWORD *)v60 = 0;
    v61 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)v60, &LocaleName, 0);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
      v56,
      v60);
    std::wstring::~wstring((char **)v60);
    std::basic_ostream<unsigned short>::operator<<(v57, v23);
    std::basic_stringbuf<unsigned short>::str(v58, v60);
    v28 = (const unsigned __int16 *)v60;
    if ( *((_QWORD *)&v61 + 1) > 7u )
      v28 = v60[0];
    v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"BroadcastChannel", v28, 0);
    std::wstring::~wstring((char **)v60);
    if ( v29 >= 0 )
    {
      *(_OWORD *)v60 = 0;
      v61 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)v60, &LocaleName, 0);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
        v56,
        v60);
      std::wstring::~wstring((char **)v60);
      GetBroadcastTypeString(v14, v56);
      std::basic_stringbuf<unsigned short>::str(v58, v60);
      v30 = (const unsigned __int16 *)v60;
      if ( *((_QWORD *)&v61 + 1) > 7u )
        v30 = v60[0];
      v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"BroadcastType", v30, 0);
      std::wstring::~wstring((char **)v60);
      if ( v29 >= 0 )
      {
        *(_OWORD *)v60 = 0;
        v61 = 0;
        std::wstring::_Construct<1,unsigned short const *>((char **)v60, &LocaleName, 0);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
          v56,
          v60);
        std::wstring::~wstring((char **)v60);
        std::basic_ostream<unsigned short>::operator<<(v57, HIDWORD(v45));
        std::basic_stringbuf<unsigned short>::str(v58, v60);
        v31 = (const unsigned __int16 *)v60;
        if ( *((_QWORD *)&v61 + 1) > 7u )
          v31 = v60[0];
        v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"MessageCode", v31, 0);
        std::wstring::~wstring((char **)v60);
        if ( v29 >= 0 )
        {
          *(_OWORD *)v60 = 0;
          v61 = 0;
          std::wstring::_Construct<1,unsigned short const *>((char **)v60, &LocaleName, 0);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
            v56,
            v60);
          std::wstring::~wstring((char **)v60);
          std::basic_ostream<unsigned short>::operator<<(v57, 0);
          std::basic_stringbuf<unsigned short>::str(v58, v60);
          v32 = (const unsigned __int16 *)v60;
          if ( *((_QWORD *)&v61 + 1) > 7u )
            v32 = v60[0];
          v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"UpdateNumber", v32, 0);
          std::wstring::~wstring((char **)v60);
          if ( v29 >= 0 )
          {
            if ( *(_QWORD *)&SystemTime.wYear
              && (v29 = Windows::Sms::Common::CSmsUtil::AddElement(
                          v26,
                          L"Receiver",
                          *(const unsigned __int16 **)&SystemTime.wYear,
                          0),
                  v29 < 0) )
            {
              std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
              if ( v26 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
              if ( v24 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
            }
            else
            {
              v33 = *((_BYTE *)a1 + 4);
              if ( v33 )
              {
                if ( (unsigned __int8)(v33 - 1) <= 1u )
                {
                  v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"CellularClass", L"Cdma", 0);
                  if ( v29 < 0 )
                  {
                    std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                    if ( v26 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                    if ( v24 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
                    goto LABEL_71;
                  }
                  *(_OWORD *)v60 = 0;
                  v61 = 0;
                  std::wstring::_Construct<1,unsigned short const *>((char **)v60, &LocaleName, 0);
                  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                    v56,
                    v60);
                  std::wstring::~wstring((char **)v60);
                  std::basic_ostream<unsigned short>::operator<<(v57, (unsigned int)v46);
                  std::basic_stringbuf<unsigned short>::str(v58, v60);
                  v35 = (const unsigned __int16 *)v60;
                  if ( *((_QWORD *)&v61 + 1) > 7u )
                    v35 = v60[0];
                  v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"TeleserviceId", v35, 0);
                  std::wstring::~wstring((char **)v60);
                  if ( v29 < 0 )
                  {
                    std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                    if ( v26 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                    if ( v24 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
                    goto LABEL_71;
                  }
                  if ( v63 )
                  {
                    v36 = (const unsigned __int16 *)v62;
                    if ( v64 > 7 )
                      v36 = v62[0];
                    Windows::Sms::Common::CSmsUtil::AddElement(v26, L"CallbackNumber", v36, 0);
                  }
                }
              }
              else
              {
                v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"CellularClass", L"Gsm", 0);
                if ( v29 < 0 )
                {
                  std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                  if ( v26 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                  if ( v24 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
                  goto LABEL_71;
                }
                *(_OWORD *)v60 = 0;
                v61 = 0;
                std::wstring::_Construct<1,unsigned short const *>((char **)v60, &LocaleName, 0);
                std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                  v56,
                  v60);
                std::wstring::~wstring((char **)v60);
                std::basic_ostream<unsigned short>::operator<<(v57, 0);
                std::basic_stringbuf<unsigned short>::str(v58, v60);
                v34 = (const unsigned __int16 *)v60;
                if ( *((_QWORD *)&v61 + 1) > 7u )
                  v34 = v60[0];
                v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"ProtocolId", v34, 0);
                std::wstring::~wstring((char **)v60);
                if ( v29 < 0 )
                {
                  std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                  if ( v26 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                  if ( v24 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
                  goto LABEL_71;
                }
              }
              v37 = (const unsigned __int16 *)Src;
              if ( si128.m128i_i64[1] > 7uLL )
                v37 = Src[0];
              if ( (int)Windows::Sms::Common::CSmsUtil::AddElement(v26, L"Text", v37, 0) < 0 )
                Windows::Sms::Common::CSmsUtil::DeleteElement(v26, L"Text");
              v38 = (const unsigned __int16 *)v67;
              if ( v68.m128i_i64[1] > 7uLL )
                v38 = v67[0];
              v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"Sender", v38, 0);
              if ( v29 >= 0 )
              {
                SystemTime = lpSystemTime;
                GetTimeString(&SystemTime);
                std::basic_stringbuf<unsigned short>::str(v58, v60);
                v39 = (const unsigned __int16 *)v60;
                if ( *((_QWORD *)&v61 + 1) > 7u )
                  v39 = v60[0];
                v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"ReceiveTime", v39, 0);
                std::wstring::~wstring((char **)v60);
                if ( v29 >= 0 )
                {
                  *(_OWORD *)v60 = 0;
                  v61 = 0;
                  std::wstring::_Construct<1,unsigned short const *>((char **)v60, &LocaleName, 0);
                  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                    v56,
                    v60);
                  std::wstring::~wstring((char **)v60);
                  GetEncodingString((unsigned int)v45, v56);
                  std::basic_stringbuf<unsigned short>::str(v58, v60);
                  v40 = (const unsigned __int16 *)v60;
                  if ( *((_QWORD *)&v61 + 1) > 7u )
                    v40 = v60[0];
                  v29 = Windows::Sms::Common::CSmsUtil::AddElement(v26, L"Encoding", v40, 0);
                  std::wstring::~wstring((char **)v60);
                  if ( v29 >= 0 )
                  {
                    *v55 = (struct IXMLDOMDocument *)v24;
                    v50 = 0;
                    std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                    if ( v26 )
                      ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v59);
                    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v59);
                    std::wstring::~wstring((char **)v62);
                    std::wstring::~wstring((char **)v67);
                    std::wstring::~wstring((char **)Src);
                    return (unsigned int)v29;
                  }
                  std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                  if ( v26 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                  if ( v24 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
                }
                else
                {
                  std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                  if ( v26 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                  if ( v24 )
                    ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
                }
              }
              else
              {
                std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
                if ( v26 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
                if ( v24 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
              }
            }
          }
          else
          {
            std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
            if ( v26 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
            if ( v24 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
          }
        }
        else
        {
          std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
          if ( v26 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
          if ( v24 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
        }
      }
      else
      {
        std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
        if ( v26 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
        if ( v24 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
      }
    }
    else
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
      if ( v26 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
    }
LABEL_71:
    Instance = v29;
    goto LABEL_170;
  }
  std::vector<unsigned char>::~vector<unsigned char>((char **)v43);
  if ( v49 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v49->lpVtbl->Release)(v49);
  if ( v24 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
  Instance = v25;
LABEL_170:
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v59);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v59);
  std::wstring::~wstring((char **)v62);
  std::wstring::~wstring((char **)v67);
  std::wstring::~wstring((char **)Src);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180051b68  push    rbp
0x180051b6a  push    rbx
0x180051b6b  push    rsi
0x180051b6c  push    rdi
0x180051b6d  push    r12
0x180051b6f  push    r13
0x180051b71  push    r14
0x180051b73  push    r15
0x180051b75  lea     rbp, [rsp-198h]
0x180051b7d  sub     rsp, 298h
0x180051b84  mov     rax, cs:__security_cookie
0x180051b8b  xor     rax, rsp
0x180051b8e  mov     [rbp+1D0h+var_50], rax
0x180051b95  mov     [rbp+1D0h+var_220], r9
0x180051b99  mov     [rbp+1D0h+var_218], r8
0x180051b9d  mov     r13d, edx
0x180051ba0  mov     [rbp+1D0h+var_238], edx
0x180051ba3  mov     r15, rcx
0x180051ba6  mov     rax, [rbp+1D0h+arg_20]
0x180051bad  mov     qword ptr [rbp+1D0h+SystemTime.wYear], rax
0x180051bb1  mov     rax, [rbp+1D0h+arg_28]
0x180051bb8  mov     [rbp+1D0h+var_210], rax
0x180051bbc  mov     rax, [rbp+1D0h+arg_30]
0x180051bc3  mov     [rbp+1D0h+var_1F0], rax
0x180051bc7  xor     r12d, r12d
0x180051bca  xorps   xmm0, xmm0
0x180051bcd  movups  xmmword ptr [rbp+1D0h+var_60.wYear], xmm0
0x180051bd4  xorps   xmm1, xmm1
0x180051bd7  movups  xmmword ptr [rbp+1D0h+Src], xmm1
0x180051bde  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x180051be6  movdqu  [rbp+1D0h+var_90], xmm2
0x180051bee  mov     word ptr [rbp+1D0h+Src], r12w
0x180051bf6  movups  xmmword ptr [rbp+1D0h+var_80], xmm0
0x180051bfd  movdqu  [rbp+1D0h+var_70], xmm2
0x180051c05  mov     word ptr [rbp+1D0h+var_80], r12w
0x180051c0d  movups  xmmword ptr [rbp+1D0h+var_C0], xmm0
0x180051c14  mov     [rbp+1D0h+var_B0], r12
0x180051c1b  mov     [rbp+1D0h+var_A8], 7
0x180051c26  mov     word ptr [rbp+1D0h+var_C0], r12w
0x180051c2e  lea     rcx, [rbp+1D0h+var_1E0]
0x180051c32  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180051c37  nop
0x180051c38  mov     dword ptr [rbp+1D0h+var_248], r12d
0x180051c3c  mov     dword ptr [rsp+2D0h+var_270], r12d
0x180051c41  mov     dword ptr [rbp+1D0h+var_250+4], r12d
0x180051c45  mov     ebx, r12d
0x180051c48  mov     [rbp+1D0h+var_228], rbx
0x180051c4c  mov     [rbp+1D0h+var_230], r12
0x180051c50  mov     dword ptr [rbp+1D0h+var_250], 1
0x180051c57  xorps   xmm0, xmm0
0x180051c5a  movdqu  xmmword ptr [rsp+2D0h+var_268], xmm0
0x180051c60  mov     [rsp+2D0h+var_258], r12
0x180051c65  test    r13d, r13d
0x180051c68  jz      loc_1800529FA
0x180051c6e  test    r15, r15
0x180051c71  jz      loc_1800529FA
0x180051c77  mov     al, [r15+4]
0x180051c7b  test    al, al
0x180051c7d  jz      loc_1800529A6
0x180051c83  cmp     al, 1
0x180051c85  jnz     loc_1800529A6
0x180051c8b  lea     rcx, [r15+5]; int
0x180051c8f  lea     rax, [rbp+1D0h+var_250+4]
0x180051c93  mov     [rsp+2D0h+var_280], rax; __int64
0x180051c98  lea     rax, [rbp+1D0h+var_240]
0x180051c9c  mov     [rsp+2D0h+var_288], rax; __int64
0x180051ca1  lea     rax, [rbp+1D0h+var_C0]
0x180051ca8  mov     [rsp+2D0h+var_290], rax; __int64
0x180051cad  lea     rax, [rbp+1D0h+var_60]
0x180051cb4  mov     [rsp+2D0h+lpSystemTime], rax; lpSystemTime
0x180051cb9  lea     rax, [rbp+1D0h+var_250]
0x180051cbd  mov     [rsp+2D0h+var_2A0], rax; __int64
0x180051cc2  lea     rax, [rsp+2D0h+var_270]
0x180051cc7  mov     [rsp+2D0h+var_2A8], rax; __int64
0x180051ccc  lea     rax, [rbp+1D0h+var_248]
0x180051cd0  mov     [rsp+2D0h+ppv], rax; __int64
0x180051cd5  lea     r9, [rbp+1D0h+var_80]; int
0x180051cdc  mov     edx, [r15]; int
0x180051cdf  call    ?DecodeBroadcastCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK3AEAW4SMS_DATA_ENCODING@@AEAU_SYSTEMTIME@@233@Z; CSmsEncodingHelper::DecodeBroadcastCdma(uchar const *,ulong,ushort const *,std::wstring &,ulong &,ulong &,SMS_DATA_ENCODING &,_SYSTEMTIME &,std::wstring &,ulong &,ulong &)
0x180051ce4  mov     edi, eax
0x180051ce6  mov     ecx, dword ptr [rsp+2D0h+var_270]
0x180051cea  sub     ecx, 1000h
0x180051cf0  jz      short loc_180051D42
0x180051cf2  sub     ecx, 1
0x180051cf5  jz      short loc_180051D35
0x180051cf7  sub     ecx, 1
0x180051cfa  jz      short loc_180051D28
0x180051cfc  sub     ecx, 1
0x180051cff  jz      short loc_180051D1B
0x180051d01  cmp     ecx, 1
0x180051d04  jz      short loc_180051D0E
0x180051d06  mov     esi, r12d
0x180051d09  mov     r14d, r12d
0x180051d0c  jmp     short loc_180051D4D
0x180051d0e  mov     esi, 111Ch
0x180051d13  mov     r14d, 5
0x180051d19  jmp     short loc_180051D4D
0x180051d1b  mov     esi, 111Bh
0x180051d20  mov     r14d, 4
0x180051d26  jmp     short loc_180051D4D
0x180051d28  mov     esi, 1115h
0x180051d2d  mov     r14d, 3
0x180051d33  jmp     short loc_180051D4D
0x180051d35  mov     esi, 1113h
0x180051d3a  mov     r14d, 2
0x180051d40  jmp     short loc_180051D4D
0x180051d42  mov     esi, 1112h
0x180051d47  mov     r14d, 1
0x180051d4d  mov     dword ptr [rsp+2D0h+var_270], esi
0x180051d51  test    eax, eax
0x180051d53  js      loc_1800529AB
0x180051d59  test    r13d, r13d
0x180051d5c  jz      loc_180051E5E
0x180051d62  xor     r13d, r13d
0x180051d65  mov     edi, 80004001h
0x180051d6a  mov     ebx, [rbp+1D0h+var_238]
0x180051d6d  mov     rsi, [rbp+1D0h+var_220]
0x180051d71  imul    rdx, r13, 208h
0x180051d78  mov     al, [rdx+r15+4]
0x180051d7d  test    al, al
0x180051d7f  jnz     short loc_180051DA7
0x180051d81  lea     rcx, [r15+5]
0x180051d85  add     rcx, rdx
0x180051d88  lea     rax, [rsp+2D0h+var_268]
0x180051d8d  mov     [rsp+2D0h+ppv], rax
0x180051d92  lea     r9, [rbp+1D0h+Src]
0x180051d99  mov     r8, rsi
0x180051d9c  mov     edx, [rdx+r15]
0x180051da0  call    ?AppendMessageContentsGsm@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsGsm(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x180051da5  jmp     short loc_180051E1B
0x180051da7  cmp     al, 1
0x180051da9  jnz     short loc_180051DD1
0x180051dab  lea     rcx, [r15+5]
0x180051daf  add     rcx, rdx
0x180051db2  lea     rax, [rsp+2D0h+var_268]
0x180051db7  mov     [rsp+2D0h+ppv], rax
0x180051dbc  lea     r9, [rbp+1D0h+Src]
0x180051dc3  mov     r8, rsi
0x180051dc6  mov     edx, [rdx+r15]
0x180051dca  call    ?AppendMessageContentsCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsCdma(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x180051dcf  jmp     short loc_180051E1B
0x180051dd1  cmp     al, 2
0x180051dd3  jnz     short loc_180051E21
0x180051dd5  movzx   r8d, byte ptr [r15+5Fh]
0x180051dda  movzx   r9d, word ptr [r15+5Dh]
0x180051ddf  mov     ecx, [r15+55h]
0x180051de3  call    ?GetSmsDataEncodingType@@YA?AW4SMS_DATA_ENCODING@@W4_WWAN_SMS_CDMA_ENCODING@@@Z; GetSmsDataEncodingType(_WWAN_SMS_CDMA_ENCODING)
0x180051de8  mov     edx, eax
0x180051dea  lea     rcx, [r15+60h]; lpMultiByteStr
0x180051dee  lea     rax, [rsp+2D0h+var_268]
0x180051df3  mov     [rsp+2D0h+var_290], rax; __int64
0x180051df8  lea     rax, [rbp+1D0h+Src]
0x180051dff  mov     [rsp+2D0h+lpSystemTime], rax; Src
0x180051e04  mov     dword ptr [rsp+2D0h+var_2A0], 0; int
0x180051e0c  mov     [rsp+2D0h+var_2A8], rsi; unsigned __int16 *
0x180051e11  mov     dword ptr [rsp+2D0h+ppv], r8d; int
0x180051e16  call    ?AppendMessageContentsCdmaText@CSmsEncodingHelper@@SAJPEBEW4SMS_DATA_ENCODING@@KKKPEBGKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; CSmsEncodingHelper::AppendMessageContentsCdmaText(uchar const *,SMS_DATA_ENCODING,ulong,ulong,ulong,ushort const *,ulong,std::wstring &,std::vector<uchar> &)
0x180051e1b  test    eax, eax
0x180051e1d  jns     short loc_180051E47
0x180051e1f  jmp     short loc_180051E23
0x180051e21  mov     eax, edi
0x180051e23  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x180051e27  mov     dword ptr [rsp+2D0h+ppv], r12d
0x180051e2c  mov     r9d, eax
0x180051e2f  lea     r8, aIgnoringFailur; "Ignoring Failure (0x%08X) to decode the"...
0x180051e36  mov     edx, 554h; unsigned int
0x180051e3b  lea     rcx, aGetbroadcastme; "GetBroadcastMessageXml"
0x180051e42  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180051e47  inc     r12d
0x180051e4a  inc     r13
0x180051e4d  cmp     r12d, ebx
0x180051e50  jb      loc_180051D71
0x180051e56  mov     rbx, [rbp+1D0h+var_228]
0x180051e5a  mov     esi, dword ptr [rsp+2D0h+var_270]
0x180051e5e  lea     r8, aBroadcastMessa; "Broadcast message decoded now generatin"...
0x180051e65  mov     edx, 55Dh; unsigned int
0x180051e6a  lea     rcx, aGetbroadcastme; "GetBroadcastMessageXml"
0x180051e71  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180051e76  xor     r13d, r13d
0x180051e79  mov     [rbp+1D0h+var_240], r13
0x180051e7d  lea     rax, [rbp+1D0h+var_240]
0x180051e81  mov     [rsp+2D0h+ppv], rax; ppv
0x180051e86  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180051e8d  xor     edx, edx; pUnkOuter
0x180051e8f  lea     r8d, [r13+17h]; dwClsContext
0x180051e93  lea     rcx, CLSID_DOMDocument60; rclsid
0x180051e9a  call    cs:__imp_CoCreateInstance
0x180051ea0  mov     edi, eax
0x180051ea2  test    eax, eax
0x180051ea4  jns     short loc_180051EE1
0x180051ea6  mov     rcx, [rbp+1D0h+var_240]
0x180051eaa  test    rcx, rcx
0x180051ead  jz      short loc_180051EBC
0x180051eaf  mov     rdx, [rcx]
0x180051eb2  mov     rax, [rdx+10h]
0x180051eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ebb  nop
0x180051ebc  lea     rcx, [rsp+2D0h+var_268]
0x180051ec1  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180051ec6  nop
0x180051ec7  test    rbx, rbx
0x180051eca  jz      short loc_180051EDC
0x180051ecc  mov     rax, [rbx]
0x180051ecf  mov     rcx, rbx
0x180051ed2  mov     rax, [rax+10h]
0x180051ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051edb  nop
0x180051edc  jmp     loc_1800529B6
0x180051ee1  mov     rdi, [rbp+1D0h+var_240]
0x180051ee5  mov     [rbp+1D0h+var_228], rdi
0x180051ee9  lea     r9, [rbp+1D0h+var_230]; struct IXMLDOMNode **
0x180051eed  xor     r8d, r8d; unsigned __int16 *
0x180051ef0  lea     rdx, aMessage; "Message"
0x180051ef7  mov     rcx, rdi; struct IXMLDOMNode *
0x180051efa  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180051eff  mov     ebx, eax
0x180051f01  test    eax, eax
0x180051f03  jns     short loc_180051F42
0x180051f05  lea     rcx, [rsp+2D0h+var_268]
0x180051f0a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180051f0f  nop
0x180051f10  mov     rcx, [rbp+1D0h+var_230]
0x180051f14  test    rcx, rcx
0x180051f17  jz      short loc_180051F26
0x180051f19  mov     rdx, [rcx]
0x180051f1c  mov     rax, [rdx+10h]
0x180051f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f25  nop
0x180051f26  test    rdi, rdi
0x180051f29  jz      short loc_180051F3B
0x180051f2b  mov     rax, [rdi]
0x180051f2e  mov     rcx, rdi
0x180051f31  mov     rax, [rax+10h]
0x180051f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f3a  nop
0x180051f3b  mov     edi, ebx
0x180051f3d  jmp     loc_1800529B6
0x180051f42  xor     r9d, r9d; struct IXMLDOMNode **
0x180051f45  lea     r8, aBroadcast; "Broadcast"
0x180051f4c  lea     rdx, aMessagetype; "MessageType"
0x180051f53  mov     rbx, [rbp+1D0h+var_230]
0x180051f57  mov     rcx, rbx; struct IXMLDOMNode *
0x180051f5a  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180051f5f  mov     r12d, eax
0x180051f62  test    eax, eax
0x180051f64  jns     short loc_180051FA3
0x180051f66  lea     rcx, [rsp+2D0h+var_268]
0x180051f6b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180051f70  nop
0x180051f71  test    rbx, rbx
0x180051f74  jz      short loc_180051F86
0x180051f76  mov     rcx, [rbx]
0x180051f79  mov     rax, [rcx+10h]
0x180051f7d  mov     rcx, rbx
0x180051f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f85  nop
0x180051f86  test    rdi, rdi
0x180051f89  jz      short loc_180051F9B
0x180051f8b  mov     rax, [rdi]
0x180051f8e  mov     rcx, rdi
0x180051f91  mov     rax, [rax+10h]
0x180051f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f9a  nop
0x180051f9b  mov     edi, r12d
0x180051f9e  jmp     loc_1800529B6
0x180051fa3  xor     r9d, r9d; struct IXMLDOMNode **
0x180051fa6  mov     r8, [rbp+1D0h+var_218]; unsigned __int16 *
0x180051faa  lea     rdx, aSmsdeviceid; "SmsDeviceId"
0x180051fb1  mov     rcx, rbx; struct IXMLDOMNode *
0x180051fb4  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180051fb9  mov     r12d, eax
0x180051fbc  test    eax, eax
0x180051fbe  jns     short loc_180051FF7
0x180051fc0  lea     rcx, [rsp+2D0h+var_268]
0x180051fc5  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180051fca  nop
0x180051fcb  test    rbx, rbx
0x180051fce  jz      short loc_180051FE0
0x180051fd0  mov     rcx, [rbx]
0x180051fd3  mov     rax, [rcx+10h]
0x180051fd7  mov     rcx, rbx
0x180051fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fdf  nop
0x180051fe0  test    rdi, rdi
0x180051fe3  jz      short loc_180051FF5
0x180051fe5  mov     rax, [rdi]
0x180051fe8  mov     rcx, rdi
0x180051feb  mov     rax, [rax+10h]
0x180051fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ff4  nop
0x180051ff5  jmp     short loc_180051F9B
0x180051ff7  xor     r9d, r9d; struct IXMLDOMNode **
0x180051ffa  mov     r8, [rbp+1D0h+var_210]; unsigned __int16 *
0x180051ffe  lea     rdx, aSimiccid; "SimIccId"
0x180052005  mov     rcx, rbx; struct IXMLDOMNode *
0x180052008  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18005200d  mov     r12d, eax
0x180052010  test    eax, eax
0x180052012  jns     short loc_18005204E
0x180052014  lea     rcx, [rsp+2D0h+var_268]
  ... truncated ...
```
