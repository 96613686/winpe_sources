# CAudioSessionManagerClient::~CAudioSessionManagerClient(void)

- ea: `0x18002824c`
- end: `0x180028507`
- name: `??1CAudioSessionManagerClient@@UEAA@XZ`
- size: `699`
- prototype: `void __fastcall(CAudioSessionManagerClient *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028210`

## callees

- `0x180007f00`
- `0x18000c55c`
- `0x18000cd10`
- `0x18000cf24`
- `0x18000d1a8`
- `0x18000d244`
- `0x18002824c`
- `0x180028694`
- `0x180028a6c`
- `0x180028b6c`
- `0x180028bb0`
- `0x18005e434`
- `0x1800b1f3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028341`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028341`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002843d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028452`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800284c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002843d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028452`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800284c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028304`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028375`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028304`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028375`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002838c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002838c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180028399`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180028399`
- `MMDevAPI!__imp_UnregisterMediaCallback` at `0x180028322`
- `MMDevAPI!__imp_UnregisterMediaCallback` at `0x180028322`

## pseudocode

```c
void __fastcall CAudioSessionManagerClient::~CAudioSessionManagerClient(CAudioSessionManagerClient *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  CAudioSessionManagerClient *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  struct _TP_WORK *v8; // rcx
  CAudioSessionManagerClient::SessionEntry *v9; // rcx
  __int64 v10; // rcx
  CAudioSessionManagerClient::SessionEntry *v11; // rcx
  CAudioSessionManagerClient *v12; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)this = &CAudioSessionManagerClient::`vftable';
  *((_QWORD *)this + 1) = &CAudioSessionManagerClient::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &CAudioSessionManagerClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionManager2,IAudioSessionManager,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionManagerInternal,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &CAudioSessionManagerClient::`vftable'{for `IAudioSessionManagerInternal'};
  *((_QWORD *)this + 4) = &CAudioSessionManagerClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 5) = &CAudioSessionManagerClient::`vftable'{for `ICrossVmMediaNotificationConsumer'};
  *((_QWORD *)this + 6) = &CAudioSessionManagerClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  if ( *((_BYTE *)this + 265) )
  {
    CAudioSessionManagerClient::DeleteAudioSessionClientNotification(v3, (void **)this + 21);
    *((_BYTE *)this + 265) = 0;
  }
  CLockedList_AllowDuplicates<IAudioVolumeDuckNotification,1>::ForEachEntry((LPCRITICAL_SECTION)((char *)this + 352));
  if ( v2 )
    LeaveCriticalSection(v2);
  v5 = *((_QWORD *)this + 23);
  if ( v5 )
  {
    if ( *((_BYTE *)this + 266) )
    {
      UnregisterMediaCallback(v5, v4);
      *((_BYTE *)this + 266) = 0;
    }
    wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset((char *)this + 184);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  v6 = *((_QWORD *)this + 58);
  v7 = *((_QWORD *)this + 57);
  if ( v7 != v6 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v7, v6);
    *((_QWORD *)this + 58) = *((_QWORD *)this + 57);
  }
  if ( this != (CAudioSessionManagerClient *)-416LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  v8 = (struct _TP_WORK *)*((_QWORD *)this + 60);
  if ( v8 )
  {
    WaitForThreadpoolWorkCallbacks(v8, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 60));
  }
  v9 = (CAudioSessionManagerClient::SessionEntry *)*((_QWORD *)this + 35);
  if ( v9 != *((CAudioSessionManagerClient::SessionEntry **)this + 36) )
  {
    std::_Destroy_range<std::allocator<CAudioSessionManagerClient::SessionEntry>>(v9);
    *((_QWORD *)this + 36) = *((_QWORD *)this + 35);
  }
  if ( *((_QWORD *)this + 21) )
  {
    v12 = this;
    lambda_e3f68923eb8857d5d52761db6818aa5c_::operator()(&v12);
  }
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 496);
  v10 = *((_QWORD *)this + 57);
  if ( v10 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v10, *((_QWORD *)this + 58));
    std::_Deallocate<16>(
      *((_QWORD *)this + 57),
      (*((_QWORD *)this + 59) - *((_QWORD *)this + 57)) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)this + 57) = 0;
    *((_QWORD *)this + 58) = 0;
    *((_QWORD *)this + 59) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  CLockedList_AllowDuplicates<IAudioSessionEvents,1>::~CLockedList_AllowDuplicates<IAudioSessionEvents,1>((char *)this + 352);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  v11 = (CAudioSessionManagerClient::SessionEntry *)*((_QWORD *)this + 35);
  if ( v11 )
  {
    std::_Destroy_range<std::allocator<CAudioSessionManagerClient::SessionEntry>>(v11);
    std::_Deallocate<16>(*((_QWORD *)this + 35), 8 * ((__int64)(*((_QWORD *)this + 37) - *((_QWORD *)this + 35)) >> 3));
    *((_QWORD *)this + 35) = 0;
    *((_QWORD *)this + 36) = 0;
    *((_QWORD *)this + 37) = 0;
  }
  DeleteCriticalSection(v2);
  std::wstring::~wstring((char *)this + 192);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 184);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 160);
  CLockedList_AllowDuplicates<IAudioSessionNotification,1>::~CLockedList_AllowDuplicates<IAudioSessionNotification,1>((char *)this + 96);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionManager2,IAudioSessionManager,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionManagerInternal,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionManager2,IAudioSessionManager,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionManagerInternal,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18002824c  push    rbx
0x18002824e  push    rbp
0x18002824f  push    rsi
0x180028250  push    rdi
0x180028251  push    r14
0x180028253  push    r15
0x180028255  sub     rsp, 38h
0x180028259  mov     rbx, rcx
0x18002825c  lea     rax, ??_7CAudioSessionManagerClient@@6B@; const CAudioSessionManagerClient::`vftable'
0x180028263  mov     [rcx], rax
0x180028266  lea     rax, ??_7CAudioSessionManagerClient@@6BIWeakReferenceSource@@@; const CAudioSessionManagerClient::`vftable'{for `IWeakReferenceSource'}
0x18002826d  mov     [rcx+8], rax
0x180028271  lea     rax, ??_7CAudioSessionManagerClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ChainInterfaces@UIAudioSessionManager2@@UIAudioSessionManager@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionManagerInternal@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioSessionManagerClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionManager2,IAudioSessionManager,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionManagerInternal,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'}
0x180028278  mov     [rcx+10h], rax
0x18002827c  lea     rax, ??_7CAudioSessionManagerClient@@6BIAudioSessionManagerInternal@@@; const CAudioSessionManagerClient::`vftable'{for `IAudioSessionManagerInternal'}
0x180028283  mov     [rcx+18h], rax
0x180028287  lea     rax, ??_7CAudioSessionManagerClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioSessionManagerClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'}
0x18002828e  mov     [rcx+20h], rax
0x180028292  lea     rax, ??_7CAudioSessionManagerClient@@6BICrossVmMediaNotificationConsumer@@@; const CAudioSessionManagerClient::`vftable'{for `ICrossVmMediaNotificationConsumer'}
0x180028299  mov     [rcx+28h], rax
0x18002829d  lea     rax, ??_7CAudioSessionManagerClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CAudioSessionManagerClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800282a4  mov     [rcx+30h], rax
0x1800282a8  lea     rsi, [rcx+0E0h]
0x1800282af  mov     rcx, rsi; lpCriticalSection
0x1800282b2  call    cs:__imp_EnterCriticalSection
0x1800282b8  lea     rbp, [rbx+0A8h]
0x1800282bf  cmp     byte ptr [rbx+109h], 0
0x1800282c6  jz      short loc_1800282D7
0x1800282c8  mov     rdx, rbp; void **
0x1800282cb  call    ?DeleteAudioSessionClientNotification@CAudioSessionManagerClient@@IEAAJPEAPEAX@Z; CAudioSessionManagerClient::DeleteAudioSessionClientNotification(void * *)
0x1800282d0  mov     byte ptr [rbx+109h], 0
0x1800282d7  lea     rax, ??_7CUnregisterDuckingNotification@@6B@; const CUnregisterDuckingNotification::`vftable'
0x1800282de  mov     [rsp+68h+var_48], rax
0x1800282e3  mov     [rsp+68h+var_40], rbp
0x1800282e8  lea     r15, [rbx+160h]
0x1800282ef  lea     rdx, [rsp+68h+var_48]
0x1800282f4  mov     rcx, r15; lpCriticalSection
0x1800282f7  call    ?ForEachEntry@?$CLockedList_AllowDuplicates@UIAudioVolumeDuckNotification@@$00@@QEAAJ$$QEAVCListWorker@1@@Z; CLockedList_AllowDuplicates<IAudioVolumeDuckNotification,1>::ForEachEntry(CLockedList_AllowDuplicates<IAudioVolumeDuckNotification,1>::CListWorker &&)
0x1800282fc  test    rsi, rsi
0x1800282ff  jz      short loc_18002830A
0x180028301  mov     rcx, rsi; lpCriticalSection
0x180028304  call    cs:__imp_LeaveCriticalSection
0x18002830a  lea     r14, [rbx+0B8h]
0x180028311  mov     rcx, [r14]
0x180028314  test    rcx, rcx
0x180028317  jz      short loc_180028337
0x180028319  cmp     byte ptr [rbx+10Ah], 0
0x180028320  jz      short loc_18002832F
0x180028322  call    cs:__imp_UnregisterMediaCallback
0x180028328  mov     byte ptr [rbx+10Ah], 0
0x18002832f  mov     rcx, r14
0x180028332  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x180028337  lea     rdi, [rbx+1A0h]
0x18002833e  mov     rcx, rdi; lpCriticalSection
0x180028341  call    cs:__imp_EnterCriticalSection
0x180028347  mov     rdx, [rbx+1D0h]
0x18002834e  mov     rcx, [rbx+1C8h]
0x180028355  cmp     rcx, rdx
0x180028358  jz      short loc_18002836D
0x18002835a  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002835f  mov     rax, [rbx+1C8h]
0x180028366  mov     [rbx+1D0h], rax
0x18002836d  test    rdi, rdi
0x180028370  jz      short loc_18002837B
0x180028372  mov     rcx, rdi; lpCriticalSection
0x180028375  call    cs:__imp_LeaveCriticalSection
0x18002837b  mov     rcx, [rbx+1E0h]; pwk
0x180028382  test    rcx, rcx
0x180028385  jz      short loc_18002839F
0x180028387  mov     edx, 1; fCancelPendingCallbacks
0x18002838c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180028392  mov     rcx, [rbx+1E0h]; pwk
0x180028399  call    cs:__imp_CloseThreadpoolWork
0x18002839f  mov     rdx, [rbx+120h]
0x1800283a6  mov     rcx, [rbx+118h]; this
0x1800283ad  cmp     rcx, rdx
0x1800283b0  jz      short loc_1800283C5
0x1800283b2  call    ??$_Destroy_range@V?$allocator@USessionEntry@CAudioSessionManagerClient@@@std@@@std@@YAXPEAUSessionEntry@CAudioSessionManagerClient@@QEAU12@AEAV?$allocator@USessionEntry@CAudioSessionManagerClient@@@0@@Z; std::_Destroy_range<std::allocator<CAudioSessionManagerClient::SessionEntry>>(CAudioSessionManagerClient::SessionEntry *,CAudioSessionManagerClient::SessionEntry * const,std::allocator<CAudioSessionManagerClient::SessionEntry> &)
0x1800283b7  mov     rax, [rbx+118h]
0x1800283be  mov     [rbx+120h], rax
0x1800283c5  cmp     qword ptr [rbp+0], 0
0x1800283ca  jz      short loc_1800283DB
0x1800283cc  mov     [rsp+68h+arg_0], rbx
0x1800283d1  lea     rcx, [rsp+68h+arg_0]
0x1800283d6  call    _lambda_e3f68923eb8857d5d52761db6818aa5c___operator__
0x1800283db  lea     rcx, [rbx+1F0h]; void *
0x1800283e2  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800283e7  mov     rcx, [rbx+1C8h]
0x1800283ee  test    rcx, rcx
0x1800283f1  jz      short loc_18002843A
0x1800283f3  mov     rdx, [rbx+1D0h]
0x1800283fa  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800283ff  mov     rcx, [rbx+1C8h]
0x180028406  mov     rdx, [rbx+1D8h]
0x18002840d  sub     rdx, rcx
0x180028410  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180028414  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180028419  mov     qword ptr [rbx+1C8h], 0
0x180028424  mov     qword ptr [rbx+1D0h], 0
0x18002842f  mov     qword ptr [rbx+1D8h], 0
0x18002843a  mov     rcx, rdi; lpCriticalSection
0x18002843d  call    cs:__imp_DeleteCriticalSection
0x180028443  mov     rcx, r15
0x180028446  call    ??1?$CLockedList_AllowDuplicates@UIAudioSessionEvents@@$00@@QEAA@XZ; CLockedList_AllowDuplicates<IAudioSessionEvents,1>::~CLockedList_AllowDuplicates<IAudioSessionEvents,1>(void)
0x18002844b  lea     rcx, [rbx+130h]; lpCriticalSection
0x180028452  call    cs:__imp_DeleteCriticalSection
0x180028458  mov     rcx, [rbx+118h]; this
0x18002845f  test    rcx, rcx
0x180028462  jz      short loc_1800284C1
0x180028464  mov     rdx, [rbx+120h]
0x18002846b  call    ??$_Destroy_range@V?$allocator@USessionEntry@CAudioSessionManagerClient@@@std@@@std@@YAXPEAUSessionEntry@CAudioSessionManagerClient@@QEAU12@AEAV?$allocator@USessionEntry@CAudioSessionManagerClient@@@0@@Z; std::_Destroy_range<std::allocator<CAudioSessionManagerClient::SessionEntry>>(CAudioSessionManagerClient::SessionEntry *,CAudioSessionManagerClient::SessionEntry * const,std::allocator<CAudioSessionManagerClient::SessionEntry> &)
0x180028470  mov     rcx, [rbx+118h]
0x180028477  mov     rax, [rbx+128h]
0x18002847e  sub     rax, rcx
0x180028481  sar     rax, 3
0x180028485  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18002848f  imul    rax, rdx
0x180028493  lea     rdx, [rax+rax*4]
0x180028497  shl     rdx, 3
0x18002849b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800284a0  mov     qword ptr [rbx+118h], 0
0x1800284ab  mov     qword ptr [rbx+120h], 0
0x1800284b6  mov     qword ptr [rbx+128h], 0
0x1800284c1  mov     rcx, rsi; lpCriticalSection
0x1800284c4  call    cs:__imp_DeleteCriticalSection
0x1800284ca  lea     rcx, [rbx+0C0h]
0x1800284d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800284d6  mov     rcx, r14; void *
0x1800284d9  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800284de  lea     rcx, [rbx+0A0h]; void *
0x1800284e5  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800284ea  lea     rcx, [rbx+60h]
0x1800284ee  call    ??1?$CLockedList_AllowDuplicates@UIAudioSessionNotification@@$00@@QEAA@XZ; CLockedList_AllowDuplicates<IAudioSessionNotification,1>::~CLockedList_AllowDuplicates<IAudioSessionNotification,1>(void)
0x1800284f3  mov     rcx, rbx
0x1800284f6  add     rsp, 38h
0x1800284fa  pop     r15
0x1800284fc  pop     r14
0x1800284fe  pop     rdi
0x1800284ff  pop     rsi
0x180028500  pop     rbp
0x180028501  pop     rbx
0x180028502  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIInspectable@@U?$ChainInterfaces@UIAudioSessionManager2@@UIAudioSessionManager@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionManagerInternal@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionManager2,IAudioSessionManager,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionManagerInternal,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionManager2,IAudioSessionManager,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionManagerInternal,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>(void)
```
