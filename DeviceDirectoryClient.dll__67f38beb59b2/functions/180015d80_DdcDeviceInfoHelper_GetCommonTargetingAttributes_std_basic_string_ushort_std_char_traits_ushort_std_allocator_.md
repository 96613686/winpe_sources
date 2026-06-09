# DdcDeviceInfoHelper::GetCommonTargetingAttributes(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180015d80`
- end: `0x180015fb5`
- name: `?GetCommonTargetingAttributes@DdcDeviceInfoHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x1800024c0`
- `0x180004e10`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x180015d80`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015df2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015df2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015f2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015f2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015ecf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015ecf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015f47`

## string_xrefs

- `0x180015e1f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180015f11`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180015e0b`: `CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Internal_Flighting_ClientAttributes).Get(), spCommonTargetingAttributesFactory.GetAddressOf()))`
- `0x180015ea5`: `CHR(spCommonTargetingAttributesFactory->GetClientAttributesForApp( HStringReference(CTAC_APP_NAME).Get(), HStringReference(L"6").Get(), spClientAttributes.GetAddressOf()))`
- `0x180015efd`: `CHR(spClientAttributes->ToJsonString(hstrJsonAtttributes.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcDeviceInfoHelper::GetCommonTargetingAttributes(__int64 a1)
{
  int v2; // edx
  int v3; // ecx
  int ActivationFactory; // ebx
  __int64 v5; // rsi
  __int64 (__fastcall *v6)(__int64, PVOID, __int64, __int64 *); // rdi
  __int64 v7; // rbx
  char v8; // r8
  HSTRING_HEADER *v9; // rax
  int v10; // edx
  int v11; // ecx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // [rsp+0h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-98h] BYREF
  __int64 v24; // [rsp+38h] [rbp-90h] BYREF
  __int64 v25; // [rsp+40h] [rbp-88h] BYREF
  int v26; // [rsp+48h] [rbp-80h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-78h] BYREF
  __int64 v28; // [rsp+68h] [rbp-60h]
  HSTRING_HEADER v29; // [rsp+70h] [rbp-58h] BYREF

  v25 = 0;
  v24 = 0;
  string = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.ClientAttributes",
    0x2Cu,
    0x2Bu);
  ActivationFactory = RoGetActivationFactory(v28, &GUID_41845433_1668_4264_8a63_315eb82ab0d6, &v25);
  if ( ActivationFactory >= 0 )
  {
    v5 = v25;
    v6 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, __int64 *))(*(_QWORD *)v25 + 48LL);
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"6", 2u, 1u);
    v7 = v28;
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v29, (const WCHAR **)off_18002B640, v8);
    ActivationFactory = v6(v5, v9[1].Reserved.Reserved1, v7, &v24);
    if ( ActivationFactory >= 0 )
    {
      v12 = v24;
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 48LL);
      WindowsDeleteString(string);
      try
      {
        string = 0;
        v14 = v13(v12, &string);
      }
      catch ( std::bad_alloc )
      {
        v26 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v16,
            (unsigned int)&v22,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            235,
            "CHR(((HRESULT)0x8007000EL))");
        ActivationFactory = v26;
        goto LABEL_13;
      }
      ActivationFactory = v14;
      if ( v14 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        std::wstring::assign(a1, (__int64)StringRawBuffer, v18);
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v16,
          v15,
          v14,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          230,
          "CHR(spClientAttributes->ToJsonString(hstrJsonAtttributes.GetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        226,
        "CHR(spCommonTargetingAttributesFactory->GetClientAttributesForApp( HStringReference(CTAC_APP_NAME).Get(), HStrin"
        "gReference(L\"6\").Get(), spClientAttributes.GetAddressOf()))",
        string);
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      221,
      "CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Internal_Flighting_ClientAttributes).Get(), spComm"
      "onTargetingAttributesFactory.GetAddressOf()))",
      string);
  }
LABEL_13:
  WindowsDeleteString(string);
  string = 0;
  v19 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180015d80  push    rbx
0x180015d82  push    rsi
0x180015d83  push    rdi
0x180015d84  push    r15
0x180015d86  sub     rsp, 0A8h
0x180015d8d  mov     rax, cs:__security_cookie
0x180015d94  xor     rax, rsp
0x180015d97  mov     [rsp+0C8h+var_38], rax
0x180015d9f  mov     r15, rcx
0x180015da2  mov     [rsp+0C8h+var_88], 0
0x180015dab  mov     [rsp+0C8h+var_90], 0
0x180015db4  mov     [rsp+0C8h+string], 0
0x180015dbd  mov     [rsp+0C8h+var_60], 0
0x180015dc6  mov     r9d, 2Bh ; '+'; unsigned int
0x180015dcc  lea     r8d, [r9+1]; unsigned int
0x180015dd0  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_ClientAttributes@@3QBGB; "Windows.Internal.Flighting.ClientAttrib"...
0x180015dd7  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x180015ddc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015de1  lea     r8, [rsp+0C8h+var_88]
0x180015de6  lea     rdx, _GUID_41845433_1668_4264_8a63_315eb82ab0d6
0x180015ded  mov     rcx, [rsp+0C8h+var_60]
0x180015df2  call    cs:__imp_RoGetActivationFactory
0x180015df8  mov     ebx, eax
0x180015dfa  test    eax, eax
0x180015dfc  jns     short loc_180015E33
0x180015dfe  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015e05  jz      loc_180015F42
0x180015e0b  lea     rax, aChrGetactivati_3; "CHR(GetActivationFactory( HStringRefere"...
0x180015e12  mov     [rsp+0C8h+var_A0], rax
0x180015e17  mov     [rsp+0C8h+var_A8], 6DDh
0x180015e1f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180015e26  mov     r8d, ebx
0x180015e29  call    McTemplateU0dsqs_EventWriteTransfer
0x180015e2e  jmp     loc_180015F42
0x180015e33  mov     rsi, [rsp+0C8h+var_88]
0x180015e38  mov     rax, [rsi]
0x180015e3b  mov     rdi, [rax+30h]
0x180015e3f  mov     [rsp+0C8h+var_60], 0
0x180015e48  mov     r9d, 1; unsigned int
0x180015e4e  lea     r8d, [r9+1]; unsigned int
0x180015e52  lea     rdx, sourceString; "6"
0x180015e59  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x180015e5e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015e63  nop
0x180015e64  mov     rbx, [rsp+0C8h+var_60]
0x180015e69  lea     rdx, off_18002B640; "DDC"
0x180015e70  lea     rcx, [rsp+0C8h+var_58]
0x180015e75  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015e7a  nop
0x180015e7b  lea     r9, [rsp+0C8h+var_90]
0x180015e80  mov     r8, rbx
0x180015e83  mov     rdx, [rax+18h]
0x180015e87  mov     rcx, rsi
0x180015e8a  mov     rax, rdi
0x180015e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e92  mov     ebx, eax
0x180015e94  test    eax, eax
0x180015e96  jns     short loc_180015EBE
0x180015e98  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015e9f  jz      loc_180015F42
0x180015ea5  lea     rax, aChrSpcommontar; "CHR(spCommonTargetingAttributesFactory-"...
0x180015eac  mov     [rsp+0C8h+var_A0], rax
0x180015eb1  mov     [rsp+0C8h+var_A8], 6E2h
0x180015eb9  jmp     loc_180015E1F
0x180015ebe  mov     rdi, [rsp+0C8h+var_90]
0x180015ec3  mov     rax, [rdi]
0x180015ec6  mov     rbx, [rax+30h]
0x180015eca  mov     rcx, [rsp+0C8h+string]; string
0x180015ecf  call    cs:__imp_WindowsDeleteString
0x180015ed5  mov     [rsp+0C8h+string], 0
0x180015ede  lea     rdx, [rsp+0C8h+string]
0x180015ee3  mov     rcx, rdi
0x180015ee6  mov     rax, rbx
0x180015ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eee  mov     ebx, eax
0x180015ef0  test    eax, eax
0x180015ef2  jns     short loc_180015F23
0x180015ef4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015efb  jz      short loc_180015F21
0x180015efd  lea     rax, aChrSpclientatt; "CHR(spClientAttributes->ToJsonString(hs"...
0x180015f04  mov     [rsp+0C8h+var_A0], rax
0x180015f09  mov     [rsp+0C8h+var_A8], 6E6h
0x180015f11  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180015f18  mov     r8d, ebx
0x180015f1b  call    McTemplateU0dsqs_EventWriteTransfer
0x180015f20  nop
0x180015f21  jmp     short loc_180015F42
0x180015f23  xor     edx, edx; length
0x180015f25  mov     rcx, [rsp+0C8h+string]; string
0x180015f2a  call    cs:__imp_WindowsGetStringRawBuffer
0x180015f30  mov     rdx, rax
0x180015f33  mov     rcx, r15
0x180015f36  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180015f3b  nop
0x180015f3c  jmp     short loc_180015F42
0x180015f3e  mov     ebx, [rsp+0C8h+var_80]
0x180015f42  mov     rcx, [rsp+0C8h+string]; string
0x180015f47  call    cs:__imp_WindowsDeleteString
0x180015f4d  mov     [rsp+0C8h+string], 0
0x180015f56  mov     rcx, [rsp+0C8h+var_90]
0x180015f5b  test    rcx, rcx
0x180015f5e  jz      short loc_180015F76
0x180015f60  mov     [rsp+0C8h+var_90], 0
0x180015f69  mov     rax, [rcx]
0x180015f6c  mov     rax, [rax+10h]
0x180015f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f75  nop
0x180015f76  mov     rcx, [rsp+0C8h+var_88]
0x180015f7b  test    rcx, rcx
0x180015f7e  jz      short loc_180015F96
0x180015f80  mov     [rsp+0C8h+var_88], 0
0x180015f89  mov     rax, [rcx]
0x180015f8c  mov     rax, [rax+10h]
0x180015f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f95  nop
0x180015f96  mov     eax, ebx
0x180015f98  mov     rcx, [rsp+0C8h+var_38]
0x180015fa0  xor     rcx, rsp; StackCookie
0x180015fa3  call    __security_check_cookie
0x180015fa8  add     rsp, 0A8h
0x180015faf  pop     r15
0x180015fb1  pop     rdi
0x180015fb2  pop     rsi
0x180015fb3  pop     rbx
0x180015fb4  retn
```
