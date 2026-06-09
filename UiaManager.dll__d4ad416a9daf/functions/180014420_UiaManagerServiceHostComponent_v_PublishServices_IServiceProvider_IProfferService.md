# UiaManagerServiceHostComponent::v_PublishServices(IServiceProvider *,IProfferService *)

- ea: `0x180014420`
- end: `0x18001462b`
- name: `?v_PublishServices@UiaManagerServiceHostComponent@@MEAAJPEAUIServiceProvider@@PEAUIProfferService@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(UiaManagerServiceHostComponent *__hidden this, struct IServiceProvider *, struct IProfferService *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800054f8`
- `0x180005a60`
- `0x180006edc`
- `0x18000dc9c`
- `0x180010d04`
- `0x1800123f4`
- `0x180012744`
- `0x180014420`
- `0x180073670`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800144a6`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18001453b`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800145a6`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180014603`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800144a6`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18001453b`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800145a6`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180014603`

## string_xrefs

- `0x18001446d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerservicehostcomponent.cpp`
- `0x180014500`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerservicehostcomponent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UiaManagerServiceHostComponent::v_PublishServices(
        UiaManagerServiceHostComponent *this,
        struct IServiceProvider *a2,
        struct IProfferService *a3)
{
  const struct _tlgProvider_t *v4; // rax
  HRESULT v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // rcx
  int lpdwRegister; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = UiaManagerTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v4 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v4,
      (unsigned __int8 *)&unk_1800ADB30,
      0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
  v5 = Microsoft::WRL::Details::MakeAndInitialize<UiaManagerImpl,UiaManagerImpl,>((char *)this + 88);
  if ( v5 < 0 )
  {
    v6 = 39;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerservicehostcomponent.cpp",
      (const char *)(unsigned int)v5,
      lpdwRegister);
    return (unsigned int)v5;
  }
  v5 = CoRegisterClassObject(&CLSID_UiaManager, (LPUNKNOWN)this - 10, 4u, 1u, (LPDWORD)this + 24);
  if ( v5 < 0 )
  {
    v6 = 47;
    goto LABEL_5;
  }
  LOBYTE(v8) = 0;
  wil::init_once_nothrow__lambda_312a8970364be71481f3490781272cd3___(v9, v8, v10);
  if ( BasicUtils::s_inCrossMachineRemoteSession )
  {
    v11 = *((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<UiaManagerCrossMachineStubFactoryClassFactory,UiaManagerCrossMachineStubFactoryClassFactory,>((char *)this + 120);
    if ( v12 < 0 )
    {
      v13 = 52;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerservicehostcomponent.cpp",
        (const char *)(unsigned int)v12,
        lpdwRegister);
      return (unsigned int)v12;
    }
    v5 = CoRegisterClassObject(
           &CLSID_UiaManagerCrossMachineStubFactory,
           *((LPUNKNOWN *)this + 15),
           4u,
           1u,
           (LPDWORD)this + 32);
    if ( v5 < 0 )
    {
      v6 = 60;
      goto LABEL_5;
    }
  }
  else
  {
    v14 = *((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<UiaManagerCrossMachineProxyFactoryClassFactory,UiaManagerCrossMachineProxyFactoryClassFactory,>((char *)this + 104);
    if ( v12 < 0 )
    {
      v13 = 65;
      goto LABEL_13;
    }
    v5 = CoRegisterClassObject(
           &CLSID_UiaManagerCrossMachineProxyFactory,
           *((LPUNKNOWN *)this + 13),
           4u,
           1u,
           (LPDWORD)this + 28);
    if ( v5 < 0 )
    {
      v6 = 73;
      goto LABEL_5;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 136);
  v5 = Microsoft::WRL::Details::MakeAndInitialize<UiaManagerEndpointStateNotifierClassFactory,UiaManagerEndpointStateNotifierClassFactory,>((char *)this + 136);
  if ( v5 < 0 )
  {
    v6 = 77;
    goto LABEL_5;
  }
  v5 = CoRegisterClassObject(
         &CLSID_UiaManagerEndpointStateNotifier,
         *((LPUNKNOWN *)this + 17),
         4u,
         1u,
         (LPDWORD)this + 36);
  if ( v5 < 0 )
  {
    v6 = 85;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180014420  mov     [rsp+arg_0], rbx
0x180014425  mov     [rsp+arg_8], rsi
0x18001442a  push    rdi
0x18001442b  sub     rsp, 30h
0x18001442f  mov     rdi, rcx
0x180014432  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x180014437  mov     edx, [rax]
0x180014439  cmp     edx, 4
0x18001443c  jbe     short loc_180014450
0x18001443e  xor     r8d, r8d
0x180014441  lea     rdx, unk_1800ADB30
0x180014448  mov     rcx, rax
0x18001444b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180014450  lea     rcx, [rdi+58h]
0x180014454  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014459  lea     rcx, [rdi+58h]
0x18001445d  call    ??$MakeAndInitialize@VUiaManagerImpl@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVUiaManagerImpl@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UiaManagerImpl,UiaManagerImpl,>(UiaManagerImpl * *)
0x180014462  mov     ebx, eax
0x180014464  test    eax, eax
0x180014466  jns     short loc_180014488
0x180014468  mov     edx, 27h ; '''; void *
0x18001446d  lea     r8, aOnecoreWindows_36; "onecore\\windows\\accessibletech\\uiama"...
0x180014474  mov     r9d, ebx; char *
0x180014477  mov     rcx, [rsp+38h]; this
0x18001447c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014481  mov     eax, ebx
0x180014483  jmp     loc_18001461B
0x180014488  lea     rax, [rdi+60h]
0x18001448c  lea     rdx, [rdi-50h]; pUnk
0x180014490  mov     qword ptr [rsp+38h+lpdwRegister], rax; int
0x180014495  mov     r9d, 1; flags
0x18001449b  lea     r8d, [r9+3]; dwClsContext
0x18001449f  lea     rcx, CLSID_UiaManager; rclsid
0x1800144a6  call    cs:__imp_CoRegisterClassObject
0x1800144ac  mov     ebx, eax
0x1800144ae  test    eax, eax
0x1800144b0  jns     short loc_1800144B9
0x1800144b2  mov     edx, 2Fh ; '/'
0x1800144b7  jmp     short loc_18001446D
0x1800144b9  xor     dl, dl
0x1800144bb  call    wil__init_once_nothrow__lambda_312a8970364be71481f3490781272cd3___
0x1800144c0  cmp     cs:?s_inCrossMachineRemoteSession@BasicUtils@@0_NA, 0; bool BasicUtils::s_inCrossMachineRemoteSession
0x1800144c7  jz      loc_180014551
0x1800144cd  lea     rbx, [rdi+78h]
0x1800144d1  mov     rcx, [rbx]
0x1800144d4  mov     qword ptr [rbx], 0
0x1800144db  test    rcx, rcx
0x1800144de  jz      short loc_1800144ED
0x1800144e0  mov     rax, [rcx]
0x1800144e3  mov     rax, [rax+10h]
0x1800144e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144ec  nop
0x1800144ed  mov     rcx, rbx
0x1800144f0  call    ??$MakeAndInitialize@VUiaManagerCrossMachineStubFactoryClassFactory@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVUiaManagerCrossMachineStubFactoryClassFactory@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UiaManagerCrossMachineStubFactoryClassFactory,UiaManagerCrossMachineStubFactoryClassFactory,>(UiaManagerCrossMachineStubFactoryClassFactory * *)
0x1800144f5  mov     esi, eax
0x1800144f7  test    eax, eax
0x1800144f9  jns     short loc_18001451B
0x1800144fb  mov     edx, 34h ; '4'; void *
0x180014500  lea     r8, aOnecoreWindows_36; "onecore\\windows\\accessibletech\\uiama"...
0x180014507  mov     r9d, esi; char *
0x18001450a  mov     rcx, [rsp+38h]; this
0x18001450f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014514  mov     eax, esi
0x180014516  jmp     loc_18001461B
0x18001451b  lea     rax, [rdi+80h]
0x180014522  mov     qword ptr [rsp+38h+lpdwRegister], rax; lpdwRegister
0x180014527  mov     r9d, 1; flags
0x18001452d  lea     r8d, [r9+3]; dwClsContext
0x180014531  mov     rdx, [rbx]; pUnk
0x180014534  lea     rcx, CLSID_UiaManagerCrossMachineStubFactory; rclsid
0x18001453b  call    cs:__imp_CoRegisterClassObject
0x180014541  mov     ebx, eax
0x180014543  test    eax, eax
0x180014545  jns     short loc_1800145BC
0x180014547  mov     edx, 3Ch ; '<'
0x18001454c  jmp     loc_18001446D
0x180014551  lea     rbx, [rdi+68h]
0x180014555  mov     rcx, [rbx]
0x180014558  mov     qword ptr [rbx], 0
0x18001455f  test    rcx, rcx
0x180014562  jz      short loc_180014571
0x180014564  mov     rax, [rcx]
0x180014567  mov     rax, [rax+10h]
0x18001456b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014570  nop
0x180014571  mov     rcx, rbx
0x180014574  call    ??$MakeAndInitialize@VUiaManagerCrossMachineProxyFactoryClassFactory@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVUiaManagerCrossMachineProxyFactoryClassFactory@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UiaManagerCrossMachineProxyFactoryClassFactory,UiaManagerCrossMachineProxyFactoryClassFactory,>(UiaManagerCrossMachineProxyFactoryClassFactory * *)
0x180014579  mov     esi, eax
0x18001457b  test    eax, eax
0x18001457d  jns     short loc_180014589
0x18001457f  mov     edx, 41h ; 'A'
0x180014584  jmp     loc_180014500
0x180014589  lea     rax, [rdi+70h]
0x18001458d  mov     qword ptr [rsp+38h+lpdwRegister], rax; lpdwRegister
0x180014592  mov     r9d, 1; flags
0x180014598  lea     r8d, [r9+3]; dwClsContext
0x18001459c  mov     rdx, [rbx]; pUnk
0x18001459f  lea     rcx, CLSID_UiaManagerCrossMachineProxyFactory; rclsid
0x1800145a6  call    cs:__imp_CoRegisterClassObject
0x1800145ac  mov     ebx, eax
0x1800145ae  test    eax, eax
0x1800145b0  jns     short loc_1800145BC
0x1800145b2  mov     edx, 49h ; 'I'
0x1800145b7  jmp     loc_18001446D
0x1800145bc  lea     rsi, [rdi+88h]
0x1800145c3  mov     rcx, rsi
0x1800145c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800145cb  mov     rcx, rsi
0x1800145ce  call    ??$MakeAndInitialize@VUiaManagerEndpointStateNotifierClassFactory@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVUiaManagerEndpointStateNotifierClassFactory@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UiaManagerEndpointStateNotifierClassFactory,UiaManagerEndpointStateNotifierClassFactory,>(UiaManagerEndpointStateNotifierClassFactory * *)
0x1800145d3  mov     ebx, eax
0x1800145d5  test    eax, eax
0x1800145d7  jns     short loc_1800145E3
0x1800145d9  mov     edx, 4Dh ; 'M'
0x1800145de  jmp     loc_18001446D
0x1800145e3  lea     rax, [rdi+90h]
0x1800145ea  mov     qword ptr [rsp+38h+lpdwRegister], rax; lpdwRegister
0x1800145ef  mov     r9d, 1; flags
0x1800145f5  lea     r8d, [r9+3]; dwClsContext
0x1800145f9  mov     rdx, [rsi]; pUnk
0x1800145fc  lea     rcx, CLSID_UiaManagerEndpointStateNotifier; rclsid
0x180014603  call    cs:__imp_CoRegisterClassObject
0x180014609  mov     ebx, eax
0x18001460b  test    eax, eax
0x18001460d  jns     short loc_180014619
0x18001460f  mov     edx, 55h ; 'U'
0x180014614  jmp     loc_18001446D
0x180014619  xor     eax, eax
0x18001461b  mov     rbx, [rsp+38h+arg_0]
0x180014620  mov     rsi, [rsp+38h+arg_8]
0x180014625  add     rsp, 30h
0x180014629  pop     rdi
0x18001462a  retn
```
