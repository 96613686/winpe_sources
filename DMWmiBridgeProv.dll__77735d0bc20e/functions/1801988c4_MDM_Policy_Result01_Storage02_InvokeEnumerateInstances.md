# MDM_Policy_Result01_Storage02_InvokeEnumerateInstances

- ea: `0x1801988c4`
- end: `0x180198f5f`
- name: `MDM_Policy_Result01_Storage02_InvokeEnumerateInstances`
- size: `1691`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180197f80`

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
- `0x1801988c4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180198bd6`
- `msvcrt!_wtoi` at `0x180198c17`
- `msvcrt!_wtoi` at `0x180198c58`
- `msvcrt!_wtoi` at `0x180198c99`
- `msvcrt!_wtoi` at `0x180198cda`
- `msvcrt!_wtoi` at `0x180198d1b`
- `msvcrt!_wtoi` at `0x180198d5c`
- `msvcrt!_wtoi` at `0x180198dd6`
- `msvcrt!_wtoi` at `0x180198bd6`
- `msvcrt!_wtoi` at `0x180198c17`
- `msvcrt!_wtoi` at `0x180198c58`
- `msvcrt!_wtoi` at `0x180198c99`
- `msvcrt!_wtoi` at `0x180198cda`
- `msvcrt!_wtoi` at `0x180198d1b`
- `msvcrt!_wtoi` at `0x180198d5c`
- `msvcrt!_wtoi` at `0x180198dd6`

## string_xrefs

- `0x180198bb2`: `AllowDiskHealthModelUpdates`
- `0x180198c34`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x180198c75`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x180198cb6`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x180198cf7`: `ConfigStorageSenseGlobalCadence`
- `0x180198d38`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x180198db2`: `RemovableDiskDenyWriteAccess`
- `0x180198df3`: `WPDDevicesDenyReadAccessPerDevice`
- `0x180198e2c`: `WPDDevicesDenyWriteAccessPerDevice`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Storage02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r14d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-170h] BYREF
  WmiRequestHandlerAdd *v11; // [rsp+50h] [rbp-168h] BYREF
  _QWORD v12[5]; // [rsp+58h] [rbp-160h] BYREF
  char v13; // [rsp+80h] [rbp-138h]
  int v14; // [rsp+88h] [rbp-130h] BYREF
  char v15; // [rsp+8Ch] [rbp-12Ch]
  _BYTE v16[16]; // [rsp+90h] [rbp-128h] BYREF
  _DWORD v17[4]; // [rsp+A0h] [rbp-118h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-108h] BYREF
  int v19; // [rsp+110h] [rbp-A8h]
  char v20; // [rsp+114h] [rbp-A4h]
  int v21; // [rsp+118h] [rbp-A0h]
  char v22; // [rsp+11Ch] [rbp-9Ch]
  int v23; // [rsp+120h] [rbp-98h]
  char v24; // [rsp+124h] [rbp-94h]
  int v25; // [rsp+128h] [rbp-90h]
  char v26; // [rsp+12Ch] [rbp-8Ch]
  int v27; // [rsp+130h] [rbp-88h]
  char v28; // [rsp+134h] [rbp-84h]
  int v29; // [rsp+138h] [rbp-80h]
  char v30; // [rsp+13Ch] [rbp-7Ch]
  int v31; // [rsp+140h] [rbp-78h]
  char v32; // [rsp+144h] [rbp-74h]
  int v33; // [rsp+158h] [rbp-60h]
  char v34; // [rsp+15Ch] [rbp-5Ch]

  memset_0(&instance, 0, 0xD0u);
  String = 0;
  v14 = 0;
  v15 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v14;
  v12[2] = "MDM_Policy_Result01_Storage02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v5 = v17;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18033628C,
      v16,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v12, v4);
  v11 = 0;
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_Storage02_NodeList,
         0xDu,
         2,
         &v11);
  if ( !v6 )
  {
    v12[4] = &v11;
    v13 = 1;
    v7 = v11;
    if ( v11 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v6 )
      {
        if ( v11 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v11 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Storage02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_71;
            }
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
                    L"Storage",
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
                      L"AllowDiskHealthModelUpdates",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowStorageSenseGlobal",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowStorageSenseTemporaryFilesCleanup",
                      &String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseCloudContentDehydrationThreshold",
                      &String)
                && String )
              {
                v25 = _wtoi(String);
                v26 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseDownloadsCleanupThreshold",
                      &String)
                && String )
              {
                v27 = _wtoi(String);
                v28 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseGlobalCadence",
                      &String)
                && String )
              {
                v29 = _wtoi(String);
                v30 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigStorageSenseRecycleBinCleanupThreshold",
                      &String)
                && String )
              {
                v31 = _wtoi(String);
                v32 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"EnhancedStorageDevices",
                      &String)
                && String )
              {
                MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RemovableDiskDenyWriteAccess",
                      &String)
                && String )
              {
                v33 = _wtoi(String);
                v34 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"WPDDevicesDenyReadAccessPerDevice",
                      &String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
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
          if ( v11 )
          {
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
    }
  }
LABEL_71:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "EnumerateInstancesEnd", v6);
  v14 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180342C0B,
      v16,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v14);
  return v6;
}

```

## disassembly

```asm
0x1801988c4  mov     [rsp+arg_8], rbx
0x1801988c9  mov     [rsp+arg_10], rsi
0x1801988ce  push    rdi
0x1801988cf  push    r12
0x1801988d1  push    r13
0x1801988d3  push    r14
0x1801988d5  push    r15
0x1801988d7  sub     rsp, 190h
0x1801988de  mov     rax, cs:__security_cookie
0x1801988e5  xor     rax, rsp
0x1801988e8  mov     [rsp+1B8h+var_38], rax
0x1801988f0  mov     r13b, dl
0x1801988f3  mov     r12, rcx
0x1801988f6  xor     edx, edx; Val
0x1801988f8  mov     r8d, 0D0h; Size
0x1801988fe  lea     rcx, [rsp+1B8h+instance]; void *
0x180198906  call    memset_0
0x18019890b  xor     edi, edi
0x18019890d  mov     [rsp+1B8h+var_178], dil
0x180198912  mov     [rsp+1B8h+String], rdi
0x180198917  mov     [rsp+1B8h+var_130], edi
0x18019891e  mov     [rsp+1B8h+var_12C], dil
0x180198926  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18019892d  mov     [rsp+1B8h+var_160], rax
0x180198932  lea     rax, [rsp+1B8h+var_130]
0x18019893a  mov     [rsp+1B8h+var_158], rax
0x18019893f  lea     rax, aMdmPolicyResul_127; "MDM_Policy_Result01_Storage02"
0x180198946  mov     [rsp+1B8h+var_150], rax
0x18019894b  lea     rcx, [rsp+1B8h+var_130]
0x180198953  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180198958  mov     eax, cs:dword_180380B68
0x18019895e  cmp     eax, 5
0x180198961  jbe     short loc_1801989D3
0x180198963  mov     rdx, 200000000000h
0x18019896d  lea     rcx, dword_180380B68
0x180198974  call    _tlgKeywordOn
0x180198979  test    al, al
0x18019897b  jz      short loc_1801989D3
0x18019897d  cmp     [rsp+1B8h+var_12C], dil
0x180198985  jz      short loc_1801989B5
0x180198987  cmp     [rsp+1B8h+var_118], edi
0x18019898e  jnz     short loc_1801989AB
0x180198990  cmp     [rsp+1B8h+var_114], edi
0x180198997  jnz     short loc_1801989AB
0x180198999  cmp     [rsp+1B8h+var_110], edi
0x1801989a0  jnz     short loc_1801989AB
0x1801989a2  cmp     [rsp+1B8h+var_10C], edi
0x1801989a9  jz      short loc_1801989B5
0x1801989ab  lea     r9, [rsp+1B8h+var_118]
0x1801989b3  jmp     short loc_1801989B8
0x1801989b5  mov     r9, rdi
0x1801989b8  lea     r8, [rsp+1B8h+var_128]
0x1801989c0  lea     rdx, dword_18033628C
0x1801989c7  lea     rcx, dword_180380B68
0x1801989ce  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801989d3  lea     rcx, [rsp+1B8h+var_160]; this
0x1801989d8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1801989dd  nop
0x1801989de  mov     [rsp+1B8h+var_168], rdi
0x1801989e3  lea     rax, [rsp+1B8h+var_168]
0x1801989e8  mov     [rsp+1B8h+var_188], rax
0x1801989ed  mov     [rsp+1B8h+var_190], 2
0x1801989f5  mov     [rsp+1B8h+var_198], 0Dh
0x1801989fd  lea     r9, ?MDM_Policy_Result01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Storage02_NodeList
0x180198a04  xor     r8d, r8d
0x180198a07  xor     edx, edx
0x180198a09  mov     rcx, r12
0x180198a0c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180198a11  mov     r14d, eax
0x180198a14  test    eax, eax
0x180198a16  jz      short loc_180198A1D
0x180198a18  jmp     loc_180198EBF
0x180198a1d  lea     rbx, [rsp+1B8h+var_168]
0x180198a22  mov     [rsp+1B8h+var_140], rbx
0x180198a27  mov     r15d, 1
0x180198a2d  mov     [rsp+1B8h+var_138], r15b
0x180198a35  mov     rsi, [rsp+1B8h+var_168]
0x180198a3a  test    rsi, rsi
0x180198a3d  jnz     short loc_180198A47
0x180198a3f  mov     r14d, r15d
0x180198a42  jmp     loc_180198EBF
0x180198a47  mov     rax, [rsi]
0x180198a4a  mov     rcx, rsi
0x180198a4d  mov     rax, [rax+10h]
0x180198a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198a56  mov     r14d, eax
0x180198a59  test    eax, eax
0x180198a5b  jz      short loc_180198A7B
0x180198a5d  mov     rcx, [rsp+1B8h+var_168]
0x180198a62  test    rcx, rcx
0x180198a65  jz      short loc_180198A76
0x180198a67  mov     rax, [rcx]
0x180198a6a  mov     edx, r15d
0x180198a6d  mov     rax, [rax]
0x180198a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198a75  nop
0x180198a76  jmp     loc_180198EBF
0x180198a7b  mov     rax, [rsi]
0x180198a7e  mov     rcx, rsi
0x180198a81  mov     rax, [rax+8]
0x180198a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198a8a  mov     r14d, eax
0x180198a8d  test    eax, eax
0x180198a8f  jz      short loc_180198AAF
0x180198a91  mov     rcx, [rsp+1B8h+var_168]
0x180198a96  test    rcx, rcx
0x180198a99  jz      short loc_180198AAA
0x180198a9b  mov     rax, [rcx]
0x180198a9e  mov     edx, r15d
0x180198aa1  mov     rax, [rax]
0x180198aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198aa9  nop
0x180198aaa  jmp     loc_180198EBF
0x180198aaf  mov     r15d, edi
0x180198ab2  mov     rax, [rsi+108h]
0x180198ab9  sub     rax, [rsi+100h]
0x180198ac0  sar     rax, 4
0x180198ac4  cmp     r15d, eax
0x180198ac7  jnb     loc_180198E87
0x180198acd  lea     r8, [rsp+1B8h+instance]; instance
0x180198ad5  lea     rdx, MDM_Policy_Result01_Storage02_rtti; classDecl
0x180198adc  mov     rcx, r12; context
0x180198adf  call    MI_Context_ConstructInstance
0x180198ae4  mov     r14d, eax
0x180198ae7  test    eax, eax
0x180198ae9  jz      short loc_180198B0B
0x180198aeb  mov     rcx, [rbx]
0x180198aee  test    rcx, rcx
0x180198af1  jz      short loc_180198B06
0x180198af3  mov     rax, [rcx]
0x180198af6  mov     edx, 1
0x180198afb  mov     rax, [rax]
0x180198afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b03  mov     [rbx], rdi
0x180198b06  jmp     loc_180198EBF
0x180198b0b  mov     [rsp+1B8h+var_178], 1
0x180198b10  mov     rax, [rsi]
0x180198b13  lea     r9, [rsp+1B8h+String]
0x180198b18  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x180198b1f  mov     edx, r15d
0x180198b22  mov     rcx, rsi
0x180198b25  mov     rax, [rax+18h]
0x180198b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b2e  test    eax, eax
0x180198b30  jnz     short loc_180198B49
0x180198b32  mov     rdx, [rsp+1B8h+String]
0x180198b37  test    rdx, rdx
0x180198b3a  jz      short loc_180198B49
0x180198b3c  lea     rcx, [rsp+1B8h+instance]
0x180198b44  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180198b49  mov     rax, [rsi]
0x180198b4c  lea     r9, [rsp+1B8h+String]
0x180198b51  lea     r8, aStorage; "Storage"
0x180198b58  mov     edx, r15d
0x180198b5b  mov     rcx, rsi
0x180198b5e  mov     rax, [rax+18h]
0x180198b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b67  test    eax, eax
0x180198b69  jnz     short loc_180198B82
0x180198b6b  mov     rdx, [rsp+1B8h+String]
0x180198b70  test    rdx, rdx
0x180198b73  jz      short loc_180198B82
0x180198b75  lea     rcx, [rsp+1B8h+instance]
0x180198b7d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180198b82  cmp     r13b, 1
0x180198b86  jnz     short loc_180198BAA
0x180198b88  lea     rdx, [rsp+1B8h+instance]
0x180198b90  mov     rcx, r12; self
0x180198b93  call    MI_Instance_Destruct
0x180198b98  lea     rcx, [rsp+1B8h+instance]; self
0x180198ba0  call    MI_Instance_Destruct
0x180198ba5  jmp     loc_180198E7A
0x180198baa  mov     rax, [rsi]
0x180198bad  lea     r9, [rsp+1B8h+String]
0x180198bb2  lea     r8, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x180198bb9  mov     edx, r15d
0x180198bbc  mov     rcx, rsi
0x180198bbf  mov     rax, [rax+18h]
0x180198bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198bc8  test    eax, eax
0x180198bca  jnz     short loc_180198BEB
0x180198bcc  mov     rcx, [rsp+1B8h+String]; String
0x180198bd1  test    rcx, rcx
0x180198bd4  jz      short loc_180198BEB
0x180198bd6  call    cs:__imp__wtoi
0x180198bdc  mov     [rsp+1B8h+var_A8], eax
0x180198be3  mov     [rsp+1B8h+var_A4], 1
0x180198beb  mov     rax, [rsi]
0x180198bee  lea     r9, [rsp+1B8h+String]
0x180198bf3  lea     r8, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x180198bfa  mov     edx, r15d
0x180198bfd  mov     rcx, rsi
0x180198c00  mov     rax, [rax+18h]
0x180198c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198c09  test    eax, eax
0x180198c0b  jnz     short loc_180198C2C
0x180198c0d  mov     rcx, [rsp+1B8h+String]; String
0x180198c12  test    rcx, rcx
0x180198c15  jz      short loc_180198C2C
0x180198c17  call    cs:__imp__wtoi
0x180198c1d  mov     [rsp+1B8h+var_A0], eax
0x180198c24  mov     [rsp+1B8h+var_9C], 1
0x180198c2c  mov     rax, [rsi]
0x180198c2f  lea     r9, [rsp+1B8h+String]
0x180198c34  lea     r8, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x180198c3b  mov     edx, r15d
0x180198c3e  mov     rcx, rsi
0x180198c41  mov     rax, [rax+18h]
0x180198c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198c4a  test    eax, eax
0x180198c4c  jnz     short loc_180198C6D
0x180198c4e  mov     rcx, [rsp+1B8h+String]; String
0x180198c53  test    rcx, rcx
0x180198c56  jz      short loc_180198C6D
0x180198c58  call    cs:__imp__wtoi
0x180198c5e  mov     [rsp+1B8h+var_98], eax
0x180198c65  mov     [rsp+1B8h+var_94], 1
0x180198c6d  mov     rax, [rsi]
0x180198c70  lea     r9, [rsp+1B8h+String]
0x180198c75  lea     r8, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x180198c7c  mov     edx, r15d
0x180198c7f  mov     rcx, rsi
0x180198c82  mov     rax, [rax+18h]
0x180198c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198c8b  test    eax, eax
0x180198c8d  jnz     short loc_180198CAE
0x180198c8f  mov     rcx, [rsp+1B8h+String]; String
0x180198c94  test    rcx, rcx
0x180198c97  jz      short loc_180198CAE
0x180198c99  call    cs:__imp__wtoi
0x180198c9f  mov     [rsp+1B8h+var_90], eax
0x180198ca6  mov     [rsp+1B8h+var_8C], 1
0x180198cae  mov     rax, [rsi]
0x180198cb1  lea     r9, [rsp+1B8h+String]
0x180198cb6  lea     r8, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x180198cbd  mov     edx, r15d
0x180198cc0  mov     rcx, rsi
0x180198cc3  mov     rax, [rax+18h]
0x180198cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198ccc  test    eax, eax
0x180198cce  jnz     short loc_180198CEF
0x180198cd0  mov     rcx, [rsp+1B8h+String]; String
0x180198cd5  test    rcx, rcx
0x180198cd8  jz      short loc_180198CEF
0x180198cda  call    cs:__imp__wtoi
0x180198ce0  mov     [rsp+1B8h+var_88], eax
0x180198ce7  mov     [rsp+1B8h+var_84], 1
0x180198cef  mov     rax, [rsi]
0x180198cf2  lea     r9, [rsp+1B8h+String]
0x180198cf7  lea     r8, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x180198cfe  mov     edx, r15d
0x180198d01  mov     rcx, rsi
0x180198d04  mov     rax, [rax+18h]
0x180198d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198d0d  test    eax, eax
0x180198d0f  jnz     short loc_180198D30
0x180198d11  mov     rcx, [rsp+1B8h+String]; String
0x180198d16  test    rcx, rcx
0x180198d19  jz      short loc_180198D30
0x180198d1b  call    cs:__imp__wtoi
0x180198d21  mov     [rsp+1B8h+var_80], eax
0x180198d28  mov     [rsp+1B8h+var_7C], 1
0x180198d30  mov     rax, [rsi]
0x180198d33  lea     r9, [rsp+1B8h+String]
0x180198d38  lea     r8, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x180198d3f  mov     edx, r15d
0x180198d42  mov     rcx, rsi
0x180198d45  mov     rax, [rax+18h]
0x180198d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198d4e  test    eax, eax
0x180198d50  jnz     short loc_180198D71
0x180198d52  mov     rcx, [rsp+1B8h+String]; String
0x180198d57  test    rcx, rcx
0x180198d5a  jz      short loc_180198D71
0x180198d5c  call    cs:__imp__wtoi
0x180198d62  mov     [rsp+1B8h+var_78], eax
0x180198d69  mov     [rsp+1B8h+var_74], 1
0x180198d71  mov     rax, [rsi]
0x180198d74  lea     r9, [rsp+1B8h+String]
0x180198d79  lea     r8, aEnhancedstorag; "EnhancedStorageDevices"
0x180198d80  mov     edx, r15d
0x180198d83  mov     rcx, rsi
0x180198d86  mov     rax, [rax+18h]
0x180198d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198d8f  test    eax, eax
0x180198d91  jnz     short loc_180198DAA
0x180198d93  mov     rdx, [rsp+1B8h+String]
0x180198d98  test    rdx, rdx
0x180198d9b  jz      short loc_180198DAA
0x180198d9d  lea     rcx, [rsp+1B8h+instance]
0x180198da5  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180198daa  mov     rax, [rsi]
0x180198dad  lea     r9, [rsp+1B8h+String]
0x180198db2  lea     r8, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x180198db9  mov     edx, r15d
0x180198dbc  mov     rcx, rsi
0x180198dbf  mov     rax, [rax+18h]
0x180198dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198dc8  test    eax, eax
0x180198dca  jnz     short loc_180198DEB
  ... truncated ...
```
