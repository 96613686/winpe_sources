# ServiceMain(ulong,ushort * *)

- ea: `0x180020310`
- end: `0x1800204f0`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `480`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callees

- `0x18001d00c`
- `0x18001e118`
- `0x18001e42c`
- `0x18001e4d8`
- `0x18001f454`
- `0x18001fd3c`
- `0x18001fdc8`
- `0x180020310`
- `0x1800204f8`
- `0x180020a50`
- `0x1800210d4`
- `0x180021104`
- `0x18002115c`
- `0x18005b56c`
- `0x18005bc94`
- `0x18009f9ac`
- `0x18009f9d4`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002036b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002036b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002044a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002044a`

## string_xrefs

- `0x1800203b9`: `onecore\base\devices\cam\svc\servicemain.cpp`
- `0x180020477`: `onecore\base\devices\cam\svc\servicemain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  bool v2; // cl
  int v3; // eax
  wil::details::in1diag3 *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers *v9; // rcx
  int v10; // edx
  Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers *v11; // rcx
  int v12; // ebx
  void *v13; // rdx
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 *v18; // [rsp+28h] [rbp-D8h]
  _BYTE *v19; // [rsp+30h] [rbp-D0h]
  char v20; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[224]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  int v24; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+158h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_329f17ae543231aead129cd668c645b8_Traceguids);
  }
  LOBYTE(v24) = 0;
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v21 = UnbiasedTime;
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v22);
  *(_QWORD *)v17 = &v24;
  v18 = &v21;
  v19 = v22;
  v20 = 1;
  v3 = Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::InitializeGlobals(v2);
  v4 = retaddr;
  if ( v3 < 0 )
  {
    v5 = 115;
LABEL_7:
    wil::details::in1diag3::_Log_Hr(
      v4,
      (void *)v5,
      (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
      (const char *)(unsigned int)v3,
      v17[0]);
    goto LABEL_21;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57337766>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57337766>::GetImpl'::`2'::impl) )
  {
    v3 = Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::Initialize();
    v4 = retaddr;
    if ( v3 < 0 )
    {
      v5 = 126;
      goto LABEL_7;
    }
  }
  LOBYTE(v7) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1>::GetImpl'::`2'::impl,
    v6,
    v7);
  LOBYTE(v8) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl'::`2'::impl,
    v8);
  if ( !Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(v9)
    || (v12 = Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::Initialize(v11, v10),
        CapabilityAccessTelemetry::InitializeCAMStorageDatabase(v12),
        v12 >= 0) )
  {
    ServiceGlobals::g_status.dwControlsAccepted = 128;
    ServiceGlobals::g_statusHandle = RegisterServiceCtrlHandlerExW(L"camsvc", ServiceControlCallback, 0);
    if ( ServiceGlobals::g_statusHandle )
    {
      v16 = ServiceStart();
      if ( v16 >= 0 )
      {
        LOBYTE(v24) = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_329f17ae543231aead129cd668c645b8_Traceguids);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
          (const char *)(unsigned int)v16,
          v17[0]);
        ServiceStop();
      }
    }
    else
    {
      wil::details::in1diag3::_Log_NullAlloc(retaddr, v13, v14, v15);
    }
  }
LABEL_21:
  v20 = 0;
  lambda_21b9f3a5f3fb4878c7ace3bf2791e00d_::operator()(v17);
  wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v22);
}

```

## disassembly

```asm
0x180020310  mov     [rsp-8+arg_0], rbx
0x180020315  mov     [rsp-8+arg_8], rsi
0x18002031a  push    rbp
0x18002031b  lea     rbp, [rsp-30h]
0x180020320  sub     rsp, 130h
0x180020327  lea     rsi, WPP_GLOBAL_Control
0x18002032e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020335  cmp     rcx, rsi
0x180020338  jz      short loc_18002035B
0x18002033a  test    byte ptr [rcx+1Ch], 1
0x18002033e  jz      short loc_18002035B
0x180020340  cmp     byte ptr [rcx+19h], 5
0x180020344  jb      short loc_18002035B
0x180020346  mov     edx, 0Ah
0x18002034b  lea     r8, WPP_329f17ae543231aead129cd668c645b8_Traceguids
0x180020352  mov     rcx, [rcx+10h]
0x180020356  call    WPP_SF_
0x18002035b  mov     byte ptr [rbp+30h+arg_10], 0
0x18002035f  mov     [rbp+30h+UnbiasedTime], 0
0x180020367  lea     rcx, [rbp+30h+UnbiasedTime]; UnbiasedTime
0x18002036b  call    cs:__imp_QueryUnbiasedInterruptTime
0x180020371  mov     rax, [rbp+30h+UnbiasedTime]
0x180020375  mov     [rsp+130h+var_F0], rax
0x18002037a  lea     rcx, [rsp+130h+var_E0]; this
0x18002037f  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x180020384  nop
0x180020385  lea     rax, [rbp+30h+arg_10]
0x180020389  mov     qword ptr [rsp+130h+var_110], rax; int
0x18002038e  lea     rax, [rsp+130h+var_F0]
0x180020393  mov     [rsp+130h+var_108], rax
0x180020398  lea     rax, [rsp+130h+var_E0]
0x18002039d  mov     [rsp+130h+var_100], rax
0x1800203a2  mov     [rsp+130h+var_F8], 1
0x1800203a7  call    ?InitializeGlobals@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAJ_N@Z; Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::InitializeGlobals(bool)
0x1800203ac  mov     rcx, [rbp+38h]; this
0x1800203b0  test    eax, eax
0x1800203b2  jns     short loc_1800203CD
0x1800203b4  mov     edx, 73h ; 's'; void *
0x1800203b9  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x1800203c0  mov     r9d, eax; char *
0x1800203c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800203c8  jmp     loc_1800204C1
0x1800203cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57337766@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57337766@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57337766> `wil::Feature<__WilFeatureTraits_Feature_57337766>::GetImpl(void)'::`2'::impl
0x1800203d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57337766@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57337766>::__private_IsEnabled(void)
0x1800203d9  test    al, al
0x1800203db  jz      short loc_1800203F1
0x1800203dd  call    ?Initialize@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAJXZ; Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::Initialize(void)
0x1800203e2  mov     rcx, [rbp+38h]
0x1800203e6  test    eax, eax
0x1800203e8  jns     short loc_1800203F1
0x1800203ea  mov     edx, 7Eh ; '~'
0x1800203ef  jmp     short loc_1800203B9
0x1800203f1  mov     r8b, 3
0x1800203f4  mov     dl, 1
0x1800203f6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1> `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1>::GetImpl(void)'::`2'::impl
0x1800203fd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase_Wave1>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180020402  mov     dl, 1
0x180020404  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase> `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl(void)'::`2'::impl
0x18002040b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180020410  call    ?IsPresent@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(void)
0x180020415  test    al, al
0x180020417  jz      short loc_18002042F
0x180020419  call    ?Initialize@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YAJH@Z; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::Initialize(int)
0x18002041e  mov     ebx, eax
0x180020420  mov     ecx, eax; int
0x180020422  call    ?InitializeCAMStorageDatabase@CapabilityAccessTelemetry@@SAXJ@Z; CapabilityAccessTelemetry::InitializeCAMStorageDatabase(long)
0x180020427  test    ebx, ebx
0x180020429  js      loc_1800204C1
0x18002042f  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 80h; _SERVICE_STATUS ServiceGlobals::g_status ...
0x180020439  xor     r8d, r8d; lpContext
0x18002043c  lea     rdx, ?ServiceControlCallback@@YAKKKPEAX0@Z; lpHandlerProc
0x180020443  lea     rcx, Annotation; "camsvc"
0x18002044a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180020450  mov     cs:?g_statusHandle@ServiceGlobals@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ServiceGlobals::g_statusHandle
0x180020457  mov     rcx, [rbp+38h]; this
0x18002045b  test    rax, rax
0x18002045e  jnz     short loc_180020467
0x180020460  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x180020465  jmp     short loc_1800204C1
0x180020467  call    ?ServiceStart@@YAJXZ; ServiceStart(void)
0x18002046c  mov     rcx, [rbp+38h]; this
0x180020470  test    eax, eax
0x180020472  jns     short loc_18002048F
0x180020474  mov     r9d, eax; char *
0x180020477  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x18002047e  mov     edx, 0BFh; void *
0x180020483  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020488  call    ?ServiceStop@@YAJXZ; ServiceStop(void)
0x18002048d  jmp     short loc_1800204C1
0x18002048f  mov     byte ptr [rbp+30h+arg_10], 1
0x180020493  mov     rcx, cs:WPP_GLOBAL_Control
0x18002049a  cmp     rcx, rsi
0x18002049d  jz      short loc_1800204C1
0x18002049f  test    byte ptr [rcx+1Ch], 1
0x1800204a3  jz      short loc_1800204C1
0x1800204a5  cmp     byte ptr [rcx+19h], 5
0x1800204a9  jb      short loc_1800204C1
0x1800204ab  mov     edx, 0Bh
0x1800204b0  lea     r8, WPP_329f17ae543231aead129cd668c645b8_Traceguids
0x1800204b7  mov     rcx, [rcx+10h]
0x1800204bb  call    WPP_SF_
0x1800204c0  nop
0x1800204c1  mov     [rsp+130h+var_F8], 0
0x1800204c6  lea     rcx, [rsp+130h+var_110]
0x1800204cb  call    _lambda_21b9f3a5f3fb4878c7ace3bf2791e00d___operator__
0x1800204d0  nop
0x1800204d1  lea     rcx, [rsp+130h+var_E0]; this
0x1800204d6  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x1800204db  lea     r11, [rsp+130h+var_s0]
0x1800204e3  mov     rbx, [r11+10h]
0x1800204e7  mov     rsi, [r11+18h]
0x1800204eb  mov     rsp, r11
0x1800204ee  pop     rbp
0x1800204ef  retn
```
