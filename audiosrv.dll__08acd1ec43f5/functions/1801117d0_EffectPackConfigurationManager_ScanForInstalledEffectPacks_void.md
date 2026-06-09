# EffectPackConfigurationManager::ScanForInstalledEffectPacks(void)

- ea: `0x1801117d0`
- end: `0x180111a93`
- name: `?ScanForInstalledEffectPacks@EffectPackConfigurationManager@@AEAAJXZ`
- size: `707`
- prototype: `__int64 __fastcall(EffectPackConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180111230`

## callees

- `0x180002198`
- `0x180008f40`
- `0x18000ae1c`
- `0x18000e284`
- `0x18000e4d0`
- `0x18001280c`
- `0x18001b520`
- `0x18002ef9c`
- `0x1800303f0`
- `0x180072e10`
- `0x1800befa8`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1801112bc`
- `0x1801117d0`
- `0x180111b64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180111876`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180111876`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011181f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011181f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801118ee`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801118ee`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011190d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011190d`

## string_xrefs

- `0x180111955`: `avcore\audiocore\server\audiosrv\dll\effectpackconfigurationmanager.cpp`
- `0x1801119d1`: `avcore\audiocore\server\audiosrv\dll\effectpackconfigurationmanager.cpp`
- `0x180111a74`: `avcore\audiocore\server\audiosrv\dll\effectpackconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EffectPackConfigurationManager::ScanForInstalledEffectPacks(EffectPackConfigurationManager *this)
{
  DWORD v2; // eax
  WCHAR *v3; // rbx
  DWORD i; // esi
  EffectPackConfigurationManager *v5; // rcx
  int v6; // eax
  struct CSerialWorkQueue *SerialWorkQueue; // rdi
  __int64 v8; // rcx
  int v9; // eax
  _DWORD *v10; // r8
  __int64 v11; // r8
  unsigned int v12; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v21[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v22; // [rsp+90h] [rbp-70h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
  GUID v24; // [rsp+A8h] [rbp-58h]
  __int64 v25[2]; // [rsp+B8h] [rbp-48h] BYREF
  GUID v26; // [rsp+C8h] [rbp-38h]
  __int64 *v27; // [rsp+F0h] [rbp-10h]
  GUID pclsid; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\EffectsPacks",
         0,
         0x20019u,
         &hKey)
    || (cSubKeys = 0, cbMaxSubKeyLen = 0, RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0)) )
  {
LABEL_16:
    v10 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v10 > 4u && (unsigned __int8)tlgKeywordOn(v10, 2048) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v11,
        word_1801A62E2);
    goto LABEL_19;
  }
  v2 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen >= 0x26 )
  {
    ++cbMaxSubKeyLen;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpName,
      0,
      v2 + 1);
    v3 = lpName;
    if ( !lpName )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\effectpackconfigurationmanager.cpp",
        (const char *)0x8007000ELL,
        phkResult);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
      goto LABEL_20;
    }
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = cbMaxSubKeyLen;
      RegEnumKeyExW(hKey, i, v3, &cchName, 0, 0, 0, 0);
      if ( cchName == 38 )
      {
        pclsid = 0;
        if ( CLSIDFromString(v3, &pclsid) >= 0 )
        {
          v22 = pclsid;
          if ( !EffectPackConfigurationManager::SkipVoiceClarityEffectPack(v5, &v22) )
          {
            v22 = pclsid;
            v6 = EffectPackConfigurationManager::AddEffectPackConfigurationToList(this, &v22);
            if ( v6 >= 0 )
            {
              wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
                v21,
                this);
              SerialWorkQueue = GetSerialWorkQueue();
              wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
                &v23,
                v21[0]);
              v24 = pclsid;
              v25[0] = (__int64)off_180175A68;
              v8 = v23;
              v23 = 0;
              v25[1] = v8;
              v26 = pclsid;
              v27 = v25;
              v9 = CSerialWorkQueue::QueueWorkItem((__int64)SerialWorkQueue, v25);
              if ( v9 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x12C,
                  (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\effectpackconfigurationmanager.cpp",
                  (const char *)(unsigned int)v9,
                  phkResulta);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v23);
              wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v21);
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x127,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\effectpackconfigurationmanager.cpp",
                (const char *)(unsigned int)v6,
                phkResulta);
            }
          }
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
    goto LABEL_16;
  }
LABEL_19:
  v12 = 0;
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v12;
}

```

## disassembly

```asm
0x1801117d0  push    rbp
0x1801117d2  push    rbx
0x1801117d3  push    rsi
0x1801117d4  push    rdi
0x1801117d5  push    r14
0x1801117d7  push    r15
0x1801117d9  lea     rbp, [rsp-28h]
0x1801117de  sub     rsp, 128h
0x1801117e5  mov     rax, cs:__security_cookie
0x1801117ec  xor     rax, rsp
0x1801117ef  mov     [rbp+50h+var_40], rax
0x1801117f3  mov     r14, rcx
0x1801117f6  xor     r15d, r15d
0x1801117f9  mov     [rsp+150h+hKey], r15
0x1801117fe  lea     rax, [rsp+150h+hKey]
0x180111803  mov     [rsp+150h+phkResult], rax; phkResult
0x180111808  mov     r9d, 20019h; samDesired
0x18011180e  xor     r8d, r8d; ulOptions
0x180111811  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180111818  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011181f  call    cs:__imp_RegOpenKeyExW
0x180111825  test    eax, eax
0x180111827  jnz     loc_180111A0C
0x18011182d  mov     [rsp+150h+cSubKeys], r15d
0x180111832  mov     [rsp+150h+cbMaxSubKeyLen], r15d
0x180111837  mov     [rsp+150h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18011183c  mov     [rsp+150h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180111841  mov     [rsp+150h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180111846  mov     [rsp+150h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18011184b  mov     [rsp+150h+lpcValues], r15; lpcValues
0x180111850  mov     [rsp+150h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180111855  lea     rax, [rsp+150h+cbMaxSubKeyLen]
0x18011185a  mov     [rsp+150h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18011185f  lea     rax, [rsp+150h+cSubKeys]
0x180111864  mov     [rsp+150h+phkResult], rax; int
0x180111869  xor     r9d, r9d; lpReserved
0x18011186c  xor     r8d, r8d; lpcchClass
0x18011186f  xor     edx, edx; lpClass
0x180111871  mov     rcx, [rsp+150h+hKey]; hKey
0x180111876  call    cs:__imp_RegQueryInfoKeyW
0x18011187c  test    eax, eax
0x18011187e  jnz     loc_180111A0C
0x180111884  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x180111888  cmp     eax, 26h ; '&'
0x18011188b  jb      loc_180111A3D
0x180111891  inc     eax
0x180111893  mov     [rsp+150h+cbMaxSubKeyLen], eax
0x180111897  mov     r8d, eax
0x18011189a  xor     edx, edx
0x18011189c  lea     rcx, [rsp+150h+lpName]
0x1801118a1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801118a6  nop
0x1801118a7  mov     rbx, [rsp+150h+lpName]
0x1801118ac  test    rbx, rbx
0x1801118af  jz      loc_180111A68
0x1801118b5  mov     esi, r15d
0x1801118b8  cmp     [rsp+150h+cSubKeys], r15d
0x1801118bd  jbe     loc_180111A02
0x1801118c3  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x1801118c7  mov     [rsp+150h+cchName], eax
0x1801118cb  mov     [rsp+150h+lpcValues], r15; lpftLastWriteTime
0x1801118d0  mov     [rsp+150h+lpcbMaxClassLen], r15; lpcchClass
0x1801118d5  mov     [rsp+150h+lpcbMaxSubKeyLen], r15; lpClass
0x1801118da  mov     [rsp+150h+phkResult], r15; int
0x1801118df  lea     r9, [rsp+150h+cchName]; lpcchName
0x1801118e4  mov     r8, rbx; lpName
0x1801118e7  mov     edx, esi; dwIndex
0x1801118e9  mov     rcx, [rsp+150h+hKey]; hKey
0x1801118ee  call    cs:__imp_RegEnumKeyExW
0x1801118f4  cmp     [rsp+150h+cchName], 26h ; '&'
0x1801118f9  jnz     loc_1801119F6
0x1801118ff  xorps   xmm0, xmm0
0x180111902  movups  xmmword ptr [rbp+50h+pclsid.Data1], xmm0
0x180111906  lea     rdx, [rbp+50h+pclsid]; pclsid
0x18011190a  mov     rcx, rbx; lpsz
0x18011190d  call    cs:__imp_CLSIDFromString
0x180111913  test    eax, eax
0x180111915  js      loc_1801119F6
0x18011191b  movaps  xmm0, xmmword ptr [rbp+50h+pclsid.Data1]
0x18011191f  movdqa  xmmword ptr [rbp+50h+var_C0.Data1], xmm0
0x180111924  lea     rdx, [rbp+50h+var_C0]; struct _GUID
0x180111928  call    ?SkipVoiceClarityEffectPack@EffectPackConfigurationManager@@AEAA_NU_GUID@@@Z; EffectPackConfigurationManager::SkipVoiceClarityEffectPack(_GUID)
0x18011192d  test    al, al
0x18011192f  jnz     loc_1801119F6
0x180111935  movaps  xmm0, xmmword ptr [rbp+50h+pclsid.Data1]
0x180111939  movdqa  xmmword ptr [rbp+50h+var_C0.Data1], xmm0
0x18011193e  lea     rdx, [rbp+50h+var_C0]; struct _GUID
0x180111942  mov     rcx, r14; this
0x180111945  call    ?AddEffectPackConfigurationToList@EffectPackConfigurationManager@@AEAAJU_GUID@@@Z; EffectPackConfigurationManager::AddEffectPackConfigurationToList(_GUID)
0x18011194a  mov     rcx, [rbp+58h]; this
0x18011194e  test    eax, eax
0x180111950  jns     short loc_18011196B
0x180111952  mov     r9d, eax; char *
0x180111955  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011195c  mov     edx, 127h; void *
0x180111961  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180111966  jmp     loc_1801119F6
0x18011196b  mov     rdx, r14
0x18011196e  lea     rcx, [rbp+50h+var_D0]
0x180111972  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x180111977  nop
0x180111978  call    ?GetSerialWorkQueue@@YAAEAVCSerialWorkQueue@@XZ; GetSerialWorkQueue(void)
0x18011197d  mov     rdi, rax
0x180111980  mov     rdx, [rbp+50h+var_D0]
0x180111984  lea     rcx, [rbp+50h+var_B0]
0x180111988  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x18011198d  movaps  xmm0, xmmword ptr [rbp+50h+pclsid.Data1]
0x180111991  movdqu  [rbp+50h+var_A8], xmm0
0x180111996  lea     rax, off_180175A68
0x18011199d  mov     [rbp+50h+var_98], rax
0x1801119a1  mov     rcx, [rbp+50h+var_B0]
0x1801119a5  mov     [rbp+50h+var_B0], r15
0x1801119a9  mov     [rbp+50h+var_90], rcx
0x1801119ad  movdqu  [rbp+50h+var_88], xmm0
0x1801119b2  lea     rax, [rbp+50h+var_98]
0x1801119b6  mov     [rbp+50h+var_60], rax
0x1801119ba  lea     rdx, [rbp+50h+var_98]
0x1801119be  mov     rcx, rdi
0x1801119c1  call    ?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z; CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)
0x1801119c6  mov     rcx, [rbp+58h]; this
0x1801119ca  test    eax, eax
0x1801119cc  jns     short loc_1801119E3
0x1801119ce  mov     r9d, eax; char *
0x1801119d1  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801119d8  mov     edx, 12Ch; void *
0x1801119dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801119e2  nop
0x1801119e3  lea     rcx, [rbp+50h+var_B0]
0x1801119e7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801119ec  nop
0x1801119ed  lea     rcx, [rbp+50h+var_D0]
0x1801119f1  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801119f6  inc     esi
0x1801119f8  cmp     esi, [rsp+150h+cSubKeys]
0x1801119fc  jb      loc_1801118C3
0x180111a02  lea     rcx, [rsp+150h+lpName]
0x180111a07  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180111a0c  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180111a11  mov     r8, [rax+8]
0x180111a15  mov     eax, [r8]
0x180111a18  cmp     eax, 4
0x180111a1b  jbe     short loc_180111A3D
0x180111a1d  mov     edx, 800h
0x180111a22  mov     rcx, r8
0x180111a25  call    _tlgKeywordOn
0x180111a2a  test    al, al
0x180111a2c  jz      short loc_180111A3D
0x180111a2e  lea     rdx, word_1801A62E2
0x180111a35  mov     rcx, r8
0x180111a38  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180111a3d  mov     ebx, r15d
0x180111a40  lea     rcx, [rsp+150h+hKey]
0x180111a45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180111a4a  mov     eax, ebx
0x180111a4c  mov     rcx, [rbp+50h+var_40]
0x180111a50  xor     rcx, rsp; StackCookie
0x180111a53  call    __security_check_cookie
0x180111a58  add     rsp, 128h
0x180111a5f  pop     r15
0x180111a61  pop     r14
0x180111a63  pop     rdi
0x180111a64  pop     rsi
0x180111a65  pop     rbx
0x180111a66  pop     rbp
0x180111a67  retn
0x180111a68  mov     rcx, [rbp+58h]; this
0x180111a6c  mov     ebx, 8007000Eh
0x180111a71  mov     r9d, ebx; char *
0x180111a74  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180111a7b  mov     edx, 109h; void *
0x180111a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111a85  nop
0x180111a86  lea     rcx, [rsp+150h+lpName]
0x180111a8b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180111a90  jmp     short loc_180111A40
```
