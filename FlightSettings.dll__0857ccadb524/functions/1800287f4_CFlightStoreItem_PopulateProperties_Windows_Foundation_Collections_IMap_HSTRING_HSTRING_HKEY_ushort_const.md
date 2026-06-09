# CFlightStoreItem::PopulateProperties(Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *,HKEY__ *,ushort const *)

- ea: `0x1800287f4`
- end: `0x180028b61`
- name: `?PopulateProperties@CFlightStoreItem@@CAJPEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAUHKEY__@@PEBG@Z`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800285b8`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001c6f4`
- `0x18001ce88`
- `0x18001cff8`
- `0x18001e50c`
- `0x1800202c4`
- `0x1800203c8`
- `0x180020c0c`
- `0x180024550`
- `0x180027b04`
- `0x1800287f4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180028951`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180028951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ad2`

## string_xrefs

- `0x180028890`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`
- `0x1800288fd`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`
- `0x180028a91`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`
- `0x180028ab9`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`
- `0x180028ae6`: `onecore\base\flighting\flightsettings\broker\libs\clientapi\flightstoreitem.cpp`

## pseudocode

```c
__int64 __fastcall CFlightStoreItem::PopulateProperties(HSTRING *a1, HKEY a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  HSTRING v6; // rdi
  signed int v7; // ebx
  HKEY *v8; // rax
  unsigned int v9; // r8d
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  DWORD i; // edi
  LSTATUS v14; // eax
  int v15; // eax
  unsigned __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  int lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  char v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v26; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v28[2]; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v30[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[256]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v26 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
  v26 = 0;
  Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(
    &string,
    v4,
    v5);
  v6 = string;
  if ( string )
  {
    v7 = XWinRT::SecureVersionTag::TagManager::Initialize((XWinRT::SecureVersionTag::TagManager *)(string + 36));
    if ( v7 >= 0 )
    {
      *((_BYTE *)v6 + 152) = 1;
      v26 = v6;
      string = 0;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
  if ( v7 >= 0 )
  {
    hKey = 0;
    v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v10 = RegWow64Helpers::OpenKey(a2, L"Properties", v9, 0x20019u, v8);
    v7 = v10;
    if ( v10 == -2147024894 || v10 == -2147023878 )
    {
LABEL_36:
      *a1 = v26;
      v26 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v7 = 0;
    }
    else
    {
      if ( v10 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          cchValueName = 255;
          Type = 0;
          v14 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, 0, 0);
          v7 = v14;
          if ( v14 > 0 )
            v7 = (unsigned __int16)v14 | 0x80070000;
          if ( v7 == -2147024637 )
            goto LABEL_36;
          if ( v7 < 0 )
            break;
          if ( Type - 1 <= 1 )
          {
            memset(v30, 0, 24);
            v15 = RegWow64Helpers::InitializeCoTaskMemNativeString(hKey, 0);
            v7 = v15;
            if ( v15 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x213,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
                (const char *)(unsigned int)v15,
                lpReserveda);
              goto LABEL_34;
            }
            v25 = 0;
            v28[0] = 0;
            v16 = -1;
            do
              ++v16;
            while ( ValueName[v16] );
            v7 = ULongLongToUInt(v16, v28);
            if ( v7 < 0
              || (v7 = Microsoft::WRL::Wrappers::HString::Set(
                         (Microsoft::WRL::Wrappers::HString *)&v25,
                         ValueName,
                         v28[0]),
                  v7 < 0) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x217,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
                (const char *)(unsigned int)v7,
                lpReserveda);
LABEL_32:
              WindowsDeleteString(v25);
              v25 = 0;
LABEL_34:
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v30);
              goto LABEL_12;
            }
            *(_QWORD *)v28 = v30[0];
            string = 0;
            v17 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v28);
            v7 = v17;
            if ( v17 < 0 )
            {
              v18 = 539;
              goto LABEL_30;
            }
            v22[0] = 0;
            v17 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, HSTRING, char *))(*(_QWORD *)v26 + 80LL))(
                    v26,
                    v25,
                    string,
                    v22);
            v7 = v17;
            if ( v17 < 0 )
            {
              v18 = 543;
LABEL_30:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v18,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
                (const char *)(unsigned int)v17,
                lpReserveda);
              WindowsDeleteString(string);
              string = 0;
              goto LABEL_32;
            }
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v25);
            v25 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v30);
          }
        }
        v11 = (unsigned int)v7;
        v12 = 519;
      }
      else
      {
        v11 = (unsigned int)v10;
        v12 = 506;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
        (const char *)v11,
        lpReserveda);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\clientapi\\flightstoreitem.cpp",
      (const char *)(unsigned int)v7,
      lpReserved);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800287f4  mov     [rsp-8+arg_10], rbx
0x1800287f9  push    rbp
0x1800287fa  push    rsi
0x1800287fb  push    rdi
0x1800287fc  push    r14
0x1800287fe  push    r15
0x180028800  lea     rbp, [rsp-1B0h]
0x180028808  sub     rsp, 2B0h
0x18002880f  mov     rax, cs:__security_cookie
0x180028816  xor     rax, rsp
0x180028819  mov     [rbp+1D0h+var_30], rax
0x180028820  mov     rsi, rcx
0x180028823  xor     r15d, r15d
0x180028826  lea     rcx, [rsp+2D0h+var_270]
0x18002882b  mov     [rsp+2D0h+var_270], r15
0x180028830  mov     r14, rdx
0x180028833  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028838  lea     rcx, [rsp+2D0h+string]
0x18002883d  mov     [rsp+2D0h+var_270], r15
0x180028842  call    ??$Make@V?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@@12@AEBU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@5678@$$QEAUpermission@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@5678@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission &&)
0x180028847  mov     rdi, [rsp+2D0h+string]
0x18002884c  test    rdi, rdi
0x18002884f  jz      short loc_180028876
0x180028851  lea     rcx, [rdi+90h]; this
0x180028858  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x18002885d  mov     ebx, eax
0x18002885f  test    eax, eax
0x180028861  js      short loc_18002887B
0x180028863  mov     byte ptr [rdi+98h], 1
0x18002886a  mov     [rsp+2D0h+var_270], rdi
0x18002886f  mov     [rsp+2D0h+string], r15
0x180028874  jmp     short loc_18002887B
0x180028876  mov     ebx, 8007000Eh
0x18002887b  lea     rcx, [rsp+2D0h+string]
0x180028880  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028885  test    ebx, ebx
0x180028887  jns     short loc_1800288A9
0x180028889  mov     rcx, [rbp+1D8h]; this
0x180028890  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x180028897  mov     r9d, ebx; char *
0x18002889a  mov     edx, 1F1h; void *
0x18002889f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288a4  jmp     loc_180028B2F
0x1800288a9  lea     rcx, [rsp+2D0h+hKey]
0x1800288ae  mov     [rsp+2D0h+hKey], r15
0x1800288b3  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800288b8  mov     r9d, 20019h; unsigned int
0x1800288be  mov     [rsp+2D0h+lpReserved], rax; int
0x1800288c3  lea     rdx, aProperties; "Properties"
0x1800288ca  mov     rcx, r14; HKEY
0x1800288cd  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x1800288d2  mov     ebx, eax
0x1800288d4  cmp     eax, 80070002h
0x1800288d9  jz      loc_180028B15
0x1800288df  cmp     eax, 800703FAh
0x1800288e4  jz      loc_180028B15
0x1800288ea  test    eax, eax
0x1800288ec  jns     short loc_180028918
0x1800288ee  mov     r9d, eax; char *
0x1800288f1  mov     edx, 1FAh; void *
0x1800288f6  mov     rcx, [rbp+1D8h]; this
0x1800288fd  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x180028904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028909  lea     rcx, [rsp+2D0h+hKey]
0x18002890e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028913  jmp     loc_180028B2F
0x180028918  mov     edi, r15d
0x18002891b  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180028920  lea     rax, [rsp+2D0h+Type]
0x180028925  mov     [rsp+2D0h+lpcbData], r15; lpcbData
0x18002892a  lea     r9, [rsp+2D0h+cchValueName]; lpcchValueName
0x18002892f  mov     [rsp+2D0h+lpData], r15; lpData
0x180028934  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x180028938  mov     [rsp+2D0h+lpType], rax; lpType
0x18002893d  mov     edx, edi; dwIndex
0x18002893f  mov     [rsp+2D0h+lpReserved], r15; int
0x180028944  mov     [rsp+2D0h+cchValueName], 0FFh
0x18002894c  mov     [rsp+2D0h+Type], r15d
0x180028951  call    cs:__imp_RegEnumValueW
0x180028957  mov     ebx, eax
0x180028959  test    eax, eax
0x18002895b  jle     short loc_180028966
0x18002895d  movzx   ebx, ax
0x180028960  or      ebx, 80070000h
0x180028966  cmp     ebx, 80070103h
0x18002896c  jz      loc_180028B15
0x180028972  test    ebx, ebx
0x180028974  js      loc_180028B08
0x18002897a  mov     eax, [rsp+2D0h+Type]
0x18002897e  dec     eax
0x180028980  cmp     eax, 1
0x180028983  ja      loc_180028A77
0x180028989  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18002898e  lea     r9, [rbp+1D0h+var_250]
0x180028992  lea     r8, [rbp+1D0h+ValueName]
0x180028996  mov     [rbp+1D0h+var_250], r15
0x18002899a  xor     edx, edx; unsigned __int16 *
0x18002899c  mov     [rbp+1D0h+var_248], r15
0x1800289a0  mov     [rbp+1D0h+var_240], r15
0x1800289a4  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800289a9  mov     ebx, eax
0x1800289ab  test    eax, eax
0x1800289ad  js      loc_180028ADF
0x1800289b3  mov     [rsp+2D0h+var_278], r15
0x1800289b8  lea     rax, [rbp+1D0h+ValueName]
0x1800289bc  mov     [rsp+2D0h+var_260], r15d
0x1800289c1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800289c5  inc     rcx; unsigned __int64
0x1800289c8  cmp     [rax+rcx*2], r15w
0x1800289cd  jnz     short loc_1800289C5
0x1800289cf  lea     rdx, [rsp+2D0h+var_260]; unsigned int *
0x1800289d4  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800289d9  mov     ebx, eax
0x1800289db  test    eax, eax
0x1800289dd  js      loc_180028AB2
0x1800289e3  mov     r8d, [rsp+2D0h+var_260]; unsigned int
0x1800289e8  lea     rdx, [rbp+1D0h+ValueName]; unsigned __int16 *
0x1800289ec  lea     rcx, [rsp+2D0h+var_278]; this
0x1800289f1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800289f6  mov     ebx, eax
0x1800289f8  test    eax, eax
0x1800289fa  js      loc_180028AB2
0x180028a00  mov     rax, [rbp+1D0h+var_250]
0x180028a04  lea     rdx, [rsp+2D0h+var_260]
0x180028a09  lea     rcx, [rsp+2D0h+string]
0x180028a0e  mov     qword ptr [rsp+2D0h+var_260], rax
0x180028a13  mov     [rsp+2D0h+string], r15
0x180028a18  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180028a1d  mov     ebx, eax
0x180028a1f  test    eax, eax
0x180028a21  js      short loc_180028A85
0x180028a23  mov     rcx, [rsp+2D0h+var_270]
0x180028a28  lea     r9, [rsp+2D0h+var_290]
0x180028a2d  mov     r8, [rsp+2D0h+string]
0x180028a32  mov     rdx, [rsp+2D0h+var_278]
0x180028a37  mov     [rsp+2D0h+var_290], r15b
0x180028a3c  mov     rax, [rcx]
0x180028a3f  mov     rax, [rax+50h]
0x180028a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a48  mov     ebx, eax
0x180028a4a  test    eax, eax
0x180028a4c  js      short loc_180028A7E
0x180028a4e  mov     rcx, [rsp+2D0h+string]; string
0x180028a53  call    cs:__imp_WindowsDeleteString
0x180028a59  mov     rcx, [rsp+2D0h+var_278]; string
0x180028a5e  mov     [rsp+2D0h+string], r15
0x180028a63  call    cs:__imp_WindowsDeleteString
0x180028a69  lea     rcx, [rbp+1D0h+var_250]
0x180028a6d  mov     [rsp+2D0h+var_278], r15
0x180028a72  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028a77  inc     edi
0x180028a79  jmp     loc_18002891B
0x180028a7e  mov     edx, 21Fh
0x180028a83  jmp     short loc_180028A8A
0x180028a85  mov     edx, 21Bh; void *
0x180028a8a  mov     rcx, [rbp+1D8h]; this
0x180028a91  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x180028a98  mov     r9d, eax; char *
0x180028a9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028aa0  mov     rcx, [rsp+2D0h+string]; string
0x180028aa5  call    cs:__imp_WindowsDeleteString
0x180028aab  mov     [rsp+2D0h+string], r15
0x180028ab0  jmp     short loc_180028ACD
0x180028ab2  mov     rcx, [rbp+1D8h]; this
0x180028ab9  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x180028ac0  mov     r9d, ebx; char *
0x180028ac3  mov     edx, 217h; void *
0x180028ac8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028acd  mov     rcx, [rsp+2D0h+var_278]; string
0x180028ad2  call    cs:__imp_WindowsDeleteString
0x180028ad8  mov     [rsp+2D0h+var_278], r15
0x180028add  jmp     short loc_180028AFA
0x180028adf  mov     rcx, [rbp+1D8h]; this
0x180028ae6  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\flightsetting"...
0x180028aed  mov     r9d, eax; char *
0x180028af0  mov     edx, 213h; void *
0x180028af5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028afa  lea     rcx, [rbp+1D0h+var_250]
0x180028afe  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028b03  jmp     loc_180028909
0x180028b08  mov     r9d, ebx
0x180028b0b  mov     edx, 207h
0x180028b10  jmp     loc_1800288F6
0x180028b15  mov     rax, [rsp+2D0h+var_270]
0x180028b1a  lea     rcx, [rsp+2D0h+hKey]
0x180028b1f  mov     [rsi], rax
0x180028b22  mov     [rsp+2D0h+var_270], r15
0x180028b27  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028b2c  mov     ebx, r15d
0x180028b2f  lea     rcx, [rsp+2D0h+var_270]
0x180028b34  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028b39  mov     eax, ebx
0x180028b3b  mov     rcx, [rbp+1D0h+var_30]
0x180028b42  xor     rcx, rsp; StackCookie
0x180028b45  call    __security_check_cookie
0x180028b4a  mov     rbx, [rsp+2D0h+arg_10]
0x180028b52  add     rsp, 2B0h
0x180028b59  pop     r15
0x180028b5b  pop     r14
0x180028b5d  pop     rdi
0x180028b5e  pop     rsi
0x180028b5f  pop     rbp
0x180028b60  retn
```
