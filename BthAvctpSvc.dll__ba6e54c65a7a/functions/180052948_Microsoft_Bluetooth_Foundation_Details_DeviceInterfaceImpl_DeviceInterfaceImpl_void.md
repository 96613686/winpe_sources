# Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::~DeviceInterfaceImpl(void)

- ea: `0x180052948`
- end: `0x180052af6`
- name: `??1DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@UEAA@XZ`
- size: `430`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053360`

## callees

- `0x18000ab4c`
- `0x18000de78`
- `0x18000deb0`
- `0x18000fa08`
- `0x180015adc`
- `0x180019c68`
- `0x180019d20`
- `0x180019ed8`
- `0x18002eb08`
- `0x180051d14`
- `0x180052680`
- `0x1800528bc`
- `0x180052948`
- `0x180053a80`
- `0x180055cd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052ab2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052ab2`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::~DeviceInterfaceImpl(
        Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl *this)
{
  char v2; // r8
  char v3; // dl
  __int64 v4; // rax
  __int64 v5; // r10
  __int64 v6; // rcx
  char *v7; // rdx
  char *v8; // rbx
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  std::_Ref_count_base *v11; // rcx
  char v12; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::`vftable';
  v2 = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
    || (v3 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v3 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 24) )
    v2 = 0;
  if ( v3 || v2 )
  {
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
    WPP_RECORDER_AND_TRACE_SF_Sq(
      *(_QWORD *)(v5 + 16),
      5,
      2,
      11,
      &WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids,
      v4,
      (char)this);
  }
  wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
    (char *)this + 32,
    0);
  wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
    (char *)this + 24,
    0);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_work_context *,void (*)(wil::details::threadpool_work_context *),&public: static void wil::details::threadpool_work_context::RequestRelease(wil::details::threadpool_work_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_work_context *,wil::details::threadpool_work_context *,0,std::nullptr_t>>::reset(
    (char *)this + 216,
    0);
  Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::CloseInternal(this, &v12);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_work_context *,void (*)(wil::details::threadpool_work_context *),&public: static void wil::details::threadpool_work_context::RequestRelease(wil::details::threadpool_work_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_work_context *,wil::details::threadpool_work_context *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::threadpool_work_context *,void (*)(wil::details::threadpool_work_context *),&public: static void wil::details::threadpool_work_context::RequestRelease(wil::details::threadpool_work_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_work_context *,wil::details::threadpool_work_context *,0,std::nullptr_t>>((char *)this + 216);
  v6 = *((_QWORD *)this + 25);
  **(_QWORD **)(v6 + 8) = 0;
  v7 = *(char **)v6;
  if ( *(_QWORD *)v6 )
  {
    do
    {
      v8 = *(char **)v7;
      std::_List_node<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>,void *>::_Freenode<std::allocator<std::_List_node<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>,void *>>>(
        v6,
        v7);
      v7 = v8;
    }
    while ( v8 );
  }
  std::_Deallocate<16>(*((void **)this + 25), (struct std::nothrow_t *)0x18);
  std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>>>,0>>((char *)this + 176);
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 21);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 19);
  if ( v10 )
    std::_Ref_count_base::_Decwref(v10);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 136);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  std::wstring::_Tidy_deallocate((char *)this + 40);
  wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>((char *)this + 32);
  wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>((char *)this + 24);
  v11 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v11 )
    std::_Ref_count_base::_Decwref(v11);
}

```

## disassembly

```asm
0x180052948  mov     [rsp+arg_8], rbx
0x18005294d  mov     [rsp+arg_10], rbp
0x180052952  push    rsi
0x180052953  push    rdi
0x180052954  push    r14
0x180052956  sub     rsp, 50h
0x18005295a  lea     rax, ??_7DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::`vftable'
0x180052961  mov     rdi, rcx
0x180052964  mov     [rcx], rax
0x180052967  mov     r10, cs:WPP_GLOBAL_Control
0x18005296e  lea     rax, WPP_GLOBAL_Control
0x180052975  xor     r14d, r14d
0x180052978  mov     r8b, 1
0x18005297b  cmp     r10, rax
0x18005297e  jz      short loc_180052991
0x180052980  test    byte ptr [r10+1Ch], 2
0x180052985  jz      short loc_180052991
0x180052987  cmp     byte ptr [r10+19h], 5
0x18005298c  mov     dl, r8b
0x18005298f  jnb     short loc_180052994
0x180052991  mov     dl, r14b
0x180052994  lea     rax, WPP_RECORDER_INITIALIZED
0x18005299b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800529a2  jz      short loc_1800529AB
0x1800529a4  cmp     [r10+30h], r14w
0x1800529a9  jnz     short loc_1800529AE
0x1800529ab  mov     r8b, r14b
0x1800529ae  test    dl, dl
0x1800529b0  jnz     short loc_1800529B7
0x1800529b2  test    r8b, r8b
0x1800529b5  jz      short loc_1800529F7
0x1800529b7  add     rcx, 28h ; '('
0x1800529bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800529c0  mov     r9, [r10+28h]
0x1800529c4  mov     rcx, [r10+10h]; LoggerHandle
0x1800529c8  mov     qword ptr [rsp+68h+var_20], rdi; char
0x1800529cd  mov     [rsp+68h+var_28], rax; __int64
0x1800529d2  lea     rax, WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids
0x1800529d9  mov     [rsp+68h+MessageGuid], rax; MessageGuid
0x1800529de  mov     [rsp+68h+var_38], 0Bh; __int16
0x1800529e5  mov     [rsp+68h+var_40], 2; int
0x1800529ed  mov     [rsp+68h+var_48], 5; char
0x1800529f2  call    WPP_RECORDER_AND_TRACE_SF_Sq
0x1800529f7  xor     edx, edx
0x1800529f9  lea     rcx, [rdi+20h]
0x1800529fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x180052a02  xor     edx, edx
0x180052a04  lea     rcx, [rdi+18h]
0x180052a08  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x180052a0d  lea     rbx, [rdi+0D8h]
0x180052a14  xor     edx, edx
0x180052a16  mov     rcx, rbx
0x180052a19  call    ?reset@?$unique_storage@U?$resource_policy@PEAUthreadpool_work_context@details@wil@@P6AXPEAU123@@Z$1?RequestRelease@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUthreadpool_work_context@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_work_context *,void (*)(wil::details::threadpool_work_context *),&wil::details::threadpool_work_context::RequestRelease(wil::details::threadpool_work_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_work_context *,wil::details::threadpool_work_context *,0,std::nullptr_t>>::reset(wil::details::threadpool_work_context *)
0x180052a1e  lea     rdx, [rsp+68h+arg_0]
0x180052a23  mov     rcx, rdi
0x180052a26  call    ?CloseInternal@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::CloseInternal(void)
0x180052a2b  lea     rcx, [rsp+68h+arg_0]
0x180052a30  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180052a35  mov     rcx, rbx
0x180052a38  call    ??1?$unique_storage@U?$resource_policy@PEAUthreadpool_work_context@details@wil@@P6AXPEAU123@@Z$1?RequestRelease@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_work_context *,void (*)(wil::details::threadpool_work_context *),&wil::details::threadpool_work_context::RequestRelease(wil::details::threadpool_work_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_work_context *,wil::details::threadpool_work_context *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::threadpool_work_context *,void (*)(wil::details::threadpool_work_context *),&wil::details::threadpool_work_context::RequestRelease(wil::details::threadpool_work_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_work_context *,wil::details::threadpool_work_context *,0,std::nullptr_t>>(void)
0x180052a3d  mov     rcx, [rdi+0C8h]
0x180052a44  mov     rax, [rcx+8]
0x180052a48  mov     [rax], r14
0x180052a4b  mov     rdx, [rcx]
0x180052a4e  test    rdx, rdx
0x180052a51  jz      short loc_180052A63
0x180052a53  mov     rbx, [rdx]
0x180052a56  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>,void *>::_Freenode<std::allocator<std::_List_node<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>,void *>>>(std::allocator<std::_List_node<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>,void *>> &,std::_List_node<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>,void *> *)
0x180052a5b  mov     rdx, rbx
0x180052a5e  test    rbx, rbx
0x180052a61  jnz     short loc_180052A53
0x180052a63  mov     rcx, [rdi+0C8h]
0x180052a6a  mov     edx, 18h
0x180052a6f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052a74  lea     rcx, [rdi+0B0h]
0x180052a7b  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@UPendingIoSubmission@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@UPendingIoSubmission@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>>>,0>>(void)
0x180052a80  mov     rcx, [rdi+0A8h]; this
0x180052a87  test    rcx, rcx
0x180052a8a  jz      short loc_180052A91
0x180052a8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180052a91  mov     rcx, [rdi+98h]; this
0x180052a98  test    rcx, rcx
0x180052a9b  jz      short loc_180052AA2
0x180052a9d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180052aa2  lea     rcx, [rdi+88h]
0x180052aa9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180052aae  lea     rcx, [rdi+60h]; lpCriticalSection
0x180052ab2  call    cs:__imp_DeleteCriticalSection
0x180052ab8  lea     rcx, [rdi+28h]
0x180052abc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052ac1  lea     rcx, [rdi+20h]
0x180052ac5  call    ??1?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(void)
0x180052aca  lea     rcx, [rdi+18h]
0x180052ace  call    ??1?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(void)
0x180052ad3  mov     rcx, [rdi+10h]; this
0x180052ad7  test    rcx, rcx
0x180052ada  jz      short loc_180052AE1
0x180052adc  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180052ae1  lea     r11, [rsp+68h+var_18]
0x180052ae6  mov     rbx, [r11+28h]
0x180052aea  mov     rbp, [r11+30h]
0x180052aee  mov     rsp, r11
0x180052af1  pop     r14
0x180052af3  pop     rdi
0x180052af4  pop     rsi
0x180052af5  retn
```
