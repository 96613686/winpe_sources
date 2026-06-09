# CPipeManager::SetupCoreObjects(void)

- ea: `0x18009d364`
- end: `0x18009daf6`
- name: `?SetupCoreObjects@CPipeManager@@IEAAJXZ`
- size: `1938`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x180094a60`
- `0x18009c0e0`

## callees

- `0x180001308`
- `0x18000202c`
- `0x18000ce04`
- `0x18008e120`
- `0x18008f858`
- `0x18009d364`
- `0x1800b0f88`
- `0x1800b5378`
- `0x1800b67e4`
- `0x1800c2594`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18009d67a`
- `OLEAUT32!__imp_VariantInit` at `0x18009d67a`
- `OLEAUT32!__imp_VariantClear` at `0x18009d702`
- `OLEAUT32!__imp_VariantClear` at `0x18009d702`

## string_xrefs

- `0x18009d3b5`: `CXRWorkItemList_CreateInstance failed!`
- `0x18009d45a`: `RdpWorkItemManager_CreateInstance failed!`
- `0x18009d5bf`: `PipeManagerError_InitInstanceCreateProfileMgrFail`
- `0x18009d5e7`: `ProfileManager::CreateInstance failed`
- `0x18009d713`: `PipeManagerError_InitInstanceCreateRdpPerfMonFail`
- `0x18009d7d1`: `PipeManagerError_InitInstanceCreateRdpPerfMonFail`
- `0x18009d88c`: `PipeManagerError_InitInstanceCreateRdpPerfMonFail`
- `0x18009d73b`: `RdpPerformanceMonitor_CreateInstance failed!`
- `0x18009d939`: `PipeManagerError_InitInstanceCreateBmpEncoderFail`
- `0x18009d961`: `CreateBitmapEncoders failed`
- `0x18009d9e6`: `PipeManagerError_InitInstanceCreateProcessorsFail`
- `0x18009da0e`: `CreateProcessors failed`
- `0x18009da89`: `CPipeManager::SetupCoreObjects Set m_spExtensionFactory `

## pseudocode

```c
__int64 __fastcall CPipeManager::SetupCoreObjects(CPipeManager *this, const struct _GUID *a2)
{
  _QWORD *v2; // rsi
  signed int Instance; // ebx
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  char *v8; // rdx
  const char **v9; // rax
  signed int v10; // eax
  _QWORD *v11; // r14
  signed int v12; // eax
  _QWORD *v13; // rsi
  signed int v14; // eax
  signed int v15; // eax
  signed int BitmapEncoders; // eax
  signed int Processors; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v22; // [rsp+20h] [rbp-60h]
  const char **v23; // [rsp+40h] [rbp-40h]
  const char *v24; // [rsp+50h] [rbp-30h] BYREF
  const char *v25; // [rsp+58h] [rbp-28h] BYREF
  const char *v26; // [rsp+60h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-18h] BYREF
  const char *v28; // [rsp+B0h] [rbp+30h] BYREF
  signed int v29; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v30; // [rsp+C0h] [rbp+40h] BYREF
  const char *v31; // [rsp+C8h] [rbp+48h] BYREF

  v2 = (_QWORD *)((char *)this + 12984);
  v30 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  Instance = CXRWorkItemList_CreateInstance((struct IUnknown *)this, a2, (void **)this + 1623);
  if ( Instance >= 0 )
  {
    Instance = RdpWorkItemManager_CreateInstance(
                 *((struct IUnknown **)this + 1627),
                 (struct IRdpWorkItemManager **)this + 6127);
    if ( Instance < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1175;
      v31 = "RdpWorkItemManager_CreateInstance failed!";
      v8 = byte_18027B5E3;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v2 + 24LL))(
            *v2,
            ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
            *((_QWORD *)this + 1624));
    Instance = v10;
    if ( v10 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceInitWorkItemListFail",
        (char *)0x49B,
        v10,
        v22);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1180;
      v31 = "IRdpWorkItemScheduler::InitalizeInstance failed";
      v8 = byte_18027B595;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    v11 = (_QWORD *)((char *)this + 13048);
    v12 = ProfileManager::CreateInstance(
            *((struct IUnknown **)this + 1627),
            *((struct IRDPCollection **)this + 6114),
            (struct IRdpProfileManager **)this + 1631);
    Instance = v12;
    if ( v12 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateProfileMgrFail",
        (char *)0x4A2,
        v12,
        v22);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1187;
      v31 = "ProfileManager::CreateInstance failed";
      v8 = &byte_18027B547;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v11 + 56LL))(
      *v11,
      ((unsigned __int64)this + 48) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    VariantInit(&pvarg);
    Instance = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 6114) + 24LL))(
                 *((_QWORD *)this + 6114),
                 L"TestPerformanceMonitor",
                 &pvarg);
    if ( Instance < 0
      || (v13 = (_QWORD *)((char *)this + 13056), pvarg.vt == 13)
      && (v11 = (_QWORD *)((char *)this + 13048),
          Instance = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, char *))pvarg.llVal)(
                       pvarg.llVal,
                       &IID_IRdpPerformanceMonitor,
                       (char *)this + 13056),
          Instance < 0) )
    {
      v13 = (_QWORD *)((char *)this + 13056);
      if ( *((_QWORD *)this + 1632) )
      {
        TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 13056);
        *v13 = 0;
      }
      Instance = RdpPerformanceMonitor_CreateInstance((struct IRdpPerformanceMonitor **)this + 1632);
    }
    VariantClear(&pvarg);
    if ( Instance < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateRdpPerfMonFail",
        (char *)0x4B5,
        Instance,
        v22);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1206;
      v31 = "RdpPerformanceMonitor_CreateInstance failed!";
      v8 = byte_18027B4F9;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    v14 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v11)(*v11, &IID_IRdpProfileDriver, &v30);
    Instance = v14;
    if ( v14 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateRdpPerfMonFail",
        (char *)0x4BC,
        v14,
        v22);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1213;
      v31 = "QueryInterface(IID_IRdpProfileDriver) failed!";
      v8 = byte_18027B4AB;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v13 + 24LL))(*v13, *v11, v30);
    Instance = v15;
    if ( v15 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateRdpPerfMonFail",
        (char *)0x4C0,
        v15,
        v22);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1217;
      v31 = "IRdpPerformanceMonitor::InitializeInstance failed!";
      v8 = byte_18027B45D;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    BitmapEncoders = CPipeManager::CreateBitmapEncoders(this);
    Instance = BitmapEncoders;
    if ( BitmapEncoders < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateBmpEncoderFail",
        (char *)0x4C7,
        BitmapEncoders,
        v22);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1224;
      v31 = "CreateBitmapEncoders failed";
      v8 = &byte_18027B40F;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    Processors = CPipeManager::CreateProcessors(this);
    Instance = Processors;
    if ( Processors < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateProcessorsFail",
        (char *)0x4CB,
        Processors,
        v22);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_38;
      LODWORD(v28) = 1228;
      v31 = "CreateProcessors failed";
      v8 = byte_18027B3C1;
      v26 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error HResult failed";
      v23 = &v26;
      v9 = &v24;
      goto LABEL_4;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v28 = "CPipeManager::SetupCoreObjects Set m_spExtensionFactory ";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v18,
        (unsigned int)&byte_18027B39F,
        v19,
        v20,
        (__int64)&v28);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6127) + 64LL))(
      *((_QWORD *)this + 6127),
      *((_QWORD *)this + 6618));
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6127) + 72LL))(
      *((_QWORD *)this + 6127),
      *((_QWORD *)this + 1641));
  }
  else
  {
    v7 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v28) = 1166;
      v31 = "CXRWorkItemList_CreateInstance failed!";
      v8 = byte_18027B631;
      v24 = "SetupCoreObjects";
      v25 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v26 = "Error HResult failed";
      v23 = &v24;
      v9 = &v26;
LABEL_4:
      v29 = Instance;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (_DWORD)v8,
        v5,
        v6,
        (__int64)v9,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)v23,
        (__int64)&v31);
    }
  }
LABEL_38:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v30);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18009d364  push    rbp
0x18009d366  push    rbx
0x18009d367  push    rsi
0x18009d368  push    rdi
0x18009d369  push    r14
0x18009d36b  mov     rbp, rsp
0x18009d36e  sub     rsp, 80h
0x18009d375  lea     rsi, [rcx+32B8h]
0x18009d37c  mov     [rbp+arg_10], 0
0x18009d384  xorps   xmm0, xmm0
0x18009d387  xor     eax, eax
0x18009d389  mov     r8, rsi; void **
0x18009d38c  mov     qword ptr [rbp+pvarg+10h], rax
0x18009d390  mov     rdi, rcx
0x18009d393  movups  xmmword ptr [rbp+pvarg], xmm0
0x18009d397  call    ?CXRWorkItemList_CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CXRWorkItemList_CreateInstance(IUnknown *,_GUID const &,void * *)
0x18009d39c  mov     ebx, eax
0x18009d39e  test    eax, eax
0x18009d3a0  jns     loc_18009D432
0x18009d3a6  mov     ecx, cs:CallbackContext
0x18009d3ac  cmp     ecx, 2
0x18009d3af  jbe     loc_18009DADD
0x18009d3b5  lea     rax, aCxrworkitemlis; "CXRWorkItemList_CreateInstance failed!"
0x18009d3bc  mov     dword ptr [rbp+arg_0], 48Eh
0x18009d3c3  mov     [rbp+arg_18], rax
0x18009d3c7  lea     rdx, byte_18027B631
0x18009d3ce  lea     rax, aSetupcoreobjec_1; "SetupCoreObjects"
0x18009d3d5  mov     [rbp+var_30], rax
0x18009d3d9  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009d3e0  mov     [rbp+var_28], rax
0x18009d3e4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009d3eb  mov     [rbp+var_20], rax
0x18009d3ef  lea     rax, [rbp+arg_18]
0x18009d3f3  mov     [rsp+80h+var_38], rax
0x18009d3f8  lea     rax, [rbp+var_30]
0x18009d3fc  mov     [rsp+80h+var_40], rax
0x18009d401  lea     rax, [rbp+arg_0]
0x18009d405  mov     [rsp+80h+var_48], rax
0x18009d40a  lea     rax, [rbp+var_28]
0x18009d40e  mov     [rsp+80h+var_50], rax
0x18009d413  lea     rax, [rbp+arg_8]
0x18009d417  mov     [rsp+80h+var_58], rax
0x18009d41c  lea     rax, [rbp+var_20]
0x18009d420  mov     [rbp+arg_8], ebx
0x18009d423  mov     [rsp+80h+var_60], rax
0x18009d428  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009d42d  jmp     loc_18009DADD
0x18009d432  mov     rcx, [rdi+32D8h]; struct IUnknown *
0x18009d439  lea     rdx, [rdi+0BF78h]; struct IRdpWorkItemManager **
0x18009d440  call    ?RdpWorkItemManager_CreateInstance@@YAJPEAUIUnknown@@PEAPEAVIRdpWorkItemManager@@@Z; RdpWorkItemManager_CreateInstance(IUnknown *,IRdpWorkItemManager * *)
0x18009d445  mov     ebx, eax
0x18009d447  test    eax, eax
0x18009d449  jns     short loc_18009D4CA
0x18009d44b  mov     eax, cs:CallbackContext
0x18009d451  cmp     eax, 2
0x18009d454  jbe     loc_18009DADD
0x18009d45a  lea     rax, aRdpworkitemman_0; "RdpWorkItemManager_CreateInstance faile"...
0x18009d461  mov     dword ptr [rbp+arg_0], 497h
0x18009d468  mov     [rbp+arg_18], rax
0x18009d46c  lea     rdx, byte_18027B5E3
0x18009d473  lea     rax, aSetupcoreobjec_1; "SetupCoreObjects"
0x18009d47a  mov     [rbp+var_20], rax
0x18009d47e  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009d485  mov     [rbp+var_28], rax
0x18009d489  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009d490  mov     [rbp+var_30], rax
0x18009d494  lea     rax, [rbp+arg_18]
0x18009d498  mov     [rsp+80h+var_38], rax
0x18009d49d  lea     rax, [rbp+var_20]
0x18009d4a1  mov     [rsp+80h+var_40], rax
0x18009d4a6  lea     rax, [rbp+arg_0]
0x18009d4aa  mov     [rsp+80h+var_48], rax
0x18009d4af  lea     rax, [rbp+var_28]
0x18009d4b3  mov     [rsp+80h+var_50], rax
0x18009d4b8  lea     rax, [rbp+arg_8]
0x18009d4bc  mov     [rsp+80h+var_58], rax
0x18009d4c1  lea     rax, [rbp+var_30]
0x18009d4c5  jmp     loc_18009D420
0x18009d4ca  mov     rcx, [rsi]
0x18009d4cd  lea     r8, [rdi+8]
0x18009d4d1  mov     rax, rdi
0x18009d4d4  neg     rax
0x18009d4d7  mov     r9, [rcx]
0x18009d4da  sbb     rdx, rdx
0x18009d4dd  and     rdx, r8
0x18009d4e0  mov     r8, [rdi+32C0h]
0x18009d4e7  mov     rax, [r9+18h]
0x18009d4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d4f0  mov     ebx, eax
0x18009d4f2  test    eax, eax
0x18009d4f4  jns     loc_18009D595
0x18009d4fa  mov     r9d, eax; unsigned int
0x18009d4fd  lea     rdx, aPipemanagererr_66; "PipeManagerError_InitInstanceInitWorkIt"...
0x18009d504  mov     r8d, 49Bh; char *
0x18009d50a  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009d511  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009d516  mov     eax, cs:CallbackContext
0x18009d51c  cmp     eax, 2
0x18009d51f  jbe     loc_18009DADD
0x18009d525  lea     rax, aIrdpworkitemsc; "IRdpWorkItemScheduler::InitalizeInstanc"...
0x18009d52c  mov     dword ptr [rbp+arg_0], 49Ch
0x18009d533  mov     [rbp+arg_18], rax
0x18009d537  lea     rdx, byte_18027B595
0x18009d53e  lea     rax, aSetupcoreobjec_1; "SetupCoreObjects"
0x18009d545  mov     [rbp+var_20], rax
0x18009d549  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009d550  mov     [rbp+var_28], rax
0x18009d554  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009d55b  mov     [rbp+var_30], rax
0x18009d55f  lea     rax, [rbp+arg_18]
0x18009d563  mov     [rsp+80h+var_38], rax
0x18009d568  lea     rax, [rbp+var_20]
0x18009d56c  mov     [rsp+80h+var_40], rax
0x18009d571  lea     rax, [rbp+arg_0]
0x18009d575  mov     [rsp+80h+var_48], rax
0x18009d57a  lea     rax, [rbp+var_28]
0x18009d57e  mov     [rsp+80h+var_50], rax
0x18009d583  lea     rax, [rbp+arg_8]
0x18009d587  mov     [rsp+80h+var_58], rax
0x18009d58c  lea     rax, [rbp+var_30]
0x18009d590  jmp     loc_18009D420
0x18009d595  mov     rdx, [rdi+0BF10h]; struct IRDPCollection *
0x18009d59c  lea     r14, [rdi+32F8h]
0x18009d5a3  mov     rcx, [rdi+32D8h]; struct IUnknown *
0x18009d5aa  mov     r8, r14; struct IRdpProfileManager **
0x18009d5ad  call    ?CreateInstance@ProfileManager@@SAJPEAUIUnknown@@PEAUIRDPCollection@@PEAPEAVIRdpProfileManager@@@Z; ProfileManager::CreateInstance(IUnknown *,IRDPCollection *,IRdpProfileManager * *)
0x18009d5b2  mov     ebx, eax
0x18009d5b4  test    eax, eax
0x18009d5b6  jns     loc_18009D657
0x18009d5bc  mov     r9d, eax; unsigned int
0x18009d5bf  lea     rdx, aPipemanagererr_67; "PipeManagerError_InitInstanceCreateProf"...
0x18009d5c6  mov     r8d, 4A2h; char *
0x18009d5cc  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009d5d3  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009d5d8  mov     eax, cs:CallbackContext
0x18009d5de  cmp     eax, 2
0x18009d5e1  jbe     loc_18009DADD
0x18009d5e7  lea     rax, aProfilemanager_3; "ProfileManager::CreateInstance failed"
0x18009d5ee  mov     dword ptr [rbp+arg_0], 4A3h
0x18009d5f5  mov     [rbp+arg_18], rax
0x18009d5f9  lea     rdx, byte_18027B547
0x18009d600  lea     rax, aSetupcoreobjec_1; "SetupCoreObjects"
0x18009d607  mov     [rbp+var_20], rax
0x18009d60b  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009d612  mov     [rbp+var_28], rax
0x18009d616  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009d61d  mov     [rbp+var_30], rax
0x18009d621  lea     rax, [rbp+arg_18]
0x18009d625  mov     [rsp+80h+var_38], rax
0x18009d62a  lea     rax, [rbp+var_20]
0x18009d62e  mov     [rsp+80h+var_40], rax
0x18009d633  lea     rax, [rbp+arg_0]
0x18009d637  mov     [rsp+80h+var_48], rax
0x18009d63c  lea     rax, [rbp+var_28]
0x18009d640  mov     [rsp+80h+var_50], rax
0x18009d645  lea     rax, [rbp+arg_8]
0x18009d649  mov     [rsp+80h+var_58], rax
0x18009d64e  lea     rax, [rbp+var_30]
0x18009d652  jmp     loc_18009D420
0x18009d657  mov     rcx, [r14]
0x18009d65a  lea     r8, [rdi+30h]
0x18009d65e  mov     rax, rdi
0x18009d661  neg     rax
0x18009d664  mov     r9, [rcx]
0x18009d667  sbb     rdx, rdx
0x18009d66a  and     rdx, r8
0x18009d66d  mov     rax, [r9+38h]
0x18009d671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d676  lea     rcx, [rbp+pvarg]; pvarg
0x18009d67a  call    cs:__imp_VariantInit
0x18009d680  mov     rcx, [rdi+0BF10h]
0x18009d687  lea     r8, [rbp+pvarg]
0x18009d68b  lea     rdx, aTestperformanc; "TestPerformanceMonitor"
0x18009d692  mov     rax, [rcx]
0x18009d695  mov     rax, [rax+18h]
0x18009d699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d69e  mov     ebx, eax
0x18009d6a0  test    eax, eax
0x18009d6a2  js      short loc_18009D6D8
0x18009d6a4  cmp     word ptr [rbp+pvarg], 0Dh
0x18009d6a9  lea     rsi, [rdi+3300h]
0x18009d6b0  jnz     short loc_18009D6FE
0x18009d6b2  mov     rcx, qword ptr [rbp+pvarg+8]
0x18009d6b6  lea     rdx, IID_IRdpPerformanceMonitor
0x18009d6bd  mov     r8, rsi
0x18009d6c0  mov     rax, [rcx]
0x18009d6c3  mov     rax, [rax]
0x18009d6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d6cb  lea     r14, [rdi+32F8h]
0x18009d6d2  mov     ebx, eax
0x18009d6d4  test    eax, eax
0x18009d6d6  jns     short loc_18009D6FE
0x18009d6d8  lea     rsi, [rdi+3300h]
0x18009d6df  cmp     qword ptr [rsi], 0
0x18009d6e3  jz      short loc_18009D6F4
0x18009d6e5  mov     rcx, rsi
0x18009d6e8  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009d6ed  mov     qword ptr [rsi], 0
0x18009d6f4  mov     rcx, rsi; struct IRdpPerformanceMonitor **
0x18009d6f7  call    ?RdpPerformanceMonitor_CreateInstance@@YAJPEAPEAVIRdpPerformanceMonitor@@@Z; RdpPerformanceMonitor_CreateInstance(IRdpPerformanceMonitor * *)
0x18009d6fc  mov     ebx, eax
0x18009d6fe  lea     rcx, [rbp+pvarg]; pvarg
0x18009d702  call    cs:__imp_VariantClear
0x18009d708  test    ebx, ebx
0x18009d70a  jns     loc_18009D7AB
0x18009d710  mov     r9d, ebx; unsigned int
0x18009d713  lea     rdx, aPipemanagererr_40; "PipeManagerError_InitInstanceCreateRdpP"...
0x18009d71a  mov     r8d, 4B5h; char *
0x18009d720  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009d727  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009d72c  mov     eax, cs:CallbackContext
0x18009d732  cmp     eax, 2
0x18009d735  jbe     loc_18009DADD
0x18009d73b  lea     rax, aRdpperformance_0; "RdpPerformanceMonitor_CreateInstance fa"...
0x18009d742  mov     dword ptr [rbp+arg_0], 4B6h
0x18009d749  mov     [rbp+arg_18], rax
0x18009d74d  lea     rdx, byte_18027B4F9
0x18009d754  lea     rax, aSetupcoreobjec_1; "SetupCoreObjects"
0x18009d75b  mov     [rbp+var_20], rax
0x18009d75f  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009d766  mov     [rbp+var_28], rax
0x18009d76a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009d771  mov     [rbp+var_30], rax
0x18009d775  lea     rax, [rbp+arg_18]
0x18009d779  mov     [rsp+80h+var_38], rax
0x18009d77e  lea     rax, [rbp+var_20]
0x18009d782  mov     [rsp+80h+var_40], rax
0x18009d787  lea     rax, [rbp+arg_0]
0x18009d78b  mov     [rsp+80h+var_48], rax
0x18009d790  lea     rax, [rbp+var_28]
0x18009d794  mov     [rsp+80h+var_50], rax
0x18009d799  lea     rax, [rbp+arg_8]
0x18009d79d  mov     [rsp+80h+var_58], rax
0x18009d7a2  lea     rax, [rbp+var_30]
0x18009d7a6  jmp     loc_18009D420
0x18009d7ab  mov     rcx, [r14]
0x18009d7ae  lea     r8, [rbp+arg_10]
0x18009d7b2  lea     rdx, IID_IRdpProfileDriver
0x18009d7b9  mov     rax, [rcx]
0x18009d7bc  mov     rax, [rax]
0x18009d7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7c4  mov     ebx, eax
0x18009d7c6  test    eax, eax
0x18009d7c8  jns     loc_18009D869
0x18009d7ce  mov     r9d, eax; unsigned int
0x18009d7d1  lea     rdx, aPipemanagererr_40; "PipeManagerError_InitInstanceCreateRdpP"...
0x18009d7d8  mov     r8d, 4BCh; char *
0x18009d7de  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009d7e5  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009d7ea  mov     eax, cs:CallbackContext
0x18009d7f0  cmp     eax, 2
0x18009d7f3  jbe     loc_18009DADD
0x18009d7f9  lea     rax, aQueryinterface_10; "QueryInterface(IID_IRdpProfileDriver) f"...
0x18009d800  mov     dword ptr [rbp+arg_0], 4BDh
0x18009d807  mov     [rbp+arg_18], rax
0x18009d80b  lea     rdx, byte_18027B4AB
0x18009d812  lea     rax, aSetupcoreobjec_1; "SetupCoreObjects"
0x18009d819  mov     [rbp+var_20], rax
0x18009d81d  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009d824  mov     [rbp+var_28], rax
0x18009d828  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009d82f  mov     [rbp+var_30], rax
0x18009d833  lea     rax, [rbp+arg_18]
0x18009d837  mov     [rsp+80h+var_38], rax
0x18009d83c  lea     rax, [rbp+var_20]
0x18009d840  mov     [rsp+80h+var_40], rax
0x18009d845  lea     rax, [rbp+arg_0]
0x18009d849  mov     [rsp+80h+var_48], rax
0x18009d84e  lea     rax, [rbp+var_28]
0x18009d852  mov     [rsp+80h+var_50], rax
0x18009d857  lea     rax, [rbp+arg_8]
0x18009d85b  mov     [rsp+80h+var_58], rax
0x18009d860  lea     rax, [rbp+var_30]
0x18009d864  jmp     loc_18009D420
0x18009d869  mov     rcx, [rsi]
0x18009d86c  mov     r8, [rbp+arg_10]
0x18009d870  mov     rdx, [r14]
0x18009d873  mov     rax, [rcx]
0x18009d876  mov     rax, [rax+18h]
0x18009d87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d87f  mov     ebx, eax
0x18009d881  test    eax, eax
0x18009d883  jns     loc_18009D924
0x18009d889  mov     r9d, eax; unsigned int
0x18009d88c  lea     rdx, aPipemanagererr_40; "PipeManagerError_InitInstanceCreateRdpP"...
0x18009d893  mov     r8d, 4C0h; char *
0x18009d899  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009d8a0  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009d8a5  mov     eax, cs:CallbackContext
0x18009d8ab  cmp     eax, 2
0x18009d8ae  jbe     loc_18009DADD
0x18009d8b4  lea     rax, aIrdpperformanc; "IRdpPerformanceMonitor::InitializeInsta"...
0x18009d8bb  mov     dword ptr [rbp+arg_0], 4C1h
0x18009d8c2  mov     [rbp+arg_18], rax
0x18009d8c6  lea     rdx, byte_18027B45D
0x18009d8cd  lea     rax, aSetupcoreobjec_1; "SetupCoreObjects"
0x18009d8d4  mov     [rbp+var_20], rax
0x18009d8d8  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009d8df  mov     [rbp+var_28], rax
0x18009d8e3  lea     rax, aErrorHresultFa; "Error HResult failed"
  ... truncated ...
```
