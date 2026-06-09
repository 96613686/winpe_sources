# NgcUtils::IsSecureBioEnabled(void)

- ea: `0x1800753fc`
- end: `0x1800755f9`
- name: `?IsSecureBioEnabled@NgcUtils@@YA_NXZ`
- size: `509`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800752b4`

## callees

- `0x180001a88`
- `0x180007670`
- `0x18001cb98`
- `0x180034fd0`
- `0x180070aec`
- `0x180074ed8`
- `0x180074efc`
- `0x180075370`
- `0x1800753fc`
- `0x180075628`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075519`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075519`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075551`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075569`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075551`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075569`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800754c8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800754c8`
- `ntdll!NtQuerySystemInformation` at `0x180075495`
- `ntdll!NtQuerySystemInformation` at `0x180075495`
- `tbs!Tbsi_GetDeviceInfo` at `0x180075429`
- `tbs!Tbsi_GetDeviceInfo` at `0x180075429`

## string_xrefs

- `0x18007543a`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x1800754a6`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x1800754e1`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall NgcUtils::IsSecureBioEnabled(NgcUtils *this)
{
  int DeviceInfo; // eax
  NTSTATUS v2; // eax
  HRESULT v3; // eax
  bool v4; // bl
  NgcUtils *v5; // rcx
  NgcUtils *v7; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  ULONG ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  LPVOID v10; // [rsp+38h] [rbp-38h] BYREF
  __int128 v11; // [rsp+40h] [rbp-30h] BYREF
  __int128 SystemInformation; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v11 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, &v11);
  if ( DeviceInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)DeviceInfo,
      ppv);
  if ( DWORD1(v11) < 2 )
  {
    if ( *(_DWORD *)g_logProvider > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        g_logProvider,
        &byte_1800B3E67,
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
    if ( *(_DWORD *)g_logProvider > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        g_logProvider,
        &word_1800B3E3E,
        0);
    return 0;
  }
  v3 = CoInitializeEx(0, 0);
  v4 = v3 >= 0;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v3,
      ppv);
LABEL_15:
    if ( v4 )
      CoUninitialize();
    return 0;
  }
  v10 = 0;
  if ( CoCreateInstance(
         &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
         0,
         1u,
         &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
         &v10) < 0 )
  {
    if ( *(_DWORD *)g_logProvider > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        g_logProvider,
        byte_1800B3DE3,
        0);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v10);
    goto LABEL_15;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v10);
  if ( v4 )
    CoUninitialize();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    return 1;
  if ( NgcUtils::IsSDEVTablePresent(v5) || NgcUtils::ExistsSecureFpRegKey(v7) )
    return (unsigned int)NgcUtils::SecureBioRegKeyState() != 0;
  if ( *(_DWORD *)g_logProvider > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      g_logProvider,
      &word_1800B3E16,
      0);
  return 0;
}

```

## disassembly

```asm
0x1800753fc  mov     [rsp-8+arg_0], rbx
0x180075401  push    rbp
0x180075402  mov     rbp, rsp
0x180075405  sub     rsp, 70h
0x180075409  mov     rax, cs:__security_cookie
0x180075410  xor     rax, rsp
0x180075413  mov     [rbp+var_10], rax
0x180075417  xorps   xmm0, xmm0
0x18007541a  movups  [rbp+var_30], xmm0
0x18007541e  lea     rdx, [rbp+var_30]
0x180075422  mov     ebx, 10h
0x180075427  mov     ecx, ebx
0x180075429  call    cs:__imp_Tbsi_GetDeviceInfo
0x18007542f  mov     rcx, [rbp+8]; this
0x180075433  test    eax, eax
0x180075435  jns     short loc_18007544B
0x180075437  mov     r9d, eax; char *
0x18007543a  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180075441  mov     edx, 17Ch; void *
0x180075446  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007544b  cmp     dword ptr [rbp+var_30+4], 2
0x18007544f  jnb     short loc_180075477
0x180075451  mov     rcx, cs:g_logProvider
0x180075458  mov     eax, [rcx]
0x18007545a  cmp     eax, 4
0x18007545d  jbe     loc_1800755DD
0x180075463  xor     r8d, r8d
0x180075466  lea     rdx, byte_1800B3E67
0x18007546d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180075472  jmp     loc_1800755DD
0x180075477  xorps   xmm0, xmm0
0x18007547a  movups  [rbp+SystemInformation], xmm0
0x18007547e  mov     [rbp+ReturnLength], 0
0x180075485  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180075489  mov     r8d, ebx; SystemInformationLength
0x18007548c  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180075490  mov     ecx, 0A5h; SystemInformationClass
0x180075495  call    cs:__imp_NtQuerySystemInformation
0x18007549b  mov     rcx, [rbp+8]; this
0x18007549f  test    eax, eax
0x1800754a1  jns     short loc_1800754B7
0x1800754a3  mov     r9d, eax; char *
0x1800754a6  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800754ad  mov     edx, 18Dh; void *
0x1800754b2  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800754b7  mov     al, byte ptr [rbp+SystemInformation]
0x1800754ba  and     al, 21h
0x1800754bc  cmp     al, 21h ; '!'
0x1800754be  jnz     loc_1800755C0
0x1800754c4  xor     edx, edx; dwCoInit
0x1800754c6  xor     ecx, ecx; pvReserved
0x1800754c8  call    cs:__imp_CoInitializeEx
0x1800754ce  mov     ebx, eax
0x1800754d0  shr     ebx, 1Fh
0x1800754d3  xor     bl, 1
0x1800754d6  mov     rcx, [rbp+8]; this
0x1800754da  test    eax, eax
0x1800754dc  jns     short loc_1800754F4
0x1800754de  mov     r9d, eax; char *
0x1800754e1  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800754e8  mov     edx, 19Dh; void *
0x1800754ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800754f2  jmp     short loc_180075549
0x1800754f4  mov     [rbp+var_38], 0
0x1800754fc  lea     rax, [rbp+var_38]
0x180075500  mov     qword ptr [rsp+70h+ppv], rax; ppv
0x180075505  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x18007550c  xor     edx, edx; pUnkOuter
0x18007550e  lea     r8d, [rdx+1]; dwClsContext
0x180075512  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x180075519  call    cs:__imp_CoCreateInstance
0x18007551f  test    eax, eax
0x180075521  jns     short loc_18007555C
0x180075523  mov     rcx, cs:g_logProvider
0x18007552a  mov     eax, [rcx]
0x18007552c  cmp     eax, 4
0x18007552f  jbe     short loc_180075540
0x180075531  xor     r8d, r8d
0x180075534  lea     rdx, byte_1800B3DE3
0x18007553b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180075540  lea     rcx, [rbp+var_38]
0x180075544  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180075549  test    bl, bl
0x18007554b  jz      loc_1800755DD
0x180075551  call    cs:__imp_CoUninitialize
0x180075557  jmp     loc_1800755DD
0x18007555c  lea     rcx, [rbp+var_38]
0x180075560  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180075565  test    bl, bl
0x180075567  jz      short loc_18007556F
0x180075569  call    cs:__imp_CoUninitialize
0x18007556f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180075576  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18007557b  test    al, al
0x18007557d  jz      short loc_180075583
0x18007557f  mov     al, 1
0x180075581  jmp     short loc_1800755DF
0x180075583  call    ?IsSDEVTablePresent@NgcUtils@@YA_NXZ; NgcUtils::IsSDEVTablePresent(void)
0x180075588  test    al, al
0x18007558a  jnz     short loc_1800755B4
0x18007558c  call    ?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ; NgcUtils::ExistsSecureFpRegKey(void)
0x180075591  test    al, al
0x180075593  jnz     short loc_1800755B4
0x180075595  mov     rcx, cs:g_logProvider
0x18007559c  mov     eax, [rcx]
0x18007559e  cmp     eax, 4
0x1800755a1  jbe     short loc_1800755DD
0x1800755a3  xor     r8d, r8d
0x1800755a6  lea     rdx, word_1800B3E16
0x1800755ad  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800755b2  jmp     short loc_1800755DD
0x1800755b4  call    ?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ; NgcUtils::SecureBioRegKeyState(void)
0x1800755b9  test    eax, eax
0x1800755bb  setnz   al
0x1800755be  jmp     short loc_1800755DF
0x1800755c0  mov     rcx, cs:g_logProvider
0x1800755c7  mov     eax, [rcx]
0x1800755c9  cmp     eax, 4
0x1800755cc  jbe     short loc_1800755DD
0x1800755ce  xor     r8d, r8d
0x1800755d1  lea     rdx, word_1800B3E3E
0x1800755d8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800755dd  xor     al, al
0x1800755df  mov     rcx, [rbp+var_10]
0x1800755e3  xor     rcx, rsp; StackCookie
0x1800755e6  call    __security_check_cookie
0x1800755eb  mov     rbx, [rsp+70h+arg_0]
0x1800755f3  add     rsp, 70h
0x1800755f7  pop     rbp
0x1800755f8  retn
```
