# ??$wait_for_completed@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@I@Foundation@Windows@1@I@Z

- ea: `0x18001e7c8`
- end: `0x18001e890`
- name: `??$wait_for_completed@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@I@Foundation@Windows@1@I@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ed68`

## callees

- `0x1800048b9`
- `0x1800048dd`
- `0x180004925`
- `0x18001e438`
- `0x18001e7c8`
- `0x18001f90c`
- `0x180021880`
- `0x180022854`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<unsigned int>>(
        __int64 *a1,
        int a2)
{
  HANDLE EventW; // rax
  const struct winrt::impl::slim_source_location *v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rbx
  HANDLE hObject; // [rsp+20h] [rbp-30h] BYREF
  __int128 v10; // [rsp+28h] [rbp-28h]
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  __int128 v12; // [rsp+40h] [rbp-10h]
  int v13; // [rsp+68h] [rbp+18h] BYREF

  v13 = a2;
  LODWORD(v11) = 0;
  v12 = 0;
  EventW = WINRT_IMPL_CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    winrt::throw_last_error((winrt *)&v11, v4);
  hObject = EventW;
  *(_QWORD *)&v10 = 0;
  ___make_delegate_with_shared_state_U__AsyncOperationCompletedHandler_I_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_I_Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_I_234_I_Z__impl_winrt__YA_AU__pair_U__AsyncOperationCompletedHandler_I_Foundation_Windows_winrt__PEAUshared_type__1____wait_for_completed_U__IAsyncOperation_I_Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_I_234_I_Z__std____QEAUshared_type__1____wait_for_completed_U__IAsyncOperation_I_Foundation_Windows_winrt___01_YA_A_PAEBU__IAsyncOperation_I_Foundation_Windows_1_I_Z__Z(
    (char *)&v11,
    (__int64 *)&hObject);
  if ( hObject )
    WINRT_IMPL_CloseHandle(hObject);
  v5 = *a1;
  LODWORD(hObject) = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 48LL))(v5, v11);
  winrt::check_hresult(&v13, v6, &hObject);
  v7 = v12;
  WaitForSingleObject_0(*(HANDLE *)v12, 0xFFFFFFFF);
  LODWORD(v7) = *(_DWORD *)(v7 + 8);
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e7c8  mov     [rsp-8+arg_0], rbx
0x18001e7cd  mov     [rsp-8+arg_8], edx
0x18001e7d1  push    rbp
0x18001e7d2  mov     rbp, rsp
0x18001e7d5  sub     rsp, 50h
0x18001e7d9  mov     rbx, rcx
0x18001e7dc  mov     dword ptr [rbp+var_18], 0
0x18001e7e3  xorps   xmm0, xmm0
0x18001e7e6  movdqu  [rbp+var_10], xmm0
0x18001e7eb  xor     r9d, r9d; lpName
0x18001e7ee  xor     r8d, r8d; bInitialState
0x18001e7f1  lea     edx, [r9+1]; bManualReset
0x18001e7f5  xor     ecx, ecx; lpEventAttributes
0x18001e7f7  call    WINRT_IMPL_CreateEventW
0x18001e7fc  test    rax, rax
0x18001e7ff  jz      loc_18001E886
0x18001e805  mov     [rbp+hObject], rax
0x18001e809  mov     qword ptr [rbp+var_28], 0
0x18001e811  lea     rdx, [rbp+hObject]
0x18001e815  lea     rcx, [rbp+var_18]
0x18001e819  call    ??$make_delegate_with_shared_state@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@I@234@I@Z@@impl@winrt@@YA?AU?$pair@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@PEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@I@234@I@Z@@std@@$$QEAUshared_type@?1???$wait_for_completed@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@01@YA?A_PAEBU?$IAsyncOperation@I@Foundation@Windows@1@I@Z@@Z
0x18001e81e  nop
0x18001e81f  mov     rcx, [rbp+hObject]; hObject
0x18001e823  test    rcx, rcx
0x18001e826  jz      short loc_18001E82D
0x18001e828  call    WINRT_IMPL_CloseHandle
0x18001e82d  mov     rcx, [rbx]
0x18001e830  mov     dword ptr [rbp+hObject], 0
0x18001e837  xorps   xmm0, xmm0
0x18001e83a  movdqu  [rbp+var_28], xmm0
0x18001e83f  mov     rax, [rcx]
0x18001e842  mov     rdx, [rbp+var_18]
0x18001e846  mov     rax, [rax+30h]
0x18001e84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e84f  lea     r8, [rbp+hObject]
0x18001e853  mov     edx, eax
0x18001e855  lea     rcx, [rbp+arg_8]
0x18001e859  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e85e  mov     rbx, qword ptr [rbp+var_10]
0x18001e862  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001e865  mov     rcx, [rbx]; hHandle
0x18001e868  call    WaitForSingleObject_0
0x18001e86d  mov     ebx, [rbx+8]
0x18001e870  lea     rcx, [rbp+var_18]; this
0x18001e874  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001e879  mov     eax, ebx
0x18001e87b  mov     rbx, [rsp+50h+arg_0]
0x18001e880  add     rsp, 50h
0x18001e884  pop     rbp
0x18001e885  retn
0x18001e886  lea     rcx, [rbp+var_18]; this
0x18001e88a  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
