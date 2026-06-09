# MdmHttpWrapper::RegisterDevice(ulong *,ushort const *,MdmRegistrationParameters *)

- ea: `0x180011800`
- end: `0x180011e4a`
- name: `?RegisterDevice@MdmHttpWrapper@@SAJPEAKPEBGPEAUMdmRegistrationParameters@@@Z`
- size: `1610`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *, struct MdmRegistrationParameters *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800053b0`

## callees

- `0x180001520`
- `0x180002de8`
- `0x1800065c0`
- `0x18000bb9c`
- `0x18000c6e8`
- `0x180011800`
- `0x1800137ac`
- `0x1800138dc`
- `0x180013a0c`
- `0x180013b3c`
- `0x180013c6c`
- `0x180013d9c`
- `0x180013f74`
- `0x1800140a4`
- `0x180014214`
- `0x18001d4f4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011d21`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011d21`

## string_xrefs

- `0x180011d87`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180011998`: `CHR(CreateRegisterDeviceRequestBody( pParameters, wstrRequestBody, wstrCommandChannelHash, wstrMobileNetworksHash, wstrDeviceInfoHash, wstrHardwareInfoHash, wstrStorageInfoHash, wstrProtectionStateHash, wstrConnectedAccountsHash, &fProtectionSessionGuidIncluded))`
- `0x180011a23`: `CHR(MdmSettings::GetRegisterDevicePath(wstrPath))`
- `0x180011a59`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x180011ad5`: `CHR(pMdmTransport->SendRequestToCommandService( L"PUT", wstrPath.c_str(), pwszTicket, nullptr, wstrRequestBody, &dwHttpStatus, nullptr))`
- `0x180011b5b`: `CHR(MdmSettings::SetCommandChannelHash(pParameters->m_eDeviceContext, wstrCommandChannelHash))`
- `0x180011d73`: `CHR(MdmSettings::SetRegisteredWithService(pParameters->m_eDeviceContext, 1))`
- `0x1800119cb`: `Software\Microsoft\MdmCommon\Internal`
- `0x1800119c4`: `RegisterDevicePath`
- `0x180011a06`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800119f2`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterDevicePathValueName, pszValue))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MdmHttpWrapper::RegisterDevice(
        unsigned int *a1,
        const unsigned __int16 *a2,
        struct MdmRegistrationParameters *a3)
{
  int v6; // edx
  int v7; // ecx
  int StringValue; // ebx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  int v13; // edx
  int v14; // ecx
  __int128 *v15; // r8
  int v16; // edx
  int v17; // ecx
  unsigned int v18; // eax
  int v19; // edx
  int v20; // ecx
  int v21; // edx
  int v22; // ecx
  int v23; // edx
  int v24; // ecx
  int v25; // edx
  int v26; // ecx
  int v27; // edx
  int v28; // ecx
  int v29; // edx
  int v30; // ecx
  int v31; // edx
  int v32; // ecx
  int v33; // edx
  int v34; // ecx
  int v35; // edx
  int v36; // ecx
  unsigned int v38; // [rsp+50h] [rbp-168h] BYREF
  int v39; // [rsp+54h] [rbp-164h] BYREF
  struct IMdmTransport *v40; // [rsp+58h] [rbp-160h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-158h] BYREF
  __int128 v42; // [rsp+68h] [rbp-150h] BYREF
  __m128i v43; // [rsp+78h] [rbp-140h]
  __int128 v44; // [rsp+88h] [rbp-130h] BYREF
  __m128i v45; // [rsp+98h] [rbp-120h]
  __int128 v46; // [rsp+A8h] [rbp-110h] BYREF
  __m128i v47; // [rsp+B8h] [rbp-100h]
  __int128 v48; // [rsp+C8h] [rbp-F0h] BYREF
  __m128i v49; // [rsp+D8h] [rbp-E0h]
  __int128 v50; // [rsp+E8h] [rbp-D0h] BYREF
  __m128i v51; // [rsp+F8h] [rbp-C0h]
  __int128 v52; // [rsp+108h] [rbp-B0h] BYREF
  __m128i v53; // [rsp+118h] [rbp-A0h]
  __int128 v54; // [rsp+128h] [rbp-90h] BYREF
  __m128i v55; // [rsp+138h] [rbp-80h]
  __int128 v56; // [rsp+148h] [rbp-70h] BYREF
  __m128i v57; // [rsp+158h] [rbp-60h]
  __int128 v58; // [rsp+168h] [rbp-50h] BYREF
  __m128i si128; // [rsp+178h] [rbp-40h]

  v58 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v58) = 0;
  v56 = 0;
  v57 = si128;
  LOWORD(v56) = 0;
  v54 = 0;
  v55 = si128;
  LOWORD(v54) = 0;
  v52 = 0;
  v53 = si128;
  LOWORD(v52) = 0;
  v50 = 0;
  v51 = si128;
  LOWORD(v50) = 0;
  v48 = 0;
  v49 = si128;
  LOWORD(v48) = 0;
  v46 = 0;
  v47 = si128;
  LOWORD(v46) = 0;
  v44 = 0;
  v45 = si128;
  LOWORD(v44) = 0;
  v40 = 0;
  v38 = 0;
  v42 = 0;
  v43 = si128;
  LOWORD(v42) = 0;
  v39 = 0;
  SystemTimeAsFileTime = 0;
  if ( a1 )
    *a1 = 0;
  StringValue = MdmHttpWrapper::CreateRegisterDeviceRequestBody(
                  (__int64)a3,
                  (unsigned __int64 *)&v58,
                  &v56,
                  &v54,
                  (__int64)&v52,
                  (__int64)&v50,
                  (__int64)&v48,
                  (__int64)&v46,
                  (__int64)&v44,
                  &v39);
  if ( StringValue >= 0 )
  {
    if ( si128.m128i_i64[0] )
    {
      StringValue = MdmRegistry::GetStringValue(
                      HKEY_LOCAL_MACHINE,
                      L"Software\\Microsoft\\MdmCommon\\Internal",
                      L"RegisterDevicePath",
                      &v42);
      if ( StringValue >= 0 )
      {
        StringValue = CreateHttpRequest(&v40);
        if ( StringValue >= 0 )
        {
          v15 = &v42;
          if ( v43.m128i_i64[1] > 7uLL )
            v15 = (__int128 *)v42;
          StringValue = (*(__int64 (__fastcall **)(struct IMdmTransport *, const wchar_t *, __int128 *, const unsigned __int16 *, _QWORD, __int128 *, unsigned int *, _QWORD))(*(_QWORD *)v40 + 24LL))(
                          v40,
                          L"PUT",
                          v15,
                          a2,
                          0,
                          &v58,
                          &v38,
                          0);
          if ( StringValue >= 0 )
          {
            v18 = v38;
            if ( a1 )
              *a1 = v38;
            if ( v18 - 200 <= 0x63 )
            {
              if ( v57.m128i_i64[0]
                && (StringValue = MdmSettings::SetCommandChannelHash(*((unsigned int *)a3 + 1), &v56), StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v20,
                    v19,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    139,
                    "CHR(MdmSettings::SetCommandChannelHash(pParameters->m_eDeviceContext, wstrCommandChannelHash))");
              }
              else if ( v55.m128i_i64[0]
                     && (StringValue = MdmSettings::SetMobileNetworksHash(*((unsigned int *)a3 + 1), &v54),
                         StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v22,
                    v21,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    144,
                    "CHR(MdmSettings::SetMobileNetworksHash(pParameters->m_eDeviceContext, wstrMobileNetworksHash))");
              }
              else if ( v53.m128i_i64[0]
                     && (StringValue = MdmSettings::SetDeviceInfoHash(*((unsigned int *)a3 + 1), &v52), StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v24,
                    v23,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    149,
                    "CHR(MdmSettings::SetDeviceInfoHash(pParameters->m_eDeviceContext, wstrDeviceInfoHash))");
              }
              else if ( v51.m128i_i64[0]
                     && (StringValue = MdmSettings::SetHardwareInfoHash(*((unsigned int *)a3 + 1), &v50), StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v26,
                    v25,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    154,
                    "CHR(MdmSettings::SetHardwareInfoHash(pParameters->m_eDeviceContext, wstrHardwareInfoHash))");
              }
              else if ( v49.m128i_i64[0]
                     && (StringValue = MdmSettings::SetStorageInfoHash(*((unsigned int *)a3 + 1), &v48), StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v28,
                    v27,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    159,
                    "CHR(MdmSettings::SetStorageInfoHash(pParameters->m_eDeviceContext, wstrStorageInfoHash))");
              }
              else if ( v47.m128i_i64[0]
                     && (StringValue = MdmSettings::SetProtectionStateHash(*((unsigned int *)a3 + 1), &v46),
                         StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v30,
                    v29,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    164,
                    "CHR(MdmSettings::SetProtectionStateHash(pParameters->m_eDeviceContext, wstrProtectionStateHash))");
              }
              else if ( v45.m128i_i64[0]
                     && (StringValue = MdmSettings::SetConnectedAccountsHash(*((unsigned int *)a3 + 1), &v44),
                         StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v32,
                    v31,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    169,
                    "CHR(MdmSettings::SetConnectedAccountsHash(pParameters->m_eDeviceContext, wstrConnectedAccountsHash))");
              }
              else if ( v39
                     && (GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
                         StringValue = MdmSettings::SetProtectionSessionLastSent(*(_QWORD *)&SystemTimeAsFileTime),
                         StringValue < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v34,
                    v33,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    175,
                    "CHR(MdmSettings::SetProtectionSessionLastSent(ftNow.ullTime))");
              }
              else
              {
                StringValue = MdmSettings::SetRegisteredWithService(*((unsigned int *)a3 + 1));
                if ( StringValue < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v36,
                    v35,
                    StringValue,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    179,
                    "CHR(MdmSettings::SetRegisteredWithService(pParameters->m_eDeviceContext, 1))");
              }
            }
            else
            {
              StringValue = -2147467259;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v17,
                  v16,
                  -2147467259,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                  133,
                  "CHR(((HRESULT)0x80004005L))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v17,
              v16,
              StringValue,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
              123,
              "CHR(pMdmTransport->SendRequestToCommandService( L\"PUT\", wstrPath.c_str(), pwszTicket, nullptr, wstrReque"
              "stBody, &dwHttpStatus, nullptr))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v14,
            v13,
            StringValue,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            115,
            "CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          StringValue,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          37,
          "CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterDevicePathValueName, pszValue))");
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v12,
            v11,
            StringValue,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            112,
            "CHR(MdmSettings::GetRegisterDevicePath(wstrPath))");
      }
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      StringValue,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      103,
      "CHR(CreateRegisterDeviceRequestBody( pParameters, wstrRequestBody, wstrCommandChannelHash, wstrMobileNetworksHash,"
      " wstrDeviceInfoHash, wstrHardwareInfoHash, wstrStorageInfoHash, wstrProtectionStateHash, wstrConnectedAccountsHash"
      ", &fProtectionSessionGuidIncluded))");
  }
  std::wstring::~wstring(&v42);
  if ( v40 )
    (*(void (__fastcall **)(struct IMdmTransport *))(*(_QWORD *)v40 + 16LL))(v40);
  std::wstring::~wstring(&v44);
  std::wstring::~wstring(&v46);
  std::wstring::~wstring(&v48);
  std::wstring::~wstring(&v50);
  std::wstring::~wstring(&v52);
  std::wstring::~wstring(&v54);
  std::wstring::~wstring(&v56);
  std::wstring::~wstring(&v58);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180011800  mov     r11, rsp
0x180011803  push    rbx
0x180011804  push    rsi
0x180011805  push    rdi
0x180011806  push    r14
0x180011808  push    r15
0x18001180a  sub     rsp, 190h
0x180011811  mov     rax, cs:__security_cookie
0x180011818  xor     rax, rsp
0x18001181b  mov     [rsp+1B8h+var_30], rax
0x180011823  mov     rdi, r8
0x180011826  mov     r14, rdx
0x180011829  mov     rsi, rcx
0x18001182c  xorps   xmm0, xmm0
0x18001182f  movups  xmmword ptr [r11-50h], xmm0
0x180011834  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001183c  movdqu  xmmword ptr [r11-40h], xmm1
0x180011842  xor     r15d, r15d
0x180011845  mov     [r11-50h], r15w
0x18001184a  movups  xmmword ptr [r11-70h], xmm0
0x18001184f  movdqu  xmmword ptr [r11-60h], xmm1
0x180011855  mov     [r11-70h], r15w
0x18001185a  movups  [rsp+1B8h+var_90], xmm0
0x180011862  movdqu  xmmword ptr [r11-80h], xmm1
0x180011868  mov     [r11-90h], r15w
0x180011870  movups  [rsp+1B8h+var_B0], xmm0
0x180011878  movdqu  [rsp+1B8h+var_A0], xmm1
0x180011881  mov     [r11-0B0h], r15w
0x180011889  movups  [rsp+1B8h+var_D0], xmm0
0x180011891  movdqu  [rsp+1B8h+var_C0], xmm1
0x18001189a  mov     [r11-0D0h], r15w
0x1800118a2  movups  [rsp+1B8h+var_F0], xmm0
0x1800118aa  movdqu  [rsp+1B8h+var_E0], xmm1
0x1800118b3  mov     [r11-0F0h], r15w
0x1800118bb  movups  [rsp+1B8h+var_110], xmm0
0x1800118c3  movdqu  [rsp+1B8h+var_100], xmm1
0x1800118cc  mov     [r11-110h], r15w
0x1800118d4  movups  [rsp+1B8h+var_130], xmm0
0x1800118dc  movdqu  [rsp+1B8h+var_120], xmm1
0x1800118e5  mov     [r11-130h], r15w
0x1800118ed  mov     [rsp+1B8h+var_160], r15
0x1800118f2  mov     [rsp+1B8h+var_168], r15d
0x1800118f7  movups  [rsp+1B8h+var_150], xmm0
0x1800118fc  movdqu  [rsp+1B8h+var_140], xmm1
0x180011902  mov     word ptr [rsp+1B8h+var_150], r15w
0x180011908  mov     [rsp+1B8h+var_164], r15d
0x18001190d  mov     qword ptr [rsp+1B8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180011912  test    rcx, rcx
0x180011915  jz      short loc_18001191A
0x180011917  mov     [rcx], r15d
0x18001191a  lea     rax, [rsp+1B8h+var_164]
0x18001191f  mov     [rsp+1B8h+var_170], rax
0x180011924  lea     rax, [rsp+1B8h+var_130]
0x18001192c  mov     [rsp+1B8h+var_178], rax
0x180011931  lea     rax, [rsp+1B8h+var_110]
0x180011939  mov     [rsp+1B8h+var_180], rax
0x18001193e  lea     rax, [rsp+1B8h+var_F0]
0x180011946  mov     [rsp+1B8h+var_188], rax
0x18001194b  lea     rax, [rsp+1B8h+var_D0]
0x180011953  mov     [rsp+1B8h+var_190], rax
0x180011958  lea     rax, [rsp+1B8h+var_B0]
0x180011960  mov     [rsp+1B8h+var_198], rax
0x180011965  lea     r9, [rsp+1B8h+var_90]
0x18001196d  lea     r8, [rsp+1B8h+var_70]
0x180011975  lea     rdx, [rsp+1B8h+var_50]
0x18001197d  mov     rcx, rdi
0x180011980  call    ?CreateRegisterDeviceRequestBody@MdmHttpWrapper@@SAJPEAUMdmRegistrationParameters@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1111111PEAH@Z; MdmHttpWrapper::CreateRegisterDeviceRequestBody(MdmRegistrationParameters *,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,int *)
0x180011985  mov     ebx, eax
0x180011987  test    eax, eax
0x180011989  jns     short loc_1800119B1
0x18001198b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011992  jz      loc_180011D97
0x180011998  lea     rax, aChrCreateregis; "CHR(CreateRegisterDeviceRequestBody( pP"...
0x18001199f  mov     [rsp+1B8h+var_190], rax
0x1800119a4  mov     dword ptr [rsp+1B8h+var_198], 67h ; 'g'
0x1800119ac  jmp     loc_180011D87
0x1800119b1  cmp     qword ptr [rsp+1B8h+var_40], r15
0x1800119b9  jz      loc_180011D97
0x1800119bf  lea     r9, [rsp+1B8h+var_150]
0x1800119c4  lea     r8, aRegisterdevice; "RegisterDevicePath"
0x1800119cb  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x1800119d2  mov     rcx, 0FFFFFFFF80000002h
0x1800119d9  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x1800119de  mov     ebx, eax
0x1800119e0  test    eax, eax
0x1800119e2  jns     short loc_180011A3C
0x1800119e4  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800119ea  test    al, 1
0x1800119ec  jz      loc_180011D97
0x1800119f2  lea     rax, aChrMdmregistry; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x1800119f9  mov     [rsp+1B8h+var_190], rax
0x1800119fe  mov     dword ptr [rsp+1B8h+var_198], 225h
0x180011a06  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011a0d  mov     r8d, ebx
0x180011a10  call    McTemplateU0dsqs_EventWriteTransfer
0x180011a15  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180011a1b  test    al, 1
0x180011a1d  jz      loc_180011D97
0x180011a23  lea     rax, aChrMdmsettings_21; "CHR(MdmSettings::GetRegisterDevicePath("...
0x180011a2a  mov     [rsp+1B8h+var_190], rax
0x180011a2f  mov     dword ptr [rsp+1B8h+var_198], 70h ; 'p'
0x180011a37  jmp     loc_180011D87
0x180011a3c  lea     rcx, [rsp+1B8h+var_160]; struct IMdmTransport **
0x180011a41  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180011a46  mov     ebx, eax
0x180011a48  test    eax, eax
0x180011a4a  jns     short loc_180011A72
0x180011a4c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011a53  jz      loc_180011D97
0x180011a59  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x180011a60  mov     [rsp+1B8h+var_190], rax
0x180011a65  mov     dword ptr [rsp+1B8h+var_198], 73h ; 's'
0x180011a6d  jmp     loc_180011D87
0x180011a72  mov     rcx, [rsp+1B8h+var_160]
0x180011a77  mov     rax, [rcx]
0x180011a7a  lea     r8, [rsp+1B8h+var_150]
0x180011a7f  cmp     qword ptr [rsp+1B8h+var_140+8], 7
0x180011a88  cmova   r8, qword ptr [rsp+1B8h+var_150]
0x180011a8e  mov     [rsp+1B8h+var_180], r15
0x180011a93  lea     rdx, [rsp+1B8h+var_168]
0x180011a98  mov     [rsp+1B8h+var_188], rdx
0x180011a9d  lea     rdx, [rsp+1B8h+var_50]
0x180011aa5  mov     [rsp+1B8h+var_190], rdx
0x180011aaa  mov     [rsp+1B8h+var_198], r15
0x180011aaf  mov     r9, r14
0x180011ab2  lea     rdx, aPut; "PUT"
0x180011ab9  mov     rax, [rax+18h]
0x180011abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ac2  mov     ebx, eax
0x180011ac4  test    eax, eax
0x180011ac6  jns     short loc_180011AEE
0x180011ac8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011acf  jz      loc_180011D97
0x180011ad5  lea     rax, aChrPmdmtranspo; "CHR(pMdmTransport->SendRequestToCommand"...
0x180011adc  mov     [rsp+1B8h+var_190], rax
0x180011ae1  mov     dword ptr [rsp+1B8h+var_198], 7Bh ; '{'
0x180011ae9  jmp     loc_180011D87
0x180011aee  mov     eax, [rsp+1B8h+var_168]
0x180011af2  test    rsi, rsi
0x180011af5  jz      short loc_180011AF9
0x180011af7  mov     [rsi], eax
0x180011af9  add     eax, 0FFFFFF38h
0x180011afe  cmp     eax, 63h ; 'c'
0x180011b01  jbe     short loc_180011B2E
0x180011b03  mov     ebx, 80004005h
0x180011b08  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011b0f  jz      loc_180011D97
0x180011b15  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x180011b1c  mov     [rsp+1B8h+var_190], rax
0x180011b21  mov     dword ptr [rsp+1B8h+var_198], 85h
0x180011b29  jmp     loc_180011D87
0x180011b2e  cmp     qword ptr [rsp+1B8h+var_60], r15
0x180011b36  jbe     short loc_180011B74
0x180011b38  lea     rdx, [rsp+1B8h+var_70]
0x180011b40  mov     ecx, [rdi+4]
0x180011b43  call    ?SetCommandChannelHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetCommandChannelHash(MdmDeviceContext,std::wstring const &)
0x180011b48  mov     ebx, eax
0x180011b4a  test    eax, eax
0x180011b4c  jns     short loc_180011B74
0x180011b4e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011b55  jz      loc_180011D97
0x180011b5b  lea     rax, aChrMdmsettings_9; "CHR(MdmSettings::SetCommandChannelHash("...
0x180011b62  mov     [rsp+1B8h+var_190], rax
0x180011b67  mov     dword ptr [rsp+1B8h+var_198], 8Bh
0x180011b6f  jmp     loc_180011D87
0x180011b74  cmp     qword ptr [rsp+1B8h+var_80], r15
0x180011b7c  jbe     short loc_180011BBA
0x180011b7e  lea     rdx, [rsp+1B8h+var_90]
0x180011b86  mov     ecx, [rdi+4]
0x180011b89  call    ?SetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetMobileNetworksHash(MdmDeviceContext,std::wstring const &)
0x180011b8e  mov     ebx, eax
0x180011b90  test    eax, eax
0x180011b92  jns     short loc_180011BBA
0x180011b94  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011b9b  jz      loc_180011D97
0x180011ba1  lea     rax, aChrMdmsettings_23; "CHR(MdmSettings::SetMobileNetworksHash("...
0x180011ba8  mov     [rsp+1B8h+var_190], rax
0x180011bad  mov     dword ptr [rsp+1B8h+var_198], 90h
0x180011bb5  jmp     loc_180011D87
0x180011bba  cmp     qword ptr [rsp+1B8h+var_A0], r15
0x180011bc2  jbe     short loc_180011C00
0x180011bc4  lea     rdx, [rsp+1B8h+var_B0]
0x180011bcc  mov     ecx, [rdi+4]
0x180011bcf  call    ?SetDeviceInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetDeviceInfoHash(MdmDeviceContext,std::wstring const &)
0x180011bd4  mov     ebx, eax
0x180011bd6  test    eax, eax
0x180011bd8  jns     short loc_180011C00
0x180011bda  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011be1  jz      loc_180011D97
0x180011be7  lea     rax, aChrMdmsettings_25; "CHR(MdmSettings::SetDeviceInfoHash(pPar"...
0x180011bee  mov     [rsp+1B8h+var_190], rax
0x180011bf3  mov     dword ptr [rsp+1B8h+var_198], 95h
0x180011bfb  jmp     loc_180011D87
0x180011c00  cmp     qword ptr [rsp+1B8h+var_C0], r15
0x180011c08  jbe     short loc_180011C46
0x180011c0a  lea     rdx, [rsp+1B8h+var_D0]
0x180011c12  mov     ecx, [rdi+4]
0x180011c15  call    ?SetHardwareInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetHardwareInfoHash(MdmDeviceContext,std::wstring const &)
0x180011c1a  mov     ebx, eax
0x180011c1c  test    eax, eax
0x180011c1e  jns     short loc_180011C46
0x180011c20  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011c27  jz      loc_180011D97
0x180011c2d  lea     rax, aChrMdmsettings; "CHR(MdmSettings::SetHardwareInfoHash(pP"...
0x180011c34  mov     [rsp+1B8h+var_190], rax
0x180011c39  mov     dword ptr [rsp+1B8h+var_198], 9Ah
0x180011c41  jmp     loc_180011D87
0x180011c46  cmp     qword ptr [rsp+1B8h+var_E0], r15
0x180011c4e  jbe     short loc_180011C8C
0x180011c50  lea     rdx, [rsp+1B8h+var_F0]
0x180011c58  mov     ecx, [rdi+4]
0x180011c5b  call    ?SetStorageInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetStorageInfoHash(MdmDeviceContext,std::wstring const &)
0x180011c60  mov     ebx, eax
0x180011c62  test    eax, eax
0x180011c64  jns     short loc_180011C8C
0x180011c66  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011c6d  jz      loc_180011D97
0x180011c73  lea     rax, aChrMdmsettings_3; "CHR(MdmSettings::SetStorageInfoHash(pPa"...
0x180011c7a  mov     [rsp+1B8h+var_190], rax
0x180011c7f  mov     dword ptr [rsp+1B8h+var_198], 9Fh
0x180011c87  jmp     loc_180011D87
0x180011c8c  cmp     qword ptr [rsp+1B8h+var_100], r15
0x180011c94  jbe     short loc_180011CD2
0x180011c96  lea     rdx, [rsp+1B8h+var_110]
0x180011c9e  mov     ecx, [rdi+4]
0x180011ca1  call    ?SetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetProtectionStateHash(MdmDeviceContext,std::wstring const &)
0x180011ca6  mov     ebx, eax
0x180011ca8  test    eax, eax
0x180011caa  jns     short loc_180011CD2
0x180011cac  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011cb3  jz      loc_180011D97
0x180011cb9  lea     rax, aChrMdmsettings_6; "CHR(MdmSettings::SetProtectionStateHash"...
0x180011cc0  mov     [rsp+1B8h+var_190], rax
0x180011cc5  mov     dword ptr [rsp+1B8h+var_198], 0A4h
0x180011ccd  jmp     loc_180011D87
0x180011cd2  cmp     qword ptr [rsp+1B8h+var_120], r15
0x180011cda  jbe     short loc_180011D15
0x180011cdc  lea     rdx, [rsp+1B8h+var_130]
0x180011ce4  mov     ecx, [rdi+4]
0x180011ce7  call    ?SetConnectedAccountsHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetConnectedAccountsHash(MdmDeviceContext,std::wstring const &)
0x180011cec  mov     ebx, eax
0x180011cee  test    eax, eax
0x180011cf0  jns     short loc_180011D15
0x180011cf2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011cf9  jz      loc_180011D97
0x180011cff  lea     rax, aChrMdmsettings_8; "CHR(MdmSettings::SetConnectedAccountsHa"...
0x180011d06  mov     [rsp+1B8h+var_190], rax
0x180011d0b  mov     dword ptr [rsp+1B8h+var_198], 0A9h
0x180011d13  jmp     short loc_180011D87
0x180011d15  cmp     [rsp+1B8h+var_164], r15d
0x180011d1a  jz      short loc_180011D5C
0x180011d1c  lea     rcx, [rsp+1B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180011d21  call    cs:__imp_GetSystemTimeAsFileTime
0x180011d28  nop     dword ptr [rax+rax+00h]
0x180011d2d  mov     rcx, qword ptr [rsp+1B8h+SystemTimeAsFileTime.dwLowDateTime]; unsigned __int64
0x180011d32  call    ?SetProtectionSessionLastSent@MdmSettings@@SAJ_K@Z; MdmSettings::SetProtectionSessionLastSent(unsigned __int64)
0x180011d37  mov     ebx, eax
0x180011d39  test    eax, eax
0x180011d3b  jns     short loc_180011D5C
0x180011d3d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011d44  jz      short loc_180011D97
0x180011d46  lea     rax, aChrMdmsettings_15; "CHR(MdmSettings::SetProtectionSessionLa"...
0x180011d4d  mov     [rsp+1B8h+var_190], rax
0x180011d52  mov     dword ptr [rsp+1B8h+var_198], 0AFh
0x180011d5a  jmp     short loc_180011D87
0x180011d5c  mov     ecx, [rdi+4]
0x180011d5f  call    ?SetRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@H@Z; MdmSettings::SetRegisteredWithService(MdmDeviceContext,int)
0x180011d64  mov     ebx, eax
0x180011d66  test    eax, eax
0x180011d68  jns     short loc_180011D97
0x180011d6a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011d71  jz      short loc_180011D97
0x180011d73  lea     rax, aChrMdmsettings_4; "CHR(MdmSettings::SetRegisteredWithServi"...
0x180011d7a  mov     [rsp+1B8h+var_190], rax
0x180011d7f  mov     dword ptr [rsp+1B8h+var_198], 0B3h
0x180011d87  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011d8e  mov     r8d, ebx
0x180011d91  call    McTemplateU0dsqs_EventWriteTransfer
0x180011d96  nop
0x180011d97  lea     rcx, [rsp+1B8h+var_150]
0x180011d9c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011da1  nop
0x180011da2  mov     rcx, [rsp+1B8h+var_160]
0x180011da7  test    rcx, rcx
0x180011daa  jz      short loc_180011DB9
0x180011dac  mov     rax, [rcx]
0x180011daf  mov     rax, [rax+10h]
0x180011db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011db8  nop
0x180011db9  lea     rcx, [rsp+1B8h+var_130]
0x180011dc1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011dc6  nop
0x180011dc7  lea     rcx, [rsp+1B8h+var_110]
0x180011dcf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011dd4  nop
0x180011dd5  lea     rcx, [rsp+1B8h+var_F0]
0x180011ddd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011de2  nop
0x180011de3  lea     rcx, [rsp+1B8h+var_D0]
0x180011deb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
