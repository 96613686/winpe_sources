# ?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ

- ea: `0x18000e210`
- end: `0x18000e251`
- name: `?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ`
- size: `65`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002434`
- `0x18000a600`
- `0x18000e210`
- `0x18000f4a8`

## pseudocode

```c
__int64 __fastcall _Release___implements_delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__UEAAIXZ(
        char *a1)
{
  unsigned int v2; // edi

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(a1 + 8));
  if ( !v2 && a1 )
  {
    __1__implements_delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__QEAA_XZ((__int64)a1);
    operator delete(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e210  mov     [rsp+arg_0], rbx
0x18000e215  push    rdi
0x18000e216  sub     rsp, 20h
0x18000e21a  mov     rbx, rcx
0x18000e21d  add     rcx, 8; this
0x18000e221  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x18000e226  mov     edi, eax
0x18000e228  test    eax, eax
0x18000e22a  jnz     short loc_18000E244
0x18000e22c  test    rbx, rbx
0x18000e22f  jz      short loc_18000E244
0x18000e231  mov     rcx, rbx
0x18000e234  call    ??1?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@QEAA@XZ
0x18000e239  lea     edx, [rdi+20h]; unsigned __int64
0x18000e23c  mov     rcx, rbx; void *
0x18000e23f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e244  mov     rbx, [rsp+28h+arg_0]
0x18000e249  mov     eax, edi
0x18000e24b  add     rsp, 20h
0x18000e24f  pop     rdi
0x18000e250  retn
```
