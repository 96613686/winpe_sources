# CLightDismissClientStore::_DismissClients(void)

- ea: `0x180016d10`
- end: `0x180017149`
- name: `?_DismissClients@CLightDismissClientStore@@AEAAJXZ`
- size: `1081`
- prototype: `__int64 __fastcall(CLightDismissClientStore *__hidden this)`
- caller_count: `9`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180015bcc`
- `0x180015cd0`
- `0x1800160a0`
- `0x1800165d0`
- `0x18002cca0`
- `0x180044b5c`
- `0x18007eebc`
- `0x18007fa30`
- `0x18007fb78`

## callees

- `0x180013244`
- `0x180016b94`
- `0x180016c30`
- `0x180016d10`
- `0x180017150`
- `0x180017240`
- `0x180017264`
- `0x1800172a8`
- `0x1800178a8`
- `0x180017980`
- `0x180033e98`
- `0x180033ef0`
- `0x180033f0c`
- `0x180050ba0`
- `0x180050f70`
- `0x180051524`
- `0x18005659c`
- `0x180056c12`
- `0x18007da84`
- `0x18007ff1c`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016f13`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800170c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800170c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180016eb6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180016eb6`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800170aa`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800170aa`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180016e80`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180016e80`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180016ee6`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180016ee6`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180016fb6`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180016fb6`

## pseudocode

```c
__int64 __fastcall CLightDismissClientStore::_DismissClients(
        CLightDismissClientStore *this,
        unsigned int a2,
        unsigned int a3)
{
  int AgileReference; // ebx
  __int64 *v5; // rcx
  __int64 v6; // rsi
  void *v7; // rdx
  __int64 v8; // rcx
  DWORD CurrentThreadId; // eax
  struct IUnknown *v10; // r12
  CAgileObjectContainer *v11; // r15
  HRESULT ApartmentType; // eax
  DWORD v13; // ebx
  CAgileObjectContainer *v14; // rax
  CAgileObjectContainer *v15; // rax
  CAgileObjectContainer *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // r14d
  __int64 v22; // rdi
  __int64 v23; // rax
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+40h] [rbp-C0h] BYREF
  APTTYPE pAptType; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Parameter; // [rsp+50h] [rbp-B0h] BYREF
  char v28; // [rsp+54h] [rbp-ACh]
  HRESULT v29; // [rsp+58h] [rbp-A8h]
  void *phNewTimer; // [rsp+60h] [rbp-A0h] BYREF
  void **v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+78h] [rbp-88h] BYREF
  char v33; // [rsp+7Ch] [rbp-84h]
  int v34; // [rsp+A0h] [rbp-60h] BYREF
  const char *v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+C0h] [rbp-40h]
  _BYTE v39[152]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v40; // [rsp+160h] [rbp+60h]
  int v41; // [rsp+170h] [rbp+70h]
  __int64 v42; // [rsp+178h] [rbp+78h]
  int *v43; // [rsp+180h] [rbp+80h]
  __int64 v44; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v45[3]; // [rsp+190h] [rbp+90h] BYREF
  int v46; // [rsp+1A8h] [rbp+A8h]
  int *v47; // [rsp+1B0h] [rbp+B0h]
  char v48; // [rsp+1B8h] [rbp+B8h]

  AgileReference = 0;
  if ( *((_QWORD *)this + 22)
    || (AgileReference = shell::TaskScheduler::CreateInstance(
                           (const struct _GUID *)this,
                           a2,
                           a3,
                           (struct TaskScheduler **)this + 22),
        AgileReference >= 0) )
  {
LABEL_48:
    v23 = *((_QWORD *)this + 16);
    if ( !v23 )
      return (unsigned int)AgileReference;
    v5 = (__int64 *)*((_QWORD *)this + 15);
    v6 = *v5;
    if ( v23 != 1 )
      memmove_0(v5, v5 + 1, 8 * (v23 - 1));
    --*((_QWORD *)this + 16);
    v32 = 0;
    v35 = "LightDismissDismissClient";
    v40 = 0;
    v33 = 0;
    v37 = 0;
    v34 = 0;
    v36 = 0;
    v38 = 0;
    memset_0(v39, 0, sizeof(v39));
    v41 = 1;
    v42 = 0;
    v44 = 0;
    v43 = &v32;
    v45[1] = &v31;
    v47 = &v34;
    v45[0] = 0;
    v45[2] = 0;
    v46 = 0;
    v48 = 0;
    v31 = &LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable';
    LightDismissFrameworkTelemetry::LightDismissDismissClient::StartActivity(
      (LightDismissFrameworkTelemetry::LightDismissDismissClient *)&v31,
      *(_DWORD *)(v6 + 40));
    while ( *(_QWORD *)(v6 + 56) )
      v6 = *(_QWORD *)(v6 + 56);
    while ( 1 )
    {
      if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
        McTemplateU0pq_EventWriteTransfer(v8, v7, *(_QWORD *)(v6 + 8), *(unsigned int *)(v6 + 40));
      CurrentThreadId = GetCurrentThreadId();
      v28 = 0;
      Parameter = CurrentThreadId;
      v29 = -2147467259;
      phNewTimer = 0;
      v29 = CoEnableCallCancellation(0);
      if ( v29 >= 0 )
        CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x3E8u, 0x3E8u, 0);
      *(_QWORD *)pAptQualifier = 0;
      Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(pAptQualifier);
      v10 = *(struct IUnknown **)(v6 + 32);
      v11 = 0;
      pAptType = APTTYPE_STA;
      pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
      ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
      AgileReference = ApartmentType;
      if ( ApartmentType >= 0 )
        break;
      v21 = ApartmentType;
LABEL_39:
      v22 = *(_QWORD *)(v6 + 48);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v6 + 32);
      operator delete((void *)v6, (const struct std::nothrow_t *)0x40);
      v6 = v22;
      if ( v22 )
        *(_QWORD *)(v22 + 56) = 0;
      if ( v11 )
        CAgileObjectContainer::Release(v11);
      if ( v29 >= 0 )
      {
        v29 = -2147467259;
        CoDisableCallCancellation(0);
        v7 = phNewTimer;
        if ( phNewTimer )
          DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
      if ( !v22 )
      {
        wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
          &v31,
          v21);
        v31 = &LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable';
        wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v31);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v45);
        wil::details::shared_object<wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v44);
        wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(&v32);
        goto LABEL_48;
      }
    }
    v13 = 0;
    if ( pAptType == APTTYPE_STA )
      goto LABEL_18;
    if ( pAptType != APTTYPE_MTA )
    {
      if ( pAptType == APTTYPE_NA )
      {
        v13 = -1;
        goto LABEL_19;
      }
      if ( pAptType == APTTYPE_MAINSTA )
LABEL_18:
        v13 = GetCurrentThreadId();
    }
LABEL_19:
    v14 = (CAgileObjectContainer *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v14 && (v15 = CAgileObjectContainer::CAgileObjectContainer(v14, v10, v13), (v16 = v15) != 0) )
    {
      *((_DWORD *)v15 + 7) = 0;
      AgileReference = GlobalInterfaceTable::s_Retrieve();
      if ( AgileReference >= 0 )
      {
        AgileReference = ((__int64 (__fastcall *)(struct IGlobalInterfaceTable *, struct IUnknown *, GUID *, char *))GlobalInterfaceTable::s_pGlobalInterfaceTable->lpVtbl->RegisterInterfaceInGlobal)(
                           GlobalInterfaceTable::s_pGlobalInterfaceTable,
                           v10,
                           &GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb,
                           (char *)v16 + 28);
        if ( AgileReference >= 0 )
        {
          v17 = 0;
          AgileReference = 0;
          *(_QWORD *)pAptQualifier = 0;
          if ( v10 )
          {
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pAptQualifier);
            AgileReference = RoGetAgileReference(0, &GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb, v10, pAptQualifier);
            v17 = *(_QWORD *)pAptQualifier;
          }
          v18 = *((_QWORD *)v16 + 2);
          *((_QWORD *)v16 + 2) = v17;
          v19 = 0;
          *(_QWORD *)pAptQualifier = 0;
          if ( v18 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v19 = *(_QWORD *)pAptQualifier;
          }
          if ( v19 )
          {
            *(_QWORD *)pAptQualifier = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          if ( AgileReference >= 0 )
          {
            v11 = v16;
            _InterlockedIncrement((volatile signed __int32 *)v16);
          }
        }
      }
      CAgileObjectContainer::Release(v16);
      if ( AgileReference >= 0 )
      {
        v20 = *((_QWORD *)this + 22);
        *(_QWORD *)pAptQualifier = v11;
        if ( v11 )
          _InterlockedIncrement((volatile signed __int32 *)v11);
        shell::TaskScheduler::AddTask__lambda_0772b9cc429bfbb776337f4e61735bae___(v20, pAptQualifier);
        Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(pAptQualifier);
      }
      v21 = AgileReference;
    }
    else
    {
      AgileReference = -2147024882;
      v21 = -2147024882;
    }
    goto LABEL_39;
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180016d10  push    rbp
0x180016d12  push    rbx
0x180016d13  push    rsi
0x180016d14  push    rdi
0x180016d15  push    r12
0x180016d17  push    r13
0x180016d19  push    r14
0x180016d1b  push    r15
0x180016d1d  lea     rbp, [rsp-0D8h]
0x180016d25  sub     rsp, 1D8h
0x180016d2c  mov     rax, cs:__security_cookie
0x180016d33  xor     rax, rsp
0x180016d36  mov     [rbp+110h+var_50], rax
0x180016d3d  xor     r12d, r12d
0x180016d40  lea     rax, [rcx+0B0h]
0x180016d47  mov     r13, rcx
0x180016d4a  mov     ebx, r12d
0x180016d4d  cmp     [rax], r12
0x180016d50  jnz     loc_180017114
0x180016d56  mov     r9, rax; struct TaskScheduler **
0x180016d59  call    ?CreateInstance@TaskScheduler@shell@@SAJAEBU_GUID@@KKPEAPEAV12@@Z; shell::TaskScheduler::CreateInstance(_GUID const &,ulong,ulong,shell::TaskScheduler * *)
0x180016d5e  mov     ebx, eax
0x180016d60  test    eax, eax
0x180016d62  jns     loc_180017114
0x180016d68  jmp     loc_180017124
0x180016d6d  mov     rcx, [r13+78h]; void *
0x180016d71  lea     rbx, ??_7LightDismissDismissClient@LightDismissFrameworkTelemetry@@6B@; const LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable'
0x180016d78  mov     rsi, [rcx]
0x180016d7b  test    rax, rax
0x180016d7e  jz      short loc_180016D9D
0x180016d80  lea     r8, [rax-1]
0x180016d84  test    r8, r8
0x180016d87  jz      short loc_180016D96
0x180016d89  shl     r8, 3; Size
0x180016d8d  lea     rdx, [rcx+8]; Src
0x180016d91  call    memmove_0
0x180016d96  dec     qword ptr [r13+80h]
0x180016d9d  lea     rax, aLightdismissdi; "LightDismissDismissClient"
0x180016da4  mov     [rsp+210h+var_198], r12d
0x180016da9  xorps   xmm0, xmm0
0x180016dac  mov     [rbp+110h+var_168], rax
0x180016db0  xor     edx, edx; Val
0x180016db2  movdqa  [rbp+110h+var_B0], xmm0
0x180016db7  mov     r8d, 98h; Size
0x180016dbd  mov     [rsp+210h+var_194], r12b
0x180016dc2  lea     rcx, [rbp+110h+var_148]; void *
0x180016dc6  mov     [rbp+110h+var_158], r12b
0x180016dca  mov     [rbp+110h+var_170], r12d
0x180016dce  mov     [rbp+110h+var_160], r12
0x180016dd2  mov     [rbp+110h+var_150], r12d
0x180016dd6  call    memset_0
0x180016ddb  xor     eax, eax
0x180016ddd  mov     [rbp+110h+var_A0], 1
0x180016de4  mov     [rbp+110h+var_98], rax
0x180016de8  lea     rcx, [rsp+210h+var_1A0]; this
0x180016ded  lea     rax, [rsp+210h+var_198]
0x180016df2  mov     [rbp+110h+var_88], r12
0x180016df9  mov     [rbp+110h+var_90], rax
0x180016e00  lea     rax, [rsp+210h+var_1A0]
0x180016e05  mov     [rbp+110h+var_78], rax
0x180016e0c  lea     rax, [rbp+110h+var_170]
0x180016e10  mov     [rbp+110h+var_60], rax
0x180016e17  mov     [rbp+110h+var_80], r12
0x180016e1e  mov     [rbp+110h+var_70], r12
0x180016e25  mov     [rbp+110h+var_68], r12d
0x180016e2c  mov     [rbp+110h+var_58], r12b
0x180016e33  mov     [rsp+210h+var_1A0], rbx
0x180016e38  mov     edx, [rsi+28h]; int
0x180016e3b  call    ?StartActivity@LightDismissDismissClient@LightDismissFrameworkTelemetry@@QEAAXH@Z; LightDismissFrameworkTelemetry::LightDismissDismissClient::StartActivity(int)
0x180016e40  jmp     short loc_180016E46
0x180016e42  mov     rsi, [rsi+38h]
0x180016e46  cmp     [rsi+38h], r12
0x180016e4a  jnz     short loc_180016E42
0x180016e4c  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, 1
0x180016e53  jz      short loc_180016E62
0x180016e55  mov     r9d, [rsi+28h]
0x180016e59  mov     r8, [rsi+8]
0x180016e5d  call    McTemplateU0pq_EventWriteTransfer
0x180016e62  call    cs:__imp_GetCurrentThreadId
0x180016e68  xor     ecx, ecx; pReserved
0x180016e6a  mov     [rsp+210h+var_1BC], r12b
0x180016e6f  mov     [rsp+210h+Parameter], eax
0x180016e73  mov     [rsp+210h+var_1B8], 80004005h
0x180016e7b  mov     [rsp+210h+phNewTimer], r12
0x180016e80  call    cs:__imp_CoEnableCallCancellation
0x180016e86  mov     [rsp+210h+var_1B8], eax
0x180016e8a  test    eax, eax
0x180016e8c  js      short loc_180016EBC
0x180016e8e  mov     [rsp+210h+Flags], r12d; Flags
0x180016e93  lea     r9, [rsp+210h+Parameter]; Parameter
0x180016e98  mov     [rsp+210h+Period], 3E8h; Period
0x180016ea0  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180016ea7  xor     edx, edx; TimerQueue
0x180016ea9  mov     [rsp+210h+DueTime], 3E8h; DueTime
0x180016eb1  lea     rcx, [rsp+210h+phNewTimer]; phNewTimer
0x180016eb6  call    cs:__imp_CreateTimerQueueTimer
0x180016ebc  lea     rcx, [rsp+210h+pAptQualifier]
0x180016ec1  mov     qword ptr [rsp+210h+pAptQualifier], r12
0x180016ec6  call    ?InternalRelease@?$ComPtr@VCAgileObjectContainer@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(void)
0x180016ecb  mov     r12, [rsi+20h]
0x180016ecf  lea     rdx, [rsp+210h+pAptQualifier]; pAptQualifier
0x180016ed4  xor     r15d, r15d
0x180016ed7  lea     rcx, [rsp+210h+pAptType]; pAptType
0x180016edc  mov     [rsp+210h+pAptType], r15d
0x180016ee1  mov     [rsp+210h+pAptQualifier], r15d
0x180016ee6  call    cs:__imp_CoGetApartmentType
0x180016eec  mov     ebx, eax
0x180016eee  test    eax, eax
0x180016ef0  js      loc_180017060
0x180016ef6  mov     ecx, [rsp+210h+pAptType]
0x180016efa  xor     ebx, ebx
0x180016efc  test    ecx, ecx
0x180016efe  jz      short loc_180016F13
0x180016f00  sub     ecx, 1
0x180016f03  jz      short loc_180016F1B
0x180016f05  sub     ecx, 1
0x180016f08  jz      loc_180017011
0x180016f0e  cmp     ecx, 1
0x180016f11  jnz     short loc_180016F1B
0x180016f13  call    cs:__imp_GetCurrentThreadId
0x180016f19  mov     ebx, eax
0x180016f1b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016f22  mov     ecx, 28h ; '('; unsigned __int64
0x180016f27  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016f2c  test    rax, rax
0x180016f2f  jz      loc_180017056
0x180016f35  mov     r8d, ebx; unsigned int
0x180016f38  mov     rdx, r12; struct IUnknown *
0x180016f3b  mov     rcx, rax; this
0x180016f3e  call    ??0CAgileObjectContainer@@IEAA@PEAUIUnknown@@K@Z; CAgileObjectContainer::CAgileObjectContainer(IUnknown *,ulong)
0x180016f43  mov     rdi, rax
0x180016f46  test    rax, rax
0x180016f49  jz      loc_180017056
0x180016f4f  mov     [rax+1Ch], r15d
0x180016f53  call    ?s_Retrieve@GlobalInterfaceTable@@CAJXZ; GlobalInterfaceTable::s_Retrieve(void)
0x180016f58  mov     ebx, eax
0x180016f5a  test    eax, eax
0x180016f5c  js      loc_180017019
0x180016f62  mov     rcx, cs:?s_pGlobalInterfaceTable@GlobalInterfaceTable@@0PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * GlobalInterfaceTable::s_pGlobalInterfaceTable
0x180016f69  lea     r9, [rdi+1Ch]
0x180016f6d  lea     r8, _GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb
0x180016f74  mov     rdx, [rcx]
0x180016f77  mov     rax, [rdx+18h]
0x180016f7b  mov     rdx, r12
0x180016f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f83  mov     ebx, eax
0x180016f85  test    eax, eax
0x180016f87  js      loc_180017019
0x180016f8d  xor     eax, eax
0x180016f8f  xor     ebx, ebx
0x180016f91  mov     qword ptr [rsp+210h+pAptQualifier], rax
0x180016f96  test    r12, r12
0x180016f99  jz      short loc_180016FC3
0x180016f9b  lea     rcx, [rsp+210h+pAptQualifier]
0x180016fa0  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180016fa5  lea     r9, [rsp+210h+pAptQualifier]
0x180016faa  mov     r8, r12
0x180016fad  lea     rdx, _GUID_8d4d1ec2_4740_4fc5_b4b1_6dc3722a2eeb
0x180016fb4  xor     ecx, ecx
0x180016fb6  call    cs:__imp_RoGetAgileReference
0x180016fbc  mov     ebx, eax
0x180016fbe  mov     rax, qword ptr [rsp+210h+pAptQualifier]
0x180016fc3  mov     rdx, [rdi+10h]
0x180016fc7  xor     r12d, r12d
0x180016fca  mov     [rdi+10h], rax
0x180016fce  mov     ecx, r12d
0x180016fd1  mov     qword ptr [rsp+210h+pAptQualifier], rcx
0x180016fd6  test    rdx, rdx
0x180016fd9  jz      short loc_180016FEF
0x180016fdb  mov     rax, [rdx]
0x180016fde  mov     rcx, rdx
0x180016fe1  mov     rax, [rax+10h]
0x180016fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fea  mov     rcx, qword ptr [rsp+210h+pAptQualifier]
0x180016fef  test    rcx, rcx
0x180016ff2  jz      short loc_180017005
0x180016ff4  mov     qword ptr [rsp+210h+pAptQualifier], r12
0x180016ff9  mov     rax, [rcx]
0x180016ffc  mov     rax, [rax+10h]
0x180017000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017005  test    ebx, ebx
0x180017007  js      short loc_18001701C
0x180017009  mov     r15, rdi
0x18001700c  lock inc dword ptr [rdi]
0x18001700f  jmp     short loc_18001701C
0x180017011  or      ebx, 0FFFFFFFFh
0x180017014  jmp     loc_180016F1B
0x180017019  xor     r12d, r12d
0x18001701c  mov     rcx, rdi; this
0x18001701f  call    ?Release@CAgileObjectContainer@@QEAAKXZ; CAgileObjectContainer::Release(void)
0x180017024  test    ebx, ebx
0x180017026  js      short loc_180017051
0x180017028  mov     rcx, [r13+0B0h]
0x18001702f  mov     qword ptr [rsp+210h+pAptQualifier], r15
0x180017034  test    r15, r15
0x180017037  jz      short loc_18001703D
0x180017039  lock inc dword ptr [r15]
0x18001703d  lea     rdx, [rsp+210h+pAptQualifier]
0x180017042  call    shell__TaskScheduler__AddTask__lambda_0772b9cc429bfbb776337f4e61735bae___
0x180017047  lea     rcx, [rsp+210h+pAptQualifier]
0x18001704c  call    ?InternalRelease@?$ComPtr@VCAgileObjectContainer@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CAgileObjectContainer>::InternalRelease(void)
0x180017051  mov     r14d, ebx
0x180017054  jmp     short loc_180017066
0x180017056  mov     ebx, 8007000Eh
0x18001705b  mov     r14d, ebx
0x18001705e  jmp     short loc_180017063
0x180017060  mov     r14d, eax
0x180017063  xor     r12d, r12d
0x180017066  mov     rdi, [rsi+30h]
0x18001706a  lea     rcx, [rsi+20h]
0x18001706e  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180017073  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x180017078  mov     rcx, rsi; void *
0x18001707b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017080  mov     rsi, rdi
0x180017083  test    rdi, rdi
0x180017086  jz      short loc_18001708C
0x180017088  mov     [rdi+38h], r12
0x18001708c  test    r15, r15
0x18001708f  jz      short loc_180017099
0x180017091  mov     rcx, r15; this
0x180017094  call    ?Release@CAgileObjectContainer@@QEAAKXZ; CAgileObjectContainer::Release(void)
0x180017099  cmp     [rsp+210h+var_1B8], r12d
0x18001709e  jl      short loc_1800170C6
0x1800170a0  xor     ecx, ecx; pReserved
0x1800170a2  mov     [rsp+210h+var_1B8], 80004005h
0x1800170aa  call    cs:__imp_CoDisableCallCancellation
0x1800170b0  mov     rdx, [rsp+210h+phNewTimer]; Timer
0x1800170b5  test    rdx, rdx
0x1800170b8  jz      short loc_1800170C6
0x1800170ba  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800170be  xor     ecx, ecx; TimerQueue
0x1800170c0  call    cs:__imp_DeleteTimerQueueTimer
0x1800170c6  test    rdi, rdi
0x1800170c9  jnz     loc_180016E4C
0x1800170cf  mov     edx, r14d
0x1800170d2  lea     rcx, [rsp+210h+var_1A0]
0x1800170d7  call    ?Stop@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800170dc  lea     rax, ??_7LightDismissDismissClient@LightDismissFrameworkTelemetry@@6B@; const LightDismissFrameworkTelemetry::LightDismissDismissClient::`vftable'
0x1800170e3  lea     rcx, [rsp+210h+var_1A0]
0x1800170e8  mov     [rsp+210h+var_1A0], rax
0x1800170ed  call    ?Destroy@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800170f2  lea     rcx, [rbp+110h+var_80]; this
0x1800170f9  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800170fe  lea     rcx, [rbp+110h+var_88]
0x180017105  call    ?reset@?$shared_object@V?$ActivityData@VLightDismissFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001710a  lea     rcx, [rsp+210h+var_198]
0x18001710f  call    ??1?$ActivityData@VLightDismissFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLightDismissFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LightDismissFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LightDismissFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017114  mov     rax, [r13+80h]
0x18001711b  test    rax, rax
0x18001711e  jnz     loc_180016D6D
0x180017124  mov     eax, ebx
0x180017126  mov     rcx, [rbp+110h+var_50]
0x18001712d  xor     rcx, rsp; StackCookie
0x180017130  call    __security_check_cookie
0x180017135  add     rsp, 1D8h
0x18001713c  pop     r15
0x18001713e  pop     r14
0x180017140  pop     r13
0x180017142  pop     r12
0x180017144  pop     rdi
0x180017145  pop     rsi
0x180017146  pop     rbx
0x180017147  pop     rbp
0x180017148  retn
```
