# PrinterCleanUpUtil::CheckForUnusedRemovablePrinters(bool *)

- ea: `0x180011ea8`
- end: `0x1800123a0`
- name: `?CheckForUnusedRemovablePrinters@PrinterCleanUpUtil@@YAJPEA_N@Z`
- size: `1272`
- prototype: `__int64 __fastcall(PrinterCleanUpUtil *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014814`

## callees

- `0x180002020`
- `0x180002490`
- `0x18000670c`
- `0x180007090`
- `0x180007118`
- `0x18000750c`
- `0x1800098b0`
- `0x18000a280`
- `0x18000a2d4`
- `0x18000a300`
- `0x18000a360`
- `0x18000aaec`
- `0x18000bf48`
- `0x18000c09c`
- `0x18000c31c`
- `0x18000d1c0`
- `0x18000d3d8`
- `0x18000db1c`
- `0x18000dfa4`
- `0x18000ea04`
- `0x18000f26c`
- `0x18000f554`
- `0x180010918`
- `0x180010f98`
- `0x180011060`
- `0x18001166c`
- `0x180011ea8`
- `0x1800127ac`
- `0x180014cc0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011f26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012291`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011f26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012291`

## string_xrefs

- `0x180012283`: `SYSTEM\CurrentControlSet\Control\Print\PrinterCleanupTask\`
- `0x180011f11`: `NoDeletePrinter`
- `0x1800122ff`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PrinterCleanUpUtil::CheckForUnusedRemovablePrinters(PrinterCleanUpUtil *this, bool *a2)
{
  int v3; // edi
  __int64 AllAsync; // rax
  unsigned int v6; // r14d
  int v7; // r12d
  __int64 v8; // rdx
  __int64 v9; // rdx
  winrt::hstring *Default; // rsi
  const unsigned __int16 *v11; // rax
  __int64 v12; // r10
  char v13; // bl
  LSTATUS ValueW; // eax
  DWORD v15; // ecx
  struct _FILETIME CurrentFileTime; // rbx
  winrt::hstring *v17; // rax
  const unsigned __int16 *v18; // rax
  int UserInteractionDate; // eax
  int pdwType; // [rsp+20h] [rbp-188h]
  int pvData; // [rsp+40h] [rbp-168h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-164h] BYREF
  DWORD v23[2]; // [rsp+48h] [rbp-160h] BYREF
  _BYTE v24[8]; // [rsp+50h] [rbp-158h] BYREF
  __int64 v25; // [rsp+58h] [rbp-150h] BYREF
  _BYTE v26[8]; // [rsp+60h] [rbp-148h] BYREF
  _BYTE v27[8]; // [rsp+68h] [rbp-140h] BYREF
  int v28; // [rsp+70h] [rbp-138h] BYREF
  __int64 v29; // [rsp+78h] [rbp-130h] BYREF
  __int64 v30; // [rsp+80h] [rbp-128h] BYREF
  __int64 v31; // [rsp+88h] [rbp-120h] BYREF
  unsigned __int64 v32; // [rsp+90h] [rbp-118h]
  _BYTE v33[8]; // [rsp+98h] [rbp-110h] BYREF
  _QWORD v34[2]; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-F8h] BYREF
  char v36; // [rsp+B8h] [rbp-F0h]
  _BYTE v37[8]; // [rsp+C0h] [rbp-E8h] BYREF
  _BYTE v38[8]; // [rsp+C8h] [rbp-E0h] BYREF
  _BYTE v39[8]; // [rsp+D0h] [rbp-D8h] BYREF
  _BYTE v40[8]; // [rsp+D8h] [rbp-D0h] BYREF
  unsigned __int64 v41; // [rsp+E0h] [rbp-C8h] BYREF
  _BYTE v42[8]; // [rsp+E8h] [rbp-C0h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v44[32]; // [rsp+110h] [rbp-98h] BYREF
  _BYTE v45[32]; // [rsp+130h] [rbp-78h] BYREF
  _BYTE v46[32]; // [rsp+150h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v3 = 0;
  v23[0] = 0;
  *(_BYTE *)this = 0;
  pvData = 0;
  pcbData = 4;
  RegGetValueW(
    HKEY_CURRENT_USER,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\",
    L"NoDeletePrinter",
    0x20000018u,
    0,
    &pvData,
    &pcbData);
  if ( pvData )
    return 0;
  v28 = 2;
  winrt::hstring::hstring((winrt::hstring *)v37, L"{F9D889C3-EE16-4E54-9551-199DA2F83490} 2");
  winrt::hstring::hstring((winrt::hstring *)v38, L"{78C34FC8-104A-4ACA-9EA4-524D52996E57} 97");
  v34[0] = v37;
  v34[1] = v39;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v35, v34);
  GetLocalPrinterSelector(v46, 0);
  winrt::param::hstring::hstring((winrt::param::hstring *)v44);
  AllAsync = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(v39, v44, &v35, &v28);
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
    AllAsync,
    v24);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v39);
  std::wstring::_Tidy_deallocate(v46);
  if ( !v36 )
    v35 = 0;
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v35);
  `eh vector destructor iterator'(v37, 8u, 2u, (void (*)(void *))winrt::hstring::~hstring);
  v6 = 0;
  v7 = winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(v24);
  while ( v6 != v7 )
  {
    winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::GetAt(
      v24,
      v27,
      v6);
    winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
      v27,
      v26);
    winrt::param::hstring::hstring((winrt::param::hstring *)v43, L"System.ItemNameDisplay");
    v8 = winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
           v26,
           &v29,
           v43);
    winrt::unbox_value<winrt::hstring>(v34, v8);
    if ( v29 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
    winrt::param::hstring::hstring((winrt::param::hstring *)v45, L"{78C34FC8-104A-4ACA-9EA4-524D52996E57} 97");
    v9 = winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
           v26,
           &v30,
           v45);
    winrt::unbox_value<winrt::hstring>(v33, v9);
    if ( v30 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v30);
    v3 |= 1u;
    if ( (unsigned __int8)winrt::operator==(v33, L"PrintFax.Printer") )
    {
      Default = (winrt::hstring *)winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(
                                    v27,
                                    v40);
      *(_QWORD *)v23 = Default;
      wil::CoCreateInstance<IDsmControl,wil::err_exception_policy>(&v31);
      pvData = 0;
      v11 = winrt::hstring::c_str(Default);
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, int *))(*(_QWORD *)v12 + 72LL))(v12, v11, &pvData) < 0
        || (v13 = 1, (pvData & 1) == 0) )
      {
        v13 = 0;
      }
      v3 |= 2u;
      wil::com_ptr_t<IDsmControl,wil::err_exception_policy>::~com_ptr_t<IDsmControl,wil::err_exception_policy>(&v31);
      winrt::handle_type<winrt::impl::hstring_traits>::close(Default);
      if ( v13 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v43, L"{F9D889C3-EE16-4E54-9551-199DA2F83490} 2");
        winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
          v26,
          &v25,
          v43);
        if ( v25 )
        {
          winrt::impl::unbox_value_type<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,winrt::Windows::Foundation::IInspectable const &>(
            &v41,
            &v25);
          v32 = v41;
          if ( !*(_BYTE *)this )
          {
            pcbData = 0;
            v23[0] = 4;
            ValueW = RegGetValueW(
                       HKEY_LOCAL_MACHINE,
                       L"SYSTEM\\CurrentControlSet\\Control\\Print\\PrinterCleanupTask\\",
                       L"PrinterUnusedDaysCondition",
                       0x20000018u,
                       0,
                       &pcbData,
                       v23);
            v15 = 90;
            if ( !ValueW )
              v15 = pcbData;
            *(_BYTE *)this = IsStale(v32, 864000000000LL * v15);
          }
        }
        else
        {
          CurrentFileTime = GetCurrentFileTime();
          v17 = (winrt::hstring *)winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(
                                    v27,
                                    v42);
          v18 = winrt::hstring::c_str(v17);
          UserInteractionDate = _SetLastUserInteractionDate(v18, CurrentFileTime);
          if ( UserInteractionDate < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0xCF,
              (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
              (const char *)(unsigned int)UserInteractionDate,
              pdwType);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v42);
        }
        if ( v25 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
      }
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(v33);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v34);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v26);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v27);
    ++v6;
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v24);
  return 0;
}

```

## disassembly

```asm
0x180011ea8  mov     [rsp+arg_8], rbx
0x180011ead  mov     [rsp+arg_10], rsi
0x180011eb2  push    rdi
0x180011eb3  push    r12
0x180011eb5  push    r13
0x180011eb7  push    r14
0x180011eb9  push    r15
0x180011ebb  sub     rsp, 180h
0x180011ec2  mov     rax, cs:__security_cookie
0x180011ec9  xor     rax, rsp
0x180011ecc  mov     [rsp+1A8h+var_38], rax
0x180011ed4  mov     r15, rcx
0x180011ed7  xor     r13d, r13d
0x180011eda  mov     edi, r13d
0x180011edd  mov     [rsp+1A8h+var_160], r13d
0x180011ee2  mov     [rcx], r13b
0x180011ee5  mov     [rsp+1A8h+var_168], r13d
0x180011eea  mov     [rsp+1A8h+var_164], 4
0x180011ef2  lea     rax, [rsp+1A8h+var_164]
0x180011ef7  mov     [rsp+1A8h+pcbData], rax; pcbData
0x180011efc  lea     rax, [rsp+1A8h+var_168]
0x180011f01  mov     [rsp+1A8h+pvData], rax; pvData
0x180011f06  mov     [rsp+1A8h+pdwType], r13; int
0x180011f0b  mov     r9d, 20000018h; dwFlags
0x180011f11  lea     r8, aNodeleteprinte; "NoDeletePrinter"
0x180011f18  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180011f1f  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180011f26  call    cs:__imp_RegGetValueW
0x180011f2c  cmp     [rsp+1A8h+var_168], r13d
0x180011f31  jz      short loc_180011F3A
0x180011f33  xor     eax, eax
0x180011f35  jmp     loc_180012372
0x180011f3a  mov     ebx, 2
0x180011f3f  mov     [rsp+1A8h+var_138], ebx
0x180011f43  lea     rdx, aF9d889c3Ee164e; "{F9D889C3-EE16-4E54-9551-199DA2F83490} "...
0x180011f4a  lea     rcx, [rsp+1A8h+var_E8]; this
0x180011f52  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180011f57  nop
0x180011f58  lea     rdx, a78c34fc8104a4a; "{78C34FC8-104A-4ACA-9EA4-524D52996E57} "...
0x180011f5f  lea     rcx, [rsp+1A8h+var_E0]; this
0x180011f67  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180011f6c  nop
0x180011f6d  lea     rax, [rsp+1A8h+var_E8]
0x180011f75  mov     [rsp+1A8h+var_108], rax
0x180011f7d  lea     rax, [rsp+1A8h+var_D8]
0x180011f85  mov     [rsp+1A8h+var_100], rax
0x180011f8d  lea     rdx, [rsp+1A8h+var_108]
0x180011f95  lea     rcx, [rsp+1A8h+var_F8]
0x180011f9d  call    ??0?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@V?$initializer_list@Uhstring@winrt@@@std@@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(std::initializer_list<winrt::hstring>)
0x180011fa2  nop
0x180011fa3  xor     edx, edx
0x180011fa5  lea     rcx, [rsp+1A8h+var_58]
0x180011fad  call    ?GetLocalPrinterSelector@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetLocalPrinterSelector(ushort const *)
0x180011fb2  nop
0x180011fb3  mov     rdx, rax
0x180011fb6  lea     rcx, [rsp+1A8h+var_98]; this
0x180011fbe  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180011fc3  lea     r9, [rsp+1A8h+var_138]
0x180011fc8  lea     r8, [rsp+1A8h+var_F8]
0x180011fd0  lea     rdx, [rsp+1A8h+var_98]
0x180011fd8  lea     rcx, [rsp+1A8h+var_D8]
0x180011fe0  call    ?FindAllAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@5@AEBU?$async_iterable@Uhstring@winrt@@@75@AEBW4DeviceInformationKind@2345@@Z; winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)
0x180011fe5  nop
0x180011fe6  lea     rdx, [rsp+1A8h+var_158]
0x180011feb  mov     rcx, rax
0x180011fee  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformationCollection@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(void)
0x180011ff3  nop
0x180011ff4  lea     rcx, [rsp+1A8h+var_D8]; this
0x180011ffc  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180012001  nop
0x180012002  lea     rcx, [rsp+1A8h+var_58]
0x18001200a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001200f  nop
0x180012010  cmp     [rsp+1A8h+var_F0], r13b
0x180012018  jnz     short loc_180012022
0x18001201a  mov     [rsp+1A8h+var_F8], r13
0x180012022  lea     rcx, [rsp+1A8h+var_F8]; this
0x18001202a  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18001202f  nop
0x180012030  lea     r9, ??1hstring@winrt@@QEAA@XZ; void (*)(void *)
0x180012037  mov     r8, rbx; unsigned __int64
0x18001203a  mov     edx, 8; unsigned __int64
0x18001203f  lea     rcx, [rsp+1A8h+var_E8]; void *
0x180012047  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001204c  lea     rbx, [rsp+1A8h+var_158]
0x180012051  mov     r14d, r13d
0x180012054  lea     rcx, [rsp+1A8h+var_158]
0x180012059  call    ?Size@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(void)
0x18001205e  mov     r12d, eax
0x180012061  cmp     r14d, r12d
0x180012064  jnz     short loc_180012077
0x180012066  lea     rcx, [rsp+1A8h+var_158]; this
0x18001206b  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180012070  xor     eax, eax
0x180012072  jmp     loc_180012372
0x180012077  mov     r8d, r14d
0x18001207a  lea     rdx, [rsp+1A8h+var_140]
0x18001207f  mov     rcx, rbx
0x180012082  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::GetAt(uint)
0x180012087  nop
0x180012088  lea     rdx, [rsp+1A8h+var_148]
0x18001208d  lea     rcx, [rsp+1A8h+var_140]
0x180012092  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x180012097  nop
0x180012098  lea     rdx, aSystemItemname_0; "System.ItemNameDisplay"
0x18001209f  lea     rcx, [rsp+1A8h+var_B8]; this
0x1800120a7  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800120ac  lea     r8, [rsp+1A8h+var_B8]
0x1800120b4  lea     rdx, [rsp+1A8h+var_130]
0x1800120b9  lea     rcx, [rsp+1A8h+var_148]
0x1800120be  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1800120c3  nop
0x1800120c4  mov     rdx, rax
0x1800120c7  lea     rcx, [rsp+1A8h+var_108]
0x1800120cf  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x1800120d4  nop
0x1800120d5  cmp     [rsp+1A8h+var_130], r13
0x1800120da  jz      short loc_1800120E6
0x1800120dc  lea     rcx, [rsp+1A8h+var_130]
0x1800120e1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800120e6  lea     rdx, a78c34fc8104a4a; "{78C34FC8-104A-4ACA-9EA4-524D52996E57} "...
0x1800120ed  lea     rcx, [rsp+1A8h+var_78]; this
0x1800120f5  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800120fa  lea     r8, [rsp+1A8h+var_78]
0x180012102  lea     rdx, [rsp+1A8h+var_128]
0x18001210a  lea     rcx, [rsp+1A8h+var_148]
0x18001210f  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x180012114  nop
0x180012115  mov     rdx, rax
0x180012118  lea     rcx, [rsp+1A8h+var_110]
0x180012120  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x180012125  nop
0x180012126  cmp     [rsp+1A8h+var_128], r13
0x18001212e  jz      short loc_18001213D
0x180012130  lea     rcx, [rsp+1A8h+var_128]
0x180012138  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001213d  or      edi, 1
0x180012140  lea     rdx, aPrintfaxPrinte; "PrintFax.Printer"
0x180012147  lea     rcx, [rsp+1A8h+var_110]
0x18001214f  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x180012154  test    al, al
0x180012156  jz      loc_180012335
0x18001215c  lea     rdx, [rsp+1A8h+var_D0]
0x180012164  lea     rcx, [rsp+1A8h+var_140]
0x180012169  call    ?GetDefault@?$consume_Windows_UI_Notifications_IToastNotificationManagerStatics5@UIToastNotificationManagerStatics5@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(void)
0x18001216e  mov     rsi, rax
0x180012171  mov     qword ptr [rsp+1A8h+var_160], rax
0x180012176  lea     rcx, [rsp+1A8h+var_120]
0x18001217e  call    ??$CoCreateInstance@UIDsmControl@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIDsmControl@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IDsmControl,wil::err_exception_policy>(_GUID const &,ulong)
0x180012183  nop
0x180012184  mov     [rsp+1A8h+var_168], r13d
0x180012189  mov     r10, [rsp+1A8h+var_120]
0x180012191  mov     rcx, rsi; this
0x180012194  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180012199  mov     rdx, [r10]
0x18001219c  mov     r9, [rdx+48h]
0x1800121a0  lea     r8, [rsp+1A8h+var_168]
0x1800121a5  mov     rdx, rax
0x1800121a8  mov     rcx, r10
0x1800121ab  mov     rax, r9
0x1800121ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121b3  test    eax, eax
0x1800121b5  js      short loc_1800121C0
0x1800121b7  test    byte ptr [rsp+1A8h+var_168], 1
0x1800121bc  mov     bl, 1
0x1800121be  jnz     short loc_1800121C3
0x1800121c0  mov     bl, r13b
0x1800121c3  or      edi, 2
0x1800121c6  lea     rcx, [rsp+1A8h+var_120]
0x1800121ce  call    ??1?$com_ptr_t@UIDsmControl@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDsmControl,wil::err_exception_policy>::~com_ptr_t<IDsmControl,wil::err_exception_policy>(void)
0x1800121d3  nop
0x1800121d4  mov     rcx, rsi
0x1800121d7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800121dc  test    bl, bl
0x1800121de  jz      loc_180012330
0x1800121e4  lea     rdx, aF9d889c3Ee164e; "{F9D889C3-EE16-4E54-9551-199DA2F83490} "...
0x1800121eb  lea     rcx, [rsp+1A8h+var_B8]; this
0x1800121f3  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800121f8  lea     r8, [rsp+1A8h+var_B8]
0x180012200  lea     rdx, [rsp+1A8h+var_150]
0x180012205  lea     rcx, [rsp+1A8h+var_148]
0x18001220a  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18001220f  nop
0x180012210  cmp     [rsp+1A8h+var_150], r13
0x180012215  jz      loc_1800122C2
0x18001221b  lea     rdx, [rsp+1A8h+var_150]
0x180012220  lea     rcx, [rsp+1A8h+var_C8]
0x180012228  call    ??$unbox_value_type@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@AEBUIInspectable@Foundation@Windows@winrt@@@impl@winrt@@YA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@AEBUIInspectable@Foundation@Windows@1@@Z; winrt::impl::unbox_value_type<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,winrt::Windows::Foundation::IInspectable const &>(winrt::Windows::Foundation::IInspectable const &)
0x18001222d  mov     rax, [rsp+1A8h+var_C8]
0x180012235  mov     dword ptr [rsp+1A8h+var_118], eax
0x18001223c  shr     rax, 20h
0x180012240  mov     dword ptr [rsp+1A8h+var_118+4], eax
0x180012247  cmp     [r15], r13b
0x18001224a  jnz     loc_18001231F
0x180012250  mov     [rsp+1A8h+var_164], r13d
0x180012255  mov     [rsp+1A8h+var_160], 4
0x18001225d  lea     rax, [rsp+1A8h+var_160]
0x180012262  mov     [rsp+1A8h+pcbData], rax; pcbData
0x180012267  lea     rax, [rsp+1A8h+var_164]
0x18001226c  mov     [rsp+1A8h+pvData], rax; pvData
0x180012271  mov     [rsp+1A8h+pdwType], r13; pdwType
0x180012276  mov     r9d, 20000018h; dwFlags
0x18001227c  lea     r8, aPrinterunusedd; "PrinterUnusedDaysCondition"
0x180012283  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x18001228a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180012291  call    cs:__imp_RegGetValueW
0x180012297  mov     ecx, 5Ah ; 'Z'
0x18001229c  test    eax, eax
0x18001229e  cmovz   ecx, [rsp+1A8h+var_164]
0x1800122a3  imul    ecx, 15180h
0x1800122a9  imul    rdx, rcx, 989680h; unsigned __int64
0x1800122b0  mov     rcx, [rsp+1A8h+var_118]; unsigned __int64
0x1800122b8  call    ?IsStale@@YA_N_K0@Z; IsStale(unsigned __int64,unsigned __int64)
0x1800122bd  mov     [r15], al
0x1800122c0  jmp     short loc_18001231F
0x1800122c2  call    ?GetCurrentFileTime@@YA?AU_FILETIME@@XZ; GetCurrentFileTime(void)
0x1800122c7  mov     rbx, rax
0x1800122ca  lea     rdx, [rsp+1A8h+var_C0]
0x1800122d2  lea     rcx, [rsp+1A8h+var_140]
0x1800122d7  call    ?GetDefault@?$consume_Windows_UI_Notifications_IToastNotificationManagerStatics5@UIToastNotificationManagerStatics5@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(void)
0x1800122dc  nop
0x1800122dd  mov     rcx, rax; this
0x1800122e0  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800122e5  mov     rdx, rbx; struct _FILETIME
0x1800122e8  mov     rcx, rax; unsigned __int16 *
0x1800122eb  call    ?_SetLastUserInteractionDate@@YAJPEBGU_FILETIME@@@Z; _SetLastUserInteractionDate(ushort const *,_FILETIME)
0x1800122f0  mov     rcx, [rsp+1A8h]; this
0x1800122f8  test    eax, eax
0x1800122fa  jns     short loc_180012311
0x1800122fc  mov     r9d, eax; char *
0x1800122ff  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180012306  mov     edx, 0CFh; void *
0x18001230b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012311  lea     rcx, [rsp+1A8h+var_C0]
0x180012319  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001231e  nop
0x18001231f  cmp     [rsp+1A8h+var_150], r13
0x180012324  jz      short loc_180012330
0x180012326  lea     rcx, [rsp+1A8h+var_150]
0x18001232b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012330  lea     rbx, [rsp+1A8h+var_158]
0x180012335  lea     rcx, [rsp+1A8h+var_110]
0x18001233d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180012342  nop
0x180012343  lea     rcx, [rsp+1A8h+var_108]
0x18001234b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180012350  nop
0x180012351  lea     rcx, [rsp+1A8h+var_148]; this
0x180012356  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18001235b  nop
0x18001235c  lea     rcx, [rsp+1A8h+var_140]; this
0x180012361  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180012366  inc     r14d
0x180012369  jmp     loc_180012061
0x18001236e  mov     eax, [rsp+1A8h+var_160]
0x180012372  mov     rcx, [rsp+1A8h+var_38]
0x18001237a  xor     rcx, rsp; StackCookie
0x18001237d  call    __security_check_cookie
0x180012382  lea     r11, [rsp+1A8h+var_28]
0x18001238a  mov     rbx, [r11+38h]
0x18001238e  mov     rsi, [r11+40h]
0x180012392  mov     rsp, r11
0x180012395  pop     r15
0x180012397  pop     r14
0x180012399  pop     r13
0x18001239b  pop     r12
0x18001239d  pop     rdi
0x18001239e  retn
```
