# winrt::Microsoft::Windows::SemanticSearch::implementation::FixObsoleteSpaceV6

- ea: `0x180038e00`
- end: `0x180039afb`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::FixObsoleteSpaceV6`
- size: `3323`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x180059df0`

## callees

- `0x180001f40`
- `0x180002080`
- `0x180002bb0`
- `0x180009580`
- `0x180009900`
- `0x180014660`
- `0x18001eb50`
- `0x18001fbc0`
- `0x18001fc90`
- `0x18002e220`
- `0x180037490`
- `0x180037ac0`
- `0x180037b70`
- `0x180037c20`
- `0x180038e00`
- `0x180039b00`
- `0x18003c660`
- `0x18003c700`
- `0x18003c780`
- `0x18003c9e0`
- `0x18003dc90`
- `0x18004c070`
- `0x18004c46c`
- `0x18004c4d8`
- `0x18004c8ac`
- `0x18004c8cc`
- `0x18004ecf0`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`
- `0x18005e670`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180039228`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800396e6`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800396f1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180039228`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800396e6`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800396f1`
- `KERNEL32!GetLastError` at `0x180038ea7`
- `KERNEL32!GetLastError` at `0x180038ea7`
- `KERNEL32!CloseHandle` at `0x180039956`
- `KERNEL32!CloseHandle` at `0x180039983`
- `KERNEL32!CloseHandle` at `0x180039956`
- `KERNEL32!CloseHandle` at `0x180039983`
- `KERNEL32!ReleaseMutex` at `0x180039940`
- `KERNEL32!ReleaseMutex` at `0x18003996e`
- `KERNEL32!ReleaseMutex` at `0x180039940`
- `KERNEL32!ReleaseMutex` at `0x18003996e`
- `KERNEL32!CreateMutexExW` at `0x180038e91`
- `KERNEL32!CreateMutexExW` at `0x180038e91`
- `KERNEL32!WaitForSingleObjectEx` at `0x180038ebc`
- `KERNEL32!WaitForSingleObjectEx` at `0x180038ebc`

## string_xrefs

- `0x1800399ca`: `Failed to create system-wide mutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
int __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::FixObsoleteSpaceV6(
        void (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2)
{
  int result; // eax
  HANDLE Mutex; // rbx
  DWORD v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  void *v10; // r13
  __int64 v11; // rsi
  _QWORD *v12; // rdx
  const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *Async; // rax
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // rax
  __int128 *VectorSpaceIds; // rax
  int v16; // eax
  void *v17; // rcx
  int v18; // eax
  bool v19; // bl
  int v20; // eax
  volatile signed __int32 *v21; // r12
  _QWORD *v22; // rbx
  void (__fastcall *v23)(__int64 *, __int64 *); // rbx
  int v24; // esi
  HANDLE ProcessHeap; // rax
  unsigned int v26; // esi
  void *v27; // rcx
  int v28; // eax
  unsigned int v29; // esi
  void *v30; // rcx
  int v31; // eax
  void *v32; // rcx
  int v33; // eax
  _QWORD *v34; // rax
  _QWORD *v35; // rdx
  const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *v36; // rax
  void (__fastcall ***v37)(_QWORD, __int64 *, __int64 *); // rax
  __int64 **v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 *v41; // rbx
  int v42; // eax
  __int64 v43; // rcx
  int v44; // eax
  HANDLE v45; // rax
  int v46; // eax
  volatile signed __int32 *v47; // r12
  _QWORD *v48; // rbx
  __int64 *v49; // rbx
  int v50; // esi
  HANDLE v51; // rax
  unsigned int v52; // esi
  __int64 v53; // rcx
  int v54; // eax
  unsigned int v55; // esi
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // rcx
  int v59; // eax
  _QWORD *v60; // rax
  _QWORD *v61; // rdx
  const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *v62; // rax
  void (__fastcall ***v63)(_QWORD, __int64 *, __int64 *); // rax
  unsigned int v64; // r8d
  const char *v65; // r9
  unsigned int v66; // r8d
  const char *v67; // r9
  unsigned int v68; // r8d
  const char *v69; // r9
  unsigned int v70; // r8d
  const char *v71; // r9
  winrt::hresult *v72; // rax
  __int64 *v73; // [rsp+20h] [rbp-E0h] BYREF
  const char *v74; // [rsp+28h] [rbp-D8h]
  void (__fastcall *v75)(__int64 *, __int64 *); // [rsp+30h] [rbp-D0h] BYREF
  const char *v76; // [rsp+38h] [rbp-C8h]
  void (__fastcall ***v77)(_QWORD, __int64 *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v78)(_QWORD, __int64 *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v79[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  void *v81; // [rsp+70h] [rbp-90h]
  void *v82; // [rsp+78h] [rbp-88h]
  _QWORD v83[2]; // [rsp+80h] [rbp-80h] BYREF
  int v84; // [rsp+90h] [rbp-70h]
  HANDLE v85; // [rsp+A0h] [rbp-60h]
  HANDLE hObject; // [rsp+A8h] [rbp-58h]
  _QWORD v87[2]; // [rsp+B0h] [rbp-50h] BYREF
  void *v88; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID lpMem[2]; // [rsp+D0h] [rbp-30h] BYREF
  void *v91; // [rsp+E0h] [rbp-20h] BYREF
  __int128 Buf1; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v93; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticIndex3<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>::GetVectorSpaceIds(
    a1,
    &Buf1);
  result = memcmp(&Buf1, &winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId, 0x10u);
  if ( result )
    return result;
  result = memcmp(
             &v93,
             &winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Obsolete::AsgVectorSpaceId,
             0x10u);
  if ( result )
    return result;
  v85 = 0;
  Mutex = CreateMutexExW(0, L"Global\\WCR_SemanticIndex_SpaceV6VectorSpaceFix", 0, 0x1F0001u);
  hObject = Mutex;
  if ( !Mutex )
  {
    LODWORD(v87[0]) = 55;
    v87[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\SemanticTextIndexStore.cpp";
    winrt::param::hstring::hstring((winrt::param::hstring *)v83, L"Failed to create system-wide mutex");
    v72 = winrt::hresult::hresult((winrt::hresult *)&v91, -2147467259);
    winrt::hresult_error::hresult_error(&pExceptionObject, *(unsigned int *)v72, v83, v87);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  GetLastError();
  v85 = Mutex;
  v6 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v6 == 258 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v6 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v7, v8, v9);
    v10 = Mutex;
  }
  v87[0] = v10;
  winrt::impl::consume_Windows_Foundation_IClosable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>::Close(a1);
  v11 = (unsigned int)tls_index;
  if ( !*a2 || *a2 == 16 )
  {
    if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
    {
      Init_thread_header(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
      if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA == -1 )
      {
        `winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null = 0;
        atexit(winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions_winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions__::_2_::_dynamic_atexit_destructor_for__null__);
        Init_thread_footer(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
      }
    }
    v12 = &`winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null;
  }
  else
  {
    v12 = (_QWORD *)(*a2 - 16LL + 56);
  }
  Async = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::CreateAsync(
            (const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *)lpMem,
            v12);
  winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>>(
    &v77,
    Async);
  if ( a1 == &v77 )
  {
    if ( v77 )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v77);
  }
  else
  {
    if ( *a1 )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1);
    v14 = v77;
    v77 = 0;
    *a1 = v14;
  }
  if ( lpMem[0] )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(lpMem);
  VectorSpaceIds = (__int128 *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticIndex3<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>::GetVectorSpaceIds(
                                 a1,
                                 &pExceptionObject);
  Buf1 = *VectorSpaceIds;
  v93 = VectorSpaceIds[1];
  if ( !memcmp(&Buf1, &winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId, 0x10u)
    && !memcmp(
          &v93,
          &winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Obsolete::AsgVectorSpaceId,
          0x10u) )
  {
    winrt::impl::consume_Windows_Foundation_IClosable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>::Close(a1);
    v73 = &qword_180086818;
    _InterlockedIncrement64(&qword_180086818);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4> )
    {
      v91 = 0;
      LODWORD(v75) = 214;
      v76 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Windows.Workloads.h";
      v16 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4>
                                                        + 48LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4>,
              &v91);
      if ( v16 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v16, &v75);
      }
      lpMem[0] = v91;
      _InterlockedDecrement64(&qword_180086818);
    }
    else
    {
      _InterlockedDecrement64(&qword_180086818);
      v75 = (void (__fastcall *)(__int64 *, __int64 *))`winrt::Microsoft::Windows::Workloads::WorkloadManager::GetDefault'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4>::call<winrt::Microsoft::Windows::Workloads::WorkloadManager (*)(winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4 const &)>(
        0,
        (__int64 *)lpMem,
        &v75);
    }
    LODWORD(v91) = 0;
    LODWORD(v73) = 146;
    v74 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Windows.Workloads.h";
    if ( lpMem[0] )
    {
      v88 = 0;
      (**(void (__fastcall ***)(LPVOID, __int64 *, void **))lpMem[0])(
        lpMem[0],
        winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager2>,
        &v88);
      v17 = v88;
    }
    else
    {
      v17 = 0;
    }
    v88 = v17;
    v18 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)v17 + 64LL))(v17, &v91);
    if ( v18 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v18, &v73);
    }
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v88);
    v19 = (_DWORD)v91 == 3;
    if ( lpMem[0] )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(lpMem);
    if ( v19 )
    {
      LODWORD(v91) = 1;
      lpMem[0] = 0;
      LODWORD(v73) = 1313;
      v74 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Windows.SemanticSearch.h";
      v20 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a2 + 48LL))(*a2, lpMem);
      if ( v20 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v20, &v73);
      }
      v21 = (volatile signed __int32 *)lpMem[0];
      v75 = (void (__fastcall *)(__int64 *, __int64 *))lpMem[0];
      v22 = operator new(0x48u);
      v73 = v22;
      LOBYTE(v84) = 1;
      *(_WORD *)((char *)&v84 + 1) = *(_WORD *)((char *)&v81 + 1);
      HIBYTE(v84) = BYTE3(v81);
      pExceptionObject = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId;
      LODWORD(v81) = v84;
      winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions::SemanticTextIndexStoreOptions(
        v22,
        (__int64 *)&v75,
        (const char *)&v91,
        (__int64)&pExceptionObject);
      *v22 = &winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions::`vftable';
      v23 = (void (__fastcall *)(__int64 *, __int64 *))(v22 + 2);
      v75 = v23;
      if ( v21 )
      {
        v24 = _InterlockedDecrement(v21 + 6);
        if ( v24 )
        {
          if ( v24 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem[0]);
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57696949>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57696949>::GetImpl'::`2'::impl) )
      {
        v26 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions5<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::QuantizationDisposition(a2);
        LODWORD(v73) = 1356;
        v74 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\win"
              "rt\\Microsoft.Windows.SemanticSearch.h";
        if ( v23 )
        {
          v88 = 0;
          (**(void (__fastcall ***)(void (__fastcall *)(__int64 *, __int64 *), __int64 *, void **))v23)(
            v23,
            &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions5>,
            &v88);
          v27 = v88;
        }
        else
        {
          v27 = 0;
        }
        v88 = v27;
        v28 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v27 + 56LL))(v27, v26);
        if ( v28 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v28, &v73);
        }
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v88);
      }
      v29 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions3<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::ModelsToLoad(a2);
      LODWORD(v73) = 1336;
      v74 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Windows.SemanticSearch.h";
      if ( v23 )
      {
        v88 = 0;
        (**(void (__fastcall ***)(void (__fastcall *)(__int64 *, __int64 *), __int64 *, void **))v23)(
          v23,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions3>,
          &v88);
        v30 = v88;
      }
      else
      {
        v30 = 0;
      }
      v88 = v30;
      v31 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v30 + 56LL))(v30, v29);
      if ( v31 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v31, &v73);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v88);
      lpMem[0] = 0;
      LODWORD(v73) = 1325;
      v74 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Windows.SemanticSearch.h";
      if ( v23 )
      {
        v88 = 0;
        (**(void (__fastcall ***)(void (__fastcall *)(__int64 *, __int64 *), __int64 *, void **))v23)(
          v23,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions2>,
          &v88);
        v32 = v88;
      }
      else
      {
        v32 = 0;
      }
      v88 = v32;
      v33 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v32 + 48LL))(v32, lpMem);
      if ( v33 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v33, &v73);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v88);
      v34 = (_QWORD *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions2<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::EncryptionOptions(
                        a2,
                        &v89);
      winrt::impl::consume_Microsoft_Windows_SemanticSearch_IIndexEncryptionOptions2<winrt::Microsoft::Windows::SemanticSearch::IndexEncryptionOptions>::CopyFrom(
        (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))lpMem,
        v34);
      if ( v89 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v89);
      if ( lpMem[0] )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(lpMem);
      if ( !v23 || v23 == (void (__fastcall *)(__int64 *, __int64 *))16 )
      {
        if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
        {
          Init_thread_header(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
          if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA == -1 )
          {
            `winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null = 0;
            atexit(winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions_winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions__::_2_::_dynamic_atexit_destructor_for__null__);
            Init_thread_footer(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
          }
        }
        v35 = &`winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null;
      }
      else
      {
        v35 = (_QWORD *)((char *)v23 + 40);
      }
      v36 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::CreateAsync(
              (const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *)&v89,
              v35);
      winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>>(
        &v78,
        v36);
      if ( a1 == &v78 )
      {
        if ( v78 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v78);
      }
      else
      {
        if ( *a1 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1);
        v37 = v78;
        v78 = 0;
        *a1 = v37;
      }
      if ( v89 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v89);
      if ( !v23 )
        goto LABEL_137;
      v38 = (__int64 **)&v75;
    }
    else
    {
      v39 = *(_QWORD *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions2<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::EncryptionOptions(
                         a2,
                         &v89);
      if ( v39 && (v40 = v39 - 16) != 0 )
      {
        v41 = (__int64 *)(v40 + 32);
      }
      else
      {
        if ( __TSS0__1____GetAsgImpl_UIndexEncryptionOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUIndexEncryptionOptions_2345__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v11) + 4LL) )
        {
          Init_thread_header(&__TSS0__1____GetAsgImpl_UIndexEncryptionOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUIndexEncryptionOptions_2345__Z_4HA);
          if ( __TSS0__1____GetAsgImpl_UIndexEncryptionOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUIndexEncryptionOptions_2345__Z_4HA == -1 )
          {
            `winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::IndexEncryptionOptions,winrt::Microsoft::Windows::SemanticSearch::IndexEncryptionOptions>'::`2'::null = 0;
            atexit(winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl_winrt::Microsoft::Windows::SemanticSearch::implementation::IndexEncryptionOptions_winrt::Microsoft::Windows::SemanticSearch::IndexEncryptionOptions__::_2_::_dynamic_atexit_destructor_for__null__);
            Init_thread_footer(&__TSS0__1____GetAsgImpl_UIndexEncryptionOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUIndexEncryptionOptions_2345__Z_4HA);
          }
        }
        v41 = &`winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::IndexEncryptionOptions,winrt::Microsoft::Windows::SemanticSearch::IndexEncryptionOptions>'::`2'::null;
      }
      lpMem[0] = 0;
      LODWORD(v73) = 1313;
      v74 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Windows.SemanticSearch.h";
      v42 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a2 + 48LL))(*a2, lpMem);
      if ( v42 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v42, &v73);
      }
      v73 = (__int64 *)lpMem[0];
      v83[0] = lpMem[0];
      *(_QWORD *)&pExceptionObject = v83;
      *((_QWORD *)&pExceptionObject + 1) = v41;
      v81 = &winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6Obsolete::VectorSpaceId;
      v82 = &winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId;
      v75 = (void (__fastcall *)(__int64 *, __int64 *))&qword_180086A38;
      _InterlockedIncrement64(&qword_180086A38);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3> )
      {
        `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::ResetVectorSpaceIds'::`2'::_lambda_1_::operator()(
          (__int64)&pExceptionObject,
          (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>);
        _InterlockedDecrement64(&qword_180086A38);
      }
      else
      {
        _InterlockedDecrement64(&qword_180086A38);
        ___call_AEAV_lambda_1___1__ResetVectorSpaceIds_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUhstring_param_9_AEBUIndexEncryptionOptions_456789_AEBUguid_9_2_Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics3_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__ResetVectorSpaceIds_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUhstring_param_2_AEBUIndexEncryptionOptions_6789Microsoft_2_AEBUguid_2_2_Z__Z(
          v43,
          (__int64)&pExceptionObject);
      }
      if ( lpMem[0] )
      {
        v44 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
        if ( v44 )
        {
          if ( v44 < 0 )
            abort();
        }
        else
        {
          v45 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v45, 0, lpMem[0]);
        }
      }
      if ( v89 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v89);
      LODWORD(v91) = 2;
      lpMem[0] = 0;
      LODWORD(v73) = 1313;
      v74 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Windows.SemanticSearch.h";
      v46 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a2 + 48LL))(*a2, lpMem);
      if ( v46 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v46, &v73);
      }
      v47 = (volatile signed __int32 *)lpMem[0];
      v75 = (void (__fastcall *)(__int64 *, __int64 *))lpMem[0];
      v48 = operator new(0x48u);
      LOBYTE(v84) = 1;
      *(_WORD *)((char *)&v84 + 1) = *(_WORD *)((char *)&v81 + 1);
      HIBYTE(v84) = BYTE3(v81);
      pExceptionObject = winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId;
      LODWORD(v81) = v84;
      winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions::SemanticTextIndexStoreOptions(
        v48,
        (__int64 *)&v75,
        (const char *)&v91,
        (__int64)&pExceptionObject);
      *v48 = &winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions::`vftable';
      v49 = v48 + 2;
      v73 = v49;
      if ( v47 )
      {
        v50 = _InterlockedDecrement(v47 + 6);
        if ( v50 )
        {
          if ( v50 < 0 )
            abort();
        }
        else
        {
          v51 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v51, 0, lpMem[0]);
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57696949>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57696949>::GetImpl'::`2'::impl) )
      {
        v52 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions5<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::QuantizationDisposition(a2);
        LODWORD(v75) = 1356;
        v76 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\win"
              "rt\\Microsoft.Windows.SemanticSearch.h";
        if ( v49 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))*v49)(
            v49,
            &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions5>,
            &v89);
          v53 = v89;
        }
        else
        {
          v53 = 0;
        }
        v89 = v53;
        v54 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v53 + 56LL))(v53, v52);
        if ( v54 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v54, &v75);
        }
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v89);
      }
      v55 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions3<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::ModelsToLoad(a2);
      LODWORD(v75) = 1336;
      v76 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Windows.SemanticSearch.h";
      if ( v49 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))*v49)(
          v49,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions3>,
          &v89);
        v56 = v89;
      }
      else
      {
        v56 = 0;
      }
      v89 = v56;
      v57 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 56LL))(v56, v55);
      if ( v57 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v57, &v75);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v89);
      v88 = 0;
      LODWORD(lpMem[0]) = 1325;
      lpMem[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\"
                 "winrt\\Microsoft.Windows.SemanticSearch.h";
      if ( v49 )
      {
        v89 = 0;
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))*v49)(
          v49,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions2>,
          &v89);
        v58 = v89;
      }
      else
      {
        v58 = 0;
      }
      v89 = v58;
      v59 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v58 + 48LL))(v58, &v88);
      if ( v59 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v59, lpMem);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v89);
      lpMem[0] = v88;
      v60 = (_QWORD *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions2<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::EncryptionOptions(
                        a2,
                        &v75);
      winrt::impl::consume_Microsoft_Windows_SemanticSearch_IIndexEncryptionOptions2<winrt::Microsoft::Windows::SemanticSearch::IndexEncryptionOptions>::CopyFrom(
        (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))lpMem,
        v60);
      if ( v75 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v75);
      if ( lpMem[0] )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(lpMem);
      if ( !v49 || v49 == (__int64 *)16 )
      {
        if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
        {
          Init_thread_header(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
          if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA == -1 )
          {
            `winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null = 0;
            atexit(winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions_winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions__::_2_::_dynamic_atexit_destructor_for__null__);
            Init_thread_footer(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
          }
        }
        v61 = &`winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null;
      }
      else
      {
        v61 = v49 + 5;
      }
      v62 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::CreateAsync(
              (const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *)&v75,
              v61);
      winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>>(
        v79,
        v62);
      if ( a1 == v79 )
      {
        if ( v79[0] )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v79);
      }
      else
      {
        if ( *a1 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1);
        v63 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))v79[0];
        v79[0] = 0;
        *a1 = v63;
      }
      if ( v75 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v75);
      if ( !v49 )
        goto LABEL_137;
      v38 = &v73;
    }
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v38);
LABEL_137:
    if ( v10 && !ReleaseMutex(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v64, v65);
    result = CloseHandle(hObject);
    if ( !result )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v66, v67);
    return result;
  }
  if ( v10 && !ReleaseMutex(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v68, v69);
  result = CloseHandle(Mutex);
  if ( !result )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v70, v71);
  return result;
}

```

## disassembly

```asm
0x180038e00  mov     [rsp-8+arg_10], rbx
0x180038e05  push    rbp
0x180038e06  push    rsi
0x180038e07  push    rdi
0x180038e08  push    r12
0x180038e0a  push    r13
0x180038e0c  push    r14
0x180038e0e  push    r15
0x180038e10  lea     rbp, [rsp-10h]
0x180038e15  sub     rsp, 110h
0x180038e1c  mov     rax, cs:__security_cookie
0x180038e23  xor     rax, rsp
0x180038e26  mov     [rbp+40h+var_38], rax
0x180038e2a  mov     r15, rdx
0x180038e2d  mov     rdi, rcx
0x180038e30  xor     r12d, r12d
0x180038e33  lea     rdx, [rbp+40h+Buf1]
0x180038e37  call    ?GetVectorSpaceIds@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticIndex3@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticIndex3<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>::GetVectorSpaceIds(void)
0x180038e3c  mov     r8d, 10h; Size
0x180038e42  lea     r14, ?VectorSpaceId@SpaceV6@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId
0x180038e49  mov     rdx, r14; Buf2
0x180038e4c  lea     rcx, [rbp+40h+Buf1]; Buf1
0x180038e50  call    memcmp
0x180038e55  test    eax, eax
0x180038e57  jnz     loc_180039991
0x180038e5d  mov     r8d, 10h; Size
0x180038e63  lea     rdx, ?AsgVectorSpaceId@SpaceV6Obsolete@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; Buf2
0x180038e6a  lea     rcx, [rbp+40h+var_48]; Buf1
0x180038e6e  call    memcmp
0x180038e73  test    eax, eax
0x180038e75  jnz     loc_180039991
0x180038e7b  mov     [rbp+40h+var_A0], r12
0x180038e7f  mov     r9d, 1F0001h; dwDesiredAccess
0x180038e85  xor     r8d, r8d; dwFlags
0x180038e88  lea     rdx, Name; "Global\\WCR_SemanticIndex_SpaceV6Vector"...
0x180038e8f  xor     ecx, ecx; lpMutexAttributes
0x180038e91  call    cs:__imp_CreateMutexExW
0x180038e97  mov     rbx, rax
0x180038e9a  mov     [rbp+40h+hObject], rax
0x180038e9e  test    rax, rax
0x180038ea1  jz      loc_1800399B8
0x180038ea7  call    cs:__imp_GetLastError
0x180038ead  mov     [rbp+40h+var_A0], rbx
0x180038eb1  xor     r8d, r8d; bAlertable
0x180038eb4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180038eb9  mov     rcx, rbx; hHandle
0x180038ebc  call    cs:__imp_WaitForSingleObjectEx
0x180038ec2  cmp     eax, 102h
0x180038ec7  jz      short loc_180038ED9
0x180038ec9  test    eax, 0FFFFFF7Fh
0x180038ece  jnz     loc_180039A1D
0x180038ed4  mov     r13, rbx
0x180038ed7  jmp     short loc_180038EDC
0x180038ed9  mov     r13, r12
0x180038edc  mov     [rbp+40h+var_90], r13
0x180038ee0  mov     rcx, rdi
0x180038ee3  call    ?Close@?$consume_Windows_Foundation_IClosable@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>::Close(void)
0x180038ee8  mov     rax, [r15]
0x180038eeb  mov     ecx, 4
0x180038ef0  mov     esi, cs:_tls_index
0x180038ef6  test    rax, rax
0x180038ef9  jz      short loc_180038F07
0x180038efb  add     rax, 0FFFFFFFFFFFFFFF0h
0x180038eff  jz      short loc_180038F07
0x180038f01  lea     rdx, [rax+38h]
0x180038f05  jmp     short loc_180038F5A
0x180038f07  mov     rax, gs:58h
0x180038f10  mov     rax, [rax+rsi*8]
0x180038f14  mov     ecx, [rcx+rax]
0x180038f17  cmp     cs:?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA, ecx
0x180038f1d  jle     short loc_180038F53
0x180038f1f  lea     rcx, ?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA
0x180038f26  call    _Init_thread_header
0x180038f2b  cmp     cs:?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA, 0FFFFFFFFh
0x180038f32  jnz     short loc_180038F53
0x180038f34  mov     cs:?null@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4U6Compatibility@AiFabric@SemanticIndex@Asg@45@B, r12
0x180038f3b  lea     rcx, _winrt__Microsoft__Windows__SemanticSearch__implementation__GetAsgImpl_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextIndexStoreOptions_winrt__Microsoft__Windows__SemanticSearch__SemanticTextIndexStoreOptions_____2____dynamic_atexit_destructor_for__null__; void (__cdecl *)()
0x180038f42  call    atexit
0x180038f47  lea     rcx, ?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA
0x180038f4e  call    _Init_thread_footer
0x180038f53  lea     rdx, ?null@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4U6Compatibility@AiFabric@SemanticIndex@Asg@45@B
0x180038f5a  lea     rcx, [rbp+40h+lpMem]; struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *
0x180038f5e  call    ?CreateAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::CreateAsync(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions const &)
0x180038f63  nop
0x180038f64  mov     rdx, rax
0x180038f67  lea     rcx, [rsp+140h+var_100]
0x180038f6c  call    ??$wait_get@U?$IAsyncOperation@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@1@@Z
0x180038f71  lea     rax, [rsp+140h+var_100]
0x180038f76  cmp     rdi, rax
0x180038f79  jz      short loc_180038F98
0x180038f7b  cmp     qword ptr [rdi], 0
0x180038f7f  jz      short loc_180038F89
0x180038f81  mov     rcx, rdi
0x180038f84  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180038f89  mov     rax, [rsp+140h+var_100]
0x180038f8e  mov     [rsp+140h+var_100], r12
0x180038f93  mov     [rdi], rax
0x180038f96  jmp     short loc_180038FAB
0x180038f98  cmp     [rsp+140h+var_100], 0
0x180038f9e  jz      short loc_180038FAB
0x180038fa0  lea     rcx, [rsp+140h+var_100]
0x180038fa5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180038faa  nop
0x180038fab  cmp     [rbp+40h+lpMem], 0
0x180038fb0  jz      short loc_180038FBB
0x180038fb2  lea     rcx, [rbp+40h+lpMem]
0x180038fb6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180038fbb  lea     rdx, [rsp+140h+pExceptionObject]
0x180038fc0  mov     rcx, rdi
0x180038fc3  call    ?GetVectorSpaceIds@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticIndex3@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticIndex3<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>::GetVectorSpaceIds(void)
0x180038fc8  movups  xmm0, xmmword ptr [rax]
0x180038fcb  movups  [rbp+40h+Buf1], xmm0
0x180038fcf  movups  xmm1, xmmword ptr [rax+10h]
0x180038fd3  movups  [rbp+40h+var_48], xmm1
0x180038fd7  mov     r8d, 10h; Size
0x180038fdd  mov     rdx, r14; Buf2
0x180038fe0  lea     rcx, [rbp+40h+Buf1]; Buf1
0x180038fe4  call    memcmp
0x180038fe9  test    eax, eax
0x180038feb  jnz     loc_180039966
0x180038ff1  mov     r8d, 10h; Size
0x180038ff7  lea     rdx, ?AsgVectorSpaceId@SpaceV6Obsolete@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; Buf2
0x180038ffe  lea     rcx, [rbp+40h+var_48]; Buf1
0x180039002  call    memcmp
0x180039007  test    eax, eax
0x180039009  jnz     loc_180039966
0x18003900f  mov     rcx, rdi
0x180039012  call    ?Close@?$consume_Windows_Foundation_IClosable@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>::Close(void)
0x180039017  lea     rax, qword_180086818
0x18003901e  mov     [rsp+140h+var_120], rax
0x180039023  lock inc cs:qword_180086818
0x18003902b  lea     rbx, aCW1SProductApi_24; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180039032  mov     rcx, cs:??$factory_cache_entry_v@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics4@2345@@impl@winrt@@3U?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics4@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4>
0x180039039  test    rcx, rcx
0x18003903c  jz      short loc_18003907A
0x18003903e  mov     [rbp+40h+var_60], r12
0x180039042  mov     dword ptr [rsp+140h+var_110], 0D6h
0x18003904a  mov     [rsp+140h+var_108], rbx
0x18003904f  mov     rax, [rcx]
0x180039052  lea     rdx, [rbp+40h+var_60]
0x180039056  mov     rax, [rax+30h]
0x18003905a  call    cs:__guard_dispatch_icall_fptr
0x180039060  test    eax, eax
0x180039062  js      loc_180039A27
0x180039068  mov     rax, [rbp+40h+var_60]
0x18003906c  mov     [rbp+40h+lpMem], rax
0x180039070  lock dec cs:qword_180086818
0x180039078  jmp     short loc_18003909D
0x18003907a  lock dec cs:qword_180086818
0x180039082  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1??GetDefault@WorkloadManager@Workloads@Windows@Microsoft@winrt@@SA@XZ@SA@AEBUIWorkloadManagerStatics4@4567@@Z; `winrt::Microsoft::Windows::Workloads::WorkloadManager::GetDefault(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics4 const &)
0x180039089  mov     [rsp+140h+var_110], rax
0x18003908e  lea     r8, [rsp+140h+var_110]
0x180039093  lea     rdx, [rbp+40h+lpMem]
0x180039097  call    ??$call@P6A?AUWorkloadManager@Workloads@Windows@Microsoft@winrt@@AEBUIWorkloadManagerStatics4@2345@@Z@?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics4@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUWorkloadManager@Workloads@Windows@Microsoft@2@AEBUIWorkloadManagerStatics4@4562@@Z@Z
0x18003909c  nop
0x18003909d  mov     dword ptr [rbp+40h+var_60], r12d
0x1800390a1  mov     dword ptr [rsp+140h+var_120], 92h
0x1800390a9  mov     [rsp+140h+var_118], rbx
0x1800390ae  mov     rcx, [rbp+40h+lpMem]
0x1800390b2  test    rcx, rcx
0x1800390b5  jnz     short loc_1800390BC
0x1800390b7  mov     rcx, r12
0x1800390ba  jmp     short loc_1800390DB
0x1800390bc  mov     [rbp+40h+var_80], r12
0x1800390c0  mov     rax, [rcx]
0x1800390c3  lea     r8, [rbp+40h+var_80]
0x1800390c7  lea     rdx, ??$guid_v@UIWorkloadManager2@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager2>
0x1800390ce  mov     rax, [rax]
0x1800390d1  call    cs:__guard_dispatch_icall_fptr
0x1800390d7  mov     rcx, [rbp+40h+var_80]
0x1800390db  mov     [rbp+40h+var_80], rcx
0x1800390df  mov     rax, [rcx]
0x1800390e2  lea     rdx, [rbp+40h+var_60]
0x1800390e6  mov     rax, [rax+40h]
0x1800390ea  call    cs:__guard_dispatch_icall_fptr
0x1800390f0  test    eax, eax
0x1800390f2  js      loc_180039A37
0x1800390f8  lea     rcx, [rbp+40h+var_80]
0x1800390fc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180039101  cmp     dword ptr [rbp+40h+var_60], 3
0x180039105  setz    bl
0x180039108  cmp     [rbp+40h+lpMem], 0
0x18003910d  jz      short loc_180039118
0x18003910f  lea     rcx, [rbp+40h+lpMem]
0x180039113  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180039118  test    bl, bl
0x18003911a  jz      loc_180039471
0x180039120  mov     dword ptr [rbp+40h+var_60], 1
0x180039127  mov     [rbp+40h+lpMem], r12
0x18003912b  mov     dword ptr [rsp+140h+var_120], 521h
0x180039133  lea     r14, aCW1SProductApi_25; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003913a  mov     [rsp+140h+var_118], r14
0x18003913f  mov     rcx, [r15]
0x180039142  mov     rax, [rcx]
0x180039145  lea     rdx, [rbp+40h+lpMem]
0x180039149  mov     rax, [rax+30h]
0x18003914d  call    cs:__guard_dispatch_icall_fptr
0x180039153  test    eax, eax
0x180039155  js      loc_180039A47
0x18003915b  mov     r12, [rbp+40h+lpMem]
0x18003915f  mov     [rsp+140h+var_110], r12
0x180039164  mov     ecx, 48h ; 'H'; Size
0x180039169  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003916e  mov     rbx, rax
0x180039171  mov     [rsp+140h+var_120], rax
0x180039176  movups  xmm0, cs:?VectorSpaceId@SpaceV6@implementation@SemanticSearch@Windows@Microsoft@winrt@@2Uguid@6@B; winrt::guid const winrt::Microsoft::Windows::SemanticSearch::implementation::SpaceV6::VectorSpaceId
0x18003917d  mov     byte ptr [rbp+40h+var_B0], 1
0x180039181  movzx   ecx, [rsp+140h+var_CF]
0x180039186  mov     word ptr [rbp+40h+var_B0+1], cx
0x18003918a  movzx   ecx, [rsp+140h+var_CD]
0x18003918f  mov     byte ptr [rbp+40h+var_B0+3], cl
0x180039192  movaps  [rsp+140h+pExceptionObject], xmm0
0x180039197  mov     eax, [rbp+40h+var_B0]
0x18003919a  mov     [rsp+70h], eax
0x18003919e  lea     r9, [rsp+140h+pExceptionObject]
0x1800391a3  lea     r8, [rbp+40h+var_60]
0x1800391a7  lea     rdx, [rsp+140h+var_110]
0x1800391ac  mov     rcx, rbx
0x1800391af  call    ??0SemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA@AEBUhstring@5@AEBW4IndexCreationDisposition@2345@V?$optional@Uguid@winrt@@@std@@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions::SemanticTextIndexStoreOptions(winrt::hstring const &,winrt::Microsoft::Windows::SemanticSearch::IndexCreationDisposition const &,std::optional<winrt::guid>)
0x1800391b4  lea     rax, ??_7SemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions::`vftable'
0x1800391bb  mov     [rbx], rax
0x1800391be  add     rbx, 10h
0x1800391c2  mov     [rsp+140h+var_110], rbx
0x1800391c7  test    r12, r12
0x1800391ca  jz      short loc_1800391F0
0x1800391cc  mov     esi, 0FFFFFFFFh
0x1800391d1  lock xadd [r12+18h], esi
0x1800391d8  sub     esi, 1
0x1800391db  jnz     short loc_180039224
0x1800391dd  call    WINRT_IMPL_GetProcessHeap
0x1800391e2  mov     rcx, rax; hHeap
0x1800391e5  mov     r8, [rbp+40h+lpMem]; lpMem
0x1800391e9  xor     edx, edx; dwFlags
0x1800391eb  call    WINRT_IMPL_HeapFree
0x1800391f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57696949@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57696949@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57696949> `wil::Feature<__WilFeatureTraits_Feature_57696949>::GetImpl(void)'::`2'::impl
0x1800391f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57696949@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57696949>::__private_IsEnabled(void)
0x1800391fc  test    al, al
0x1800391fe  jz      short loc_180039277
0x180039200  mov     rcx, r15
0x180039203  call    ?QuantizationDisposition@?$consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions5@USemanticTextIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions5<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::QuantizationDisposition(void)
0x180039208  mov     esi, eax
0x18003920a  mov     dword ptr [rsp+140h+var_120], 54Ch
0x180039212  mov     [rsp+140h+var_118], r14
0x180039217  xor     r12d, r12d
0x18003921a  test    rbx, rbx
0x18003921d  jnz     short loc_18003922F
0x18003921f  mov     ecx, r12d
0x180039222  jmp     short loc_180039251
0x180039224  test    esi, esi
0x180039226  jns     short loc_1800391F0
0x180039228  call    cs:__imp_abort
0x18003922f  mov     [rbp+40h+var_80], r12
0x180039233  mov     rax, [rbx]
0x180039236  lea     r8, [rbp+40h+var_80]
0x18003923a  lea     rdx, ??$guid_v@UISemanticTextIndexStoreOptions5@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions5>
0x180039241  mov     rcx, rbx
0x180039244  mov     rax, [rax]
0x180039247  call    cs:__guard_dispatch_icall_fptr
0x18003924d  mov     rcx, [rbp+40h+var_80]
0x180039251  mov     [rbp+40h+var_80], rcx
0x180039255  mov     rax, [rcx]
0x180039258  mov     edx, esi
0x18003925a  mov     rax, [rax+38h]
0x18003925e  call    cs:__guard_dispatch_icall_fptr
0x180039264  test    eax, eax
0x180039266  js      loc_180039A57
0x18003926c  lea     rcx, [rbp+40h+var_80]
0x180039270  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180039275  jmp     short loc_18003927A
0x180039277  xor     r12d, r12d
0x18003927a  mov     rcx, r15
0x18003927d  call    ?ModelsToLoad@?$consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions3@USemanticTextIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStoreOptions3<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>::ModelsToLoad(void)
0x180039282  mov     esi, eax
0x180039284  mov     dword ptr [rsp+140h+var_120], 538h
0x18003928c  mov     [rsp+140h+var_118], r14
0x180039291  test    rbx, rbx
0x180039294  jnz     short loc_18003929B
0x180039296  mov     rcx, r12
0x180039299  jmp     short loc_1800392BD
0x18003929b  mov     [rbp+40h+var_80], r12
0x18003929f  mov     rax, [rbx]
0x1800392a2  lea     r8, [rbp+40h+var_80]
0x1800392a6  lea     rdx, ??$guid_v@UISemanticTextIndexStoreOptions3@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions3>
0x1800392ad  mov     rcx, rbx
0x1800392b0  mov     rax, [rax]
0x1800392b3  call    cs:__guard_dispatch_icall_fptr
0x1800392b9  mov     rcx, [rbp+40h+var_80]
0x1800392bd  mov     [rbp+40h+var_80], rcx
0x1800392c1  mov     rax, [rcx]
0x1800392c4  mov     edx, esi
0x1800392c6  mov     rax, [rax+38h]
0x1800392ca  call    cs:__guard_dispatch_icall_fptr
0x1800392d0  test    eax, eax
0x1800392d2  js      loc_180039A67
0x1800392d8  lea     rcx, [rbp+40h+var_80]
0x1800392dc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800392e1  mov     [rbp+40h+lpMem], r12
0x1800392e5  mov     dword ptr [rsp+140h+var_120], 52Dh
0x1800392ed  mov     [rsp+140h+var_118], r14
0x1800392f2  test    rbx, rbx
  ... truncated ...
```
