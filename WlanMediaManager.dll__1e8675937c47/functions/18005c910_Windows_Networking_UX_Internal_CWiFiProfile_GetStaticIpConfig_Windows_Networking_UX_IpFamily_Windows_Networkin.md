# Windows::Networking::UX::Internal::CWiFiProfile::GetStaticIpConfig(Windows::Networking::UX::IpFamily,Windows::Networking::UX::IStaticIpConfig * *)

- ea: `0x18005c910`
- end: `0x18005cc46`
- name: `?GetStaticIpConfig@CWiFiProfile@Internal@UX@Networking@Windows@@UEAAJW4IpFamily@345@PEAPEAUIStaticIpConfig@345@@Z`
- size: `822`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x1800097b4`
- `0x1800120c4`
- `0x180012228`
- `0x18001668c`
- `0x1800287a0`
- `0x18005b728`
- `0x18005b774`
- `0x18005c910`
- `0x18005e7d0`
- `0x18005eb34`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ca5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ca5f`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cabb`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cb22`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cbac`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cbfd`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cabb`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cb22`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cbac`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005cbfd`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x18005ca87`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x18005ca87`
- `wlanapi!WlanVerifyProfileIpConfiguration` at `0x18005cae7`
- `wlanapi!WlanVerifyProfileIpConfiguration` at `0x18005cae7`

## string_xrefs

- `0x18005ca09`: `ProfileIpConfigurationV4`
- `0x18005ca14`: `ProfileIpConfigurationV6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiProfile::GetStaticIpConfig(
        __int64 a1,
        unsigned int a2,
        struct Windows::Networking::UX::IStaticIpConfig **a3)
{
  const unsigned __int16 (*v6)[37]; // rdx
  __int64 *v7; // rax
  __int64 v8; // r8
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  const wchar_t *v18; // rbx
  PCWSTR StringRawBuffer; // rax
  signed int ProfileMetadata; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  PVOID v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rdx
  Windows::Networking::UX::Internal::CWiFiProfile *v26; // rcx
  __int64 v27; // r8
  PVOID v28; // rcx
  struct _WLAN_PROFILE_IP_CONFIGURATION *v29; // rbx
  int v30; // edi
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  PVOID v34; // rcx
  struct Windows::Networking::UX::IStaticIpConfig *v35; // rcx
  PVOID v36; // rcx
  int v37; // [rsp+20h] [rbp-88h]
  unsigned int v38; // [rsp+20h] [rbp-88h]
  struct Windows::Networking::UX::IStaticIpConfig *v39; // [rsp+30h] [rbp-78h] BYREF
  PVOID pMemory; // [rsp+38h] [rbp-70h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v42[8]; // [rsp+48h] [rbp-60h] BYREF
  HSTRING string; // [rsp+50h] [rbp-58h] BYREF
  __int64 v44; // [rsp+58h] [rbp-50h] BYREF
  char v45; // [rsp+60h] [rbp-48h]
  __int128 v46; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a3 = 0;
  wil::impersonate_token(v42);
  v39 = 0;
  v7 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, v6);
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>(
         *v7,
         &v39,
         v8);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
      (const char *)(unsigned int)v9,
      v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39, v11, v12);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v42);
    return v10;
  }
  v14 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, _QWORD))(*(_QWORD *)v39 + 56LL))(
          v39,
          a2);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
      (const char *)(unsigned int)v14,
      v37);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39, v16, v17);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v42);
    return v15;
  }
  if ( a2 == 4 )
  {
    v18 = L"ProfileIpConfigurationV4";
  }
  else
  {
    v18 = L"ProfileIpConfigurationV6";
    if ( a2 != 6 )
      v18 = 0;
  }
  v46 = *(_OWORD *)(*(_QWORD *)(a1 + 64) + 8LL);
  v41 = 0;
  pMemory = 0;
  string = (HSTRING)&pMemory;
  v44 = 0;
  v45 = 1;
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 72), 0);
  ProfileMetadata = WlanGetProfileMetadata(&v46, StringRawBuffer, 0, v18, &v41, &v44, v39);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>(&string);
  if ( ProfileMetadata )
  {
    if ( ProfileMetadata > 0 )
      ProfileMetadata = (unsigned __int16)ProfileMetadata | 0x80070000;
    v23 = pMemory;
    pMemory = 0;
    if ( v23 )
      WlanFreeMemory(v23);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39, v21, v22);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v42);
    return (unsigned int)ProfileMetadata;
  }
  v24 = WlanVerifyProfileIpConfiguration(v41, pMemory);
  if ( v24 )
  {
    ProfileMetadata = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xEB,
                        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                        (const char *)v24,
                        v38);
    v28 = pMemory;
    pMemory = 0;
    if ( v28 )
      WlanFreeMemory(v28);
    goto LABEL_14;
  }
  v29 = (struct _WLAN_PROFILE_IP_CONFIGURATION *)pMemory;
  v30 = 0;
  if ( *((_DWORD *)pMemory + 1) )
    v30 = Windows::Networking::UX::Internal::CWiFiProfile::_ParseIpFromConfig(
            v26,
            (struct _WLAN_PROFILE_IP_CONFIGURATION *)pMemory,
            v39);
  v31 = 0;
  if ( *((_DWORD *)v29 + 5) )
    v31 = Windows::Networking::UX::Internal::CWiFiProfile::_ParseDnsFromConfig(v26, v29, v39);
  if ( v30 >= 0 || v31 >= 0 )
  {
    v35 = v39;
    if ( v39 )
    {
      (*(void (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *))(*(_QWORD *)v39 + 8LL))(v39);
      v35 = v39;
    }
    *a3 = v35;
    v36 = pMemory;
    pMemory = 0;
    if ( v36 )
      WlanFreeMemory(v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39, v25, v27);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v42);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
      (const char *)(unsigned int)v30,
      v38);
    v34 = pMemory;
    pMemory = 0;
    if ( v34 )
      WlanFreeMemory(v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39, v32, v33);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v42);
    return (unsigned int)v30;
  }
}

```

## disassembly

```asm
0x18005c910  mov     [rsp+arg_18], rbx
0x18005c915  push    rsi
0x18005c916  push    rdi
0x18005c917  push    r14
0x18005c919  sub     rsp, 90h
0x18005c920  mov     rax, cs:__security_cookie
0x18005c927  xor     rax, rsp
0x18005c92a  mov     [rsp+0A8h+var_28], rax
0x18005c932  mov     rsi, r8
0x18005c935  mov     edi, edx
0x18005c937  mov     r14, rcx
0x18005c93a  mov     qword ptr [r8], 0
0x18005c941  mov     rdx, [rcx+80h]
0x18005c948  lea     rcx, [rsp+0A8h+var_60]
0x18005c94d  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18005c952  nop
0x18005c953  mov     [rsp+0A8h+var_78], 0
0x18005c95c  lea     rcx, [rsp+0A8h+string]; string
0x18005c961  call    ??$?0$0CF@@StringReference@Internal@Windows@@QEAA@AEAY0CF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[37])
0x18005c966  lea     rdx, [rsp+0A8h+var_78]
0x18005c96b  mov     rcx, [rax]
0x18005c96e  call    ??$ActivateInstance@V?$ComPtr@UIStaticIpConfig@UX@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStaticIpConfig@UX@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IStaticIpConfig>>)
0x18005c973  mov     ebx, eax
0x18005c975  test    eax, eax
0x18005c977  jns     short loc_18005C9B2
0x18005c979  mov     rcx, [rsp+0A8h]; this
0x18005c981  mov     r9d, eax; char *
0x18005c984  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005c98b  mov     edx, 0D8h; void *
0x18005c990  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c995  nop
0x18005c996  lea     rcx, [rsp+0A8h+var_78]
0x18005c99b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c9a0  nop
0x18005c9a1  lea     rcx, [rsp+0A8h+var_60]
0x18005c9a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005c9ab  mov     eax, ebx
0x18005c9ad  jmp     loc_18005CC21
0x18005c9b2  mov     rcx, [rsp+0A8h+var_78]
0x18005c9b7  mov     rax, [rcx]
0x18005c9ba  mov     edx, edi
0x18005c9bc  mov     rax, [rax+38h]
0x18005c9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9c5  mov     ebx, eax
0x18005c9c7  test    eax, eax
0x18005c9c9  jns     short loc_18005CA04
0x18005c9cb  mov     rcx, [rsp+0A8h]; this
0x18005c9d3  mov     r9d, eax; char *
0x18005c9d6  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005c9dd  mov     edx, 0D9h; void *
0x18005c9e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c9e7  nop
0x18005c9e8  lea     rcx, [rsp+0A8h+var_78]
0x18005c9ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005c9f2  nop
0x18005c9f3  lea     rcx, [rsp+0A8h+var_60]
0x18005c9f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005c9fd  mov     eax, ebx
0x18005c9ff  jmp     loc_18005CC21
0x18005ca04  cmp     edi, 4
0x18005ca07  jnz     short loc_18005CA12
0x18005ca09  lea     rbx, aProfileipconfi; "ProfileIpConfigurationV4"
0x18005ca10  jmp     short loc_18005CA22
0x18005ca12  xor     eax, eax
0x18005ca14  lea     rbx, aProfileipconfi_0; "ProfileIpConfigurationV6"
0x18005ca1b  cmp     edi, 6
0x18005ca1e  cmovnz  rbx, rax
0x18005ca22  mov     rax, [r14+40h]
0x18005ca26  movups  xmm0, xmmword ptr [rax+8]
0x18005ca2a  movdqu  [rsp+0A8h+var_38], xmm0
0x18005ca30  mov     [rsp+0A8h+var_68], 0
0x18005ca38  mov     [rsp+0A8h+pMemory], 0
0x18005ca41  lea     rax, [rsp+0A8h+pMemory]
0x18005ca46  mov     [rsp+0A8h+string], rax
0x18005ca4b  mov     [rsp+0A8h+var_50], 0
0x18005ca54  mov     [rsp+0A8h+var_48], 1
0x18005ca59  xor     edx, edx; length
0x18005ca5b  mov     rcx, [r14+48h]; string
0x18005ca5f  call    cs:__imp_WindowsGetStringRawBuffer
0x18005ca65  lea     rcx, [rsp+0A8h+var_50]
0x18005ca6a  mov     [rsp+0A8h+var_80], rcx
0x18005ca6f  lea     rcx, [rsp+0A8h+var_68]
0x18005ca74  mov     qword ptr [rsp+0A8h+var_88], rcx; int
0x18005ca79  mov     r9, rbx
0x18005ca7c  xor     r8d, r8d
0x18005ca7f  mov     rdx, rax
0x18005ca82  lea     rcx, [rsp+0A8h+var_38]
0x18005ca87  call    cs:__imp_WlanGetProfileMetadata
0x18005ca8d  mov     ebx, eax
0x18005ca8f  lea     rcx, [rsp+0A8h+string]
0x18005ca94  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18005ca99  test    ebx, ebx
0x18005ca9b  jz      short loc_18005CADE
0x18005ca9d  jle     short loc_18005CAA8
0x18005ca9f  movzx   ebx, bx
0x18005caa2  or      ebx, 80070000h
0x18005caa8  mov     rcx, [rsp+0A8h+pMemory]; pMemory
0x18005caad  mov     [rsp+0A8h+pMemory], 0
0x18005cab6  test    rcx, rcx
0x18005cab9  jz      short loc_18005CAC2
0x18005cabb  call    cs:__imp_WlanFreeMemory
0x18005cac1  nop
0x18005cac2  lea     rcx, [rsp+0A8h+var_78]
0x18005cac7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cacc  nop
0x18005cacd  lea     rcx, [rsp+0A8h+var_60]
0x18005cad2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005cad7  mov     eax, ebx
0x18005cad9  jmp     loc_18005CC21
0x18005cade  mov     rdx, [rsp+0A8h+pMemory]
0x18005cae3  mov     ecx, [rsp+0A8h+var_68]
0x18005cae7  call    cs:__imp_WlanVerifyProfileIpConfiguration
0x18005caed  test    eax, eax
0x18005caef  jz      short loc_18005CB45
0x18005caf1  mov     rcx, [rsp+0A8h]; this
0x18005caf9  mov     r9d, eax; char *
0x18005cafc  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005cb03  mov     edx, 0EBh; void *
0x18005cb08  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005cb0d  mov     ebx, eax
0x18005cb0f  mov     rcx, [rsp+0A8h+pMemory]; pMemory
0x18005cb14  mov     [rsp+0A8h+pMemory], 0
0x18005cb1d  test    rcx, rcx
0x18005cb20  jz      short loc_18005CB29
0x18005cb22  call    cs:__imp_WlanFreeMemory
0x18005cb28  nop
0x18005cb29  lea     rcx, [rsp+0A8h+var_78]
0x18005cb2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cb33  nop
0x18005cb34  lea     rcx, [rsp+0A8h+var_60]
0x18005cb39  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005cb3e  mov     eax, ebx
0x18005cb40  jmp     loc_18005CC21
0x18005cb45  mov     rbx, [rsp+0A8h+pMemory]
0x18005cb4a  xor     edi, edi
0x18005cb4c  cmp     [rbx+4], edi
0x18005cb4f  jbe     short loc_18005CB60
0x18005cb51  mov     r8, [rsp+0A8h+var_78]; struct Windows::Networking::UX::IStaticIpConfig *
0x18005cb56  mov     rdx, rbx; struct _WLAN_PROFILE_IP_CONFIGURATION *
0x18005cb59  call    ?_ParseIpFromConfig@CWiFiProfile@Internal@UX@Networking@Windows@@AEAAJPEAU_WLAN_PROFILE_IP_CONFIGURATION@@PEAUIStaticIpConfig@345@@Z; Windows::Networking::UX::Internal::CWiFiProfile::_ParseIpFromConfig(_WLAN_PROFILE_IP_CONFIGURATION *,Windows::Networking::UX::IStaticIpConfig *)
0x18005cb5e  mov     edi, eax
0x18005cb60  xor     eax, eax
0x18005cb62  cmp     [rbx+14h], eax
0x18005cb65  jbe     short loc_18005CB74
0x18005cb67  mov     r8, [rsp+0A8h+var_78]; struct Windows::Networking::UX::IStaticIpConfig *
0x18005cb6c  mov     rdx, rbx; struct _WLAN_PROFILE_IP_CONFIGURATION *
0x18005cb6f  call    ?_ParseDnsFromConfig@CWiFiProfile@Internal@UX@Networking@Windows@@AEAAJPEAU_WLAN_PROFILE_IP_CONFIGURATION@@PEAUIStaticIpConfig@345@@Z; Windows::Networking::UX::Internal::CWiFiProfile::_ParseDnsFromConfig(_WLAN_PROFILE_IP_CONFIGURATION *,Windows::Networking::UX::IStaticIpConfig *)
0x18005cb74  test    edi, edi
0x18005cb76  jns     short loc_18005CBCC
0x18005cb78  test    eax, eax
0x18005cb7a  jns     short loc_18005CBCC
0x18005cb7c  mov     rcx, [rsp+0A8h]; this
0x18005cb84  mov     r9d, edi; char *
0x18005cb87  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005cb8e  mov     edx, 100h; void *
0x18005cb93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb98  nop
0x18005cb99  mov     rcx, [rsp+0A8h+pMemory]; pMemory
0x18005cb9e  mov     [rsp+0A8h+pMemory], 0
0x18005cba7  test    rcx, rcx
0x18005cbaa  jz      short loc_18005CBB3
0x18005cbac  call    cs:__imp_WlanFreeMemory
0x18005cbb2  nop
0x18005cbb3  lea     rcx, [rsp+0A8h+var_78]
0x18005cbb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cbbd  nop
0x18005cbbe  lea     rcx, [rsp+0A8h+var_60]
0x18005cbc3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005cbc8  mov     eax, edi
0x18005cbca  jmp     short loc_18005CC21
0x18005cbcc  mov     rcx, [rsp+0A8h+var_78]
0x18005cbd1  test    rcx, rcx
0x18005cbd4  jz      short loc_18005CBE7
0x18005cbd6  mov     rax, [rcx]
0x18005cbd9  mov     rax, [rax+8]
0x18005cbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbe2  mov     rcx, [rsp+0A8h+var_78]
0x18005cbe7  mov     [rsi], rcx
0x18005cbea  mov     rcx, [rsp+0A8h+pMemory]; pMemory
0x18005cbef  mov     [rsp+0A8h+pMemory], 0
0x18005cbf8  test    rcx, rcx
0x18005cbfb  jz      short loc_18005CC04
0x18005cbfd  call    cs:__imp_WlanFreeMemory
0x18005cc03  nop
0x18005cc04  lea     rcx, [rsp+0A8h+var_78]
0x18005cc09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005cc0e  nop
0x18005cc0f  lea     rcx, [rsp+0A8h+var_60]
0x18005cc14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005cc19  xor     eax, eax
0x18005cc1b  jmp     short loc_18005CC21
0x18005cc1d  mov     eax, [rsp+0A8h+var_68]
0x18005cc21  mov     rcx, [rsp+0A8h+var_28]
0x18005cc29  xor     rcx, rsp; StackCookie
0x18005cc2c  call    __security_check_cookie
0x18005cc31  mov     rbx, [rsp+0A8h+arg_18]
0x18005cc39  add     rsp, 90h
0x18005cc40  pop     r14
0x18005cc42  pop     rdi
0x18005cc43  pop     rsi
0x18005cc44  retn
```
