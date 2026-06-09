# Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddPortToUrl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801b5a60`
- end: `0x1801b5c60`
- name: `?AddPortToUrl@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV56@@Z`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801d40fc`

## callees

- `0x18000c504`
- `0x180067e54`
- `0x180080bac`
- `0x180080c10`
- `0x18008aea8`
- `0x18008d290`
- `0x1800a35f8`
- `0x1801b5a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5bfe`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b5b46`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b5bee`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b5b46`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b5bee`
- `WINHTTP!WinHttpCrackUrl` at `0x1801b5af2`
- `WINHTTP!WinHttpCrackUrl` at `0x1801b5af2`

## string_xrefs

- `0x1801b5a97`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b5bb9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddPortToUrl(__int64 a1, DWORD a2, __int64 a3)
{
  const char *v5; // r9
  signed int result; // eax
  const WCHAR *v7; // rax
  LPWSTR v8; // rbx
  signed int LastError; // eax
  unsigned int v10; // ebx
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+20h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  DWORD pdwUrlLength; // [rsp+A8h] [rbp+10h] BYREF
  LPWSTR pwszUrl; // [rsp+B8h] [rbp+20h] BYREF

  pdwUrlLength = a2;
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      memset_0(&UrlComponents, 0, sizeof(UrlComponents));
      UrlComponents.dwStructSize = 104;
      UrlComponents.dwSchemeLength = -1;
      UrlComponents.dwHostNameLength = -1;
      UrlComponents.dwUrlPathLength = -1;
      UrlComponents.dwExtraInfoLength = -1;
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      if ( WinHttpCrackUrl(v7, 0, 0, &UrlComponents) )
      {
        UrlComponents.nPort = 443;
        pdwUrlLength = 0;
        if ( WinHttpCreateUrl(&UrlComponents, 0, 0, &pdwUrlLength) || GetLastError() == 122 )
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pwszUrl,
            0,
            pdwUrlLength);
          v8 = pwszUrl;
          if ( pwszUrl )
          {
            if ( WinHttpCreateUrl(&UrlComponents, 0, pwszUrl, &pdwUrlLength) )
            {
              std::wstring::assign(a3, v8);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pwszUrl);
              result = 0;
            }
            else
            {
              LastError = GetLastError();
              v10 = LastError;
              if ( LastError > 0 )
                v10 = (unsigned __int16)LastError | 0x80070000;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pwszUrl);
              result = v10;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
              (const char *)0x8007000ELL,
              UrlComponents.dwStructSize);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pwszUrl);
            result = -2147024882;
          }
        }
        else
        {
          result = GetLastError();
          if ( result > 0 )
            result = (unsigned __int16)result | 0x80070000;
        }
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
        (const char *)0x80004001LL,
        UrlComponents.dwStructSize);
      result = -2147467263;
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0xC5,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\httpnetworkwrapper.cpp",
             v5);
  }
  return result;
}

```

## disassembly

```asm
0x1801b5a60  mov     [rsp+arg_0], rbx
0x1801b5a65  mov     [rsp+pdwUrlLength], edx
0x1801b5a69  push    rdi
0x1801b5a6a  sub     rsp, 90h
0x1801b5a71  mov     rdi, r8
0x1801b5a74  mov     rbx, rcx
0x1801b5a77  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b5a7e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b5a83  test    al, al
0x1801b5a85  jnz     short loc_1801B5AAF
0x1801b5a87  mov     rcx, [rsp+98h]; this
0x1801b5a8f  mov     ebx, 80004001h
0x1801b5a94  mov     r9d, ebx; char *
0x1801b5a97  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b5a9e  mov     edx, 0A0h; void *
0x1801b5aa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5aa8  mov     eax, ebx
0x1801b5aaa  jmp     loc_1801B5C4E
0x1801b5aaf  xor     edx, edx; Val
0x1801b5ab1  lea     r8d, [rdx+68h]; Size
0x1801b5ab5  lea     rcx, [rsp+98h+UrlComponents]; void *
0x1801b5aba  call    memset_0
0x1801b5abf  mov     [rsp+98h+UrlComponents.dwStructSize], 68h ; 'h'; int
0x1801b5ac7  or      eax, 0FFFFFFFFh
0x1801b5aca  mov     [rsp+98h+UrlComponents.dwSchemeLength], eax
0x1801b5ace  mov     [rsp+98h+UrlComponents.dwHostNameLength], eax
0x1801b5ad2  mov     [rsp+98h+UrlComponents.dwUrlPathLength], eax
0x1801b5ad6  mov     [rsp+98h+UrlComponents.dwExtraInfoLength], eax
0x1801b5add  mov     rcx, rbx
0x1801b5ae0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b5ae5  lea     r9, [rsp+98h+UrlComponents]; lpUrlComponents
0x1801b5aea  xor     r8d, r8d; dwFlags
0x1801b5aed  xor     edx, edx; dwUrlLength
0x1801b5aef  mov     rcx, rax; pwszUrl
0x1801b5af2  call    cs:__imp_WinHttpCrackUrl
0x1801b5af9  nop     dword ptr [rax+rax+00h]
0x1801b5afe  test    eax, eax
0x1801b5b00  jnz     short loc_1801B5B1F
0x1801b5b02  call    cs:__imp_GetLastError
0x1801b5b09  nop     dword ptr [rax+rax+00h]
0x1801b5b0e  test    eax, eax
0x1801b5b10  jle     short loc_1801B5B1A
0x1801b5b12  movzx   eax, ax
0x1801b5b15  or      eax, 80070000h
0x1801b5b1a  jmp     loc_1801B5C4E
0x1801b5b1f  mov     eax, 1BBh
0x1801b5b24  mov     [rsp+98h+UrlComponents.nPort], ax
0x1801b5b29  mov     [rsp+98h+pdwUrlLength], 0
0x1801b5b34  lea     r9, [rsp+98h+pdwUrlLength]; pdwUrlLength
0x1801b5b3c  xor     r8d, r8d; pwszUrl
0x1801b5b3f  xor     edx, edx; dwFlags
0x1801b5b41  lea     rcx, [rsp+98h+UrlComponents]; lpUrlComponents
0x1801b5b46  call    cs:__imp_WinHttpCreateUrl
0x1801b5b4d  nop     dword ptr [rax+rax+00h]
0x1801b5b52  test    eax, eax
0x1801b5b54  jnz     short loc_1801B5B84
0x1801b5b56  call    cs:__imp_GetLastError
0x1801b5b5d  nop     dword ptr [rax+rax+00h]
0x1801b5b62  cmp     eax, 7Ah ; 'z'
0x1801b5b65  jz      short loc_1801B5B84
0x1801b5b67  call    cs:__imp_GetLastError
0x1801b5b6e  nop     dword ptr [rax+rax+00h]
0x1801b5b73  test    eax, eax
0x1801b5b75  jle     short loc_1801B5B7F
0x1801b5b77  movzx   eax, ax
0x1801b5b7a  or      eax, 80070000h
0x1801b5b7f  jmp     loc_1801B5C4E
0x1801b5b84  mov     r8d, [rsp+98h+pdwUrlLength]
0x1801b5b8c  xor     edx, edx
0x1801b5b8e  lea     rcx, [rsp+98h+pwszUrl]
0x1801b5b96  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801b5b9b  nop
0x1801b5b9c  mov     rbx, [rsp+98h+pwszUrl]
0x1801b5ba4  test    rbx, rbx
0x1801b5ba7  jnz     short loc_1801B5BDC
0x1801b5ba9  mov     rcx, [rsp+98h]; this
0x1801b5bb1  mov     ebx, 8007000Eh
0x1801b5bb6  mov     r9d, ebx; char *
0x1801b5bb9  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b5bc0  mov     edx, 0BAh; void *
0x1801b5bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5bca  nop
0x1801b5bcb  lea     rcx, [rsp+98h+pwszUrl]
0x1801b5bd3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b5bd8  mov     eax, ebx
0x1801b5bda  jmp     short loc_1801B5C4E
0x1801b5bdc  lea     r9, [rsp+98h+pdwUrlLength]; pdwUrlLength
0x1801b5be4  mov     r8, rbx; pwszUrl
0x1801b5be7  xor     edx, edx; dwFlags
0x1801b5be9  lea     rcx, [rsp+98h+UrlComponents]; lpUrlComponents
0x1801b5bee  call    cs:__imp_WinHttpCreateUrl
0x1801b5bf5  nop     dword ptr [rax+rax+00h]
0x1801b5bfa  test    eax, eax
0x1801b5bfc  jnz     short loc_1801B5C2A
0x1801b5bfe  call    cs:__imp_GetLastError
0x1801b5c05  nop     dword ptr [rax+rax+00h]
0x1801b5c0a  mov     ebx, eax
0x1801b5c0c  test    eax, eax
0x1801b5c0e  jle     short loc_1801B5C19
0x1801b5c10  movzx   ebx, ax
0x1801b5c13  or      ebx, 80070000h
0x1801b5c19  lea     rcx, [rsp+98h+pwszUrl]
0x1801b5c21  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b5c26  mov     eax, ebx
0x1801b5c28  jmp     short loc_1801B5C4E
0x1801b5c2a  mov     rdx, rbx
0x1801b5c2d  mov     rcx, rdi
0x1801b5c30  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b5c35  nop
0x1801b5c36  lea     rcx, [rsp+98h+pwszUrl]
0x1801b5c3e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b5c43  xor     eax, eax
0x1801b5c45  jmp     short loc_1801B5C4E
0x1801b5c47  mov     eax, [rsp+98h+pdwUrlLength]
0x1801b5c4e  mov     rbx, [rsp+98h+arg_0]
0x1801b5c56  add     rsp, 90h
0x1801b5c5d  pop     rdi
0x1801b5c5e  retn
```
