# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceCoreAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore___

- ea: `0x18022be30`
- end: `0x18022c49c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceCoreAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore___`
- size: `1644`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002cb40`
- `0x18022be20`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x18000b2a0`
- `0x180020670`
- `0x18002ccf0`
- `0x18002f8e0`
- `0x180030a30`
- `0x180046940`
- `0x180047520`
- `0x1800475c0`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d1e70`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18022be30`
- `0x180242120`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18022c2f3`
- `KERNEL32!SetEvent` at `0x18022c2f3`

## string_xrefs

- `0x18022c305`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x18022c132`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022c236`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18022c244`: `struct winrt::Windows::Foundation::IAsyncAction __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,str`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceCoreAsync__ResumeCoro_1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore___(
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
      *(_QWORD *)v6 = ___7__variadic_delegate_V_lambda_1___1____PerformMaintenanceCoreAsync_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUIAsyncAction_Foundation_Windows_9_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9_UCancellationTokenSource_asg___Z_X__V_impl_winrt__6B_;
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
                              "manticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Ima"
                              "geEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility"
                              "::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::Ai"
                              "Fabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex"
                              "::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCor"
                              "eAsync<struct winrt::com_ptr<struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compat"
                              "ibility::implementation::SemanticImageIndexStore>>(struct winrt::com_ptr<struct winrt::Mic"
                              "rosoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexSto"
                              "re>,struct asg::CancellationTokenSource)";
      *(_QWORD *)(a1 + 280) = a1 + 192;
      *(_QWORD *)(a1 + 288) = v19;
      ___InvokeDbMethod_V_lambda_4___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUIAsyncAction_Foundation_Windows_9_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9_UCancellationTokenSource_asg___Z_AEAV_lambda_2___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___23456789_AEAA_AUIAsyncAction_Foundation_Windows_9_01_Z____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_4___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___01234567_AEAA_AUIAsyncAction_Foundation_Windows_7_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___7_UCancellationTokenSource_asg___Z_AEAV_lambda_2___2____PerformMaintenanceCoreAsync_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___01234567_AEAA_AU9Foundation_Windows_7_01_Z_AEBUsource_location_std___Z();
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
0x18022be30  mov     [rsp+Block], rcx
0x18022be35  push    rbx
0x18022be36  push    rsi
0x18022be37  push    rdi
0x18022be38  push    r12
0x18022be3a  push    r13
0x18022be3c  push    r14
0x18022be3e  push    r15
0x18022be40  sub     rsp, 0B0h
0x18022be47  mov     rdi, [rsp+0E8h+Block]
0x18022be4f  movzx   eax, word ptr [rdi+0A0h]
0x18022be56  mov     [rsp+0E8h+var_C8], ax
0x18022be5b  inc     ax; switch 9 cases
0x18022be5e  cmp     ax, 8
0x18022be62  ja      def_18022BE7D; jumptable 000000018022BE7D default case, cases 0,4,5
0x18022be68  movsx   rax, ax
0x18022be6c  lea     rdx, cs:180000000h
0x18022be73  mov     ecx, ds:(jpt_18022BE7D - 180000000h)[rdx+rax*4]
0x18022be7a  add     rcx, rdx
0x18022be7d  jmp     rcx; switch jump
0x18022be7f  mov     esi, 0FFFFFFFFh; jumptable 000000018022BE7D case 3
0x18022be84  jmp     loc_18022C3F5
0x18022be89  xor     r14d, r14d; jumptable 000000018022BE7D case 2
0x18022be8c  lea     rdx, [rdi+0B0h]
0x18022be93  mov     [rdx], r14
0x18022be96  mov     [rdi+0B8h], r14
0x18022be9d  mov     rax, [rdi+98h]
0x18022bea4  test    rax, rax
0x18022bea7  jz      short loc_18022BEAD
0x18022bea9  lock inc dword ptr [rax+8]
0x18022bead  mov     rax, [rdi+90h]
0x18022beb4  mov     rcx, [rdi+98h]
0x18022bebb  mov     [rdi+140h], rdx
0x18022bec2  lea     rbx, [rdi+130h]
0x18022bec9  mov     [rsp+0E8h+var_B0], rax
0x18022bece  mov     [rbx], rax
0x18022bed1  mov     [rdi+138h], rcx
0x18022bed8  mov     [rdx], r14
0x18022bedb  mov     [rdi+0B8h], r14
0x18022bee2  mov     [rdi+148h], rbx
0x18022bee9  mov     ecx, 20h ; ' '; Size
0x18022beee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022bef3  mov     r15, rax
0x18022bef6  mov     dword ptr [rax+8], 1
0x18022befd  mov     [rax+10h], r14
0x18022bf01  mov     [rax+18h], r14
0x18022bf05  mov     rax, [rbx]
0x18022bf08  mov     [rsp+0E8h+var_C0], rax
0x18022bf0d  mov     [r15+10h], rax
0x18022bf11  mov     rax, [rdi+138h]
0x18022bf18  mov     [rsp+0E8h+var_B8], rax
0x18022bf1d  mov     [r15+18h], rax
0x18022bf21  mov     [rbx], r14
0x18022bf24  mov     [rdi+138h], r14
0x18022bf2b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022bf32  lea     rax, ??_7?$variadic_delegate@V_lambda_1_@?1???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUIAsyncAction@Foundation@Windows@9@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@UCancellationTokenSource@asg@@@Z@X$$V@impl@winrt@@6B@; const winrt::impl::variadic_delegate<`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource)'::`2'::_lambda_1_,void,>::`vftable'
0x18022bf39  mov     [r15], rax
0x18022bf3c  lea     r13, [rdi+0A8h]
0x18022bf43  mov     [r13+0], r15
0x18022bf47  mov     rbx, [rdi+138h]
0x18022bf4e  mov     esi, 0FFFFFFFFh
0x18022bf53  test    rbx, rbx
0x18022bf56  jz      short loc_18022BF95
0x18022bf58  mov     [rsp+0E8h+var_B8], rbx
0x18022bf5d  mov     eax, esi
0x18022bf5f  lock xadd [rbx+8], eax
0x18022bf64  cmp     eax, 1
0x18022bf67  jnz     short loc_18022BF95
0x18022bf69  mov     rax, [rbx]
0x18022bf6c  mov     rcx, rbx
0x18022bf6f  mov     rax, [rax]
0x18022bf72  call    cs:__guard_dispatch_icall_fptr
0x18022bf78  mov     eax, esi
0x18022bf7a  lock xadd [rbx+0Ch], eax
0x18022bf7f  cmp     eax, 1
0x18022bf82  jnz     short loc_18022BF95
0x18022bf84  mov     rax, [rbx]
0x18022bf87  mov     rcx, rbx
0x18022bf8a  mov     rax, [rax+8]
0x18022bf8e  call    cs:__guard_dispatch_icall_fptr
0x18022bf94  nop
0x18022bf95  mov     rbx, [rdi+0B8h]
0x18022bf9c  test    rbx, rbx
0x18022bf9f  jz      short loc_18022BFDE
0x18022bfa1  mov     [rsp+0E8h+var_A8], rbx
0x18022bfa6  mov     eax, esi
0x18022bfa8  lock xadd [rbx+8], eax
0x18022bfad  cmp     eax, 1
0x18022bfb0  jnz     short loc_18022BFDE
0x18022bfb2  mov     rax, [rbx]
0x18022bfb5  mov     rcx, rbx
0x18022bfb8  mov     rax, [rax]
0x18022bfbb  call    cs:__guard_dispatch_icall_fptr
0x18022bfc1  mov     eax, esi
0x18022bfc3  lock xadd [rbx+0Ch], eax
0x18022bfc8  cmp     eax, 1
0x18022bfcb  jnz     short loc_18022BFDE
0x18022bfcd  mov     rax, [rbx]
0x18022bfd0  mov     rcx, rbx
0x18022bfd3  mov     rax, [rax+8]
0x18022bfd7  call    cs:__guard_dispatch_icall_fptr
0x18022bfdd  nop
0x18022bfde  lea     rcx, [rdi+58h]; SRWLock
0x18022bfe2  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18022bfe7  mov     eax, [rdi+70h]
0x18022bfea  cmp     eax, 2
0x18022bfed  jz      short loc_18022C01D
0x18022bfef  lea     r12, [rdi+68h]
0x18022bff3  cmp     r12, r13
0x18022bff6  jz      short loc_18022C012
0x18022bff8  cmp     qword ptr [r12], 0
0x18022bffd  jz      short loc_18022C007
0x18022bfff  mov     rcx, r12
0x18022c002  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022c007  mov     [r13+0], r14
0x18022c00b  mov     [r12], r15
0x18022c00f  mov     r15, r14
0x18022c012  lea     rcx, [rdi+58h]; SRWLock
0x18022c016  call    ReleaseSRWLockExclusive_0
0x18022c01b  jmp     short loc_18022C037
0x18022c01d  lea     rcx, [rdi+58h]; SRWLock
0x18022c021  call    ReleaseSRWLockExclusive_0
0x18022c026  mov     rax, [r15]
0x18022c029  mov     rcx, r15
0x18022c02c  mov     rax, [rax+18h]
0x18022c030  call    cs:__guard_dispatch_icall_fptr
0x18022c036  nop
0x18022c037  mov     [rsp+0E8h+arg_10], r15
0x18022c03f  test    r15, r15
0x18022c042  jz      short loc_18022C04C
0x18022c044  mov     rcx, r13
0x18022c047  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022c04c  mov     rax, [rdi+98h]
0x18022c053  test    rax, rax
0x18022c056  jz      short loc_18022C05C
0x18022c058  lock inc dword ptr [rax+8]
0x18022c05c  mov     rax, [rdi+90h]
0x18022c063  mov     rbx, [rdi+98h]
0x18022c06a  mov     [rdi+0C0h], r14
0x18022c071  mov     [rdi+0C8h], r14
0x18022c078  test    rbx, rbx
0x18022c07b  jz      short loc_18022C0C6
0x18022c07d  lock inc dword ptr [rbx+8]
0x18022c081  mov     [rdi+0C0h], rax
0x18022c088  mov     [rdi+0C8h], rbx
0x18022c08f  mov     eax, esi
0x18022c091  lock xadd [rbx+8], eax
0x18022c096  cmp     eax, 1
0x18022c099  jnz     short loc_18022C0D4
0x18022c09b  mov     rax, [rbx]
0x18022c09e  mov     rcx, rbx
0x18022c0a1  mov     rax, [rax]
0x18022c0a4  call    cs:__guard_dispatch_icall_fptr
0x18022c0aa  lock xadd [rbx+0Ch], esi
0x18022c0af  cmp     esi, 1
0x18022c0b2  jnz     short loc_18022C0D4
0x18022c0b4  mov     rax, [rbx]
0x18022c0b7  mov     rcx, rbx
0x18022c0ba  mov     rax, [rax+8]
0x18022c0be  call    cs:__guard_dispatch_icall_fptr
0x18022c0c4  jmp     short loc_18022C0D4
0x18022c0c6  mov     [rdi+0C0h], rax
0x18022c0cd  mov     [rdi+0C8h], rbx
0x18022c0d4  mov     rcx, [rdi+88h]
0x18022c0db  mov     [rdi+0D0h], rcx
0x18022c0e2  test    rcx, rcx
0x18022c0e5  jz      short loc_18022C116
0x18022c0e7  mov     [rsp+0E8h+arg_8], rcx
0x18022c0ef  mov     rax, [rcx+8]
0x18022c0f3  test    rax, rax
0x18022c0f6  js      short loc_18022C111
0x18022c0f8  nop     dword ptr [rax+rax+00000000h]
0x18022c100  lea     rdx, [rax+1]
0x18022c104  lock cmpxchg [rcx+8], rdx
0x18022c10a  jz      short loc_18022C116
0x18022c10c  test    rax, rax
0x18022c10f  jns     short loc_18022C100
0x18022c111  lock inc dword ptr [rax+rax+18h]
0x18022c116  mov     byte ptr [rdi+0D8h], 0
0x18022c11d  mov     eax, [rdi+70h]
0x18022c120  cmp     eax, 2
0x18022c123  jnz     short loc_18022C162
0x18022c125  lea     rdx, [rdi+150h]; struct winrt::impl::slim_source_location *
0x18022c12c  mov     dword ptr [rdx], 1628h
0x18022c132  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022c139  mov     [rdi+158h], rax
0x18022c140  mov     [rdi+160h], r14
0x18022c147  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x18022c14c  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022c151  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022c158  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18022c15d  call    _CxxThrowException
0x18022c162  mov     eax, 6
0x18022c167  mov     [rdi+0A0h], ax
0x18022c16e  mov     rdx, rdi
0x18022c171  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18022c176  jmp     loc_18022C462
0x18022c17b  lea     rcx, [rdi+0D0h]; jumptable 000000018022BE7D case 7
0x18022c182  mov     rax, [rcx]
0x18022c185  mov     [rsp+0E8h+arg_8], rax
0x18022c18d  test    rax, rax
0x18022c190  jz      short loc_18022C198
0x18022c192  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022c197  nop
0x18022c198  mov     rbx, [rdi+0C8h]
0x18022c19f  mov     esi, 0FFFFFFFFh
0x18022c1a4  test    rbx, rbx
0x18022c1a7  jz      short loc_18022C1E6
0x18022c1a9  mov     [rsp+0E8h+var_98], rbx
0x18022c1ae  mov     eax, esi
0x18022c1b0  lock xadd [rbx+8], eax
0x18022c1b5  cmp     eax, 1
0x18022c1b8  jnz     short loc_18022C1E6
0x18022c1ba  mov     rax, [rbx]
0x18022c1bd  mov     rcx, rbx
0x18022c1c0  mov     rax, [rax]
0x18022c1c3  call    cs:__guard_dispatch_icall_fptr
0x18022c1c9  mov     eax, esi
0x18022c1cb  lock xadd [rbx+0Ch], eax
0x18022c1d0  cmp     eax, 1
0x18022c1d3  jnz     short loc_18022C1E6
0x18022c1d5  mov     rax, [rbx]
0x18022c1d8  mov     rcx, rbx
0x18022c1db  mov     rax, [rax+8]
0x18022c1df  call    cs:__guard_dispatch_icall_fptr
0x18022c1e5  nop
0x18022c1e6  jmp     loc_18022C3F5
0x18022c1eb  lea     rax, [rdi+0D9h]; jumptable 000000018022BE7D case 6
0x18022c1f2  mov     byte ptr [rax], 0
0x18022c1f5  mov     rcx, [rdi+80h]
0x18022c1fc  lea     rsi, [rdi+0E0h]
0x18022c203  mov     [rsi], rcx
0x18022c206  lea     rbx, [rdi+0E8h]
0x18022c20d  mov     [rbx], rax
0x18022c210  mov     [rdi+0F0h], rsi
0x18022c217  mov     byte ptr [rdi+0F8h], 1
0x18022c21e  lea     r9, [rdi+100h]
0x18022c225  mov     dword ptr [r9], 85Dh
0x18022c22c  mov     dword ptr [rdi+104h], 11h
0x18022c236  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022c23d  mov     [rdi+108h], rax
0x18022c244  lea     rax, aStructWinrtWin_7; "struct winrt::Windows::Foundation::IAsy"...
0x18022c24b  mov     [rdi+110h], rax
0x18022c252  lea     rdx, [rdi+118h]
0x18022c259  lea     rax, [rdi+0C0h]
0x18022c260  mov     [rdx], rax
0x18022c263  mov     [rdi+120h], rcx
0x18022c26a  call    ??$InvokeDbMethod@V_lambda_4_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUIAsyncAction@Foundation@Windows@9@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@UCancellationTokenSource@asg@@@Z@AEAV_lambda_2_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@23456789@AEAA?AUIAsyncAction@Foundation@Windows@9@01@Z@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_4_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@01234567@AEAA?AUIAsyncAction@Foundation@Windows@7@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@UCancellationTokenSource@asg@@@Z@AEAV_lambda_2_@?2???$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@01234567@AEAA?AU9Foundation@Windows@7@01@Z@AEBUsource_location@std@@@Z
0x18022c26f  nop
0x18022c270  lea     r15, [rdi+168h]
0x18022c277  mov     rcx, [rsi]
0x18022c27a  mov     [rsp+0E8h+var_C0], rcx
0x18022c27f  mov     r8b, 1
0x18022c282  mov     rdx, r15
0x18022c285  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18022c28a  mov     rax, [rbx]
0x18022c28d  mov     [rsp+0E8h+var_B8], rax
0x18022c292  cmp     byte ptr [rax], 0
0x18022c295  jnz     loc_18022C324
0x18022c29b  mov     rax, [rsi]
0x18022c29e  mov     byte ptr [rax+0CBh], 0
0x18022c2a5  mov     r12, [rsi]
0x18022c2a8  add     r12, 0D0h
0x18022c2af  lea     rax, [rdi+178h]
0x18022c2b6  cmp     r12, rax
0x18022c2b9  jz      short loc_18022C2E1
0x18022c2bb  cmp     qword ptr [r12], 0
0x18022c2c0  jz      short loc_18022C2D1
0x18022c2c2  mov     rcx, r12
0x18022c2c5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022c2ca  lea     rbx, [rdi+0E8h]
0x18022c2d1  xor     r14d, r14d
0x18022c2d4  mov     [r12], r14
0x18022c2d8  lea     r15, [rdi+168h]
0x18022c2df  jmp     short loc_18022C2E4
0x18022c2e1  xor     r14d, r14d
0x18022c2e4  mov     rcx, [rsi]
0x18022c2e7  mov     [rsp+0E8h+var_C0], rcx
0x18022c2ec  mov     rcx, [rcx+0D8h]; hEvent
0x18022c2f3  call    cs:__imp_SetEvent
0x18022c2f9  mov     rcx, [rsp+0E8h]; this
0x18022c301  test    eax, eax
0x18022c303  jnz     short loc_18022C317
0x18022c305  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18022c30c  mov     edx, 9C7h; void *
0x18022c311  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18022c317  mov     rax, [rbx]
0x18022c31a  mov     [rsp+0E8h+var_B8], rax
0x18022c31f  mov     byte ptr [rax], 1
0x18022c322  jmp     short loc_18022C327
0x18022c324  xor     r14d, r14d
0x18022c327  movzx   eax, byte ptr [rdi+170h]
0x18022c32e  mov     byte ptr [rsp+0E8h+var_A8], al
0x18022c332  test    al, al
0x18022c334  jz      short loc_18022C344
0x18022c336  mov     rcx, [r15]; _Mtx_t
0x18022c339  mov     [rsp+0E8h+var_B0], rcx
0x18022c33e  call    _Mtx_unlock
0x18022c343  nop
0x18022c344  lea     rcx, [rdi+0D0h]
  ... truncated ...
```
