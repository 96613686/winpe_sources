# ?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z

- ea: `0x18000f740`
- end: `0x18000f75f`
- name: `?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003b85`
- `0x18000f740`

## pseudocode

```c
__int64 __fastcall _Invoke___delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__UEAAHPEAXH_Z(
        __int64 a1,
        __int64 a2,
        int a3)
{
  *(_DWORD *)(a1 + 24) = a3;
  WINRT_IMPL_SetEvent(*(HANDLE *)(a1 + 16));
  return 0;
}

```

## disassembly

```asm
0x18000f740  sub     rsp, 28h
0x18000f744  mov     [rcx+18h], r8d
0x18000f748  mov     rcx, [rcx+10h]; hEvent
0x18000f74c  call    WINRT_IMPL_SetEvent
0x18000f751  xor     eax, eax
0x18000f753  jmp     short loc_18000F759
0x18000f755  mov     eax, [rsp+28h+arg_10]
0x18000f759  add     rsp, 28h
0x18000f75d  retn
```
