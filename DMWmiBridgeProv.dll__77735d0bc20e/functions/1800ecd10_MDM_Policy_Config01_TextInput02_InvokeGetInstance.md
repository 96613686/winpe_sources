# MDM_Policy_Config01_TextInput02_InvokeGetInstance

- ea: `0x1800ecd10`
- end: `0x1800ed67a`
- name: `MDM_Policy_Config01_TextInput02_InvokeGetInstance`
- size: `2410`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800eb4c0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800ecd10`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800ecfaf`
- `msvcrt!_wtoi` at `0x1800ecfe6`
- `msvcrt!_wtoi` at `0x1800ed01d`
- `msvcrt!_wtoi` at `0x1800ed054`
- `msvcrt!_wtoi` at `0x1800ed08b`
- `msvcrt!_wtoi` at `0x1800ed0c2`
- `msvcrt!_wtoi` at `0x1800ed0f9`
- `msvcrt!_wtoi` at `0x1800ed130`
- `msvcrt!_wtoi` at `0x1800ed167`
- `msvcrt!_wtoi` at `0x1800ed19e`
- `msvcrt!_wtoi` at `0x1800ed1d5`
- `msvcrt!_wtoi` at `0x1800ed20c`
- `msvcrt!_wtoi` at `0x1800ed243`
- `msvcrt!_wtoi` at `0x1800ed27a`
- `msvcrt!_wtoi` at `0x1800ed2b1`
- `msvcrt!_wtoi` at `0x1800ed2e8`
- `msvcrt!_wtoi` at `0x1800ed31f`
- `msvcrt!_wtoi` at `0x1800ed356`
- `msvcrt!_wtoi` at `0x1800ed38d`
- `msvcrt!_wtoi` at `0x1800ed3c4`
- `msvcrt!_wtoi` at `0x1800ed3fb`
- `msvcrt!_wtoi` at `0x1800ed432`
- `msvcrt!_wtoi` at `0x1800ed469`
- `msvcrt!_wtoi` at `0x1800ed4a0`
- `msvcrt!_wtoi` at `0x1800ed4d7`
- `msvcrt!_wtoi` at `0x1800ed50e`
- `msvcrt!_wtoi` at `0x1800ed545`
- `msvcrt!_wtoi` at `0x1800ed57c`
- `msvcrt!_wtoi` at `0x1800ecfaf`
- `msvcrt!_wtoi` at `0x1800ecfe6`
- `msvcrt!_wtoi` at `0x1800ed01d`
- `msvcrt!_wtoi` at `0x1800ed054`
- `msvcrt!_wtoi` at `0x1800ed08b`
- `msvcrt!_wtoi` at `0x1800ed0c2`
- `msvcrt!_wtoi` at `0x1800ed0f9`
- `msvcrt!_wtoi` at `0x1800ed130`
- `msvcrt!_wtoi` at `0x1800ed167`
- `msvcrt!_wtoi` at `0x1800ed19e`
- `msvcrt!_wtoi` at `0x1800ed1d5`
- `msvcrt!_wtoi` at `0x1800ed20c`
- `msvcrt!_wtoi` at `0x1800ed243`
- `msvcrt!_wtoi` at `0x1800ed27a`
- `msvcrt!_wtoi` at `0x1800ed2b1`
- `msvcrt!_wtoi` at `0x1800ed2e8`
- `msvcrt!_wtoi` at `0x1800ed31f`
- `msvcrt!_wtoi` at `0x1800ed356`
- `msvcrt!_wtoi` at `0x1800ed38d`
- `msvcrt!_wtoi` at `0x1800ed3c4`
- `msvcrt!_wtoi` at `0x1800ed3fb`
- `msvcrt!_wtoi` at `0x1800ed432`
- `msvcrt!_wtoi` at `0x1800ed469`
- `msvcrt!_wtoi` at `0x1800ed4a0`
- `msvcrt!_wtoi` at `0x1800ed4d7`
- `msvcrt!_wtoi` at `0x1800ed50e`
- `msvcrt!_wtoi` at `0x1800ed545`
- `msvcrt!_wtoi` at `0x1800ed57c`

## string_xrefs

- `0x1800ed000`: `AllowIMENetworkAccess`
- `0x1800ed181`: `AllowLanguageFeaturesUninstall`
- `0x1800ed1ef`: `AllowTextInputSuggestionUpdate`
- `0x1800ed226`: `ConfigureJapaneseIMEVersion`
- `0x1800ed25d`: `ConfigureKoreanIMEVersion`
- `0x1800ed294`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1800ed2cb`: `ConfigureTraditionalChineseIMEVersion`
- `0x1800ecd7f`: `MDM_Policy_Config01_TextInput02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_TextInput02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-1E8h] BYREF
  char v9; // [rsp+48h] [rbp-1E0h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-1D8h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-1D0h] BYREF
  char v12; // [rsp+80h] [rbp-1A8h]
  int v13; // [rsp+88h] [rbp-1A0h] BYREF
  char v14; // [rsp+8Ch] [rbp-19Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-198h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-188h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-178h] BYREF
  int v18; // [rsp+110h] [rbp-118h]
  char v19; // [rsp+114h] [rbp-114h]
  int v20; // [rsp+118h] [rbp-110h]
  char v21; // [rsp+11Ch] [rbp-10Ch]
  int v22; // [rsp+120h] [rbp-108h]
  char v23; // [rsp+124h] [rbp-104h]
  int v24; // [rsp+128h] [rbp-100h]
  char v25; // [rsp+12Ch] [rbp-FCh]
  int v26; // [rsp+130h] [rbp-F8h]
  char v27; // [rsp+134h] [rbp-F4h]
  int v28; // [rsp+138h] [rbp-F0h]
  char v29; // [rsp+13Ch] [rbp-ECh]
  int v30; // [rsp+140h] [rbp-E8h]
  char v31; // [rsp+144h] [rbp-E4h]
  int v32; // [rsp+148h] [rbp-E0h]
  char v33; // [rsp+14Ch] [rbp-DCh]
  int v34; // [rsp+150h] [rbp-D8h]
  char v35; // [rsp+154h] [rbp-D4h]
  int v36; // [rsp+158h] [rbp-D0h]
  char v37; // [rsp+15Ch] [rbp-CCh]
  int v38; // [rsp+160h] [rbp-C8h]
  char v39; // [rsp+164h] [rbp-C4h]
  int v40; // [rsp+168h] [rbp-C0h]
  char v41; // [rsp+16Ch] [rbp-BCh]
  int v42; // [rsp+170h] [rbp-B8h]
  char v43; // [rsp+174h] [rbp-B4h]
  int v44; // [rsp+178h] [rbp-B0h]
  char v45; // [rsp+17Ch] [rbp-ACh]
  int v46; // [rsp+180h] [rbp-A8h]
  char v47; // [rsp+184h] [rbp-A4h]
  int v48; // [rsp+188h] [rbp-A0h]
  char v49; // [rsp+18Ch] [rbp-9Ch]
  int v50; // [rsp+190h] [rbp-98h]
  char v51; // [rsp+194h] [rbp-94h]
  int v52; // [rsp+198h] [rbp-90h]
  char v53; // [rsp+19Ch] [rbp-8Ch]
  int v54; // [rsp+1A0h] [rbp-88h]
  char v55; // [rsp+1A4h] [rbp-84h]
  int v56; // [rsp+1A8h] [rbp-80h]
  char v57; // [rsp+1ACh] [rbp-7Ch]
  int v58; // [rsp+1B0h] [rbp-78h]
  char v59; // [rsp+1B4h] [rbp-74h]
  int v60; // [rsp+1B8h] [rbp-70h]
  char v61; // [rsp+1BCh] [rbp-6Ch]
  int v62; // [rsp+1C0h] [rbp-68h]
  char v63; // [rsp+1C4h] [rbp-64h]
  int v64; // [rsp+1C8h] [rbp-60h]
  char v65; // [rsp+1CCh] [rbp-5Ch]
  int v66; // [rsp+1D0h] [rbp-58h]
  char v67; // [rsp+1D4h] [rbp-54h]
  int v68; // [rsp+1D8h] [rbp-50h]
  char v69; // [rsp+1DCh] [rbp-4Ch]
  int v70; // [rsp+1E0h] [rbp-48h]
  char v71; // [rsp+1E4h] [rbp-44h]
  int v72; // [rsp+1E8h] [rbp-40h]
  char v73; // [rsp+1ECh] [rbp-3Ch]

  String = 0;
  memset_0(&instance, 0, 0x140u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_TextInput02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18033695E,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = 4;
    goto LABEL_113;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = CreateRequestHandlerInstance(
         (__int64)self,
         (wchar_t *)a2[1].serverName,
         (const unsigned __int16 *)a2[1].ft,
         (struct WmiNodeInfo *)&MDM_Policy_Config01_TextInput02_NodeList,
         0x1Eu,
         0,
         &v10);
  if ( !v5 )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = 1;
      goto LABEL_113;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_TextInput02_NodeList,
      0x1Eu);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_113;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_113;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_113;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_TextInput02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_113;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowHardwareKeyboardTextSuggestions",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowIMELogging",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowIMENetworkAccess",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowInputPanel",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowJapaneseIMESurrogatePairCharacters",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowJapaneseIVSCharacters",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowJapaneseNonPublishingStandardGlyph",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowJapaneseUserDictionary",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowKeyboardTextSuggestions",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowLanguageFeaturesUninstall",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowLinguisticDataCollection",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowTextInputSuggestionUpdate",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureJapaneseIMEVersion",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureKoreanIMEVersion",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureSimplifiedChineseIMEVersion",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ConfigureTraditionalChineseIMEVersion",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"EnableTouchKeyboardAutoInvokeInDesktopMode",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ExcludeJapaneseIMEExceptJIS0208",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ExcludeJapaneseIMEExceptJIS0208andEUDC",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ExcludeJapaneseIMEExceptShiftJIS",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ForceTouchKeyboardDockedState",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"TouchKeyboardDictationButtonAvailability",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v60 = _wtoi(String);
      v61 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"TouchKeyboardEmojiButtonAvailability",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v62 = _wtoi(String);
      v63 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"TouchKeyboardFullModeAvailability",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v64 = _wtoi(String);
      v65 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"TouchKeyboardHandwritingModeAvailability",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v66 = _wtoi(String);
      v67 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"TouchKeyboardNarrowModeAvailability",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v68 = _wtoi(String);
      v69 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"TouchKeyboardSplitModeAvailability",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v70 = _wtoi(String);
      v71 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"TouchKeyboardWideModeAvailability",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v72 = _wtoi(String);
      v73 = 1;
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_113:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_180360E47,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x1800ecd10  mov     [rsp+arg_10], rbx
0x1800ecd15  push    rsi
0x1800ecd16  push    rdi
0x1800ecd17  push    r12
0x1800ecd19  push    r14
0x1800ecd1b  push    r15
0x1800ecd1d  sub     rsp, 200h
0x1800ecd24  mov     rax, cs:__security_cookie
0x1800ecd2b  xor     rax, rsp
0x1800ecd2e  mov     [rsp+228h+var_38], rax
0x1800ecd36  mov     rsi, rdx
0x1800ecd39  mov     r15, rcx
0x1800ecd3c  xor     ebx, ebx
0x1800ecd3e  mov     [rsp+228h+String], rbx
0x1800ecd43  xor     edx, edx; Val
0x1800ecd45  mov     r8d, 140h; Size
0x1800ecd4b  lea     rcx, [rsp+228h+instance]; void *
0x1800ecd53  call    memset_0
0x1800ecd58  mov     [rsp+228h+var_1A0], ebx
0x1800ecd5f  mov     [rsp+228h+var_19C], bl
0x1800ecd66  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ecd6d  mov     [rsp+228h+var_1D0], rax
0x1800ecd72  lea     rax, [rsp+228h+var_1A0]
0x1800ecd7a  mov     [rsp+228h+var_1C8], rax
0x1800ecd7f  lea     rax, aMdmPolicyConfi_92; "MDM_Policy_Config01_TextInput02"
0x1800ecd86  mov     [rsp+228h+var_1C0], rax
0x1800ecd8b  lea     rcx, [rsp+228h+var_1A0]
0x1800ecd93  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ecd98  mov     eax, cs:dword_180380B68
0x1800ecd9e  cmp     eax, 5
0x1800ecda1  jbe     short loc_1800ECE12
0x1800ecda3  mov     rdx, 200000000000h
0x1800ecdad  lea     rcx, dword_180380B68
0x1800ecdb4  call    _tlgKeywordOn
0x1800ecdb9  test    al, al
0x1800ecdbb  jz      short loc_1800ECE12
0x1800ecdbd  cmp     [rsp+228h+var_19C], bl
0x1800ecdc4  jz      short loc_1800ECDF4
0x1800ecdc6  cmp     [rsp+228h+var_188], ebx
0x1800ecdcd  jnz     short loc_1800ECDEA
0x1800ecdcf  cmp     [rsp+228h+var_184], ebx
0x1800ecdd6  jnz     short loc_1800ECDEA
0x1800ecdd8  cmp     [rsp+228h+var_180], ebx
0x1800ecddf  jnz     short loc_1800ECDEA
0x1800ecde1  cmp     [rsp+228h+var_17C], ebx
0x1800ecde8  jz      short loc_1800ECDF4
0x1800ecdea  lea     r9, [rsp+228h+var_188]
0x1800ecdf2  jmp     short loc_1800ECDF7
0x1800ecdf4  mov     r9, rbx
0x1800ecdf7  lea     r8, [rsp+228h+var_198]
0x1800ecdff  lea     rdx, word_18033695E
0x1800ece06  lea     rcx, dword_180380B68
0x1800ece0d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ece12  cmp     [rsi+48h], bl
0x1800ece15  jz      loc_1800ED5D9
0x1800ece1b  mov     [rsp+228h+var_1E0], bl
0x1800ece1f  cmp     [rsi+58h], bl
0x1800ece22  jz      loc_1800ED5D9
0x1800ece28  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800ece2c  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800ece30  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800ece37  lea     rcx, [rsp+228h+var_1D0]; this
0x1800ece3c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800ece41  nop
0x1800ece42  mov     [rsp+228h+var_1D8], rbx
0x1800ece47  lea     rax, [rsp+228h+var_1D8]
0x1800ece4c  mov     [rsp+228h+var_1F8], rax
0x1800ece51  mov     [rsp+228h+var_200], ebx
0x1800ece55  mov     [rsp+228h+var_208], 1Eh
0x1800ece5d  lea     r9, ?MDM_Policy_Config01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TextInput02_NodeList
0x1800ece64  mov     r8, [rsi+40h]
0x1800ece68  mov     rdx, [rsi+50h]
0x1800ece6c  mov     rcx, r15
0x1800ece6f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ece74  mov     r14d, eax
0x1800ece77  test    eax, eax
0x1800ece79  jz      short loc_1800ECE80
0x1800ece7b  jmp     loc_1800ED5DF
0x1800ece80  lea     rax, [rsp+228h+var_1D8]
0x1800ece85  mov     [rsp+228h+var_1B0], rax
0x1800ece8a  mov     r12d, 1
0x1800ece90  mov     [rsp+228h+var_1A8], r12b
0x1800ece98  mov     rdi, [rsp+228h+var_1D8]
0x1800ece9d  test    rdi, rdi
0x1800ecea0  jnz     short loc_1800ECEAA
0x1800ecea2  mov     r14d, r12d
0x1800ecea5  jmp     loc_1800ED5DF
0x1800eceaa  mov     r9d, 1Eh; unsigned int
0x1800eceb0  lea     r8, ?MDM_Policy_Config01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800eceb7  mov     rdx, rsi; struct _MI_Instance *
0x1800eceba  mov     rcx, rdi; this
0x1800ecebd  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800ecec2  mov     rax, [rdi]
0x1800ecec5  mov     rcx, rdi
0x1800ecec8  mov     rax, [rax+10h]
0x1800ececc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eced1  mov     r14d, eax
0x1800eced4  test    eax, eax
0x1800eced6  jz      short loc_1800ECEF6
0x1800eced8  mov     rcx, [rsp+228h+var_1D8]
0x1800ecedd  test    rcx, rcx
0x1800ecee0  jz      short loc_1800ECEF1
0x1800ecee2  mov     rax, [rcx]
0x1800ecee5  mov     edx, r12d
0x1800ecee8  mov     rax, [rax]
0x1800eceeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecef0  nop
0x1800ecef1  jmp     loc_1800ED5DF
0x1800ecef6  mov     rax, [rdi]
0x1800ecef9  mov     rcx, rdi
0x1800ecefc  mov     rax, [rax+8]
0x1800ecf00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf05  mov     r14d, eax
0x1800ecf08  test    eax, eax
0x1800ecf0a  jz      short loc_1800ECF2A
0x1800ecf0c  mov     rcx, [rsp+228h+var_1D8]
0x1800ecf11  test    rcx, rcx
0x1800ecf14  jz      short loc_1800ECF25
0x1800ecf16  mov     rax, [rcx]
0x1800ecf19  mov     edx, r12d
0x1800ecf1c  mov     rax, [rax]
0x1800ecf1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf24  nop
0x1800ecf25  jmp     loc_1800ED5DF
0x1800ecf2a  lea     r8, [rsp+228h+instance]; instance
0x1800ecf32  lea     rdx, MDM_Policy_Config01_TextInput02_rtti; classDecl
0x1800ecf39  mov     rcx, r15; context
0x1800ecf3c  call    MI_Context_ConstructInstance
0x1800ecf41  mov     r14d, eax
0x1800ecf44  test    eax, eax
0x1800ecf46  jz      short loc_1800ECF66
0x1800ecf48  mov     rcx, [rsp+228h+var_1D8]
0x1800ecf4d  test    rcx, rcx
0x1800ecf50  jz      short loc_1800ECF61
0x1800ecf52  mov     rax, [rcx]
0x1800ecf55  mov     edx, r12d
0x1800ecf58  mov     rax, [rax]
0x1800ecf5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf60  nop
0x1800ecf61  jmp     loc_1800ED5DF
0x1800ecf66  mov     [rsp+228h+var_1E0], r12b
0x1800ecf6b  mov     rdx, [rsi+40h]
0x1800ecf6f  lea     rcx, [rsp+228h+instance]
0x1800ecf77  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800ecf7c  mov     rdx, [rsi+50h]
0x1800ecf80  lea     rcx, [rsp+228h+instance]
0x1800ecf88  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800ecf8d  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ecf92  lea     rdx, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1800ecf99  mov     rcx, rdi; this
0x1800ecf9c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ecfa1  test    eax, eax
0x1800ecfa3  jnz     short loc_1800ECFC4
0x1800ecfa5  mov     rcx, [rsp+228h+String]; String
0x1800ecfaa  test    rcx, rcx
0x1800ecfad  jz      short loc_1800ECFC4
0x1800ecfaf  call    cs:__imp__wtoi
0x1800ecfb5  mov     [rsp+228h+var_118], eax
0x1800ecfbc  mov     [rsp+228h+var_114], r12b
0x1800ecfc4  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ecfc9  lea     rdx, aAllowimeloggin; "AllowIMELogging"
0x1800ecfd0  mov     rcx, rdi; this
0x1800ecfd3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ecfd8  test    eax, eax
0x1800ecfda  jnz     short loc_1800ECFFB
0x1800ecfdc  mov     rcx, [rsp+228h+String]; String
0x1800ecfe1  test    rcx, rcx
0x1800ecfe4  jz      short loc_1800ECFFB
0x1800ecfe6  call    cs:__imp__wtoi
0x1800ecfec  mov     [rsp+228h+var_110], eax
0x1800ecff3  mov     [rsp+228h+var_10C], r12b
0x1800ecffb  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed000  lea     rdx, aAllowimenetwor; "AllowIMENetworkAccess"
0x1800ed007  mov     rcx, rdi; this
0x1800ed00a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed00f  test    eax, eax
0x1800ed011  jnz     short loc_1800ED032
0x1800ed013  mov     rcx, [rsp+228h+String]; String
0x1800ed018  test    rcx, rcx
0x1800ed01b  jz      short loc_1800ED032
0x1800ed01d  call    cs:__imp__wtoi
0x1800ed023  mov     [rsp+228h+var_108], eax
0x1800ed02a  mov     [rsp+228h+var_104], r12b
0x1800ed032  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed037  lea     rdx, aAllowinputpane; "AllowInputPanel"
0x1800ed03e  mov     rcx, rdi; this
0x1800ed041  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed046  test    eax, eax
0x1800ed048  jnz     short loc_1800ED069
0x1800ed04a  mov     rcx, [rsp+228h+String]; String
0x1800ed04f  test    rcx, rcx
0x1800ed052  jz      short loc_1800ED069
0x1800ed054  call    cs:__imp__wtoi
0x1800ed05a  mov     [rsp+228h+var_100], eax
0x1800ed061  mov     [rsp+228h+var_FC], r12b
0x1800ed069  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed06e  lea     rdx, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1800ed075  mov     rcx, rdi; this
0x1800ed078  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed07d  test    eax, eax
0x1800ed07f  jnz     short loc_1800ED0A0
0x1800ed081  mov     rcx, [rsp+228h+String]; String
0x1800ed086  test    rcx, rcx
0x1800ed089  jz      short loc_1800ED0A0
0x1800ed08b  call    cs:__imp__wtoi
0x1800ed091  mov     [rsp+228h+var_F8], eax
0x1800ed098  mov     [rsp+228h+var_F4], r12b
0x1800ed0a0  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed0a5  lea     rdx, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1800ed0ac  mov     rcx, rdi; this
0x1800ed0af  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed0b4  test    eax, eax
0x1800ed0b6  jnz     short loc_1800ED0D7
0x1800ed0b8  mov     rcx, [rsp+228h+String]; String
0x1800ed0bd  test    rcx, rcx
0x1800ed0c0  jz      short loc_1800ED0D7
0x1800ed0c2  call    cs:__imp__wtoi
0x1800ed0c8  mov     [rsp+228h+var_F0], eax
0x1800ed0cf  mov     [rsp+228h+var_EC], r12b
0x1800ed0d7  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed0dc  lea     rdx, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1800ed0e3  mov     rcx, rdi; this
0x1800ed0e6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed0eb  test    eax, eax
0x1800ed0ed  jnz     short loc_1800ED10E
0x1800ed0ef  mov     rcx, [rsp+228h+String]; String
0x1800ed0f4  test    rcx, rcx
0x1800ed0f7  jz      short loc_1800ED10E
0x1800ed0f9  call    cs:__imp__wtoi
0x1800ed0ff  mov     [rsp+228h+var_E8], eax
0x1800ed106  mov     [rsp+228h+var_E4], r12b
0x1800ed10e  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed113  lea     rdx, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1800ed11a  mov     rcx, rdi; this
0x1800ed11d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed122  test    eax, eax
0x1800ed124  jnz     short loc_1800ED145
0x1800ed126  mov     rcx, [rsp+228h+String]; String
0x1800ed12b  test    rcx, rcx
0x1800ed12e  jz      short loc_1800ED145
0x1800ed130  call    cs:__imp__wtoi
0x1800ed136  mov     [rsp+228h+var_E0], eax
0x1800ed13d  mov     [rsp+228h+var_DC], r12b
0x1800ed145  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed14a  lea     rdx, aAllowkeyboardt; "AllowKeyboardTextSuggestions"
0x1800ed151  mov     rcx, rdi; this
0x1800ed154  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed159  test    eax, eax
0x1800ed15b  jnz     short loc_1800ED17C
0x1800ed15d  mov     rcx, [rsp+228h+String]; String
0x1800ed162  test    rcx, rcx
0x1800ed165  jz      short loc_1800ED17C
0x1800ed167  call    cs:__imp__wtoi
0x1800ed16d  mov     [rsp+228h+var_D8], eax
0x1800ed174  mov     [rsp+228h+var_D4], r12b
0x1800ed17c  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed181  lea     rdx, aAllowlanguagef; "AllowLanguageFeaturesUninstall"
0x1800ed188  mov     rcx, rdi; this
0x1800ed18b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed190  test    eax, eax
0x1800ed192  jnz     short loc_1800ED1B3
0x1800ed194  mov     rcx, [rsp+228h+String]; String
0x1800ed199  test    rcx, rcx
0x1800ed19c  jz      short loc_1800ED1B3
0x1800ed19e  call    cs:__imp__wtoi
0x1800ed1a4  mov     [rsp+228h+var_D0], eax
0x1800ed1ab  mov     [rsp+228h+var_CC], r12b
0x1800ed1b3  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed1b8  lea     rdx, aAllowlinguisti; "AllowLinguisticDataCollection"
0x1800ed1bf  mov     rcx, rdi; this
0x1800ed1c2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed1c7  test    eax, eax
0x1800ed1c9  jnz     short loc_1800ED1EA
0x1800ed1cb  mov     rcx, [rsp+228h+String]; String
0x1800ed1d0  test    rcx, rcx
0x1800ed1d3  jz      short loc_1800ED1EA
0x1800ed1d5  call    cs:__imp__wtoi
0x1800ed1db  mov     [rsp+228h+var_C8], eax
0x1800ed1e2  mov     [rsp+228h+var_C4], r12b
0x1800ed1ea  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed1ef  lea     rdx, aAllowtextinput; "AllowTextInputSuggestionUpdate"
0x1800ed1f6  mov     rcx, rdi; this
0x1800ed1f9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed1fe  test    eax, eax
0x1800ed200  jnz     short loc_1800ED221
0x1800ed202  mov     rcx, [rsp+228h+String]; String
0x1800ed207  test    rcx, rcx
0x1800ed20a  jz      short loc_1800ED221
0x1800ed20c  call    cs:__imp__wtoi
0x1800ed212  mov     [rsp+228h+var_C0], eax
0x1800ed219  mov     [rsp+228h+var_BC], r12b
0x1800ed221  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ed226  lea     rdx, aConfigurejapan; "ConfigureJapaneseIMEVersion"
0x1800ed22d  mov     rcx, rdi; this
0x1800ed230  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ed235  test    eax, eax
0x1800ed237  jnz     short loc_1800ED258
0x1800ed239  mov     rcx, [rsp+228h+String]; String
0x1800ed23e  test    rcx, rcx
0x1800ed241  jz      short loc_1800ED258
  ... truncated ...
```
