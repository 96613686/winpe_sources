# CameraOcclusionStateMonitor::~CameraOcclusionStateMonitor(void)

- ea: `0x180024ea4`
- end: `0x180024f78`
- name: `??1CameraOcclusionStateMonitor@@EEAA@XZ`
- size: `212`
- prototype: `void __fastcall(CameraOcclusionStateMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180063210`

## callees

- `0x180008f9c`
- `0x18000aa08`
- `0x180024c64`
- `0x180024ea4`
- `0x180024f80`
- `0x18003ef28`
- `0x180063940`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f5b`
- `MFPlat!MFUnlockWorkQueue` at `0x180024ed7`
- `MFPlat!MFUnlockWorkQueue` at `0x180024ed7`

## pseudocode

```c
void __fastcall CameraOcclusionStateMonitor::~CameraOcclusionStateMonitor(CameraOcclusionStateMonitor *this)
{
  DWORD v2; // ecx
  __int64 v3; // rcx
  struct wil::details::wnf_subscription_state_base *v4; // rdx

  *(_QWORD *)this = &CameraOcclusionStateMonitor::`vftable';
  CameraOcclusionStateMonitor::Stop(this);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
    (char *)this + 88,
    0);
  v2 = *((_DWORD *)this + 18);
  if ( v2 )
  {
    MFUnlockWorkQueue(v2);
    *((_DWORD *)this + 18) = 0;
  }
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_70567b7aa3313d2d575f02faf3e844e7_Traceguids, this);
  utl::vector<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>,utl::allocator<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>>::_Uninit((char *)this + 640);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 77);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
    (wil::details **)this + 11,
    v4);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x180024ea4  mov     [rsp+arg_0], rbx
0x180024ea9  mov     [rsp+arg_8], rsi
0x180024eae  push    rdi
0x180024eaf  sub     rsp, 20h
0x180024eb3  lea     rax, ??_7CameraOcclusionStateMonitor@@6B@; const CameraOcclusionStateMonitor::`vftable'
0x180024eba  mov     rbx, rcx
0x180024ebd  mov     [rcx], rax
0x180024ec0  call    ?Stop@CameraOcclusionStateMonitor@@UEAAJXZ; CameraOcclusionStateMonitor::Stop(void)
0x180024ec5  xor     edx, edx
0x180024ec7  lea     rcx, [rbx+58h]
0x180024ecb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x180024ed0  mov     ecx, [rbx+48h]; dwWorkQueue
0x180024ed3  test    ecx, ecx
0x180024ed5  jz      short loc_180024EE4
0x180024ed7  call    cs:__imp_MFUnlockWorkQueue
0x180024edd  mov     dword ptr [rbx+48h], 0
0x180024ee4  lea     rdi, [rbx+50h]
0x180024ee8  mov     rcx, [rdi]
0x180024eeb  mov     qword ptr [rdi], 0
0x180024ef2  test    rcx, rcx
0x180024ef5  jz      short loc_180024F03
0x180024ef7  mov     rax, [rcx]
0x180024efa  mov     rax, [rax+10h]
0x180024efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f03  cmp     cs:byte_18008D62D, 8
0x180024f0a  jb      short loc_180024F2E
0x180024f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f13  lea     r8, WPP_70567b7aa3313d2d575f02faf3e844e7_Traceguids
0x180024f1a  mov     edx, 0Eh
0x180024f1f  mov     r9, rbx
0x180024f22  mov     rcx, [rcx+0D8h]
0x180024f29  call    WPP_SF_q
0x180024f2e  lea     rcx, [rbx+280h]
0x180024f35  call    ?_Uninit@?$vector@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@utl@@@utl@@AEAAXXZ; utl::vector<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>,utl::allocator<wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>>>::_Uninit(void)
0x180024f3a  lea     rcx, [rbx+268h]
0x180024f41  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180024f46  lea     rcx, [rbx+58h]
0x180024f4a  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180024f4f  mov     rcx, rdi
0x180024f52  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180024f57  lea     rcx, [rbx+20h]; lpCriticalSection
0x180024f5b  call    cs:__imp_DeleteCriticalSection
0x180024f61  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x180024f68  mov     rbx, [rsp+28h+arg_0]
0x180024f6d  mov     rsi, [rsp+28h+arg_8]
0x180024f72  add     rsp, 20h
0x180024f76  pop     rdi
0x180024f77  retn
```
