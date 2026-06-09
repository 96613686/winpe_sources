# Pal::Detail::WrlTimerWrapper::start(std::function<void (void)> const &,Core::TimeSpan,Core::TimeSpan)

- ea: `0x18002cf9c`
- end: `0x18002d431`
- name: `?start@WrlTimerWrapper@Detail@Pal@@AEAAXAEBV?$function@$$A6AXXZ@std@@UTimeSpan@Core@@1@Z`
- size: `1173`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ce90`

## callees

- `0x18000d090`
- `0x18000dce0`
- `0x180016770`
- `0x180019f3c`
- `0x18001b9e0`
- `0x18001dd30`
- `0x180021da8`
- `0x180022140`
- `0x18002220c`
- `0x180024a34`
- `0x180025360`
- `0x180026430`
- `0x180027054`
- `0x1800279d0`
- `0x18002cf9c`
- `0x18002d9d8`
- `0x180098010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d12b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d24a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d335`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d12b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d24a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d335`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d136`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d255`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d340`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d136`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d255`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d340`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002d1a3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002d1a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d029`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d029`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d3ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d3ce`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d0e0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002d0e0`

## string_xrefs

- `0x18002d0ab`: `Windows.System.Threading.ThreadPoolTimer`
- `0x18002d0fe`: `Failed to retrieve the activation factory for Windows.System.Threading.ThreadPoolTimer`
- `0x18002d21d`: `TimerWrapper::start - CreateTimerWithCompletion failed`
- `0x18002d308`: `TimerWrapper::start - CreatePeriodicTimer failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Pal::Detail::WrlTimerWrapper::start(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // r13
  __int64 *v8; // rax
  __int64 v9; // r12
  __int64 *v10; // rax
  __int64 v11; // r15
  __int64 v12; // rsi
  int ActivationFactory; // eax
  unsigned int v14; // esi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 v20; // rsi
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, __int64, __int64, __int64, __int64); // rdi
  int v23; // ebx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 (__fastcall *v28)(__int64, __int64, unsigned __int64, __int64, __int64); // rdi
  int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // [rsp+30h] [rbp-208h] BYREF
  __int64 v35; // [rsp+38h] [rbp-200h] BYREF
  __int64 v36; // [rsp+40h] [rbp-1F8h]
  __int64 v37; // [rsp+48h] [rbp-1F0h]
  _BYTE v38[8]; // [rsp+50h] [rbp-1E8h] BYREF
  std::_Ref_count_base *v39; // [rsp+58h] [rbp-1E0h]
  _BYTE v40[8]; // [rsp+60h] [rbp-1D8h] BYREF
  std::_Ref_count_base *v41; // [rsp+68h] [rbp-1D0h]
  _BYTE v42[8]; // [rsp+70h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v43; // [rsp+78h] [rbp-1C0h]
  __int64 v44; // [rsp+80h] [rbp-1B8h]
  __int64 v45; // [rsp+88h] [rbp-1B0h]
  __int64 v46; // [rsp+90h] [rbp-1A8h]
  _BYTE pExceptionObject[24]; // [rsp+98h] [rbp-1A0h] BYREF
  _BYTE v48[24]; // [rsp+B0h] [rbp-188h] BYREF
  _BYTE v49[24]; // [rsp+C8h] [rbp-170h] BYREF
  _BYTE v50[16]; // [rsp+E0h] [rbp-158h] BYREF
  _BYTE v51[8]; // [rsp+F0h] [rbp-148h] BYREF
  _BYTE v52[232]; // [rsp+F8h] [rbp-140h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1E0h] [rbp-58h] BYREF
  __int64 v54; // [rsp+1F8h] [rbp-40h]

  v36 = a2;
  v37 = a1;
  if ( a3 == a4 || a4 <= 0 )
  {
    std::enable_shared_from_this<Pal::AsyncInfo>::shared_from_this(a1 + 8, v38);
    std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
      v42,
      v38);
    std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
      v40,
      v38);
    v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
    v44 = a1 + 24;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v8 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_ABI::Windows::System::Threading::ITimerElapsedHandler::___ABI::Windows::System::Threading::IThreadPoolTimer____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__ABI::Windows::System::Threading::ITimerElapsedHandler_Microsoft::WRL::FtmBase___lambda_b7a7d2c1126611cc35d6c6348a985474_____1_ABI::Windows::System::Threading::IThreadPoolTimer_____lambda_b7a7d2c1126611cc35d6c6348a985474____(
                      &v35,
                      v42);
    v9 = *v8;
    v45 = *v8;
    *v8 = 0;
    if ( v35 )
    {
      v35 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release();
    }
    v10 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_ABI::Windows::System::Threading::ITimerDestroyedHandler::___ABI::Windows::System::Threading::IThreadPoolTimer____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__ABI::Windows::System::Threading::ITimerDestroyedHandler_Microsoft::WRL::FtmBase___lambda_3e7e265548c130d7b8942cf77cabdc8b_____1_ABI::Windows::System::Threading::IThreadPoolTimer_____lambda_3e7e265548c130d7b8942cf77cabdc8b____(
                       &v35,
                       v40);
    v11 = *v10;
    v46 = *v10;
    *v10 = 0;
    if ( v35 )
    {
      v35 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release();
    }
    v34 = 0;
    v54 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Threading.ThreadPoolTimer",
      0x29u,
      0x28u);
    v12 = v54;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    ActivationFactory = RoGetActivationFactory(v12, &GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590, &v34);
    try
    {
      v14 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v50);
        v15 = std::operator<<<std::char_traits<char>>(
                v51,
                "Failed to retrieve the activation factory for Windows.System.Threading.ThreadPoolTimer");
        v16 = std::operator<<<std::char_traits<char>>(v15, " (HRESULT: 0x");
        v17 = std::ostream::operator<<(v16, std::hex);
        v18 = std::ostream::operator<<(v17, v14);
        std::operator<<<std::char_traits<char>>(v18, ")");
        std::stringbuf::str(v52, &hstringHeader);
        std::runtime_error::runtime_error((std::exception *)pExceptionObject);
        throw (std::runtime_error *)pExceptionObject;
      }
      std::function<void (_GUID const &)>::operator=(a1 + 64, v36);
      ResetEvent(**(HANDLE **)(a1 + 144));
      v19 = a1 + 128;
      v20 = v34;
      if ( a4 > 0 )
      {
        v28 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, __int64, __int64))(*(_QWORD *)v34 + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19);
        v29 = v28(v20, v9, 10000 * (a4 / 0x3E8uLL), v11, v19);
        if ( v29 < 0 )
        {
          std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v50);
          v30 = std::operator<<<std::char_traits<char>>(v51, "TimerWrapper::start - CreatePeriodicTimer failed");
          v31 = std::operator<<<std::char_traits<char>>(v30, " (HRESULT: 0x");
          v32 = std::ostream::operator<<(v31, std::hex);
          v33 = std::ostream::operator<<(v32, (unsigned int)v29);
          std::operator<<<std::char_traits<char>>(v33, ")");
          std::stringbuf::str(v52, &hstringHeader);
          std::runtime_error::runtime_error((std::exception *)v49);
          throw (std::runtime_error *)v49;
        }
      }
      else
      {
        v21 = 10000 * (a3 / 1000);
        v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int64))(*(_QWORD *)v34 + 72LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19);
        v23 = v22(v20, v9, v21, v11, v19);
        if ( v23 < 0 )
        {
          std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v50);
          v24 = std::operator<<<std::char_traits<char>>(v51, "TimerWrapper::start - CreateTimerWithCompletion failed");
          v25 = std::operator<<<std::char_traits<char>>(v24, " (HRESULT: 0x");
          v26 = std::ostream::operator<<(v25, std::hex);
          v27 = std::ostream::operator<<(v26, (unsigned int)v23);
          std::operator<<<std::char_traits<char>>(v27, ")");
          std::stringbuf::str(v52, &hstringHeader);
          std::runtime_error::runtime_error((std::exception *)v48);
          throw (std::runtime_error *)v48;
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      LeaveCriticalSection(v7);
      if ( v41 )
        std::_Ref_count_base::_Decref(v41);
      if ( v43 )
        std::_Ref_count_base::_Decref(v43);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
    }
    catch ( ... )
    {
      SetEvent(**(HANDLE **)(v37 + 144));
      throw;
    }
  }
}

```

## disassembly

```asm
0x18002cf9c  mov     [rsp+arg_10], rbx
0x18002cfa1  mov     [rsp+arg_18], rsi
0x18002cfa6  push    rdi
0x18002cfa7  push    r12
0x18002cfa9  push    r13
0x18002cfab  push    r14
0x18002cfad  push    r15
0x18002cfaf  sub     rsp, 210h
0x18002cfb6  mov     rax, cs:__security_cookie
0x18002cfbd  xor     rax, rsp
0x18002cfc0  mov     [rsp+238h+var_38], rax
0x18002cfc8  mov     rbx, r9
0x18002cfcb  mov     rdi, r8
0x18002cfce  mov     [rsp+238h+var_1F8], rdx
0x18002cfd3  mov     r14, rcx
0x18002cfd6  mov     [rsp+238h+var_1F0], rcx
0x18002cfdb  xor     esi, esi
0x18002cfdd  cmp     r8, r9
0x18002cfe0  jz      short loc_18002CFEB
0x18002cfe2  test    rbx, rbx
0x18002cfe5  jg      loc_18002D404
0x18002cfeb  add     rcx, 8
0x18002cfef  lea     rdx, [rsp+238h+var_1E8]
0x18002cff4  call    ?shared_from_this@?$enable_shared_from_this@VAsyncInfo@Pal@@@std@@QEBA?AV?$shared_ptr@$$CBVAsyncInfo@Pal@@@2@XZ; std::enable_shared_from_this<Pal::AsyncInfo>::shared_from_this(void)
0x18002cff9  nop
0x18002cffa  lea     rdx, [rsp+238h+var_1E8]
0x18002cfff  lea     rcx, [rsp+238h+var_1C8]
0x18002d004  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x18002d009  nop
0x18002d00a  lea     rdx, [rsp+238h+var_1E8]
0x18002d00f  lea     rcx, [rsp+238h+var_1D8]
0x18002d014  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x18002d019  nop
0x18002d01a  lea     r13, [r14+18h]
0x18002d01e  mov     [rsp+238h+var_1B8], r13
0x18002d026  mov     rcx, r13; lpCriticalSection
0x18002d029  call    cs:__imp_EnterCriticalSection
0x18002d02f  nop
0x18002d030  lea     rdx, [rsp+238h+var_1C8]
0x18002d035  lea     rcx, [rsp+238h+var_200]
0x18002d03a  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_ABI__Windows__System__Threading__ITimerElapsedHandler_____ABI__Windows__System__Threading__IThreadPoolTimer______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__ABI__Windows__System__Threading__ITimerElapsedHandler_Microsoft__WRL__FtmBase___lambda_b7a7d2c1126611cc35d6c6348a985474_____1_ABI__Windows__System__Threading__IThreadPoolTimer_____lambda_b7a7d2c1126611cc35d6c6348a985474____
0x18002d03f  mov     r12, [rax]
0x18002d042  mov     [rsp+238h+var_1B0], r12
0x18002d04a  mov     [rax], rsi
0x18002d04d  mov     rcx, [rsp+238h+var_200]
0x18002d052  test    rcx, rcx
0x18002d055  jz      short loc_18002D062
0x18002d057  mov     [rsp+238h+var_200], rsi
0x18002d05c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITimerDestroyedHandler@Threading@System@Windows@ABI@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x18002d061  nop
0x18002d062  lea     rdx, [rsp+238h+var_1D8]
0x18002d067  lea     rcx, [rsp+238h+var_200]
0x18002d06c  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_ABI__Windows__System__Threading__ITimerDestroyedHandler_____ABI__Windows__System__Threading__IThreadPoolTimer______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__ABI__Windows__System__Threading__ITimerDestroyedHandler_Microsoft__WRL__FtmBase___lambda_3e7e265548c130d7b8942cf77cabdc8b_____1_ABI__Windows__System__Threading__IThreadPoolTimer_____lambda_3e7e265548c130d7b8942cf77cabdc8b____
0x18002d071  mov     r15, [rax]
0x18002d074  mov     [rsp+238h+var_1A8], r15
0x18002d07c  mov     [rax], rsi
0x18002d07f  mov     rcx, [rsp+238h+var_200]
0x18002d084  test    rcx, rcx
0x18002d087  jz      short loc_18002D094
0x18002d089  mov     [rsp+238h+var_200], rsi
0x18002d08e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITimerDestroyedHandler@Threading@System@Windows@ABI@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x18002d093  nop
0x18002d094  mov     [rsp+238h+var_208], rsi
0x18002d099  mov     [rsp+238h+var_40], rsi
0x18002d0a1  mov     r9d, 28h ; '('; unsigned int
0x18002d0a7  lea     r8d, [r9+1]; unsigned int
0x18002d0ab  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPoolTimer@@3QBGB; "Windows.System.Threading.ThreadPoolTime"...
0x18002d0b2  lea     rcx, [rsp+238h+hstringHeader]; hstringHeader
0x18002d0ba  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002d0bf  mov     rsi, [rsp+238h+var_40]
0x18002d0c7  lea     rcx, [rsp+238h+var_208]
0x18002d0cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d0d1  lea     r8, [rsp+238h+var_208]
0x18002d0d6  lea     rdx, _GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590
0x18002d0dd  mov     rcx, rsi
0x18002d0e0  call    cs:__imp_RoGetActivationFactory
0x18002d0e6  mov     esi, eax
0x18002d0e8  test    eax, eax
0x18002d0ea  jns     loc_18002D18B
0x18002d0f0  lea     rcx, [rsp+238h+var_158]
0x18002d0f8  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002d0fd  nop
0x18002d0fe  lea     rdx, aFailedToRetrie; "Failed to retrieve the activation facto"...
0x18002d105  lea     rcx, [rsp+238h+var_148]
0x18002d10d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d112  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002d119  mov     rcx, rax
0x18002d11c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d121  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002d128  mov     rcx, rax
0x18002d12b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002d131  mov     edx, esi
0x18002d133  mov     rcx, rax
0x18002d136  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002d13c  lea     rdx, asc_1800A4BE0; ")"
0x18002d143  mov     rcx, rax
0x18002d146  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d14b  lea     rdx, [rsp+238h+hstringHeader]
0x18002d153  lea     rcx, [rsp+238h+var_140]
0x18002d15b  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002d160  nop
0x18002d161  lea     rdx, [rsp+238h+hstringHeader]
0x18002d169  lea     rcx, [rsp+238h+pExceptionObject]; this
0x18002d171  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002d176  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002d17d  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x18002d185  call    _CxxThrowException_0
0x18002d18b  lea     rcx, [r14+40h]
0x18002d18f  mov     rdx, [rsp+238h+var_1F8]
0x18002d194  call    ??4?$function@$$A6AXAEBU_GUID@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (_GUID const &)>::operator=(std::function<void (_GUID const &)> const &)
0x18002d199  mov     rcx, [r14+90h]
0x18002d1a0  mov     rcx, [rcx]; hEvent
0x18002d1a3  call    cs:__imp_ResetEvent
0x18002d1a9  sub     r14, 0FFFFFFFFFFFFFF80h
0x18002d1ad  mov     rsi, [rsp+238h+var_208]
0x18002d1b2  mov     rcx, r14
0x18002d1b5  test    rbx, rbx
0x18002d1b8  jg      loc_18002D2AA
0x18002d1be  mov     rax, 20C49BA5E353F7CFh
0x18002d1c8  imul    rdi
0x18002d1cb  sar     rdx, 7
0x18002d1cf  mov     rax, rdx
0x18002d1d2  shr     rax, 3Fh
0x18002d1d6  add     rdx, rax
0x18002d1d9  imul    rbx, rdx, 2710h
0x18002d1e0  mov     rax, [rsi]
0x18002d1e3  mov     rdi, [rax+48h]
0x18002d1e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d1ec  mov     [rsp+238h+var_218], r14
0x18002d1f1  mov     r9, r15
0x18002d1f4  mov     r8, rbx
0x18002d1f7  mov     rdx, r12
0x18002d1fa  mov     rcx, rsi
0x18002d1fd  mov     rax, rdi
0x18002d200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d205  mov     ebx, eax
0x18002d207  test    eax, eax
0x18002d209  jns     loc_18002D395
0x18002d20f  lea     rcx, [rsp+238h+var_158]
0x18002d217  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002d21c  nop
0x18002d21d  lea     rdx, aTimerwrapperSt; "TimerWrapper::start - CreateTimerWithCo"...
0x18002d224  lea     rcx, [rsp+238h+var_148]
0x18002d22c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d231  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002d238  mov     rcx, rax
0x18002d23b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d240  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002d247  mov     rcx, rax
0x18002d24a  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002d250  mov     edx, ebx
0x18002d252  mov     rcx, rax
0x18002d255  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002d25b  lea     rdx, asc_1800A4BE0; ")"
0x18002d262  mov     rcx, rax
0x18002d265  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d26a  lea     rdx, [rsp+238h+hstringHeader]
0x18002d272  lea     rcx, [rsp+238h+var_140]
0x18002d27a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002d27f  nop
0x18002d280  lea     rdx, [rsp+238h+hstringHeader]
0x18002d288  lea     rcx, [rsp+238h+var_188]; this
0x18002d290  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002d295  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002d29c  lea     rcx, [rsp+238h+var_188]; pExceptionObject
0x18002d2a4  call    _CxxThrowException_0
0x18002d2aa  mov     rax, 624DD2F1A9FBE77h
0x18002d2b4  mul     rbx
0x18002d2b7  sub     rbx, rdx
0x18002d2ba  shr     rbx, 1
0x18002d2bd  add     rbx, rdx
0x18002d2c0  shr     rbx, 9
0x18002d2c4  imul    rbx, 2710h
0x18002d2cb  mov     rax, [rsi]
0x18002d2ce  mov     rdi, [rax+40h]
0x18002d2d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d2d7  mov     [rsp+238h+var_218], r14
0x18002d2dc  mov     r9, r15
0x18002d2df  mov     r8, rbx
0x18002d2e2  mov     rdx, r12
0x18002d2e5  mov     rcx, rsi
0x18002d2e8  mov     rax, rdi
0x18002d2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2f0  mov     ebx, eax
0x18002d2f2  test    eax, eax
0x18002d2f4  jns     loc_18002D395
0x18002d2fa  lea     rcx, [rsp+238h+var_158]
0x18002d302  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002d307  nop
0x18002d308  lea     rdx, aTimerwrapperSt_0; "TimerWrapper::start - CreatePeriodicTim"...
0x18002d30f  lea     rcx, [rsp+238h+var_148]
0x18002d317  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d31c  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002d323  mov     rcx, rax
0x18002d326  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d32b  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002d332  mov     rcx, rax
0x18002d335  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002d33b  mov     edx, ebx
0x18002d33d  mov     rcx, rax
0x18002d340  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002d346  lea     rdx, asc_1800A4BE0; ")"
0x18002d34d  mov     rcx, rax
0x18002d350  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002d355  lea     rdx, [rsp+238h+hstringHeader]
0x18002d35d  lea     rcx, [rsp+238h+var_140]
0x18002d365  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002d36a  nop
0x18002d36b  lea     rdx, [rsp+238h+hstringHeader]
0x18002d373  lea     rcx, [rsp+238h+var_170]; this
0x18002d37b  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002d380  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002d387  lea     rcx, [rsp+238h+var_170]; pExceptionObject
0x18002d38f  call    _CxxThrowException_0
0x18002d395  lea     rcx, [rsp+238h+var_208]
0x18002d39a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d39f  nop
0x18002d3a0  test    r15, r15
0x18002d3a3  jz      short loc_18002D3B5
0x18002d3a5  mov     rax, [r15]
0x18002d3a8  mov     rcx, r15
0x18002d3ab  mov     rax, [rax+10h]
0x18002d3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3b4  nop
0x18002d3b5  test    r12, r12
0x18002d3b8  jz      short loc_18002D3CB
0x18002d3ba  mov     rax, [r12]
0x18002d3be  mov     rcx, r12
0x18002d3c1  mov     rax, [rax+10h]
0x18002d3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3ca  nop
0x18002d3cb  mov     rcx, r13; lpCriticalSection
0x18002d3ce  call    cs:__imp_LeaveCriticalSection
0x18002d3d4  nop
0x18002d3d5  mov     rcx, [rsp+238h+var_1D0]; this
0x18002d3da  test    rcx, rcx
0x18002d3dd  jz      short loc_18002D3E5
0x18002d3df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d3e4  nop
0x18002d3e5  mov     rcx, [rsp+238h+var_1C0]; this
0x18002d3ea  test    rcx, rcx
0x18002d3ed  jz      short loc_18002D3F5
0x18002d3ef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d3f4  nop
0x18002d3f5  mov     rcx, [rsp+238h+var_1E0]; this
0x18002d3fa  test    rcx, rcx
0x18002d3fd  jz      short loc_18002D404
0x18002d3ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002d404  mov     rcx, [rsp+238h+var_38]
0x18002d40c  xor     rcx, rsp; StackCookie
0x18002d40f  call    __security_check_cookie
0x18002d414  lea     r11, [rsp+238h+var_28]
0x18002d41c  mov     rbx, [r11+40h]
0x18002d420  mov     rsi, [r11+48h]
0x18002d424  mov     rsp, r11
0x18002d427  pop     r15
0x18002d429  pop     r14
0x18002d42b  pop     r13
0x18002d42d  pop     r12
0x18002d42f  pop     rdi
0x18002d430  retn
```
