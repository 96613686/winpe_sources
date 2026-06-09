# MdmHttpWrapper::RegisterDevice(ulong *,ushort const *,MdmRegistrationParameters *)

- ea: `0x18001142c`
- end: `0x180011a6f`
- name: `?RegisterDevice@MdmHttpWrapper@@SAJPEAKPEBGPEAUMdmRegistrationParameters@@@Z`
- size: `1603`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *, struct MdmRegistrationParameters *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005360`

## callees

- `0x180001520`
- `0x180002de4`
- `0x180006548`
- `0x18000b88c`
- `0x18000c38c`
- `0x18001142c`
- `0x1800133bc`
- `0x1800134ec`
- `0x18001361c`
- `0x18001374c`
- `0x18001387c`
- `0x1800139ac`
- `0x180013b74`
- `0x180013ca4`
- `0x180013e10`
- `0x18001ce60`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001194d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001194d`

## string_xrefs

- `0x1800119ad`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x1800115c4`: `CHR(CreateRegisterDeviceRequestBody( pParameters, wstrRequestBody, wstrCommandChannelHash, wstrMobileNetworksHash, wstrDeviceInfoHash, wstrHardwareInfoHash, wstrStorageInfoHash, wstrProtectionStateHash, wstrConnectedAccountsHash, &fProtectionSessionGuidIncluded))`
- `0x18001164f`: `CHR(MdmSettings::GetRegisterDevicePath(wstrPath))`
- `0x180011685`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x180011701`: `CHR(pMdmTransport->SendRequestToCommandService( L"PUT", wstrPath.c_str(), pwszTicket, nullptr, wstrRequestBody, &dwHttpStatus, nullptr))`
- `0x180011787`: `CHR(MdmSettings::SetCommandChannelHash(pParameters->m_eDeviceContext, wstrCommandChannelHash))`
- `0x180011999`: `CHR(MdmSettings::SetRegisteredWithService(pParameters->m_eDeviceContext, 1))`
- `0x1800115f7`: `Software\Microsoft\MdmCommon\Internal`
- `0x1800115f0`: `RegisterDevicePath`
- `0x180011632`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001161e`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterDevicePathValueName, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::RegisterDevice(
        unsigned int *a1,
        const unsigned __int16 *a2,
        struct MdmRegistrationParameters *a3)
{
  int v6; // edx
  int v7; // ecx
  int RegisterDeviceRequestBody; // ebx
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
  RegisterDeviceRequestBody = MdmHttpWrapper::CreateRegisterDeviceRequestBody(
                                (_DWORD)a3,
                                (unsigned int)&v58,
                                (unsigned int)&v56,
                                (unsigned int)&v54,
                                (__int64)&v52,
                                (__int64)&v50,
                                (__int64)&v48,
                                (__int64)&v46,
                                (__int64)&v44,
                                (__int64)&v39);
  if ( RegisterDeviceRequestBody >= 0 )
  {
    if ( si128.m128i_i64[0] )
    {
      RegisterDeviceRequestBody = MdmRegistry::GetStringValue(
                                    HKEY_LOCAL_MACHINE,
                                    L"Software\\Microsoft\\MdmCommon\\Internal",
                                    L"RegisterDevicePath",
                                    &v42);
      if ( RegisterDeviceRequestBody >= 0 )
      {
        RegisterDeviceRequestBody = CreateHttpRequest(&v40);
        if ( RegisterDeviceRequestBody >= 0 )
        {
          v15 = &v42;
          if ( v43.m128i_i64[1] > 7uLL )
            v15 = (__int128 *)v42;
          RegisterDeviceRequestBody = (*(__int64 (__fastcall **)(struct IMdmTransport *, const wchar_t *, __int128 *, const unsigned __int16 *, _QWORD, __int128 *, unsigned int *, _QWORD))(*(_QWORD *)v40 + 24LL))(
                                        v40,
                                        L"PUT",
                                        v15,
                                        a2,
                                        0,
                                        &v58,
                                        &v38,
                                        0);
          if ( RegisterDeviceRequestBody >= 0 )
          {
            v18 = v38;
            if ( a1 )
              *a1 = v38;
            if ( v18 - 200 <= 0x63 )
            {
              if ( v57.m128i_i64[0]
                && (RegisterDeviceRequestBody = MdmSettings::SetCommandChannelHash(*((unsigned int *)a3 + 1), &v56),
                    RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v20,
                    v19,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    139,
                    (__int64)"CHR(MdmSettings::SetCommandChannelHash(pParameters->m_eDeviceContext, wstrCommandChannelHash))");
              }
              else if ( v55.m128i_i64[0]
                     && (RegisterDeviceRequestBody = MdmSettings::SetMobileNetworksHash(
                                                       *((_DWORD *)a3 + 1),
                                                       (__int64)&v54),
                         RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v22,
                    v21,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    144,
                    (__int64)"CHR(MdmSettings::SetMobileNetworksHash(pParameters->m_eDeviceContext, wstrMobileNetworksHash))");
              }
              else if ( v53.m128i_i64[0]
                     && (RegisterDeviceRequestBody = MdmSettings::SetDeviceInfoHash(*((unsigned int *)a3 + 1), &v52),
                         RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v24,
                    v23,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    149,
                    (__int64)"CHR(MdmSettings::SetDeviceInfoHash(pParameters->m_eDeviceContext, wstrDeviceInfoHash))");
              }
              else if ( v51.m128i_i64[0]
                     && (RegisterDeviceRequestBody = MdmSettings::SetHardwareInfoHash(
                                                       *((_DWORD *)a3 + 1),
                                                       (__int64)&v50),
                         RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v26,
                    v25,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    154,
                    (__int64)"CHR(MdmSettings::SetHardwareInfoHash(pParameters->m_eDeviceContext, wstrHardwareInfoHash))");
              }
              else if ( v49.m128i_i64[0]
                     && (RegisterDeviceRequestBody = MdmSettings::SetStorageInfoHash(*((unsigned int *)a3 + 1), &v48),
                         RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v28,
                    v27,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    159,
                    (__int64)"CHR(MdmSettings::SetStorageInfoHash(pParameters->m_eDeviceContext, wstrStorageInfoHash))");
              }
              else if ( v47.m128i_i64[0]
                     && (RegisterDeviceRequestBody = MdmSettings::SetProtectionStateHash(
                                                       *((unsigned int *)a3 + 1),
                                                       &v46),
                         RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v30,
                    v29,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    164,
                    (__int64)"CHR(MdmSettings::SetProtectionStateHash(pParameters->m_eDeviceContext, wstrProtectionStateHash))");
              }
              else if ( v45.m128i_i64[0]
                     && (RegisterDeviceRequestBody = MdmSettings::SetConnectedAccountsHash(
                                                       *((unsigned int *)a3 + 1),
                                                       &v44),
                         RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v32,
                    v31,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    169,
                    (__int64)"CHR(MdmSettings::SetConnectedAccountsHash(pParameters->m_eDeviceContext, wstrConnectedAccountsHash))");
              }
              else if ( v39
                     && (GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
                         RegisterDeviceRequestBody = MdmSettings::SetProtectionSessionLastSent(*(_QWORD *)&SystemTimeAsFileTime),
                         RegisterDeviceRequestBody < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v34,
                    v33,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    175,
                    (__int64)"CHR(MdmSettings::SetProtectionSessionLastSent(ftNow.ullTime))");
              }
              else
              {
                RegisterDeviceRequestBody = MdmSettings::SetRegisteredWithService(*((unsigned int *)a3 + 1));
                if ( RegisterDeviceRequestBody < 0
                  && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v36,
                    v35,
                    RegisterDeviceRequestBody,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                    179,
                    (__int64)"CHR(MdmSettings::SetRegisteredWithService(pParameters->m_eDeviceContext, 1))");
                }
              }
            }
            else
            {
              RegisterDeviceRequestBody = -2147467259;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v17,
                  v16,
                  -2147467259,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                  133,
                  (__int64)"CHR(((HRESULT)0x80004005L))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v17,
              v16,
              RegisterDeviceRequestBody,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
              123,
              (__int64)"CHR(pMdmTransport->SendRequestToCommandService( L\"PUT\", wstrPath.c_str(), pwszTicket, nullptr, "
                       "wstrRequestBody, &dwHttpStatus, nullptr))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v14,
            v13,
            RegisterDeviceRequestBody,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            115,
            (__int64)"CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          RegisterDeviceRequestBody,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          37,
          (__int64)"CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterDevicePathValueName, pszValue))");
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v12,
            v11,
            RegisterDeviceRequestBody,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            112,
            (__int64)"CHR(MdmSettings::GetRegisterDevicePath(wstrPath))");
      }
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      RegisterDeviceRequestBody,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      103,
      (__int64)"CHR(CreateRegisterDeviceRequestBody( pParameters, wstrRequestBody, wstrCommandChannelHash, wstrMobileNetw"
               "orksHash, wstrDeviceInfoHash, wstrHardwareInfoHash, wstrStorageInfoHash, wstrProtectionStateHash, wstrCon"
               "nectedAccountsHash, &fProtectionSessionGuidIncluded))");
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
  return (unsigned int)RegisterDeviceRequestBody;
}

```

## disassembly

```asm
0x18001142c  mov     r11, rsp
0x18001142f  push    rbx
0x180011430  push    rsi
0x180011431  push    rdi
0x180011432  push    r14
0x180011434  push    r15
0x180011436  sub     rsp, 190h
0x18001143d  mov     rax, cs:__security_cookie
0x180011444  xor     rax, rsp
0x180011447  mov     [rsp+1B8h+var_30], rax
0x18001144f  mov     rdi, r8
0x180011452  mov     r14, rdx
0x180011455  mov     rsi, rcx
0x180011458  xorps   xmm0, xmm0
0x18001145b  movups  xmmword ptr [r11-50h], xmm0
0x180011460  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011468  movdqu  xmmword ptr [r11-40h], xmm1
0x18001146e  xor     r15d, r15d
0x180011471  mov     [r11-50h], r15w
0x180011476  movups  xmmword ptr [r11-70h], xmm0
0x18001147b  movdqu  xmmword ptr [r11-60h], xmm1
0x180011481  mov     [r11-70h], r15w
0x180011486  movups  [rsp+1B8h+var_90], xmm0
0x18001148e  movdqu  xmmword ptr [r11-80h], xmm1
0x180011494  mov     [r11-90h], r15w
0x18001149c  movups  [rsp+1B8h+var_B0], xmm0
0x1800114a4  movdqu  [rsp+1B8h+var_A0], xmm1
0x1800114ad  mov     [r11-0B0h], r15w
0x1800114b5  movups  [rsp+1B8h+var_D0], xmm0
0x1800114bd  movdqu  [rsp+1B8h+var_C0], xmm1
0x1800114c6  mov     [r11-0D0h], r15w
0x1800114ce  movups  [rsp+1B8h+var_F0], xmm0
0x1800114d6  movdqu  [rsp+1B8h+var_E0], xmm1
0x1800114df  mov     [r11-0F0h], r15w
0x1800114e7  movups  [rsp+1B8h+var_110], xmm0
0x1800114ef  movdqu  [rsp+1B8h+var_100], xmm1
0x1800114f8  mov     [r11-110h], r15w
0x180011500  movups  [rsp+1B8h+var_130], xmm0
0x180011508  movdqu  [rsp+1B8h+var_120], xmm1
0x180011511  mov     [r11-130h], r15w
0x180011519  mov     [rsp+1B8h+var_160], r15
0x18001151e  mov     [rsp+1B8h+var_168], r15d
0x180011523  movups  [rsp+1B8h+var_150], xmm0
0x180011528  movdqu  [rsp+1B8h+var_140], xmm1
0x18001152e  mov     word ptr [rsp+1B8h+var_150], r15w
0x180011534  mov     [rsp+1B8h+var_164], r15d
0x180011539  mov     qword ptr [rsp+1B8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18001153e  test    rcx, rcx
0x180011541  jz      short loc_180011546
0x180011543  mov     [rcx], r15d
0x180011546  lea     rax, [rsp+1B8h+var_164]
0x18001154b  mov     [rsp+1B8h+var_170], rax
0x180011550  lea     rax, [rsp+1B8h+var_130]
0x180011558  mov     [rsp+1B8h+var_178], rax
0x18001155d  lea     rax, [rsp+1B8h+var_110]
0x180011565  mov     [rsp+1B8h+var_180], rax
0x18001156a  lea     rax, [rsp+1B8h+var_F0]
0x180011572  mov     [rsp+1B8h+var_188], rax
0x180011577  lea     rax, [rsp+1B8h+var_D0]
0x18001157f  mov     [rsp+1B8h+var_190], rax
0x180011584  lea     rax, [rsp+1B8h+var_B0]
0x18001158c  mov     [rsp+1B8h+var_198], rax
0x180011591  lea     r9, [rsp+1B8h+var_90]
0x180011599  lea     r8, [rsp+1B8h+var_70]
0x1800115a1  lea     rdx, [rsp+1B8h+var_50]
0x1800115a9  mov     rcx, rdi
0x1800115ac  call    ?CreateRegisterDeviceRequestBody@MdmHttpWrapper@@SAJPEAUMdmRegistrationParameters@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1111111PEAH@Z; MdmHttpWrapper::CreateRegisterDeviceRequestBody(MdmRegistrationParameters *,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,int *)
0x1800115b1  mov     ebx, eax
0x1800115b3  test    eax, eax
0x1800115b5  jns     short loc_1800115DD
0x1800115b7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800115be  jz      loc_1800119BD
0x1800115c4  lea     rax, aChrCreateregis; "CHR(CreateRegisterDeviceRequestBody( pP"...
0x1800115cb  mov     [rsp+1B8h+var_190], rax
0x1800115d0  mov     dword ptr [rsp+1B8h+var_198], 67h ; 'g'
0x1800115d8  jmp     loc_1800119AD
0x1800115dd  cmp     qword ptr [rsp+1B8h+var_40], r15
0x1800115e5  jz      loc_1800119BD
0x1800115eb  lea     r9, [rsp+1B8h+var_150]
0x1800115f0  lea     r8, aRegisterdevice; "RegisterDevicePath"
0x1800115f7  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x1800115fe  mov     rcx, 0FFFFFFFF80000002h
0x180011605  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x18001160a  mov     ebx, eax
0x18001160c  test    eax, eax
0x18001160e  jns     short loc_180011668
0x180011610  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180011616  test    al, 1
0x180011618  jz      loc_1800119BD
0x18001161e  lea     rax, aChrMdmregistry; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x180011625  mov     [rsp+1B8h+var_190], rax
0x18001162a  mov     dword ptr [rsp+1B8h+var_198], 225h
0x180011632  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011639  mov     r8d, ebx
0x18001163c  call    McTemplateU0dsqs_EventWriteTransfer
0x180011641  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180011647  test    al, 1
0x180011649  jz      loc_1800119BD
0x18001164f  lea     rax, aChrMdmsettings_21; "CHR(MdmSettings::GetRegisterDevicePath("...
0x180011656  mov     [rsp+1B8h+var_190], rax
0x18001165b  mov     dword ptr [rsp+1B8h+var_198], 70h ; 'p'
0x180011663  jmp     loc_1800119AD
0x180011668  lea     rcx, [rsp+1B8h+var_160]; struct IMdmTransport **
0x18001166d  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180011672  mov     ebx, eax
0x180011674  test    eax, eax
0x180011676  jns     short loc_18001169E
0x180011678  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001167f  jz      loc_1800119BD
0x180011685  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x18001168c  mov     [rsp+1B8h+var_190], rax
0x180011691  mov     dword ptr [rsp+1B8h+var_198], 73h ; 's'
0x180011699  jmp     loc_1800119AD
0x18001169e  mov     rcx, [rsp+1B8h+var_160]
0x1800116a3  mov     rax, [rcx]
0x1800116a6  lea     r8, [rsp+1B8h+var_150]
0x1800116ab  cmp     qword ptr [rsp+1B8h+var_140+8], 7
0x1800116b4  cmova   r8, qword ptr [rsp+1B8h+var_150]
0x1800116ba  mov     [rsp+1B8h+var_180], r15
0x1800116bf  lea     rdx, [rsp+1B8h+var_168]
0x1800116c4  mov     [rsp+1B8h+var_188], rdx
0x1800116c9  lea     rdx, [rsp+1B8h+var_50]
0x1800116d1  mov     [rsp+1B8h+var_190], rdx
0x1800116d6  mov     [rsp+1B8h+var_198], r15
0x1800116db  mov     r9, r14
0x1800116de  lea     rdx, aPut; "PUT"
0x1800116e5  mov     rax, [rax+18h]
0x1800116e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ee  mov     ebx, eax
0x1800116f0  test    eax, eax
0x1800116f2  jns     short loc_18001171A
0x1800116f4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800116fb  jz      loc_1800119BD
0x180011701  lea     rax, aChrPmdmtranspo; "CHR(pMdmTransport->SendRequestToCommand"...
0x180011708  mov     [rsp+1B8h+var_190], rax
0x18001170d  mov     dword ptr [rsp+1B8h+var_198], 7Bh ; '{'
0x180011715  jmp     loc_1800119AD
0x18001171a  mov     eax, [rsp+1B8h+var_168]
0x18001171e  test    rsi, rsi
0x180011721  jz      short loc_180011725
0x180011723  mov     [rsi], eax
0x180011725  add     eax, 0FFFFFF38h
0x18001172a  cmp     eax, 63h ; 'c'
0x18001172d  jbe     short loc_18001175A
0x18001172f  mov     ebx, 80004005h
0x180011734  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001173b  jz      loc_1800119BD
0x180011741  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x180011748  mov     [rsp+1B8h+var_190], rax
0x18001174d  mov     dword ptr [rsp+1B8h+var_198], 85h
0x180011755  jmp     loc_1800119AD
0x18001175a  cmp     qword ptr [rsp+1B8h+var_60], r15
0x180011762  jbe     short loc_1800117A0
0x180011764  lea     rdx, [rsp+1B8h+var_70]
0x18001176c  mov     ecx, [rdi+4]
0x18001176f  call    ?SetCommandChannelHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetCommandChannelHash(MdmDeviceContext,std::wstring const &)
0x180011774  mov     ebx, eax
0x180011776  test    eax, eax
0x180011778  jns     short loc_1800117A0
0x18001177a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011781  jz      loc_1800119BD
0x180011787  lea     rax, aChrMdmsettings_9; "CHR(MdmSettings::SetCommandChannelHash("...
0x18001178e  mov     [rsp+1B8h+var_190], rax
0x180011793  mov     dword ptr [rsp+1B8h+var_198], 8Bh
0x18001179b  jmp     loc_1800119AD
0x1800117a0  cmp     qword ptr [rsp+1B8h+var_80], r15
0x1800117a8  jbe     short loc_1800117E6
0x1800117aa  lea     rdx, [rsp+1B8h+var_90]
0x1800117b2  mov     ecx, [rdi+4]
0x1800117b5  call    ?SetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetMobileNetworksHash(MdmDeviceContext,std::wstring const &)
0x1800117ba  mov     ebx, eax
0x1800117bc  test    eax, eax
0x1800117be  jns     short loc_1800117E6
0x1800117c0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800117c7  jz      loc_1800119BD
0x1800117cd  lea     rax, aChrMdmsettings_23; "CHR(MdmSettings::SetMobileNetworksHash("...
0x1800117d4  mov     [rsp+1B8h+var_190], rax
0x1800117d9  mov     dword ptr [rsp+1B8h+var_198], 90h
0x1800117e1  jmp     loc_1800119AD
0x1800117e6  cmp     qword ptr [rsp+1B8h+var_A0], r15
0x1800117ee  jbe     short loc_18001182C
0x1800117f0  lea     rdx, [rsp+1B8h+var_B0]
0x1800117f8  mov     ecx, [rdi+4]
0x1800117fb  call    ?SetDeviceInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetDeviceInfoHash(MdmDeviceContext,std::wstring const &)
0x180011800  mov     ebx, eax
0x180011802  test    eax, eax
0x180011804  jns     short loc_18001182C
0x180011806  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001180d  jz      loc_1800119BD
0x180011813  lea     rax, aChrMdmsettings_25; "CHR(MdmSettings::SetDeviceInfoHash(pPar"...
0x18001181a  mov     [rsp+1B8h+var_190], rax
0x18001181f  mov     dword ptr [rsp+1B8h+var_198], 95h
0x180011827  jmp     loc_1800119AD
0x18001182c  cmp     qword ptr [rsp+1B8h+var_C0], r15
0x180011834  jbe     short loc_180011872
0x180011836  lea     rdx, [rsp+1B8h+var_D0]
0x18001183e  mov     ecx, [rdi+4]
0x180011841  call    ?SetHardwareInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetHardwareInfoHash(MdmDeviceContext,std::wstring const &)
0x180011846  mov     ebx, eax
0x180011848  test    eax, eax
0x18001184a  jns     short loc_180011872
0x18001184c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011853  jz      loc_1800119BD
0x180011859  lea     rax, aChrMdmsettings; "CHR(MdmSettings::SetHardwareInfoHash(pP"...
0x180011860  mov     [rsp+1B8h+var_190], rax
0x180011865  mov     dword ptr [rsp+1B8h+var_198], 9Ah
0x18001186d  jmp     loc_1800119AD
0x180011872  cmp     qword ptr [rsp+1B8h+var_E0], r15
0x18001187a  jbe     short loc_1800118B8
0x18001187c  lea     rdx, [rsp+1B8h+var_F0]
0x180011884  mov     ecx, [rdi+4]
0x180011887  call    ?SetStorageInfoHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetStorageInfoHash(MdmDeviceContext,std::wstring const &)
0x18001188c  mov     ebx, eax
0x18001188e  test    eax, eax
0x180011890  jns     short loc_1800118B8
0x180011892  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011899  jz      loc_1800119BD
0x18001189f  lea     rax, aChrMdmsettings_3; "CHR(MdmSettings::SetStorageInfoHash(pPa"...
0x1800118a6  mov     [rsp+1B8h+var_190], rax
0x1800118ab  mov     dword ptr [rsp+1B8h+var_198], 9Fh
0x1800118b3  jmp     loc_1800119AD
0x1800118b8  cmp     qword ptr [rsp+1B8h+var_100], r15
0x1800118c0  jbe     short loc_1800118FE
0x1800118c2  lea     rdx, [rsp+1B8h+var_110]
0x1800118ca  mov     ecx, [rdi+4]
0x1800118cd  call    ?SetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetProtectionStateHash(MdmDeviceContext,std::wstring const &)
0x1800118d2  mov     ebx, eax
0x1800118d4  test    eax, eax
0x1800118d6  jns     short loc_1800118FE
0x1800118d8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800118df  jz      loc_1800119BD
0x1800118e5  lea     rax, aChrMdmsettings_6; "CHR(MdmSettings::SetProtectionStateHash"...
0x1800118ec  mov     [rsp+1B8h+var_190], rax
0x1800118f1  mov     dword ptr [rsp+1B8h+var_198], 0A4h
0x1800118f9  jmp     loc_1800119AD
0x1800118fe  cmp     qword ptr [rsp+1B8h+var_120], r15
0x180011906  jbe     short loc_180011941
0x180011908  lea     rdx, [rsp+1B8h+var_130]
0x180011910  mov     ecx, [rdi+4]
0x180011913  call    ?SetConnectedAccountsHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::SetConnectedAccountsHash(MdmDeviceContext,std::wstring const &)
0x180011918  mov     ebx, eax
0x18001191a  test    eax, eax
0x18001191c  jns     short loc_180011941
0x18001191e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011925  jz      loc_1800119BD
0x18001192b  lea     rax, aChrMdmsettings_8; "CHR(MdmSettings::SetConnectedAccountsHa"...
0x180011932  mov     [rsp+1B8h+var_190], rax
0x180011937  mov     dword ptr [rsp+1B8h+var_198], 0A9h
0x18001193f  jmp     short loc_1800119AD
0x180011941  cmp     [rsp+1B8h+var_164], r15d
0x180011946  jz      short loc_180011982
0x180011948  lea     rcx, [rsp+1B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001194d  call    cs:__imp_GetSystemTimeAsFileTime
0x180011953  mov     rcx, qword ptr [rsp+1B8h+SystemTimeAsFileTime.dwLowDateTime]; unsigned __int64
0x180011958  call    ?SetProtectionSessionLastSent@MdmSettings@@SAJ_K@Z; MdmSettings::SetProtectionSessionLastSent(unsigned __int64)
0x18001195d  mov     ebx, eax
0x18001195f  test    eax, eax
0x180011961  jns     short loc_180011982
0x180011963  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001196a  jz      short loc_1800119BD
0x18001196c  lea     rax, aChrMdmsettings_15; "CHR(MdmSettings::SetProtectionSessionLa"...
0x180011973  mov     [rsp+1B8h+var_190], rax
0x180011978  mov     dword ptr [rsp+1B8h+var_198], 0AFh
0x180011980  jmp     short loc_1800119AD
0x180011982  mov     ecx, [rdi+4]
0x180011985  call    ?SetRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@H@Z; MdmSettings::SetRegisteredWithService(MdmDeviceContext,int)
0x18001198a  mov     ebx, eax
0x18001198c  test    eax, eax
0x18001198e  jns     short loc_1800119BD
0x180011990  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011997  jz      short loc_1800119BD
0x180011999  lea     rax, aChrMdmsettings_4; "CHR(MdmSettings::SetRegisteredWithServi"...
0x1800119a0  mov     [rsp+1B8h+var_190], rax
0x1800119a5  mov     dword ptr [rsp+1B8h+var_198], 0B3h
0x1800119ad  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800119b4  mov     r8d, ebx
0x1800119b7  call    McTemplateU0dsqs_EventWriteTransfer
0x1800119bc  nop
0x1800119bd  lea     rcx, [rsp+1B8h+var_150]
0x1800119c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800119c7  nop
0x1800119c8  mov     rcx, [rsp+1B8h+var_160]
0x1800119cd  test    rcx, rcx
0x1800119d0  jz      short loc_1800119DF
0x1800119d2  mov     rax, [rcx]
0x1800119d5  mov     rax, [rax+10h]
0x1800119d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119de  nop
0x1800119df  lea     rcx, [rsp+1B8h+var_130]
0x1800119e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800119ec  nop
0x1800119ed  lea     rcx, [rsp+1B8h+var_110]
0x1800119f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800119fa  nop
0x1800119fb  lea     rcx, [rsp+1B8h+var_F0]
0x180011a03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011a08  nop
0x180011a09  lea     rcx, [rsp+1B8h+var_D0]
0x180011a11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011a16  nop
  ... truncated ...
```
