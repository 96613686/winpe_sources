# OleRegGetUserType

- ea: `0x18001a640`
- end: `0x18001aa85`
- name: `OleRegGetUserType`
- size: `1093`
- prototype: `HRESULT __stdcall(const IID *const clsid, DWORD dwFormOfType, LPOLESTR *pszUserType)`
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180043a30`
- `0x1800450e0`
- `0x18004b870`
- `0x18007e524`
- `0x1800a1474`
- `0x1800a3c28`

## callees

- `0x18001775c`
- `0x1800185ec`
- `0x18001a3c8`
- `0x18001a640`
- `0x18001aad8`
- `0x18001aafc`
- `0x18001b0e4`
- `0x180052390`
- `0x180053014`
- `0x180098e78`
- `0x180098eec`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a8e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a925`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a8e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a925`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18001a953`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18001a9cf`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18001a953`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18001a9cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a787`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18001a87f`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18001a87f`

## string_xrefs

- `0x18001a708`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x18001a7b5`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x18001a80f`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x18001a892`: `com\ole32\ole232\stdimpl\olereg.cpp`

## pseudocode

```c
HRESULT __stdcall OleRegGetUserType(const IID *const clsid, DWORD dwFormOfType, LPOLESTR *pszUserType)
{
  HRESULT String; // ebx
  DWORD v7; // ebx
  DWORD v8; // ebx
  HRESULT v9; // eax
  unsigned int v10; // edx
  const wchar_t *StringRawBuffer; // rax
  HRESULT v12; // eax
  OLECHAR *m_ptr; // rax
  OLECHAR *v14; // rax
  HRESULT v15; // eax
  HRESULT v16; // esi
  OLECHAR *v17; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > allocatedDisplayNameString; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > displayNameStringOrResourceReference; // [rsp+48h] [rbp-B8h] BYREF
  HKEY__ *hkeyClsid; // [rsp+50h] [rbp-B0h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+58h] [rbp-A8h] BYREF
  HKEY__ *hkeyAux; // [rsp+60h] [rbp-A0h] BYREF
  HKEY__ *hkeyAuxWithIndex; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *displayNameString; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szIndex[20]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t szLocalized[512]; // [rsp+A0h] [rbp-60h] BYREF
  void *retaddr; // [rsp+4D8h] [rbp+3D8h]

  allocatedDisplayNameString.m_ptr = 0;
  hkeyClsid = 0;
  hkeyAux = 0;
  hkeyAuxWithIndex = 0;
  memset_0(szLocalized, 0, sizeof(szLocalized));
  if ( !pszUserType )
    return -2147024809;
  *pszUserType = 0;
  oleClassInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         clsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) >= 0 )
  {
    displayNameStringOrResourceReference.m_ptr = 0;
    v7 = dwFormOfType - 1;
    if ( !v7 )
      goto LABEL_14;
    v8 = v7 - 1;
    if ( !v8 )
    {
      v9 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))oleClassInfo.m_ptr->lpVtbl[2].QueryInterface)(
             oleClassInfo.m_ptr,
             &displayNameStringOrResourceReference);
      String = v9;
      if ( v9 < 0 )
      {
        v10 = 323;
        goto LABEL_9;
      }
      goto LABEL_16;
    }
    if ( v8 == 1 )
    {
      v9 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))oleClassInfo.m_ptr->lpVtbl[2].AddRef)(
             oleClassInfo.m_ptr,
             &displayNameStringOrResourceReference);
      String = v9;
      if ( v9 < 0 )
      {
        v10 = 326;
LABEL_9:
        wil::details::in1diag3::Return_Hr(retaddr, v10, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v9);
LABEL_10:
        if ( displayNameStringOrResourceReference.m_ptr )
          WindowsDeleteString(displayNameStringOrResourceReference.m_ptr);
        goto LABEL_34;
      }
    }
    else
    {
LABEL_14:
      v9 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))oleClassInfo.m_ptr->lpVtbl[1].Release)(
             oleClassInfo.m_ptr,
             &displayNameStringOrResourceReference);
      String = v9;
      if ( v9 < 0 )
      {
        v10 = 330;
        goto LABEL_9;
      }
    }
LABEL_16:
    allocatedDisplayNameString.m_ptr = 0;
    displayNameString = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(displayNameStringOrResourceReference.m_ptr, 0);
    v12 = ResolveStringOrResourceReference(0, 0, StringRawBuffer, &allocatedDisplayNameString, &displayNameString);
    String = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x151u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v12);
      if ( allocatedDisplayNameString.m_ptr )
        CoTaskMemFree(allocatedDisplayNameString.m_ptr);
      goto LABEL_10;
    }
    m_ptr = allocatedDisplayNameString.m_ptr;
    if ( allocatedDisplayNameString.m_ptr )
    {
      allocatedDisplayNameString.m_ptr = 0;
      *pszUserType = m_ptr;
    }
    else
    {
      v14 = UtDupString(displayNameString);
      *pszUserType = v14;
      if ( !v14 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x15Bu, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", -2147024882);
        if ( allocatedDisplayNameString.m_ptr )
          CoTaskMemFree(allocatedDisplayNameString.m_ptr);
        if ( displayNameStringOrResourceReference.m_ptr )
          WindowsDeleteString(displayNameStringOrResourceReference.m_ptr);
        String = -2147024882;
        goto LABEL_34;
      }
      if ( allocatedDisplayNameString.m_ptr )
        CoTaskMemFree(allocatedDisplayNameString.m_ptr);
    }
    if ( displayNameStringOrResourceReference.m_ptr )
      WindowsDeleteString(displayNameStringOrResourceReference.m_ptr);
    String = 0;
LABEL_34:
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
    return String;
  }
  v15 = InternalRegOpenClassKey(clsid, 131097, &hkeyClsid);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x160u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v15);
    String = v16;
    goto LABEL_34;
  }
  if ( dwFormOfType == 1 )
    goto $trymain;
  if ( RegOpenKeyExW(hkeyClsid, Com::Catalog::Constants::AuxUserType, 0, 0x20019u, &hkeyAux) )
    goto $trymain;
  StringCchPrintfW(szIndex, 0x14u, L"%d", dwFormOfType);
  if ( RegOpenKeyExW(hkeyAux, szIndex, 0, 0x20019u, &hkeyAuxWithIndex) )
    goto $trymain;
  if ( RegLoadMUIStringW(hkeyAuxWithIndex, L"LocalizedString", szLocalized, 0x400u, 0, 1u, 0) )
  {
    if ( OleRegGetString_0(hkeyAux, dwFormOfType, &allocatedDisplayNameString.m_ptr) >= 0 )
    {
      if ( *allocatedDisplayNameString.m_ptr )
      {
        *pszUserType = allocatedDisplayNameString.m_ptr;
        goto LABEL_49;
      }
      CoTaskMemFree(allocatedDisplayNameString.m_ptr);
      allocatedDisplayNameString.m_ptr = 0;
    }
$trymain:
    if ( !RegLoadMUIStringW(hkeyClsid, L"LocalizedString", szLocalized, 0x400u, 0, 1u, 0) )
      goto LABEL_39;
    String = OleRegGetString(hkeyClsid, 0, &allocatedDisplayNameString.m_ptr);
    if ( String )
      goto $errRtn_9;
    if ( !*allocatedDisplayNameString.m_ptr )
    {
      CoTaskMemFree(allocatedDisplayNameString.m_ptr);
      String = -2147221165;
      goto $errRtn_9;
    }
    *pszUserType = allocatedDisplayNameString.m_ptr;
LABEL_49:
    String = 0;
    goto $errRtn_9;
  }
LABEL_39:
  v17 = UtDupString(szLocalized);
  *pszUserType = v17;
  String = v17 == 0 ? 0x8007000E : 0;
$errRtn_9:
  if ( hkeyClsid )
  {
    RegCloseKey(hkeyClsid);
    hkeyClsid = 0;
  }
  if ( hkeyAux )
  {
    RegCloseKey(hkeyAux);
    hkeyAux = 0;
  }
  if ( hkeyAuxWithIndex )
  {
    RegCloseKey(hkeyAuxWithIndex);
    hkeyAuxWithIndex = 0;
  }
  if ( oleClassInfo.m_ptr )
    ((void (__fastcall *)(IOleClassInfo *))oleClassInfo.m_ptr->lpVtbl->Release)(oleClassInfo.m_ptr);
  return String;
}

```

## disassembly

```asm
0x18001a640  push    rbp
0x18001a642  push    rbx
0x18001a643  push    rsi
0x18001a644  push    rdi
0x18001a645  push    r14
0x18001a647  lea     rbp, [rsp-3B0h]
0x18001a64f  sub     rsp, 4B0h
0x18001a656  mov     rax, cs:__security_cookie
0x18001a65d  xor     rax, rsp
0x18001a660  mov     [rbp+3D0h+var_30], rax
0x18001a667  xor     r14d, r14d
0x18001a66a  mov     rdi, ppszUserType
0x18001a66d  mov     ebx, dwFormOfType
0x18001a66f  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18001a674  mov     rsi, clsid
0x18001a677  mov     [rsp+4D0h+hkeyClsid], r14
0x18001a67c  xor     dwFormOfType, dwFormOfType; Val
0x18001a67e  mov     [rsp+4D0h+hkeyAux], r14
0x18001a683  mov     r8d, 400h; Size
0x18001a689  mov     [rsp+4D0h+hkeyAuxWithIndex], r14
0x18001a68e  lea     clsid, [rbp+3D0h+szLocalized]; void *
0x18001a692  call    memset_0
0x18001a697  test    rdi, rdi
0x18001a69a  jnz     short loc_18001A6A6
0x18001a69c  mov     ebx, 80070057h
0x18001a6a1  jmp     loc_18001AA66
0x18001a6a6  lea     r9, [rsp+4D0h+oleClassInfo]; ppv
0x18001a6ab  mov     [rdi], r14
0x18001a6ae  lea     ppszUserType, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18001a6b5  mov     [rsp+4D0h+oleClassInfo.m_ptr], r14
0x18001a6ba  xor     dwFormOfType, dwFormOfType; pComCatalog
0x18001a6bc  mov     clsid, rsi; clsid
0x18001a6bf  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18001a6c4  test    eax, eax
0x18001a6c6  js      loc_18001A872
0x18001a6cc  mov     [rsp+4D0h+displayNameStringOrResourceReference.m_ptr], r14
0x18001a6d1  sub     ebx, 1
0x18001a6d4  jz      short loc_18001A753
0x18001a6d6  sub     ebx, 1
0x18001a6d9  jz      short loc_18001A730
0x18001a6db  cmp     ebx, 1
0x18001a6de  jnz     short loc_18001A753
0x18001a6e0  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18001a6e5  lea     rdx, [rsp+4D0h+displayNameStringOrResourceReference]
0x18001a6ea  mov     rax, [clsid]
0x18001a6ed  mov     rax, [rax+38h]
0x18001a6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6f6  mov     ebx, eax
0x18001a6f8  test    eax, eax
0x18001a6fa  jns     short loc_18001A776
0x18001a6fc  mov     dwFormOfType, 146h; lineNumber
0x18001a701  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18001a708  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18001a70f  mov     r9d, eax; hr
0x18001a712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a717  mov     clsid, [rsp+4D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18001a71c  test    clsid, clsid
0x18001a71f  jz      loc_18001A8A8
0x18001a725  call    cs:__imp_WindowsDeleteString
0x18001a72b  jmp     loc_18001A8A8
0x18001a730  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18001a735  lea     rdx, [rsp+4D0h+displayNameStringOrResourceReference]
0x18001a73a  mov     rax, [clsid]
0x18001a73d  mov     rax, [rax+30h]
0x18001a741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a746  mov     ebx, eax
0x18001a748  test    eax, eax
0x18001a74a  jns     short loc_18001A776
0x18001a74c  mov     dwFormOfType, 143h
0x18001a751  jmp     short loc_18001A701
0x18001a753  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18001a758  lea     rdx, [rsp+4D0h+displayNameStringOrResourceReference]
0x18001a75d  mov     rax, [clsid]
0x18001a760  mov     rax, [rax+28h]
0x18001a764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a769  mov     ebx, eax
0x18001a76b  test    eax, eax
0x18001a76d  jns     short loc_18001A776
0x18001a76f  mov     dwFormOfType, 14Ah
0x18001a774  jmp     short loc_18001A701
0x18001a776  mov     clsid, [rsp+4D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18001a77b  xor     dwFormOfType, dwFormOfType; length
0x18001a77d  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18001a782  mov     [rsp+4D0h+displayNameString], r14
0x18001a787  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a78d  lea     clsid, [rsp+4D0h+displayNameString]
0x18001a792  xor     dwFormOfType, dwFormOfType; resourceContext
0x18001a794  mov     [rsp+4D0h+result], clsid; result
0x18001a799  lea     r9, [rsp+4D0h+allocatedDisplayNameString]; allocatedResult
0x18001a79e  xor     ecx, ecx; providedResourceManager
0x18001a7a0  mov     ppszUserType, rax; stringOrResourceReference
0x18001a7a3  call    ?ResolveStringOrResourceReference@@YAJPEAUIMrtResourceManager@@PEAUIResourceContext@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAPEBG@Z; ResolveStringOrResourceReference(IMrtResourceManager *,IResourceContext *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * *)
0x18001a7a8  mov     ebx, eax
0x18001a7aa  test    eax, eax
0x18001a7ac  jns     short loc_18001A7E2
0x18001a7ae  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18001a7b5  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18001a7bc  mov     r9d, eax; hr
0x18001a7bf  mov     dwFormOfType, 151h; lineNumber
0x18001a7c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7c9  mov     clsid, [rsp+4D0h+allocatedDisplayNameString.m_ptr]; pv
0x18001a7ce  test    clsid, clsid
0x18001a7d1  jz      loc_18001A717
0x18001a7d7  call    cs:__imp_CoTaskMemFree
0x18001a7dd  jmp     loc_18001A717
0x18001a7e2  mov     rax, [rsp+4D0h+allocatedDisplayNameString.m_ptr]
0x18001a7e7  test    rax, rax
0x18001a7ea  jz      short loc_18001A7F6
0x18001a7ec  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18001a7f1  mov     [rdi], rax
0x18001a7f4  jmp     short loc_18001A85D
0x18001a7f6  mov     clsid, [rsp+4D0h+displayNameString]; lpszIn
0x18001a7fb  call    ?UtDupString@@YAPEAGPEBG@Z; UtDupString(ushort const *)
0x18001a800  mov     [rdi], rax
0x18001a803  test    rax, rax
0x18001a806  jnz     short loc_18001A84D
0x18001a808  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18001a80f  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18001a816  mov     r9d, 8007000Eh; hr
0x18001a81c  mov     dwFormOfType, 15Bh; lineNumber
0x18001a821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a826  mov     clsid, [rsp+4D0h+allocatedDisplayNameString.m_ptr]; pv
0x18001a82b  test    clsid, clsid
0x18001a82e  jz      short loc_18001A836
0x18001a830  call    cs:__imp_CoTaskMemFree
0x18001a836  mov     clsid, [rsp+4D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18001a83b  test    clsid, clsid
0x18001a83e  jz      short loc_18001A846
0x18001a840  call    cs:__imp_WindowsDeleteString
0x18001a846  mov     ebx, 8007000Eh
0x18001a84b  jmp     short loc_18001A8A8
0x18001a84d  mov     clsid, [rsp+4D0h+allocatedDisplayNameString.m_ptr]; pv
0x18001a852  test    clsid, clsid
0x18001a855  jz      short loc_18001A85D
0x18001a857  call    cs:__imp_CoTaskMemFree
0x18001a85d  mov     clsid, [rsp+4D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18001a862  test    clsid, clsid
0x18001a865  jz      short loc_18001A86D
0x18001a867  call    cs:__imp_WindowsDeleteString
0x18001a86d  mov     ebx, r14d
0x18001a870  jmp     short loc_18001A8A8
0x18001a872  lea     ppszUserType, [rsp+4D0h+hkeyClsid]
0x18001a877  mov     dwFormOfType, 20019h
0x18001a87c  mov     clsid, rsi
0x18001a87f  call    cs:__imp_InternalRegOpenClassKey
0x18001a885  mov     esi, eax
0x18001a887  test    eax, eax
0x18001a889  jns     short loc_18001A8B7
0x18001a88b  mov     clsid, [rbp+3D8h]; callerReturnAddress
0x18001a892  lea     ppszUserType, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18001a899  mov     r9d, eax; hr
0x18001a89c  mov     dwFormOfType, 160h; lineNumber
0x18001a8a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a8a6  mov     ebx, esi
0x18001a8a8  lea     clsid, [rsp+4D0h+oleClassInfo]; this
0x18001a8ad  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18001a8b2  jmp     loc_18001AA66
0x18001a8b7  mov     esi, 1
0x18001a8bc  cmp     ebx, esi
0x18001a8be  jz      $trymain
0x18001a8c4  mov     clsid, [rsp+4D0h+hkeyClsid]; hKey
0x18001a8c9  lea     rax, [rsp+4D0h+hkeyAux]
0x18001a8ce  mov     r9d, 20019h; samDesired
0x18001a8d4  mov     [rsp+4D0h+result], rax; phkResult
0x18001a8d9  xor     r8d, r8d; ulOptions
0x18001a8dc  lea     rdx, ?AuxUserType@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18001a8e3  call    cs:__imp_RegOpenKeyExW
0x18001a8e9  test    eax, eax
0x18001a8eb  jnz     $trymain
0x18001a8f1  mov     r9d, ebx
0x18001a8f4  lea     ppszUserType, aD; "%d"
0x18001a8fb  lea     dwFormOfType, [rsi+13h]; cchDest
0x18001a8fe  lea     clsid, [rsp+4D0h+szIndex]; pszDest
0x18001a903  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a908  mov     clsid, [rsp+4D0h+hkeyAux]; hKey
0x18001a90d  lea     rax, [rsp+4D0h+hkeyAuxWithIndex]
0x18001a912  mov     r9d, 20019h; samDesired
0x18001a918  mov     [rsp+4D0h+result], rax; phkResult
0x18001a91d  xor     r8d, r8d; ulOptions
0x18001a920  lea     rdx, [rsp+4D0h+szIndex]; lpSubKey
0x18001a925  call    cs:__imp_RegOpenKeyExW
0x18001a92b  test    eax, eax
0x18001a92d  jnz     short $trymain
0x18001a92f  mov     clsid, [rsp+4D0h+hkeyAuxWithIndex]; hKey
0x18001a934  lea     ppszUserType, [rbp+3D0h+szLocalized]; pszOutBuf
0x18001a938  mov     [rsp+4D0h+pszDirectory], r14; pszDirectory
0x18001a93d  lea     rdx, aLocalizedstrin; "LocalizedString"
0x18001a944  mov     [rsp+4D0h+Flags], esi; Flags
0x18001a948  mov     r9d, 400h; cbOutBuf
0x18001a94e  mov     [rsp+4D0h+result], r14; pcbData
0x18001a953  call    cs:__imp_RegLoadMUIStringW
0x18001a959  test    eax, eax
0x18001a95b  jnz     short loc_18001A97B
0x18001a95d  lea     clsid, [rbp+3D0h+szLocalized]; lpszIn
0x18001a961  call    ?UtDupString@@YAPEAGPEBG@Z; UtDupString(ushort const *)
0x18001a966  mov     [rdi], rax
0x18001a969  neg     rax
0x18001a96c  sbb     ebx, ebx
0x18001a96e  not     ebx
0x18001a970  and     ebx, 8007000Eh
0x18001a976  jmp     $errRtn_9
0x18001a97b  mov     clsid, [rsp+4D0h+hkeyAux]; hkey
0x18001a980  lea     ppszUserType, [rsp+4D0h+allocatedDisplayNameString]; ppszValue
0x18001a985  mov     dwFormOfType, ebx; dwKey
0x18001a987  call    OleRegGetString_0
0x18001a98c  test    eax, eax
0x18001a98e  js      short $trymain
0x18001a990  mov     clsid, [rsp+4D0h+allocatedDisplayNameString.m_ptr]; pv
0x18001a995  cmp     [clsid], r14w
0x18001a999  jz      short loc_18001A9A0
0x18001a99b  mov     [rdi], clsid
0x18001a99e  jmp     short loc_18001AA0E
0x18001a9a0  call    cs:__imp_CoTaskMemFree
0x18001a9a6  mov     [rsp+4D0h+allocatedDisplayNameString.m_ptr], r14
0x18001a9ab  mov     clsid, [rsp+4D0h+hkeyClsid]; hKey
0x18001a9b0  lea     ppszUserType, [rbp+3D0h+szLocalized]; pszOutBuf
0x18001a9b4  mov     [rsp+4D0h+pszDirectory], r14; pszDirectory
0x18001a9b9  lea     rdx, aLocalizedstrin; "LocalizedString"
0x18001a9c0  mov     [rsp+4D0h+Flags], esi; Flags
0x18001a9c4  mov     r9d, 400h; cbOutBuf
0x18001a9ca  mov     [rsp+4D0h+result], r14; pcbData
0x18001a9cf  call    cs:__imp_RegLoadMUIStringW
0x18001a9d5  test    eax, eax
0x18001a9d7  jz      short loc_18001A95D
0x18001a9d9  mov     clsid, [rsp+4D0h+hkeyClsid]; hkey
0x18001a9de  lea     ppszUserType, [rsp+4D0h+allocatedDisplayNameString]; ppszValue
0x18001a9e3  xor     dwFormOfType, dwFormOfType; szKey
0x18001a9e5  call    OleRegGetString
0x18001a9ea  mov     ebx, eax
0x18001a9ec  test    eax, eax
0x18001a9ee  jnz     short $errRtn_9
0x18001a9f0  mov     rax, [rsp+4D0h+allocatedDisplayNameString.m_ptr]
0x18001a9f5  cmp     [rax], r14w
0x18001a9f9  jnz     short loc_18001AA0B
0x18001a9fb  mov     clsid, rax; pv
0x18001a9fe  call    cs:__imp_CoTaskMemFree
0x18001aa04  mov     ebx, 80040153h
0x18001aa09  jmp     short $errRtn_9
0x18001aa0b  mov     [rdi], rax
0x18001aa0e  mov     ebx, r14d
0x18001aa11  mov     clsid, [rsp+4D0h+hkeyClsid]; hKey
0x18001aa16  test    clsid, clsid
0x18001aa19  jz      short loc_18001AA26
0x18001aa1b  call    cs:__imp_RegCloseKey
0x18001aa21  mov     [rsp+4D0h+hkeyClsid], r14
0x18001aa26  mov     clsid, [rsp+4D0h+hkeyAux]; hKey
0x18001aa2b  test    clsid, clsid
0x18001aa2e  jz      short loc_18001AA3B
0x18001aa30  call    cs:__imp_RegCloseKey
0x18001aa36  mov     [rsp+4D0h+hkeyAux], r14
0x18001aa3b  mov     clsid, [rsp+4D0h+hkeyAuxWithIndex]; hKey
0x18001aa40  test    clsid, clsid
0x18001aa43  jz      short $safeRtn
0x18001aa45  call    cs:__imp_RegCloseKey
0x18001aa4b  mov     [rsp+4D0h+hkeyAuxWithIndex], r14
0x18001aa50  mov     clsid, [rsp+4D0h+oleClassInfo.m_ptr]
0x18001aa55  test    clsid, clsid
0x18001aa58  jz      short loc_18001AA66
0x18001aa5a  mov     rax, [clsid]
0x18001aa5d  mov     rax, [rax+10h]
0x18001aa61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa66  mov     eax, ebx
0x18001aa68  mov     clsid, [rbp+3D0h+var_30]
0x18001aa6f  xor     clsid, rsp; StackCookie
0x18001aa72  call    __security_check_cookie
0x18001aa77  add     rsp, 4B0h
0x18001aa7e  pop     r14
0x18001aa80  pop     rdi
0x18001aa81  pop     rsi
0x18001aa82  pop     rbx
0x18001aa83  pop     rbp
0x18001aa84  retn
```
