# MDM_Policy_Config01_TextInput02_InvokeGetInstance

- ea: `0x1800ec56c`
- end: `0x1800ecf7f`
- name: `MDM_Policy_Config01_TextInput02_InvokeGetInstance`
- size: `2579`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800eac80`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800ec56c`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800ec80b`
- `msvcrt!_wtoi` at `0x1800ec848`
- `msvcrt!_wtoi` at `0x1800ec885`
- `msvcrt!_wtoi` at `0x1800ec8c2`
- `msvcrt!_wtoi` at `0x1800ec8ff`
- `msvcrt!_wtoi` at `0x1800ec93c`
- `msvcrt!_wtoi` at `0x1800ec979`
- `msvcrt!_wtoi` at `0x1800ec9b6`
- `msvcrt!_wtoi` at `0x1800ec9f3`
- `msvcrt!_wtoi` at `0x1800eca30`
- `msvcrt!_wtoi` at `0x1800eca6d`
- `msvcrt!_wtoi` at `0x1800ecaaa`
- `msvcrt!_wtoi` at `0x1800ecae7`
- `msvcrt!_wtoi` at `0x1800ecb24`
- `msvcrt!_wtoi` at `0x1800ecb61`
- `msvcrt!_wtoi` at `0x1800ecb9e`
- `msvcrt!_wtoi` at `0x1800ecbdb`
- `msvcrt!_wtoi` at `0x1800ecc18`
- `msvcrt!_wtoi` at `0x1800ecc55`
- `msvcrt!_wtoi` at `0x1800ecc92`
- `msvcrt!_wtoi` at `0x1800ecccf`
- `msvcrt!_wtoi` at `0x1800ecd0c`
- `msvcrt!_wtoi` at `0x1800ecd49`
- `msvcrt!_wtoi` at `0x1800ecd86`
- `msvcrt!_wtoi` at `0x1800ecdc3`
- `msvcrt!_wtoi` at `0x1800ece00`
- `msvcrt!_wtoi` at `0x1800ece3d`
- `msvcrt!_wtoi` at `0x1800ece7a`
- `msvcrt!_wtoi` at `0x1800ec80b`
- `msvcrt!_wtoi` at `0x1800ec848`
- `msvcrt!_wtoi` at `0x1800ec885`
- `msvcrt!_wtoi` at `0x1800ec8c2`
- `msvcrt!_wtoi` at `0x1800ec8ff`
- `msvcrt!_wtoi` at `0x1800ec93c`
- `msvcrt!_wtoi` at `0x1800ec979`
- `msvcrt!_wtoi` at `0x1800ec9b6`
- `msvcrt!_wtoi` at `0x1800ec9f3`
- `msvcrt!_wtoi` at `0x1800eca30`
- `msvcrt!_wtoi` at `0x1800eca6d`
- `msvcrt!_wtoi` at `0x1800ecaaa`
- `msvcrt!_wtoi` at `0x1800ecae7`
- `msvcrt!_wtoi` at `0x1800ecb24`
- `msvcrt!_wtoi` at `0x1800ecb61`
- `msvcrt!_wtoi` at `0x1800ecb9e`
- `msvcrt!_wtoi` at `0x1800ecbdb`
- `msvcrt!_wtoi` at `0x1800ecc18`
- `msvcrt!_wtoi` at `0x1800ecc55`
- `msvcrt!_wtoi` at `0x1800ecc92`
- `msvcrt!_wtoi` at `0x1800ecccf`
- `msvcrt!_wtoi` at `0x1800ecd0c`
- `msvcrt!_wtoi` at `0x1800ecd49`
- `msvcrt!_wtoi` at `0x1800ecd86`
- `msvcrt!_wtoi` at `0x1800ecdc3`
- `msvcrt!_wtoi` at `0x1800ece00`
- `msvcrt!_wtoi` at `0x1800ece3d`
- `msvcrt!_wtoi` at `0x1800ece7a`

## string_xrefs

- `0x1800ec868`: `AllowIMENetworkAccess`
- `0x1800eca13`: `AllowLanguageFeaturesUninstall`
- `0x1800eca8d`: `AllowTextInputSuggestionUpdate`
- `0x1800ecaca`: `ConfigureJapaneseIMEVersion`
- `0x1800ecb07`: `ConfigureKoreanIMEVersion`
- `0x1800ecb44`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1800ecb81`: `ConfigureTraditionalChineseIMEVersion`
- `0x1800ec5db`: `MDM_Policy_Config01_TextInput02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_TextInput02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
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
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_113;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       a2[1].serverName,
                       a2[1].ft,
                       &MDM_Policy_Config01_TextInput02_NodeList,
                       30,
                       0,
                       &v10);
  if ( v5 == MI_RESULT_OK )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = MI_RESULT_FAILED;
      goto LABEL_113;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_TextInput02_NodeList,
      0x1Eu);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_113;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_113;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowHardwareKeyboardTextSuggestions",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowIMELogging", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowIMENetworkAccess", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowInputPanel", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowJapaneseIMESurrogatePairCharacters",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowJapaneseIVSCharacters", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowJapaneseNonPublishingStandardGlyph",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowJapaneseUserDictionary",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowKeyboardTextSuggestions",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v34 = _wtoi(String);
      v35 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowLanguageFeaturesUninstall",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v36 = _wtoi(String);
      v37 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowLinguisticDataCollection",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v38 = _wtoi(String);
      v39 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowTextInputSuggestionUpdate",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v40 = _wtoi(String);
      v41 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureJapaneseIMEVersion",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v42 = _wtoi(String);
      v43 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ConfigureKoreanIMEVersion", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v44 = _wtoi(String);
      v45 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureSimplifiedChineseIMEVersion",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v46 = _wtoi(String);
      v47 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigureTraditionalChineseIMEVersion",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v48 = _wtoi(String);
      v49 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"EnableTouchKeyboardAutoInvokeInDesktopMode",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v50 = _wtoi(String);
      v51 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ExcludeJapaneseIMEExceptJIS0208",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v52 = _wtoi(String);
      v53 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ExcludeJapaneseIMEExceptJIS0208andEUDC",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v54 = _wtoi(String);
      v55 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ExcludeJapaneseIMEExceptShiftJIS",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v56 = _wtoi(String);
      v57 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ForceTouchKeyboardDockedState",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v58 = _wtoi(String);
      v59 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"TouchKeyboardDictationButtonAvailability",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v60 = _wtoi(String);
      v61 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"TouchKeyboardEmojiButtonAvailability",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v62 = _wtoi(String);
      v63 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"TouchKeyboardFullModeAvailability",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v64 = _wtoi(String);
      v65 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"TouchKeyboardHandwritingModeAvailability",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v66 = _wtoi(String);
      v67 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"TouchKeyboardNarrowModeAvailability",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v68 = _wtoi(String);
      v69 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"TouchKeyboardSplitModeAvailability",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v70 = _wtoi(String);
      v71 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"TouchKeyboardWideModeAvailability",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ec56c  mov     [rsp+arg_10], rbx
0x1800ec571  push    rsi
0x1800ec572  push    rdi
0x1800ec573  push    r12
0x1800ec575  push    r14
0x1800ec577  push    r15
0x1800ec579  sub     rsp, 200h
0x1800ec580  mov     rax, cs:__security_cookie
0x1800ec587  xor     rax, rsp
0x1800ec58a  mov     [rsp+228h+var_38], rax
0x1800ec592  mov     rsi, rdx
0x1800ec595  mov     r15, rcx
0x1800ec598  xor     ebx, ebx
0x1800ec59a  mov     [rsp+228h+String], rbx
0x1800ec59f  xor     edx, edx; Val
0x1800ec5a1  mov     r8d, 140h; Size
0x1800ec5a7  lea     rcx, [rsp+228h+instance]; void *
0x1800ec5af  call    memset_0
0x1800ec5b4  mov     [rsp+228h+var_1A0], ebx
0x1800ec5bb  mov     [rsp+228h+var_19C], bl
0x1800ec5c2  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ec5c9  mov     [rsp+228h+var_1D0], rax
0x1800ec5ce  lea     rax, [rsp+228h+var_1A0]
0x1800ec5d6  mov     [rsp+228h+var_1C8], rax
0x1800ec5db  lea     rax, aMdmPolicyConfi_92; "MDM_Policy_Config01_TextInput02"
0x1800ec5e2  mov     [rsp+228h+var_1C0], rax
0x1800ec5e7  lea     rcx, [rsp+228h+var_1A0]
0x1800ec5ef  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ec5f4  mov     eax, cs:dword_180380B68
0x1800ec5fa  cmp     eax, 5
0x1800ec5fd  jbe     short loc_1800EC66E
0x1800ec5ff  mov     rdx, 200000000000h
0x1800ec609  lea     rcx, dword_180380B68
0x1800ec610  call    _tlgKeywordOn
0x1800ec615  test    al, al
0x1800ec617  jz      short loc_1800EC66E
0x1800ec619  cmp     [rsp+228h+var_19C], bl
0x1800ec620  jz      short loc_1800EC650
0x1800ec622  cmp     [rsp+228h+var_188], ebx
0x1800ec629  jnz     short loc_1800EC646
0x1800ec62b  cmp     [rsp+228h+var_184], ebx
0x1800ec632  jnz     short loc_1800EC646
0x1800ec634  cmp     [rsp+228h+var_180], ebx
0x1800ec63b  jnz     short loc_1800EC646
0x1800ec63d  cmp     [rsp+228h+var_17C], ebx
0x1800ec644  jz      short loc_1800EC650
0x1800ec646  lea     r9, [rsp+228h+var_188]
0x1800ec64e  jmp     short loc_1800EC653
0x1800ec650  mov     r9, rbx
0x1800ec653  lea     r8, [rsp+228h+var_198]
0x1800ec65b  lea     rdx, word_18033695E
0x1800ec662  lea     rcx, dword_180380B68
0x1800ec669  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ec66e  cmp     [rsi+48h], bl
0x1800ec671  jz      loc_1800ECEDD
0x1800ec677  mov     [rsp+228h+var_1E0], bl
0x1800ec67b  cmp     [rsi+58h], bl
0x1800ec67e  jz      loc_1800ECEDD
0x1800ec684  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800ec688  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800ec68c  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800ec693  lea     rcx, [rsp+228h+var_1D0]; this
0x1800ec698  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800ec69d  nop
0x1800ec69e  mov     [rsp+228h+var_1D8], rbx
0x1800ec6a3  lea     rax, [rsp+228h+var_1D8]
0x1800ec6a8  mov     [rsp+228h+var_1F8], rax
0x1800ec6ad  mov     [rsp+228h+var_200], ebx
0x1800ec6b1  mov     [rsp+228h+var_208], 1Eh
0x1800ec6b9  lea     r9, ?MDM_Policy_Config01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TextInput02_NodeList
0x1800ec6c0  mov     r8, [rsi+40h]
0x1800ec6c4  mov     rdx, [rsi+50h]
0x1800ec6c8  mov     rcx, r15
0x1800ec6cb  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ec6d0  mov     r14d, eax
0x1800ec6d3  test    eax, eax
0x1800ec6d5  jz      short loc_1800EC6DC
0x1800ec6d7  jmp     loc_1800ECEE3
0x1800ec6dc  lea     rax, [rsp+228h+var_1D8]
0x1800ec6e1  mov     [rsp+228h+var_1B0], rax
0x1800ec6e6  mov     r12d, 1
0x1800ec6ec  mov     [rsp+228h+var_1A8], r12b
0x1800ec6f4  mov     rdi, [rsp+228h+var_1D8]
0x1800ec6f9  test    rdi, rdi
0x1800ec6fc  jnz     short loc_1800EC706
0x1800ec6fe  mov     r14d, r12d
0x1800ec701  jmp     loc_1800ECEE3
0x1800ec706  mov     r9d, 1Eh; unsigned int
0x1800ec70c  lea     r8, ?MDM_Policy_Config01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800ec713  mov     rdx, rsi; struct _MI_Instance *
0x1800ec716  mov     rcx, rdi; this
0x1800ec719  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800ec71e  mov     rax, [rdi]
0x1800ec721  mov     rcx, rdi
0x1800ec724  mov     rax, [rax+10h]
0x1800ec728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec72d  mov     r14d, eax
0x1800ec730  test    eax, eax
0x1800ec732  jz      short loc_1800EC752
0x1800ec734  mov     rcx, [rsp+228h+var_1D8]
0x1800ec739  test    rcx, rcx
0x1800ec73c  jz      short loc_1800EC74D
0x1800ec73e  mov     rax, [rcx]
0x1800ec741  mov     edx, r12d
0x1800ec744  mov     rax, [rax]
0x1800ec747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec74c  nop
0x1800ec74d  jmp     loc_1800ECEE3
0x1800ec752  mov     rax, [rdi]
0x1800ec755  mov     rcx, rdi
0x1800ec758  mov     rax, [rax+8]
0x1800ec75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec761  mov     r14d, eax
0x1800ec764  test    eax, eax
0x1800ec766  jz      short loc_1800EC786
0x1800ec768  mov     rcx, [rsp+228h+var_1D8]
0x1800ec76d  test    rcx, rcx
0x1800ec770  jz      short loc_1800EC781
0x1800ec772  mov     rax, [rcx]
0x1800ec775  mov     edx, r12d
0x1800ec778  mov     rax, [rax]
0x1800ec77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec780  nop
0x1800ec781  jmp     loc_1800ECEE3
0x1800ec786  lea     r8, [rsp+228h+instance]; instance
0x1800ec78e  lea     rdx, MDM_Policy_Config01_TextInput02_rtti; classDecl
0x1800ec795  mov     rcx, r15; context
0x1800ec798  call    MI_Context_ConstructInstance
0x1800ec79d  mov     r14d, eax
0x1800ec7a0  test    eax, eax
0x1800ec7a2  jz      short loc_1800EC7C2
0x1800ec7a4  mov     rcx, [rsp+228h+var_1D8]
0x1800ec7a9  test    rcx, rcx
0x1800ec7ac  jz      short loc_1800EC7BD
0x1800ec7ae  mov     rax, [rcx]
0x1800ec7b1  mov     edx, r12d
0x1800ec7b4  mov     rax, [rax]
0x1800ec7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec7bc  nop
0x1800ec7bd  jmp     loc_1800ECEE3
0x1800ec7c2  mov     [rsp+228h+var_1E0], r12b
0x1800ec7c7  mov     rdx, [rsi+40h]
0x1800ec7cb  lea     rcx, [rsp+228h+instance]
0x1800ec7d3  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800ec7d8  mov     rdx, [rsi+50h]
0x1800ec7dc  lea     rcx, [rsp+228h+instance]
0x1800ec7e4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800ec7e9  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec7ee  lea     rdx, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1800ec7f5  mov     rcx, rdi; this
0x1800ec7f8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec7fd  test    eax, eax
0x1800ec7ff  jnz     short loc_1800EC826
0x1800ec801  mov     rcx, [rsp+228h+String]; String
0x1800ec806  test    rcx, rcx
0x1800ec809  jz      short loc_1800EC826
0x1800ec80b  call    cs:__imp__wtoi
0x1800ec812  nop     dword ptr [rax+rax+00h]
0x1800ec817  mov     [rsp+228h+var_118], eax
0x1800ec81e  mov     [rsp+228h+var_114], r12b
0x1800ec826  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec82b  lea     rdx, aAllowimeloggin; "AllowIMELogging"
0x1800ec832  mov     rcx, rdi; this
0x1800ec835  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec83a  test    eax, eax
0x1800ec83c  jnz     short loc_1800EC863
0x1800ec83e  mov     rcx, [rsp+228h+String]; String
0x1800ec843  test    rcx, rcx
0x1800ec846  jz      short loc_1800EC863
0x1800ec848  call    cs:__imp__wtoi
0x1800ec84f  nop     dword ptr [rax+rax+00h]
0x1800ec854  mov     [rsp+228h+var_110], eax
0x1800ec85b  mov     [rsp+228h+var_10C], r12b
0x1800ec863  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec868  lea     rdx, aAllowimenetwor; "AllowIMENetworkAccess"
0x1800ec86f  mov     rcx, rdi; this
0x1800ec872  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec877  test    eax, eax
0x1800ec879  jnz     short loc_1800EC8A0
0x1800ec87b  mov     rcx, [rsp+228h+String]; String
0x1800ec880  test    rcx, rcx
0x1800ec883  jz      short loc_1800EC8A0
0x1800ec885  call    cs:__imp__wtoi
0x1800ec88c  nop     dword ptr [rax+rax+00h]
0x1800ec891  mov     [rsp+228h+var_108], eax
0x1800ec898  mov     [rsp+228h+var_104], r12b
0x1800ec8a0  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec8a5  lea     rdx, aAllowinputpane; "AllowInputPanel"
0x1800ec8ac  mov     rcx, rdi; this
0x1800ec8af  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec8b4  test    eax, eax
0x1800ec8b6  jnz     short loc_1800EC8DD
0x1800ec8b8  mov     rcx, [rsp+228h+String]; String
0x1800ec8bd  test    rcx, rcx
0x1800ec8c0  jz      short loc_1800EC8DD
0x1800ec8c2  call    cs:__imp__wtoi
0x1800ec8c9  nop     dword ptr [rax+rax+00h]
0x1800ec8ce  mov     [rsp+228h+var_100], eax
0x1800ec8d5  mov     [rsp+228h+var_FC], r12b
0x1800ec8dd  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec8e2  lea     rdx, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1800ec8e9  mov     rcx, rdi; this
0x1800ec8ec  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec8f1  test    eax, eax
0x1800ec8f3  jnz     short loc_1800EC91A
0x1800ec8f5  mov     rcx, [rsp+228h+String]; String
0x1800ec8fa  test    rcx, rcx
0x1800ec8fd  jz      short loc_1800EC91A
0x1800ec8ff  call    cs:__imp__wtoi
0x1800ec906  nop     dword ptr [rax+rax+00h]
0x1800ec90b  mov     [rsp+228h+var_F8], eax
0x1800ec912  mov     [rsp+228h+var_F4], r12b
0x1800ec91a  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec91f  lea     rdx, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1800ec926  mov     rcx, rdi; this
0x1800ec929  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec92e  test    eax, eax
0x1800ec930  jnz     short loc_1800EC957
0x1800ec932  mov     rcx, [rsp+228h+String]; String
0x1800ec937  test    rcx, rcx
0x1800ec93a  jz      short loc_1800EC957
0x1800ec93c  call    cs:__imp__wtoi
0x1800ec943  nop     dword ptr [rax+rax+00h]
0x1800ec948  mov     [rsp+228h+var_F0], eax
0x1800ec94f  mov     [rsp+228h+var_EC], r12b
0x1800ec957  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec95c  lea     rdx, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1800ec963  mov     rcx, rdi; this
0x1800ec966  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec96b  test    eax, eax
0x1800ec96d  jnz     short loc_1800EC994
0x1800ec96f  mov     rcx, [rsp+228h+String]; String
0x1800ec974  test    rcx, rcx
0x1800ec977  jz      short loc_1800EC994
0x1800ec979  call    cs:__imp__wtoi
0x1800ec980  nop     dword ptr [rax+rax+00h]
0x1800ec985  mov     [rsp+228h+var_E8], eax
0x1800ec98c  mov     [rsp+228h+var_E4], r12b
0x1800ec994  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec999  lea     rdx, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1800ec9a0  mov     rcx, rdi; this
0x1800ec9a3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec9a8  test    eax, eax
0x1800ec9aa  jnz     short loc_1800EC9D1
0x1800ec9ac  mov     rcx, [rsp+228h+String]; String
0x1800ec9b1  test    rcx, rcx
0x1800ec9b4  jz      short loc_1800EC9D1
0x1800ec9b6  call    cs:__imp__wtoi
0x1800ec9bd  nop     dword ptr [rax+rax+00h]
0x1800ec9c2  mov     [rsp+228h+var_E0], eax
0x1800ec9c9  mov     [rsp+228h+var_DC], r12b
0x1800ec9d1  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800ec9d6  lea     rdx, aAllowkeyboardt; "AllowKeyboardTextSuggestions"
0x1800ec9dd  mov     rcx, rdi; this
0x1800ec9e0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800ec9e5  test    eax, eax
0x1800ec9e7  jnz     short loc_1800ECA0E
0x1800ec9e9  mov     rcx, [rsp+228h+String]; String
0x1800ec9ee  test    rcx, rcx
0x1800ec9f1  jz      short loc_1800ECA0E
0x1800ec9f3  call    cs:__imp__wtoi
0x1800ec9fa  nop     dword ptr [rax+rax+00h]
0x1800ec9ff  mov     [rsp+228h+var_D8], eax
0x1800eca06  mov     [rsp+228h+var_D4], r12b
0x1800eca0e  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800eca13  lea     rdx, aAllowlanguagef; "AllowLanguageFeaturesUninstall"
0x1800eca1a  mov     rcx, rdi; this
0x1800eca1d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800eca22  test    eax, eax
0x1800eca24  jnz     short loc_1800ECA4B
0x1800eca26  mov     rcx, [rsp+228h+String]; String
0x1800eca2b  test    rcx, rcx
0x1800eca2e  jz      short loc_1800ECA4B
0x1800eca30  call    cs:__imp__wtoi
0x1800eca37  nop     dword ptr [rax+rax+00h]
0x1800eca3c  mov     [rsp+228h+var_D0], eax
0x1800eca43  mov     [rsp+228h+var_CC], r12b
0x1800eca4b  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800eca50  lea     rdx, aAllowlinguisti; "AllowLinguisticDataCollection"
0x1800eca57  mov     rcx, rdi; this
0x1800eca5a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800eca5f  test    eax, eax
0x1800eca61  jnz     short loc_1800ECA88
0x1800eca63  mov     rcx, [rsp+228h+String]; String
0x1800eca68  test    rcx, rcx
0x1800eca6b  jz      short loc_1800ECA88
0x1800eca6d  call    cs:__imp__wtoi
0x1800eca74  nop     dword ptr [rax+rax+00h]
0x1800eca79  mov     [rsp+228h+var_C8], eax
0x1800eca80  mov     [rsp+228h+var_C4], r12b
0x1800eca88  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1800eca8d  lea     rdx, aAllowtextinput; "AllowTextInputSuggestionUpdate"
0x1800eca94  mov     rcx, rdi; this
0x1800eca97  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800eca9c  test    eax, eax
0x1800eca9e  jnz     short loc_1800ECAC5
0x1800ecaa0  mov     rcx, [rsp+228h+String]; String
0x1800ecaa5  test    rcx, rcx
0x1800ecaa8  jz      short loc_1800ECAC5
0x1800ecaaa  call    cs:__imp__wtoi
  ... truncated ...
```
