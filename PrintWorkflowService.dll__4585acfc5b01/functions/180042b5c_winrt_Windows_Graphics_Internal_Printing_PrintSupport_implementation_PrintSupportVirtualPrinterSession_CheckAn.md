# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CheckAndStartPdlConversionIfNeeded(void)

- ea: `0x180042b5c`
- end: `0x180042d23`
- name: `?CheckAndStartPdlConversionIfNeeded@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA_NXZ`
- size: `455`
- prototype: `bool __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b250`

## callees

- `0x180003ca0`
- `0x1800097ec`
- `0x18000a074`
- `0x18000a6a0`
- `0x18000b360`
- `0x180012784`
- `0x1800127a4`
- `0x180012820`
- `0x1800129dc`
- `0x180012b10`
- `0x180027dd4`
- `0x180032c60`
- `0x1800334dc`
- `0x180041ba0`
- `0x1800421b0`
- `0x180042b5c`
- `0x180042dc8`
- `0x180043694`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042bb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042c1a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042bb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042c1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042c85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042c85`

## string_xrefs

- `0x180042d11`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CheckAndStartPdlConversionIfNeeded(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *this)
{
  winrt::hstring *v2; // rdi
  const unsigned __int16 *v3; // rax
  const unsigned __int16 *v4; // rax
  __int64 PreferredInputFormatForVirtualPrinter; // rax
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  int v10; // r8d
  int v11; // r9d
  struct IUnknown *v12; // rdx
  LPVOID *v13; // rax
  HRESULT Instance; // eax
  __int64 FolderFromPathAsync; // rax
  int ppv; // [rsp+20h] [rbp-60h]
  __int64 v18; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v2 = (winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *)((char *)this + 472);
  if ( !*((_QWORD *)this + 59) )
  {
    PrintSupportSessionCommon::SessionInitDataHandler::GetSourcePdlFormat(*((_QWORD *)this + 8), &v18);
    v3 = winrt::hstring::c_str((winrt::hstring *)&v18);
    if ( !(unsigned int)_o__wcsicmp(v3, L"application/oxps") )
    {
      v4 = winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *)((char *)this + 88));
      PreferredInputFormatForVirtualPrinter = VirtualPrinterHelper::GetPreferredInputFormatForVirtualPrinter(v22, v4);
      v20[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(PreferredInputFormatForVirtualPrinter);
      v20[1] = *(_QWORD *)(v6 + 16);
      winrt::hstring::operator=(v2, v20);
      std::wstring::_Tidy_deallocate(v22);
      winrt::hstring::c_str(v2);
      v7 = winrt::hstring::c_str((winrt::hstring *)&v18);
      if ( (unsigned int)_o__wcsicmp(v8, v7) )
      {
        *((_BYTE *)this + 488) = 1;
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CreateTemporaryFileHandlesForPreferredPdl(
          this,
          v9,
          v10,
          v11);
      }
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
  }
  if ( *((_BYTE *)this + 488) )
  {
    wil::AcquireSRWLockExclusive(v20, (char *)this + 496);
    v18 = 0;
    v13 = winrt::put_abi((winrt *)&v18, v12);
    Instance = CoCreateInstance(&stru_18006BB88, 0, 4u, &GUID_1225d816_5a86_4945_9b97_ec2ed739046c, v13);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
    winrt::make<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterAppSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession &>(
      v19,
      this);
    FolderFromPathAsync = winrt::impl::consume_Windows_Storage_IStorageFolderStatics<winrt::Windows::Storage::IStorageFolderStatics>::GetFolderFromPathAsync(
                            &v18,
                            v21,
                            v19);
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 480, FolderFromPathAsync);
    winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v21);
    winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v19);
    winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)&v18);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v20);
  }
  return *((_BYTE *)this + 488);
}

```

## disassembly

```asm
0x180042b5c  mov     [rsp-8+arg_8], rbx
0x180042b61  mov     [rsp-8+arg_10], rdi
0x180042b66  push    rbp
0x180042b67  mov     rbp, rsp
0x180042b6a  sub     rsp, 80h
0x180042b71  mov     rax, cs:__security_cookie
0x180042b78  xor     rax, rsp
0x180042b7b  mov     [rbp+var_8], rax
0x180042b7f  mov     rbx, rcx
0x180042b82  lea     rdi, [rcx+1D8h]
0x180042b89  cmp     qword ptr [rdi], 0
0x180042b8d  jnz     loc_180042C3D
0x180042b93  lea     rdx, [rbp+var_50]
0x180042b97  mov     rcx, [rcx+40h]
0x180042b9b  call    ?GetSourcePdlFormat@SessionInitDataHandler@PrintSupportSessionCommon@@QEAA?AUhstring@winrt@@XZ; PrintSupportSessionCommon::SessionInitDataHandler::GetSourcePdlFormat(void)
0x180042ba0  nop
0x180042ba1  lea     rcx, [rbp+var_50]; this
0x180042ba5  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042baa  mov     rcx, rax
0x180042bad  lea     rdx, aApplicationOxp; "application/oxps"
0x180042bb4  call    cs:__imp__o__wcsicmp
0x180042bba  test    eax, eax
0x180042bbc  jnz     short loc_180042C34
0x180042bbe  lea     rcx, [rbx+58h]; this
0x180042bc2  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042bc7  mov     rdx, rax
0x180042bca  lea     rcx, [rbp+var_28]
0x180042bce  call    ?GetPreferredInputFormatForVirtualPrinter@VirtualPrinterHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; VirtualPrinterHelper::GetPreferredInputFormatForVirtualPrinter(ushort const *)
0x180042bd3  mov     rdx, rax
0x180042bd6  mov     rcx, rax
0x180042bd9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042bde  mov     [rbp+var_40], rax
0x180042be2  mov     rax, [rdx+10h]
0x180042be6  mov     [rbp+var_38], rax
0x180042bea  lea     rdx, [rbp+var_40]
0x180042bee  mov     rcx, rdi
0x180042bf1  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x180042bf6  nop
0x180042bf7  lea     rcx, [rbp+var_28]
0x180042bfb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042c00  mov     rcx, rdi; this
0x180042c03  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042c08  mov     r8, rax
0x180042c0b  lea     rcx, [rbp+var_50]; this
0x180042c0f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180042c14  mov     rdx, rax
0x180042c17  mov     rcx, r8
0x180042c1a  call    cs:__imp__o__wcsicmp
0x180042c20  test    eax, eax
0x180042c22  jz      short loc_180042C34
0x180042c24  mov     byte ptr [rbx+1E8h], 1
0x180042c2b  mov     rcx, rbx; this
0x180042c2e  call    ?CreateTemporaryFileHandlesForPreferredPdl@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::CreateTemporaryFileHandlesForPreferredPdl(void)
0x180042c33  nop
0x180042c34  lea     rcx, [rbp+var_50]
0x180042c38  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180042c3d  cmp     byte ptr [rbx+1E8h], 0
0x180042c44  jz      loc_180042CE7
0x180042c4a  lea     rdx, [rbx+1F0h]
0x180042c51  lea     rcx, [rbp+var_40]
0x180042c55  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180042c5a  nop
0x180042c5b  mov     [rbp+var_50], 0
0x180042c63  lea     rcx, [rbp+var_50]; this
0x180042c67  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180042c6c  mov     qword ptr [rsp+80h+ppv], rax; int
0x180042c71  lea     r9, _GUID_1225d816_5a86_4945_9b97_ec2ed739046c; riid
0x180042c78  xor     edx, edx; pUnkOuter
0x180042c7a  lea     r8d, [rdx+4]; dwClsContext
0x180042c7e  lea     rcx, stru_18006BB88; rclsid
0x180042c85  call    cs:__imp_CoCreateInstance
0x180042c8b  mov     rcx, [rbp+8]; this
0x180042c8f  test    eax, eax
0x180042c91  js      short loc_180042D0E
0x180042c93  mov     rdx, rbx
0x180042c96  lea     rcx, [rbp+var_48]
0x180042c9a  call    ??$make@UPrintSupportVirtualPrinterAppSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAUPrintSupportVirtualPrinterSession@2345678@@winrt@@YA?A_PAEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@0@@Z
0x180042c9f  nop
0x180042ca0  lea     r8, [rbp+var_48]
0x180042ca4  lea     rdx, [rbp+var_30]
0x180042ca8  lea     rcx, [rbp+var_50]
0x180042cac  call    ?GetFolderFromPathAsync@?$consume_Windows_Storage_IStorageFolderStatics@UIStorageFolderStatics@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Storage_IStorageFolderStatics<winrt::Windows::Storage::IStorageFolderStatics>::GetFolderFromPathAsync(winrt::param::hstring const &)
0x180042cb1  lea     rcx, [rbx+1E0h]
0x180042cb8  mov     rdx, rax
0x180042cbb  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180042cc0  lea     rcx, [rbp+var_30]; this
0x180042cc4  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180042cc9  nop
0x180042cca  lea     rcx, [rbp+var_48]; this
0x180042cce  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180042cd3  nop
0x180042cd4  lea     rcx, [rbp+var_50]; this
0x180042cd8  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180042cdd  nop
0x180042cde  lea     rcx, [rbp+var_40]
0x180042ce2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180042ce7  mov     al, [rbx+1E8h]
0x180042ced  mov     rcx, [rbp+var_8]
0x180042cf1  xor     rcx, rsp; StackCookie
0x180042cf4  call    __security_check_cookie
0x180042cf9  lea     r11, [rsp+80h+var_s0]
0x180042d01  mov     rbx, [r11+18h]
0x180042d05  mov     rdi, [r11+20h]
0x180042d09  mov     rsp, r11
0x180042d0c  pop     rbp
0x180042d0d  retn
0x180042d0e  mov     r9d, eax; char *
0x180042d11  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180042d18  mov     edx, 1B9h; void *
0x180042d1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
