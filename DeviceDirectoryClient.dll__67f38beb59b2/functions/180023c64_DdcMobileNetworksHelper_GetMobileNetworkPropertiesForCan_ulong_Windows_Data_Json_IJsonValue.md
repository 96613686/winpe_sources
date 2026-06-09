# DdcMobileNetworksHelper::GetMobileNetworkPropertiesForCan(ulong,Windows::Data::Json::IJsonValue * *)

- ea: `0x180023c64`
- end: `0x180023f85`
- name: `?GetMobileNetworkPropertiesForCan@DdcMobileNetworksHelper@@CAJKPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `801`
- prototype: `__int64 __fastcall(unsigned int, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023f8c`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800036e8`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x18001bbe8`
- `0x180022240`
- `0x180023c64`
- `0x18002439c`

## string_xrefs

- `0x180023f39`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmobilenetworkshelper.cpp`
- `0x180023d78`: `CHR(QueryWnfState(dwCan == 0 ? &WNF_CELL_CONFIGURED_LINES_CAN0 : &WNF_CELL_CONFIGURED_LINES_CAN1, (PVOID)&canConfiguration, &dwSize))`
- `0x180023f25`: `CHR(CreateMobileNetworkPropertiesForCanJsonValue( &canConfiguration, pDeviceInfo, pPhoneNumber, pHomeOperatorInfo, pRilSystemType, pwszBillingOperatorId, ppJsonValue))`

## pseudocode

```c
__int64 __fastcall DdcMobileNetworksHelper::GetMobileNetworkPropertiesForCan(
        unsigned int a1,
        struct Windows::Data::Json::IJsonValue **a2)
{
  struct Windows::Data::Json::IJsonValue **v2; // r14
  int v4; // edx
  int v5; // ecx
  int CanJsonValue; // edi
  const struct _WNF_STATE_NAME *v7; // rcx
  int v8; // edx
  int v9; // ecx
  const unsigned __int16 *v10; // rsi
  const struct _WNF_STATE_NAME *v11; // rcx
  const WCHAR *v12; // r12
  const struct _WNF_STATE_NAME *v13; // rcx
  const WCHAR *v14; // r13
  const struct _WNF_STATE_NAME *v15; // rcx
  int v16; // eax
  struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *v17; // rcx
  const struct _WNF_STATE_NAME *v18; // rcx
  __int64 v19; // rcx
  enum RILSYSTEMTYPE *v20; // rdi
  struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *v21; // r9
  int v22; // edx
  int v23; // ecx
  unsigned int v25; // [rsp+40h] [rbp-298h] BYREF
  int v26; // [rsp+44h] [rbp-294h] BYREF
  const unsigned __int16 *v27; // [rsp+48h] [rbp-290h]
  struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *v28; // [rsp+50h] [rbp-288h]
  struct Windows::Data::Json::IJsonValue **v29; // [rsp+58h] [rbp-280h]
  enum RILSYSTEMTYPE *v30; // [rsp+60h] [rbp-278h]
  const WCHAR *v31; // [rsp+68h] [rbp-270h]
  const WCHAR *v32; // [rsp+70h] [rbp-268h]
  struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *v33; // [rsp+78h] [rbp-260h]
  _BYTE v34[32]; // [rsp+80h] [rbp-258h] BYREF
  _BYTE v35[64]; // [rsp+A0h] [rbp-238h] BYREF
  _BYTE v36[80]; // [rsp+E0h] [rbp-1F8h] BYREF
  _BYTE v37[128]; // [rsp+130h] [rbp-1A8h] BYREF
  _BYTE v38[240]; // [rsp+1B0h] [rbp-128h] BYREF

  v2 = a2;
  v29 = a2;
  memset_0(v37, 0, 0x74u);
  memset_0(v38, 0, sizeof(v38));
  memset_0(v35, 0, sizeof(v35));
  memset_0(v36, 0, 0x44u);
  v26 = 0;
  v25 = 0;
  std::wstring::wstring((__int64)v34);
  if ( a1 < 2 )
  {
    v25 = 116;
    v7 = (const struct _WNF_STATE_NAME *)&WNF_CELL_CONFIGURED_LINES_CAN0;
    if ( a1 )
      v7 = &WNF_CELL_CONFIGURED_LINES_CAN1;
    CanJsonValue = DdcMobileNetworksHelper::QueryWnfState(v7, v37, &v25);
    if ( CanJsonValue >= 0 )
    {
      v10 = 0;
      v27 = 0;
      v25 = 240;
      v11 = (const struct _WNF_STATE_NAME *)&WNF_CELL_DEVICE_INFO_CAN0;
      if ( a1 )
        v11 = &WNF_CELL_DEVICE_INFO_CAN1;
      v12 = (const WCHAR *)v38;
      if ( (int)DdcMobileNetworksHelper::QueryWnfState(v11, v38, &v25) < 0 )
        v12 = 0;
      v31 = v12;
      v25 = 64;
      v13 = (const struct _WNF_STATE_NAME *)&WNF_CELL_PHONE_NUMBER_CAN0;
      if ( a1 )
        v13 = &WNF_CELL_PHONE_NUMBER_CAN1;
      v14 = (const WCHAR *)v35;
      if ( (int)DdcMobileNetworksHelper::QueryWnfState(v13, v35, &v25) < 0 )
        v14 = 0;
      v32 = v14;
      v25 = 68;
      v15 = (const struct _WNF_STATE_NAME *)&WNF_CELL_HOME_OPERATOR_CAN0;
      if ( a1 )
        v15 = &WNF_CELL_HOME_OPERATOR_CAN1;
      v16 = DdcMobileNetworksHelper::QueryWnfState(v15, v36, &v25);
      v17 = (struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *)v36;
      if ( v16 < 0 )
        v17 = 0;
      v28 = v17;
      v33 = v17;
      v25 = 4;
      v18 = (const struct _WNF_STATE_NAME *)&WNF_CELL_SYSTEM_TYPE_CAN0;
      if ( a1 )
        v18 = &WNF_CELL_SYSTEM_TYPE_CAN1;
      v20 = (enum RILSYSTEMTYPE *)&v26;
      if ( (int)DdcMobileNetworksHelper::QueryWnfState(v18, &v26, &v25) < 0 )
        v20 = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v30 = v20;
        if ( (int)DdcRegistry::GetStringValue(v19, L"SOFTWARE\\Microsoft\\Zune\\Settings", L"CurrentMOID", (__int64)v34) >= 0 )
        {
          v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          v27 = v10;
        }
        v21 = v28;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          v10 = v27;
          v2 = v29;
          v20 = v30;
          v12 = v31;
          v14 = v32;
          v21 = v33;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180023ED6);
        }
      }
      CanJsonValue = DdcMobileNetworksHelper::CreateMobileNetworkPropertiesForCanJsonValue(
                       (struct WNF_CELL_CAN_CONFIGURATION_TYPE *)v37,
                       v12,
                       v14,
                       v21,
                       v20,
                       v10,
                       v2);
      if ( CanJsonValue < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v23,
          v22,
          CanJsonValue,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
          160,
          "CHR(CreateMobileNetworkPropertiesForCanJsonValue( &canConfiguration, pDeviceInfo, pPhoneNumber, pHomeOperatorI"
          "nfo, pRilSystemType, pwszBillingOperatorId, ppJsonValue))");
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        CanJsonValue,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
        110,
        "CHR(QueryWnfState(dwCan == 0 ? &WNF_CELL_CONFIGURED_LINES_CAN0 : &WNF_CELL_CONFIGURED_LINES_CAN1, (PVOID)&canCon"
        "figuration, &dwSize))");
    }
  }
  else
  {
    CanJsonValue = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
        104,
        "CBR(dwCan == 0 || dwCan == 1)");
  }
  std::wstring::_Tidy_deallocate((__int64)v34);
  return (unsigned int)CanJsonValue;
}

```

## disassembly

```asm
0x180023c64  mov     [rsp+arg_0], rbx
0x180023c69  mov     [rsp+arg_10], rsi
0x180023c6e  push    rdi
0x180023c6f  push    r12
0x180023c71  push    r13
0x180023c73  push    r14
0x180023c75  push    r15
0x180023c77  sub     rsp, 2B0h
0x180023c7e  mov     rax, cs:__security_cookie
0x180023c85  xor     rax, rsp
0x180023c88  mov     [rsp+2D8h+var_38], rax
0x180023c90  mov     r14, rdx
0x180023c93  mov     r15d, ecx
0x180023c96  mov     [rsp+2D8h+var_280], rdx
0x180023c9b  mov     edi, 74h ; 't'
0x180023ca0  mov     r8d, edi; Size
0x180023ca3  xor     edx, edx; Val
0x180023ca5  lea     rcx, [rsp+2D8h+var_1A8]; void *
0x180023cad  call    memset_0
0x180023cb2  lea     r12d, [rdi+7Ch]
0x180023cb6  mov     r8d, r12d; Size
0x180023cb9  xor     edx, edx; Val
0x180023cbb  lea     rcx, [rsp+2D8h+var_128]; void *
0x180023cc3  call    memset_0
0x180023cc8  lea     r13d, [rdi-34h]
0x180023ccc  mov     r8d, r13d; Size
0x180023ccf  xor     edx, edx; Val
0x180023cd1  lea     rcx, [rsp+2D8h+var_238]; void *
0x180023cd9  call    memset_0
0x180023cde  xor     edx, edx; Val
0x180023ce0  lea     r8d, [rdi-30h]; Size
0x180023ce4  lea     rcx, [rsp+2D8h+var_1F8]; void *
0x180023cec  call    memset_0
0x180023cf1  xor     ebx, ebx
0x180023cf3  mov     [rsp+2D8h+var_294], ebx
0x180023cf7  mov     [rsp+2D8h+var_298], ebx
0x180023cfb  lea     rcx, [rsp+2D8h+var_258]
0x180023d03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023d08  nop
0x180023d09  cmp     r15d, 2
0x180023d0d  jb      short loc_180023D3A
0x180023d0f  mov     edi, 80070057h
0x180023d14  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180023d1b  jz      loc_180023F49
0x180023d21  lea     rax, aCbrDwcan0Dwcan; "CBR(dwCan == 0 || dwCan == 1)"
0x180023d28  mov     [rsp+2D8h+var_2B0], rax
0x180023d2d  mov     dword ptr [rsp+2D8h+var_2B8], 68h ; 'h'
0x180023d35  jmp     loc_180023F39
0x180023d3a  mov     [rsp+2D8h+var_298], edi
0x180023d3e  lea     rax, WNF_CELL_CONFIGURED_LINES_CAN1
0x180023d45  lea     rcx, WNF_CELL_CONFIGURED_LINES_CAN0
0x180023d4c  test    r15d, r15d
0x180023d4f  cmovnz  rcx, rax; struct _WNF_STATE_NAME *
0x180023d53  lea     r8, [rsp+2D8h+var_298]; unsigned int *
0x180023d58  lea     rdx, [rsp+2D8h+var_1A8]; void *
0x180023d60  call    ?QueryWnfState@DdcMobileNetworksHelper@@CAJPEBU_WNF_STATE_NAME@@PEAXPEAK@Z; DdcMobileNetworksHelper::QueryWnfState(_WNF_STATE_NAME const *,void *,ulong *)
0x180023d65  mov     edi, eax
0x180023d67  test    eax, eax
0x180023d69  jns     short loc_180023D91
0x180023d6b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180023d72  jz      loc_180023F49
0x180023d78  lea     rax, aChrQuerywnfsta; "CHR(QueryWnfState(dwCan == 0 ? &WNF_CEL"...
0x180023d7f  mov     [rsp+2D8h+var_2B0], rax
0x180023d84  mov     dword ptr [rsp+2D8h+var_2B8], 6Eh ; 'n'
0x180023d8c  jmp     loc_180023F39
0x180023d91  mov     rsi, rbx
0x180023d94  mov     [rsp+2D8h+var_290], rbx
0x180023d99  mov     [rsp+2D8h+var_298], r12d
0x180023d9e  lea     rax, WNF_CELL_DEVICE_INFO_CAN1
0x180023da5  lea     rcx, WNF_CELL_DEVICE_INFO_CAN0
0x180023dac  test    r15d, r15d
0x180023daf  cmovnz  rcx, rax; struct _WNF_STATE_NAME *
0x180023db3  lea     r8, [rsp+2D8h+var_298]; unsigned int *
0x180023db8  lea     rdx, [rsp+2D8h+var_128]; void *
0x180023dc0  call    ?QueryWnfState@DdcMobileNetworksHelper@@CAJPEBU_WNF_STATE_NAME@@PEAXPEAK@Z; DdcMobileNetworksHelper::QueryWnfState(_WNF_STATE_NAME const *,void *,ulong *)
0x180023dc5  lea     r12, [rsp+2D8h+var_128]
0x180023dcd  test    eax, eax
0x180023dcf  cmovs   r12, rbx
0x180023dd3  mov     [rsp+2D8h+var_270], r12
0x180023dd8  mov     [rsp+2D8h+var_298], r13d
0x180023ddd  lea     rax, WNF_CELL_PHONE_NUMBER_CAN1
0x180023de4  lea     rcx, WNF_CELL_PHONE_NUMBER_CAN0
0x180023deb  test    r15d, r15d
0x180023dee  cmovnz  rcx, rax; struct _WNF_STATE_NAME *
0x180023df2  lea     r8, [rsp+2D8h+var_298]; unsigned int *
0x180023df7  lea     rdx, [rsp+2D8h+var_238]; void *
0x180023dff  call    ?QueryWnfState@DdcMobileNetworksHelper@@CAJPEBU_WNF_STATE_NAME@@PEAXPEAK@Z; DdcMobileNetworksHelper::QueryWnfState(_WNF_STATE_NAME const *,void *,ulong *)
0x180023e04  lea     r13, [rsp+2D8h+var_238]
0x180023e0c  test    eax, eax
0x180023e0e  cmovs   r13, rbx
0x180023e12  mov     [rsp+2D8h+var_268], r13
0x180023e17  mov     [rsp+2D8h+var_298], 44h ; 'D'
0x180023e1f  lea     rax, WNF_CELL_HOME_OPERATOR_CAN1
0x180023e26  lea     rcx, WNF_CELL_HOME_OPERATOR_CAN0
0x180023e2d  test    r15d, r15d
0x180023e30  cmovnz  rcx, rax; struct _WNF_STATE_NAME *
0x180023e34  lea     r8, [rsp+2D8h+var_298]; unsigned int *
0x180023e39  lea     rdx, [rsp+2D8h+var_1F8]; void *
0x180023e41  call    ?QueryWnfState@DdcMobileNetworksHelper@@CAJPEBU_WNF_STATE_NAME@@PEAXPEAK@Z; DdcMobileNetworksHelper::QueryWnfState(_WNF_STATE_NAME const *,void *,ulong *)
0x180023e46  lea     rcx, [rsp+2D8h+var_1F8]
0x180023e4e  test    eax, eax
0x180023e50  cmovs   rcx, rbx
0x180023e54  mov     [rsp+2D8h+var_288], rcx
0x180023e59  mov     [rsp+2D8h+var_260], rcx
0x180023e5e  mov     [rsp+2D8h+var_298], 4
0x180023e66  lea     rax, WNF_CELL_SYSTEM_TYPE_CAN1
0x180023e6d  lea     rcx, WNF_CELL_SYSTEM_TYPE_CAN0
0x180023e74  test    r15d, r15d
0x180023e77  cmovnz  rcx, rax; struct _WNF_STATE_NAME *
0x180023e7b  lea     r8, [rsp+2D8h+var_298]; unsigned int *
0x180023e80  lea     rdx, [rsp+2D8h+var_294]; void *
0x180023e85  call    ?QueryWnfState@DdcMobileNetworksHelper@@CAJPEBU_WNF_STATE_NAME@@PEAXPEAK@Z; DdcMobileNetworksHelper::QueryWnfState(_WNF_STATE_NAME const *,void *,ulong *)
0x180023e8a  nop
0x180023e8b  lea     rdi, [rsp+2D8h+var_294]
0x180023e90  test    eax, eax
0x180023e92  cmovs   rdi, rbx
0x180023e96  mov     [rsp+2D8h+var_278], rdi
0x180023e9b  lea     r9, [rsp+2D8h+var_258]
0x180023ea3  lea     r8, aCurrentmoid; "CurrentMOID"
0x180023eaa  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Zune\\Settings"
0x180023eb1  call    ?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180023eb6  test    eax, eax
0x180023eb8  js      short loc_180023ECF
0x180023eba  lea     rcx, [rsp+2D8h+var_258]
0x180023ec2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023ec7  mov     rsi, rax
0x180023eca  mov     [rsp+2D8h+var_290], rax
0x180023ecf  mov     r9, [rsp+2D8h+var_288]
0x180023ed4  jmp     short loc_180023EF4
0x180023ed6  mov     rsi, [rsp+2D8h+var_290]
0x180023edb  mov     r14, [rsp+2D8h+var_280]
0x180023ee0  mov     rdi, [rsp+2D8h+var_278]
0x180023ee5  mov     r12, [rsp+2D8h+var_270]
0x180023eea  mov     r13, [rsp+2D8h+var_268]
0x180023eef  mov     r9, [rsp+2D8h+var_260]; struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *
0x180023ef4  mov     [rsp+2D8h+var_2A8], r14; struct Windows::Data::Json::IJsonValue **
0x180023ef9  mov     [rsp+2D8h+var_2B0], rsi; unsigned __int16 *
0x180023efe  mov     [rsp+2D8h+var_2B8], rdi; enum RILSYSTEMTYPE *
0x180023f03  mov     r8, r13; struct WNF_CELL_PHONE_NUMBER_TYPE *
0x180023f06  mov     rdx, r12; struct WNF_CELL_DEVICE_INFO_TYPE *
0x180023f09  lea     rcx, [rsp+2D8h+var_1A8]; struct WNF_CELL_CAN_CONFIGURATION_TYPE *
0x180023f11  call    ?CreateMobileNetworkPropertiesForCanJsonValue@DdcMobileNetworksHelper@@CAJPEAUWNF_CELL_CAN_CONFIGURATION_TYPE@@PEAUWNF_CELL_DEVICE_INFO_TYPE@@PEAUWNF_CELL_PHONE_NUMBER_TYPE@@PEAUWNF_CELL_HOME_OPERATOR_INFO_TYPE@@PEAW4RILSYSTEMTYPE@@PEBGPEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcMobileNetworksHelper::CreateMobileNetworkPropertiesForCanJsonValue(WNF_CELL_CAN_CONFIGURATION_TYPE *,WNF_CELL_DEVICE_INFO_TYPE *,WNF_CELL_PHONE_NUMBER_TYPE *,WNF_CELL_HOME_OPERATOR_INFO_TYPE *,RILSYSTEMTYPE *,ushort const *,Windows::Data::Json::IJsonValue * *)
0x180023f16  mov     edi, eax
0x180023f18  test    eax, eax
0x180023f1a  jns     short loc_180023F49
0x180023f1c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180023f23  jz      short loc_180023F49
0x180023f25  lea     rax, aChrCreatemobil; "CHR(CreateMobileNetworkPropertiesForCan"...
0x180023f2c  mov     [rsp+2D8h+var_2B0], rax
0x180023f31  mov     dword ptr [rsp+2D8h+var_2B8], 0A0h
0x180023f39  lea     r9, aOnecoreuapShel_14; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180023f40  mov     r8d, edi
0x180023f43  call    McTemplateU0dsqs_EventWriteTransfer
0x180023f48  nop
0x180023f49  lea     rcx, [rsp+2D8h+var_258]
0x180023f51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023f56  mov     eax, edi
0x180023f58  mov     rcx, [rsp+2D8h+var_38]
0x180023f60  xor     rcx, rsp; StackCookie
0x180023f63  call    __security_check_cookie
0x180023f68  lea     r11, [rsp+2D8h+var_28]
0x180023f70  mov     rbx, [r11+30h]
0x180023f74  mov     rsi, [r11+40h]
0x180023f78  mov     rsp, r11
0x180023f7b  pop     r15
0x180023f7d  pop     r14
0x180023f7f  pop     r13
0x180023f81  pop     r12
0x180023f83  pop     rdi
0x180023f84  retn
```
