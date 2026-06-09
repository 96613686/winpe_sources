# ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BFI@AA@impl@winrt@@QEAA@XZ

- ea: `0x18000d1f8`
- end: `0x18000d260`
- name: `??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BFI@AA@impl@winrt@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d36c`
- `0x18000e950`

## callees

- `0x18000d1f8`
- `0x18000d7b8`
- `0x180011e0c`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(
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
       winrt::impl::abi<winrt::Windows::Devices::Enumeration::IDeviceWatcher,void>::type::`vcall'{88,{flat}}(v4, a1[1]);
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
0x18000d1f8  push    rbx
0x18000d1fa  sub     rsp, 20h
0x18000d1fe  mov     rbx, rcx
0x18000d201  mov     rcx, [rcx]
0x18000d204  test    rcx, rcx
0x18000d207  jz      short loc_18000D24C
0x18000d209  mov     [rsp+28h+arg_0], 0
0x18000d212  lea     r8, [rsp+28h+arg_0]
0x18000d217  mov     rax, [rcx]
0x18000d21a  lea     rdx, ??$guid_v@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Devices::Enumeration::IDeviceWatcher>
0x18000d221  mov     rax, [rax+18h]
0x18000d225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d22a  mov     rcx, [rsp+28h+arg_0]
0x18000d22f  mov     [rsp+28h+arg_0], rcx
0x18000d234  test    rcx, rcx
0x18000d237  jz      short loc_18000D24C
0x18000d239  mov     rdx, [rbx+8]
0x18000d23d  call    ??_9type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@winrt@@$BFI@AA; [thunk]: winrt::impl::abi<winrt::Windows::Devices::Enumeration::IDeviceWatcher,void>::type::`vcall'{88,{flat}}
0x18000d242  lea     rcx, [rsp+28h+arg_0]
0x18000d247  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d24c  cmp     qword ptr [rbx], 0
0x18000d250  jz      short loc_18000D25A
0x18000d252  mov     rcx, rbx
0x18000d255  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d25a  add     rsp, 20h
0x18000d25e  pop     rbx
0x18000d25f  retn
```
