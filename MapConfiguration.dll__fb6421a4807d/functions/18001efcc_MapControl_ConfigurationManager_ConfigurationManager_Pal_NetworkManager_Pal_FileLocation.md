# MapControl::ConfigurationManager::ConfigurationManager(Pal::NetworkManager &,Pal::FileLocation)

- ea: `0x18001efcc`
- end: `0x18001f44a`
- name: `??0ConfigurationManager@MapControl@@QEAA@AEAVNetworkManager@Pal@@W4FileLocation@3@@Z`
- size: `1150`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, service_task`

## callers

- `0x18001d1a0`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000ba50`
- `0x18000c354`
- `0x18000c850`
- `0x18000cab8`
- `0x18000cb0c`
- `0x18000fcd8`
- `0x180010f34`
- `0x1800124bc`
- `0x180013da8`
- `0x1800153b4`
- `0x180015858`
- `0x180017ad8`
- `0x18001b15c`
- `0x18001d324`
- `0x18001d390`
- `0x18001e6a4`
- `0x18001e94c`
- `0x18001eafc`
- `0x18001ec28`
- `0x18001ee30`
- `0x18001efcc`
- `0x18001f668`
- `0x1800205a0`
- `0x1800206c0`
- `0x180020bdc`
- `0x180020ec0`
- `0x18002149c`
- `0x180021ccc`
- `0x180022f60`
- `0x18002305c`
- `0x180023a4c`
- `0x180023a88`
- `0x180029b68`
- `0x180029c84`
- `0x180029dc4`
- `0x180034324`
- `0x180034630`
- `0x18003662c`
- `0x1800367e8`
- `0x180036850`
- `0x180038380`

## import_xrefs

- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18001f32d`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18001f32d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001f443`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001f443`

## pseudocode

```c
__int64 __fastcall MapControl::ConfigurationManager::ConfigurationManager(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 SanitizedLanguage; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 Configuration; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  std::_Ref_count_base *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rax
  char v22[8]; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+28h] [rbp-D8h]
  __int128 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  _BYTE v27[48]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[256]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v29[4]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v30[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v31; // [rsp+1C0h] [rbp+C0h] BYREF
  std::_Ref_count_base *v32; // [rsp+1C8h] [rbp+C8h]
  _BYTE v33[32]; // [rsp+1E0h] [rbp+E0h] BYREF

  v26 = a1;
  anonymous_namespace_::chinaRegionOverrides();
  anonymous_namespace_::chinaOsVersionOverrides(a1 + 16);
  anonymous_namespace_::embargoedRegionOverrides(a1 + 32);
  Pal::Mutex::Mutex((Pal::Mutex *)(a1 + 48));
  Pal::Timer::Timer((Pal::Timer *)(a1 + 88));
  *(_DWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  std::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>(a1 + 120);
  std::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>(a1 + 144);
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_DWORD *)(a1 + 184) = 0;
  Pal::Mutex::Mutex((Pal::Mutex *)(a1 + 192));
  std::wstring::wstring(a1 + 232);
  *(_QWORD *)(a1 + 264) = 0;
  Json::Value::Value(a1 + 272, 0);
  *(_QWORD *)(a1 + 312) = a2;
  Core::PresentSharedPtr<Utility::PrioritizedTaskQueue>::make_shared<>(a1 + 320);
  std::wstring::wstring(a1 + 336);
  std::wstring::wstring(a1 + 368);
  *(_DWORD *)(a1 + 400) = a3;
  *(_DWORD *)(a1 + 404) = Pal::DeviceTypeClassifierImplWindows::calculateDeviceType();
  *(_DWORD *)(a1 + 408) = 0;
  std::wstring::wstring(a1 + 416);
  *(_DWORD *)(a1 + 448) = 0;
  Pal::UntypedAsyncOperationCancelList::UntypedAsyncOperationCancelList((Pal::UntypedAsyncOperationCancelList *)(a1 + 456));
  *(_WORD *)(a1 + 561) = 0;
  Pal::CancellationToken::CancellationToken((Pal::CancellationToken *)(a1 + 563));
  Pal::CancellationToken::CancellationToken((Pal::CancellationToken *)(a1 + 564));
  LODWORD(v29[0]) = 255;
  if ( MapControl::ConfigurationLocalSettings::queryDeviceTypeOverride((enum Pal::DeviceType *)v29) )
    *(_DWORD *)(a1 + 404) = v29[0];
  v29[0] = operator new(8u);
  v29[0] = Pal::TaskQueue::TaskQueue(v29[0], 0);
  std::unique_ptr<Pal::TaskQueue>::operator=<std::default_delete<Pal::TaskQueue>,0>(a1 + 112, v29);
  std::unique_ptr<Pal::TaskQueue>::~unique_ptr<Pal::TaskQueue>(v29);
  MapControl::LegacyConfigurationLocalSettings::queryOSVariant((enum Pal::OSVariant *)(a1 + 408));
  Json::CharReaderBuilder::CharReaderBuilder((Json::CharReaderBuilder *)v27);
  v29[0] = v22;
  LOBYTE(v23) = 5;
  v23 &= ~0x100u;
  v24 = 0;
  v25 = 0;
  v22[0] = 1;
  v6 = std::wstring::wstring(v30, L"strictRoot");
  v7 = Json::CharReaderBuilder::operator[](v27, v6);
  Json::Value::operator=(v7, v22);
  v31 = v22;
  LOBYTE(v23) = 5;
  v23 &= ~0x100u;
  v24 = 0;
  v25 = 0;
  v22[0] = 1;
  v8 = std::wstring::wstring(v30, L"rejectDupKeys");
  v9 = Json::CharReaderBuilder::operator[](v27, v8);
  Json::Value::operator=(v9, v22);
  if ( !(unsigned __int8)Json::parseFromString(
                           v27,
                           MapControl::ConfigurationManager::sLanguageMappingDefaults,
                           a1 + 272) )
  {
    _o_terminate();
    JUMPOUT(0x18001F44ALL);
  }
  std::wstring::wstring(v33);
  Pal::UserLanguageSettingsImplWindows::getLanguageFallbackList(v30);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
    v28,
    v30);
  std::wstring::_Tidy_deallocate(v30);
  while ( 1 )
  {
    v12 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v28, v33, 59);
    if ( !(unsigned __int8)std::ios_base::operator bool(v12 + *(int *)(*(_QWORD *)v12 + 4LL)) )
      break;
    SanitizedLanguage = MapControl::ConfigurationManager::getSanitizedLanguage(a1, v29, v33);
    v11 = std::operator+<unsigned short>(&v31, SanitizedLanguage);
    std::wstring::append(a1 + 416, v11);
    std::wstring::_Tidy_deallocate(&v31);
    std::wstring::_Tidy_deallocate(v29);
  }
  Configuration = MapControl::ConfigurationManager::getConfiguration((MapControl::ConfigurationManager *)a1);
  v14 = (__int64 *)std::make_shared<MapControl::MapConfiguration,Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>(
                     &v31,
                     Configuration);
  v15 = *v14;
  v16 = v14[1];
  *v14 = 0;
  v14[1] = 0;
  *(_QWORD *)(a1 + 168) = v15;
  v17 = *(std::_Ref_count_base **)(a1 + 176);
  *(_QWORD *)(a1 + 176) = v16;
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v29);
  MapControl::MapConfiguration::getValueString(*(_QWORD *)(a1 + 168), v18, a1 + 232);
  MapControl::MapConfiguration::getValuePalTimeInterval(*(_QWORD *)(a1 + 168), v19, a1 + 264);
  v20 = Pal::CppEvent<>::attach<MapControl::ConfigurationManager,&private: void MapControl::ConfigurationManager::onDefaultConfigurationChanged(void)>(
          *(_QWORD *)(a1 + 168) + 56LL,
          v29,
          a1);
  Pal::EventId::operator=(a1 + 184, v20);
  MapControl::ConfigurationManager::readOverridesCacheSync((MapControl::ConfigurationManager *)a1);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v28);
  std::wstring::_Tidy_deallocate(v33);
  Json::CharReaderBuilder::~CharReaderBuilder((Json::CharReaderBuilder *)v27);
  return a1;
}

```

## disassembly

```asm
0x18001efcc  push    rbp
0x18001efce  push    rbx
0x18001efcf  push    rsi
0x18001efd0  push    rdi
0x18001efd1  push    r12
0x18001efd3  push    r13
0x18001efd5  push    r14
0x18001efd7  push    r15
0x18001efd9  lea     rbp, [rsp-118h]
0x18001efe1  sub     rsp, 218h
0x18001efe8  mov     rax, cs:__security_cookie
0x18001efef  xor     rax, rsp
0x18001eff2  mov     [rbp+150h+var_50], rax
0x18001eff9  mov     edi, r8d
0x18001effc  mov     rbx, rdx
0x18001efff  mov     rsi, rcx
0x18001f002  mov     [rsp+250h+var_208], rcx
0x18001f007  xor     r15d, r15d
0x18001f00a  call    _anonymous_namespace___chinaRegionOverrides
0x18001f00f  nop
0x18001f010  lea     rcx, [rsi+10h]
0x18001f014  call    _anonymous_namespace___chinaOsVersionOverrides
0x18001f019  nop
0x18001f01a  lea     rcx, [rsi+20h]
0x18001f01e  call    _anonymous_namespace___embargoedRegionOverrides
0x18001f023  nop
0x18001f024  lea     rcx, [rsi+30h]; this
0x18001f028  call    ??0Mutex@Pal@@QEAA@XZ; Pal::Mutex::Mutex(void)
0x18001f02d  nop
0x18001f02e  lea     rcx, [rsi+58h]; this
0x18001f032  call    ??0Timer@Pal@@QEAA@XZ; Pal::Timer::Timer(void)
0x18001f037  nop
0x18001f038  mov     [rsi+68h], r15d
0x18001f03c  mov     [rsi+70h], r15
0x18001f040  lea     rcx, [rsi+78h]
0x18001f044  call    ??0?$vector@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@V?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@2@@std@@QEAA@XZ; std::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>(void)
0x18001f049  nop
0x18001f04a  lea     rcx, [rsi+90h]
0x18001f051  call    ??0?$vector@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@V?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@2@@std@@QEAA@XZ; std::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>(void)
0x18001f056  nop
0x18001f057  mov     [rsi+0A8h], r15
0x18001f05e  mov     [rsi+0B0h], r15
0x18001f065  lea     r14, [rsi+0B8h]
0x18001f06c  mov     [r14], r15d
0x18001f06f  lea     rcx, [rsi+0C0h]; this
0x18001f076  call    ??0Mutex@Pal@@QEAA@XZ; Pal::Mutex::Mutex(void)
0x18001f07b  nop
0x18001f07c  lea     r15, [rsi+0E8h]
0x18001f083  mov     rcx, r15
0x18001f086  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f08b  nop
0x18001f08c  lea     r12, [rsi+108h]
0x18001f093  mov     qword ptr [r12], 0
0x18001f09b  lea     rcx, [rsi+110h]
0x18001f0a2  xor     edx, edx
0x18001f0a4  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x18001f0a9  nop
0x18001f0aa  mov     [rsi+138h], rbx
0x18001f0b1  lea     rcx, [rsi+140h]
0x18001f0b8  call    ??$make_shared@$$V@?$PresentSharedPtr@VPrioritizedTaskQueue@Utility@@@Core@@SA?AV01@XZ; Core::PresentSharedPtr<Utility::PrioritizedTaskQueue>::make_shared<>(void)
0x18001f0bd  nop
0x18001f0be  lea     rcx, [rsi+150h]
0x18001f0c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f0ca  nop
0x18001f0cb  lea     rcx, [rsi+170h]
0x18001f0d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f0d7  nop
0x18001f0d8  mov     [rsi+190h], edi
0x18001f0de  call    ?calculateDeviceType@DeviceTypeClassifierImplWindows@Pal@@SA?AW4DeviceType@2@XZ; Pal::DeviceTypeClassifierImplWindows::calculateDeviceType(void)
0x18001f0e3  mov     [rsi+194h], eax
0x18001f0e9  lea     rdi, [rsi+198h]
0x18001f0f0  mov     dword ptr [rdi], 0
0x18001f0f6  lea     rbx, [rsi+1A0h]
0x18001f0fd  mov     rcx, rbx
0x18001f100  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f105  nop
0x18001f106  mov     dword ptr [rsi+1C0h], 0
0x18001f110  lea     rcx, [rsi+1C8h]; this
0x18001f117  call    ??0UntypedAsyncOperationCancelList@Pal@@QEAA@XZ; Pal::UntypedAsyncOperationCancelList::UntypedAsyncOperationCancelList(void)
0x18001f11c  nop
0x18001f11d  mov     word ptr [rsi+231h], 0
0x18001f126  lea     rcx, [rsi+233h]; this
0x18001f12d  call    ??0CancellationToken@Pal@@QEAA@XZ; Pal::CancellationToken::CancellationToken(void)
0x18001f132  lea     rcx, [rsi+234h]; this
0x18001f139  call    ??0CancellationToken@Pal@@QEAA@XZ; Pal::CancellationToken::CancellationToken(void)
0x18001f13e  mov     dword ptr [rbp+150h+var_D0], 0FFh
0x18001f148  lea     rcx, [rbp+150h+var_D0]; enum Pal::DeviceType *
0x18001f14f  call    ?queryDeviceTypeOverride@ConfigurationLocalSettings@MapControl@@SA_NPEAW4DeviceType@Pal@@@Z; MapControl::ConfigurationLocalSettings::queryDeviceTypeOverride(Pal::DeviceType *)
0x18001f154  test    al, al
0x18001f156  jz      short loc_18001F164
0x18001f158  mov     eax, dword ptr [rbp+150h+var_D0]
0x18001f15e  mov     [rsi+194h], eax
0x18001f164  mov     ecx, 8; Size
0x18001f169  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f16e  mov     [rbp+150h+var_D0], rax
0x18001f175  xor     edx, edx
0x18001f177  mov     rcx, rax
0x18001f17a  call    ??0TaskQueue@Pal@@QEAA@W4TaskQueueType@1@@Z; Pal::TaskQueue::TaskQueue(Pal::TaskQueueType)
0x18001f17f  nop
0x18001f180  mov     [rbp+150h+var_D0], rax
0x18001f187  lea     rdx, [rbp+150h+var_D0]
0x18001f18e  lea     rcx, [rsi+70h]
0x18001f192  call    ??$?4U?$default_delete@VTaskQueue@Pal@@@std@@$0A@@?$unique_ptr@VTaskQueue@Pal@@U?$default_delete@VTaskQueue@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::TaskQueue>::operator=<std::default_delete<Pal::TaskQueue>,0>(std::unique_ptr<Pal::TaskQueue> &&)
0x18001f197  lea     rcx, [rbp+150h+var_D0]
0x18001f19e  call    ??1?$unique_ptr@VTaskQueue@Pal@@U?$default_delete@VTaskQueue@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::TaskQueue>::~unique_ptr<Pal::TaskQueue>(void)
0x18001f1a3  mov     rcx, rdi; enum Pal::OSVariant *
0x18001f1a6  call    ?queryOSVariant@LegacyConfigurationLocalSettings@MapControl@@SA_NPEAW4OSVariant@Pal@@@Z; MapControl::LegacyConfigurationLocalSettings::queryOSVariant(Pal::OSVariant *)
0x18001f1ab  lea     rcx, [rsp+250h+var_200]; this
0x18001f1b0  call    ??0CharReaderBuilder@Json@@QEAA@XZ; Json::CharReaderBuilder::CharReaderBuilder(void)
0x18001f1b5  nop
0x18001f1b6  lea     rax, [rsp+250h+var_230]
0x18001f1bb  mov     [rbp+150h+var_D0], rax
0x18001f1c2  mov     byte ptr [rsp+250h+var_228], 5
0x18001f1c7  mov     edi, 0FFFFFEFFh
0x18001f1cc  and     [rsp+250h+var_228], edi
0x18001f1d0  xorps   xmm0, xmm0
0x18001f1d3  movdqu  [rsp+250h+var_220], xmm0
0x18001f1d9  xor     r13d, r13d
0x18001f1dc  mov     [rsp+250h+var_210], r13
0x18001f1e1  mov     [rsp+250h+var_230], 1
0x18001f1e6  lea     rdx, aStrictroot; "strictRoot"
0x18001f1ed  lea     rcx, [rbp+150h+var_B0]
0x18001f1f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f1f9  mov     rdx, rax
0x18001f1fc  lea     rcx, [rsp+250h+var_200]
0x18001f201  call    ??ACharReaderBuilder@Json@@QEAAAEAVValue@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::CharReaderBuilder::operator[](std::wstring)
0x18001f206  nop
0x18001f207  lea     rdx, [rsp+250h+var_230]
0x18001f20c  mov     rcx, rax
0x18001f20f  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x18001f214  lea     rax, [rsp+250h+var_230]
0x18001f219  mov     [rbp+150h+var_90], rax
0x18001f220  mov     byte ptr [rsp+250h+var_228], 5
0x18001f225  and     [rsp+250h+var_228], edi
0x18001f229  xorps   xmm0, xmm0
0x18001f22c  movdqu  [rsp+250h+var_220], xmm0
0x18001f232  mov     [rsp+250h+var_210], r13
0x18001f237  mov     [rsp+250h+var_230], 1
0x18001f23c  lea     rdx, aRejectdupkeys; "rejectDupKeys"
0x18001f243  lea     rcx, [rbp+150h+var_B0]
0x18001f24a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f24f  mov     rdx, rax
0x18001f252  lea     rcx, [rsp+250h+var_200]
0x18001f257  call    ??ACharReaderBuilder@Json@@QEAAAEAVValue@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::CharReaderBuilder::operator[](std::wstring)
0x18001f25c  nop
0x18001f25d  lea     rdx, [rsp+250h+var_230]
0x18001f262  mov     rcx, rax
0x18001f265  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x18001f26a  lea     r8, [rsi+110h]
0x18001f271  lea     rdx, ?sLanguageMappingDefaults@ConfigurationManager@MapControl@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::ConfigurationManager::sLanguageMappingDefaults
0x18001f278  lea     rcx, [rsp+250h+var_200]
0x18001f27d  call    ?parseFromString@Json@@YA_NAEBVFactory@CharReader@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVValue@1@PEAV45@@Z; Json::parseFromString(Json::CharReader::Factory const &,std::wstring const &,Json::Value *,std::wstring *)
0x18001f282  test    al, al
0x18001f284  jz      loc_18001F443
0x18001f28a  lea     rcx, [rbp+150h+var_70]
0x18001f291  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f296  nop
0x18001f297  lea     rcx, [rbp+150h+var_B0]
0x18001f29e  call    ?getLanguageFallbackList@UserLanguageSettingsImplWindows@Pal@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Pal::UserLanguageSettingsImplWindows::getLanguageFallbackList(void)
0x18001f2a3  nop
0x18001f2a4  lea     rdx, [rbp+150h+var_B0]
0x18001f2ab  lea     rcx, [rbp+150h+var_1D0]
0x18001f2af  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::wstring const &,int)
0x18001f2b4  nop
0x18001f2b5  lea     rcx, [rbp+150h+var_B0]
0x18001f2bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f2c1  lea     edi, [r13+3Bh]
0x18001f2c5  jmp     short loc_18001F310
0x18001f2c7  lea     r8, [rbp+150h+var_70]
0x18001f2ce  lea     rdx, [rbp+150h+var_D0]
0x18001f2d5  call    ?getSanitizedLanguage@ConfigurationManager@MapControl@@AEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; MapControl::ConfigurationManager::getSanitizedLanguage(std::wstring const &)
0x18001f2da  nop
0x18001f2db  mov     rdx, rax
0x18001f2de  lea     rcx, [rbp+150h+var_90]
0x18001f2e5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x18001f2ea  nop
0x18001f2eb  mov     rdx, rax
0x18001f2ee  mov     rcx, rbx
0x18001f2f1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001f2f6  nop
0x18001f2f7  lea     rcx, [rbp+150h+var_90]
0x18001f2fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f303  nop
0x18001f304  lea     rcx, [rbp+150h+var_D0]
0x18001f30b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f310  mov     r8d, edi
0x18001f313  lea     rdx, [rbp+150h+var_70]
0x18001f31a  lea     rcx, [rbp+150h+var_1D0]
0x18001f31e  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x18001f323  mov     rcx, [rax]
0x18001f326  movsxd  rcx, dword ptr [rcx+4]
0x18001f32a  add     rcx, rax
0x18001f32d  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x18001f333  mov     rcx, rsi; this
0x18001f336  test    al, al
0x18001f338  jnz     short loc_18001F2C7
0x18001f33a  lea     r9, ?kDefaultLanguage@EndPoints@MapControl@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::EndPoints::kDefaultLanguage
0x18001f341  lea     r8, ?kDefaultRegion@EndPoints@MapControl@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::EndPoints::kDefaultRegion
0x18001f348  lea     rdx, [rbp+150h+var_D0]
0x18001f34f  call    ?getConfiguration@ConfigurationManager@MapControl@@QEAA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapControl::ConfigurationManager::getConfiguration(std::wstring const &,std::wstring const &)
0x18001f354  nop
0x18001f355  mov     rdx, rax
0x18001f358  lea     rcx, [rbp+150h+var_90]
0x18001f35f  call    ??$make_shared@VMapConfiguration@MapControl@@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@std@@YA?AV?$shared_ptr@VMapConfiguration@MapControl@@@0@$$QEAV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Z; std::make_shared<MapControl::MapConfiguration,Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>(Core::PresentSharedPtr<MapControl::LocaleMapConfiguration> &&)
0x18001f364  mov     rcx, [rax]
0x18001f367  mov     rdx, [rax+8]
0x18001f36b  mov     [rax], r13
0x18001f36e  mov     [rax+8], r13
0x18001f372  mov     [rsi+0A8h], rcx
0x18001f379  mov     rcx, [rsi+0B0h]; this
0x18001f380  mov     [rsi+0B0h], rdx
0x18001f387  test    rcx, rcx
0x18001f38a  jz      short loc_18001F391
0x18001f38c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f391  mov     rcx, [rbp+150h+var_88]; this
0x18001f398  test    rcx, rcx
0x18001f39b  jz      short loc_18001F3A3
0x18001f39d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f3a2  nop
0x18001f3a3  lea     rcx, [rbp+150h+var_D0]
0x18001f3aa  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18001f3af  mov     r8, r15
0x18001f3b2  mov     rcx, [rsi+0A8h]
0x18001f3b9  call    ?getValueString@MapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::MapConfiguration::getValueString(MapControl::ConfigurationKeys,std::wstring *)
0x18001f3be  mov     r8, r12
0x18001f3c1  mov     rcx, [rsi+0A8h]
0x18001f3c8  call    ?getValuePalTimeInterval@MapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAN@Z; MapControl::MapConfiguration::getValuePalTimeInterval(MapControl::ConfigurationKeys,double *)
0x18001f3cd  mov     rcx, [rsi+0A8h]
0x18001f3d4  add     rcx, 38h ; '8'
0x18001f3d8  mov     r8, rsi
0x18001f3db  lea     rdx, [rbp+150h+var_D0]
0x18001f3e2  call    ??$attach@VConfigurationManager@MapControl@@$1?onDefaultConfigurationChanged@12@AEAAXXZ@?$CppEvent@$$V@Pal@@QEAA?AVEventId@1@PEAVConfigurationManager@MapControl@@@Z; Pal::CppEvent<>::attach<MapControl::ConfigurationManager,&MapControl::ConfigurationManager::onDefaultConfigurationChanged(void)>(MapControl::ConfigurationManager *)
0x18001f3e7  mov     rdx, rax
0x18001f3ea  mov     rcx, r14
0x18001f3ed  call    ??4EventId@Pal@@QEAAAEAV01@$$QEAV01@@Z; Pal::EventId::operator=(Pal::EventId &&)
0x18001f3f2  mov     rcx, rsi; this
0x18001f3f5  call    ?readOverridesCacheSync@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::readOverridesCacheSync(void)
0x18001f3fa  nop
0x18001f3fb  lea     rcx, [rbp+150h+var_1D0]
0x18001f3ff  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18001f404  nop
0x18001f405  lea     rcx, [rbp+150h+var_70]
0x18001f40c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f411  nop
0x18001f412  lea     rcx, [rsp+250h+var_200]; this
0x18001f417  call    ??1CharReaderBuilder@Json@@UEAA@XZ; Json::CharReaderBuilder::~CharReaderBuilder(void)
0x18001f41c  nop
0x18001f41d  mov     rax, rsi
0x18001f420  mov     rcx, [rbp+150h+var_50]
0x18001f427  xor     rcx, rsp; StackCookie
0x18001f42a  call    __security_check_cookie
0x18001f42f  add     rsp, 218h
0x18001f436  pop     r15
0x18001f438  pop     r14
0x18001f43a  pop     r13
0x18001f43c  pop     r12
0x18001f43e  pop     rdi
0x18001f43f  pop     rsi
0x18001f440  pop     rbx
0x18001f441  pop     rbp
0x18001f442  retn
0x18001f443  call    cs:__imp__o_terminate
0x18001f449  nop
```
