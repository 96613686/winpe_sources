# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceCoreAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___

- ea: `0x1802376b0`
- end: `0x180237d1c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceCoreAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___`
- size: `1644`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180054490`
- `0x1802376a0`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x18000b2a0`
- `0x180020670`
- `0x18002f8e0`
- `0x180030a30`
- `0x180046940`
- `0x180047520`
- `0x1800475c0`
- `0x180054640`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d1e70`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x1802376b0`
- `0x180242120`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180237b73`
- `KERNEL32!SetEvent` at `0x180237b73`

## string_xrefs

- `0x180237b85`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x1802379b2`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180237ab6`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180237ac4`: `struct winrt::Windows::Foundation::IAsyncAction __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struc`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceCoreAsync__ResumeCoro_1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___(
        __int64 a1)
{
  _QWORD *v2; // rdx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rcx
  _DWORD *v6; // r15
  _QWORD *v7; // r13
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  _QWORD *v10; // r12
  __int64 v11; // rax
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rcx
  signed __int64 v15; // rax
  signed __int64 v16; // rtt
  __int64 v17; // rcx
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rsi
  _BYTE **v21; // rbx
  _Mtx_t *v22; // r15
  __int64 v23; // r8
  _QWORD *v24; // r12
  const char *v25; // r9
  volatile signed __int32 *v26; // rbx
  _BYTE pExceptionObject[144]; // [rsp+58h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 160) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_60;
    case 2:
      v2 = (_QWORD *)(a1 + 176);
      *(_QWORD *)(a1 + 176) = 0;
      *(_QWORD *)(a1 + 184) = 0;
      v3 = *(_QWORD *)(a1 + 152);
      if ( v3 )
        _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
      v4 = *(_QWORD *)(a1 + 144);
      v5 = *(_QWORD *)(a1 + 152);
      *(_QWORD *)(a1 + 320) = v2;
      *(_QWORD *)(a1 + 304) = v4;
      *(_QWORD *)(a1 + 312) = v5;
      *v2 = 0;
      *(_QWORD *)(a1 + 184) = 0;
      *(_QWORD *)(a1 + 328) = a1 + 304;
      v6 = operator new(0x20u);
      v6[2] = 1;
      *((_QWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 3) = 0;
      *((_QWORD *)v6 + 2) = *(_QWORD *)(a1 + 304);
      *((_QWORD *)v6 + 3) = *(_QWORD *)(a1 + 312);
      *(_QWORD *)(a1 + 304) = 0;
      *(_QWORD *)(a1 + 312) = 0;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)v6 = ___7__variadic_delegate_V_lambda_1___1____PerformMaintenanceCoreAsync_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUIAsyncAction_Foundation_Windows_9_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9_UCancellationTokenSource_asg___Z_X__V_impl_winrt__6B_;
      v7 = (_QWORD *)(a1 + 168);
      *(_QWORD *)(a1 + 168) = v6;
      v8 = *(volatile signed __int32 **)(a1 + 312);
      if ( v8 )
      {
        if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
      v9 = *(volatile signed __int32 **)(a1 + 184);
      if ( v9 )
      {
        if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 88));
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 88));
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 24LL))(v6);
      }
      else
      {
        v10 = (_QWORD *)(a1 + 104);
        if ( (_QWORD *)(a1 + 104) != v7 )
        {
          if ( *v10 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
          *v7 = 0;
          *v10 = v6;
          v6 = 0;
        }
        ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 88));
      }
      if ( v6 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 168);
      v11 = *(_QWORD *)(a1 + 152);
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      v12 = *(_QWORD *)(a1 + 144);
      v13 = *(volatile signed __int32 **)(a1 + 152);
      *(_QWORD *)(a1 + 192) = 0;
      *(_QWORD *)(a1 + 200) = 0;
      if ( v13 )
      {
        _InterlockedIncrement(v13 + 2);
        *(_QWORD *)(a1 + 192) = v12;
        *(_QWORD *)(a1 + 200) = v13;
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      else
      {
        *(_QWORD *)(a1 + 192) = v12;
        *(_QWORD *)(a1 + 200) = 0;
      }
      v14 = *(_QWORD *)(a1 + 136);
      *(_QWORD *)(a1 + 208) = v14;
      if ( !v14 )
        goto LABEL_33;
      v15 = *(_QWORD *)(v14 + 8);
      if ( v15 < 0 )
        goto LABEL_32;
      break;
    case 6:
      *(_BYTE *)(a1 + 217) = 0;
      v19 = *(_QWORD *)(a1 + 128);
      v20 = a1 + 224;
      *(_QWORD *)(a1 + 224) = v19;
      v21 = (_BYTE **)(a1 + 232);
      *(_QWORD *)(a1 + 232) = a1 + 217;
      *(_QWORD *)(a1 + 240) = a1 + 224;
      *(_BYTE *)(a1 + 248) = 1;
      *(_DWORD *)(a1 + 256) = 2141;
      *(_DWORD *)(a1 + 260) = 17;
      *(_QWORD *)(a1 + 264) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
      *(_QWORD *)(a1 + 272) = "struct winrt::Windows::Foundation::IAsyncAction __cdecl winrt::Microsoft::Asg::SemanticInd"
                              "ex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::Se"
                              "manticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Tex"
                              "tEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility:"
                              ":implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFa"
                              "bric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::"
                              "AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreA"
                              "sync<struct winrt::com_ptr<struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatib"
                              "ility::implementation::SemanticTextIndexStore>>(struct winrt::com_ptr<struct winrt::Micros"
                              "oft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>,"
                              "struct asg::CancellationTokenSource)";
      *(_QWORD *)(a1 + 280) = a1 + 192;
      *(_QWORD *)(a1 + 288) = v19;
      ___InvokeDbMethod_V_lambda_4___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUIAsyncAction_Foundation_Windows_9_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9_UCancellationTokenSource_asg___Z_AEAV_lambda_2___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___23456789_AEAA_AUIAsyncAction_Foundation_Windows_9_01_Z____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_4___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___01234567_AEAA_AUIAsyncAction_Foundation_Windows_7_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___7_UCancellationTokenSource_asg___Z_AEAV_lambda_2___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___01234567_AEAA_AU9Foundation_Windows_7_01_Z_AEBUsource_location_std___Z();
      v22 = (_Mtx_t *)(a1 + 360);
      LOBYTE(v23) = 1;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
        *(_QWORD *)(a1 + 224),
        a1 + 360,
        v23);
      if ( !**(_BYTE **)(a1 + 232) )
      {
        *(_BYTE *)(*(_QWORD *)v20 + 203LL) = 0;
        v24 = (_QWORD *)(*(_QWORD *)v20 + 208LL);
        if ( v24 != (_QWORD *)(a1 + 376) )
        {
          if ( *v24 )
          {
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(*(_QWORD *)v20 + 208LL);
            v21 = (_BYTE **)(a1 + 232);
          }
          *v24 = 0;
          v22 = (_Mtx_t *)(a1 + 360);
        }
        if ( !SetEvent(*(HANDLE *)(*(_QWORD *)v20 + 216LL)) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9C7,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
            v25);
        **v21 = 1;
      }
      if ( *(_BYTE *)(a1 + 368) )
        Mtx_unlock(*v22);
      if ( *(_QWORD *)(a1 + 208) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 208);
      v26 = *(volatile signed __int32 **)(a1 + 200);
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      *(_QWORD *)(a1 + 296) = a1 + 16;
      *(_WORD *)(a1 + 160) = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_60;
      return;
    case 7:
      v17 = a1 + 208;
      if ( *(_QWORD *)(a1 + 208) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(v17);
      v18 = *(volatile signed __int32 **)(a1 + 200);
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
LABEL_60:
      if ( *(_QWORD *)(a1 + 104) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      if ( *(_QWORD *)(a1 + 96) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      __ExceptionPtrDestroy((void *)(a1 + 72));
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 16);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>'::`4'::_parameters_::~_parameters_(a1 + 128);
      if ( *(_WORD *)(a1 + 162) )
        operator delete((void *)a1);
      return;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
    v16 = v15;
    v15 = _InterlockedCompareExchange64((volatile signed __int64 *)(v14 + 8), v15 + 1, v15);
    if ( v16 == v15 )
      break;
    if ( v15 < 0 )
    {
LABEL_32:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v15 + 24));
      break;
    }
  }
LABEL_33:
  *(_BYTE *)(a1 + 216) = 0;
  if ( *(_DWORD *)(a1 + 112) == 2 )
  {
    *(_DWORD *)(a1 + 336) = 5672;
    *(_QWORD *)(a1 + 344) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated F"
                            "iles\\winrt\\Windows.Foundation.h";
    *(_QWORD *)(a1 + 352) = 0;
    winrt::hresult_canceled::hresult_canceled(
      (winrt::hresult_canceled *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)(a1 + 336));
    throw (winrt::hresult_canceled *)pExceptionObject;
  }
  *(_WORD *)(a1 + 160) = 6;
  `winrt::resume_background'::`2'::awaitable::await_suspend(v14, a1);
}

```

## disassembly

```asm
0x1802376b0  mov     [rsp+Block], rcx
0x1802376b5  push    rbx
0x1802376b6  push    rsi
0x1802376b7  push    rdi
0x1802376b8  push    r12
0x1802376ba  push    r13
0x1802376bc  push    r14
0x1802376be  push    r15
0x1802376c0  sub     rsp, 0B0h
0x1802376c7  mov     rdi, [rsp+0E8h+Block]
0x1802376cf  movzx   eax, word ptr [rdi+0A0h]
0x1802376d6  mov     [rsp+0E8h+var_C8], ax
0x1802376db  inc     ax; switch 9 cases
0x1802376de  cmp     ax, 8
0x1802376e2  ja      def_1802376FD; jumptable 00000001802376FD default case, cases 0,4,5
0x1802376e8  movsx   rax, ax
0x1802376ec  lea     rdx, cs:180000000h
0x1802376f3  mov     ecx, ds:(jpt_1802376FD - 180000000h)[rdx+rax*4]
0x1802376fa  add     rcx, rdx
0x1802376fd  jmp     rcx; switch jump
0x1802376ff  mov     esi, 0FFFFFFFFh; jumptable 00000001802376FD case 3
0x180237704  jmp     loc_180237C75
0x180237709  xor     r14d, r14d; jumptable 00000001802376FD case 2
0x18023770c  lea     rdx, [rdi+0B0h]
0x180237713  mov     [rdx], r14
0x180237716  mov     [rdi+0B8h], r14
0x18023771d  mov     rax, [rdi+98h]
0x180237724  test    rax, rax
0x180237727  jz      short loc_18023772D
0x180237729  lock inc dword ptr [rax+8]
0x18023772d  mov     rax, [rdi+90h]
0x180237734  mov     rcx, [rdi+98h]
0x18023773b  mov     [rdi+140h], rdx
0x180237742  lea     rbx, [rdi+130h]
0x180237749  mov     [rsp+0E8h+var_B0], rax
0x18023774e  mov     [rbx], rax
0x180237751  mov     [rdi+138h], rcx
0x180237758  mov     [rdx], r14
0x18023775b  mov     [rdi+0B8h], r14
0x180237762  mov     [rdi+148h], rbx
0x180237769  mov     ecx, 20h ; ' '; Size
0x18023776e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180237773  mov     r15, rax
0x180237776  mov     dword ptr [rax+8], 1
0x18023777d  mov     [rax+10h], r14
0x180237781  mov     [rax+18h], r14
0x180237785  mov     rax, [rbx]
0x180237788  mov     [rsp+0E8h+var_C0], rax
0x18023778d  mov     [r15+10h], rax
0x180237791  mov     rax, [rdi+138h]
0x180237798  mov     [rsp+0E8h+var_B8], rax
0x18023779d  mov     [r15+18h], rax
0x1802377a1  mov     [rbx], r14
0x1802377a4  mov     [rdi+138h], r14
0x1802377ab  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802377b2  lea     rax, ??_7?$variadic_delegate@V_lambda_1_@?1???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUIAsyncAction@Foundation@Windows@9@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@UCancellationTokenSource@asg@@@Z@X$$V@impl@winrt@@6B@; const winrt::impl::variadic_delegate<`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>,asg::CancellationTokenSource)'::`2'::_lambda_1_,void,>::`vftable'
0x1802377b9  mov     [r15], rax
0x1802377bc  lea     r13, [rdi+0A8h]
0x1802377c3  mov     [r13+0], r15
0x1802377c7  mov     rbx, [rdi+138h]
0x1802377ce  mov     esi, 0FFFFFFFFh
0x1802377d3  test    rbx, rbx
0x1802377d6  jz      short loc_180237815
0x1802377d8  mov     [rsp+0E8h+var_B8], rbx
0x1802377dd  mov     eax, esi
0x1802377df  lock xadd [rbx+8], eax
0x1802377e4  cmp     eax, 1
0x1802377e7  jnz     short loc_180237815
0x1802377e9  mov     rax, [rbx]
0x1802377ec  mov     rcx, rbx
0x1802377ef  mov     rax, [rax]
0x1802377f2  call    cs:__guard_dispatch_icall_fptr
0x1802377f8  mov     eax, esi
0x1802377fa  lock xadd [rbx+0Ch], eax
0x1802377ff  cmp     eax, 1
0x180237802  jnz     short loc_180237815
0x180237804  mov     rax, [rbx]
0x180237807  mov     rcx, rbx
0x18023780a  mov     rax, [rax+8]
0x18023780e  call    cs:__guard_dispatch_icall_fptr
0x180237814  nop
0x180237815  mov     rbx, [rdi+0B8h]
0x18023781c  test    rbx, rbx
0x18023781f  jz      short loc_18023785E
0x180237821  mov     [rsp+0E8h+var_A8], rbx
0x180237826  mov     eax, esi
0x180237828  lock xadd [rbx+8], eax
0x18023782d  cmp     eax, 1
0x180237830  jnz     short loc_18023785E
0x180237832  mov     rax, [rbx]
0x180237835  mov     rcx, rbx
0x180237838  mov     rax, [rax]
0x18023783b  call    cs:__guard_dispatch_icall_fptr
0x180237841  mov     eax, esi
0x180237843  lock xadd [rbx+0Ch], eax
0x180237848  cmp     eax, 1
0x18023784b  jnz     short loc_18023785E
0x18023784d  mov     rax, [rbx]
0x180237850  mov     rcx, rbx
0x180237853  mov     rax, [rax+8]
0x180237857  call    cs:__guard_dispatch_icall_fptr
0x18023785d  nop
0x18023785e  lea     rcx, [rdi+58h]; SRWLock
0x180237862  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180237867  mov     eax, [rdi+70h]
0x18023786a  cmp     eax, 2
0x18023786d  jz      short loc_18023789D
0x18023786f  lea     r12, [rdi+68h]
0x180237873  cmp     r12, r13
0x180237876  jz      short loc_180237892
0x180237878  cmp     qword ptr [r12], 0
0x18023787d  jz      short loc_180237887
0x18023787f  mov     rcx, r12
0x180237882  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180237887  mov     [r13+0], r14
0x18023788b  mov     [r12], r15
0x18023788f  mov     r15, r14
0x180237892  lea     rcx, [rdi+58h]; SRWLock
0x180237896  call    ReleaseSRWLockExclusive_0
0x18023789b  jmp     short loc_1802378B7
0x18023789d  lea     rcx, [rdi+58h]; SRWLock
0x1802378a1  call    ReleaseSRWLockExclusive_0
0x1802378a6  mov     rax, [r15]
0x1802378a9  mov     rcx, r15
0x1802378ac  mov     rax, [rax+18h]
0x1802378b0  call    cs:__guard_dispatch_icall_fptr
0x1802378b6  nop
0x1802378b7  mov     [rsp+0E8h+arg_10], r15
0x1802378bf  test    r15, r15
0x1802378c2  jz      short loc_1802378CC
0x1802378c4  mov     rcx, r13
0x1802378c7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802378cc  mov     rax, [rdi+98h]
0x1802378d3  test    rax, rax
0x1802378d6  jz      short loc_1802378DC
0x1802378d8  lock inc dword ptr [rax+8]
0x1802378dc  mov     rax, [rdi+90h]
0x1802378e3  mov     rbx, [rdi+98h]
0x1802378ea  mov     [rdi+0C0h], r14
0x1802378f1  mov     [rdi+0C8h], r14
0x1802378f8  test    rbx, rbx
0x1802378fb  jz      short loc_180237946
0x1802378fd  lock inc dword ptr [rbx+8]
0x180237901  mov     [rdi+0C0h], rax
0x180237908  mov     [rdi+0C8h], rbx
0x18023790f  mov     eax, esi
0x180237911  lock xadd [rbx+8], eax
0x180237916  cmp     eax, 1
0x180237919  jnz     short loc_180237954
0x18023791b  mov     rax, [rbx]
0x18023791e  mov     rcx, rbx
0x180237921  mov     rax, [rax]
0x180237924  call    cs:__guard_dispatch_icall_fptr
0x18023792a  lock xadd [rbx+0Ch], esi
0x18023792f  cmp     esi, 1
0x180237932  jnz     short loc_180237954
0x180237934  mov     rax, [rbx]
0x180237937  mov     rcx, rbx
0x18023793a  mov     rax, [rax+8]
0x18023793e  call    cs:__guard_dispatch_icall_fptr
0x180237944  jmp     short loc_180237954
0x180237946  mov     [rdi+0C0h], rax
0x18023794d  mov     [rdi+0C8h], rbx
0x180237954  mov     rcx, [rdi+88h]
0x18023795b  mov     [rdi+0D0h], rcx
0x180237962  test    rcx, rcx
0x180237965  jz      short loc_180237996
0x180237967  mov     [rsp+0E8h+arg_8], rcx
0x18023796f  mov     rax, [rcx+8]
0x180237973  test    rax, rax
0x180237976  js      short loc_180237991
0x180237978  nop     dword ptr [rax+rax+00000000h]
0x180237980  lea     rdx, [rax+1]
0x180237984  lock cmpxchg [rcx+8], rdx
0x18023798a  jz      short loc_180237996
0x18023798c  test    rax, rax
0x18023798f  jns     short loc_180237980
0x180237991  lock inc dword ptr [rax+rax+18h]
0x180237996  mov     byte ptr [rdi+0D8h], 0
0x18023799d  mov     eax, [rdi+70h]
0x1802379a0  cmp     eax, 2
0x1802379a3  jnz     short loc_1802379E2
0x1802379a5  lea     rdx, [rdi+150h]; struct winrt::impl::slim_source_location *
0x1802379ac  mov     dword ptr [rdx], 1628h
0x1802379b2  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802379b9  mov     [rdi+158h], rax
0x1802379c0  mov     [rdi+160h], r14
0x1802379c7  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x1802379cc  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802379d1  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802379d8  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x1802379dd  call    _CxxThrowException
0x1802379e2  mov     eax, 6
0x1802379e7  mov     [rdi+0A0h], ax
0x1802379ee  mov     rdx, rdi
0x1802379f1  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x1802379f6  jmp     loc_180237CE2
0x1802379fb  lea     rcx, [rdi+0D0h]; jumptable 00000001802376FD case 7
0x180237a02  mov     rax, [rcx]
0x180237a05  mov     [rsp+0E8h+arg_8], rax
0x180237a0d  test    rax, rax
0x180237a10  jz      short loc_180237A18
0x180237a12  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x180237a17  nop
0x180237a18  mov     rbx, [rdi+0C8h]
0x180237a1f  mov     esi, 0FFFFFFFFh
0x180237a24  test    rbx, rbx
0x180237a27  jz      short loc_180237A66
0x180237a29  mov     [rsp+0E8h+var_98], rbx
0x180237a2e  mov     eax, esi
0x180237a30  lock xadd [rbx+8], eax
0x180237a35  cmp     eax, 1
0x180237a38  jnz     short loc_180237A66
0x180237a3a  mov     rax, [rbx]
0x180237a3d  mov     rcx, rbx
0x180237a40  mov     rax, [rax]
0x180237a43  call    cs:__guard_dispatch_icall_fptr
0x180237a49  mov     eax, esi
0x180237a4b  lock xadd [rbx+0Ch], eax
0x180237a50  cmp     eax, 1
0x180237a53  jnz     short loc_180237A66
0x180237a55  mov     rax, [rbx]
0x180237a58  mov     rcx, rbx
0x180237a5b  mov     rax, [rax+8]
0x180237a5f  call    cs:__guard_dispatch_icall_fptr
0x180237a65  nop
0x180237a66  jmp     loc_180237C75
0x180237a6b  lea     rax, [rdi+0D9h]; jumptable 00000001802376FD case 6
0x180237a72  mov     byte ptr [rax], 0
0x180237a75  mov     rcx, [rdi+80h]
0x180237a7c  lea     rsi, [rdi+0E0h]
0x180237a83  mov     [rsi], rcx
0x180237a86  lea     rbx, [rdi+0E8h]
0x180237a8d  mov     [rbx], rax
0x180237a90  mov     [rdi+0F0h], rsi
0x180237a97  mov     byte ptr [rdi+0F8h], 1
0x180237a9e  lea     r9, [rdi+100h]
0x180237aa5  mov     dword ptr [r9], 85Dh
0x180237aac  mov     dword ptr [rdi+104h], 11h
0x180237ab6  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180237abd  mov     [rdi+108h], rax
0x180237ac4  lea     rax, aStructWinrtWin_0; "struct winrt::Windows::Foundation::IAsy"...
0x180237acb  mov     [rdi+110h], rax
0x180237ad2  lea     rdx, [rdi+118h]
0x180237ad9  lea     rax, [rdi+0C0h]
0x180237ae0  mov     [rdx], rax
0x180237ae3  mov     [rdi+120h], rcx
0x180237aea  call    ??$InvokeDbMethod@V_lambda_4_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUIAsyncAction@Foundation@Windows@9@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@UCancellationTokenSource@asg@@@Z@AEAV_lambda_2_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@23456789@AEAA?AUIAsyncAction@Foundation@Windows@9@01@Z@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_4_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@01234567@AEAA?AUIAsyncAction@Foundation@Windows@7@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@UCancellationTokenSource@asg@@@Z@AEAV_lambda_2_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@01234567@AEAA?AU9Foundation@Windows@7@01@Z@AEBUsource_location@std@@@Z
0x180237aef  nop
0x180237af0  lea     r15, [rdi+168h]
0x180237af7  mov     rcx, [rsi]
0x180237afa  mov     [rsp+0E8h+var_C0], rcx
0x180237aff  mov     r8b, 1
0x180237b02  mov     rdx, r15
0x180237b05  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x180237b0a  mov     rax, [rbx]
0x180237b0d  mov     [rsp+0E8h+var_B8], rax
0x180237b12  cmp     byte ptr [rax], 0
0x180237b15  jnz     loc_180237BA4
0x180237b1b  mov     rax, [rsi]
0x180237b1e  mov     byte ptr [rax+0CBh], 0
0x180237b25  mov     r12, [rsi]
0x180237b28  add     r12, 0D0h
0x180237b2f  lea     rax, [rdi+178h]
0x180237b36  cmp     r12, rax
0x180237b39  jz      short loc_180237B61
0x180237b3b  cmp     qword ptr [r12], 0
0x180237b40  jz      short loc_180237B51
0x180237b42  mov     rcx, r12
0x180237b45  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180237b4a  lea     rbx, [rdi+0E8h]
0x180237b51  xor     r14d, r14d
0x180237b54  mov     [r12], r14
0x180237b58  lea     r15, [rdi+168h]
0x180237b5f  jmp     short loc_180237B64
0x180237b61  xor     r14d, r14d
0x180237b64  mov     rcx, [rsi]
0x180237b67  mov     [rsp+0E8h+var_C0], rcx
0x180237b6c  mov     rcx, [rcx+0D8h]; hEvent
0x180237b73  call    cs:__imp_SetEvent
0x180237b79  mov     rcx, [rsp+0E8h]; this
0x180237b81  test    eax, eax
0x180237b83  jnz     short loc_180237B97
0x180237b85  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180237b8c  mov     edx, 9C7h; void *
0x180237b91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180237b97  mov     rax, [rbx]
0x180237b9a  mov     [rsp+0E8h+var_B8], rax
0x180237b9f  mov     byte ptr [rax], 1
0x180237ba2  jmp     short loc_180237BA7
0x180237ba4  xor     r14d, r14d
0x180237ba7  movzx   eax, byte ptr [rdi+170h]
0x180237bae  mov     byte ptr [rsp+0E8h+var_A8], al
0x180237bb2  test    al, al
0x180237bb4  jz      short loc_180237BC4
0x180237bb6  mov     rcx, [r15]; _Mtx_t
0x180237bb9  mov     [rsp+0E8h+var_B0], rcx
0x180237bbe  call    _Mtx_unlock
0x180237bc3  nop
0x180237bc4  lea     rcx, [rdi+0D0h]
  ... truncated ...
```
