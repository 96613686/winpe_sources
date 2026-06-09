# NgcUtils::IsSecureBioEnabled(void)

- ea: `0x180055e5c`
- end: `0x18005607c`
- name: `?IsSecureBioEnabled@NgcUtils@@YA_NXZ`
- size: `544`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `6`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018378`
- `0x180022b70`
- `0x180023a88`
- `0x180023e64`
- `0x180033a80`
- `0x180033f24`

## callees

- `0x18000c688`
- `0x1800134a0`
- `0x180016888`
- `0x180019ce8`
- `0x180021c38`
- `0x1800294e8`
- `0x180029980`
- `0x18002b13c`
- `0x18002c640`
- `0x180037348`
- `0x180055e5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055fc5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055fe5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055fc5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055fe5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055f81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055f81`
- `ntdll!NtQuerySystemInformation` at `0x180055efc`
- `ntdll!NtQuerySystemInformation` at `0x180055efc`
- `tbs!Tbsi_GetDeviceInfo` at `0x180055e83`
- `tbs!Tbsi_GetDeviceInfo` at `0x180055e83`

## string_xrefs

- `0x180055e9a`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180055f13`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180055f49`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall NgcUtils::IsSecureBioEnabled(NgcUtils *this)
{
  int DeviceInfo; // eax
  NTSTATUS v2; // eax
  unsigned int v3; // edx
  int v4; // eax
  NgcUtils *v5; // rcx
  NgcUtils *v7; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  _BYTE v9[4]; // [rsp+30h] [rbp-40h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-3Ch] BYREF
  LPVOID v11; // [rsp+38h] [rbp-38h] BYREF
  __int128 v12; // [rsp+40h] [rbp-30h] BYREF
  __int128 SystemInformation; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v12 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, &v12);
  if ( DeviceInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)DeviceInfo,
      ppv);
  if ( DWORD1(v12) < 2 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&word_1800ADCE6,
        0);
    return 0;
  }
  SystemInformation = 0;
  ReturnLength = 0;
  v2 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, &ReturnLength);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  if ( (SystemInformation & 0x21) != 0x21 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&word_1800ADD16,
        0);
    return 0;
  }
  v9[0] = 0;
  v4 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v9, v3);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_15:
    if ( v9[0] )
      CoUninitialize();
    return 0;
  }
  v11 = 0;
  if ( CoCreateInstance(
         &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
         0,
         1u,
         &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
         &v11) < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800ADCB3,
        0);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v11);
    goto LABEL_15;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v11);
  if ( v9[0] )
    CoUninitialize();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    return 1;
  if ( NgcUtils::IsSDEVTablePresent(v5) || NgcUtils::ExistsSecureFpRegKey(v7) )
    return (unsigned int)NgcUtils::SecureBioRegKeyState() != 0;
  if ( (unsigned int)dword_1800BE0B8 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800ADC8B,
      0);
  return 0;
}

```

## disassembly

```asm
0x180055e5c  push    rbp
0x180055e5e  mov     rbp, rsp
0x180055e61  sub     rsp, 70h
0x180055e65  mov     rax, cs:__security_cookie
0x180055e6c  xor     rax, rsp
0x180055e6f  mov     [rbp+var_10], rax
0x180055e73  xorps   xmm0, xmm0
0x180055e76  movups  [rbp+var_30], xmm0
0x180055e7a  lea     rdx, [rbp+var_30]
0x180055e7e  mov     ecx, 10h
0x180055e83  call    cs:__imp_Tbsi_GetDeviceInfo
0x180055e8a  nop     dword ptr [rax+rax+00h]
0x180055e8f  mov     rcx, [rbp+8]; this
0x180055e93  test    eax, eax
0x180055e95  jns     short loc_180055EAB
0x180055e97  mov     r9d, eax; char *
0x180055e9a  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180055ea1  mov     edx, 17Ch; void *
0x180055ea6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180055eab  cmp     dword ptr [rbp+var_30+4], 2
0x180055eaf  jnb     short loc_180055EDB
0x180055eb1  mov     eax, cs:dword_1800BE0B8
0x180055eb7  cmp     eax, 4
0x180055eba  jbe     loc_180056067
0x180055ec0  xor     r8d, r8d
0x180055ec3  lea     rdx, word_1800ADCE6
0x180055eca  lea     rcx, dword_1800BE0B8
0x180055ed1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180055ed6  jmp     loc_180056067
0x180055edb  xorps   xmm0, xmm0
0x180055ede  movups  [rbp+SystemInformation], xmm0
0x180055ee2  mov     [rbp+ReturnLength], 0
0x180055ee9  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180055eed  mov     r8d, 10h; SystemInformationLength
0x180055ef3  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180055ef7  mov     ecx, 0A5h; SystemInformationClass
0x180055efc  call    cs:__imp_NtQuerySystemInformation
0x180055f03  nop     dword ptr [rax+rax+00h]
0x180055f08  mov     rcx, [rbp+8]; this
0x180055f0c  test    eax, eax
0x180055f0e  jns     short loc_180055F24
0x180055f10  mov     r9d, eax; char *
0x180055f13  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180055f1a  mov     edx, 18Dh; void *
0x180055f1f  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180055f24  mov     al, byte ptr [rbp+SystemInformation]
0x180055f27  and     al, 21h
0x180055f29  cmp     al, 21h ; '!'
0x180055f2b  jnz     loc_180056046
0x180055f31  mov     [rbp+var_40], 0
0x180055f35  lea     rcx, [rbp+var_40]; this
0x180055f39  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180055f3e  mov     rcx, [rbp+8]; this
0x180055f42  test    eax, eax
0x180055f44  jns     short loc_180055F5C
0x180055f46  mov     r9d, eax; char *
0x180055f49  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180055f50  mov     edx, 19Dh; void *
0x180055f55  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180055f5a  jmp     short loc_180055FBB
0x180055f5c  mov     [rbp+var_38], 0
0x180055f64  lea     rax, [rbp+var_38]
0x180055f68  mov     qword ptr [rsp+70h+ppv], rax; ppv
0x180055f6d  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x180055f74  xor     edx, edx; pUnkOuter
0x180055f76  lea     r8d, [rdx+1]; dwClsContext
0x180055f7a  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x180055f81  call    cs:__imp_CoCreateInstance
0x180055f88  nop     dword ptr [rax+rax+00h]
0x180055f8d  test    eax, eax
0x180055f8f  jns     short loc_180055FD6
0x180055f91  mov     eax, cs:dword_1800BE0B8
0x180055f97  cmp     eax, 4
0x180055f9a  jbe     short loc_180055FB2
0x180055f9c  xor     r8d, r8d
0x180055f9f  lea     rdx, byte_1800ADCB3
0x180055fa6  lea     rcx, dword_1800BE0B8
0x180055fad  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180055fb2  lea     rcx, [rbp+var_38]
0x180055fb6  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180055fbb  cmp     [rbp+var_40], 0
0x180055fbf  jz      loc_180056067
0x180055fc5  call    cs:__imp_CoUninitialize
0x180055fcc  nop     dword ptr [rax+rax+00h]
0x180055fd1  jmp     loc_180056067
0x180055fd6  lea     rcx, [rbp+var_38]
0x180055fda  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180055fdf  cmp     [rbp+var_40], 0
0x180055fe3  jz      short loc_180055FF1
0x180055fe5  call    cs:__imp_CoUninitialize
0x180055fec  nop     dword ptr [rax+rax+00h]
0x180055ff1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180055ff8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180055ffd  test    al, al
0x180055fff  jz      short loc_180056005
0x180056001  mov     al, 1
0x180056003  jmp     short loc_180056069
0x180056005  call    ?IsSDEVTablePresent@NgcUtils@@YA_NXZ; NgcUtils::IsSDEVTablePresent(void)
0x18005600a  test    al, al
0x18005600c  jnz     short loc_18005603A
0x18005600e  call    ?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ; NgcUtils::ExistsSecureFpRegKey(void)
0x180056013  test    al, al
0x180056015  jnz     short loc_18005603A
0x180056017  mov     eax, cs:dword_1800BE0B8
0x18005601d  cmp     eax, 4
0x180056020  jbe     short loc_180056067
0x180056022  xor     r8d, r8d
0x180056025  lea     rdx, byte_1800ADC8B
0x18005602c  lea     rcx, dword_1800BE0B8
0x180056033  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180056038  jmp     short loc_180056067
0x18005603a  call    ?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ; NgcUtils::SecureBioRegKeyState(void)
0x18005603f  test    eax, eax
0x180056041  setnz   al
0x180056044  jmp     short loc_180056069
0x180056046  mov     eax, cs:dword_1800BE0B8
0x18005604c  cmp     eax, 4
0x18005604f  jbe     short loc_180056067
0x180056051  xor     r8d, r8d
0x180056054  lea     rdx, word_1800ADD16
0x18005605b  lea     rcx, dword_1800BE0B8
0x180056062  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180056067  xor     al, al
0x180056069  mov     rcx, [rbp+var_10]
0x18005606d  xor     rcx, rsp; StackCookie
0x180056070  call    __security_check_cookie
0x180056075  add     rsp, 70h
0x180056079  pop     rbp
0x18005607a  retn
```
