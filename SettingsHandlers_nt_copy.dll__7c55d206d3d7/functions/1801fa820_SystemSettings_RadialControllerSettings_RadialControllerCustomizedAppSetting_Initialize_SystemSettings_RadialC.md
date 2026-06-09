# SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppSetting::_Initialize(SystemSettings::RadialControllerSettings::RadialControllerNotificationItem const &)

- ea: `0x1801fa820`
- end: `0x1801fabf6`
- name: `?_Initialize@RadialControllerCustomizedAppSetting@RadialControllerSettings@SystemSettings@@AEAAJAEBURadialControllerNotificationItem@23@@Z`
- size: `982`
- prototype: `__int64 __fastcall(SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppSetting *__hidden this, const struct SystemSettings::RadialControllerSettings::RadialControllerNotificationItem *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801f61cc`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x1800234c4`
- `0x1800684c8`
- `0x18006956c`
- `0x180069d78`
- `0x1801f656c`
- `0x1801f8af4`
- `0x1801f9150`
- `0x1801fa820`
- `0x180244f44`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1801fa9f3`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1801fa9f3`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1801fa8ce`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1801fa8ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faa65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faaa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fab11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faa65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801faaa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fab11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801faac2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801faac2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppSetting::_Initialize(
        SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppSetting *this,
        LPCWSTR *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  HRESULT AppBackgroundColor; // eax
  LPCWSTR v9; // rdx
  __int64 v10; // rbx
  const WCHAR *v11; // rdi
  __int64 v12; // r8
  const WCHAR *v13; // rbx
  int StringOrdinal; // eax
  __int64 v15; // rbx
  struct SystemSettings::StorageSenseHandlers::CAppInfo *v16; // rdi
  __int64 (__fastcall *v17)(struct SystemSettings::StorageSenseHandlers::CAppInfo *, HSTRING *); // rbx
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v22; // rbx
  LPCWSTR v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rbx
  int v26; // eax
  int ppv; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  HSTRING string; // [rsp+70h] [rbp+40h] BYREF
  struct SystemSettings::StorageSenseHandlers::CAppInfo *v31; // [rsp+78h] [rbp+48h] BYREF
  struct IShellItem2 *v32; // [rsp+80h] [rbp+50h] BYREF
  char v33; // [rsp+88h] [rbp+58h] BYREF

  v32 = 0;
  v31 = 0;
  *((_BYTE *)this + 308) = anonymous_namespace_::IsDesktopApp(a2[1]);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &string,
    a2[1],
    -1);
  v4 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (char *)this + 248,
                    &string);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&string);
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = 2147942414LL;
    v7 = 302;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
      (const char *)v6,
      ppv);
    goto LABEL_41;
  }
  if ( !*((_BYTE *)this + 308) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    AppBackgroundColor = SHCreateItemInKnownFolder(
                           &FOLDERID_AppsFolder,
                           0x4000u,
                           *((PCWSTR *)this + 31),
                           &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                           (void **)&v32);
    v5 = AppBackgroundColor;
    if ( AppBackgroundColor < 0 )
    {
      v7 = 306;
LABEL_6:
      v6 = (unsigned int)AppBackgroundColor;
      goto LABEL_7;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    AppBackgroundColor = SystemSettings::StorageSenseHandlers::CAppInfo::Create(v32, &v31);
    v5 = AppBackgroundColor;
    if ( AppBackgroundColor < 0 )
    {
      v7 = 307;
      goto LABEL_6;
    }
    string = (HSTRING)v31;
    if ( v31 )
      (*(void (__fastcall **)(struct SystemSettings::StorageSenseHandlers::CAppInfo *))(*(_QWORD *)v31 + 8LL))(v31);
    AppBackgroundColor = anonymous_namespace_::GetAppBackgroundColor(&string, (char *)this + 304);
    v5 = AppBackgroundColor;
    if ( AppBackgroundColor < 0 )
    {
      v7 = 308;
      goto LABEL_6;
    }
  }
  v9 = a2[2];
  if ( v9 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &string,
      v9,
      -1);
    v10 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                       (char *)this + 256,
                       &string);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&string);
    if ( !v10 )
    {
      v5 = -2147024882;
      v6 = 2147942414LL;
      v7 = 313;
      goto LABEL_7;
    }
  }
  else
  {
    if ( !*((_BYTE *)this + 308) )
    {
      string = 0;
      v16 = v31;
      v17 = *(__int64 (__fastcall **)(struct SystemSettings::StorageSenseHandlers::CAppInfo *, HSTRING *))(*(_QWORD *)v31 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v18 = v17(v16, &string);
      v5 = v18;
      if ( v18 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v33,
          StringRawBuffer,
          -1);
        v22 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                           (char *)this + 256,
                           &v33);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
        if ( v22 )
        {
          WindowsDeleteString(string);
          goto LABEL_33;
        }
        v5 = -2147024882;
        v19 = 2147942414LL;
        v20 = 327;
      }
      else
      {
        v19 = (unsigned int)v18;
        v20 = 326;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
        (const char *)v19,
        ppv);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_41;
    }
    v11 = a2[1];
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v13 = &v11[v12];
    if ( v12 && *(v13 - 1) == 92 )
      LODWORD(v12) = v12 - 1;
    StringOrdinal = FindStringOrdinal(0x800000u, v11, v12, L"\\", 1, 1);
    if ( StringOrdinal != -1 )
      v13 = &v11[StringOrdinal + 1];
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &string,
      v13,
      -1);
    v15 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                       (char *)this + 256,
                       &string);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&string);
    if ( !v15 )
    {
      v5 = -2147024882;
      v6 = 2147942414LL;
      v7 = 321;
      goto LABEL_7;
    }
  }
LABEL_33:
  v23 = a2[4];
  if ( v23 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v33,
      v23,
      -1);
    v24 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                       (char *)this + 264,
                       &v33);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
    if ( !v24 )
    {
      v5 = -2147024882;
      v6 = 2147942414LL;
      v7 = 333;
      goto LABEL_7;
    }
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v33,
      &LocaleName,
      -1);
    v25 = *(_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                       (char *)this + 264,
                       &v33);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
    if ( !v25 )
    {
      v5 = -2147024882;
      v6 = 2147942414LL;
      v7 = 338;
      goto LABEL_7;
    }
  }
  v26 = SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppSetting::InitializeToolSummary(this);
  if ( v26 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
      (const char *)(unsigned int)v26,
      ppv);
  *((_BYTE *)this + 309) = 1;
  v5 = 0;
LABEL_41:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  return v5;
}

```

## disassembly

```asm
0x1801fa820  push    rbp
0x1801fa822  push    rbx
0x1801fa823  push    rsi
0x1801fa824  push    rdi
0x1801fa825  push    r12
0x1801fa827  push    r14
0x1801fa829  push    r15
0x1801fa82b  mov     rbp, rsp
0x1801fa82e  sub     rsp, 30h
0x1801fa832  mov     r14, rdx
0x1801fa835  mov     rsi, rcx
0x1801fa838  xor     r15d, r15d
0x1801fa83b  mov     [rbp+arg_10], r15
0x1801fa83f  mov     [rbp+arg_8], r15
0x1801fa843  mov     rcx, [rdx+8]; lpStringSource
0x1801fa847  call    _anonymous_namespace___IsDesktopApp
0x1801fa84c  mov     [rsi+134h], al
0x1801fa852  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801fa856  mov     r8, r12
0x1801fa859  mov     rdx, [r14+8]
0x1801fa85d  lea     rcx, [rbp+string]
0x1801fa861  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801fa866  lea     rdi, [rsi+0F8h]
0x1801fa86d  lea     rdx, [rbp+string]
0x1801fa871  mov     rcx, rdi
0x1801fa874  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801fa879  mov     rbx, [rax]
0x1801fa87c  lea     rcx, [rbp+string]
0x1801fa880  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fa885  test    rbx, rbx
0x1801fa888  jnz     short loc_1801FA899
0x1801fa88a  mov     ebx, 8007000Eh
0x1801fa88f  mov     r9d, ebx
0x1801fa892  mov     edx, 12Eh
0x1801fa897  jmp     short loc_1801FA8E8
0x1801fa899  cmp     [rsi+134h], r15b
0x1801fa8a0  jnz     loc_1801FA957
0x1801fa8a6  lea     rcx, [rbp+arg_10]
0x1801fa8aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fa8af  lea     rax, [rbp+arg_10]
0x1801fa8b3  mov     [rsp+30h+ppv], rax; int
0x1801fa8b8  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1801fa8bf  mov     r8, [rdi]; pszItem
0x1801fa8c2  mov     edx, 4000h; dwKFFlags
0x1801fa8c7  lea     rcx, FOLDERID_AppsFolder; kfid
0x1801fa8ce  call    cs:__imp_SHCreateItemInKnownFolder
0x1801fa8d5  nop     dword ptr [rax+rax+00h]
0x1801fa8da  mov     ebx, eax
0x1801fa8dc  test    eax, eax
0x1801fa8de  jns     short loc_1801FA8FD
0x1801fa8e0  mov     edx, 132h; void *
0x1801fa8e5  mov     r9d, eax; char *
0x1801fa8e8  lea     r8, aShellSystemset_55; "shell\\systemsettingsthreshold\\handler"...
0x1801fa8ef  mov     rcx, [rbp+38h]; this
0x1801fa8f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa8f8  jmp     loc_1801FABD1
0x1801fa8fd  lea     rcx, [rbp+arg_8]
0x1801fa901  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fa906  lea     rdx, [rbp+arg_8]; struct SystemSettings::StorageSenseHandlers::CAppInfo **
0x1801fa90a  mov     rcx, [rbp+arg_10]; struct IShellItem2 *
0x1801fa90e  call    ?Create@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUIShellItem2@@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::Create(IShellItem2 *,SystemSettings::StorageSenseHandlers::CAppInfo * *)
0x1801fa913  mov     ebx, eax
0x1801fa915  test    eax, eax
0x1801fa917  jns     short loc_1801FA920
0x1801fa919  mov     edx, 133h
0x1801fa91e  jmp     short loc_1801FA8E5
0x1801fa920  mov     rcx, [rbp+arg_8]
0x1801fa924  mov     [rbp+string], rcx
0x1801fa928  test    rcx, rcx
0x1801fa92b  jz      short loc_1801FA93A
0x1801fa92d  mov     rax, [rcx]
0x1801fa930  mov     rax, [rax+8]
0x1801fa934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa939  nop
0x1801fa93a  lea     rdx, [rsi+130h]
0x1801fa941  lea     rcx, [rbp+string]
0x1801fa945  call    _anonymous_namespace___GetAppBackgroundColor
0x1801fa94a  mov     ebx, eax
0x1801fa94c  test    eax, eax
0x1801fa94e  jns     short loc_1801FA957
0x1801fa950  mov     edx, 134h
0x1801fa955  jmp     short loc_1801FA8E5
0x1801fa957  mov     rdx, [r14+10h]
0x1801fa95b  test    rdx, rdx
0x1801fa95e  jz      short loc_1801FA9A3
0x1801fa960  mov     r8, r12
0x1801fa963  lea     rcx, [rbp+string]
0x1801fa967  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801fa96c  lea     rcx, [rsi+100h]
0x1801fa973  lea     rdx, [rbp+string]
0x1801fa977  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801fa97c  mov     rbx, [rax]
0x1801fa97f  lea     rcx, [rbp+string]
0x1801fa983  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fa988  test    rbx, rbx
0x1801fa98b  jnz     loc_1801FAB1D
0x1801fa991  mov     ebx, 8007000Eh
0x1801fa996  mov     r9d, ebx
0x1801fa999  mov     edx, 139h
0x1801fa99e  jmp     loc_1801FA8E8
0x1801fa9a3  cmp     [rsi+134h], r15b
0x1801fa9aa  jz      loc_1801FAA54
0x1801fa9b0  mov     rdi, [r14+8]
0x1801fa9b4  mov     r8, r12
0x1801fa9b7  inc     r8
0x1801fa9ba  cmp     [rdi+r8*2], r15w
0x1801fa9bf  jnz     short loc_1801FA9B7
0x1801fa9c1  lea     rbx, [rdi+r8*2]
0x1801fa9c5  test    r8, r8
0x1801fa9c8  jz      short loc_1801FA9D4
0x1801fa9ca  cmp     word ptr [rbx-2], 5Ch ; '\'
0x1801fa9cf  jnz     short loc_1801FA9D4
0x1801fa9d1  dec     r8; cchSource
0x1801fa9d4  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x1801fa9dc  mov     dword ptr [rsp+30h+ppv], 1; cchValue
0x1801fa9e4  lea     r9, Control; "\\"
0x1801fa9eb  mov     rdx, rdi; lpStringSource
0x1801fa9ee  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1801fa9f3  call    cs:__imp_FindStringOrdinal
0x1801fa9fa  nop     dword ptr [rax+rax+00h]
0x1801fa9ff  cmp     eax, r12d
0x1801faa02  jz      short loc_1801FAA0E
0x1801faa04  movsxd  rbx, eax
0x1801faa07  inc     rbx
0x1801faa0a  lea     rbx, [rdi+rbx*2]
0x1801faa0e  mov     r8, r12
0x1801faa11  mov     rdx, rbx
0x1801faa14  lea     rcx, [rbp+string]
0x1801faa18  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801faa1d  lea     rcx, [rsi+100h]
0x1801faa24  lea     rdx, [rbp+string]
0x1801faa28  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801faa2d  mov     rbx, [rax]
0x1801faa30  lea     rcx, [rbp+string]
0x1801faa34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801faa39  test    rbx, rbx
0x1801faa3c  jnz     loc_1801FAB1D
0x1801faa42  mov     ebx, 8007000Eh
0x1801faa47  mov     r9d, ebx
0x1801faa4a  mov     edx, 141h
0x1801faa4f  jmp     loc_1801FA8E8
0x1801faa54  mov     [rbp+string], r15
0x1801faa58  mov     rdi, [rbp+arg_8]
0x1801faa5c  mov     rax, [rdi]
0x1801faa5f  mov     rbx, [rax+30h]
0x1801faa63  xor     ecx, ecx; string
0x1801faa65  call    cs:__imp_WindowsDeleteString
0x1801faa6c  nop     dword ptr [rax+rax+00h]
0x1801faa71  mov     [rbp+string], r15
0x1801faa75  lea     rdx, [rbp+string]
0x1801faa79  mov     rcx, rdi
0x1801faa7c  mov     rax, rbx
0x1801faa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801faa84  mov     ebx, eax
0x1801faa86  test    eax, eax
0x1801faa88  jns     short loc_1801FAABC
0x1801faa8a  mov     r9d, eax; char *
0x1801faa8d  mov     edx, 146h; void *
0x1801faa92  lea     r8, aShellSystemset_55; "shell\\systemsettingsthreshold\\handler"...
0x1801faa99  mov     rcx, [rbp+38h]; this
0x1801faa9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801faaa2  nop
0x1801faaa3  mov     rcx, [rbp+string]; string
0x1801faaa7  call    cs:__imp_WindowsDeleteString
0x1801faaae  nop     dword ptr [rax+rax+00h]
0x1801faab3  mov     [rbp+string], r15
0x1801faab7  jmp     loc_1801FABD1
0x1801faabc  xor     edx, edx; length
0x1801faabe  mov     rcx, [rbp+string]; string
0x1801faac2  call    cs:__imp_WindowsGetStringRawBuffer
0x1801faac9  nop     dword ptr [rax+rax+00h]
0x1801faace  mov     r8, r12
0x1801faad1  mov     rdx, rax
0x1801faad4  lea     rcx, [rbp+arg_18]
0x1801faad8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801faadd  lea     rcx, [rsi+100h]
0x1801faae4  lea     rdx, [rbp+arg_18]
0x1801faae8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801faaed  mov     rbx, [rax]
0x1801faaf0  lea     rcx, [rbp+arg_18]
0x1801faaf4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801faaf9  test    rbx, rbx
0x1801faafc  jnz     short loc_1801FAB0D
0x1801faafe  mov     ebx, 8007000Eh
0x1801fab03  mov     r9d, ebx
0x1801fab06  mov     edx, 147h
0x1801fab0b  jmp     short loc_1801FAA92
0x1801fab0d  mov     rcx, [rbp+string]; string
0x1801fab11  call    cs:__imp_WindowsDeleteString
0x1801fab18  nop     dword ptr [rax+rax+00h]
0x1801fab1d  mov     rdx, [r14+20h]
0x1801fab21  lea     rbx, [rsi+108h]
0x1801fab28  mov     r8, r12
0x1801fab2b  lea     rcx, [rbp+arg_18]
0x1801fab2f  test    rdx, rdx
0x1801fab32  jz      short loc_1801FAB68
0x1801fab34  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801fab39  lea     rdx, [rbp+arg_18]
0x1801fab3d  mov     rcx, rbx
0x1801fab40  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801fab45  mov     rbx, [rax]
0x1801fab48  lea     rcx, [rbp+arg_18]
0x1801fab4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fab51  test    rbx, rbx
0x1801fab54  jnz     short loc_1801FABA3
0x1801fab56  mov     ebx, 8007000Eh
0x1801fab5b  mov     r9d, ebx
0x1801fab5e  mov     edx, 14Dh
0x1801fab63  jmp     loc_1801FA8E8
0x1801fab68  lea     rdx, LocaleName
0x1801fab6f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801fab74  lea     rdx, [rbp+arg_18]
0x1801fab78  mov     rcx, rbx
0x1801fab7b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801fab80  mov     rbx, [rax]
0x1801fab83  lea     rcx, [rbp+arg_18]
0x1801fab87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801fab8c  test    rbx, rbx
0x1801fab8f  jnz     short loc_1801FABA3
0x1801fab91  mov     ebx, 8007000Eh
0x1801fab96  mov     r9d, ebx
0x1801fab99  mov     edx, 152h
0x1801fab9e  jmp     loc_1801FA8E8
0x1801faba3  mov     rcx, rsi; this
0x1801faba6  call    ?InitializeToolSummary@RadialControllerCustomizedAppSetting@RadialControllerSettings@SystemSettings@@AEAAJXZ; SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppSetting::InitializeToolSummary(void)
0x1801fabab  mov     rcx, [rbp+38h]; this
0x1801fabaf  test    eax, eax
0x1801fabb1  jns     short loc_1801FABC7
0x1801fabb3  mov     r9d, eax; char *
0x1801fabb6  lea     r8, aShellSystemset_55; "shell\\systemsettingsthreshold\\handler"...
0x1801fabbd  mov     edx, 155h; void *
0x1801fabc2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801fabc7  mov     byte ptr [rsi+135h], 1
0x1801fabce  mov     ebx, r15d
0x1801fabd1  lea     rcx, [rbp+arg_8]
0x1801fabd5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fabda  nop
0x1801fabdb  lea     rcx, [rbp+arg_10]
0x1801fabdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801fabe4  mov     eax, ebx
0x1801fabe6  add     rsp, 30h
0x1801fabea  pop     r15
0x1801fabec  pop     r14
0x1801fabee  pop     r12
0x1801fabf0  pop     rdi
0x1801fabf1  pop     rsi
0x1801fabf2  pop     rbx
0x1801fabf3  pop     rbp
0x1801fabf4  retn
```
