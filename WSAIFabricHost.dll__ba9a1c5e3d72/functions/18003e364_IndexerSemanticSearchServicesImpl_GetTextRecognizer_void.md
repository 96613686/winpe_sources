# IndexerSemanticSearchServicesImpl::GetTextRecognizer(void)

- ea: `0x18003e364`
- end: `0x18003e68d`
- name: `?GetTextRecognizer@IndexerSemanticSearchServicesImpl@@AEAA?AUTextRecognizer@Vision@Windows@Microsoft@winrt@@XZ`
- size: `809`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800403b0`
- `0x180046140`

## callees

- `0x180007f72`
- `0x18000c478`
- `0x180013d94`
- `0x180018fa0`
- `0x18001a464`
- `0x18001fd14`
- `0x18002f924`
- `0x180030900`
- `0x1800318c4`
- `0x180031a68`
- `0x180031bac`
- `0x180031d44`
- `0x1800326e8`
- `0x180032ac4`
- `0x180032c94`
- `0x180032ca0`
- `0x180034f90`
- `0x18003e364`
- `0x18004dea8`
- `0x18004ec04`
- `0x18004ff60`
- `0x18005079c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e404`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e404`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e5d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e5d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003e39c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003e39c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e3c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e3dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e3c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e3dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e528`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003e528`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e46e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e4fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e598`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e46e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e4fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e5ff`

## string_xrefs

- `0x18003e64c`: `TextRecognizer::CreateAsync timed out`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 *__fastcall IndexerSemanticSearchServicesImpl::GetTextRecognizer(__int64 a1, __int64 *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 *v5; // rdi
  __int64 v6; // rcx
  RTL_SRWLOCK *v7; // r14
  __int64 v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  __int64 *v10; // rbx
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  void *v17; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  unsigned int *v21; // rax
  LPVOID v22[4]; // [rsp+20h] [rbp-79h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v24[48]; // [rsp+48h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-21h]
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v27[32]; // [rsp+98h] [rbp-1h] BYREF
  _BYTE v28[56]; // [rsp+B8h] [rbp+1Fh] BYREF
  LPVOID v29; // [rsp+100h] [rbp+67h] BYREF
  __int64 v30; // [rsp+110h] [rbp+77h] BYREF
  __int64 v31; // [rsp+118h] [rbp+7Fh] BYREF

  LODWORD(v29) = 0;
  v4 = *(RTL_SRWLOCK **)std::unordered_map<enum AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](
                          a1 + 32,
                          &v29);
  AcquireSRWLockShared(v4);
  v5 = (__int64 *)(a1 + 96);
  v6 = *(_QWORD *)(a1 + 96);
  if ( v6 )
  {
    *a2 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v4 )
      ReleaseSRWLockShared(v4);
  }
  else
  {
    if ( v4 )
      ReleaseSRWLockShared(v4);
    v22[0] = 0;
    LODWORD(v29) = 0;
    v7 = *(RTL_SRWLOCK **)std::unordered_map<enum AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](
                            a1 + 32,
                            &v29);
    AcquireSRWLockExclusive(v7);
    v22[2] = v7;
    if ( *v5 )
    {
      v15 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::ensure_data(v22);
      v29 = (LPVOID)v15;
      if ( v15 )
        _InterlockedIncrement((volatile signed __int32 *)(v15 + 288));
      EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 200));
      ++*(_DWORD *)(v15 + 240);
      *(_BYTE *)(v15 + 278) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>(&v29);
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 152) + 32LL))(*(_QWORD *)(a1 + 152), &v31);
      winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v8);
      if ( v31 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v31);
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v23);
      v9 = (struct _RTL_CRITICAL_SECTION *)pv;
      v29 = pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v9 + 5);
      ++LODWORD(v9[6].DebugInfo);
      LODWORD(v9[6].SpinCount) = 34;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v29);
      winrt::Microsoft::Windows::Vision::TextRecognizer::CreateAsync();
      if ( !(unsigned int)winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Vision::TextRecognizer>>(
                            &v30,
                            0x1D4C0u) )
      {
        v19 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
                v23,
                &v29);
        *(_BYTE *)(std::unique_ptr<wil::srwlock>::operator->(v19) + 276) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v29);
        v20 = winrt::impl::slim_source_location::current(v28);
        winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"TextRecognizer::CreateAsync timed out");
        v21 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v29, -2147023436);
        winrt::hresult_error::hresult_error(pExceptionObject, *v21, v27, v20);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      v10 = (__int64 *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Vision::TextRecognizer>,winrt::Microsoft::Windows::Vision::TextRecognizer>::get(
                         &v30,
                         &v29);
      if ( v5 != v10 )
      {
        if ( *v5 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 96);
        v11 = *v10;
        *v10 = 0;
        *v5 = v11;
      }
      if ( v29 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v29);
      v12 = pv;
      v13 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      v12[18] |= 0x300u;
      if ( *((_QWORD *)v12 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v12 + 2, 2);
      if ( v13 )
        LeaveCriticalSection(v13);
      if ( v30 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v30);
      v14 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v14);
        CoTaskMemFree(v14);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v24);
    }
    v16 = *v5;
    *a2 = *v5;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    v17 = v22[0];
    if ( v22[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v22[0] + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(v17);
      CoTaskMemFree(v17);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18003e364  mov     [rsp-8+arg_8], rbx
0x18003e369  push    rbp
0x18003e36a  push    rsi
0x18003e36b  push    rdi
0x18003e36c  push    r14
0x18003e36e  push    r15
0x18003e370  lea     rbp, [rsp-37h]
0x18003e375  sub     rsp, 0D0h
0x18003e37c  mov     r15, rdx
0x18003e37f  mov     rsi, rcx
0x18003e382  mov     dword ptr [rbp+57h+arg_0], 0
0x18003e389  lea     rdx, [rbp+57h+arg_0]
0x18003e38d  add     rcx, 20h ; ' '
0x18003e391  call    ??A?$unordered_map@W4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@U?$hash@W4AIFabric_Component@@@3@U?$equal_to@W4AIFabric_Component@@@3@V?$allocator@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@3@@std@@QEAAAEAV?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@1@$$QEAW4AIFabric_Component@@@Z; std::unordered_map<AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](AIFabric_Component &&)
0x18003e396  mov     rbx, [rax]
0x18003e399  mov     rcx, rbx; SRWLock
0x18003e39c  call    cs:__imp_AcquireSRWLockShared
0x18003e3a2  lea     rdi, [rsi+60h]
0x18003e3a6  mov     rcx, [rdi]
0x18003e3a9  test    rcx, rcx
0x18003e3ac  jz      short loc_18003E3D4
0x18003e3ae  mov     [r15], rcx
0x18003e3b1  mov     rax, [rcx]
0x18003e3b4  mov     rax, [rax+8]
0x18003e3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3bd  test    rbx, rbx
0x18003e3c0  jz      loc_18003E605
0x18003e3c6  mov     rcx, rbx; SRWLock
0x18003e3c9  call    cs:__imp_ReleaseSRWLockShared
0x18003e3cf  jmp     loc_18003E605
0x18003e3d4  test    rbx, rbx
0x18003e3d7  jz      short loc_18003E3E2
0x18003e3d9  mov     rcx, rbx; SRWLock
0x18003e3dc  call    cs:__imp_ReleaseSRWLockShared
0x18003e3e2  mov     [rbp+57h+var_D0], 0
0x18003e3ea  mov     dword ptr [rbp+57h+arg_0], 0
0x18003e3f1  lea     rdx, [rbp+57h+arg_0]
0x18003e3f5  lea     rcx, [rsi+20h]
0x18003e3f9  call    ??A?$unordered_map@W4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@U?$hash@W4AIFabric_Component@@@3@U?$equal_to@W4AIFabric_Component@@@3@V?$allocator@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@3@@std@@QEAAAEAV?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@1@$$QEAW4AIFabric_Component@@@Z; std::unordered_map<AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](AIFabric_Component &&)
0x18003e3fe  mov     r14, [rax]
0x18003e401  mov     rcx, r14; SRWLock
0x18003e404  call    cs:__imp_AcquireSRWLockExclusive
0x18003e40a  mov     [rbp+57h+var_C0], r14
0x18003e40e  cmp     qword ptr [rdi], 0
0x18003e412  jnz     loc_18003E575
0x18003e418  mov     rcx, [rsi+98h]
0x18003e41f  mov     rax, [rcx]
0x18003e422  lea     rdx, [rbp+57h+arg_18]
0x18003e426  mov     rax, [rax+20h]
0x18003e42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e42f  nop
0x18003e430  mov     rcx, rax
0x18003e433  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18003e438  nop
0x18003e439  cmp     [rbp+57h+arg_18], 0
0x18003e43e  jz      short loc_18003E449
0x18003e440  lea     rcx, [rbp+57h+arg_18]
0x18003e444  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003e449  lea     rcx, [rbp+57h+var_B0]
0x18003e44d  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003e452  nop
0x18003e453  mov     rbx, [rbp+57h+pv]
0x18003e457  mov     [rbp+57h+arg_0], rbx
0x18003e45b  test    rbx, rbx
0x18003e45e  jz      short loc_18003E467
0x18003e460  lock inc dword ptr [rbx+120h]
0x18003e467  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18003e46e  call    cs:__imp_EnterCriticalSection
0x18003e474  inc     dword ptr [rbx+0F0h]
0x18003e47a  mov     dword ptr [rbx+110h], 22h ; '"'
0x18003e484  lea     rcx, [rbp+57h+arg_0]
0x18003e488  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003e48d  lea     rcx, [rbp+57h+arg_10]
0x18003e491  call    ?CreateAsync@TextRecognizer@Vision@Windows@Microsoft@winrt@@SA@XZ; winrt::Microsoft::Windows::Vision::TextRecognizer::CreateAsync(void)
0x18003e496  nop
0x18003e497  mov     edx, 1D4C0h
0x18003e49c  lea     rcx, [rbp+57h+arg_10]
0x18003e4a0  call    ??$wait_for_completed@U?$IAsyncOperation@UTextRecognizer@Vision@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UTextRecognizer@Vision@Windows@Microsoft@winrt@@@Foundation@Windows@1@I@Z
0x18003e4a5  lea     rdx, [rbp+57h+arg_0]
0x18003e4a9  test    eax, eax
0x18003e4ab  jz      loc_18003E61F
0x18003e4b1  lea     rcx, [rbp+57h+arg_10]
0x18003e4b5  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UTextRecognizer@Vision@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@UTextRecognizer@Vision@3Microsoft@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Vision::TextRecognizer>,winrt::Microsoft::Windows::Vision::TextRecognizer>::get(void)
0x18003e4ba  mov     rbx, rax
0x18003e4bd  cmp     rdi, rax
0x18003e4c0  jz      short loc_18003E4DD
0x18003e4c2  cmp     qword ptr [rdi], 0
0x18003e4c6  jz      short loc_18003E4D0
0x18003e4c8  mov     rcx, rdi
0x18003e4cb  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003e4d0  mov     rcx, [rbx]
0x18003e4d3  mov     qword ptr [rbx], 0
0x18003e4da  mov     [rdi], rcx
0x18003e4dd  cmp     [rbp+57h+arg_0], 0
0x18003e4e2  jz      short loc_18003E4ED
0x18003e4e4  lea     rcx, [rbp+57h+arg_0]
0x18003e4e8  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003e4ed  mov     rbx, [rbp+57h+pv]
0x18003e4f1  lea     rsi, [rbx+0C8h]
0x18003e4f8  mov     rcx, rsi; lpCriticalSection
0x18003e4fb  call    cs:__imp_EnterCriticalSection
0x18003e501  or      dword ptr [rbx+48h], 300h
0x18003e508  cmp     qword ptr [rbx+0F8h], 0
0x18003e510  jz      short loc_18003E520
0x18003e512  mov     edx, 2
0x18003e517  lea     rcx, [rbx+8]
0x18003e51b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003e520  test    rsi, rsi
0x18003e523  jz      short loc_18003E52F
0x18003e525  mov     rcx, rsi; lpCriticalSection
0x18003e528  call    cs:__imp_LeaveCriticalSection
0x18003e52e  nop
0x18003e52f  cmp     [rbp+57h+arg_10], 0
0x18003e534  jz      short loc_18003E540
0x18003e536  lea     rcx, [rbp+57h+arg_10]
0x18003e53a  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003e53f  nop
0x18003e540  mov     rbx, [rbp+57h+pv]
0x18003e544  test    rbx, rbx
0x18003e547  jz      short loc_18003E56A
0x18003e549  or      eax, 0FFFFFFFFh
0x18003e54c  lock xadd [rbx+120h], eax
0x18003e554  cmp     eax, 1
0x18003e557  jnz     short loc_18003E56A
0x18003e559  mov     rcx, rbx
0x18003e55c  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18003e561  mov     rcx, rbx; pv
0x18003e564  call    cs:__imp_CoTaskMemFree
0x18003e56a  lea     rcx, [rbp+57h+var_A8]; this
0x18003e56e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003e573  jmp     short loc_18003E5B4
0x18003e575  lea     rcx, [rbp+57h+var_D0]
0x18003e579  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::ensure_data(void)
0x18003e57e  mov     rbx, [rax]
0x18003e581  mov     [rbp+57h+arg_0], rbx
0x18003e585  test    rbx, rbx
0x18003e588  jz      short loc_18003E591
0x18003e58a  lock inc dword ptr [rbx+120h]
0x18003e591  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18003e598  call    cs:__imp_EnterCriticalSection
0x18003e59e  inc     dword ptr [rbx+0F0h]
0x18003e5a4  mov     byte ptr [rbx+116h], 1
0x18003e5ab  lea     rcx, [rbp+57h+arg_0]
0x18003e5af  call    ??1?$test_data_control@V?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>>(void)
0x18003e5b4  mov     rcx, [rdi]
0x18003e5b7  mov     [r15], rcx
0x18003e5ba  test    rcx, rcx
0x18003e5bd  jz      short loc_18003E5CC
0x18003e5bf  mov     rax, [rcx]
0x18003e5c2  mov     rax, [rax+8]
0x18003e5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5cb  nop
0x18003e5cc  test    r14, r14
0x18003e5cf  jz      short loc_18003E5DB
0x18003e5d1  mov     rcx, r14; SRWLock
0x18003e5d4  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e5da  nop
0x18003e5db  mov     rbx, [rbp+57h+var_D0]
0x18003e5df  test    rbx, rbx
0x18003e5e2  jz      short loc_18003E605
0x18003e5e4  or      eax, 0FFFFFFFFh
0x18003e5e7  lock xadd [rbx+120h], eax
0x18003e5ef  cmp     eax, 1
0x18003e5f2  jnz     short loc_18003E605
0x18003e5f4  mov     rcx, rbx
0x18003e5f7  call    ??1?$merged_data@U_tip_ModelLoadPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>::~merged_data<_tip_ModelLoadPerfTest,_tip_ModelLoadPerfTest>(void)
0x18003e5fc  mov     rcx, rbx; pv
0x18003e5ff  call    cs:__imp_CoTaskMemFree
0x18003e605  mov     rax, r15
0x18003e608  mov     rbx, [rsp+0F0h+arg_8]
0x18003e610  add     rsp, 0D0h
0x18003e617  pop     r15
0x18003e619  pop     r14
0x18003e61b  pop     rdi
0x18003e61c  pop     rsi
0x18003e61d  pop     rbp
0x18003e61e  retn
0x18003e61f  lea     rcx, [rbp+57h+var_B0]
0x18003e623  call    ??C?$test_watcher@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@1@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(void)
0x18003e628  mov     rcx, rax
0x18003e62b  call    ??C?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@QEBAPEAVsrwlock@wil@@XZ; std::unique_ptr<wil::srwlock>::operator->(void)
0x18003e630  mov     byte ptr [rax+114h], 1
0x18003e637  lea     rcx, [rbp+57h+arg_0]
0x18003e63b  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003e640  lea     rcx, [rbp+57h+var_38]
0x18003e644  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18003e649  mov     rbx, rax
0x18003e64c  lea     rdx, aTextrecognizer; "TextRecognizer::CreateAsync timed out"
0x18003e653  lea     rcx, [rbp+57h+var_58]; this
0x18003e657  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003e65c  mov     edx, 800705B4h; int
0x18003e661  lea     rcx, [rbp+57h+arg_0]; this
0x18003e665  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003e66a  mov     r9, rbx
0x18003e66d  lea     r8, [rbp+57h+var_58]
0x18003e671  mov     edx, [rax]
0x18003e673  lea     rcx, [rbp+57h+pExceptionObject]
0x18003e677  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18003e67c  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003e683  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003e687  call    _CxxThrowException_0
```
