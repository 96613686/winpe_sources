# Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendGetRequest(ushort const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *)

- ea: `0x18019b5c8`
- end: `0x18019b889`
- name: `?SendGetRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111111PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@@Z`
- size: `705`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this@<rcx>, LPCWSTR pwszObjectName@<rdx>, DWORD dwFlags@<r8d>, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180199ddc`

## callees

- `0x180067a34`
- `0x180067a54`
- `0x18008019c`
- `0x18008afec`
- `0x1800a3264`
- `0x180198634`
- `0x180199d50`
- `0x18019b5c8`
- `0x18019b95c`
- `0x18019ba78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019b817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019b817`
- `WINHTTP!WinHttpOpenRequest` at `0x18019b604`
- `WINHTTP!WinHttpOpenRequest` at `0x18019b604`
- `WINHTTP!WinHttpSendRequest` at `0x18019b80d`
- `WINHTTP!WinHttpSendRequest` at `0x18019b80d`

## string_xrefs

- `0x18019b62a`: `X-Device-Token`
- `0x18019b649`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019b86e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendGetRequest(
        HINTERNET *this,
        LPCWSTR pwszObjectName,
        DWORD dwFlags,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 **a11)
{
  HINTERNET *v11; // r14
  HINTERNET v14; // rax
  const char *v15; // r9
  const unsigned __int16 *v16; // rax
  signed int v17; // ebx
  __int64 v18; // rdx
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  const unsigned __int16 *v22; // rax
  const unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // rax
  const unsigned __int16 *v25; // rax
  const unsigned __int16 *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rbx
  const unsigned __int16 *v29; // rdi
  const unsigned __int16 *v30; // rax
  signed int LastError; // eax
  int pwszReferrer; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v34; // [rsp+70h] [rbp+8h] BYREF

  v11 = this + 10;
  v14 = WinHttpOpenRequest(this[9], L"GET", pwszObjectName, 0, 0, 0, dwFlags);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    v11,
    v14);
  if ( !*v11 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1D4,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v15);
  v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"X-Device-Token",
          v16);
  if ( v17 < 0 )
  {
    v18 = 471;
    goto LABEL_4;
  }
  v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"MS-CV",
          v20);
  if ( v17 < 0 )
  {
    v18 = 474;
    goto LABEL_4;
  }
  LOBYTE(v21) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl'::`2'::impl,
    v21);
  v22 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"X-Hardware-Hash",
          v22);
  if ( v17 < 0 )
  {
    v18 = 479;
    goto LABEL_4;
  }
  v23 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a7);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"X-Device-Manufacturer",
          v23);
  if ( v17 < 0 )
  {
    v18 = 482;
    goto LABEL_4;
  }
  v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a8);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"X-Device-Model",
          v24);
  if ( v17 < 0 )
  {
    v18 = 483;
    goto LABEL_4;
  }
  v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a9);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"X-OsVersion",
          v25);
  if ( v17 < 0 )
  {
    v18 = 484;
    goto LABEL_4;
  }
  v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a10);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
          L"X-OsEdition",
          v26);
  if ( v17 < 0 )
  {
    v18 = 485;
    goto LABEL_4;
  }
  if ( a11 )
  {
    v27 = **a11;
    v34 = v27;
    while ( !*(_BYTE *)(v27 + 25) )
    {
      v28 = v27 + 32;
      v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27 + 64);
      v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
      v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(
              (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this,
              v30,
              v29);
      if ( v17 < 0 )
      {
        v18 = 492;
        goto LABEL_4;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(&v34);
      v27 = v34;
    }
  }
  if ( !WinHttpSendRequest(*v11, 0, 0, 0, 0, 0, 0) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v17) || v17 >= 0 )
      return (unsigned int)v17;
    v18 = 507;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v17,
      pwszReferrer);
    return (unsigned int)v17;
  }
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)this);
  if ( v17 < 0 )
  {
    v18 = 510;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18019b5c8  push    rbx
0x18019b5ca  push    rsi
0x18019b5cb  push    rdi
0x18019b5cc  push    r14
0x18019b5ce  sub     rsp, 48h
0x18019b5d2  mov     [rsp+68h+dwFlags], r8d; dwFlags
0x18019b5d7  lea     r14, [rcx+50h]
0x18019b5db  mov     r8, rdx; pwszObjectName
0x18019b5de  mov     [rsp+68h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18019b5e7  mov     rbx, r9
0x18019b5ea  mov     [rsp+68h+pwszReferrer], 0; int
0x18019b5f3  mov     rsi, rcx
0x18019b5f6  lea     rdx, pwszVerb; "GET"
0x18019b5fd  mov     rcx, [rcx+48h]; hConnect
0x18019b601  xor     r9d, r9d; pwszVersion
0x18019b604  call    cs:__imp_WinHttpOpenRequest
0x18019b60a  mov     rdx, rax
0x18019b60d  mov     rcx, r14
0x18019b610  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18019b615  cmp     qword ptr [r14], 0
0x18019b619  jz      loc_18019B869
0x18019b61f  mov     rcx, rbx
0x18019b622  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b627  mov     r8, rax; unsigned __int16 *
0x18019b62a  lea     rdx, aXDeviceToken; "X-Device-Token"
0x18019b631  mov     rcx, rsi; this
0x18019b634  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b639  mov     ebx, eax
0x18019b63b  test    eax, eax
0x18019b63d  jns     short loc_18019B65F
0x18019b63f  mov     edx, 1D7h; void *
0x18019b644  mov     rcx, [rsp+68h]; this
0x18019b649  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b650  mov     r9d, ebx; char *
0x18019b653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019b658  mov     eax, ebx
0x18019b65a  jmp     loc_18019B87F
0x18019b65f  mov     rcx, [rsp+68h+arg_20]
0x18019b667  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b66c  mov     r8, rax; unsigned __int16 *
0x18019b66f  lea     rdx, aMsCv; "MS-CV"
0x18019b676  mov     rcx, rsi; this
0x18019b679  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b67e  mov     ebx, eax
0x18019b680  test    eax, eax
0x18019b682  jns     short loc_18019B68B
0x18019b684  mov     edx, 1DAh
0x18019b689  jmp     short loc_18019B644
0x18019b68b  mov     dl, 1
0x18019b68d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotRestoration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration> `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl(void)'::`2'::impl
0x18019b694  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18019b699  mov     rcx, [rsp+68h+arg_28]
0x18019b6a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b6a6  mov     r8, rax; unsigned __int16 *
0x18019b6a9  lea     rdx, aXHardwareHash; "X-Hardware-Hash"
0x18019b6b0  mov     rcx, rsi; this
0x18019b6b3  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b6b8  mov     ebx, eax
0x18019b6ba  test    eax, eax
0x18019b6bc  jns     short loc_18019B6C8
0x18019b6be  mov     edx, 1DFh
0x18019b6c3  jmp     loc_18019B644
0x18019b6c8  mov     rcx, [rsp+68h+arg_30]
0x18019b6d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b6d5  mov     r8, rax; unsigned __int16 *
0x18019b6d8  lea     rdx, aXDeviceManufac; "X-Device-Manufacturer"
0x18019b6df  mov     rcx, rsi; this
0x18019b6e2  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b6e7  mov     ebx, eax
0x18019b6e9  test    eax, eax
0x18019b6eb  jns     short loc_18019B6F7
0x18019b6ed  mov     edx, 1E2h
0x18019b6f2  jmp     loc_18019B644
0x18019b6f7  mov     rcx, [rsp+68h+arg_38]
0x18019b6ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b704  mov     r8, rax; unsigned __int16 *
0x18019b707  lea     rdx, aXDeviceModel; "X-Device-Model"
0x18019b70e  mov     rcx, rsi; this
0x18019b711  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b716  mov     ebx, eax
0x18019b718  test    eax, eax
0x18019b71a  jns     short loc_18019B726
0x18019b71c  mov     edx, 1E3h
0x18019b721  jmp     loc_18019B644
0x18019b726  mov     rcx, [rsp+68h+arg_40]
0x18019b72e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b733  mov     r8, rax; unsigned __int16 *
0x18019b736  lea     rdx, aXOsversion; "X-OsVersion"
0x18019b73d  mov     rcx, rsi; this
0x18019b740  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b745  mov     ebx, eax
0x18019b747  test    eax, eax
0x18019b749  jns     short loc_18019B755
0x18019b74b  mov     edx, 1E4h
0x18019b750  jmp     loc_18019B644
0x18019b755  mov     rcx, [rsp+68h+arg_48]
0x18019b75d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b762  mov     r8, rax; unsigned __int16 *
0x18019b765  lea     rdx, aXOsedition; "X-OsEdition"
0x18019b76c  mov     rcx, rsi; this
0x18019b76f  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b774  mov     ebx, eax
0x18019b776  test    eax, eax
0x18019b778  jns     short loc_18019B784
0x18019b77a  mov     edx, 1E5h
0x18019b77f  jmp     loc_18019B644
0x18019b784  mov     rax, [rsp+68h+arg_50]
0x18019b78c  test    rax, rax
0x18019b78f  jz      short loc_18019B7E9
0x18019b791  mov     rax, [rax]
0x18019b794  mov     rax, [rax]
0x18019b797  mov     [rsp+68h+arg_0], rax
0x18019b79c  cmp     byte ptr [rax+19h], 0
0x18019b7a0  jnz     short loc_18019B7E9
0x18019b7a2  lea     rbx, [rax+20h]
0x18019b7a6  lea     rcx, [rbx+20h]
0x18019b7aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b7af  mov     rcx, rbx
0x18019b7b2  mov     rdi, rax
0x18019b7b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019b7ba  mov     r8, rdi; unsigned __int16 *
0x18019b7bd  mov     rdx, rax; unsigned __int16 *
0x18019b7c0  mov     rcx, rsi; this
0x18019b7c3  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x18019b7c8  mov     ebx, eax
0x18019b7ca  test    eax, eax
0x18019b7cc  js      short loc_18019B7DF
0x18019b7ce  lea     rcx, [rsp+68h+arg_0]
0x18019b7d3  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x18019b7d8  mov     rax, [rsp+68h+arg_0]
0x18019b7dd  jmp     short loc_18019B79C
0x18019b7df  mov     edx, 1ECh
0x18019b7e4  jmp     loc_18019B644
0x18019b7e9  mov     rcx, [r14]; hRequest
0x18019b7ec  xor     r9d, r9d; lpOptional
0x18019b7ef  mov     qword ptr [rsp+68h+dwFlags], 0; dwContext
0x18019b7f8  xor     r8d, r8d; dwHeadersLength
0x18019b7fb  mov     dword ptr [rsp+68h+ppwszAcceptTypes], 0; dwTotalLength
0x18019b803  xor     edx, edx; lpszHeaders
0x18019b805  mov     dword ptr [rsp+68h+pwszReferrer], 0; dwOptionalLength
0x18019b80d  call    cs:__imp_WinHttpSendRequest
0x18019b813  test    eax, eax
0x18019b815  jnz     short loc_18019B84D
0x18019b817  call    cs:__imp_GetLastError
0x18019b81d  mov     ebx, eax
0x18019b81f  test    eax, eax
0x18019b821  jle     short loc_18019B82C
0x18019b823  movzx   ebx, ax
0x18019b826  or      ebx, 80070000h
0x18019b82c  mov     ecx, ebx; int
0x18019b82e  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x18019b833  test    al, al
0x18019b835  jnz     loc_18019B658
0x18019b83b  test    ebx, ebx
0x18019b83d  jns     loc_18019B658
0x18019b843  mov     edx, 1FBh
0x18019b848  jmp     loc_18019B644
0x18019b84d  mov     rcx, rsi; this
0x18019b850  call    ?VerifyResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(void)
0x18019b855  mov     ebx, eax
0x18019b857  test    eax, eax
0x18019b859  jns     short loc_18019B865
0x18019b85b  mov     edx, 1FEh
0x18019b860  jmp     loc_18019B644
0x18019b865  xor     eax, eax
0x18019b867  jmp     short loc_18019B87F
0x18019b869  mov     rcx, [rsp+68h]; this
0x18019b86e  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019b875  mov     edx, 1D4h; void *
0x18019b87a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019b87f  add     rsp, 48h
0x18019b883  pop     r14
0x18019b885  pop     rdi
0x18019b886  pop     rsi
0x18019b887  pop     rbx
0x18019b888  retn
```
