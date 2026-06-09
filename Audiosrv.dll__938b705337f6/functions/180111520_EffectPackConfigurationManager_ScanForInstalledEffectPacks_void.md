# EffectPackConfigurationManager::ScanForInstalledEffectPacks(void)

- ea: `0x180111520`
- end: `0x1801117e3`
- name: `?ScanForInstalledEffectPacks@EffectPackConfigurationManager@@AEAAJXZ`
- size: `707`
- prototype: `__int64 __fastcall(EffectPackConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180110f80`

## callees

- `0x180002198`
- `0x180008df0`
- `0x18000accc`
- `0x18000e134`
- `0x18000e380`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18002ee3c`
- `0x180030290`
- `0x180073310`
- `0x1800c0af8`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x18011100c`
- `0x180111520`
- `0x1801118b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801115c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801115c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011156f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011156f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18011163e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18011163e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011165d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011165d`

## string_xrefs

- `0x1801116a5`: `avcore\audiocore\server\audiosrv\dll\effectpackconfigurationmanager.cpp`
- `0x180111721`: `avcore\audiocore\server\audiosrv\dll\effectpackconfigurationmanager.cpp`
- `0x1801117c4`: `avcore\audiocore\server\audiosrv\dll\effectpackconfigurationmanager.cpp`

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
        &unk_1801A509F);
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
              v25[0] = (__int64)off_180174A58;
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
0x180111520  push    rbp
0x180111522  push    rbx
0x180111523  push    rsi
0x180111524  push    rdi
0x180111525  push    r14
0x180111527  push    r15
0x180111529  lea     rbp, [rsp-28h]
0x18011152e  sub     rsp, 128h
0x180111535  mov     rax, cs:__security_cookie
0x18011153c  xor     rax, rsp
0x18011153f  mov     [rbp+50h+var_40], rax
0x180111543  mov     r14, rcx
0x180111546  xor     r15d, r15d
0x180111549  mov     [rsp+150h+hKey], r15
0x18011154e  lea     rax, [rsp+150h+hKey]
0x180111553  mov     [rsp+150h+phkResult], rax; phkResult
0x180111558  mov     r9d, 20019h; samDesired
0x18011155e  xor     r8d, r8d; ulOptions
0x180111561  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180111568  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011156f  call    cs:__imp_RegOpenKeyExW
0x180111575  test    eax, eax
0x180111577  jnz     loc_18011175C
0x18011157d  mov     [rsp+150h+cSubKeys], r15d
0x180111582  mov     [rsp+150h+cbMaxSubKeyLen], r15d
0x180111587  mov     [rsp+150h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18011158c  mov     [rsp+150h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180111591  mov     [rsp+150h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180111596  mov     [rsp+150h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18011159b  mov     [rsp+150h+lpcValues], r15; lpcValues
0x1801115a0  mov     [rsp+150h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1801115a5  lea     rax, [rsp+150h+cbMaxSubKeyLen]
0x1801115aa  mov     [rsp+150h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1801115af  lea     rax, [rsp+150h+cSubKeys]
0x1801115b4  mov     [rsp+150h+phkResult], rax; int
0x1801115b9  xor     r9d, r9d; lpReserved
0x1801115bc  xor     r8d, r8d; lpcchClass
0x1801115bf  xor     edx, edx; lpClass
0x1801115c1  mov     rcx, [rsp+150h+hKey]; hKey
0x1801115c6  call    cs:__imp_RegQueryInfoKeyW
0x1801115cc  test    eax, eax
0x1801115ce  jnz     loc_18011175C
0x1801115d4  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x1801115d8  cmp     eax, 26h ; '&'
0x1801115db  jb      loc_18011178D
0x1801115e1  inc     eax
0x1801115e3  mov     [rsp+150h+cbMaxSubKeyLen], eax
0x1801115e7  mov     r8d, eax
0x1801115ea  xor     edx, edx
0x1801115ec  lea     rcx, [rsp+150h+lpName]
0x1801115f1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801115f6  nop
0x1801115f7  mov     rbx, [rsp+150h+lpName]
0x1801115fc  test    rbx, rbx
0x1801115ff  jz      loc_1801117B8
0x180111605  mov     esi, r15d
0x180111608  cmp     [rsp+150h+cSubKeys], r15d
0x18011160d  jbe     loc_180111752
0x180111613  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x180111617  mov     [rsp+150h+cchName], eax
0x18011161b  mov     [rsp+150h+lpcValues], r15; lpftLastWriteTime
0x180111620  mov     [rsp+150h+lpcbMaxClassLen], r15; lpcchClass
0x180111625  mov     [rsp+150h+lpcbMaxSubKeyLen], r15; lpClass
0x18011162a  mov     [rsp+150h+phkResult], r15; int
0x18011162f  lea     r9, [rsp+150h+cchName]; lpcchName
0x180111634  mov     r8, rbx; lpName
0x180111637  mov     edx, esi; dwIndex
0x180111639  mov     rcx, [rsp+150h+hKey]; hKey
0x18011163e  call    cs:__imp_RegEnumKeyExW
0x180111644  cmp     [rsp+150h+cchName], 26h ; '&'
0x180111649  jnz     loc_180111746
0x18011164f  xorps   xmm0, xmm0
0x180111652  movups  xmmword ptr [rbp+50h+pclsid.Data1], xmm0
0x180111656  lea     rdx, [rbp+50h+pclsid]; pclsid
0x18011165a  mov     rcx, rbx; lpsz
0x18011165d  call    cs:__imp_CLSIDFromString
0x180111663  test    eax, eax
0x180111665  js      loc_180111746
0x18011166b  movaps  xmm0, xmmword ptr [rbp+50h+pclsid.Data1]
0x18011166f  movdqa  xmmword ptr [rbp+50h+var_C0.Data1], xmm0
0x180111674  lea     rdx, [rbp+50h+var_C0]; struct _GUID
0x180111678  call    ?SkipVoiceClarityEffectPack@EffectPackConfigurationManager@@AEAA_NU_GUID@@@Z; EffectPackConfigurationManager::SkipVoiceClarityEffectPack(_GUID)
0x18011167d  test    al, al
0x18011167f  jnz     loc_180111746
0x180111685  movaps  xmm0, xmmword ptr [rbp+50h+pclsid.Data1]
0x180111689  movdqa  xmmword ptr [rbp+50h+var_C0.Data1], xmm0
0x18011168e  lea     rdx, [rbp+50h+var_C0]; struct _GUID
0x180111692  mov     rcx, r14; this
0x180111695  call    ?AddEffectPackConfigurationToList@EffectPackConfigurationManager@@AEAAJU_GUID@@@Z; EffectPackConfigurationManager::AddEffectPackConfigurationToList(_GUID)
0x18011169a  mov     rcx, [rbp+58h]; this
0x18011169e  test    eax, eax
0x1801116a0  jns     short loc_1801116BB
0x1801116a2  mov     r9d, eax; char *
0x1801116a5  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801116ac  mov     edx, 127h; void *
0x1801116b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801116b6  jmp     loc_180111746
0x1801116bb  mov     rdx, r14
0x1801116be  lea     rcx, [rbp+50h+var_D0]
0x1801116c2  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x1801116c7  nop
0x1801116c8  call    ?GetSerialWorkQueue@@YAAEAVCSerialWorkQueue@@XZ; GetSerialWorkQueue(void)
0x1801116cd  mov     rdi, rax
0x1801116d0  mov     rdx, [rbp+50h+var_D0]
0x1801116d4  lea     rcx, [rbp+50h+var_B0]
0x1801116d8  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x1801116dd  movaps  xmm0, xmmword ptr [rbp+50h+pclsid.Data1]
0x1801116e1  movdqu  [rbp+50h+var_A8], xmm0
0x1801116e6  lea     rax, off_180174A58
0x1801116ed  mov     [rbp+50h+var_98], rax
0x1801116f1  mov     rcx, [rbp+50h+var_B0]
0x1801116f5  mov     [rbp+50h+var_B0], r15
0x1801116f9  mov     [rbp+50h+var_90], rcx
0x1801116fd  movdqu  [rbp+50h+var_88], xmm0
0x180111702  lea     rax, [rbp+50h+var_98]
0x180111706  mov     [rbp+50h+var_60], rax
0x18011170a  lea     rdx, [rbp+50h+var_98]
0x18011170e  mov     rcx, rdi
0x180111711  call    ?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z; CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)
0x180111716  mov     rcx, [rbp+58h]; this
0x18011171a  test    eax, eax
0x18011171c  jns     short loc_180111733
0x18011171e  mov     r9d, eax; char *
0x180111721  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180111728  mov     edx, 12Ch; void *
0x18011172d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180111732  nop
0x180111733  lea     rcx, [rbp+50h+var_B0]
0x180111737  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18011173c  nop
0x18011173d  lea     rcx, [rbp+50h+var_D0]
0x180111741  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180111746  inc     esi
0x180111748  cmp     esi, [rsp+150h+cSubKeys]
0x18011174c  jb      loc_180111613
0x180111752  lea     rcx, [rsp+150h+lpName]
0x180111757  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18011175c  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180111761  mov     r8, [rax+8]
0x180111765  mov     eax, [r8]
0x180111768  cmp     eax, 4
0x18011176b  jbe     short loc_18011178D
0x18011176d  mov     edx, 800h
0x180111772  mov     rcx, r8
0x180111775  call    _tlgKeywordOn
0x18011177a  test    al, al
0x18011177c  jz      short loc_18011178D
0x18011177e  lea     rdx, unk_1801A509F
0x180111785  mov     rcx, r8
0x180111788  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18011178d  mov     ebx, r15d
0x180111790  lea     rcx, [rsp+150h+hKey]
0x180111795  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011179a  mov     eax, ebx
0x18011179c  mov     rcx, [rbp+50h+var_40]
0x1801117a0  xor     rcx, rsp; StackCookie
0x1801117a3  call    __security_check_cookie
0x1801117a8  add     rsp, 128h
0x1801117af  pop     r15
0x1801117b1  pop     r14
0x1801117b3  pop     rdi
0x1801117b4  pop     rsi
0x1801117b5  pop     rbx
0x1801117b6  pop     rbp
0x1801117b7  retn
0x1801117b8  mov     rcx, [rbp+58h]; this
0x1801117bc  mov     ebx, 8007000Eh
0x1801117c1  mov     r9d, ebx; char *
0x1801117c4  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801117cb  mov     edx, 109h; void *
0x1801117d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801117d5  nop
0x1801117d6  lea     rcx, [rsp+150h+lpName]
0x1801117db  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1801117e0  jmp     short loc_180111790
```
