# MDM_Policy_Config01_Connectivity02_InvokeEnumerateInstances

- ea: `0x180071134`
- end: `0x180071841`
- name: `MDM_Policy_Config01_Connectivity02_InvokeEnumerateInstances`
- size: `1805`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180070770`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000506c`
- `0x1800050dc`
- `0x1800051bc`
- `0x1800051f4`
- `0x180005264`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180071134`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180071446`
- `msvcrt!_wtoi` at `0x180071487`
- `msvcrt!_wtoi` at `0x1800714c8`
- `msvcrt!_wtoi` at `0x180071509`
- `msvcrt!_wtoi` at `0x18007154a`
- `msvcrt!_wtoi` at `0x18007158b`
- `msvcrt!_wtoi` at `0x1800715cc`
- `msvcrt!_wtoi` at `0x1800716b8`
- `msvcrt!_wtoi` at `0x180071446`
- `msvcrt!_wtoi` at `0x180071487`
- `msvcrt!_wtoi` at `0x1800714c8`
- `msvcrt!_wtoi` at `0x180071509`
- `msvcrt!_wtoi` at `0x18007154a`
- `msvcrt!_wtoi` at `0x18007158b`
- `msvcrt!_wtoi` at `0x1800715cc`
- `msvcrt!_wtoi` at `0x1800716b8`

## string_xrefs

- `0x180071526`: `AllowPhonePCLinking`
- `0x1800716d5`: `HardenedUNCPaths`
- `0x18007170e`: `ProhibitInstallationAndConfigurationOfNetworkBridge`
- `0x180071388`: `./Vendor/MSFT/Policy/Config`
- `0x1800711af`: `MDM_Policy_Config01_Connectivity02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Connectivity02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r14d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-190h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-180h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-168h] BYREF
  char v17; // [rsp+80h] [rbp-158h]
  int v18; // [rsp+88h] [rbp-150h] BYREF
  char v19; // [rsp+8Ch] [rbp-14Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-148h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-138h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-128h] BYREF
  int v23; // [rsp+110h] [rbp-C8h]
  char v24; // [rsp+114h] [rbp-C4h]
  int v25; // [rsp+118h] [rbp-C0h]
  char v26; // [rsp+11Ch] [rbp-BCh]
  int v27; // [rsp+120h] [rbp-B8h]
  char v28; // [rsp+124h] [rbp-B4h]
  int v29; // [rsp+128h] [rbp-B0h]
  char v30; // [rsp+12Ch] [rbp-ACh]
  int v31; // [rsp+130h] [rbp-A8h]
  char v32; // [rsp+134h] [rbp-A4h]
  int v33; // [rsp+138h] [rbp-A0h]
  char v34; // [rsp+13Ch] [rbp-9Ch]
  int v35; // [rsp+140h] [rbp-98h]
  char v36; // [rsp+144h] [rbp-94h]
  int v37; // [rsp+178h] [rbp-60h]
  char v38; // [rsp+17Ch] [rbp-5Ch]

  memset_0(&instance, 0, 0xF0u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_Connectivity02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180368A19,
      v20,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v15, v4);
  try
  {
    v14 = 0;
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Connectivity02_NodeList,
           0xFu,
           2,
           &v14);
    if ( !v7 )
    {
      v16[1] = (const exception *)&v14;
      v17 = 1;
      v8 = v14;
      if ( v14 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v7 )
        {
          v6 = v14;
          if ( v14 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v14;
            if ( v14 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Connectivity02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_85;
              }
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
                      L"Connectivity",
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
                        L"AllowBluetooth",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCellularData",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCellularDataRoaming",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowConnectedDevices",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowPhonePCLinking",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowVPNOverCellular",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowVPNRoamingOverCellular",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DiablePrintingOverHTTP",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDownloadingOfPrintDriversOverHTTP",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisallowNetworkConnectivityActiveTests",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HardenedUNCPaths",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_ProfileXML(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ProhibitInstallationAndConfigurationOfNetworkBridge",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
            }
            v6 = v14;
            if ( v14 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
              v14 = 0;
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
  catch ( const exception *v16 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v16[0] + 8LL))(v16[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v15, v11);
    LODWORD(v14) = 1;
    v7 = 1;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v15, v12);
    LODWORD(v14) = 1;
    v7 = 1;
  }
LABEL_85:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18036603D,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return v7;
}

```

## disassembly

```asm
0x180071134  mov     [rsp+arg_8], rbx
0x180071139  mov     [rsp+arg_10], rsi
0x18007113e  push    rdi
0x18007113f  push    r12
0x180071141  push    r13
0x180071143  push    r14
0x180071145  push    r15
0x180071147  sub     rsp, 1B0h
0x18007114e  mov     rax, cs:__security_cookie
0x180071155  xor     rax, rsp
0x180071158  mov     [rsp+1D8h+var_38], rax
0x180071160  mov     r13b, dl
0x180071163  mov     r12, rcx
0x180071166  xor     edx, edx; Val
0x180071168  mov     r8d, 0F0h; Size
0x18007116e  lea     rcx, [rsp+1D8h+instance]; void *
0x180071176  call    memset_0
0x18007117b  xor     edi, edi
0x18007117d  mov     [rsp+1D8h+var_198], dil
0x180071182  mov     [rsp+1D8h+String], rdi
0x180071187  mov     [rsp+1D8h+var_150], edi
0x18007118e  mov     [rsp+1D8h+var_14C], dil
0x180071196  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18007119d  mov     [rsp+1D8h+var_180], rax
0x1800711a2  lea     rax, [rsp+1D8h+var_150]
0x1800711aa  mov     [rsp+1D8h+var_178], rax
0x1800711af  lea     rax, aMdmPolicyConfi_107; "MDM_Policy_Config01_Connectivity02"
0x1800711b6  mov     [rsp+1D8h+var_170], rax
0x1800711bb  lea     rcx, [rsp+1D8h+var_150]
0x1800711c3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800711c8  mov     eax, cs:dword_180380B68
0x1800711ce  cmp     eax, 5
0x1800711d1  jbe     short loc_180071243
0x1800711d3  mov     rdx, 200000000000h
0x1800711dd  lea     rcx, dword_180380B68
0x1800711e4  call    _tlgKeywordOn
0x1800711e9  test    al, al
0x1800711eb  jz      short loc_180071243
0x1800711ed  cmp     [rsp+1D8h+var_14C], dil
0x1800711f5  jz      short loc_180071225
0x1800711f7  cmp     [rsp+1D8h+var_138], edi
0x1800711fe  jnz     short loc_18007121B
0x180071200  cmp     [rsp+1D8h+var_134], edi
0x180071207  jnz     short loc_18007121B
0x180071209  cmp     [rsp+1D8h+var_130], edi
0x180071210  jnz     short loc_18007121B
0x180071212  cmp     [rsp+1D8h+var_12C], edi
0x180071219  jz      short loc_180071225
0x18007121b  lea     r9, [rsp+1D8h+var_138]
0x180071223  jmp     short loc_180071228
0x180071225  mov     r9, rdi
0x180071228  lea     r8, [rsp+1D8h+var_148]
0x180071230  lea     rdx, byte_180368A19
0x180071237  lea     rcx, dword_180380B68
0x18007123e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180071243  lea     rcx, [rsp+1D8h+var_180]; this
0x180071248  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18007124d  nop
0x18007124e  mov     [rsp+1D8h+var_188], rdi
0x180071253  lea     rax, [rsp+1D8h+var_188]
0x180071258  mov     [rsp+1D8h+var_1A8], rax
0x18007125d  mov     [rsp+1D8h+var_1B0], 2
0x180071265  mov     [rsp+1D8h+var_1B8], 0Fh
0x18007126d  lea     r9, ?MDM_Policy_Config01_Connectivity02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Connectivity02_NodeList
0x180071274  xor     r8d, r8d
0x180071277  xor     edx, edx
0x180071279  mov     rcx, r12
0x18007127c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180071281  mov     r14d, eax
0x180071284  test    eax, eax
0x180071286  jz      short loc_18007128D
0x180071288  jmp     loc_1800717A1
0x18007128d  lea     rbx, [rsp+1D8h+var_188]
0x180071292  mov     [rsp+1D8h+var_160], rbx
0x180071297  mov     r15d, 1
0x18007129d  mov     [rsp+1D8h+var_158], r15b
0x1800712a5  mov     rsi, [rsp+1D8h+var_188]
0x1800712aa  test    rsi, rsi
0x1800712ad  jnz     short loc_1800712B7
0x1800712af  mov     r14d, r15d
0x1800712b2  jmp     loc_1800717A1
0x1800712b7  mov     rax, [rsi]
0x1800712ba  mov     rcx, rsi
0x1800712bd  mov     rax, [rax+10h]
0x1800712c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712c6  mov     r14d, eax
0x1800712c9  test    eax, eax
0x1800712cb  jz      short loc_1800712EB
0x1800712cd  mov     rcx, [rsp+1D8h+var_188]
0x1800712d2  test    rcx, rcx
0x1800712d5  jz      short loc_1800712E6
0x1800712d7  mov     rax, [rcx]
0x1800712da  mov     edx, r15d
0x1800712dd  mov     rax, [rax]
0x1800712e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712e5  nop
0x1800712e6  jmp     loc_1800717A1
0x1800712eb  mov     rax, [rsi]
0x1800712ee  mov     rcx, rsi
0x1800712f1  mov     rax, [rax+8]
0x1800712f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712fa  mov     r14d, eax
0x1800712fd  test    eax, eax
0x1800712ff  jz      short loc_18007131F
0x180071301  mov     rcx, [rsp+1D8h+var_188]
0x180071306  test    rcx, rcx
0x180071309  jz      short loc_18007131A
0x18007130b  mov     rax, [rcx]
0x18007130e  mov     edx, r15d
0x180071311  mov     rax, [rax]
0x180071314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071319  nop
0x18007131a  jmp     loc_1800717A1
0x18007131f  mov     r15d, edi
0x180071322  mov     rax, [rsi+108h]
0x180071329  sub     rax, [rsi+100h]
0x180071330  sar     rax, 4
0x180071334  cmp     r15d, eax
0x180071337  jnb     loc_180071769
0x18007133d  lea     r8, [rsp+1D8h+instance]; instance
0x180071345  lea     rdx, MDM_Policy_Config01_Connectivity02_rtti; classDecl
0x18007134c  mov     rcx, r12; context
0x18007134f  call    MI_Context_ConstructInstance
0x180071354  mov     r14d, eax
0x180071357  test    eax, eax
0x180071359  jz      short loc_18007137B
0x18007135b  mov     rcx, [rbx]
0x18007135e  test    rcx, rcx
0x180071361  jz      short loc_180071376
0x180071363  mov     rax, [rcx]
0x180071366  mov     edx, 1
0x18007136b  mov     rax, [rax]
0x18007136e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071373  mov     [rbx], rdi
0x180071376  jmp     loc_1800717A1
0x18007137b  mov     [rsp+1D8h+var_198], 1
0x180071380  mov     rax, [rsi]
0x180071383  lea     r9, [rsp+1D8h+String]
0x180071388  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18007138f  mov     edx, r15d
0x180071392  mov     rcx, rsi
0x180071395  mov     rax, [rax+18h]
0x180071399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007139e  test    eax, eax
0x1800713a0  jnz     short loc_1800713B9
0x1800713a2  mov     rdx, [rsp+1D8h+String]
0x1800713a7  test    rdx, rdx
0x1800713aa  jz      short loc_1800713B9
0x1800713ac  lea     rcx, [rsp+1D8h+instance]
0x1800713b4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800713b9  mov     rax, [rsi]
0x1800713bc  lea     r9, [rsp+1D8h+String]
0x1800713c1  lea     r8, aConnectivity; "Connectivity"
0x1800713c8  mov     edx, r15d
0x1800713cb  mov     rcx, rsi
0x1800713ce  mov     rax, [rax+18h]
0x1800713d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713d7  test    eax, eax
0x1800713d9  jnz     short loc_1800713F2
0x1800713db  mov     rdx, [rsp+1D8h+String]
0x1800713e0  test    rdx, rdx
0x1800713e3  jz      short loc_1800713F2
0x1800713e5  lea     rcx, [rsp+1D8h+instance]
0x1800713ed  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800713f2  cmp     r13b, 1
0x1800713f6  jnz     short loc_18007141A
0x1800713f8  lea     rdx, [rsp+1D8h+instance]
0x180071400  mov     rcx, r12; self
0x180071403  call    MI_Instance_Destruct
0x180071408  lea     rcx, [rsp+1D8h+instance]; self
0x180071410  call    MI_Instance_Destruct
0x180071415  jmp     loc_18007175C
0x18007141a  mov     rax, [rsi]
0x18007141d  lea     r9, [rsp+1D8h+String]
0x180071422  lea     r8, aAllowbluetooth; "AllowBluetooth"
0x180071429  mov     edx, r15d
0x18007142c  mov     rcx, rsi
0x18007142f  mov     rax, [rax+18h]
0x180071433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071438  test    eax, eax
0x18007143a  jnz     short loc_18007145B
0x18007143c  mov     rcx, [rsp+1D8h+String]; String
0x180071441  test    rcx, rcx
0x180071444  jz      short loc_18007145B
0x180071446  call    cs:__imp__wtoi
0x18007144c  mov     [rsp+1D8h+var_C8], eax
0x180071453  mov     [rsp+1D8h+var_C4], 1
0x18007145b  mov     rax, [rsi]
0x18007145e  lea     r9, [rsp+1D8h+String]
0x180071463  lea     r8, aAllowcellulard; "AllowCellularData"
0x18007146a  mov     edx, r15d
0x18007146d  mov     rcx, rsi
0x180071470  mov     rax, [rax+18h]
0x180071474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071479  test    eax, eax
0x18007147b  jnz     short loc_18007149C
0x18007147d  mov     rcx, [rsp+1D8h+String]; String
0x180071482  test    rcx, rcx
0x180071485  jz      short loc_18007149C
0x180071487  call    cs:__imp__wtoi
0x18007148d  mov     [rsp+1D8h+var_C0], eax
0x180071494  mov     [rsp+1D8h+var_BC], 1
0x18007149c  mov     rax, [rsi]
0x18007149f  lea     r9, [rsp+1D8h+String]
0x1800714a4  lea     r8, aAllowcellulard_0; "AllowCellularDataRoaming"
0x1800714ab  mov     edx, r15d
0x1800714ae  mov     rcx, rsi
0x1800714b1  mov     rax, [rax+18h]
0x1800714b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800714ba  test    eax, eax
0x1800714bc  jnz     short loc_1800714DD
0x1800714be  mov     rcx, [rsp+1D8h+String]; String
0x1800714c3  test    rcx, rcx
0x1800714c6  jz      short loc_1800714DD
0x1800714c8  call    cs:__imp__wtoi
0x1800714ce  mov     [rsp+1D8h+var_B8], eax
0x1800714d5  mov     [rsp+1D8h+var_B4], 1
0x1800714dd  mov     rax, [rsi]
0x1800714e0  lea     r9, [rsp+1D8h+String]
0x1800714e5  lea     r8, aAllowconnected; "AllowConnectedDevices"
0x1800714ec  mov     edx, r15d
0x1800714ef  mov     rcx, rsi
0x1800714f2  mov     rax, [rax+18h]
0x1800714f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800714fb  test    eax, eax
0x1800714fd  jnz     short loc_18007151E
0x1800714ff  mov     rcx, [rsp+1D8h+String]; String
0x180071504  test    rcx, rcx
0x180071507  jz      short loc_18007151E
0x180071509  call    cs:__imp__wtoi
0x18007150f  mov     [rsp+1D8h+var_B0], eax
0x180071516  mov     [rsp+1D8h+var_AC], 1
0x18007151e  mov     rax, [rsi]
0x180071521  lea     r9, [rsp+1D8h+String]
0x180071526  lea     r8, aAllowphonepcli; "AllowPhonePCLinking"
0x18007152d  mov     edx, r15d
0x180071530  mov     rcx, rsi
0x180071533  mov     rax, [rax+18h]
0x180071537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007153c  test    eax, eax
0x18007153e  jnz     short loc_18007155F
0x180071540  mov     rcx, [rsp+1D8h+String]; String
0x180071545  test    rcx, rcx
0x180071548  jz      short loc_18007155F
0x18007154a  call    cs:__imp__wtoi
0x180071550  mov     [rsp+1D8h+var_A8], eax
0x180071557  mov     [rsp+1D8h+var_A4], 1
0x18007155f  mov     rax, [rsi]
0x180071562  lea     r9, [rsp+1D8h+String]
0x180071567  lea     r8, aAllowvpnoverce; "AllowVPNOverCellular"
0x18007156e  mov     edx, r15d
0x180071571  mov     rcx, rsi
0x180071574  mov     rax, [rax+18h]
0x180071578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007157d  test    eax, eax
0x18007157f  jnz     short loc_1800715A0
0x180071581  mov     rcx, [rsp+1D8h+String]; String
0x180071586  test    rcx, rcx
0x180071589  jz      short loc_1800715A0
0x18007158b  call    cs:__imp__wtoi
0x180071591  mov     [rsp+1D8h+var_A0], eax
0x180071598  mov     [rsp+1D8h+var_9C], 1
0x1800715a0  mov     rax, [rsi]
0x1800715a3  lea     r9, [rsp+1D8h+String]
0x1800715a8  lea     r8, aAllowvpnroamin; "AllowVPNRoamingOverCellular"
0x1800715af  mov     edx, r15d
0x1800715b2  mov     rcx, rsi
0x1800715b5  mov     rax, [rax+18h]
0x1800715b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800715be  test    eax, eax
0x1800715c0  jnz     short loc_1800715E1
0x1800715c2  mov     rcx, [rsp+1D8h+String]; String
0x1800715c7  test    rcx, rcx
0x1800715ca  jz      short loc_1800715E1
0x1800715cc  call    cs:__imp__wtoi
0x1800715d2  mov     [rsp+1D8h+var_98], eax
0x1800715d9  mov     [rsp+1D8h+var_94], 1
0x1800715e1  mov     rax, [rsi]
0x1800715e4  lea     r9, [rsp+1D8h+String]
0x1800715e9  lea     r8, aDiableprinting; "DiablePrintingOverHTTP"
0x1800715f0  mov     edx, r15d
0x1800715f3  mov     rcx, rsi
0x1800715f6  mov     rax, [rax+18h]
0x1800715fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800715ff  test    eax, eax
0x180071601  jnz     short loc_18007161A
0x180071603  mov     rdx, [rsp+1D8h+String]
0x180071608  test    rdx, rdx
0x18007160b  jz      short loc_18007161A
0x18007160d  lea     rcx, [rsp+1D8h+instance]
0x180071615  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x18007161a  mov     rax, [rsi]
0x18007161d  lea     r9, [rsp+1D8h+String]
0x180071622  lea     r8, aDisabledownloa; "DisableDownloadingOfPrintDriversOverHTT"...
0x180071629  mov     edx, r15d
0x18007162c  mov     rcx, rsi
0x18007162f  mov     rax, [rax+18h]
0x180071633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071638  test    eax, eax
0x18007163a  jnz     short loc_180071653
  ... truncated ...
```
