# PhoneController::Initialize(InternalSinkMessageDispatcher *,IDispatcherQueue *,IPhoneLineFactory * *,uint,ICallAudioRouting *)

- ea: `0x18002b120`
- end: `0x18002b8b0`
- name: `?Initialize@PhoneController@@UEAAJPEAVInternalSinkMessageDispatcher@@PEAUIDispatcherQueue@@PEAPEAUIPhoneLineFactory@@IPEAUICallAudioRouting@@@Z`
- size: `1936`
- prototype: `__int64 __usercall@<rax>(PhoneController *__hidden this@<rcx>, struct InternalSinkMessageDispatcher *@<rdx>, struct IDispatcherQueue *@<r8>, struct IPhoneLineFactory **@<r9>, unsigned int, struct ICallAudioRouting *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005660`
- `0x180006e94`
- `0x18001de50`
- `0x18001df90`
- `0x18001e240`
- `0x18001e370`
- `0x18001ed70`
- `0x18001f514`
- `0x18002ab80`
- `0x18002b120`
- `0x18002c574`
- `0x18002c580`
- `0x18002f30c`
- `0x180034e08`
- `0x18003fbb4`
- `0x1800404a0`
- `0x180040760`
- `0x180049e24`
- `0x180051fd0`
- `0x180053970`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002b6b4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002b728`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002b6b4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002b728`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002b6e1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002b755`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002b6e1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002b755`

## string_xrefs

- `0x18002b615`: `onecoreuap\private\net\inc\phone\PhoneTestHookConfig.h`
- `0x18002b461`: `System\Accessibility`
- `0x18002b18d`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002b40b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002b5b9`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002b680`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002b7b4`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002b7de`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002b7ed`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002b860`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::Initialize(
        PhoneController *this,
        struct InternalSinkMessageDispatcher *a2,
        struct IDispatcherQueue *a3,
        struct IPhoneLineFactory **a4,
        unsigned int a5,
        struct ICallAudioRouting *a6)
{
  __int64 v10; // rcx
  char *v11; // rax
  BackTraceCollection *v12; // rcx
  char *v13; // rdi
  struct ATL::CAtlModule *v14; // rcx
  char *v15; // rax
  BackTraceCollection *v16; // rcx
  char *v17; // rdi
  struct ATL::CAtlModule *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  PhoneServiceConfig *v21; // rax
  PhoneServiceConfig *v22; // rbx
  __int64 v23; // rdx
  PhoneServiceConfig *v24; // rax
  __int64 v25; // rbx
  int v26; // eax
  BackTraceCollection *v27; // rcx
  unsigned int v28; // edi
  __int64 v29; // r9
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  void *v31; // rax
  __int64 v32; // rbx
  __int64 v33; // rdx
  ConfigSet *v34; // rax
  int v35; // eax
  BackTraceCollection *v36; // rcx
  void (__fastcall ***v37)(_QWORD, __int64); // rcx
  void *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rdx
  int v41; // eax
  void (__fastcall ***v42)(_QWORD, __int64); // rcx
  int v43; // eax
  void (*v44)(void *, unsigned __int8); // rdx
  BackTraceCollection *v45; // rcx
  __int64 v46; // r9
  int v47; // eax
  BackTraceCollection *v48; // rcx
  PhoneTestHookConfig *v49; // rax
  PhoneTestHookConfig *v50; // rdi
  __int64 v51; // rdx
  PhoneTestHookConfig *v52; // rax
  PhoneTestHookConfig *v53; // rdi
  int v54; // eax
  PhoneTestHookConfig *v55; // rcx
  int v56; // eax
  BackTraceCollection *v57; // rcx
  int v58; // eax
  BackTraceCollection *v59; // rcx
  __int64 v60; // r9
  int v61; // eax
  BackTraceCollection *v62; // rcx
  __int64 v64; // r8
  BackTraceCollection *v65; // rcx
  __int64 v66; // r8
  BackTraceCollection *v67; // rcx
  LPCRITICAL_SECTION v68[8]; // [rsp+40h] [rbp-98h] BYREF

  memset_0(v68, 0, sizeof(v68));
  AutoLockWithWatchdog::AutoLockWithWatchdog(
    (AutoLockWithWatchdog *)v68,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 224),
    "PhoneController::Initialize");
  if ( (unsigned int)PhoneController::_IsShutdown(this) )
  {
    Log_AssertionEvent_3(v10, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 277);
    if ( (unsigned int)PhoneController::_IsShutdown(this) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v11 = (char *)operator new(0x38u);
  v13 = v11;
  if ( !v11 )
  {
    v28 = -2147024882;
    BackTraceCollection::Capture(v12, -2147024882);
    Log_HREvent_12(2147942414LL, 1, v66, 19);
    BackTraceCollection::Capture(v67, -2147024882);
    v46 = 279;
    goto LABEL_78;
  }
  *(_QWORD *)(v11 + 12) = 0;
  *((_DWORD *)v11 + 5) = 0;
  v14 = ATL::_pAtlModule;
  *((_DWORD *)v11 + 2) = 0;
  *((_QWORD *)v11 + 3) = -1;
  *((_QWORD *)v11 + 4) = -1;
  *((_QWORD *)v11 + 5) = -1;
  *(_QWORD *)v11 = &ATL::CComObject<PhoneLineStorage>::`vftable';
  *((_QWORD *)v11 + 6) = 0;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v14 + 8LL))(v14);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 16LL))(v13);
  *((_QWORD *)this + 19) = v13;
  v15 = (char *)operator new(0x38u);
  v17 = v15;
  if ( !v15 )
  {
    v28 = -2147024882;
    BackTraceCollection::Capture(v16, -2147024882);
    Log_HREvent_13(2147942414LL, 1, v64, 20);
    BackTraceCollection::Capture(v65, -2147024882);
    v46 = 280;
    goto LABEL_78;
  }
  *(_QWORD *)(v15 + 12) = 0;
  *((_DWORD *)v15 + 5) = 0;
  *((_DWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 6) = 0;
  *((_QWORD *)v15 + 3) = v15 + 24;
  *((_QWORD *)v15 + 4) = v15 + 24;
  *((_QWORD *)v15 + 5) = 0;
  v18 = ATL::_pAtlModule;
  *(_QWORD *)v15 = &ATL::CComObject<PhoneCallStorage>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v18 + 8LL))(v18);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 8LL))(v17);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 8LL))(v17);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
  *((_QWORD *)this + 12) = v17;
  if ( *((_QWORD *)this + 11) )
  {
    Log_AssertionEvent_3(v19, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 282);
    if ( *((_QWORD *)this + 11) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( *((struct InternalSinkMessageDispatcher **)this + 11) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct InternalSinkMessageDispatcher *))(*(_QWORD *)a2 + 8LL))(a2);
    v20 = *((_QWORD *)this + 11);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    *((_QWORD *)this + 11) = a2;
  }
  v21 = (PhoneServiceConfig *)operator new(0x1D0u);
  v22 = v21;
  if ( !v21
    || (memset_0(v21, 0, 0x1D0u), v24 = PhoneServiceConfig::PhoneServiceConfig(v22, v23), (v25 = (__int64)v24) == 0) )
  {
    v46 = 286;
    goto LABEL_74;
  }
  v26 = ConfigSet::Initialize(v24);
  v28 = v26;
  if ( v26 < 0 )
  {
    BackTraceCollection::Capture(v27, v26);
    v29 = 287;
LABEL_19:
    Log_HREvent_7(v28, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v29);
LABEL_20:
    (**(void (__fastcall ***)(__int64, __int64))v25)(v25, 1);
LABEL_80:
    PhoneController::_LockedInitialShutDown(this);
    AutoLockWithWatchdog::~AutoLockWithWatchdog(v68);
    PhoneController::_NotLockedFinalShutDown(this);
    return v28;
  }
  v30 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 62);
  if ( (void (__fastcall ***)(_QWORD, __int64))v25 != v30 )
  {
    if ( v30 )
      (**v30)(v30, 1);
    *((_QWORD *)this + 62) = v25;
  }
  v31 = operator new(0xD68u);
  v32 = (__int64)v31;
  if ( !v31
    || (memset_0(v31, 0, 0xD68u),
        v34 = (ConfigSet *)PhoneSettingsConfig::PhoneSettingsConfig(v32, v33),
        (v25 = (__int64)v34) == 0) )
  {
    v46 = 291;
LABEL_74:
    v39 = 0;
    goto LABEL_75;
  }
  v35 = ConfigSet::Initialize(v34);
  v28 = v35;
  if ( v35 < 0 )
  {
    BackTraceCollection::Capture(v36, v35);
    v29 = 292;
    goto LABEL_19;
  }
  v37 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 61);
  if ( (void (__fastcall ***)(_QWORD, __int64))v25 != v37 )
  {
    if ( v37 )
      (**v37)(v37, 1);
    *((_QWORD *)this + 61) = v25;
  }
  v38 = operator new(0x158u);
  v39 = 0;
  v25 = (__int64)v38;
  if ( !v38 )
  {
    v46 = 297;
LABEL_75:
    v28 = -2147024882;
LABEL_79:
    Log_HREvent_7(v28, v39, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v46);
    goto LABEL_80;
  }
  memset_0(v38, 0, 0x158u);
  ConfigSet::ConfigSet(v25, v40, 0, (__int64)&qword_18009A460, (__int64)L"System\\Accessibility");
  *(_QWORD *)(v25 + 184) = 0;
  *(_QWORD *)(v25 + 152) = v25 + 168;
  *(_QWORD *)(v25 + 160) = v25 + 168;
  *(_WORD *)(v25 + 168) = 0;
  *(_QWORD *)(v25 + 216) = v25 + 232;
  *(_QWORD *)(v25 + 224) = v25 + 232;
  *(_WORD *)(v25 + 232) = 0;
  *(_QWORD *)(v25 + 280) = v25 + 296;
  *(_QWORD *)(v25 + 288) = v25 + 296;
  *(_WORD *)(v25 + 296) = 0;
  *(_QWORD *)v25 = &AccessibilitySettingsConfig::`vftable';
  *(_QWORD *)(v25 + 192) = 0;
  *(_DWORD *)(v25 + 204) = -1;
  *(_QWORD *)(v25 + 248) = 0;
  *(_QWORD *)(v25 + 256) = 0;
  *(_DWORD *)(v25 + 268) = -1;
  *(_QWORD *)(v25 + 312) = 0;
  *(_QWORD *)(v25 + 320) = 0;
  *(_DWORD *)(v25 + 332) = -1;
  v41 = ConfigSet::Initialize((ConfigSet *)v25);
  if ( v41 < 0 )
  {
    Log_HREvent_7((unsigned int)v41, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 312);
  }
  else
  {
    v42 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 63);
    if ( (void (__fastcall ***)(_QWORD, __int64))v25 != v42 )
    {
      if ( v42 )
        (**v42)(v42, 1);
      *((_QWORD *)this + 63) = v25;
    }
    v43 = PhoneController::_TTYSettingChanged(this);
    v28 = v43;
    if ( v43 < 0 )
    {
      BackTraceCollection::Capture(v45, v43);
      v46 = 302;
LABEL_78:
      v39 = 1;
      goto LABEL_79;
    }
    v47 = ConfigSet::RegisterChangeCallback(*((ConfigSet **)this + 63), v44, this, (void **)this + 71);
    v28 = v47;
    if ( v47 < 0 )
    {
      BackTraceCollection::Capture(v48, v47);
      v46 = 304;
      goto LABEL_78;
    }
    v25 = 0;
    (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)this + 8LL))(this);
  }
  v49 = (PhoneTestHookConfig *)operator new(0x350u);
  v50 = v49;
  if ( !v49 || (memset_0(v49, 0, 0x350u), v52 = PhoneTestHookConfig::PhoneTestHookConfig(v50, v51), (v53 = v52) == 0) )
  {
    v60 = 316;
    v28 = -2147024882;
LABEL_69:
    Log_HREvent_7(v28, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v60);
    if ( !v25 )
      goto LABEL_80;
    goto LABEL_20;
  }
  v54 = ConfigSet::Initialize(v52);
  if ( v54 >= 0 )
    *((_DWORD *)v53 + 38) = 1;
  else
    Log_HREvent_7((unsigned int)v54, 0, "onecoreuap\\private\\net\\inc\\phone\\PhoneTestHookConfig.h", 78);
  v55 = (PhoneTestHookConfig *)*((_QWORD *)this + 64);
  if ( v53 != v55 )
  {
    if ( v55 )
      (**(void (__fastcall ***)(PhoneTestHookConfig *, __int64))v55)(v55, 1);
    *((_QWORD *)this + 64) = v53;
  }
  v56 = PhoneController::_AdditionalInit(this, a3, a4, a5, a6);
  v28 = v56;
  if ( v56 < 0 )
  {
    BackTraceCollection::Capture(v57, v56);
    Log_HREvent_7(v28, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 320);
    if ( !v25 )
      goto LABEL_80;
    goto LABEL_20;
  }
  if ( *((_QWORD *)this + 37) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  *((_QWORD *)this + 37) = 0;
  v58 = RtlSubscribeWnfStateChangeNotification(
          (char *)this + 296,
          WNF_CELL_CONFIGURED_LINES_CAN0,
          0,
          PhoneController::_DataLineNotify,
          this,
          0,
          0,
          0);
  if ( v58 < 0 )
  {
    v28 = v58 | 0x10000000;
    BackTraceCollection::Capture(v59, v58 | 0x10000000);
    v60 = 325;
    goto LABEL_69;
  }
  (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)this + 8LL))(this);
  if ( *((_QWORD *)this + 38) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  *((_QWORD *)this + 38) = 0;
  v61 = RtlSubscribeWnfStateChangeNotification(
          (char *)this + 304,
          WNF_CELL_DATA_ENABLED_BY_USER_MODEM0,
          0,
          PhoneController::_CellDataStateChangedCallback,
          this,
          0,
          0,
          0);
  if ( v61 < 0 )
  {
    v28 = v61 | 0x10000000;
    BackTraceCollection::Capture(v62, v61 | 0x10000000);
    v60 = 334;
    goto LABEL_69;
  }
  (*(void (__fastcall **)(PhoneController *))(*(_QWORD *)this + 8LL))(this);
  if ( v25 )
    (**(void (__fastcall ***)(__int64, __int64))v25)(v25, 1);
  AutoLockWithWatchdog::~AutoLockWithWatchdog(v68);
  return 0;
}

```

## disassembly

```asm
0x18002b120  push    rbx
0x18002b122  push    rbp
0x18002b123  push    rsi
0x18002b124  push    rdi
0x18002b125  push    r12
0x18002b127  push    r13
0x18002b129  push    r14
0x18002b12b  push    r15
0x18002b12d  sub     rsp, 98h
0x18002b134  mov     rax, cs:__security_cookie
0x18002b13b  xor     rax, rsp
0x18002b13e  mov     [rsp+0D8h+var_58], rax
0x18002b146  mov     r12, [rsp+0D8h+arg_28]
0x18002b14e  mov     rbx, rdx
0x18002b151  xor     edx, edx; Val
0x18002b153  mov     r14, r8
0x18002b156  mov     rsi, rcx
0x18002b159  mov     r15, r9
0x18002b15c  lea     rcx, [rsp+0D8h+var_98]; void *
0x18002b161  lea     r8d, [rdx+40h]; Size
0x18002b165  call    memset_0
0x18002b16a  lea     rdx, [rsi+0E0h]; struct utl::recursive_mutex *
0x18002b171  lea     r8, aPhonecontrolle_82; "PhoneController::Initialize"
0x18002b178  lea     rcx, [rsp+0D8h+var_98]; this
0x18002b17d  call    ??0AutoLockWithWatchdog@@QEAA@PEAVrecursive_mutex@utl@@PEBD@Z; AutoLockWithWatchdog::AutoLockWithWatchdog(utl::recursive_mutex *,char const *)
0x18002b182  mov     rcx, rsi; this
0x18002b185  call    ?_IsShutdown@PhoneController@@IEAAHXZ; PhoneController::_IsShutdown(void)
0x18002b18a  xor     r13d, r13d
0x18002b18d  lea     rbp, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18002b194  test    eax, eax
0x18002b196  jz      short loc_18002B1B7
0x18002b198  mov     r8d, 115h
0x18002b19e  mov     rdx, rbp
0x18002b1a1  call    Log_AssertionEvent_3
0x18002b1a6  mov     rcx, rsi; this
0x18002b1a9  call    ?_IsShutdown@PhoneController@@IEAAHXZ; PhoneController::_IsShutdown(void)
0x18002b1ae  test    eax, eax
0x18002b1b0  jz      short loc_18002B1B7
0x18002b1b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b1b7  mov     ecx, 38h ; '8'; Size
0x18002b1bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b1c1  mov     rdi, rax
0x18002b1c4  test    rax, rax
0x18002b1c7  jz      loc_18002B835
0x18002b1cd  mov     [rax+0Ch], r13
0x18002b1d1  mov     [rax+14h], r13d
0x18002b1d5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002b1dc  mov     [rax+8], r13d
0x18002b1e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b1e4  mov     [rdi+18h], rax
0x18002b1e8  mov     [rdi+20h], rax
0x18002b1ec  mov     [rdi+28h], rax
0x18002b1f0  lea     rax, ??_7?$CComObject@VPhoneLineStorage@@@ATL@@6B@; const ATL::CComObject<PhoneLineStorage>::`vftable'
0x18002b1f7  mov     [rdi], rax
0x18002b1fa  mov     [rdi+30h], r13
0x18002b1fe  mov     rax, [rcx]
0x18002b201  mov     rax, [rax+8]
0x18002b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b20a  mov     rax, [rdi]
0x18002b20d  mov     rcx, rdi
0x18002b210  mov     rax, [rax+8]
0x18002b214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b219  mov     rax, [rdi]
0x18002b21c  mov     rcx, rdi
0x18002b21f  mov     rax, [rax+8]
0x18002b223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b228  mov     rax, [rdi]
0x18002b22b  mov     rcx, rdi
0x18002b22e  mov     rax, [rax+10h]
0x18002b232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b237  mov     ecx, 38h ; '8'; Size
0x18002b23c  mov     [rsi+98h], rdi
0x18002b243  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b248  mov     rdi, rax
0x18002b24b  test    rax, rax
0x18002b24e  jz      loc_18002B808
0x18002b254  mov     [rax+0Ch], r13
0x18002b258  lea     rcx, [rax+18h]
0x18002b25c  mov     [rax+14h], r13d
0x18002b260  mov     [rax+8], r13d
0x18002b264  mov     [rax+30h], r13
0x18002b268  lea     rax, ??_7?$CComObject@VPhoneCallStorage@@@ATL@@6B@; const ATL::CComObject<PhoneCallStorage>::`vftable'
0x18002b26f  mov     [rcx], rcx
0x18002b272  mov     [rcx+8], rcx
0x18002b276  mov     [rcx+10h], r13
0x18002b27a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002b281  mov     [rdi], rax
0x18002b284  mov     rax, [rcx]
0x18002b287  mov     rax, [rax+8]
0x18002b28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b290  mov     rax, [rdi]
0x18002b293  mov     rcx, rdi
0x18002b296  mov     rax, [rax+8]
0x18002b29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b29f  mov     rax, [rdi]
0x18002b2a2  mov     rcx, rdi
0x18002b2a5  mov     rax, [rax+8]
0x18002b2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2ae  mov     rax, [rdi]
0x18002b2b1  mov     rcx, rdi
0x18002b2b4  mov     rax, [rax+10h]
0x18002b2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2bd  mov     [rsi+60h], rdi
0x18002b2c1  cmp     [rsi+58h], r13
0x18002b2c5  jz      short loc_18002B2E0
0x18002b2c7  mov     r8d, 11Ah
0x18002b2cd  mov     rdx, rbp
0x18002b2d0  call    Log_AssertionEvent_3
0x18002b2d5  cmp     [rsi+58h], r13
0x18002b2d9  jz      short loc_18002B2E0
0x18002b2db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b2e0  cmp     [rsi+58h], rbx
0x18002b2e4  jz      short loc_18002B313
0x18002b2e6  test    rbx, rbx
0x18002b2e9  jz      short loc_18002B2FA
0x18002b2eb  mov     rax, [rbx]
0x18002b2ee  mov     rcx, rbx
0x18002b2f1  mov     rax, [rax+8]
0x18002b2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2fa  mov     rcx, [rsi+58h]
0x18002b2fe  test    rcx, rcx
0x18002b301  jz      short loc_18002B30F
0x18002b303  mov     rax, [rcx]
0x18002b306  mov     rax, [rax+10h]
0x18002b30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b30f  mov     [rsi+58h], rbx
0x18002b313  mov     edi, 1D0h
0x18002b318  mov     ecx, edi; Size
0x18002b31a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b31f  mov     rbx, rax
0x18002b322  test    rax, rax
0x18002b325  jz      loc_18002B7F6
0x18002b32b  mov     r8d, edi; Size
0x18002b32e  xor     edx, edx; Val
0x18002b330  mov     rcx, rax; void *
0x18002b333  call    memset_0
0x18002b338  mov     rcx, rbx; this
0x18002b33b  call    ??0PhoneServiceConfig@@QEAA@XZ; PhoneServiceConfig::PhoneServiceConfig(void)
0x18002b340  mov     rbx, rax
0x18002b343  test    rax, rax
0x18002b346  jz      loc_18002B7F6
0x18002b34c  mov     rcx, rax; this
0x18002b34f  call    ?Initialize@ConfigSet@@QEAAJH@Z; ConfigSet::Initialize(int)
0x18002b354  mov     edi, eax
0x18002b356  test    eax, eax
0x18002b358  jns     short loc_18002B38D
0x18002b35a  mov     edx, eax; int
0x18002b35c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002b361  mov     r8, rbp
0x18002b364  mov     r9d, 11Fh
0x18002b36a  mov     ebp, 1
0x18002b36f  mov     edx, ebp
0x18002b371  mov     ecx, edi
0x18002b373  call    Log_HREvent_7
0x18002b378  mov     rcx, [rbx]
0x18002b37b  mov     rax, [rcx]
0x18002b37e  mov     rcx, rbx
0x18002b381  mov     edx, ebp
0x18002b383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b388  jmp     loc_18002B870
0x18002b38d  mov     rcx, [rsi+1F0h]
0x18002b394  mov     ebp, 1
0x18002b399  cmp     rbx, rcx
0x18002b39c  jz      short loc_18002B3B7
0x18002b39e  test    rcx, rcx
0x18002b3a1  jz      short loc_18002B3B0
0x18002b3a3  mov     rax, [rcx]
0x18002b3a6  mov     edx, ebp
0x18002b3a8  mov     rax, [rax]
0x18002b3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3b0  mov     [rsi+1F0h], rbx
0x18002b3b7  mov     edi, 0D68h
0x18002b3bc  mov     ecx, edi; Size
0x18002b3be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b3c3  mov     rbx, rax
0x18002b3c6  test    rax, rax
0x18002b3c9  jz      loc_18002B7E7
0x18002b3cf  mov     r8d, edi; Size
0x18002b3d2  xor     edx, edx; Val
0x18002b3d4  mov     rcx, rax; void *
0x18002b3d7  call    memset_0
0x18002b3dc  mov     rcx, rbx
0x18002b3df  call    ??0PhoneSettingsConfig@@QEAA@W4ConfigSetAccess@@@Z; PhoneSettingsConfig::PhoneSettingsConfig(ConfigSetAccess)
0x18002b3e4  mov     rbx, rax
0x18002b3e7  test    rax, rax
0x18002b3ea  jz      loc_18002B7E7
0x18002b3f0  mov     rcx, rax; this
0x18002b3f3  call    ?Initialize@ConfigSet@@QEAAJH@Z; ConfigSet::Initialize(int)
0x18002b3f8  mov     edi, eax
0x18002b3fa  test    eax, eax
0x18002b3fc  jns     short loc_18002B417
0x18002b3fe  mov     edx, eax; int
0x18002b400  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002b405  mov     r9d, 124h
0x18002b40b  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18002b412  jmp     loc_18002B36F
0x18002b417  mov     rcx, [rsi+1E8h]
0x18002b41e  cmp     rbx, rcx
0x18002b421  jz      short loc_18002B43C
0x18002b423  test    rcx, rcx
0x18002b426  jz      short loc_18002B435
0x18002b428  mov     rax, [rcx]
0x18002b42b  mov     edx, ebp
0x18002b42d  mov     rax, [rax]
0x18002b430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b435  mov     [rsi+1E8h], rbx
0x18002b43c  mov     edi, 158h
0x18002b441  mov     ecx, edi; Size
0x18002b443  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b448  xor     edx, edx; Val
0x18002b44a  mov     rbx, rax
0x18002b44d  test    rax, rax
0x18002b450  jz      loc_18002B7D8
0x18002b456  mov     r8d, edi; Size
0x18002b459  mov     rcx, rax; void *
0x18002b45c  call    memset_0
0x18002b461  lea     rax, aSystemAccessib; "System\\Accessibility"
0x18002b468  xor     r8d, r8d
0x18002b46b  lea     r9, qword_18009A460
0x18002b472  mov     [rsp+0D8h+var_B8], rax
0x18002b477  mov     rcx, rbx
0x18002b47a  call    ??0ConfigSet@@QEAA@QEAUHKEY__@@PEBG11W4ConfigSetAccess@@@Z; ConfigSet::ConfigSet(HKEY__ * const,ushort const *,ushort const *,ushort const *,ConfigSetAccess)
0x18002b47f  lea     rcx, [rbx+0A8h]
0x18002b486  mov     [rbx+0B8h], r13
0x18002b48d  mov     [rbx+98h], rcx
0x18002b494  lea     rax, ??_7AccessibilitySettingsConfig@@6B@; const AccessibilitySettingsConfig::`vftable'
0x18002b49b  mov     [rbx+0A0h], rcx
0x18002b4a2  mov     [rcx], r13w
0x18002b4a6  lea     rcx, [rbx+0E8h]
0x18002b4ad  mov     [rbx+0D8h], rcx
0x18002b4b4  mov     [rbx+0E0h], rcx
0x18002b4bb  mov     [rcx], r13w
0x18002b4bf  lea     rcx, [rbx+128h]
0x18002b4c6  mov     [rbx+118h], rcx
0x18002b4cd  mov     [rbx+120h], rcx
0x18002b4d4  mov     [rcx], r13w
0x18002b4d8  mov     rcx, rbx; this
0x18002b4db  mov     [rbx], rax
0x18002b4de  mov     [rbx+0C0h], r13
0x18002b4e5  mov     dword ptr [rbx+0CCh], 0FFFFFFFFh
0x18002b4ef  mov     [rbx+0F8h], r13
0x18002b4f6  mov     [rbx+100h], r13
0x18002b4fd  mov     dword ptr [rbx+10Ch], 0FFFFFFFFh
0x18002b507  mov     [rbx+138h], r13
0x18002b50e  mov     [rbx+140h], r13
0x18002b515  mov     dword ptr [rbx+14Ch], 0FFFFFFFFh
0x18002b51f  call    ?Initialize@ConfigSet@@QEAAJH@Z; ConfigSet::Initialize(int)
0x18002b524  test    eax, eax
0x18002b526  js      loc_18002B5B3
0x18002b52c  mov     rcx, [rsi+1F8h]
0x18002b533  cmp     rbx, rcx
0x18002b536  jz      short loc_18002B551
0x18002b538  test    rcx, rcx
0x18002b53b  jz      short loc_18002B54A
0x18002b53d  mov     rax, [rcx]
0x18002b540  mov     edx, ebp
0x18002b542  mov     rax, [rax]
0x18002b545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b54a  mov     [rsi+1F8h], rbx
0x18002b551  mov     rcx, rsi; this
0x18002b554  call    ?_TTYSettingChanged@PhoneController@@IEAAJXZ; PhoneController::_TTYSettingChanged(void)
0x18002b559  mov     edi, eax
0x18002b55b  test    eax, eax
0x18002b55d  jns     short loc_18002B571
0x18002b55f  mov     edx, eax; int
0x18002b561  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002b566  mov     r9d, 12Eh
0x18002b56c  jmp     loc_18002B860
0x18002b571  mov     rcx, [rsi+1F8h]; this
0x18002b578  lea     r9, [rsi+238h]; void **
0x18002b57f  mov     r8, rsi; void *
0x18002b582  call    ?RegisterChangeCallback@ConfigSet@@QEAAJP6AXPEAXE@Z0PEAPEAX@Z; ConfigSet::RegisterChangeCallback(void (*)(void *,uchar),void *,void * *)
0x18002b587  mov     edi, eax
0x18002b589  test    eax, eax
0x18002b58b  jns     short loc_18002B59F
0x18002b58d  mov     edx, eax; int
0x18002b58f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002b594  mov     r9d, 130h
0x18002b59a  jmp     loc_18002B860
0x18002b59f  mov     rax, [rsi]
0x18002b5a2  mov     rcx, rsi
0x18002b5a5  mov     rbx, r13
0x18002b5a8  mov     rax, [rax+8]
0x18002b5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5b1  jmp     short loc_18002B5C9
0x18002b5b3  mov     r9d, 138h
0x18002b5b9  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18002b5c0  xor     edx, edx
0x18002b5c2  mov     ecx, eax
0x18002b5c4  call    Log_HREvent_7
0x18002b5c9  mov     ecx, 350h; Size
0x18002b5ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b5d3  mov     rdi, rax
0x18002b5d6  test    rax, rax
0x18002b5d9  jz      loc_18002B7A9
0x18002b5df  xor     edx, edx; Val
0x18002b5e1  mov     r8d, 350h; Size
0x18002b5e7  mov     rcx, rax; void *
0x18002b5ea  call    memset_0
0x18002b5ef  mov     rcx, rdi; this
  ... truncated ...
```
