# ??$?0U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@3@$0A@@?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@$$QEAU?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@5@@Z

- ea: `0x18000763c`
- end: `0x180007661`
- name: `??$?0U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@3@$0A@@?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@$$QEAU?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@5@@Z`
- size: `37`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800092f8`
- `0x180009390`

## pseudocode

```c
_QWORD *__fastcall ____0U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__AEAPEAU__delegate_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__impl_3__0A____pair_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__std__QEAA___QEAU__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__AEAPEAU__delegate_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__impl_5__Z(
        _QWORD *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v3; // rax

  v3 = *a2;
  *a2 = 0;
  *a1 = v3;
  a1[1] = (*a3 + 16LL) & -(__int64)(*a3 != 0);
  return a1;
}

```

## disassembly

```asm
0x18000763c  mov     rax, [rdx]
0x18000763f  mov     qword ptr [rdx], 0
0x180007646  mov     [rcx], rax
0x180007649  mov     rax, [r8]
0x18000764c  lea     rdx, [rax+10h]
0x180007650  neg     rax
0x180007653  sbb     rax, rax
0x180007656  and     rax, rdx
0x180007659  mov     [rcx+8], rax
0x18000765d  mov     rax, rcx
0x180007660  retn
```
