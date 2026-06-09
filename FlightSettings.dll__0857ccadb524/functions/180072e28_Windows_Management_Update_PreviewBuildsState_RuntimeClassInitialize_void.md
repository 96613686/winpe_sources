# Windows::Management::Update::PreviewBuildsState::RuntimeClassInitialize(void)

- ea: `0x180072e28`
- end: `0x180072f57`
- name: `?RuntimeClassInitialize@PreviewBuildsState@Update@Management@Windows@@QEAAJXZ`
- size: `303`
- prototype: `__int64 __fastcall(Windows::Management::Update::PreviewBuildsState *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18006f22c`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x1800714b4`
- `0x180071ee4`
- `0x180072e28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072e72`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072e72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072e59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072e93`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072e93`

## string_xrefs

- `0x180072ea6`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x180072f26`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Management::Update::PreviewBuildsState::RuntimeClassInitialize(
        struct Windows::Foundation::Collections::IPropertySet **this)
{
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  Windows::Management::Update::PreviewBuildsState *v5; // rcx
  int InsiderPropertyMapAsString; // eax
  __int64 v7; // rdx
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this + 5);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, this + 5);
  v4 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    string = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
    hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
    InsiderPropertyMapAsString = Windows::Management::Update::PreviewBuildsState::GetInsiderPropertyMapAsString(
                                   v5,
                                   (unsigned __int16 **)&string);
    v4 = InsiderPropertyMapAsString;
    if ( InsiderPropertyMapAsString >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this + 4);
      InsiderPropertyMapAsString = Windows::Management::Update::PreviewBuildsState::MakeInsiderPropertySetFromJsonString(
                                     (Windows::Management::Update::PreviewBuildsState *)this,
                                     (const unsigned __int16 *)string,
                                     this + 4);
      v4 = InsiderPropertyMapAsString;
      if ( InsiderPropertyMapAsString >= 0 )
      {
LABEL_10:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
        return v4;
      }
      v7 = 124;
    }
    else
    {
      v7 = 122;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
      (const char *)(unsigned int)InsiderPropertyMapAsString,
      (int)string);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x77,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)string);
  return v4;
}

```

## disassembly

```asm
0x180072e28  push    rbp
0x180072e2a  push    rbx
0x180072e2b  push    rsi
0x180072e2c  push    rdi
0x180072e2d  mov     rbp, rsp
0x180072e30  sub     rsp, 58h
0x180072e34  mov     rax, cs:__security_cookie
0x180072e3b  xor     rax, rsp
0x180072e3e  mov     [rbp+var_18], rax
0x180072e42  mov     rdi, rcx
0x180072e45  lea     r9, [rbp+string]; string
0x180072e49  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180072e4d  mov     edx, 20h ; ' '; length
0x180072e52  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180072e59  call    cs:__imp_WindowsCreateStringReference
0x180072e5f  test    eax, eax
0x180072e61  jns     short loc_180072E78
0x180072e63  xor     r9d, r9d; lpArguments
0x180072e66  xor     r8d, r8d; nNumberOfArguments
0x180072e69  lea     edx, [r9+1]; dwExceptionFlags
0x180072e6d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180072e72  call    cs:__imp_RaiseException
0x180072e78  mov     rbx, [rbp+string]
0x180072e7c  lea     rcx, [rdi+28h]
0x180072e80  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072e85  lea     r8, [rdi+28h]
0x180072e89  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180072e90  mov     rcx, rbx
0x180072e93  call    cs:__imp_RoGetActivationFactory
0x180072e99  mov     ebx, eax
0x180072e9b  test    eax, eax
0x180072e9d  jns     short loc_180072EBC
0x180072e9f  mov     rcx, [rbp+20h]; this
0x180072ea3  mov     r9d, eax; char *
0x180072ea6  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x180072ead  mov     edx, 77h ; 'w'; void *
0x180072eb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072eb7  jmp     loc_180072F40
0x180072ebc  mov     [rbp+string], 0
0x180072ec4  mov     qword ptr [rbp+hstringHeader.Reserved], 0
0x180072ecc  mov     qword ptr [rbp+hstringHeader.Reserved+8], 0
0x180072ed4  lea     rcx, [rbp+string]
0x180072ed8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180072edd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180072ee1  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x180072ee5  mov     qword ptr [rbp+hstringHeader.Reserved+8], rax
0x180072ee9  lea     rdx, [rbp+string]; unsigned __int16 **
0x180072eed  call    ?GetInsiderPropertyMapAsString@PreviewBuildsState@Update@Management@Windows@@AEAAJPEAPEAG@Z; Windows::Management::Update::PreviewBuildsState::GetInsiderPropertyMapAsString(ushort * *)
0x180072ef2  mov     ebx, eax
0x180072ef4  test    eax, eax
0x180072ef6  jns     short loc_180072EFF
0x180072ef8  mov     edx, 7Ah ; 'z'
0x180072efd  jmp     short loc_180072F23
0x180072eff  lea     rcx, [rdi+20h]
0x180072f03  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072f08  lea     r8, [rdi+20h]; struct Windows::Foundation::Collections::IPropertySet **
0x180072f0c  mov     rdx, [rbp+string]; unsigned __int16 *
0x180072f10  mov     rcx, rdi; this
0x180072f13  call    ?MakeInsiderPropertySetFromJsonString@PreviewBuildsState@Update@Management@Windows@@AEAAJPEBGPEAPEAUIPropertySet@Collections@Foundation@4@@Z; Windows::Management::Update::PreviewBuildsState::MakeInsiderPropertySetFromJsonString(ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x180072f18  mov     ebx, eax
0x180072f1a  test    eax, eax
0x180072f1c  jns     short loc_180072F37
0x180072f1e  mov     edx, 7Ch ; '|'; void *
0x180072f23  mov     r9d, eax; char *
0x180072f26  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x180072f2d  mov     rcx, [rbp+20h]; this
0x180072f31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072f36  nop
0x180072f37  lea     rcx, [rbp+string]
0x180072f3b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180072f40  mov     eax, ebx
0x180072f42  mov     rcx, [rbp+var_18]
0x180072f46  xor     rcx, rsp; StackCookie
0x180072f49  call    __security_check_cookie
0x180072f4e  add     rsp, 58h
0x180072f52  pop     rdi
0x180072f53  pop     rsi
0x180072f54  pop     rbx
0x180072f55  pop     rbp
0x180072f56  retn
```
