# UpdateSoftwareInventoryTC2(char const *,bool,bool,char const *)

- ea: `0x180021990`
- end: `0x180022010`
- name: `?UpdateSoftwareInventoryTC2@@YAJPEBD_N10@Z`
- size: `1664`
- prototype: `__int64 __fastcall(const char *, bool, bool, const char *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000116c`
- `0x180001230`
- `0x180005890`
- `0x180006040`
- `0x180006938`
- `0x18000f0bc`
- `0x18000faf0`
- `0x18001084c`
- `0x180015cf0`
- `0x180016884`
- `0x18001c5f0`
- `0x18001d988`
- `0x18001e464`
- `0x18001e510`
- `0x18001e93c`
- `0x18001eab4`
- `0x18001f038`
- `0x18001f318`
- `0x180021530`
- `0x180021990`
- `0x1800295dc`
- `0x1800c2d74`
- `0x1800cdd98`
- `0x1800cdec0`
- `0x1800ceccc`
- `0x1800d066c`
- `0x1800d562c`
- `0x1800d570c`
- `0x1800d5ab4`
- `0x1800e16e8`
- `0x1800e4d80`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800219d4`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180021eb0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800219d4`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180021eb0`

## string_xrefs

- `0x180021a3a`: `UpdateSoftwareInventoryTC2`
- `0x180021b2a`: `UpdateSoftwareInventoryTC2`
- `0x180021c45`: `UpdateSoftwareInventoryTC2`
- `0x180021f50`: `AepicUpdateSoftwareInventory`
- `0x180021b1f`: `TelCacheProvider::Initialize failed [%#x]`
- `0x180021c38`: `TelCacheProvider::Initialize failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall UpdateSoftwareInventoryTC2(const char *a1, __int64 a2, char a3, const char *a4)
{
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v5; // rcx
  unsigned int v6; // ebx
  int v7; // eax
  Application *v8; // rax
  const unsigned __int16 *v9; // rdx
  int v10; // eax
  File *v11; // rax
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  unsigned __int16 v14; // r8
  int v15; // esi
  int v16; // r8d
  int v17; // r9d
  const char *v18; // rax
  const struct wil::FailureInfo *v20; // r9
  signed int LastError; // eax
  const char *v22; // rcx
  int v23; // [rsp+30h] [rbp-13A8h]
  int v24; // [rsp+A0h] [rbp-1338h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-1330h] BYREF
  unsigned __int64 v26; // [rsp+B0h] [rbp-1328h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+B8h] [rbp-1320h] BYREF
  void *v28; // [rsp+C0h] [rbp-1318h] BYREF
  __int128 v29; // [rsp+C8h] [rbp-1310h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-1300h]
  char *v31; // [rsp+E0h] [rbp-12F8h] BYREF
  const unsigned __int16 *Version; // [rsp+E8h] [rbp-12F0h] BYREF
  unsigned __int64 v33; // [rsp+F0h] [rbp-12E8h] BYREF
  const char *v34; // [rsp+F8h] [rbp-12E0h] BYREF
  const char *v35; // [rsp+100h] [rbp-12D8h] BYREF
  void **v36; // [rsp+108h] [rbp-12D0h] BYREF
  const char *v37; // [rsp+110h] [rbp-12C8h] BYREF
  _BYTE v38[40]; // [rsp+120h] [rbp-12B8h] BYREF
  __int128 v39; // [rsp+148h] [rbp-1290h]
  __int128 v40; // [rsp+158h] [rbp-1280h]
  __int128 v41; // [rsp+168h] [rbp-1270h]
  __int128 v42; // [rsp+178h] [rbp-1260h]
  __int128 v43; // [rsp+188h] [rbp-1250h]
  __int128 v44; // [rsp+198h] [rbp-1240h]
  __int128 v45; // [rsp+1A8h] [rbp-1230h]
  __int128 v46; // [rsp+1B8h] [rbp-1220h]
  __int64 v47; // [rsp+1C8h] [rbp-1210h]
  _OWORD v48[5]; // [rsp+1F0h] [rbp-11E8h] BYREF
  __int128 v49; // [rsp+240h] [rbp-1198h]
  __int128 v50; // [rsp+250h] [rbp-1188h]
  __int128 v51; // [rsp+260h] [rbp-1178h]
  __int128 v52; // [rsp+270h] [rbp-1168h]
  __int64 v53; // [rsp+280h] [rbp-1158h]
  __int64 v54; // [rsp+290h] [rbp-1148h] BYREF
  _BYTE v55[80]; // [rsp+298h] [rbp-1140h] BYREF
  __int64 v56; // [rsp+2E8h] [rbp-10F0h]
  __int16 v57; // [rsp+2F0h] [rbp-10E8h]
  __int64 v58; // [rsp+2F8h] [rbp-10E0h]
  __int128 v59; // [rsp+300h] [rbp-10D8h]
  __int64 v60; // [rsp+310h] [rbp-10C8h]
  int v61; // [rsp+318h] [rbp-10C0h]
  char v62; // [rsp+31Ch] [rbp-10BCh]
  _BYTE v63[32]; // [rsp+320h] [rbp-10B8h] BYREF
  _BYTE v64[32]; // [rsp+340h] [rbp-1098h] BYREF
  _BYTE v65[32]; // [rsp+360h] [rbp-1078h] BYREF
  _BYTE v66[32]; // [rsp+380h] [rbp-1058h] BYREF
  _BYTE v67[32]; // [rsp+3A0h] [rbp-1038h] BYREF
  _BYTE v68[4096]; // [rsp+3C0h] [rbp-1018h] BYREF

  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(v5, a1);
  v28 = 0;
  if ( Utility::IsAeInvAlreadyRunning(&v28) )
  {
    v6 = -2147024726;
  }
  else
  {
    try
    {
      Utility::InitializeWatchdogTimer();
      v24 = -2147221008;
      v7 = Common::AutoWinRTInitialize::Initialize(&v24);
      v6 = v7;
      if ( v7 >= 0 )
      {
        memset_0(v55, 0, 0x4Eu);
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v61 = 0;
        v62 = 0;
        v56 = 0;
        v54 = 0;
        v25 = (__int64)operator new(0x3F0u);
        v8 = Application::Application((Application *)v25);
        v9 = (const unsigned __int16 *)&Application::ApplicationCacheProviderName;
        if ( (unsigned __int64)qword_1801222A8 > 7 )
          v9 = (const unsigned __int16 *)Application::ApplicationCacheProviderName;
        v10 = TelCacheProvider::Initialize(&v54, v9, (__int64)v8, 0, 2, 5u, 0x1F4u);
        v6 = v10;
        if ( v10 >= 0 )
        {
          if ( a3 )
            TelCacheProvider::ClearData((TelCacheProvider *)&v54);
          memset_0((char *)v48 + 8, 0, 0x4Eu);
          LOWORD(v50) = 0;
          *((_QWORD *)&v50 + 1) = 0;
          v51 = 0;
          *(_QWORD *)&v52 = 0;
          DWORD2(v52) = 0;
          BYTE12(v52) = 0;
          *((_QWORD *)&v49 + 1) = 0;
          *(_QWORD *)&v48[0] = 0;
          v25 = (__int64)operator new(0x330u);
          v11 = File::File((File *)v25);
          v12 = (const unsigned __int16 *)&File::FileCacheProviderName;
          if ( (unsigned __int64)qword_180121AA8 > 7 )
            v12 = (const unsigned __int16 *)File::FileCacheProviderName;
          v13 = TelCacheProvider::Initialize(
                  v48,
                  v12,
                  ((unsigned __int64)v11 + 8) & -(__int64)(v11 != 0),
                  0,
                  2,
                  5u,
                  0x1F4u);
          v6 = v13;
          if ( v13 >= 0 )
          {
            std::wstring::wstring(v67, &pszFormat);
            std::wstring::wstring(v66, &pszFormat);
            std::wstring::wstring(v65, &pszFormat);
            std::wstring::wstring(v64, &pszFormat);
            std::wstring::wstring(v63, &pszFormat);
            ConfigSettings::ConfigSettings(
              (unsigned int)v68,
              0,
              (unsigned int)&v54,
              (unsigned int)v48,
              0,
              0,
              v23,
              (__int64)v63,
              (__int64)v64,
              (__int64)v65,
              (__int64)v66,
              (__int64)v67);
            std::wstring::_Tidy_deallocate(v63);
            std::wstring::_Tidy_deallocate(v64);
            std::wstring::_Tidy_deallocate(v65);
            std::wstring::_Tidy_deallocate(v66);
            std::wstring::_Tidy_deallocate(v67);
            v29 = 0;
            v30 = 0;
            TelCacheProvider::BatchBegin((TelCacheProvider *)&v54);
            v25 = (__int64)&StoreAppFinder::`vftable';
            StoreAppFinder::EnumeratePackages((__int64)v68, &v29, v14);
            TelCacheProvider::BatchEnd((TelCacheProvider *)&v54);
            SetLastInventoryScanTime((struct TelCacheProvider *)&v54);
            if ( (_QWORD)v29 )
            {
              std::_Destroy_range<std::allocator<Application>>(v29, *((_QWORD *)&v29 + 1));
              std::_Deallocate<16>(v29, 16 * ((v30 - (__int64)v29) >> 4));
              v29 = 0;
              v30 = 0;
            }
            ConfigSettings::~ConfigSettings((ConfigSettings *)v68);
            TelCacheProvider::~TelCacheProvider((TelCacheProvider *)v48);
            TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v54);
            Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v24);
          }
          else
          {
            AslLogCallPrintf(1, "UpdateSoftwareInventoryTC2", 127, "TelCacheProvider::Initialize failed [%#x]", v13);
            TelCacheProvider::~TelCacheProvider((TelCacheProvider *)v48);
            TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v54);
            Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v24);
          }
        }
        else
        {
          AslLogCallPrintf(1, "UpdateSoftwareInventoryTC2", 113, "TelCacheProvider::Initialize failed [%#x]", v10);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v54);
          Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v24);
        }
      }
      else
      {
        AslLogCallPrintf(1, "UpdateSoftwareInventoryTC2", 104, "AutoWinRTInitialize::Initialize failed [%#x]", v7);
        Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v24);
      }
    }
    catch ( wil::ResultException v38 )
    {
      memset_0(v68, 0, sizeof(v68));
      v48[0] = *(_OWORD *)&v38[24];
      v48[1] = v39;
      v48[2] = v40;
      v48[3] = v41;
      v48[4] = v42;
      v49 = v43;
      v50 = v44;
      v51 = v45;
      v52 = v46;
      v53 = v47;
      wil::GetFailureLogString((wil *)v68, (unsigned __int16 *)0x800, (unsigned __int64)v48, v20);
      AslLogCallPrintf(1, "UpdateSoftwareInventoryTC2", 168, "%ws", v68);
      v24 = DWORD2(v48[0]);
      wil::ResultException::~ResultException((wil::ResultException *)v38);
      v6 = v24;
    }
    catch ( std::exception v36 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v24 = LastError;
      v22 = "Unknown exception";
      if ( v37 )
        v22 = v37;
      AslLogCallPrintf(1, "UpdateSoftwareInventoryTC2", 174, "Exception: %s", v22);
      v36 = &std::exception::`vftable';
      o___std_exception_destroy_0(&v37);
      v6 = v24;
    }
    catch ( ... )
    {
      v24 = -2147024322;
      AslLogCallPrintf(1, "UpdateSoftwareInventoryTC2", 179, "Exception: [%#x]", -2147024322);
      v6 = v24;
    }
  }
  Utility::UninitializeWatchdogTimer();
  v26 = 0;
  QueryUnbiasedInterruptTime(&v26);
  v15 = DWORD2(xmmword_1801216E0);
  if ( **((_DWORD **)&xmmword_1801216E0 + 1) > 5u
    && (unsigned __int8)tlgKeywordOn(*((_QWORD *)&xmmword_1801216E0 + 1), 0x400000000000LL) )
  {
    v31 = &byte_1801216F8;
    Version = InventoryCoreGetVersion();
    v24 = v6;
    v33 = (v26 - UnbiasedTime) / 0x2710;
    v18 = "fullSync";
    if ( !a3 )
      v18 = "incremental";
    v34 = v18;
    v35 = "AepicUpdateSoftwareInventory";
    v25 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v15,
      (unsigned int)byte_18010DDAB,
      v16,
      v17,
      (__int64)&v25,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v24,
      (__int64)&Version,
      (__int64)&v31);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v28);
  return v6;
}

```

## disassembly

```asm
0x180021990  mov     [rsp+arg_8], rbx
0x180021995  mov     [rsp+arg_18], rsi
0x18002199a  mov     [rsp+arg_10], r8b
0x18002199f  push    rdi
0x1800219a0  mov     eax, 13D0h
0x1800219a5  call    _alloca_probe
0x1800219aa  sub     rsp, rax
0x1800219ad  mov     rax, cs:__security_cookie
0x1800219b4  xor     rax, rsp
0x1800219b7  mov     [rsp+13D8h+var_18], rax
0x1800219bf  mov     rbx, rcx
0x1800219c2  xor     edi, edi
0x1800219c4  mov     [rsp+13D8h+UnbiasedTime], rdi
0x1800219cc  lea     rcx, [rsp+13D8h+UnbiasedTime]; UnbiasedTime
0x1800219d4  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800219da  mov     rdx, rbx; char *
0x1800219dd  call    ?ExtendCv@TelemetryProvider@Telemetry@Shared@Compat@Windows@@QEAAXPEBD@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(char const *)
0x1800219e2  nop
0x1800219e3  mov     [rsp+13D8h+var_1318], rdi
0x1800219eb  lea     rcx, [rsp+13D8h+var_1318]; void **
0x1800219f3  call    ?IsAeInvAlreadyRunning@Utility@@SA_NPEAPEAX@Z; Utility::IsAeInvAlreadyRunning(void * *)
0x1800219f8  test    al, al
0x1800219fa  jz      short loc_180021A06
0x1800219fc  mov     ebx, 800700AAh
0x180021a01  jmp     loc_180021E9B
0x180021a06  call    ?InitializeWatchdogTimer@Utility@@SA_NXZ; Utility::InitializeWatchdogTimer(void)
0x180021a0b  mov     [rsp+13D8h+var_1338], 800401F0h
0x180021a16  lea     rcx, [rsp+13D8h+var_1338]
0x180021a1e  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x180021a23  mov     ebx, eax
0x180021a25  test    eax, eax
0x180021a27  jns     short loc_180021A5E
0x180021a29  mov     dword ptr [rsp+13D8h+var_13B8], eax
0x180021a2d  lea     r9, aAutowinrtiniti; "AutoWinRTInitialize::Initialize failed "...
0x180021a34  mov     r8d, 68h ; 'h'
0x180021a3a  lea     rdx, aUpdatesoftware_0; "UpdateSoftwareInventoryTC2"
0x180021a41  lea     ecx, [r8-67h]
0x180021a45  call    AslLogCallPrintf
0x180021a4a  nop
0x180021a4b  lea     rcx, [rsp+13D8h+var_1338]; this
0x180021a53  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180021a58  nop
0x180021a59  jmp     loc_180021E9B
0x180021a5e  mov     esi, 4Eh ; 'N'
0x180021a63  mov     r8d, esi; Size
0x180021a66  xor     edx, edx; Val
0x180021a68  lea     rcx, [rsp+13D8h+var_1140]; void *
0x180021a70  call    memset_0
0x180021a75  mov     [rsp+13D8h+var_10E8], di
0x180021a7d  mov     [rsp+13D8h+var_10E0], rdi
0x180021a85  xorps   xmm0, xmm0
0x180021a88  movdqa  [rsp+13D8h+var_10D8], xmm0
0x180021a91  mov     [rsp+13D8h+var_10C8], rdi
0x180021a99  mov     [rsp+13D8h+var_10C0], edi
0x180021aa0  mov     [rsp+13D8h+var_10BC], dil
0x180021aa8  mov     [rsp+13D8h+var_10F0], rdi
0x180021ab0  mov     [rsp+13D8h+var_1148], rdi
0x180021ab8  mov     ecx, 3F0h; Size
0x180021abd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021ac2  mov     [rsp+13D8h+var_1330], rax
0x180021aca  mov     rcx, rax; this
0x180021acd  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x180021ad2  nop
0x180021ad3  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180021ada  cmp     cs:qword_1801222A8, 7
0x180021ae2  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180021aea  mov     dword ptr [rsp+13D8h+var_13A8], 1F4h
0x180021af2  mov     dword ptr [rsp+13D8h+var_13B0], 5
0x180021afa  mov     dword ptr [rsp+13D8h+var_13B8], 2
0x180021b02  xor     r9d, r9d
0x180021b05  mov     r8, rax
0x180021b08  lea     rcx, [rsp+13D8h+var_1148]
0x180021b10  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180021b15  mov     ebx, eax
0x180021b17  test    eax, eax
0x180021b19  jns     short loc_180021B5B
0x180021b1b  mov     dword ptr [rsp+13D8h+var_13B8], eax
0x180021b1f  lea     r9, aTelcacheprovid_13; "TelCacheProvider::Initialize failed [%#"...
0x180021b26  lea     r8d, [rsi+23h]
0x180021b2a  lea     rdx, aUpdatesoftware_0; "UpdateSoftwareInventoryTC2"
0x180021b31  lea     ecx, [rsi-4Dh]
0x180021b34  call    AslLogCallPrintf
0x180021b39  nop
0x180021b3a  lea     rcx, [rsp+13D8h+var_1148]; this
0x180021b42  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180021b47  nop
0x180021b48  lea     rcx, [rsp+13D8h+var_1338]; this
0x180021b50  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180021b55  nop
0x180021b56  jmp     loc_180021E9B
0x180021b5b  cmp     [rsp+13D8h+arg_10], dil
0x180021b63  jz      short loc_180021B72
0x180021b65  lea     rcx, [rsp+13D8h+var_1148]; this
0x180021b6d  call    ?ClearData@TelCacheProvider@@QEAAJXZ; TelCacheProvider::ClearData(void)
0x180021b72  mov     r8, rsi; Size
0x180021b75  xor     edx, edx; Val
0x180021b77  lea     rcx, [rsp+13D8h+var_11E0]; void *
0x180021b7f  call    memset_0
0x180021b84  mov     [rsp+13D8h+var_1188], di
0x180021b8c  mov     [rsp+13D8h+var_1180], rdi
0x180021b94  xorps   xmm0, xmm0
0x180021b97  movdqa  [rsp+13D8h+var_1178], xmm0
0x180021ba0  mov     [rsp+13D8h+var_1168], rdi
0x180021ba8  mov     [rsp+13D8h+var_1160], edi
0x180021baf  mov     [rsp+13D8h+var_115C], dil
0x180021bb7  mov     [rsp+13D8h+var_1190], rdi
0x180021bbf  mov     [rsp+13D8h+var_11E8], rdi
0x180021bc7  mov     ecx, 330h; Size
0x180021bcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021bd1  mov     [rsp+13D8h+var_1330], rax
0x180021bd9  mov     rcx, rax; this
0x180021bdc  call    ??0File@@QEAA@XZ; File::File(void)
0x180021be1  nop
0x180021be2  lea     rcx, [rax+8]
0x180021be6  neg     rax
0x180021be9  sbb     r8, r8
0x180021bec  and     r8, rcx
0x180021bef  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180021bf6  cmp     cs:qword_180121AA8, 7
0x180021bfe  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180021c06  mov     dword ptr [rsp+13D8h+var_13A8], 1F4h
0x180021c0e  mov     dword ptr [rsp+13D8h+var_13B0], 5
0x180021c16  mov     dword ptr [rsp+13D8h+var_13B8], 2
0x180021c1e  xor     r9d, r9d
0x180021c21  lea     rcx, [rsp+13D8h+var_11E8]
0x180021c29  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180021c2e  mov     ebx, eax
0x180021c30  test    eax, eax
0x180021c32  jns     short loc_180021C85
0x180021c34  mov     dword ptr [rsp+13D8h+var_13B8], eax
0x180021c38  lea     r9, aTelcacheprovid_13; "TelCacheProvider::Initialize failed [%#"...
0x180021c3f  mov     r8d, 7Fh
0x180021c45  lea     rdx, aUpdatesoftware_0; "UpdateSoftwareInventoryTC2"
0x180021c4c  lea     ecx, [r8-7Eh]
0x180021c50  call    AslLogCallPrintf
0x180021c55  nop
0x180021c56  lea     rcx, [rsp+13D8h+var_11E8]; this
0x180021c5e  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180021c63  nop
0x180021c64  lea     rcx, [rsp+13D8h+var_1148]; this
0x180021c6c  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180021c71  nop
0x180021c72  lea     rcx, [rsp+13D8h+var_1338]; this
0x180021c7a  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180021c7f  nop
0x180021c80  jmp     loc_180021E9B
0x180021c85  lea     rsi, pszFormat
0x180021c8c  mov     rdx, rsi
0x180021c8f  lea     rcx, [rsp+13D8h+var_1038]
0x180021c97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021c9c  nop
0x180021c9d  mov     rdx, rsi
0x180021ca0  lea     rcx, [rsp+13D8h+var_1058]
0x180021ca8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021cad  nop
0x180021cae  mov     rdx, rsi
0x180021cb1  lea     rcx, [rsp+13D8h+var_1078]
0x180021cb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021cbe  nop
0x180021cbf  mov     rdx, rsi
0x180021cc2  lea     rcx, [rsp+13D8h+var_1098]
0x180021cca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021ccf  nop
0x180021cd0  mov     rdx, rsi
0x180021cd3  lea     rcx, [rsp+13D8h+var_10B8]
0x180021cdb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021ce0  nop
0x180021ce1  mov     [rsp+13D8h+var_1358], dil
0x180021ce9  lea     rax, [rsp+13D8h+var_1038]
0x180021cf1  mov     [rsp+13D8h+var_1380], rax
0x180021cf6  lea     rax, [rsp+13D8h+var_1058]
0x180021cfe  mov     [rsp+13D8h+var_1388], rax
0x180021d03  lea     rax, [rsp+13D8h+var_1078]
0x180021d0b  mov     [rsp+13D8h+var_1390], rax
0x180021d10  lea     rax, [rsp+13D8h+var_1098]
0x180021d18  mov     [rsp+13D8h+var_1398], rax
0x180021d1d  lea     rax, [rsp+13D8h+var_10B8]
0x180021d25  mov     [rsp+13D8h+var_13A0], rax
0x180021d2a  mov     byte ptr [rsp+13D8h+var_13B0], dil
0x180021d2f  mov     byte ptr [rsp+13D8h+var_13B8], dil
0x180021d34  lea     r9, [rsp+13D8h+var_11E8]
0x180021d3c  lea     r8, [rsp+13D8h+var_1148]
0x180021d44  xor     edx, edx
0x180021d46  lea     rcx, [rsp+13D8h+var_1018]
0x180021d4e  call    ??0ConfigSettings@@QEAA@W4FileInventoryMode@@PEAVTelCacheProvider@@1_N2W4StoreAppEnumType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@4444_N5555555@Z; ConfigSettings::ConfigSettings(FileInventoryMode,TelCacheProvider *,TelCacheProvider *,bool,bool,StoreAppEnumType,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool,bool,bool,bool,bool)
0x180021d53  nop
0x180021d54  lea     rcx, [rsp+13D8h+var_10B8]
0x180021d5c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021d61  nop
0x180021d62  lea     rcx, [rsp+13D8h+var_1098]
0x180021d6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021d6f  nop
0x180021d70  lea     rcx, [rsp+13D8h+var_1078]
0x180021d78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021d7d  nop
0x180021d7e  lea     rcx, [rsp+13D8h+var_1058]
0x180021d86  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021d8b  nop
0x180021d8c  lea     rcx, [rsp+13D8h+var_1038]
0x180021d94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021d99  xorps   xmm0, xmm0
0x180021d9c  movdqu  [rsp+13D8h+var_1310], xmm0
0x180021da5  mov     [rsp+13D8h+var_1300], rdi
0x180021dad  lea     rcx, [rsp+13D8h+var_1148]; this
0x180021db5  call    ?BatchBegin@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchBegin(void)
0x180021dba  lea     rax, ??_7StoreAppFinder@@6B@; const StoreAppFinder::`vftable'
0x180021dc1  mov     [rsp+13D8h+var_1330], rax
0x180021dc9  lea     rdx, [rsp+13D8h+var_1310]
0x180021dd1  lea     rcx, [rsp+13D8h+var_1018]
0x180021dd9  call    ?EnumeratePackages@StoreAppFinder@@SAXAEBVConfigSettings@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z; StoreAppFinder::EnumeratePackages(ConfigSettings const &,std::vector<Application> &)
0x180021dde  lea     rcx, [rsp+13D8h+var_1148]; this
0x180021de6  call    ?BatchEnd@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchEnd(void)
0x180021deb  lea     rcx, [rsp+13D8h+var_1148]; struct TelCacheProvider *
0x180021df3  call    ?SetLastInventoryScanTime@@YAXAEAVTelCacheProvider@@@Z; SetLastInventoryScanTime(TelCacheProvider &)
0x180021df8  nop
0x180021df9  mov     rcx, qword ptr [rsp+13D8h+var_1310]
0x180021e01  test    rcx, rcx
0x180021e04  jz      short loc_180021E58
0x180021e06  mov     rdx, qword ptr [rsp+13D8h+var_1310+8]
0x180021e0e  call    ??$_Destroy_range@V?$allocator@VApplication@@@std@@@std@@YAXPEAVApplication@@QEAV1@AEAV?$allocator@VApplication@@@0@@Z; std::_Destroy_range<std::allocator<Application>>(Application *,Application * const,std::allocator<Application> &)
0x180021e13  mov     rcx, qword ptr [rsp+13D8h+var_1310]
0x180021e1b  mov     rax, [rsp+13D8h+var_1300]
0x180021e23  sub     rax, rcx
0x180021e26  sar     rax, 4
0x180021e2a  mov     rdx, 0EFBEFBEFBEFBEFBFh
0x180021e34  imul    rax, rdx
0x180021e38  imul    rdx, rax, 3F0h
0x180021e3f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021e44  xorps   xmm0, xmm0
0x180021e47  movdqu  [rsp+13D8h+var_1310], xmm0
0x180021e50  mov     [rsp+13D8h+var_1300], rdi
0x180021e58  lea     rcx, [rsp+13D8h+var_1018]; this
0x180021e60  call    ??1ConfigSettings@@UEAA@XZ; ConfigSettings::~ConfigSettings(void)
0x180021e65  nop
0x180021e66  lea     rcx, [rsp+13D8h+var_11E8]; this
0x180021e6e  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180021e73  nop
0x180021e74  lea     rcx, [rsp+13D8h+var_1148]; this
0x180021e7c  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180021e81  nop
0x180021e82  lea     rcx, [rsp+13D8h+var_1338]; this
0x180021e8a  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180021e8f  nop
0x180021e90  jmp     short loc_180021E9B
0x180021e92  xor     edi, edi
0x180021e94  mov     ebx, [rsp+13D8h+var_1338]
0x180021e9b  call    ?UninitializeWatchdogTimer@Utility@@SA_NXZ; Utility::UninitializeWatchdogTimer(void)
0x180021ea0  mov     [rsp+13D8h+var_1328], rdi
0x180021ea8  lea     rcx, [rsp+13D8h+var_1328]; UnbiasedTime
0x180021eb0  call    cs:__imp_QueryUnbiasedInterruptTime
0x180021eb6  mov     rsi, qword ptr cs:xmmword_1801216E0+8
0x180021ebd  mov     eax, [rsi]
0x180021ebf  cmp     eax, 5
0x180021ec2  jbe     loc_180021FD6
0x180021ec8  mov     rdx, 400000000000h
0x180021ed2  mov     rcx, rsi
0x180021ed5  call    _tlgKeywordOn
0x180021eda  test    al, al
0x180021edc  jz      loc_180021FD6
0x180021ee2  lea     rax, byte_1801216F8
0x180021ee9  mov     [rsp+13D8h+var_12F8], rax
0x180021ef1  call    ?InventoryCoreGetVersion@@YAPEBGXZ; InventoryCoreGetVersion(void)
0x180021ef6  mov     [rsp+13D8h+var_12F0], rax
0x180021efe  mov     [rsp+13D8h+var_1338], ebx
0x180021f05  mov     rcx, [rsp+13D8h+var_1328]
0x180021f0d  sub     rcx, [rsp+13D8h+UnbiasedTime]
0x180021f15  mov     rax, 346DC5D63886594Bh
0x180021f1f  mul     rcx
0x180021f22  shr     rdx, 0Bh
0x180021f26  mov     [rsp+13D8h+var_12E8], rdx
0x180021f2e  lea     rcx, aIncremental; "incremental"
0x180021f35  lea     rax, aFullsync; "fullSync"
0x180021f3c  cmp     [rsp+13D8h+arg_10], dil
0x180021f44  cmovz   rax, rcx
0x180021f48  mov     [rsp+13D8h+var_12E0], rax
0x180021f50  lea     rax, aAepicupdatesof; "AepicUpdateSoftwareInventory"
0x180021f57  mov     [rsp+13D8h+var_12D8], rax
0x180021f5f  mov     [rsp+13D8h+var_1330], 1000000h
0x180021f6b  lea     rax, [rsp+13D8h+var_12F8]
0x180021f73  mov     [rsp+13D8h+var_1388], rax
0x180021f78  lea     rax, [rsp+13D8h+var_12F0]
0x180021f80  mov     [rsp+13D8h+var_1390], rax
0x180021f85  lea     rax, [rsp+13D8h+var_1338]
0x180021f8d  mov     [rsp+13D8h+var_1398], rax
0x180021f92  lea     rax, [rsp+13D8h+var_12E8]
0x180021f9a  mov     [rsp+13D8h+var_13A0], rax
0x180021f9f  lea     rax, [rsp+13D8h+var_12E0]
0x180021fa7  mov     [rsp+13D8h+var_13A8], rax
0x180021fac  lea     rax, [rsp+13D8h+var_12D8]
0x180021fb4  mov     [rsp+13D8h+var_13B0], rax
0x180021fb9  lea     rax, [rsp+13D8h+var_1330]
0x180021fc1  mov     [rsp+13D8h+var_13B8], rax
0x180021fc6  lea     rdx, byte_18010DDAB
0x180021fcd  mov     rcx, rsi
0x180021fd0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x180021fd5  nop
0x180021fd6  lea     rcx, [rsp+13D8h+var_1318]
0x180021fde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180021fe3  mov     eax, ebx
0x180021fe5  mov     rcx, [rsp+13D8h+var_18]
  ... truncated ...
```
