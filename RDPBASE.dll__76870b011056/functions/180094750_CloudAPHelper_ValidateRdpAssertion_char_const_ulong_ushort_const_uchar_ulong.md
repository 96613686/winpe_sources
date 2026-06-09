# CloudAPHelper::ValidateRdpAssertion(char const *,ulong,ushort const *,uchar * *,ulong *)

- ea: `0x180094750`
- end: `0x1800952a8`
- name: `?ValidateRdpAssertion@CloudAPHelper@@UEAAJPEBDKPEBGPEAPEAEPEAK@Z`
- size: `2904`
- prototype: `__int64 __fastcall(CloudAPHelper *__hidden this, const char *, unsigned int, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180019a80`
- `0x180078820`
- `0x180090460`
- `0x1800937cc`
- `0x180094750`
- `0x1800b910c`
- `0x180162010`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x180095272`
- `SspiCli!LsaFreeReturnBuffer` at `0x180095272`

## string_xrefs

- `0x180094979`: `GetInstanceOfJsonHelper failed`
- `0x180094c22`: `GetInstanceOfJsonHelper failed`
- `0x180094b6f`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x180094ec5`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x1800947db`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094878`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18009490b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800949a0`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094a4e`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094af3`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094b96`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094c49`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094cf7`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094d9f`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094e49`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094eec`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094f95`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18009504a`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800950f0`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18009518d`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180095202`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094cd0`: `spJsonHelper->SetValue(call) failed`
- `0x180094e22`: `spJsonHelper->SetValue(correlationId) failed`
- `0x180094a27`: `spJsonHelper->SetJsonString failed`
- `0x180095023`: `spJsonHelper->SetJsonString failed`
- `0x180094acc`: `spJsonHelper->SetValue(rdp_resourceid) failed`
- `0x180094d78`: `spJsonHelper->SetValue(payload) failed`
- `0x1800950c9`: `spJsonHelper->GetValue failed`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::ValidateRdpAssertion(
        CloudAPHelper *this,
        const char *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned int v7; // r15d
  const char *v8; // rsi
  int InstanceOfJsonHelper; // ebx
  int v10; // r8d
  int v11; // r9d
  struct IJsonHelper *v12; // rdi
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  struct IJsonHelper *v25; // rdi
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  unsigned int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v51; // [rsp+50h] [rbp-39h] BYREF
  int v52; // [rsp+54h] [rbp-35h] BYREF
  const char *v53; // [rsp+58h] [rbp-31h] BYREF
  const char *v54; // [rsp+60h] [rbp-29h] BYREF
  const char *v55; // [rsp+68h] [rbp-21h] BYREF
  const char *v56; // [rsp+70h] [rbp-19h] BYREF
  struct IJsonHelper *v57; // [rsp+78h] [rbp-11h] BYREF
  unsigned int v58; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v59; // [rsp+84h] [rbp-5h] BYREF
  void *Block; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int16 *v61; // [rsp+90h] [rbp+7h] BYREF
  PVOID Buffer; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int8 *v63; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int v65; // [rsp+E8h] [rbp+5Fh] BYREF

  v57 = 0;
  v7 = a3;
  Block = 0;
  v8 = a2;
  v65 = 0;
  v63 = 0;
  v58 = 0;
  Buffer = 0;
  v59 = 0;
  v61 = 0;
  if ( !a2 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v51 = 243;
      v56 = "Missing paramter pRdpAssertion";
      v52 = -2147024809;
      v53 = "ValidateRdpAssertion";
      v54 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v55 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)&byte_1801AF757,
        a3,
        (_DWORD)a4,
        (__int64)&v55,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v56);
    }
    goto LABEL_57;
  }
  if ( !a5 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 244;
      v55 = "Missing paramter ppAuthBlob";
      v51 = -2147024809;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)byte_1801AF709,
        a3,
        (_DWORD)a4,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  if ( !a6 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 245;
      v55 = "Missing paramter pcbAuthBlob";
      v51 = -2147024809;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)byte_1801AF6BB,
        a3,
        (_DWORD)a4,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  InstanceOfJsonHelper = GetInstanceOfJsonHelper(&v57);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 253;
      v55 = "GetInstanceOfJsonHelper failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_1801AF66D,
        v10,
        v11,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  if ( !a4 )
    goto LABEL_29;
  v12 = v57;
  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const char *, _QWORD))(*(_QWORD *)v57 + 56LL))(
                           v57,
                           v8,
                           v7);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 258;
      v55 = "spJsonHelper->SetJsonString failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)&byte_1801AF61F,
        v14,
        v15,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v12 + 120LL))(
                           v12,
                           L"rdp_resourceid",
                           a4);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 261;
      v55 = "spJsonHelper->SetValue(rdp_resourceid) failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)byte_1801AF5D1,
        v17,
        v18,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, void **, unsigned int *))(*(_QWORD *)v12 + 48LL))(
                           v12,
                           &Block,
                           &v65);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 264;
      v55 = "spJsonHelper->GetJsonStringAsByteArray failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)byte_1801AF583,
        v20,
        v21,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  if ( v12 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v57);
    v57 = 0;
  }
  v8 = (const char *)Block;
  v7 = v65;
  InstanceOfJsonHelper = GetInstanceOfJsonHelper(&v57);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 270;
      v55 = "GetInstanceOfJsonHelper failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v22,
        (unsigned int)byte_1801AF535,
        v23,
        v24,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
  }
  else
  {
LABEL_29:
    v25 = v57;
    InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *))(*(_QWORD *)v57 + 104LL))(
                             v57,
                             L"call");
    if ( InstanceOfJsonHelper >= 0 )
    {
      InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, const char *, _QWORD))(*(_QWORD *)v25 + 112LL))(
                               v25,
                               L"payload",
                               v8,
                               v7);
      if ( InstanceOfJsonHelper >= 0 )
      {
        InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, char *))(*(_QWORD *)v25 + 120LL))(
                                 v25,
                                 L"correlationId",
                                 (char *)this + 72);
        if ( InstanceOfJsonHelper >= 0 )
        {
          InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, unsigned __int8 **, unsigned int *))(*(_QWORD *)v25 + 48LL))(
                                   v25,
                                   &v63,
                                   &v58);
          if ( InstanceOfJsonHelper >= 0 )
          {
            InstanceOfJsonHelper = CloudAPHelper::CallCloudAP(this, v63, v58, &Buffer, &v59);
            if ( InstanceOfJsonHelper >= 0 )
            {
              if ( Buffer && (v39 = v59) != 0 )
              {
                InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *))(*(_QWORD *)v25 + 56LL))(v25);
                if ( InstanceOfJsonHelper >= 0 )
                {
                  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v25 + 88LL))(
                                           v25,
                                           L"authbuffer",
                                           &v61);
                  if ( InstanceOfJsonHelper >= 0 )
                  {
                    InstanceOfJsonHelper = CTSCryptUtils::UrlEncodedStringToBinaryW(v61, a5, a6);
                    if ( InstanceOfJsonHelper < 0 && (unsigned int)CallbackContext > 2 )
                    {
                      v52 = 311;
                      v55 = "CTSCryptUtils::UrlEncodedStringToBinaryW failed";
                      v51 = InstanceOfJsonHelper;
                      v54 = "ValidateRdpAssertion";
                      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                      v56 = "Error HResult failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                        v47,
                        (unsigned int)&byte_1801AF27F,
                        v48,
                        v49,
                        (__int64)&v56,
                        (__int64)&v51,
                        (__int64)&v53,
                        (__int64)&v52,
                        (__int64)&v54,
                        (__int64)&v55);
                    }
                  }
                  else if ( (unsigned int)CallbackContext > 2 )
                  {
                    v52 = 304;
                    v55 = "spJsonHelper->GetValue failed";
                    v51 = InstanceOfJsonHelper;
                    v54 = "ValidateRdpAssertion";
                    v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                    v56 = "Error HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      v44,
                      (unsigned int)byte_1801AF2CD,
                      v45,
                      v46,
                      (__int64)&v56,
                      (__int64)&v51,
                      (__int64)&v53,
                      (__int64)&v52,
                      (__int64)&v54,
                      (__int64)&v55);
                  }
                }
                else if ( (unsigned int)CallbackContext > 2 )
                {
                  v52 = 301;
                  v55 = "spJsonHelper->SetJsonString failed";
                  v51 = InstanceOfJsonHelper;
                  v54 = "ValidateRdpAssertion";
                  v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                  v56 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v41,
                    (unsigned int)byte_1801AF31B,
                    v42,
                    v43,
                    (__int64)&v56,
                    (__int64)&v51,
                    (__int64)&v53,
                    (__int64)&v52,
                    (__int64)&v54,
                    (__int64)&v55);
                }
              }
              else
              {
                InstanceOfJsonHelper = -2147467259;
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v52 = 291;
                  v55 = "ValidateRdpAssertion";
                  v51 = -2147467259;
                  v54 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                  v53 = "CloudAP returned an empty responce to the RDP assertion validation request";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v38,
                    (unsigned int)byte_1801AF369,
                    v39,
                    v40,
                    (__int64)&v53,
                    (__int64)&v51,
                    (__int64)&v54,
                    (__int64)&v52,
                    (__int64)&v55);
                }
              }
            }
            else if ( (unsigned int)CallbackContext > 2 )
            {
              v52 = 286;
              v55 = "CallCloudAP failed";
              v51 = InstanceOfJsonHelper;
              v54 = "ValidateRdpAssertion";
              v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
              v56 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v38,
                (unsigned int)&byte_1801AF3AF,
                v39,
                v40,
                (__int64)&v56,
                (__int64)&v51,
                (__int64)&v53,
                (__int64)&v52,
                (__int64)&v54,
                (__int64)&v55);
            }
          }
          else if ( (unsigned int)CallbackContext > 2 )
          {
            v52 = 283;
            v55 = "spJsonHelper->GetJsonStringAsByteArray failed";
            v51 = InstanceOfJsonHelper;
            v54 = "ValidateRdpAssertion";
            v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
            v56 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v35,
              (unsigned int)byte_1801AF3FD,
              v36,
              v37,
              (__int64)&v56,
              (__int64)&v51,
              (__int64)&v53,
              (__int64)&v52,
              (__int64)&v54,
              (__int64)&v55);
          }
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          v52 = 280;
          v55 = "spJsonHelper->SetValue(correlationId) failed";
          v51 = InstanceOfJsonHelper;
          v54 = "ValidateRdpAssertion";
          v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
          v56 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v32,
            (unsigned int)byte_1801AF44B,
            v33,
            v34,
            (__int64)&v56,
            (__int64)&v51,
            (__int64)&v53,
            (__int64)&v52,
            (__int64)&v54,
            (__int64)&v55);
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v52 = 277;
        v55 = "spJsonHelper->SetValue(payload) failed";
        v51 = InstanceOfJsonHelper;
        v54 = "ValidateRdpAssertion";
        v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
        v56 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v29,
          (unsigned int)byte_1801AF499,
          v30,
          v31,
          (__int64)&v56,
          (__int64)&v51,
          (__int64)&v53,
          (__int64)&v52,
          (__int64)&v54,
          (__int64)&v55);
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v52 = 274;
      v55 = "spJsonHelper->SetValue(call) failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v26,
        (unsigned int)&byte_1801AF4E7,
        v27,
        v28,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
  }
LABEL_57:
  if ( Block )
    operator delete(Block);
  if ( v61 )
    operator delete(v61);
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v63 )
    operator delete(v63);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v57);
  return (unsigned int)InstanceOfJsonHelper;
}

```

## disassembly

```asm
0x180094750  mov     [rsp-8+arg_10], rbx
0x180094755  mov     [rsp-8+arg_0], rcx
0x18009475a  push    rbp
0x18009475b  push    rsi
0x18009475c  push    rdi
0x18009475d  push    r14
0x18009475f  push    r15
0x180094761  lea     rbp, [rsp-27h]
0x180094766  sub     rsp, 0B0h
0x18009476d  xor     eax, eax
0x18009476f  mov     r14, r9
0x180094772  mov     [rbp+47h+var_58], rax
0x180094776  mov     r15d, r8d
0x180094779  mov     [rbp+47h+Block], rax
0x18009477d  mov     rsi, rdx
0x180094780  mov     [rbp+47h+arg_8], eax
0x180094783  mov     [rbp+47h+var_30], rax
0x180094787  mov     [rbp+47h+var_50], eax
0x18009478a  mov     [rbp+47h+Buffer], rax
0x18009478e  mov     [rbp+47h+var_4C], eax
0x180094791  mov     [rbp+47h+var_40], rax
0x180094795  test    rdx, rdx
0x180094798  jnz     loc_180094831
0x18009479e  mov     eax, cs:CallbackContext
0x1800947a4  mov     ecx, 80070057h
0x1800947a9  mov     ebx, ecx
0x1800947ab  cmp     eax, 2
0x1800947ae  jbe     loc_18009524D
0x1800947b4  lea     rax, aMissingParamte_3; "Missing paramter pRdpAssertion"
0x1800947bb  mov     [rbp+47h+var_80], 0F3h
0x1800947c2  mov     [rbp+47h+var_60], rax
0x1800947c6  lea     rdx, byte_1801AF757
0x1800947cd  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x1800947d4  mov     [rbp+47h+var_7C], ecx
0x1800947d7  mov     [rbp+47h+var_78], rax
0x1800947db  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800947e2  mov     [rbp+47h+var_70], rax
0x1800947e6  lea     rax, aErrorCondition; "Error condition failed"
0x1800947ed  mov     [rbp+47h+var_68], rax
0x1800947f1  lea     rax, [rbp+47h+var_60]
0x1800947f5  mov     [rsp+0D0h+var_88], rax
0x1800947fa  lea     rax, [rbp+47h+var_78]
0x1800947fe  mov     [rsp+0D0h+var_90], rax
0x180094803  lea     rax, [rbp+47h+var_80]
0x180094807  mov     [rsp+0D0h+var_98], rax
0x18009480c  lea     rax, [rbp+47h+var_70]
0x180094810  mov     [rsp+0D0h+var_A0], rax
0x180094815  lea     rax, [rbp+47h+var_7C]
0x180094819  mov     [rsp+0D0h+var_A8], rax
0x18009481e  lea     rax, [rbp+47h+var_68]
0x180094822  mov     [rsp+0D0h+var_B0], rax
0x180094827  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009482c  jmp     loc_18009524D
0x180094831  cmp     [rbp+47h+arg_20], rax
0x180094835  jnz     loc_1800948C4
0x18009483b  mov     eax, cs:CallbackContext
0x180094841  mov     ecx, 80070057h
0x180094846  mov     ebx, ecx
0x180094848  cmp     eax, 2
0x18009484b  jbe     loc_18009524D
0x180094851  lea     rax, aMissingParamte_7; "Missing paramter ppAuthBlob"
0x180094858  mov     [rbp+47h+var_7C], 0F4h
0x18009485f  mov     [rbp+47h+var_68], rax
0x180094863  lea     rdx, byte_1801AF709
0x18009486a  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x180094871  mov     [rbp+47h+var_80], ecx
0x180094874  mov     [rbp+47h+var_70], rax
0x180094878  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18009487f  mov     [rbp+47h+var_78], rax
0x180094883  lea     rax, aErrorCondition; "Error condition failed"
0x18009488a  mov     [rbp+47h+var_60], rax
0x18009488e  lea     rax, [rbp+47h+var_68]
0x180094892  mov     [rsp+0D0h+var_88], rax
0x180094897  lea     rax, [rbp+47h+var_70]
0x18009489b  mov     [rsp+0D0h+var_90], rax
0x1800948a0  lea     rax, [rbp+47h+var_7C]
0x1800948a4  mov     [rsp+0D0h+var_98], rax
0x1800948a9  lea     rax, [rbp+47h+var_78]
0x1800948ad  mov     [rsp+0D0h+var_A0], rax
0x1800948b2  lea     rax, [rbp+47h+var_80]
0x1800948b6  mov     [rsp+0D0h+var_A8], rax
0x1800948bb  lea     rax, [rbp+47h+var_60]
0x1800948bf  jmp     loc_180094822
0x1800948c4  cmp     [rbp+47h+arg_28], rax
0x1800948c8  jnz     loc_180094957
0x1800948ce  mov     eax, cs:CallbackContext
0x1800948d4  mov     ecx, 80070057h
0x1800948d9  mov     ebx, ecx
0x1800948db  cmp     eax, 2
0x1800948de  jbe     loc_18009524D
0x1800948e4  lea     rax, aMissingParamte_6; "Missing paramter pcbAuthBlob"
0x1800948eb  mov     [rbp+47h+var_7C], 0F5h
0x1800948f2  mov     [rbp+47h+var_68], rax
0x1800948f6  lea     rdx, byte_1801AF6BB
0x1800948fd  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x180094904  mov     [rbp+47h+var_80], ecx
0x180094907  mov     [rbp+47h+var_70], rax
0x18009490b  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180094912  mov     [rbp+47h+var_78], rax
0x180094916  lea     rax, aErrorCondition; "Error condition failed"
0x18009491d  mov     [rbp+47h+var_60], rax
0x180094921  lea     rax, [rbp+47h+var_68]
0x180094925  mov     [rsp+0D0h+var_88], rax
0x18009492a  lea     rax, [rbp+47h+var_70]
0x18009492e  mov     [rsp+0D0h+var_90], rax
0x180094933  lea     rax, [rbp+47h+var_7C]
0x180094937  mov     [rsp+0D0h+var_98], rax
0x18009493c  lea     rax, [rbp+47h+var_78]
0x180094940  mov     [rsp+0D0h+var_A0], rax
0x180094945  lea     rax, [rbp+47h+var_80]
0x180094949  mov     [rsp+0D0h+var_A8], rax
0x18009494e  lea     rax, [rbp+47h+var_60]
0x180094952  jmp     loc_180094822
0x180094957  lea     rcx, [rbp+47h+var_58]; struct IJsonHelper **
0x18009495b  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x180094960  mov     ebx, eax
0x180094962  test    eax, eax
0x180094964  jns     loc_1800949EC
0x18009496a  mov     ecx, cs:CallbackContext
0x180094970  cmp     ecx, 2
0x180094973  jbe     loc_18009524D
0x180094979  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x180094980  mov     [rbp+47h+var_7C], 0FDh
0x180094987  mov     [rbp+47h+var_68], rax
0x18009498b  lea     rdx, byte_1801AF66D
0x180094992  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x180094999  mov     [rbp+47h+var_80], ebx
0x18009499c  mov     [rbp+47h+var_70], rax
0x1800949a0  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800949a7  mov     [rbp+47h+var_78], rax
0x1800949ab  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800949b2  mov     [rbp+47h+var_60], rax
0x1800949b6  lea     rax, [rbp+47h+var_68]
0x1800949ba  mov     [rsp+0D0h+var_88], rax
0x1800949bf  lea     rax, [rbp+47h+var_70]
0x1800949c3  mov     [rsp+0D0h+var_90], rax
0x1800949c8  lea     rax, [rbp+47h+var_7C]
0x1800949cc  mov     [rsp+0D0h+var_98], rax
0x1800949d1  lea     rax, [rbp+47h+var_78]
0x1800949d5  mov     [rsp+0D0h+var_A0], rax
0x1800949da  lea     rax, [rbp+47h+var_80]
0x1800949de  mov     [rsp+0D0h+var_A8], rax
0x1800949e3  lea     rax, [rbp+47h+var_60]
0x1800949e7  jmp     loc_180094822
0x1800949ec  test    r14, r14
0x1800949ef  jz      loc_180094C95
0x1800949f5  mov     rdi, [rbp+47h+var_58]
0x1800949f9  mov     r8d, r15d
0x1800949fc  mov     rdx, rsi
0x1800949ff  mov     rcx, rdi
0x180094a02  mov     rax, [rdi]
0x180094a05  mov     rax, [rax+38h]
0x180094a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a0e  mov     ebx, eax
0x180094a10  test    eax, eax
0x180094a12  jns     loc_180094A9A
0x180094a18  mov     eax, cs:CallbackContext
0x180094a1e  cmp     eax, 2
0x180094a21  jbe     loc_18009524D
0x180094a27  lea     rax, aSpjsonhelperSe_3; "spJsonHelper->SetJsonString failed"
0x180094a2e  mov     [rbp+47h+var_7C], 102h
0x180094a35  mov     [rbp+47h+var_68], rax
0x180094a39  lea     rdx, byte_1801AF61F
0x180094a40  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x180094a47  mov     [rbp+47h+var_80], ebx
0x180094a4a  mov     [rbp+47h+var_70], rax
0x180094a4e  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180094a55  mov     [rbp+47h+var_78], rax
0x180094a59  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180094a60  mov     [rbp+47h+var_60], rax
0x180094a64  lea     rax, [rbp+47h+var_68]
0x180094a68  mov     [rsp+0D0h+var_88], rax
0x180094a6d  lea     rax, [rbp+47h+var_70]
0x180094a71  mov     [rsp+0D0h+var_90], rax
0x180094a76  lea     rax, [rbp+47h+var_7C]
0x180094a7a  mov     [rsp+0D0h+var_98], rax
0x180094a7f  lea     rax, [rbp+47h+var_78]
0x180094a83  mov     [rsp+0D0h+var_A0], rax
0x180094a88  lea     rax, [rbp+47h+var_80]
0x180094a8c  mov     [rsp+0D0h+var_A8], rax
0x180094a91  lea     rax, [rbp+47h+var_60]
0x180094a95  jmp     loc_180094822
0x180094a9a  mov     rax, [rdi]
0x180094a9d  lea     rdx, aRdpResourceid; "rdp_resourceid"
0x180094aa4  mov     r8, r14
0x180094aa7  mov     rcx, rdi
0x180094aaa  mov     rax, [rax+78h]
0x180094aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094ab3  mov     ebx, eax
0x180094ab5  test    eax, eax
0x180094ab7  jns     loc_180094B3F
0x180094abd  mov     eax, cs:CallbackContext
0x180094ac3  cmp     eax, 2
0x180094ac6  jbe     loc_18009524D
0x180094acc  lea     rax, aSpjsonhelperSe_4; "spJsonHelper->SetValue(rdp_resourceid) "...
0x180094ad3  mov     [rbp+47h+var_7C], 105h
0x180094ada  mov     [rbp+47h+var_68], rax
0x180094ade  lea     rdx, byte_1801AF5D1
0x180094ae5  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x180094aec  mov     [rbp+47h+var_80], ebx
0x180094aef  mov     [rbp+47h+var_70], rax
0x180094af3  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180094afa  mov     [rbp+47h+var_78], rax
0x180094afe  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180094b05  mov     [rbp+47h+var_60], rax
0x180094b09  lea     rax, [rbp+47h+var_68]
0x180094b0d  mov     [rsp+0D0h+var_88], rax
0x180094b12  lea     rax, [rbp+47h+var_70]
0x180094b16  mov     [rsp+0D0h+var_90], rax
0x180094b1b  lea     rax, [rbp+47h+var_7C]
0x180094b1f  mov     [rsp+0D0h+var_98], rax
0x180094b24  lea     rax, [rbp+47h+var_78]
0x180094b28  mov     [rsp+0D0h+var_A0], rax
0x180094b2d  lea     rax, [rbp+47h+var_80]
0x180094b31  mov     [rsp+0D0h+var_A8], rax
0x180094b36  lea     rax, [rbp+47h+var_60]
0x180094b3a  jmp     loc_180094822
0x180094b3f  mov     rax, [rdi]
0x180094b42  lea     r8, [rbp+47h+arg_8]
0x180094b46  lea     rdx, [rbp+47h+Block]
0x180094b4a  mov     rcx, rdi
0x180094b4d  mov     rax, [rax+30h]
0x180094b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094b56  mov     ebx, eax
0x180094b58  test    eax, eax
0x180094b5a  jns     loc_180094BE2
0x180094b60  mov     eax, cs:CallbackContext
0x180094b66  cmp     eax, 2
0x180094b69  jbe     loc_18009524D
0x180094b6f  lea     rax, aSpjsonhelperGe_1; "spJsonHelper->GetJsonStringAsByteArray "...
0x180094b76  mov     [rbp+47h+var_7C], 108h
0x180094b7d  mov     [rbp+47h+var_68], rax
0x180094b81  lea     rdx, byte_1801AF583
0x180094b88  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x180094b8f  mov     [rbp+47h+var_80], ebx
0x180094b92  mov     [rbp+47h+var_70], rax
0x180094b96  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180094b9d  mov     [rbp+47h+var_78], rax
0x180094ba1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180094ba8  mov     [rbp+47h+var_60], rax
0x180094bac  lea     rax, [rbp+47h+var_68]
0x180094bb0  mov     [rsp+0D0h+var_88], rax
0x180094bb5  lea     rax, [rbp+47h+var_70]
0x180094bb9  mov     [rsp+0D0h+var_90], rax
0x180094bbe  lea     rax, [rbp+47h+var_7C]
0x180094bc2  mov     [rsp+0D0h+var_98], rax
0x180094bc7  lea     rax, [rbp+47h+var_78]
0x180094bcb  mov     [rsp+0D0h+var_A0], rax
0x180094bd0  lea     rax, [rbp+47h+var_80]
0x180094bd4  mov     [rsp+0D0h+var_A8], rax
0x180094bd9  lea     rax, [rbp+47h+var_60]
0x180094bdd  jmp     loc_180094822
0x180094be2  test    rdi, rdi
0x180094be5  jz      short loc_180094BF8
0x180094be7  lea     rcx, [rbp+47h+var_58]; void *
0x180094beb  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180094bf0  mov     [rbp+47h+var_58], 0
0x180094bf8  mov     rsi, [rbp+47h+Block]
0x180094bfc  lea     rcx, [rbp+47h+var_58]; struct IJsonHelper **
0x180094c00  mov     r15d, [rbp+47h+arg_8]
0x180094c04  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x180094c09  mov     ebx, eax
0x180094c0b  test    eax, eax
0x180094c0d  jns     loc_180094C95
0x180094c13  mov     eax, cs:CallbackContext
0x180094c19  cmp     eax, 2
0x180094c1c  jbe     loc_18009524D
0x180094c22  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x180094c29  mov     [rbp+47h+var_7C], 10Eh
0x180094c30  mov     [rbp+47h+var_68], rax
0x180094c34  lea     rdx, byte_1801AF535
0x180094c3b  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x180094c42  mov     [rbp+47h+var_80], ebx
0x180094c45  mov     [rbp+47h+var_70], rax
0x180094c49  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180094c50  mov     [rbp+47h+var_78], rax
0x180094c54  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180094c5b  mov     [rbp+47h+var_60], rax
0x180094c5f  lea     rax, [rbp+47h+var_68]
0x180094c63  mov     [rsp+0D0h+var_88], rax
0x180094c68  lea     rax, [rbp+47h+var_70]
0x180094c6c  mov     [rsp+0D0h+var_90], rax
0x180094c71  lea     rax, [rbp+47h+var_7C]
0x180094c75  mov     [rsp+0D0h+var_98], rax
0x180094c7a  lea     rax, [rbp+47h+var_78]
0x180094c7e  mov     [rsp+0D0h+var_A0], rax
0x180094c83  lea     rax, [rbp+47h+var_80]
0x180094c87  mov     [rsp+0D0h+var_A8], rax
0x180094c8c  lea     rax, [rbp+47h+var_60]
0x180094c90  jmp     loc_180094822
0x180094c95  mov     rdi, [rbp+47h+var_58]
0x180094c99  lea     rdx, aCall; "call"
0x180094ca0  movsd   xmm2, cs:__real@4024000000000000
0x180094ca8  mov     rcx, rdi
0x180094cab  mov     rax, [rdi]
0x180094cae  mov     rax, [rax+68h]
0x180094cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cb7  mov     ebx, eax
0x180094cb9  test    eax, eax
0x180094cbb  jns     loc_180094D43
  ... truncated ...
```
