# ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ

- ea: `0x18000d118`
- end: `0x18000d180`
- name: `??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d36c`
- `0x18000e950`

## callees

- `0x18000d118`
- `0x18000d790`
- `0x180011e0c`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( v2 )
  {
    v4 = 0;
    result = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v2 + 24LL))(
               v2,
               winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceWatcher>,
               &v4);
    if ( v4 )
    {
       winrt::impl::abi<winrt::Windows::Devices::Enumeration::IDeviceWatcher,void>::type::`vcall'{56,{flat}}(v4, a1[1]);
      result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v4);
    }
  }
  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000d118  push    rbx
0x18000d11a  sub     rsp, 20h
0x18000d11e  mov     rbx, rcx
0x18000d121  mov     rcx, [rcx]
0x18000d124  test    rcx, rcx
0x18000d127  jz      short loc_18000D16C
0x18000d129  mov     [rsp+28h+arg_0], 0
0x18000d132  lea     r8, [rsp+28h+arg_0]
0x18000d137  mov     rax, [rcx]
0x18000d13a  lea     rdx, ??$guid_v@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceWatcher>
0x18000d141  mov     rax, [rax+18h]
0x18000d145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d14a  mov     rcx, [rsp+28h+arg_0]
0x18000d14f  mov     [rsp+28h+arg_0], rcx
0x18000d154  test    rcx, rcx
0x18000d157  jz      short loc_18000D16C
0x18000d159  mov     rdx, [rbx+8]
0x18000d15d  call    ??_9type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@winrt@@$BDI@AA; [thunk]: winrt::impl::abi<winrt::Windows::Devices::Enumeration::IDeviceWatcher,void>::type::`vcall'{56,{flat}}
0x18000d162  lea     rcx, [rsp+28h+arg_0]
0x18000d167  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d16c  cmp     qword ptr [rbx], 0
0x18000d170  jz      short loc_18000D17A
0x18000d172  mov     rcx, rbx
0x18000d175  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d17a  add     rsp, 20h
0x18000d17e  pop     rbx
0x18000d17f  retn
```
