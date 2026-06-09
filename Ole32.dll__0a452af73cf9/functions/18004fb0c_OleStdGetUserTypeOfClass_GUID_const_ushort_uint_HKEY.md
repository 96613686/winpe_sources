# OleStdGetUserTypeOfClass(_GUID const &,ushort *,uint,HKEY__ *)

- ea: `0x18004fb0c`
- end: `0x18004fdf3`
- name: `?OleStdGetUserTypeOfClass@@YAJAEBU_GUID@@PEAGIPEAUHKEY__@@@Z`
- size: `743`
- prototype: `HRESULT __fastcall(const _GUID *clsid, wchar_t *userType, unsigned int clsid, HKEY__ *userType)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180099cf0`

## callees

- `0x18001248c`
- `0x1800185ec`
- `0x18001a3c8`
- `0x18001b0e4`
- `0x18001b810`
- `0x1800242c4`
- `0x180034bfc`
- `0x180036488`
- `0x18003ffb4`
- `0x18004bafc`
- `0x18004fb0c`
- `0x18004fdfc`
- `0x180052390`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fcc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fdba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fcc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fdba`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18004fd01`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18004fd01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fd32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fd88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fd32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fd88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fbdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fbf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fbdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fbf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fb90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fb90`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18004fcd6`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18004fcd6`

## string_xrefs

- `0x18004fbba`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004fc66`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004fd14`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004fd62`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004fda2`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004fc41`: `CLSID\`

## pseudocode

```c
__int64 __fastcall OleStdGetUserTypeOfClass(const _GUID *clsid, wchar_t *userType, unsigned int a3, HKEY__ *a4)
{
  int v6; // eax
  HSTRING__ *m_ptr; // rcx
  unsigned int v8; // ebx
  const wchar_t *StringRawBuffer; // rax
  HRESULT v10; // eax
  int v11; // eax
  unsigned int v12; // r9d
  unsigned int v13; // edx
  HKEY__ *v14; // rsi
  HRESULT v15; // eax
  unsigned __int64 v16; // r10
  unsigned int v17; // edx
  int v18; // ebx
  int v19; // eax
  unsigned int v20; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > openedKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int valueSize; // [rsp+38h] [rbp-C8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&CoTaskMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > progId; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > displayNameStringOrResourceReference; // [rsp+48h] [rbp-B8h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+50h] [rbp-B0h] BYREF
  GuidString clsidString; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t szKey[128]; // [rsp+B0h] [rbp-50h] BYREF
  void *retaddr; // [rsp+1D8h] [rbp+D8h]

  oleClassInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         clsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) >= 0 )
  {
    displayNameStringOrResourceReference.m_ptr = 0;
    v6 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))oleClassInfo.m_ptr->lpVtbl[1].Release)(
           oleClassInfo.m_ptr,
           &displayNameStringOrResourceReference);
    m_ptr = displayNameStringOrResourceReference.m_ptr;
    v8 = v6;
    if ( v6 < 0 )
      goto LABEL_5;
    StringRawBuffer = WindowsGetStringRawBuffer(displayNameStringOrResourceReference.m_ptr, 0);
    v10 = ResolveStringOrResourceReference(0, 0, StringRawBuffer, 0x2Au, userType);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x6A5u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v10);
      m_ptr = displayNameStringOrResourceReference.m_ptr;
LABEL_5:
      if ( m_ptr )
        WindowsDeleteString(m_ptr);
      goto LABEL_33;
    }
    if ( displayNameStringOrResourceReference.m_ptr )
      WindowsDeleteString(displayNameStringOrResourceReference.m_ptr);
LABEL_9:
    v8 = 0;
    goto LABEL_33;
  }
  openedKey.m_ptr = 0;
  v11 = OpenClassesRootKeyExW(0, 0x2000000u, &openedKey.m_ptr);
  if ( !v11 )
  {
    v14 = openedKey.m_ptr;
    GuidString::GuidString(&clsidString, clsid);
    v15 = StringCchCopyW(szKey, 0x80u, L"CLSID\\");
    v8 = v15;
    if ( v15 < 0 )
    {
      v17 = 1717;
LABEL_14:
      wil::details::in1diag3::Return_Hr(retaddr, v17, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v15);
      goto LABEL_31;
    }
    v15 = StringCchCatW(szKey, v16, clsidString.m_string);
    v8 = v15;
    if ( v15 < 0 )
    {
      v17 = 1718;
      goto LABEL_14;
    }
    valueSize = 84;
    v18 = wRegQueryValue(v14, szKey, userType, &valueSize);
    if ( !v18 )
    {
LABEL_18:
      if ( openedKey.m_ptr )
        RegCloseKey(openedKey.m_ptr);
      goto LABEL_9;
    }
    if ( !CoIsOle1Class(clsid) )
    {
      v12 = v18;
      v13 = 1741;
      goto LABEL_30;
    }
    progId.m_ptr = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &progId,
      0);
    v19 = ProgIDFromCLSID(clsid, &progId.m_ptr);
    v8 = v19;
    if ( v19 >= 0 )
    {
      valueSize = 84;
      v20 = wRegQueryValue(v14, progId.m_ptr, userType, &valueSize);
      if ( !v20 )
      {
        if ( progId.m_ptr )
          CoTaskMemFree(progId.m_ptr);
        goto LABEL_18;
      }
      v8 = wil::details::in1diag3::Return_Win32(retaddr, 0x6C8u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x6C5u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v19);
    }
    if ( progId.m_ptr )
      CoTaskMemFree(progId.m_ptr);
    goto LABEL_31;
  }
  v12 = v11;
  v13 = 1710;
LABEL_30:
  v8 = wil::details::in1diag3::Return_Win32(retaddr, v13, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v12);
LABEL_31:
  if ( openedKey.m_ptr )
    RegCloseKey(openedKey.m_ptr);
LABEL_33:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
  return v8;
}

```

## disassembly

```asm
0x18004fb0c  mov     [rsp-8+arg_10], rbx
0x18004fb11  mov     [rsp-8+arg_18], rsi
0x18004fb16  push    rbp
0x18004fb17  push    rdi
0x18004fb18  push    r14
0x18004fb1a  lea     rbp, [rsp-0C0h]
0x18004fb22  sub     rsp, 1C0h
0x18004fb29  mov     rax, cs:__security_cookie
0x18004fb30  xor     rax, rsp
0x18004fb33  mov     [rbp+0D0h+var_20], rax
0x18004fb3a  mov     r14, userType
0x18004fb3d  mov     [rsp+1D0h+oleClassInfo.m_ptr], 0
0x18004fb46  xor     edx, edx; pComCatalog
0x18004fb48  lea     r9, [rsp+1D0h+oleClassInfo]; ppv
0x18004fb4d  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18004fb54  mov     rdi, clsid
0x18004fb57  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18004fb5c  test    eax, eax
0x18004fb5e  js      loc_18004FBFE
0x18004fb64  mov     clsid, [rsp+1D0h+oleClassInfo.m_ptr]
0x18004fb69  lea     userType, [rsp+1D0h+displayNameStringOrResourceReference]
0x18004fb6e  mov     [rsp+1D0h+displayNameStringOrResourceReference.m_ptr], 0
0x18004fb77  mov     rax, [clsid]
0x18004fb7a  mov     rax, [rax+28h]
0x18004fb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb83  mov     clsid, [rsp+1D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18004fb88  mov     ebx, eax
0x18004fb8a  test    eax, eax
0x18004fb8c  js      short loc_18004FBD3
0x18004fb8e  xor     edx, edx; length
0x18004fb90  call    cs:__imp_WindowsGetStringRawBuffer
0x18004fb96  mov     r9d, 2Ah ; '*'; bufferSize
0x18004fb9c  mov     [rsp+1D0h+buffer], r14; buffer
0x18004fba1  mov     r8, rax; stringOrResourceReference
0x18004fba4  xor     edx, edx; resourceContext
0x18004fba6  xor     ecx, ecx; providedResourceManager
0x18004fba8  call    ?ResolveStringOrResourceReference@@YAJPEAUIMrtResourceManager@@PEAUIResourceContext@@PEBG_KPEAG@Z; ResolveStringOrResourceReference(IMrtResourceManager *,IResourceContext *,ushort const *,unsigned __int64,ushort *)
0x18004fbad  mov     ebx, eax
0x18004fbaf  test    eax, eax
0x18004fbb1  jns     short loc_18004FBE7
0x18004fbb3  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18004fbba  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004fbc1  mov     r9d, eax; hr
0x18004fbc4  mov     edx, 6A5h; lineNumber
0x18004fbc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fbce  mov     clsid, [rsp+1D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18004fbd3  test    clsid, clsid
0x18004fbd6  jz      loc_18004FDC0
0x18004fbdc  call    cs:__imp_WindowsDeleteString
0x18004fbe2  jmp     loc_18004FDC0
0x18004fbe7  mov     clsid, [rsp+1D0h+displayNameStringOrResourceReference.m_ptr]; string
0x18004fbec  test    clsid, clsid
0x18004fbef  jz      short loc_18004FBF7
0x18004fbf1  call    cs:__imp_WindowsDeleteString
0x18004fbf7  xor     ebx, ebx
0x18004fbf9  jmp     loc_18004FDC0
0x18004fbfe  lea     r8, [rsp+1D0h+openedKey]; phkResult
0x18004fc03  mov     [rsp+1D0h+openedKey.m_ptr], 0
0x18004fc0c  mov     edx, 2000000h; samDesired
0x18004fc11  xor     ecx, ecx; pszSubKey
0x18004fc13  call    OpenClassesRootKeyExW
0x18004fc18  test    eax, eax
0x18004fc1a  jz      short loc_18004FC29
0x18004fc1c  mov     r9d, eax
0x18004fc1f  mov     edx, 6AEh
0x18004fc24  jmp     loc_18004FD9B
0x18004fc29  mov     rsi, [rsp+1D0h+openedKey.m_ptr]
0x18004fc2e  lea     clsid, [rsp+1D0h+clsidString]; this
0x18004fc33  mov     userType, rdi; guid
0x18004fc36  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18004fc3b  mov     r10d, 80h
0x18004fc41  lea     r8, aClsid_0; "CLSID\\"
0x18004fc48  mov     edx, r10d; cchDest
0x18004fc4b  lea     clsid, [rbp+0D0h+szKey]; pszDest
0x18004fc4f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004fc54  mov     ebx, eax
0x18004fc56  test    eax, eax
0x18004fc58  jns     short loc_18004FC7A
0x18004fc5a  mov     edx, 6B5h; lineNumber
0x18004fc5f  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18004fc66  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004fc6d  mov     r9d, eax; hr
0x18004fc70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fc75  jmp     loc_18004FDB0
0x18004fc7a  lea     r8, [rsp+1D0h+clsidString]; pszSrc
0x18004fc7f  mov     userType, r10; cchDest
0x18004fc82  lea     clsid, [rbp+0D0h+szKey]; pszDest
0x18004fc86  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004fc8b  mov     ebx, eax
0x18004fc8d  test    eax, eax
0x18004fc8f  jns     short loc_18004FC98
0x18004fc91  mov     edx, 6B6h
0x18004fc96  jmp     short loc_18004FC5F
0x18004fc98  lea     r9, [rsp+1D0h+valueSize]; lpdwSize
0x18004fc9d  mov     [rsp+1D0h+valueSize], 54h ; 'T'
0x18004fca5  mov     r8, r14; lpValue
0x18004fca8  lea     userType, [rbp+0D0h+szKey]; lpSubKey
0x18004fcac  mov     clsid, rsi; hKey
0x18004fcaf  call    wRegQueryValue
0x18004fcb4  mov     ebx, eax
0x18004fcb6  test    eax, eax
0x18004fcb8  jnz     short loc_18004FCD3
0x18004fcba  mov     clsid, [rsp+1D0h+openedKey.m_ptr]; hKey
0x18004fcbf  test    clsid, clsid
0x18004fcc2  jz      loc_18004FBF7
0x18004fcc8  call    cs:__imp_RegCloseKey
0x18004fcce  jmp     loc_18004FBF7
0x18004fcd3  mov     clsid, rdi; rclsid
0x18004fcd6  call    cs:__imp_CoIsOle1Class
0x18004fcdc  test    eax, eax
0x18004fcde  jz      loc_18004FD93
0x18004fce4  xor     edx, edx; ptr
0x18004fce6  mov     [rsp+1D0h+progId.m_ptr], 0
0x18004fcef  lea     clsid, [rsp+1D0h+progId]; this
0x18004fcf4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004fcf9  lea     userType, [rsp+1D0h+progId]; lplpszProgID
0x18004fcfe  mov     clsid, rdi; clsid
0x18004fd01  call    cs:__imp_ProgIDFromCLSID
0x18004fd07  mov     ebx, eax
0x18004fd09  test    eax, eax
0x18004fd0b  jns     short loc_18004FD3A
0x18004fd0d  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18004fd14  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004fd1b  mov     r9d, eax; hr
0x18004fd1e  mov     edx, 6C5h; lineNumber
0x18004fd23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fd28  mov     clsid, [rsp+1D0h+progId.m_ptr]; pv
0x18004fd2d  test    clsid, clsid
0x18004fd30  jz      short loc_18004FDB0
0x18004fd32  call    cs:__imp_CoTaskMemFree
0x18004fd38  jmp     short loc_18004FDB0
0x18004fd3a  mov     userType, [rsp+1D0h+progId.m_ptr]; lpSubKey
0x18004fd3f  lea     r9, [rsp+1D0h+valueSize]; lpdwSize
0x18004fd44  mov     r8, r14; lpValue
0x18004fd47  mov     [rsp+1D0h+valueSize], 54h ; 'T'
0x18004fd4f  mov     clsid, rsi; hKey
0x18004fd52  call    wRegQueryValue
0x18004fd57  test    eax, eax
0x18004fd59  jz      short loc_18004FD7A
0x18004fd5b  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18004fd62  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004fd69  mov     r9d, eax; err
0x18004fd6c  mov     edx, 6C8h; lineNumber
0x18004fd71  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004fd76  mov     ebx, eax
0x18004fd78  jmp     short loc_18004FD28
0x18004fd7a  mov     clsid, [rsp+1D0h+progId.m_ptr]; pv
0x18004fd7f  test    clsid, clsid
0x18004fd82  jz      loc_18004FCBA
0x18004fd88  call    cs:__imp_CoTaskMemFree
0x18004fd8e  jmp     loc_18004FCBA
0x18004fd93  mov     r9d, ebx; err
0x18004fd96  mov     edx, 6CDh; lineNumber
0x18004fd9b  mov     clsid, [rbp+0D8h]; callerReturnAddress
0x18004fda2  lea     r8, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004fda9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004fdae  mov     ebx, eax
0x18004fdb0  mov     clsid, [rsp+1D0h+openedKey.m_ptr]; hKey
0x18004fdb5  test    clsid, clsid
0x18004fdb8  jz      short loc_18004FDC0
0x18004fdba  call    cs:__imp_RegCloseKey
0x18004fdc0  lea     clsid, [rsp+1D0h+oleClassInfo]; this
0x18004fdc5  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18004fdca  mov     eax, ebx
0x18004fdcc  mov     clsid, [rbp+0D0h+var_20]
0x18004fdd3  xor     clsid, rsp; StackCookie
0x18004fdd6  call    __security_check_cookie
0x18004fddb  lea     r11, [rsp+1D0h+var_10]
0x18004fde3  mov     rbx, [r11+30h]
0x18004fde7  mov     rsi, [r11+38h]
0x18004fdeb  mov     rsp, r11
0x18004fdee  pop     r14
0x18004fdf0  pop     rdi
0x18004fdf1  pop     rbp
0x18004fdf2  retn
```
