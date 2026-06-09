# MdmHttpWrapper::RegisterUserDevice(ulong *,ushort const *,MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *)

- ea: `0x180011e50`
- end: `0x1800120c7`
- name: `?RegisterUserDevice@MdmHttpWrapper@@SAJPEAKPEBGW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@3@Z`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800054a0`

## callees

- `0x180001520`
- `0x180002de8`
- `0x1800065c0`
- `0x18000bb9c`
- `0x18000edc0`
- `0x180011e50`
- `0x18001d4f4`
- `0x18001f010`

## string_xrefs

- `0x18001206a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180011fa0`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x18001201d`: `CHR(pMdmTransport->SendRequestToCommandService( L"PUT", wstrPath.c_str(), pwszTicket, nullptr, wstrRequestBody, &dwHttpStatus, nullptr))`
- `0x180011eed`: `CHR(CreateRegisterUserDeviceRequestBody( eTrigger, pDeviceInfo, pUserInfo, wstrRequestBody))`
- `0x180011f6a`: `CHR(MdmSettings::GetRegisterUserDevicePath(wstrPath))`
- `0x180011f12`: `Software\Microsoft\MdmCommon\Internal`
- `0x180011f0b`: `RegisterUserDevicePath`
- `0x180011f4d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180011f39`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterUserDevicePathValueName, pszValue))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MdmHttpWrapper::RegisterUserDevice(_DWORD *a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  int v7; // edx
  int v8; // ecx
  int StringValue; // ebx
  int v10; // edx
  int v11; // ecx
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  __int128 *v16; // r8
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  int v21; // [rsp+50h] [rbp-78h] BYREF
  struct IMdmTransport *v22; // [rsp+58h] [rbp-70h] BYREF
  __int128 v23; // [rsp+60h] [rbp-68h] BYREF
  __m128i v24; // [rsp+70h] [rbp-58h]
  __int128 v25; // [rsp+80h] [rbp-48h] BYREF
  __m128i si128; // [rsp+90h] [rbp-38h]

  v25 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v25) = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v24 = si128;
  LOWORD(v23) = 0;
  if ( a1 )
    *a1 = 0;
  StringValue = MdmHttpWrapper::CreateRegisterUserDeviceRequestBody(a3, a4, a5, &v25);
  if ( StringValue >= 0 )
  {
    StringValue = MdmRegistry::GetStringValue(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\MdmCommon\\Internal",
                    L"RegisterUserDevicePath",
                    &v23);
    if ( StringValue >= 0 )
    {
      StringValue = CreateHttpRequest(&v22);
      if ( StringValue >= 0 )
      {
        v16 = &v23;
        if ( v24.m128i_i64[1] > 7uLL )
          v16 = (__int128 *)v23;
        StringValue = (*(__int64 (__fastcall **)(struct IMdmTransport *, const wchar_t *, __int128 *, __int64, _QWORD, __int128 *, int *, _QWORD))(*(_QWORD *)v22 + 24LL))(
                        v22,
                        L"PUT",
                        v16,
                        a2,
                        0,
                        &v25,
                        &v21,
                        0);
        if ( StringValue >= 0 )
        {
          v19 = v21;
          if ( a1 )
            *a1 = v21;
          if ( (unsigned int)(v19 - 200) > 0x63 )
          {
            StringValue = -2147467259;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v18,
                v17,
                -2147467259,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
                231,
                "CHR(((HRESULT)0x80004005L))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v18,
            v17,
            StringValue,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
            221,
            "CHR(pMdmTransport->SendRequestToCommandService( L\"PUT\", wstrPath.c_str(), pwszTicket, nullptr, wstrRequest"
            "Body, &dwHttpStatus, nullptr))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v15,
          v14,
          StringValue,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          213,
          "CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        StringValue,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        51,
        "CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterUserDevicePathValueName, pszValue))");
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          StringValue,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          211,
          "CHR(MdmSettings::GetRegisterUserDevicePath(wstrPath))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v8,
      v7,
      StringValue,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      209,
      "CHR(CreateRegisterUserDeviceRequestBody( eTrigger, pDeviceInfo, pUserInfo, wstrRequestBody))");
  }
  std::wstring::~wstring(&v23);
  if ( v22 )
    (*(void (__fastcall **)(struct IMdmTransport *))(*(_QWORD *)v22 + 16LL))(v22);
  std::wstring::~wstring(&v25);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180011e50  push    rbx
0x180011e52  push    rsi
0x180011e53  push    rdi
0x180011e54  sub     rsp, 0B0h
0x180011e5b  mov     rax, cs:__security_cookie
0x180011e62  xor     rax, rsp
0x180011e65  mov     [rsp+0C8h+var_28], rax
0x180011e6d  mov     r11, r9
0x180011e70  mov     r10d, r8d
0x180011e73  mov     rsi, rdx
0x180011e76  mov     rdi, rcx
0x180011e79  mov     r8, [rsp+0C8h+arg_20]
0x180011e81  xorps   xmm0, xmm0
0x180011e84  movups  [rsp+0C8h+var_48], xmm0
0x180011e8c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011e94  movdqu  [rsp+0C8h+var_38], xmm1
0x180011e9d  xor     eax, eax
0x180011e9f  mov     word ptr [rsp+0C8h+var_48], ax
0x180011ea7  mov     [rsp+0C8h+var_70], rax
0x180011eac  mov     [rsp+0C8h+var_78], eax
0x180011eb0  movups  [rsp+0C8h+var_68], xmm0
0x180011eb5  movdqu  [rsp+0C8h+var_58], xmm1
0x180011ebb  mov     word ptr [rsp+0C8h+var_68], ax
0x180011ec0  test    rcx, rcx
0x180011ec3  jz      short loc_180011EC7
0x180011ec5  mov     [rcx], eax
0x180011ec7  lea     r9, [rsp+0C8h+var_48]
0x180011ecf  mov     rdx, r11
0x180011ed2  mov     ecx, r10d
0x180011ed5  call    ?CreateRegisterUserDeviceRequestBody@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpWrapper::CreateRegisterUserDeviceRequestBody(MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,std::wstring &)
0x180011eda  mov     ebx, eax
0x180011edc  test    eax, eax
0x180011ede  jns     short loc_180011F06
0x180011ee0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011ee7  jz      loc_18001207A
0x180011eed  lea     rax, aChrCreateregis_0; "CHR(CreateRegisterUserDeviceRequestBody"...
0x180011ef4  mov     [rsp+0C8h+var_A0], rax
0x180011ef9  mov     dword ptr [rsp+0C8h+var_A8], 0D1h
0x180011f01  jmp     loc_18001206A
0x180011f06  lea     r9, [rsp+0C8h+var_68]
0x180011f0b  lea     r8, aRegisteruserde; "RegisterUserDevicePath"
0x180011f12  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x180011f19  mov     rcx, 0FFFFFFFF80000002h
0x180011f20  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180011f25  mov     ebx, eax
0x180011f27  test    eax, eax
0x180011f29  jns     short loc_180011F83
0x180011f2b  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180011f31  test    al, 1
0x180011f33  jz      loc_18001207A
0x180011f39  lea     rax, aChrMdmregistry_21; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x180011f40  mov     [rsp+0C8h+var_A0], rax
0x180011f45  mov     dword ptr [rsp+0C8h+var_A8], 233h
0x180011f4d  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011f54  mov     r8d, ebx
0x180011f57  call    McTemplateU0dsqs_EventWriteTransfer
0x180011f5c  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180011f62  test    al, 1
0x180011f64  jz      loc_18001207A
0x180011f6a  lea     rax, aChrMdmsettings_2; "CHR(MdmSettings::GetRegisterUserDeviceP"...
0x180011f71  mov     [rsp+0C8h+var_A0], rax
0x180011f76  mov     dword ptr [rsp+0C8h+var_A8], 0D3h
0x180011f7e  jmp     loc_18001206A
0x180011f83  lea     rcx, [rsp+0C8h+var_70]; struct IMdmTransport **
0x180011f88  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180011f8d  mov     ebx, eax
0x180011f8f  test    eax, eax
0x180011f91  jns     short loc_180011FB9
0x180011f93  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011f9a  jz      loc_18001207A
0x180011fa0  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x180011fa7  mov     [rsp+0C8h+var_A0], rax
0x180011fac  mov     dword ptr [rsp+0C8h+var_A8], 0D5h
0x180011fb4  jmp     loc_18001206A
0x180011fb9  mov     rcx, [rsp+0C8h+var_70]
0x180011fbe  mov     rax, [rcx]
0x180011fc1  lea     r8, [rsp+0C8h+var_68]
0x180011fc6  cmp     qword ptr [rsp+0C8h+var_58+8], 7
0x180011fcc  cmova   r8, qword ptr [rsp+0C8h+var_68]
0x180011fd2  mov     [rsp+0C8h+var_90], 0
0x180011fdb  lea     rdx, [rsp+0C8h+var_78]
0x180011fe0  mov     [rsp+0C8h+var_98], rdx
0x180011fe5  lea     rdx, [rsp+0C8h+var_48]
0x180011fed  mov     [rsp+0C8h+var_A0], rdx
0x180011ff2  mov     [rsp+0C8h+var_A8], 0
0x180011ffb  mov     r9, rsi
0x180011ffe  lea     rdx, aPut; "PUT"
0x180012005  mov     rax, [rax+18h]
0x180012009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001200e  mov     ebx, eax
0x180012010  test    eax, eax
0x180012012  jns     short loc_180012033
0x180012014  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001201b  jz      short loc_18001207A
0x18001201d  lea     rax, aChrPmdmtranspo; "CHR(pMdmTransport->SendRequestToCommand"...
0x180012024  mov     [rsp+0C8h+var_A0], rax
0x180012029  mov     dword ptr [rsp+0C8h+var_A8], 0DDh
0x180012031  jmp     short loc_18001206A
0x180012033  mov     eax, [rsp+0C8h+var_78]
0x180012037  test    rdi, rdi
0x18001203a  jz      short loc_18001203E
0x18001203c  mov     [rdi], eax
0x18001203e  add     eax, 0FFFFFF38h
0x180012043  cmp     eax, 63h ; 'c'
0x180012046  jbe     short loc_18001207A
0x180012048  mov     ebx, 80004005h
0x18001204d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012054  jz      short loc_18001207A
0x180012056  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x18001205d  mov     [rsp+0C8h+var_A0], rax
0x180012062  mov     dword ptr [rsp+0C8h+var_A8], 0E7h
0x18001206a  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012071  mov     r8d, ebx
0x180012074  call    McTemplateU0dsqs_EventWriteTransfer
0x180012079  nop
0x18001207a  lea     rcx, [rsp+0C8h+var_68]
0x18001207f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012084  nop
0x180012085  mov     rcx, [rsp+0C8h+var_70]
0x18001208a  test    rcx, rcx
0x18001208d  jz      short loc_18001209C
0x18001208f  mov     rax, [rcx]
0x180012092  mov     rax, [rax+10h]
0x180012096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001209b  nop
0x18001209c  lea     rcx, [rsp+0C8h+var_48]
0x1800120a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800120a9  mov     eax, ebx
0x1800120ab  mov     rcx, [rsp+0C8h+var_28]
0x1800120b3  xor     rcx, rsp; StackCookie
0x1800120b6  call    __security_check_cookie
0x1800120bb  add     rsp, 0B0h
0x1800120c2  pop     rdi
0x1800120c3  pop     rsi
0x1800120c4  pop     rbx
0x1800120c5  retn
```
