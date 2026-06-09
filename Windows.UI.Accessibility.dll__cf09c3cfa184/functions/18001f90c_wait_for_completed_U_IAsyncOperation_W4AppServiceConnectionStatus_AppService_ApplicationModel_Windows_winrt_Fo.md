# ??$wait_for_completed@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z

- ea: `0x18001f90c`
- end: `0x18001f9cd`
- name: `??$wait_for_completed@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z`
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
- `0x18001ef10`
- `0x18001f90c`
- `0x180024334`
- `0x180035010`

## pseudocode

```c
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(
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
  ___make_delegate_with_shared_state_U__AsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___234_I_Z__impl_winrt__YA_AU__pair_U__AsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___234_I_Z__std____QEAUshared_type__1____wait_for_completed_U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_winrt___01_YA_A_PAEBU__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows_winrt___Foundation_Windows_1_I_Z__Z(
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
0x18001f90c  mov     [rsp-8+arg_0], rbx
0x18001f911  mov     [rsp-8+arg_8], edx
0x18001f915  push    rbp
0x18001f916  mov     rbp, rsp
0x18001f919  sub     rsp, 50h
0x18001f91d  mov     rbx, rcx
0x18001f920  mov     dword ptr [rbp+var_18], 0
0x18001f927  xorps   xmm0, xmm0
0x18001f92a  movdqu  [rbp+var_10], xmm0
0x18001f92f  xor     r9d, r9d; lpName
0x18001f932  xor     r8d, r8d; bInitialState
0x18001f935  lea     edx, [r9+1]; bManualReset
0x18001f939  xor     ecx, ecx; lpEventAttributes
0x18001f93b  call    WINRT_IMPL_CreateEventW
0x18001f940  lea     rdx, [rbp+var_18]
0x18001f944  mov     rcx, rax
0x18001f947  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x18001f94c  mov     [rbp+hObject], rax
0x18001f950  mov     qword ptr [rbp+var_28], 0
0x18001f958  lea     rdx, [rbp+hObject]
0x18001f95c  lea     rcx, [rbp+var_18]
0x18001f960  call    ??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@winrt@@@Foundation@Windows@1@I@Z@@Z
0x18001f965  nop
0x18001f966  mov     rcx, [rbp+hObject]; hObject
0x18001f96a  test    rcx, rcx
0x18001f96d  jz      short loc_18001F974
0x18001f96f  call    WINRT_IMPL_CloseHandle
0x18001f974  mov     rcx, [rbx]
0x18001f977  mov     dword ptr [rbp+hObject], 0
0x18001f97e  xorps   xmm0, xmm0
0x18001f981  movdqu  [rbp+var_28], xmm0
0x18001f986  mov     rax, [rcx]
0x18001f989  mov     rdx, [rbp+var_18]
0x18001f98d  mov     rax, [rax+30h]
0x18001f991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f996  lea     r8, [rbp+hObject]
0x18001f99a  mov     edx, eax
0x18001f99c  lea     rcx, [rbp+arg_8]
0x18001f9a0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f9a5  mov     rbx, qword ptr [rbp+var_10]
0x18001f9a9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f9ac  mov     rcx, [rbx]; hHandle
0x18001f9af  call    WaitForSingleObject_0
0x18001f9b4  mov     ebx, [rbx+8]
0x18001f9b7  lea     rcx, [rbp+var_18]
0x18001f9bb  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001f9c0  mov     eax, ebx
0x18001f9c2  mov     rbx, [rsp+50h+arg_0]
0x18001f9c7  add     rsp, 50h
0x18001f9cb  pop     rbp
0x18001f9cc  retn
```
