# Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::StartEventRead(void)

- ea: `0x1800499bc`
- end: `0x180049c79`
- name: `?StartEventRead@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@AEAAXXZ`
- size: `701`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180048218`
- `0x1800484b8`
- `0x180049770`

## callees

- `0x180001dd0`
- `0x180003fbc`
- `0x180004060`
- `0x180009920`
- `0x18000b69c`
- `0x18000de78`
- `0x18000deb0`
- `0x18000f3a0`
- `0x180012168`
- `0x180012554`
- `0x180023374`
- `0x1800334f8`
- `0x1800478e0`
- `0x180047c94`
- `0x180047fac`
- `0x1800499bc`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049a71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049a71`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::StartEventRead(
        RTL_SRWLOCK *this)
{
  char v2; // dl
  char v3; // r8
  __int64 v4; // rax
  char IsEnabled; // al
  std::_Ref_count_base *v6; // rbx
  __int64 *v7; // rax
  _QWORD *v8; // rax
  __int64 *v9; // rax
  RTL_SRWLOCK **v10; // r8
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v14; // [rsp+68h] [rbp-98h]
  std::_Ref_count_base *v15[2]; // [rsp+70h] [rbp-90h] BYREF
  RTL_SRWLOCK *v16; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+90h] [rbp-70h]
  __int64 v19; // [rsp+98h] [rbp-68h]
  __int64 v20; // [rsp+A0h] [rbp-60h] BYREF
  char v21[8]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v22; // [rsp+B8h] [rbp-48h]
  char v23[8]; // [rsp+C0h] [rbp-40h] BYREF
  char v24[104]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v25; // [rsp+130h] [rbp+30h]

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v2 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v2 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v3 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v3 = 0;
  }
  if ( v2 || v3 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      v3,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      15,
      &WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids,
      (char)this);
  *(_OWORD *)v15 = 0;
  AcquireSRWLockExclusive(this + 3);
  v11 = this + 3;
  v4 = (*(__int64 (__fastcall **)(PVOID, __int64 *, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)this[11].Ptr + 32LL))(
         this[11].Ptr,
         &v13,
         4276236,
         0,
         0,
         17);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(&this[15], v4);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::operator=(
    v15,
    &this[15]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl'::`2'::impl);
  v6 = v15[0];
  if ( IsEnabled )
  {
    std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
      &v11,
      &this[1].Ptr);
    v7 = std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
           &v13,
           &this[15].Ptr);
    v16 = v11;
    v17 = v12;
    v18 = *v7;
    v19 = v7[1];
    *v7 = 0;
    v7[1] = 0;
    std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
      &v20,
      &this[25].Ptr);
    v25 = 0;
    v25 = wistd::__function::__func__lambda_4b84b87ae400067f4713791c4e511659__void___cdecl_void__::__func__lambda_4b84b87ae400067f4713791c4e511659__void___cdecl_void__(
            v24,
            &v16);
    lambda_4b84b87ae400067f4713791c4e511659_::__lambda_4b84b87ae400067f4713791c4e511659_(&v16);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v6 + 1) + 24LL))(*((_QWORD *)v6 + 1), v23);
    wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>((__int64)v23);
    if ( v14 )
      std::_Ref_count_base::_Decwref(v14);
  }
  else
  {
    v8 = (_QWORD *)std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(
                     &this[1],
                     v21);
    std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
      &v11,
      v8);
    v9 = std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
           &v13,
           &this[15].Ptr);
    v16 = *v10;
    v17 = (std::_Ref_count_base *)v10[1];
    *v10 = 0;
    v10[1] = 0;
    v18 = *v9;
    v19 = v9[1];
    *v9 = 0;
    v9[1] = 0;
    wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_3938f83892fac809731ff2af30ce4dfc__void_(
      v23,
      &v16);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v6 + 1) + 24LL))(*((_QWORD *)v6 + 1), v23);
    wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>((__int64)v23);
    if ( v14 )
      std::_Ref_count_base::_Decwref(v14);
    if ( v12 )
      std::_Ref_count_base::_Decwref(v12);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
  }
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
}

```

## disassembly

```asm
0x1800499bc  push    rbp
0x1800499be  push    rbx
0x1800499bf  push    rsi
0x1800499c0  push    rdi
0x1800499c1  push    r14
0x1800499c3  push    r15
0x1800499c5  lea     rbp, [rsp-48h]
0x1800499ca  sub     rsp, 148h
0x1800499d1  mov     rax, cs:__security_cookie
0x1800499d8  xor     rax, rsp
0x1800499db  mov     [rbp+70h+var_38], rax
0x1800499df  mov     rdi, rcx
0x1800499e2  lea     rax, WPP_GLOBAL_Control
0x1800499e9  xor     r15d, r15d
0x1800499ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800499f3  cmp     rcx, rax
0x1800499f6  jz      short loc_180049A06
0x1800499f8  test    byte ptr [rcx+1Ch], 1
0x1800499fc  jz      short loc_180049A06
0x1800499fe  cmp     byte ptr [rcx+19h], 5
0x180049a02  mov     dl, 1
0x180049a04  jnb     short loc_180049A09
0x180049a06  mov     dl, r15b; int
0x180049a09  lea     rax, WPP_RECORDER_INITIALIZED
0x180049a10  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180049a17  jz      short loc_180049A23
0x180049a19  cmp     [rcx+30h], r15w
0x180049a1e  mov     r8b, 1
0x180049a21  jnz     short loc_180049A26
0x180049a23  mov     r8b, r15b; int
0x180049a26  test    dl, dl
0x180049a28  jnz     short loc_180049A2F
0x180049a2a  test    r8b, r8b
0x180049a2d  jz      short loc_180049A61
0x180049a2f  mov     qword ptr [rsp+170h+var_130], rdi; char
0x180049a34  lea     rax, WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids
0x180049a3b  mov     [rsp+170h+MessageGuid], rax; MessageGuid
0x180049a40  mov     [rsp+170h+var_140], 0Fh; __int16
0x180049a47  mov     [rsp+170h+var_148], 1; int
0x180049a4f  mov     [rsp+170h+var_150], 5; char
0x180049a54  mov     r9, [rcx+28h]; int
0x180049a58  mov     rcx, [rcx+10h]; int
0x180049a5c  call    WPP_RECORDER_AND_TRACE_SF_q
0x180049a61  xorps   xmm0, xmm0
0x180049a64  movdqu  xmmword ptr [rsp+170h+var_100], xmm0
0x180049a6a  lea     rbx, [rdi+18h]
0x180049a6e  mov     rcx, rbx; SRWLock
0x180049a71  call    cs:__imp_AcquireSRWLockExclusive
0x180049a77  mov     [rsp+170h+var_120], rbx
0x180049a7c  mov     rcx, [rdi+58h]
0x180049a80  mov     rax, [rcx]
0x180049a83  mov     qword ptr [rsp+170h+var_148], 11h
0x180049a8c  mov     qword ptr [rsp+170h+var_150], r15
0x180049a91  xor     r9d, r9d
0x180049a94  mov     r8d, 41400Ch
0x180049a9a  lea     rdx, [rsp+170h+var_110]
0x180049a9f  mov     rax, [rax+20h]
0x180049aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049aa8  lea     rsi, [rdi+78h]
0x180049aac  mov     rdx, rax
0x180049aaf  mov     rcx, rsi
0x180049ab2  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x180049ab7  mov     rcx, [rsp+170h+var_108]; this
0x180049abc  test    rcx, rcx
0x180049abf  jz      short loc_180049AC6
0x180049ac1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049ac6  mov     rdx, rsi
0x180049ac9  lea     rcx, [rsp+170h+var_100]
0x180049ace  call    ??4?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049ad3  nop
0x180049ad4  lea     rcx, [rsp+170h+var_120]
0x180049ad9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180049ade  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59215879@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879> `wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl(void)'::`2'::impl
0x180049ae5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(void)
0x180049aea  mov     rbx, [rsp+170h+var_100]
0x180049aef  test    al, al
0x180049af1  jz      loc_180049B9F
0x180049af7  lea     rdx, [rdi+8]
0x180049afb  lea     rcx, [rsp+170h+var_120]
0x180049b00  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049b05  mov     rdx, rsi
0x180049b08  lea     rcx, [rsp+170h+var_110]
0x180049b0d  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049b12  mov     rcx, [rsp+170h+var_120]
0x180049b17  mov     [rbp+70h+var_F0], rcx
0x180049b1b  mov     rcx, [rsp+170h+var_118]
0x180049b20  mov     [rbp+70h+var_E8], rcx
0x180049b24  mov     rcx, [rax]
0x180049b27  mov     [rbp+70h+var_E0], rcx
0x180049b2b  mov     rcx, [rax+8]
0x180049b2f  mov     [rbp+70h+var_D8], rcx
0x180049b33  mov     [rax], r15
0x180049b36  mov     [rax+8], r15
0x180049b3a  lea     rdx, [rdi+0C8h]
0x180049b41  lea     rcx, [rbp+70h+var_D0]
0x180049b45  call    ??0?$shared_ptr@VThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl> const &)
0x180049b4a  mov     [rbp+70h+var_40], r15
0x180049b4e  lea     rdx, [rbp+70h+var_F0]
0x180049b52  lea     rcx, [rbp+70h+var_A8]
0x180049b56  call    wistd____function____func__lambda_4b84b87ae400067f4713791c4e511659__void___cdecl_void______func__lambda_4b84b87ae400067f4713791c4e511659__void___cdecl_void__
0x180049b5b  mov     [rbp+70h+var_40], rax
0x180049b5f  lea     rcx, [rbp+70h+var_F0]
0x180049b63  call    _lambda_4b84b87ae400067f4713791c4e511659_____lambda_4b84b87ae400067f4713791c4e511659_
0x180049b68  nop
0x180049b69  mov     rcx, [rbx+8]
0x180049b6d  mov     rax, [rcx]
0x180049b70  lea     rdx, [rbp+70h+var_B0]
0x180049b74  mov     rax, [rax+18h]
0x180049b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b7d  nop
0x180049b7e  lea     rcx, [rbp+70h+var_B0]
0x180049b82  call    ??1?$function@$$A6AXU?$IoTargetIoctlResult@V?$RequestBufferView@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>(void)
0x180049b87  mov     rcx, [rsp+170h+var_108]; this
0x180049b8c  test    rcx, rcx
0x180049b8f  jz      loc_180049C4E
0x180049b95  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180049b9a  jmp     loc_180049C4E
0x180049b9f  lea     rdx, [rbp+70h+var_C0]
0x180049ba3  lea     rcx, [rdi+8]
0x180049ba7  call    ?shared_from_this@?$enable_shared_from_this@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(void)
0x180049bac  mov     rdx, rax
0x180049baf  lea     rcx, [rsp+170h+var_120]
0x180049bb4  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049bb9  mov     r8, rax
0x180049bbc  mov     rdx, rsi
0x180049bbf  lea     rcx, [rsp+170h+var_110]
0x180049bc4  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049bc9  mov     rcx, [r8]
0x180049bcc  mov     [rbp+70h+var_F0], rcx
0x180049bd0  mov     rcx, [r8+8]
0x180049bd4  mov     [rbp+70h+var_E8], rcx
0x180049bd8  mov     [r8], r15
0x180049bdb  mov     [r8+8], r15
0x180049bdf  mov     rcx, [rax]
0x180049be2  mov     [rbp+70h+var_E0], rcx
0x180049be6  mov     rcx, [rax+8]
0x180049bea  mov     [rbp+70h+var_D8], rcx
0x180049bee  mov     [rax], r15
0x180049bf1  mov     [rax+8], r15
0x180049bf5  lea     rdx, [rbp+70h+var_F0]
0x180049bf9  lea     rcx, [rbp+70h+var_B0]
0x180049bfd  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_3938f83892fac809731ff2af30ce4dfc__void_
0x180049c02  nop
0x180049c03  mov     rcx, [rbx+8]
0x180049c07  mov     rax, [rcx]
0x180049c0a  lea     rdx, [rbp+70h+var_B0]
0x180049c0e  mov     rax, [rax+18h]
0x180049c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c17  nop
0x180049c18  lea     rcx, [rbp+70h+var_B0]
0x180049c1c  call    ??1?$function@$$A6AXU?$IoTargetIoctlResult@V?$RequestBufferView@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>(void)
0x180049c21  mov     rcx, [rsp+170h+var_108]; this
0x180049c26  test    rcx, rcx
0x180049c29  jz      short loc_180049C30
0x180049c2b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180049c30  mov     rcx, [rsp+170h+var_118]; this
0x180049c35  test    rcx, rcx
0x180049c38  jz      short loc_180049C3F
0x180049c3a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180049c3f  mov     rcx, [rbp+70h+var_B8]; this
0x180049c43  test    rcx, rcx
0x180049c46  jz      short loc_180049C4E
0x180049c48  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049c4d  nop
0x180049c4e  mov     rcx, [rsp+170h+var_100+8]; this
0x180049c53  test    rcx, rcx
0x180049c56  jz      short loc_180049C5D
0x180049c58  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049c5d  mov     rcx, [rbp+70h+var_38]
0x180049c61  xor     rcx, rsp; StackCookie
0x180049c64  call    __security_check_cookie
0x180049c69  add     rsp, 148h
0x180049c70  pop     r15
0x180049c72  pop     r14
0x180049c74  pop     rdi
0x180049c75  pop     rsi
0x180049c76  pop     rbx
0x180049c77  pop     rbp
0x180049c78  retn
```
