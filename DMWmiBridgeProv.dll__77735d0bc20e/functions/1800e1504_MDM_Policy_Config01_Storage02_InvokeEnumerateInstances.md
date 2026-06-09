# MDM_Policy_Config01_Storage02_InvokeEnumerateInstances

- ea: `0x1800e1504`
- end: `0x1800e1b9f`
- name: `MDM_Policy_Config01_Storage02_InvokeEnumerateInstances`
- size: `1691`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e0bc0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000506c`
- `0x180005184`
- `0x180005264`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800e1504`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e1816`
- `msvcrt!_wtoi` at `0x1800e1857`
- `msvcrt!_wtoi` at `0x1800e1898`
- `msvcrt!_wtoi` at `0x1800e18d9`
- `msvcrt!_wtoi` at `0x1800e191a`
- `msvcrt!_wtoi` at `0x1800e195b`
- `msvcrt!_wtoi` at `0x1800e199c`
- `msvcrt!_wtoi` at `0x1800e1a16`
- `msvcrt!_wtoi` at `0x1800e1816`
- `msvcrt!_wtoi` at `0x1800e1857`
- `msvcrt!_wtoi` at `0x1800e1898`
- `msvcrt!_wtoi` at `0x1800e18d9`
- `msvcrt!_wtoi` at `0x1800e191a`
- `msvcrt!_wtoi` at `0x1800e195b`
- `msvcrt!_wtoi` at `0x1800e199c`
- `msvcrt!_wtoi` at `0x1800e1a16`

## string_xrefs

- `0x1800e17f2`: `AllowDiskHealthModelUpdates`
- `0x1800e1874`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x1800e18b5`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x1800e18f6`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1800e1937`: `ConfigStorageSenseGlobalCadence`
- `0x1800e1978`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x1800e19f2`: `RemovableDiskDenyWriteAccess`
- `0x1800e1a33`: `WPDDevicesDenyReadAccessPerDevice`
- `0x1800e1a6c`: `WPDDevicesDenyWriteAccessPerDevice`
- `0x1800e1758`: `./Vendor/MSFT/Policy/Config`
- `0x1800e157f`: `MDM_Policy_Config01_Storage02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Storage02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r14d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-170h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-168h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Storage02_NodeList,
           0xDu,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Storage02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_79;
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
                      L"Storage",
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
                        L"AllowDiskHealthModelUpdates",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStorageSenseGlobal",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStorageSenseTemporaryFilesCleanup",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseCloudContentDehydrationThreshold",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseDownloadsCleanupThreshold",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseGlobalCadence",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigStorageSenseRecycleBinCleanupThreshold",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnhancedStorageDevices",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RemovableDiskDenyWriteAccess",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"WPDDevicesDenyReadAccessPerDevice",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
  return v7;
}

```

## disassembly

```asm
0x1800e1504  mov     [rsp+arg_8], rbx
0x1800e1509  mov     [rsp+arg_10], rsi
0x1800e150e  push    rdi
0x1800e150f  push    r12
0x1800e1511  push    r13
0x1800e1513  push    r14
0x1800e1515  push    r15
0x1800e1517  sub     rsp, 190h
0x1800e151e  mov     rax, cs:__security_cookie
0x1800e1525  xor     rax, rsp
0x1800e1528  mov     [rsp+1B8h+var_38], rax
0x1800e1530  mov     r13b, dl
0x1800e1533  mov     r12, rcx
0x1800e1536  xor     edx, edx; Val
0x1800e1538  mov     r8d, 0D0h; Size
0x1800e153e  lea     rcx, [rsp+1B8h+instance]; void *
0x1800e1546  call    memset_0
0x1800e154b  xor     edi, edi
0x1800e154d  mov     [rsp+1B8h+var_178], dil
0x1800e1552  mov     [rsp+1B8h+String], rdi
0x1800e1557  mov     [rsp+1B8h+var_130], edi
0x1800e155e  mov     [rsp+1B8h+var_12C], dil
0x1800e1566  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e156d  mov     [rsp+1B8h+var_160], rax
0x1800e1572  lea     rax, [rsp+1B8h+var_130]
0x1800e157a  mov     [rsp+1B8h+var_158], rax
0x1800e157f  lea     rax, aMdmPolicyConfi_172; "MDM_Policy_Config01_Storage02"
0x1800e1586  mov     [rsp+1B8h+var_150], rax
0x1800e158b  lea     rcx, [rsp+1B8h+var_130]
0x1800e1593  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e1598  mov     eax, cs:dword_180380B68
0x1800e159e  cmp     eax, 5
0x1800e15a1  jbe     short loc_1800E1613
0x1800e15a3  mov     rdx, 200000000000h
0x1800e15ad  lea     rcx, dword_180380B68
0x1800e15b4  call    _tlgKeywordOn
0x1800e15b9  test    al, al
0x1800e15bb  jz      short loc_1800E1613
0x1800e15bd  cmp     [rsp+1B8h+var_12C], dil
0x1800e15c5  jz      short loc_1800E15F5
0x1800e15c7  cmp     [rsp+1B8h+var_118], edi
0x1800e15ce  jnz     short loc_1800E15EB
0x1800e15d0  cmp     [rsp+1B8h+var_114], edi
0x1800e15d7  jnz     short loc_1800E15EB
0x1800e15d9  cmp     [rsp+1B8h+var_110], edi
0x1800e15e0  jnz     short loc_1800E15EB
0x1800e15e2  cmp     [rsp+1B8h+var_10C], edi
0x1800e15e9  jz      short loc_1800E15F5
0x1800e15eb  lea     r9, [rsp+1B8h+var_118]
0x1800e15f3  jmp     short loc_1800E15F8
0x1800e15f5  mov     r9, rdi
0x1800e15f8  lea     r8, [rsp+1B8h+var_128]
0x1800e1600  lea     rdx, dword_18034AC44
0x1800e1607  lea     rcx, dword_180380B68
0x1800e160e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e1613  lea     rcx, [rsp+1B8h+var_160]; this
0x1800e1618  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800e161d  nop
0x1800e161e  mov     [rsp+1B8h+var_168], rdi
0x1800e1623  lea     rax, [rsp+1B8h+var_168]
0x1800e1628  mov     [rsp+1B8h+var_188], rax
0x1800e162d  mov     [rsp+1B8h+var_190], 2
0x1800e1635  mov     [rsp+1B8h+var_198], 0Dh
0x1800e163d  lea     r9, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Storage02_NodeList
0x1800e1644  xor     r8d, r8d
0x1800e1647  xor     edx, edx
0x1800e1649  mov     rcx, r12
0x1800e164c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e1651  mov     r14d, eax
0x1800e1654  test    eax, eax
0x1800e1656  jz      short loc_1800E165D
0x1800e1658  jmp     loc_1800E1AFF
0x1800e165d  lea     rbx, [rsp+1B8h+var_168]
0x1800e1662  mov     [rsp+1B8h+var_140], rbx
0x1800e1667  mov     r15d, 1
0x1800e166d  mov     [rsp+1B8h+var_138], r15b
0x1800e1675  mov     rsi, [rsp+1B8h+var_168]
0x1800e167a  test    rsi, rsi
0x1800e167d  jnz     short loc_1800E1687
0x1800e167f  mov     r14d, r15d
0x1800e1682  jmp     loc_1800E1AFF
0x1800e1687  mov     rax, [rsi]
0x1800e168a  mov     rcx, rsi
0x1800e168d  mov     rax, [rax+10h]
0x1800e1691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1696  mov     r14d, eax
0x1800e1699  test    eax, eax
0x1800e169b  jz      short loc_1800E16BB
0x1800e169d  mov     rcx, [rsp+1B8h+var_168]
0x1800e16a2  test    rcx, rcx
0x1800e16a5  jz      short loc_1800E16B6
0x1800e16a7  mov     rax, [rcx]
0x1800e16aa  mov     edx, r15d
0x1800e16ad  mov     rax, [rax]
0x1800e16b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e16b5  nop
0x1800e16b6  jmp     loc_1800E1AFF
0x1800e16bb  mov     rax, [rsi]
0x1800e16be  mov     rcx, rsi
0x1800e16c1  mov     rax, [rax+8]
0x1800e16c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e16ca  mov     r14d, eax
0x1800e16cd  test    eax, eax
0x1800e16cf  jz      short loc_1800E16EF
0x1800e16d1  mov     rcx, [rsp+1B8h+var_168]
0x1800e16d6  test    rcx, rcx
0x1800e16d9  jz      short loc_1800E16EA
0x1800e16db  mov     rax, [rcx]
0x1800e16de  mov     edx, r15d
0x1800e16e1  mov     rax, [rax]
0x1800e16e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e16e9  nop
0x1800e16ea  jmp     loc_1800E1AFF
0x1800e16ef  mov     r15d, edi
0x1800e16f2  mov     rax, [rsi+108h]
0x1800e16f9  sub     rax, [rsi+100h]
0x1800e1700  sar     rax, 4
0x1800e1704  cmp     r15d, eax
0x1800e1707  jnb     loc_1800E1AC7
0x1800e170d  lea     r8, [rsp+1B8h+instance]; instance
0x1800e1715  lea     rdx, MDM_Policy_Config01_Storage02_rtti; classDecl
0x1800e171c  mov     rcx, r12; context
0x1800e171f  call    MI_Context_ConstructInstance
0x1800e1724  mov     r14d, eax
0x1800e1727  test    eax, eax
0x1800e1729  jz      short loc_1800E174B
0x1800e172b  mov     rcx, [rbx]
0x1800e172e  test    rcx, rcx
0x1800e1731  jz      short loc_1800E1746
0x1800e1733  mov     rax, [rcx]
0x1800e1736  mov     edx, 1
0x1800e173b  mov     rax, [rax]
0x1800e173e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1743  mov     [rbx], rdi
0x1800e1746  jmp     loc_1800E1AFF
0x1800e174b  mov     [rsp+1B8h+var_178], 1
0x1800e1750  mov     rax, [rsi]
0x1800e1753  lea     r9, [rsp+1B8h+String]
0x1800e1758  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800e175f  mov     edx, r15d
0x1800e1762  mov     rcx, rsi
0x1800e1765  mov     rax, [rax+18h]
0x1800e1769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e176e  test    eax, eax
0x1800e1770  jnz     short loc_1800E1789
0x1800e1772  mov     rdx, [rsp+1B8h+String]
0x1800e1777  test    rdx, rdx
0x1800e177a  jz      short loc_1800E1789
0x1800e177c  lea     rcx, [rsp+1B8h+instance]
0x1800e1784  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e1789  mov     rax, [rsi]
0x1800e178c  lea     r9, [rsp+1B8h+String]
0x1800e1791  lea     r8, aStorage; "Storage"
0x1800e1798  mov     edx, r15d
0x1800e179b  mov     rcx, rsi
0x1800e179e  mov     rax, [rax+18h]
0x1800e17a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e17a7  test    eax, eax
0x1800e17a9  jnz     short loc_1800E17C2
0x1800e17ab  mov     rdx, [rsp+1B8h+String]
0x1800e17b0  test    rdx, rdx
0x1800e17b3  jz      short loc_1800E17C2
0x1800e17b5  lea     rcx, [rsp+1B8h+instance]
0x1800e17bd  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e17c2  cmp     r13b, 1
0x1800e17c6  jnz     short loc_1800E17EA
0x1800e17c8  lea     rdx, [rsp+1B8h+instance]
0x1800e17d0  mov     rcx, r12; self
0x1800e17d3  call    MI_Instance_Destruct
0x1800e17d8  lea     rcx, [rsp+1B8h+instance]; self
0x1800e17e0  call    MI_Instance_Destruct
0x1800e17e5  jmp     loc_1800E1ABA
0x1800e17ea  mov     rax, [rsi]
0x1800e17ed  lea     r9, [rsp+1B8h+String]
0x1800e17f2  lea     r8, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x1800e17f9  mov     edx, r15d
0x1800e17fc  mov     rcx, rsi
0x1800e17ff  mov     rax, [rax+18h]
0x1800e1803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1808  test    eax, eax
0x1800e180a  jnz     short loc_1800E182B
0x1800e180c  mov     rcx, [rsp+1B8h+String]; String
0x1800e1811  test    rcx, rcx
0x1800e1814  jz      short loc_1800E182B
0x1800e1816  call    cs:__imp__wtoi
0x1800e181c  mov     [rsp+1B8h+var_A8], eax
0x1800e1823  mov     [rsp+1B8h+var_A4], 1
0x1800e182b  mov     rax, [rsi]
0x1800e182e  lea     r9, [rsp+1B8h+String]
0x1800e1833  lea     r8, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x1800e183a  mov     edx, r15d
0x1800e183d  mov     rcx, rsi
0x1800e1840  mov     rax, [rax+18h]
0x1800e1844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1849  test    eax, eax
0x1800e184b  jnz     short loc_1800E186C
0x1800e184d  mov     rcx, [rsp+1B8h+String]; String
0x1800e1852  test    rcx, rcx
0x1800e1855  jz      short loc_1800E186C
0x1800e1857  call    cs:__imp__wtoi
0x1800e185d  mov     [rsp+1B8h+var_A0], eax
0x1800e1864  mov     [rsp+1B8h+var_9C], 1
0x1800e186c  mov     rax, [rsi]
0x1800e186f  lea     r9, [rsp+1B8h+String]
0x1800e1874  lea     r8, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x1800e187b  mov     edx, r15d
0x1800e187e  mov     rcx, rsi
0x1800e1881  mov     rax, [rax+18h]
0x1800e1885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e188a  test    eax, eax
0x1800e188c  jnz     short loc_1800E18AD
0x1800e188e  mov     rcx, [rsp+1B8h+String]; String
0x1800e1893  test    rcx, rcx
0x1800e1896  jz      short loc_1800E18AD
0x1800e1898  call    cs:__imp__wtoi
0x1800e189e  mov     [rsp+1B8h+var_98], eax
0x1800e18a5  mov     [rsp+1B8h+var_94], 1
0x1800e18ad  mov     rax, [rsi]
0x1800e18b0  lea     r9, [rsp+1B8h+String]
0x1800e18b5  lea     r8, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x1800e18bc  mov     edx, r15d
0x1800e18bf  mov     rcx, rsi
0x1800e18c2  mov     rax, [rax+18h]
0x1800e18c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e18cb  test    eax, eax
0x1800e18cd  jnz     short loc_1800E18EE
0x1800e18cf  mov     rcx, [rsp+1B8h+String]; String
0x1800e18d4  test    rcx, rcx
0x1800e18d7  jz      short loc_1800E18EE
0x1800e18d9  call    cs:__imp__wtoi
0x1800e18df  mov     [rsp+1B8h+var_90], eax
0x1800e18e6  mov     [rsp+1B8h+var_8C], 1
0x1800e18ee  mov     rax, [rsi]
0x1800e18f1  lea     r9, [rsp+1B8h+String]
0x1800e18f6  lea     r8, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x1800e18fd  mov     edx, r15d
0x1800e1900  mov     rcx, rsi
0x1800e1903  mov     rax, [rax+18h]
0x1800e1907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e190c  test    eax, eax
0x1800e190e  jnz     short loc_1800E192F
0x1800e1910  mov     rcx, [rsp+1B8h+String]; String
0x1800e1915  test    rcx, rcx
0x1800e1918  jz      short loc_1800E192F
0x1800e191a  call    cs:__imp__wtoi
0x1800e1920  mov     [rsp+1B8h+var_88], eax
0x1800e1927  mov     [rsp+1B8h+var_84], 1
0x1800e192f  mov     rax, [rsi]
0x1800e1932  lea     r9, [rsp+1B8h+String]
0x1800e1937  lea     r8, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x1800e193e  mov     edx, r15d
0x1800e1941  mov     rcx, rsi
0x1800e1944  mov     rax, [rax+18h]
0x1800e1948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e194d  test    eax, eax
0x1800e194f  jnz     short loc_1800E1970
0x1800e1951  mov     rcx, [rsp+1B8h+String]; String
0x1800e1956  test    rcx, rcx
0x1800e1959  jz      short loc_1800E1970
0x1800e195b  call    cs:__imp__wtoi
0x1800e1961  mov     [rsp+1B8h+var_80], eax
0x1800e1968  mov     [rsp+1B8h+var_7C], 1
0x1800e1970  mov     rax, [rsi]
0x1800e1973  lea     r9, [rsp+1B8h+String]
0x1800e1978  lea     r8, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x1800e197f  mov     edx, r15d
0x1800e1982  mov     rcx, rsi
0x1800e1985  mov     rax, [rax+18h]
0x1800e1989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e198e  test    eax, eax
0x1800e1990  jnz     short loc_1800E19B1
0x1800e1992  mov     rcx, [rsp+1B8h+String]; String
0x1800e1997  test    rcx, rcx
0x1800e199a  jz      short loc_1800E19B1
0x1800e199c  call    cs:__imp__wtoi
0x1800e19a2  mov     [rsp+1B8h+var_78], eax
0x1800e19a9  mov     [rsp+1B8h+var_74], 1
0x1800e19b1  mov     rax, [rsi]
0x1800e19b4  lea     r9, [rsp+1B8h+String]
0x1800e19b9  lea     r8, aEnhancedstorag; "EnhancedStorageDevices"
0x1800e19c0  mov     edx, r15d
0x1800e19c3  mov     rcx, rsi
0x1800e19c6  mov     rax, [rax+18h]
0x1800e19ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e19cf  test    eax, eax
0x1800e19d1  jnz     short loc_1800E19EA
0x1800e19d3  mov     rdx, [rsp+1B8h+String]
0x1800e19d8  test    rdx, rdx
0x1800e19db  jz      short loc_1800E19EA
0x1800e19dd  lea     rcx, [rsp+1B8h+instance]
0x1800e19e5  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800e19ea  mov     rax, [rsi]
0x1800e19ed  lea     r9, [rsp+1B8h+String]
0x1800e19f2  lea     r8, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x1800e19f9  mov     edx, r15d
0x1800e19fc  mov     rcx, rsi
0x1800e19ff  mov     rax, [rax+18h]
0x1800e1a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1a08  test    eax, eax
0x1800e1a0a  jnz     short loc_1800E1A2B
  ... truncated ...
```
