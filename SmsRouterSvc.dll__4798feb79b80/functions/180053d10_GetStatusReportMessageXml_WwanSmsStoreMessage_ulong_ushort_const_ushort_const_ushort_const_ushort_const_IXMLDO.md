# GetStatusReportMessageXml(WwanSmsStoreMessage *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)

- ea: `0x180053d10`
- end: `0x1800547cf`
- name: `?GetStatusReportMessageXml@@YAJPEAUWwanSmsStoreMessage@@KPEBG111PEAPEAUIXMLDOMDocument@@@Z`
- size: `2751`
- prototype: `int(struct WwanSmsStoreMessage *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `19`
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
- `0x1800288f4`
- `0x18002f864`
- `0x18003246c`
- `0x180051628`
- `0x180053c98`
- `0x180053d10`
- `0x1800578c4`
- `0x180057ec0`
- `0x180058070`
- `0x180059c8c`
- `0x18005a098`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054395`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054642`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054395`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x180054642`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18005470a`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18005474b`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180054787`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18005470a`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18005474b`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180054787`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053fbe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053fbe`

## string_xrefs

- `0x1800544b0`: `ServiceCenterTime`
- `0x180053f7f`: `Status message decoded now generating xml for the message.`
- `0x180053f5f`: `GetStatusReportMessageXml`
- `0x180053f8b`: `GetStatusReportMessageXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall GetStatusReportMessageXml(
        struct WwanSmsStoreMessage *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct IXMLDOMDocument **a7)
{
  unsigned int v10; // r14d
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
  int v24; // r14d
  char v25; // al
  int v26; // esi
  const unsigned __int16 *v27; // r8
  SYSTEMTIME *p_SystemTime; // r8
  SYSTEMTIME *v29; // r8
  SYSTEMTIME *v30; // r8
  SYSTEMTIME *v31; // r8
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h]
  struct IXMLDOMNode *ppv; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMNode *v37; // [rsp+78h] [rbp-88h] BYREF
  struct IXMLDOMNode *v38; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v39; // [rsp+88h] [rbp-78h]
  struct IXMLDOMDocument **v40; // [rsp+90h] [rbp-70h]
  _BYTE v41[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v42[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v43[128]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v44[104]; // [rsp+138h] [rbp+38h] BYREF
  SYSTEMTIME SystemTime; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v46; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 *v47[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  __m128i si128; // [rsp+1D0h] [rbp+D0h]
  _OWORD Src[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _SYSTEMTIME lpSystemTime; // [rsp+200h] [rbp+100h] BYREF
  SYSTEMTIME v51; // [rsp+210h] [rbp+110h] BYREF

  v39 = a3;
  ppv = (struct IXMLDOMNode *)a5;
  *(_QWORD *)&SystemTime.wYear = a6;
  v40 = a7;
  v10 = 0;
  v33 = 0;
  lpSystemTime = 0;
  v51 = 0;
  *(_OWORD *)v47 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v47[0]) = 0;
  Src[0] = 0;
  Src[1] = si128;
  LOWORD(Src[0]) = 0;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v41);
  v38 = 0;
  v37 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  if ( !a2 || !a1 )
  {
    std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v44);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v44);
    std::wstring::~wstring((char **)Src);
    std::wstring::~wstring((char **)v47);
    return 2147942487LL;
  }
  v12 = *((_BYTE *)a1 + 4);
  if ( v12 )
  {
    if ( v12 != 1 )
    {
      Instance = -2147467263;
      goto LABEL_119;
    }
    v13 = CSmsEncodingHelper::DecodeStatusReportCdma(
            (int)a1 + 5,
            *(_DWORD *)a1,
            v11,
            (int)&v33 + 4,
            (__int64)v47,
            &lpSystemTime,
            (__int64)&v33);
  }
  else
  {
    v13 = CSmsEncodingHelper::DecodeStatusReportGsm(
            (char *)a1 + 5,
            *(unsigned int *)a1,
            a4,
            (char *)&v33 + 4,
            v47,
            &lpSystemTime,
            &v51,
            &v33);
  }
  Instance = v13;
  if ( v13 < 0 )
    goto LABEL_119;
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
                     v34);
        goto LABEL_15;
      case 1:
        appended = CSmsEncodingHelper::AppendMessageContentsCdma(
                     (int)v16 + (int)a1 + 5,
                     *(_DWORD *)((char *)a1 + v16),
                     (_DWORD)a4,
                     (unsigned int)Src,
                     (__int64)v34);
        goto LABEL_15;
      case 2:
        GetSmsDataEncodingType(*(unsigned int *)((char *)a1 + 85));
        appended = CSmsEncodingHelper::AppendMessageContentsCdmaText((LPCCH)a1 + 96, v19, a4, 0, Src, (__int64)v34);
LABEL_15:
        if ( appended >= 0 )
          goto LABEL_19;
        goto LABEL_18;
    }
    appended = -2147467263;
LABEL_18:
    LogSmsRouterInfo(
      "GetStatusReportMessageXml",
      0x37Bu,
      "Ignoring Failure (0x%08X) to decode the text data of the status message partindex %d, totalparts %d.",
      appended,
      v10,
      a2);
LABEL_19:
    ++v10;
    ++v15;
  }
  while ( v10 < a2 );
  v20 = ppv;
  LogSmsRouterInfo("GetStatusReportMessageXml", 0x384u, "Status message decoded now generating xml for the message.");
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
    v38 = ppv;
    v22 = Windows::Sms::Common::CSmsUtil::AddElement(ppv, L"Message", 0, &v37);
    if ( v22 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
      if ( v37 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v37->lpVtbl->Release)(v37);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      Instance = v22;
      goto LABEL_120;
    }
    v23 = v37;
    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v37, L"MessageType", L"Status", 0);
    if ( v24 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
      if ( v23 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
LABEL_35:
      Instance = v24;
      goto LABEL_120;
    }
    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"SmsDeviceId", v39, 0);
    if ( v24 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
      if ( v23 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      goto LABEL_35;
    }
    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"SimIccId", *(const unsigned __int16 **)&SystemTime.wYear, 0);
    if ( v24 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
      if ( v23 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      goto LABEL_35;
    }
    v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Imsi", a4, 0);
    if ( v24 < 0 )
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
      if ( v23 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      goto LABEL_35;
    }
    if ( v20 )
    {
      v24 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Receiver", (const unsigned __int16 *)v20, 0);
      if ( v24 < 0 )
      {
        std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
        if ( v23 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
        goto LABEL_35;
      }
    }
    v25 = *((_BYTE *)a1 + 4);
    if ( v25 )
    {
      if ( (unsigned __int8)(v25 - 1) <= 1u )
      {
        v26 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"CellularClass", L"Cdma", 0);
        if ( v26 < 0 )
        {
          std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
          if ( v23 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
          if ( v21 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          goto LABEL_67;
        }
      }
    }
    else
    {
      v26 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"CellularClass", L"Gsm", 0);
      if ( v26 < 0 )
      {
        std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
        if ( v23 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
        goto LABEL_67;
      }
    }
    v27 = (const unsigned __int16 *)v47;
    if ( si128.m128i_i64[1] > 7uLL )
      v27 = v47[0];
    v26 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"Sender", v27, 0);
    if ( v26 >= 0 )
    {
      SystemTime = 0;
      v46 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
        v41,
        &SystemTime);
      std::wstring::~wstring((char **)&SystemTime);
      std::basic_ostream<unsigned short>::operator<<(v42, HIDWORD(v33));
      std::basic_stringbuf<unsigned short>::str(v43, &SystemTime);
      p_SystemTime = &SystemTime;
      if ( *((_QWORD *)&v46 + 1) > 7u )
        p_SystemTime = *(SYSTEMTIME **)&SystemTime.wYear;
      v26 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"MessageReference", &p_SystemTime->wYear, 0);
      std::wstring::~wstring((char **)&SystemTime);
      if ( v26 >= 0 )
      {
        SystemTime = 0;
        v46 = 0;
        std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
          v41,
          &SystemTime);
        std::wstring::~wstring((char **)&SystemTime);
        SystemTime = lpSystemTime;
        GetTimeString(&SystemTime);
        std::basic_stringbuf<unsigned short>::str(v43, &SystemTime);
        v29 = &SystemTime;
        if ( *((_QWORD *)&v46 + 1) > 7u )
          v29 = *(SYSTEMTIME **)&SystemTime.wYear;
        v26 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"ServiceCenterTime", &v29->wYear, 0);
        std::wstring::~wstring((char **)&SystemTime);
        if ( v26 >= 0 )
        {
          SystemTime = 0;
          v46 = 0;
          std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
            v41,
            &SystemTime);
          std::wstring::~wstring((char **)&SystemTime);
          SystemTime = v51;
          GetTimeString(&SystemTime);
          std::basic_stringbuf<unsigned short>::str(v43, &SystemTime);
          v30 = &SystemTime;
          if ( *((_QWORD *)&v46 + 1) > 7u )
            v30 = *(SYSTEMTIME **)&SystemTime.wYear;
          v26 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"DischargeTime", &v30->wYear, 0);
          std::wstring::~wstring((char **)&SystemTime);
          if ( v26 >= 0 )
          {
            SystemTime = 0;
            v46 = 0;
            std::wstring::_Construct<1,unsigned short const *>((char **)&SystemTime, &LocaleName, 0);
            std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
              v41,
              &SystemTime);
            std::wstring::~wstring((char **)&SystemTime);
            std::basic_ostream<unsigned short>::operator<<(v42, (unsigned int)v33);
            std::basic_stringbuf<unsigned short>::str(v43, &SystemTime);
            v31 = &SystemTime;
            if ( *((_QWORD *)&v46 + 1) > 7u )
              v31 = *(SYSTEMTIME **)&SystemTime.wYear;
            v26 = Windows::Sms::Common::CSmsUtil::AddElement(v23, L"StatusCode", &v31->wYear, 0);
            std::wstring::~wstring((char **)&SystemTime);
            if ( v26 >= 0 )
            {
              *v40 = (struct IXMLDOMDocument *)v21;
              v38 = 0;
              std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
              if ( v23 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
              std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v44);
              std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v44);
              std::wstring::~wstring((char **)Src);
              std::wstring::~wstring((char **)v47);
              return (unsigned int)v26;
            }
            std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
            if ( v23 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
            if ( v21 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          }
          else
          {
            std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
            if ( v23 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
            if ( v21 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
          }
        }
        else
        {
          std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
          if ( v23 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
          if ( v21 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
        }
      }
      else
      {
        std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
        if ( v23 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
      }
    }
    else
    {
      std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
      if ( v23 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v23->lpVtbl->Release)(v23);
      if ( v21 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
    }
LABEL_67:
    Instance = v26;
    goto LABEL_120;
  }
  if ( ppv )
    ((void (__fastcall *)(struct IXMLDOMNode *))ppv->lpVtbl->Release)(ppv);
LABEL_119:
  std::vector<unsigned char>::~vector<unsigned char>((char **)v34);
LABEL_120:
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v44);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v44);
  std::wstring::~wstring((char **)Src);
  std::wstring::~wstring((char **)v47);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180053d10  push    rbp
0x180053d12  push    rbx
0x180053d13  push    rsi
0x180053d14  push    rdi
0x180053d15  push    r12
0x180053d17  push    r13
0x180053d19  push    r14
0x180053d1b  push    r15
0x180053d1d  lea     rbp, [rsp-138h]
0x180053d25  sub     rsp, 238h
0x180053d2c  mov     rax, cs:__security_cookie
0x180053d33  xor     rax, rsp
0x180053d36  mov     [rbp+170h+var_50], rax
0x180053d3d  mov     r12, r9
0x180053d40  mov     [rbp+170h+var_1E8], r8
0x180053d44  mov     r13d, edx
0x180053d47  mov     rsi, rcx
0x180053d4a  mov     r15, [rbp+170h+arg_20]
0x180053d51  mov     [rsp+270h+var_200], r15
0x180053d56  mov     rax, [rbp+170h+arg_28]
0x180053d5d  mov     qword ptr [rbp+170h+SystemTime.wYear], rax
0x180053d64  mov     rax, [rbp+170h+arg_30]
0x180053d6b  mov     [rbp+170h+var_1E0], rax
0x180053d6f  xor     r14d, r14d
0x180053d72  mov     dword ptr [rsp+270h+var_220], r14d
0x180053d77  mov     dword ptr [rsp+270h+var_220+4], r14d
0x180053d7c  xorps   xmm0, xmm0
0x180053d7f  movups  xmmword ptr [rbp+170h+var_70.wYear], xmm0
0x180053d86  xorps   xmm1, xmm1
0x180053d89  movups  [rbp+170h+var_60], xmm1
0x180053d90  movups  xmmword ptr [rbp+170h+var_B0], xmm0
0x180053d97  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180053d9f  movdqu  [rbp+170h+var_A0], xmm1
0x180053da7  mov     word ptr [rbp+170h+var_B0], r14w
0x180053daf  movups  [rbp+170h+var_90], xmm0
0x180053db6  movdqu  [rbp+170h+var_80], xmm1
0x180053dbe  mov     word ptr [rbp+170h+var_90], r14w
0x180053dc6  lea     rcx, [rbp+170h+var_1D0]
0x180053dca  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180053dcf  nop
0x180053dd0  mov     [rbp+170h+var_1F0], r14
0x180053dd4  mov     [rsp+270h+var_1F8], r14
0x180053dd9  xorps   xmm0, xmm0
0x180053ddc  movdqu  xmmword ptr [rsp+270h+var_218], xmm0
0x180053de2  mov     [rsp+270h+var_208], r14
0x180053de7  test    r13d, r13d
0x180053dea  jz      loc_18005476F
0x180053df0  test    rsi, rsi
0x180053df3  jz      loc_18005476F
0x180053df9  mov     al, [rsi+4]
0x180053dfc  test    al, al
0x180053dfe  jnz     short loc_180053E43
0x180053e00  lea     rcx, [rsi+5]
0x180053e04  lea     rax, [rsp+270h+var_220]
0x180053e09  mov     [rsp+270h+Src], rax
0x180053e0e  lea     rax, [rbp+170h+var_60]
0x180053e15  mov     [rsp+270h+var_240], rax
0x180053e1a  lea     rax, [rbp+170h+var_70]
0x180053e21  mov     [rsp+270h+lpSystemTime], rax
0x180053e26  lea     rax, [rbp+170h+var_B0]
0x180053e2d  mov     [rsp+270h+ppv], rax
0x180053e32  lea     r9, [rsp+270h+var_220+4]
0x180053e37  mov     r8, r12
0x180053e3a  mov     edx, [rsi]
0x180053e3c  call    ?DecodeStatusReportGsm@CSmsEncodingHelper@@SAJPEBEKPEBGAEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@42@Z; CSmsEncodingHelper::DecodeStatusReportGsm(uchar const *,ulong,ushort const *,ulong &,std::wstring &,_SYSTEMTIME &,_SYSTEMTIME &,ulong &)
0x180053e41  jmp     short loc_180053E7D
0x180053e43  cmp     al, 1
0x180053e45  jnz     loc_18005472E
0x180053e4b  lea     rcx, [rsi+5]; int
0x180053e4f  lea     rax, [rsp+270h+var_220]
0x180053e54  mov     [rsp+270h+var_240], rax; __int64
0x180053e59  lea     rax, [rbp+170h+var_70]
0x180053e60  mov     [rsp+270h+lpSystemTime], rax; lpSystemTime
0x180053e65  lea     rax, [rbp+170h+var_B0]
0x180053e6c  mov     [rsp+270h+ppv], rax; __int64
0x180053e71  lea     r9, [rsp+270h+var_220+4]; int
0x180053e76  mov     edx, [rsi]; int
0x180053e78  call    ?DecodeStatusReportCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SYSTEMTIME@@2@Z; CSmsEncodingHelper::DecodeStatusReportCdma(uchar const *,ulong,ushort const *,ulong &,std::wstring &,_SYSTEMTIME &,ulong &)
0x180053e7d  mov     edi, eax
0x180053e7f  test    eax, eax
0x180053e81  js      loc_180054733
0x180053e87  test    r13d, r13d
0x180053e8a  jz      loc_180053F7F
0x180053e90  xor     r15d, r15d
0x180053e93  mov     edi, 80004001h
0x180053e98  imul    rdx, r15, 208h
0x180053e9f  mov     al, [rdx+rsi+4]
0x180053ea3  test    al, al
0x180053ea5  jnz     short loc_180053ECC
0x180053ea7  lea     rcx, [rsi+5]
0x180053eab  add     rcx, rdx
0x180053eae  lea     rax, [rsp+270h+var_218]
0x180053eb3  mov     [rsp+270h+ppv], rax
0x180053eb8  lea     r9, [rbp+170h+var_90]
0x180053ebf  mov     r8, r12
0x180053ec2  mov     edx, [rdx+rsi]
0x180053ec5  call    ?AppendMessageContentsGsm@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsGsm(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x180053eca  jmp     short loc_180053F3E
0x180053ecc  cmp     al, 1
0x180053ece  jnz     short loc_180053EF5
0x180053ed0  lea     rcx, [rsi+5]
0x180053ed4  add     rcx, rdx
0x180053ed7  lea     rax, [rsp+270h+var_218]
0x180053edc  mov     [rsp+270h+ppv], rax
0x180053ee1  lea     r9, [rbp+170h+var_90]
0x180053ee8  mov     r8, r12
0x180053eeb  mov     edx, [rdx+rsi]
0x180053eee  call    ?AppendMessageContentsCdma@CSmsEncodingHelper@@SAJPEBEKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; CSmsEncodingHelper::AppendMessageContentsCdma(uchar const *,ulong,ushort const *,std::wstring &,std::vector<uchar> &)
0x180053ef3  jmp     short loc_180053F3E
0x180053ef5  cmp     al, 2
0x180053ef7  jnz     short loc_180053F44
0x180053ef9  movzx   r8d, byte ptr [rsi+5Fh]
0x180053efe  movzx   r9d, word ptr [rsi+5Dh]
0x180053f03  mov     ecx, [rsi+55h]
0x180053f06  call    ?GetSmsDataEncodingType@@YA?AW4SMS_DATA_ENCODING@@W4_WWAN_SMS_CDMA_ENCODING@@@Z; GetSmsDataEncodingType(_WWAN_SMS_CDMA_ENCODING)
0x180053f0b  mov     edx, eax
0x180053f0d  lea     rcx, [rsi+60h]; lpMultiByteStr
0x180053f11  lea     rax, [rsp+270h+var_218]
0x180053f16  mov     [rsp+270h+var_230], rax; __int64
0x180053f1b  lea     rax, [rbp+170h+var_90]
0x180053f22  mov     [rsp+270h+Src], rax; Src
0x180053f27  mov     dword ptr [rsp+270h+var_240], 0; int
0x180053f2f  mov     [rsp+270h+lpSystemTime], r12; unsigned __int16 *
0x180053f34  mov     dword ptr [rsp+270h+ppv], r8d; int
0x180053f39  call    ?AppendMessageContentsCdmaText@CSmsEncodingHelper@@SAJPEBEW4SMS_DATA_ENCODING@@KKKPEBGKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@4@@Z; CSmsEncodingHelper::AppendMessageContentsCdmaText(uchar const *,SMS_DATA_ENCODING,ulong,ulong,ulong,ushort const *,ulong,std::wstring &,std::vector<uchar> &)
0x180053f3e  test    eax, eax
0x180053f40  jns     short loc_180053F6B
0x180053f42  jmp     short loc_180053F46
0x180053f44  mov     eax, edi
0x180053f46  mov     dword ptr [rsp+270h+lpSystemTime], r13d
0x180053f4b  mov     dword ptr [rsp+270h+ppv], r14d
0x180053f50  mov     r9d, eax
0x180053f53  lea     r8, aIgnoringFailur_1; "Ignoring Failure (0x%08X) to decode the"...
0x180053f5a  mov     edx, 37Bh; unsigned int
0x180053f5f  lea     rcx, aGetstatusrepor; "GetStatusReportMessageXml"
0x180053f66  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180053f6b  inc     r14d
0x180053f6e  inc     r15
0x180053f71  cmp     r14d, r13d
0x180053f74  jb      loc_180053E98
0x180053f7a  mov     r15, [rsp+270h+var_200]
0x180053f7f  lea     r8, aStatusMessageD; "Status message decoded now generating x"...
0x180053f86  mov     edx, 384h; unsigned int
0x180053f8b  lea     rcx, aGetstatusrepor; "GetStatusReportMessageXml"
0x180053f92  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180053f97  mov     [rsp+270h+var_200], 0
0x180053fa0  lea     rax, [rsp+270h+var_200]
0x180053fa5  mov     [rsp+270h+ppv], rax; ppv
0x180053faa  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180053fb1  xor     edx, edx; pUnkOuter
0x180053fb3  lea     r8d, [rdx+17h]; dwClsContext
0x180053fb7  lea     rcx, CLSID_DOMDocument60; rclsid
0x180053fbe  call    cs:__imp_CoCreateInstance
0x180053fc4  mov     edi, eax
0x180053fc6  test    eax, eax
0x180053fc8  jns     short loc_180053FF1
0x180053fca  mov     rcx, [rsp+270h+var_200]
0x180053fcf  test    rcx, rcx
0x180053fd2  jz      short loc_180053FE1
0x180053fd4  mov     rdx, [rcx]
0x180053fd7  mov     rax, [rdx+10h]
0x180053fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fe0  nop
0x180053fe1  lea     rcx, [rsp+270h+var_218]
0x180053fe6  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180053feb  nop
0x180053fec  jmp     loc_18005473E
0x180053ff1  mov     rdi, [rsp+270h+var_200]
0x180053ff6  mov     [rbp+170h+var_1F0], rdi
0x180053ffa  lea     r9, [rsp+270h+var_1F8]; struct IXMLDOMNode **
0x180053fff  xor     r8d, r8d; unsigned __int16 *
0x180054002  lea     rdx, aMessage; "Message"
0x180054009  mov     rcx, rdi; struct IXMLDOMNode *
0x18005400c  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054011  mov     ebx, eax
0x180054013  test    eax, eax
0x180054015  jns     short loc_180054055
0x180054017  lea     rcx, [rsp+270h+var_218]
0x18005401c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054021  nop
0x180054022  mov     rcx, [rsp+270h+var_1F8]
0x180054027  test    rcx, rcx
0x18005402a  jz      short loc_180054039
0x18005402c  mov     rdx, [rcx]
0x18005402f  mov     rax, [rdx+10h]
0x180054033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054038  nop
0x180054039  test    rdi, rdi
0x18005403c  jz      short loc_18005404E
0x18005403e  mov     rax, [rdi]
0x180054041  mov     rcx, rdi
0x180054044  mov     rax, [rax+10h]
0x180054048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005404d  nop
0x18005404e  mov     edi, ebx
0x180054050  jmp     loc_18005473E
0x180054055  xor     r9d, r9d; struct IXMLDOMNode **
0x180054058  lea     r8, aStatus; "Status"
0x18005405f  lea     rdx, aMessagetype; "MessageType"
0x180054066  mov     rbx, [rsp+270h+var_1F8]
0x18005406b  mov     rcx, rbx; struct IXMLDOMNode *
0x18005406e  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054073  mov     r14d, eax
0x180054076  test    eax, eax
0x180054078  jns     short loc_1800540B7
0x18005407a  lea     rcx, [rsp+270h+var_218]
0x18005407f  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054084  nop
0x180054085  test    rbx, rbx
0x180054088  jz      short loc_18005409A
0x18005408a  mov     rcx, [rbx]
0x18005408d  mov     rax, [rcx+10h]
0x180054091  mov     rcx, rbx
0x180054094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054099  nop
0x18005409a  test    rdi, rdi
0x18005409d  jz      short loc_1800540AF
0x18005409f  mov     rax, [rdi]
0x1800540a2  mov     rcx, rdi
0x1800540a5  mov     rax, [rax+10h]
0x1800540a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540ae  nop
0x1800540af  mov     edi, r14d
0x1800540b2  jmp     loc_18005473E
0x1800540b7  xor     r9d, r9d; struct IXMLDOMNode **
0x1800540ba  mov     r8, [rbp+170h+var_1E8]; unsigned __int16 *
0x1800540be  lea     rdx, aSmsdeviceid; "SmsDeviceId"
0x1800540c5  mov     rcx, rbx; struct IXMLDOMNode *
0x1800540c8  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800540cd  mov     r14d, eax
0x1800540d0  test    eax, eax
0x1800540d2  jns     short loc_18005410B
0x1800540d4  lea     rcx, [rsp+270h+var_218]
0x1800540d9  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800540de  nop
0x1800540df  test    rbx, rbx
0x1800540e2  jz      short loc_1800540F4
0x1800540e4  mov     rcx, [rbx]
0x1800540e7  mov     rax, [rcx+10h]
0x1800540eb  mov     rcx, rbx
0x1800540ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540f3  nop
0x1800540f4  test    rdi, rdi
0x1800540f7  jz      short loc_180054109
0x1800540f9  mov     rax, [rdi]
0x1800540fc  mov     rcx, rdi
0x1800540ff  mov     rax, [rax+10h]
0x180054103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054108  nop
0x180054109  jmp     short loc_1800540AF
0x18005410b  xor     r9d, r9d; struct IXMLDOMNode **
0x18005410e  mov     r8, qword ptr [rbp+170h+SystemTime.wYear]; unsigned __int16 *
0x180054115  lea     rdx, aSimiccid; "SimIccId"
0x18005411c  mov     rcx, rbx; struct IXMLDOMNode *
0x18005411f  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180054124  mov     r14d, eax
0x180054127  test    eax, eax
0x180054129  jns     short loc_180054165
0x18005412b  lea     rcx, [rsp+270h+var_218]
0x180054130  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180054135  nop
0x180054136  test    rbx, rbx
0x180054139  jz      short loc_18005414B
0x18005413b  mov     rcx, [rbx]
0x18005413e  mov     rax, [rcx+10h]
0x180054142  mov     rcx, rbx
0x180054145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005414a  nop
0x18005414b  test    rdi, rdi
0x18005414e  jz      short loc_180054160
0x180054150  mov     rax, [rdi]
0x180054153  mov     rcx, rdi
0x180054156  mov     rax, [rax+10h]
0x18005415a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005415f  nop
0x180054160  jmp     loc_1800540AF
0x180054165  xor     r9d, r9d; struct IXMLDOMNode **
0x180054168  mov     r8, r12; unsigned __int16 *
0x18005416b  lea     rdx, aImsi; "Imsi"
0x180054172  mov     rcx, rbx; struct IXMLDOMNode *
0x180054175  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18005417a  mov     r14d, eax
0x18005417d  test    eax, eax
0x18005417f  jns     short loc_1800541BB
0x180054181  lea     rcx, [rsp+270h+var_218]
0x180054186  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18005418b  nop
0x18005418c  test    rbx, rbx
0x18005418f  jz      short loc_1800541A1
0x180054191  mov     rcx, [rbx]
0x180054194  mov     rax, [rcx+10h]
0x180054198  mov     rcx, rbx
0x18005419b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541a0  nop
0x1800541a1  test    rdi, rdi
0x1800541a4  jz      short loc_1800541B6
0x1800541a6  mov     rax, [rdi]
0x1800541a9  mov     rcx, rdi
0x1800541ac  mov     rax, [rax+10h]
0x1800541b0  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
