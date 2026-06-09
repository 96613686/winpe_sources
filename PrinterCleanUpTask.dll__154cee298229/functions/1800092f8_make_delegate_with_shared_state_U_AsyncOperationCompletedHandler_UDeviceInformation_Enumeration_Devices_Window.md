# ??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z

- ea: `0x1800092f8`
- end: `0x18000938a`
- name: `??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z`
- size: `146`
- prototype: `char *__fastcall(char *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009710`

## callees

- `0x180002044`
- `0x18000750c`
- `0x18000763c`
- `0x1800092f8`
- `0x18000a32c`

## pseudocode

```c
char *__fastcall ___make_delegate_with_shared_state_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__YA_AU__pair_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__std____QEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___01_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_1_I_Z__Z(
        char *a1,
        __int64 *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  char *v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = a1;
  v7 = (char *)operator new(0x20u);
  winrt::impl::implements_delegate_base::implements_delegate_base((winrt::impl::implements_delegate_base *)(v7 + 8));
  v4 = *a2;
  *a2 = 0;
  *(_QWORD *)(v5 + 16) = v4;
  *(_DWORD *)(v5 + 24) = *((_DWORD *)a2 + 2);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v7 = (char *)v5;
  *(_QWORD *)v5 = ___7__delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__6B_;
  v8 = v5;
  ____0U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__AEAPEAU__delegate_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__impl_3__0A____pair_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__std__QEAA___QEAU__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__AEAPEAU__delegate_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__impl_5__Z(
    a1,
    (__int64 *)&v7,
    &v8);
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v7);
  return a1;
}

```

## disassembly

```asm
0x1800092f8  mov     [rsp+arg_8], rbx
0x1800092fd  mov     [rsp+arg_0], rcx
0x180009302  push    rdi
0x180009303  sub     rsp, 30h
0x180009307  mov     rdi, rcx
0x18000930a  mov     rbx, rdx
0x18000930d  mov     ecx, 20h ; ' '; Size
0x180009312  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009317  mov     r9, rax
0x18000931a  mov     [rsp+38h+arg_0], rax
0x18000931f  lea     rcx, [rax+8]; this
0x180009323  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x180009328  mov     r8, [rbx]
0x18000932b  mov     qword ptr [rbx], 0
0x180009332  mov     [r9+10h], r8
0x180009336  mov     ecx, [rbx+8]
0x180009339  mov     [r9+18h], ecx
0x18000933d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009344  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@6B@
0x18000934b  mov     [rsp+38h+arg_0], r9
0x180009350  lea     r8, [rsp+38h+arg_10]
0x180009355  mov     [r9], rax
0x180009358  lea     rdx, [rsp+38h+arg_0]
0x18000935d  mov     [rsp+38h+arg_10], r9
0x180009362  mov     rcx, rdi
0x180009365  call    ??$?0U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@3@$0A@@?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@$$QEAU?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@5@@Z
0x18000936a  cmp     [rsp+38h+arg_0], 0
0x180009370  jz      short loc_18000937C
0x180009372  lea     rcx, [rsp+38h+arg_0]
0x180009377  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000937c  mov     rbx, [rsp+38h+arg_8]
0x180009381  mov     rax, rdi
0x180009384  add     rsp, 30h
0x180009388  pop     rdi
0x180009389  retn
```
