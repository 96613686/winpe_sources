# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___

- ea: `0x180237100`
- end: `0x180237698`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___`
- size: `1432`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180049f60`
- `0x1802370f0`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x18000b2a0`
- `0x1800176b0`
- `0x180020670`
- `0x18002cd70`
- `0x18002f2e0`
- `0x18002f8e0`
- `0x180046940`
- `0x180047520`
- `0x180054490`
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
- `0x180237100`
- `0x180242120`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x1802371af`
- `KERNEL32!ResetEvent` at `0x1802371af`

## string_xrefs

- `0x180237522`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\base.h`
- `0x1802371c1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.27\inc\wil\opensource\wil\resource.h`
- `0x18023743d`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::PerformMaintenanceAsync__ResumeCoro_1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___(
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
  v11 = (__int64 *)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>>(
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
  *(_QWORD *)v17 = ___7__variadic_delegate_V_lambda_1___6____PerformMaintenanceAsync_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AUIAsyncAction_Foundation_Windows_9_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9__Z_X__V_impl_winrt__6B_;
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
0x180237100  mov     [rsp+Block], rcx
0x180237105  push    rbx
0x180237106  push    rsi
0x180237107  push    rdi
0x180237108  push    r12
0x18023710a  push    r13
0x18023710c  push    r14
0x18023710e  push    r15
0x180237110  sub     rsp, 0F0h
0x180237117  mov     rdi, [rsp+128h+Block]
0x18023711f  movzx   eax, word ptr [rdi+90h]
0x180237126  mov     [rsp+128h+var_108], ax
0x18023712b  inc     ax; switch 9 cases
0x18023712e  cmp     ax, 8
0x180237132  ja      def_18023714D; jumptable 000000018023714D default case, cases 0,4,5
0x180237138  movsx   rax, ax
0x18023713c  lea     rdx, cs:180000000h
0x180237143  mov     ecx, ds:(jpt_18023714D - 180000000h)[rdx+rax*4]
0x18023714a  add     rcx, rdx
0x18023714d  jmp     rcx; switch jump
0x18023714f  jmp     loc_1802375E5; jumptable 000000018023714D case 3
0x180237154  xor     esi, esi; jumptable 000000018023714D case 2
0x180237156  lea     r14, [rdi+80h]
0x18023715d  mov     r15, [r14]
0x180237160  lea     rbx, [rdi+98h]
0x180237167  mov     r8b, 1
0x18023716a  mov     rdx, rbx
0x18023716d  mov     rcx, r15
0x180237170  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x180237175  nop
0x180237176  cmp     [r15+0CBh], sil
0x18023717d  jnz     loc_1802373D3
0x180237183  movzx   eax, byte ptr [r15+0CAh]
0x18023718b  test    al, al
0x18023718d  jz      loc_1802373D3
0x180237193  mov     byte ptr [r15+0CBh], 1
0x18023719b  lea     rcx, [rdi+0A8h]
0x1802371a2  call    ?Make@CancellationTokenSourceCore@details@asg@@SA?AV?$shared_ptr@UCancellationTokenSourceCore@details@asg@@@std@@XZ; asg::details::CancellationTokenSourceCore::Make(void)
0x1802371a7  nop
0x1802371a8  mov     rcx, [r15+0D8h]; hEvent
0x1802371af  call    cs:__imp_ResetEvent
0x1802371b5  mov     rcx, [rsp+128h]; this
0x1802371bd  test    eax, eax
0x1802371bf  jnz     short loc_1802371D3
0x1802371c1  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1802371c8  mov     edx, 9CCh; void *
0x1802371cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1802371d3  lea     r9, [rdi+0B8h]
0x1802371da  mov     rax, [rdi+0A8h]
0x1802371e1  mov     [rsp+128h+var_F8], rax
0x1802371e6  mov     [r9], rax
0x1802371e9  mov     rax, [rdi+0B0h]
0x1802371f0  mov     [rsp+128h+var_F0], rax
0x1802371f5  mov     [rdi+0C0h], rax
0x1802371fc  mov     [rdi+0A8h], rsi
0x180237203  mov     [rdi+0B0h], rsi
0x18023720a  lea     r8, [rdi+0C8h]
0x180237211  mov     rdx, [rdi+88h]
0x180237218  mov     [r8], rdx
0x18023721b  test    rdx, rdx
0x18023721e  jz      short loc_180237246
0x180237220  mov     rax, [rdx+8]
0x180237224  test    rax, rax
0x180237227  js      short loc_180237241
0x180237229  nop     dword ptr [rax+00000000h]
0x180237230  lea     rcx, [rax+1]
0x180237234  lock cmpxchg [rdx+8], rcx
0x18023723a  jz      short loc_180237246
0x18023723c  test    rax, rax
0x18023723f  jns     short loc_180237230
0x180237241  lock inc dword ptr [rax+rax+18h]
0x180237246  lea     rdx, [rdi+0D0h]
0x18023724d  mov     rcx, r15
0x180237250  call    ??$PerformMaintenanceCoreAsync@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUIAsyncAction@Foundation@Windows@7@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@UCancellationTokenSource@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceCoreAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>,asg::CancellationTokenSource)
0x180237255  mov     rbx, rax
0x180237258  lea     r14, [r15+0D0h]
0x18023725f  cmp     r14, rax
0x180237262  jz      short loc_18023727B
0x180237264  cmp     qword ptr [r14], 0
0x180237268  jz      short loc_180237272
0x18023726a  mov     rcx, r14
0x18023726d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180237272  mov     rax, [rbx]
0x180237275  mov     [rbx], rsi
0x180237278  mov     [r14], rax
0x18023727b  mov     rax, [rdi+0D0h]
0x180237282  mov     [rsp+128h+arg_8], rax
0x18023728a  test    rax, rax
0x18023728d  jz      short loc_18023729B
0x18023728f  lea     rcx, [rdi+0D0h]
0x180237296  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023729b  lea     rbx, [rdi+0E0h]
0x1802372a2  mov     rcx, [r14]
0x1802372a5  mov     [rbx], rcx
0x1802372a8  test    rcx, rcx
0x1802372ab  jz      short loc_1802372BA
0x1802372ad  mov     rax, [rcx]
0x1802372b0  mov     rax, [rax+8]
0x1802372b4  call    cs:__guard_dispatch_icall_fptr
0x1802372ba  mov     [rdi+130h], rbx
0x1802372c1  lea     r15, [rdi+168h]
0x1802372c8  mov     rax, [rbx]
0x1802372cb  mov     [rbx], rsi
0x1802372ce  mov     [r15], rax
0x1802372d1  mov     [rdi+170h], r15
0x1802372d8  mov     ecx, 18h; Size
0x1802372dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802372e2  mov     r14, rax
0x1802372e5  mov     dword ptr [rax+8], 1
0x1802372ec  mov     rcx, [r15]
0x1802372ef  mov     [r15], rsi
0x1802372f2  mov     [rax+10h], rcx
0x1802372f6  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802372fd  lea     rax, ??_7?$variadic_delegate@V_lambda_1_@?6???$PerformMaintenanceAsync@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUIAsyncAction@Foundation@Windows@9@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@@Z@X$$V@impl@winrt@@6B@; const winrt::impl::variadic_delegate<`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::PerformMaintenanceAsync<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>)'::`7'::_lambda_1_,void,>::`vftable'
0x180237304  mov     [r14], rax
0x180237307  lea     r13, [rdi+0D8h]
0x18023730e  mov     [r13+0], r14
0x180237312  mov     rax, [r15]
0x180237315  mov     [rsp+128h+arg_18], rax
0x18023731d  mov     rcx, rbx
0x180237320  test    rax, rax
0x180237323  jz      short loc_180237334
0x180237325  mov     rcx, r15
0x180237328  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023732d  lea     rcx, [rdi+0E0h]
0x180237334  mov     rax, [rbx]
0x180237337  mov     [rsp+128h+var_100], rax
0x18023733c  mov     r15, r13
0x18023733f  test    rax, rax
0x180237342  jz      short loc_180237350
0x180237344  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180237349  lea     r15, [rdi+0D8h]
0x180237350  lea     rcx, [rdi+58h]; SRWLock
0x180237354  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180237359  mov     eax, [rdi+70h]
0x18023735c  cmp     eax, 2
0x18023735f  jz      short loc_180237395
0x180237361  lea     r12, [rdi+68h]
0x180237365  cmp     r12, r13
0x180237368  jz      short loc_18023738A
0x18023736a  cmp     qword ptr [r12], 0
0x18023736f  jz      short loc_180237380
0x180237371  mov     rcx, r12
0x180237374  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180237379  lea     r15, [rdi+0D8h]
0x180237380  mov     [r15], rsi
0x180237383  mov     [r12], r14
0x180237387  mov     r14, rsi
0x18023738a  lea     rcx, [rdi+58h]; SRWLock
0x18023738e  call    ReleaseSRWLockExclusive_0
0x180237393  jmp     short loc_1802373AF
0x180237395  lea     rcx, [rdi+58h]; SRWLock
0x180237399  call    ReleaseSRWLockExclusive_0
0x18023739e  mov     rax, [r14]
0x1802373a1  mov     rcx, r14
0x1802373a4  mov     rax, [rax+18h]
0x1802373a8  call    cs:__guard_dispatch_icall_fptr
0x1802373ae  nop
0x1802373af  mov     [rsp+128h+arg_10], r14
0x1802373b7  test    r14, r14
0x1802373ba  jz      short loc_1802373C5
0x1802373bc  mov     rcx, r15
0x1802373bf  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802373c4  nop
0x1802373c5  lea     rbx, [rdi+98h]
0x1802373cc  lea     r14, [rdi+80h]
0x1802373d3  movzx   eax, byte ptr [rdi+0A0h]
0x1802373da  mov     [rsp+128h+var_E0], al
0x1802373de  test    al, al
0x1802373e0  jz      short loc_1802373EF
0x1802373e2  mov     rcx, [rbx]; _Mtx_t
0x1802373e5  mov     [rsp+128h+var_E8], rcx
0x1802373ea  call    _Mtx_unlock
0x1802373ef  mov     rax, [r14]
0x1802373f2  mov     rcx, [rax+0D8h]
0x1802373f9  mov     [rdi+0F0h], rsi
0x180237400  mov     [rdi+0F8h], rsi
0x180237407  mov     [rdi+100h], rsi
0x18023740e  mov     [rdi+108h], rcx
0x180237415  mov     [rdi+110h], esi
0x18023741b  mov     [rdi+118h], rsi
0x180237422  mov     [rdi+120h], esi
0x180237428  mov     eax, [rdi+70h]
0x18023742b  cmp     eax, 2
0x18023742e  jnz     short loc_180237473
0x180237430  lea     rdx, [rdi+138h]; struct winrt::impl::slim_source_location *
0x180237437  mov     dword ptr [rdx], 1628h
0x18023743d  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180237444  mov     [rdi+140h], rax
0x18023744b  mov     [rdi+148h], rsi
0x180237452  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18023745a  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023745f  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180237466  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18023746e  call    _CxxThrowException
0x180237473  mov     rcx, [rdi+108h]; hHandle
0x18023747a  mov     [rsp+128h+var_C0], rcx
0x18023747f  xor     edx, edx; dwMilliseconds
0x180237481  call    WaitForSingleObject_0
0x180237486  test    eax, eax
0x180237488  jz      short loc_180237508
0x18023748a  mov     eax, 6
0x18023748f  mov     [rdi+90h], ax
0x180237496  mov     rdx, rdi
0x180237499  lea     rcx, [rdi+0F0h]
0x1802374a0  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@signal_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@std@@@Z; winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>)
0x1802374a5  jmp     loc_18023765D
0x1802374aa  mov     rcx, [rdi+0F8h]; jumptable 000000018023714D case 7
0x1802374b1  mov     [rsp+128h+var_D0], rcx
0x1802374b6  test    rcx, rcx
0x1802374b9  jz      short loc_1802374D0
0x1802374bb  mov     [rsp+128h+var_D0], rcx
0x1802374c0  call    CloseThreadpoolWait_0
0x1802374c5  xor     esi, esi
0x1802374c7  mov     [rdi+0F8h], rsi
0x1802374ce  jmp     short loc_1802374D2
0x1802374d0  xor     esi, esi
0x1802374d2  mov     rbx, [rdi+0F0h]
0x1802374d9  test    rbx, rbx
0x1802374dc  jz      short loc_180237501
0x1802374de  mov     [rsp+128h+var_D8], rbx
0x1802374e3  mov     rax, rsi
0x1802374e6  xchg    rax, [rbx]
0x1802374e9  cmp     rax, 1
0x1802374ed  jnz     short loc_180237501
0x1802374ef  nop
0x1802374f0  call    _Thrd_yield
0x1802374f5  mov     rax, rsi
0x1802374f8  xchg    rax, [rbx]
0x1802374fb  cmp     rax, 1
0x1802374ff  jz      short loc_1802374F0
0x180237501  jmp     loc_1802375E5; jumptable 000000018023714D cases -1,1
0x180237506  xor     esi, esi; jumptable 000000018023714D case 6
0x180237508  mov     eax, esi
0x18023750a  xchg    eax, [rdi+120h]
0x180237510  cmp     eax, 2
0x180237513  jnz     short loc_180237559
0x180237515  lea     rdx, [rdi+150h]; struct winrt::impl::slim_source_location *
0x18023751c  mov     dword ptr [rdx], 24C2h
0x180237522  lea     rax, aCW1SX64Release_13; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180237529  mov     [rdi+158h], rax
0x180237530  mov     [rdi+160h], rsi
0x180237537  lea     rcx, [rsp+128h+var_88]; this
0x18023753f  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180237544  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18023754b  lea     rcx, [rsp+128h+var_88]; pExceptionObject
0x180237553  call    _CxxThrowException
0x180237559  mov     rcx, [rdi+0F8h]; pwa
0x180237560  mov     [rsp+128h+var_D0], rcx
0x180237565  test    rcx, rcx
0x180237568  jz      short loc_18023757B
0x18023756a  mov     [rsp+128h+var_D0], rcx
0x18023756f  call    CloseThreadpoolWait_0
0x180237574  mov     [rdi+0F8h], rsi
0x18023757b  mov     rbx, [rdi+0F0h]
0x180237582  test    rbx, rbx
0x180237585  jz      short loc_1802375A9
0x180237587  mov     [rsp+128h+var_D8], rbx
0x18023758c  mov     rax, rsi
0x18023758f  xchg    rax, [rbx]
0x180237592  cmp     rax, 1
0x180237596  jnz     short loc_1802375A9
0x180237598  call    _Thrd_yield
0x18023759d  mov     rax, rsi
0x1802375a0  xchg    rax, [rbx]
0x1802375a3  cmp     rax, 1
0x1802375a7  jz      short loc_180237598
0x1802375a9  mov     rcx, [rdi+80h]
0x1802375b0  call    ?EnsureNotCorrupted@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBAXXZ; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::EnsureNotCorrupted(void)
0x1802375b5  nop
0x1802375b6  jmp     short loc_1802375C2
0x1802375b8  xor     esi, esi
0x1802375ba  mov     rdi, [rsp+128h+Block]
0x1802375c2  lea     rax, [rdi+10h]
0x1802375c6  lea     rcx, [rdi+128h]
0x1802375cd  mov     [rcx], rax
0x1802375d0  xor     eax, eax
0x1802375d2  mov     [rdi+90h], ax
0x1802375d9  mov     [rdi], rsi
0x1802375dc  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@4@UCancellationTokenSource@asg@@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x1802375e1  test    al, al
0x1802375e3  jnz     short loc_18023765D
0x1802375e5  lea     rcx, [rdi+68h]; jumptable 000000018023714D cases -1,1
0x1802375e9  cmp     qword ptr [rcx], 0
0x1802375ed  jz      short loc_1802375F4
0x1802375ef  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802375f4  lea     rcx, [rdi+60h]
0x1802375f8  cmp     qword ptr [rcx], 0
0x1802375fc  jz      short loc_180237603
0x1802375fe  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180237603  lea     rcx, [rdi+48h]; void *
0x180237607  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18023760c  lea     rcx, [rdi+10h]
0x180237610  call    ?subtract_final_reference@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@U12@V?$map@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(void)
0x180237615  mov     eax, 0FFFFFFFFh
0x18023761a  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180237622  sub     eax, 1
0x180237625  jz      short loc_180237631
0x180237627  test    eax, eax
0x180237629  jns     short loc_180237631
  ... truncated ...
```
