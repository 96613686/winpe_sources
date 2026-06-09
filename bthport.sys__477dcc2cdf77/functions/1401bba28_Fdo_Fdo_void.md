# Fdo::~Fdo(void)

- ea: `0x1401bba28`
- end: `0x1401bbcd1`
- name: `??1Fdo@@AEAA@XZ`
- size: `681`
- prototype: `void __fastcall(Fdo *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002a280`

## callees

- `0x140005b4c`
- `0x14001029c`
- `0x1400102bc`
- `0x140013014`
- `0x14001c5dc`
- `0x14001c5fc`
- `0x14001c6a4`
- `0x140020574`
- `0x140029cb8`
- `0x14002a504`
- `0x14002b330`
- `0x140055748`
- `0x1400776c8`
- `0x1400777ac`
- `0x1400b6434`
- `0x1400bcc5c`
- `0x14012e3e0`
- `0x14013ed5c`
- `0x14014b5a4`
- `0x14014d0c4`
- `0x140164690`
- `0x1401b6d24`
- `0x1401bba28`
- `0x1401bcb90`
- `0x1401f2a08`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1401bbb54`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1401bbb54`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1401bbac1`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1401bbac1`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1401bbb71`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1401bbb71`

## pseudocode

```c
void __fastcall Fdo::~Fdo(Fdo *this)
{
  unsigned int RecorderLog; // eax
  _QWORD *v3; // rcx
  __int64 v4; // r10
  int v5; // edx
  int v6; // r8d
  void *v7; // rcx
  struct HCI_INTERFACE **v8; // rsi
  _QWORD *v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  void *v12; // rcx
  _SMP_INTERFACE *v13; // rcx
  struct L2CAP_INTERFACE *v14; // rcx
  struct _SCO_INTERFACE *v15; // rcx
  char v16; // [rsp+80h] [rbp+8h] BYREF

  RecorderLog = (unsigned int)Fdo::GetRecorderLog(this);
  WPP_RECORDER_AND_TRACE_SF_q(
    *(_QWORD *)(v4 + 24),
    v5,
    v6,
    RecorderLog,
    4,
    v6,
    29,
    (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
    *v3);
  _InterlockedCompareExchange64(&qword_140197C10, 0, *((_QWORD *)this + 103));
  Fdo::LogDriverRemoveEvent(this);
  BthSetPolicyChangedCallback(0, 0);
  v7 = (void *)*((_QWORD *)this + 171);
  if ( v7 )
  {
    PoUnregisterPowerSettingCallback(v7);
    *((_QWORD *)this + 171) = 0;
  }
  v8 = (struct HCI_INTERFACE **)((char *)this + 1184);
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( *v8 )
      HCI_Shutdown(*v8);
    SleepStudyComponent::Uninitialize((SleepStudyComponent *)((char *)this + 1384));
    ErrorRecovery::Uninitialize((ErrorRecovery *)((char *)this + 1416));
  }
  else
  {
    SleepStudyComponent::Uninitialize((SleepStudyComponent *)((char *)this + 1384));
    ErrorRecovery::Uninitialize((ErrorRecovery *)((char *)this + 1416));
    if ( *v8 )
      HCI_Shutdown(*v8);
  }
  IoAcquireRemoveLockEx(
    (PIO_REMOVE_LOCK)((char *)this + 872),
    "EvtObjectContextCleanup",
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\fdo.cpp",
    0x20Du,
    0x20u);
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)((char *)this + 872), "EvtObjectContextCleanup", 0x20u);
  wil::acquire_fast_mutex_with_critical_region(&v16, &dword_140197C20);
  v9 = (_QWORD *)((char *)this + 8);
  v10 = *((_QWORD *)this + 1);
  if ( *(Fdo **)(v10 + 8) != (Fdo *)((char *)this + 8) || (v11 = (_QWORD *)*((_QWORD *)this + 2), (_QWORD *)*v11 != v9) )
    __fastfail(3u);
  *v11 = v10;
  *(_QWORD *)(v10 + 8) = v11;
  *((_QWORD *)this + 2) = (char *)this + 8;
  *v9 = v9;
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v16);
  BthCleanUpFakePdoExtensions((struct DEVICE_EXTENSION *)((char *)this + 816));
  if ( *((_QWORD *)this + 108) )
  {
    *((_QWORD *)this + 108) = 0;
    utl::default_delete<_SDP_DATABASE>::operator()();
  }
  v12 = (void *)*((_QWORD *)this + 150);
  if ( v12 )
  {
    SdpInt_Destroy(v12);
    *((_QWORD *)this + 150) = 0;
  }
  v13 = (_SMP_INTERFACE *)*((_QWORD *)this + 153);
  if ( v13 )
  {
    SMPInt_Destroy(v13);
    *((_QWORD *)this + 153) = 0;
  }
  v14 = (struct L2CAP_INTERFACE *)*((_QWORD *)this + 149);
  if ( v14 )
  {
    L2CapInt_Release(v14);
    *((_QWORD *)this + 149) = 0;
  }
  v15 = (struct _SCO_INTERFACE *)*((_QWORD *)this + 151);
  if ( v15 )
  {
    ScoInt_Release(v15);
    *((_QWORD *)this + 151) = 0;
  }
  if ( *v8 )
  {
    HCI_VS_MSFT_TrackedFiltersCleanup(*v8);
    HCI_DibDrainDestructionList(*v8);
    HCI_Release(*v8, *v8);
    *v8 = 0;
  }
  PowerCoordinator::PowerReference::Reset((PowerCoordinator::PowerReference *)this + 101);
  DEVICE_EXTENSION::~DEVICE_EXTENSION((DEVICE_EXTENSION *)((char *)this + 816));
  wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>((char *)this + 800);
  Controller::~Controller((Controller *)((char *)this + 48));
  wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&void WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&void WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>((char *)this + 40);
  wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&void WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&void WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>((char *)this + 32);
}

```

## disassembly

```asm
0x1401bba28  push    rbx
0x1401bba2a  push    rbp
0x1401bba2b  push    rsi
0x1401bba2c  push    rdi
0x1401bba2d  sub     rsp, 58h
0x1401bba31  mov     rdi, rcx
0x1401bba34  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bba3b  mov     r8d, 1
0x1401bba41  mov     eax, [r10+2Ch]
0x1401bba45  test    r8b, al
0x1401bba48  jz      short loc_1401BBA56
0x1401bba4a  cmp     byte ptr [r10+29h], 4
0x1401bba4f  jb      short loc_1401BBA56
0x1401bba51  mov     dl, r8b
0x1401bba54  jmp     short loc_1401BBA58
0x1401bba56  xor     dl, dl
0x1401bba58  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401bba5d  mov     r9, [rcx]
0x1401bba60  lea     rcx, WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids
0x1401bba67  mov     [rsp+78h+var_38], r9
0x1401bba6c  mov     r9, rax
0x1401bba6f  mov     [rsp+78h+var_40], rcx
0x1401bba74  mov     rcx, [r10+18h]
0x1401bba78  mov     [rsp+78h+var_48], 1Dh
0x1401bba7f  mov     [rsp+78h+var_50], r8d
0x1401bba84  mov     byte ptr [rsp+78h+RemlockSize], 4
0x1401bba89  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401bba8e  lea     rbp, [rdi+330h]
0x1401bba95  xor     ecx, ecx
0x1401bba97  mov     rax, [rbp+8]
0x1401bba9b  lock cmpxchg cs:qword_140197C10, rcx
0x1401bbaa4  mov     rcx, rdi; this
0x1401bbaa7  call    ?LogDriverRemoveEvent@Fdo@@AEAAXXZ; Fdo::LogDriverRemoveEvent(void)
0x1401bbaac  xor     edx, edx
0x1401bbaae  xor     ecx, ecx
0x1401bbab0  call    BthSetPolicyChangedCallback
0x1401bbab5  mov     rcx, [rdi+558h]; Handle
0x1401bbabc  test    rcx, rcx
0x1401bbabf  jz      short loc_1401BBAD8
0x1401bbac1  call    cs:__imp_PoUnregisterPowerSettingCallback
0x1401bbac8  nop     dword ptr [rax+rax+00h]
0x1401bbacd  mov     qword ptr [rdi+558h], 0
0x1401bbad8  lea     rsi, [rdi+4A0h]
0x1401bbadf  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1401bbae4  test    eax, eax
0x1401bbae6  jz      short loc_1401BBB0F
0x1401bbae8  mov     rcx, [rsi]; struct HCI_INTERFACE *
0x1401bbaeb  test    rcx, rcx
0x1401bbaee  jz      short loc_1401BBAF5
0x1401bbaf0  call    ?HCI_Shutdown@@YAXPEAUHCI_INTERFACE@@@Z; HCI_Shutdown(HCI_INTERFACE *)
0x1401bbaf5  lea     rcx, [rbp+238h]; this
0x1401bbafc  call    ?Uninitialize@SleepStudyComponent@@QEAAXXZ; SleepStudyComponent::Uninitialize(void)
0x1401bbb01  lea     rcx, [rbp+258h]; this
0x1401bbb08  call    ?Uninitialize@ErrorRecovery@@QEAAXXZ; ErrorRecovery::Uninitialize(void)
0x1401bbb0d  jmp     short loc_1401BBB34
0x1401bbb0f  lea     rcx, [rdi+568h]; this
0x1401bbb16  call    ?Uninitialize@SleepStudyComponent@@QEAAXXZ; SleepStudyComponent::Uninitialize(void)
0x1401bbb1b  lea     rcx, [rbp+258h]; this
0x1401bbb22  call    ?Uninitialize@ErrorRecovery@@QEAAXXZ; ErrorRecovery::Uninitialize(void)
0x1401bbb27  mov     rcx, [rsi]; struct HCI_INTERFACE *
0x1401bbb2a  test    rcx, rcx
0x1401bbb2d  jz      short loc_1401BBB34
0x1401bbb2f  call    ?HCI_Shutdown@@YAXPEAUHCI_INTERFACE@@@Z; HCI_Shutdown(HCI_INTERFACE *)
0x1401bbb34  mov     r9d, 20Dh; Line
0x1401bbb3a  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1401bbb42  lea     r8, aOnecoreDrivers_54; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1401bbb49  lea     rdx, aEvtobjectconte; "EvtObjectContextCleanup"
0x1401bbb50  lea     rcx, [rbp+38h]; RemoveLock
0x1401bbb54  call    cs:__imp_IoAcquireRemoveLockEx
0x1401bbb5b  nop     dword ptr [rax+rax+00h]
0x1401bbb60  mov     r8d, 20h ; ' '; RemlockSize
0x1401bbb66  lea     rdx, aEvtobjectconte; "EvtObjectContextCleanup"
0x1401bbb6d  lea     rcx, [rbp+38h]; RemoveLock
0x1401bbb71  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1401bbb78  nop     dword ptr [rax+rax+00h]
0x1401bbb7d  lea     rdx, dword_140197C20
0x1401bbb84  lea     rcx, [rsp+78h+arg_0]
0x1401bbb8c  call    ?acquire_fast_mutex_with_critical_region@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_FAST_MUTEX@@@Z
0x1401bbb91  lea     rax, [rdi+8]
0x1401bbb95  mov     rdx, [rax]
0x1401bbb98  cmp     [rdx+8], rax
0x1401bbb9c  jnz     loc_1401BBCCA
0x1401bbba2  mov     rcx, [rax+8]
0x1401bbba6  cmp     [rcx], rax
0x1401bbba9  jnz     loc_1401BBCCA
0x1401bbbaf  mov     [rcx], rdx
0x1401bbbb2  mov     [rdx+8], rcx
0x1401bbbb6  lea     rcx, [rsp+78h+arg_0]
0x1401bbbbe  mov     [rax+8], rax
0x1401bbbc2  mov     [rax], rax
0x1401bbbc5  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1401bbbca  mov     rcx, rbp; struct DEVICE_EXTENSION *
0x1401bbbcd  call    ?BthCleanUpFakePdoExtensions@@YAXPEAUDEVICE_EXTENSION@@@Z; BthCleanUpFakePdoExtensions(DEVICE_EXTENSION *)
0x1401bbbd2  mov     rdx, [rdi+360h]
0x1401bbbd9  test    rdx, rdx
0x1401bbbdc  jz      short loc_1401BBBEE
0x1401bbbde  mov     qword ptr [rdi+360h], 0
0x1401bbbe9  call    ??R?$default_delete@U_SDP_DATABASE@@@utl@@QEBAXPEAU_SDP_DATABASE@@@Z; utl::default_delete<_SDP_DATABASE>::operator()(_SDP_DATABASE *)
0x1401bbbee  mov     rcx, [rdi+4B0h]; P
0x1401bbbf5  test    rcx, rcx
0x1401bbbf8  jz      short loc_1401BBC0A
0x1401bbbfa  call    ?SdpInt_Destroy@@YAXPEAU_SDP_INTERFACE@@@Z; SdpInt_Destroy(_SDP_INTERFACE *)
0x1401bbbff  mov     qword ptr [rdi+4B0h], 0
0x1401bbc0a  mov     rcx, [rdi+4C8h]; this
0x1401bbc11  test    rcx, rcx
0x1401bbc14  jz      short loc_1401BBC26
0x1401bbc16  call    ?SMPInt_Destroy@@YAXPEAU_SMP_INTERFACE@@@Z; SMPInt_Destroy(_SMP_INTERFACE *)
0x1401bbc1b  mov     qword ptr [rdi+4C8h], 0
0x1401bbc26  mov     rcx, [rdi+4A8h]; struct L2CAP_INTERFACE *
0x1401bbc2d  test    rcx, rcx
0x1401bbc30  jz      short loc_1401BBC42
0x1401bbc32  call    ?L2CapInt_Release@@YAKPEAUL2CAP_INTERFACE@@@Z; L2CapInt_Release(L2CAP_INTERFACE *)
0x1401bbc37  mov     qword ptr [rdi+4A8h], 0
0x1401bbc42  mov     rcx, [rdi+4B8h]; struct _SCO_INTERFACE *
0x1401bbc49  test    rcx, rcx
0x1401bbc4c  jz      short loc_1401BBC5E
0x1401bbc4e  call    ?ScoInt_Release@@YAKPEAU_SCO_INTERFACE@@@Z; ScoInt_Release(_SCO_INTERFACE *)
0x1401bbc53  mov     qword ptr [rdi+4B8h], 0
0x1401bbc5e  mov     rcx, [rsi]; struct HCI_INTERFACE *
0x1401bbc61  test    rcx, rcx
0x1401bbc64  jz      short loc_1401BBC85
0x1401bbc66  call    ?HCI_VS_MSFT_TrackedFiltersCleanup@@YAXPEAUHCI_INTERFACE@@@Z; HCI_VS_MSFT_TrackedFiltersCleanup(HCI_INTERFACE *)
0x1401bbc6b  mov     rcx, [rsi]; struct HCI_INTERFACE *
0x1401bbc6e  call    ?HCI_DibDrainDestructionList@@YAXPEAUHCI_INTERFACE@@@Z; HCI_DibDrainDestructionList(HCI_INTERFACE *)
0x1401bbc73  mov     rcx, [rsi]; struct HCI_INTERFACE *
0x1401bbc76  mov     rdx, rcx; void *
0x1401bbc79  call    ?HCI_Release@@YAJPEAUHCI_INTERFACE@@PEAX@Z; HCI_Release(HCI_INTERFACE *,void *)
0x1401bbc7e  mov     qword ptr [rsi], 0
0x1401bbc85  lea     rcx, [rdi+650h]; this
0x1401bbc8c  call    ?Reset@PowerReference@PowerCoordinator@@QEAAXXZ; PowerCoordinator::PowerReference::Reset(void)
0x1401bbc91  mov     rcx, rbp; this
0x1401bbc94  call    ??1DEVICE_EXTENSION@@QEAA@XZ; DEVICE_EXTENSION::~DEVICE_EXTENSION(void)
0x1401bbc99  lea     rcx, [rdi+320h]
0x1401bbca0  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x1401bbca5  lea     rcx, [rdi+30h]; this
0x1401bbca9  call    ??1Controller@@QEAA@XZ; Controller::~Controller(void)
0x1401bbcae  lea     rcx, [rdi+28h]
0x1401bbcb2  call    ??1?$unique_storage@U?$resource_policy@PEAURECORDER_LOG__@@P6AXPEAU1@@Z$1?WppRecorderLogCloseFunction@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>(void)
0x1401bbcb7  lea     rcx, [rdi+20h]
0x1401bbcbb  call    ??1?$unique_storage@U?$resource_policy@PEAURECORDER_LOG__@@P6AXPEAU1@@Z$1?WppRecorderLogCloseFunction@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>(void)
0x1401bbcc0  add     rsp, 58h
0x1401bbcc4  pop     rdi
0x1401bbcc5  pop     rsi
0x1401bbcc6  pop     rbp
0x1401bbcc7  pop     rbx
0x1401bbcc8  retn
0x1401bbcca  mov     ecx, 3
0x1401bbccf  int     29h; Win8: RtlFailFast(ecx)
```
