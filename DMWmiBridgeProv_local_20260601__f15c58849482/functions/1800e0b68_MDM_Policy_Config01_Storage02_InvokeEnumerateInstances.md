# MDM_Policy_Config01_Storage02_InvokeEnumerateInstances

- ea: `0x1800e0b68`
- end: `0x1800e1234`
- name: `MDM_Policy_Config01_Storage02_InvokeEnumerateInstances`
- size: `1740`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e0240`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180005240`
- `0x180005358`
- `0x180005438`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800e0b68`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e0e7a`
- `msvcrt!_wtoi` at `0x1800e0ec1`
- `msvcrt!_wtoi` at `0x1800e0f08`
- `msvcrt!_wtoi` at `0x1800e0f4f`
- `msvcrt!_wtoi` at `0x1800e0f96`
- `msvcrt!_wtoi` at `0x1800e0fdd`
- `msvcrt!_wtoi` at `0x1800e1024`
- `msvcrt!_wtoi` at `0x1800e10a4`
- `msvcrt!_wtoi` at `0x1800e0e7a`
- `msvcrt!_wtoi` at `0x1800e0ec1`
- `msvcrt!_wtoi` at `0x1800e0f08`
- `msvcrt!_wtoi` at `0x1800e0f4f`
- `msvcrt!_wtoi` at `0x1800e0f96`
- `msvcrt!_wtoi` at `0x1800e0fdd`
- `msvcrt!_wtoi` at `0x1800e1024`
- `msvcrt!_wtoi` at `0x1800e10a4`

## string_xrefs

- `0x1800e0e56`: `AllowDiskHealthModelUpdates`
- `0x1800e0ee4`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x1800e0f2b`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x1800e0f72`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1800e0fb9`: `ConfigStorageSenseGlobalCadence`
- `0x1800e1000`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x1800e1080`: `RemovableDiskDenyWriteAccess`
- `0x1800e10c7`: `WPDDevicesDenyReadAccessPerDevice`
- `0x1800e1100`: `WPDDevicesDenyWriteAccessPerDevice`
- `0x1800e0dbc`: `./Vendor/MSFT/Policy/Config`
- `0x1800e0be3`: `MDM_Policy_Config01_Storage02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Storage02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r14d
  _QWORD *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-170h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-168h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-160h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-148h] BYREF
  char v17; // [rsp+80h] [rbp-138h]
  int v18; // [rsp+88h] [rbp-130h] BYREF
  char v19; // [rsp+8Ch] [rbp-12Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-128h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-118h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-108h] BYREF
  int v23; // [rsp+110h] [rbp-A8h]
  char v24; // [rsp+114h] [rbp-A4h]
  int v25; // [rsp+118h] [rbp-A0h]
  char v26; // [rsp+11Ch] [rbp-9Ch]
  int v27; // [rsp+120h] [rbp-98h]
  char v28; // [rsp+124h] [rbp-94h]
  int v29; // [rsp+128h] [rbp-90h]
  char v30; // [rsp+12Ch] [rbp-8Ch]
  int v31; // [rsp+130h] [rbp-88h]
  char v32; // [rsp+134h] [rbp-84h]
  int v33; // [rsp+138h] [rbp-80h]
  char v34; // [rsp+13Ch] [rbp-7Ch]
  int v35; // [rsp+140h] [rbp-78h]
  char v36; // [rsp+144h] [rbp-74h]
  int v37; // [rsp+158h] [rbp-60h]
  char v38; // [rsp+15Ch] [rbp-5Ch]

  memset_0(&instance, 0, 0xD0u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_Storage02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18034AC44,
      v20,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v15, v4);
  try
  {
    v14 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_Storage02_NodeList, 13, 2, &v14);
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Storage02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_79;
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
                      L"Storage",
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
                        L"AllowDiskHealthModelUpdates",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStorageSenseGlobal",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStorageSenseTemporaryFilesCleanup",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseCloudContentDehydrationThreshold",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseDownloadsCleanupThreshold",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseGlobalCadence",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseRecycleBinCleanupThreshold",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnhancedStorageDevices",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RemovableDiskDenyWriteAccess",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"WPDDevicesDenyReadAccessPerDevice",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"WPDDevicesDenyWriteAccessPerDevice",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
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
LABEL_79:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_1803493C6,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800e0b68  mov     [rsp+arg_8], rbx
0x1800e0b6d  mov     [rsp+arg_10], rsi
0x1800e0b72  push    rdi
0x1800e0b73  push    r12
0x1800e0b75  push    r13
0x1800e0b77  push    r14
0x1800e0b79  push    r15
0x1800e0b7b  sub     rsp, 190h
0x1800e0b82  mov     rax, cs:__security_cookie
0x1800e0b89  xor     rax, rsp
0x1800e0b8c  mov     [rsp+1B8h+var_38], rax
0x1800e0b94  mov     r13b, dl
0x1800e0b97  mov     r12, rcx
0x1800e0b9a  xor     edx, edx; Val
0x1800e0b9c  mov     r8d, 0D0h; Size
0x1800e0ba2  lea     rcx, [rsp+1B8h+instance]; void *
0x1800e0baa  call    memset_0
0x1800e0baf  xor     edi, edi
0x1800e0bb1  mov     [rsp+1B8h+var_178], dil
0x1800e0bb6  mov     [rsp+1B8h+String], rdi
0x1800e0bbb  mov     [rsp+1B8h+var_130], edi
0x1800e0bc2  mov     [rsp+1B8h+var_12C], dil
0x1800e0bca  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e0bd1  mov     [rsp+1B8h+var_160], rax
0x1800e0bd6  lea     rax, [rsp+1B8h+var_130]
0x1800e0bde  mov     [rsp+1B8h+var_158], rax
0x1800e0be3  lea     rax, aMdmPolicyConfi_172; "MDM_Policy_Config01_Storage02"
0x1800e0bea  mov     [rsp+1B8h+var_150], rax
0x1800e0bef  lea     rcx, [rsp+1B8h+var_130]
0x1800e0bf7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e0bfc  mov     eax, cs:dword_180380B68
0x1800e0c02  cmp     eax, 5
0x1800e0c05  jbe     short loc_1800E0C77
0x1800e0c07  mov     rdx, 200000000000h
0x1800e0c11  lea     rcx, dword_180380B68
0x1800e0c18  call    _tlgKeywordOn
0x1800e0c1d  test    al, al
0x1800e0c1f  jz      short loc_1800E0C77
0x1800e0c21  cmp     [rsp+1B8h+var_12C], dil
0x1800e0c29  jz      short loc_1800E0C59
0x1800e0c2b  cmp     [rsp+1B8h+var_118], edi
0x1800e0c32  jnz     short loc_1800E0C4F
0x1800e0c34  cmp     [rsp+1B8h+var_114], edi
0x1800e0c3b  jnz     short loc_1800E0C4F
0x1800e0c3d  cmp     [rsp+1B8h+var_110], edi
0x1800e0c44  jnz     short loc_1800E0C4F
0x1800e0c46  cmp     [rsp+1B8h+var_10C], edi
0x1800e0c4d  jz      short loc_1800E0C59
0x1800e0c4f  lea     r9, [rsp+1B8h+var_118]
0x1800e0c57  jmp     short loc_1800E0C5C
0x1800e0c59  mov     r9, rdi
0x1800e0c5c  lea     r8, [rsp+1B8h+var_128]
0x1800e0c64  lea     rdx, dword_18034AC44
0x1800e0c6b  lea     rcx, dword_180380B68
0x1800e0c72  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e0c77  lea     rcx, [rsp+1B8h+var_160]; this
0x1800e0c7c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800e0c81  nop
0x1800e0c82  mov     [rsp+1B8h+var_168], rdi
0x1800e0c87  lea     rax, [rsp+1B8h+var_168]
0x1800e0c8c  mov     [rsp+1B8h+var_188], rax
0x1800e0c91  mov     [rsp+1B8h+var_190], 2
0x1800e0c99  mov     [rsp+1B8h+var_198], 0Dh
0x1800e0ca1  lea     r9, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Storage02_NodeList
0x1800e0ca8  xor     r8d, r8d
0x1800e0cab  xor     edx, edx
0x1800e0cad  mov     rcx, r12
0x1800e0cb0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e0cb5  mov     r14d, eax
0x1800e0cb8  test    eax, eax
0x1800e0cba  jz      short loc_1800E0CC1
0x1800e0cbc  jmp     loc_1800E1193
0x1800e0cc1  lea     rbx, [rsp+1B8h+var_168]
0x1800e0cc6  mov     [rsp+1B8h+var_140], rbx
0x1800e0ccb  mov     r15d, 1
0x1800e0cd1  mov     [rsp+1B8h+var_138], r15b
0x1800e0cd9  mov     rsi, [rsp+1B8h+var_168]
0x1800e0cde  test    rsi, rsi
0x1800e0ce1  jnz     short loc_1800E0CEB
0x1800e0ce3  mov     r14d, r15d
0x1800e0ce6  jmp     loc_1800E1193
0x1800e0ceb  mov     rax, [rsi]
0x1800e0cee  mov     rcx, rsi
0x1800e0cf1  mov     rax, [rax+10h]
0x1800e0cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0cfa  mov     r14d, eax
0x1800e0cfd  test    eax, eax
0x1800e0cff  jz      short loc_1800E0D1F
0x1800e0d01  mov     rcx, [rsp+1B8h+var_168]
0x1800e0d06  test    rcx, rcx
0x1800e0d09  jz      short loc_1800E0D1A
0x1800e0d0b  mov     rax, [rcx]
0x1800e0d0e  mov     edx, r15d
0x1800e0d11  mov     rax, [rax]
0x1800e0d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0d19  nop
0x1800e0d1a  jmp     loc_1800E1193
0x1800e0d1f  mov     rax, [rsi]
0x1800e0d22  mov     rcx, rsi
0x1800e0d25  mov     rax, [rax+8]
0x1800e0d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0d2e  mov     r14d, eax
0x1800e0d31  test    eax, eax
0x1800e0d33  jz      short loc_1800E0D53
0x1800e0d35  mov     rcx, [rsp+1B8h+var_168]
0x1800e0d3a  test    rcx, rcx
0x1800e0d3d  jz      short loc_1800E0D4E
0x1800e0d3f  mov     rax, [rcx]
0x1800e0d42  mov     edx, r15d
0x1800e0d45  mov     rax, [rax]
0x1800e0d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0d4d  nop
0x1800e0d4e  jmp     loc_1800E1193
0x1800e0d53  mov     r15d, edi
0x1800e0d56  mov     rax, [rsi+108h]
0x1800e0d5d  sub     rax, [rsi+100h]
0x1800e0d64  sar     rax, 4
0x1800e0d68  cmp     r15d, eax
0x1800e0d6b  jnb     loc_1800E115B
0x1800e0d71  lea     r8, [rsp+1B8h+instance]; instance
0x1800e0d79  lea     rdx, MDM_Policy_Config01_Storage02_rtti; classDecl
0x1800e0d80  mov     rcx, r12; context
0x1800e0d83  call    MI_Context_ConstructInstance
0x1800e0d88  mov     r14d, eax
0x1800e0d8b  test    eax, eax
0x1800e0d8d  jz      short loc_1800E0DAF
0x1800e0d8f  mov     rcx, [rbx]
0x1800e0d92  test    rcx, rcx
0x1800e0d95  jz      short loc_1800E0DAA
0x1800e0d97  mov     rax, [rcx]
0x1800e0d9a  mov     edx, 1
0x1800e0d9f  mov     rax, [rax]
0x1800e0da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0da7  mov     [rbx], rdi
0x1800e0daa  jmp     loc_1800E1193
0x1800e0daf  mov     [rsp+1B8h+var_178], 1
0x1800e0db4  mov     rax, [rsi]
0x1800e0db7  lea     r9, [rsp+1B8h+String]
0x1800e0dbc  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800e0dc3  mov     edx, r15d
0x1800e0dc6  mov     rcx, rsi
0x1800e0dc9  mov     rax, [rax+18h]
0x1800e0dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0dd2  test    eax, eax
0x1800e0dd4  jnz     short loc_1800E0DED
0x1800e0dd6  mov     rdx, [rsp+1B8h+String]
0x1800e0ddb  test    rdx, rdx
0x1800e0dde  jz      short loc_1800E0DED
0x1800e0de0  lea     rcx, [rsp+1B8h+instance]
0x1800e0de8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e0ded  mov     rax, [rsi]
0x1800e0df0  lea     r9, [rsp+1B8h+String]
0x1800e0df5  lea     r8, aStorage; "Storage"
0x1800e0dfc  mov     edx, r15d
0x1800e0dff  mov     rcx, rsi
0x1800e0e02  mov     rax, [rax+18h]
0x1800e0e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e0b  test    eax, eax
0x1800e0e0d  jnz     short loc_1800E0E26
0x1800e0e0f  mov     rdx, [rsp+1B8h+String]
0x1800e0e14  test    rdx, rdx
0x1800e0e17  jz      short loc_1800E0E26
0x1800e0e19  lea     rcx, [rsp+1B8h+instance]
0x1800e0e21  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e0e26  cmp     r13b, 1
0x1800e0e2a  jnz     short loc_1800E0E4E
0x1800e0e2c  lea     rdx, [rsp+1B8h+instance]
0x1800e0e34  mov     rcx, r12; self
0x1800e0e37  call    MI_Instance_Destruct
0x1800e0e3c  lea     rcx, [rsp+1B8h+instance]; self
0x1800e0e44  call    MI_Instance_Destruct
0x1800e0e49  jmp     loc_1800E114E
0x1800e0e4e  mov     rax, [rsi]
0x1800e0e51  lea     r9, [rsp+1B8h+String]
0x1800e0e56  lea     r8, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x1800e0e5d  mov     edx, r15d
0x1800e0e60  mov     rcx, rsi
0x1800e0e63  mov     rax, [rax+18h]
0x1800e0e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e6c  test    eax, eax
0x1800e0e6e  jnz     short loc_1800E0E95
0x1800e0e70  mov     rcx, [rsp+1B8h+String]; String
0x1800e0e75  test    rcx, rcx
0x1800e0e78  jz      short loc_1800E0E95
0x1800e0e7a  call    cs:__imp__wtoi
0x1800e0e81  nop     dword ptr [rax+rax+00h]
0x1800e0e86  mov     [rsp+1B8h+var_A8], eax
0x1800e0e8d  mov     [rsp+1B8h+var_A4], 1
0x1800e0e95  mov     rax, [rsi]
0x1800e0e98  lea     r9, [rsp+1B8h+String]
0x1800e0e9d  lea     r8, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x1800e0ea4  mov     edx, r15d
0x1800e0ea7  mov     rcx, rsi
0x1800e0eaa  mov     rax, [rax+18h]
0x1800e0eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0eb3  test    eax, eax
0x1800e0eb5  jnz     short loc_1800E0EDC
0x1800e0eb7  mov     rcx, [rsp+1B8h+String]; String
0x1800e0ebc  test    rcx, rcx
0x1800e0ebf  jz      short loc_1800E0EDC
0x1800e0ec1  call    cs:__imp__wtoi
0x1800e0ec8  nop     dword ptr [rax+rax+00h]
0x1800e0ecd  mov     [rsp+1B8h+var_A0], eax
0x1800e0ed4  mov     [rsp+1B8h+var_9C], 1
0x1800e0edc  mov     rax, [rsi]
0x1800e0edf  lea     r9, [rsp+1B8h+String]
0x1800e0ee4  lea     r8, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x1800e0eeb  mov     edx, r15d
0x1800e0eee  mov     rcx, rsi
0x1800e0ef1  mov     rax, [rax+18h]
0x1800e0ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0efa  test    eax, eax
0x1800e0efc  jnz     short loc_1800E0F23
0x1800e0efe  mov     rcx, [rsp+1B8h+String]; String
0x1800e0f03  test    rcx, rcx
0x1800e0f06  jz      short loc_1800E0F23
0x1800e0f08  call    cs:__imp__wtoi
0x1800e0f0f  nop     dword ptr [rax+rax+00h]
0x1800e0f14  mov     [rsp+1B8h+var_98], eax
0x1800e0f1b  mov     [rsp+1B8h+var_94], 1
0x1800e0f23  mov     rax, [rsi]
0x1800e0f26  lea     r9, [rsp+1B8h+String]
0x1800e0f2b  lea     r8, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x1800e0f32  mov     edx, r15d
0x1800e0f35  mov     rcx, rsi
0x1800e0f38  mov     rax, [rax+18h]
0x1800e0f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0f41  test    eax, eax
0x1800e0f43  jnz     short loc_1800E0F6A
0x1800e0f45  mov     rcx, [rsp+1B8h+String]; String
0x1800e0f4a  test    rcx, rcx
0x1800e0f4d  jz      short loc_1800E0F6A
0x1800e0f4f  call    cs:__imp__wtoi
0x1800e0f56  nop     dword ptr [rax+rax+00h]
0x1800e0f5b  mov     [rsp+1B8h+var_90], eax
0x1800e0f62  mov     [rsp+1B8h+var_8C], 1
0x1800e0f6a  mov     rax, [rsi]
0x1800e0f6d  lea     r9, [rsp+1B8h+String]
0x1800e0f72  lea     r8, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x1800e0f79  mov     edx, r15d
0x1800e0f7c  mov     rcx, rsi
0x1800e0f7f  mov     rax, [rax+18h]
0x1800e0f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0f88  test    eax, eax
0x1800e0f8a  jnz     short loc_1800E0FB1
0x1800e0f8c  mov     rcx, [rsp+1B8h+String]; String
0x1800e0f91  test    rcx, rcx
0x1800e0f94  jz      short loc_1800E0FB1
0x1800e0f96  call    cs:__imp__wtoi
0x1800e0f9d  nop     dword ptr [rax+rax+00h]
0x1800e0fa2  mov     [rsp+1B8h+var_88], eax
0x1800e0fa9  mov     [rsp+1B8h+var_84], 1
0x1800e0fb1  mov     rax, [rsi]
0x1800e0fb4  lea     r9, [rsp+1B8h+String]
0x1800e0fb9  lea     r8, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x1800e0fc0  mov     edx, r15d
0x1800e0fc3  mov     rcx, rsi
0x1800e0fc6  mov     rax, [rax+18h]
0x1800e0fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0fcf  test    eax, eax
0x1800e0fd1  jnz     short loc_1800E0FF8
0x1800e0fd3  mov     rcx, [rsp+1B8h+String]; String
0x1800e0fd8  test    rcx, rcx
0x1800e0fdb  jz      short loc_1800E0FF8
0x1800e0fdd  call    cs:__imp__wtoi
0x1800e0fe4  nop     dword ptr [rax+rax+00h]
0x1800e0fe9  mov     [rsp+1B8h+var_80], eax
0x1800e0ff0  mov     [rsp+1B8h+var_7C], 1
0x1800e0ff8  mov     rax, [rsi]
0x1800e0ffb  lea     r9, [rsp+1B8h+String]
0x1800e1000  lea     r8, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x1800e1007  mov     edx, r15d
0x1800e100a  mov     rcx, rsi
0x1800e100d  mov     rax, [rax+18h]
0x1800e1011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1016  test    eax, eax
0x1800e1018  jnz     short loc_1800E103F
0x1800e101a  mov     rcx, [rsp+1B8h+String]; String
0x1800e101f  test    rcx, rcx
0x1800e1022  jz      short loc_1800E103F
0x1800e1024  call    cs:__imp__wtoi
0x1800e102b  nop     dword ptr [rax+rax+00h]
0x1800e1030  mov     [rsp+1B8h+var_78], eax
0x1800e1037  mov     [rsp+1B8h+var_74], 1
0x1800e103f  mov     rax, [rsi]
0x1800e1042  lea     r9, [rsp+1B8h+String]
0x1800e1047  lea     r8, aEnhancedstorag; "EnhancedStorageDevices"
0x1800e104e  mov     edx, r15d
0x1800e1051  mov     rcx, rsi
0x1800e1054  mov     rax, [rax+18h]
0x1800e1058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e105d  test    eax, eax
0x1800e105f  jnz     short loc_1800E1078
0x1800e1061  mov     rdx, [rsp+1B8h+String]
0x1800e1066  test    rdx, rdx
0x1800e1069  jz      short loc_1800E1078
0x1800e106b  lea     rcx, [rsp+1B8h+instance]
0x1800e1073  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800e1078  mov     rax, [rsi]
0x1800e107b  lea     r9, [rsp+1B8h+String]
  ... truncated ...
```
