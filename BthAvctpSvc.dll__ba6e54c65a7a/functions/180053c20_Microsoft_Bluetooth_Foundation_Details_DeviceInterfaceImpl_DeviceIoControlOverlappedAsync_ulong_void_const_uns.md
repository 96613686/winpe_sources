# Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DeviceIoControlOverlappedAsync(ulong,void const *,unsigned __int64,unsigned __int64)

- ea: `0x180053c20`
- end: `0x1800542c0`
- name: `?DeviceIoControlOverlappedAsync@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@UEAA?AV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@KPEBX_K1@Z`
- size: `1696`
- prototype: `__int64 __usercall@<rax>(char@<cl>, __int64, char)`
- caller_count: `0`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001dd0`
- `0x1800021dc`
- `0x180003fbc`
- `0x180004040`
- `0x18000a91c`
- `0x18000ce3c`
- `0x18000dca8`
- `0x18000de78`
- `0x18000e0c0`
- `0x18000e16c`
- `0x18000f3a0`
- `0x180010b78`
- `0x180012168`
- `0x180012554`
- `0x180051994`
- `0x180051aa0`
- `0x180051ad8`
- `0x180051b64`
- `0x180051d70`
- `0x180051eb4`
- `0x18005203c`
- `0x180052214`
- `0x180052594`
- `0x1800527dc`
- `0x1800528a0`
- `0x180052afc`
- `0x180053c20`
- `0x180055aa0`
- `0x180055c80`
- `0x180055df0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053d27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053d27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800540a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800540a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
struct _GUID *Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DeviceIoControlOverlappedAsync(
        __int64 a1,
        struct _GUID *a2,
        ...)
{
  __int64 v2; // r13
  int v5; // edx
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  _DWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  std::_Ref_count_base *v12; // rcx
  __int64 v13; // rdi
  std::_Ref_count_base *v14; // rsi
  volatile signed __int32 *v15; // r14
  __int64 v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // r9
  std::_Ref_count_base *v19; // rdi
  __int64 v20; // rsi
  unsigned __int128 v21; // xmm6
  _QWORD *v22; // rbx
  const char *v23; // r9
  __int64 v24; // rcx
  std::_Ref_count_base *v25; // rdi
  __int64 v26; // rdx
  std::_Ref_count_base *v27; // rcx
  void (__fastcall *v28)(__int64, __int64 *, void ***); // r9
  __int64 v29; // r10
  __int64 v30; // rdi
  void (__fastcall *v31)(__int64, void ***); // rbx
  int v33; // [rsp+28h] [rbp-E0h]
  std::_Ref_count_base *v34; // [rsp+68h] [rbp-A0h] BYREF
  std::_Ref_count_base *v35; // [rsp+70h] [rbp-98h] BYREF
  std::_Ref_count_base *v36; // [rsp+78h] [rbp-90h]
  __int64 v37; // [rsp+80h] [rbp-88h] BYREF
  _DWORD *v38; // [rsp+88h] [rbp-80h] BYREF
  std::_Ref_count_base *v39; // [rsp+90h] [rbp-78h]
  _QWORD v40[2]; // [rsp+98h] [rbp-70h] BYREF
  struct _GUID *v41; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-58h] BYREF
  std::_Ref_count_base *v43; // [rsp+B8h] [rbp-50h]
  _DWORD *v44; // [rsp+C0h] [rbp-48h] BYREF
  std::_Ref_count_base *v45; // [rsp+C8h] [rbp-40h]
  __int64 v46; // [rsp+D8h] [rbp-30h] BYREF
  std::_Ref_count_base *v47; // [rsp+E0h] [rbp-28h]
  _QWORD v48[3]; // [rsp+E8h] [rbp-20h] BYREF
  char v49; // [rsp+100h] [rbp-8h]
  std::_Ref_count_base *v50[2]; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v51[2]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int128 v52; // [rsp+138h] [rbp+30h] BYREF
  void **v53; // [rsp+148h] [rbp+40h] BYREF
  void **v54; // [rsp+150h] [rbp+48h] BYREF
  std::_Ref_count_base *v55; // [rsp+158h] [rbp+50h]
  unsigned __int128 v56; // [rsp+160h] [rbp+58h]
  __int64 v57; // [rsp+170h] [rbp+68h]
  unsigned __int128 v58; // [rsp+178h] [rbp+70h]
  void ***v59; // [rsp+1B8h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+230h] [rbp+128h]
  __int64 v61; // [rsp+248h] [rbp+140h] BYREF
  va_list va; // [rsp+248h] [rbp+140h]
  __int64 v63; // [rsp+250h] [rbp+148h]
  __int64 v64; // [rsp+258h] [rbp+150h] BYREF
  va_list va1; // [rsp+258h] [rbp+150h]
  va_list va2; // [rsp+260h] [rbp+158h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v61 = va_arg(va1, _QWORD);
  v63 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v64 = va_arg(va2, _QWORD);
  v2 = v63;
  v41 = a2;
  v52 = (unsigned __int128)*Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(
                              (Microsoft::Bluetooth::Foundation::GuidFactory *)&v44,
                              a2);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
    || (LOBYTE(v5) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v5) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v6) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    LOBYTE(v6) = 0;
  }
  if ( (_BYTE)v5 || (_BYTE)v6 )
    WPP_RECORDER_AND_TRACE_SF_DP_guid_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( (*(_DWORD *)(a1 + 88) & 0x40000000) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\deviceinterface.cpp",
      (const char *)0x8000000ELL,
      v33);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v41 = (struct _GUID *)(a1 + 96);
  if ( *(_QWORD *)(a1 + 136) == -1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || (LOBYTE(v7) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
    {
      LOBYTE(v7) = 0;
    }
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        2,
        2,
        13,
        &WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids,
        a1);
    }
    v9 = operator new(0x140u);
    v34 = (std::_Ref_count_base *)v9;
    *(_OWORD *)v9 = 0;
    v9[2] = 1;
    v9[3] = 1;
    *(_QWORD *)v9 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<unsigned char>,long>>::`vftable';
    std::_Construct_in_place<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<unsigned char>,long>,std::nullptr_t>(v9 + 4);
    v35 = (std::_Ref_count_base *)(v9 + 4);
    v36 = (std::_Ref_count_base *)v9;
    v10 = *((_QWORD *)v9 + 2);
    LODWORD(v40[0]) = -2147024890;
    v34 = 0;
    (*(void (__fastcall **)(_DWORD *, std::_Ref_count_base **, _QWORD *))(v10 + 48))(v9 + 4, &v34, v40);
    v11 = std::static_pointer_cast<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<unsigned char>,long>,Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<unsigned char>,long>>(
            &v42,
            &v35);
    std::make_shared<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<unsigned char>,long>>>(
      a2,
      v11);
    if ( v43 )
      std::_Ref_count_base::_Decref(v43);
    v12 = (std::_Ref_count_base *)v9;
LABEL_41:
    std::_Ref_count_base::_Decref(v12);
    goto LABEL_42;
  }
  v13 = std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(
          a1 + 8,
          &v42);
  v14 = (std::_Ref_count_base *)operator new(0x70u);
  v34 = v14;
  *(_OWORD *)v14 = 0;
  *((_DWORD *)v14 + 2) = 1;
  *((_DWORD *)v14 + 3) = 1;
  *(_QWORD *)v14 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContext>::`vftable';
  std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContext,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl>,unsigned __int64 &>(
    (char *)v14 + 16,
    v13,
    va2);
  v38 = (_DWORD *)((char *)v14 + 16);
  v39 = v14;
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  v48[2] = &v38;
  v49 = 1;
  std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
    v50,
    &v38);
  v51[0] = v52;
  v15 = (volatile signed __int32 *)operator new(0x140u);
  v34 = (std::_Ref_count_base *)v15;
  *(_OWORD *)v15 = 0;
  *((_DWORD *)v15 + 2) = 1;
  *((_DWORD *)v15 + 3) = 1;
  *(_QWORD *)v15 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<unsigned char>,long>>::`vftable';
  std::_Construct_in_place<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<unsigned char>,long>,_lambda_dd2af8d92d731e33f148f25250c36fcb_>(
    v15 + 4,
    v50);
  v48[0] = v15 + 4;
  v48[1] = v15;
  if ( v50[1] )
    std::_Ref_count_base::_Decref(v50[1]);
  v16 = std::static_pointer_cast<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<unsigned char>,long>,Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<unsigned char>,long>>(
          &v35,
          v48);
  std::make_shared<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<unsigned char>,long>>>(
    &v42,
    v16);
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  operator new(0x20u);
  v35 = (std::_Ref_count_base *)(v15 + 4);
  v36 = (std::_Ref_count_base *)v15;
  _InterlockedAdd(v15 + 3, 1u);
  v17 = std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
          v40,
          &v38);
  v19 = (std::_Ref_count_base *)Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper::AsyncIoContextWrapper(
                                  v18,
                                  v17,
                                  &v35);
  v34 = v19;
  v20 = *(_QWORD *)Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::Instance(&v44);
  v34 = 0;
  LOWORD(v36) = 1;
  v35 = 0;
  v50[0] = v19;
  LOWORD(v50[1]) = 0;
  v21 = v52;
  v51[0] = v52;
  *((_QWORD *)&v58 + 1) = 0;
  v22 = std::_Allocate<16,std::_Default_allocate_traits>(0x28u);
  *v22 = &std::_Func_impl_no_alloc<_lambda_78405172cadb86c1f8aa7a01cba8cb2b_,void,>::`vftable';
  v50[0] = 0;
  v22[1] = v19;
  *((_WORD *)v22 + 8) = 0;
  LOBYTE(v50[1]) = 1;
  *(_OWORD *)(v22 + 3) = v21;
  v40[0] = 0;
  `std::_Global_new<std::_Func_impl_no_alloc<_lambda_78405172cadb86c1f8aa7a01cba8cb2b_,void,>,_lambda_78405172cadb86c1f8aa7a01cba8cb2b_ const &>'::`2'::_Guard_type::~_Guard_type(v40);
  *((_QWORD *)&v58 + 1) = v22;
  wil::make_threadpool_wait_safe_release(&v37, &v53, *(_QWORD *)(v20 + 8));
  if ( v38 + 14 != (_DWORD *)&v37 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_wait_context *,void (*)(wil::details::threadpool_wait_context *),&public: static void wil::details::threadpool_wait_context::RequestRelease(wil::details::threadpool_wait_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_wait_context *,wil::details::threadpool_wait_context *,0,std::nullptr_t>>::reset(
      v38 + 14,
      v37);
    v37 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_wait_context *,void (*)(wil::details::threadpool_wait_context *),&public: static void wil::details::threadpool_wait_context::RequestRelease(wil::details::threadpool_wait_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_wait_context *,wil::details::threadpool_wait_context *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::threadpool_wait_context *,void (*)(wil::details::threadpool_wait_context *),&public: static void wil::details::threadpool_wait_context::RequestRelease(wil::details::threadpool_wait_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_wait_context *,wil::details::threadpool_wait_context *,0,std::nullptr_t>>(&v37);
  std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(&v53);
  std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>(v50);
  std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>(&v35);
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  v24 = *((_QWORD *)v38 + 7);
  if ( !v24 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\deviceinterface.cpp",
      v23);
  SetThreadpoolWait(*(PTP_WAIT *)(v24 + 80), *((HANDLE *)v38 + 2), 0);
  v40[0] = v2;
  v25 = (std::_Ref_count_base *)operator new(0x38u);
  v35 = v25;
  *(_OWORD *)v25 = 0;
  *((_DWORD *)v25 + 2) = 1;
  *((_DWORD *)v25 + 3) = 1;
  *(_QWORD *)v25 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>::`vftable';
  std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission,_GUID &,unsigned long &,unsigned char const *,unsigned __int64 &>(
    (_DWORD)v25 + 16,
    (unsigned int)&v52,
    (unsigned int)va,
    (unsigned int)v40,
    (__int64)va1);
  v44 = (_DWORD *)((char *)v25 + 16);
  v45 = v25;
  v26 = *(_QWORD *)std::map<_GUID,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>>::_Try_emplace<_GUID const &,>(
                     a1 + 176,
                     &v35,
                     &v52);
  *(_QWORD *)(v26 + 48) = (char *)v25 + 16;
  v27 = *(std::_Ref_count_base **)(v26 + 56);
  *(_QWORD *)(v26 + 56) = v25;
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
    v50,
    &v38);
  v51[0] = v52;
  v53 = &std::_Func_impl_no_alloc<_lambda_3e68fc1903073138e2d9f6b9fd9bc392_,long,>::`vftable';
  v54 = (void **)v50[0];
  v55 = v50[1];
  *(_OWORD *)v50 = 0;
  v56 = v52;
  *((_QWORD *)&v58 + 1) = &v53;
  v28(v29, &v46, &v53);
  std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(&v53);
  v30 = v46;
  v31 = *(void (__fastcall **)(__int64, void ***))(*(_QWORD *)v46 + 24LL);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
    v50,
    &v38);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
    v51,
    &v46);
  v51[1] = v52;
  v54 = &wistd::__function::__func<_lambda_eb4021b76763f755cb9953e92ac29a97_,void (void)>::`vftable';
  v55 = v50[0];
  v56 = __PAIR128__(*(unsigned __int64 *)&v51[0], (unsigned __int64)v50[1]);
  *(_OWORD *)v50 = 0;
  v57 = *((_QWORD *)&v51[0] + 1);
  v51[0] = 0;
  v58 = v52;
  v59 = &v54;
  _lambda_eb4021b76763f755cb9953e92ac29a97_::~_lambda_eb4021b76763f755cb9953e92ac29a97_((_lambda_eb4021b76763f755cb9953e92ac29a97_ *)v50);
  v31(v30, &v53);
  wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>((__int64)&v53);
  *(_QWORD *)&a2->Data1 = v42;
  *(_QWORD *)a2->Data4 = v43;
  if ( v47 )
    std::_Ref_count_base::_Decref(v47);
  std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>(&v34);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v15);
  v12 = v39;
  if ( v39 )
    goto LABEL_41;
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v41);
  return a2;
}

```

## disassembly

```asm
0x180053c20  mov     rax, rsp
0x180053c23  mov     [rax+18h], r8d
0x180053c27  push    rbp
0x180053c28  push    rbx
0x180053c29  push    rsi
0x180053c2a  push    rdi
0x180053c2b  push    r12
0x180053c2d  push    r13
0x180053c2f  push    r14
0x180053c31  push    r15
0x180053c33  lea     rbp, [rax-128h]
0x180053c3a  sub     rsp, 1E8h
0x180053c41  movaps  xmmword ptr [rax-58h], xmm6
0x180053c45  mov     rax, cs:__security_cookie
0x180053c4c  xor     rax, rsp
0x180053c4f  mov     [rbp+120h+var_60], rax
0x180053c56  mov     r13, r9
0x180053c59  mov     ebx, r8d
0x180053c5c  mov     r12, rdx
0x180053c5f  mov     r15, rcx
0x180053c62  mov     [rbp+120h+var_180], rdx
0x180053c66  xor     r14d, r14d
0x180053c69  lea     rcx, [rbp+120h+var_168]; this
0x180053c6d  call    ?GetNextId@GuidFactory@Foundation@Bluetooth@Microsoft@@YA?AU_GUID@@XZ; Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(void)
0x180053c72  movups  xmm0, xmmword ptr [rax]
0x180053c75  movdqu  [rbp+120h+var_F0], xmm0
0x180053c7a  lea     rax, WPP_GLOBAL_Control
0x180053c81  lea     esi, [r14+1]
0x180053c85  lea     edi, [rsi+1]
0x180053c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c8f  cmp     rcx, rax
0x180053c92  jz      short loc_180053CA3
0x180053c94  test    [rcx+1Ch], dil
0x180053c98  jz      short loc_180053CA3
0x180053c9a  cmp     byte ptr [rcx+19h], 5
0x180053c9e  mov     dl, sil
0x180053ca1  jnb     short loc_180053CA6
0x180053ca3  mov     dl, r14b
0x180053ca6  lea     rax, WPP_RECORDER_INITIALIZED
0x180053cad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180053cb4  jz      short loc_180053CC0
0x180053cb6  cmp     [rcx+30h], r14w
0x180053cbb  mov     r8b, sil
0x180053cbe  jnz     short loc_180053CC3
0x180053cc0  mov     r8b, r14b
0x180053cc3  test    dl, dl
0x180053cc5  jnz     short loc_180053CCC
0x180053cc7  test    r8b, r8b
0x180053cca  jz      short loc_180053CF7
0x180053ccc  mov     [rsp+220h+var_1C8], r15
0x180053cd1  lea     rax, [rbp+120h+var_F0]
0x180053cd5  mov     [rsp+220h+var_1D0], rax
0x180053cda  mov     rax, [rbp+120h+arg_20]
0x180053ce1  mov     [rsp+220h+var_1D8], rax
0x180053ce6  mov     dword ptr [rsp+220h+var_1E0], ebx
0x180053cea  mov     r9, [rcx+28h]
0x180053cee  mov     rcx, [rcx+10h]
0x180053cf2  call    WPP_RECORDER_AND_TRACE_SF_DP_guid_q
0x180053cf7  mov     rcx, [rbp+128h]; this
0x180053cfe  test    dword ptr [r15+58h], 40000000h
0x180053d06  jnz     short loc_180053D20
0x180053d08  mov     r9d, 8000000Eh; char *
0x180053d0e  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\bluetooth\\foundation"...
0x180053d15  mov     edx, 92h; void *
0x180053d1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053d20  lea     rbx, [r15+60h]
0x180053d24  mov     rcx, rbx; lpCriticalSection
0x180053d27  call    cs:__imp_EnterCriticalSection
0x180053d2d  mov     [rbp+120h+var_180], rbx
0x180053d31  cmp     qword ptr [r15+88h], 0FFFFFFFFFFFFFFFFh
0x180053d39  jnz     loc_180053E42
0x180053d3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d46  lea     rax, WPP_GLOBAL_Control
0x180053d4d  cmp     rcx, rax
0x180053d50  jz      short loc_180053D61
0x180053d52  test    [rcx+1Ch], dil
0x180053d56  jz      short loc_180053D61
0x180053d58  cmp     [rcx+19h], dil
0x180053d5c  mov     dl, sil
0x180053d5f  jnb     short loc_180053D64
0x180053d61  mov     dl, r14b; int
0x180053d64  lea     rax, WPP_RECORDER_INITIALIZED
0x180053d6b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180053d72  setnz   r8b; int
0x180053d76  test    dl, dl
0x180053d78  jnz     short loc_180053D7F
0x180053d7a  test    r8b, r8b
0x180053d7d  jz      short loc_180053DAD
0x180053d7f  mov     qword ptr [rsp+220h+var_1E0], r15; char
0x180053d84  lea     rax, WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids
0x180053d8b  mov     [rsp+220h+MessageGuid], rax; MessageGuid
0x180053d90  mov     [rsp+220h+var_1F0], 0Dh; __int16
0x180053d97  mov     [rsp+220h+var_1F8], edi; int
0x180053d9b  mov     [rsp+220h+var_200], dil; char
0x180053da0  mov     r9, [rcx+28h]; int
0x180053da4  mov     rcx, [rcx+10h]; int
0x180053da8  call    WPP_RECORDER_AND_TRACE_SF_q
0x180053dad  mov     ecx, 140h; Size
0x180053db2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053db7  mov     rdi, rax
0x180053dba  mov     [rsp+220h+var_1C0], rax
0x180053dbf  xorps   xmm0, xmm0
0x180053dc2  movups  xmmword ptr [rax], xmm0
0x180053dc5  mov     [rax+8], esi
0x180053dc8  mov     [rax+0Ch], esi
0x180053dcb  lea     rax, ??_7?$_Ref_count_obj2@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>>::`vftable'
0x180053dd2  mov     [rdi], rax
0x180053dd5  lea     rbx, [rdi+10h]
0x180053dd9  mov     rcx, rbx
0x180053ddc  call    ??$_Construct_in_place@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$$T@std@@YAXAEAV?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$$QEA$$T@Z
0x180053de1  nop
0x180053de2  mov     [rsp+220h+var_1B8], rbx
0x180053de7  mov     [rsp+220h+var_1B0], rdi
0x180053dec  mov     rax, [rbx]
0x180053def  mov     dword ptr [rbp+120h+var_190], 80070006h
0x180053df6  mov     [rsp+220h+var_1C0], r14
0x180053dfb  lea     r8, [rbp+120h+var_190]
0x180053dff  lea     rdx, [rsp+220h+var_1C0]
0x180053e04  mov     rcx, rbx
0x180053e07  mov     rax, [rax+30h]
0x180053e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e10  lea     rdx, [rsp+220h+var_1B8]
0x180053e15  lea     rcx, [rbp+120h+var_178]
0x180053e19  call    ??$static_pointer_cast@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@234@@std@@YA?AV?$shared_ptr@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@@Z; std::static_pointer_cast<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<uchar>,long>,Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>> const &)
0x180053e1e  nop
0x180053e1f  mov     rdx, rax
0x180053e22  mov     rcx, r12
0x180053e25  call    ??$make_shared@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@V?$shared_ptr@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@@std@@YA?AV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@$$QEAV?$shared_ptr@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@@Z; std::make_shared<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<uchar>,long>>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<uchar>,long>> &&)
0x180053e2a  nop
0x180053e2b  mov     rcx, [rbp+120h+var_170]; this
0x180053e2f  test    rcx, rcx
0x180053e32  jz      short loc_180053E3A
0x180053e34  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053e39  nop
0x180053e3a  mov     rcx, rdi
0x180053e3d  jmp     loc_180054283
0x180053e42  lea     rcx, [r15+8]
0x180053e46  lea     rdx, [rbp+120h+var_178]
0x180053e4a  call    ?shared_from_this@?$enable_shared_from_this@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(void)
0x180053e4f  mov     rdi, rax
0x180053e52  mov     ecx, 70h ; 'p'; Size
0x180053e57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053e5c  mov     rsi, rax
0x180053e5f  mov     [rsp+220h+var_1C0], rax
0x180053e64  xorps   xmm0, xmm0
0x180053e67  movups  xmmword ptr [rax], xmm0
0x180053e6a  mov     eax, 1
0x180053e6f  mov     [rsi+8], eax
0x180053e72  mov     [rsi+0Ch], eax
0x180053e75  lea     rax, ??_7?$_Ref_count_obj2@VAsyncIoContext@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContext>::`vftable'
0x180053e7c  mov     [rsi], rax
0x180053e7f  lea     rbx, [rsi+10h]
0x180053e83  lea     r8, [rbp+120h+arg_28]
0x180053e8a  mov     rdx, rdi
0x180053e8d  mov     rcx, rbx
0x180053e90  call    ??$_Construct_in_place@VAsyncIoContext@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@V?$shared_ptr@VDeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@AEA_K@std@@YAXAEAVAsyncIoContext@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@$$QEAV?$shared_ptr@VDeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@0@AEA_K@Z; std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContext,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl>,unsigned __int64 &>(Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContext &,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl> &&,unsigned __int64 &)
0x180053e95  nop
0x180053e96  mov     [rbp+120h+var_1A0], rbx
0x180053e9a  mov     [rbp+120h+var_198], rsi
0x180053e9e  mov     rcx, [rbp+120h+var_170]; this
0x180053ea2  test    rcx, rcx
0x180053ea5  jz      short loc_180053EAC
0x180053ea7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053eac  lea     rax, [rbp+120h+var_1A0]
0x180053eb0  mov     [rbp+120h+var_130], rax
0x180053eb4  mov     edi, 1
0x180053eb9  mov     [rbp+120h+var_128], dil
0x180053ebd  lea     rdx, [rbp+120h+var_1A0]
0x180053ec1  lea     rcx, [rbp+120h+var_120]
0x180053ec5  call    ??0?$shared_ptr@VThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl> const &)
0x180053eca  movups  xmm0, [rbp+120h+var_F0]
0x180053ece  movdqu  [rbp+120h+var_110], xmm0
0x180053ed3  mov     ecx, 140h; Size
0x180053ed8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053edd  mov     r14, rax
0x180053ee0  mov     [rsp+220h+var_1C0], rax
0x180053ee5  xorps   xmm0, xmm0
0x180053ee8  movups  xmmword ptr [rax], xmm0
0x180053eeb  mov     [rax+8], edi
0x180053eee  mov     [rax+0Ch], edi
0x180053ef1  lea     rax, ??_7?$_Ref_count_obj2@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>>::`vftable'
0x180053ef8  mov     [r14], rax
0x180053efb  lea     rbx, [r14+10h]
0x180053eff  lea     rdx, [rbp+120h+var_120]
0x180053f03  mov     rcx, rbx
0x180053f06  call    ??$_Construct_in_place@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@V_lambda_dd2af8d92d731e33f148f25250c36fcb_@@@std@@YAXAEAV?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$$QEAV_lambda_dd2af8d92d731e33f148f25250c36fcb_@@@Z; std::_Construct_in_place<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>,_lambda_dd2af8d92d731e33f148f25250c36fcb_>(Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long> &,_lambda_dd2af8d92d731e33f148f25250c36fcb_ &&)
0x180053f0b  nop
0x180053f0c  mov     [rbp+120h+var_140], rbx
0x180053f10  mov     [rbp+120h+var_138], r14
0x180053f14  mov     rcx, [rbp+120h+var_120+8]; this
0x180053f18  test    rcx, rcx
0x180053f1b  jz      short loc_180053F22
0x180053f1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053f22  lea     rdx, [rbp+120h+var_140]
0x180053f26  lea     rcx, [rsp+220h+var_1B8]
0x180053f2b  call    ??$static_pointer_cast@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@234@@std@@YA?AV?$shared_ptr@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@@Z; std::static_pointer_cast<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<uchar>,long>,Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>> const &)
0x180053f30  nop
0x180053f31  mov     rdx, rax
0x180053f34  lea     rcx, [rbp+120h+var_178]
0x180053f38  call    ??$make_shared@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@V?$shared_ptr@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@@std@@YA?AV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@$$QEAV?$shared_ptr@V?$AsyncRequestWithUniqueResult@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@0@@Z; std::make_shared<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<uchar>,long>>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResult<std::vector<uchar>,long>> &&)
0x180053f3d  nop
0x180053f3e  mov     rcx, [rsp+220h+var_1B0]; this
0x180053f43  test    rcx, rcx
0x180053f46  jz      short loc_180053F4D
0x180053f48  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053f4d  mov     ecx, 20h ; ' '; Size
0x180053f52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053f57  mov     r9, rax
0x180053f5a  mov     [rsp+220h+var_1C0], rax
0x180053f5f  mov     [rsp+220h+var_1B8], rbx
0x180053f64  mov     [rsp+220h+var_1B0], r14
0x180053f69  lock add [r14+0Ch], edi
0x180053f6e  lea     rdx, [rbp+120h+var_1A0]
0x180053f72  lea     rcx, [rbp+120h+var_190]
0x180053f76  call    ??0?$shared_ptr@VThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl> const &)
0x180053f7b  lea     r8, [rsp+220h+var_1B8]
0x180053f80  mov     rdx, rax
0x180053f83  mov     rcx, r9
0x180053f86  call    ??0AsyncIoContextWrapper@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@QEAA@V?$shared_ptr@VAsyncIoContext@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@V?$weak_ptr@V?$AsyncRequestWithUniqueResultServer@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@7@@Z; Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper::AsyncIoContextWrapper(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContext>,std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultServer<std::vector<uchar>,long>>)
0x180053f8b  mov     rdi, rax
0x180053f8e  mov     [rsp+220h+var_1C0], rax
0x180053f93  lea     rcx, [rbp+120h+var_168]
0x180053f97  call    ?Instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::Instance(void)
0x180053f9c  nop
0x180053f9d  mov     rsi, [rax]
0x180053fa0  xor     eax, eax
0x180053fa2  mov     [rsp+220h+var_1C0], rax
0x180053fa7  mov     word ptr [rsp+220h+var_1B0], 1
0x180053fae  mov     [rsp+220h+var_1B8], rax
0x180053fb3  mov     [rbp+120h+var_120], rdi
0x180053fb7  mov     word ptr [rbp+120h+var_120+8], ax
0x180053fbb  movups  xmm6, [rbp+120h+var_F0]
0x180053fbf  movups  [rbp+120h+var_110], xmm6
0x180053fc3  mov     [rbp+120h+var_A8], rax
0x180053fc7  lea     ecx, [rax+28h]
0x180053fca  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180053fcf  mov     rbx, rax
0x180053fd2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_78405172cadb86c1f8aa7a01cba8cb2b_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_78405172cadb86c1f8aa7a01cba8cb2b_,void,>::`vftable'
0x180053fd9  mov     [rbx], rax
0x180053fdc  mov     [rbp+120h+var_120], 0
0x180053fe4  mov     [rbx+8], rdi
0x180053fe8  xor     edi, edi
0x180053fea  mov     [rbx+10h], di
0x180053fee  mov     byte ptr [rbp+120h+var_120+8], 1
0x180053ff2  movdqu  xmmword ptr [rbx+18h], xmm6
0x180053ff7  mov     [rbp+120h+var_190], rdi
0x180053ffb  lea     rcx, [rbp+120h+var_190]
0x180053fff  call    ??1_Guard_type@?1???$_Global_new@V?$_Func_impl_no_alloc@V_lambda_78405172cadb86c1f8aa7a01cba8cb2b_@@X$$V@std@@AEBV_lambda_78405172cadb86c1f8aa7a01cba8cb2b_@@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_78405172cadb86c1f8aa7a01cba8cb2b_@@X$$V@1@AEBV_lambda_78405172cadb86c1f8aa7a01cba8cb2b_@@@Z@QEAA@XZ; `std::_Global_new<std::_Func_impl_no_alloc<_lambda_78405172cadb86c1f8aa7a01cba8cb2b_,void,>,_lambda_78405172cadb86c1f8aa7a01cba8cb2b_ const &>(_lambda_78405172cadb86c1f8aa7a01cba8cb2b_ const &)'::`2'::_Guard_type::~_Guard_type(void)
0x180054004  mov     [rbp+120h+var_A8], rbx
0x180054008  mov     r8, [rsi+8]
0x18005400c  lea     rdx, [rbp+120h+var_E0]
0x180054010  lea     rcx, [rsp+220h+var_1A8]
0x180054015  call    ?make_threadpool_wait_safe_release@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUthreadpool_wait_context@details@wil@@P6AXPEAU123@@Z$1?RequestRelease@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@1@$$QEAV?$function@$$A6AXXZ@std@@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; wil::make_threadpool_wait_safe_release(std::function<void (void)> &&,_TP_CALLBACK_ENVIRON_V3 *)
0x18005401a  mov     rcx, [rbp+120h+var_1A0]
0x18005401e  add     rcx, 38h ; '8'
0x180054022  lea     rax, [rsp+220h+var_1A8]
0x180054027  cmp     rcx, rax
0x18005402a  jz      short loc_18005403B
0x18005402c  mov     rdx, [rsp+220h+var_1A8]
0x180054031  call    ?reset@?$unique_storage@U?$resource_policy@PEAUthreadpool_wait_context@details@wil@@P6AXPEAU123@@Z$1?RequestRelease@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUthreadpool_wait_context@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_wait_context *,void (*)(wil::details::threadpool_wait_context *),&wil::details::threadpool_wait_context::RequestRelease(wil::details::threadpool_wait_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_wait_context *,wil::details::threadpool_wait_context *,0,std::nullptr_t>>::reset(wil::details::threadpool_wait_context *)
0x180054036  mov     [rsp+220h+var_1A8], rdi
0x18005403b  lea     rcx, [rsp+220h+var_1A8]
0x180054040  call    ??1?$unique_storage@U?$resource_policy@PEAUthreadpool_wait_context@details@wil@@P6AXPEAU123@@Z$1?RequestRelease@123@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::threadpool_wait_context *,void (*)(wil::details::threadpool_wait_context *),&wil::details::threadpool_wait_context::RequestRelease(wil::details::threadpool_wait_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_wait_context *,wil::details::threadpool_wait_context *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::threadpool_wait_context *,void (*)(wil::details::threadpool_wait_context *),&wil::details::threadpool_wait_context::RequestRelease(wil::details::threadpool_wait_context *),wistd::integral_constant<unsigned __int64,0>,wil::details::threadpool_wait_context *,wil::details::threadpool_wait_context *,0,std::nullptr_t>>(void)
0x180054045  nop
0x180054046  lea     rcx, [rbp+120h+var_E0]
0x18005404a  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x18005404f  nop
0x180054050  lea     rcx, [rbp+120h+var_120]
0x180054054  call    ??1?$unique_ptr@UAsyncIoContextWrapper@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UAsyncIoContextWrapper@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>(void)
0x180054059  nop
0x18005405a  lea     rcx, [rsp+220h+var_1B8]
0x18005405f  call    ??1?$unique_ptr@UAsyncIoContextWrapper@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UAsyncIoContextWrapper@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::AsyncIoContextWrapper>(void)
0x180054064  nop
0x180054065  mov     rcx, [rbp+120h+var_160]; this
0x180054069  test    rcx, rcx
0x18005406c  jz      short loc_180054073
0x18005406e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054073  mov     rdx, [rbp+120h+var_1A0]
0x180054077  mov     rcx, [rdx+38h]
0x18005407b  mov     rax, [rbp+128h]
0x180054082  test    rcx, rcx
0x180054085  jnz     short loc_18005409C
0x180054087  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\bluetooth\\foundation"...
0x18005408e  mov     edx, 0F2h; void *
0x180054093  mov     rcx, rax; this
0x180054096  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005409c  xor     r8d, r8d; pftTimeout
0x18005409f  mov     rdx, [rdx+10h]; h
0x1800540a3  mov     rcx, [rcx+50h]; pwa
0x1800540a7  call    cs:__imp_SetThreadpoolWait
0x1800540ad  mov     [rbp+120h+var_190], r13
0x1800540b1  mov     ecx, 38h ; '8'; Size
0x1800540b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800540bb  mov     rdi, rax
0x1800540be  mov     [rsp+220h+var_1B8], rax
0x1800540c3  xorps   xmm0, xmm0
0x1800540c6  movups  xmmword ptr [rax], xmm0
0x1800540c9  mov     eax, 1
0x1800540ce  mov     [rdi+8], eax
0x1800540d1  mov     [rdi+0Ch], eax
  ... truncated ...
```
