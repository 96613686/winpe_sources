# ??1?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@XZ

- ea: `0x18000fa8c`
- end: `0x18000faa0`
- name: `??1?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `34`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800304e8`
- `0x18003050c`
- `0x18003055c`
- `0x1800306cc`
- `0x180030714`
- `0x180030726`
- `0x1800307d2`
- `0x180030996`
- `0x1800309a8`
- `0x180030d93`
- `0x180030db7`
- `0x180030e11`
- `0x180030e23`
- `0x180030ea9`
- `0x180030f2f`
- `0x180030f70`
- `0x180030f94`
- `0x180030fa6`
- `0x18003105a`
- `0x1800310d8`
- `0x18003112e`
- `0x180031152`
- `0x180031164`
- `0x180031176`
- `0x180031188`
- `0x1800312b4`
- `0x1800312c6`
- `0x1800312d8`
- `0x1800312fc`
- `0x18003130e`
- `0x180031343`
- `0x18003138b`
- `0x1800313af`
- `0x1800313c1`

## callees

- `0x18000fa8c`
- `0x180014974`

## pseudocode

```c
__int64 __fastcall __1__pair_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__std__QEAA_XZ(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000fa8c  sub     rsp, 28h
0x18000fa90  cmp     qword ptr [rcx], 0
0x18000fa94  jz      short loc_18000FA9B
0x18000fa96  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fa9b  add     rsp, 28h
0x18000fa9f  retn
```
