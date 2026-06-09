# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetDefaultQueuePropertyBag(void *)

- ea: `0x18002250c`
- end: `0x1800229a5`
- name: `?_GetDefaultQueuePropertyBag@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUhstring@8@PEAX@Z`
- size: `1177`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bad4`

## callees

- `0x180002d40`
- `0x180007a58`
- `0x18000f8a8`
- `0x180010ef0`
- `0x1800181ac`
- `0x180018224`
- `0x18001a190`
- `0x18001a69c`
- `0x18001b27c`
- `0x18001b6b8`
- `0x18001cc68`
- `0x18001ce7c`
- `0x18001cfd4`
- `0x18001d058`
- `0x18001d0e4`
- `0x18002250c`
- `0x1800229ac`
- `0x180048010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002257b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002257b`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x180022766`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDataExW` at `0x180022766`

## string_xrefs

- `0x180022594`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x1800225c4`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18002277f`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetDefaultQueuePropertyBag(
        __int64 a1,
        __int64 a2,
        void *a3)
{
  double v3; // xmm0_8
  int ModernPrinterType; // esi
  int DriverInfo; // r14d
  void *v9; // rbx
  __int64 NumberValue; // rbx
  const unsigned __int16 *v11; // rdx
  __int64 StringValue; // rbx
  BYTE *pData; // rdx
  DWORD PrinterData; // eax
  __int64 v15; // rbx
  LPBYTE *v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rbx
  const char *nSize; // [rsp+28h] [rbp-B1h]
  const char *nSizea; // [rsp+28h] [rbp-B1h]
  const char *pcbNeeded; // [rsp+30h] [rbp-A9h]
  void *Block; // [rsp+40h] [rbp-99h] BYREF
  struct IUnknown v24; // [rsp+48h] [rbp-91h] BYREF
  struct IUnknown v25; // [rsp+50h] [rbp-89h] BYREF
  struct IUnknown v26; // [rsp+58h] [rbp-81h] BYREF
  struct IUnknown v27; // [rsp+60h] [rbp-79h] BYREF
  DWORD v28; // [rsp+68h] [rbp-71h] BYREF
  DWORD pType[3]; // [rsp+6Ch] [rbp-6Dh] BYREF
  _BYTE v30[32]; // [rsp+78h] [rbp-61h] BYREF
  _BYTE v31[32]; // [rsp+98h] [rbp-41h] BYREF
  LPBYTE v32[2]; // [rsp+B8h] [rbp-21h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-11h]
  unsigned __int16 *v34[4]; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  pType[0] = 0;
  v28 = 0;
  ModernPrinterType = 0;
  Block = 0;
  DriverInfo = PrintCore::GetDriverInfo(a3, &Block, (struct _DRIVER_INFO_8W **)a3);
  if ( DriverInfo >= 0 )
  {
    v9 = Block;
    ModernPrinterType = PrintCore::IppSelection::GetModernPrinterType(*((_QWORD *)Block + 15));
    free(v9);
  }
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x87,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)(unsigned int)DriverInfo,
    (int)"Failed to get printer type!",
    nSize);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x88,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
    (const char *)0x80070057LL,
    ModernPrinterType == 0,
    (bool)"Printer is not an IPP, UP, or VP printer!",
    pcbNeeded);
  winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetPrinterDeviceId(
    a1,
    (__int64)v34,
    a3);
  winrt::Windows::Data::Json::JsonObject::JsonObject(&v27);
  winrt::Windows::Data::Json::JsonObject::JsonObject(&v26);
  NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)v32, L"Type");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v27,
    v32,
    NumberValue);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&Block);
  v11 = (const unsigned __int16 *)v34;
  if ( v34[3] > (unsigned __int16 *)7 )
    v11 = v34[0];
  winrt::param::hstring::hstring((winrt::param::hstring *)v32, v11);
  StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&Block);
  winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"Value");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v27,
    v30,
    StringValue);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&Block);
  if ( v27.lpVtbl )
  {
    Block = 0;
    (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, void **))v27.lpVtbl->QueryInterface)(
      v27.lpVtbl,
      winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
      &Block);
    v24.lpVtbl = (struct IUnknownVtbl *)Block;
  }
  else
  {
    v24.lpVtbl = 0;
  }
  winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"DeviceId");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v26,
    v30,
    &v24);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v24);
  if ( (unsigned int)(ModernPrinterType - 1) <= 1 )
  {
    *(_OWORD *)v32 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v32[0]) = 0;
    std::wstring::resize(v32, 260);
    pData = (BYTE *)v32;
    if ( si128.m128i_i64[1] > 7uLL )
      pData = v32[0];
    PrinterData = GetPrinterDataExW(a3, L"PnPData", L"PSAHardwareId", pType, pData, 2 * si128.m128i_i32[0], &v28);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)PrinterData,
      (unsigned int)"GetPrinterDataEx for PSA Hardware Id failed!",
      nSizea);
    winrt::Windows::Data::Json::JsonObject::JsonObject(&v24);
    v15 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(0.0);
    winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"Type");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v24,
      v30,
      v15);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&Block);
    v16 = v32;
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = (LPBYTE *)v32[0];
    winrt::param::hstring::hstring((winrt::param::hstring *)v30, (const unsigned __int16 *const)v16);
    v17 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&Block);
    winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"Value");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v24,
      v31,
      v17);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&Block);
    Block = 0;
    if ( v24.lpVtbl )
      (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, void **))v24.lpVtbl->QueryInterface)(
        v24.lpVtbl,
        winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
        &Block);
    winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"PSAHardwareId");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v26,
      v31,
      &Block);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&Block);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v24);
    v3 = std::wstring::_Tidy_deallocate(v32);
  }
  winrt::Windows::Data::Json::JsonObject::JsonObject(&v25);
  v18 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"Version");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v25,
    v31,
    v18);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&Block);
  Block = 0;
  if ( v26.lpVtbl )
    (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, void **))v26.lpVtbl->QueryInterface)(
      v26.lpVtbl,
      winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
      &Block);
  winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"QueuePropertyBag");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v25,
    v31,
    &Block);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&Block);
  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(&v25, a2);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v25);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v26);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v27);
  std::wstring::_Tidy_deallocate(v34);
  return a2;
}

```

## disassembly

```asm
0x18002250c  push    rbp
0x18002250e  push    rbx
0x18002250f  push    rsi
0x180022510  push    rdi
0x180022511  push    r12
0x180022513  push    r14
0x180022515  push    r15
0x180022517  lea     rbp, [rsp-27h]
0x18002251c  sub     rsp, 100h
0x180022523  mov     rax, cs:__security_cookie
0x18002252a  xor     rax, rsp
0x18002252d  mov     [rbp+57h+var_38], rax
0x180022531  mov     r15, r8
0x180022534  mov     rdi, rdx
0x180022537  mov     r12, rcx
0x18002253a  mov     [rsp+130h+Block], rdx
0x18002253f  mov     [rbp+57h+pType], 0
0x180022546  mov     [rbp+57h+var_C8], 0
0x18002254d  xor     esi, esi
0x18002254f  mov     [rsp+130h+Block], rsi
0x180022554  lea     rdx, [rsp+130h+Block]; void *
0x180022559  mov     rcx, r8; hPrinter
0x18002255c  call    ?GetDriverInfo@PrintCore@@YAJPEAXPEAPEAU_DRIVER_INFO_8W@@@Z; PrintCore::GetDriverInfo(void *,_DRIVER_INFO_8W * *)
0x180022561  mov     r14d, eax
0x180022564  test    eax, eax
0x180022566  js      short loc_180022581
0x180022568  mov     rbx, [rsp+130h+Block]
0x18002256d  mov     rcx, [rbx+78h]
0x180022571  call    ?GetModernPrinterType@IppSelection@PrintCore@@SA?AW4ModernPrinterType@2@PEBG@Z; PrintCore::IppSelection::GetModernPrinterType(ushort const *)
0x180022576  mov     esi, eax
0x180022578  mov     rcx, rbx; Block
0x18002257b  call    cs:__imp_free
0x180022581  mov     rcx, [rbp+5Fh]; this
0x180022585  lea     rax, aFailedToGetPri; "Failed to get printer type!"
0x18002258c  mov     [rsp+130h+pData], rax; int
0x180022591  mov     r9d, r14d; char *
0x180022594  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x18002259b  mov     edx, 87h; void *
0x1800225a0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800225a5  test    esi, esi
0x1800225a7  setz    al
0x1800225aa  mov     rcx, [rbp+5Fh]; this
0x1800225ae  lea     rdx, aPrinterIsNotAn; "Printer is not an IPP, UP, or VP printe"...
0x1800225b5  mov     qword ptr [rsp+130h+nSize], rdx; bool
0x1800225ba  mov     byte ptr [rsp+130h+pData], al; char
0x1800225be  mov     r9d, 80070057h; char *
0x1800225c4  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x1800225cb  mov     edx, 88h; void *
0x1800225d0  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800225d5  mov     r8, r15
0x1800225d8  lea     rdx, [rbp+57h+var_58]
0x1800225dc  mov     rcx, r12
0x1800225df  call    ?_GetPrinterDeviceId@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_GetPrinterDeviceId(void *)
0x1800225e4  nop
0x1800225e5  lea     rcx, [rbp+57h+var_D0]; this
0x1800225e9  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800225ee  nop
0x1800225ef  lea     rcx, [rsp+130h+var_D8]; this
0x1800225f4  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800225f9  nop
0x1800225fa  movsd   xmm1, cs:__real@4028000000000000
0x180022602  lea     rcx, [rsp+130h+Block]
0x180022607  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x18002260c  mov     rbx, rax
0x18002260f  lea     rdx, aType_0; "Type"
0x180022616  lea     rcx, [rbp+57h+var_78]; this
0x18002261a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002261f  mov     r8, rbx
0x180022622  lea     rdx, [rbp+57h+var_78]
0x180022626  lea     rcx, [rbp+57h+var_D0]
0x18002262a  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18002262f  nop
0x180022630  lea     rcx, [rsp+130h+Block]; this
0x180022635  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18002263a  lea     rdx, [rbp+57h+var_58]
0x18002263e  cmp     [rbp+57h+var_40], 7
0x180022643  cmova   rdx, [rbp+57h+var_58]; unsigned __int16 *
0x180022648  lea     rcx, [rbp+57h+var_78]; this
0x18002264c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180022651  lea     rdx, [rbp+57h+var_78]
0x180022655  lea     rcx, [rsp+130h+Block]; struct winrt::param::hstring *
0x18002265a  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18002265f  mov     rbx, rax
0x180022662  lea     rdx, aValue; "Value"
0x180022669  lea     rcx, [rbp+57h+var_B8]; this
0x18002266d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180022672  mov     r8, rbx
0x180022675  lea     rdx, [rbp+57h+var_B8]
0x180022679  lea     rcx, [rbp+57h+var_D0]
0x18002267d  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180022682  nop
0x180022683  lea     rcx, [rsp+130h+Block]; this
0x180022688  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18002268d  mov     rcx, [rbp+57h+var_D0]
0x180022691  lea     r14, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180022698  test    rcx, rcx
0x18002269b  jnz     short loc_1800226A4
0x18002269d  mov     [rsp+130h+var_E8], rcx
0x1800226a2  jmp     short loc_1800226CA
0x1800226a4  mov     [rsp+130h+Block], 0
0x1800226ad  mov     rax, [rcx]
0x1800226b0  lea     r8, [rsp+130h+Block]
0x1800226b5  mov     rdx, r14
0x1800226b8  mov     rax, [rax]
0x1800226bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226c0  mov     rax, [rsp+130h+Block]
0x1800226c5  mov     [rsp+130h+var_E8], rax
0x1800226ca  lea     rdx, aDeviceid; "DeviceId"
0x1800226d1  lea     rcx, [rbp+57h+var_B8]; this
0x1800226d5  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800226da  lea     r8, [rsp+130h+var_E8]
0x1800226df  lea     rdx, [rbp+57h+var_B8]
0x1800226e3  lea     rcx, [rsp+130h+var_D8]
0x1800226e8  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800226ed  nop
0x1800226ee  lea     rcx, [rsp+130h+var_E8]; this
0x1800226f3  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800226f8  lea     eax, [rsi-1]
0x1800226fb  cmp     eax, 1
0x1800226fe  ja      loc_1800228A3
0x180022704  xorps   xmm0, xmm0
0x180022707  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18002270b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180022713  movdqu  [rbp+57h+var_68], xmm1
0x180022718  xor     eax, eax
0x18002271a  mov     word ptr [rbp+57h+var_78], ax
0x18002271e  mov     edx, 104h
0x180022723  lea     rcx, [rbp+57h+var_78]
0x180022727  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002272c  mov     eax, dword ptr [rbp+57h+var_68]
0x18002272f  lea     rdx, [rbp+57h+var_78]
0x180022733  cmp     qword ptr [rbp+57h+var_68+8], 7
0x180022738  cmova   rdx, [rbp+57h+var_78]
0x18002273d  add     eax, eax
0x18002273f  lea     rcx, [rbp+57h+var_C8]
0x180022743  mov     [rsp+130h+pcbNeeded], rcx; pcbNeeded
0x180022748  mov     [rsp+130h+nSize], eax; char *
0x18002274c  mov     [rsp+130h+pData], rdx; pData
0x180022751  lea     r9, [rbp+57h+pType]; pType
0x180022755  lea     r8, aPsahardwareid; "PSAHardwareId"
0x18002275c  lea     rdx, aPnpdata; "PnPData"
0x180022763  mov     rcx, r15; hPrinter
0x180022766  call    cs:__imp_GetPrinterDataExW
0x18002276c  mov     r9d, eax; char *
0x18002276f  mov     rcx, [rbp+5Fh]; this
0x180022773  lea     rax, aGetprinterdata_1; "GetPrinterDataEx for PSA Hardware Id fa"...
0x18002277a  mov     [rsp+130h+pData], rax; unsigned int
0x18002277f  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022786  mov     edx, 99h; void *
0x18002278b  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180022790  lea     rcx, [rsp+130h+var_E8]; this
0x180022795  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18002279a  nop
0x18002279b  movsd   xmm1, cs:__real@4028000000000000
0x1800227a3  lea     rcx, [rsp+130h+Block]
0x1800227a8  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x1800227ad  mov     rbx, rax
0x1800227b0  lea     rdx, aType_0; "Type"
0x1800227b7  lea     rcx, [rbp+57h+var_B8]; this
0x1800227bb  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800227c0  mov     r8, rbx
0x1800227c3  lea     rdx, [rbp+57h+var_B8]
0x1800227c7  lea     rcx, [rsp+130h+var_E8]
0x1800227cc  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800227d1  nop
0x1800227d2  lea     rcx, [rsp+130h+Block]; this
0x1800227d7  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800227dc  lea     rdx, [rbp+57h+var_78]
0x1800227e0  cmp     qword ptr [rbp+57h+var_68+8], 7
0x1800227e5  cmova   rdx, [rbp+57h+var_78]; unsigned __int16 *
0x1800227ea  lea     rcx, [rbp+57h+var_B8]; this
0x1800227ee  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800227f3  lea     rdx, [rbp+57h+var_B8]
0x1800227f7  lea     rcx, [rsp+130h+Block]; struct winrt::param::hstring *
0x1800227fc  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180022801  mov     rbx, rax
0x180022804  lea     rdx, aValue; "Value"
0x18002280b  lea     rcx, [rbp+57h+var_98]; this
0x18002280f  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180022814  mov     r8, rbx
0x180022817  lea     rdx, [rbp+57h+var_98]
0x18002281b  lea     rcx, [rsp+130h+var_E8]
0x180022820  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180022825  nop
0x180022826  lea     rcx, [rsp+130h+Block]; this
0x18002282b  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180022830  mov     rcx, [rsp+130h+var_E8]
0x180022835  mov     [rsp+130h+Block], 0
0x18002283e  test    rcx, rcx
0x180022841  jz      short loc_180022860
0x180022843  mov     rax, [rcx]
0x180022846  lea     r8, [rsp+130h+Block]
0x18002284b  mov     rdx, r14
0x18002284e  mov     rax, [rax]
0x180022851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022856  mov     rax, [rsp+130h+Block]
0x18002285b  mov     [rsp+130h+Block], rax
0x180022860  lea     rdx, aPsahardwareid; "PSAHardwareId"
0x180022867  lea     rcx, [rbp+57h+var_98]; this
0x18002286b  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180022870  lea     r8, [rsp+130h+Block]
0x180022875  lea     rdx, [rbp+57h+var_98]
0x180022879  lea     rcx, [rsp+130h+var_D8]
0x18002287e  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180022883  nop
0x180022884  lea     rcx, [rsp+130h+Block]; this
0x180022889  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18002288e  nop
0x18002288f  lea     rcx, [rsp+130h+var_E8]; this
0x180022894  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180022899  nop
0x18002289a  lea     rcx, [rbp+57h+var_78]
0x18002289e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800228a3  lea     rcx, [rsp+130h+var_E0]; this
0x1800228a8  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800228ad  nop
0x1800228ae  movsd   xmm1, cs:__real@3ff0000000000000
0x1800228b6  lea     rcx, [rsp+130h+Block]
0x1800228bb  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x1800228c0  mov     rbx, rax
0x1800228c3  lea     rdx, aVersion; "Version"
0x1800228ca  lea     rcx, [rbp+57h+var_98]; this
0x1800228ce  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800228d3  mov     r8, rbx
0x1800228d6  lea     rdx, [rbp+57h+var_98]
0x1800228da  lea     rcx, [rsp+130h+var_E0]
0x1800228df  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800228e4  nop
0x1800228e5  lea     rcx, [rsp+130h+Block]; this
0x1800228ea  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800228ef  mov     rcx, [rsp+130h+var_D8]
0x1800228f4  mov     [rsp+130h+Block], 0
0x1800228fd  test    rcx, rcx
0x180022900  jz      short loc_18002291F
0x180022902  mov     rax, [rcx]
0x180022905  lea     r8, [rsp+130h+Block]
0x18002290a  mov     rdx, r14
0x18002290d  mov     rax, [rax]
0x180022910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022915  mov     rax, [rsp+130h+Block]
0x18002291a  mov     [rsp+130h+Block], rax
0x18002291f  lea     rdx, aQueuepropertyb; "QueuePropertyBag"
0x180022926  lea     rcx, [rbp+57h+var_98]; this
0x18002292a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002292f  lea     r8, [rsp+130h+Block]
0x180022934  lea     rdx, [rbp+57h+var_98]
0x180022938  lea     rcx, [rsp+130h+var_E0]
0x18002293d  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180022942  nop
0x180022943  lea     rcx, [rsp+130h+Block]; this
0x180022948  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18002294d  mov     rdx, rdi
0x180022950  lea     rcx, [rsp+130h+var_E0]
0x180022955  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x18002295a  nop
0x18002295b  lea     rcx, [rsp+130h+var_E0]; this
0x180022960  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180022965  nop
0x180022966  lea     rcx, [rsp+130h+var_D8]; this
0x18002296b  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180022970  nop
0x180022971  lea     rcx, [rbp+57h+var_D0]; this
0x180022975  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18002297a  nop
0x18002297b  lea     rcx, [rbp+57h+var_58]
0x18002297f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022984  mov     rax, rdi
0x180022987  mov     rcx, [rbp+57h+var_38]
0x18002298b  xor     rcx, rsp; StackCookie
0x18002298e  call    __security_check_cookie
0x180022993  add     rsp, 100h
0x18002299a  pop     r15
0x18002299c  pop     r14
0x18002299e  pop     r12
0x1800229a0  pop     rdi
0x1800229a1  pop     rsi
0x1800229a2  pop     rbx
0x1800229a3  pop     rbp
0x1800229a4  retn
```
