# SetCachedLastScanTime(Microsoft::WRL::Wrappers::HString const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,ushort const *)

- ea: `0x1800dc2cc`
- end: `0x1800dc4ab`
- name: `?SetCachedLastScanTime@@YAJAEBVHString@Wrappers@WRL@Microsoft@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEBG@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800db7b4`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18002ec2c`
- `0x1800370f4`
- `0x180043320`
- `0x1800d57c8`
- `0x1800d5f08`
- `0x1800d5fa8`
- `0x1800daccc`
- `0x1800db024`
- `0x1800dc2cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc433`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dc433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc3c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc44c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc46b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc3c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc44c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc46b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc31d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc37e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc3e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc31d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc37e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc3e6`

## string_xrefs

- `0x1800dc3fd`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State\CategoryCache`
- `0x1800dc499`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SetCachedLastScanTime(
        Microsoft::WRL::Wrappers::Details **a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  HSTRING v5; // r8
  const WCHAR *StringRawBuffer; // r14
  HSTRING v7; // rbx
  int EmptyObject; // eax
  signed int CachedFulfillmentDataPlaceholderAllowed; // edi
  const unsigned __int16 *v10; // rax
  PCWSTR v11; // rax
  PCWSTR v12; // rsi
  __int64 v13; // rdi
  const WCHAR *RegistryLocation; // rax
  LSTATUS v15; // eax
  int lpData; // [rsp+20h] [rbp-39h]
  struct IInspectable *v18; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v19; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v20; // [rsp+40h] [rbp-19h] BYREF
  HSTRING string; // [rsp+48h] [rbp-11h] BYREF
  wchar_t Buffer[28]; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  time_point_iso8601::time_point_iso8601(Buffer);
  GetCategoryIdFromPackageFamilyNameOrEmpty(&string, a1, v5);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v18 = 0;
  v7 = 0;
  v19 = 0;
  v20 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
  EmptyObject = Json_CreateEmptyObject((struct Windows::Data::Json::IJsonObject **)&v18);
  if ( EmptyObject < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
      (const char *)(unsigned int)EmptyObject,
      lpData);
  WindowsDeleteString(0);
  v20 = 0;
  CachedFulfillmentDataPlaceholderAllowed = GetCachedFulfillmentDataPlaceholderAllowed(StringRawBuffer, &v20);
  if ( CachedFulfillmentDataPlaceholderAllowed >= 0 )
  {
    v10 = WindowsGetStringRawBuffer(v20, 0);
    CachedFulfillmentDataPlaceholderAllowed = Json_SetNamedValue(
                                                (struct Windows::Data::Json::IJsonObject *)v18,
                                                L"FulfillmentData",
                                                v10);
    if ( CachedFulfillmentDataPlaceholderAllowed >= 0 )
    {
      CachedFulfillmentDataPlaceholderAllowed = Json_SetNamedValue(
                                                  (struct Windows::Data::Json::IJsonObject *)v18,
                                                  L"LastScanTime",
                                                  a3);
      if ( CachedFulfillmentDataPlaceholderAllowed >= 0 )
      {
        WindowsDeleteString(0);
        v19 = 0;
        CachedFulfillmentDataPlaceholderAllowed = Json_Stringify(v18, &v19);
        v7 = v19;
        if ( CachedFulfillmentDataPlaceholderAllowed >= 0 )
        {
          v11 = WindowsGetStringRawBuffer(v19, 0);
          v12 = v11;
          v13 = -1;
          do
            ++v13;
          while ( v11[v13] );
          RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                              &qword_1802CAE68,
                                              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State\\CategoryCache");
          v15 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, RegistryLocation, StringRawBuffer, 1u, v12, 2 * v13 + 2);
          CachedFulfillmentDataPlaceholderAllowed = v15;
          if ( v15 > 0 )
            CachedFulfillmentDataPlaceholderAllowed = (unsigned __int16)v15 | 0x80070000;
        }
      }
    }
  }
  WindowsDeleteString(v20);
  WindowsDeleteString(v7);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v18);
  WindowsDeleteString(string);
  return (unsigned int)CachedFulfillmentDataPlaceholderAllowed;
}

```

## disassembly

```asm
0x1800dc2cc  mov     [rsp-8+arg_18], rbx
0x1800dc2d1  mov     [rsp-8+arg_8], rdx
0x1800dc2d6  push    rbp
0x1800dc2d7  push    rsi
0x1800dc2d8  push    rdi
0x1800dc2d9  push    r14
0x1800dc2db  push    r15
0x1800dc2dd  lea     rbp, [rsp-37h]
0x1800dc2e2  sub     rsp, 90h
0x1800dc2e9  mov     rax, cs:__security_cookie
0x1800dc2f0  xor     rax, rsp
0x1800dc2f3  mov     [rbp+57h+var_28], rax
0x1800dc2f7  mov     rsi, r8
0x1800dc2fa  mov     rbx, rcx
0x1800dc2fd  lea     rdx, [rbp+57h+arg_8]
0x1800dc301  lea     rcx, [rbp+57h+Buffer]; Buffer
0x1800dc305  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800dc30a  mov     rdx, rbx
0x1800dc30d  lea     rcx, [rbp+57h+string]
0x1800dc311  call    ?GetCategoryIdFromPackageFamilyNameOrEmpty@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV1234@PEAUHKEY__@@@Z; GetCategoryIdFromPackageFamilyNameOrEmpty(Microsoft::WRL::Wrappers::HString const &,HKEY__ *)
0x1800dc316  nop
0x1800dc317  xor     edx, edx; length
0x1800dc319  mov     rcx, [rbp+57h+string]; string
0x1800dc31d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc323  mov     r14, rax
0x1800dc326  xor     r15d, r15d
0x1800dc329  mov     [rbp+57h+var_80], r15
0x1800dc32d  mov     ebx, r15d
0x1800dc330  mov     [rbp+57h+var_78], rbx
0x1800dc334  mov     [rbp+57h+var_70], r15
0x1800dc338  lea     rcx, [rbp+57h+var_80]
0x1800dc33c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800dc341  lea     rcx, [rbp+57h+var_80]; struct Windows::Data::Json::IJsonObject **
0x1800dc345  call    ?Json_CreateEmptyObject@@YAJPEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_CreateEmptyObject(Windows::Data::Json::IJsonObject * *)
0x1800dc34a  mov     rcx, [rbp+5Fh]; this
0x1800dc34e  test    eax, eax
0x1800dc350  js      loc_1800DC496
0x1800dc356  xor     ecx, ecx; string
0x1800dc358  call    cs:__imp_WindowsDeleteString
0x1800dc35e  mov     [rbp+57h+var_70], r15
0x1800dc362  lea     rdx, [rbp+57h+var_70]; HSTRING *
0x1800dc366  mov     rcx, r14; lpValue
0x1800dc369  call    ?GetCachedFulfillmentDataPlaceholderAllowed@@YAJPEBGPEAPEAUHSTRING__@@@Z; GetCachedFulfillmentDataPlaceholderAllowed(ushort const *,HSTRING__ * *)
0x1800dc36e  mov     edi, eax
0x1800dc370  test    eax, eax
0x1800dc372  js      loc_1800DC448
0x1800dc378  xor     edx, edx; length
0x1800dc37a  mov     rcx, [rbp+57h+var_70]; string
0x1800dc37e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc384  mov     r8, rax; unsigned __int16 *
0x1800dc387  lea     rdx, aFulfillmentdat; "FulfillmentData"
0x1800dc38e  mov     rcx, [rbp+57h+var_80]; struct Windows::Data::Json::IJsonObject *
0x1800dc392  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800dc397  mov     edi, eax
0x1800dc399  test    eax, eax
0x1800dc39b  js      loc_1800DC448
0x1800dc3a1  mov     r8, rsi; unsigned __int16 *
0x1800dc3a4  lea     rdx, aLastscantime; "LastScanTime"
0x1800dc3ab  mov     rcx, [rbp+57h+var_80]; struct Windows::Data::Json::IJsonObject *
0x1800dc3af  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800dc3b4  mov     edi, eax
0x1800dc3b6  test    eax, eax
0x1800dc3b8  js      loc_1800DC448
0x1800dc3be  xor     ecx, ecx; string
0x1800dc3c0  call    cs:__imp_WindowsDeleteString
0x1800dc3c6  mov     [rbp+57h+var_78], r15
0x1800dc3ca  lea     rdx, [rbp+57h+var_78]; HSTRING *
0x1800dc3ce  mov     rcx, [rbp+57h+var_80]; struct IInspectable *
0x1800dc3d2  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x1800dc3d7  mov     edi, eax
0x1800dc3d9  mov     rbx, [rbp+57h+var_78]
0x1800dc3dd  test    eax, eax
0x1800dc3df  js      short loc_1800DC448
0x1800dc3e1  xor     edx, edx; length
0x1800dc3e3  mov     rcx, rbx; string
0x1800dc3e6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc3ec  mov     rsi, rax
0x1800dc3ef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800dc3f3  inc     rdi
0x1800dc3f6  cmp     [rax+rdi*2], r15w
0x1800dc3fb  jnz     short loc_1800DC3F3
0x1800dc3fd  lea     rdx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800dc404  lea     rcx, qword_1802CAE68
0x1800dc40b  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x1800dc410  lea     ecx, ds:2[rdi*2]
0x1800dc417  mov     [rsp+0B0h+cbData], ecx; cbData
0x1800dc41b  mov     [rsp+0B0h+lpData], rsi; lpData
0x1800dc420  mov     r9d, 1; dwType
0x1800dc426  mov     r8, r14; lpValueName
0x1800dc429  mov     rdx, rax; lpSubKey
0x1800dc42c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dc433  call    cs:__imp_RegSetKeyValueW
0x1800dc439  mov     edi, eax
0x1800dc43b  test    eax, eax
0x1800dc43d  jle     short loc_1800DC448
0x1800dc43f  movzx   edi, ax
0x1800dc442  or      edi, 80070000h
0x1800dc448  mov     rcx, [rbp+57h+var_70]; string
0x1800dc44c  call    cs:__imp_WindowsDeleteString
0x1800dc452  nop
0x1800dc453  mov     rcx, rbx; string
0x1800dc456  call    cs:__imp_WindowsDeleteString
0x1800dc45c  nop
0x1800dc45d  lea     rcx, [rbp+57h+var_80]
0x1800dc461  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800dc466  nop
0x1800dc467  mov     rcx, [rbp+57h+string]; string
0x1800dc46b  call    cs:__imp_WindowsDeleteString
0x1800dc471  mov     eax, edi
0x1800dc473  mov     rcx, [rbp+57h+var_28]
0x1800dc477  xor     rcx, rsp; StackCookie
0x1800dc47a  call    __security_check_cookie
0x1800dc47f  mov     rbx, [rsp+0B0h+arg_18]
0x1800dc487  add     rsp, 90h
0x1800dc48e  pop     r15
0x1800dc490  pop     r14
0x1800dc492  pop     rdi
0x1800dc493  pop     rsi
0x1800dc494  pop     rbp
0x1800dc495  retn
0x1800dc496  mov     r9d, eax; char *
0x1800dc499  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800dc4a0  mov     edx, 14Eh; void *
0x1800dc4a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
