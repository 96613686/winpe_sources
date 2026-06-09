# Persistence_ServiceStart(void)

- ea: `0x18002fecc`
- end: `0x1800301af`
- name: `?Persistence_ServiceStart@@YAJXZ`
- size: `739`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180047240`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001f374`
- `0x180021060`
- `0x180024ca0`
- `0x1800263ec`
- `0x18002f040`
- `0x18002fecc`
- `0x180033444`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ffba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ffba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002ff74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002ff74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003010e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003018f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003010e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003018f`

## string_xrefs

- `0x18002ff8a`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18003000c`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030175`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 Persistence_ServiceStart(void)
{
  const struct _tlgProvider_t *v0; // rax
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  const char *v2; // r9
  unsigned int LastError; // ebx
  const struct _tlgProvider_t *v4; // rax
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // esi
  __int64 v8; // rax
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPVOID *); // rbx
  __int64 v16; // rdx
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+20h] [rbp-20h] BYREF
  struct IUnknown *v18; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v21; // [rsp+70h] [rbp+30h] BYREF
  __int64 v22; // [rsp+78h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+40h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp+48h] BYREF

  v19[0] = 0;
  v21 = 0;
  v18 = 0;
  v0 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v0 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v0,
      byte_1800774C1);
  if ( v18 != g_DeviceEnumerator )
    ATL::AtlComQIPtrAssign(&v18, g_DeviceEnumerator, &GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0);
  g_PersistenceEnvironment.Version = 3;
  g_PersistenceEnvironment.Pool = 0;
  g_PersistenceEnvironment.CleanupGroup = 0;
  g_PersistenceEnvironment.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&g_PersistenceEnvironment.RaceDll = 0;
  g_PersistenceEnvironment.FinalizationCallback = 0;
  g_PersistenceEnvironment.u.Flags = 0;
  g_PersistenceEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  g_PersistenceEnvironment.Size = 72;
  g_PersistenceEnvironmentInitialized = 1;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  g_PersistenceCleanupGroup = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    g_PersistenceEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
    g_PersistenceEnvironment.CleanupGroupCancelCallback = 0;
    EnterCriticalSection(&g_PersistedControlListLock);
    v17 = &g_PersistedControlListLock;
    v4 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v4 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v4,
        &dword_18007747C);
    g_PersistenceInitialized = 1;
    v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))v18->lpVtbl[1].AddRef)(
           v18,
           &GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196,
           v19);
    LastError = v5;
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v19[0] + 24LL))(v19[0], &v21);
      LastError = v5;
      if ( v5 >= 0 )
      {
        v7 = 0;
        if ( !v21 )
        {
LABEL_24:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v17);
          LastError = 0;
          goto LABEL_25;
        }
        while ( 1 )
        {
          v24 = 0;
          v22 = 0;
          pv = 0;
          v8 = *(_QWORD *)v19[0];
          v24 = 0;
          v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v8 + 32))(v19[0], v7, &v24);
          LastError = v9;
          if ( v9 < 0 )
            break;
          v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
          v11 = **v24;
          v12 = v22;
          v22 = 0;
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v9 = v11(v10, &GUID_3ade56af_4375_4413_9c91_4c652595ab07, &v22);
          LastError = v9;
          if ( v9 < 0 )
          {
            v16 = 1209;
            goto LABEL_29;
          }
          v13 = v22;
          v14 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v22 + 32LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pv,
            0);
          v9 = v14(v13, &pv);
          LastError = v9;
          if ( v9 < 0 )
          {
            v16 = 1210;
            goto LABEL_29;
          }
          Persistence_AudioInterfaceArrival((const unsigned __int16 *)pv);
          if ( pv )
            CoTaskMemFree(pv);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
          if ( ++v7 >= v21 )
            goto LABEL_24;
        }
        v16 = 1208;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)(unsigned int)v9,
          (int)v17);
        if ( pv )
          CoTaskMemFree(pv);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        goto LABEL_12;
      }
      v6 = 1199;
    }
    else
    {
      v6 = 1196;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v5,
      (int)v17);
LABEL_12:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v17);
    goto LABEL_25;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x49C,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
                v2);
LABEL_25:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v19);
  return LastError;
}

```

## disassembly

```asm
0x18002fecc  push    rbp
0x18002fece  push    rbx
0x18002fecf  push    rsi
0x18002fed0  push    rdi
0x18002fed1  push    r14
0x18002fed3  mov     rbp, rsp
0x18002fed6  sub     rsp, 40h
0x18002feda  xor     r14d, r14d
0x18002fedd  mov     [rbp+var_10], r14
0x18002fee1  mov     [rbp+arg_0], r14d
0x18002fee5  mov     [rbp+var_18], r14
0x18002fee9  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002feee  mov     ecx, [rax]
0x18002fef0  cmp     ecx, 4
0x18002fef3  jbe     short loc_18002FF04
0x18002fef5  lea     rdx, byte_1800774C1
0x18002fefc  mov     rcx, rax
0x18002feff  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002ff04  mov     rdx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; struct IUnknown *
0x18002ff0b  cmp     [rbp+var_18], rdx
0x18002ff0f  jz      short loc_18002FF21
0x18002ff11  lea     r8, _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0; struct _GUID *
0x18002ff18  lea     rcx, [rbp+var_18]; struct IUnknown **
0x18002ff1c  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x18002ff21  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff2b  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, r14; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff32  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, r14; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff39  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, r14; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff40  xorps   xmm0, xmm0
0x18002ff43  movdqa  xmmword ptr cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff4b  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, r14; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff52  mov     dword ptr cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, r14d; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff59  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff63  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ff6d  mov     cs:?g_PersistenceEnvironmentInitialized@@3_NA, 1; bool g_PersistenceEnvironmentInitialized
0x18002ff74  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002ff7a  mov     cs:?g_PersistenceCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * g_PersistenceCleanupGroup
0x18002ff81  test    rax, rax
0x18002ff84  jnz     short loc_18002FFA2
0x18002ff86  mov     rcx, [rbp+28h]; this
0x18002ff8a  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002ff91  mov     edx, 49Ch; void *
0x18002ff96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ff9b  mov     ebx, eax
0x18002ff9d  jmp     loc_18003013F
0x18002ffa2  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ffa9  mov     cs:?g_PersistenceEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, r14; _TP_CALLBACK_ENVIRON_V3 g_PersistenceEnvironment ...
0x18002ffb0  lea     rbx, ?g_PersistedControlListLock@@3Vcritical_section@wil@@A; wil::critical_section g_PersistedControlListLock
0x18002ffb7  mov     rcx, rbx; lpCriticalSection
0x18002ffba  call    cs:__imp_EnterCriticalSection
0x18002ffc0  mov     [rbp+var_20], rbx
0x18002ffc4  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002ffc9  mov     ecx, [rax]
0x18002ffcb  cmp     ecx, 4
0x18002ffce  jbe     short loc_18002FFDF
0x18002ffd0  lea     rdx, dword_18007747C
0x18002ffd7  mov     rcx, rax
0x18002ffda  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002ffdf  mov     cs:?g_PersistenceInitialized@@3_NA, 1; bool g_PersistenceInitialized
0x18002ffe6  mov     rcx, [rbp+var_18]
0x18002ffea  mov     rax, [rcx]
0x18002ffed  lea     r8, [rbp+var_10]
0x18002fff1  lea     rdx, _GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196
0x18002fff8  mov     rax, [rax+20h]
0x18002fffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030001  mov     ebx, eax
0x180030003  test    eax, eax
0x180030005  jns     short loc_18003002E
0x180030007  mov     edx, 4ACh; void *
0x18003000c  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180030013  mov     r9d, eax; char *
0x180030016  mov     rcx, [rbp+28h]; this
0x18003001a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003001f  nop
0x180030020  lea     rcx, [rbp+var_20]
0x180030024  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180030029  jmp     loc_18003013F
0x18003002e  mov     rcx, [rbp+var_10]
0x180030032  mov     rax, [rcx]
0x180030035  lea     rdx, [rbp+arg_0]
0x180030039  mov     rax, [rax+18h]
0x18003003d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030042  mov     ebx, eax
0x180030044  test    eax, eax
0x180030046  jns     short loc_18003004F
0x180030048  mov     edx, 4AFh
0x18003004d  jmp     short loc_18003000C
0x18003004f  mov     esi, r14d
0x180030052  cmp     [rbp+arg_0], r14d
0x180030056  jbe     loc_180030133
0x18003005c  mov     [rbp+arg_18], r14
0x180030060  mov     [rbp+arg_8], r14
0x180030064  mov     [rbp+pv], r14
0x180030068  mov     rcx, [rbp+var_10]
0x18003006c  mov     rax, [rcx]
0x18003006f  mov     [rbp+arg_18], r14
0x180030073  lea     r8, [rbp+arg_18]
0x180030077  mov     edx, esi
0x180030079  mov     rax, [rax+20h]
0x18003007d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030082  mov     ebx, eax
0x180030084  test    eax, eax
0x180030086  js      loc_18003016D
0x18003008c  mov     rbx, [rbp+arg_18]
0x180030090  mov     rax, [rbx]
0x180030093  mov     rdi, [rax]
0x180030096  mov     rcx, [rbp+arg_8]
0x18003009a  mov     [rbp+arg_8], r14
0x18003009e  test    rcx, rcx
0x1800300a1  jz      short loc_1800300B0
0x1800300a3  mov     rdx, [rcx]
0x1800300a6  mov     rax, [rdx+10h]
0x1800300aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300af  nop
0x1800300b0  lea     r8, [rbp+arg_8]
0x1800300b4  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x1800300bb  mov     rcx, rbx
0x1800300be  mov     rax, rdi
0x1800300c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300c6  mov     ebx, eax
0x1800300c8  test    eax, eax
0x1800300ca  js      loc_180030166
0x1800300d0  mov     rdi, [rbp+arg_8]
0x1800300d4  mov     rax, [rdi]
0x1800300d7  mov     rbx, [rax+20h]
0x1800300db  xor     edx, edx
0x1800300dd  lea     rcx, [rbp+pv]
0x1800300e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800300e6  lea     rdx, [rbp+pv]
0x1800300ea  mov     rcx, rdi
0x1800300ed  mov     rax, rbx
0x1800300f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300f5  mov     ebx, eax
0x1800300f7  test    eax, eax
0x1800300f9  js      short loc_18003015F
0x1800300fb  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1800300ff  call    ?Persistence_AudioInterfaceArrival@@YAJPEBG@Z; Persistence_AudioInterfaceArrival(ushort const *)
0x180030104  nop
0x180030105  mov     rcx, [rbp+pv]; pv
0x180030109  test    rcx, rcx
0x18003010c  jz      short loc_180030115
0x18003010e  call    cs:__imp_CoTaskMemFree
0x180030114  nop
0x180030115  lea     rcx, [rbp+arg_8]
0x180030119  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003011e  nop
0x18003011f  lea     rcx, [rbp+arg_18]
0x180030123  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030128  inc     esi
0x18003012a  cmp     esi, [rbp+arg_0]
0x18003012d  jb      loc_18003005C
0x180030133  lea     rcx, [rbp+var_20]
0x180030137  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18003013c  mov     ebx, r14d
0x18003013f  lea     rcx, [rbp+var_18]
0x180030143  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030148  nop
0x180030149  lea     rcx, [rbp+var_10]
0x18003014d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030152  mov     eax, ebx
0x180030154  add     rsp, 40h
0x180030158  pop     r14
0x18003015a  pop     rdi
0x18003015b  pop     rsi
0x18003015c  pop     rbx
0x18003015d  pop     rbp
0x18003015e  retn
0x18003015f  mov     edx, 4BAh
0x180030164  jmp     short loc_180030172
0x180030166  mov     edx, 4B9h
0x18003016b  jmp     short loc_180030172
0x18003016d  mov     edx, 4B8h; void *
0x180030172  mov     r9d, eax; char *
0x180030175  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18003017c  mov     rcx, [rbp+28h]; this
0x180030180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030185  nop
0x180030186  mov     rcx, [rbp+pv]; pv
0x18003018a  test    rcx, rcx
0x18003018d  jz      short loc_180030196
0x18003018f  call    cs:__imp_CoTaskMemFree
0x180030195  nop
0x180030196  lea     rcx, [rbp+arg_8]
0x18003019a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003019f  nop
0x1800301a0  lea     rcx, [rbp+arg_18]
0x1800301a4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800301a9  jmp     loc_180030020
```
