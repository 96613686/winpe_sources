# Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendGetRequest(ushort const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *)

- ea: `0x1801a09b0`
- end: `0x1801a0c84`
- name: `?SendGetRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111111PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@@Z`
- size: `724`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this@<rcx>, LPCWSTR pwszObjectName@<rdx>, DWORD dwFlags@<r8d>, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18019f170`

## callees

- `0x180067e34`
- `0x180067e54`
- `0x180080bac`
- `0x18008bf28`
- `0x1800a48b4`
- `0x18019d884`
- `0x18019f0e0`
- `0x1801a09b0`
- `0x1801a0d60`
- `0x1801a0e1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0c0b`
- `WINHTTP!WinHttpOpenRequest` at `0x1801a09ec`
- `WINHTTP!WinHttpOpenRequest` at `0x1801a09ec`
- `WINHTTP!WinHttpSendRequest` at `0x1801a0bfb`
- `WINHTTP!WinHttpSendRequest` at `0x1801a0bfb`

## string_xrefs

- `0x1801a0a18`: `X-Device-Token`
- `0x1801a0a37`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801a0c68`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

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
0x1801a09b0  push    rbx
0x1801a09b2  push    rsi
0x1801a09b3  push    rdi
0x1801a09b4  push    r14
0x1801a09b6  sub     rsp, 48h
0x1801a09ba  mov     [rsp+68h+dwFlags], r8d; dwFlags
0x1801a09bf  lea     r14, [rcx+50h]
0x1801a09c3  mov     r8, rdx; pwszObjectName
0x1801a09c6  mov     [rsp+68h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1801a09cf  mov     rbx, r9
0x1801a09d2  mov     [rsp+68h+pwszReferrer], 0; int
0x1801a09db  mov     rsi, rcx
0x1801a09de  lea     rdx, pwszVerb; "GET"
0x1801a09e5  mov     rcx, [rcx+48h]; hConnect
0x1801a09e9  xor     r9d, r9d; pwszVersion
0x1801a09ec  call    cs:__imp_WinHttpOpenRequest
0x1801a09f3  nop     dword ptr [rax+rax+00h]
0x1801a09f8  mov     rdx, rax
0x1801a09fb  mov     rcx, r14
0x1801a09fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801a0a03  cmp     qword ptr [r14], 0
0x1801a0a07  jz      loc_1801A0C63
0x1801a0a0d  mov     rcx, rbx
0x1801a0a10  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0a15  mov     r8, rax; unsigned __int16 *
0x1801a0a18  lea     rdx, aXDeviceToken; "X-Device-Token"
0x1801a0a1f  mov     rcx, rsi; this
0x1801a0a22  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0a27  mov     ebx, eax
0x1801a0a29  test    eax, eax
0x1801a0a2b  jns     short loc_1801A0A4D
0x1801a0a2d  mov     edx, 1D7h; void *
0x1801a0a32  mov     rcx, [rsp+68h]; this
0x1801a0a37  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a0a3e  mov     r9d, ebx; char *
0x1801a0a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a0a46  mov     eax, ebx
0x1801a0a48  jmp     loc_1801A0C79
0x1801a0a4d  mov     rcx, [rsp+68h+arg_20]
0x1801a0a55  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0a5a  mov     r8, rax; unsigned __int16 *
0x1801a0a5d  lea     rdx, aMsCv; "MS-CV"
0x1801a0a64  mov     rcx, rsi; this
0x1801a0a67  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0a6c  mov     ebx, eax
0x1801a0a6e  test    eax, eax
0x1801a0a70  jns     short loc_1801A0A79
0x1801a0a72  mov     edx, 1DAh
0x1801a0a77  jmp     short loc_1801A0A32
0x1801a0a79  mov     dl, 1
0x1801a0a7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotRestoration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration> `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl(void)'::`2'::impl
0x1801a0a82  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801a0a87  mov     rcx, [rsp+68h+arg_28]
0x1801a0a8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0a94  mov     r8, rax; unsigned __int16 *
0x1801a0a97  lea     rdx, aXHardwareHash; "X-Hardware-Hash"
0x1801a0a9e  mov     rcx, rsi; this
0x1801a0aa1  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0aa6  mov     ebx, eax
0x1801a0aa8  test    eax, eax
0x1801a0aaa  jns     short loc_1801A0AB6
0x1801a0aac  mov     edx, 1DFh
0x1801a0ab1  jmp     loc_1801A0A32
0x1801a0ab6  mov     rcx, [rsp+68h+arg_30]
0x1801a0abe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0ac3  mov     r8, rax; unsigned __int16 *
0x1801a0ac6  lea     rdx, aXDeviceManufac; "X-Device-Manufacturer"
0x1801a0acd  mov     rcx, rsi; this
0x1801a0ad0  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0ad5  mov     ebx, eax
0x1801a0ad7  test    eax, eax
0x1801a0ad9  jns     short loc_1801A0AE5
0x1801a0adb  mov     edx, 1E2h
0x1801a0ae0  jmp     loc_1801A0A32
0x1801a0ae5  mov     rcx, [rsp+68h+arg_38]
0x1801a0aed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0af2  mov     r8, rax; unsigned __int16 *
0x1801a0af5  lea     rdx, aXDeviceModel; "X-Device-Model"
0x1801a0afc  mov     rcx, rsi; this
0x1801a0aff  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0b04  mov     ebx, eax
0x1801a0b06  test    eax, eax
0x1801a0b08  jns     short loc_1801A0B14
0x1801a0b0a  mov     edx, 1E3h
0x1801a0b0f  jmp     loc_1801A0A32
0x1801a0b14  mov     rcx, [rsp+68h+arg_40]
0x1801a0b1c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0b21  mov     r8, rax; unsigned __int16 *
0x1801a0b24  lea     rdx, aXOsversion; "X-OsVersion"
0x1801a0b2b  mov     rcx, rsi; this
0x1801a0b2e  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0b33  mov     ebx, eax
0x1801a0b35  test    eax, eax
0x1801a0b37  jns     short loc_1801A0B43
0x1801a0b39  mov     edx, 1E4h
0x1801a0b3e  jmp     loc_1801A0A32
0x1801a0b43  mov     rcx, [rsp+68h+arg_48]
0x1801a0b4b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0b50  mov     r8, rax; unsigned __int16 *
0x1801a0b53  lea     rdx, aXOsedition; "X-OsEdition"
0x1801a0b5a  mov     rcx, rsi; this
0x1801a0b5d  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0b62  mov     ebx, eax
0x1801a0b64  test    eax, eax
0x1801a0b66  jns     short loc_1801A0B72
0x1801a0b68  mov     edx, 1E5h
0x1801a0b6d  jmp     loc_1801A0A32
0x1801a0b72  mov     rax, [rsp+68h+arg_50]
0x1801a0b7a  test    rax, rax
0x1801a0b7d  jz      short loc_1801A0BD7
0x1801a0b7f  mov     rax, [rax]
0x1801a0b82  mov     rax, [rax]
0x1801a0b85  mov     [rsp+68h+arg_0], rax
0x1801a0b8a  cmp     byte ptr [rax+19h], 0
0x1801a0b8e  jnz     short loc_1801A0BD7
0x1801a0b90  lea     rbx, [rax+20h]
0x1801a0b94  lea     rcx, [rbx+20h]
0x1801a0b98  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0b9d  mov     rcx, rbx
0x1801a0ba0  mov     rdi, rax
0x1801a0ba3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0ba8  mov     r8, rdi; unsigned __int16 *
0x1801a0bab  mov     rdx, rax; unsigned __int16 *
0x1801a0bae  mov     rcx, rsi; this
0x1801a0bb1  call    ?AddHeaderToRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest(ushort const *,ushort const *)
0x1801a0bb6  mov     ebx, eax
0x1801a0bb8  test    eax, eax
0x1801a0bba  js      short loc_1801A0BCD
0x1801a0bbc  lea     rcx, [rsp+68h+arg_0]
0x1801a0bc1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x1801a0bc6  mov     rax, [rsp+68h+arg_0]
0x1801a0bcb  jmp     short loc_1801A0B8A
0x1801a0bcd  mov     edx, 1ECh
0x1801a0bd2  jmp     loc_1801A0A32
0x1801a0bd7  mov     rcx, [r14]; hRequest
0x1801a0bda  xor     r9d, r9d; lpOptional
0x1801a0bdd  mov     qword ptr [rsp+68h+dwFlags], 0; dwContext
0x1801a0be6  xor     r8d, r8d; dwHeadersLength
0x1801a0be9  mov     dword ptr [rsp+68h+ppwszAcceptTypes], 0; dwTotalLength
0x1801a0bf1  xor     edx, edx; lpszHeaders
0x1801a0bf3  mov     dword ptr [rsp+68h+pwszReferrer], 0; dwOptionalLength
0x1801a0bfb  call    cs:__imp_WinHttpSendRequest
0x1801a0c02  nop     dword ptr [rax+rax+00h]
0x1801a0c07  test    eax, eax
0x1801a0c09  jnz     short loc_1801A0C47
0x1801a0c0b  call    cs:__imp_GetLastError
0x1801a0c12  nop     dword ptr [rax+rax+00h]
0x1801a0c17  mov     ebx, eax
0x1801a0c19  test    eax, eax
0x1801a0c1b  jle     short loc_1801A0C26
0x1801a0c1d  movzx   ebx, ax
0x1801a0c20  or      ebx, 80070000h
0x1801a0c26  mov     ecx, ebx; int
0x1801a0c28  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x1801a0c2d  test    al, al
0x1801a0c2f  jnz     loc_1801A0A46
0x1801a0c35  test    ebx, ebx
0x1801a0c37  jns     loc_1801A0A46
0x1801a0c3d  mov     edx, 1FBh
0x1801a0c42  jmp     loc_1801A0A32
0x1801a0c47  mov     rcx, rsi; this
0x1801a0c4a  call    ?VerifyResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::VerifyResponse(void)
0x1801a0c4f  mov     ebx, eax
0x1801a0c51  test    eax, eax
0x1801a0c53  jns     short loc_1801A0C5F
0x1801a0c55  mov     edx, 1FEh
0x1801a0c5a  jmp     loc_1801A0A32
0x1801a0c5f  xor     eax, eax
0x1801a0c61  jmp     short loc_1801A0C79
0x1801a0c63  mov     rcx, [rsp+68h]; this
0x1801a0c68  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a0c6f  mov     edx, 1D4h; void *
0x1801a0c74  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801a0c79  add     rsp, 48h
0x1801a0c7d  pop     r14
0x1801a0c7f  pop     rdi
0x1801a0c80  pop     rsi
0x1801a0c81  pop     rbx
0x1801a0c82  retn
```
