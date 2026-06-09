# ConnectedStorage::NtmWebService::UploadContainerImpl(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)>,ulong,std::shared_ptr<ConnectedStorage::NtmCancelCallback>)

- ea: `0x180046bec`
- end: `0x180047247`
- name: `?UploadContainerImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@AEBVSimpleHStringWrapper@2@1AEBU_FILETIME@@1V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@Z@std@@KV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@7@@Z`
- size: `1627`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180046540`
- `0x1800467c8`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x18000d6bc`
- `0x180011c0c`
- `0x180011c68`
- `0x1800125ec`
- `0x1800136a8`
- `0x1800190f0`
- `0x180019128`
- `0x18001c090`
- `0x18001ec34`
- `0x180022dec`
- `0x18002cf5c`
- `0x18003c2b8`
- `0x18003d098`
- `0x18003e300`
- `0x18003ee9c`
- `0x18003eff4`
- `0x180040cbc`
- `0x180043580`
- `0x180043824`
- `0x1800449b0`
- `0x180046bec`
- `0x180048370`
- `0x180048720`
- `0x180085408`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046cd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046cd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471de`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046d78`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046d88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004705b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004706b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004707b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800471b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046d88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004705b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004706b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004707b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800471b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046df0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004715e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004716d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046df0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004715e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004716d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046ce0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046ce0`

## string_xrefs

- `0x180046d48`: `Windows.Foundation.Uri`
- `0x180046e59`: `Content-Type: application/json\n`
- `0x180047228`: `GetActivationFactory(SimpleHStringWrapper(RuntimeClass_Windows_Foundation_Uri).Get(), &uriStatics)`
- `0x180047237`: `uriStatics->EscapeComponent(containerDisplayName.Get(), escapedDisplayName.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall ConnectedStorage::NtmWebService::UploadContainerImpl(
        __int64 a1,
        HSTRING *a2,
        char *a3,
        ConnectedStorage::SimpleHStringWrapper *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8,
        ConnectedStorage::NtmCancelCallback **a9)
{
  HSTRING *v10; // r14
  __int64 v12; // r15
  ConnectedStorage::NtmCancelCallback **v13; // rdi
  struct ConnectedStorage::Mutex *v14; // rbx
  char *v15; // r8
  ULONGLONG TickCount64; // rax
  HSTRING v17; // rbx
  int ActivationFactory; // ebx
  const unsigned __int16 *v19; // r8
  HSTRING v20; // rbx
  __int64 (__fastcall *v21)(HSTRING, _QWORD, HSTRING *); // r12
  HSTRING *AddressOf; // rax
  int v23; // eax
  const unsigned __int16 *v24; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v26; // r8
  __int64 v27; // rax
  HSTRING *v28; // rax
  HSTRING v29; // rbx
  HSTRING v30; // rcx
  __int64 *v31; // r12
  __int64 v32; // r13
  __int64 v33; // rax
  HSTRING *v34; // rbx
  HSTRING *v35; // rax
  char *v36; // r8
  const unsigned __int16 *v37; // rdi
  const unsigned __int16 *v38; // rbx
  ConnectedStorage *v39; // rax
  std::_Ref_count_base *v40; // rcx
  int v41; // [rsp+20h] [rbp-2E8h]
  HSTRING string; // [rsp+60h] [rbp-2A8h] BYREF
  HSTRING v43; // [rsp+68h] [rbp-2A0h] BYREF
  HSTRING v44; // [rsp+70h] [rbp-298h] BYREF
  HSTRING v45; // [rsp+78h] [rbp-290h] BYREF
  HSTRING v46; // [rsp+80h] [rbp-288h] BYREF
  __int64 v47; // [rsp+88h] [rbp-280h]
  __int64 v48; // [rsp+90h] [rbp-278h]
  HSTRING *v49; // [rsp+98h] [rbp-270h]
  __int64 v50; // [rsp+A0h] [rbp-268h]
  ConnectedStorage::NtmCancelCallback **v51; // [rsp+A8h] [rbp-260h]
  HSTRING *p_string; // [rsp+B0h] [rbp-258h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp-250h] BYREF
  std::_Ref_count_base *v54; // [rsp+C0h] [rbp-248h]
  struct ConnectedStorage::Mutex *v55; // [rsp+C8h] [rbp-240h]
  HSTRING *v56; // [rsp+D0h] [rbp-238h]
  struct _GUID v57; // [rsp+E0h] [rbp-228h] BYREF
  LPCRITICAL_SECTION v58[2]; // [rsp+100h] [rbp-208h] BYREF
  char v59; // [rsp+110h] [rbp-1F8h] BYREF
  __int64 v60; // [rsp+148h] [rbp-1C0h]
  LPCRITICAL_SECTION v61[2]; // [rsp+150h] [rbp-1B8h] BYREF
  _BYTE Src[32]; // [rsp+160h] [rbp-1A8h] BYREF
  _OWORD v63[2]; // [rsp+180h] [rbp-188h] BYREF
  _QWORD v64[2]; // [rsp+1A0h] [rbp-168h] BYREF
  _DWORD v65[16]; // [rsp+1C0h] [rbp-148h] BYREF
  _BYTE v66[192]; // [rsp+200h] [rbp-108h] BYREF

  v45 = (HSTRING)a4;
  v44 = (HSTRING)a3;
  v10 = a2;
  v56 = (HSTRING *)a3;
  v49 = a2;
  v48 = a5;
  v47 = a6;
  v12 = a7;
  v50 = a7;
  v13 = a9;
  v51 = a9;
  v14 = (struct ConnectedStorage::Mutex *)(a1 + 40);
  v55 = (struct ConnectedStorage::Mutex *)(a1 + 40);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)v58,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
    a3);
  if ( *(_QWORD *)(a1 + 88) )
  {
    TickCount64 = GetTickCount64();
    try
    {
      p_string = (HSTRING *)TickCount64;
      ConnectedStorage::MakeUrlForContainer(Src, v10, v44);
      std::wstring::_Append<unsigned short>(Src);
      ConnectedStorage::AppendW3cDateTime(Src, v48);
      if ( !ConnectedStorage::SimpleHStringWrapper::IsEmpty(a4) )
      {
        string = 0;
        v17 = *ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v46, L"Windows.Foundation.Uri");
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        ActivationFactory = RoGetActivationFactory(v17, &GUID_c1d432ba_c824_4452_a7fd_512bc3bbe9a1, &string);
        WindowsDeleteString(v46);
        if ( ActivationFactory < 0 )
          ConnectedStorage::ReportErrorAndThrow(
            (ConnectedStorage *)(unsigned int)ActivationFactory,
            (int)L"GetActivationFactory(SimpleHStringWrapper(RuntimeClass_Windows_Foundation_Uri).Get(), &uriStatics)",
            v19);
        v43 = 0;
        v20 = string;
        v21 = *(__int64 (__fastcall **)(HSTRING, _QWORD, HSTRING *))(*(_QWORD *)string + 56LL);
        AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v43);
        v23 = v21(v20, *(_QWORD *)v45, AddressOf);
        if ( v23 < 0 )
          ConnectedStorage::ReportErrorAndThrow(
            (ConnectedStorage *)(unsigned int)v23,
            (int)L"uriStatics->EscapeComponent(containerDisplayName.Get(), escapedDisplayName.GetAddressOf())",
            v24);
        std::wstring::_Append<unsigned short>(Src);
        StringRawBuffer = WindowsGetStringRawBuffer(v43, 0);
        v26 = -1;
        do
          ++v26;
        while ( StringRawBuffer[v26] );
        std::wstring::_Append<unsigned short>(Src);
        WindowsDeleteString(v43);
        v43 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      }
      v63[0] = 0;
      v63[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v63[0]) = 0;
      std::wstring::_Append<unsigned short>(v63);
      ConnectedStorage::NtmWebService::MakeHeadersWithContext(a1, v64, Src, v10);
      std::wstring::_Append<unsigned short>(v63);
      v27 = ConnectedStorage::ToUtf8(&v57, v47);
      v28 = (HSTRING *)Microsoft::WRL::Details::Make<ConnectedStorage::ByteUploadStream,std::vector<unsigned char>>(
                         &string,
                         v27);
      v29 = *v28;
      v46 = *v28;
      *v28 = 0;
      v30 = string;
      if ( string )
      {
        string = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v30 + 16LL))(v30);
      }
      std::vector<unsigned char>::_Tidy(&v57);
      ConnectedStorage::NtmWebService::weak_from_this(a1, &lpCriticalSection);
      v31 = *(__int64 **)(a1 + 88);
      v32 = *v31;
      *(_QWORD *)&v57.Data1 = &v59;
      v33 = lambda_6da7532f48ec632a12d59055cd5c4618_::_lambda_6da7532f48ec632a12d59055cd5c4618__1(
              v66,
              a7,
              v10,
              v44,
              v45,
              v48,
              v47,
              v13,
              &p_string,
              &a8,
              &lpCriticalSection);
      v60 = 0;
      v60 = std::_Global_new_std::_Func_impl_no_alloc__lambda_6da7532f48ec632a12d59055cd5c4618__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_6da7532f48ec632a12d59055cd5c4618___(v33);
      v43 = 0;
      p_string = &string;
      string = v29;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&string);
      v34 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v45, (__int64)v63);
      v35 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v44, (__int64)Src);
      LOWORD(v41) = 95;
      (*(void (__fastcall **)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, int, HSTRING *, HSTRING *))(v32 + 16))(
        v31,
        v61,
        v35,
        24,
        v41,
        v34,
        &string);
      WindowsDeleteString(v44);
      v44 = 0;
      WindowsDeleteString(v45);
      v45 = 0;
      WindowsDeleteString(v43);
      v43 = 0;
      lambda_6da7532f48ec632a12d59055cd5c4618_::__lambda_6da7532f48ec632a12d59055cd5c4618_(v66);
      v57 = *(struct _GUID *)v61;
      ConnectedStorage::NtmCancelCallback::ReplaceCompletedTransfer(*v13, &v57);
      if ( v54 )
        std::_Ref_count_base::_Decwref(v54);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      std::wstring::_Tidy_deallocate(v64);
      std::wstring::_Tidy_deallocate(v63);
      std::wstring::_Tidy_deallocate(Src);
    }
    catch ( ConnectedStorage::ComError v65 )
    {
      LODWORD(v43) = v65[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v65);
      if ( (int)v43 < 0 )
      {
LABEL_17:
        ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)v61, v55, v36);
        v37 = WindowsGetStringRawBuffer(*v56, 0);
        v10 = v49;
        v38 = WindowsGetStringRawBuffer(v49[2], 0);
        v39 = (ConnectedStorage *)WindowsGetStringRawBuffer(v10[3], 0);
        ConnectedStorage::EventWriteWebUploadContainer(v39, v38, v37, 0, 0, (unsigned int)v43, 0, (unsigned int)&v43);
        v44 = 0;
        v12 = v50;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
          v50,
          1,
          &v44);
        WindowsDeleteString(v44);
        EnterCriticalSection(v61[0]);
      }
      else
      {
        v10 = v49;
        v12 = v50;
      }
      v13 = v51;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v43) = -2147024882;
      goto LABEL_17;
    }
    catch ( ... )
    {
      LODWORD(v43) = -2147467259;
      goto LABEL_17;
    }
  }
  else
  {
    ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)&lpCriticalSection, v14, v15);
    string = 0;
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a7,
      1,
      &string);
    WindowsDeleteString(string);
    EnterCriticalSection(lpCriticalSection);
  }
  LeaveCriticalSection(v58[0]);
  ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v10);
  std::function<long (void)>::~function<long (void)>(v12);
  v40 = v13[1];
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
}

```

## disassembly

```asm
0x180046bec  mov     r11, rsp
0x180046bef  push    rbx
0x180046bf0  push    rsi
0x180046bf1  push    rdi
0x180046bf2  push    r12
0x180046bf4  push    r13
0x180046bf6  push    r14
0x180046bf8  push    r15
0x180046bfa  sub     rsp, 2D0h
0x180046c01  mov     rax, cs:__security_cookie
0x180046c08  xor     rax, rsp
0x180046c0b  mov     [rsp+308h+var_48], rax
0x180046c13  mov     r12, r9
0x180046c16  mov     [rsp+308h+var_290], r9
0x180046c1b  mov     rax, r8
0x180046c1e  mov     [rsp+308h+var_298], rax
0x180046c23  mov     r14, rdx
0x180046c26  mov     r13, rcx
0x180046c29  mov     [rsp+308h+var_238], rax
0x180046c31  mov     [r11-270h], rdx
0x180046c38  mov     rax, [rsp+308h+arg_20]
0x180046c40  mov     [rsp+308h+var_278], rax
0x180046c48  mov     rax, [rsp+308h+arg_28]
0x180046c50  mov     [rsp+308h+var_280], rax
0x180046c58  mov     r15, [rsp+308h+arg_30]
0x180046c60  mov     [r11-268h], r15
0x180046c67  mov     rdi, [rsp+308h+arg_40]
0x180046c6f  mov     [r11-260h], rdi
0x180046c76  lea     rbx, [rcx+28h]
0x180046c7a  mov     [rsp+308h+var_240], rbx
0x180046c82  mov     rdx, rbx; struct ConnectedStorage::Mutex *
0x180046c85  lea     rcx, [r11-208h]; this
0x180046c8c  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180046c91  nop
0x180046c92  xor     esi, esi
0x180046c94  cmp     [r13+58h], rsi
0x180046c98  jnz     short loc_180046CE0
0x180046c9a  mov     rdx, rbx; struct ConnectedStorage::Mutex *
0x180046c9d  lea     rcx, [rsp+308h+lpCriticalSection]; this
0x180046ca5  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180046caa  nop
0x180046cab  mov     [rsp+308h+string], rsi
0x180046cb0  lea     r8, [rsp+308h+string]
0x180046cb5  lea     edx, [rsi+1]
0x180046cb8  mov     rcx, r15
0x180046cbb  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180046cc0  nop
0x180046cc1  mov     rcx, [rsp+308h+string]; string
0x180046cc6  call    cs:__imp_WindowsDeleteString
0x180046ccc  nop
0x180046ccd  mov     rcx, [rsp+308h+lpCriticalSection]; lpCriticalSection
0x180046cd5  call    cs:__imp_EnterCriticalSection
0x180046cdb  jmp     loc_1800471D6
0x180046ce0  call    cs:__imp_GetTickCount64
0x180046ce6  mov     [rsp+308h+var_258], rax
0x180046cee  mov     r8, [rsp+308h+var_298]
0x180046cf3  mov     rdx, r14
0x180046cf6  lea     rcx, [rsp+308h+Src]
0x180046cfe  call    ?MakeUrlForContainer@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@AEBVSimpleHStringWrapper@1@@Z; ConnectedStorage::MakeUrlForContainer(ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180046d03  nop
0x180046d04  mov     r8d, 10h
0x180046d0a  lea     rdx, aClientfiletime; "?clientFileTime="
0x180046d11  lea     rcx, [rsp+308h+Src]; Src
0x180046d19  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180046d1e  mov     rdx, [rsp+308h+var_278]
0x180046d26  lea     rcx, [rsp+308h+Src]
0x180046d2e  call    ?AppendW3cDateTime@ConnectedStorage@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_FILETIME@@@Z; ConnectedStorage::AppendW3cDateTime(std::wstring *,_FILETIME const &)
0x180046d33  mov     rcx, r12; this
0x180046d36  call    ?IsEmpty@SimpleHStringWrapper@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::SimpleHStringWrapper::IsEmpty(void)
0x180046d3b  test    al, al
0x180046d3d  jnz     loc_180046E2F
0x180046d43  mov     [rsp+308h+string], rsi
0x180046d48  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180046d4f  lea     rcx, [rsp+308h+var_288]; string
0x180046d57  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180046d5c  mov     rbx, [rax]
0x180046d5f  lea     rcx, [rsp+308h+string]
0x180046d64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046d69  lea     r8, [rsp+308h+string]
0x180046d6e  lea     rdx, _GUID_c1d432ba_c824_4452_a7fd_512bc3bbe9a1
0x180046d75  mov     rcx, rbx
0x180046d78  call    cs:__imp_RoGetActivationFactory
0x180046d7e  mov     ebx, eax
0x180046d80  mov     rcx, [rsp+308h+var_288]; string
0x180046d88  call    cs:__imp_WindowsDeleteString
0x180046d8e  test    ebx, ebx
0x180046d90  js      loc_180047228
0x180046d96  mov     [rsp+308h+var_2A0], rsi
0x180046d9b  mov     rbx, [rsp+308h+string]
0x180046da0  mov     rax, [rbx]
0x180046da3  mov     r12, [rax+38h]
0x180046da7  lea     rcx, [rsp+308h+var_2A0]; this
0x180046dac  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180046db1  mov     r8, rax
0x180046db4  mov     rdx, [rsp+308h+var_290]
0x180046db9  mov     rdx, [rdx]
0x180046dbc  mov     rcx, rbx
0x180046dbf  mov     rax, r12
0x180046dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dc7  test    eax, eax
0x180046dc9  js      loc_180047237
0x180046dcf  mov     r8d, 0Dh
0x180046dd5  lea     rdx, aDisplayname_0; "&displayName="
0x180046ddc  lea     rcx, [rsp+308h+Src]; Src
0x180046de4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180046de9  xor     edx, edx; length
0x180046deb  mov     rcx, [rsp+308h+var_2A0]; string
0x180046df0  call    cs:__imp_WindowsGetStringRawBuffer
0x180046df6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180046dfa  inc     r8
0x180046dfd  cmp     [rax+r8*2], si
0x180046e02  jnz     short loc_180046DFA
0x180046e04  mov     rdx, rax
0x180046e07  lea     rcx, [rsp+308h+Src]; Src
0x180046e0f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180046e14  nop
0x180046e15  mov     rcx, [rsp+308h+var_2A0]; string
0x180046e1a  call    cs:__imp_WindowsDeleteString
0x180046e20  mov     [rsp+308h+var_2A0], rsi
0x180046e25  lea     rcx, [rsp+308h+string]
0x180046e2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e2f  xorps   xmm0, xmm0
0x180046e32  movups  [rsp+308h+var_188], xmm0
0x180046e3a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180046e42  movdqu  [rsp+308h+var_178], xmm1
0x180046e4b  mov     word ptr [rsp+308h+var_188], si
0x180046e53  mov     r8d, 20h ; ' '
0x180046e59  lea     rdx, aContentTypeApp; "Content-Type: application/json\r\n"
0x180046e60  lea     rcx, [rsp+308h+var_188]; Src
0x180046e68  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180046e6d  mov     r9, r14
0x180046e70  lea     r8, [rsp+308h+Src]
0x180046e78  lea     rdx, [rsp+308h+var_168]
0x180046e80  mov     rcx, r13
0x180046e83  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180046e88  nop
0x180046e89  lea     rdx, [rsp+308h+var_168]
0x180046e91  cmp     [rsp+308h+var_150], 7
0x180046e9a  cmova   rdx, [rsp+308h+var_168]
0x180046ea3  mov     r8, [rsp+308h+var_158]
0x180046eab  lea     rcx, [rsp+308h+var_188]; Src
0x180046eb3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180046eb8  mov     rdx, [rsp+308h+var_280]
0x180046ec0  lea     rcx, [rsp+308h+var_228]
0x180046ec8  call    ?ToUtf8@ConnectedStorage@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBVSimpleHStringWrapper@1@@Z; ConnectedStorage::ToUtf8(ConnectedStorage::SimpleHStringWrapper const &)
0x180046ecd  nop
0x180046ece  mov     rdx, rax
0x180046ed1  lea     rcx, [rsp+308h+string]
0x180046ed6  call    ??$Make@VByteUploadStream@ConnectedStorage@@V?$vector@EV?$allocator@E@std@@@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VByteUploadStream@ConnectedStorage@@@12@$$QEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Microsoft::WRL::Details::Make<ConnectedStorage::ByteUploadStream,std::vector<uchar>>(std::vector<uchar> &&)
0x180046edb  mov     rbx, [rax]
0x180046ede  mov     [rsp+308h+var_288], rbx
0x180046ee6  mov     [rax], rsi
0x180046ee9  mov     rcx, [rsp+308h+string]
0x180046eee  test    rcx, rcx
0x180046ef1  jz      short loc_180046F05
0x180046ef3  mov     [rsp+308h+string], rsi
0x180046ef8  mov     rax, [rcx]
0x180046efb  mov     rax, [rax+10h]
0x180046eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f04  nop
0x180046f05  lea     rcx, [rsp+308h+var_228]
0x180046f0d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180046f12  lea     rdx, [rsp+308h+lpCriticalSection]
0x180046f1a  mov     rcx, r13
0x180046f1d  call    ?weak_from_this@NtmWebService@ConnectedStorage@@AEBA?AV?$weak_ptr@$$CBVNtmWebService@ConnectedStorage@@@std@@XZ; ConnectedStorage::NtmWebService::weak_from_this(void)
0x180046f22  nop
0x180046f23  mov     r12, [r13+58h]
0x180046f27  mov     r13, [r12]
0x180046f2b  lea     rax, [rsp+308h+var_1F8]
0x180046f33  mov     qword ptr [rsp+308h+var_228.Data1], rax
0x180046f3b  lea     rax, [rsp+308h+lpCriticalSection]
0x180046f43  mov     [rsp+308h+var_2B8], rax
0x180046f48  lea     rax, [rsp+308h+arg_38]
0x180046f50  mov     [rsp+308h+var_2C0], rax
0x180046f55  lea     rax, [rsp+308h+var_258]
0x180046f5d  mov     [rsp+308h+var_2C8], rax
0x180046f62  mov     [rsp+308h+var_2D0], rdi
0x180046f67  mov     rax, [rsp+308h+var_280]
0x180046f6f  mov     qword ptr [rsp+308h+var_2D8], rax
0x180046f74  mov     rax, [rsp+308h+var_278]
0x180046f7c  mov     qword ptr [rsp+308h+var_2E0], rax
0x180046f81  mov     rax, [rsp+308h+var_290]
0x180046f86  mov     qword ptr [rsp+308h+var_2E8], rax
0x180046f8b  mov     r9, [rsp+308h+var_298]
0x180046f90  mov     r8, r14
0x180046f93  mov     rdx, r15
0x180046f96  lea     rcx, [rsp+308h+var_108]
0x180046f9e  call    _lambda_6da7532f48ec632a12d59055cd5c4618____lambda_6da7532f48ec632a12d59055cd5c4618__1
0x180046fa3  nop
0x180046fa4  mov     [rsp+308h+var_1C0], rsi
0x180046fac  mov     rcx, rax
0x180046faf  call    std___Global_new_std___Func_impl_no_alloc__lambda_6da7532f48ec632a12d59055cd5c4618__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_6da7532f48ec632a12d59055cd5c4618___
0x180046fb4  mov     [rsp+308h+var_1C0], rax
0x180046fbc  mov     [rsp+308h+var_2A0], rsi
0x180046fc1  lea     rax, [rsp+308h+string]
0x180046fc6  mov     [rsp+308h+var_258], rax
0x180046fce  mov     [rsp+308h+string], rbx
0x180046fd3  lea     rcx, [rsp+308h+string]
0x180046fd8  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180046fdd  nop
0x180046fde  lea     rdx, [rsp+308h+var_188]
0x180046fe6  lea     rcx, [rsp+308h+var_290]; string
0x180046feb  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180046ff0  mov     rbx, rax
0x180046ff3  lea     rdx, [rsp+308h+Src]
0x180046ffb  lea     rcx, [rsp+308h+var_298]; string
0x180047000  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180047005  nop
0x180047006  lea     rcx, [rsp+308h+var_1F8]
0x18004700e  mov     [rsp+308h+var_2C0], rcx
0x180047013  mov     [rsp+308h+var_2C8], rsi
0x180047018  lea     rcx, [rsp+308h+var_2A0]
0x18004701d  mov     [rsp+308h+var_2D0], rcx
0x180047022  lea     rcx, [rsp+308h+string]
0x180047027  mov     qword ptr [rsp+308h+var_2D8], rcx
0x18004702c  mov     qword ptr [rsp+308h+var_2E0], rbx
0x180047031  mov     word ptr [rsp+308h+var_2E8], 5Fh ; '_'
0x180047038  mov     r9d, 18h
0x18004703e  mov     r8, rax
0x180047041  lea     rdx, [rsp+308h+var_1B8]
0x180047049  mov     rcx, r12
0x18004704c  mov     rax, [r13+10h]
0x180047050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047055  nop
0x180047056  mov     rcx, [rsp+308h+var_298]; string
0x18004705b  call    cs:__imp_WindowsDeleteString
0x180047061  mov     [rsp+308h+var_298], rsi
0x180047066  mov     rcx, [rsp+308h+var_290]; string
0x18004706b  call    cs:__imp_WindowsDeleteString
0x180047071  mov     [rsp+308h+var_290], rsi
0x180047076  mov     rcx, [rsp+308h+var_2A0]; string
0x18004707b  call    cs:__imp_WindowsDeleteString
0x180047081  mov     [rsp+308h+var_2A0], rsi
0x180047086  lea     rcx, [rsp+308h+var_108]
0x18004708e  call    _lambda_6da7532f48ec632a12d59055cd5c4618_____lambda_6da7532f48ec632a12d59055cd5c4618_
0x180047093  movaps  xmm0, xmmword ptr [rsp+308h+var_1B8]
0x18004709b  movdqa  xmmword ptr [rsp+308h+var_228.Data1], xmm0
0x1800470a4  lea     rdx, [rsp+308h+var_228]; struct _GUID
0x1800470ac  mov     rcx, [rdi]; this
0x1800470af  call    ?ReplaceCompletedTransfer@NtmCancelCallback@ConnectedStorage@@QEAAXU_GUID@@@Z; ConnectedStorage::NtmCancelCallback::ReplaceCompletedTransfer(_GUID)
0x1800470b4  nop
0x1800470b5  mov     rcx, [rsp+308h+var_248]; this
0x1800470bd  test    rcx, rcx
0x1800470c0  jz      short loc_1800470C8
0x1800470c2  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800470c7  nop
0x1800470c8  lea     rcx, [rsp+308h+var_288]
0x1800470d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800470d5  nop
0x1800470d6  lea     rcx, [rsp+308h+var_168]
0x1800470de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800470e3  nop
0x1800470e4  lea     rcx, [rsp+308h+var_188]
0x1800470ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800470f1  nop
0x1800470f2  lea     rcx, [rsp+308h+Src]
0x1800470fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800470ff  nop
0x180047100  jmp     loc_1800471D6
0x180047105  xor     esi, esi
0x180047107  cmp     dword ptr [rsp+308h+var_2A0], esi
0x18004710b  jl      short loc_180047124
0x18004710d  mov     r14, [rsp+308h+var_270]
0x180047115  mov     r15, [rsp+308h+var_268]
0x18004711d  jmp     loc_1800471CE
0x180047122  xor     esi, esi
0x180047124  mov     rdx, [rsp+308h+var_240]; struct ConnectedStorage::Mutex *
0x18004712c  lea     rcx, [rsp+308h+var_1B8]; this
0x180047134  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180047139  nop
0x18004713a  xor     edx, edx; length
0x18004713c  mov     rcx, [rsp+308h+var_238]
0x180047144  mov     rcx, [rcx]; string
0x180047147  call    cs:__imp_WindowsGetStringRawBuffer
0x18004714d  mov     rdi, rax
0x180047150  xor     edx, edx; length
0x180047152  mov     r14, [rsp+308h+var_270]
0x18004715a  mov     rcx, [r14+10h]; string
0x18004715e  call    cs:__imp_WindowsGetStringRawBuffer
0x180047164  mov     rbx, rax
0x180047167  xor     edx, edx; length
0x180047169  mov     rcx, [r14+18h]; string
0x18004716d  call    cs:__imp_WindowsGetStringRawBuffer
0x180047173  mov     [rsp+308h+var_2D8], esi; unsigned int
0x180047177  mov     ecx, dword ptr [rsp+308h+var_2A0]
0x18004717b  mov     [rsp+308h+var_2E0], ecx; unsigned int
0x18004717f  mov     [rsp+308h+var_2E8], esi; unsigned int
0x180047183  xor     r9d, r9d; unsigned __int16 *
0x180047186  mov     r8, rdi; unsigned __int16 *
0x180047189  mov     rdx, rbx; unsigned __int16 *
0x18004718c  mov     rcx, rax; this
0x18004718f  call    ?EventWriteWebUploadContainer@ConnectedStorage@@YAXQEBG00IIII@Z; ConnectedStorage::EventWriteWebUploadContainer(ushort const * const,ushort const * const,ushort const * const,uint,uint,uint,uint)
0x180047194  mov     [rsp+308h+var_298], rsi
0x180047199  lea     r8, [rsp+308h+var_298]
0x18004719e  mov     edx, 1
0x1800471a3  mov     r15, [rsp+308h+var_268]
0x1800471ab  mov     rcx, r15
0x1800471ae  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x1800471b3  nop
0x1800471b4  mov     rcx, [rsp+308h+var_298]; string
  ... truncated ...
```
