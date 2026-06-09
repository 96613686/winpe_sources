# CameraControlNotificationMonitor::~CameraControlNotificationMonitor(void)

- ea: `0x180063e3c`
- end: `0x180063ee9`
- name: `??1CameraControlNotificationMonitor@@EEAA@XZ`
- size: `173`
- prototype: `void __fastcall(CameraControlNotificationMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064030`

## callees

- `0x180008bd0`
- `0x180008f9c`
- `0x18000aa08`
- `0x18003ef28`
- `0x180063e3c`
- `0x180065438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063ed6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063ed6`
- `MFPlat!MFUnlockWorkQueue` at `0x180063e5e`
- `MFPlat!MFUnlockWorkQueue` at `0x180063e5e`

## pseudocode

```c
void __fastcall CameraControlNotificationMonitor::~CameraControlNotificationMonitor(
        CameraControlNotificationMonitor *this)
{
  DWORD v2; // ecx
  struct wil::details::wnf_subscription_state_base *v3; // rdx
  struct wil::details::wnf_subscription_state_base *v4; // rdx
  struct wil::details::wnf_subscription_state_base *v5; // rdx
  struct wil::details::wnf_subscription_state_base *v6; // rdx

  *(_QWORD *)this = &CameraControlNotificationMonitor::`vftable';
  CameraControlNotificationMonitor::ResetWNFSubscriptions(this);
  v2 = *((_DWORD *)this + 34);
  if ( v2 )
  {
    MFUnlockWorkQueue(v2);
    *((_DWORD *)this + 34) = 0;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_baf6de1ba3ee357d741c4ed31a2f3d4c_Traceguids, this);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 16);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 15,
    v3);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 14,
    v4);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 13,
    v5);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 12,
    v6);
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>((_DWORD *)this + 18);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x180063e3c  push    rbx
0x180063e3e  sub     rsp, 20h
0x180063e42  lea     rax, ??_7CameraControlNotificationMonitor@@6B@; const CameraControlNotificationMonitor::`vftable'
0x180063e49  mov     rbx, rcx
0x180063e4c  mov     [rcx], rax
0x180063e4f  call    ?ResetWNFSubscriptions@CameraControlNotificationMonitor@@AEAAXXZ; CameraControlNotificationMonitor::ResetWNFSubscriptions(void)
0x180063e54  mov     ecx, [rbx+88h]; dwWorkQueue
0x180063e5a  test    ecx, ecx
0x180063e5c  jz      short loc_180063E6E
0x180063e5e  call    cs:__imp_MFUnlockWorkQueue
0x180063e64  mov     dword ptr [rbx+88h], 0
0x180063e6e  cmp     cs:byte_18008D62D, 8
0x180063e75  jb      short loc_180063E99
0x180063e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e7e  lea     r8, WPP_baf6de1ba3ee357d741c4ed31a2f3d4c_Traceguids
0x180063e85  mov     edx, 0Eh
0x180063e8a  mov     r9, rbx
0x180063e8d  mov     rcx, [rcx+0D8h]
0x180063e94  call    WPP_SF_q
0x180063e99  lea     rcx, [rbx+80h]
0x180063ea0  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180063ea5  lea     rcx, [rbx+78h]
0x180063ea9  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180063eae  lea     rcx, [rbx+70h]
0x180063eb2  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180063eb7  lea     rcx, [rbx+68h]
0x180063ebb  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180063ec0  lea     rcx, [rbx+60h]
0x180063ec4  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180063ec9  lea     rcx, [rbx+48h]; void *
0x180063ecd  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ; CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(void)
0x180063ed2  lea     rcx, [rbx+20h]; lpCriticalSection
0x180063ed6  call    cs:__imp_DeleteCriticalSection
0x180063edc  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x180063ee3  add     rsp, 20h
0x180063ee7  pop     rbx
0x180063ee8  retn
```
