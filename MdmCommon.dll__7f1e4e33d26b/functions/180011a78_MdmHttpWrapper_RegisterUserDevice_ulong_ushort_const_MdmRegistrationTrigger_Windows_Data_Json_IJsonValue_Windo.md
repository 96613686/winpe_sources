# MdmHttpWrapper::RegisterUserDevice(ulong *,ushort const *,MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *)

- ea: `0x180011a78`
- end: `0x180011cee`
- name: `?RegisterUserDevice@MdmHttpWrapper@@SAJPEAKPEBGW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@3@Z`
- size: `630`
- prototype: `__int64 __fastcall(_DWORD *, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005450`

## callees

- `0x180001520`
- `0x180002de4`
- `0x180006548`
- `0x18000b88c`
- `0x18000e97c`
- `0x180011a78`
- `0x18001ce60`
- `0x18001f010`

## string_xrefs

- `0x180011c92`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x180011bc8`: `CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))`
- `0x180011c45`: `CHR(pMdmTransport->SendRequestToCommandService( L"PUT", wstrPath.c_str(), pwszTicket, nullptr, wstrRequestBody, &dwHttpStatus, nullptr))`
- `0x180011b15`: `CHR(CreateRegisterUserDeviceRequestBody( eTrigger, pDeviceInfo, pUserInfo, wstrRequestBody))`
- `0x180011b92`: `CHR(MdmSettings::GetRegisterUserDevicePath(wstrPath))`
- `0x180011b3a`: `Software\Microsoft\MdmCommon\Internal`
- `0x180011b33`: `RegisterUserDevicePath`
- `0x180011b75`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180011b61`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterUserDevicePathValueName, pszValue))`

## pseudocode

```c
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
                (__int64)"CHR(((HRESULT)0x80004005L))");
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
            (__int64)"CHR(pMdmTransport->SendRequestToCommandService( L\"PUT\", wstrPath.c_str(), pwszTicket, nullptr, ws"
                     "trRequestBody, &dwHttpStatus, nullptr))");
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
          (__int64)"CHR(CreateHttpRequest(pMdmTransport.GetAddressOf()))");
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
        (__int64)"CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszRegisterUserDevicePathValueName, pszValue))");
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          StringValue,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
          211,
          (__int64)"CHR(MdmSettings::GetRegisterUserDevicePath(wstrPath))");
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
      (__int64)"CHR(CreateRegisterUserDeviceRequestBody( eTrigger, pDeviceInfo, pUserInfo, wstrRequestBody))");
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
0x180011a78  push    rbx
0x180011a7a  push    rsi
0x180011a7b  push    rdi
0x180011a7c  sub     rsp, 0B0h
0x180011a83  mov     rax, cs:__security_cookie
0x180011a8a  xor     rax, rsp
0x180011a8d  mov     [rsp+0C8h+var_28], rax
0x180011a95  mov     r11, r9
0x180011a98  mov     r10d, r8d
0x180011a9b  mov     rsi, rdx
0x180011a9e  mov     rdi, rcx
0x180011aa1  mov     r8, [rsp+0C8h+arg_20]
0x180011aa9  xorps   xmm0, xmm0
0x180011aac  movups  [rsp+0C8h+var_48], xmm0
0x180011ab4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011abc  movdqu  [rsp+0C8h+var_38], xmm1
0x180011ac5  xor     eax, eax
0x180011ac7  mov     word ptr [rsp+0C8h+var_48], ax
0x180011acf  mov     [rsp+0C8h+var_70], rax
0x180011ad4  mov     [rsp+0C8h+var_78], eax
0x180011ad8  movups  [rsp+0C8h+var_68], xmm0
0x180011add  movdqu  [rsp+0C8h+var_58], xmm1
0x180011ae3  mov     word ptr [rsp+0C8h+var_68], ax
0x180011ae8  test    rcx, rcx
0x180011aeb  jz      short loc_180011AEF
0x180011aed  mov     [rcx], eax
0x180011aef  lea     r9, [rsp+0C8h+var_48]
0x180011af7  mov     rdx, r11
0x180011afa  mov     ecx, r10d
0x180011afd  call    ?CreateRegisterUserDeviceRequestBody@MdmHttpWrapper@@CAJW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmHttpWrapper::CreateRegisterUserDeviceRequestBody(MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,std::wstring &)
0x180011b02  mov     ebx, eax
0x180011b04  test    eax, eax
0x180011b06  jns     short loc_180011B2E
0x180011b08  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011b0f  jz      loc_180011CA2
0x180011b15  lea     rax, aChrCreateregis_0; "CHR(CreateRegisterUserDeviceRequestBody"...
0x180011b1c  mov     [rsp+0C8h+var_A0], rax
0x180011b21  mov     dword ptr [rsp+0C8h+var_A8], 0D1h
0x180011b29  jmp     loc_180011C92
0x180011b2e  lea     r9, [rsp+0C8h+var_68]
0x180011b33  lea     r8, aRegisteruserde; "RegisterUserDevicePath"
0x180011b3a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x180011b41  mov     rcx, 0FFFFFFFF80000002h
0x180011b48  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180011b4d  mov     ebx, eax
0x180011b4f  test    eax, eax
0x180011b51  jns     short loc_180011BAB
0x180011b53  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180011b59  test    al, 1
0x180011b5b  jz      loc_180011CA2
0x180011b61  lea     rax, aChrMdmregistry_21; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x180011b68  mov     [rsp+0C8h+var_A0], rax
0x180011b6d  mov     dword ptr [rsp+0C8h+var_A8], 233h
0x180011b75  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011b7c  mov     r8d, ebx
0x180011b7f  call    McTemplateU0dsqs_EventWriteTransfer
0x180011b84  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180011b8a  test    al, 1
0x180011b8c  jz      loc_180011CA2
0x180011b92  lea     rax, aChrMdmsettings_2; "CHR(MdmSettings::GetRegisterUserDeviceP"...
0x180011b99  mov     [rsp+0C8h+var_A0], rax
0x180011b9e  mov     dword ptr [rsp+0C8h+var_A8], 0D3h
0x180011ba6  jmp     loc_180011C92
0x180011bab  lea     rcx, [rsp+0C8h+var_70]; struct IMdmTransport **
0x180011bb0  call    ?CreateHttpRequest@@YAJPEAPEAUIMdmTransport@@@Z; CreateHttpRequest(IMdmTransport * *)
0x180011bb5  mov     ebx, eax
0x180011bb7  test    eax, eax
0x180011bb9  jns     short loc_180011BE1
0x180011bbb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011bc2  jz      loc_180011CA2
0x180011bc8  lea     rax, aChrCreatehttpr; "CHR(CreateHttpRequest(pMdmTransport.Get"...
0x180011bcf  mov     [rsp+0C8h+var_A0], rax
0x180011bd4  mov     dword ptr [rsp+0C8h+var_A8], 0D5h
0x180011bdc  jmp     loc_180011C92
0x180011be1  mov     rcx, [rsp+0C8h+var_70]
0x180011be6  mov     rax, [rcx]
0x180011be9  lea     r8, [rsp+0C8h+var_68]
0x180011bee  cmp     qword ptr [rsp+0C8h+var_58+8], 7
0x180011bf4  cmova   r8, qword ptr [rsp+0C8h+var_68]
0x180011bfa  mov     [rsp+0C8h+var_90], 0
0x180011c03  lea     rdx, [rsp+0C8h+var_78]
0x180011c08  mov     [rsp+0C8h+var_98], rdx
0x180011c0d  lea     rdx, [rsp+0C8h+var_48]
0x180011c15  mov     [rsp+0C8h+var_A0], rdx
0x180011c1a  mov     [rsp+0C8h+var_A8], 0
0x180011c23  mov     r9, rsi
0x180011c26  lea     rdx, aPut; "PUT"
0x180011c2d  mov     rax, [rax+18h]
0x180011c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c36  mov     ebx, eax
0x180011c38  test    eax, eax
0x180011c3a  jns     short loc_180011C5B
0x180011c3c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011c43  jz      short loc_180011CA2
0x180011c45  lea     rax, aChrPmdmtranspo; "CHR(pMdmTransport->SendRequestToCommand"...
0x180011c4c  mov     [rsp+0C8h+var_A0], rax
0x180011c51  mov     dword ptr [rsp+0C8h+var_A8], 0DDh
0x180011c59  jmp     short loc_180011C92
0x180011c5b  mov     eax, [rsp+0C8h+var_78]
0x180011c5f  test    rdi, rdi
0x180011c62  jz      short loc_180011C66
0x180011c64  mov     [rdi], eax
0x180011c66  add     eax, 0FFFFFF38h
0x180011c6b  cmp     eax, 63h ; 'c'
0x180011c6e  jbe     short loc_180011CA2
0x180011c70  mov     ebx, 80004005h
0x180011c75  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180011c7c  jz      short loc_180011CA2
0x180011c7e  lea     rax, aChrHresult0x80_2; "CHR(((HRESULT)0x80004005L))"
0x180011c85  mov     [rsp+0C8h+var_A0], rax
0x180011c8a  mov     dword ptr [rsp+0C8h+var_A8], 0E7h
0x180011c92  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180011c99  mov     r8d, ebx
0x180011c9c  call    McTemplateU0dsqs_EventWriteTransfer
0x180011ca1  nop
0x180011ca2  lea     rcx, [rsp+0C8h+var_68]
0x180011ca7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011cac  nop
0x180011cad  mov     rcx, [rsp+0C8h+var_70]
0x180011cb2  test    rcx, rcx
0x180011cb5  jz      short loc_180011CC4
0x180011cb7  mov     rax, [rcx]
0x180011cba  mov     rax, [rax+10h]
0x180011cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc3  nop
0x180011cc4  lea     rcx, [rsp+0C8h+var_48]
0x180011ccc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011cd1  mov     eax, ebx
0x180011cd3  mov     rcx, [rsp+0C8h+var_28]
0x180011cdb  xor     rcx, rsp; StackCookie
0x180011cde  call    __security_check_cookie
0x180011ce3  add     rsp, 0B0h
0x180011cea  pop     rdi
0x180011ceb  pop     rsi
0x180011cec  pop     rbx
0x180011ced  retn
```
