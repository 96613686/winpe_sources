# ??$wait_for_completed@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z

- ea: `0x18001f844`
- end: `0x18001f905`
- name: `??$wait_for_completed@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023898`

## callees

- `0x180004631`
- `0x180004649`
- `0x1800050f2`
- `0x18000dfc0`
- `0x18001e418`
- `0x18001ee78`
- `0x18001f844`
- `0x180024334`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::AppService::AppServiceResponse>>(
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
  ___make_delegate_with_shared_state_U__AsyncOperationCompletedHandler_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___234_I_Z__impl_winrt__YA_AU__pair_U__AsyncOperationCompletedHandler_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___234_I_Z__std____QEAUshared_type__1____wait_for_completed_U__IAsyncOperation_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt___01_YA_A_PAEBU__IAsyncOperation_UAppServiceResponse_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_1_I_Z__Z(
    &v10,
    &hObject);
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
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f844  mov     [rsp-8+arg_0], rbx
0x18001f849  mov     [rsp-8+arg_8], edx
0x18001f84d  push    rbp
0x18001f84e  mov     rbp, rsp
0x18001f851  sub     rsp, 50h
0x18001f855  mov     rbx, rcx
0x18001f858  mov     dword ptr [rbp+var_18], 0
0x18001f85f  xorps   xmm0, xmm0
0x18001f862  movdqu  [rbp+var_10], xmm0
0x18001f867  xor     r9d, r9d; lpName
0x18001f86a  xor     r8d, r8d; bInitialState
0x18001f86d  lea     edx, [r9+1]; bManualReset
0x18001f871  xor     ecx, ecx; lpEventAttributes
0x18001f873  call    WINRT_IMPL_CreateEventW
0x18001f878  lea     rdx, [rbp+var_18]
0x18001f87c  mov     rcx, rax
0x18001f87f  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x18001f884  mov     [rbp+hObject], rax
0x18001f888  mov     qword ptr [rbp+var_28], 0
0x18001f890  lea     rdx, [rbp+hObject]
0x18001f894  lea     rcx, [rbp+var_18]
0x18001f898  call    ??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@UAppServiceResponse@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z
0x18001f89d  nop
0x18001f89e  mov     rcx, [rbp+hObject]; hObject
0x18001f8a2  test    rcx, rcx
0x18001f8a5  jz      short loc_18001F8AC
0x18001f8a7  call    WINRT_IMPL_CloseHandle
0x18001f8ac  mov     rcx, [rbx]
0x18001f8af  mov     dword ptr [rbp+hObject], 0
0x18001f8b6  xorps   xmm0, xmm0
0x18001f8b9  movdqu  [rbp+var_28], xmm0
0x18001f8be  mov     rax, [rcx]
0x18001f8c1  mov     rdx, [rbp+var_18]
0x18001f8c5  mov     rax, [rax+30h]
0x18001f8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8ce  lea     r8, [rbp+hObject]
0x18001f8d2  mov     edx, eax
0x18001f8d4  lea     rcx, [rbp+arg_8]
0x18001f8d8  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f8dd  mov     rbx, qword ptr [rbp+var_10]
0x18001f8e1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f8e4  mov     rcx, [rbx]; hHandle
0x18001f8e7  call    WaitForSingleObject_0
0x18001f8ec  mov     ebx, [rbx+8]
0x18001f8ef  lea     rcx, [rbp+var_18]
0x18001f8f3  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001f8f8  mov     eax, ebx
0x18001f8fa  mov     rbx, [rsp+50h+arg_0]
0x18001f8ff  add     rsp, 50h
0x18001f903  pop     rbp
0x18001f904  retn
```
