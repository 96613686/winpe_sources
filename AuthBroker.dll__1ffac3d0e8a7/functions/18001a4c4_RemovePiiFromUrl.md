# RemovePiiFromUrl

- ea: `0x18001a4c4`
- end: `0x18001a623`
- name: `RemovePiiFromUrl`
- size: `351`
- prototype: `void __fastcall(const wchar_t *piiString, wchar_t *noPiiString, unsigned int piiString)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018148`
- `0x18001a920`

## callees

- `0x180003f40`
- `0x1800060b8`
- `0x180016924`
- `0x18001a4c4`
- `0x1800204ee`
- `0x180020520`

## import_xrefs

- `WINHTTP!WinHttpCrackUrl` at `0x18001a565`
- `WINHTTP!WinHttpCrackUrl` at `0x18001a565`
- `WINHTTP!WinHttpCreateUrl` at `0x18001a5e0`
- `WINHTTP!WinHttpCreateUrl` at `0x18001a5e0`

## pseudocode

```c
void __fastcall RemovePiiFromUrl(const wchar_t *piiString, wchar_t *noPiiString, unsigned int a3)
{
  wchar_t *m_ptr; // rbx
  unsigned int tempUrlSize; // [rsp+20h] [rbp-E0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > tempUrl; // [rsp+28h] [rbp-D8h] BYREF
  _WINHTTP_URL_COMPONENTS urlComponents; // [rsp+30h] [rbp-D0h] BYREF
  _WINHTTP_URL_COMPONENTS urlComponentsNoPii; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t schemeName[32]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t serverName[256]; // [rsp+150h] [rbp+50h] BYREF

  *noPiiString = 0;
  memset_0(serverName, 0, sizeof(serverName));
  memset_0(schemeName, 0, sizeof(schemeName));
  memset_0(&urlComponents, 0, sizeof(urlComponents));
  urlComponents.dwStructSize = 104;
  urlComponents.lpszScheme = schemeName;
  urlComponents.dwSchemeLength = 32;
  urlComponents.lpszHostName = serverName;
  urlComponents.dwHostNameLength = 256;
  urlComponents.dwUrlPathLength = 1;
  if ( WinHttpCrackUrl(piiString, 0, 0, &urlComponents) )
  {
    memset_0(&urlComponentsNoPii, 0, sizeof(urlComponentsNoPii));
    urlComponentsNoPii.nPort = urlComponents.nPort;
    urlComponentsNoPii.dwSchemeLength = urlComponents.dwSchemeLength;
    urlComponentsNoPii.lpszScheme = urlComponents.lpszScheme;
    urlComponentsNoPii.dwStructSize = 104;
    urlComponentsNoPii.dwHostNameLength = urlComponents.dwHostNameLength;
    urlComponentsNoPii.lpszHostName = urlComponents.lpszHostName;
    tempUrlSize = 2084;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &tempUrl,
      0,
      0x824u);
    m_ptr = tempUrl.m_ptr;
    if ( tempUrl.m_ptr )
    {
      if ( WinHttpCreateUrl(&urlComponentsNoPii, 0x80000000, tempUrl.m_ptr, &tempUrlSize) )
        StringCchCopyW(noPiiString, 0x824u, m_ptr);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&tempUrl);
  }
}

```

## disassembly

```asm
0x18001a4c4  mov     [rsp-8+arg_10], rbx
0x18001a4c9  push    rbp
0x18001a4ca  push    rsi
0x18001a4cb  push    rdi
0x18001a4cc  lea     rbp, [rsp-260h]
0x18001a4d4  sub     rsp, 360h
0x18001a4db  mov     rax, cs:__security_cookie
0x18001a4e2  xor     rax, rsp
0x18001a4e5  mov     [rbp+270h+var_20], rax
0x18001a4ec  xor     eax, eax
0x18001a4ee  mov     rdi, noPiiString
0x18001a4f1  mov     [noPiiString], ax
0x18001a4f4  mov     rbx, piiString
0x18001a4f7  xor     edx, edx; Val
0x18001a4f9  lea     piiString, [rbp+270h+serverName]; void *
0x18001a4fd  mov     r8d, 200h; Size
0x18001a503  call    memset_0
0x18001a508  xor     edx, edx; Val
0x18001a50a  lea     piiString, [rbp+270h+schemeName]; void *
0x18001a50e  lea     r8d, [noPiiString+40h]; Size
0x18001a512  call    memset_0
0x18001a517  mov     esi, 68h ; 'h'
0x18001a51c  lea     piiString, [rsp+370h+urlComponents]; void *
0x18001a521  mov     r8d, esi; Size
0x18001a524  xor     edx, edx; Val
0x18001a526  call    memset_0
0x18001a52b  lea     rax, [rbp+270h+schemeName]
0x18001a52f  mov     [rsp+370h+urlComponents.dwStructSize], esi
0x18001a533  mov     [rsp+370h+urlComponents.lpszScheme], rax
0x18001a538  lea     r9, [rsp+370h+urlComponents]; lpUrlComponents
0x18001a53d  lea     rax, [rbp+270h+serverName]
0x18001a541  mov     [rsp+370h+urlComponents.dwSchemeLength], 20h ; ' '
0x18001a549  xor     r8d, r8d; dwFlags
0x18001a54c  mov     [rsp+370h+urlComponents.lpszHostName], rax
0x18001a551  xor     edx, edx; dwUrlLength
0x18001a553  mov     [rsp+370h+urlComponents.dwHostNameLength], 100h
0x18001a55b  mov     piiString, rbx; pwszUrl
0x18001a55e  mov     [rbp+270h+urlComponents.dwUrlPathLength], 1
0x18001a565  call    cs:__imp_WinHttpCrackUrl
0x18001a56b  test    eax, eax
0x18001a56d  jz      loc_18001A601
0x18001a573  mov     r8d, esi; Size
0x18001a576  lea     piiString, [rbp+270h+urlComponentsNoPii]; void *
0x18001a57a  xor     edx, edx; Val
0x18001a57c  call    memset_0
0x18001a581  movzx   eax, [rsp+370h+urlComponents.nPort]
0x18001a586  lea     piiString, [rsp+370h+tempUrl]; result
0x18001a58b  mov     [rbp+270h+urlComponentsNoPii.nPort], ax
0x18001a58f  xor     edx, edx; source
0x18001a591  mov     eax, [rsp+370h+urlComponents.dwSchemeLength]
0x18001a595  mov     [rbp+270h+urlComponentsNoPii.dwSchemeLength], eax
0x18001a598  mov     rax, [rsp+370h+urlComponents.lpszScheme]
0x18001a59d  mov     [rbp+270h+urlComponentsNoPii.lpszScheme], rax
0x18001a5a1  mov     eax, [rsp+370h+urlComponents.dwHostNameLength]
0x18001a5a5  mov     [rbp+270h+urlComponentsNoPii.dwStructSize], esi
0x18001a5a8  mov     esi, 824h
0x18001a5ad  mov     [rbp+270h+urlComponentsNoPii.dwHostNameLength], eax
0x18001a5b0  mov     r8d, esi; length
0x18001a5b3  mov     rax, [rsp+370h+urlComponents.lpszHostName]
0x18001a5b8  mov     [rbp+270h+urlComponentsNoPii.lpszHostName], rax
0x18001a5bc  mov     [rsp+370h+tempUrlSize], esi
0x18001a5c0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001a5c5  mov     rbx, [rsp+370h+tempUrl.m_ptr]
0x18001a5ca  test    rbx, rbx
0x18001a5cd  jz      short loc_18001A5F7
0x18001a5cf  lea     r9, [rsp+370h+tempUrlSize]; pdwUrlLength
0x18001a5d4  mov     r8, rbx; pwszUrl
0x18001a5d7  mov     edx, 80000000h; dwFlags
0x18001a5dc  lea     piiString, [rbp+270h+urlComponentsNoPii]; lpUrlComponents
0x18001a5e0  call    cs:__imp_WinHttpCreateUrl
0x18001a5e6  test    eax, eax
0x18001a5e8  jz      short loc_18001A5F7
0x18001a5ea  mov     r8, rbx; pszSrc
0x18001a5ed  mov     edx, esi; cchDest
0x18001a5ef  mov     piiString, rdi; pszDest
0x18001a5f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a5f7  lea     piiString, [rsp+370h+tempUrl]; this
0x18001a5fc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a601  mov     piiString, [rbp+270h+var_20]
0x18001a608  xor     piiString, rsp; StackCookie
0x18001a60b  call    __security_check_cookie
0x18001a610  mov     rbx, [rsp+370h+arg_10]
0x18001a618  add     rsp, 360h
0x18001a61f  pop     rdi
0x18001a620  pop     rsi
0x18001a621  pop     rbp
0x18001a622  retn
```
