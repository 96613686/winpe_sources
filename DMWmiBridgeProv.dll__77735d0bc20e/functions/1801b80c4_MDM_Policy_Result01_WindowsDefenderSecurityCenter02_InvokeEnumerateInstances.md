# MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances

- ea: `0x1801b80c4`
- end: `0x1801b8a22`
- name: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances`
- size: `2398`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801b74c0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f54`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000522c`
- `0x180005344`
- `0x18000537c`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801b80c4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801b840f`
- `msvcrt!_wtoi` at `0x1801b8450`
- `msvcrt!_wtoi` at `0x1801b8491`
- `msvcrt!_wtoi` at `0x1801b84d2`
- `msvcrt!_wtoi` at `0x1801b8513`
- `msvcrt!_wtoi` at `0x1801b8554`
- `msvcrt!_wtoi` at `0x1801b8595`
- `msvcrt!_wtoi` at `0x1801b85d6`
- `msvcrt!_wtoi` at `0x1801b8617`
- `msvcrt!_wtoi` at `0x1801b8658`
- `msvcrt!_wtoi` at `0x1801b8699`
- `msvcrt!_wtoi` at `0x1801b86da`
- `msvcrt!_wtoi` at `0x1801b8754`
- `msvcrt!_wtoi` at `0x1801b8795`
- `msvcrt!_wtoi` at `0x1801b87d6`
- `msvcrt!_wtoi` at `0x1801b8817`
- `msvcrt!_wtoi` at `0x1801b8858`
- `msvcrt!_wtoi` at `0x1801b8899`
- `msvcrt!_wtoi` at `0x1801b840f`
- `msvcrt!_wtoi` at `0x1801b8450`
- `msvcrt!_wtoi` at `0x1801b8491`
- `msvcrt!_wtoi` at `0x1801b84d2`
- `msvcrt!_wtoi` at `0x1801b8513`
- `msvcrt!_wtoi` at `0x1801b8554`
- `msvcrt!_wtoi` at `0x1801b8595`
- `msvcrt!_wtoi` at `0x1801b85d6`
- `msvcrt!_wtoi` at `0x1801b8617`
- `msvcrt!_wtoi` at `0x1801b8658`
- `msvcrt!_wtoi` at `0x1801b8699`
- `msvcrt!_wtoi` at `0x1801b86da`
- `msvcrt!_wtoi` at `0x1801b8754`
- `msvcrt!_wtoi` at `0x1801b8795`
- `msvcrt!_wtoi` at `0x1801b87d6`
- `msvcrt!_wtoi` at `0x1801b8817`
- `msvcrt!_wtoi` at `0x1801b8858`
- `msvcrt!_wtoi` at `0x1801b8899`

## string_xrefs

- `0x1801b83b2`: `CompanyName`
- `0x1801b84ae`: `DisableDeviceSecurityUI`
- `0x1801b8634`: `DisableTpmFirmwareUpdateWarning`
- `0x1801b8875`: `HideWindowsSecurityNotificationAreaControl`
- `0x1801b813f`: `MDM_Policy_Result01_WindowsDefenderSecurityCenter02`
- `0x1801b8351`: `WindowsDefenderSecurityCenter`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_WindowsDefenderSecurityCenter02_InvokeEnumerateInstances(
        MI_Context *self,
        char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r15d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r14d
  wchar_t *String; // [rsp+40h] [rbp-1D8h] BYREF
  char v11; // [rsp+48h] [rbp-1D0h]
  WmiRequestHandlerAdd *v12; // [rsp+50h] [rbp-1C8h] BYREF
  _QWORD v13[5]; // [rsp+58h] [rbp-1C0h] BYREF
  char v14; // [rsp+80h] [rbp-198h]
  int v15; // [rsp+88h] [rbp-190h] BYREF
  char v16; // [rsp+8Ch] [rbp-18Ch]
  _BYTE v17[16]; // [rsp+90h] [rbp-188h] BYREF
  _DWORD v18[4]; // [rsp+A0h] [rbp-178h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-168h] BYREF
  int v20; // [rsp+120h] [rbp-F8h]
  char v21; // [rsp+124h] [rbp-F4h]
  int v22; // [rsp+128h] [rbp-F0h]
  char v23; // [rsp+12Ch] [rbp-ECh]
  int v24; // [rsp+130h] [rbp-E8h]
  char v25; // [rsp+134h] [rbp-E4h]
  int v26; // [rsp+138h] [rbp-E0h]
  char v27; // [rsp+13Ch] [rbp-DCh]
  int v28; // [rsp+140h] [rbp-D8h]
  char v29; // [rsp+144h] [rbp-D4h]
  int v30; // [rsp+148h] [rbp-D0h]
  char v31; // [rsp+14Ch] [rbp-CCh]
  int v32; // [rsp+150h] [rbp-C8h]
  char v33; // [rsp+154h] [rbp-C4h]
  int v34; // [rsp+158h] [rbp-C0h]
  char v35; // [rsp+15Ch] [rbp-BCh]
  int v36; // [rsp+160h] [rbp-B8h]
  char v37; // [rsp+164h] [rbp-B4h]
  int v38; // [rsp+168h] [rbp-B0h]
  char v39; // [rsp+16Ch] [rbp-ACh]
  int v40; // [rsp+170h] [rbp-A8h]
  char v41; // [rsp+174h] [rbp-A4h]
  int v42; // [rsp+178h] [rbp-A0h]
  char v43; // [rsp+17Ch] [rbp-9Ch]
  int v44; // [rsp+190h] [rbp-88h]
  char v45; // [rsp+194h] [rbp-84h]
  int v46; // [rsp+198h] [rbp-80h]
  char v47; // [rsp+19Ch] [rbp-7Ch]
  int v48; // [rsp+1A0h] [rbp-78h]
  char v49; // [rsp+1A4h] [rbp-74h]
  int v50; // [rsp+1A8h] [rbp-70h]
  char v51; // [rsp+1ACh] [rbp-6Ch]
  int v52; // [rsp+1B0h] [rbp-68h]
  char v53; // [rsp+1B4h] [rbp-64h]
  int v54; // [rsp+1B8h] [rbp-60h]
  char v55; // [rsp+1BCh] [rbp-5Ch]

  memset_0(&instance, 0, 0x130u);
  v11 = 0;
  String = 0;
  v15 = 0;
  v16 = 0;
  v13[0] = &TelemetryEventWriter::`vftable';
  v13[1] = &v15;
  v13[2] = "MDM_Policy_Result01_WindowsDefenderSecurityCenter02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v5 = v18;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_1803558D8,
      v17,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v13, v4);
  v12 = 0;
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList,
         0x18u,
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
            v6 = MI_Context_ConstructInstance(
                   self,
                   &MDM_Policy_Result01_WindowsDefenderSecurityCenter02_rtti,
                   &instance);
            if ( v6 )
            {
              if ( v12 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v12)(v12, 1);
                v12 = 0;
              }
              goto LABEL_104;
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
                    L"WindowsDefenderSecurityCenter",
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
                      L"CompanyName",
                      &String)
                && String )
              {
                MDM_VPNv2_User_01_Set_EdpModeId(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableAccountProtectionUI",
                      &String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableAppBrowserUI",
                      &String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableClearTpmButton",
                      &String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableDeviceSecurityUI",
                      &String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableEnhancedNotifications",
                      &String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableFamilyUI",
                      &String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableHealthUI",
                      &String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableNetworkUI",
                      &String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableNotifications",
                      &String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableTpmFirmwareUpdateWarning",
                      &String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableVirusUI",
                      &String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisallowExploitProtectionOverride",
                      &String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"Email",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableCustomizedToasts",
                      &String)
                && String )
              {
                v44 = _wtoi(String);
                v45 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnableInAppCustomization",
                      &String)
                && String )
              {
                v46 = _wtoi(String);
                v47 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"HideRansomwareDataRecovery",
                      &String)
                && String )
              {
                v48 = _wtoi(String);
                v49 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"HideSecureBoot",
                      &String)
                && String )
              {
                v50 = _wtoi(String);
                v51 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"HideTPMTroubleshooting",
                      &String)
                && String )
              {
                v52 = _wtoi(String);
                v53 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"HideWindowsSecurityNotificationAreaControl",
                      &String)
                && String )
              {
                v54 = _wtoi(String);
                v55 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"Phone",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSaveTargetAsInIEMode(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"URL",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowSiteToZoneAssignmentList(&instance);
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
LABEL_104:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v13, "EnumerateInstancesEnd", v6);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033584B,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return v6;
}

```

## disassembly

```asm
0x1801b80c4  mov     [rsp+arg_8], rbx
0x1801b80c9  mov     [rsp+arg_10], rsi
0x1801b80ce  push    rdi
0x1801b80cf  push    r12
0x1801b80d1  push    r13
0x1801b80d3  push    r14
0x1801b80d5  push    r15
0x1801b80d7  sub     rsp, 1F0h
0x1801b80de  mov     rax, cs:__security_cookie
0x1801b80e5  xor     rax, rsp
0x1801b80e8  mov     [rsp+218h+var_38], rax
0x1801b80f0  mov     r13b, dl
0x1801b80f3  mov     r12, rcx
0x1801b80f6  xor     edx, edx; Val
0x1801b80f8  mov     r8d, 130h; Size
0x1801b80fe  lea     rcx, [rsp+218h+instance]; void *
0x1801b8106  call    memset_0
0x1801b810b  xor     edi, edi
0x1801b810d  mov     [rsp+218h+var_1D0], dil
0x1801b8112  mov     [rsp+218h+String], rdi
0x1801b8117  mov     [rsp+218h+var_190], edi
0x1801b811e  mov     [rsp+218h+var_18C], dil
0x1801b8126  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801b812d  mov     [rsp+218h+var_1C0], rax
0x1801b8132  lea     rax, [rsp+218h+var_190]
0x1801b813a  mov     [rsp+218h+var_1B8], rax
0x1801b813f  lea     rax, aMdmPolicyResul_186; "MDM_Policy_Result01_WindowsDefenderSecu"...
0x1801b8146  mov     [rsp+218h+var_1B0], rax
0x1801b814b  lea     rcx, [rsp+218h+var_190]
0x1801b8153  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801b8158  mov     eax, cs:dword_180380B68
0x1801b815e  cmp     eax, 5
0x1801b8161  jbe     short loc_1801B81D3
0x1801b8163  mov     rdx, 200000000000h
0x1801b816d  lea     rcx, dword_180380B68
0x1801b8174  call    _tlgKeywordOn
0x1801b8179  test    al, al
0x1801b817b  jz      short loc_1801B81D3
0x1801b817d  cmp     [rsp+218h+var_18C], dil
0x1801b8185  jz      short loc_1801B81B5
0x1801b8187  cmp     [rsp+218h+var_178], edi
0x1801b818e  jnz     short loc_1801B81AB
0x1801b8190  cmp     [rsp+218h+var_174], edi
0x1801b8197  jnz     short loc_1801B81AB
0x1801b8199  cmp     [rsp+218h+var_170], edi
0x1801b81a0  jnz     short loc_1801B81AB
0x1801b81a2  cmp     [rsp+218h+var_16C], edi
0x1801b81a9  jz      short loc_1801B81B5
0x1801b81ab  lea     r9, [rsp+218h+var_178]
0x1801b81b3  jmp     short loc_1801B81B8
0x1801b81b5  mov     r9, rdi
0x1801b81b8  lea     r8, [rsp+218h+var_188]
0x1801b81c0  lea     rdx, qword_1803558D8
0x1801b81c7  lea     rcx, dword_180380B68
0x1801b81ce  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801b81d3  lea     rcx, [rsp+218h+var_1C0]; this
0x1801b81d8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801b81dd  nop
0x1801b81de  mov     [rsp+218h+var_1C8], rdi
0x1801b81e3  lea     rax, [rsp+218h+var_1C8]
0x1801b81e8  mov     [rsp+218h+var_1E8], rax
0x1801b81ed  mov     [rsp+218h+var_1F0], 2
0x1801b81f5  mov     [rsp+218h+var_1F8], 18h
0x1801b81fd  lea     r9, ?MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_WindowsDefenderSecurityCenter02_NodeList
0x1801b8204  xor     r8d, r8d
0x1801b8207  xor     edx, edx
0x1801b8209  mov     rcx, r12
0x1801b820c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801b8211  mov     r15d, eax
0x1801b8214  test    eax, eax
0x1801b8216  jz      short loc_1801B821D
0x1801b8218  jmp     loc_1801B8982
0x1801b821d  lea     rbx, [rsp+218h+var_1C8]
0x1801b8222  mov     [rsp+218h+var_1A0], rbx
0x1801b8227  mov     r14d, 1
0x1801b822d  mov     [rsp+218h+var_198], r14b
0x1801b8235  mov     rsi, [rsp+218h+var_1C8]
0x1801b823a  test    rsi, rsi
0x1801b823d  jnz     short loc_1801B8247
0x1801b823f  mov     r15d, r14d
0x1801b8242  jmp     loc_1801B8982
0x1801b8247  mov     rax, [rsi]
0x1801b824a  mov     rcx, rsi
0x1801b824d  mov     rax, [rax+10h]
0x1801b8251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8256  mov     r15d, eax
0x1801b8259  test    eax, eax
0x1801b825b  jz      short loc_1801B827B
0x1801b825d  mov     rcx, [rsp+218h+var_1C8]
0x1801b8262  test    rcx, rcx
0x1801b8265  jz      short loc_1801B8276
0x1801b8267  mov     rax, [rcx]
0x1801b826a  mov     edx, r14d
0x1801b826d  mov     rax, [rax]
0x1801b8270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8275  nop
0x1801b8276  jmp     loc_1801B8982
0x1801b827b  mov     rax, [rsi]
0x1801b827e  mov     rcx, rsi
0x1801b8281  mov     rax, [rax+8]
0x1801b8285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b828a  mov     r15d, eax
0x1801b828d  test    eax, eax
0x1801b828f  jz      short loc_1801B82AF
0x1801b8291  mov     rcx, [rsp+218h+var_1C8]
0x1801b8296  test    rcx, rcx
0x1801b8299  jz      short loc_1801B82AA
0x1801b829b  mov     rax, [rcx]
0x1801b829e  mov     edx, r14d
0x1801b82a1  mov     rax, [rax]
0x1801b82a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b82a9  nop
0x1801b82aa  jmp     loc_1801B8982
0x1801b82af  mov     r14d, edi
0x1801b82b2  mov     rax, [rsi+108h]
0x1801b82b9  sub     rax, [rsi+100h]
0x1801b82c0  sar     rax, 4
0x1801b82c4  cmp     r14d, eax
0x1801b82c7  jnb     loc_1801B894A
0x1801b82cd  lea     r8, [rsp+218h+instance]; instance
0x1801b82d5  lea     rdx, MDM_Policy_Result01_WindowsDefenderSecurityCenter02_rtti; classDecl
0x1801b82dc  mov     rcx, r12; context
0x1801b82df  call    MI_Context_ConstructInstance
0x1801b82e4  mov     r15d, eax
0x1801b82e7  test    eax, eax
0x1801b82e9  jz      short loc_1801B830B
0x1801b82eb  mov     rcx, [rbx]
0x1801b82ee  test    rcx, rcx
0x1801b82f1  jz      short loc_1801B8306
0x1801b82f3  mov     rax, [rcx]
0x1801b82f6  mov     edx, 1
0x1801b82fb  mov     rax, [rax]
0x1801b82fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8303  mov     [rbx], rdi
0x1801b8306  jmp     loc_1801B8982
0x1801b830b  mov     [rsp+218h+var_1D0], 1
0x1801b8310  mov     rax, [rsi]
0x1801b8313  lea     r9, [rsp+218h+String]
0x1801b8318  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x1801b831f  mov     edx, r14d
0x1801b8322  mov     rcx, rsi
0x1801b8325  mov     rax, [rax+18h]
0x1801b8329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b832e  test    eax, eax
0x1801b8330  jnz     short loc_1801B8349
0x1801b8332  mov     rdx, [rsp+218h+String]
0x1801b8337  test    rdx, rdx
0x1801b833a  jz      short loc_1801B8349
0x1801b833c  lea     rcx, [rsp+218h+instance]
0x1801b8344  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801b8349  mov     rax, [rsi]
0x1801b834c  lea     r9, [rsp+218h+String]
0x1801b8351  lea     r8, aWindowsdefende; "WindowsDefenderSecurityCenter"
0x1801b8358  mov     edx, r14d
0x1801b835b  mov     rcx, rsi
0x1801b835e  mov     rax, [rax+18h]
0x1801b8362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8367  test    eax, eax
0x1801b8369  jnz     short loc_1801B8382
0x1801b836b  mov     rdx, [rsp+218h+String]
0x1801b8370  test    rdx, rdx
0x1801b8373  jz      short loc_1801B8382
0x1801b8375  lea     rcx, [rsp+218h+instance]
0x1801b837d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801b8382  cmp     r13b, 1
0x1801b8386  jnz     short loc_1801B83AA
0x1801b8388  lea     rdx, [rsp+218h+instance]
0x1801b8390  mov     rcx, r12; self
0x1801b8393  call    MI_Instance_Destruct
0x1801b8398  lea     rcx, [rsp+218h+instance]; self
0x1801b83a0  call    MI_Instance_Destruct
0x1801b83a5  jmp     loc_1801B893D
0x1801b83aa  mov     rax, [rsi]
0x1801b83ad  lea     r9, [rsp+218h+String]
0x1801b83b2  lea     r8, aCompanyname; "CompanyName"
0x1801b83b9  mov     edx, r14d
0x1801b83bc  mov     rcx, rsi
0x1801b83bf  mov     rax, [rax+18h]
0x1801b83c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b83c8  test    eax, eax
0x1801b83ca  jnz     short loc_1801B83E3
0x1801b83cc  mov     rdx, [rsp+218h+String]
0x1801b83d1  test    rdx, rdx
0x1801b83d4  jz      short loc_1801B83E3
0x1801b83d6  lea     rcx, [rsp+218h+instance]
0x1801b83de  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801b83e3  mov     rax, [rsi]
0x1801b83e6  lea     r9, [rsp+218h+String]
0x1801b83eb  lea     r8, aDisableaccount; "DisableAccountProtectionUI"
0x1801b83f2  mov     edx, r14d
0x1801b83f5  mov     rcx, rsi
0x1801b83f8  mov     rax, [rax+18h]
0x1801b83fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8401  test    eax, eax
0x1801b8403  jnz     short loc_1801B8424
0x1801b8405  mov     rcx, [rsp+218h+String]; String
0x1801b840a  test    rcx, rcx
0x1801b840d  jz      short loc_1801B8424
0x1801b840f  call    cs:__imp__wtoi
0x1801b8415  mov     [rsp+218h+var_F8], eax
0x1801b841c  mov     [rsp+218h+var_F4], 1
0x1801b8424  mov     rax, [rsi]
0x1801b8427  lea     r9, [rsp+218h+String]
0x1801b842c  lea     r8, aDisableappbrow; "DisableAppBrowserUI"
0x1801b8433  mov     edx, r14d
0x1801b8436  mov     rcx, rsi
0x1801b8439  mov     rax, [rax+18h]
0x1801b843d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8442  test    eax, eax
0x1801b8444  jnz     short loc_1801B8465
0x1801b8446  mov     rcx, [rsp+218h+String]; String
0x1801b844b  test    rcx, rcx
0x1801b844e  jz      short loc_1801B8465
0x1801b8450  call    cs:__imp__wtoi
0x1801b8456  mov     [rsp+218h+var_F0], eax
0x1801b845d  mov     [rsp+218h+var_EC], 1
0x1801b8465  mov     rax, [rsi]
0x1801b8468  lea     r9, [rsp+218h+String]
0x1801b846d  lea     r8, aDisablecleartp; "DisableClearTpmButton"
0x1801b8474  mov     edx, r14d
0x1801b8477  mov     rcx, rsi
0x1801b847a  mov     rax, [rax+18h]
0x1801b847e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8483  test    eax, eax
0x1801b8485  jnz     short loc_1801B84A6
0x1801b8487  mov     rcx, [rsp+218h+String]; String
0x1801b848c  test    rcx, rcx
0x1801b848f  jz      short loc_1801B84A6
0x1801b8491  call    cs:__imp__wtoi
0x1801b8497  mov     [rsp+218h+var_E8], eax
0x1801b849e  mov     [rsp+218h+var_E4], 1
0x1801b84a6  mov     rax, [rsi]
0x1801b84a9  lea     r9, [rsp+218h+String]
0x1801b84ae  lea     r8, aDisabledevices; "DisableDeviceSecurityUI"
0x1801b84b5  mov     edx, r14d
0x1801b84b8  mov     rcx, rsi
0x1801b84bb  mov     rax, [rax+18h]
0x1801b84bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b84c4  test    eax, eax
0x1801b84c6  jnz     short loc_1801B84E7
0x1801b84c8  mov     rcx, [rsp+218h+String]; String
0x1801b84cd  test    rcx, rcx
0x1801b84d0  jz      short loc_1801B84E7
0x1801b84d2  call    cs:__imp__wtoi
0x1801b84d8  mov     [rsp+218h+var_E0], eax
0x1801b84df  mov     [rsp+218h+var_DC], 1
0x1801b84e7  mov     rax, [rsi]
0x1801b84ea  lea     r9, [rsp+218h+String]
0x1801b84ef  lea     r8, aDisableenhance; "DisableEnhancedNotifications"
0x1801b84f6  mov     edx, r14d
0x1801b84f9  mov     rcx, rsi
0x1801b84fc  mov     rax, [rax+18h]
0x1801b8500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8505  test    eax, eax
0x1801b8507  jnz     short loc_1801B8528
0x1801b8509  mov     rcx, [rsp+218h+String]; String
0x1801b850e  test    rcx, rcx
0x1801b8511  jz      short loc_1801B8528
0x1801b8513  call    cs:__imp__wtoi
0x1801b8519  mov     [rsp+218h+var_D8], eax
0x1801b8520  mov     [rsp+218h+var_D4], 1
0x1801b8528  mov     rax, [rsi]
0x1801b852b  lea     r9, [rsp+218h+String]
0x1801b8530  lea     r8, aDisablefamilyu; "DisableFamilyUI"
0x1801b8537  mov     edx, r14d
0x1801b853a  mov     rcx, rsi
0x1801b853d  mov     rax, [rax+18h]
0x1801b8541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8546  test    eax, eax
0x1801b8548  jnz     short loc_1801B8569
0x1801b854a  mov     rcx, [rsp+218h+String]; String
0x1801b854f  test    rcx, rcx
0x1801b8552  jz      short loc_1801B8569
0x1801b8554  call    cs:__imp__wtoi
0x1801b855a  mov     [rsp+218h+var_D0], eax
0x1801b8561  mov     [rsp+218h+var_CC], 1
0x1801b8569  mov     rax, [rsi]
0x1801b856c  lea     r9, [rsp+218h+String]
0x1801b8571  lea     r8, aDisablehealthu; "DisableHealthUI"
0x1801b8578  mov     edx, r14d
0x1801b857b  mov     rcx, rsi
0x1801b857e  mov     rax, [rax+18h]
0x1801b8582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8587  test    eax, eax
0x1801b8589  jnz     short loc_1801B85AA
0x1801b858b  mov     rcx, [rsp+218h+String]; String
0x1801b8590  test    rcx, rcx
0x1801b8593  jz      short loc_1801B85AA
0x1801b8595  call    cs:__imp__wtoi
0x1801b859b  mov     [rsp+218h+var_C8], eax
0x1801b85a2  mov     [rsp+218h+var_C4], 1
0x1801b85aa  mov     rax, [rsi]
0x1801b85ad  lea     r9, [rsp+218h+String]
0x1801b85b2  lea     r8, aDisablenetwork; "DisableNetworkUI"
0x1801b85b9  mov     edx, r14d
0x1801b85bc  mov     rcx, rsi
0x1801b85bf  mov     rax, [rax+18h]
0x1801b85c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b85c8  test    eax, eax
0x1801b85ca  jnz     short loc_1801B85EB
  ... truncated ...
```
