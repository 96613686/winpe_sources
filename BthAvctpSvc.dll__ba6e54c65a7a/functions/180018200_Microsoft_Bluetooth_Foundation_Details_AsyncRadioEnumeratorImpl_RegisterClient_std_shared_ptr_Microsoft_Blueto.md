# Microsoft::Bluetooth::Foundation::Details::AsyncRadioEnumeratorImpl::RegisterClient(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRadioEnumeratorClient> const &)

- ea: `0x180018200`
- end: `0x1800183d9`
- name: `?RegisterClient@AsyncRadioEnumeratorImpl@Details@Foundation@Bluetooth@Microsoft@@UEAA?AV?$unique_ptr@VAsyncRadioEnumeratorClientRegistration@AsyncRadioEnumerator@Foundation@Bluetooth@Microsoft@@U?$default_delete@VAsyncRadioEnumeratorClientRegistration@AsyncRadioEnumerator@Foundation@Bluetooth@Microsoft@@@std@@@std@@AEBV?$shared_ptr@VAsyncRadioEnumeratorClient@Foundation@Bluetooth@Microsoft@@@7@@Z`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001dd0`
- `0x1800021dc`
- `0x180004060`
- `0x180004080`
- `0x18000ab4c`
- `0x18000ad20`
- `0x18000de78`
- `0x18000deb0`
- `0x18000f3a0`
- `0x180010b78`
- `0x180012168`
- `0x1800146c4`
- `0x180014b90`
- `0x180018200`
- `0x180019d20`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018331`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018331`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct _GUID *__fastcall Microsoft::Bluetooth::Foundation::Details::AsyncRadioEnumeratorImpl::RegisterClient(
        __int64 a1,
        struct _GUID *a2,
        _QWORD *a3)
{
  GUID *v6; // rbx
  _QWORD *v7; // r15
  std::_Ref_count_base *v8; // r8
  struct _GUID *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rdx
  std::_Ref_count_base *v13; // rdx
  _QWORD *i; // rbx
  _QWORD *v15; // rdi
  _QWORD *v16; // rbx
  _QWORD *v18; // [rsp+20h] [rbp-60h] BYREF
  _QWORD *v19; // [rsp+28h] [rbp-58h] BYREF
  int v20; // [rsp+30h] [rbp-50h]
  GUID v21; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v22[8]; // [rsp+48h] [rbp-38h] BYREF
  std::_Ref_count_base *v23; // [rsp+50h] [rbp-30h]
  struct _GUID *v24; // [rsp+58h] [rbp-28h]
  struct _GUID v25; // [rsp+60h] [rbp-20h] BYREF

  v24 = a2;
  v20 = 0;
  v25 = *Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(&v21, a2);
  v6 = (GUID *)std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(
                 a1 + 16,
                 v22);
  v7 = operator new(0x20u);
  v18 = v7;
  v21 = *v6;
  *(_QWORD *)&v6->Data1 = 0;
  *(_QWORD *)v6->Data4 = 0;
  std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(
    v7,
    &v21);
  v9[1] = v25;
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  *(_QWORD *)&a2->Data1 = v7;
  v20 = 3;
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
  v18 = (_QWORD *)(a1 + 32);
  v10 = *(_QWORD *)std::map<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRadioEnumeratorClient>>::_Try_emplace<_GUID const &,>(
                     a1 + 40,
                     v22,
                     &v25);
  v11 = a3[1];
  if ( v11 )
  {
    v12 = (void (__fastcall ***)(_QWORD, __int64))*a3;
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
  }
  else
  {
    v12 = 0;
    v11 = 0;
  }
  *(_QWORD *)(v10 + 48) = v12;
  v13 = *(std::_Ref_count_base **)(v10 + 56);
  *(_QWORD *)(v10 + 56) = v11;
  if ( v13 )
    std::_Ref_count_base::_Decwref(v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
  std::forward_list<std::pair<std::wstring,Microsoft::Bluetooth::BluetoothLocalAddress>>::forward_list<std::pair<std::wstring,Microsoft::Bluetooth::BluetoothLocalAddress>>(&v19);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 56));
  v18 = (_QWORD *)(a1 + 56);
  std::copy<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::Bluetooth::BluetoothLocalAddress>>>>,std::front_insert_iterator<std::forward_list<std::pair<std::wstring,Microsoft::Bluetooth::BluetoothLocalAddress>>>>(
    &v21,
    **(_QWORD **)(a1 + 64),
    *(_QWORD *)(a1 + 64),
    &v19);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
  for ( i = v19; i; i = (_QWORD *)*i )
    (**(void (__fastcall ***)(_QWORD, __int64))*a3)(*a3, (__int64)(i + 5));
  v15 = v19;
  v19 = 0;
  if ( v15 )
  {
    do
    {
      v16 = (_QWORD *)*v15;
      std::wstring::_Tidy_deallocate(v15 + 1);
      std::_Deallocate<16>(v15, (struct std::nothrow_t *)0x38);
      v15 = v16;
    }
    while ( v16 );
  }
  return a2;
}

```

## disassembly

```asm
0x180018200  mov     [rsp-28h+arg_18], rbx
0x180018205  push    rbp
0x180018206  push    rsi
0x180018207  push    rdi
0x180018208  push    r14
0x18001820a  push    r15
0x18001820c  mov     rbp, rsp
0x18001820f  sub     rsp, 80h
0x180018216  mov     rax, cs:__security_cookie
0x18001821d  xor     rax, rsp
0x180018220  mov     [rbp+var_10], rax
0x180018224  mov     rsi, r8
0x180018227  mov     r14, rdx
0x18001822a  mov     rdi, rcx
0x18001822d  mov     [rbp+var_28], rdx
0x180018231  mov     [rbp+var_50], 0
0x180018238  lea     rcx, [rbp+var_48]; this
0x18001823c  call    ?GetNextId@GuidFactory@Foundation@Bluetooth@Microsoft@@YA?AU_GUID@@XZ; Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(void)
0x180018241  movups  xmm0, xmmword ptr [rax]
0x180018244  movdqu  [rbp+var_20], xmm0
0x180018249  lea     rcx, [rdi+10h]
0x18001824d  lea     rdx, [rbp+var_38]
0x180018251  call    ?shared_from_this@?$enable_shared_from_this@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(void)
0x180018256  mov     rbx, rax
0x180018259  mov     ecx, 20h ; ' '; Size
0x18001825e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018263  mov     r15, rax
0x180018266  mov     [rbp+var_60], rax
0x18001826a  mov     rcx, [rbx]
0x18001826d  mov     [rbp+var_48], rcx
0x180018271  mov     r8, [rbx+8]
0x180018275  mov     [rbp+var_40], r8
0x180018279  mov     qword ptr [rbx], 0
0x180018280  mov     qword ptr [rbx+8], 0
0x180018288  lea     rdx, [rbp+var_48]
0x18001828c  mov     rcx, rax
0x18001828f  call    ??0?$shared_ptr@VThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl> const &)
0x180018294  movups  xmm0, [rbp+var_20]
0x180018298  movdqu  xmmword ptr [rcx+10h], xmm0
0x18001829d  test    r8, r8
0x1800182a0  jz      short loc_1800182AA
0x1800182a2  mov     rcx, r8; this
0x1800182a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800182aa  mov     [r14], r15
0x1800182ad  mov     [rbp+var_50], 3
0x1800182b4  mov     rcx, [rbp+var_30]; this
0x1800182b8  test    rcx, rcx
0x1800182bb  jz      short loc_1800182C2
0x1800182bd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800182c2  lea     rbx, [rdi+20h]
0x1800182c6  mov     rcx, rbx; SRWLock
0x1800182c9  call    cs:__imp_AcquireSRWLockExclusive
0x1800182cf  mov     [rbp+var_60], rbx
0x1800182d3  lea     rcx, [rdi+28h]
0x1800182d7  lea     r8, [rbp+var_20]
0x1800182db  lea     rdx, [rbp+var_38]
0x1800182df  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@V?$weak_ptr@VAsyncRadioEnumeratorClient@Foundation@Bluetooth@Microsoft@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$weak_ptr@VAsyncRadioEnumeratorClient@Foundation@Bluetooth@Microsoft@@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$weak_ptr@VAsyncRadioEnumeratorClient@Foundation@Bluetooth@Microsoft@@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRadioEnumeratorClient>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x1800182e4  mov     rcx, [rax]
0x1800182e7  mov     rax, [rsi+8]
0x1800182eb  test    rax, rax
0x1800182ee  jz      short loc_1800182F9
0x1800182f0  mov     rdx, [rsi]
0x1800182f3  lock inc dword ptr [rax+0Ch]
0x1800182f7  jmp     short loc_1800182FD
0x1800182f9  xor     edx, edx
0x1800182fb  xor     eax, eax
0x1800182fd  mov     [rcx+30h], rdx
0x180018301  mov     rdx, [rcx+38h]
0x180018305  mov     [rcx+38h], rax
0x180018309  test    rdx, rdx
0x18001830c  jz      short loc_180018317
0x18001830e  mov     rcx, rdx; this
0x180018311  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180018316  nop
0x180018317  lea     rcx, [rbp+var_60]
0x18001831b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018320  lea     rcx, [rbp+var_58]; void *
0x180018324  call    ??0?$forward_list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::forward_list<std::pair<std::wstring,Microsoft::Bluetooth::BluetoothLocalAddress>>::forward_list<std::pair<std::wstring,Microsoft::Bluetooth::BluetoothLocalAddress>>(void)
0x180018329  nop
0x18001832a  lea     rbx, [rdi+38h]
0x18001832e  mov     rcx, rbx; SRWLock
0x180018331  call    cs:__imp_AcquireSRWLockShared
0x180018337  mov     [rbp+var_60], rbx
0x18001833b  mov     rdx, [rdi+40h]
0x18001833f  lea     r9, [rbp+var_58]
0x180018343  mov     r8, rdx
0x180018346  mov     rdx, [rdx]
0x180018349  lea     rcx, [rbp+var_48]
0x18001834d  call    ??$copy@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@@std@@@std@@@std@@V?$front_insert_iterator@V?$forward_list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@@2@@std@@@2@@std@@YA?AV?$front_insert_iterator@V?$forward_list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@@2@@std@@@0@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VBluetoothLocalAddress@Bluetooth@Microsoft@@@std@@@std@@@std@@@0@0V10@@Z; std::copy<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::Bluetooth::BluetoothLocalAddress>>>>,std::front_insert_iterator<std::forward_list<std::pair<std::wstring,Microsoft::Bluetooth::BluetoothLocalAddress>>>>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::Bluetooth::BluetoothLocalAddress>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::Bluetooth::BluetoothLocalAddress>>>>,std::front_insert_iterator<std::forward_list<std::pair<std::wstring,Microsoft::Bluetooth::BluetoothLocalAddress>>>)
0x180018352  nop
0x180018353  lea     rcx, [rbp+var_60]
0x180018357  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001835c  mov     rbx, [rbp+var_58]
0x180018360  test    rbx, rbx
0x180018363  jz      short loc_180018380
0x180018365  lea     r8, [rbx+8]
0x180018369  mov     rcx, [rsi]
0x18001836c  mov     rax, [rcx]
0x18001836f  lea     rdx, [r8+20h]
0x180018373  mov     rax, [rax]
0x180018376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001837b  mov     rbx, [rbx]
0x18001837e  jmp     short loc_180018360
0x180018380  mov     rdi, [rbp+var_58]
0x180018384  mov     [rbp+var_58], 0
0x18001838c  test    rdi, rdi
0x18001838f  jz      short loc_1800183B2
0x180018391  mov     rbx, [rdi]
0x180018394  lea     rcx, [rdi+8]
0x180018398  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001839d  mov     edx, 38h ; '8'
0x1800183a2  mov     rcx, rdi
0x1800183a5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800183aa  mov     rdi, rbx
0x1800183ad  test    rbx, rbx
0x1800183b0  jnz     short loc_180018391
0x1800183b2  mov     rax, r14
0x1800183b5  mov     rcx, [rbp+var_10]
0x1800183b9  xor     rcx, rsp; StackCookie
0x1800183bc  call    __security_check_cookie
0x1800183c1  mov     rbx, [rsp+80h+arg_18]
0x1800183c9  add     rsp, 80h
0x1800183d0  pop     r15
0x1800183d2  pop     r14
0x1800183d4  pop     rdi
0x1800183d5  pop     rsi
0x1800183d6  pop     rbp
0x1800183d7  retn
```
