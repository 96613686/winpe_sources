# Pal::Detail::WrlTimerWrapper::start(std::function<void (void)> const &,Core::TimeSpan,Core::TimeSpan)

- ea: `0x180019d6c`
- end: `0x18001a201`
- name: `?start@WrlTimerWrapper@Detail@Pal@@AEAAXAEBV?$function@$$A6AXXZ@std@@UTimeSpan@Core@@1@Z`
- size: `1173`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019c60`

## callees

- `0x1800094a0`
- `0x18000a080`
- `0x18000b4b8`
- `0x18000cb24`
- `0x18000cd80`
- `0x18000d18c`
- `0x18000d258`
- `0x18001006c`
- `0x180010b18`
- `0x180011e4c`
- `0x180012ca4`
- `0x180013620`
- `0x180013da8`
- `0x180019ab8`
- `0x180019d6c`
- `0x18001a7a8`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180019efb`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a01a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a105`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180019efb`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a01a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001a105`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180019f06`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a025`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a110`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180019f06`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a025`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18001a110`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019df9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019df9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019f73`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019f73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a19e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a19e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180019eb0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180019eb0`

## string_xrefs

- `0x180019ece`: `Failed to retrieve the activation factory for Windows.System.Threading.ThreadPoolTimer`
- `0x180019fed`: `TimerWrapper::start - CreateTimerWithCompletion failed`
- `0x18001a0d8`: `TimerWrapper::start - CreatePeriodicTimer failed`
- `0x180019e7b`: `Windows.System.Threading.ThreadPoolTimer`

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
  __int64 v38; // [rsp+50h] [rbp-1E8h] BYREF
  std::_Ref_count_base *v39; // [rsp+58h] [rbp-1E0h]
  __int64 v40; // [rsp+60h] [rbp-1D8h] BYREF
  std::_Ref_count_base *v41; // [rsp+68h] [rbp-1D0h]
  __int64 v42; // [rsp+70h] [rbp-1C8h] BYREF
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
    std::enable_shared_from_this<Pal::AsyncInfo>::shared_from_this(a1 + 8, &v38);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v42, &v38);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v40, &v38);
    v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
    v44 = a1 + 24;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v8 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_ABI::Windows::System::Threading::ITimerElapsedHandler::___ABI::Windows::System::Threading::IThreadPoolTimer____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__ABI::Windows::System::Threading::ITimerElapsedHandler_Microsoft::WRL::FtmBase___lambda_b7a7d2c1126611cc35d6c6348a985474_____1_ABI::Windows::System::Threading::IThreadPoolTimer_____lambda_b7a7d2c1126611cc35d6c6348a985474____(
                      &v35,
                      &v42);
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
                       &v40);
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
                (__int64)v51,
                (__int64)"Failed to retrieve the activation factory for Windows.System.Threading.ThreadPoolTimer");
        v16 = std::operator<<<std::char_traits<char>>(v15, (__int64)" (HRESULT: 0x");
        v17 = std::ostream::operator<<(v16, std::hex);
        v18 = std::ostream::operator<<(v17, v14);
        std::operator<<<std::char_traits<char>>(v18, (__int64)")");
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
          v30 = std::operator<<<std::char_traits<char>>(
                  (__int64)v51,
                  (__int64)"TimerWrapper::start - CreatePeriodicTimer failed");
          v31 = std::operator<<<std::char_traits<char>>(v30, (__int64)" (HRESULT: 0x");
          v32 = std::ostream::operator<<(v31, std::hex);
          v33 = std::ostream::operator<<(v32, (unsigned int)v29);
          std::operator<<<std::char_traits<char>>(v33, (__int64)")");
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
          v24 = std::operator<<<std::char_traits<char>>(
                  (__int64)v51,
                  (__int64)"TimerWrapper::start - CreateTimerWithCompletion failed");
          v25 = std::operator<<<std::char_traits<char>>(v24, (__int64)" (HRESULT: 0x");
          v26 = std::ostream::operator<<(v25, std::hex);
          v27 = std::ostream::operator<<(v26, (unsigned int)v23);
          std::operator<<<std::char_traits<char>>(v27, (__int64)")");
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
0x180019d6c  mov     [rsp+arg_10], rbx
0x180019d71  mov     [rsp+arg_18], rsi
0x180019d76  push    rdi
0x180019d77  push    r12
0x180019d79  push    r13
0x180019d7b  push    r14
0x180019d7d  push    r15
0x180019d7f  sub     rsp, 210h
0x180019d86  mov     rax, cs:__security_cookie
0x180019d8d  xor     rax, rsp
0x180019d90  mov     [rsp+238h+var_38], rax
0x180019d98  mov     rbx, r9
0x180019d9b  mov     rdi, r8
0x180019d9e  mov     [rsp+238h+var_1F8], rdx
0x180019da3  mov     r14, rcx
0x180019da6  mov     [rsp+238h+var_1F0], rcx
0x180019dab  xor     esi, esi
0x180019dad  cmp     r8, r9
0x180019db0  jz      short loc_180019DBB
0x180019db2  test    rbx, rbx
0x180019db5  jg      loc_18001A1D4
0x180019dbb  add     rcx, 8
0x180019dbf  lea     rdx, [rsp+238h+var_1E8]
0x180019dc4  call    ?shared_from_this@?$enable_shared_from_this@VAsyncInfo@Pal@@@std@@QEAA?AV?$shared_ptr@VAsyncInfo@Pal@@@2@XZ; std::enable_shared_from_this<Pal::AsyncInfo>::shared_from_this(void)
0x180019dc9  nop
0x180019dca  lea     rdx, [rsp+238h+var_1E8]
0x180019dcf  lea     rcx, [rsp+238h+var_1C8]
0x180019dd4  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180019dd9  nop
0x180019dda  lea     rdx, [rsp+238h+var_1E8]
0x180019ddf  lea     rcx, [rsp+238h+var_1D8]
0x180019de4  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180019de9  nop
0x180019dea  lea     r13, [r14+18h]
0x180019dee  mov     [rsp+238h+var_1B8], r13
0x180019df6  mov     rcx, r13; lpCriticalSection
0x180019df9  call    cs:__imp_EnterCriticalSection
0x180019dff  nop
0x180019e00  lea     rdx, [rsp+238h+var_1C8]
0x180019e05  lea     rcx, [rsp+238h+var_200]
0x180019e0a  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_ABI__Windows__System__Threading__ITimerElapsedHandler_____ABI__Windows__System__Threading__IThreadPoolTimer______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__ABI__Windows__System__Threading__ITimerElapsedHandler_Microsoft__WRL__FtmBase___lambda_b7a7d2c1126611cc35d6c6348a985474_____1_ABI__Windows__System__Threading__IThreadPoolTimer_____lambda_b7a7d2c1126611cc35d6c6348a985474____
0x180019e0f  mov     r12, [rax]
0x180019e12  mov     [rsp+238h+var_1B0], r12
0x180019e1a  mov     [rax], rsi
0x180019e1d  mov     rcx, [rsp+238h+var_200]
0x180019e22  test    rcx, rcx
0x180019e25  jz      short loc_180019E32
0x180019e27  mov     [rsp+238h+var_200], rsi
0x180019e2c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITimerDestroyedHandler@Threading@System@Windows@ABI@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x180019e31  nop
0x180019e32  lea     rdx, [rsp+238h+var_1D8]
0x180019e37  lea     rcx, [rsp+238h+var_200]
0x180019e3c  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_ABI__Windows__System__Threading__ITimerDestroyedHandler_____ABI__Windows__System__Threading__IThreadPoolTimer______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__ABI__Windows__System__Threading__ITimerDestroyedHandler_Microsoft__WRL__FtmBase___lambda_3e7e265548c130d7b8942cf77cabdc8b_____1_ABI__Windows__System__Threading__IThreadPoolTimer_____lambda_3e7e265548c130d7b8942cf77cabdc8b____
0x180019e41  mov     r15, [rax]
0x180019e44  mov     [rsp+238h+var_1A8], r15
0x180019e4c  mov     [rax], rsi
0x180019e4f  mov     rcx, [rsp+238h+var_200]
0x180019e54  test    rcx, rcx
0x180019e57  jz      short loc_180019E64
0x180019e59  mov     [rsp+238h+var_200], rsi
0x180019e5e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITimerDestroyedHandler@Threading@System@Windows@ABI@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::System::Threading::ITimerDestroyedHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x180019e63  nop
0x180019e64  mov     [rsp+238h+var_208], rsi
0x180019e69  mov     [rsp+238h+var_40], rsi
0x180019e71  mov     r9d, 28h ; '('; unsigned int
0x180019e77  lea     r8d, [r9+1]; unsigned int
0x180019e7b  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPoolTimer@@3QBGB; "Windows.System.Threading.ThreadPoolTime"...
0x180019e82  lea     rcx, [rsp+238h+hstringHeader]; hstringHeader
0x180019e8a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180019e8f  mov     rsi, [rsp+238h+var_40]
0x180019e97  lea     rcx, [rsp+238h+var_208]
0x180019e9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019ea1  lea     r8, [rsp+238h+var_208]
0x180019ea6  lea     rdx, _GUID_1a8a9d02_e482_461b_b8c7_8efad1cce590
0x180019ead  mov     rcx, rsi
0x180019eb0  call    cs:__imp_RoGetActivationFactory
0x180019eb6  mov     esi, eax
0x180019eb8  test    eax, eax
0x180019eba  jns     loc_180019F5B
0x180019ec0  lea     rcx, [rsp+238h+var_158]
0x180019ec8  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180019ecd  nop
0x180019ece  lea     rdx, aFailedToRetrie; "Failed to retrieve the activation facto"...
0x180019ed5  lea     rcx, [rsp+238h+var_148]
0x180019edd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180019ee2  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x180019ee9  mov     rcx, rax
0x180019eec  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180019ef1  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180019ef8  mov     rcx, rax
0x180019efb  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x180019f01  mov     edx, esi
0x180019f03  mov     rcx, rax
0x180019f06  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x180019f0c  lea     rdx, asc_180048470; ")"
0x180019f13  mov     rcx, rax
0x180019f16  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180019f1b  lea     rdx, [rsp+238h+hstringHeader]
0x180019f23  lea     rcx, [rsp+238h+var_140]
0x180019f2b  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180019f30  nop
0x180019f31  lea     rdx, [rsp+238h+hstringHeader]
0x180019f39  lea     rcx, [rsp+238h+pExceptionObject]; this
0x180019f41  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180019f46  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180019f4d  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x180019f55  call    _CxxThrowException_0
0x180019f5b  lea     rcx, [r14+40h]
0x180019f5f  mov     rdx, [rsp+238h+var_1F8]
0x180019f64  call    ??4?$function@$$A6AXAEBU_GUID@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (_GUID const &)>::operator=(std::function<void (_GUID const &)> const &)
0x180019f69  mov     rcx, [r14+90h]
0x180019f70  mov     rcx, [rcx]; hEvent
0x180019f73  call    cs:__imp_ResetEvent
0x180019f79  sub     r14, 0FFFFFFFFFFFFFF80h
0x180019f7d  mov     rsi, [rsp+238h+var_208]
0x180019f82  mov     rcx, r14
0x180019f85  test    rbx, rbx
0x180019f88  jg      loc_18001A07A
0x180019f8e  mov     rax, 20C49BA5E353F7CFh
0x180019f98  imul    rdi
0x180019f9b  sar     rdx, 7
0x180019f9f  mov     rax, rdx
0x180019fa2  shr     rax, 3Fh
0x180019fa6  add     rdx, rax
0x180019fa9  imul    rbx, rdx, 2710h
0x180019fb0  mov     rax, [rsi]
0x180019fb3  mov     rdi, [rax+48h]
0x180019fb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019fbc  mov     [rsp+238h+var_218], r14
0x180019fc1  mov     r9, r15
0x180019fc4  mov     r8, rbx
0x180019fc7  mov     rdx, r12
0x180019fca  mov     rcx, rsi
0x180019fcd  mov     rax, rdi
0x180019fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fd5  mov     ebx, eax
0x180019fd7  test    eax, eax
0x180019fd9  jns     loc_18001A165
0x180019fdf  lea     rcx, [rsp+238h+var_158]
0x180019fe7  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180019fec  nop
0x180019fed  lea     rdx, aTimerwrapperSt; "TimerWrapper::start - CreateTimerWithCo"...
0x180019ff4  lea     rcx, [rsp+238h+var_148]
0x180019ffc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a001  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18001a008  mov     rcx, rax
0x18001a00b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a010  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18001a017  mov     rcx, rax
0x18001a01a  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18001a020  mov     edx, ebx
0x18001a022  mov     rcx, rax
0x18001a025  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18001a02b  lea     rdx, asc_180048470; ")"
0x18001a032  mov     rcx, rax
0x18001a035  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a03a  lea     rdx, [rsp+238h+hstringHeader]
0x18001a042  lea     rcx, [rsp+238h+var_140]
0x18001a04a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18001a04f  nop
0x18001a050  lea     rdx, [rsp+238h+hstringHeader]
0x18001a058  lea     rcx, [rsp+238h+var_188]; this
0x18001a060  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18001a065  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001a06c  lea     rcx, [rsp+238h+var_188]; pExceptionObject
0x18001a074  call    _CxxThrowException_0
0x18001a07a  mov     rax, 624DD2F1A9FBE77h
0x18001a084  mul     rbx
0x18001a087  sub     rbx, rdx
0x18001a08a  shr     rbx, 1
0x18001a08d  add     rbx, rdx
0x18001a090  shr     rbx, 9
0x18001a094  imul    rbx, 2710h
0x18001a09b  mov     rax, [rsi]
0x18001a09e  mov     rdi, [rax+40h]
0x18001a0a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a0a7  mov     [rsp+238h+var_218], r14
0x18001a0ac  mov     r9, r15
0x18001a0af  mov     r8, rbx
0x18001a0b2  mov     rdx, r12
0x18001a0b5  mov     rcx, rsi
0x18001a0b8  mov     rax, rdi
0x18001a0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c0  mov     ebx, eax
0x18001a0c2  test    eax, eax
0x18001a0c4  jns     loc_18001A165
0x18001a0ca  lea     rcx, [rsp+238h+var_158]
0x18001a0d2  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18001a0d7  nop
0x18001a0d8  lea     rdx, aTimerwrapperSt_0; "TimerWrapper::start - CreatePeriodicTim"...
0x18001a0df  lea     rcx, [rsp+238h+var_148]
0x18001a0e7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a0ec  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18001a0f3  mov     rcx, rax
0x18001a0f6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a0fb  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18001a102  mov     rcx, rax
0x18001a105  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18001a10b  mov     edx, ebx
0x18001a10d  mov     rcx, rax
0x18001a110  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18001a116  lea     rdx, asc_180048470; ")"
0x18001a11d  mov     rcx, rax
0x18001a120  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001a125  lea     rdx, [rsp+238h+hstringHeader]
0x18001a12d  lea     rcx, [rsp+238h+var_140]
0x18001a135  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18001a13a  nop
0x18001a13b  lea     rdx, [rsp+238h+hstringHeader]
0x18001a143  lea     rcx, [rsp+238h+var_170]; this
0x18001a14b  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18001a150  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001a157  lea     rcx, [rsp+238h+var_170]; pExceptionObject
0x18001a15f  call    _CxxThrowException_0
0x18001a165  lea     rcx, [rsp+238h+var_208]
0x18001a16a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a16f  nop
0x18001a170  test    r15, r15
0x18001a173  jz      short loc_18001A185
0x18001a175  mov     rax, [r15]
0x18001a178  mov     rcx, r15
0x18001a17b  mov     rax, [rax+10h]
0x18001a17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a184  nop
0x18001a185  test    r12, r12
0x18001a188  jz      short loc_18001A19B
0x18001a18a  mov     rax, [r12]
0x18001a18e  mov     rcx, r12
0x18001a191  mov     rax, [rax+10h]
0x18001a195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a19a  nop
0x18001a19b  mov     rcx, r13; lpCriticalSection
0x18001a19e  call    cs:__imp_LeaveCriticalSection
0x18001a1a4  nop
0x18001a1a5  mov     rcx, [rsp+238h+var_1D0]; this
0x18001a1aa  test    rcx, rcx
0x18001a1ad  jz      short loc_18001A1B5
0x18001a1af  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a1b4  nop
0x18001a1b5  mov     rcx, [rsp+238h+var_1C0]; this
0x18001a1ba  test    rcx, rcx
0x18001a1bd  jz      short loc_18001A1C5
0x18001a1bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a1c4  nop
0x18001a1c5  mov     rcx, [rsp+238h+var_1E0]; this
0x18001a1ca  test    rcx, rcx
0x18001a1cd  jz      short loc_18001A1D4
0x18001a1cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a1d4  mov     rcx, [rsp+238h+var_38]
0x18001a1dc  xor     rcx, rsp; StackCookie
0x18001a1df  call    __security_check_cookie
0x18001a1e4  lea     r11, [rsp+238h+var_28]
0x18001a1ec  mov     rbx, [r11+40h]
0x18001a1f0  mov     rsi, [r11+48h]
0x18001a1f4  mov     rsp, r11
0x18001a1f7  pop     r15
0x18001a1f9  pop     r14
0x18001a1fb  pop     r13
0x18001a1fd  pop     r12
0x18001a1ff  pop     rdi
0x18001a200  retn
```
