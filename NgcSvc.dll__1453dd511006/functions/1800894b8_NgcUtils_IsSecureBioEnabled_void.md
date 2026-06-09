# NgcUtils::IsSecureBioEnabled(void)

- ea: `0x1800894b8`
- end: `0x1800896b9`
- name: `?IsSecureBioEnabled@NgcUtils@@YA_NXZ`
- size: `513`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007990`

## callees

- `0x180029f0c`
- `0x18003601c`
- `0x1800471f4`
- `0x180047228`
- `0x1800523d4`
- `0x1800598c8`
- `0x18005cee0`
- `0x1800726a0`
- `0x18008915c`
- `0x1800894b8`
- `0x1800898dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800895d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800895d1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008960f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180089629`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008960f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180089629`
- `ntdll!NtQuerySystemInformation` at `0x180089552`
- `ntdll!NtQuerySystemInformation` at `0x180089552`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800894df`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800894df`

## string_xrefs

- `0x1800894f0`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180089563`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180089599`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

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
    if ( (unsigned int)dword_180122070 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180106BB1,
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
    if ( (unsigned int)dword_180122070 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&unk_180106B88,
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
    if ( (unsigned int)dword_180122070 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180106B55,
        0);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v11);
    goto LABEL_15;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v11);
  if ( v9[0] )
    CoUninitialize();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    return 1;
  if ( NgcUtils::IsSDEVTablePresent(v5) || NgcUtils::ExistsSecureFpRegKey(v7) )
    return (unsigned int)NgcUtils::SecureBioRegKeyState() != 0;
  if ( (unsigned int)dword_180122070 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_180106B2D,
      0);
  return 0;
}

```

## disassembly

```asm
0x1800894b8  push    rbp
0x1800894ba  mov     rbp, rsp
0x1800894bd  sub     rsp, 70h
0x1800894c1  mov     rax, cs:__security_cookie
0x1800894c8  xor     rax, rsp
0x1800894cb  mov     [rbp+var_10], rax
0x1800894cf  xorps   xmm0, xmm0
0x1800894d2  movups  [rbp+var_30], xmm0
0x1800894d6  lea     rdx, [rbp+var_30]
0x1800894da  mov     ecx, 10h
0x1800894df  call    cs:__imp_Tbsi_GetDeviceInfo
0x1800894e5  mov     rcx, [rbp+8]; this
0x1800894e9  test    eax, eax
0x1800894eb  jns     short loc_180089501
0x1800894ed  mov     r9d, eax; char *
0x1800894f0  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800894f7  mov     edx, 17Ch; void *
0x1800894fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180089501  cmp     dword ptr [rbp+var_30+4], 2
0x180089505  jnb     short loc_180089531
0x180089507  mov     eax, cs:dword_180122070
0x18008950d  cmp     eax, 4
0x180089510  jbe     loc_1800896A5
0x180089516  xor     r8d, r8d
0x180089519  lea     rdx, byte_180106BB1
0x180089520  lea     rcx, dword_180122070
0x180089527  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18008952c  jmp     loc_1800896A5
0x180089531  xorps   xmm0, xmm0
0x180089534  movups  [rbp+SystemInformation], xmm0
0x180089538  mov     [rbp+ReturnLength], 0
0x18008953f  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180089543  mov     r8d, 10h; SystemInformationLength
0x180089549  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18008954d  mov     ecx, 0A5h; SystemInformationClass
0x180089552  call    cs:__imp_NtQuerySystemInformation
0x180089558  mov     rcx, [rbp+8]; this
0x18008955c  test    eax, eax
0x18008955e  jns     short loc_180089574
0x180089560  mov     r9d, eax; char *
0x180089563  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x18008956a  mov     edx, 18Dh; void *
0x18008956f  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180089574  mov     al, byte ptr [rbp+SystemInformation]
0x180089577  and     al, 21h
0x180089579  cmp     al, 21h ; '!'
0x18008957b  jnz     loc_180089684
0x180089581  mov     [rbp+var_40], 0
0x180089585  lea     rcx, [rbp+var_40]; this
0x180089589  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18008958e  mov     rcx, [rbp+8]; this
0x180089592  test    eax, eax
0x180089594  jns     short loc_1800895AC
0x180089596  mov     r9d, eax; char *
0x180089599  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800895a0  mov     edx, 19Dh; void *
0x1800895a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800895aa  jmp     short loc_180089605
0x1800895ac  mov     [rbp+var_38], 0
0x1800895b4  lea     rax, [rbp+var_38]
0x1800895b8  mov     qword ptr [rsp+70h+ppv], rax; ppv
0x1800895bd  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x1800895c4  xor     edx, edx; pUnkOuter
0x1800895c6  lea     r8d, [rdx+1]; dwClsContext
0x1800895ca  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x1800895d1  call    cs:__imp_CoCreateInstance
0x1800895d7  test    eax, eax
0x1800895d9  jns     short loc_18008961A
0x1800895db  mov     eax, cs:dword_180122070
0x1800895e1  cmp     eax, 4
0x1800895e4  jbe     short loc_1800895FC
0x1800895e6  xor     r8d, r8d
0x1800895e9  lea     rdx, byte_180106B55
0x1800895f0  lea     rcx, dword_180122070
0x1800895f7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800895fc  lea     rcx, [rbp+var_38]
0x180089600  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180089605  cmp     [rbp+var_40], 0
0x180089609  jz      loc_1800896A5
0x18008960f  call    cs:__imp_CoUninitialize
0x180089615  jmp     loc_1800896A5
0x18008961a  lea     rcx, [rbp+var_38]
0x18008961e  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180089623  cmp     [rbp+var_40], 0
0x180089627  jz      short loc_18008962F
0x180089629  call    cs:__imp_CoUninitialize
0x18008962f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180089636  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18008963b  test    al, al
0x18008963d  jz      short loc_180089643
0x18008963f  mov     al, 1
0x180089641  jmp     short loc_1800896A7
0x180089643  call    ?IsSDEVTablePresent@NgcUtils@@YA_NXZ; NgcUtils::IsSDEVTablePresent(void)
0x180089648  test    al, al
0x18008964a  jnz     short loc_180089678
0x18008964c  call    ?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ; NgcUtils::ExistsSecureFpRegKey(void)
0x180089651  test    al, al
0x180089653  jnz     short loc_180089678
0x180089655  mov     eax, cs:dword_180122070
0x18008965b  cmp     eax, 4
0x18008965e  jbe     short loc_1800896A5
0x180089660  xor     r8d, r8d
0x180089663  lea     rdx, byte_180106B2D
0x18008966a  lea     rcx, dword_180122070
0x180089671  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180089676  jmp     short loc_1800896A5
0x180089678  call    ?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ; NgcUtils::SecureBioRegKeyState(void)
0x18008967d  test    eax, eax
0x18008967f  setnz   al
0x180089682  jmp     short loc_1800896A7
0x180089684  mov     eax, cs:dword_180122070
0x18008968a  cmp     eax, 4
0x18008968d  jbe     short loc_1800896A5
0x18008968f  xor     r8d, r8d
0x180089692  lea     rdx, unk_180106B88
0x180089699  lea     rcx, dword_180122070
0x1800896a0  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800896a5  xor     al, al
0x1800896a7  mov     rcx, [rbp+var_10]
0x1800896ab  xor     rcx, rsp; StackCookie
0x1800896ae  call    __security_check_cookie
0x1800896b3  add     rsp, 70h
0x1800896b7  pop     rbp
0x1800896b8  retn
```
