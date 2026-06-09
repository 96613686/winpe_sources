# Microsoft::Bluetooth::Foundation::DeviceIoTarget::ReopenAfterCancelRemove(void)

- ea: `0x18001e2e4`
- end: `0x18001e60a`
- name: `?ReopenAfterCancelRemove@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `806`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::DeviceIoTarget *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f330`

## callees

- `0x180004060`
- `0x18000de78`
- `0x180016374`
- `0x180019fd4`
- `0x18001a094`
- `0x18001b0bc`
- `0x18001ba10`
- `0x18001c6d0`
- `0x18001d160`
- `0x18001de70`
- `0x18001dfa8`
- `0x18001e2e4`
- `0x18001eea4`
- `0x18001f140`
- `0x18001f680`
- `0x18001f6b8`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e332`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e36d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e40a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e508`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e584`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e332`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e36d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e40a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e508`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e584`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Bluetooth::Foundation::DeviceIoTarget::ReopenAfterCancelRemove(RTL_SRWLOCK *this)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // ecx
  int v5; // r8d
  __int64 *v6; // rdi
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  struct Microsoft::Bluetooth::Foundation::Details::IoTargetRequest *v10; // rbx
  _QWORD v11[2]; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v13[2]; // [rsp+50h] [rbp-58h] BYREF
  RTL_SRWLOCK *v14; // [rsp+60h] [rbp-48h] BYREF
  char v15; // [rsp+68h] [rbp-40h]
  _QWORD *v16; // [rsp+70h] [rbp-38h] BYREF
  std::_Ref_count_base *v17; // [rsp+78h] [rbp-30h]
  __int64 *v18; // [rsp+80h] [rbp-28h]
  RTL_SRWLOCK SRWLock; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v20; // [rsp+B8h] [rbp+10h] BYREF
  RTL_SRWLOCK *p_SRWLock; // [rsp+C0h] [rbp+18h] BYREF
  RTL_SRWLOCK *v22; // [rsp+C8h] [rbp+20h] BYREF

  v14 = this;
  v15 = 1;
  try
  {
    Microsoft::Bluetooth::Foundation::DeviceIoTarget::OpenFileHandleTemplateMethod((Microsoft::Bluetooth::Foundation::DeviceIoTarget *)this);
    v15 = 0;
    Microsoft::Bluetooth::Foundation::Details::LockedFileHandleGate::Open((Microsoft::Bluetooth::Foundation::Details::LockedFileHandleGate *)&this[29]);
    v11[1] = v11;
    v11[0] = v11;
    AcquireSRWLockExclusive(this + 1);
    p_SRWLock = this + 1;
    LODWORD(this[19].Ptr) = 1;
    if ( this[18].Ptr )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        &p_SRWLock,
        0);
      Microsoft::Bluetooth::Foundation::DeviceIoTarget::InvokeStateChangeCallback(this, 2);
      AcquireSRWLockExclusive(this + 1);
      v22 = this + 1;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
        &p_SRWLock,
        &v22);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
    }
    v22 = this;
    ___splice_if_V_lambda_e9b6f7b60f8f207ba58c88e9538d22e0______list_impl_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft__V__intrusive_list_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEAA_KV__iterator_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___00_1234_AEBV__intrusive_list_ref_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___234_00__QEAV_lambda_e9b6f7b60f8f207ba58c88e9538d22e0____Z(
      v2,
      (unsigned int)v11,
      v3,
      this[22].Ptr,
      (__int64)&this[22],
      (__int64)&v22);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&p_SRWLock);
    v13[1] = v13;
    v13[0] = v13;
    SRWLock.Ptr = 0;
    v20 = 1;
    AcquireSRWLockExclusive(&SRWLock);
    p_SRWLock = &SRWLock;
    v16 = v13;
    v17 = (std::_Ref_count_base *)&SRWLock;
    v18 = &v20;
    v6 = (__int64 *)v11[0];
    v12[1] = v12;
    v12[0] = v12;
    while ( v6 != v11 )
    {
      v7 = v6;
      v6 = (__int64 *)*v6;
      if ( (unsigned __int8)_lambda_6328c143da26ebbc5687afddcffcf621_::operator()(&v16, v7 - 7) )
      {
        if ( v7 != v12 )
          _splice___list_impl_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft__V__intrusive_list_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEAAXV__iterator_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___00_2345_AEBV__intrusive_list_ref_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___345_00_Z(
            v4,
            (unsigned int)v12,
            v5,
            (_DWORD)v7,
            *v7);
      }
    }
    _splice___list_impl_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft__V__intrusive_list_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEAAXV__iterator_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___00_2345_AEBV__intrusive_list_ref_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___345_00_Z(
      v4,
      (unsigned int)v13,
      v5,
      v12[0],
      (__int64)v12);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&p_SRWLock);
    while ( 1 )
    {
      v8 = _try_pop_front___list_impl_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft__V__intrusive_list_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEAAPEAVIoTargetRequest_2345_XZ(v12);
      if ( !v8 )
        break;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, 995, 0);
    }
    Microsoft::Bluetooth::Foundation::Details::CountdownEvent::WaitForZero((Microsoft::Bluetooth::Foundation::Details::CountdownEvent *)&this[25]);
    AcquireSRWLockExclusive(&SRWLock);
    p_SRWLock = &SRWLock;
    while ( 1 )
    {
      v9 = _try_pop_front___list_impl_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft__V__intrusive_list_t_U__intrusive_member_hook_traits__MPEQIoTargetRequest_Details_Foundation_Bluetooth_Microsoft__Vintrusive_list_hook_345_0DI__Foundation_Bluetooth_Microsoft___234__Details_Foundation_Bluetooth_Microsoft__QEAAPEAVIoTargetRequest_2345_XZ(&v14);
      v10 = (struct Microsoft::Bluetooth::Foundation::Details::IoTargetRequest *)v9;
      if ( !v9 )
        break;
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
          &p_SRWLock,
          0);
        Microsoft::Bluetooth::Foundation::Details::CountdownEvent::Decrement((Microsoft::Bluetooth::Foundation::Details::CountdownEvent *)&v20);
        std::enable_shared_from_this<Microsoft::Bluetooth::Protocols::Avctp::AvctpChannelProvider>::shared_from_this(
          (char *)v10 + 40,
          &v16);
        Microsoft::Bluetooth::Foundation::DeviceIoTarget::SubmitRequest(
          (Microsoft::Bluetooth::Foundation::DeviceIoTarget *)this,
          v10);
        AcquireSRWLockExclusive(&SRWLock);
        v22 = &SRWLock;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
          &p_SRWLock,
          &v22);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &p_SRWLock,
      0);
    Microsoft::Bluetooth::Foundation::Details::CountdownEvent::WaitForZero((Microsoft::Bluetooth::Foundation::Details::CountdownEvent *)&v20);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&p_SRWLock);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18001e2e4  push    rbx
0x18001e2e6  push    rsi
0x18001e2e7  push    rdi
0x18001e2e8  sub     rsp, 90h
0x18001e2ef  mov     rsi, rcx
0x18001e2f2  mov     [rsp+0A8h+var_48], rcx
0x18001e2f7  mov     edi, 1
0x18001e2fc  mov     [rsp+0A8h+var_40], dil
0x18001e301  call    ?OpenFileHandleTemplateMethod@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Foundation::DeviceIoTarget::OpenFileHandleTemplateMethod(void)
0x18001e306  mov     [rsp+0A8h+var_40], 0
0x18001e30b  lea     rcx, [rsi+0E8h]; this
0x18001e312  call    ?Open@LockedFileHandleGate@Details@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Details::LockedFileHandleGate::Open(void)
0x18001e317  lea     rax, [rsp+0A8h+var_78]
0x18001e31c  mov     [rsp+0A8h+var_70], rax
0x18001e321  lea     rax, [rsp+0A8h+var_78]
0x18001e326  mov     [rsp+0A8h+var_78], rax
0x18001e32b  lea     rbx, [rsi+8]
0x18001e32f  mov     rcx, rbx; SRWLock
0x18001e332  call    cs:__imp_AcquireSRWLockExclusive
0x18001e338  mov     [rsp+0A8h+arg_10], rbx
0x18001e340  mov     [rsi+98h], edi
0x18001e346  cmp     qword ptr [rsi+90h], 0
0x18001e34e  jz      short loc_18001E39D
0x18001e350  xor     edx, edx
0x18001e352  lea     rcx, [rsp+0A8h+arg_10]
0x18001e35a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001e35f  lea     edx, [rdi+1]
0x18001e362  mov     rcx, rsi
0x18001e365  call    ?InvokeStateChangeCallback@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@AEBAXW4State@1234@@Z; Microsoft::Bluetooth::Foundation::DeviceIoTarget::InvokeStateChangeCallback(Microsoft::Bluetooth::Foundation::DeviceIoTarget::State)
0x18001e36a  mov     rcx, rbx; SRWLock
0x18001e36d  call    cs:__imp_AcquireSRWLockExclusive
0x18001e373  mov     [rsp+0A8h+arg_18], rbx
0x18001e37b  lea     rdx, [rsp+0A8h+arg_18]
0x18001e383  lea     rcx, [rsp+0A8h+arg_10]
0x18001e38b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x18001e390  lea     rcx, [rsp+0A8h+arg_18]
0x18001e398  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e39d  mov     [rsp+0A8h+arg_18], rsi
0x18001e3a5  lea     r9, [rsi+0B0h]
0x18001e3ac  lea     rax, [rsp+0A8h+arg_18]
0x18001e3b4  mov     [rsp+0A8h+var_80], rax
0x18001e3b9  mov     [rsp+0A8h+var_88], r9
0x18001e3be  mov     r9, [r9]
0x18001e3c1  lea     rdx, [rsp+0A8h+var_78]
0x18001e3c6  call    ??$splice_if@V_lambda_e9b6f7b60f8f207ba58c88e9538d22e0_@@@?$list_impl@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEAA_KV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@$00@1234@AEBV?$intrusive_list_ref_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@234@00$$QEAV_lambda_e9b6f7b60f8f207ba58c88e9538d22e0_@@@Z
0x18001e3cb  lea     rcx, [rsp+0A8h+arg_10]
0x18001e3d3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e3d8  lea     rax, [rsp+0A8h+var_58]
0x18001e3dd  mov     [rsp+0A8h+var_50], rax
0x18001e3e2  lea     rax, [rsp+0A8h+var_58]
0x18001e3e7  mov     [rsp+0A8h+var_58], rax
0x18001e3ec  xor     eax, eax
0x18001e3ee  mov     [rsp+0A8h+SRWLock.Ptr], rax
0x18001e3f6  mov     [rsp+0A8h+arg_8], 1
0x18001e402  lea     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18001e40a  call    cs:__imp_AcquireSRWLockExclusive
0x18001e410  lea     rax, [rsp+0A8h+SRWLock]
0x18001e418  mov     [rsp+0A8h+arg_10], rax
0x18001e420  lea     rax, [rsp+0A8h+var_58]
0x18001e425  mov     [rsp+0A8h+var_38], rax
0x18001e42a  lea     rax, [rsp+0A8h+SRWLock]
0x18001e432  mov     [rsp+0A8h+var_30], rax
0x18001e437  lea     rax, [rsp+0A8h+arg_8]
0x18001e43f  mov     [rsp+0A8h+var_28], rax
0x18001e447  mov     rdi, [rsp+0A8h+var_78]
0x18001e44c  lea     rax, [rsp+0A8h+var_68]
0x18001e451  mov     [rsp+0A8h+var_60], rax
0x18001e456  lea     rax, [rsp+0A8h+var_68]
0x18001e45b  mov     [rsp+0A8h+var_68], rax
0x18001e460  lea     rax, [rsp+0A8h+var_78]
0x18001e465  cmp     rdi, rax
0x18001e468  jz      short loc_18001E4A3
0x18001e46a  mov     rbx, rdi
0x18001e46d  mov     rdi, [rdi]
0x18001e470  lea     rdx, [rbx-38h]
0x18001e474  lea     rcx, [rsp+0A8h+var_38]
0x18001e479  call    ??R_lambda_6328c143da26ebbc5687afddcffcf621_@@QEBA@AEAVIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@@Z; _lambda_6328c143da26ebbc5687afddcffcf621_::operator()(Microsoft::Bluetooth::Foundation::Details::IoTargetRequest &)
0x18001e47e  test    al, al
0x18001e480  jz      short loc_18001E460
0x18001e482  lea     rax, [rsp+0A8h+var_68]
0x18001e487  cmp     rbx, rax
0x18001e48a  jz      short loc_18001E460
0x18001e48c  mov     rax, [rbx]
0x18001e48f  mov     [rsp+0A8h+var_88], rax
0x18001e494  mov     r9, rbx
0x18001e497  lea     rdx, [rsp+0A8h+var_68]
0x18001e49c  call    ?splice@?$list_impl@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEAAXV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@$00@2345@AEBV?$intrusive_list_ref_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@345@00@Z
0x18001e4a1  jmp     short loc_18001E460
0x18001e4a3  lea     rax, [rsp+0A8h+var_68]
0x18001e4a8  mov     [rsp+0A8h+var_88], rax
0x18001e4ad  mov     r9, [rsp+0A8h+var_68]
0x18001e4b2  lea     rdx, [rsp+0A8h+var_58]
0x18001e4b7  call    ?splice@?$list_impl@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEAAXV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@$00@2345@AEBV?$intrusive_list_ref_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@345@00@Z
0x18001e4bc  lea     rcx, [rsp+0A8h+arg_10]
0x18001e4c4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e4c9  jmp     short loc_18001E4E2
0x18001e4cb  mov     rcx, [r9]
0x18001e4ce  mov     rax, [rcx+20h]
0x18001e4d2  xor     r8d, r8d
0x18001e4d5  mov     edx, 3E3h
0x18001e4da  mov     rcx, r9
0x18001e4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4e2  lea     rcx, [rsp+0A8h+var_68]
0x18001e4e7  call    ?try_pop_front@?$list_impl@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEAAPEAVIoTargetRequest@2345@XZ
0x18001e4ec  test    rax, rax
0x18001e4ef  mov     r9, rax
0x18001e4f2  jnz     short loc_18001E4CB
0x18001e4f4  lea     rcx, [rsi+0C8h]; this
0x18001e4fb  call    ?WaitForZero@CountdownEvent@Details@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Details::CountdownEvent::WaitForZero(void)
0x18001e500  lea     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18001e508  call    cs:__imp_AcquireSRWLockExclusive
0x18001e50e  lea     rax, [rsp+0A8h+SRWLock]
0x18001e516  mov     [rsp+0A8h+arg_10], rax
0x18001e51e  lea     rcx, [rsp+0A8h+var_48]
0x18001e523  call    ?try_pop_front@?$list_impl@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_t@U?$intrusive_member_hook_traits@$MPEQIoTargetRequest@Details@Foundation@Bluetooth@Microsoft@@Vintrusive_list_hook@345@0DI@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEAAPEAVIoTargetRequest@2345@XZ
0x18001e528  mov     rbx, rax
0x18001e52b  test    rax, rax
0x18001e52e  jz      loc_18001E5D4
0x18001e534  mov     rcx, [rax]
0x18001e537  mov     rax, [rcx+10h]
0x18001e53b  mov     rcx, rbx
0x18001e53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e543  test    al, al
0x18001e545  jz      short loc_18001E51E
0x18001e547  xor     edx, edx
0x18001e549  lea     rcx, [rsp+0A8h+arg_10]
0x18001e551  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001e556  lea     rcx, [rsp+0A8h+arg_8]; this
0x18001e55e  call    ?Decrement@CountdownEvent@Details@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Details::CountdownEvent::Decrement(void)
0x18001e563  lea     rcx, [rbx+28h]
0x18001e567  lea     rdx, [rsp+0A8h+var_38]
0x18001e56c  call    ?shared_from_this@?$enable_shared_from_this@VAvctpChannelProvider@Avctp@Protocols@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAvctpChannelProvider@Avctp@Protocols@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Protocols::Avctp::AvctpChannelProvider>::shared_from_this(void)
0x18001e571  mov     rdx, rbx; struct Microsoft::Bluetooth::Foundation::Details::IoTargetRequest *
0x18001e574  mov     rcx, rsi; this
0x18001e577  call    ?SubmitRequest@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@AEAAXAEAVIoTargetRequest@Details@234@@Z; Microsoft::Bluetooth::Foundation::DeviceIoTarget::SubmitRequest(Microsoft::Bluetooth::Foundation::Details::IoTargetRequest &)
0x18001e57c  lea     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x18001e584  call    cs:__imp_AcquireSRWLockExclusive
0x18001e58a  lea     rax, [rsp+0A8h+SRWLock]
0x18001e592  mov     [rsp+0A8h+arg_18], rax
0x18001e59a  lea     rdx, [rsp+0A8h+arg_18]
0x18001e5a2  lea     rcx, [rsp+0A8h+arg_10]
0x18001e5aa  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x18001e5af  lea     rcx, [rsp+0A8h+arg_18]
0x18001e5b7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e5bc  mov     rcx, [rsp+0A8h+var_30]; this
0x18001e5c1  test    rcx, rcx
0x18001e5c4  jz      loc_18001E51E
0x18001e5ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e5cf  jmp     loc_18001E51E
0x18001e5d4  xor     edx, edx
0x18001e5d6  lea     rcx, [rsp+0A8h+arg_10]
0x18001e5de  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001e5e3  lea     rcx, [rsp+0A8h+arg_8]; this
0x18001e5eb  call    ?WaitForZero@CountdownEvent@Details@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::Details::CountdownEvent::WaitForZero(void)
0x18001e5f0  nop
0x18001e5f1  lea     rcx, [rsp+0A8h+arg_10]
0x18001e5f9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e5fe  nop
0x18001e5ff  add     rsp, 90h
0x18001e606  pop     rdi
0x18001e607  pop     rsi
0x18001e608  pop     rbx
0x18001e609  retn
```
