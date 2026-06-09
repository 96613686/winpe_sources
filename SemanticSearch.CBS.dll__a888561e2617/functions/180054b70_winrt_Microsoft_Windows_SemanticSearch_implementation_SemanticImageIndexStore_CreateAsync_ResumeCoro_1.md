# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync$_ResumeCoro$1

- ea: `0x180054b70`
- end: `0x180055d58`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync$_ResumeCoro$1`
- size: `4584`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001fa70`
- `0x180054b60`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180009fa0`
- `0x18000d050`
- `0x180014100`
- `0x18001e330`
- `0x18001e9d0`
- `0x18001ee40`
- `0x18001f630`
- `0x18001fc90`
- `0x180021450`
- `0x1800322d0`
- `0x1800454f0`
- `0x18004c070`
- `0x18004c090`
- `0x18004c46c`
- `0x18004c4d8`
- `0x18004c8ac`
- `0x18004c8cc`
- `0x18004df50`
- `0x18004ecf0`
- `0x180051379`
- `0x18005137f`
- `0x180054b70`
- `0x18005e260`
- `0x18005e670`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180055202`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800557b0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180055202`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800557b0`

## string_xrefs

- `0x180054dfd`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800559a8`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync__ResumeCoro_1(
        char *a1)
{
  _QWORD *v2; // rdx
  const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions *Async; // rax
  volatile __int64 *v4; // rdi
  char *v5; // r14
  volatile __int64 *v6; // rdi
  __int64 v7; // rax
  void (__fastcall *v8)(_QWORD, __int64 *, char *); // rax
  int v9; // eax
  __int64 *v10; // rcx
  __int64 **v11; // r15
  _QWORD *v12; // r14
  __int64 v13; // rax
  int v14; // eax
  char *v15; // r13
  char *v16; // rdi
  int v17; // eax
  _QWORD *v18; // r10
  __int64 v19; // rax
  int v20; // eax
  __int128 v21; // xmm0
  char v22; // al
  char v23; // al
  int v24; // eax
  void (__fastcall ***v25)(_QWORD, __int64 *, char *); // r12
  int v26; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v28; // r13d
  __int64 v29; // rax
  int v30; // eax
  __int64 **v31; // r15
  __int64 v32; // rax
  int v33; // eax
  __int64 **v34; // r12
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  _QWORD *v41; // r15
  void (__fastcall ***v42)(_QWORD, __int64 *, char *); // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 **v45; // r12
  __int64 v46; // rax
  int v47; // eax
  char *v48; // rdi
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rax
  int v52; // eax
  signed __int32 v53; // ecx
  HANDLE v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  _QWORD *v57; // rax
  const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions *v58; // rax
  volatile __int64 *v59; // rdi
  char *v60; // r12
  _QWORD *v61; // r14
  __int64 v62; // rax
  volatile __int64 *v63; // rdi
  __int64 v64; // rax
  void (__fastcall *v65)(_QWORD, __int64 *, char *); // rax
  int v66; // eax
  __int128 v67; // xmm0
  _QWORD *v68; // rdi
  void (__fastcall ***v69)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v70; // r14
  _QWORD *v71; // rdi
  _BYTE pExceptionObject[24]; // [rsp+E0h] [rbp-218h] BYREF
  _BYTE v73[24]; // [rsp+F8h] [rbp-200h] BYREF
  __int128 v74; // [rsp+110h] [rbp-1E8h]
  volatile __int64 *v75; // [rsp+120h] [rbp-1D8h]
  volatile __int64 *v76; // [rsp+140h] [rbp-1B8h]
  __int128 v77; // [rsp+160h] [rbp-198h]
  __int128 v78; // [rsp+170h] [rbp-188h]
  _QWORD *v79; // [rsp+180h] [rbp-178h]
  __int64 *v80; // [rsp+188h] [rbp-170h]
  __int64 *v81; // [rsp+190h] [rbp-168h]
  __int64 *v82; // [rsp+198h] [rbp-160h]
  __int64 *v83; // [rsp+1A0h] [rbp-158h]
  LPVOID v84; // [rsp+1A8h] [rbp-150h]
  __int64 v85; // [rsp+1B0h] [rbp-148h]
  __int64 v86; // [rsp+1B8h] [rbp-140h]
  LPVOID v87; // [rsp+1C0h] [rbp-138h]
  __int64 v88; // [rsp+1C8h] [rbp-130h]
  __int64 v89; // [rsp+1D0h] [rbp-128h]
  __int64 v90; // [rsp+1D8h] [rbp-120h]
  __int64 v91; // [rsp+1E0h] [rbp-118h]
  __int64 v92; // [rsp+1E8h] [rbp-110h]
  __int64 v93; // [rsp+1F0h] [rbp-108h]
  void (__fastcall ***v94)(_QWORD, __int64 *, char *); // [rsp+1F8h] [rbp-100h]
  int v95; // [rsp+200h] [rbp-F8h]

  switch ( *((_WORD *)a1 + 72) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_158;
    case 2:
      winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::EnsureRegistered();
      winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::EnsureVectorSpaceId(
        a1 + 152,
        *((_QWORD *)a1 + 17));
      if ( !*((_QWORD *)a1 + 19) || *((_QWORD *)a1 + 19) == 16 )
      {
        if ( __TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
        {
          Init_thread_header(&__TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA);
          if ( __TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA == -1 )
          {
            `winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions>'::`2'::null = 0;
            atexit(winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions_winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions__::_2_::_dynamic_atexit_destructor_for__null__);
            Init_thread_footer(&__TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA);
          }
        }
        v2 = &`winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions>'::`2'::null;
      }
      else
      {
        v2 = (_QWORD *)(*((_QWORD *)a1 + 19) - 16LL + 56);
      }
      Async = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::CreateAsync(
                (const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions *)(a1 + 160),
                v2);
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 102) = 3980;
        *((_QWORD *)a1 + 52) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 408));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)a1 + 21) = 0;
      *((_QWORD *)a1 + 22) = Async;
      *((_QWORD *)a1 + 23) = 0;
      a1[192] = 1;
      *((_WORD *)a1 + 72) = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions const &>::promise_type>(
                              (__int64)(a1 + 168),
                              (__int64)a1) )
        return;
      goto LABEL_21;
    case 4:
LABEL_21:
      v5 = a1 + 200;
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(
        (__int64)(a1 + 168),
        (_QWORD *)a1 + 25);
      if ( *((_QWORD *)a1 + 21) )
      {
        v6 = (volatile __int64 *)*((_QWORD *)a1 + 21);
        v75 = v6;
        while ( _InterlockedExchange64(v6, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 20) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 160);
      *((_OWORD *)a1 + 13) = 0;
      *((_OWORD *)a1 + 14) = 0;
      *((_DWORD *)a1 + 106) = 946;
      *((_QWORD *)a1 + 54) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      if ( *(_QWORD *)v5 )
      {
        *((_QWORD *)a1 + 56) = 0;
        v94 = *(void (__fastcall ****)(_QWORD, __int64 *, char *))v5;
        v8 = **v94;
        v94 = *(void (__fastcall ****)(_QWORD, __int64 *, char *))v5;
        v8(
          v94,
          winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex3>,
          a1 + 448);
        v7 = *((_QWORD *)a1 + 56);
        v85 = v7;
      }
      else
      {
        v7 = 0;
      }
      *((_QWORD *)a1 + 55) = v7;
      v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v7 + 48LL))(*((_QWORD *)a1 + 55), a1 + 208);
      if ( v9 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v9, a1 + 424);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 440);
      if ( memcmp(
             a1 + 208,
             `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync'::`2'::florenceD3Compliant,
             0x10u) )
      {
        goto LABEL_145;
      }
      v10 = `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync'::`5'::florenceD3Obsolete;
      do
      {
        if ( *v10 == *((_QWORD *)a1 + 28) && v10[1] == *((_QWORD *)a1 + 29) )
          break;
        v10 += 2;
      }
      while ( v10 != `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync'::`2'::florenceD3Compliant );
      if ( `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync'::`2'::florenceD3Compliant == v10 )
        goto LABEL_145;
      winrt::impl::consume_Windows_Foundation_IClosable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>::Close((void (__fastcall ****)(_QWORD, __int64 *, __int64 *))a1 + 25);
      if ( *(_QWORD *)v5 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
      *(_QWORD *)v5 = 0;
      v11 = (__int64 **)(a1 + 544);
      *((_QWORD *)a1 + 68) = 0;
      *((_DWORD *)a1 + 132) = 783;
      *((_QWORD *)a1 + 67) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      v12 = a1 + 152;
      if ( *((_QWORD *)a1 + 19) )
      {
        *((_QWORD *)a1 + 70) = 0;
        (**(void (__fastcall ***)(_QWORD, __int64 *, char *))*v12)(
          *v12,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions4>,
          a1 + 560);
        v13 = *((_QWORD *)a1 + 70);
        v86 = v13;
      }
      else
      {
        v13 = 0;
      }
      *((_QWORD *)a1 + 69) = v13;
      v14 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v13 + 48LL))(*((_QWORD *)a1 + 69), a1 + 544);
      if ( v14 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v14, a1 + 528);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 552);
      v15 = a1 + 240;
      *((_QWORD *)a1 + 30) = *v11;
      *((_DWORD *)a1 + 62) = 1;
      v16 = a1 + 584;
      *((_QWORD *)a1 + 73) = 0;
      *((_DWORD *)a1 + 142) = 755;
      *((_QWORD *)a1 + 72) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      v17 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v12 + 48LL))(*v12, a1 + 584);
      if ( v17 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v17, a1 + 568);
      }
      *((_QWORD *)a1 + 32) = *(_QWORD *)v16;
      v18 = operator new(0x48u);
      v79 = v18;
      *((_QWORD *)a1 + 75) = v18;
      if ( *v11 )
      {
        *((_OWORD *)a1 + 42) = 0;
        *((_DWORD *)a1 + 172) = 629;
        *((_QWORD *)a1 + 87) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        v80 = *v11;
        v19 = *v80;
        v80 = *v11;
        v20 = (*(__int64 (__fastcall **)(__int64 *, char *))(v19 + 48))(v80, a1 + 672);
        if ( v20 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v20, a1 + 688);
        }
        v21 = *((_OWORD *)a1 + 42);
        v74 = v21;
        v22 = 1;
        v18 = v79;
        v15 = a1 + 240;
      }
      else
      {
        v21 = *((_OWORD *)a1 + 38);
        v22 = 0;
      }
      *((_OWORD *)a1 + 40) = v21;
      a1[656] = v22;
      v23 = a1[627];
      *(_WORD *)(a1 + 657) = *(_WORD *)(a1 + 625);
      a1[659] = v23;
      v24 = *((_DWORD *)a1 + 164);
      *((_OWORD *)a1 + 44) = *((_OWORD *)a1 + 40);
      *((_DWORD *)a1 + 180) = v24;
      winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions::SemanticImageIndexStoreOptions(
        v18,
        (__int64 *)a1 + 32,
        a1 + 248,
        (__int64)(a1 + 704));
      **((_QWORD **)a1 + 75) = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions>::`vftable';
      v25 = (void (__fastcall ***)(_QWORD, __int64 *, char *))(*((_QWORD *)a1 + 75) + 16LL);
      *((_QWORD *)a1 + 74) = v25;
      *((_QWORD *)a1 + 33) = v25;
      if ( *(_QWORD *)v16 )
      {
        v26 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v16 + 24LL));
        if ( v26 )
        {
          if ( v26 < 0 )
            abort();
        }
        else
        {
          v87 = *(LPVOID *)v16;
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v87);
        }
      }
      v80 = *v11;
      if ( v80 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v15);
      v28 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndexStoreOptions3<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions>::ModelsToLoad(a1 + 152);
      *((_DWORD *)a1 + 114) = 778;
      *((_QWORD *)a1 + 58) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      if ( v25 )
      {
        *((_QWORD *)a1 + 61) = 0;
        (**v25)(
          v25,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions3>,
          a1 + 488);
        v29 = *((_QWORD *)a1 + 61);
        v88 = v29;
      }
      else
      {
        v29 = 0;
      }
      *((_QWORD *)a1 + 59) = v29;
      v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v29 + 56LL))(*((_QWORD *)a1 + 59), v28);
      if ( v30 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v30, a1 + 456);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 472);
      v31 = (__int64 **)(a1 + 944);
      *((_QWORD *)a1 + 118) = 0;
      *((_DWORD *)a1 + 232) = 767;
      *((_QWORD *)a1 + 117) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gene"
                              "rated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      if ( v25 )
      {
        *((_QWORD *)a1 + 120) = 0;
        (**v25)(
          v25,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions2>,
          a1 + 960);
        v32 = *((_QWORD *)a1 + 120);
        v89 = v32;
      }
      else
      {
        v32 = 0;
      }
      *((_QWORD *)a1 + 119) = v32;
      v33 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v32 + 48LL))(*((_QWORD *)a1 + 119), a1 + 944);
      if ( v33 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v33, a1 + 928);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 952);
      *((_QWORD *)a1 + 34) = *v31;
      v34 = (__int64 **)(a1 + 904);
      *((_QWORD *)a1 + 113) = 0;
      *((_DWORD *)a1 + 222) = 767;
      *((_QWORD *)a1 + 112) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gene"
                              "rated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      if ( *v12 )
      {
        *((_QWORD *)a1 + 115) = 0;
        (**(void (__fastcall ***)(_QWORD, __int64 *, char *))*v12)(
          *v12,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions2>,
          a1 + 920);
        v35 = *((_QWORD *)a1 + 115);
        v90 = v35;
      }
      else
      {
        v35 = 0;
      }
      *((_QWORD *)a1 + 114) = v35;
      v36 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v35 + 48LL))(*((_QWORD *)a1 + 114), a1 + 904);
      if ( v36 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v36, a1 + 888);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 912);
      *((_QWORD *)a1 + 35) = *v34;
      *((_DWORD *)a1 + 206) = 0;
      *((_DWORD *)a1 + 208) = 359;
      *((_QWORD *)a1 + 105) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gene"
                              "rated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      v81 = *v34;
      v37 = *v81;
      v81 = *v34;
      v38 = (*(__int64 (**)(void))(v37 + 48))();
      if ( v38 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v38, a1 + 832);
      }
      *((_DWORD *)a1 + 202) = 364;
      *((_QWORD *)a1 + 102) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gene"
                              "rated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      v82 = *v31;
      v39 = *v82;
      v95 = *((_DWORD *)a1 + 206);
      v82 = *v31;
      v40 = (*(__int64 (**)(void))(v39 + 56))();
      if ( v40 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v40, a1 + 808);
      }
      v81 = *v34;
      if ( v81 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 280);
      v82 = *v31;
      if ( v82 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 272);
      v41 = a1 + 848;
      *((_QWORD *)a1 + 106) = 0;
      *((_DWORD *)a1 + 214) = 767;
      *((_QWORD *)a1 + 108) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gene"
                              "rated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      v42 = (void (__fastcall ***)(_QWORD, __int64 *, char *))*((_QWORD *)a1 + 74);
      if ( v42 )
      {
        *((_QWORD *)a1 + 110) = 0;
        (**v42)(
          v42,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions2>,
          a1 + 880);
        v43 = *((_QWORD *)a1 + 110);
        v91 = v43;
      }
      else
      {
        v43 = 0;
      }
      *((_QWORD *)a1 + 109) = v43;
      v44 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v43 + 48LL))(*((_QWORD *)a1 + 109), a1 + 848);
      if ( v44 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v44, a1 + 856);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 872);
      *((_QWORD *)a1 + 36) = *v41;
      v45 = (__int64 **)(a1 + 480);
      *((_QWORD *)a1 + 60) = 0;
      *((_DWORD *)a1 + 124) = 767;
      *((_QWORD *)a1 + 63) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      if ( *v12 )
      {
        *((_QWORD *)a1 + 65) = 0;
        (**(void (__fastcall ***)(_QWORD, __int64 *, char *))*v12)(
          *v12,
          &winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions2>,
          a1 + 520);
        v46 = *((_QWORD *)a1 + 65);
        v92 = v46;
      }
      else
      {
        v46 = 0;
      }
      *((_QWORD *)a1 + 64) = v46;
      v47 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v46 + 48LL))(*((_QWORD *)a1 + 64), a1 + 480);
      if ( v47 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v47, a1 + 496);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 512);
      *((_QWORD *)a1 + 37) = *v45;
      v48 = a1 + 736;
      *((_QWORD *)a1 + 92) = 0;
      *((_DWORD *)a1 + 188) = 369;
      *((_QWORD *)a1 + 95) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      v83 = *v45;
      v49 = *v83;
      v83 = *v45;
      v50 = (*(__int64 (__fastcall **)(__int64 *, char *))(v49 + 64))(v83, a1 + 736);
      if ( v50 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v50, a1 + 752);
      }
      *((_QWORD *)a1 + 38) = *(_QWORD *)v48;
      *((_DWORD *)a1 + 192) = 374;
      *((_QWORD *)a1 + 97) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Windows.SemanticSearch.h";
      v79 = (_QWORD *)*v41;
      v51 = *v79;
      v84 = *(LPVOID *)v48;
      v79 = (_QWORD *)*v41;
      v52 = (*(__int64 (**)(void))(v51 + 72))();
      if ( v52 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v52, a1 + 768);
      }
      if ( *(_QWORD *)v48 )
      {
        v53 = _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v48 + 24LL), 0xFFFFFFFF);
        if ( v53 == 1 )
        {
          v84 = *(LPVOID *)v48;
          v54 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v54, 0, v84);
        }
        else if ( v53 - 1 < 0 )
        {
          abort();
        }
      }
      v83 = *v45;
      if ( v83 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 296);
      v79 = (_QWORD *)*v41;
      if ( v79 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 288);
      v55 = *((_QWORD *)a1 + 74);
      if ( v55 && (v56 = v55 - 16) != 0 )
      {
        v57 = (_QWORD *)(v56 + 56);
      }
      else
      {
        if ( __TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
        {
          Init_thread_header(&__TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA);
          if ( __TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA == -1 )
          {
            `winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions>'::`2'::null = 0;
            atexit(winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions_winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions__::_2_::_dynamic_atexit_destructor_for__null__);
            Init_thread_footer(&__TSS0__1____GetAsgImpl_USemanticImageIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticImageIndexStoreOptions_2345__Z_4HA);
          }
        }
        v57 = &`winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions>'::`2'::null;
      }
      v58 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::CreateAsync(
              (const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions *)(a1 + 312),
              v57);
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 198) = 3980;
        *((_QWORD *)a1 + 100) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Ge"
                                "nerated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v73,
          (const struct winrt::impl::slim_source_location *)(a1 + 792));
        throw (winrt::hresult_canceled *)v73;
      }
      *((_QWORD *)a1 + 40) = 0;
      *((_QWORD *)a1 + 41) = v58;
      *((_QWORD *)a1 + 42) = 0;
      a1[344] = 1;
      *((_WORD *)a1 + 72) = 6;
      if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions const &>::promise_type>(
                               (__int64)(a1 + 320),
                               (__int64)a1) )
      {
LABEL_127:
        v60 = (char *)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(
                        (__int64)(a1 + 320),
                        (_QWORD *)a1 + 44);
        v61 = a1 + 200;
        if ( a1 + 200 != v60 )
        {
          if ( *v61 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
          v62 = *(_QWORD *)v60;
          *(_QWORD *)v60 = 0;
          *v61 = v62;
        }
        if ( *((_QWORD *)a1 + 44) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 352);
        if ( *((_QWORD *)a1 + 40) )
        {
          v63 = (volatile __int64 *)*((_QWORD *)a1 + 40);
          v76 = v63;
          while ( _InterlockedExchange64(v63, 0) == 1 )
            Thrd_yield();
        }
        if ( *((_QWORD *)a1 + 39) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 312);
        *(_OWORD *)(a1 + 360) = 0;
        *(_OWORD *)(a1 + 376) = 0;
        *((_DWORD *)a1 + 242) = 946;
        *((_QWORD *)a1 + 122) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Ge"
                                "nerated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
        if ( *v61 )
        {
          *((_QWORD *)a1 + 124) = 0;
          v94 = (void (__fastcall ***)(_QWORD, __int64 *, char *))*((_QWORD *)a1 + 25);
          v65 = **v94;
          v94 = (void (__fastcall ***)(_QWORD, __int64 *, char *))*((_QWORD *)a1 + 25);
          v65(
            v94,
            winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex3>,
            a1 + 992);
          v64 = *((_QWORD *)a1 + 124);
          v93 = v64;
        }
        else
        {
          v64 = 0;
        }
        *((_QWORD *)a1 + 123) = v64;
        v66 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)v64 + 48LL))(*((_QWORD *)a1 + 123), a1 + 360);
        if ( v66 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v66, a1 + 968);
        }
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 984);
        v77 = *(_OWORD *)(a1 + 360);
        v78 = *(_OWORD *)(a1 + 376);
        v67 = v78;
        *((_OWORD *)a1 + 13) = v77;
        *((_OWORD *)a1 + 14) = v67;
        if ( *((_QWORD *)a1 + 74) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 264);
LABEL_145:
        v68 = operator new(0x70u);
        v68[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStore>::`vftable';
        v68[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStore2>::`vftable';
        v68[4] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore,winrt::Windows::Foundation::IClosable>::`vftable';
        v68[5] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex>::`vftable';
        v68[6] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndex>::`vftable';
        v68[7] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex2>::`vftable';
        v68[8] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex2>::`vftable';
        v68[9] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex3>::`vftable';
        v68[10] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex3>::`vftable';
        v68[11] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex4>::`vftable';
        v68[12] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndex4>::`vftable';
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        v68[1] = 1;
        *v68 = &winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::`vftable';
        v94 = (void (__fastcall ***)(_QWORD, __int64 *, char *))*((_QWORD *)a1 + 25);
        v69 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v94;
        v68[13] = v94;
        if ( v69 )
          ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v69)[1])(v69);
        *v68 = &winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::`vftable';
        v70 = v68 + 2;
        *((_QWORD *)a1 + 49) = v68 + 2;
        v71 = a1 + 120;
        if ( a1 + 120 == a1 + 392 )
        {
          if ( v70 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 392);
        }
        else
        {
          if ( *v71 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
          *v71 = v70;
        }
        v94 = (void (__fastcall ***)(_QWORD, __int64 *, char *))*((_QWORD *)a1 + 25);
        if ( v94 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
        if ( *((_QWORD *)a1 + 19) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
        *((_QWORD *)a1 + 50) = a1 + 16;
        *((_WORD *)a1 + 72) = 0;
        *(_QWORD *)a1 = 0;
        if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 50) )
        {
LABEL_158:
          std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
          if ( *((_WORD *)a1 + 73) )
            operator delete(a1);
        }
      }
      return;
    case 5:
      if ( *((_QWORD *)a1 + 21) )
      {
        v4 = (volatile __int64 *)*((_QWORD *)a1 + 21);
        v75 = v4;
        while ( _InterlockedExchange64(v4, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 20) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 160);
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
      goto LABEL_158;
    case 6:
      goto LABEL_127;
    case 7:
      if ( *((_QWORD *)a1 + 40) )
      {
        v59 = (volatile __int64 *)*((_QWORD *)a1 + 40);
        v76 = v59;
        while ( _InterlockedExchange64(v59, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 39) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 312);
      if ( *((_QWORD *)a1 + 74) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 264);
      v94 = (void (__fastcall ***)(_QWORD, __int64 *, char *))*((_QWORD *)a1 + 25);
      if ( v94 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
      goto LABEL_158;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180054b70  mov     r11, rsp
0x180054b73  mov     [r11+10h], rbx
0x180054b77  mov     [r11+18h], rsi
0x180054b7b  mov     [r11+8], rcx
0x180054b7f  push    rdi
0x180054b80  push    r12
0x180054b82  push    r13
0x180054b84  push    r14
0x180054b86  push    r15
0x180054b88  sub     rsp, 2D0h
0x180054b8f  mov     rax, cs:__security_cookie
0x180054b96  xor     rax, rsp
0x180054b99  mov     [rsp+2F8h+var_38], rax
0x180054ba1  mov     rbx, rcx
0x180054ba4  mov     [rsp+2F8h+var_2C0], rcx
0x180054ba9  movzx   eax, word ptr [rbx+90h]
0x180054bb0  mov     [rsp+2F8h+var_2D0], ax
0x180054bb5  inc     ax; switch 9 cases
0x180054bb8  cmp     ax, 8
0x180054bbc  ja      def_180054BD7; jumptable 0000000180054BD7 default case, case 0
0x180054bc2  movsx   rax, ax
0x180054bc6  lea     rdx, cs:180000000h
0x180054bcd  mov     ecx, ds:(jpt_180054BD7 - 180000000h)[rdx+rax*4]
0x180054bd4  add     rcx, rdx
0x180054bd7  jmp     rcx; switch jump
0x180054bd9  jmp     loc_180055CE0; jumptable 0000000180054BD7 case 3
0x180054bde  xor     esi, esi; jumptable 0000000180054BD7 case 2
0x180054be0  call    ?EnsureRegistered@AiFabricModelFactories@implementation@SemanticSearch@Windows@Microsoft@winrt@@SAXXZ; winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::EnsureRegistered(void)
0x180054be5  mov     rdx, [rbx+88h]
0x180054bec  lea     rcx, [rbx+98h]
0x180054bf3  call    ?EnsureVectorSpaceId@SemanticImageIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@SA?AUSemanticImageIndexStoreOptions@3456@AEBU73456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::EnsureVectorSpaceId(winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions const &)
0x180054bf8  nop
0x180054bf9  cmp     [rbx+98h], rsi
0x180054c00  jz      short loc_180054C15
0x180054c02  mov     rax, [rbx+98h]
0x180054c09  sub     rax, 10h
0x180054c0d  jz      short loc_180054C15
0x180054c0f  lea     rdx, [rax+38h]
0x180054c13  jmp     short loc_180054C73
0x180054c15  mov     edx, cs:_tls_index
0x180054c1b  mov     rax, gs:58h
0x180054c24  mov     edi, 4
0x180054c29  mov     rax, [rax+rdx*8]
0x180054c2d  mov     ecx, [rdi+rax]
0x180054c30  cmp     cs:?$TSS0@?1???$GetAsgImpl@USemanticImageIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticImageIndexStoreOptions@2345@@Z@4HA, ecx
0x180054c36  jle     short loc_180054C6C
0x180054c38  lea     rcx, ?$TSS0@?1???$GetAsgImpl@USemanticImageIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticImageIndexStoreOptions@2345@@Z@4HA
0x180054c3f  call    _Init_thread_header
0x180054c44  cmp     cs:?$TSS0@?1???$GetAsgImpl@USemanticImageIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticImageIndexStoreOptions@2345@@Z@4HA, 0FFFFFFFFh
0x180054c4b  jnz     short loc_180054C6C
0x180054c4d  mov     cs:?null@?1???$GetAsgImpl@USemanticImageIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticImageIndexStoreOptions@2345@@Z@4U6Compatibility@AiFabric@SemanticIndex@Asg@45@B, rsi
0x180054c54  lea     rcx, _winrt__Microsoft__Windows__SemanticSearch__implementation__GetAsgImpl_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticImageIndexStoreOptions_winrt__Microsoft__Windows__SemanticSearch__SemanticImageIndexStoreOptions_____2____dynamic_atexit_destructor_for__null__; void (__cdecl *)()
0x180054c5b  call    atexit
0x180054c60  lea     rcx, ?$TSS0@?1???$GetAsgImpl@USemanticImageIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticImageIndexStoreOptions@2345@@Z@4HA
0x180054c67  call    _Init_thread_footer
0x180054c6c  lea     rdx, ?null@?1???$GetAsgImpl@USemanticImageIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticImageIndexStoreOptions@2345@@Z@4U6Compatibility@AiFabric@SemanticIndex@Asg@45@B
0x180054c73  lea     rcx, [rbx+0A0h]; struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions *
0x180054c7a  call    ?CreateAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::CreateAsync(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions const &)
0x180054c7f  nop
0x180054c80  mov     ecx, [rbx+70h]
0x180054c83  cmp     ecx, 2
0x180054c86  jnz     short loc_180054CC4
0x180054c88  lea     rdx, [rbx+198h]; struct winrt::impl::slim_source_location *
0x180054c8f  mov     dword ptr [rdx], 0F8Ch
0x180054c95  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180054c9c  mov     [rbx+1A0h], rax
0x180054ca3  lea     rcx, [rsp+2F8h+pExceptionObject]; this
0x180054cab  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180054cb0  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180054cb7  lea     rcx, [rsp+2F8h+pExceptionObject]; pExceptionObject
0x180054cbf  call    _CxxThrowException
0x180054cc4  lea     rcx, [rbx+0A8h]
0x180054ccb  mov     [rcx], rsi
0x180054cce  mov     [rbx+0B0h], rax
0x180054cd5  mov     [rbx+0B8h], rsi
0x180054cdc  mov     byte ptr [rbx+0C0h], 1
0x180054ce3  mov     eax, 4
0x180054ce8  mov     [rbx+90h], ax
0x180054cef  mov     rdx, rbx
0x180054cf2  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEBUSemanticImageIndexStoreOptions@SemanticSearch@3Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperation@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEBUSemanticImageIndexStoreOptions@SemanticSearch@3Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions const &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions const &>::promise_type>)
0x180054cf7  test    al, al
0x180054cf9  jz      loc_180054D7C
0x180054cff  jmp     loc_180055D03
0x180054d04  cmp     qword ptr [rbx+0A8h], 0; jumptable 0000000180054BD7 case 5
0x180054d0c  jz      short loc_180054D41
0x180054d0e  mov     rdi, [rbx+0A8h]
0x180054d15  mov     rcx, rdi
0x180054d18  mov     [rsp+2F8h+var_1D8], rcx
0x180054d20  xor     esi, esi
0x180054d22  mov     eax, esi
0x180054d24  xchg    rax, [rcx]
0x180054d27  cmp     rax, 1
0x180054d2b  jnz     short loc_180054D41
0x180054d2d  nop     dword ptr [rax]
0x180054d30  call    _Thrd_yield
0x180054d35  mov     rax, rsi
0x180054d38  xchg    rax, [rdi]
0x180054d3b  cmp     rax, 1
0x180054d3f  jz      short loc_180054D30
0x180054d41  lea     rcx, [rbx+0A0h]
0x180054d48  mov     rax, [rcx]
0x180054d4b  mov     [rsp+2F8h+var_280], rax
0x180054d50  test    rax, rax
0x180054d53  jz      short loc_180054D5B
0x180054d55  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054d5a  nop
0x180054d5b  lea     rcx, [rbx+98h]
0x180054d62  mov     rax, [rcx]
0x180054d65  mov     [rsp+2F8h+var_2D8], rax
0x180054d6a  test    rax, rax
0x180054d6d  jz      short loc_180054D75
0x180054d6f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054d74  nop
0x180054d75  jmp     loc_180055CE0; jumptable 0000000180054BD7 cases -1,1
0x180054d7a  xor     esi, esi; jumptable 0000000180054BD7 case 4
0x180054d7c  lea     r14, [rbx+0C8h]
0x180054d83  mov     rdx, r14
0x180054d86  lea     rcx, [rbx+0A8h]
0x180054d8d  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,1>::await_resume(void)
0x180054d92  nop
0x180054d93  cmp     qword ptr [rbx+0A8h], 0
0x180054d9b  jz      short loc_180054DC9
0x180054d9d  mov     rdi, [rbx+0A8h]
0x180054da4  mov     [rsp+2F8h+var_1D8], rdi
0x180054dac  mov     rcx, rsi
0x180054daf  xchg    rcx, [rdi]
0x180054db2  cmp     rcx, 1
0x180054db6  jnz     short loc_180054DC9
0x180054db8  call    _Thrd_yield
0x180054dbd  mov     rax, rsi
0x180054dc0  xchg    rax, [rdi]
0x180054dc3  cmp     rax, 1
0x180054dc7  jz      short loc_180054DB8
0x180054dc9  lea     rcx, [rbx+0A0h]
0x180054dd0  mov     rax, [rcx]
0x180054dd3  mov     [rsp+2F8h+var_280], rax
0x180054dd8  test    rax, rax
0x180054ddb  jz      short loc_180054DE2
0x180054ddd  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054de2  xorps   xmm0, xmm0
0x180054de5  movups  xmmword ptr [rbx+0D0h], xmm0
0x180054dec  movups  xmmword ptr [rbx+0E0h], xmm0
0x180054df3  mov     dword ptr [rbx+1A8h], 3B2h
0x180054dfd  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180054e04  mov     [rbx+1B0h], rax
0x180054e0b  cmp     qword ptr [r14], 0
0x180054e0f  jnz     short loc_180054E16
0x180054e11  mov     rax, rsi
0x180054e14  jmp     short loc_180054E5C
0x180054e16  mov     [rbx+1C0h], rsi
0x180054e1d  mov     rax, [r14]
0x180054e20  mov     [rsp+2F8h+var_100], rax
0x180054e28  mov     rcx, [rax]
0x180054e2b  mov     rax, [rcx]
0x180054e2e  mov     rcx, [r14]
0x180054e31  mov     [rsp+2F8h+var_100], rcx
0x180054e39  lea     r8, [rbx+1C0h]
0x180054e40  lea     rdx, ??$guid_v@UISemanticIndex3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex3>
0x180054e47  call    cs:__guard_dispatch_icall_fptr
0x180054e4d  mov     rax, [rbx+1C0h]
0x180054e54  mov     [rsp+2F8h+var_148], rax
0x180054e5c  mov     [rbx+1B8h], rax
0x180054e63  mov     [rsp+2F8h+var_278], rax
0x180054e6b  mov     rcx, [rax]
0x180054e6e  mov     rax, [rcx+30h]
0x180054e72  mov     rcx, [rbx+1B8h]
0x180054e79  mov     [rsp+2F8h+var_278], rcx
0x180054e81  lea     rdx, [rbx+0D0h]
0x180054e88  call    cs:__guard_dispatch_icall_fptr
0x180054e8e  test    eax, eax
0x180054e90  jns     short loc_180054EA4
0x180054e92  lfence
0x180054e95  lea     rdx, [rbx+1A8h]
0x180054e9c  mov     ecx, eax
0x180054e9e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180054ea4  lea     rcx, [rbx+1B8h]
0x180054eab  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054eb0  mov     r8d, 10h; Size
0x180054eb6  lea     rdx, ?florenceD3Compliant@?1??CreateAsync@SemanticImageIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@SA?AU?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@57@AEBUSemanticImageIndexStoreOptions@4567@@Z@4Uguid@7@B; Buf2
0x180054ebd  lea     rcx, [rbx+0D0h]; Buf1
0x180054ec4  call    memcmp
0x180054ec9  test    eax, eax
0x180054ecb  jnz     loc_180055B65
0x180054ed1  lea     rcx, ?florenceD3Obsolete@?4??CreateAsync@SemanticImageIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@SA?AU?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@57@AEBUSemanticImageIndexStoreOptions@4567@@Z@4V?$array@Uguid@winrt@@$03@std@@B; std::array<winrt::guid,4> const `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync(winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions const &)'::`5'::florenceD3Obsolete
0x180054ed8  lea     rdx, ?florenceD3Compliant@?1??CreateAsync@SemanticImageIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@SA?AU?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@57@AEBUSemanticImageIndexStoreOptions@4567@@Z@4Uguid@7@B; winrt::guid const `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::CreateAsync(winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStoreOptions const &)'::`2'::florenceD3Compliant
0x180054edf  nop
0x180054ee0  mov     rax, [rcx]
0x180054ee3  cmp     rax, [rbx+0E0h]
0x180054eea  jnz     short loc_180054EF9
0x180054eec  mov     rax, [rcx+8]
0x180054ef0  cmp     rax, [rbx+0E8h]
0x180054ef7  jz      short loc_180054F02
0x180054ef9  add     rcx, 10h
0x180054efd  cmp     rcx, rdx
0x180054f00  jnz     short loc_180054EE0
0x180054f02  cmp     rdx, rcx
0x180054f05  jz      loc_180055B65
0x180054f0b  mov     rcx, r14
0x180054f0e  call    ?Close@?$consume_Windows_Foundation_IClosable@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>::Close(void)
0x180054f13  cmp     qword ptr [r14], 0
0x180054f17  jz      short loc_180054F21
0x180054f19  mov     rcx, r14
0x180054f1c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054f21  mov     [r14], rsi
0x180054f24  lea     r15, [rbx+220h]
0x180054f2b  mov     [r15], rsi
0x180054f2e  mov     dword ptr [rbx+210h], 30Fh
0x180054f38  lea     rax, aCW1SProductApi_25; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180054f3f  mov     [rbx+218h], rax
0x180054f46  lea     r14, [rbx+98h]
0x180054f4d  cmp     qword ptr [r14], 0
0x180054f51  jnz     short loc_180054F58
0x180054f53  mov     rax, rsi
0x180054f56  jmp     short loc_180054F98
0x180054f58  mov     [rbx+230h], rsi
0x180054f5f  mov     rax, [r14]
0x180054f62  mov     [rsp+2F8h+var_2D8], rax
0x180054f67  mov     rcx, [rax]
0x180054f6a  mov     rax, [rcx]
0x180054f6d  mov     rcx, [r14]
0x180054f70  mov     [rsp+2F8h+var_2D8], rcx
0x180054f75  lea     r8, [rbx+230h]
0x180054f7c  lea     rdx, ??$guid_v@UISemanticImageIndexStoreOptions4@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions4>
0x180054f83  call    cs:__guard_dispatch_icall_fptr
0x180054f89  mov     rax, [rbx+230h]
0x180054f90  mov     [rsp+2F8h+var_140], rax
0x180054f98  mov     [rbx+228h], rax
0x180054f9f  mov     [rsp+2F8h+var_270], rax
0x180054fa7  mov     rcx, [rax]
0x180054faa  mov     rax, [rcx+30h]
0x180054fae  mov     rcx, [rbx+228h]
0x180054fb5  mov     [rsp+2F8h+var_270], rcx
0x180054fbd  mov     rdx, r15
0x180054fc0  call    cs:__guard_dispatch_icall_fptr
0x180054fc6  test    eax, eax
0x180054fc8  jns     short loc_180054FDC
0x180054fca  lfence
0x180054fcd  lea     rdx, [rbx+210h]
0x180054fd4  mov     ecx, eax
0x180054fd6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180054fdc  lea     rcx, [rbx+228h]
0x180054fe3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180054fe8  lea     r13, [rbx+0F0h]
0x180054fef  mov     rax, [r15]
0x180054ff2  mov     [r13+0], rax
0x180054ff6  mov     dword ptr [rbx+0F8h], 1
0x180055000  lea     rdi, [rbx+248h]
0x180055007  mov     [rdi], rsi
0x18005500a  mov     dword ptr [rbx+238h], 2F3h
0x180055014  lea     rax, aCW1SProductApi_25; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005501b  mov     [rbx+240h], rax
0x180055022  mov     r8, [r14]
0x180055025  mov     [rsp+2F8h+var_2D8], r8
0x18005502a  mov     rcx, [r8]
0x18005502d  mov     rax, [rcx+30h]
0x180055031  mov     rdx, rdi
0x180055034  mov     rcx, r8
0x180055037  call    cs:__guard_dispatch_icall_fptr
0x18005503d  test    eax, eax
0x18005503f  jns     short loc_180055052
0x180055041  lfence
0x180055044  lea     rdx, [rbx+238h]
0x18005504b  mov     ecx, eax
0x18005504d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180055052  mov     rax, [rdi]
0x180055055  mov     [rbx+100h], rax
0x18005505c  mov     ecx, 48h ; 'H'; Size
0x180055061  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055066  mov     r10, rax
0x180055069  mov     [rsp+2F8h+var_178], rax
0x180055071  mov     [rbx+258h], rax
0x180055078  cmp     qword ptr [r15], 0
0x18005507c  jz      loc_180055105
0x180055082  xorps   xmm0, xmm0
0x180055085  movups  xmmword ptr [rbx+2A0h], xmm0
0x18005508c  mov     dword ptr [rbx+2B0h], 275h
0x180055096  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005509d  mov     [rbx+2B8h], rax
0x1800550a4  mov     rax, [r15]
0x1800550a7  mov     [rsp+2F8h+var_170], rax
0x1800550af  mov     rax, [rax]
0x1800550b2  mov     rcx, [r15]
0x1800550b5  mov     [rsp+2F8h+var_170], rcx
0x1800550bd  lea     rdx, [rbx+2A0h]
0x1800550c4  mov     rax, [rax+30h]
0x1800550c8  call    cs:__guard_dispatch_icall_fptr
0x1800550ce  test    eax, eax
0x1800550d0  jns     short loc_1800550E3
0x1800550d2  lfence
0x1800550d5  lea     rdx, [rbx+2B0h]
0x1800550dc  mov     ecx, eax
0x1800550de  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800550e3  movups  xmm0, xmmword ptr [rbx+2A0h]
0x1800550ea  movups  [rsp+2F8h+var_1E8], xmm0
0x1800550f2  mov     al, 1
0x1800550f4  mov     r10, [rsp+2F8h+var_178]
0x1800550fc  lea     r13, [rbx+0F0h]
0x180055103  jmp     short loc_180055116
0x180055105  movups  xmm0, xmmword ptr [rbx+260h]
0x18005510c  movups  [rsp+2F8h+var_268], xmm0
  ... truncated ...
```
