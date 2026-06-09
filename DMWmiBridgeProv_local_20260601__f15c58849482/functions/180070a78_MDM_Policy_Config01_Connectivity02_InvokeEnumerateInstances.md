# MDM_Policy_Config01_Connectivity02_InvokeEnumerateInstances

- ea: `0x180070a78`
- end: `0x1800711b6`
- name: `MDM_Policy_Config01_Connectivity02_InvokeEnumerateInstances`
- size: `1854`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800700d0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180005240`
- `0x1800052b0`
- `0x180005390`
- `0x1800053c8`
- `0x180005438`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180070a78`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180070d8a`
- `msvcrt!_wtoi` at `0x180070dd1`
- `msvcrt!_wtoi` at `0x180070e18`
- `msvcrt!_wtoi` at `0x180070e5f`
- `msvcrt!_wtoi` at `0x180070ea6`
- `msvcrt!_wtoi` at `0x180070eed`
- `msvcrt!_wtoi` at `0x180070f34`
- `msvcrt!_wtoi` at `0x180071026`
- `msvcrt!_wtoi` at `0x180070d8a`
- `msvcrt!_wtoi` at `0x180070dd1`
- `msvcrt!_wtoi` at `0x180070e18`
- `msvcrt!_wtoi` at `0x180070e5f`
- `msvcrt!_wtoi` at `0x180070ea6`
- `msvcrt!_wtoi` at `0x180070eed`
- `msvcrt!_wtoi` at `0x180070f34`
- `msvcrt!_wtoi` at `0x180071026`

## string_xrefs

- `0x180070e82`: `AllowPhonePCLinking`
- `0x180071049`: `HardenedUNCPaths`
- `0x180071082`: `ProhibitInstallationAndConfigurationOfNetworkBridge`
- `0x180070ccc`: `./Vendor/MSFT/Policy/Config`
- `0x180070af3`: `MDM_Policy_Config01_Connectivity02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Connectivity02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r14d
  _QWORD *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-190h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-188h] BYREF
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
    v7 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         0,
                         0,
                         &MDM_Policy_Config01_Connectivity02_NodeList,
                         15,
                         2,
                         &v14);
    if ( v7 == MI_RESULT_OK )
    {
      v16[1] = (const exception *)&v14;
      v17 = 1;
      v8 = v14;
      if ( v14 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
        if ( v7 )
        {
          v6 = (wil *)v14;
          if ( v14 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v14;
            if ( v14 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Connectivity02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_85;
              }
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
                      L"Connectivity",
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
                        L"AllowBluetooth",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCellularData",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowCellularDataRoaming",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowConnectedDevices",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowPhonePCLinking",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowVPNOverCellular",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowVPNRoamingOverCellular",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DiablePrintingOverHTTP",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableDownloadingOfPrintDriversOverHTTP",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisallowNetworkConnectivityActiveTests",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HardenedUNCPaths",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_ProfileXML(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
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
            v6 = (wil *)v14;
            if ( v14 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
              v14 = 0;
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
  catch ( const exception *v16 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v16[0] + 8LL))(v16[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v15, v11);
    LODWORD(v14) = 1;
    v7 = MI_RESULT_FAILED;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v15, v12);
    LODWORD(v14) = 1;
    v7 = MI_RESULT_FAILED;
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
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180070a78  mov     [rsp+arg_8], rbx
0x180070a7d  mov     [rsp+arg_10], rsi
0x180070a82  push    rdi
0x180070a83  push    r12
0x180070a85  push    r13
0x180070a87  push    r14
0x180070a89  push    r15
0x180070a8b  sub     rsp, 1B0h
0x180070a92  mov     rax, cs:__security_cookie
0x180070a99  xor     rax, rsp
0x180070a9c  mov     [rsp+1D8h+var_38], rax
0x180070aa4  mov     r13b, dl
0x180070aa7  mov     r12, rcx
0x180070aaa  xor     edx, edx; Val
0x180070aac  mov     r8d, 0F0h; Size
0x180070ab2  lea     rcx, [rsp+1D8h+instance]; void *
0x180070aba  call    memset_0
0x180070abf  xor     edi, edi
0x180070ac1  mov     [rsp+1D8h+var_198], dil
0x180070ac6  mov     [rsp+1D8h+String], rdi
0x180070acb  mov     [rsp+1D8h+var_150], edi
0x180070ad2  mov     [rsp+1D8h+var_14C], dil
0x180070ada  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180070ae1  mov     [rsp+1D8h+var_180], rax
0x180070ae6  lea     rax, [rsp+1D8h+var_150]
0x180070aee  mov     [rsp+1D8h+var_178], rax
0x180070af3  lea     rax, aMdmPolicyConfi_107; "MDM_Policy_Config01_Connectivity02"
0x180070afa  mov     [rsp+1D8h+var_170], rax
0x180070aff  lea     rcx, [rsp+1D8h+var_150]
0x180070b07  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180070b0c  mov     eax, cs:dword_180380B68
0x180070b12  cmp     eax, 5
0x180070b15  jbe     short loc_180070B87
0x180070b17  mov     rdx, 200000000000h
0x180070b21  lea     rcx, dword_180380B68
0x180070b28  call    _tlgKeywordOn
0x180070b2d  test    al, al
0x180070b2f  jz      short loc_180070B87
0x180070b31  cmp     [rsp+1D8h+var_14C], dil
0x180070b39  jz      short loc_180070B69
0x180070b3b  cmp     [rsp+1D8h+var_138], edi
0x180070b42  jnz     short loc_180070B5F
0x180070b44  cmp     [rsp+1D8h+var_134], edi
0x180070b4b  jnz     short loc_180070B5F
0x180070b4d  cmp     [rsp+1D8h+var_130], edi
0x180070b54  jnz     short loc_180070B5F
0x180070b56  cmp     [rsp+1D8h+var_12C], edi
0x180070b5d  jz      short loc_180070B69
0x180070b5f  lea     r9, [rsp+1D8h+var_138]
0x180070b67  jmp     short loc_180070B6C
0x180070b69  mov     r9, rdi
0x180070b6c  lea     r8, [rsp+1D8h+var_148]
0x180070b74  lea     rdx, byte_180368A19
0x180070b7b  lea     rcx, dword_180380B68
0x180070b82  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180070b87  lea     rcx, [rsp+1D8h+var_180]; this
0x180070b8c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180070b91  nop
0x180070b92  mov     [rsp+1D8h+var_188], rdi
0x180070b97  lea     rax, [rsp+1D8h+var_188]
0x180070b9c  mov     [rsp+1D8h+var_1A8], rax
0x180070ba1  mov     [rsp+1D8h+var_1B0], 2
0x180070ba9  mov     [rsp+1D8h+var_1B8], 0Fh
0x180070bb1  lea     r9, ?MDM_Policy_Config01_Connectivity02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Connectivity02_NodeList
0x180070bb8  xor     r8d, r8d
0x180070bbb  xor     edx, edx
0x180070bbd  mov     rcx, r12
0x180070bc0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180070bc5  mov     r14d, eax
0x180070bc8  test    eax, eax
0x180070bca  jz      short loc_180070BD1
0x180070bcc  jmp     loc_180071115
0x180070bd1  lea     rbx, [rsp+1D8h+var_188]
0x180070bd6  mov     [rsp+1D8h+var_160], rbx
0x180070bdb  mov     r15d, 1
0x180070be1  mov     [rsp+1D8h+var_158], r15b
0x180070be9  mov     rsi, [rsp+1D8h+var_188]
0x180070bee  test    rsi, rsi
0x180070bf1  jnz     short loc_180070BFB
0x180070bf3  mov     r14d, r15d
0x180070bf6  jmp     loc_180071115
0x180070bfb  mov     rax, [rsi]
0x180070bfe  mov     rcx, rsi
0x180070c01  mov     rax, [rax+10h]
0x180070c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c0a  mov     r14d, eax
0x180070c0d  test    eax, eax
0x180070c0f  jz      short loc_180070C2F
0x180070c11  mov     rcx, [rsp+1D8h+var_188]
0x180070c16  test    rcx, rcx
0x180070c19  jz      short loc_180070C2A
0x180070c1b  mov     rax, [rcx]
0x180070c1e  mov     edx, r15d
0x180070c21  mov     rax, [rax]
0x180070c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c29  nop
0x180070c2a  jmp     loc_180071115
0x180070c2f  mov     rax, [rsi]
0x180070c32  mov     rcx, rsi
0x180070c35  mov     rax, [rax+8]
0x180070c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c3e  mov     r14d, eax
0x180070c41  test    eax, eax
0x180070c43  jz      short loc_180070C63
0x180070c45  mov     rcx, [rsp+1D8h+var_188]
0x180070c4a  test    rcx, rcx
0x180070c4d  jz      short loc_180070C5E
0x180070c4f  mov     rax, [rcx]
0x180070c52  mov     edx, r15d
0x180070c55  mov     rax, [rax]
0x180070c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c5d  nop
0x180070c5e  jmp     loc_180071115
0x180070c63  mov     r15d, edi
0x180070c66  mov     rax, [rsi+108h]
0x180070c6d  sub     rax, [rsi+100h]
0x180070c74  sar     rax, 4
0x180070c78  cmp     r15d, eax
0x180070c7b  jnb     loc_1800710DD
0x180070c81  lea     r8, [rsp+1D8h+instance]; instance
0x180070c89  lea     rdx, MDM_Policy_Config01_Connectivity02_rtti; classDecl
0x180070c90  mov     rcx, r12; context
0x180070c93  call    MI_Context_ConstructInstance
0x180070c98  mov     r14d, eax
0x180070c9b  test    eax, eax
0x180070c9d  jz      short loc_180070CBF
0x180070c9f  mov     rcx, [rbx]
0x180070ca2  test    rcx, rcx
0x180070ca5  jz      short loc_180070CBA
0x180070ca7  mov     rax, [rcx]
0x180070caa  mov     edx, 1
0x180070caf  mov     rax, [rax]
0x180070cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070cb7  mov     [rbx], rdi
0x180070cba  jmp     loc_180071115
0x180070cbf  mov     [rsp+1D8h+var_198], 1
0x180070cc4  mov     rax, [rsi]
0x180070cc7  lea     r9, [rsp+1D8h+String]
0x180070ccc  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x180070cd3  mov     edx, r15d
0x180070cd6  mov     rcx, rsi
0x180070cd9  mov     rax, [rax+18h]
0x180070cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ce2  test    eax, eax
0x180070ce4  jnz     short loc_180070CFD
0x180070ce6  mov     rdx, [rsp+1D8h+String]
0x180070ceb  test    rdx, rdx
0x180070cee  jz      short loc_180070CFD
0x180070cf0  lea     rcx, [rsp+1D8h+instance]
0x180070cf8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180070cfd  mov     rax, [rsi]
0x180070d00  lea     r9, [rsp+1D8h+String]
0x180070d05  lea     r8, aConnectivity; "Connectivity"
0x180070d0c  mov     edx, r15d
0x180070d0f  mov     rcx, rsi
0x180070d12  mov     rax, [rax+18h]
0x180070d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070d1b  test    eax, eax
0x180070d1d  jnz     short loc_180070D36
0x180070d1f  mov     rdx, [rsp+1D8h+String]
0x180070d24  test    rdx, rdx
0x180070d27  jz      short loc_180070D36
0x180070d29  lea     rcx, [rsp+1D8h+instance]
0x180070d31  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180070d36  cmp     r13b, 1
0x180070d3a  jnz     short loc_180070D5E
0x180070d3c  lea     rdx, [rsp+1D8h+instance]
0x180070d44  mov     rcx, r12; self
0x180070d47  call    MI_Instance_Destruct
0x180070d4c  lea     rcx, [rsp+1D8h+instance]; self
0x180070d54  call    MI_Instance_Destruct
0x180070d59  jmp     loc_1800710D0
0x180070d5e  mov     rax, [rsi]
0x180070d61  lea     r9, [rsp+1D8h+String]
0x180070d66  lea     r8, aAllowbluetooth; "AllowBluetooth"
0x180070d6d  mov     edx, r15d
0x180070d70  mov     rcx, rsi
0x180070d73  mov     rax, [rax+18h]
0x180070d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070d7c  test    eax, eax
0x180070d7e  jnz     short loc_180070DA5
0x180070d80  mov     rcx, [rsp+1D8h+String]; String
0x180070d85  test    rcx, rcx
0x180070d88  jz      short loc_180070DA5
0x180070d8a  call    cs:__imp__wtoi
0x180070d91  nop     dword ptr [rax+rax+00h]
0x180070d96  mov     [rsp+1D8h+var_C8], eax
0x180070d9d  mov     [rsp+1D8h+var_C4], 1
0x180070da5  mov     rax, [rsi]
0x180070da8  lea     r9, [rsp+1D8h+String]
0x180070dad  lea     r8, aAllowcellulard; "AllowCellularData"
0x180070db4  mov     edx, r15d
0x180070db7  mov     rcx, rsi
0x180070dba  mov     rax, [rax+18h]
0x180070dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070dc3  test    eax, eax
0x180070dc5  jnz     short loc_180070DEC
0x180070dc7  mov     rcx, [rsp+1D8h+String]; String
0x180070dcc  test    rcx, rcx
0x180070dcf  jz      short loc_180070DEC
0x180070dd1  call    cs:__imp__wtoi
0x180070dd8  nop     dword ptr [rax+rax+00h]
0x180070ddd  mov     [rsp+1D8h+var_C0], eax
0x180070de4  mov     [rsp+1D8h+var_BC], 1
0x180070dec  mov     rax, [rsi]
0x180070def  lea     r9, [rsp+1D8h+String]
0x180070df4  lea     r8, aAllowcellulard_0; "AllowCellularDataRoaming"
0x180070dfb  mov     edx, r15d
0x180070dfe  mov     rcx, rsi
0x180070e01  mov     rax, [rax+18h]
0x180070e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e0a  test    eax, eax
0x180070e0c  jnz     short loc_180070E33
0x180070e0e  mov     rcx, [rsp+1D8h+String]; String
0x180070e13  test    rcx, rcx
0x180070e16  jz      short loc_180070E33
0x180070e18  call    cs:__imp__wtoi
0x180070e1f  nop     dword ptr [rax+rax+00h]
0x180070e24  mov     [rsp+1D8h+var_B8], eax
0x180070e2b  mov     [rsp+1D8h+var_B4], 1
0x180070e33  mov     rax, [rsi]
0x180070e36  lea     r9, [rsp+1D8h+String]
0x180070e3b  lea     r8, aAllowconnected; "AllowConnectedDevices"
0x180070e42  mov     edx, r15d
0x180070e45  mov     rcx, rsi
0x180070e48  mov     rax, [rax+18h]
0x180070e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e51  test    eax, eax
0x180070e53  jnz     short loc_180070E7A
0x180070e55  mov     rcx, [rsp+1D8h+String]; String
0x180070e5a  test    rcx, rcx
0x180070e5d  jz      short loc_180070E7A
0x180070e5f  call    cs:__imp__wtoi
0x180070e66  nop     dword ptr [rax+rax+00h]
0x180070e6b  mov     [rsp+1D8h+var_B0], eax
0x180070e72  mov     [rsp+1D8h+var_AC], 1
0x180070e7a  mov     rax, [rsi]
0x180070e7d  lea     r9, [rsp+1D8h+String]
0x180070e82  lea     r8, aAllowphonepcli; "AllowPhonePCLinking"
0x180070e89  mov     edx, r15d
0x180070e8c  mov     rcx, rsi
0x180070e8f  mov     rax, [rax+18h]
0x180070e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e98  test    eax, eax
0x180070e9a  jnz     short loc_180070EC1
0x180070e9c  mov     rcx, [rsp+1D8h+String]; String
0x180070ea1  test    rcx, rcx
0x180070ea4  jz      short loc_180070EC1
0x180070ea6  call    cs:__imp__wtoi
0x180070ead  nop     dword ptr [rax+rax+00h]
0x180070eb2  mov     [rsp+1D8h+var_A8], eax
0x180070eb9  mov     [rsp+1D8h+var_A4], 1
0x180070ec1  mov     rax, [rsi]
0x180070ec4  lea     r9, [rsp+1D8h+String]
0x180070ec9  lea     r8, aAllowvpnoverce; "AllowVPNOverCellular"
0x180070ed0  mov     edx, r15d
0x180070ed3  mov     rcx, rsi
0x180070ed6  mov     rax, [rax+18h]
0x180070eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070edf  test    eax, eax
0x180070ee1  jnz     short loc_180070F08
0x180070ee3  mov     rcx, [rsp+1D8h+String]; String
0x180070ee8  test    rcx, rcx
0x180070eeb  jz      short loc_180070F08
0x180070eed  call    cs:__imp__wtoi
0x180070ef4  nop     dword ptr [rax+rax+00h]
0x180070ef9  mov     [rsp+1D8h+var_A0], eax
0x180070f00  mov     [rsp+1D8h+var_9C], 1
0x180070f08  mov     rax, [rsi]
0x180070f0b  lea     r9, [rsp+1D8h+String]
0x180070f10  lea     r8, aAllowvpnroamin; "AllowVPNRoamingOverCellular"
0x180070f17  mov     edx, r15d
0x180070f1a  mov     rcx, rsi
0x180070f1d  mov     rax, [rax+18h]
0x180070f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f26  test    eax, eax
0x180070f28  jnz     short loc_180070F4F
0x180070f2a  mov     rcx, [rsp+1D8h+String]; String
0x180070f2f  test    rcx, rcx
0x180070f32  jz      short loc_180070F4F
0x180070f34  call    cs:__imp__wtoi
0x180070f3b  nop     dword ptr [rax+rax+00h]
0x180070f40  mov     [rsp+1D8h+var_98], eax
0x180070f47  mov     [rsp+1D8h+var_94], 1
0x180070f4f  mov     rax, [rsi]
0x180070f52  lea     r9, [rsp+1D8h+String]
0x180070f57  lea     r8, aDiableprinting; "DiablePrintingOverHTTP"
0x180070f5e  mov     edx, r15d
0x180070f61  mov     rcx, rsi
0x180070f64  mov     rax, [rax+18h]
0x180070f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070f6d  test    eax, eax
0x180070f6f  jnz     short loc_180070F88
0x180070f71  mov     rdx, [rsp+1D8h+String]
0x180070f76  test    rdx, rdx
0x180070f79  jz      short loc_180070F88
0x180070f7b  lea     rcx, [rsp+1D8h+instance]
0x180070f83  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180070f88  mov     rax, [rsi]
0x180070f8b  lea     r9, [rsp+1D8h+String]
  ... truncated ...
```
