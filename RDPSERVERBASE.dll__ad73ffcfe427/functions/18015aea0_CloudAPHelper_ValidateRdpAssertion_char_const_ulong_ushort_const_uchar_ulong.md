# CloudAPHelper::ValidateRdpAssertion(char const *,ulong,ushort const *,uchar * *,ulong *)

- ea: `0x18015aea0`
- end: `0x18015b9f8`
- name: `?ValidateRdpAssertion@CloudAPHelper@@UEAAJPEBDKPEBGPEAPEAEPEAK@Z`
- size: `2904`
- prototype: `__int64 __fastcall(CloudAPHelper *__hidden this, const char *, unsigned int, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000116c`
- `0x18000202c`
- `0x18000ce04`
- `0x18007f6a4`
- `0x18015944c`
- `0x18015aea0`
- `0x18015f650`
- `0x180162bdc`
- `0x18019c010`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18015b9c2`
- `SspiCli!LsaFreeReturnBuffer` at `0x18015b9c2`

## string_xrefs

- `0x18015af2b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015afc8`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b05b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b0f0`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b19e`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b243`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b2e6`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b399`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b447`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b4ef`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b599`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b63c`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b6e5`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b79a`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b840`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b8dd`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b952`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015b0c9`: `GetInstanceOfJsonHelper failed`
- `0x18015b372`: `GetInstanceOfJsonHelper failed`
- `0x18015b420`: `spJsonHelper->SetValue(call) failed`
- `0x18015b2bf`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x18015b615`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x18015b572`: `spJsonHelper->SetValue(correlationId) failed`
- `0x18015b177`: `spJsonHelper->SetJsonString failed`
- `0x18015b773`: `spJsonHelper->SetJsonString failed`
- `0x18015b21c`: `spJsonHelper->SetValue(rdp_resourceid) failed`
- `0x18015b4c8`: `spJsonHelper->SetValue(payload) failed`
- `0x18015b819`: `spJsonHelper->GetValue failed`

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
        (unsigned int)&dword_18029ED3C,
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
        (unsigned int)word_18029EC52,
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
        (unsigned int)qword_18029ECA0,
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
        (unsigned int)&word_18029EBB6,
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
        (unsigned int)&dword_18029EC04,
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
        (unsigned int)word_18029EB1A,
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
        (unsigned int)qword_18029EB68,
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
    TCntPtr<IRdpVCMgr>::SafeRelease(&v57);
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
        (unsigned int)&word_18029EA7E,
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
                        (unsigned int)&word_18029E816,
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
                      (unsigned int)word_18029E8B2,
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
                    (unsigned int)&dword_18029E864,
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
                    (unsigned int)&word_18029E94E,
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
                (unsigned int)qword_18029E900,
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
              (unsigned int)word_18029E9E2,
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
            (unsigned int)&dword_18029E994,
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
          (unsigned int)qword_18029EA30,
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
        (unsigned int)&dword_18029EACC,
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
  TCntPtr<IRdpVCMgr>::SafeRelease(&v57);
  return (unsigned int)InstanceOfJsonHelper;
}

```

## disassembly

```asm
0x18015aea0  mov     [rsp-8+arg_10], rbx
0x18015aea5  mov     [rsp-8+arg_0], rcx
0x18015aeaa  push    rbp
0x18015aeab  push    rsi
0x18015aeac  push    rdi
0x18015aead  push    r14
0x18015aeaf  push    r15
0x18015aeb1  lea     rbp, [rsp-27h]
0x18015aeb6  sub     rsp, 0B0h
0x18015aebd  xor     eax, eax
0x18015aebf  mov     r14, r9
0x18015aec2  mov     [rbp+47h+var_58], rax
0x18015aec6  mov     r15d, r8d
0x18015aec9  mov     [rbp+47h+Block], rax
0x18015aecd  mov     rsi, rdx
0x18015aed0  mov     [rbp+47h+arg_8], eax
0x18015aed3  mov     [rbp+47h+var_30], rax
0x18015aed7  mov     [rbp+47h+var_50], eax
0x18015aeda  mov     [rbp+47h+Buffer], rax
0x18015aede  mov     [rbp+47h+var_4C], eax
0x18015aee1  mov     [rbp+47h+var_40], rax
0x18015aee5  test    rdx, rdx
0x18015aee8  jnz     loc_18015AF81
0x18015aeee  mov     eax, cs:CallbackContext
0x18015aef4  mov     ecx, 80070057h
0x18015aef9  mov     ebx, ecx
0x18015aefb  cmp     eax, 2
0x18015aefe  jbe     loc_18015B99D
0x18015af04  lea     rax, aMissingParamte_3; "Missing paramter pRdpAssertion"
0x18015af0b  mov     [rbp+47h+var_80], 0F3h
0x18015af12  mov     [rbp+47h+var_60], rax
0x18015af16  lea     rdx, dword_18029ED3C
0x18015af1d  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015af24  mov     [rbp+47h+var_7C], ecx
0x18015af27  mov     [rbp+47h+var_78], rax
0x18015af2b  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015af32  mov     [rbp+47h+var_70], rax
0x18015af36  lea     rax, aErrorCondition; "Error condition failed"
0x18015af3d  mov     [rbp+47h+var_68], rax
0x18015af41  lea     rax, [rbp+47h+var_60]
0x18015af45  mov     [rsp+0D0h+var_88], rax
0x18015af4a  lea     rax, [rbp+47h+var_78]
0x18015af4e  mov     [rsp+0D0h+var_90], rax
0x18015af53  lea     rax, [rbp+47h+var_80]
0x18015af57  mov     [rsp+0D0h+var_98], rax
0x18015af5c  lea     rax, [rbp+47h+var_70]
0x18015af60  mov     [rsp+0D0h+var_A0], rax
0x18015af65  lea     rax, [rbp+47h+var_7C]
0x18015af69  mov     [rsp+0D0h+var_A8], rax
0x18015af6e  lea     rax, [rbp+47h+var_68]
0x18015af72  mov     [rsp+0D0h+var_B0], rax
0x18015af77  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015af7c  jmp     loc_18015B99D
0x18015af81  cmp     [rbp+47h+arg_20], rax
0x18015af85  jnz     loc_18015B014
0x18015af8b  mov     eax, cs:CallbackContext
0x18015af91  mov     ecx, 80070057h
0x18015af96  mov     ebx, ecx
0x18015af98  cmp     eax, 2
0x18015af9b  jbe     loc_18015B99D
0x18015afa1  lea     rax, aMissingParamte_7; "Missing paramter ppAuthBlob"
0x18015afa8  mov     [rbp+47h+var_7C], 0F4h
0x18015afaf  mov     [rbp+47h+var_68], rax
0x18015afb3  lea     rdx, word_18029EC52
0x18015afba  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015afc1  mov     [rbp+47h+var_80], ecx
0x18015afc4  mov     [rbp+47h+var_70], rax
0x18015afc8  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015afcf  mov     [rbp+47h+var_78], rax
0x18015afd3  lea     rax, aErrorCondition; "Error condition failed"
0x18015afda  mov     [rbp+47h+var_60], rax
0x18015afde  lea     rax, [rbp+47h+var_68]
0x18015afe2  mov     [rsp+0D0h+var_88], rax
0x18015afe7  lea     rax, [rbp+47h+var_70]
0x18015afeb  mov     [rsp+0D0h+var_90], rax
0x18015aff0  lea     rax, [rbp+47h+var_7C]
0x18015aff4  mov     [rsp+0D0h+var_98], rax
0x18015aff9  lea     rax, [rbp+47h+var_78]
0x18015affd  mov     [rsp+0D0h+var_A0], rax
0x18015b002  lea     rax, [rbp+47h+var_80]
0x18015b006  mov     [rsp+0D0h+var_A8], rax
0x18015b00b  lea     rax, [rbp+47h+var_60]
0x18015b00f  jmp     loc_18015AF72
0x18015b014  cmp     [rbp+47h+arg_28], rax
0x18015b018  jnz     loc_18015B0A7
0x18015b01e  mov     eax, cs:CallbackContext
0x18015b024  mov     ecx, 80070057h
0x18015b029  mov     ebx, ecx
0x18015b02b  cmp     eax, 2
0x18015b02e  jbe     loc_18015B99D
0x18015b034  lea     rax, aMissingParamte_6; "Missing paramter pcbAuthBlob"
0x18015b03b  mov     [rbp+47h+var_7C], 0F5h
0x18015b042  mov     [rbp+47h+var_68], rax
0x18015b046  lea     rdx, qword_18029ECA0
0x18015b04d  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015b054  mov     [rbp+47h+var_80], ecx
0x18015b057  mov     [rbp+47h+var_70], rax
0x18015b05b  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015b062  mov     [rbp+47h+var_78], rax
0x18015b066  lea     rax, aErrorCondition; "Error condition failed"
0x18015b06d  mov     [rbp+47h+var_60], rax
0x18015b071  lea     rax, [rbp+47h+var_68]
0x18015b075  mov     [rsp+0D0h+var_88], rax
0x18015b07a  lea     rax, [rbp+47h+var_70]
0x18015b07e  mov     [rsp+0D0h+var_90], rax
0x18015b083  lea     rax, [rbp+47h+var_7C]
0x18015b087  mov     [rsp+0D0h+var_98], rax
0x18015b08c  lea     rax, [rbp+47h+var_78]
0x18015b090  mov     [rsp+0D0h+var_A0], rax
0x18015b095  lea     rax, [rbp+47h+var_80]
0x18015b099  mov     [rsp+0D0h+var_A8], rax
0x18015b09e  lea     rax, [rbp+47h+var_60]
0x18015b0a2  jmp     loc_18015AF72
0x18015b0a7  lea     rcx, [rbp+47h+var_58]; struct IJsonHelper **
0x18015b0ab  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x18015b0b0  mov     ebx, eax
0x18015b0b2  test    eax, eax
0x18015b0b4  jns     loc_18015B13C
0x18015b0ba  mov     ecx, cs:CallbackContext
0x18015b0c0  cmp     ecx, 2
0x18015b0c3  jbe     loc_18015B99D
0x18015b0c9  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x18015b0d0  mov     [rbp+47h+var_7C], 0FDh
0x18015b0d7  mov     [rbp+47h+var_68], rax
0x18015b0db  lea     rdx, word_18029EBB6
0x18015b0e2  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015b0e9  mov     [rbp+47h+var_80], ebx
0x18015b0ec  mov     [rbp+47h+var_70], rax
0x18015b0f0  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015b0f7  mov     [rbp+47h+var_78], rax
0x18015b0fb  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015b102  mov     [rbp+47h+var_60], rax
0x18015b106  lea     rax, [rbp+47h+var_68]
0x18015b10a  mov     [rsp+0D0h+var_88], rax
0x18015b10f  lea     rax, [rbp+47h+var_70]
0x18015b113  mov     [rsp+0D0h+var_90], rax
0x18015b118  lea     rax, [rbp+47h+var_7C]
0x18015b11c  mov     [rsp+0D0h+var_98], rax
0x18015b121  lea     rax, [rbp+47h+var_78]
0x18015b125  mov     [rsp+0D0h+var_A0], rax
0x18015b12a  lea     rax, [rbp+47h+var_80]
0x18015b12e  mov     [rsp+0D0h+var_A8], rax
0x18015b133  lea     rax, [rbp+47h+var_60]
0x18015b137  jmp     loc_18015AF72
0x18015b13c  test    r14, r14
0x18015b13f  jz      loc_18015B3E5
0x18015b145  mov     rdi, [rbp+47h+var_58]
0x18015b149  mov     r8d, r15d
0x18015b14c  mov     rdx, rsi
0x18015b14f  mov     rcx, rdi
0x18015b152  mov     rax, [rdi]
0x18015b155  mov     rax, [rax+38h]
0x18015b159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b15e  mov     ebx, eax
0x18015b160  test    eax, eax
0x18015b162  jns     loc_18015B1EA
0x18015b168  mov     eax, cs:CallbackContext
0x18015b16e  cmp     eax, 2
0x18015b171  jbe     loc_18015B99D
0x18015b177  lea     rax, aSpjsonhelperSe_3; "spJsonHelper->SetJsonString failed"
0x18015b17e  mov     [rbp+47h+var_7C], 102h
0x18015b185  mov     [rbp+47h+var_68], rax
0x18015b189  lea     rdx, dword_18029EC04
0x18015b190  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015b197  mov     [rbp+47h+var_80], ebx
0x18015b19a  mov     [rbp+47h+var_70], rax
0x18015b19e  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015b1a5  mov     [rbp+47h+var_78], rax
0x18015b1a9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015b1b0  mov     [rbp+47h+var_60], rax
0x18015b1b4  lea     rax, [rbp+47h+var_68]
0x18015b1b8  mov     [rsp+0D0h+var_88], rax
0x18015b1bd  lea     rax, [rbp+47h+var_70]
0x18015b1c1  mov     [rsp+0D0h+var_90], rax
0x18015b1c6  lea     rax, [rbp+47h+var_7C]
0x18015b1ca  mov     [rsp+0D0h+var_98], rax
0x18015b1cf  lea     rax, [rbp+47h+var_78]
0x18015b1d3  mov     [rsp+0D0h+var_A0], rax
0x18015b1d8  lea     rax, [rbp+47h+var_80]
0x18015b1dc  mov     [rsp+0D0h+var_A8], rax
0x18015b1e1  lea     rax, [rbp+47h+var_60]
0x18015b1e5  jmp     loc_18015AF72
0x18015b1ea  mov     rax, [rdi]
0x18015b1ed  lea     rdx, aRdpResourceid; "rdp_resourceid"
0x18015b1f4  mov     r8, r14
0x18015b1f7  mov     rcx, rdi
0x18015b1fa  mov     rax, [rax+78h]
0x18015b1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b203  mov     ebx, eax
0x18015b205  test    eax, eax
0x18015b207  jns     loc_18015B28F
0x18015b20d  mov     eax, cs:CallbackContext
0x18015b213  cmp     eax, 2
0x18015b216  jbe     loc_18015B99D
0x18015b21c  lea     rax, aSpjsonhelperSe_4; "spJsonHelper->SetValue(rdp_resourceid) "...
0x18015b223  mov     [rbp+47h+var_7C], 105h
0x18015b22a  mov     [rbp+47h+var_68], rax
0x18015b22e  lea     rdx, word_18029EB1A
0x18015b235  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015b23c  mov     [rbp+47h+var_80], ebx
0x18015b23f  mov     [rbp+47h+var_70], rax
0x18015b243  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015b24a  mov     [rbp+47h+var_78], rax
0x18015b24e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015b255  mov     [rbp+47h+var_60], rax
0x18015b259  lea     rax, [rbp+47h+var_68]
0x18015b25d  mov     [rsp+0D0h+var_88], rax
0x18015b262  lea     rax, [rbp+47h+var_70]
0x18015b266  mov     [rsp+0D0h+var_90], rax
0x18015b26b  lea     rax, [rbp+47h+var_7C]
0x18015b26f  mov     [rsp+0D0h+var_98], rax
0x18015b274  lea     rax, [rbp+47h+var_78]
0x18015b278  mov     [rsp+0D0h+var_A0], rax
0x18015b27d  lea     rax, [rbp+47h+var_80]
0x18015b281  mov     [rsp+0D0h+var_A8], rax
0x18015b286  lea     rax, [rbp+47h+var_60]
0x18015b28a  jmp     loc_18015AF72
0x18015b28f  mov     rax, [rdi]
0x18015b292  lea     r8, [rbp+47h+arg_8]
0x18015b296  lea     rdx, [rbp+47h+Block]
0x18015b29a  mov     rcx, rdi
0x18015b29d  mov     rax, [rax+30h]
0x18015b2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b2a6  mov     ebx, eax
0x18015b2a8  test    eax, eax
0x18015b2aa  jns     loc_18015B332
0x18015b2b0  mov     eax, cs:CallbackContext
0x18015b2b6  cmp     eax, 2
0x18015b2b9  jbe     loc_18015B99D
0x18015b2bf  lea     rax, aSpjsonhelperGe_1; "spJsonHelper->GetJsonStringAsByteArray "...
0x18015b2c6  mov     [rbp+47h+var_7C], 108h
0x18015b2cd  mov     [rbp+47h+var_68], rax
0x18015b2d1  lea     rdx, qword_18029EB68
0x18015b2d8  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015b2df  mov     [rbp+47h+var_80], ebx
0x18015b2e2  mov     [rbp+47h+var_70], rax
0x18015b2e6  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015b2ed  mov     [rbp+47h+var_78], rax
0x18015b2f1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015b2f8  mov     [rbp+47h+var_60], rax
0x18015b2fc  lea     rax, [rbp+47h+var_68]
0x18015b300  mov     [rsp+0D0h+var_88], rax
0x18015b305  lea     rax, [rbp+47h+var_70]
0x18015b309  mov     [rsp+0D0h+var_90], rax
0x18015b30e  lea     rax, [rbp+47h+var_7C]
0x18015b312  mov     [rsp+0D0h+var_98], rax
0x18015b317  lea     rax, [rbp+47h+var_78]
0x18015b31b  mov     [rsp+0D0h+var_A0], rax
0x18015b320  lea     rax, [rbp+47h+var_80]
0x18015b324  mov     [rsp+0D0h+var_A8], rax
0x18015b329  lea     rax, [rbp+47h+var_60]
0x18015b32d  jmp     loc_18015AF72
0x18015b332  test    rdi, rdi
0x18015b335  jz      short loc_18015B348
0x18015b337  lea     rcx, [rbp+47h+var_58]
0x18015b33b  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18015b340  mov     [rbp+47h+var_58], 0
0x18015b348  mov     rsi, [rbp+47h+Block]
0x18015b34c  lea     rcx, [rbp+47h+var_58]; struct IJsonHelper **
0x18015b350  mov     r15d, [rbp+47h+arg_8]
0x18015b354  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x18015b359  mov     ebx, eax
0x18015b35b  test    eax, eax
0x18015b35d  jns     loc_18015B3E5
0x18015b363  mov     eax, cs:CallbackContext
0x18015b369  cmp     eax, 2
0x18015b36c  jbe     loc_18015B99D
0x18015b372  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x18015b379  mov     [rbp+47h+var_7C], 10Eh
0x18015b380  mov     [rbp+47h+var_68], rax
0x18015b384  lea     rdx, word_18029EA7E
0x18015b38b  lea     rax, aValidaterdpass_0; "ValidateRdpAssertion"
0x18015b392  mov     [rbp+47h+var_80], ebx
0x18015b395  mov     [rbp+47h+var_70], rax
0x18015b399  lea     rax, aOnecoreTermsrv_32; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18015b3a0  mov     [rbp+47h+var_78], rax
0x18015b3a4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015b3ab  mov     [rbp+47h+var_60], rax
0x18015b3af  lea     rax, [rbp+47h+var_68]
0x18015b3b3  mov     [rsp+0D0h+var_88], rax
0x18015b3b8  lea     rax, [rbp+47h+var_70]
0x18015b3bc  mov     [rsp+0D0h+var_90], rax
0x18015b3c1  lea     rax, [rbp+47h+var_7C]
0x18015b3c5  mov     [rsp+0D0h+var_98], rax
0x18015b3ca  lea     rax, [rbp+47h+var_78]
0x18015b3ce  mov     [rsp+0D0h+var_A0], rax
0x18015b3d3  lea     rax, [rbp+47h+var_80]
0x18015b3d7  mov     [rsp+0D0h+var_A8], rax
0x18015b3dc  lea     rax, [rbp+47h+var_60]
0x18015b3e0  jmp     loc_18015AF72
0x18015b3e5  mov     rdi, [rbp+47h+var_58]
0x18015b3e9  lea     rdx, aCall; "call"
0x18015b3f0  movsd   xmm2, cs:__real@4024000000000000
0x18015b3f8  mov     rcx, rdi
0x18015b3fb  mov     rax, [rdi]
0x18015b3fe  mov     rax, [rax+68h]
0x18015b402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b407  mov     ebx, eax
0x18015b409  test    eax, eax
0x18015b40b  jns     loc_18015B493
  ... truncated ...
```
