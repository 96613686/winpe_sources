# MDM_Policy_Config01_TextInput02_InvokeEnumerateInstances

- ea: `0x1800ec204`
- end: `0x1800ecd08`
- name: `MDM_Policy_Config01_TextInput02_InvokeEnumerateInstances`
- size: `2820`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800eb480`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800ec204`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800ec516`
- `msvcrt!_wtoi` at `0x1800ec557`
- `msvcrt!_wtoi` at `0x1800ec598`
- `msvcrt!_wtoi` at `0x1800ec5d9`
- `msvcrt!_wtoi` at `0x1800ec61a`
- `msvcrt!_wtoi` at `0x1800ec65b`
- `msvcrt!_wtoi` at `0x1800ec69c`
- `msvcrt!_wtoi` at `0x1800ec6dd`
- `msvcrt!_wtoi` at `0x1800ec71e`
- `msvcrt!_wtoi` at `0x1800ec75f`
- `msvcrt!_wtoi` at `0x1800ec7a0`
- `msvcrt!_wtoi` at `0x1800ec7e1`
- `msvcrt!_wtoi` at `0x1800ec822`
- `msvcrt!_wtoi` at `0x1800ec863`
- `msvcrt!_wtoi` at `0x1800ec8a4`
- `msvcrt!_wtoi` at `0x1800ec8e5`
- `msvcrt!_wtoi` at `0x1800ec926`
- `msvcrt!_wtoi` at `0x1800ec967`
- `msvcrt!_wtoi` at `0x1800ec9a8`
- `msvcrt!_wtoi` at `0x1800ec9e9`
- `msvcrt!_wtoi` at `0x1800eca2a`
- `msvcrt!_wtoi` at `0x1800eca6b`
- `msvcrt!_wtoi` at `0x1800ecaac`
- `msvcrt!_wtoi` at `0x1800ecaed`
- `msvcrt!_wtoi` at `0x1800ecb2e`
- `msvcrt!_wtoi` at `0x1800ecb6f`
- `msvcrt!_wtoi` at `0x1800ecbb0`
- `msvcrt!_wtoi` at `0x1800ecbf1`
- `msvcrt!_wtoi` at `0x1800ec516`
- `msvcrt!_wtoi` at `0x1800ec557`
- `msvcrt!_wtoi` at `0x1800ec598`
- `msvcrt!_wtoi` at `0x1800ec5d9`
- `msvcrt!_wtoi` at `0x1800ec61a`
- `msvcrt!_wtoi` at `0x1800ec65b`
- `msvcrt!_wtoi` at `0x1800ec69c`
- `msvcrt!_wtoi` at `0x1800ec6dd`
- `msvcrt!_wtoi` at `0x1800ec71e`
- `msvcrt!_wtoi` at `0x1800ec75f`
- `msvcrt!_wtoi` at `0x1800ec7a0`
- `msvcrt!_wtoi` at `0x1800ec7e1`
- `msvcrt!_wtoi` at `0x1800ec822`
- `msvcrt!_wtoi` at `0x1800ec863`
- `msvcrt!_wtoi` at `0x1800ec8a4`
- `msvcrt!_wtoi` at `0x1800ec8e5`
- `msvcrt!_wtoi` at `0x1800ec926`
- `msvcrt!_wtoi` at `0x1800ec967`
- `msvcrt!_wtoi` at `0x1800ec9a8`
- `msvcrt!_wtoi` at `0x1800ec9e9`
- `msvcrt!_wtoi` at `0x1800eca2a`
- `msvcrt!_wtoi` at `0x1800eca6b`
- `msvcrt!_wtoi` at `0x1800ecaac`
- `msvcrt!_wtoi` at `0x1800ecaed`
- `msvcrt!_wtoi` at `0x1800ecb2e`
- `msvcrt!_wtoi` at `0x1800ecb6f`
- `msvcrt!_wtoi` at `0x1800ecbb0`
- `msvcrt!_wtoi` at `0x1800ecbf1`

## string_xrefs

- `0x1800ec574`: `AllowIMENetworkAccess`
- `0x1800ec73b`: `AllowLanguageFeaturesUninstall`
- `0x1800ec7bd`: `AllowTextInputSuggestionUpdate`
- `0x1800ec7fe`: `ConfigureJapaneseIMEVersion`
- `0x1800ec83f`: `ConfigureKoreanIMEVersion`
- `0x1800ec880`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1800ec8c1`: `ConfigureTraditionalChineseIMEVersion`
- `0x1800ec458`: `./Vendor/MSFT/Policy/Config`
- `0x1800ec27f`: `MDM_Policy_Config01_TextInput02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_TextInput02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1E8h] BYREF
  char v14; // [rsp+48h] [rbp-1E0h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-1D8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-1D0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-1B8h] BYREF
  char v18; // [rsp+80h] [rbp-1A8h]
  int v19; // [rsp+88h] [rbp-1A0h] BYREF
  char v20; // [rsp+8Ch] [rbp-19Ch]
  _BYTE v21[16]; // [rsp+90h] [rbp-198h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-188h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-178h] BYREF
  int v24; // [rsp+110h] [rbp-118h]
  char v25; // [rsp+114h] [rbp-114h]
  int v26; // [rsp+118h] [rbp-110h]
  char v27; // [rsp+11Ch] [rbp-10Ch]
  int v28; // [rsp+120h] [rbp-108h]
  char v29; // [rsp+124h] [rbp-104h]
  int v30; // [rsp+128h] [rbp-100h]
  char v31; // [rsp+12Ch] [rbp-FCh]
  int v32; // [rsp+130h] [rbp-F8h]
  char v33; // [rsp+134h] [rbp-F4h]
  int v34; // [rsp+138h] [rbp-F0h]
  char v35; // [rsp+13Ch] [rbp-ECh]
  int v36; // [rsp+140h] [rbp-E8h]
  char v37; // [rsp+144h] [rbp-E4h]
  int v38; // [rsp+148h] [rbp-E0h]
  char v39; // [rsp+14Ch] [rbp-DCh]
  int v40; // [rsp+150h] [rbp-D8h]
  char v41; // [rsp+154h] [rbp-D4h]
  int v42; // [rsp+158h] [rbp-D0h]
  char v43; // [rsp+15Ch] [rbp-CCh]
  int v44; // [rsp+160h] [rbp-C8h]
  char v45; // [rsp+164h] [rbp-C4h]
  int v46; // [rsp+168h] [rbp-C0h]
  char v47; // [rsp+16Ch] [rbp-BCh]
  int v48; // [rsp+170h] [rbp-B8h]
  char v49; // [rsp+174h] [rbp-B4h]
  int v50; // [rsp+178h] [rbp-B0h]
  char v51; // [rsp+17Ch] [rbp-ACh]
  int v52; // [rsp+180h] [rbp-A8h]
  char v53; // [rsp+184h] [rbp-A4h]
  int v54; // [rsp+188h] [rbp-A0h]
  char v55; // [rsp+18Ch] [rbp-9Ch]
  int v56; // [rsp+190h] [rbp-98h]
  char v57; // [rsp+194h] [rbp-94h]
  int v58; // [rsp+198h] [rbp-90h]
  char v59; // [rsp+19Ch] [rbp-8Ch]
  int v60; // [rsp+1A0h] [rbp-88h]
  char v61; // [rsp+1A4h] [rbp-84h]
  int v62; // [rsp+1A8h] [rbp-80h]
  char v63; // [rsp+1ACh] [rbp-7Ch]
  int v64; // [rsp+1B0h] [rbp-78h]
  char v65; // [rsp+1B4h] [rbp-74h]
  int v66; // [rsp+1B8h] [rbp-70h]
  char v67; // [rsp+1BCh] [rbp-6Ch]
  int v68; // [rsp+1C0h] [rbp-68h]
  char v69; // [rsp+1C4h] [rbp-64h]
  int v70; // [rsp+1C8h] [rbp-60h]
  char v71; // [rsp+1CCh] [rbp-5Ch]
  int v72; // [rsp+1D0h] [rbp-58h]
  char v73; // [rsp+1D4h] [rbp-54h]
  int v74; // [rsp+1D8h] [rbp-50h]
  char v75; // [rsp+1DCh] [rbp-4Ch]
  int v76; // [rsp+1E0h] [rbp-48h]
  char v77; // [rsp+1E4h] [rbp-44h]
  int v78; // [rsp+1E8h] [rbp-40h]
  char v79; // [rsp+1ECh] [rbp-3Ch]

  memset_0(&instance, 0, 0x140u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_TextInput02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180343D33,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_TextInput02_NodeList,
           0x1Eu,
           2,
           &v15);
    if ( !v7 )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = v15;
          if ( v15 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v15;
            if ( v15 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_TextInput02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_133;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"TextInput",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowHardwareKeyboardTextSuggestions",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIMELogging",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIMENetworkAccess",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowInputPanel",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseIMESurrogatePairCharacters",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseIVSCharacters",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseNonPublishingStandardGlyph",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseUserDictionary",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowKeyboardTextSuggestions",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLanguageFeaturesUninstall",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLinguisticDataCollection",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowTextInputSuggestionUpdate",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureJapaneseIMEVersion",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureKoreanIMEVersion",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSimplifiedChineseIMEVersion",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureTraditionalChineseIMEVersion",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableTouchKeyboardAutoInvokeInDesktopMode",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludeJapaneseIMEExceptJIS0208",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludeJapaneseIMEExceptJIS0208andEUDC",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludeJapaneseIMEExceptShiftJIS",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ForceTouchKeyboardDockedState",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardDictationButtonAvailability",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardEmojiButtonAvailability",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardFullModeAvailability",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardHandwritingModeAvailability",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardNarrowModeAvailability",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardSplitModeAvailability",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardWideModeAvailability",
                        &String)
                  && String )
                {
                  v78 = _wtoi(String);
                  v79 = 1;
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
              v14 = 0;
            }
            v6 = v15;
            if ( v15 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
      }
    }
  }
  catch ( const exception *v17 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v16, v11);
    LODWORD(v15) = 1;
    goto LABEL_124;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_124:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (unsigned int)v15;
  }
LABEL_133:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_1803618D7,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return v7;
}

```

## disassembly

```asm
0x1800ec204  mov     [rsp+arg_8], rbx
0x1800ec209  mov     [rsp+arg_10], rsi
0x1800ec20e  push    rdi
0x1800ec20f  push    r12
0x1800ec211  push    r13
0x1800ec213  push    r14
0x1800ec215  push    r15
0x1800ec217  sub     rsp, 200h
0x1800ec21e  mov     rax, cs:__security_cookie
0x1800ec225  xor     rax, rsp
0x1800ec228  mov     [rsp+228h+var_38], rax
0x1800ec230  mov     r13b, dl
0x1800ec233  mov     r12, rcx
0x1800ec236  xor     edx, edx; Val
0x1800ec238  mov     r8d, 140h; Size
0x1800ec23e  lea     rcx, [rsp+228h+instance]; void *
0x1800ec246  call    memset_0
0x1800ec24b  xor     edi, edi
0x1800ec24d  mov     [rsp+228h+var_1E0], dil
0x1800ec252  mov     [rsp+228h+String], rdi
0x1800ec257  mov     [rsp+228h+var_1A0], edi
0x1800ec25e  mov     [rsp+228h+var_19C], dil
0x1800ec266  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ec26d  mov     [rsp+228h+var_1D0], rax
0x1800ec272  lea     rax, [rsp+228h+var_1A0]
0x1800ec27a  mov     [rsp+228h+var_1C8], rax
0x1800ec27f  lea     rax, aMdmPolicyConfi_92; "MDM_Policy_Config01_TextInput02"
0x1800ec286  mov     [rsp+228h+var_1C0], rax
0x1800ec28b  lea     rcx, [rsp+228h+var_1A0]
0x1800ec293  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ec298  mov     eax, cs:dword_180380B68
0x1800ec29e  cmp     eax, 5
0x1800ec2a1  jbe     short loc_1800EC313
0x1800ec2a3  mov     rdx, 200000000000h
0x1800ec2ad  lea     rcx, dword_180380B68
0x1800ec2b4  call    _tlgKeywordOn
0x1800ec2b9  test    al, al
0x1800ec2bb  jz      short loc_1800EC313
0x1800ec2bd  cmp     [rsp+228h+var_19C], dil
0x1800ec2c5  jz      short loc_1800EC2F5
0x1800ec2c7  cmp     [rsp+228h+var_188], edi
0x1800ec2ce  jnz     short loc_1800EC2EB
0x1800ec2d0  cmp     [rsp+228h+var_184], edi
0x1800ec2d7  jnz     short loc_1800EC2EB
0x1800ec2d9  cmp     [rsp+228h+var_180], edi
0x1800ec2e0  jnz     short loc_1800EC2EB
0x1800ec2e2  cmp     [rsp+228h+var_17C], edi
0x1800ec2e9  jz      short loc_1800EC2F5
0x1800ec2eb  lea     r9, [rsp+228h+var_188]
0x1800ec2f3  jmp     short loc_1800EC2F8
0x1800ec2f5  mov     r9, rdi
0x1800ec2f8  lea     r8, [rsp+228h+var_198]
0x1800ec300  lea     rdx, byte_180343D33
0x1800ec307  lea     rcx, dword_180380B68
0x1800ec30e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ec313  lea     rcx, [rsp+228h+var_1D0]; this
0x1800ec318  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800ec31d  nop
0x1800ec31e  mov     [rsp+228h+var_1D8], rdi
0x1800ec323  lea     rax, [rsp+228h+var_1D8]
0x1800ec328  mov     [rsp+228h+var_1F8], rax
0x1800ec32d  mov     [rsp+228h+var_200], 2
0x1800ec335  mov     [rsp+228h+var_208], 1Eh
0x1800ec33d  lea     r9, ?MDM_Policy_Config01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TextInput02_NodeList
0x1800ec344  xor     r8d, r8d
0x1800ec347  xor     edx, edx
0x1800ec349  mov     rcx, r12
0x1800ec34c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ec351  mov     r15d, eax
0x1800ec354  test    eax, eax
0x1800ec356  jz      short loc_1800EC35D
0x1800ec358  jmp     loc_1800ECC68
0x1800ec35d  lea     rbx, [rsp+228h+var_1D8]
0x1800ec362  mov     [rsp+228h+var_1B0], rbx
0x1800ec367  mov     r14d, 1
0x1800ec36d  mov     [rsp+228h+var_1A8], r14b
0x1800ec375  mov     rsi, [rsp+228h+var_1D8]
0x1800ec37a  test    rsi, rsi
0x1800ec37d  jnz     short loc_1800EC387
0x1800ec37f  mov     r15d, r14d
0x1800ec382  jmp     loc_1800ECC68
0x1800ec387  mov     rax, [rsi]
0x1800ec38a  mov     rcx, rsi
0x1800ec38d  mov     rax, [rax+10h]
0x1800ec391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec396  mov     r15d, eax
0x1800ec399  test    eax, eax
0x1800ec39b  jz      short loc_1800EC3BB
0x1800ec39d  mov     rcx, [rsp+228h+var_1D8]
0x1800ec3a2  test    rcx, rcx
0x1800ec3a5  jz      short loc_1800EC3B6
0x1800ec3a7  mov     rax, [rcx]
0x1800ec3aa  mov     edx, r14d
0x1800ec3ad  mov     rax, [rax]
0x1800ec3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec3b5  nop
0x1800ec3b6  jmp     loc_1800ECC68
0x1800ec3bb  mov     rax, [rsi]
0x1800ec3be  mov     rcx, rsi
0x1800ec3c1  mov     rax, [rax+8]
0x1800ec3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec3ca  mov     r15d, eax
0x1800ec3cd  test    eax, eax
0x1800ec3cf  jz      short loc_1800EC3EF
0x1800ec3d1  mov     rcx, [rsp+228h+var_1D8]
0x1800ec3d6  test    rcx, rcx
0x1800ec3d9  jz      short loc_1800EC3EA
0x1800ec3db  mov     rax, [rcx]
0x1800ec3de  mov     edx, r14d
0x1800ec3e1  mov     rax, [rax]
0x1800ec3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec3e9  nop
0x1800ec3ea  jmp     loc_1800ECC68
0x1800ec3ef  mov     r14d, edi
0x1800ec3f2  mov     rax, [rsi+108h]
0x1800ec3f9  sub     rax, [rsi+100h]
0x1800ec400  sar     rax, 4
0x1800ec404  cmp     r14d, eax
0x1800ec407  jnb     loc_1800ECC30
0x1800ec40d  lea     r8, [rsp+228h+instance]; instance
0x1800ec415  lea     rdx, MDM_Policy_Config01_TextInput02_rtti; classDecl
0x1800ec41c  mov     rcx, r12; context
0x1800ec41f  call    MI_Context_ConstructInstance
0x1800ec424  mov     r15d, eax
0x1800ec427  test    eax, eax
0x1800ec429  jz      short loc_1800EC44B
0x1800ec42b  mov     rcx, [rbx]
0x1800ec42e  test    rcx, rcx
0x1800ec431  jz      short loc_1800EC446
0x1800ec433  mov     rax, [rcx]
0x1800ec436  mov     edx, 1
0x1800ec43b  mov     rax, [rax]
0x1800ec43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec443  mov     [rbx], rdi
0x1800ec446  jmp     loc_1800ECC68
0x1800ec44b  mov     [rsp+228h+var_1E0], 1
0x1800ec450  mov     rax, [rsi]
0x1800ec453  lea     r9, [rsp+228h+String]
0x1800ec458  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800ec45f  mov     edx, r14d
0x1800ec462  mov     rcx, rsi
0x1800ec465  mov     rax, [rax+18h]
0x1800ec469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec46e  test    eax, eax
0x1800ec470  jnz     short loc_1800EC489
0x1800ec472  mov     rdx, [rsp+228h+String]
0x1800ec477  test    rdx, rdx
0x1800ec47a  jz      short loc_1800EC489
0x1800ec47c  lea     rcx, [rsp+228h+instance]
0x1800ec484  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800ec489  mov     rax, [rsi]
0x1800ec48c  lea     r9, [rsp+228h+String]
0x1800ec491  lea     r8, aTextinput; "TextInput"
0x1800ec498  mov     edx, r14d
0x1800ec49b  mov     rcx, rsi
0x1800ec49e  mov     rax, [rax+18h]
0x1800ec4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec4a7  test    eax, eax
0x1800ec4a9  jnz     short loc_1800EC4C2
0x1800ec4ab  mov     rdx, [rsp+228h+String]
0x1800ec4b0  test    rdx, rdx
0x1800ec4b3  jz      short loc_1800EC4C2
0x1800ec4b5  lea     rcx, [rsp+228h+instance]
0x1800ec4bd  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800ec4c2  cmp     r13b, 1
0x1800ec4c6  jnz     short loc_1800EC4EA
0x1800ec4c8  lea     rdx, [rsp+228h+instance]
0x1800ec4d0  mov     rcx, r12; self
0x1800ec4d3  call    MI_Instance_Destruct
0x1800ec4d8  lea     rcx, [rsp+228h+instance]; self
0x1800ec4e0  call    MI_Instance_Destruct
0x1800ec4e5  jmp     loc_1800ECC23
0x1800ec4ea  mov     rax, [rsi]
0x1800ec4ed  lea     r9, [rsp+228h+String]
0x1800ec4f2  lea     r8, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1800ec4f9  mov     edx, r14d
0x1800ec4fc  mov     rcx, rsi
0x1800ec4ff  mov     rax, [rax+18h]
0x1800ec503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec508  test    eax, eax
0x1800ec50a  jnz     short loc_1800EC52B
0x1800ec50c  mov     rcx, [rsp+228h+String]; String
0x1800ec511  test    rcx, rcx
0x1800ec514  jz      short loc_1800EC52B
0x1800ec516  call    cs:__imp__wtoi
0x1800ec51c  mov     [rsp+228h+var_118], eax
0x1800ec523  mov     [rsp+228h+var_114], 1
0x1800ec52b  mov     rax, [rsi]
0x1800ec52e  lea     r9, [rsp+228h+String]
0x1800ec533  lea     r8, aAllowimeloggin; "AllowIMELogging"
0x1800ec53a  mov     edx, r14d
0x1800ec53d  mov     rcx, rsi
0x1800ec540  mov     rax, [rax+18h]
0x1800ec544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec549  test    eax, eax
0x1800ec54b  jnz     short loc_1800EC56C
0x1800ec54d  mov     rcx, [rsp+228h+String]; String
0x1800ec552  test    rcx, rcx
0x1800ec555  jz      short loc_1800EC56C
0x1800ec557  call    cs:__imp__wtoi
0x1800ec55d  mov     [rsp+228h+var_110], eax
0x1800ec564  mov     [rsp+228h+var_10C], 1
0x1800ec56c  mov     rax, [rsi]
0x1800ec56f  lea     r9, [rsp+228h+String]
0x1800ec574  lea     r8, aAllowimenetwor; "AllowIMENetworkAccess"
0x1800ec57b  mov     edx, r14d
0x1800ec57e  mov     rcx, rsi
0x1800ec581  mov     rax, [rax+18h]
0x1800ec585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec58a  test    eax, eax
0x1800ec58c  jnz     short loc_1800EC5AD
0x1800ec58e  mov     rcx, [rsp+228h+String]; String
0x1800ec593  test    rcx, rcx
0x1800ec596  jz      short loc_1800EC5AD
0x1800ec598  call    cs:__imp__wtoi
0x1800ec59e  mov     [rsp+228h+var_108], eax
0x1800ec5a5  mov     [rsp+228h+var_104], 1
0x1800ec5ad  mov     rax, [rsi]
0x1800ec5b0  lea     r9, [rsp+228h+String]
0x1800ec5b5  lea     r8, aAllowinputpane; "AllowInputPanel"
0x1800ec5bc  mov     edx, r14d
0x1800ec5bf  mov     rcx, rsi
0x1800ec5c2  mov     rax, [rax+18h]
0x1800ec5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec5cb  test    eax, eax
0x1800ec5cd  jnz     short loc_1800EC5EE
0x1800ec5cf  mov     rcx, [rsp+228h+String]; String
0x1800ec5d4  test    rcx, rcx
0x1800ec5d7  jz      short loc_1800EC5EE
0x1800ec5d9  call    cs:__imp__wtoi
0x1800ec5df  mov     [rsp+228h+var_100], eax
0x1800ec5e6  mov     [rsp+228h+var_FC], 1
0x1800ec5ee  mov     rax, [rsi]
0x1800ec5f1  lea     r9, [rsp+228h+String]
0x1800ec5f6  lea     r8, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1800ec5fd  mov     edx, r14d
0x1800ec600  mov     rcx, rsi
0x1800ec603  mov     rax, [rax+18h]
0x1800ec607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec60c  test    eax, eax
0x1800ec60e  jnz     short loc_1800EC62F
0x1800ec610  mov     rcx, [rsp+228h+String]; String
0x1800ec615  test    rcx, rcx
0x1800ec618  jz      short loc_1800EC62F
0x1800ec61a  call    cs:__imp__wtoi
0x1800ec620  mov     [rsp+228h+var_F8], eax
0x1800ec627  mov     [rsp+228h+var_F4], 1
0x1800ec62f  mov     rax, [rsi]
0x1800ec632  lea     r9, [rsp+228h+String]
0x1800ec637  lea     r8, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1800ec63e  mov     edx, r14d
0x1800ec641  mov     rcx, rsi
0x1800ec644  mov     rax, [rax+18h]
0x1800ec648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec64d  test    eax, eax
0x1800ec64f  jnz     short loc_1800EC670
0x1800ec651  mov     rcx, [rsp+228h+String]; String
0x1800ec656  test    rcx, rcx
0x1800ec659  jz      short loc_1800EC670
0x1800ec65b  call    cs:__imp__wtoi
0x1800ec661  mov     [rsp+228h+var_F0], eax
0x1800ec668  mov     [rsp+228h+var_EC], 1
0x1800ec670  mov     rax, [rsi]
0x1800ec673  lea     r9, [rsp+228h+String]
0x1800ec678  lea     r8, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1800ec67f  mov     edx, r14d
0x1800ec682  mov     rcx, rsi
0x1800ec685  mov     rax, [rax+18h]
0x1800ec689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec68e  test    eax, eax
0x1800ec690  jnz     short loc_1800EC6B1
0x1800ec692  mov     rcx, [rsp+228h+String]; String
0x1800ec697  test    rcx, rcx
0x1800ec69a  jz      short loc_1800EC6B1
0x1800ec69c  call    cs:__imp__wtoi
0x1800ec6a2  mov     [rsp+228h+var_E8], eax
0x1800ec6a9  mov     [rsp+228h+var_E4], 1
0x1800ec6b1  mov     rax, [rsi]
0x1800ec6b4  lea     r9, [rsp+228h+String]
0x1800ec6b9  lea     r8, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1800ec6c0  mov     edx, r14d
0x1800ec6c3  mov     rcx, rsi
0x1800ec6c6  mov     rax, [rax+18h]
0x1800ec6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec6cf  test    eax, eax
0x1800ec6d1  jnz     short loc_1800EC6F2
0x1800ec6d3  mov     rcx, [rsp+228h+String]; String
0x1800ec6d8  test    rcx, rcx
0x1800ec6db  jz      short loc_1800EC6F2
0x1800ec6dd  call    cs:__imp__wtoi
0x1800ec6e3  mov     [rsp+228h+var_E0], eax
0x1800ec6ea  mov     [rsp+228h+var_DC], 1
0x1800ec6f2  mov     rax, [rsi]
0x1800ec6f5  lea     r9, [rsp+228h+String]
0x1800ec6fa  lea     r8, aAllowkeyboardt; "AllowKeyboardTextSuggestions"
0x1800ec701  mov     edx, r14d
0x1800ec704  mov     rcx, rsi
0x1800ec707  mov     rax, [rax+18h]
0x1800ec70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec710  test    eax, eax
  ... truncated ...
```
