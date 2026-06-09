# MDM_Policy_Result01_TextInput02_InvokeEnumerateInstances

- ea: `0x1801a35c4`
- end: `0x1801a40c8`
- name: `MDM_Policy_Result01_TextInput02_InvokeEnumerateInstances`
- size: `2820`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1801a2840`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801a35c4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801a38d6`
- `msvcrt!_wtoi` at `0x1801a3917`
- `msvcrt!_wtoi` at `0x1801a3958`
- `msvcrt!_wtoi` at `0x1801a3999`
- `msvcrt!_wtoi` at `0x1801a39da`
- `msvcrt!_wtoi` at `0x1801a3a1b`
- `msvcrt!_wtoi` at `0x1801a3a5c`
- `msvcrt!_wtoi` at `0x1801a3a9d`
- `msvcrt!_wtoi` at `0x1801a3ade`
- `msvcrt!_wtoi` at `0x1801a3b1f`
- `msvcrt!_wtoi` at `0x1801a3b60`
- `msvcrt!_wtoi` at `0x1801a3ba1`
- `msvcrt!_wtoi` at `0x1801a3be2`
- `msvcrt!_wtoi` at `0x1801a3c23`
- `msvcrt!_wtoi` at `0x1801a3c64`
- `msvcrt!_wtoi` at `0x1801a3ca5`
- `msvcrt!_wtoi` at `0x1801a3ce6`
- `msvcrt!_wtoi` at `0x1801a3d27`
- `msvcrt!_wtoi` at `0x1801a3d68`
- `msvcrt!_wtoi` at `0x1801a3da9`
- `msvcrt!_wtoi` at `0x1801a3dea`
- `msvcrt!_wtoi` at `0x1801a3e2b`
- `msvcrt!_wtoi` at `0x1801a3e6c`
- `msvcrt!_wtoi` at `0x1801a3ead`
- `msvcrt!_wtoi` at `0x1801a3eee`
- `msvcrt!_wtoi` at `0x1801a3f2f`
- `msvcrt!_wtoi` at `0x1801a3f70`
- `msvcrt!_wtoi` at `0x1801a3fb1`
- `msvcrt!_wtoi` at `0x1801a38d6`
- `msvcrt!_wtoi` at `0x1801a3917`
- `msvcrt!_wtoi` at `0x1801a3958`
- `msvcrt!_wtoi` at `0x1801a3999`
- `msvcrt!_wtoi` at `0x1801a39da`
- `msvcrt!_wtoi` at `0x1801a3a1b`
- `msvcrt!_wtoi` at `0x1801a3a5c`
- `msvcrt!_wtoi` at `0x1801a3a9d`
- `msvcrt!_wtoi` at `0x1801a3ade`
- `msvcrt!_wtoi` at `0x1801a3b1f`
- `msvcrt!_wtoi` at `0x1801a3b60`
- `msvcrt!_wtoi` at `0x1801a3ba1`
- `msvcrt!_wtoi` at `0x1801a3be2`
- `msvcrt!_wtoi` at `0x1801a3c23`
- `msvcrt!_wtoi` at `0x1801a3c64`
- `msvcrt!_wtoi` at `0x1801a3ca5`
- `msvcrt!_wtoi` at `0x1801a3ce6`
- `msvcrt!_wtoi` at `0x1801a3d27`
- `msvcrt!_wtoi` at `0x1801a3d68`
- `msvcrt!_wtoi` at `0x1801a3da9`
- `msvcrt!_wtoi` at `0x1801a3dea`
- `msvcrt!_wtoi` at `0x1801a3e2b`
- `msvcrt!_wtoi` at `0x1801a3e6c`
- `msvcrt!_wtoi` at `0x1801a3ead`
- `msvcrt!_wtoi` at `0x1801a3eee`
- `msvcrt!_wtoi` at `0x1801a3f2f`
- `msvcrt!_wtoi` at `0x1801a3f70`
- `msvcrt!_wtoi` at `0x1801a3fb1`

## string_xrefs

- `0x1801a3934`: `AllowIMENetworkAccess`
- `0x1801a3afb`: `AllowLanguageFeaturesUninstall`
- `0x1801a3b7d`: `AllowTextInputSuggestionUpdate`
- `0x1801a3bbe`: `ConfigureJapaneseIMEVersion`
- `0x1801a3bff`: `ConfigureKoreanIMEVersion`
- `0x1801a3c40`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1801a3c81`: `ConfigureTraditionalChineseIMEVersion`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_TextInput02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-1E8h] BYREF
  char v11; // [rsp+48h] [rbp-1E0h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-1D8h] BYREF
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
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_TextInput02_NodeList,
         0x1Eu,
         2,
         &v12);
  if ( !v6 )
  {
    v13[4] = &v12;
    v14 = 1;
    v7 = v12;
    if ( v12 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v6 )
      {
        if ( v12 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v12 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_TextInput02_rtti, &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_122;
            }
            v11 = 1;
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowHardwareKeyboardTextSuggestions",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIMELogging",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowIMENetworkAccess",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowInputPanel",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseIMESurrogatePairCharacters",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseIVSCharacters",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseNonPublishingStandardGlyph",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowJapaneseUserDictionary",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowKeyboardTextSuggestions",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLanguageFeaturesUninstall",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowLinguisticDataCollection",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowTextInputSuggestionUpdate",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureJapaneseIMEVersion",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureKoreanIMEVersion",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureSimplifiedChineseIMEVersion",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTraditionalChineseIMEVersion",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableTouchKeyboardAutoInvokeInDesktopMode",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludeJapaneseIMEExceptJIS0208",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludeJapaneseIMEExceptJIS0208andEUDC",
                      &String)
                && String )
              {
                v56 = _wtoi(String);
                v57 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ExcludeJapaneseIMEExceptShiftJIS",
                      &String)
                && String )
              {
                v58 = _wtoi(String);
                v59 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ForceTouchKeyboardDockedState",
                      &String)
                && String )
              {
                v60 = _wtoi(String);
                v61 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardDictationButtonAvailability",
                      &String)
                && String )
              {
                v62 = _wtoi(String);
                v63 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardEmojiButtonAvailability",
                      &String)
                && String )
              {
                v64 = _wtoi(String);
                v65 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardFullModeAvailability",
                      &String)
                && String )
              {
                v66 = _wtoi(String);
                v67 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardHandwritingModeAvailability",
                      &String)
                && String )
              {
                v68 = _wtoi(String);
                v69 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardNarrowModeAvailability",
                      &String)
                && String )
              {
                v70 = _wtoi(String);
                v71 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"TouchKeyboardSplitModeAvailability",
                      &String)
                && String )
              {
                v72 = _wtoi(String);
                v73 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
            v12 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
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
  return v6;
}

```

## disassembly

```asm
0x1801a35c4  mov     [rsp+arg_8], rbx
0x1801a35c9  mov     [rsp+arg_10], rsi
0x1801a35ce  push    rdi
0x1801a35cf  push    r12
0x1801a35d1  push    r13
0x1801a35d3  push    r14
0x1801a35d5  push    r15
0x1801a35d7  sub     rsp, 200h
0x1801a35de  mov     rax, cs:__security_cookie
0x1801a35e5  xor     rax, rsp
0x1801a35e8  mov     [rsp+228h+var_38], rax
0x1801a35f0  mov     r13b, dl
0x1801a35f3  mov     r12, rcx
0x1801a35f6  xor     edx, edx; Val
0x1801a35f8  mov     r8d, 140h; Size
0x1801a35fe  lea     rcx, [rsp+228h+instance]; void *
0x1801a3606  call    memset_0
0x1801a360b  xor     edi, edi
0x1801a360d  mov     [rsp+228h+var_1E0], dil
0x1801a3612  mov     [rsp+228h+String], rdi
0x1801a3617  mov     [rsp+228h+var_1A0], edi
0x1801a361e  mov     [rsp+228h+var_19C], dil
0x1801a3626  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801a362d  mov     [rsp+228h+var_1D0], rax
0x1801a3632  lea     rax, [rsp+228h+var_1A0]
0x1801a363a  mov     [rsp+228h+var_1C8], rax
0x1801a363f  lea     rax, aMdmPolicyResul_132; "MDM_Policy_Result01_TextInput02"
0x1801a3646  mov     [rsp+228h+var_1C0], rax
0x1801a364b  lea     rcx, [rsp+228h+var_1A0]
0x1801a3653  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801a3658  mov     eax, cs:dword_180380B68
0x1801a365e  cmp     eax, 5
0x1801a3661  jbe     short loc_1801A36D3
0x1801a3663  mov     rdx, 200000000000h
0x1801a366d  lea     rcx, dword_180380B68
0x1801a3674  call    _tlgKeywordOn
0x1801a3679  test    al, al
0x1801a367b  jz      short loc_1801A36D3
0x1801a367d  cmp     [rsp+228h+var_19C], dil
0x1801a3685  jz      short loc_1801A36B5
0x1801a3687  cmp     [rsp+228h+var_188], edi
0x1801a368e  jnz     short loc_1801A36AB
0x1801a3690  cmp     [rsp+228h+var_184], edi
0x1801a3697  jnz     short loc_1801A36AB
0x1801a3699  cmp     [rsp+228h+var_180], edi
0x1801a36a0  jnz     short loc_1801A36AB
0x1801a36a2  cmp     [rsp+228h+var_17C], edi
0x1801a36a9  jz      short loc_1801A36B5
0x1801a36ab  lea     r9, [rsp+228h+var_188]
0x1801a36b3  jmp     short loc_1801A36B8
0x1801a36b5  mov     r9, rdi
0x1801a36b8  lea     r8, [rsp+228h+var_198]
0x1801a36c0  lea     rdx, dword_180339C04
0x1801a36c7  lea     rcx, dword_180380B68
0x1801a36ce  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801a36d3  lea     rcx, [rsp+228h+var_1D0]; this
0x1801a36d8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801a36dd  nop
0x1801a36de  mov     [rsp+228h+var_1D8], rdi
0x1801a36e3  lea     rax, [rsp+228h+var_1D8]
0x1801a36e8  mov     [rsp+228h+var_1F8], rax
0x1801a36ed  mov     [rsp+228h+var_200], 2
0x1801a36f5  mov     [rsp+228h+var_208], 1Eh
0x1801a36fd  lea     r9, ?MDM_Policy_Result01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_TextInput02_NodeList
0x1801a3704  xor     r8d, r8d
0x1801a3707  xor     edx, edx
0x1801a3709  mov     rcx, r12
0x1801a370c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801a3711  mov     r15d, eax
0x1801a3714  test    eax, eax
0x1801a3716  jz      short loc_1801A371D
0x1801a3718  jmp     loc_1801A4028
0x1801a371d  lea     rbx, [rsp+228h+var_1D8]
0x1801a3722  mov     [rsp+228h+var_1B0], rbx
0x1801a3727  mov     r14d, 1
0x1801a372d  mov     [rsp+228h+var_1A8], r14b
0x1801a3735  mov     rsi, [rsp+228h+var_1D8]
0x1801a373a  test    rsi, rsi
0x1801a373d  jnz     short loc_1801A3747
0x1801a373f  mov     r15d, r14d
0x1801a3742  jmp     loc_1801A4028
0x1801a3747  mov     rax, [rsi]
0x1801a374a  mov     rcx, rsi
0x1801a374d  mov     rax, [rax+10h]
0x1801a3751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3756  mov     r15d, eax
0x1801a3759  test    eax, eax
0x1801a375b  jz      short loc_1801A377B
0x1801a375d  mov     rcx, [rsp+228h+var_1D8]
0x1801a3762  test    rcx, rcx
0x1801a3765  jz      short loc_1801A3776
0x1801a3767  mov     rax, [rcx]
0x1801a376a  mov     edx, r14d
0x1801a376d  mov     rax, [rax]
0x1801a3770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3775  nop
0x1801a3776  jmp     loc_1801A4028
0x1801a377b  mov     rax, [rsi]
0x1801a377e  mov     rcx, rsi
0x1801a3781  mov     rax, [rax+8]
0x1801a3785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a378a  mov     r15d, eax
0x1801a378d  test    eax, eax
0x1801a378f  jz      short loc_1801A37AF
0x1801a3791  mov     rcx, [rsp+228h+var_1D8]
0x1801a3796  test    rcx, rcx
0x1801a3799  jz      short loc_1801A37AA
0x1801a379b  mov     rax, [rcx]
0x1801a379e  mov     edx, r14d
0x1801a37a1  mov     rax, [rax]
0x1801a37a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a37a9  nop
0x1801a37aa  jmp     loc_1801A4028
0x1801a37af  mov     r14d, edi
0x1801a37b2  mov     rax, [rsi+108h]
0x1801a37b9  sub     rax, [rsi+100h]
0x1801a37c0  sar     rax, 4
0x1801a37c4  cmp     r14d, eax
0x1801a37c7  jnb     loc_1801A3FF0
0x1801a37cd  lea     r8, [rsp+228h+instance]; instance
0x1801a37d5  lea     rdx, MDM_Policy_Result01_TextInput02_rtti; classDecl
0x1801a37dc  mov     rcx, r12; context
0x1801a37df  call    MI_Context_ConstructInstance
0x1801a37e4  mov     r15d, eax
0x1801a37e7  test    eax, eax
0x1801a37e9  jz      short loc_1801A380B
0x1801a37eb  mov     rcx, [rbx]
0x1801a37ee  test    rcx, rcx
0x1801a37f1  jz      short loc_1801A3806
0x1801a37f3  mov     rax, [rcx]
0x1801a37f6  mov     edx, 1
0x1801a37fb  mov     rax, [rax]
0x1801a37fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3803  mov     [rbx], rdi
0x1801a3806  jmp     loc_1801A4028
0x1801a380b  mov     [rsp+228h+var_1E0], 1
0x1801a3810  mov     rax, [rsi]
0x1801a3813  lea     r9, [rsp+228h+String]
0x1801a3818  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801a381f  mov     edx, r14d
0x1801a3822  mov     rcx, rsi
0x1801a3825  mov     rax, [rax+18h]
0x1801a3829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a382e  test    eax, eax
0x1801a3830  jnz     short loc_1801A3849
0x1801a3832  mov     rdx, [rsp+228h+String]
0x1801a3837  test    rdx, rdx
0x1801a383a  jz      short loc_1801A3849
0x1801a383c  lea     rcx, [rsp+228h+instance]
0x1801a3844  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801a3849  mov     rax, [rsi]
0x1801a384c  lea     r9, [rsp+228h+String]
0x1801a3851  lea     r8, aTextinput; "TextInput"
0x1801a3858  mov     edx, r14d
0x1801a385b  mov     rcx, rsi
0x1801a385e  mov     rax, [rax+18h]
0x1801a3862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3867  test    eax, eax
0x1801a3869  jnz     short loc_1801A3882
0x1801a386b  mov     rdx, [rsp+228h+String]
0x1801a3870  test    rdx, rdx
0x1801a3873  jz      short loc_1801A3882
0x1801a3875  lea     rcx, [rsp+228h+instance]
0x1801a387d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801a3882  cmp     r13b, 1
0x1801a3886  jnz     short loc_1801A38AA
0x1801a3888  lea     rdx, [rsp+228h+instance]
0x1801a3890  mov     rcx, r12; self
0x1801a3893  call    MI_Instance_Destruct
0x1801a3898  lea     rcx, [rsp+228h+instance]; self
0x1801a38a0  call    MI_Instance_Destruct
0x1801a38a5  jmp     loc_1801A3FE3
0x1801a38aa  mov     rax, [rsi]
0x1801a38ad  lea     r9, [rsp+228h+String]
0x1801a38b2  lea     r8, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1801a38b9  mov     edx, r14d
0x1801a38bc  mov     rcx, rsi
0x1801a38bf  mov     rax, [rax+18h]
0x1801a38c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a38c8  test    eax, eax
0x1801a38ca  jnz     short loc_1801A38EB
0x1801a38cc  mov     rcx, [rsp+228h+String]; String
0x1801a38d1  test    rcx, rcx
0x1801a38d4  jz      short loc_1801A38EB
0x1801a38d6  call    cs:__imp__wtoi
0x1801a38dc  mov     [rsp+228h+var_118], eax
0x1801a38e3  mov     [rsp+228h+var_114], 1
0x1801a38eb  mov     rax, [rsi]
0x1801a38ee  lea     r9, [rsp+228h+String]
0x1801a38f3  lea     r8, aAllowimeloggin; "AllowIMELogging"
0x1801a38fa  mov     edx, r14d
0x1801a38fd  mov     rcx, rsi
0x1801a3900  mov     rax, [rax+18h]
0x1801a3904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3909  test    eax, eax
0x1801a390b  jnz     short loc_1801A392C
0x1801a390d  mov     rcx, [rsp+228h+String]; String
0x1801a3912  test    rcx, rcx
0x1801a3915  jz      short loc_1801A392C
0x1801a3917  call    cs:__imp__wtoi
0x1801a391d  mov     [rsp+228h+var_110], eax
0x1801a3924  mov     [rsp+228h+var_10C], 1
0x1801a392c  mov     rax, [rsi]
0x1801a392f  lea     r9, [rsp+228h+String]
0x1801a3934  lea     r8, aAllowimenetwor; "AllowIMENetworkAccess"
0x1801a393b  mov     edx, r14d
0x1801a393e  mov     rcx, rsi
0x1801a3941  mov     rax, [rax+18h]
0x1801a3945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a394a  test    eax, eax
0x1801a394c  jnz     short loc_1801A396D
0x1801a394e  mov     rcx, [rsp+228h+String]; String
0x1801a3953  test    rcx, rcx
0x1801a3956  jz      short loc_1801A396D
0x1801a3958  call    cs:__imp__wtoi
0x1801a395e  mov     [rsp+228h+var_108], eax
0x1801a3965  mov     [rsp+228h+var_104], 1
0x1801a396d  mov     rax, [rsi]
0x1801a3970  lea     r9, [rsp+228h+String]
0x1801a3975  lea     r8, aAllowinputpane; "AllowInputPanel"
0x1801a397c  mov     edx, r14d
0x1801a397f  mov     rcx, rsi
0x1801a3982  mov     rax, [rax+18h]
0x1801a3986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a398b  test    eax, eax
0x1801a398d  jnz     short loc_1801A39AE
0x1801a398f  mov     rcx, [rsp+228h+String]; String
0x1801a3994  test    rcx, rcx
0x1801a3997  jz      short loc_1801A39AE
0x1801a3999  call    cs:__imp__wtoi
0x1801a399f  mov     [rsp+228h+var_100], eax
0x1801a39a6  mov     [rsp+228h+var_FC], 1
0x1801a39ae  mov     rax, [rsi]
0x1801a39b1  lea     r9, [rsp+228h+String]
0x1801a39b6  lea     r8, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1801a39bd  mov     edx, r14d
0x1801a39c0  mov     rcx, rsi
0x1801a39c3  mov     rax, [rax+18h]
0x1801a39c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a39cc  test    eax, eax
0x1801a39ce  jnz     short loc_1801A39EF
0x1801a39d0  mov     rcx, [rsp+228h+String]; String
0x1801a39d5  test    rcx, rcx
0x1801a39d8  jz      short loc_1801A39EF
0x1801a39da  call    cs:__imp__wtoi
0x1801a39e0  mov     [rsp+228h+var_F8], eax
0x1801a39e7  mov     [rsp+228h+var_F4], 1
0x1801a39ef  mov     rax, [rsi]
0x1801a39f2  lea     r9, [rsp+228h+String]
0x1801a39f7  lea     r8, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1801a39fe  mov     edx, r14d
0x1801a3a01  mov     rcx, rsi
0x1801a3a04  mov     rax, [rax+18h]
0x1801a3a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3a0d  test    eax, eax
0x1801a3a0f  jnz     short loc_1801A3A30
0x1801a3a11  mov     rcx, [rsp+228h+String]; String
0x1801a3a16  test    rcx, rcx
0x1801a3a19  jz      short loc_1801A3A30
0x1801a3a1b  call    cs:__imp__wtoi
0x1801a3a21  mov     [rsp+228h+var_F0], eax
0x1801a3a28  mov     [rsp+228h+var_EC], 1
0x1801a3a30  mov     rax, [rsi]
0x1801a3a33  lea     r9, [rsp+228h+String]
0x1801a3a38  lea     r8, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1801a3a3f  mov     edx, r14d
0x1801a3a42  mov     rcx, rsi
0x1801a3a45  mov     rax, [rax+18h]
0x1801a3a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3a4e  test    eax, eax
0x1801a3a50  jnz     short loc_1801A3A71
0x1801a3a52  mov     rcx, [rsp+228h+String]; String
0x1801a3a57  test    rcx, rcx
0x1801a3a5a  jz      short loc_1801A3A71
0x1801a3a5c  call    cs:__imp__wtoi
0x1801a3a62  mov     [rsp+228h+var_E8], eax
0x1801a3a69  mov     [rsp+228h+var_E4], 1
0x1801a3a71  mov     rax, [rsi]
0x1801a3a74  lea     r9, [rsp+228h+String]
0x1801a3a79  lea     r8, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1801a3a80  mov     edx, r14d
0x1801a3a83  mov     rcx, rsi
0x1801a3a86  mov     rax, [rax+18h]
0x1801a3a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3a8f  test    eax, eax
0x1801a3a91  jnz     short loc_1801A3AB2
0x1801a3a93  mov     rcx, [rsp+228h+String]; String
0x1801a3a98  test    rcx, rcx
0x1801a3a9b  jz      short loc_1801A3AB2
0x1801a3a9d  call    cs:__imp__wtoi
0x1801a3aa3  mov     [rsp+228h+var_E0], eax
0x1801a3aaa  mov     [rsp+228h+var_DC], 1
0x1801a3ab2  mov     rax, [rsi]
0x1801a3ab5  lea     r9, [rsp+228h+String]
0x1801a3aba  lea     r8, aAllowkeyboardt; "AllowKeyboardTextSuggestions"
0x1801a3ac1  mov     edx, r14d
0x1801a3ac4  mov     rcx, rsi
0x1801a3ac7  mov     rax, [rax+18h]
0x1801a3acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3ad0  test    eax, eax
  ... truncated ...
```
