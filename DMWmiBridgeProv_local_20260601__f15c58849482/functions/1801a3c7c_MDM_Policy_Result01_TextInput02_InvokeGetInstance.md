# MDM_Policy_Result01_TextInput02_InvokeGetInstance

- ea: `0x1801a3c7c`
- end: `0x1801a468f`
- name: `MDM_Policy_Result01_TextInput02_InvokeGetInstance`
- size: `2579`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1801a2390`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801a3c7c`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801a3f1b`
- `msvcrt!_wtoi` at `0x1801a3f58`
- `msvcrt!_wtoi` at `0x1801a3f95`
- `msvcrt!_wtoi` at `0x1801a3fd2`
- `msvcrt!_wtoi` at `0x1801a400f`
- `msvcrt!_wtoi` at `0x1801a404c`
- `msvcrt!_wtoi` at `0x1801a4089`
- `msvcrt!_wtoi` at `0x1801a40c6`
- `msvcrt!_wtoi` at `0x1801a4103`
- `msvcrt!_wtoi` at `0x1801a4140`
- `msvcrt!_wtoi` at `0x1801a417d`
- `msvcrt!_wtoi` at `0x1801a41ba`
- `msvcrt!_wtoi` at `0x1801a41f7`
- `msvcrt!_wtoi` at `0x1801a4234`
- `msvcrt!_wtoi` at `0x1801a4271`
- `msvcrt!_wtoi` at `0x1801a42ae`
- `msvcrt!_wtoi` at `0x1801a42eb`
- `msvcrt!_wtoi` at `0x1801a4328`
- `msvcrt!_wtoi` at `0x1801a4365`
- `msvcrt!_wtoi` at `0x1801a43a2`
- `msvcrt!_wtoi` at `0x1801a43df`
- `msvcrt!_wtoi` at `0x1801a441c`
- `msvcrt!_wtoi` at `0x1801a4459`
- `msvcrt!_wtoi` at `0x1801a4496`
- `msvcrt!_wtoi` at `0x1801a44d3`
- `msvcrt!_wtoi` at `0x1801a4510`
- `msvcrt!_wtoi` at `0x1801a454d`
- `msvcrt!_wtoi` at `0x1801a458a`
- `msvcrt!_wtoi` at `0x1801a3f1b`
- `msvcrt!_wtoi` at `0x1801a3f58`
- `msvcrt!_wtoi` at `0x1801a3f95`
- `msvcrt!_wtoi` at `0x1801a3fd2`
- `msvcrt!_wtoi` at `0x1801a400f`
- `msvcrt!_wtoi` at `0x1801a404c`
- `msvcrt!_wtoi` at `0x1801a4089`
- `msvcrt!_wtoi` at `0x1801a40c6`
- `msvcrt!_wtoi` at `0x1801a4103`
- `msvcrt!_wtoi` at `0x1801a4140`
- `msvcrt!_wtoi` at `0x1801a417d`
- `msvcrt!_wtoi` at `0x1801a41ba`
- `msvcrt!_wtoi` at `0x1801a41f7`
- `msvcrt!_wtoi` at `0x1801a4234`
- `msvcrt!_wtoi` at `0x1801a4271`
- `msvcrt!_wtoi` at `0x1801a42ae`
- `msvcrt!_wtoi` at `0x1801a42eb`
- `msvcrt!_wtoi` at `0x1801a4328`
- `msvcrt!_wtoi` at `0x1801a4365`
- `msvcrt!_wtoi` at `0x1801a43a2`
- `msvcrt!_wtoi` at `0x1801a43df`
- `msvcrt!_wtoi` at `0x1801a441c`
- `msvcrt!_wtoi` at `0x1801a4459`
- `msvcrt!_wtoi` at `0x1801a4496`
- `msvcrt!_wtoi` at `0x1801a44d3`
- `msvcrt!_wtoi` at `0x1801a4510`
- `msvcrt!_wtoi` at `0x1801a454d`
- `msvcrt!_wtoi` at `0x1801a458a`

## string_xrefs

- `0x1801a3f78`: `AllowIMENetworkAccess`
- `0x1801a4123`: `AllowLanguageFeaturesUninstall`
- `0x1801a419d`: `AllowTextInputSuggestionUpdate`
- `0x1801a41da`: `ConfigureJapaneseIMEVersion`
- `0x1801a4217`: `ConfigureKoreanIMEVersion`
- `0x1801a4254`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1801a4291`: `ConfigureTraditionalChineseIMEVersion`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_TextInput02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v11[2] = "MDM_Policy_Result01_TextInput02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18034995B,
      v15,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                         &MDM_Policy_Result01_TextInput02_NodeList,
                         30,
                         0,
                         &v10);
    if ( v5 == MI_RESULT_OK )
    {
      v11[4] = &v10;
      v12 = 1;
      v6 = v10;
      if ( v10 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v10,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_TextInput02_NodeList,
          0x1Eu);
        v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( v5 )
          {
            if ( v10 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
          }
          else
          {
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_TextInput02_rtti, &instance);
            if ( v5 )
            {
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
            }
            else
            {
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowIMENetworkAccess",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowJapaneseIVSCharacters",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ConfigureKoreanIMEVersion",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
          }
        }
      }
      else
      {
        v5 = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033CCF3,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801a3c7c  mov     [rsp+arg_10], rbx
0x1801a3c81  push    rsi
0x1801a3c82  push    rdi
0x1801a3c83  push    r12
0x1801a3c85  push    r14
0x1801a3c87  push    r15
0x1801a3c89  sub     rsp, 200h
0x1801a3c90  mov     rax, cs:__security_cookie
0x1801a3c97  xor     rax, rsp
0x1801a3c9a  mov     [rsp+228h+var_38], rax
0x1801a3ca2  mov     rsi, rdx
0x1801a3ca5  mov     r15, rcx
0x1801a3ca8  xor     ebx, ebx
0x1801a3caa  mov     [rsp+228h+String], rbx
0x1801a3caf  xor     edx, edx; Val
0x1801a3cb1  mov     r8d, 140h; Size
0x1801a3cb7  lea     rcx, [rsp+228h+instance]; void *
0x1801a3cbf  call    memset_0
0x1801a3cc4  mov     [rsp+228h+var_1A0], ebx
0x1801a3ccb  mov     [rsp+228h+var_19C], bl
0x1801a3cd2  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801a3cd9  mov     [rsp+228h+var_1D0], rax
0x1801a3cde  lea     rax, [rsp+228h+var_1A0]
0x1801a3ce6  mov     [rsp+228h+var_1C8], rax
0x1801a3ceb  lea     rax, aMdmPolicyResul_132; "MDM_Policy_Result01_TextInput02"
0x1801a3cf2  mov     [rsp+228h+var_1C0], rax
0x1801a3cf7  lea     rcx, [rsp+228h+var_1A0]
0x1801a3cff  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801a3d04  mov     eax, cs:dword_180380B68
0x1801a3d0a  cmp     eax, 5
0x1801a3d0d  jbe     short loc_1801A3D7E
0x1801a3d0f  mov     rdx, 200000000000h
0x1801a3d19  lea     rcx, dword_180380B68
0x1801a3d20  call    _tlgKeywordOn
0x1801a3d25  test    al, al
0x1801a3d27  jz      short loc_1801A3D7E
0x1801a3d29  cmp     [rsp+228h+var_19C], bl
0x1801a3d30  jz      short loc_1801A3D60
0x1801a3d32  cmp     [rsp+228h+var_188], ebx
0x1801a3d39  jnz     short loc_1801A3D56
0x1801a3d3b  cmp     [rsp+228h+var_184], ebx
0x1801a3d42  jnz     short loc_1801A3D56
0x1801a3d44  cmp     [rsp+228h+var_180], ebx
0x1801a3d4b  jnz     short loc_1801A3D56
0x1801a3d4d  cmp     [rsp+228h+var_17C], ebx
0x1801a3d54  jz      short loc_1801A3D60
0x1801a3d56  lea     r9, [rsp+228h+var_188]
0x1801a3d5e  jmp     short loc_1801A3D63
0x1801a3d60  mov     r9, rbx
0x1801a3d63  lea     r8, [rsp+228h+var_198]
0x1801a3d6b  lea     rdx, byte_18034995B
0x1801a3d72  lea     rcx, dword_180380B68
0x1801a3d79  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801a3d7e  cmp     [rsi+48h], bl
0x1801a3d81  jz      loc_1801A45ED
0x1801a3d87  mov     [rsp+228h+var_1E0], bl
0x1801a3d8b  cmp     [rsi+58h], bl
0x1801a3d8e  jz      loc_1801A45ED
0x1801a3d94  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801a3d98  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801a3d9c  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801a3da3  lea     rcx, [rsp+228h+var_1D0]; this
0x1801a3da8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801a3dad  nop
0x1801a3dae  mov     [rsp+228h+var_1D8], rbx
0x1801a3db3  lea     rax, [rsp+228h+var_1D8]
0x1801a3db8  mov     [rsp+228h+var_1F8], rax
0x1801a3dbd  mov     [rsp+228h+var_200], ebx
0x1801a3dc1  mov     [rsp+228h+var_208], 1Eh
0x1801a3dc9  lea     r9, ?MDM_Policy_Result01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_TextInput02_NodeList
0x1801a3dd0  mov     r8, [rsi+40h]
0x1801a3dd4  mov     rdx, [rsi+50h]
0x1801a3dd8  mov     rcx, r15
0x1801a3ddb  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801a3de0  mov     r14d, eax
0x1801a3de3  test    eax, eax
0x1801a3de5  jz      short loc_1801A3DEC
0x1801a3de7  jmp     loc_1801A45F3
0x1801a3dec  lea     rax, [rsp+228h+var_1D8]
0x1801a3df1  mov     [rsp+228h+var_1B0], rax
0x1801a3df6  mov     r12d, 1
0x1801a3dfc  mov     [rsp+228h+var_1A8], r12b
0x1801a3e04  mov     rdi, [rsp+228h+var_1D8]
0x1801a3e09  test    rdi, rdi
0x1801a3e0c  jnz     short loc_1801A3E16
0x1801a3e0e  mov     r14d, r12d
0x1801a3e11  jmp     loc_1801A45F3
0x1801a3e16  mov     r9d, 1Eh; unsigned int
0x1801a3e1c  lea     r8, ?MDM_Policy_Result01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801a3e23  mov     rdx, rsi; struct _MI_Instance *
0x1801a3e26  mov     rcx, rdi; this
0x1801a3e29  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801a3e2e  mov     rax, [rdi]
0x1801a3e31  mov     rcx, rdi
0x1801a3e34  mov     rax, [rax+10h]
0x1801a3e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3e3d  mov     r14d, eax
0x1801a3e40  test    eax, eax
0x1801a3e42  jz      short loc_1801A3E62
0x1801a3e44  mov     rcx, [rsp+228h+var_1D8]
0x1801a3e49  test    rcx, rcx
0x1801a3e4c  jz      short loc_1801A3E5D
0x1801a3e4e  mov     rax, [rcx]
0x1801a3e51  mov     edx, r12d
0x1801a3e54  mov     rax, [rax]
0x1801a3e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3e5c  nop
0x1801a3e5d  jmp     loc_1801A45F3
0x1801a3e62  mov     rax, [rdi]
0x1801a3e65  mov     rcx, rdi
0x1801a3e68  mov     rax, [rax+8]
0x1801a3e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3e71  mov     r14d, eax
0x1801a3e74  test    eax, eax
0x1801a3e76  jz      short loc_1801A3E96
0x1801a3e78  mov     rcx, [rsp+228h+var_1D8]
0x1801a3e7d  test    rcx, rcx
0x1801a3e80  jz      short loc_1801A3E91
0x1801a3e82  mov     rax, [rcx]
0x1801a3e85  mov     edx, r12d
0x1801a3e88  mov     rax, [rax]
0x1801a3e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3e90  nop
0x1801a3e91  jmp     loc_1801A45F3
0x1801a3e96  lea     r8, [rsp+228h+instance]; instance
0x1801a3e9e  lea     rdx, MDM_Policy_Result01_TextInput02_rtti; classDecl
0x1801a3ea5  mov     rcx, r15; context
0x1801a3ea8  call    MI_Context_ConstructInstance
0x1801a3ead  mov     r14d, eax
0x1801a3eb0  test    eax, eax
0x1801a3eb2  jz      short loc_1801A3ED2
0x1801a3eb4  mov     rcx, [rsp+228h+var_1D8]
0x1801a3eb9  test    rcx, rcx
0x1801a3ebc  jz      short loc_1801A3ECD
0x1801a3ebe  mov     rax, [rcx]
0x1801a3ec1  mov     edx, r12d
0x1801a3ec4  mov     rax, [rax]
0x1801a3ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3ecc  nop
0x1801a3ecd  jmp     loc_1801A45F3
0x1801a3ed2  mov     [rsp+228h+var_1E0], r12b
0x1801a3ed7  mov     rdx, [rsi+40h]
0x1801a3edb  lea     rcx, [rsp+228h+instance]
0x1801a3ee3  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801a3ee8  mov     rdx, [rsi+50h]
0x1801a3eec  lea     rcx, [rsp+228h+instance]
0x1801a3ef4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801a3ef9  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a3efe  lea     rdx, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1801a3f05  mov     rcx, rdi; this
0x1801a3f08  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a3f0d  test    eax, eax
0x1801a3f0f  jnz     short loc_1801A3F36
0x1801a3f11  mov     rcx, [rsp+228h+String]; String
0x1801a3f16  test    rcx, rcx
0x1801a3f19  jz      short loc_1801A3F36
0x1801a3f1b  call    cs:__imp__wtoi
0x1801a3f22  nop     dword ptr [rax+rax+00h]
0x1801a3f27  mov     [rsp+228h+var_118], eax
0x1801a3f2e  mov     [rsp+228h+var_114], r12b
0x1801a3f36  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a3f3b  lea     rdx, aAllowimeloggin; "AllowIMELogging"
0x1801a3f42  mov     rcx, rdi; this
0x1801a3f45  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a3f4a  test    eax, eax
0x1801a3f4c  jnz     short loc_1801A3F73
0x1801a3f4e  mov     rcx, [rsp+228h+String]; String
0x1801a3f53  test    rcx, rcx
0x1801a3f56  jz      short loc_1801A3F73
0x1801a3f58  call    cs:__imp__wtoi
0x1801a3f5f  nop     dword ptr [rax+rax+00h]
0x1801a3f64  mov     [rsp+228h+var_110], eax
0x1801a3f6b  mov     [rsp+228h+var_10C], r12b
0x1801a3f73  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a3f78  lea     rdx, aAllowimenetwor; "AllowIMENetworkAccess"
0x1801a3f7f  mov     rcx, rdi; this
0x1801a3f82  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a3f87  test    eax, eax
0x1801a3f89  jnz     short loc_1801A3FB0
0x1801a3f8b  mov     rcx, [rsp+228h+String]; String
0x1801a3f90  test    rcx, rcx
0x1801a3f93  jz      short loc_1801A3FB0
0x1801a3f95  call    cs:__imp__wtoi
0x1801a3f9c  nop     dword ptr [rax+rax+00h]
0x1801a3fa1  mov     [rsp+228h+var_108], eax
0x1801a3fa8  mov     [rsp+228h+var_104], r12b
0x1801a3fb0  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a3fb5  lea     rdx, aAllowinputpane; "AllowInputPanel"
0x1801a3fbc  mov     rcx, rdi; this
0x1801a3fbf  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a3fc4  test    eax, eax
0x1801a3fc6  jnz     short loc_1801A3FED
0x1801a3fc8  mov     rcx, [rsp+228h+String]; String
0x1801a3fcd  test    rcx, rcx
0x1801a3fd0  jz      short loc_1801A3FED
0x1801a3fd2  call    cs:__imp__wtoi
0x1801a3fd9  nop     dword ptr [rax+rax+00h]
0x1801a3fde  mov     [rsp+228h+var_100], eax
0x1801a3fe5  mov     [rsp+228h+var_FC], r12b
0x1801a3fed  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a3ff2  lea     rdx, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1801a3ff9  mov     rcx, rdi; this
0x1801a3ffc  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4001  test    eax, eax
0x1801a4003  jnz     short loc_1801A402A
0x1801a4005  mov     rcx, [rsp+228h+String]; String
0x1801a400a  test    rcx, rcx
0x1801a400d  jz      short loc_1801A402A
0x1801a400f  call    cs:__imp__wtoi
0x1801a4016  nop     dword ptr [rax+rax+00h]
0x1801a401b  mov     [rsp+228h+var_F8], eax
0x1801a4022  mov     [rsp+228h+var_F4], r12b
0x1801a402a  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a402f  lea     rdx, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1801a4036  mov     rcx, rdi; this
0x1801a4039  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a403e  test    eax, eax
0x1801a4040  jnz     short loc_1801A4067
0x1801a4042  mov     rcx, [rsp+228h+String]; String
0x1801a4047  test    rcx, rcx
0x1801a404a  jz      short loc_1801A4067
0x1801a404c  call    cs:__imp__wtoi
0x1801a4053  nop     dword ptr [rax+rax+00h]
0x1801a4058  mov     [rsp+228h+var_F0], eax
0x1801a405f  mov     [rsp+228h+var_EC], r12b
0x1801a4067  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a406c  lea     rdx, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1801a4073  mov     rcx, rdi; this
0x1801a4076  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a407b  test    eax, eax
0x1801a407d  jnz     short loc_1801A40A4
0x1801a407f  mov     rcx, [rsp+228h+String]; String
0x1801a4084  test    rcx, rcx
0x1801a4087  jz      short loc_1801A40A4
0x1801a4089  call    cs:__imp__wtoi
0x1801a4090  nop     dword ptr [rax+rax+00h]
0x1801a4095  mov     [rsp+228h+var_E8], eax
0x1801a409c  mov     [rsp+228h+var_E4], r12b
0x1801a40a4  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a40a9  lea     rdx, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1801a40b0  mov     rcx, rdi; this
0x1801a40b3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a40b8  test    eax, eax
0x1801a40ba  jnz     short loc_1801A40E1
0x1801a40bc  mov     rcx, [rsp+228h+String]; String
0x1801a40c1  test    rcx, rcx
0x1801a40c4  jz      short loc_1801A40E1
0x1801a40c6  call    cs:__imp__wtoi
0x1801a40cd  nop     dword ptr [rax+rax+00h]
0x1801a40d2  mov     [rsp+228h+var_E0], eax
0x1801a40d9  mov     [rsp+228h+var_DC], r12b
0x1801a40e1  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a40e6  lea     rdx, aAllowkeyboardt; "AllowKeyboardTextSuggestions"
0x1801a40ed  mov     rcx, rdi; this
0x1801a40f0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a40f5  test    eax, eax
0x1801a40f7  jnz     short loc_1801A411E
0x1801a40f9  mov     rcx, [rsp+228h+String]; String
0x1801a40fe  test    rcx, rcx
0x1801a4101  jz      short loc_1801A411E
0x1801a4103  call    cs:__imp__wtoi
0x1801a410a  nop     dword ptr [rax+rax+00h]
0x1801a410f  mov     [rsp+228h+var_D8], eax
0x1801a4116  mov     [rsp+228h+var_D4], r12b
0x1801a411e  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a4123  lea     rdx, aAllowlanguagef; "AllowLanguageFeaturesUninstall"
0x1801a412a  mov     rcx, rdi; this
0x1801a412d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4132  test    eax, eax
0x1801a4134  jnz     short loc_1801A415B
0x1801a4136  mov     rcx, [rsp+228h+String]; String
0x1801a413b  test    rcx, rcx
0x1801a413e  jz      short loc_1801A415B
0x1801a4140  call    cs:__imp__wtoi
0x1801a4147  nop     dword ptr [rax+rax+00h]
0x1801a414c  mov     [rsp+228h+var_D0], eax
0x1801a4153  mov     [rsp+228h+var_CC], r12b
0x1801a415b  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a4160  lea     rdx, aAllowlinguisti; "AllowLinguisticDataCollection"
0x1801a4167  mov     rcx, rdi; this
0x1801a416a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a416f  test    eax, eax
0x1801a4171  jnz     short loc_1801A4198
0x1801a4173  mov     rcx, [rsp+228h+String]; String
0x1801a4178  test    rcx, rcx
0x1801a417b  jz      short loc_1801A4198
0x1801a417d  call    cs:__imp__wtoi
0x1801a4184  nop     dword ptr [rax+rax+00h]
0x1801a4189  mov     [rsp+228h+var_C8], eax
0x1801a4190  mov     [rsp+228h+var_C4], r12b
0x1801a4198  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a419d  lea     rdx, aAllowtextinput; "AllowTextInputSuggestionUpdate"
0x1801a41a4  mov     rcx, rdi; this
0x1801a41a7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a41ac  test    eax, eax
0x1801a41ae  jnz     short loc_1801A41D5
0x1801a41b0  mov     rcx, [rsp+228h+String]; String
0x1801a41b5  test    rcx, rcx
0x1801a41b8  jz      short loc_1801A41D5
0x1801a41ba  call    cs:__imp__wtoi
  ... truncated ...
```
