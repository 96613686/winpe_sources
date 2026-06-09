# MDM_Policy_Config01_Storage02_InvokeCreateInstance

- ea: `0x1800e029c`
- end: `0x1800e08bc`
- name: `MDM_Policy_Config01_Storage02_InvokeCreateInstance`
- size: `1568`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e01e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800e029c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1800e0465`: `AllowDiskHealthModelUpdates`
- `0x1800e04df`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x1800e051c`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x1800e055c`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1800e059c`: `ConfigStorageSenseGlobalCadence`
- `0x1800e05dc`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x1800e065c`: `RemovableDiskDenyWriteAccess`
- `0x1800e069c`: `WPDDevicesDenyReadAccessPerDevice`
- `0x1800e06dc`: `WPDDevicesDenyWriteAccessPerDevice`
- `0x1800e03c5`: `CreateInstanceStart`
- `0x1800e0822`: `CreateInstanceEnd`
- `0x1800e030c`: `MDM_Policy_Config01_Storage02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Storage02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_73;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v9,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = (unsigned int)CreateRequestHandlerInstance(
                             self,
                             a2[1].serverName,
                             a2[1].ft,
                             &MDM_Policy_Config01_Storage02_NodeList,
                             13,
                             4,
                             &v8);
  if ( inserted == MI_RESULT_OK )
  {
    v9[4] = &v8;
    v10 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = MI_RESULT_FAILED;
      goto LABEL_73;
    }
    WmiRequestHandler::SetRequestMIInstance(v8, a2, (struct WmiNodeInfo *)&MDM_Policy_Config01_Storage02_NodeList, 0xDu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDiskHealthModelUpdates", a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowStorageSenseGlobal", &a2[1].reserved[1]);
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
                   &a2[1].reserved[2]);
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
                   &a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigStorageSenseDownloadsCleanupThreshold", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigStorageSenseGlobalCadence", &a2[2].classDecl);
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
                   &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( LOBYTE(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnhancedStorageDevices", &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"RemovableDiskDenyWriteAccess", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( LOBYTE(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"WPDDevicesDenyReadAccessPerDevice", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    if ( LOBYTE(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"WPDDevicesDenyWriteAccessPerDevice", &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_73;
        goto LABEL_68;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_73;
      goto LABEL_68;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800e029c  mov     [rsp+arg_10], rsi
0x1800e02a1  mov     [rsp+arg_18], rdi
0x1800e02a6  push    r12
0x1800e02a8  push    r14
0x1800e02aa  push    r15
0x1800e02ac  sub     rsp, 190h
0x1800e02b3  mov     rax, cs:__security_cookie
0x1800e02ba  xor     rax, rsp
0x1800e02bd  mov     [rsp+1A8h+var_28], rax
0x1800e02c5  mov     rsi, rdx
0x1800e02c8  mov     r15, rcx
0x1800e02cb  xor     edx, edx; Val
0x1800e02cd  mov     r8d, 0D0h; Size
0x1800e02d3  lea     rcx, [rsp+1A8h+instance]; void *
0x1800e02db  call    memset_0
0x1800e02e0  mov     [rsp+1A8h+var_128], 0
0x1800e02eb  mov     [rsp+1A8h+var_124], 0
0x1800e02f3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e02fa  mov     [rsp+1A8h+var_158], rax
0x1800e02ff  lea     rax, [rsp+1A8h+var_128]
0x1800e0307  mov     [rsp+1A8h+var_150], rax
0x1800e030c  lea     rax, aMdmPolicyConfi_172; "MDM_Policy_Config01_Storage02"
0x1800e0313  mov     [rsp+1A8h+var_148], rax
0x1800e0318  lea     rcx, [rsp+1A8h+var_128]
0x1800e0320  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e0325  mov     eax, cs:dword_180380B68
0x1800e032b  cmp     eax, 5
0x1800e032e  jbe     short loc_1800E03A4
0x1800e0330  mov     rdx, 200000000000h
0x1800e033a  lea     rcx, dword_180380B68
0x1800e0341  call    _tlgKeywordOn
0x1800e0346  test    al, al
0x1800e0348  jz      short loc_1800E03A4
0x1800e034a  cmp     [rsp+1A8h+var_124], 0
0x1800e0352  jz      short loc_1800E0386
0x1800e0354  cmp     [rsp+1A8h+var_110], 0
0x1800e035c  jnz     short loc_1800E037C
0x1800e035e  cmp     [rsp+1A8h+var_10C], 0
0x1800e0366  jnz     short loc_1800E037C
0x1800e0368  cmp     [rsp+1A8h+var_108], 0
0x1800e0370  jnz     short loc_1800E037C
0x1800e0372  cmp     [rsp+1A8h+var_104], 0
0x1800e037a  jz      short loc_1800E0386
0x1800e037c  lea     r9, [rsp+1A8h+var_110]
0x1800e0384  jmp     short loc_1800E0389
0x1800e0386  xor     r9d, r9d
0x1800e0389  lea     r8, [rsp+1A8h+var_120]
0x1800e0391  lea     rdx, byte_18033FB2D
0x1800e0398  lea     rcx, dword_180380B68
0x1800e039f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e03a4  cmp     byte ptr [rsi+48h], 0
0x1800e03a8  jz      loc_1800E081A
0x1800e03ae  mov     [rsp+1A8h+var_168], 0
0x1800e03b3  cmp     byte ptr [rsi+58h], 0
0x1800e03b7  jz      loc_1800E081A
0x1800e03bd  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800e03c1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800e03c5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800e03cc  lea     rcx, [rsp+1A8h+var_158]; this
0x1800e03d1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e03d6  nop
0x1800e03d7  mov     [rsp+1A8h+var_160], 0
0x1800e03e0  lea     rax, [rsp+1A8h+var_160]
0x1800e03e5  mov     [rsp+1A8h+var_178], rax
0x1800e03ea  mov     [rsp+1A8h+var_180], 4
0x1800e03f2  mov     [rsp+1A8h+var_188], 0Dh
0x1800e03fa  lea     r9, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Storage02_NodeList
0x1800e0401  mov     r8, [rsi+40h]
0x1800e0405  mov     rdx, [rsi+50h]
0x1800e0409  mov     rcx, r15
0x1800e040c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e0411  mov     edi, eax
0x1800e0413  test    eax, eax
0x1800e0415  jz      short loc_1800E041C
0x1800e0417  jmp     loc_1800E081F
0x1800e041c  lea     rax, [rsp+1A8h+var_160]
0x1800e0421  mov     [rsp+1A8h+var_138], rax
0x1800e0426  mov     r12d, 1
0x1800e042c  mov     [rsp+1A8h+var_130], r12b
0x1800e0431  mov     r14, [rsp+1A8h+var_160]
0x1800e0436  test    r14, r14
0x1800e0439  jnz     short loc_1800E0443
0x1800e043b  mov     edi, r12d
0x1800e043e  jmp     loc_1800E081F
0x1800e0443  mov     r9d, 0Dh; unsigned int
0x1800e0449  lea     r8, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e0450  mov     rdx, rsi; struct _MI_Instance *
0x1800e0453  mov     rcx, r14; this
0x1800e0456  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e045b  lea     r8, [rsi+60h]; void *
0x1800e045f  cmp     [r8+4], r12b
0x1800e0463  jnz     short loc_1800E0498
0x1800e0465  lea     rdx, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x1800e046c  mov     rcx, r14; this
0x1800e046f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e0474  mov     edi, eax
0x1800e0476  test    eax, eax
0x1800e0478  jz      short loc_1800E0498
0x1800e047a  mov     rcx, [rsp+1A8h+var_160]
0x1800e047f  test    rcx, rcx
0x1800e0482  jz      short loc_1800E0493
0x1800e0484  mov     rax, [rcx]
0x1800e0487  mov     edx, r12d
0x1800e048a  mov     rax, [rax]
0x1800e048d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0492  nop
0x1800e0493  jmp     loc_1800E081F
0x1800e0498  lea     r8, [rsi+68h]; void *
0x1800e049c  cmp     [r8+4], r12b
0x1800e04a0  jnz     short loc_1800E04D5
0x1800e04a2  lea     rdx, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x1800e04a9  mov     rcx, r14; this
0x1800e04ac  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e04b1  mov     edi, eax
0x1800e04b3  test    eax, eax
0x1800e04b5  jz      short loc_1800E04D5
0x1800e04b7  mov     rcx, [rsp+1A8h+var_160]
0x1800e04bc  test    rcx, rcx
0x1800e04bf  jz      short loc_1800E04D0
0x1800e04c1  mov     rax, [rcx]
0x1800e04c4  mov     edx, r12d
0x1800e04c7  mov     rax, [rax]
0x1800e04ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e04cf  nop
0x1800e04d0  jmp     loc_1800E081F
0x1800e04d5  lea     r8, [rsi+70h]; void *
0x1800e04d9  cmp     [r8+4], r12b
0x1800e04dd  jnz     short loc_1800E0512
0x1800e04df  lea     rdx, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x1800e04e6  mov     rcx, r14; this
0x1800e04e9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e04ee  mov     edi, eax
0x1800e04f0  test    eax, eax
0x1800e04f2  jz      short loc_1800E0512
0x1800e04f4  mov     rcx, [rsp+1A8h+var_160]
0x1800e04f9  test    rcx, rcx
0x1800e04fc  jz      short loc_1800E050D
0x1800e04fe  mov     rax, [rcx]
0x1800e0501  mov     edx, r12d
0x1800e0504  mov     rax, [rax]
0x1800e0507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e050c  nop
0x1800e050d  jmp     loc_1800E081F
0x1800e0512  lea     r8, [rsi+78h]; void *
0x1800e0516  cmp     [r8+4], r12b
0x1800e051a  jnz     short loc_1800E054F
0x1800e051c  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x1800e0523  mov     rcx, r14; this
0x1800e0526  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e052b  mov     edi, eax
0x1800e052d  test    eax, eax
0x1800e052f  jz      short loc_1800E054F
0x1800e0531  mov     rcx, [rsp+1A8h+var_160]
0x1800e0536  test    rcx, rcx
0x1800e0539  jz      short loc_1800E054A
0x1800e053b  mov     rax, [rcx]
0x1800e053e  mov     edx, r12d
0x1800e0541  mov     rax, [rax]
0x1800e0544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0549  nop
0x1800e054a  jmp     loc_1800E081F
0x1800e054f  lea     r8, [rsi+80h]; void *
0x1800e0556  cmp     [r8+4], r12b
0x1800e055a  jnz     short loc_1800E058F
0x1800e055c  lea     rdx, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x1800e0563  mov     rcx, r14; this
0x1800e0566  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e056b  mov     edi, eax
0x1800e056d  test    eax, eax
0x1800e056f  jz      short loc_1800E058F
0x1800e0571  mov     rcx, [rsp+1A8h+var_160]
0x1800e0576  test    rcx, rcx
0x1800e0579  jz      short loc_1800E058A
0x1800e057b  mov     rax, [rcx]
0x1800e057e  mov     edx, r12d
0x1800e0581  mov     rax, [rax]
0x1800e0584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0589  nop
0x1800e058a  jmp     loc_1800E081F
0x1800e058f  lea     r8, [rsi+88h]; void *
0x1800e0596  cmp     [r8+4], r12b
0x1800e059a  jnz     short loc_1800E05CF
0x1800e059c  lea     rdx, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x1800e05a3  mov     rcx, r14; this
0x1800e05a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e05ab  mov     edi, eax
0x1800e05ad  test    eax, eax
0x1800e05af  jz      short loc_1800E05CF
0x1800e05b1  mov     rcx, [rsp+1A8h+var_160]
0x1800e05b6  test    rcx, rcx
0x1800e05b9  jz      short loc_1800E05CA
0x1800e05bb  mov     rax, [rcx]
0x1800e05be  mov     edx, r12d
0x1800e05c1  mov     rax, [rax]
0x1800e05c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e05c9  nop
0x1800e05ca  jmp     loc_1800E081F
0x1800e05cf  lea     r8, [rsi+90h]; void *
0x1800e05d6  cmp     [r8+4], r12b
0x1800e05da  jnz     short loc_1800E060F
0x1800e05dc  lea     rdx, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x1800e05e3  mov     rcx, r14; this
0x1800e05e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e05eb  mov     edi, eax
0x1800e05ed  test    eax, eax
0x1800e05ef  jz      short loc_1800E060F
0x1800e05f1  mov     rcx, [rsp+1A8h+var_160]
0x1800e05f6  test    rcx, rcx
0x1800e05f9  jz      short loc_1800E060A
0x1800e05fb  mov     rax, [rcx]
0x1800e05fe  mov     edx, r12d
0x1800e0601  mov     rax, [rax]
0x1800e0604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0609  nop
0x1800e060a  jmp     loc_1800E081F
0x1800e060f  lea     r8, [rsi+98h]; void *
0x1800e0616  cmp     [r8+8], r12b
0x1800e061a  jnz     short loc_1800E064F
0x1800e061c  lea     rdx, aEnhancedstorag; "EnhancedStorageDevices"
0x1800e0623  mov     rcx, r14; this
0x1800e0626  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e062b  mov     edi, eax
0x1800e062d  test    eax, eax
0x1800e062f  jz      short loc_1800E064F
0x1800e0631  mov     rcx, [rsp+1A8h+var_160]
0x1800e0636  test    rcx, rcx
0x1800e0639  jz      short loc_1800E064A
0x1800e063b  mov     rax, [rcx]
0x1800e063e  mov     edx, r12d
0x1800e0641  mov     rax, [rax]
0x1800e0644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0649  nop
0x1800e064a  jmp     loc_1800E081F
0x1800e064f  lea     r8, [rsi+0A8h]; void *
0x1800e0656  cmp     [r8+4], r12b
0x1800e065a  jnz     short loc_1800E068F
0x1800e065c  lea     rdx, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x1800e0663  mov     rcx, r14; this
0x1800e0666  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e066b  mov     edi, eax
0x1800e066d  test    eax, eax
0x1800e066f  jz      short loc_1800E068F
0x1800e0671  mov     rcx, [rsp+1A8h+var_160]
0x1800e0676  test    rcx, rcx
0x1800e0679  jz      short loc_1800E068A
0x1800e067b  mov     rax, [rcx]
0x1800e067e  mov     edx, r12d
0x1800e0681  mov     rax, [rax]
0x1800e0684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0689  nop
0x1800e068a  jmp     loc_1800E081F
0x1800e068f  lea     r8, [rsi+0B0h]; void *
0x1800e0696  cmp     [r8+8], r12b
0x1800e069a  jnz     short loc_1800E06CF
0x1800e069c  lea     rdx, aWpddevicesdeny_1; "WPDDevicesDenyReadAccessPerDevice"
0x1800e06a3  mov     rcx, r14; this
0x1800e06a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e06ab  mov     edi, eax
0x1800e06ad  test    eax, eax
0x1800e06af  jz      short loc_1800E06CF
0x1800e06b1  mov     rcx, [rsp+1A8h+var_160]
0x1800e06b6  test    rcx, rcx
0x1800e06b9  jz      short loc_1800E06CA
0x1800e06bb  mov     rax, [rcx]
0x1800e06be  mov     edx, r12d
0x1800e06c1  mov     rax, [rax]
0x1800e06c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e06c9  nop
0x1800e06ca  jmp     loc_1800E081F
0x1800e06cf  lea     r8, [rsi+0C0h]; void *
0x1800e06d6  cmp     [r8+8], r12b
0x1800e06da  jnz     short loc_1800E070F
0x1800e06dc  lea     rdx, aWpddevicesdeny_2; "WPDDevicesDenyWriteAccessPerDevice"
0x1800e06e3  mov     rcx, r14; this
0x1800e06e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800e06eb  mov     edi, eax
0x1800e06ed  test    eax, eax
0x1800e06ef  jz      short loc_1800E070F
0x1800e06f1  mov     rcx, [rsp+1A8h+var_160]
0x1800e06f6  test    rcx, rcx
0x1800e06f9  jz      short loc_1800E070A
0x1800e06fb  mov     rax, [rcx]
0x1800e06fe  mov     edx, r12d
0x1800e0701  mov     rax, [rax]
0x1800e0704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0709  nop
0x1800e070a  jmp     loc_1800E081F
0x1800e070f  mov     rax, [r14]
0x1800e0712  mov     rcx, r14
0x1800e0715  mov     rax, [rax+10h]
0x1800e0719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e071e  mov     edi, eax
0x1800e0720  test    eax, eax
0x1800e0722  jz      short loc_1800E0742
0x1800e0724  mov     rcx, [rsp+1A8h+var_160]
0x1800e0729  test    rcx, rcx
0x1800e072c  jz      short loc_1800E073D
0x1800e072e  mov     rax, [rcx]
0x1800e0731  mov     edx, r12d
0x1800e0734  mov     rax, [rax]
  ... truncated ...
```
