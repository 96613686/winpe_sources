# SetFulfillmentCachePlaceholder(Microsoft::WRL::Wrappers::HString const &)

- ea: `0x1800dc4b4`
- end: `0x1800dc62a`
- name: `?SetFulfillmentCachePlaceholder@@YAJAEBVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(const struct Microsoft::WRL::Wrappers::HString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800db7b4`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800d57c8`
- `0x1800d5f08`
- `0x1800d5fa8`
- `0x1800d9c20`
- `0x1800da324`
- `0x1800dc164`
- `0x1800dc4b4`
- `0x1801deaf8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc5ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc5f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc60a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc5ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc5f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc60a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc4e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc56e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc5cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc5db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc4e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc56e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc5cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc5db`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetFulfillmentCachePlaceholder(HSTRING *a1)
{
  HSTRING v2; // rbx
  const WCHAR *StringRawBuffer; // rax
  int ContentId; // edi
  unsigned __int64 v5; // r8
  const unsigned __int16 *v6; // rax
  const WCHAR *v7; // rdi
  const WCHAR *v8; // rax
  HSTRING v9; // rcx
  struct IInspectable *v11; // [rsp+20h] [rbp-59h] BYREF
  HSTRING string; // [rsp+28h] [rbp-51h] BYREF
  HSTRING v13; // [rsp+30h] [rbp-49h] BYREF
  struct _GUID v14; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 v15[40]; // [rsp+50h] [rbp-29h] BYREF

  v14 = 0;
  v2 = 0;
  v13 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
  ContentId = GetContentId(StringRawBuffer);
  if ( ContentId >= 0 )
  {
    ContentId = GUIDToString(&v14, v15, v5);
    if ( ContentId >= 0 )
    {
      WindowsDeleteString(0);
      v13 = 0;
      ContentId = ConstructFulfillmentDataCacheKey(v15, &v13);
      v2 = v13;
    }
  }
  v11 = 0;
  string = 0;
  if ( ContentId < 0
    || (Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v11),
        ContentId = Json_CreateEmptyObject((struct Windows::Data::Json::IJsonObject **)&v11),
        ContentId < 0)
    || (v6 = WindowsGetStringRawBuffer(*a1, 0),
        ContentId = Json_SetNamedValue((struct Windows::Data::Json::IJsonObject *)v11, L"PackageFamilyName", v6),
        ContentId < 0)
    || (ContentId = Json_SetNamedValue((struct Windows::Data::Json::IJsonObject *)v11, L"Placeholder", L"TRUE"),
        ContentId < 0) )
  {
    v9 = 0;
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    Json_Stringify(v11, &string);
    v7 = WindowsGetStringRawBuffer(string, 0);
    v8 = WindowsGetStringRawBuffer(v2, 0);
    ContentId = SetCachedFulfillmentData(v8, v7);
    v9 = string;
  }
  WindowsDeleteString(v9);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v11);
  WindowsDeleteString(v2);
  return (unsigned int)ContentId;
}

```

## disassembly

```asm
0x1800dc4b4  push    rbp
0x1800dc4b6  push    rbx
0x1800dc4b7  push    rsi
0x1800dc4b8  push    rdi
0x1800dc4b9  lea     rbp, [rsp-3Fh]
0x1800dc4be  sub     rsp, 0B8h
0x1800dc4c5  mov     rax, cs:__security_cookie
0x1800dc4cc  xor     rax, rsp
0x1800dc4cf  mov     [rbp+57h+var_30], rax
0x1800dc4d3  mov     rsi, rcx
0x1800dc4d6  xorps   xmm0, xmm0
0x1800dc4d9  movups  xmmword ptr [rbp+57h+var_98.Data1], xmm0
0x1800dc4dd  xor     ebx, ebx
0x1800dc4df  mov     [rbp+57h+var_A0], rbx
0x1800dc4e3  xor     edx, edx; length
0x1800dc4e5  mov     rcx, [rcx]; string
0x1800dc4e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc4ee  lea     r8, [rbp+57h+var_98]
0x1800dc4f2  lea     edx, [rbx+4]
0x1800dc4f5  mov     rcx, rax; packageFamilyName
0x1800dc4f8  call    GetContentId
0x1800dc4fd  mov     edi, eax
0x1800dc4ff  test    eax, eax
0x1800dc501  js      short loc_1800DC535
0x1800dc503  lea     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x1800dc507  lea     rcx, [rbp+57h+var_98]; struct _GUID *
0x1800dc50b  call    ?GUIDToString@@YAJAEBU_GUID@@PEAG_K@Z; GUIDToString(_GUID const &,ushort *,unsigned __int64)
0x1800dc510  mov     edi, eax
0x1800dc512  test    eax, eax
0x1800dc514  js      short loc_1800DC535
0x1800dc516  xor     ecx, ecx; string
0x1800dc518  call    cs:__imp_WindowsDeleteString
0x1800dc51e  mov     [rbp+57h+var_A0], rbx
0x1800dc522  lea     rdx, [rbp+57h+var_A0]; HSTRING *
0x1800dc526  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800dc52a  call    ?ConstructFulfillmentDataCacheKey@@YAJPEBGPEAPEAUHSTRING__@@@Z; ConstructFulfillmentDataCacheKey(ushort const *,HSTRING__ * *)
0x1800dc52f  mov     edi, eax
0x1800dc531  mov     rbx, [rbp+57h+var_A0]
0x1800dc535  mov     [rbp+57h+var_B0], 0
0x1800dc53d  mov     [rbp+57h+string], 0
0x1800dc545  test    edi, edi
0x1800dc547  js      loc_1800DC5F4
0x1800dc54d  lea     rcx, [rbp+57h+var_B0]
0x1800dc551  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800dc556  lea     rcx, [rbp+57h+var_B0]; struct Windows::Data::Json::IJsonObject **
0x1800dc55a  call    ?Json_CreateEmptyObject@@YAJPEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_CreateEmptyObject(Windows::Data::Json::IJsonObject * *)
0x1800dc55f  mov     edi, eax
0x1800dc561  test    eax, eax
0x1800dc563  js      loc_1800DC5F4
0x1800dc569  xor     edx, edx; length
0x1800dc56b  mov     rcx, [rsi]; string
0x1800dc56e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc574  mov     r8, rax; unsigned __int16 *
0x1800dc577  lea     rdx, aPackagefamilyn_3; "PackageFamilyName"
0x1800dc57e  mov     rcx, [rbp+57h+var_B0]; struct Windows::Data::Json::IJsonObject *
0x1800dc582  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800dc587  mov     edi, eax
0x1800dc589  test    eax, eax
0x1800dc58b  js      short loc_1800DC5F4
0x1800dc58d  lea     r8, aTrue_1; "TRUE"
0x1800dc594  lea     rdx, aPlaceholder; "Placeholder"
0x1800dc59b  mov     rcx, [rbp+57h+var_B0]; struct Windows::Data::Json::IJsonObject *
0x1800dc59f  call    ?Json_SetNamedValue@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; Json_SetNamedValue(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800dc5a4  mov     edi, eax
0x1800dc5a6  test    eax, eax
0x1800dc5a8  js      short loc_1800DC5F4
0x1800dc5aa  xor     ecx, ecx; string
0x1800dc5ac  call    cs:__imp_WindowsDeleteString
0x1800dc5b2  mov     [rbp+57h+string], 0
0x1800dc5ba  lea     rdx, [rbp+57h+string]; HSTRING *
0x1800dc5be  mov     rcx, [rbp+57h+var_B0]; struct IInspectable *
0x1800dc5c2  call    ?Json_Stringify@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; Json_Stringify(IInspectable *,HSTRING__ * *)
0x1800dc5c7  xor     edx, edx; length
0x1800dc5c9  mov     rcx, [rbp+57h+string]; string
0x1800dc5cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc5d3  mov     rdi, rax
0x1800dc5d6  xor     edx, edx; length
0x1800dc5d8  mov     rcx, rbx; string
0x1800dc5db  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc5e1  mov     rdx, rdi; lpData
0x1800dc5e4  mov     rcx, rax; lpValueName
0x1800dc5e7  call    ?SetCachedFulfillmentData@@YAJPEBG0@Z; SetCachedFulfillmentData(ushort const *,ushort const *)
0x1800dc5ec  mov     edi, eax
0x1800dc5ee  mov     rcx, [rbp+57h+string]
0x1800dc5f2  jmp     short loc_1800DC5F6
0x1800dc5f4  xor     ecx, ecx; string
0x1800dc5f6  call    cs:__imp_WindowsDeleteString
0x1800dc5fc  nop
0x1800dc5fd  lea     rcx, [rbp+57h+var_B0]
0x1800dc601  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800dc606  nop
0x1800dc607  mov     rcx, rbx; string
0x1800dc60a  call    cs:__imp_WindowsDeleteString
0x1800dc610  mov     eax, edi
0x1800dc612  mov     rcx, [rbp+57h+var_30]
0x1800dc616  xor     rcx, rsp; StackCookie
0x1800dc619  call    __security_check_cookie
0x1800dc61e  add     rsp, 0B8h
0x1800dc625  pop     rdi
0x1800dc626  pop     rsi
0x1800dc627  pop     rbx
0x1800dc628  pop     rbp
0x1800dc629  retn
```
