# MDM_Policy_Config01_TextInput02_InvokeEnumerateInstances

- ea: `0x1800eb9b8`
- end: `0x1800ec565`
- name: `MDM_Policy_Config01_TextInput02_InvokeEnumerateInstances`
- size: `2989`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800eac50`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800eb9b8`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800ebcca`
- `msvcrt!_wtoi` at `0x1800ebd11`
- `msvcrt!_wtoi` at `0x1800ebd58`
- `msvcrt!_wtoi` at `0x1800ebd9f`
- `msvcrt!_wtoi` at `0x1800ebde6`
- `msvcrt!_wtoi` at `0x1800ebe2d`
- `msvcrt!_wtoi` at `0x1800ebe74`
- `msvcrt!_wtoi` at `0x1800ebebb`
- `msvcrt!_wtoi` at `0x1800ebf02`
- `msvcrt!_wtoi` at `0x1800ebf49`
- `msvcrt!_wtoi` at `0x1800ebf90`
- `msvcrt!_wtoi` at `0x1800ebfd7`
- `msvcrt!_wtoi` at `0x1800ec01e`
- `msvcrt!_wtoi` at `0x1800ec065`
- `msvcrt!_wtoi` at `0x1800ec0ac`
- `msvcrt!_wtoi` at `0x1800ec0f3`
- `msvcrt!_wtoi` at `0x1800ec13a`
- `msvcrt!_wtoi` at `0x1800ec181`
- `msvcrt!_wtoi` at `0x1800ec1c8`
- `msvcrt!_wtoi` at `0x1800ec20f`
- `msvcrt!_wtoi` at `0x1800ec256`
- `msvcrt!_wtoi` at `0x1800ec29d`
- `msvcrt!_wtoi` at `0x1800ec2e4`
- `msvcrt!_wtoi` at `0x1800ec32b`
- `msvcrt!_wtoi` at `0x1800ec372`
- `msvcrt!_wtoi` at `0x1800ec3b9`
- `msvcrt!_wtoi` at `0x1800ec400`
- `msvcrt!_wtoi` at `0x1800ec447`
- `msvcrt!_wtoi` at `0x1800ebcca`
- `msvcrt!_wtoi` at `0x1800ebd11`
- `msvcrt!_wtoi` at `0x1800ebd58`
- `msvcrt!_wtoi` at `0x1800ebd9f`
- `msvcrt!_wtoi` at `0x1800ebde6`
- `msvcrt!_wtoi` at `0x1800ebe2d`
- `msvcrt!_wtoi` at `0x1800ebe74`
- `msvcrt!_wtoi` at `0x1800ebebb`
- `msvcrt!_wtoi` at `0x1800ebf02`
- `msvcrt!_wtoi` at `0x1800ebf49`
- `msvcrt!_wtoi` at `0x1800ebf90`
- `msvcrt!_wtoi` at `0x1800ebfd7`
- `msvcrt!_wtoi` at `0x1800ec01e`
- `msvcrt!_wtoi` at `0x1800ec065`
- `msvcrt!_wtoi` at `0x1800ec0ac`
- `msvcrt!_wtoi` at `0x1800ec0f3`
- `msvcrt!_wtoi` at `0x1800ec13a`
- `msvcrt!_wtoi` at `0x1800ec181`
- `msvcrt!_wtoi` at `0x1800ec1c8`
- `msvcrt!_wtoi` at `0x1800ec20f`
- `msvcrt!_wtoi` at `0x1800ec256`
- `msvcrt!_wtoi` at `0x1800ec29d`
- `msvcrt!_wtoi` at `0x1800ec2e4`
- `msvcrt!_wtoi` at `0x1800ec32b`
- `msvcrt!_wtoi` at `0x1800ec372`
- `msvcrt!_wtoi` at `0x1800ec3b9`
- `msvcrt!_wtoi` at `0x1800ec400`
- `msvcrt!_wtoi` at `0x1800ec447`

## string_xrefs

- `0x1800ebd34`: `AllowIMENetworkAccess`
- `0x1800ebf25`: `AllowLanguageFeaturesUninstall`
- `0x1800ebfb3`: `AllowTextInputSuggestionUpdate`
- `0x1800ebffa`: `ConfigureJapaneseIMEVersion`
- `0x1800ec041`: `ConfigureKoreanIMEVersion`
- `0x1800ec088`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1800ec0cf`: `ConfigureTraditionalChineseIMEVersion`
- `0x1800ebc0c`: `./Vendor/MSFT/Policy/Config`
- `0x1800eba33`: `MDM_Policy_Config01_TextInput02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_TextInput02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1E8h] BYREF
  char v14; // [rsp+48h] [rbp-1E0h]
  _QWORD *v15; // [rsp+50h] [rbp-1D8h] BYREF
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
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_TextInput02_NodeList, 30, 2, &v15);
    if ( v7 == MI_RESULT_OK )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = (wil *)v15;
          if ( v15 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v15;
            if ( v15 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_TextInput02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_133;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowHardwareKeyboardTextSuggestions",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIMELogging",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowIMENetworkAccess",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowInputPanel",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseIMESurrogatePairCharacters",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseIVSCharacters",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseNonPublishingStandardGlyph",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowJapaneseUserDictionary",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowKeyboardTextSuggestions",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLanguageFeaturesUninstall",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLinguisticDataCollection",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowTextInputSuggestionUpdate",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureJapaneseIMEVersion",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureKoreanIMEVersion",
                        &String)
                  && String )
                {
                  v50 = _wtoi(String);
                  v51 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureSimplifiedChineseIMEVersion",
                        &String)
                  && String )
                {
                  v52 = _wtoi(String);
                  v53 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureTraditionalChineseIMEVersion",
                        &String)
                  && String )
                {
                  v54 = _wtoi(String);
                  v55 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableTouchKeyboardAutoInvokeInDesktopMode",
                        &String)
                  && String )
                {
                  v56 = _wtoi(String);
                  v57 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludeJapaneseIMEExceptJIS0208",
                        &String)
                  && String )
                {
                  v58 = _wtoi(String);
                  v59 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludeJapaneseIMEExceptJIS0208andEUDC",
                        &String)
                  && String )
                {
                  v60 = _wtoi(String);
                  v61 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ExcludeJapaneseIMEExceptShiftJIS",
                        &String)
                  && String )
                {
                  v62 = _wtoi(String);
                  v63 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ForceTouchKeyboardDockedState",
                        &String)
                  && String )
                {
                  v64 = _wtoi(String);
                  v65 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardDictationButtonAvailability",
                        &String)
                  && String )
                {
                  v66 = _wtoi(String);
                  v67 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardEmojiButtonAvailability",
                        &String)
                  && String )
                {
                  v68 = _wtoi(String);
                  v69 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardFullModeAvailability",
                        &String)
                  && String )
                {
                  v70 = _wtoi(String);
                  v71 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardHandwritingModeAvailability",
                        &String)
                  && String )
                {
                  v72 = _wtoi(String);
                  v73 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardNarrowModeAvailability",
                        &String)
                  && String )
                {
                  v74 = _wtoi(String);
                  v75 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TouchKeyboardSplitModeAvailability",
                        &String)
                  && String )
                {
                  v76 = _wtoi(String);
                  v77 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
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
            v6 = (wil *)v15;
            if ( v15 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
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
    v7 = (int)v15;
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
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800eb9b8  mov     [rsp+arg_8], rbx
0x1800eb9bd  mov     [rsp+arg_10], rsi
0x1800eb9c2  push    rdi
0x1800eb9c3  push    r12
0x1800eb9c5  push    r13
0x1800eb9c7  push    r14
0x1800eb9c9  push    r15
0x1800eb9cb  sub     rsp, 200h
0x1800eb9d2  mov     rax, cs:__security_cookie
0x1800eb9d9  xor     rax, rsp
0x1800eb9dc  mov     [rsp+228h+var_38], rax
0x1800eb9e4  mov     r13b, dl
0x1800eb9e7  mov     r12, rcx
0x1800eb9ea  xor     edx, edx; Val
0x1800eb9ec  mov     r8d, 140h; Size
0x1800eb9f2  lea     rcx, [rsp+228h+instance]; void *
0x1800eb9fa  call    memset_0
0x1800eb9ff  xor     edi, edi
0x1800eba01  mov     [rsp+228h+var_1E0], dil
0x1800eba06  mov     [rsp+228h+String], rdi
0x1800eba0b  mov     [rsp+228h+var_1A0], edi
0x1800eba12  mov     [rsp+228h+var_19C], dil
0x1800eba1a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800eba21  mov     [rsp+228h+var_1D0], rax
0x1800eba26  lea     rax, [rsp+228h+var_1A0]
0x1800eba2e  mov     [rsp+228h+var_1C8], rax
0x1800eba33  lea     rax, aMdmPolicyConfi_92; "MDM_Policy_Config01_TextInput02"
0x1800eba3a  mov     [rsp+228h+var_1C0], rax
0x1800eba3f  lea     rcx, [rsp+228h+var_1A0]
0x1800eba47  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800eba4c  mov     eax, cs:dword_180380B68
0x1800eba52  cmp     eax, 5
0x1800eba55  jbe     short loc_1800EBAC7
0x1800eba57  mov     rdx, 200000000000h
0x1800eba61  lea     rcx, dword_180380B68
0x1800eba68  call    _tlgKeywordOn
0x1800eba6d  test    al, al
0x1800eba6f  jz      short loc_1800EBAC7
0x1800eba71  cmp     [rsp+228h+var_19C], dil
0x1800eba79  jz      short loc_1800EBAA9
0x1800eba7b  cmp     [rsp+228h+var_188], edi
0x1800eba82  jnz     short loc_1800EBA9F
0x1800eba84  cmp     [rsp+228h+var_184], edi
0x1800eba8b  jnz     short loc_1800EBA9F
0x1800eba8d  cmp     [rsp+228h+var_180], edi
0x1800eba94  jnz     short loc_1800EBA9F
0x1800eba96  cmp     [rsp+228h+var_17C], edi
0x1800eba9d  jz      short loc_1800EBAA9
0x1800eba9f  lea     r9, [rsp+228h+var_188]
0x1800ebaa7  jmp     short loc_1800EBAAC
0x1800ebaa9  mov     r9, rdi
0x1800ebaac  lea     r8, [rsp+228h+var_198]
0x1800ebab4  lea     rdx, byte_180343D33
0x1800ebabb  lea     rcx, dword_180380B68
0x1800ebac2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ebac7  lea     rcx, [rsp+228h+var_1D0]; this
0x1800ebacc  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800ebad1  nop
0x1800ebad2  mov     [rsp+228h+var_1D8], rdi
0x1800ebad7  lea     rax, [rsp+228h+var_1D8]
0x1800ebadc  mov     [rsp+228h+var_1F8], rax
0x1800ebae1  mov     [rsp+228h+var_200], 2
0x1800ebae9  mov     [rsp+228h+var_208], 1Eh
0x1800ebaf1  lea     r9, ?MDM_Policy_Config01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TextInput02_NodeList
0x1800ebaf8  xor     r8d, r8d
0x1800ebafb  xor     edx, edx
0x1800ebafd  mov     rcx, r12
0x1800ebb00  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ebb05  mov     r15d, eax
0x1800ebb08  test    eax, eax
0x1800ebb0a  jz      short loc_1800EBB11
0x1800ebb0c  jmp     loc_1800EC4C4
0x1800ebb11  lea     rbx, [rsp+228h+var_1D8]
0x1800ebb16  mov     [rsp+228h+var_1B0], rbx
0x1800ebb1b  mov     r14d, 1
0x1800ebb21  mov     [rsp+228h+var_1A8], r14b
0x1800ebb29  mov     rsi, [rsp+228h+var_1D8]
0x1800ebb2e  test    rsi, rsi
0x1800ebb31  jnz     short loc_1800EBB3B
0x1800ebb33  mov     r15d, r14d
0x1800ebb36  jmp     loc_1800EC4C4
0x1800ebb3b  mov     rax, [rsi]
0x1800ebb3e  mov     rcx, rsi
0x1800ebb41  mov     rax, [rax+10h]
0x1800ebb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebb4a  mov     r15d, eax
0x1800ebb4d  test    eax, eax
0x1800ebb4f  jz      short loc_1800EBB6F
0x1800ebb51  mov     rcx, [rsp+228h+var_1D8]
0x1800ebb56  test    rcx, rcx
0x1800ebb59  jz      short loc_1800EBB6A
0x1800ebb5b  mov     rax, [rcx]
0x1800ebb5e  mov     edx, r14d
0x1800ebb61  mov     rax, [rax]
0x1800ebb64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebb69  nop
0x1800ebb6a  jmp     loc_1800EC4C4
0x1800ebb6f  mov     rax, [rsi]
0x1800ebb72  mov     rcx, rsi
0x1800ebb75  mov     rax, [rax+8]
0x1800ebb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebb7e  mov     r15d, eax
0x1800ebb81  test    eax, eax
0x1800ebb83  jz      short loc_1800EBBA3
0x1800ebb85  mov     rcx, [rsp+228h+var_1D8]
0x1800ebb8a  test    rcx, rcx
0x1800ebb8d  jz      short loc_1800EBB9E
0x1800ebb8f  mov     rax, [rcx]
0x1800ebb92  mov     edx, r14d
0x1800ebb95  mov     rax, [rax]
0x1800ebb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebb9d  nop
0x1800ebb9e  jmp     loc_1800EC4C4
0x1800ebba3  mov     r14d, edi
0x1800ebba6  mov     rax, [rsi+108h]
0x1800ebbad  sub     rax, [rsi+100h]
0x1800ebbb4  sar     rax, 4
0x1800ebbb8  cmp     r14d, eax
0x1800ebbbb  jnb     loc_1800EC48C
0x1800ebbc1  lea     r8, [rsp+228h+instance]; instance
0x1800ebbc9  lea     rdx, MDM_Policy_Config01_TextInput02_rtti; classDecl
0x1800ebbd0  mov     rcx, r12; context
0x1800ebbd3  call    MI_Context_ConstructInstance
0x1800ebbd8  mov     r15d, eax
0x1800ebbdb  test    eax, eax
0x1800ebbdd  jz      short loc_1800EBBFF
0x1800ebbdf  mov     rcx, [rbx]
0x1800ebbe2  test    rcx, rcx
0x1800ebbe5  jz      short loc_1800EBBFA
0x1800ebbe7  mov     rax, [rcx]
0x1800ebbea  mov     edx, 1
0x1800ebbef  mov     rax, [rax]
0x1800ebbf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebbf7  mov     [rbx], rdi
0x1800ebbfa  jmp     loc_1800EC4C4
0x1800ebbff  mov     [rsp+228h+var_1E0], 1
0x1800ebc04  mov     rax, [rsi]
0x1800ebc07  lea     r9, [rsp+228h+String]
0x1800ebc0c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800ebc13  mov     edx, r14d
0x1800ebc16  mov     rcx, rsi
0x1800ebc19  mov     rax, [rax+18h]
0x1800ebc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebc22  test    eax, eax
0x1800ebc24  jnz     short loc_1800EBC3D
0x1800ebc26  mov     rdx, [rsp+228h+String]
0x1800ebc2b  test    rdx, rdx
0x1800ebc2e  jz      short loc_1800EBC3D
0x1800ebc30  lea     rcx, [rsp+228h+instance]
0x1800ebc38  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800ebc3d  mov     rax, [rsi]
0x1800ebc40  lea     r9, [rsp+228h+String]
0x1800ebc45  lea     r8, aTextinput; "TextInput"
0x1800ebc4c  mov     edx, r14d
0x1800ebc4f  mov     rcx, rsi
0x1800ebc52  mov     rax, [rax+18h]
0x1800ebc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebc5b  test    eax, eax
0x1800ebc5d  jnz     short loc_1800EBC76
0x1800ebc5f  mov     rdx, [rsp+228h+String]
0x1800ebc64  test    rdx, rdx
0x1800ebc67  jz      short loc_1800EBC76
0x1800ebc69  lea     rcx, [rsp+228h+instance]
0x1800ebc71  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800ebc76  cmp     r13b, 1
0x1800ebc7a  jnz     short loc_1800EBC9E
0x1800ebc7c  lea     rdx, [rsp+228h+instance]
0x1800ebc84  mov     rcx, r12; self
0x1800ebc87  call    MI_Instance_Destruct
0x1800ebc8c  lea     rcx, [rsp+228h+instance]; self
0x1800ebc94  call    MI_Instance_Destruct
0x1800ebc99  jmp     loc_1800EC47F
0x1800ebc9e  mov     rax, [rsi]
0x1800ebca1  lea     r9, [rsp+228h+String]
0x1800ebca6  lea     r8, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1800ebcad  mov     edx, r14d
0x1800ebcb0  mov     rcx, rsi
0x1800ebcb3  mov     rax, [rax+18h]
0x1800ebcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebcbc  test    eax, eax
0x1800ebcbe  jnz     short loc_1800EBCE5
0x1800ebcc0  mov     rcx, [rsp+228h+String]; String
0x1800ebcc5  test    rcx, rcx
0x1800ebcc8  jz      short loc_1800EBCE5
0x1800ebcca  call    cs:__imp__wtoi
0x1800ebcd1  nop     dword ptr [rax+rax+00h]
0x1800ebcd6  mov     [rsp+228h+var_118], eax
0x1800ebcdd  mov     [rsp+228h+var_114], 1
0x1800ebce5  mov     rax, [rsi]
0x1800ebce8  lea     r9, [rsp+228h+String]
0x1800ebced  lea     r8, aAllowimeloggin; "AllowIMELogging"
0x1800ebcf4  mov     edx, r14d
0x1800ebcf7  mov     rcx, rsi
0x1800ebcfa  mov     rax, [rax+18h]
0x1800ebcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebd03  test    eax, eax
0x1800ebd05  jnz     short loc_1800EBD2C
0x1800ebd07  mov     rcx, [rsp+228h+String]; String
0x1800ebd0c  test    rcx, rcx
0x1800ebd0f  jz      short loc_1800EBD2C
0x1800ebd11  call    cs:__imp__wtoi
0x1800ebd18  nop     dword ptr [rax+rax+00h]
0x1800ebd1d  mov     [rsp+228h+var_110], eax
0x1800ebd24  mov     [rsp+228h+var_10C], 1
0x1800ebd2c  mov     rax, [rsi]
0x1800ebd2f  lea     r9, [rsp+228h+String]
0x1800ebd34  lea     r8, aAllowimenetwor; "AllowIMENetworkAccess"
0x1800ebd3b  mov     edx, r14d
0x1800ebd3e  mov     rcx, rsi
0x1800ebd41  mov     rax, [rax+18h]
0x1800ebd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebd4a  test    eax, eax
0x1800ebd4c  jnz     short loc_1800EBD73
0x1800ebd4e  mov     rcx, [rsp+228h+String]; String
0x1800ebd53  test    rcx, rcx
0x1800ebd56  jz      short loc_1800EBD73
0x1800ebd58  call    cs:__imp__wtoi
0x1800ebd5f  nop     dword ptr [rax+rax+00h]
0x1800ebd64  mov     [rsp+228h+var_108], eax
0x1800ebd6b  mov     [rsp+228h+var_104], 1
0x1800ebd73  mov     rax, [rsi]
0x1800ebd76  lea     r9, [rsp+228h+String]
0x1800ebd7b  lea     r8, aAllowinputpane; "AllowInputPanel"
0x1800ebd82  mov     edx, r14d
0x1800ebd85  mov     rcx, rsi
0x1800ebd88  mov     rax, [rax+18h]
0x1800ebd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebd91  test    eax, eax
0x1800ebd93  jnz     short loc_1800EBDBA
0x1800ebd95  mov     rcx, [rsp+228h+String]; String
0x1800ebd9a  test    rcx, rcx
0x1800ebd9d  jz      short loc_1800EBDBA
0x1800ebd9f  call    cs:__imp__wtoi
0x1800ebda6  nop     dword ptr [rax+rax+00h]
0x1800ebdab  mov     [rsp+228h+var_100], eax
0x1800ebdb2  mov     [rsp+228h+var_FC], 1
0x1800ebdba  mov     rax, [rsi]
0x1800ebdbd  lea     r9, [rsp+228h+String]
0x1800ebdc2  lea     r8, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1800ebdc9  mov     edx, r14d
0x1800ebdcc  mov     rcx, rsi
0x1800ebdcf  mov     rax, [rax+18h]
0x1800ebdd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebdd8  test    eax, eax
0x1800ebdda  jnz     short loc_1800EBE01
0x1800ebddc  mov     rcx, [rsp+228h+String]; String
0x1800ebde1  test    rcx, rcx
0x1800ebde4  jz      short loc_1800EBE01
0x1800ebde6  call    cs:__imp__wtoi
0x1800ebded  nop     dword ptr [rax+rax+00h]
0x1800ebdf2  mov     [rsp+228h+var_F8], eax
0x1800ebdf9  mov     [rsp+228h+var_F4], 1
0x1800ebe01  mov     rax, [rsi]
0x1800ebe04  lea     r9, [rsp+228h+String]
0x1800ebe09  lea     r8, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1800ebe10  mov     edx, r14d
0x1800ebe13  mov     rcx, rsi
0x1800ebe16  mov     rax, [rax+18h]
0x1800ebe1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebe1f  test    eax, eax
0x1800ebe21  jnz     short loc_1800EBE48
0x1800ebe23  mov     rcx, [rsp+228h+String]; String
0x1800ebe28  test    rcx, rcx
0x1800ebe2b  jz      short loc_1800EBE48
0x1800ebe2d  call    cs:__imp__wtoi
0x1800ebe34  nop     dword ptr [rax+rax+00h]
0x1800ebe39  mov     [rsp+228h+var_F0], eax
0x1800ebe40  mov     [rsp+228h+var_EC], 1
0x1800ebe48  mov     rax, [rsi]
0x1800ebe4b  lea     r9, [rsp+228h+String]
0x1800ebe50  lea     r8, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1800ebe57  mov     edx, r14d
0x1800ebe5a  mov     rcx, rsi
0x1800ebe5d  mov     rax, [rax+18h]
0x1800ebe61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebe66  test    eax, eax
0x1800ebe68  jnz     short loc_1800EBE8F
0x1800ebe6a  mov     rcx, [rsp+228h+String]; String
0x1800ebe6f  test    rcx, rcx
0x1800ebe72  jz      short loc_1800EBE8F
0x1800ebe74  call    cs:__imp__wtoi
0x1800ebe7b  nop     dword ptr [rax+rax+00h]
0x1800ebe80  mov     [rsp+228h+var_E8], eax
0x1800ebe87  mov     [rsp+228h+var_E4], 1
0x1800ebe8f  mov     rax, [rsi]
0x1800ebe92  lea     r9, [rsp+228h+String]
0x1800ebe97  lea     r8, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1800ebe9e  mov     edx, r14d
0x1800ebea1  mov     rcx, rsi
0x1800ebea4  mov     rax, [rax+18h]
0x1800ebea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebead  test    eax, eax
0x1800ebeaf  jnz     short loc_1800EBED6
0x1800ebeb1  mov     rcx, [rsp+228h+String]; String
0x1800ebeb6  test    rcx, rcx
0x1800ebeb9  jz      short loc_1800EBED6
0x1800ebebb  call    cs:__imp__wtoi
0x1800ebec2  nop     dword ptr [rax+rax+00h]
0x1800ebec7  mov     [rsp+228h+var_E0], eax
0x1800ebece  mov     [rsp+228h+var_DC], 1
  ... truncated ...
```
