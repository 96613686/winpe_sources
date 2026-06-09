# Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider::Shutdown(void)

- ea: `0x18002fb00`
- end: `0x18002fe7b`
- name: `?Shutdown@AvctpProfileServiceProvider@Avctp@Protocols@Bluetooth@Microsoft@@QEAAXXZ`
- size: `891`
- prototype: `void __fastcall(Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027ec0`

## callees

- `0x180004060`
- `0x18000ab4c`
- `0x18000de78`
- `0x18000fcf8`
- `0x18000fe8c`
- `0x180012554`
- `0x1800157c0`
- `0x180019dd4`
- `0x180023374`
- `0x18002ec88`
- `0x18002ecc8`
- `0x18002f0e0`
- `0x18002fb00`
- `0x180030080`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fc90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fc90`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider::Shutdown(
        Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider *this)
{
  Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider *v1; // rsi
  bool v2; // dl
  char v3; // r8
  char IsEnabled; // al
  __int64 v5; // rdx
  char *v6; // rbx
  char *v7; // rax
  _QWORD *v8; // rax
  const char *v9; // r9
  _QWORD **v10; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  char *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  _QWORD *v18; // rbx
  _QWORD *v19; // r14
  char v20; // dl
  char v21; // r8
  _QWORD *v22; // [rsp+50h] [rbp-78h] BYREF
  __int64 v23; // [rsp+58h] [rbp-70h]
  char v24[8]; // [rsp+60h] [rbp-68h] BYREF
  std::_Ref_count_base *v25; // [rsp+68h] [rbp-60h]
  __int128 v26; // [rsp+70h] [rbp-58h] BYREF
  __int64 v27; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  char v29; // [rsp+D0h] [rbp+8h]
  char *v30; // [rsp+D8h] [rbp+10h] BYREF
  char *v31; // [rsp+E0h] [rbp+18h]

  v29 = (char)this;
  v1 = this;
  v2 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
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
      12,
      &WPP_c64d18cdcabb334f470ed39ab9995d91_Traceguids,
      (char)this);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl'::`2'::impl);
  v5 = *((_QWORD *)v1 + 6);
  *((_QWORD *)v1 + 6) = 0;
  if ( IsEnabled )
  {
    if ( v5 )
      std::default_delete<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>::operator()();
    wil::operation_guard::close_and_wait(*((wil::operation_guard **)v1 + 10));
    v6 = (char *)v1 + 64;
    v31 = (char *)v1 + 64;
    v7 = (char *)**((_QWORD **)v1 + 8);
    v30 = v7;
    while ( !v7[25] )
    {
      try
      {
        v8 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)v7 + 8) + 24LL))(
                         *((_QWORD *)v7 + 8),
                         v24);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 32LL))(*v8);
        if ( v25 )
          std::_Ref_count_base::_Decref(v25);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpprofileserviceprovider.cpp",
          v9);
        LOBYTE(v1) = v29;
        v6 = v31;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(&v30);
      v7 = v30;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>>,0>>::clear(v6);
  }
  else
  {
    if ( v5 )
      std::default_delete<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>::operator()();
    std::map<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>::map<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>(&v22);
    AcquireSRWLockExclusive((PSRWLOCK)v1 + 7);
    v30 = (char *)v1 + 56;
    v10 = (_QWORD **)((char *)v1 + 64);
    if ( &v22 != (_QWORD **)((char *)v1 + 64) )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>>,0>>::clear(&v22);
      v11 = v22;
      v22 = *v10;
      *v10 = v11;
      v12 = v23;
      v23 = *((_QWORD *)v1 + 9);
      *((_QWORD *)v1 + 9) = v12;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v30);
    v26 = 0;
    v27 = 0;
    v15 = (char *)*v22;
    v30 = (char *)*v22;
    while ( !v15[25] )
    {
      v16 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)v15 + 8) + 24LL))(
                        *((_QWORD *)v15 + 8),
                        v24);
      v17 = (_QWORD *)*((_QWORD *)&v26 + 1);
      if ( *((_QWORD *)&v26 + 1) == v27 )
      {
        std::vector<std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>>>(
          &v26,
          *((_QWORD *)&v26 + 1),
          v16);
      }
      else
      {
        **((_QWORD **)&v26 + 1) = 0;
        v17[1] = 0;
        *v17 = *v16;
        v17[1] = v16[1];
        *v16 = 0;
        v16[1] = 0;
        *((_QWORD *)&v26 + 1) += 16LL;
      }
      if ( v25 )
        std::_Ref_count_base::_Decref(v25);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(&v30);
      v15 = v30;
    }
    v19 = (_QWORD *)*((_QWORD *)&v26 + 1);
    v18 = (_QWORD *)v26;
    if ( (_QWORD)v26 != *((_QWORD *)&v26 + 1) )
    {
      do
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 32LL))(*v18);
        v18 += 2;
      }
      while ( v18 != v19 );
      v18 = (_QWORD *)v26;
    }
    if ( v18 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>>>>(
        v18,
        *((_QWORD *)&v26 + 1),
        v13,
        v14);
      std::_Deallocate<16>((void *)v26, (struct std::nothrow_t *)((v27 - v26) & 0xFFFFFFFFFFFFFFF0uLL));
      v26 = 0;
      v27 = 0;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>>>,0>>((void **)&v22);
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v20 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v21 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v21 = 0;
  }
  if ( v20 || v21 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      v21,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      13,
      &WPP_c64d18cdcabb334f470ed39ab9995d91_Traceguids,
      (char)v1);
}

```

## disassembly

```asm
0x18002fb00  mov     [rsp+arg_0], rcx
0x18002fb05  push    rbx
0x18002fb06  push    rsi
0x18002fb07  push    rdi
0x18002fb08  push    r12
0x18002fb0a  push    r13
0x18002fb0c  push    r14
0x18002fb0e  push    r15
0x18002fb10  sub     rsp, 90h
0x18002fb17  mov     rsi, rcx
0x18002fb1a  lea     r15, WPP_GLOBAL_Control
0x18002fb21  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb28  cmp     rcx, r15
0x18002fb2b  jz      short loc_18002FB3F
0x18002fb2d  test    byte ptr [rcx+1Ch], 1
0x18002fb31  jz      short loc_18002FB3F
0x18002fb33  cmp     byte ptr [rcx+19h], 5
0x18002fb37  jb      short loc_18002FB3F
0x18002fb39  mov     dl, 1
0x18002fb3b  xor     edi, edi
0x18002fb3d  jmp     short loc_18002FB44
0x18002fb3f  xor     edi, edi
0x18002fb41  mov     dl, dil; int
0x18002fb44  lea     r13, WPP_RECORDER_INITIALIZED
0x18002fb4b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002fb52  jz      short loc_18002FB5D
0x18002fb54  cmp     [rcx+30h], di
0x18002fb58  mov     r8b, 1
0x18002fb5b  jnz     short loc_18002FB60
0x18002fb5d  mov     r8b, dil; int
0x18002fb60  test    dl, dl
0x18002fb62  jnz     short loc_18002FB72
0x18002fb64  test    r8b, r8b
0x18002fb67  jnz     short loc_18002FB72
0x18002fb69  lea     r12, WPP_c64d18cdcabb334f470ed39ab9995d91_Traceguids
0x18002fb70  jmp     short loc_18002FBA4
0x18002fb72  mov     qword ptr [rsp+0C8h+var_88], rsi; char
0x18002fb77  lea     r12, WPP_c64d18cdcabb334f470ed39ab9995d91_Traceguids
0x18002fb7e  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x18002fb83  mov     [rsp+0C8h+var_98], 0Ch; __int16
0x18002fb8a  mov     [rsp+0C8h+var_A0], 1; int
0x18002fb92  mov     [rsp+0C8h+var_A8], 5; char
0x18002fb97  mov     r9, [rcx+28h]; int
0x18002fb9b  mov     rcx, [rcx+10h]; int
0x18002fb9f  call    WPP_RECORDER_AND_TRACE_SF_q
0x18002fba4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59215879@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879> `wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl(void)'::`2'::impl
0x18002fbab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(void)
0x18002fbb0  mov     rdx, [rsi+30h]
0x18002fbb4  mov     [rsi+30h], rdi
0x18002fbb8  test    al, al
0x18002fbba  jz      loc_18002FC74
0x18002fbc0  test    rdx, rdx
0x18002fbc3  jz      short loc_18002FBCA
0x18002fbc5  call    ??R?$default_delete@VEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@@std@@QEBAXPEAVEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@@Z; std::default_delete<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>::operator()(Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration *)
0x18002fbca  mov     rcx, [rsi+50h]; this
0x18002fbce  call    ?close_and_wait@operation_guard@wil@@QEAAXXZ; wil::operation_guard::close_and_wait(void)
0x18002fbd3  lea     rbx, [rsi+40h]
0x18002fbd7  mov     [rsp+0C8h+arg_10], rbx
0x18002fbdf  mov     rax, [rbx]
0x18002fbe2  mov     rax, [rax]
0x18002fbe5  mov     [rsp+0C8h+arg_8], rax
0x18002fbed  cmp     [rax+19h], dil
0x18002fbf1  jnz     short loc_18002FC67
0x18002fbf3  mov     rcx, [rax+40h]
0x18002fbf7  mov     rax, [rcx]
0x18002fbfa  lea     rdx, [rsp+0C8h+var_68]
0x18002fbff  mov     rax, [rax+18h]
0x18002fc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc08  mov     rcx, [rax]
0x18002fc0b  mov     rax, [rcx]
0x18002fc0e  mov     rax, [rax+20h]
0x18002fc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc17  mov     rcx, [rsp+0C8h+var_60]; this
0x18002fc1c  test    rcx, rcx
0x18002fc1f  jz      short loc_18002FC27
0x18002fc21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fc26  nop
0x18002fc27  jmp     short loc_18002FC50
0x18002fc29  lea     r15, WPP_GLOBAL_Control
0x18002fc30  xor     edi, edi
0x18002fc32  lea     r13, WPP_RECORDER_INITIALIZED
0x18002fc39  lea     r12, WPP_c64d18cdcabb334f470ed39ab9995d91_Traceguids
0x18002fc40  mov     rsi, [rsp+0C8h+arg_0]
0x18002fc48  mov     rbx, [rsp+0C8h+arg_10]
0x18002fc50  lea     rcx, [rsp+0C8h+arg_8]
0x18002fc58  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UChosenTransportContext@Audio@Bluetooth@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(void)
0x18002fc5d  mov     rax, [rsp+0C8h+arg_8]
0x18002fc65  jmp     short loc_18002FBED
0x18002fc67  mov     rcx, rbx
0x18002fc6a  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAVCTPServiceInterface@Avctp@Protocols@Bluetooth@Microsoft@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAVCTPServiceInterface@Avctp@Protocols@Bluetooth@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>>,0>>::clear(void)
0x18002fc6f  jmp     loc_18002FE02
0x18002fc74  test    rdx, rdx
0x18002fc77  jz      short loc_18002FC7E
0x18002fc79  call    ??R?$default_delete@VEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@@std@@QEBAXPEAVEventRegistration@EventNotifier@Foundation@Bluetooth@Microsoft@@@Z; std::default_delete<Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration>::operator()(Microsoft::Bluetooth::Foundation::EventNotifier::EventRegistration *)
0x18002fc7e  lea     rcx, [rsp+0C8h+var_78]
0x18002fc83  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAVCTPServiceInterface@Avctp@Protocols@Bluetooth@Microsoft@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAVCTPServiceInterface@Avctp@Protocols@Bluetooth@Microsoft@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>::map<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>(void)
0x18002fc88  nop
0x18002fc89  lea     rbx, [rsi+38h]
0x18002fc8d  mov     rcx, rbx; SRWLock
0x18002fc90  call    cs:__imp_AcquireSRWLockExclusive
0x18002fc96  mov     [rsp+0C8h+arg_8], rbx
0x18002fc9e  lea     rbx, [rsi+40h]
0x18002fca2  lea     rax, [rsp+0C8h+var_78]
0x18002fca7  cmp     rax, rbx
0x18002fcaa  jz      short loc_18002FCD8
0x18002fcac  lea     rcx, [rsp+0C8h+var_78]
0x18002fcb1  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAVCTPServiceInterface@Avctp@Protocols@Bluetooth@Microsoft@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAVCTPServiceInterface@Avctp@Protocols@Bluetooth@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Protocols::Avctp::AVCTPServiceInterface>>>,0>>::clear(void)
0x18002fcb6  mov     rcx, [rsp+0C8h+var_78]
0x18002fcbb  mov     rax, [rbx]
0x18002fcbe  mov     [rsp+0C8h+var_78], rax
0x18002fcc3  mov     [rbx], rcx
0x18002fcc6  mov     rcx, [rsp+0C8h+var_70]
0x18002fccb  mov     rax, [rbx+8]
0x18002fccf  mov     [rsp+0C8h+var_70], rax
0x18002fcd4  mov     [rbx+8], rcx
0x18002fcd8  lea     rcx, [rsp+0C8h+arg_8]
0x18002fce0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002fce5  xorps   xmm0, xmm0
0x18002fce8  movdqu  [rsp+0C8h+var_58], xmm0
0x18002fcee  mov     [rsp+0C8h+var_48], rdi
0x18002fcf6  mov     rax, [rsp+0C8h+var_78]
0x18002fcfb  mov     rax, [rax]
0x18002fcfe  mov     [rsp+0C8h+arg_8], rax
0x18002fd06  cmp     [rax+19h], dil
0x18002fd0a  jnz     loc_18002FD90
0x18002fd10  mov     rcx, [rax+40h]
0x18002fd14  mov     rax, [rcx]
0x18002fd17  lea     rdx, [rsp+0C8h+var_68]
0x18002fd1c  mov     rax, [rax+18h]
0x18002fd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd25  nop
0x18002fd26  mov     rdx, qword ptr [rsp+0C8h+var_58+8]
0x18002fd2b  cmp     rdx, [rsp+0C8h+var_48]
0x18002fd33  jz      short loc_18002FD59
0x18002fd35  mov     [rdx], rdi
0x18002fd38  mov     [rdx+8], rdi
0x18002fd3c  mov     rcx, [rax]
0x18002fd3f  mov     [rdx], rcx
0x18002fd42  mov     rcx, [rax+8]
0x18002fd46  mov     [rdx+8], rcx
0x18002fd4a  mov     [rax], rdi
0x18002fd4d  mov     [rax+8], rdi
0x18002fd51  add     qword ptr [rsp+0C8h+var_58+8], 10h
0x18002fd57  jmp     short loc_18002FD67
0x18002fd59  mov     r8, rax
0x18002fd5c  lea     rcx, [rsp+0C8h+var_58]
0x18002fd61  call    ??$_Emplace_reallocate@V?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@std@@@?$vector@V?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@std@@V?$allocator@V?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>> * const,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>> &&)
0x18002fd66  nop
0x18002fd67  mov     rcx, [rsp+0C8h+var_60]; this
0x18002fd6c  test    rcx, rcx
0x18002fd6f  jz      short loc_18002FD76
0x18002fd71  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fd76  lea     rcx, [rsp+0C8h+arg_8]
0x18002fd7e  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UChosenTransportContext@Audio@Bluetooth@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(void)
0x18002fd83  mov     rax, [rsp+0C8h+arg_8]
0x18002fd8b  jmp     loc_18002FD06
0x18002fd90  mov     rbx, qword ptr [rsp+0C8h+var_58]
0x18002fd95  mov     r14, qword ptr [rsp+0C8h+var_58+8]
0x18002fd9a  cmp     rbx, r14
0x18002fd9d  jz      short loc_18002FDBC
0x18002fd9f  mov     rcx, [rbx]
0x18002fda2  mov     rax, [rcx]
0x18002fda5  mov     rax, [rax+20h]
0x18002fda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdae  add     rbx, 10h
0x18002fdb2  cmp     rbx, r14
0x18002fdb5  jnz     short loc_18002FD9F
0x18002fdb7  mov     rbx, qword ptr [rsp+0C8h+var_58]
0x18002fdbc  test    rbx, rbx
0x18002fdbf  jz      short loc_18002FDF8
0x18002fdc1  mov     rdx, qword ptr [rsp+0C8h+var_58+8]
0x18002fdc6  mov     rcx, rbx
0x18002fdc9  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>>>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>> *,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>> * const,std::allocator<std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequest<long>>> &)
0x18002fdce  mov     rcx, qword ptr [rsp+0C8h+var_58]
0x18002fdd3  mov     rdx, [rsp+0C8h+var_48]
0x18002fddb  sub     rdx, rcx
0x18002fdde  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002fde2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002fde7  xorps   xmm0, xmm0
0x18002fdea  movdqu  [rsp+0C8h+var_58], xmm0
0x18002fdf0  mov     [rsp+0C8h+var_48], rdi
0x18002fdf8  lea     rcx, [rsp+0C8h+var_78]
0x18002fdfd  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VA2dpDeviceImpl@Details@Service@A2dp@Profiles@Bluetooth@Microsoft@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VA2dpDeviceImpl@Details@Service@A2dp@Profiles@Bluetooth@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpDeviceImpl>>>,0>>(void)
0x18002fe02  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe09  cmp     rcx, r15
0x18002fe0c  jz      short loc_18002FE1C
0x18002fe0e  test    byte ptr [rcx+1Ch], 1
0x18002fe12  jz      short loc_18002FE1C
0x18002fe14  cmp     byte ptr [rcx+19h], 5
0x18002fe18  mov     dl, 1
0x18002fe1a  jnb     short loc_18002FE1F
0x18002fe1c  mov     dl, dil; int
0x18002fe1f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002fe26  jz      short loc_18002FE31
0x18002fe28  cmp     [rcx+30h], di
0x18002fe2c  mov     r8b, 1
0x18002fe2f  jnz     short loc_18002FE34
0x18002fe31  mov     r8b, dil; int
0x18002fe34  test    dl, dl
0x18002fe36  jnz     short loc_18002FE3D
0x18002fe38  test    r8b, r8b
0x18002fe3b  jz      short loc_18002FE68
0x18002fe3d  mov     qword ptr [rsp+0C8h+var_88], rsi; char
0x18002fe42  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x18002fe47  mov     [rsp+0C8h+var_98], 0Dh; __int16
0x18002fe4e  mov     [rsp+0C8h+var_A0], 1; int
0x18002fe56  mov     [rsp+0C8h+var_A8], 5; char
0x18002fe5b  mov     r9, [rcx+28h]; int
0x18002fe5f  mov     rcx, [rcx+10h]; int
0x18002fe63  call    WPP_RECORDER_AND_TRACE_SF_q
0x18002fe68  add     rsp, 90h
0x18002fe6f  pop     r15
0x18002fe71  pop     r14
0x18002fe73  pop     r13
0x18002fe75  pop     r12
0x18002fe77  pop     rdi
0x18002fe78  pop     rsi
0x18002fe79  pop     rbx
0x18002fe7a  retn
```
