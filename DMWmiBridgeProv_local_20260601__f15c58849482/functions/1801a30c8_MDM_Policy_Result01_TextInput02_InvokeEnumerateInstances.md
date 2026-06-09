# MDM_Policy_Result01_TextInput02_InvokeEnumerateInstances

- ea: `0x1801a30c8`
- end: `0x1801a3c75`
- name: `MDM_Policy_Result01_TextInput02_InvokeEnumerateInstances`
- size: `2989`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1801a2360`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801a30c8`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801a33da`
- `msvcrt!_wtoi` at `0x1801a3421`
- `msvcrt!_wtoi` at `0x1801a3468`
- `msvcrt!_wtoi` at `0x1801a34af`
- `msvcrt!_wtoi` at `0x1801a34f6`
- `msvcrt!_wtoi` at `0x1801a353d`
- `msvcrt!_wtoi` at `0x1801a3584`
- `msvcrt!_wtoi` at `0x1801a35cb`
- `msvcrt!_wtoi` at `0x1801a3612`
- `msvcrt!_wtoi` at `0x1801a3659`
- `msvcrt!_wtoi` at `0x1801a36a0`
- `msvcrt!_wtoi` at `0x1801a36e7`
- `msvcrt!_wtoi` at `0x1801a372e`
- `msvcrt!_wtoi` at `0x1801a3775`
- `msvcrt!_wtoi` at `0x1801a37bc`
- `msvcrt!_wtoi` at `0x1801a3803`
- `msvcrt!_wtoi` at `0x1801a384a`
- `msvcrt!_wtoi` at `0x1801a3891`
- `msvcrt!_wtoi` at `0x1801a38d8`
- `msvcrt!_wtoi` at `0x1801a391f`
- `msvcrt!_wtoi` at `0x1801a3966`
- `msvcrt!_wtoi` at `0x1801a39ad`
- `msvcrt!_wtoi` at `0x1801a39f4`
- `msvcrt!_wtoi` at `0x1801a3a3b`
- `msvcrt!_wtoi` at `0x1801a3a82`
- `msvcrt!_wtoi` at `0x1801a3ac9`
- `msvcrt!_wtoi` at `0x1801a3b10`
- `msvcrt!_wtoi` at `0x1801a3b57`
- `msvcrt!_wtoi` at `0x1801a33da`
- `msvcrt!_wtoi` at `0x1801a3421`
- `msvcrt!_wtoi` at `0x1801a3468`
- `msvcrt!_wtoi` at `0x1801a34af`
- `msvcrt!_wtoi` at `0x1801a34f6`
- `msvcrt!_wtoi` at `0x1801a353d`
- `msvcrt!_wtoi` at `0x1801a3584`
- `msvcrt!_wtoi` at `0x1801a35cb`
- `msvcrt!_wtoi` at `0x1801a3612`
- `msvcrt!_wtoi` at `0x1801a3659`
- `msvcrt!_wtoi` at `0x1801a36a0`
- `msvcrt!_wtoi` at `0x1801a36e7`
- `msvcrt!_wtoi` at `0x1801a372e`
- `msvcrt!_wtoi` at `0x1801a3775`
- `msvcrt!_wtoi` at `0x1801a37bc`
- `msvcrt!_wtoi` at `0x1801a3803`
- `msvcrt!_wtoi` at `0x1801a384a`
- `msvcrt!_wtoi` at `0x1801a3891`
- `msvcrt!_wtoi` at `0x1801a38d8`
- `msvcrt!_wtoi` at `0x1801a391f`
- `msvcrt!_wtoi` at `0x1801a3966`
- `msvcrt!_wtoi` at `0x1801a39ad`
- `msvcrt!_wtoi` at `0x1801a39f4`
- `msvcrt!_wtoi` at `0x1801a3a3b`
- `msvcrt!_wtoi` at `0x1801a3a82`
- `msvcrt!_wtoi` at `0x1801a3ac9`
- `msvcrt!_wtoi` at `0x1801a3b10`
- `msvcrt!_wtoi` at `0x1801a3b57`

## string_xrefs

- `0x1801a3444`: `AllowIMENetworkAccess`
- `0x1801a3635`: `AllowLanguageFeaturesUninstall`
- `0x1801a36c3`: `AllowTextInputSuggestionUpdate`
- `0x1801a370a`: `ConfigureJapaneseIMEVersion`
- `0x1801a3751`: `ConfigureKoreanIMEVersion`
- `0x1801a3798`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1801a37df`: `ConfigureTraditionalChineseIMEVersion`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_TextInput02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r15d
  _QWORD *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-1E8h] BYREF
  char v11; // [rsp+48h] [rbp-1E0h]
  _QWORD *v12; // [rsp+50h] [rbp-1D8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-1D0h] BYREF
  char v14; // [rsp+80h] [rbp-1A8h]
  int v15; // [rsp+88h] [rbp-1A0h] BYREF
  char v16; // [rsp+8Ch] [rbp-19Ch]
  _BYTE v17[16]; // [rsp+90h] [rbp-198h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-188h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-178h] BYREF
  int v20; // [rsp+110h] [rbp-118h]
  char v21; // [rsp+114h] [rbp-114h]
  int v22; // [rsp+118h] [rbp-110h]
  char v23; // [rsp+11Ch] [rbp-10Ch]
  int v24; // [rsp+120h] [rbp-108h]
  char v25; // [rsp+124h] [rbp-104h]
  int v26; // [rsp+128h] [rbp-100h]
  char v27; // [rsp+12Ch] [rbp-FCh]
  int v28; // [rsp+130h] [rbp-F8h]
  char v29; // [rsp+134h] [rbp-F4h]
  int v30; // [rsp+138h] [rbp-F0h]
  char v31; // [rsp+13Ch] [rbp-ECh]
  int v32; // [rsp+140h] [rbp-E8h]
  char v33; // [rsp+144h] [rbp-E4h]
  int v34; // [rsp+148h] [rbp-E0h]
  char v35; // [rsp+14Ch] [rbp-DCh]
  int v36; // [rsp+150h] [rbp-D8h]
  char v37; // [rsp+154h] [rbp-D4h]
  int v38; // [rsp+158h] [rbp-D0h]
  char v39; // [rsp+15Ch] [rbp-CCh]
  int v40; // [rsp+160h] [rbp-C8h]
  char v41; // [rsp+164h] [rbp-C4h]
  int v42; // [rsp+168h] [rbp-C0h]
  char v43; // [rsp+16Ch] [rbp-BCh]
  int v44; // [rsp+170h] [rbp-B8h]
  char v45; // [rsp+174h] [rbp-B4h]
  int v46; // [rsp+178h] [rbp-B0h]
  char v47; // [rsp+17Ch] [rbp-ACh]
  int v48; // [rsp+180h] [rbp-A8h]
  char v49; // [rsp+184h] [rbp-A4h]
  int v50; // [rsp+188h] [rbp-A0h]
  char v51; // [rsp+18Ch] [rbp-9Ch]
  int v52; // [rsp+190h] [rbp-98h]
  char v53; // [rsp+194h] [rbp-94h]
  int v54; // [rsp+198h] [rbp-90h]
  char v55; // [rsp+19Ch] [rbp-8Ch]
  int v56; // [rsp+1A0h] [rbp-88h]
  char v57; // [rsp+1A4h] [rbp-84h]
  int v58; // [rsp+1A8h] [rbp-80h]
  char v59; // [rsp+1ACh] [rbp-7Ch]
  int v60; // [rsp+1B0h] [rbp-78h]
  char v61; // [rsp+1B4h] [rbp-74h]
  int v62; // [rsp+1B8h] [rbp-70h]
  char v63; // [rsp+1BCh] [rbp-6Ch]
  int v64; // [rsp+1C0h] [rbp-68h]
  char v65; // [rsp+1C4h] [rbp-64h]
  int v66; // [rsp+1C8h] [rbp-60h]
  char v67; // [rsp+1CCh] [rbp-5Ch]
  int v68; // [rsp+1D0h] [rbp-58h]
  char v69; // [rsp+1D4h] [rbp-54h]
  int v70; // [rsp+1D8h] [rbp-50h]
  char v71; // [rsp+1DCh] [rbp-4Ch]
  int v72; // [rsp+1E0h] [rbp-48h]
  char v73; // [rsp+1E4h] [rbp-44h]
  int v74; // [rsp+1E8h] [rbp-40h]
  char v75; // [rsp+1ECh] [rbp-3Ch]

  memset_0(&instance, 0, 0x140u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_TextInput02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180339C04,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Result01_TextInput02_NodeList, 30, 2, &v12);
  if ( v6 == MI_RESULT_OK )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_TextInput02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_122;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"TextInput",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
            }
            if ( a2 != 1 )
            {
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowHardwareKeyboardTextSuggestions",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIMELogging",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIMENetworkAccess",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowInputPanel",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseIMESurrogatePairCharacters",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseIVSCharacters",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseNonPublishingStandardGlyph",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseUserDictionary",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowKeyboardTextSuggestions",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLanguageFeaturesUninstall",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLinguisticDataCollection",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowTextInputSuggestionUpdate",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureJapaneseIMEVersion",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureKoreanIMEVersion",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSimplifiedChineseIMEVersion",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTraditionalChineseIMEVersion",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"EnableTouchKeyboardAutoInvokeInDesktopMode",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludeJapaneseIMEExceptJIS0208",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludeJapaneseIMEExceptJIS0208andEUDC",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludeJapaneseIMEExceptShiftJIS",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ForceTouchKeyboardDockedState",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardDictationButtonAvailability",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardEmojiButtonAvailability",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardFullModeAvailability",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardHandwritingModeAvailability",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardNarrowModeAvailability",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardSplitModeAvailability",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardWideModeAvailability",
                      &String)
                && String )
              {
                v74 = _wtoi(String);
                v75 = 1;
              }
            }
            MI_Instance_Destruct((MI_Instance *)self);
            MI_Instance_Destruct(&instance);
            v11 = 0;
          }
          if ( v12 )
          {
            (*(void (__fastcall **)(_QWORD *, __int64))*v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
    }
  }
LABEL_122:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180365725,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801a30c8  mov     [rsp+arg_8], rbx
0x1801a30cd  mov     [rsp+arg_10], rsi
0x1801a30d2  push    rdi
0x1801a30d3  push    r12
0x1801a30d5  push    r13
0x1801a30d7  push    r14
0x1801a30d9  push    r15
0x1801a30db  sub     rsp, 200h
0x1801a30e2  mov     rax, cs:__security_cookie
0x1801a30e9  xor     rax, rsp
0x1801a30ec  mov     [rsp+228h+var_38], rax
0x1801a30f4  mov     r13b, dl
0x1801a30f7  mov     r12, rcx
0x1801a30fa  xor     edx, edx; Val
0x1801a30fc  mov     r8d, 140h; Size
0x1801a3102  lea     rcx, [rsp+228h+instance]; void *
0x1801a310a  call    memset_0
0x1801a310f  xor     edi, edi
0x1801a3111  mov     [rsp+228h+var_1E0], dil
0x1801a3116  mov     [rsp+228h+String], rdi
0x1801a311b  mov     [rsp+228h+var_1A0], edi
0x1801a3122  mov     [rsp+228h+var_19C], dil
0x1801a312a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801a3131  mov     [rsp+228h+var_1D0], rax
0x1801a3136  lea     rax, [rsp+228h+var_1A0]
0x1801a313e  mov     [rsp+228h+var_1C8], rax
0x1801a3143  lea     rax, aMdmPolicyResul_132; "MDM_Policy_Result01_TextInput02"
0x1801a314a  mov     [rsp+228h+var_1C0], rax
0x1801a314f  lea     rcx, [rsp+228h+var_1A0]
0x1801a3157  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801a315c  mov     eax, cs:dword_180380B68
0x1801a3162  cmp     eax, 5
0x1801a3165  jbe     short loc_1801A31D7
0x1801a3167  mov     rdx, 200000000000h
0x1801a3171  lea     rcx, dword_180380B68
0x1801a3178  call    _tlgKeywordOn
0x1801a317d  test    al, al
0x1801a317f  jz      short loc_1801A31D7
0x1801a3181  cmp     [rsp+228h+var_19C], dil
0x1801a3189  jz      short loc_1801A31B9
0x1801a318b  cmp     [rsp+228h+var_188], edi
0x1801a3192  jnz     short loc_1801A31AF
0x1801a3194  cmp     [rsp+228h+var_184], edi
0x1801a319b  jnz     short loc_1801A31AF
0x1801a319d  cmp     [rsp+228h+var_180], edi
0x1801a31a4  jnz     short loc_1801A31AF
0x1801a31a6  cmp     [rsp+228h+var_17C], edi
0x1801a31ad  jz      short loc_1801A31B9
0x1801a31af  lea     r9, [rsp+228h+var_188]
0x1801a31b7  jmp     short loc_1801A31BC
0x1801a31b9  mov     r9, rdi
0x1801a31bc  lea     r8, [rsp+228h+var_198]
0x1801a31c4  lea     rdx, dword_180339C04
0x1801a31cb  lea     rcx, dword_180380B68
0x1801a31d2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801a31d7  lea     rcx, [rsp+228h+var_1D0]; this
0x1801a31dc  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801a31e1  nop
0x1801a31e2  mov     [rsp+228h+var_1D8], rdi
0x1801a31e7  lea     rax, [rsp+228h+var_1D8]
0x1801a31ec  mov     [rsp+228h+var_1F8], rax
0x1801a31f1  mov     [rsp+228h+var_200], 2
0x1801a31f9  mov     [rsp+228h+var_208], 1Eh
0x1801a3201  lea     r9, ?MDM_Policy_Result01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_TextInput02_NodeList
0x1801a3208  xor     r8d, r8d
0x1801a320b  xor     edx, edx
0x1801a320d  mov     rcx, r12
0x1801a3210  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801a3215  mov     r15d, eax
0x1801a3218  test    eax, eax
0x1801a321a  jz      short loc_1801A3221
0x1801a321c  jmp     loc_1801A3BD4
0x1801a3221  lea     rbx, [rsp+228h+var_1D8]
0x1801a3226  mov     [rsp+228h+var_1B0], rbx
0x1801a322b  mov     r14d, 1
0x1801a3231  mov     [rsp+228h+var_1A8], r14b
0x1801a3239  mov     rsi, [rsp+228h+var_1D8]
0x1801a323e  test    rsi, rsi
0x1801a3241  jnz     short loc_1801A324B
0x1801a3243  mov     r15d, r14d
0x1801a3246  jmp     loc_1801A3BD4
0x1801a324b  mov     rax, [rsi]
0x1801a324e  mov     rcx, rsi
0x1801a3251  mov     rax, [rax+10h]
0x1801a3255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a325a  mov     r15d, eax
0x1801a325d  test    eax, eax
0x1801a325f  jz      short loc_1801A327F
0x1801a3261  mov     rcx, [rsp+228h+var_1D8]
0x1801a3266  test    rcx, rcx
0x1801a3269  jz      short loc_1801A327A
0x1801a326b  mov     rax, [rcx]
0x1801a326e  mov     edx, r14d
0x1801a3271  mov     rax, [rax]
0x1801a3274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3279  nop
0x1801a327a  jmp     loc_1801A3BD4
0x1801a327f  mov     rax, [rsi]
0x1801a3282  mov     rcx, rsi
0x1801a3285  mov     rax, [rax+8]
0x1801a3289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a328e  mov     r15d, eax
0x1801a3291  test    eax, eax
0x1801a3293  jz      short loc_1801A32B3
0x1801a3295  mov     rcx, [rsp+228h+var_1D8]
0x1801a329a  test    rcx, rcx
0x1801a329d  jz      short loc_1801A32AE
0x1801a329f  mov     rax, [rcx]
0x1801a32a2  mov     edx, r14d
0x1801a32a5  mov     rax, [rax]
0x1801a32a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a32ad  nop
0x1801a32ae  jmp     loc_1801A3BD4
0x1801a32b3  mov     r14d, edi
0x1801a32b6  mov     rax, [rsi+108h]
0x1801a32bd  sub     rax, [rsi+100h]
0x1801a32c4  sar     rax, 4
0x1801a32c8  cmp     r14d, eax
0x1801a32cb  jnb     loc_1801A3B9C
0x1801a32d1  lea     r8, [rsp+228h+instance]; instance
0x1801a32d9  lea     rdx, MDM_Policy_Result01_TextInput02_rtti; classDecl
0x1801a32e0  mov     rcx, r12; context
0x1801a32e3  call    MI_Context_ConstructInstance
0x1801a32e8  mov     r15d, eax
0x1801a32eb  test    eax, eax
0x1801a32ed  jz      short loc_1801A330F
0x1801a32ef  mov     rcx, [rbx]
0x1801a32f2  test    rcx, rcx
0x1801a32f5  jz      short loc_1801A330A
0x1801a32f7  mov     rax, [rcx]
0x1801a32fa  mov     edx, 1
0x1801a32ff  mov     rax, [rax]
0x1801a3302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3307  mov     [rbx], rdi
0x1801a330a  jmp     loc_1801A3BD4
0x1801a330f  mov     [rsp+228h+var_1E0], 1
0x1801a3314  mov     rax, [rsi]
0x1801a3317  lea     r9, [rsp+228h+String]
0x1801a331c  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801a3323  mov     edx, r14d
0x1801a3326  mov     rcx, rsi
0x1801a3329  mov     rax, [rax+18h]
0x1801a332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3332  test    eax, eax
0x1801a3334  jnz     short loc_1801A334D
0x1801a3336  mov     rdx, [rsp+228h+String]
0x1801a333b  test    rdx, rdx
0x1801a333e  jz      short loc_1801A334D
0x1801a3340  lea     rcx, [rsp+228h+instance]
0x1801a3348  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801a334d  mov     rax, [rsi]
0x1801a3350  lea     r9, [rsp+228h+String]
0x1801a3355  lea     r8, aTextinput; "TextInput"
0x1801a335c  mov     edx, r14d
0x1801a335f  mov     rcx, rsi
0x1801a3362  mov     rax, [rax+18h]
0x1801a3366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a336b  test    eax, eax
0x1801a336d  jnz     short loc_1801A3386
0x1801a336f  mov     rdx, [rsp+228h+String]
0x1801a3374  test    rdx, rdx
0x1801a3377  jz      short loc_1801A3386
0x1801a3379  lea     rcx, [rsp+228h+instance]
0x1801a3381  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801a3386  cmp     r13b, 1
0x1801a338a  jnz     short loc_1801A33AE
0x1801a338c  lea     rdx, [rsp+228h+instance]
0x1801a3394  mov     rcx, r12; self
0x1801a3397  call    MI_Instance_Destruct
0x1801a339c  lea     rcx, [rsp+228h+instance]; self
0x1801a33a4  call    MI_Instance_Destruct
0x1801a33a9  jmp     loc_1801A3B8F
0x1801a33ae  mov     rax, [rsi]
0x1801a33b1  lea     r9, [rsp+228h+String]
0x1801a33b6  lea     r8, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1801a33bd  mov     edx, r14d
0x1801a33c0  mov     rcx, rsi
0x1801a33c3  mov     rax, [rax+18h]
0x1801a33c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a33cc  test    eax, eax
0x1801a33ce  jnz     short loc_1801A33F5
0x1801a33d0  mov     rcx, [rsp+228h+String]; String
0x1801a33d5  test    rcx, rcx
0x1801a33d8  jz      short loc_1801A33F5
0x1801a33da  call    cs:__imp__wtoi
0x1801a33e1  nop     dword ptr [rax+rax+00h]
0x1801a33e6  mov     [rsp+228h+var_118], eax
0x1801a33ed  mov     [rsp+228h+var_114], 1
0x1801a33f5  mov     rax, [rsi]
0x1801a33f8  lea     r9, [rsp+228h+String]
0x1801a33fd  lea     r8, aAllowimeloggin; "AllowIMELogging"
0x1801a3404  mov     edx, r14d
0x1801a3407  mov     rcx, rsi
0x1801a340a  mov     rax, [rax+18h]
0x1801a340e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3413  test    eax, eax
0x1801a3415  jnz     short loc_1801A343C
0x1801a3417  mov     rcx, [rsp+228h+String]; String
0x1801a341c  test    rcx, rcx
0x1801a341f  jz      short loc_1801A343C
0x1801a3421  call    cs:__imp__wtoi
0x1801a3428  nop     dword ptr [rax+rax+00h]
0x1801a342d  mov     [rsp+228h+var_110], eax
0x1801a3434  mov     [rsp+228h+var_10C], 1
0x1801a343c  mov     rax, [rsi]
0x1801a343f  lea     r9, [rsp+228h+String]
0x1801a3444  lea     r8, aAllowimenetwor; "AllowIMENetworkAccess"
0x1801a344b  mov     edx, r14d
0x1801a344e  mov     rcx, rsi
0x1801a3451  mov     rax, [rax+18h]
0x1801a3455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a345a  test    eax, eax
0x1801a345c  jnz     short loc_1801A3483
0x1801a345e  mov     rcx, [rsp+228h+String]; String
0x1801a3463  test    rcx, rcx
0x1801a3466  jz      short loc_1801A3483
0x1801a3468  call    cs:__imp__wtoi
0x1801a346f  nop     dword ptr [rax+rax+00h]
0x1801a3474  mov     [rsp+228h+var_108], eax
0x1801a347b  mov     [rsp+228h+var_104], 1
0x1801a3483  mov     rax, [rsi]
0x1801a3486  lea     r9, [rsp+228h+String]
0x1801a348b  lea     r8, aAllowinputpane; "AllowInputPanel"
0x1801a3492  mov     edx, r14d
0x1801a3495  mov     rcx, rsi
0x1801a3498  mov     rax, [rax+18h]
0x1801a349c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a34a1  test    eax, eax
0x1801a34a3  jnz     short loc_1801A34CA
0x1801a34a5  mov     rcx, [rsp+228h+String]; String
0x1801a34aa  test    rcx, rcx
0x1801a34ad  jz      short loc_1801A34CA
0x1801a34af  call    cs:__imp__wtoi
0x1801a34b6  nop     dword ptr [rax+rax+00h]
0x1801a34bb  mov     [rsp+228h+var_100], eax
0x1801a34c2  mov     [rsp+228h+var_FC], 1
0x1801a34ca  mov     rax, [rsi]
0x1801a34cd  lea     r9, [rsp+228h+String]
0x1801a34d2  lea     r8, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1801a34d9  mov     edx, r14d
0x1801a34dc  mov     rcx, rsi
0x1801a34df  mov     rax, [rax+18h]
0x1801a34e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a34e8  test    eax, eax
0x1801a34ea  jnz     short loc_1801A3511
0x1801a34ec  mov     rcx, [rsp+228h+String]; String
0x1801a34f1  test    rcx, rcx
0x1801a34f4  jz      short loc_1801A3511
0x1801a34f6  call    cs:__imp__wtoi
0x1801a34fd  nop     dword ptr [rax+rax+00h]
0x1801a3502  mov     [rsp+228h+var_F8], eax
0x1801a3509  mov     [rsp+228h+var_F4], 1
0x1801a3511  mov     rax, [rsi]
0x1801a3514  lea     r9, [rsp+228h+String]
0x1801a3519  lea     r8, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1801a3520  mov     edx, r14d
0x1801a3523  mov     rcx, rsi
0x1801a3526  mov     rax, [rax+18h]
0x1801a352a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a352f  test    eax, eax
0x1801a3531  jnz     short loc_1801A3558
0x1801a3533  mov     rcx, [rsp+228h+String]; String
0x1801a3538  test    rcx, rcx
0x1801a353b  jz      short loc_1801A3558
0x1801a353d  call    cs:__imp__wtoi
0x1801a3544  nop     dword ptr [rax+rax+00h]
0x1801a3549  mov     [rsp+228h+var_F0], eax
0x1801a3550  mov     [rsp+228h+var_EC], 1
0x1801a3558  mov     rax, [rsi]
0x1801a355b  lea     r9, [rsp+228h+String]
0x1801a3560  lea     r8, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1801a3567  mov     edx, r14d
0x1801a356a  mov     rcx, rsi
0x1801a356d  mov     rax, [rax+18h]
0x1801a3571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3576  test    eax, eax
0x1801a3578  jnz     short loc_1801A359F
0x1801a357a  mov     rcx, [rsp+228h+String]; String
0x1801a357f  test    rcx, rcx
0x1801a3582  jz      short loc_1801A359F
0x1801a3584  call    cs:__imp__wtoi
0x1801a358b  nop     dword ptr [rax+rax+00h]
0x1801a3590  mov     [rsp+228h+var_E8], eax
0x1801a3597  mov     [rsp+228h+var_E4], 1
0x1801a359f  mov     rax, [rsi]
0x1801a35a2  lea     r9, [rsp+228h+String]
0x1801a35a7  lea     r8, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1801a35ae  mov     edx, r14d
0x1801a35b1  mov     rcx, rsi
0x1801a35b4  mov     rax, [rax+18h]
0x1801a35b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a35bd  test    eax, eax
0x1801a35bf  jnz     short loc_1801A35E6
0x1801a35c1  mov     rcx, [rsp+228h+String]; String
0x1801a35c6  test    rcx, rcx
0x1801a35c9  jz      short loc_1801A35E6
0x1801a35cb  call    cs:__imp__wtoi
0x1801a35d2  nop     dword ptr [rax+rax+00h]
0x1801a35d7  mov     [rsp+228h+var_E0], eax
0x1801a35de  mov     [rsp+228h+var_DC], 1
  ... truncated ...
```
