# MDM_Policy_Result01_TextInput02_InvokeGetInstance

- ea: `0x1801a40d0`
- end: `0x1801a4a3a`
- name: `MDM_Policy_Result01_TextInput02_InvokeGetInstance`
- size: `2410`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1801a2880`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801a40d0`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801a436f`
- `msvcrt!_wtoi` at `0x1801a43a6`
- `msvcrt!_wtoi` at `0x1801a43dd`
- `msvcrt!_wtoi` at `0x1801a4414`
- `msvcrt!_wtoi` at `0x1801a444b`
- `msvcrt!_wtoi` at `0x1801a4482`
- `msvcrt!_wtoi` at `0x1801a44b9`
- `msvcrt!_wtoi` at `0x1801a44f0`
- `msvcrt!_wtoi` at `0x1801a4527`
- `msvcrt!_wtoi` at `0x1801a455e`
- `msvcrt!_wtoi` at `0x1801a4595`
- `msvcrt!_wtoi` at `0x1801a45cc`
- `msvcrt!_wtoi` at `0x1801a4603`
- `msvcrt!_wtoi` at `0x1801a463a`
- `msvcrt!_wtoi` at `0x1801a4671`
- `msvcrt!_wtoi` at `0x1801a46a8`
- `msvcrt!_wtoi` at `0x1801a46df`
- `msvcrt!_wtoi` at `0x1801a4716`
- `msvcrt!_wtoi` at `0x1801a474d`
- `msvcrt!_wtoi` at `0x1801a4784`
- `msvcrt!_wtoi` at `0x1801a47bb`
- `msvcrt!_wtoi` at `0x1801a47f2`
- `msvcrt!_wtoi` at `0x1801a4829`
- `msvcrt!_wtoi` at `0x1801a4860`
- `msvcrt!_wtoi` at `0x1801a4897`
- `msvcrt!_wtoi` at `0x1801a48ce`
- `msvcrt!_wtoi` at `0x1801a4905`
- `msvcrt!_wtoi` at `0x1801a493c`
- `msvcrt!_wtoi` at `0x1801a436f`
- `msvcrt!_wtoi` at `0x1801a43a6`
- `msvcrt!_wtoi` at `0x1801a43dd`
- `msvcrt!_wtoi` at `0x1801a4414`
- `msvcrt!_wtoi` at `0x1801a444b`
- `msvcrt!_wtoi` at `0x1801a4482`
- `msvcrt!_wtoi` at `0x1801a44b9`
- `msvcrt!_wtoi` at `0x1801a44f0`
- `msvcrt!_wtoi` at `0x1801a4527`
- `msvcrt!_wtoi` at `0x1801a455e`
- `msvcrt!_wtoi` at `0x1801a4595`
- `msvcrt!_wtoi` at `0x1801a45cc`
- `msvcrt!_wtoi` at `0x1801a4603`
- `msvcrt!_wtoi` at `0x1801a463a`
- `msvcrt!_wtoi` at `0x1801a4671`
- `msvcrt!_wtoi` at `0x1801a46a8`
- `msvcrt!_wtoi` at `0x1801a46df`
- `msvcrt!_wtoi` at `0x1801a4716`
- `msvcrt!_wtoi` at `0x1801a474d`
- `msvcrt!_wtoi` at `0x1801a4784`
- `msvcrt!_wtoi` at `0x1801a47bb`
- `msvcrt!_wtoi` at `0x1801a47f2`
- `msvcrt!_wtoi` at `0x1801a4829`
- `msvcrt!_wtoi` at `0x1801a4860`
- `msvcrt!_wtoi` at `0x1801a4897`
- `msvcrt!_wtoi` at `0x1801a48ce`
- `msvcrt!_wtoi` at `0x1801a4905`
- `msvcrt!_wtoi` at `0x1801a493c`

## string_xrefs

- `0x1801a43c0`: `AllowIMENetworkAccess`
- `0x1801a4541`: `AllowLanguageFeaturesUninstall`
- `0x1801a45af`: `AllowTextInputSuggestionUpdate`
- `0x1801a45e6`: `ConfigureJapaneseIMEVersion`
- `0x1801a461d`: `ConfigureKoreanIMEVersion`
- `0x1801a4654`: `ConfigureSimplifiedChineseIMEVersion`
- `0x1801a468b`: `ConfigureTraditionalChineseIMEVersion`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_TextInput02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Result01_TextInput02_NodeList,
           0x1Eu,
           0,
           &v10);
    if ( !v5 )
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
        v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
          }
        }
      }
      else
      {
        v5 = 1;
      }
    }
  }
  else
  {
    v5 = 4;
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
  return v5;
}

```

## disassembly

```asm
0x1801a40d0  mov     [rsp+arg_10], rbx
0x1801a40d5  push    rsi
0x1801a40d6  push    rdi
0x1801a40d7  push    r12
0x1801a40d9  push    r14
0x1801a40db  push    r15
0x1801a40dd  sub     rsp, 200h
0x1801a40e4  mov     rax, cs:__security_cookie
0x1801a40eb  xor     rax, rsp
0x1801a40ee  mov     [rsp+228h+var_38], rax
0x1801a40f6  mov     rsi, rdx
0x1801a40f9  mov     r15, rcx
0x1801a40fc  xor     ebx, ebx
0x1801a40fe  mov     [rsp+228h+String], rbx
0x1801a4103  xor     edx, edx; Val
0x1801a4105  mov     r8d, 140h; Size
0x1801a410b  lea     rcx, [rsp+228h+instance]; void *
0x1801a4113  call    memset_0
0x1801a4118  mov     [rsp+228h+var_1A0], ebx
0x1801a411f  mov     [rsp+228h+var_19C], bl
0x1801a4126  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801a412d  mov     [rsp+228h+var_1D0], rax
0x1801a4132  lea     rax, [rsp+228h+var_1A0]
0x1801a413a  mov     [rsp+228h+var_1C8], rax
0x1801a413f  lea     rax, aMdmPolicyResul_132; "MDM_Policy_Result01_TextInput02"
0x1801a4146  mov     [rsp+228h+var_1C0], rax
0x1801a414b  lea     rcx, [rsp+228h+var_1A0]
0x1801a4153  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801a4158  mov     eax, cs:dword_180380B68
0x1801a415e  cmp     eax, 5
0x1801a4161  jbe     short loc_1801A41D2
0x1801a4163  mov     rdx, 200000000000h
0x1801a416d  lea     rcx, dword_180380B68
0x1801a4174  call    _tlgKeywordOn
0x1801a4179  test    al, al
0x1801a417b  jz      short loc_1801A41D2
0x1801a417d  cmp     [rsp+228h+var_19C], bl
0x1801a4184  jz      short loc_1801A41B4
0x1801a4186  cmp     [rsp+228h+var_188], ebx
0x1801a418d  jnz     short loc_1801A41AA
0x1801a418f  cmp     [rsp+228h+var_184], ebx
0x1801a4196  jnz     short loc_1801A41AA
0x1801a4198  cmp     [rsp+228h+var_180], ebx
0x1801a419f  jnz     short loc_1801A41AA
0x1801a41a1  cmp     [rsp+228h+var_17C], ebx
0x1801a41a8  jz      short loc_1801A41B4
0x1801a41aa  lea     r9, [rsp+228h+var_188]
0x1801a41b2  jmp     short loc_1801A41B7
0x1801a41b4  mov     r9, rbx
0x1801a41b7  lea     r8, [rsp+228h+var_198]
0x1801a41bf  lea     rdx, byte_18034995B
0x1801a41c6  lea     rcx, dword_180380B68
0x1801a41cd  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801a41d2  cmp     [rsi+48h], bl
0x1801a41d5  jz      loc_1801A4999
0x1801a41db  mov     [rsp+228h+var_1E0], bl
0x1801a41df  cmp     [rsi+58h], bl
0x1801a41e2  jz      loc_1801A4999
0x1801a41e8  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801a41ec  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801a41f0  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801a41f7  lea     rcx, [rsp+228h+var_1D0]; this
0x1801a41fc  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801a4201  nop
0x1801a4202  mov     [rsp+228h+var_1D8], rbx
0x1801a4207  lea     rax, [rsp+228h+var_1D8]
0x1801a420c  mov     [rsp+228h+var_1F8], rax
0x1801a4211  mov     [rsp+228h+var_200], ebx
0x1801a4215  mov     [rsp+228h+var_208], 1Eh
0x1801a421d  lea     r9, ?MDM_Policy_Result01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_TextInput02_NodeList
0x1801a4224  mov     r8, [rsi+40h]
0x1801a4228  mov     rdx, [rsi+50h]
0x1801a422c  mov     rcx, r15
0x1801a422f  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801a4234  mov     r14d, eax
0x1801a4237  test    eax, eax
0x1801a4239  jz      short loc_1801A4240
0x1801a423b  jmp     loc_1801A499F
0x1801a4240  lea     rax, [rsp+228h+var_1D8]
0x1801a4245  mov     [rsp+228h+var_1B0], rax
0x1801a424a  mov     r12d, 1
0x1801a4250  mov     [rsp+228h+var_1A8], r12b
0x1801a4258  mov     rdi, [rsp+228h+var_1D8]
0x1801a425d  test    rdi, rdi
0x1801a4260  jnz     short loc_1801A426A
0x1801a4262  mov     r14d, r12d
0x1801a4265  jmp     loc_1801A499F
0x1801a426a  mov     r9d, 1Eh; unsigned int
0x1801a4270  lea     r8, ?MDM_Policy_Result01_TextInput02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801a4277  mov     rdx, rsi; struct _MI_Instance *
0x1801a427a  mov     rcx, rdi; this
0x1801a427d  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801a4282  mov     rax, [rdi]
0x1801a4285  mov     rcx, rdi
0x1801a4288  mov     rax, [rax+10h]
0x1801a428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4291  mov     r14d, eax
0x1801a4294  test    eax, eax
0x1801a4296  jz      short loc_1801A42B6
0x1801a4298  mov     rcx, [rsp+228h+var_1D8]
0x1801a429d  test    rcx, rcx
0x1801a42a0  jz      short loc_1801A42B1
0x1801a42a2  mov     rax, [rcx]
0x1801a42a5  mov     edx, r12d
0x1801a42a8  mov     rax, [rax]
0x1801a42ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a42b0  nop
0x1801a42b1  jmp     loc_1801A499F
0x1801a42b6  mov     rax, [rdi]
0x1801a42b9  mov     rcx, rdi
0x1801a42bc  mov     rax, [rax+8]
0x1801a42c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a42c5  mov     r14d, eax
0x1801a42c8  test    eax, eax
0x1801a42ca  jz      short loc_1801A42EA
0x1801a42cc  mov     rcx, [rsp+228h+var_1D8]
0x1801a42d1  test    rcx, rcx
0x1801a42d4  jz      short loc_1801A42E5
0x1801a42d6  mov     rax, [rcx]
0x1801a42d9  mov     edx, r12d
0x1801a42dc  mov     rax, [rax]
0x1801a42df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a42e4  nop
0x1801a42e5  jmp     loc_1801A499F
0x1801a42ea  lea     r8, [rsp+228h+instance]; instance
0x1801a42f2  lea     rdx, MDM_Policy_Result01_TextInput02_rtti; classDecl
0x1801a42f9  mov     rcx, r15; context
0x1801a42fc  call    MI_Context_ConstructInstance
0x1801a4301  mov     r14d, eax
0x1801a4304  test    eax, eax
0x1801a4306  jz      short loc_1801A4326
0x1801a4308  mov     rcx, [rsp+228h+var_1D8]
0x1801a430d  test    rcx, rcx
0x1801a4310  jz      short loc_1801A4321
0x1801a4312  mov     rax, [rcx]
0x1801a4315  mov     edx, r12d
0x1801a4318  mov     rax, [rax]
0x1801a431b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4320  nop
0x1801a4321  jmp     loc_1801A499F
0x1801a4326  mov     [rsp+228h+var_1E0], r12b
0x1801a432b  mov     rdx, [rsi+40h]
0x1801a432f  lea     rcx, [rsp+228h+instance]
0x1801a4337  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801a433c  mov     rdx, [rsi+50h]
0x1801a4340  lea     rcx, [rsp+228h+instance]
0x1801a4348  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801a434d  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a4352  lea     rdx, aAllowhardwarek; "AllowHardwareKeyboardTextSuggestions"
0x1801a4359  mov     rcx, rdi; this
0x1801a435c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4361  test    eax, eax
0x1801a4363  jnz     short loc_1801A4384
0x1801a4365  mov     rcx, [rsp+228h+String]; String
0x1801a436a  test    rcx, rcx
0x1801a436d  jz      short loc_1801A4384
0x1801a436f  call    cs:__imp__wtoi
0x1801a4375  mov     [rsp+228h+var_118], eax
0x1801a437c  mov     [rsp+228h+var_114], r12b
0x1801a4384  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a4389  lea     rdx, aAllowimeloggin; "AllowIMELogging"
0x1801a4390  mov     rcx, rdi; this
0x1801a4393  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4398  test    eax, eax
0x1801a439a  jnz     short loc_1801A43BB
0x1801a439c  mov     rcx, [rsp+228h+String]; String
0x1801a43a1  test    rcx, rcx
0x1801a43a4  jz      short loc_1801A43BB
0x1801a43a6  call    cs:__imp__wtoi
0x1801a43ac  mov     [rsp+228h+var_110], eax
0x1801a43b3  mov     [rsp+228h+var_10C], r12b
0x1801a43bb  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a43c0  lea     rdx, aAllowimenetwor; "AllowIMENetworkAccess"
0x1801a43c7  mov     rcx, rdi; this
0x1801a43ca  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a43cf  test    eax, eax
0x1801a43d1  jnz     short loc_1801A43F2
0x1801a43d3  mov     rcx, [rsp+228h+String]; String
0x1801a43d8  test    rcx, rcx
0x1801a43db  jz      short loc_1801A43F2
0x1801a43dd  call    cs:__imp__wtoi
0x1801a43e3  mov     [rsp+228h+var_108], eax
0x1801a43ea  mov     [rsp+228h+var_104], r12b
0x1801a43f2  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a43f7  lea     rdx, aAllowinputpane; "AllowInputPanel"
0x1801a43fe  mov     rcx, rdi; this
0x1801a4401  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4406  test    eax, eax
0x1801a4408  jnz     short loc_1801A4429
0x1801a440a  mov     rcx, [rsp+228h+String]; String
0x1801a440f  test    rcx, rcx
0x1801a4412  jz      short loc_1801A4429
0x1801a4414  call    cs:__imp__wtoi
0x1801a441a  mov     [rsp+228h+var_100], eax
0x1801a4421  mov     [rsp+228h+var_FC], r12b
0x1801a4429  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a442e  lea     rdx, aAllowjapanesei_0; "AllowJapaneseIMESurrogatePairCharacters"
0x1801a4435  mov     rcx, rdi; this
0x1801a4438  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a443d  test    eax, eax
0x1801a443f  jnz     short loc_1801A4460
0x1801a4441  mov     rcx, [rsp+228h+String]; String
0x1801a4446  test    rcx, rcx
0x1801a4449  jz      short loc_1801A4460
0x1801a444b  call    cs:__imp__wtoi
0x1801a4451  mov     [rsp+228h+var_F8], eax
0x1801a4458  mov     [rsp+228h+var_F4], r12b
0x1801a4460  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a4465  lea     rdx, aAllowjapanesei; "AllowJapaneseIVSCharacters"
0x1801a446c  mov     rcx, rdi; this
0x1801a446f  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4474  test    eax, eax
0x1801a4476  jnz     short loc_1801A4497
0x1801a4478  mov     rcx, [rsp+228h+String]; String
0x1801a447d  test    rcx, rcx
0x1801a4480  jz      short loc_1801A4497
0x1801a4482  call    cs:__imp__wtoi
0x1801a4488  mov     [rsp+228h+var_F0], eax
0x1801a448f  mov     [rsp+228h+var_EC], r12b
0x1801a4497  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a449c  lea     rdx, aAllowjapanesen; "AllowJapaneseNonPublishingStandardGlyph"
0x1801a44a3  mov     rcx, rdi; this
0x1801a44a6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a44ab  test    eax, eax
0x1801a44ad  jnz     short loc_1801A44CE
0x1801a44af  mov     rcx, [rsp+228h+String]; String
0x1801a44b4  test    rcx, rcx
0x1801a44b7  jz      short loc_1801A44CE
0x1801a44b9  call    cs:__imp__wtoi
0x1801a44bf  mov     [rsp+228h+var_E8], eax
0x1801a44c6  mov     [rsp+228h+var_E4], r12b
0x1801a44ce  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a44d3  lea     rdx, aAllowjapaneseu; "AllowJapaneseUserDictionary"
0x1801a44da  mov     rcx, rdi; this
0x1801a44dd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a44e2  test    eax, eax
0x1801a44e4  jnz     short loc_1801A4505
0x1801a44e6  mov     rcx, [rsp+228h+String]; String
0x1801a44eb  test    rcx, rcx
0x1801a44ee  jz      short loc_1801A4505
0x1801a44f0  call    cs:__imp__wtoi
0x1801a44f6  mov     [rsp+228h+var_E0], eax
0x1801a44fd  mov     [rsp+228h+var_DC], r12b
0x1801a4505  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a450a  lea     rdx, aAllowkeyboardt; "AllowKeyboardTextSuggestions"
0x1801a4511  mov     rcx, rdi; this
0x1801a4514  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4519  test    eax, eax
0x1801a451b  jnz     short loc_1801A453C
0x1801a451d  mov     rcx, [rsp+228h+String]; String
0x1801a4522  test    rcx, rcx
0x1801a4525  jz      short loc_1801A453C
0x1801a4527  call    cs:__imp__wtoi
0x1801a452d  mov     [rsp+228h+var_D8], eax
0x1801a4534  mov     [rsp+228h+var_D4], r12b
0x1801a453c  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a4541  lea     rdx, aAllowlanguagef; "AllowLanguageFeaturesUninstall"
0x1801a4548  mov     rcx, rdi; this
0x1801a454b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4550  test    eax, eax
0x1801a4552  jnz     short loc_1801A4573
0x1801a4554  mov     rcx, [rsp+228h+String]; String
0x1801a4559  test    rcx, rcx
0x1801a455c  jz      short loc_1801A4573
0x1801a455e  call    cs:__imp__wtoi
0x1801a4564  mov     [rsp+228h+var_D0], eax
0x1801a456b  mov     [rsp+228h+var_CC], r12b
0x1801a4573  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a4578  lea     rdx, aAllowlinguisti; "AllowLinguisticDataCollection"
0x1801a457f  mov     rcx, rdi; this
0x1801a4582  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a4587  test    eax, eax
0x1801a4589  jnz     short loc_1801A45AA
0x1801a458b  mov     rcx, [rsp+228h+String]; String
0x1801a4590  test    rcx, rcx
0x1801a4593  jz      short loc_1801A45AA
0x1801a4595  call    cs:__imp__wtoi
0x1801a459b  mov     [rsp+228h+var_C8], eax
0x1801a45a2  mov     [rsp+228h+var_C4], r12b
0x1801a45aa  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a45af  lea     rdx, aAllowtextinput; "AllowTextInputSuggestionUpdate"
0x1801a45b6  mov     rcx, rdi; this
0x1801a45b9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a45be  test    eax, eax
0x1801a45c0  jnz     short loc_1801A45E1
0x1801a45c2  mov     rcx, [rsp+228h+String]; String
0x1801a45c7  test    rcx, rcx
0x1801a45ca  jz      short loc_1801A45E1
0x1801a45cc  call    cs:__imp__wtoi
0x1801a45d2  mov     [rsp+228h+var_C0], eax
0x1801a45d9  mov     [rsp+228h+var_BC], r12b
0x1801a45e1  lea     r8, [rsp+228h+String]; unsigned __int16 **
0x1801a45e6  lea     rdx, aConfigurejapan; "ConfigureJapaneseIMEVersion"
0x1801a45ed  mov     rcx, rdi; this
0x1801a45f0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801a45f5  test    eax, eax
0x1801a45f7  jnz     short loc_1801A4618
0x1801a45f9  mov     rcx, [rsp+228h+String]; String
0x1801a45fe  test    rcx, rcx
0x1801a4601  jz      short loc_1801A4618
  ... truncated ...
```
