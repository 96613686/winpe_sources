# ??$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z

- ea: `0x180009710`
- end: `0x1800097d1`
- name: `??$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c534`

## callees

- `0x180002bf0`
- `0x180002c14`
- `0x1800034ad`
- `0x180008aa0`
- `0x1800092f8`
- `0x180009710`
- `0x18000a360`
- `0x18000f38c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>>(
        __int64 *a1,
        int a2)
{
  HANDLE EventW; // rax
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rbx
  HANDLE hObject; // [rsp+20h] [rbp-30h] BYREF
  __int128 v9; // [rsp+28h] [rbp-28h]
  __int64 v10; // [rsp+38h] [rbp-18h] BYREF
  __int128 v11; // [rsp+40h] [rbp-10h]
  int v12; // [rsp+68h] [rbp+18h] BYREF

  v12 = a2;
  LODWORD(v10) = 0;
  v11 = 0;
  EventW = WINRT_IMPL_CreateEventW(0, 1, 0, 0);
  hObject = (HANDLE)winrt::check_pointer<void>(EventW, &v10);
  *(_QWORD *)&v9 = 0;
  ___make_delegate_with_shared_state_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__YA_AU__pair_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__std____QEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___01_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_1_I_Z__Z(
    (char *)&v10,
    (__int64 *)&hObject);
  if ( hObject )
    WINRT_IMPL_CloseHandle(hObject);
  v4 = *a1;
  LODWORD(hObject) = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 48LL))(v4, v10);
  winrt::check_hresult(&v12, v5, &hObject);
  v6 = v11;
  WaitForSingleObject_0(*(HANDLE *)v11, 0xFFFFFFFF);
  LODWORD(v6) = *(_DWORD *)(v6 + 8);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009710  mov     [rsp-8+arg_0], rbx
0x180009715  mov     [rsp-8+arg_8], edx
0x180009719  push    rbp
0x18000971a  mov     rbp, rsp
0x18000971d  sub     rsp, 50h
0x180009721  mov     rbx, rcx
0x180009724  mov     dword ptr [rbp+var_18], 0
0x18000972b  xorps   xmm0, xmm0
0x18000972e  movdqu  [rbp+var_10], xmm0
0x180009733  xor     r9d, r9d; lpName
0x180009736  xor     r8d, r8d; bInitialState
0x180009739  lea     edx, [r9+1]; bManualReset
0x18000973d  xor     ecx, ecx; lpEventAttributes
0x18000973f  call    WINRT_IMPL_CreateEventW
0x180009744  lea     rdx, [rbp+var_18]
0x180009748  mov     rcx, rax
0x18000974b  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x180009750  mov     [rbp+hObject], rax
0x180009754  mov     qword ptr [rbp+var_28], 0
0x18000975c  lea     rdx, [rbp+hObject]
0x180009760  lea     rcx, [rbp+var_18]
0x180009764  call    ??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z
0x180009769  nop
0x18000976a  mov     rcx, [rbp+hObject]; hObject
0x18000976e  test    rcx, rcx
0x180009771  jz      short loc_180009778
0x180009773  call    WINRT_IMPL_CloseHandle
0x180009778  mov     rcx, [rbx]
0x18000977b  mov     dword ptr [rbp+hObject], 0
0x180009782  xorps   xmm0, xmm0
0x180009785  movdqu  [rbp+var_28], xmm0
0x18000978a  mov     rax, [rcx]
0x18000978d  mov     rdx, [rbp+var_18]
0x180009791  mov     rax, [rax+30h]
0x180009795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000979a  lea     r8, [rbp+hObject]
0x18000979e  mov     edx, eax
0x1800097a0  lea     rcx, [rbp+arg_8]
0x1800097a4  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800097a9  mov     rbx, qword ptr [rbp+var_10]
0x1800097ad  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800097b0  mov     rcx, [rbx]; hHandle
0x1800097b3  call    WaitForSingleObject_0
0x1800097b8  mov     ebx, [rbx+8]
0x1800097bb  lea     rcx, [rbp+var_18]; this
0x1800097bf  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x1800097c4  mov     eax, ebx
0x1800097c6  mov     rbx, [rsp+50h+arg_0]
0x1800097cb  add     rsp, 50h
0x1800097cf  pop     rbp
0x1800097d0  retn
```
