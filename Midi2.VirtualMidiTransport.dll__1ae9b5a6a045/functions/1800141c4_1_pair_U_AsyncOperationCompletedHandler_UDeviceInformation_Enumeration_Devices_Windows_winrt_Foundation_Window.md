# ??1?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@XZ

- ea: `0x1800141c4`
- end: `0x1800141d8`
- name: `??1?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020083`
- `0x1800200a7`
- `0x1800200f7`
- `0x180020331`
- `0x180020379`
- `0x18002038b`
- `0x180020425`
- `0x1800206e8`
- `0x1800206fa`
- `0x180020b3e`
- `0x180020b62`
- `0x180020b86`
- `0x180020baa`
- `0x180020be0`

## callees

- `0x1800141c4`
- `0x18001a798`

## pseudocode

```c
__int64 __fastcall __1__pair_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__std__QEAA_XZ(
        __int64 *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x1800141c4  sub     rsp, 28h
0x1800141c8  cmp     qword ptr [rcx], 0
0x1800141cc  jz      short loc_1800141D3
0x1800141ce  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800141d3  add     rsp, 28h
0x1800141d7  retn
```
