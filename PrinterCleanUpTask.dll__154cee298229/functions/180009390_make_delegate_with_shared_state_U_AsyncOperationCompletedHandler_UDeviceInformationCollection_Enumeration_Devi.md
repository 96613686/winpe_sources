# ??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z

- ea: `0x180009390`
- end: `0x180009422`
- name: `??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z`
- size: `146`
- prototype: `char *__fastcall(char *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800097d8`

## callees

- `0x180002044`
- `0x18000750c`
- `0x18000763c`
- `0x180009390`
- `0x18000a32c`

## pseudocode

```c
char *__fastcall ___make_delegate_with_shared_state_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__YA_AU__pair_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__std____QEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___01_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_1_I_Z__Z(
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
  *(_QWORD *)v5 = ___7__delegate_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__6B_;
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
0x180009390  mov     [rsp+arg_8], rbx
0x180009395  mov     [rsp+arg_0], rcx
0x18000939a  push    rdi
0x18000939b  sub     rsp, 30h
0x18000939f  mov     rdi, rcx
0x1800093a2  mov     rbx, rdx
0x1800093a5  mov     ecx, 20h ; ' '; Size
0x1800093aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800093af  mov     r9, rax
0x1800093b2  mov     [rsp+38h+arg_0], rax
0x1800093b7  lea     rcx, [rax+8]; this
0x1800093bb  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x1800093c0  mov     r8, [rbx]
0x1800093c3  mov     qword ptr [rbx], 0
0x1800093ca  mov     [r9+10h], r8
0x1800093ce  mov     ecx, [rbx+8]
0x1800093d1  mov     [r9+18h], ecx
0x1800093d5  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800093dc  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@6B@
0x1800093e3  mov     [rsp+38h+arg_0], r9
0x1800093e8  lea     r8, [rsp+38h+arg_10]
0x1800093ed  mov     [r9], rax
0x1800093f0  lea     rdx, [rsp+38h+arg_0]
0x1800093f5  mov     [rsp+38h+arg_10], r9
0x1800093fa  mov     rcx, rdi
0x1800093fd  call    ??$?0U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@3@$0A@@?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@QEAA@$$QEAU?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@AEAPEAU?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@5@@Z
0x180009402  cmp     [rsp+38h+arg_0], 0
0x180009408  jz      short loc_180009414
0x18000940a  lea     rcx, [rsp+38h+arg_0]
0x18000940f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009414  mov     rbx, [rsp+38h+arg_8]
0x180009419  mov     rax, rdi
0x18000941c  add     rsp, 30h
0x180009420  pop     rdi
0x180009421  retn
```
