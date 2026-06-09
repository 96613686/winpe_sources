# ?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z

- ea: `0x18000d3b0`
- end: `0x18000d3cf`
- name: `?Invoke@?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHPEAXH@Z`
- size: `31`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800034a1`
- `0x18000d3b0`

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
0x18000d3b0  sub     rsp, 28h
0x18000d3b4  mov     [rcx+18h], r8d
0x18000d3b8  mov     rcx, [rcx+10h]; hEvent
0x18000d3bc  call    WINRT_IMPL_SetEvent
0x18000d3c1  xor     eax, eax
0x18000d3c3  jmp     short loc_18000D3C9
0x18000d3c5  mov     eax, [rsp+28h+arg_10]
0x18000d3c9  add     rsp, 28h
0x18000d3cd  retn
```
