# ??1?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@QEAA@XZ

- ea: `0x18000a600`
- end: `0x18000a631`
- name: `??1?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@QEAA@XZ`
- size: `49`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e210`

## callees

- `0x180002c14`
- `0x180006aec`
- `0x18000a600`

## pseudocode

```c
int __fastcall __1__implements_delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__QEAA_XZ(
        __int64 a1)
{
  int result; // eax
  void *v3; // rcx

  result = winrt::impl::atomic_ref_count::operator--(&`winrt::get_module_lock'::`2'::s_lock);
  v3 = *(void **)(a1 + 16);
  if ( v3 )
  {
    result = WINRT_IMPL_CloseHandle(v3);
    *(_QWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a600  push    rbx
0x18000a602  sub     rsp, 20h
0x18000a606  mov     rbx, rcx
0x18000a609  lea     rcx, ?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000a610  call    ??Fatomic_ref_count@impl@winrt@@QEAAIXZ; winrt::impl::atomic_ref_count::operator--(void)
0x18000a615  mov     rcx, [rbx+10h]; hObject
0x18000a619  test    rcx, rcx
0x18000a61c  jz      short loc_18000A62B
0x18000a61e  call    WINRT_IMPL_CloseHandle
0x18000a623  mov     qword ptr [rbx+10h], 0
0x18000a62b  add     rsp, 20h
0x18000a62f  pop     rbx
0x18000a630  retn
```
