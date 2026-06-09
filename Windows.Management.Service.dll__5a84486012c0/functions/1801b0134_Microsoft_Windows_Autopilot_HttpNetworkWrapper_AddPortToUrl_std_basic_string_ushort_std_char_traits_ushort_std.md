# Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddPortToUrl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801b0134`
- end: `0x1801b030a`
- name: `?AddPortToUrl@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV56@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801ce320`

## callees

- `0x18000c414`
- `0x180067a54`
- `0x18008019c`
- `0x1800801fc`
- `0x180089ff4`
- `0x18008c244`
- `0x1800a1fe4`
- `0x1801b0134`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b01d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b02ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b01d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b02ae`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b020e`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b02a4`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b020e`
- `WINHTTP!WinHttpCreateUrl` at `0x1801b02a4`
- `WINHTTP!WinHttpCrackUrl` at `0x1801b01c6`
- `WINHTTP!WinHttpCrackUrl` at `0x1801b01c6`

## string_xrefs

- `0x1801b016b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b026f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

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
0x1801b0134  mov     [rsp+arg_0], rbx
0x1801b0139  mov     [rsp+pdwUrlLength], edx
0x1801b013d  push    rdi
0x1801b013e  sub     rsp, 90h
0x1801b0145  mov     rdi, r8
0x1801b0148  mov     rbx, rcx
0x1801b014b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801b0152  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801b0157  test    al, al
0x1801b0159  jnz     short loc_1801B0183
0x1801b015b  mov     rcx, [rsp+98h]; this
0x1801b0163  mov     ebx, 80004001h
0x1801b0168  mov     r9d, ebx; char *
0x1801b016b  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0172  mov     edx, 0A0h; void *
0x1801b0177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b017c  mov     eax, ebx
0x1801b017e  jmp     loc_1801B02F8
0x1801b0183  xor     edx, edx; Val
0x1801b0185  lea     r8d, [rdx+68h]; Size
0x1801b0189  lea     rcx, [rsp+98h+UrlComponents]; void *
0x1801b018e  call    memset_0
0x1801b0193  mov     [rsp+98h+UrlComponents.dwStructSize], 68h ; 'h'; int
0x1801b019b  or      eax, 0FFFFFFFFh
0x1801b019e  mov     [rsp+98h+UrlComponents.dwSchemeLength], eax
0x1801b01a2  mov     [rsp+98h+UrlComponents.dwHostNameLength], eax
0x1801b01a6  mov     [rsp+98h+UrlComponents.dwUrlPathLength], eax
0x1801b01aa  mov     [rsp+98h+UrlComponents.dwExtraInfoLength], eax
0x1801b01b1  mov     rcx, rbx
0x1801b01b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b01b9  lea     r9, [rsp+98h+UrlComponents]; lpUrlComponents
0x1801b01be  xor     r8d, r8d; dwFlags
0x1801b01c1  xor     edx, edx; dwUrlLength
0x1801b01c3  mov     rcx, rax; pwszUrl
0x1801b01c6  call    cs:__imp_WinHttpCrackUrl
0x1801b01cc  test    eax, eax
0x1801b01ce  jnz     short loc_1801B01E7
0x1801b01d0  call    cs:__imp_GetLastError
0x1801b01d6  test    eax, eax
0x1801b01d8  jle     short loc_1801B01E2
0x1801b01da  movzx   eax, ax
0x1801b01dd  or      eax, 80070000h
0x1801b01e2  jmp     loc_1801B02F8
0x1801b01e7  mov     eax, 1BBh
0x1801b01ec  mov     [rsp+98h+UrlComponents.nPort], ax
0x1801b01f1  mov     [rsp+98h+pdwUrlLength], 0
0x1801b01fc  lea     r9, [rsp+98h+pdwUrlLength]; pdwUrlLength
0x1801b0204  xor     r8d, r8d; pwszUrl
0x1801b0207  xor     edx, edx; dwFlags
0x1801b0209  lea     rcx, [rsp+98h+UrlComponents]; lpUrlComponents
0x1801b020e  call    cs:__imp_WinHttpCreateUrl
0x1801b0214  test    eax, eax
0x1801b0216  jnz     short loc_1801B023A
0x1801b0218  call    cs:__imp_GetLastError
0x1801b021e  cmp     eax, 7Ah ; 'z'
0x1801b0221  jz      short loc_1801B023A
0x1801b0223  call    cs:__imp_GetLastError
0x1801b0229  test    eax, eax
0x1801b022b  jle     short loc_1801B0235
0x1801b022d  movzx   eax, ax
0x1801b0230  or      eax, 80070000h
0x1801b0235  jmp     loc_1801B02F8
0x1801b023a  mov     r8d, [rsp+98h+pdwUrlLength]
0x1801b0242  xor     edx, edx
0x1801b0244  lea     rcx, [rsp+98h+pwszUrl]
0x1801b024c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801b0251  nop
0x1801b0252  mov     rbx, [rsp+98h+pwszUrl]
0x1801b025a  test    rbx, rbx
0x1801b025d  jnz     short loc_1801B0292
0x1801b025f  mov     rcx, [rsp+98h]; this
0x1801b0267  mov     ebx, 8007000Eh
0x1801b026c  mov     r9d, ebx; char *
0x1801b026f  lea     r8, aOnecoreuapAdmi_81; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b0276  mov     edx, 0BAh; void *
0x1801b027b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b0280  nop
0x1801b0281  lea     rcx, [rsp+98h+pwszUrl]
0x1801b0289  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b028e  mov     eax, ebx
0x1801b0290  jmp     short loc_1801B02F8
0x1801b0292  lea     r9, [rsp+98h+pdwUrlLength]; pdwUrlLength
0x1801b029a  mov     r8, rbx; pwszUrl
0x1801b029d  xor     edx, edx; dwFlags
0x1801b029f  lea     rcx, [rsp+98h+UrlComponents]; lpUrlComponents
0x1801b02a4  call    cs:__imp_WinHttpCreateUrl
0x1801b02aa  test    eax, eax
0x1801b02ac  jnz     short loc_1801B02D4
0x1801b02ae  call    cs:__imp_GetLastError
0x1801b02b4  mov     ebx, eax
0x1801b02b6  test    eax, eax
0x1801b02b8  jle     short loc_1801B02C3
0x1801b02ba  movzx   ebx, ax
0x1801b02bd  or      ebx, 80070000h
0x1801b02c3  lea     rcx, [rsp+98h+pwszUrl]
0x1801b02cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b02d0  mov     eax, ebx
0x1801b02d2  jmp     short loc_1801B02F8
0x1801b02d4  mov     rdx, rbx
0x1801b02d7  mov     rcx, rdi
0x1801b02da  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801b02df  nop
0x1801b02e0  lea     rcx, [rsp+98h+pwszUrl]
0x1801b02e8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801b02ed  xor     eax, eax
0x1801b02ef  jmp     short loc_1801B02F8
0x1801b02f1  mov     eax, [rsp+98h+pdwUrlLength]
0x1801b02f8  mov     rbx, [rsp+98h+arg_0]
0x1801b0300  add     rsp, 90h
0x1801b0307  pop     rdi
0x1801b0308  retn
```
