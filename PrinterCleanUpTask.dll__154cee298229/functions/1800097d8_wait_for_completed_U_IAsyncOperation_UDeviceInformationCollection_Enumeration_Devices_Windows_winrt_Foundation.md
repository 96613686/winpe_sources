# ??$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z

- ea: `0x1800097d8`
- end: `0x180009899`
- name: `??$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f554`

## callees

- `0x180002bf0`
- `0x180002c14`
- `0x1800034ad`
- `0x180008aa0`
- `0x180009390`
- `0x1800097d8`
- `0x18000a360`
- `0x18000f38c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>>(
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
  ___make_delegate_with_shared_state_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__YA_AU__pair_U__AsyncOperationCompletedHandler_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___234_I_Z__std____QEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___01_YA_A_PAEBU__IAsyncOperation_UDeviceInformationCollection_Enumeration_Devices_Windows_winrt___Foundation_Windows_1_I_Z__Z(
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
0x1800097d8  mov     [rsp-8+arg_0], rbx
0x1800097dd  mov     [rsp-8+arg_8], edx
0x1800097e1  push    rbp
0x1800097e2  mov     rbp, rsp
0x1800097e5  sub     rsp, 50h
0x1800097e9  mov     rbx, rcx
0x1800097ec  mov     dword ptr [rbp+var_18], 0
0x1800097f3  xorps   xmm0, xmm0
0x1800097f6  movdqu  [rbp+var_10], xmm0
0x1800097fb  xor     r9d, r9d; lpName
0x1800097fe  xor     r8d, r8d; bInitialState
0x180009801  lea     edx, [r9+1]; bManualReset
0x180009805  xor     ecx, ecx; lpEventAttributes
0x180009807  call    WINRT_IMPL_CreateEventW
0x18000980c  lea     rdx, [rbp+var_18]
0x180009810  mov     rcx, rax
0x180009813  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x180009818  mov     [rbp+hObject], rax
0x18000981c  mov     qword ptr [rbp+var_28], 0
0x180009824  lea     rdx, [rbp+hObject]
0x180009828  lea     rcx, [rbp+var_18]
0x18000982c  call    ??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z
0x180009831  nop
0x180009832  mov     rcx, [rbp+hObject]; hObject
0x180009836  test    rcx, rcx
0x180009839  jz      short loc_180009840
0x18000983b  call    WINRT_IMPL_CloseHandle
0x180009840  mov     rcx, [rbx]
0x180009843  mov     dword ptr [rbp+hObject], 0
0x18000984a  xorps   xmm0, xmm0
0x18000984d  movdqu  [rbp+var_28], xmm0
0x180009852  mov     rax, [rcx]
0x180009855  mov     rdx, [rbp+var_18]
0x180009859  mov     rax, [rax+30h]
0x18000985d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009862  lea     r8, [rbp+hObject]
0x180009866  mov     edx, eax
0x180009868  lea     rcx, [rbp+arg_8]
0x18000986c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180009871  mov     rbx, qword ptr [rbp+var_10]
0x180009875  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009878  mov     rcx, [rbx]; hHandle
0x18000987b  call    WaitForSingleObject_0
0x180009880  mov     ebx, [rbx+8]
0x180009883  lea     rcx, [rbp+var_18]; this
0x180009887  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000988c  mov     eax, ebx
0x18000988e  mov     rbx, [rsp+50h+arg_0]
0x180009893  add     rsp, 50h
0x180009897  pop     rbp
0x180009898  retn
```
