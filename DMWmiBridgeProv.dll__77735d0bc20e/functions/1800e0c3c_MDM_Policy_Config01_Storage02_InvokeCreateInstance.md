# MDM_Policy_Config01_Storage02_InvokeCreateInstance

- ea: `0x1800e0c3c`
- end: `0x1800e125b`
- name: `MDM_Policy_Config01_Storage02_InvokeCreateInstance`
- size: `1567`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e0b40`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800e0c3c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800e0e05`: `AllowDiskHealthModelUpdates`
- `0x1800e0e7f`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x1800e0ebc`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x1800e0efc`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1800e0f3c`: `ConfigStorageSenseGlobalCadence`
- `0x1800e0f7c`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x1800e0ffc`: `RemovableDiskDenyWriteAccess`
- `0x1800e103c`: `WPDDevicesDenyReadAccessPerDevice`
- `0x1800e107c`: `WPDDevicesDenyWriteAccessPerDevice`
- `0x1800e0d65`: `CreateInstanceStart`
- `0x1800e11c2`: `CreateInstanceEnd`
- `0x1800e0cac`: `MDM_Policy_Config01_Storage02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Storage02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+48h] [rbp-160h] BYREF
  _QWORD v9[5]; // [rsp+50h] [rbp-158h] BYREF
  char v10; // [rsp+78h] [rbp-130h]
  int v11; // [rsp+80h] [rbp-128h] BYREF
  char v12; // [rsp+84h] [rbp-124h]
  _BYTE v13[16]; // [rsp+88h] [rbp-120h] BYREF
  _DWORD v14[6]; // [rsp+98h] [rbp-110h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-F8h] BYREF

  memset_0(&instance, 0, 0xD0u);
  v11 = 0;
  v12 = 0;
  v9[0] = &TelemetryEventWriter::`vftable';
  v9[1] = &v11;
  v9[2] = "MDM_Policy_Config01_Storage02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033FB2D,
      v13,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || !LOBYTE(a2[1].nameSpace) )
  {
    inserted = 4;
    goto LABEL_73;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v9,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_Storage02_NodeList,
               0xDu,
               4,
               &v8);
  if ( !inserted )
  {
    v9[4] = &v8;
    v10 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_73;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Storage02_NodeList, 0xDu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDiskHealthModelUpdates", (LONG *)a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
LABEL_68:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_73;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowStorageSenseGlobal", (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowStorageSenseTemporaryFilesCleanup",
                   (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigStorageSenseCloudContentDehydrationThreshold",
                   (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigStorageSenseDownloadsCleanupThreshold",
                   (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigStorageSenseGlobalCadence",
                   (LONG *)&a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigStorageSenseRecycleBinCleanupThreshold",
                   (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( LOBYTE(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnhancedStorageDevices", (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"RemovableDiskDenyWriteAccess",
                   (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( LOBYTE(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"WPDDevicesDenyReadAccessPerDevice",
                   (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( LOBYTE(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"WPDDevicesDenyWriteAccessPerDevice", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_73;
      goto LABEL_68;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_73;
      goto LABEL_68;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Storage02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_73;
      goto LABEL_68;
    }
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_73:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "CreateInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18034B179,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return inserted;
}

```

## disassembly

```asm
0x1800e0c3c  mov     [rsp+arg_10], rsi
0x1800e0c41  mov     [rsp+arg_18], rdi
0x1800e0c46  push    r12
0x1800e0c48  push    r14
0x1800e0c4a  push    r15
0x1800e0c4c  sub     rsp, 190h
0x1800e0c53  mov     rax, cs:__security_cookie
0x1800e0c5a  xor     rax, rsp
0x1800e0c5d  mov     [rsp+1A8h+var_28], rax
0x1800e0c65  mov     rsi, rdx
0x1800e0c68  mov     r15, rcx
0x1800e0c6b  xor     edx, edx; Val
0x1800e0c6d  mov     r8d, 0D0h; Size
0x1800e0c73  lea     rcx, [rsp+1A8h+instance]; void *
0x1800e0c7b  call    memset_0
0x1800e0c80  mov     [rsp+1A8h+var_128], 0
0x1800e0c8b  mov     [rsp+1A8h+var_124], 0
0x1800e0c93  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e0c9a  mov     [rsp+1A8h+var_158], rax
0x1800e0c9f  lea     rax, [rsp+1A8h+var_128]
0x1800e0ca7  mov     [rsp+1A8h+var_150], rax
0x1800e0cac  lea     rax, aMdmPolicyConfi_172; "MDM_Policy_Config01_Storage02"
0x1800e0cb3  mov     [rsp+1A8h+var_148], rax
0x1800e0cb8  lea     rcx, [rsp+1A8h+var_128]
0x1800e0cc0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e0cc5  mov     eax, cs:dword_180380B68
0x1800e0ccb  cmp     eax, 5
0x1800e0cce  jbe     short loc_1800E0D44
0x1800e0cd0  mov     rdx, 200000000000h
0x1800e0cda  lea     rcx, dword_180380B68
0x1800e0ce1  call    _tlgKeywordOn
0x1800e0ce6  test    al, al
0x1800e0ce8  jz      short loc_1800E0D44
0x1800e0cea  cmp     [rsp+1A8h+var_124], 0
0x1800e0cf2  jz      short loc_1800E0D26
0x1800e0cf4  cmp     [rsp+1A8h+var_110], 0
0x1800e0cfc  jnz     short loc_1800E0D1C
0x1800e0cfe  cmp     [rsp+1A8h+var_10C], 0
0x1800e0d06  jnz     short loc_1800E0D1C
0x1800e0d08  cmp     [rsp+1A8h+var_108], 0
0x1800e0d10  jnz     short loc_1800E0D1C
0x1800e0d12  cmp     [rsp+1A8h+var_104], 0
0x1800e0d1a  jz      short loc_1800E0D26
0x1800e0d1c  lea     r9, [rsp+1A8h+var_110]
0x1800e0d24  jmp     short loc_1800E0D29
0x1800e0d26  xor     r9d, r9d
0x1800e0d29  lea     r8, [rsp+1A8h+var_120]
0x1800e0d31  lea     rdx, byte_18033FB2D
0x1800e0d38  lea     rcx, dword_180380B68
0x1800e0d3f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e0d44  cmp     byte ptr [rsi+48h], 0
0x1800e0d48  jz      loc_1800E11BA
0x1800e0d4e  mov     [rsp+1A8h+var_168], 0
0x1800e0d53  cmp     byte ptr [rsi+58h], 0
0x1800e0d57  jz      loc_1800E11BA
0x1800e0d5d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e0d61  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e0d65  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800e0d6c  lea     rcx, [rsp+1A8h+var_158]; this
0x1800e0d71  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e0d76  nop
0x1800e0d77  mov     [rsp+1A8h+var_160], 0
0x1800e0d80  lea     rax, [rsp+1A8h+var_160]
0x1800e0d85  mov     [rsp+1A8h+var_178], rax
0x1800e0d8a  mov     [rsp+1A8h+var_180], 4
0x1800e0d92  mov     [rsp+1A8h+var_188], 0Dh
0x1800e0d9a  lea     r9, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Storage02_NodeList
0x1800e0da1  mov     r8, [rsi+40h]
0x1800e0da5  mov     rdx, [rsi+50h]
0x1800e0da9  mov     rcx, r15
0x1800e0dac  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e0db1  mov     edi, eax
0x1800e0db3  test    eax, eax
0x1800e0db5  jz      short loc_1800E0DBC
0x1800e0db7  jmp     loc_1800E11BF
0x1800e0dbc  lea     rax, [rsp+1A8h+var_160]
0x1800e0dc1  mov     [rsp+1A8h+var_138], rax
0x1800e0dc6  mov     r12d, 1
0x1800e0dcc  mov     [rsp+1A8h+var_130], r12b
0x1800e0dd1  mov     r14, [rsp+1A8h+var_160]
0x1800e0dd6  test    r14, r14
0x1800e0dd9  jnz     short loc_1800E0DE3
0x1800e0ddb  mov     edi, r12d
0x1800e0dde  jmp     loc_1800E11BF
0x1800e0de3  mov     r9d, 0Dh; unsigned int
0x1800e0de9  lea     r8, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e0df0  mov     rdx, rsi; struct _MI_Instance *
0x1800e0df3  mov     rcx, r14; this
0x1800e0df6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e0dfb  lea     r8, [rsi+60h]; void *
0x1800e0dff  cmp     [r8+4], r12b
0x1800e0e03  jnz     short loc_1800E0E38
0x1800e0e05  lea     rdx, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x1800e0e0c  mov     rcx, r14; this
0x1800e0e0f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0e14  mov     edi, eax
0x1800e0e16  test    eax, eax
0x1800e0e18  jz      short loc_1800E0E38
0x1800e0e1a  mov     rcx, [rsp+1A8h+var_160]
0x1800e0e1f  test    rcx, rcx
0x1800e0e22  jz      short loc_1800E0E33
0x1800e0e24  mov     rax, [rcx]
0x1800e0e27  mov     edx, r12d
0x1800e0e2a  mov     rax, [rax]
0x1800e0e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e32  nop
0x1800e0e33  jmp     loc_1800E11BF
0x1800e0e38  lea     r8, [rsi+68h]; void *
0x1800e0e3c  cmp     [r8+4], r12b
0x1800e0e40  jnz     short loc_1800E0E75
0x1800e0e42  lea     rdx, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x1800e0e49  mov     rcx, r14; this
0x1800e0e4c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0e51  mov     edi, eax
0x1800e0e53  test    eax, eax
0x1800e0e55  jz      short loc_1800E0E75
0x1800e0e57  mov     rcx, [rsp+1A8h+var_160]
0x1800e0e5c  test    rcx, rcx
0x1800e0e5f  jz      short loc_1800E0E70
0x1800e0e61  mov     rax, [rcx]
0x1800e0e64  mov     edx, r12d
0x1800e0e67  mov     rax, [rax]
0x1800e0e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e6f  nop
0x1800e0e70  jmp     loc_1800E11BF
0x1800e0e75  lea     r8, [rsi+70h]; void *
0x1800e0e79  cmp     [r8+4], r12b
0x1800e0e7d  jnz     short loc_1800E0EB2
0x1800e0e7f  lea     rdx, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x1800e0e86  mov     rcx, r14; this
0x1800e0e89  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0e8e  mov     edi, eax
0x1800e0e90  test    eax, eax
0x1800e0e92  jz      short loc_1800E0EB2
0x1800e0e94  mov     rcx, [rsp+1A8h+var_160]
0x1800e0e99  test    rcx, rcx
0x1800e0e9c  jz      short loc_1800E0EAD
0x1800e0e9e  mov     rax, [rcx]
0x1800e0ea1  mov     edx, r12d
0x1800e0ea4  mov     rax, [rax]
0x1800e0ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0eac  nop
0x1800e0ead  jmp     loc_1800E11BF
0x1800e0eb2  lea     r8, [rsi+78h]; void *
0x1800e0eb6  cmp     [r8+4], r12b
0x1800e0eba  jnz     short loc_1800E0EEF
0x1800e0ebc  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x1800e0ec3  mov     rcx, r14; this
0x1800e0ec6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0ecb  mov     edi, eax
0x1800e0ecd  test    eax, eax
0x1800e0ecf  jz      short loc_1800E0EEF
0x1800e0ed1  mov     rcx, [rsp+1A8h+var_160]
0x1800e0ed6  test    rcx, rcx
0x1800e0ed9  jz      short loc_1800E0EEA
0x1800e0edb  mov     rax, [rcx]
0x1800e0ede  mov     edx, r12d
0x1800e0ee1  mov     rax, [rax]
0x1800e0ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0ee9  nop
0x1800e0eea  jmp     loc_1800E11BF
0x1800e0eef  lea     r8, [rsi+80h]; void *
0x1800e0ef6  cmp     [r8+4], r12b
0x1800e0efa  jnz     short loc_1800E0F2F
0x1800e0efc  lea     rdx, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x1800e0f03  mov     rcx, r14; this
0x1800e0f06  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0f0b  mov     edi, eax
0x1800e0f0d  test    eax, eax
0x1800e0f0f  jz      short loc_1800E0F2F
0x1800e0f11  mov     rcx, [rsp+1A8h+var_160]
0x1800e0f16  test    rcx, rcx
0x1800e0f19  jz      short loc_1800E0F2A
0x1800e0f1b  mov     rax, [rcx]
0x1800e0f1e  mov     edx, r12d
0x1800e0f21  mov     rax, [rax]
0x1800e0f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0f29  nop
0x1800e0f2a  jmp     loc_1800E11BF
0x1800e0f2f  lea     r8, [rsi+88h]; void *
0x1800e0f36  cmp     [r8+4], r12b
0x1800e0f3a  jnz     short loc_1800E0F6F
0x1800e0f3c  lea     rdx, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x1800e0f43  mov     rcx, r14; this
0x1800e0f46  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0f4b  mov     edi, eax
0x1800e0f4d  test    eax, eax
0x1800e0f4f  jz      short loc_1800E0F6F
0x1800e0f51  mov     rcx, [rsp+1A8h+var_160]
0x1800e0f56  test    rcx, rcx
0x1800e0f59  jz      short loc_1800E0F6A
0x1800e0f5b  mov     rax, [rcx]
0x1800e0f5e  mov     edx, r12d
0x1800e0f61  mov     rax, [rax]
0x1800e0f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0f69  nop
0x1800e0f6a  jmp     loc_1800E11BF
0x1800e0f6f  lea     r8, [rsi+90h]; void *
0x1800e0f76  cmp     [r8+4], r12b
0x1800e0f7a  jnz     short loc_1800E0FAF
0x1800e0f7c  lea     rdx, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x1800e0f83  mov     rcx, r14; this
0x1800e0f86  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0f8b  mov     edi, eax
0x1800e0f8d  test    eax, eax
0x1800e0f8f  jz      short loc_1800E0FAF
0x1800e0f91  mov     rcx, [rsp+1A8h+var_160]
0x1800e0f96  test    rcx, rcx
0x1800e0f99  jz      short loc_1800E0FAA
0x1800e0f9b  mov     rax, [rcx]
0x1800e0f9e  mov     edx, r12d
0x1800e0fa1  mov     rax, [rax]
0x1800e0fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0fa9  nop
0x1800e0faa  jmp     loc_1800E11BF
0x1800e0faf  lea     r8, [rsi+98h]; void *
0x1800e0fb6  cmp     [r8+8], r12b
0x1800e0fba  jnz     short loc_1800E0FEF
0x1800e0fbc  lea     rdx, aEnhancedstorag; "EnhancedStorageDevices"
0x1800e0fc3  mov     rcx, r14; this
0x1800e0fc6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0fcb  mov     edi, eax
0x1800e0fcd  test    eax, eax
0x1800e0fcf  jz      short loc_1800E0FEF
0x1800e0fd1  mov     rcx, [rsp+1A8h+var_160]
0x1800e0fd6  test    rcx, rcx
0x1800e0fd9  jz      short loc_1800E0FEA
0x1800e0fdb  mov     rax, [rcx]
0x1800e0fde  mov     edx, r12d
0x1800e0fe1  mov     rax, [rax]
0x1800e0fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0fe9  nop
0x1800e0fea  jmp     loc_1800E11BF
0x1800e0fef  lea     r8, [rsi+0A8h]; void *
0x1800e0ff6  cmp     [r8+4], r12b
0x1800e0ffa  jnz     short loc_1800E102F
0x1800e0ffc  lea     rdx, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x1800e1003  mov     rcx, r14; this
0x1800e1006  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e100b  mov     edi, eax
0x1800e100d  test    eax, eax
0x1800e100f  jz      short loc_1800E102F
0x1800e1011  mov     rcx, [rsp+1A8h+var_160]
0x1800e1016  test    rcx, rcx
0x1800e1019  jz      short loc_1800E102A
0x1800e101b  mov     rax, [rcx]
0x1800e101e  mov     edx, r12d
0x1800e1021  mov     rax, [rax]
0x1800e1024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1029  nop
0x1800e102a  jmp     loc_1800E11BF
0x1800e102f  lea     r8, [rsi+0B0h]; void *
0x1800e1036  cmp     [r8+8], r12b
0x1800e103a  jnz     short loc_1800E106F
0x1800e103c  lea     rdx, aWpddevicesdeny_1; "WPDDevicesDenyReadAccessPerDevice"
0x1800e1043  mov     rcx, r14; this
0x1800e1046  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e104b  mov     edi, eax
0x1800e104d  test    eax, eax
0x1800e104f  jz      short loc_1800E106F
0x1800e1051  mov     rcx, [rsp+1A8h+var_160]
0x1800e1056  test    rcx, rcx
0x1800e1059  jz      short loc_1800E106A
0x1800e105b  mov     rax, [rcx]
0x1800e105e  mov     edx, r12d
0x1800e1061  mov     rax, [rax]
0x1800e1064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1069  nop
0x1800e106a  jmp     loc_1800E11BF
0x1800e106f  lea     r8, [rsi+0C0h]; void *
0x1800e1076  cmp     [r8+8], r12b
0x1800e107a  jnz     short loc_1800E10AF
0x1800e107c  lea     rdx, aWpddevicesdeny_2; "WPDDevicesDenyWriteAccessPerDevice"
0x1800e1083  mov     rcx, r14; this
0x1800e1086  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e108b  mov     edi, eax
0x1800e108d  test    eax, eax
0x1800e108f  jz      short loc_1800E10AF
0x1800e1091  mov     rcx, [rsp+1A8h+var_160]
0x1800e1096  test    rcx, rcx
0x1800e1099  jz      short loc_1800E10AA
0x1800e109b  mov     rax, [rcx]
0x1800e109e  mov     edx, r12d
0x1800e10a1  mov     rax, [rax]
0x1800e10a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e10a9  nop
0x1800e10aa  jmp     loc_1800E11BF
0x1800e10af  mov     rax, [r14]
0x1800e10b2  mov     rcx, r14
0x1800e10b5  mov     rax, [rax+10h]
0x1800e10b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e10be  mov     edi, eax
0x1800e10c0  test    eax, eax
0x1800e10c2  jz      short loc_1800E10E2
0x1800e10c4  mov     rcx, [rsp+1A8h+var_160]
0x1800e10c9  test    rcx, rcx
0x1800e10cc  jz      short loc_1800E10DD
0x1800e10ce  mov     rax, [rcx]
0x1800e10d1  mov     edx, r12d
0x1800e10d4  mov     rax, [rax]
  ... truncated ...
```
