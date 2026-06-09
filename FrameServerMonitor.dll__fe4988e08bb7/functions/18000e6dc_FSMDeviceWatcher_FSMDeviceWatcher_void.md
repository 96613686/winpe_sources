# FSMDeviceWatcher::~FSMDeviceWatcher(void)

- ea: `0x18000e6dc`
- end: `0x18000e7c0`
- name: `??1FSMDeviceWatcher@@MEAA@XZ`
- size: `228`
- prototype: `void __fastcall(FSMDeviceWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e830`

## callees

- `0x180003194`
- `0x180005f98`
- `0x180006700`
- `0x180006ffc`
- `0x1800071e4`
- `0x18000d154`
- `0x18000d4f8`
- `0x18000e100`
- `0x18000e6dc`
- `0x180015fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e7b9`

## pseudocode

```c
void __fastcall FSMDeviceWatcher::~FSMDeviceWatcher(FSMDeviceWatcher *this)
{
  void *v2; // rdx
  wil::details *v3; // rcx
  void *v4; // rdx
  __int64 v5; // rcx
  char *v6; // rdx
  void *v7; // rdx

  *(_QWORD *)this = &FSMDeviceWatcher::`vftable';
  FSMDeviceWatcher::ShutdownWatcher(this);
  v3 = (wil::details *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    wil::details::SetEvent(v3, v2);
    __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___T_Z((char *)this + 96);
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 25);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 192);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 23,
    v4);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 22);
  v6 = (char *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = 0;
  if ( v6 )
    wistd::default_delete<FSMDeviceWatcherCMRegisterInfo [0]>::operator()<FSMDeviceWatcherCMRegisterInfo>(v5, v6);
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear((char *)this + 120);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 14);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 12,
    v7);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)this + 11);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
}

```

## disassembly

```asm
0x18000e6dc  mov     [rsp+arg_0], rbx
0x18000e6e1  push    rdi
0x18000e6e2  sub     rsp, 20h
0x18000e6e6  lea     rax, ??_7FSMDeviceWatcher@@6B@; const FSMDeviceWatcher::`vftable'
0x18000e6ed  mov     rbx, rcx
0x18000e6f0  mov     [rcx], rax
0x18000e6f3  call    ?ShutdownWatcher@FSMDeviceWatcher@@UEAAJXZ; FSMDeviceWatcher::ShutdownWatcher(void)
0x18000e6f8  lea     rdi, [rbx+60h]
0x18000e6fc  mov     rcx, [rdi]; this
0x18000e6ff  test    rcx, rcx
0x18000e702  jz      short loc_18000E711
0x18000e704  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000e709  mov     rcx, rdi
0x18000e70c  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$T@Z
0x18000e711  cmp     cs:byte_18005E5A5, 10h
0x18000e718  jb      short loc_18000E73C
0x18000e71a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e721  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x18000e728  mov     edx, 0Bh
0x18000e72d  mov     r9, rbx
0x18000e730  mov     rcx, [rcx+0D8h]
0x18000e737  call    WPP_SF_q
0x18000e73c  lea     rcx, [rbx+0C8h]
0x18000e743  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000e748  lea     rcx, [rbx+0C0h]
0x18000e74f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e754  lea     rcx, [rbx+0B8h]
0x18000e75b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e760  lea     rcx, [rbx+0B0h]
0x18000e767  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000e76c  mov     rdx, [rbx+0A8h]
0x18000e773  mov     qword ptr [rbx+0A8h], 0
0x18000e77e  test    rdx, rdx
0x18000e781  jz      short loc_18000E788
0x18000e783  call    ??$?RUFSMDeviceWatcherCMRegisterInfo@@@?$default_delete@$$BY0A@UFSMDeviceWatcherCMRegisterInfo@@@wistd@@QEBAXPEAUFSMDeviceWatcherCMRegisterInfo@@@Z; wistd::default_delete<FSMDeviceWatcherCMRegisterInfo [0]>::operator()<FSMDeviceWatcherCMRegisterInfo>(FSMDeviceWatcherCMRegisterInfo *)
0x18000e788  lea     rcx, [rbx+78h]
0x18000e78c  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x18000e791  lea     rcx, [rbx+70h]
0x18000e795  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000e79a  mov     rcx, rdi
0x18000e79d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e7a2  lea     rcx, [rbx+58h]
0x18000e7a6  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000e7ab  lea     rcx, [rbx+28h]
0x18000e7af  mov     rbx, [rsp+28h+arg_0]
0x18000e7b4  add     rsp, 20h
0x18000e7b8  pop     rdi
0x18000e7b9  jmp     cs:__imp_DeleteCriticalSection
```
