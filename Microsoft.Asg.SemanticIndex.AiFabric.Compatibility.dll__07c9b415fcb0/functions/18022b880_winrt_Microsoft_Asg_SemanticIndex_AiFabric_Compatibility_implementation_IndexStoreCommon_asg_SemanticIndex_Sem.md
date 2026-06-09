# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore___

- ea: `0x18022b880`
- end: `0x18022be18`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore___`
- size: `1432`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a7c0`
- `0x18022b870`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x18000b2a0`
- `0x1800176b0`
- `0x180020670`
- `0x18002cb40`
- `0x18002cd70`
- `0x18002f2e0`
- `0x18002f8e0`
- `0x180046940`
- `0x180047520`
- `0x180078d56`
- `0x180078d5c`
- `0x180078da0`
- `0x1801d1e70`
- `0x1801d2b20`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x180229032`
- `0x18022b880`
- `0x180242120`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x18022b92f`
- `KERNEL32!ResetEvent` at `0x18022b92f`

## string_xrefs

- `0x18022bca2`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\base.h`
- `0x18022b941`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x18022bbbd`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceAsync__ResumeCoro_1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // r14
  __int64 v5; // r15
  _Mtx_t *v6; // rbx
  const char *v7; // r9
  __int64 v8; // rdx
  signed __int64 v9; // rax
  signed __int64 v10; // rtt
  __int64 *v11; // rbx
  __int64 *v12; // r14
  __int64 v13; // rax
  __int64 *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  _DWORD *v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // r15
  _QWORD *v21; // r12
  __int64 v22; // rcx
  struct _TP_WAIT *v23; // rcx
  volatile __int64 *v24; // rbx
  struct _TP_WAIT *v25; // rcx
  volatile __int64 *v26; // rbx
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-A0h] BYREF
  _BYTE v28[136]; // [rsp+A0h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 144) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_53;
    case 2:
      v4 = a1 + 128;
      v5 = *(_QWORD *)(a1 + 128);
      v6 = (_Mtx_t *)(a1 + 152);
      LOBYTE(a3) = 1;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
        v5,
        a1 + 152,
        a3);
      if ( *(_BYTE *)(v5 + 203) || !*(_BYTE *)(v5 + 202) )
        goto LABEL_33;
      *(_BYTE *)(v5 + 203) = 1;
      asg::details::CancellationTokenSourceCore::Make(a1 + 168);
      if ( !ResetEvent(*(HANDLE *)(v5 + 216)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9CC,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.27\\inc\\wil\\opensource\\wil\\resource.h",
          v7);
      *(_QWORD *)(a1 + 184) = *(_QWORD *)(a1 + 168);
      *(_QWORD *)(a1 + 192) = *(_QWORD *)(a1 + 176);
      *(_QWORD *)(a1 + 168) = 0;
      *(_QWORD *)(a1 + 176) = 0;
      v8 = *(_QWORD *)(a1 + 136);
      *(_QWORD *)(a1 + 200) = v8;
      if ( !v8 )
        goto LABEL_11;
      v9 = *(_QWORD *)(v8 + 8);
      if ( v9 < 0 )
        goto LABEL_10;
      break;
    case 6:
      goto LABEL_45;
    case 7:
      v23 = *(struct _TP_WAIT **)(a1 + 248);
      if ( v23 )
      {
        CloseThreadpoolWait_0(v23);
        *(_QWORD *)(a1 + 248) = 0;
      }
      v24 = *(volatile __int64 **)(a1 + 240);
      if ( v24 && _InterlockedExchange64(v24, 0) == 1 )
      {
        do
          Thrd_yield();
        while ( _InterlockedExchange64(v24, 0) == 1 );
      }
      goto LABEL_53;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
    v10 = v9;
    v9 = _InterlockedCompareExchange64((volatile signed __int64 *)(v8 + 8), v9 + 1, v9);
    if ( v10 == v9 )
      break;
    if ( v9 < 0 )
    {
LABEL_10:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v9 + 24));
      break;
    }
  }
LABEL_11:
  v11 = (__int64 *)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(
                     v5,
                     a1 + 208);
  v12 = (__int64 *)(v5 + 208);
  if ( (__int64 *)(v5 + 208) != v11 )
  {
    if ( *v12 )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v5 + 208);
    v13 = *v11;
    *v11 = 0;
    *v12 = v13;
  }
  if ( *(_QWORD *)(a1 + 208) )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 208);
  v14 = (__int64 *)(a1 + 224);
  v15 = *v12;
  *(_QWORD *)(a1 + 224) = *v12;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  *(_QWORD *)(a1 + 304) = v14;
  v16 = *v14;
  *v14 = 0;
  *(_QWORD *)(a1 + 360) = v16;
  *(_QWORD *)(a1 + 368) = a1 + 360;
  v17 = operator new(0x18u);
  v17[2] = 1;
  v18 = *(_QWORD *)(a1 + 360);
  *(_QWORD *)(a1 + 360) = 0;
  *((_QWORD *)v17 + 2) = v18;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v17 = ___7__variadic_delegate_V_lambda_1___6____PerformMaintenanceAsync_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AUIAsyncAction_Foundation_Windows_9_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9__Z_X__V_impl_winrt__6B_;
  *(_QWORD *)(a1 + 216) = v17;
  v19 = a1 + 224;
  if ( *(_QWORD *)(a1 + 360) )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 360);
    v19 = a1 + 224;
  }
  v20 = (_QWORD *)(a1 + 216);
  if ( *v14 )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v19);
    v20 = (_QWORD *)(a1 + 216);
  }
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 88));
  if ( *(_DWORD *)(a1 + 112) == 2 )
  {
    ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 88));
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 24LL))(v17);
  }
  else
  {
    v21 = (_QWORD *)(a1 + 104);
    if ( a1 + 104 != a1 + 216 )
    {
      if ( *v21 )
      {
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
        v20 = (_QWORD *)(a1 + 216);
      }
      *v20 = 0;
      *v21 = v17;
      v17 = 0;
    }
    ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 88));
  }
  if ( v17 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v20);
  v6 = (_Mtx_t *)(a1 + 152);
  v4 = a1 + 128;
LABEL_33:
  if ( *(_BYTE *)(a1 + 160) )
    Mtx_unlock(*v6);
  v22 = *(_QWORD *)(*(_QWORD *)v4 + 216LL);
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = v22;
  *(_DWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_DWORD *)(a1 + 288) = 0;
  if ( *(_DWORD *)(a1 + 112) == 2 )
  {
    *(_DWORD *)(a1 + 312) = 5672;
    *(_QWORD *)(a1 + 320) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated F"
                            "iles\\winrt\\Windows.Foundation.h";
    *(_QWORD *)(a1 + 328) = 0;
    winrt::hresult_canceled::hresult_canceled(
      (winrt::hresult_canceled *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)(a1 + 312));
    throw (winrt::hresult_canceled *)pExceptionObject;
  }
  if ( WaitForSingleObject_0(*(HANDLE *)(a1 + 264), 0) )
  {
    *(_WORD *)(a1 + 144) = 6;
    winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>(
      (_QWORD *)(a1 + 240),
      a1);
  }
  else
  {
LABEL_45:
    if ( _InterlockedExchange((volatile __int32 *)(a1 + 288), 0) == 2 )
    {
      *(_DWORD *)(a1 + 336) = 9410;
      *(_QWORD *)(a1 + 344) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated"
                              " Files\\winrt\\base.h";
      *(_QWORD *)(a1 + 352) = 0;
      winrt::hresult_canceled::hresult_canceled(
        (winrt::hresult_canceled *)v28,
        (const struct winrt::impl::slim_source_location *)(a1 + 336));
      throw (winrt::hresult_canceled *)v28;
    }
    v25 = *(struct _TP_WAIT **)(a1 + 248);
    if ( v25 )
    {
      CloseThreadpoolWait_0(v25);
      *(_QWORD *)(a1 + 248) = 0;
    }
    v26 = *(volatile __int64 **)(a1 + 240);
    if ( v26 && _InterlockedExchange64(v26, 0) == 1 )
    {
      do
        Thrd_yield();
      while ( _InterlockedExchange64(v26, 0) == 1 );
    }
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::EnsureNotCorrupted(*(_QWORD *)(a1 + 128));
    *(_QWORD *)(a1 + 296) = a1 + 16;
    *(_WORD *)(a1 + 144) = 0;
    *(_QWORD *)a1 = 0;
    if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
    {
LABEL_53:
      if ( *(_QWORD *)(a1 + 104) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      if ( *(_QWORD *)(a1 + 96) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      __ExceptionPtrDestroy((void *)(a1 + 72));
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 16);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( *(_QWORD *)(a1 + 136) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 136);
      if ( *(_WORD *)(a1 + 146) )
        operator delete((void *)a1);
    }
  }
}

```

## disassembly

```asm
0x18022b880  mov     [rsp+Block], rcx
0x18022b885  push    rbx
0x18022b886  push    rsi
0x18022b887  push    rdi
0x18022b888  push    r12
0x18022b88a  push    r13
0x18022b88c  push    r14
0x18022b88e  push    r15
0x18022b890  sub     rsp, 0F0h
0x18022b897  mov     rdi, [rsp+128h+Block]
0x18022b89f  movzx   eax, word ptr [rdi+90h]
0x18022b8a6  mov     [rsp+128h+var_108], ax
0x18022b8ab  inc     ax; switch 9 cases
0x18022b8ae  cmp     ax, 8
0x18022b8b2  ja      def_18022B8CD; jumptable 000000018022B8CD default case, cases 0,4,5
0x18022b8b8  movsx   rax, ax
0x18022b8bc  lea     rdx, cs:180000000h
0x18022b8c3  mov     ecx, ds:(jpt_18022B8CD - 180000000h)[rdx+rax*4]
0x18022b8ca  add     rcx, rdx
0x18022b8cd  jmp     rcx; switch jump
0x18022b8cf  jmp     loc_18022BD65; jumptable 000000018022B8CD case 3
0x18022b8d4  xor     esi, esi; jumptable 000000018022B8CD case 2
0x18022b8d6  lea     r14, [rdi+80h]
0x18022b8dd  mov     r15, [r14]
0x18022b8e0  lea     rbx, [rdi+98h]
0x18022b8e7  mov     r8b, 1
0x18022b8ea  mov     rdx, rbx
0x18022b8ed  mov     rcx, r15
0x18022b8f0  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18022b8f5  nop
0x18022b8f6  cmp     [r15+0CBh], sil
0x18022b8fd  jnz     loc_18022BB53
0x18022b903  movzx   eax, byte ptr [r15+0CAh]
0x18022b90b  test    al, al
0x18022b90d  jz      loc_18022BB53
0x18022b913  mov     byte ptr [r15+0CBh], 1
0x18022b91b  lea     rcx, [rdi+0A8h]
0x18022b922  call    ?Make@CancellationTokenSourceCore@details@asg@@SA?AV?$shared_ptr@UCancellationTokenSourceCore@details@asg@@@std@@XZ; asg::details::CancellationTokenSourceCore::Make(void)
0x18022b927  nop
0x18022b928  mov     rcx, [r15+0D8h]; hEvent
0x18022b92f  call    cs:__imp_ResetEvent
0x18022b935  mov     rcx, [rsp+128h]; this
0x18022b93d  test    eax, eax
0x18022b93f  jnz     short loc_18022B953
0x18022b941  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18022b948  mov     edx, 9CCh; void *
0x18022b94d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18022b953  lea     r9, [rdi+0B8h]
0x18022b95a  mov     rax, [rdi+0A8h]
0x18022b961  mov     [rsp+128h+var_F8], rax
0x18022b966  mov     [r9], rax
0x18022b969  mov     rax, [rdi+0B0h]
0x18022b970  mov     [rsp+128h+var_F0], rax
0x18022b975  mov     [rdi+0C0h], rax
0x18022b97c  mov     [rdi+0A8h], rsi
0x18022b983  mov     [rdi+0B0h], rsi
0x18022b98a  lea     r8, [rdi+0C8h]
0x18022b991  mov     rdx, [rdi+88h]
0x18022b998  mov     [r8], rdx
0x18022b99b  test    rdx, rdx
0x18022b99e  jz      short loc_18022B9C6
0x18022b9a0  mov     rax, [rdx+8]
0x18022b9a4  test    rax, rax
0x18022b9a7  js      short loc_18022B9C1
0x18022b9a9  nop     dword ptr [rax+00000000h]
0x18022b9b0  lea     rcx, [rax+1]
0x18022b9b4  lock cmpxchg [rdx+8], rcx
0x18022b9ba  jz      short loc_18022B9C6
0x18022b9bc  test    rax, rax
0x18022b9bf  jns     short loc_18022B9B0
0x18022b9c1  lock inc dword ptr [rax+rax+18h]
0x18022b9c6  lea     rdx, [rdi+0D0h]
0x18022b9cd  mov     rcx, r15
0x18022b9d0  call    ??$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUIAsyncAction@Foundation@Windows@7@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@UCancellationTokenSource@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource)
0x18022b9d5  mov     rbx, rax
0x18022b9d8  lea     r14, [r15+0D0h]
0x18022b9df  cmp     r14, rax
0x18022b9e2  jz      short loc_18022B9FB
0x18022b9e4  cmp     qword ptr [r14], 0
0x18022b9e8  jz      short loc_18022B9F2
0x18022b9ea  mov     rcx, r14
0x18022b9ed  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b9f2  mov     rax, [rbx]
0x18022b9f5  mov     [rbx], rsi
0x18022b9f8  mov     [r14], rax
0x18022b9fb  mov     rax, [rdi+0D0h]
0x18022ba02  mov     [rsp+128h+arg_8], rax
0x18022ba0a  test    rax, rax
0x18022ba0d  jz      short loc_18022BA1B
0x18022ba0f  lea     rcx, [rdi+0D0h]
0x18022ba16  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022ba1b  lea     rbx, [rdi+0E0h]
0x18022ba22  mov     rcx, [r14]
0x18022ba25  mov     [rbx], rcx
0x18022ba28  test    rcx, rcx
0x18022ba2b  jz      short loc_18022BA3A
0x18022ba2d  mov     rax, [rcx]
0x18022ba30  mov     rax, [rax+8]
0x18022ba34  call    cs:__guard_dispatch_icall_fptr
0x18022ba3a  mov     [rdi+130h], rbx
0x18022ba41  lea     r15, [rdi+168h]
0x18022ba48  mov     rax, [rbx]
0x18022ba4b  mov     [rbx], rsi
0x18022ba4e  mov     [r15], rax
0x18022ba51  mov     [rdi+170h], r15
0x18022ba58  mov     ecx, 18h; Size
0x18022ba5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022ba62  mov     r14, rax
0x18022ba65  mov     dword ptr [rax+8], 1
0x18022ba6c  mov     rcx, [r15]
0x18022ba6f  mov     [r15], rsi
0x18022ba72  mov     [rax+10h], rcx
0x18022ba76  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022ba7d  lea     rax, ??_7?$variadic_delegate@V_lambda_1_@?6???$PerformMaintenanceAsync@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUIAsyncAction@Foundation@Windows@9@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@@Z@X$$V@impl@winrt@@6B@; const winrt::impl::variadic_delegate<`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>)'::`7'::_lambda_1_,void,>::`vftable'
0x18022ba84  mov     [r14], rax
0x18022ba87  lea     r13, [rdi+0D8h]
0x18022ba8e  mov     [r13+0], r14
0x18022ba92  mov     rax, [r15]
0x18022ba95  mov     [rsp+128h+arg_18], rax
0x18022ba9d  mov     rcx, rbx
0x18022baa0  test    rax, rax
0x18022baa3  jz      short loc_18022BAB4
0x18022baa5  mov     rcx, r15
0x18022baa8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022baad  lea     rcx, [rdi+0E0h]
0x18022bab4  mov     rax, [rbx]
0x18022bab7  mov     [rsp+128h+var_100], rax
0x18022babc  mov     r15, r13
0x18022babf  test    rax, rax
0x18022bac2  jz      short loc_18022BAD0
0x18022bac4  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022bac9  lea     r15, [rdi+0D8h]
0x18022bad0  lea     rcx, [rdi+58h]; SRWLock
0x18022bad4  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18022bad9  mov     eax, [rdi+70h]
0x18022badc  cmp     eax, 2
0x18022badf  jz      short loc_18022BB15
0x18022bae1  lea     r12, [rdi+68h]
0x18022bae5  cmp     r12, r13
0x18022bae8  jz      short loc_18022BB0A
0x18022baea  cmp     qword ptr [r12], 0
0x18022baef  jz      short loc_18022BB00
0x18022baf1  mov     rcx, r12
0x18022baf4  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022baf9  lea     r15, [rdi+0D8h]
0x18022bb00  mov     [r15], rsi
0x18022bb03  mov     [r12], r14
0x18022bb07  mov     r14, rsi
0x18022bb0a  lea     rcx, [rdi+58h]; SRWLock
0x18022bb0e  call    ReleaseSRWLockExclusive_0
0x18022bb13  jmp     short loc_18022BB2F
0x18022bb15  lea     rcx, [rdi+58h]; SRWLock
0x18022bb19  call    ReleaseSRWLockExclusive_0
0x18022bb1e  mov     rax, [r14]
0x18022bb21  mov     rcx, r14
0x18022bb24  mov     rax, [rax+18h]
0x18022bb28  call    cs:__guard_dispatch_icall_fptr
0x18022bb2e  nop
0x18022bb2f  mov     [rsp+128h+arg_10], r14
0x18022bb37  test    r14, r14
0x18022bb3a  jz      short loc_18022BB45
0x18022bb3c  mov     rcx, r15
0x18022bb3f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022bb44  nop
0x18022bb45  lea     rbx, [rdi+98h]
0x18022bb4c  lea     r14, [rdi+80h]
0x18022bb53  movzx   eax, byte ptr [rdi+0A0h]
0x18022bb5a  mov     [rsp+128h+var_E0], al
0x18022bb5e  test    al, al
0x18022bb60  jz      short loc_18022BB6F
0x18022bb62  mov     rcx, [rbx]; _Mtx_t
0x18022bb65  mov     [rsp+128h+var_E8], rcx
0x18022bb6a  call    _Mtx_unlock
0x18022bb6f  mov     rax, [r14]
0x18022bb72  mov     rcx, [rax+0D8h]
0x18022bb79  mov     [rdi+0F0h], rsi
0x18022bb80  mov     [rdi+0F8h], rsi
0x18022bb87  mov     [rdi+100h], rsi
0x18022bb8e  mov     [rdi+108h], rcx
0x18022bb95  mov     [rdi+110h], esi
0x18022bb9b  mov     [rdi+118h], rsi
0x18022bba2  mov     [rdi+120h], esi
0x18022bba8  mov     eax, [rdi+70h]
0x18022bbab  cmp     eax, 2
0x18022bbae  jnz     short loc_18022BBF3
0x18022bbb0  lea     rdx, [rdi+138h]; struct winrt::impl::slim_source_location *
0x18022bbb7  mov     dword ptr [rdx], 1628h
0x18022bbbd  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022bbc4  mov     [rdi+140h], rax
0x18022bbcb  mov     [rdi+148h], rsi
0x18022bbd2  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18022bbda  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022bbdf  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022bbe6  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18022bbee  call    _CxxThrowException
0x18022bbf3  mov     rcx, [rdi+108h]; hHandle
0x18022bbfa  mov     [rsp+128h+var_C0], rcx
0x18022bbff  xor     edx, edx; dwMilliseconds
0x18022bc01  call    WaitForSingleObject_0
0x18022bc06  test    eax, eax
0x18022bc08  jz      short loc_18022BC88
0x18022bc0a  mov     eax, 6
0x18022bc0f  mov     [rdi+90h], ax
0x18022bc16  mov     rdx, rdi
0x18022bc19  lea     rcx, [rdi+0F0h]
0x18022bc20  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@signal_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@std@@@Z; winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>)
0x18022bc25  jmp     loc_18022BDDD
0x18022bc2a  mov     rcx, [rdi+0F8h]; jumptable 000000018022B8CD case 7
0x18022bc31  mov     [rsp+128h+var_D0], rcx
0x18022bc36  test    rcx, rcx
0x18022bc39  jz      short loc_18022BC50
0x18022bc3b  mov     [rsp+128h+var_D0], rcx
0x18022bc40  call    CloseThreadpoolWait_0
0x18022bc45  xor     esi, esi
0x18022bc47  mov     [rdi+0F8h], rsi
0x18022bc4e  jmp     short loc_18022BC52
0x18022bc50  xor     esi, esi
0x18022bc52  mov     rbx, [rdi+0F0h]
0x18022bc59  test    rbx, rbx
0x18022bc5c  jz      short loc_18022BC81
0x18022bc5e  mov     [rsp+128h+var_D8], rbx
0x18022bc63  mov     rax, rsi
0x18022bc66  xchg    rax, [rbx]
0x18022bc69  cmp     rax, 1
0x18022bc6d  jnz     short loc_18022BC81
0x18022bc6f  nop
0x18022bc70  call    _Thrd_yield
0x18022bc75  mov     rax, rsi
0x18022bc78  xchg    rax, [rbx]
0x18022bc7b  cmp     rax, 1
0x18022bc7f  jz      short loc_18022BC70
0x18022bc81  jmp     loc_18022BD65; jumptable 000000018022B8CD cases -1,1
0x18022bc86  xor     esi, esi; jumptable 000000018022B8CD case 6
0x18022bc88  mov     eax, esi
0x18022bc8a  xchg    eax, [rdi+120h]
0x18022bc90  cmp     eax, 2
0x18022bc93  jnz     short loc_18022BCD9
0x18022bc95  lea     rdx, [rdi+150h]; struct winrt::impl::slim_source_location *
0x18022bc9c  mov     dword ptr [rdx], 24C2h
0x18022bca2  lea     rax, aCW1SX64Release_13; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022bca9  mov     [rdi+158h], rax
0x18022bcb0  mov     [rdi+160h], rsi
0x18022bcb7  lea     rcx, [rsp+128h+var_88]; this
0x18022bcbf  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022bcc4  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022bccb  lea     rcx, [rsp+128h+var_88]; pExceptionObject
0x18022bcd3  call    _CxxThrowException
0x18022bcd9  mov     rcx, [rdi+0F8h]; pwa
0x18022bce0  mov     [rsp+128h+var_D0], rcx
0x18022bce5  test    rcx, rcx
0x18022bce8  jz      short loc_18022BCFB
0x18022bcea  mov     [rsp+128h+var_D0], rcx
0x18022bcef  call    CloseThreadpoolWait_0
0x18022bcf4  mov     [rdi+0F8h], rsi
0x18022bcfb  mov     rbx, [rdi+0F0h]
0x18022bd02  test    rbx, rbx
0x18022bd05  jz      short loc_18022BD29
0x18022bd07  mov     [rsp+128h+var_D8], rbx
0x18022bd0c  mov     rax, rsi
0x18022bd0f  xchg    rax, [rbx]
0x18022bd12  cmp     rax, 1
0x18022bd16  jnz     short loc_18022BD29
0x18022bd18  call    _Thrd_yield
0x18022bd1d  mov     rax, rsi
0x18022bd20  xchg    rax, [rbx]
0x18022bd23  cmp     rax, 1
0x18022bd27  jz      short loc_18022BD18
0x18022bd29  mov     rcx, [rdi+80h]
0x18022bd30  call    ?EnsureNotCorrupted@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBAXXZ; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::EnsureNotCorrupted(void)
0x18022bd35  nop
0x18022bd36  jmp     short loc_18022BD42
0x18022bd38  xor     esi, esi
0x18022bd3a  mov     rdi, [rsp+128h+Block]
0x18022bd42  lea     rax, [rdi+10h]
0x18022bd46  lea     rcx, [rdi+128h]
0x18022bd4d  mov     [rcx], rax
0x18022bd50  xor     eax, eax
0x18022bd52  mov     [rdi+90h], ax
0x18022bd59  mov     [rdi], rsi
0x18022bd5c  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@4@UCancellationTokenSource@asg@@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18022bd61  test    al, al
0x18022bd63  jnz     short loc_18022BDDD
0x18022bd65  lea     rcx, [rdi+68h]; jumptable 000000018022B8CD cases -1,1
0x18022bd69  cmp     qword ptr [rcx], 0
0x18022bd6d  jz      short loc_18022BD74
0x18022bd6f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022bd74  lea     rcx, [rdi+60h]
0x18022bd78  cmp     qword ptr [rcx], 0
0x18022bd7c  jz      short loc_18022BD83
0x18022bd7e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022bd83  lea     rcx, [rdi+48h]; void *
0x18022bd87  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18022bd8c  lea     rcx, [rdi+10h]
0x18022bd90  call    ?subtract_final_reference@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@U12@V?$map@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(void)
0x18022bd95  mov     eax, 0FFFFFFFFh
0x18022bd9a  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022bda2  sub     eax, 1
0x18022bda5  jz      short loc_18022BDB1
0x18022bda7  test    eax, eax
0x18022bda9  jns     short loc_18022BDB1
  ... truncated ...
```
