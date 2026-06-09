# SetLastUserInteractionDate

- ea: `0x180015400`
- end: `0x180015681`
- name: `SetLastUserInteractionDate`
- size: `641`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180002020`
- `0x18000670c`
- `0x180007090`
- `0x180007118`
- `0x180008008`
- `0x18000a280`
- `0x18000a360`
- `0x18000a6e0`
- `0x18000bf48`
- `0x18000c09c`
- `0x18000c31c`
- `0x18000d1c0`
- `0x18000ea04`
- `0x18000f554`
- `0x1800127ac`
- `0x1800147b8`
- `0x180014cc0`
- `0x180015400`

## import_xrefs

- `Print.PrintSupport.Source!GetDeviceContainerIdByPerUserPrinterName` at `0x18001554c`
- `Print.PrintSupport.Source!GetDeviceContainerIdByPerUserPrinterName` at `0x18001554c`

## string_xrefs

- `0x18001551c`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x180015578`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x180015644`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x180015659`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x18001566e`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SetLastUserInteractionDate(char *a1)
{
  __int64 AllAsync; // rax
  unsigned int v3; // eax
  int DeviceContainerIdByPerUserPrinterName; // eax
  struct _FILETIME CurrentFileTime; // rax
  int v6; // eax
  __int64 **v7; // rax
  const unsigned __int16 *v8; // rax
  struct _FILETIME v9; // rdx
  int UserInteractionDate; // eax
  const char *v11; // r9
  __int64 result; // rax
  int v13; // [rsp+20h] [rbp-A8h]
  int v14; // [rsp+20h] [rbp-A8h]
  int v15; // [rsp+20h] [rbp-A8h]
  unsigned __int16 *v16; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v17[8]; // [rsp+48h] [rbp-80h] BYREF
  volatile signed __int32 *v18; // [rsp+50h] [rbp-78h] BYREF
  __int64 v19; // [rsp+58h] [rbp-70h] BYREF
  char v20; // [rsp+60h] [rbp-68h]
  _BYTE v21[8]; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v22[8]; // [rsp+70h] [rbp-58h] BYREF
  _BYTE v23[32]; // [rsp+78h] [rbp-50h] BYREF
  _QWORD *v24; // [rsp+98h] [rbp-30h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x137,
        (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
        (const char *)0x80070057LL,
        v13);
    LODWORD(v16) = 2;
    v19 = 0;
    v20 = 1;
    GetLocalPrinterSelector(&v24, a1);
    winrt::param::hstring::hstring((winrt::param::hstring *)v23);
    AllAsync = winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(v21, v23, &v19, &v16);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(
      AllAsync,
      v17);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v21);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v24, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v24) = 0;
    if ( !v20 )
      v19 = 0;
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v19);
    v3 = winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(v17);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x13E,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
      (const char *)0x8007000DLL,
      v3 > 1,
      (bool)"Too many device containers found with name: %ls",
      a1);
    if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(v17) )
    {
      v7 = (__int64 **)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::GetAt(
                         v17,
                         v22,
                         0);
      winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(
        v7,
        &v18);
      winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v22);
      GetCurrentFileTime();
      v8 = winrt::hstring::c_str((winrt::hstring *)&v18);
      UserInteractionDate = _SetLastUserInteractionDate(v8, v9);
      if ( UserInteractionDate < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14B,
          (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
          (const char *)(unsigned int)UserInteractionDate,
          v14);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
    }
    else
    {
      v16 = 0;
      DeviceContainerIdByPerUserPrinterName = GetDeviceContainerIdByPerUserPrinterName(a1, &v16);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x145,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
        (const char *)0x8007000DLL,
        DeviceContainerIdByPerUserPrinterName < 0,
        (bool)"No device containers found with name: %ls",
        a1);
      CurrentFileTime = GetCurrentFileTime();
      v6 = _SetLastUserInteractionDate(v16, CurrentFileTime);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x146,
          (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
          (const char *)(unsigned int)v6,
          v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v16);
    }
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v17);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x150,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180015400  push    rdi
0x180015402  sub     rsp, 0C0h
0x180015409  mov     rax, cs:__security_cookie
0x180015410  xor     rax, rsp
0x180015413  mov     [rsp+0C8h+var_10], rax
0x18001541b  mov     rdi, rcx
0x18001541e  mov     rcx, [rsp+0C8h]; this
0x180015426  test    rdi, rdi
0x180015429  jz      loc_18001563E
0x18001542f  mov     dword ptr [rsp+0C8h+var_88], 2
0x180015437  mov     [rsp+0C8h+var_70], 0
0x180015440  mov     [rsp+0C8h+var_68], 1
0x180015445  mov     rdx, rdi
0x180015448  lea     rcx, [rsp+0C8h+var_30]
0x180015450  call    ?GetLocalPrinterSelector@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetLocalPrinterSelector(ushort const *)
0x180015455  nop
0x180015456  mov     rdx, rax
0x180015459  lea     rcx, [rsp+0C8h+var_50]; this
0x18001545e  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x180015463  lea     r9, [rsp+0C8h+var_88]
0x180015468  lea     r8, [rsp+0C8h+var_70]
0x18001546d  lea     rdx, [rsp+0C8h+var_50]
0x180015472  lea     rcx, [rsp+0C8h+var_60]
0x180015477  call    ?FindAllAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@5@AEBU?$async_iterable@Uhstring@winrt@@@75@AEBW4DeviceInformationKind@2345@@Z; winrt::Windows::Devices::Enumeration::DeviceInformation::FindAllAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)
0x18001547c  nop
0x18001547d  lea     rdx, [rsp+0C8h+var_80]
0x180015482  mov     rcx, rax
0x180015485  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformationCollection@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformationCollection@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformationCollection>,winrt::Windows::Devices::Enumeration::DeviceInformationCollection>::get(void)
0x18001548a  nop
0x18001548b  lea     rcx, [rsp+0C8h+var_60]; this
0x180015490  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180015495  nop
0x180015496  mov     rdx, [rsp+0C8h+var_18]
0x18001549e  cmp     rdx, 7
0x1800154a2  jbe     short loc_1800154B9
0x1800154a4  lea     rdx, ds:2[rdx*2]
0x1800154ac  mov     rcx, [rsp+0C8h+var_30]
0x1800154b4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800154b9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800154c1  movdqu  xmmword ptr [rsp+0A8h], xmm0
0x1800154ca  xor     eax, eax
0x1800154cc  mov     word ptr [rsp+0C8h+var_30], ax
0x1800154d4  cmp     [rsp+0C8h+var_68], al
0x1800154d8  jnz     short loc_1800154DF
0x1800154da  mov     [rsp+0C8h+var_70], rax
0x1800154df  lea     rcx, [rsp+0C8h+var_70]; this
0x1800154e4  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x1800154e9  lea     rcx, [rsp+0C8h+var_80]
0x1800154ee  call    ?Size@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(void)
0x1800154f3  cmp     eax, 1
0x1800154f6  setnbe  al
0x1800154f9  mov     rcx, [rsp+0C8h]; this
0x180015501  mov     [rsp+0C8h+var_98], rdi; char *
0x180015506  lea     rdx, aTooManyDeviceC; "Too many device containers found with n"...
0x18001550d  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x180015512  mov     [rsp+0C8h+var_A8], al; int
0x180015516  mov     r9d, 8007000Dh; char *
0x18001551c  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180015523  mov     edx, 13Eh; void *
0x180015528  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001552d  lea     rcx, [rsp+0C8h+var_80]
0x180015532  call    ?Size@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Size(void)
0x180015537  test    eax, eax
0x180015539  jnz     short loc_1800155B7
0x18001553b  mov     [rsp+0C8h+var_88], 0
0x180015544  lea     rdx, [rsp+0C8h+var_88]
0x180015549  mov     rcx, rdi
0x18001554c  call    cs:__imp_GetDeviceContainerIdByPerUserPrinterName
0x180015552  shr     eax, 1Fh
0x180015555  mov     rcx, [rsp+0C8h]; this
0x18001555d  mov     [rsp+0C8h+var_98], rdi; char *
0x180015562  lea     rdx, aNoDeviceContai; "No device containers found with name: %"...
0x180015569  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x18001556e  mov     [rsp+0C8h+var_A8], al; int
0x180015572  mov     r9d, 8007000Dh; char *
0x180015578  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x18001557f  mov     edx, 145h; void *
0x180015584  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015589  call    ?GetCurrentFileTime@@YA?AU_FILETIME@@XZ; GetCurrentFileTime(void)
0x18001558e  mov     rdx, rax; struct _FILETIME
0x180015591  mov     rcx, [rsp+0C8h+var_88]; unsigned __int16 *
0x180015596  call    ?_SetLastUserInteractionDate@@YAJPEBGU_FILETIME@@@Z; _SetLastUserInteractionDate(ushort const *,_FILETIME)
0x18001559b  mov     rcx, [rsp+0C8h]; this
0x1800155a3  test    eax, eax
0x1800155a5  js      loc_180015656
0x1800155ab  lea     rcx, [rsp+0C8h+var_88]
0x1800155b0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800155b5  jmp     short loc_180015613
0x1800155b7  xor     r8d, r8d
0x1800155ba  lea     rdx, [rsp+0C8h+var_58]
0x1800155bf  lea     rcx, [rsp+0C8h+var_80]
0x1800155c4  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::GetAt(uint)
0x1800155c9  nop
0x1800155ca  lea     rdx, [rsp+0C8h+var_78]
0x1800155cf  mov     rcx, rax
0x1800155d2  call    ?GetDefault@?$consume_Windows_UI_Notifications_IToastNotificationManagerStatics5@UIToastNotificationManagerStatics5@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerStatics5<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::GetDefault(void)
0x1800155d7  nop
0x1800155d8  lea     rcx, [rsp+0C8h+var_58]; this
0x1800155dd  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x1800155e2  call    ?GetCurrentFileTime@@YA?AU_FILETIME@@XZ; GetCurrentFileTime(void)
0x1800155e7  mov     rdx, rax
0x1800155ea  lea     rcx, [rsp+0C8h+var_78]; this
0x1800155ef  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800155f4  mov     rcx, rax; unsigned __int16 *
0x1800155f7  call    ?_SetLastUserInteractionDate@@YAJPEBGU_FILETIME@@@Z; _SetLastUserInteractionDate(ushort const *,_FILETIME)
0x1800155fc  mov     rcx, [rsp+0C8h]; this
0x180015604  test    eax, eax
0x180015606  js      short loc_18001566B
0x180015608  lea     rcx, [rsp+0C8h+var_78]
0x18001560d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180015612  nop
0x180015613  lea     rcx, [rsp+0C8h+var_80]; this
0x180015618  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18001561d  xor     eax, eax
0x18001561f  jmp     short loc_180015625
0x180015621  mov     eax, dword ptr [rsp+0C8h+var_88]
0x180015625  mov     rcx, [rsp+0C8h+var_10]
0x18001562d  xor     rcx, rsp; StackCookie
0x180015630  call    __security_check_cookie
0x180015635  add     rsp, 0C0h
0x18001563c  pop     rdi
0x18001563d  retn
0x18001563e  mov     r9d, 80070057h; char *
0x180015644  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x18001564b  mov     edx, 137h; void *
0x180015650  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015656  mov     r9d, eax; char *
0x180015659  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180015660  mov     edx, 146h; void *
0x180015665  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001566b  mov     r9d, eax; char *
0x18001566e  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180015675  mov     edx, 14Bh; void *
0x18001567a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
