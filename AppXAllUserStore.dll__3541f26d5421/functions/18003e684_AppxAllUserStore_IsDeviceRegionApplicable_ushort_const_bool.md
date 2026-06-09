# AppxAllUserStore::IsDeviceRegionApplicable(ushort const *,bool *)

- ea: `0x18003e684`
- end: `0x18003eab9`
- name: `?IsDeviceRegionApplicable@AppxAllUserStore@@YAJPEBGPEA_N@Z`
- size: `1077`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038560`
- `0x18003906c`

## callees

- `0x180004920`
- `0x180008db0`
- `0x18000d770`
- `0x180017f50`
- `0x180018248`
- `0x18001a464`
- `0x18001ca24`
- `0x180036bf4`
- `0x1800384e8`
- `0x18003e684`
- `0x18003f2ec`
- `0x180040304`
- `0x18004c9d0`
- `0x18004d010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18003e824`
- `msvcrt!wcstok_s` at `0x18003ea3d`
- `msvcrt!wcstok_s` at `0x18003e824`
- `msvcrt!wcstok_s` at `0x18003ea3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e849`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18003e787`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18003e7a9`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18003e787`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x18003e7a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e732`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e732`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e8e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e8e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ea6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e899`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::IsDeviceRegionApplicable(AppxAllUserStore *this, unsigned __int16 *a2, bool *a3)
{
  __int64 v5; // rcx
  int ValueW; // eax
  __int64 v7; // rdx
  bool v8; // sf
  GEOID v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  wchar_t *v12; // rcx
  char v13; // bl
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // rdi
  signed int LastError; // eax
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // rdi
  const unsigned __int16 *v26; // r12
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  int v28; // eax
  PCWSTR v29; // rax
  const unsigned __int16 *v30; // r15
  int v31; // eax
  wchar_t *v33; // rcx
  char v34; // bl
  wchar_t *v35; // rax
  const unsigned __int16 *v36; // rdi
  int pdwType; // [rsp+20h] [rbp-79h]
  int pdwTypea; // [rsp+20h] [rbp-79h]
  const char *pvData; // [rsp+28h] [rbp-71h]
  HSTRING v40; // [rsp+40h] [rbp-59h] BYREF
  HSTRING v41; // [rsp+48h] [rbp-51h] BYREF
  __int64 v42; // [rsp+50h] [rbp-49h] BYREF
  GEOID Location; // [rsp+58h] [rbp-41h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-39h] BYREF
  UINT32 length; // [rsp+68h] [rbp-31h] BYREF
  UINT32 v46; // [rsp+6Ch] [rbp-2Dh] BYREF
  wchar_t *Context; // [rsp+70h] [rbp-29h] BYREF
  wchar_t *v48; // [rsp+78h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-19h] BYREF
  HSTRING string; // [rsp+98h] [rbp-1h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+7h] BYREF
  __int16 v52; // [rsp+A4h] [rbp+Bh]
  WCHAR GeoData[4]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( !Common::String::CaseInsensitiveEquals((const unsigned __int16 *)this, L"all") )
  {
    hkey = 0;
    ValueW = wil::reg::open_unique_key_nothrow(
               v5,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\DeviceRegion",
               &hkey);
    if ( ValueW < 0 )
    {
      v7 = 577;
LABEL_10:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v7,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)ValueW);
      goto LABEL_27;
    }
    if ( hkey )
    {
      Location = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"DeviceRegion", 0x10u, 0, &Location, &pcbData);
      v8 = ValueW < 0;
      if ( ValueW > 0 )
      {
        ValueW = (unsigned __int16)ValueW | 0x80070000;
        v8 = ValueW < 0;
      }
      if ( v8 )
      {
        v7 = 581;
        goto LABEL_10;
      }
      v9 = Location;
      *(_QWORD *)GeoData = 0;
      pcbData = 0;
      v52 = 0;
      if ( GetGeoInfoW(Location, 4u, (LPWSTR)&pcbData, 3, 0) && GetGeoInfoW(v9, 5u, GeoData, 4, 0) )
      {
        memset(&hstringHeader, 0, 20);
        v10 = Common::StringBuffer::SetValueFromString(
                (Common::StringBuffer *)&hstringHeader,
                (const unsigned __int16 *)this);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v12 = *(wchar_t **)&hstringHeader.Reserved.Reserved2[8];
          v13 = 0;
          Context = 0;
          while ( 1 )
          {
            v14 = wcstok_s(v12, L";", &Context);
            v15 = v14;
            if ( !v14 )
              break;
            if ( Common::String::CaseInsensitiveEquals(v14, (const unsigned __int16 *)&pcbData)
              || Common::String::CaseInsensitiveEquals(v15, GeoData) )
            {
              v13 = 1;
              break;
            }
            v12 = 0;
          }
          *(_BYTE *)a2 = v13;
          v11 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24E,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
            (const char *)(unsigned int)v10,
            pdwTypea);
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&hstringHeader);
        goto LABEL_39;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(pvData) = v9;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x268,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)LastError,
        (int)"GetGeoInfoW failed for GEOID:%d",
        pvData);
    }
LABEL_27:
    v42 = 0;
    string = 0;
    v17 = WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &hstringHeader, &string);
    if ( v17 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
      JUMPOUT(0x18003EAB8LL);
    }
    v20 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(
            (__int64)string,
            &v42);
    v11 = v20;
    if ( v20 >= 0 )
    {
      v21 = v42;
      v40 = 0;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 56LL);
      WindowsDeleteString(0);
      v40 = 0;
      v23 = v22(v21, &v40);
      v11 = v23;
      if ( v23 >= 0 )
      {
        length = 2;
        StringRawBuffer = WindowsGetStringRawBuffer(v40, &length);
        v25 = v42;
        v41 = 0;
        v26 = StringRawBuffer;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 64LL);
        WindowsDeleteString(0);
        v41 = 0;
        v28 = v27(v25, &v41);
        v11 = v28;
        if ( v28 >= 0 )
        {
          v46 = 3;
          v29 = WindowsGetStringRawBuffer(v41, &v46);
          memset(&hstringHeader, 0, 20);
          v30 = v29;
          v31 = Common::StringBuffer::SetValueFromString(
                  (Common::StringBuffer *)&hstringHeader,
                  (const unsigned __int16 *)this);
          v11 = v31;
          if ( v31 >= 0 )
          {
            v33 = *(wchar_t **)&hstringHeader.Reserved.Reserved2[8];
            v34 = 0;
            v48 = 0;
            while ( 1 )
            {
              v35 = wcstok_s(v33, L";", &v48);
              v36 = v35;
              if ( !v35 )
                break;
              if ( Common::String::CaseInsensitiveEquals(v35, v26) || Common::String::CaseInsensitiveEquals(v36, v30) )
              {
                v34 = 1;
                break;
              }
              v33 = 0;
            }
            *(_BYTE *)a2 = v34;
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&hstringHeader);
            WindowsDeleteString(v41);
            v41 = 0;
            WindowsDeleteString(v40);
            v40 = 0;
            Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v42);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x280,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
            (const char *)(unsigned int)v31,
            pdwType);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&hstringHeader);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x27B,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
            (const char *)(unsigned int)v28,
            pdwType);
        }
        WindowsDeleteString(v41);
        v41 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x275,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
          (const char *)(unsigned int)v23,
          pdwType);
      }
      WindowsDeleteString(v40);
      v40 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x271,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v20,
        pdwType);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v42);
LABEL_39:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return v11;
  }
  *(_BYTE *)a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x18003e684  mov     [rsp-8+arg_10], rbx
0x18003e689  push    rbp
0x18003e68a  push    rsi
0x18003e68b  push    rdi
0x18003e68c  push    r12
0x18003e68e  push    r13
0x18003e690  push    r14
0x18003e692  push    r15
0x18003e694  lea     rbp, [rsp-27h]
0x18003e699  sub     rsp, 0C0h
0x18003e6a0  mov     rax, cs:__security_cookie
0x18003e6a7  xor     rax, rsp
0x18003e6aa  mov     [rbp+57h+var_40], rax
0x18003e6ae  mov     rsi, rdx
0x18003e6b1  mov     r14, rcx
0x18003e6b4  lea     rdx, aAll; "all"
0x18003e6bb  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x18003e6c0  xor     r13d, r13d
0x18003e6c3  test    eax, eax
0x18003e6c5  jz      short loc_18003E6CF
0x18003e6c7  mov     byte ptr [rsi], 1
0x18003e6ca  jmp     loc_18003EA88
0x18003e6cf  lea     r8, [rbp+57h+hkey]
0x18003e6d3  mov     [rbp+57h+hkey], r13
0x18003e6d7  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003e6de  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003e6e3  lea     r15, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003e6ea  test    eax, eax
0x18003e6ec  jns     short loc_18003E6F5
0x18003e6ee  mov     edx, 241h
0x18003e6f3  jmp     short loc_18003E751
0x18003e6f5  mov     rcx, [rbp+57h+hkey]; hkey
0x18003e6f9  test    rcx, rcx
0x18003e6fc  jz      loc_18003E87D
0x18003e702  mov     edi, 4
0x18003e707  mov     [rbp+57h+Location], r13d
0x18003e70b  lea     rax, [rbp+57h+var_50]
0x18003e70f  mov     [rbp+57h+var_50], edi
0x18003e712  mov     [rsp+0F0h+pcbData], rax; pcbData
0x18003e717  lea     r8, aDeviceregion; "DeviceRegion"
0x18003e71e  lea     rax, [rbp+57h+Location]
0x18003e722  xor     edx, edx; lpSubKey
0x18003e724  mov     [rsp+0F0h+pvData], rax; pvData
0x18003e729  lea     r9d, [rdi+0Ch]; dwFlags
0x18003e72d  mov     [rsp+0F0h+pdwType], r13; int
0x18003e732  call    cs:__imp_RegGetValueW
0x18003e738  mov     r12d, 80070000h
0x18003e73e  test    eax, eax
0x18003e740  jle     short loc_18003E74A
0x18003e742  movzx   eax, ax
0x18003e745  or      eax, r12d
0x18003e748  test    eax, eax
0x18003e74a  jns     short loc_18003E765
0x18003e74c  mov     edx, 245h; void *
0x18003e751  mov     rcx, [rbp+5Fh]; this
0x18003e755  mov     r8, r15; unsigned int
0x18003e758  mov     r9d, eax; char *
0x18003e75b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003e760  jmp     loc_18003E87D
0x18003e765  mov     ebx, [rbp+57h+Location]
0x18003e768  lea     r8, [rbp+57h+var_50]; lpGeoData
0x18003e76c  xor     eax, eax
0x18003e76e  mov     qword ptr [rbp+57h+GeoData], r13
0x18003e772  mov     edx, edi; GeoType
0x18003e774  mov     [rbp+57h+var_50], eax
0x18003e777  mov     ecx, ebx; Location
0x18003e779  mov     [rbp+57h+var_4C], ax
0x18003e77d  mov     word ptr [rsp+0F0h+pdwType], r13w; LangId
0x18003e783  lea     r9d, [rax+3]; cchData
0x18003e787  call    cs:__imp_GetGeoInfoW
0x18003e78d  test    eax, eax
0x18003e78f  jz      loc_18003E849
0x18003e795  mov     r9d, edi; cchData
0x18003e798  mov     word ptr [rsp+0F0h+pdwType], r13w; int
0x18003e79e  lea     r8, [rbp+57h+GeoData]; lpGeoData
0x18003e7a2  mov     edx, 5; GeoType
0x18003e7a7  mov     ecx, ebx; Location
0x18003e7a9  call    cs:__imp_GetGeoInfoW
0x18003e7af  test    eax, eax
0x18003e7b1  jz      loc_18003E849
0x18003e7b7  xorps   xmm0, xmm0
0x18003e7ba  mov     dword ptr [rbp+57h+hstringHeader.Reserved+10h], r13d
0x18003e7be  mov     rdx, r14; Src
0x18003e7c1  lea     rcx, [rbp+57h+hstringHeader]; this
0x18003e7c5  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18003e7c9  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18003e7ce  mov     ebx, eax
0x18003e7d0  test    eax, eax
0x18003e7d2  jns     short loc_18003E7EA
0x18003e7d4  mov     rcx, [rbp+5Fh]; this
0x18003e7d8  mov     r9d, eax; char *
0x18003e7db  mov     r8, r15; unsigned int
0x18003e7de  mov     edx, 24Eh; void *
0x18003e7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e7e8  jmp     short loc_18003E83B
0x18003e7ea  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18003e7ee  mov     bl, r13b
0x18003e7f1  mov     [rbp+57h+Context], r13
0x18003e7f5  jmp     short loc_18003E819
0x18003e7f7  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x18003e7fb  mov     rcx, rdi; unsigned __int16 *
0x18003e7fe  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x18003e803  test    eax, eax
0x18003e805  jnz     short loc_18003E834
0x18003e807  lea     rdx, [rbp+57h+GeoData]; unsigned __int16 *
0x18003e80b  mov     rcx, rdi; unsigned __int16 *
0x18003e80e  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x18003e813  test    eax, eax
0x18003e815  jnz     short loc_18003E834
0x18003e817  xor     ecx, ecx; String
0x18003e819  lea     r8, [rbp+57h+Context]; Context
0x18003e81d  lea     rdx, Delimiter; ";"
0x18003e824  call    cs:__imp_wcstok_s
0x18003e82a  mov     rdi, rax
0x18003e82d  test    rax, rax
0x18003e830  jnz     short loc_18003E7F7
0x18003e832  jmp     short loc_18003E836
0x18003e834  mov     bl, 1
0x18003e836  mov     [rsi], bl
0x18003e838  mov     ebx, r13d
0x18003e83b  lea     rcx, [rbp+57h+hstringHeader]; this
0x18003e83f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003e844  jmp     loc_18003E9F5
0x18003e849  call    cs:__imp_GetLastError
0x18003e84f  test    eax, eax
0x18003e851  jle     short loc_18003E859
0x18003e853  movzx   eax, ax
0x18003e856  or      eax, r12d
0x18003e859  mov     rcx, [rbp+5Fh]; this
0x18003e85d  lea     rdx, aGetgeoinfowFai; "GetGeoInfoW failed for GEOID:%d"
0x18003e864  mov     dword ptr [rsp+0F0h+pvData], ebx; char *
0x18003e868  mov     r9d, eax; char *
0x18003e86b  mov     [rsp+0F0h+pdwType], rdx; int
0x18003e870  mov     r8, r15; unsigned int
0x18003e873  mov     edx, 268h; void *
0x18003e878  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e87d  lea     r9, [rbp+57h+string]; string
0x18003e881  mov     [rbp+57h+var_A0], r13
0x18003e885  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003e889  mov     [rbp+57h+string], r13
0x18003e88d  mov     edx, 26h ; '&'; length
0x18003e892  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x18003e899  call    cs:__imp_WindowsCreateStringReference
0x18003e89f  test    eax, eax
0x18003e8a1  js      loc_18003EAB1
0x18003e8a7  mov     rcx, [rbp+57h+string]
0x18003e8ab  lea     rdx, [rbp+57h+var_A0]
0x18003e8af  call    ??$ActivateInstance@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>)
0x18003e8b4  mov     ebx, eax
0x18003e8b6  test    eax, eax
0x18003e8b8  jns     short loc_18003E8D3
0x18003e8ba  mov     rcx, [rbp+5Fh]; this
0x18003e8be  mov     r9d, eax; char *
0x18003e8c1  mov     r8, r15; unsigned int
0x18003e8c4  mov     edx, 271h; void *
0x18003e8c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e8ce  jmp     loc_18003E9EC
0x18003e8d3  mov     rdi, [rbp+57h+var_A0]
0x18003e8d7  xor     ecx, ecx; string
0x18003e8d9  mov     [rbp+57h+var_B0], r13
0x18003e8dd  mov     rax, [rdi]
0x18003e8e0  mov     rbx, [rax+38h]
0x18003e8e4  call    cs:__imp_WindowsDeleteString
0x18003e8ea  lea     rdx, [rbp+57h+var_B0]
0x18003e8ee  mov     [rbp+57h+var_B0], r13
0x18003e8f2  mov     rcx, rdi
0x18003e8f5  mov     rax, rbx
0x18003e8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8fd  mov     ebx, eax
0x18003e8ff  test    eax, eax
0x18003e901  jns     short loc_18003E91C
0x18003e903  mov     rcx, [rbp+5Fh]; this
0x18003e907  mov     r9d, eax; char *
0x18003e90a  mov     r8, r15; unsigned int
0x18003e90d  mov     edx, 275h; void *
0x18003e912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e917  jmp     loc_18003E9DE
0x18003e91c  mov     rcx, [rbp+57h+var_B0]; string
0x18003e920  lea     rdx, [rbp+57h+length]; length
0x18003e924  mov     [rbp+57h+length], 2
0x18003e92b  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e931  mov     rdi, [rbp+57h+var_A0]
0x18003e935  xor     ecx, ecx; string
0x18003e937  mov     [rbp+57h+var_A8], r13
0x18003e93b  mov     r12, rax
0x18003e93e  mov     rdx, [rdi]
0x18003e941  mov     rbx, [rdx+40h]
0x18003e945  call    cs:__imp_WindowsDeleteString
0x18003e94b  lea     rdx, [rbp+57h+var_A8]
0x18003e94f  mov     [rbp+57h+var_A8], r13
0x18003e953  mov     rcx, rdi
0x18003e956  mov     rax, rbx
0x18003e959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e95e  mov     ebx, eax
0x18003e960  test    eax, eax
0x18003e962  jns     short loc_18003E97A
0x18003e964  mov     rcx, [rbp+5Fh]; this
0x18003e968  mov     r9d, eax; char *
0x18003e96b  mov     r8, r15; unsigned int
0x18003e96e  mov     edx, 27Bh; void *
0x18003e973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e978  jmp     short loc_18003E9D0
0x18003e97a  mov     rcx, [rbp+57h+var_A8]; string
0x18003e97e  lea     rdx, [rbp+57h+var_84]; length
0x18003e982  mov     [rbp+57h+var_84], 3
0x18003e989  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e98f  xorps   xmm0, xmm0
0x18003e992  mov     dword ptr [rbp+57h+hstringHeader.Reserved+10h], r13d
0x18003e996  mov     rdx, r14; Src
0x18003e999  lea     rcx, [rbp+57h+hstringHeader]; this
0x18003e99d  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18003e9a1  mov     r15, rax
0x18003e9a4  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18003e9a9  mov     ebx, eax
0x18003e9ab  test    eax, eax
0x18003e9ad  jns     short loc_18003EA05
0x18003e9af  mov     rcx, [rbp+5Fh]; this
0x18003e9b3  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003e9ba  mov     r9d, eax; char *
0x18003e9bd  mov     edx, 280h; void *
0x18003e9c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e9c7  lea     rcx, [rbp+57h+hstringHeader]; this
0x18003e9cb  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003e9d0  mov     rcx, [rbp+57h+var_A8]; string
0x18003e9d4  call    cs:__imp_WindowsDeleteString
0x18003e9da  mov     [rbp+57h+var_A8], r13
0x18003e9de  mov     rcx, [rbp+57h+var_B0]; string
0x18003e9e2  call    cs:__imp_WindowsDeleteString
0x18003e9e8  mov     [rbp+57h+var_B0], r13
0x18003e9ec  lea     rcx, [rbp+57h+var_A0]
0x18003e9f0  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18003e9f5  lea     rcx, [rbp+57h+hkey]
0x18003e9f9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003e9fe  mov     eax, ebx
0x18003ea00  jmp     loc_18003EA8A
0x18003ea05  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18003ea09  mov     bl, r13b
0x18003ea0c  mov     [rbp+57h+var_78], r13
0x18003ea10  jmp     short loc_18003EA32
0x18003ea12  mov     rdx, r12; unsigned __int16 *
0x18003ea15  mov     rcx, rdi; unsigned __int16 *
0x18003ea18  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x18003ea1d  test    eax, eax
0x18003ea1f  jnz     short loc_18003EA4D
0x18003ea21  mov     rdx, r15; unsigned __int16 *
0x18003ea24  mov     rcx, rdi; unsigned __int16 *
0x18003ea27  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x18003ea2c  test    eax, eax
0x18003ea2e  jnz     short loc_18003EA4D
0x18003ea30  xor     ecx, ecx; String
0x18003ea32  lea     r8, [rbp+57h+var_78]; Context
0x18003ea36  lea     rdx, Delimiter; ";"
0x18003ea3d  call    cs:__imp_wcstok_s
0x18003ea43  mov     rdi, rax
0x18003ea46  test    rax, rax
0x18003ea49  jnz     short loc_18003EA12
0x18003ea4b  jmp     short loc_18003EA4F
0x18003ea4d  mov     bl, 1
0x18003ea4f  lea     rcx, [rbp+57h+hstringHeader]; this
0x18003ea53  mov     [rsi], bl
0x18003ea55  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003ea5a  mov     rcx, [rbp+57h+var_A8]; string
0x18003ea5e  call    cs:__imp_WindowsDeleteString
0x18003ea64  mov     rcx, [rbp+57h+var_B0]; string
0x18003ea68  mov     [rbp+57h+var_A8], r13
0x18003ea6c  call    cs:__imp_WindowsDeleteString
0x18003ea72  lea     rcx, [rbp+57h+var_A0]
0x18003ea76  mov     [rbp+57h+var_B0], r13
0x18003ea7a  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18003ea7f  lea     rcx, [rbp+57h+hkey]
0x18003ea83  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ea88  xor     eax, eax
0x18003ea8a  mov     rcx, [rbp+57h+var_40]
0x18003ea8e  xor     rcx, rsp; StackCookie
0x18003ea91  call    __security_check_cookie
0x18003ea96  mov     rbx, [rsp+0F0h+arg_10]
0x18003ea9e  add     rsp, 0C0h
0x18003eaa5  pop     r15
0x18003eaa7  pop     r14
0x18003eaa9  pop     r13
0x18003eaab  pop     r12
0x18003eaad  pop     rdi
0x18003eaae  pop     rsi
0x18003eaaf  pop     rbp
0x18003eab0  retn
0x18003eab1  mov     ecx, eax; this
0x18003eab3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
