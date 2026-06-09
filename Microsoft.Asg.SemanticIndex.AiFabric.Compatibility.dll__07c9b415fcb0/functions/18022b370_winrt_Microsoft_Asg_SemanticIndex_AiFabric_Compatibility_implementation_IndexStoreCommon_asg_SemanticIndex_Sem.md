# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::CancelMaintenanceAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___

- ea: `0x18022b370`
- end: `0x18022b868`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::CancelMaintenanceAsync$_ResumeCoro$1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___`
- size: `1272`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a950`
- `0x18004a0f0`
- `0x18022aee0`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x18000b2a0`
- `0x180010dd0`
- `0x180020670`
- `0x18002cd70`
- `0x18002f8e0`
- `0x180047520`
- `0x180078da0`
- `0x1801d1e70`
- `0x1801d2b20`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x180229032`
- `0x18022b370`
- `0x180242120`

## string_xrefs

- `0x18022b6c3`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\base.h`
- `0x18022b4bb`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022b527`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::CancelMaintenanceAsync__ResumeCoro_1_winrt::com_ptr_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore___(
        _WORD *a1)
{
  _WORD *v2; // r15
  __int64 *v3; // rbx
  __int64 v4; // r13
  __int64 *v5; // rax
  __int64 v6; // r14
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  signed __int64 v11; // rax
  signed __int64 v12; // rtt
  __int64 v13; // rax
  struct _TP_WAIT *v14; // rcx
  volatile __int64 *v15; // rbx
  struct _TP_WAIT *v16; // rcx
  volatile __int64 *v17; // rbx
  _BYTE pExceptionObject[24]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v19[120]; // [rsp+90h] [rbp-78h] BYREF

  v2 = a1 + 72;
  switch ( a1[72] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_46;
    case 2:
      v3 = (__int64 *)(a1 + 76);
      *((_QWORD *)a1 + 19) = 0;
      v4 = *((_QWORD *)a1 + 16);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
        v4,
        a1 + 80,
        0);
      if ( !*(_BYTE *)(v4 + 203) )
      {
        if ( *((_BYTE *)a1 + 168) )
          Mtx_unlock(*((_Mtx_t *)a1 + 20));
        goto LABEL_45;
      }
      v5 = (__int64 *)(v4 + 208);
      v6 = 0;
      if ( v3 != (__int64 *)(v4 + 208) )
      {
        v6 = *v5;
        *v3 = *v5;
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      }
      if ( *((_BYTE *)a1 + 168) )
        Mtx_unlock(*((_Mtx_t *)a1 + 20));
      if ( v6 )
      {
        *((_QWORD *)a1 + 45) = 0;
        v7 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64))v6)(
               v6,
               &winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo>,
               (__int64)(a1 + 180));
        v8 = *((_QWORD *)a1 + 45);
        *((_QWORD *)a1 + 38) = v8;
        *((_DWORD *)a1 + 78) = 207;
        *((_QWORD *)a1 + 40) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 41) = 0;
        if ( v7 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v7, a1 + 156);
        }
        *((_DWORD *)a1 + 84) = 209;
        *((_QWORD *)a1 + 43) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 44) = 0;
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 72LL))(v8);
        if ( v9 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v9, a1 + 168);
        }
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
      }
      v10 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 22) = v10;
      if ( !v10 )
        goto LABEL_21;
      v11 = *(_QWORD *)(v10 + 8);
      if ( v11 < 0 )
        goto LABEL_20;
      break;
    case 4:
      goto LABEL_34;
    case 5:
      v14 = (struct _TP_WAIT *)*((_QWORD *)a1 + 24);
      if ( v14 )
      {
        CloseThreadpoolWait_0(v14);
        *((_QWORD *)a1 + 24) = 0;
      }
      v15 = (volatile __int64 *)*((_QWORD *)a1 + 23);
      if ( v15 && _InterlockedExchange64(v15, 0) == 1 )
      {
        do
          Thrd_yield();
        while ( _InterlockedExchange64(v15, 0) == 1 );
      }
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 88);
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 76);
      goto LABEL_46;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
    v12 = v11;
    v11 = _InterlockedCompareExchange64((volatile signed __int64 *)(v10 + 8), v11 + 1, v11);
    if ( v12 == v11 )
      break;
    if ( v11 < 0 )
    {
LABEL_20:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v11 + 24));
      break;
    }
  }
LABEL_21:
  v13 = *(_QWORD *)(v4 + 216);
  *((_QWORD *)a1 + 23) = 0;
  *((_QWORD *)a1 + 24) = 0;
  *((_QWORD *)a1 + 25) = 0;
  *((_QWORD *)a1 + 26) = v13;
  *((_DWORD *)a1 + 54) = 0;
  *((_QWORD *)a1 + 28) = 0;
  *((_DWORD *)a1 + 58) = 0;
  if ( *((_DWORD *)a1 + 28) == 2 )
  {
    *((_DWORD *)a1 + 64) = 5672;
    *((_QWORD *)a1 + 33) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fi"
                           "les\\winrt\\Windows.Foundation.h";
    *((_QWORD *)a1 + 34) = 0;
    winrt::hresult_canceled::hresult_canceled(
      (winrt::hresult_canceled *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)(a1 + 128));
    throw (winrt::hresult_canceled *)pExceptionObject;
  }
  if ( WaitForSingleObject_0(*((HANDLE *)a1 + 26), 0) )
  {
    *v2 = 4;
    winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>(
      (_QWORD *)a1 + 23,
      (__int64)a1);
    return;
  }
LABEL_34:
  if ( _InterlockedExchange((volatile __int32 *)a1 + 58, 0) == 2 )
  {
    *((_DWORD *)a1 + 70) = 9410;
    *((_QWORD *)a1 + 36) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fi"
                           "les\\winrt\\base.h";
    *((_QWORD *)a1 + 37) = 0;
    winrt::hresult_canceled::hresult_canceled(
      (winrt::hresult_canceled *)v19,
      (const struct winrt::impl::slim_source_location *)(a1 + 140));
    throw (winrt::hresult_canceled *)v19;
  }
  v16 = (struct _TP_WAIT *)*((_QWORD *)a1 + 24);
  if ( v16 )
  {
    CloseThreadpoolWait_0(v16);
    *((_QWORD *)a1 + 24) = 0;
  }
  v17 = (volatile __int64 *)*((_QWORD *)a1 + 23);
  if ( v17 && _InterlockedExchange64(v17, 0) == 1 )
  {
    do
      Thrd_yield();
    while ( _InterlockedExchange64(v17, 0) == 1 );
  }
  if ( *((_QWORD *)a1 + 22) )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 88);
  if ( *((_QWORD *)a1 + 19) )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 76);
LABEL_45:
  *((_QWORD *)a1 + 30) = a1 + 8;
  *v2 = 0;
  *(_QWORD *)a1 = 0;
  if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
  {
LABEL_46:
    if ( *((_QWORD *)a1 + 13) )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 52);
    if ( *((_QWORD *)a1 + 12) )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 48);
    __ExceptionPtrDestroy(a1 + 36);
    winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 8);
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    if ( *((_QWORD *)a1 + 17) )
      winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 68);
    if ( a1[73] )
      operator delete(a1);
  }
}

```

## disassembly

```asm
0x18022b370  mov     [rsp+Block], rcx
0x18022b375  push    rbx
0x18022b376  push    rsi
0x18022b377  push    rdi
0x18022b378  push    r12
0x18022b37a  push    r13
0x18022b37c  push    r14
0x18022b37e  push    r15
0x18022b380  sub     rsp, 0D0h
0x18022b387  mov     rdi, [rsp+108h+Block]
0x18022b38f  lea     r15, [rdi+90h]
0x18022b396  mov     [rsp+108h+arg_18], r15
0x18022b39e  movzx   eax, word ptr [r15]
0x18022b3a2  mov     [rsp+108h+var_E8], ax
0x18022b3a7  inc     ax; switch 7 cases
0x18022b3aa  cmp     ax, 6
0x18022b3ae  ja      def_18022B3C9; jumptable 000000018022B3C9 default case, case 0
0x18022b3b4  movsx   rax, ax
0x18022b3b8  lea     rdx, cs:180000000h
0x18022b3bf  mov     ecx, ds:(jpt_18022B3C9 - 180000000h)[rdx+rax*4]
0x18022b3c6  add     rcx, rdx
0x18022b3c9  jmp     rcx; switch jump
0x18022b3cb  jmp     loc_18022B7C0; jumptable 000000018022B3C9 case 3
0x18022b3d0  xor     esi, esi; jumptable 000000018022B3C9 case 2
0x18022b3d2  lea     rbx, [rdi+98h]
0x18022b3d9  mov     [rbx], rsi
0x18022b3dc  mov     r13, [rdi+80h]
0x18022b3e3  xor     r8d, r8d
0x18022b3e6  lea     rdx, [rdi+0A0h]
0x18022b3ed  mov     rcx, r13
0x18022b3f0  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18022b3f5  cmp     [r13+0CBh], sil
0x18022b3fc  jnz     short loc_18022B424
0x18022b3fe  movzx   eax, byte ptr [rdi+0A8h]
0x18022b405  mov     [rsp+108h+var_D8], al
0x18022b409  test    al, al
0x18022b40b  jz      short loc_18022B41F
0x18022b40d  mov     rcx, [rdi+0A0h]; _Mtx_t
0x18022b414  mov     [rsp+108h+var_E0], rcx
0x18022b419  call    _Mtx_unlock
0x18022b41e  nop
0x18022b41f  jmp     loc_18022B79F
0x18022b424  lea     rax, [r13+0D0h]
0x18022b42b  mov     r14, rsi
0x18022b42e  cmp     rbx, rax
0x18022b431  jz      short loc_18022B44E
0x18022b433  mov     r14, [rax]
0x18022b436  mov     [rbx], r14
0x18022b439  test    r14, r14
0x18022b43c  jz      short loc_18022B44E
0x18022b43e  mov     rax, [r14]
0x18022b441  mov     rcx, r14
0x18022b444  mov     rax, [rax+8]
0x18022b448  call    cs:__guard_dispatch_icall_fptr
0x18022b44e  movzx   eax, byte ptr [rdi+0A8h]
0x18022b455  mov     [rsp+108h+var_D8], al
0x18022b459  test    al, al
0x18022b45b  jz      short loc_18022B46E
0x18022b45d  mov     rcx, [rdi+0A0h]; _Mtx_t
0x18022b464  mov     [rsp+108h+var_E0], rcx
0x18022b469  call    _Mtx_unlock
0x18022b46e  test    r14, r14
0x18022b471  jz      loc_18022B527
0x18022b477  mov     [rdi+168h], rsi
0x18022b47e  mov     rax, [r14]
0x18022b481  lea     r8, [rdi+168h]
0x18022b488  lea     rdx, ??$guid_v@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo>
0x18022b48f  mov     rcx, r14
0x18022b492  mov     rax, [rax]
0x18022b495  call    cs:__guard_dispatch_icall_fptr
0x18022b49b  mov     rcx, [rdi+168h]
0x18022b4a2  mov     [rsp+108h+var_D0], rcx
0x18022b4a7  mov     [rdi+130h], rcx
0x18022b4ae  lea     rdx, [rdi+138h]
0x18022b4b5  mov     dword ptr [rdx], 0CFh
0x18022b4bb  lea     r14, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022b4c2  mov     [rdi+140h], r14
0x18022b4c9  mov     [rdi+148h], rsi
0x18022b4d0  test    eax, eax
0x18022b4d2  jns     short loc_18022B4DE
0x18022b4d4  lfence
0x18022b4d7  mov     ecx, eax
0x18022b4d9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022b4de  mov     dword ptr [rdi+150h], 0D1h
0x18022b4e8  mov     [rdi+158h], r14
0x18022b4ef  mov     [rdi+160h], rsi
0x18022b4f6  mov     rax, [rcx]
0x18022b4f9  mov     rax, [rax+48h]
0x18022b4fd  call    cs:__guard_dispatch_icall_fptr
0x18022b503  test    eax, eax
0x18022b505  jns     short loc_18022B519
0x18022b507  lfence
0x18022b50a  lea     rdx, [rdi+150h]
0x18022b511  mov     ecx, eax
0x18022b513  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022b519  lea     rcx, [rdi+130h]
0x18022b520  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b525  jmp     short loc_18022B52E
0x18022b527  lea     r14, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022b52e  mov     rdx, [rdi+88h]
0x18022b535  mov     [rdi+0B0h], rdx
0x18022b53c  test    rdx, rdx
0x18022b53f  jz      short loc_18022B566
0x18022b541  mov     rax, [rdx+8]
0x18022b545  test    rax, rax
0x18022b548  js      short loc_18022B561
0x18022b54a  nop     word ptr [rax+rax+00h]
0x18022b550  lea     rcx, [rax+1]
0x18022b554  lock cmpxchg [rdx+8], rcx
0x18022b55a  jz      short loc_18022B566
0x18022b55c  test    rax, rax
0x18022b55f  jns     short loc_18022B550
0x18022b561  lock inc dword ptr [rax+rax+18h]
0x18022b566  mov     rax, [r13+0D8h]
0x18022b56d  mov     [rdi+0B8h], rsi
0x18022b574  mov     [rdi+0C0h], rsi
0x18022b57b  mov     [rdi+0C8h], rsi
0x18022b582  mov     [rdi+0D0h], rax
0x18022b589  mov     [rdi+0D8h], esi
0x18022b58f  mov     [rdi+0E0h], rsi
0x18022b596  mov     [rdi+0E8h], esi
0x18022b59c  mov     eax, [rdi+70h]
0x18022b59f  cmp     eax, 2
0x18022b5a2  jnz     short loc_18022B5DA
0x18022b5a4  lea     rdx, [rdi+100h]; struct winrt::impl::slim_source_location *
0x18022b5ab  mov     dword ptr [rdx], 1628h
0x18022b5b1  mov     [rdi+108h], r14
0x18022b5b8  mov     [rdi+110h], rsi
0x18022b5bf  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18022b5c4  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022b5c9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022b5d0  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18022b5d5  call    _CxxThrowException
0x18022b5da  mov     rcx, [rdi+0D0h]; hHandle
0x18022b5e1  mov     [rsp+108h+var_B0], rcx
0x18022b5e6  xor     edx, edx; dwMilliseconds
0x18022b5e8  call    WaitForSingleObject_0
0x18022b5ed  test    eax, eax
0x18022b5ef  jz      loc_18022B6A9
0x18022b5f5  mov     eax, 4
0x18022b5fa  mov     [r15], ax
0x18022b5fe  mov     rdx, rdi
0x18022b601  lea     rcx, [rdi+0B8h]
0x18022b608  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@signal_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@std@@@Z; winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>)
0x18022b60d  jmp     loc_18022B838
0x18022b612  mov     rcx, [rdi+0C0h]; jumptable 000000018022B3C9 case 5
0x18022b619  mov     [rsp+108h+var_C0], rcx
0x18022b61e  test    rcx, rcx
0x18022b621  jz      short loc_18022B638
0x18022b623  mov     [rsp+108h+var_C0], rcx
0x18022b628  call    CloseThreadpoolWait_0
0x18022b62d  xor     esi, esi
0x18022b62f  mov     [rdi+0C0h], rsi
0x18022b636  jmp     short loc_18022B63A
0x18022b638  xor     esi, esi
0x18022b63a  mov     rbx, [rdi+0B8h]
0x18022b641  test    rbx, rbx
0x18022b644  jz      short loc_18022B668
0x18022b646  mov     [rsp+108h+var_C8], rbx
0x18022b64b  mov     rax, rsi
0x18022b64e  xchg    rax, [rbx]
0x18022b651  cmp     rax, 1
0x18022b655  jnz     short loc_18022B668
0x18022b657  call    _Thrd_yield
0x18022b65c  mov     rax, rsi
0x18022b65f  xchg    rax, [rbx]
0x18022b662  cmp     rax, 1
0x18022b666  jz      short loc_18022B657
0x18022b668  lea     rcx, [rdi+0B0h]
0x18022b66f  mov     rax, [rcx]
0x18022b672  mov     [rsp+108h+arg_8], rax
0x18022b67a  test    rax, rax
0x18022b67d  jz      short loc_18022B685
0x18022b67f  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022b684  nop
0x18022b685  lea     rcx, [rdi+98h]
0x18022b68c  mov     rax, [rcx]
0x18022b68f  mov     [rsp+108h+arg_10], rax
0x18022b697  test    rax, rax
0x18022b69a  jz      short loc_18022B6A2
0x18022b69c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b6a1  nop
0x18022b6a2  jmp     loc_18022B7C0; jumptable 000000018022B3C9 cases -1,1
0x18022b6a7  xor     esi, esi; jumptable 000000018022B3C9 case 4
0x18022b6a9  mov     eax, esi
0x18022b6ab  xchg    eax, [rdi+0E8h]
0x18022b6b1  cmp     eax, 2
0x18022b6b4  jnz     short loc_18022B6FA
0x18022b6b6  lea     rdx, [rdi+118h]; struct winrt::impl::slim_source_location *
0x18022b6bd  mov     dword ptr [rdx], 24C2h
0x18022b6c3  lea     rax, aCW1SX64Release_13; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022b6ca  mov     [rdi+120h], rax
0x18022b6d1  mov     [rdi+128h], rsi
0x18022b6d8  lea     rcx, [rsp+108h+var_78]; this
0x18022b6e0  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022b6e5  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022b6ec  lea     rcx, [rsp+108h+var_78]; pExceptionObject
0x18022b6f4  call    _CxxThrowException
0x18022b6fa  mov     rcx, [rdi+0C0h]; pwa
0x18022b701  mov     [rsp+108h+var_C0], rcx
0x18022b706  test    rcx, rcx
0x18022b709  jz      short loc_18022B71C
0x18022b70b  mov     [rsp+108h+var_C0], rcx
0x18022b710  call    CloseThreadpoolWait_0
0x18022b715  mov     [rdi+0C0h], rsi
0x18022b71c  mov     rbx, [rdi+0B8h]
0x18022b723  test    rbx, rbx
0x18022b726  jz      short loc_18022B751
0x18022b728  mov     [rsp+108h+var_C8], rbx
0x18022b72d  mov     rax, rsi
0x18022b730  xchg    rax, [rbx]
0x18022b733  cmp     rax, 1
0x18022b737  jnz     short loc_18022B751
0x18022b739  nop     dword ptr [rax+00000000h]
0x18022b740  call    _Thrd_yield
0x18022b745  mov     rax, rsi
0x18022b748  xchg    rax, [rbx]
0x18022b74b  cmp     rax, 1
0x18022b74f  jz      short loc_18022B740
0x18022b751  lea     rcx, [rdi+0B0h]
0x18022b758  mov     rax, [rcx]
0x18022b75b  mov     [rsp+108h+arg_8], rax
0x18022b763  test    rax, rax
0x18022b766  jz      short loc_18022B76E
0x18022b768  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022b76d  nop
0x18022b76e  lea     rcx, [rdi+98h]
0x18022b775  mov     rax, [rcx]
0x18022b778  mov     [rsp+108h+arg_10], rax
0x18022b780  test    rax, rax
0x18022b783  jz      short loc_18022B78B
0x18022b785  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b78a  nop
0x18022b78b  jmp     short loc_18022B79F
0x18022b78d  xor     esi, esi
0x18022b78f  mov     rdi, [rsp+108h+Block]
0x18022b797  mov     r15, [rsp+108h+arg_18]
0x18022b79f  lea     rcx, [rdi+0F0h]
0x18022b7a6  lea     rax, [rdi+10h]
0x18022b7aa  mov     [rcx], rax
0x18022b7ad  xor     eax, eax
0x18022b7af  mov     [r15], ax
0x18022b7b3  mov     [rdi], rsi
0x18022b7b6  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@4@UCancellationTokenSource@asg@@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18022b7bb  test    al, al
0x18022b7bd  jnz     short loc_18022B838
0x18022b7bf  nop
0x18022b7c0  lea     rcx, [rdi+68h]; jumptable 000000018022B3C9 cases -1,1
0x18022b7c4  cmp     qword ptr [rcx], 0
0x18022b7c8  jz      short loc_18022B7CF
0x18022b7ca  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b7cf  lea     rcx, [rdi+60h]
0x18022b7d3  cmp     qword ptr [rcx], 0
0x18022b7d7  jz      short loc_18022B7DE
0x18022b7d9  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b7de  lea     rcx, [rdi+48h]; void *
0x18022b7e2  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18022b7e7  lea     rcx, [rdi+10h]
0x18022b7eb  call    ?subtract_final_reference@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@U12@V?$map@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(void)
0x18022b7f0  mov     eax, 0FFFFFFFFh
0x18022b7f5  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022b7fd  sub     eax, 1
0x18022b800  jz      short loc_18022B80C
0x18022b802  test    eax, eax
0x18022b804  jns     short loc_18022B80C
0x18022b806  call    abort
0x18022b80c  lea     rcx, [rdi+88h]
0x18022b813  cmp     qword ptr [rcx], 0
0x18022b817  jz      short loc_18022B81E
0x18022b819  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022b81e  cmp     word ptr [rdi+92h], 0
0x18022b826  jz      short loc_18022B838
0x18022b828  mov     edx, 170h
0x18022b82d  mov     rcx, rdi; Block
0x18022b830  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18022b835  jmp     short loc_18022B838
0x18022b837  int     3; Trap to Debugger
0x18022b838  add     rsp, 0D0h
0x18022b83f  pop     r15
0x18022b841  pop     r14
0x18022b843  pop     r13
0x18022b845  pop     r12
0x18022b847  pop     rdi
0x18022b848  pop     rsi
0x18022b849  pop     rbx
0x18022b84a  retn
```
