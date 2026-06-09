# AVCTPService::StopAsync(void)

- ea: `0x180026ef0`
- end: `0x1800270bc`
- name: `?StopAsync@AVCTPService@@UEAA?AV?$shared_ptr@V?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@@std@@XZ`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800021dc`
- `0x180003fbc`
- `0x180004060`
- `0x18000994c`
- `0x18000dcc4`
- `0x18000de78`
- `0x18000f30c`
- `0x180023374`
- `0x180026ef0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026fd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026fd4`

## string_xrefs

- `0x18002700b`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\bthavctpsvc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
RTL_SRWLOCK *__fastcall AVCTPService::StopAsync(RTL_SRWLOCK *a1, RTL_SRWLOCK *a2)
{
  char *v4; // rdi
  std::_Ref_count_base *Ptr; // rcx
  _QWORD **v6; // rcx
  const char *v8; // [rsp+30h] [rbp-B8h]
  _BYTE v9[112]; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v10; // [rsp+B8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  RTL_SRWLOCK *v12; // [rsp+F8h] [rbp+10h] BYREF
  char *v13; // [rsp+100h] [rbp+18h]

  v12 = a2;
  v4 = (char *)operator new(0x138u);
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestServer<long>>::`vftable';
  v13 = v4 + 16;
  v10 = 0;
  *((_QWORD *)v4 + 2) = &Microsoft::Bluetooth::Foundation::AsyncRequest<long>::`vftable';
  LODWORD(v12) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    (_QWORD *)v4 + 4,
    (int *)&v12);
  *((_QWORD *)v4 + 5) = 0;
  *((_DWORD *)v4 + 12) = 0;
  wistd::function<void (void)>::function<void (void)>(v4 + 56, v9);
  *((_QWORD *)v4 + 22) = 0;
  *((_QWORD *)v4 + 37) = 0;
  *((_QWORD *)v4 + 2) = &Microsoft::Bluetooth::Foundation::AsyncRequestServer<long>::`vftable';
  *((_DWORD *)v4 + 76) = 0;
  wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>((__int64)v9);
  AcquireSRWLockExclusive(a1 + 30);
  v12 = a1 + 30;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x9C,
    (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\bthavctpsvc.cpp",
    (const char *)0x8007139FLL,
    a1[31].Ptr != 0,
    (bool)"StopAsync shall only be called once.",
    v8);
  _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
  a1[31].Ptr = v4 + 16;
  Ptr = (std::_Ref_count_base *)a1[32].Ptr;
  a1[32].Ptr = v4;
  if ( Ptr )
    std::_Ref_count_base::_Decref(Ptr);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl'::`2'::impl) )
  {
    v6 = (_QWORD **)a1[28].Ptr;
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6[3] + 32LL))(v6[3]);
  }
  (*((void (__fastcall **)(RTL_SRWLOCK *))a1[2].Ptr + 1))(a1 + 2);
  a2->Ptr = 0;
  a2[1].Ptr = 0;
  _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
  a2->Ptr = v4 + 16;
  a2[1].Ptr = v4;
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v4);
  return a2;
}

```

## disassembly

```asm
0x180026ef0  mov     [rsp+arg_8], rdx
0x180026ef5  push    rbx
0x180026ef6  push    rbp
0x180026ef7  push    rsi
0x180026ef8  push    rdi
0x180026ef9  push    r14
0x180026efb  sub     rsp, 0C0h
0x180026f02  mov     rsi, rdx
0x180026f05  mov     rbp, rcx
0x180026f08  mov     ecx, 138h; Size
0x180026f0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026f12  mov     rdi, rax
0x180026f15  mov     [rsp+0E8h+arg_0], rax
0x180026f1d  xorps   xmm0, xmm0
0x180026f20  movups  xmmword ptr [rax], xmm0
0x180026f23  mov     dword ptr [rax+8], 1
0x180026f2a  mov     dword ptr [rax+0Ch], 1
0x180026f31  lea     rax, ??_7?$_Ref_count_obj2@V?$AsyncRequestServer@J@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestServer<long>>::`vftable'
0x180026f38  mov     [rdi], rax
0x180026f3b  lea     r14, [rdi+10h]
0x180026f3f  mov     [rsp+0E8h+arg_10], r14
0x180026f47  mov     [rsp+0E8h+var_30], 0
0x180026f53  lea     rax, ??_7?$AsyncRequest@J@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::AsyncRequest<long>::`vftable'
0x180026f5a  mov     [r14], rax
0x180026f5d  mov     dword ptr [rsp+0E8h+arg_8], 1
0x180026f68  lea     rcx, [r14+10h]
0x180026f6c  lea     rdx, [rsp+0E8h+arg_8]
0x180026f74  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180026f79  nop
0x180026f7a  xor     eax, eax
0x180026f7c  mov     [r14+18h], rax
0x180026f80  mov     [r14+20h], eax
0x180026f84  lea     rcx, [r14+28h]
0x180026f88  lea     rdx, [rsp+0E8h+var_A0]
0x180026f8d  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x180026f92  xor     eax, eax
0x180026f94  mov     [r14+0A0h], rax
0x180026f9b  mov     [r14+118h], rax
0x180026fa2  lea     rax, ??_7?$AsyncRequestServer@J@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::AsyncRequestServer<long>::`vftable'
0x180026fa9  mov     [r14], rax
0x180026fac  xor     eax, eax
0x180026fae  mov     [r14+120h], eax
0x180026fb5  lea     rcx, [rsp+0E8h+var_A0]
0x180026fba  call    ??1?$function@$$A6AXU?$IoTargetIoctlResult@V?$RequestBufferView@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>(void)
0x180026fbf  nop
0x180026fc0  mov     [rsp+0E8h+var_B0], r14
0x180026fc5  mov     [rsp+0E8h+var_A8], rdi
0x180026fca  lea     rbx, [rbp+0F0h]
0x180026fd1  mov     rcx, rbx; SRWLock
0x180026fd4  call    cs:__imp_AcquireSRWLockExclusive
0x180026fda  mov     [rsp+0E8h+arg_8], rbx
0x180026fe2  cmp     qword ptr [rbp+0F8h], 0
0x180026fea  setnz   al
0x180026fed  mov     rcx, [rsp+0E8h]; this
0x180026ff5  lea     rdx, aStopasyncShall; "StopAsync shall only be called once."
0x180026ffc  mov     qword ptr [rsp+0E8h+var_C0], rdx; bool
0x180027001  mov     [rsp+0E8h+var_C8], al; char
0x180027005  mov     r9d, 8007139Fh; char *
0x18002700b  lea     r8, aOnecoreDrivers_24; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180027012  mov     edx, 9Ch; void *
0x180027017  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002701c  lock inc dword ptr [rdi+8]
0x180027020  mov     [rbp+0F8h], r14
0x180027027  mov     rcx, [rbp+100h]; this
0x18002702e  mov     [rbp+100h], rdi
0x180027035  test    rcx, rcx
0x180027038  jz      short loc_180027040
0x18002703a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002703f  nop
0x180027040  lea     rcx, [rsp+0E8h+arg_8]
0x180027048  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002704d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59215879@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879> `wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl(void)'::`2'::impl
0x180027054  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(void)
0x180027059  test    al, al
0x18002705b  jz      short loc_180027079
0x18002705d  mov     rcx, [rbp+0E0h]
0x180027064  test    rcx, rcx
0x180027067  jz      short loc_180027079
0x180027069  mov     rcx, [rcx+18h]
0x18002706d  mov     rax, [rcx]
0x180027070  mov     rax, [rax+20h]
0x180027074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027079  lea     rcx, [rbp+10h]
0x18002707d  mov     rax, [rcx]
0x180027080  mov     rax, [rax+8]
0x180027084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027089  mov     qword ptr [rsi], 0
0x180027090  mov     qword ptr [rsi+8], 0
0x180027098  lock inc dword ptr [rdi+8]
0x18002709c  mov     [rsi], r14
0x18002709f  mov     [rsi+8], rdi
0x1800270a3  mov     rcx, rdi; this
0x1800270a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800270ab  mov     rax, rsi
0x1800270ae  add     rsp, 0C0h
0x1800270b5  pop     r14
0x1800270b7  pop     rdi
0x1800270b8  pop     rsi
0x1800270b9  pop     rbp
0x1800270ba  pop     rbx
0x1800270bb  retn
```
