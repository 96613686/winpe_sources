# TryGetLockMessageFromResponse(ushort *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800115e0`
- end: `0x1800118d2`
- name: `?TryGetLockMessageFromResponse@@YAJPEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800107e0`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x180004e10`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x1800115e0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011668`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800117e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800117e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011850`

## string_xrefs

- `0x180011647`: `Windows.Data.Json.JsonObject`
- `0x180011695`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x180011681`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObjectStatics.GetAddressOf()))`
- `0x1800116ec`: `CHR(pJsonObjectStatics->Parse(HStringReference(pwszResponse).Get(), pJsonObject.GetAddressOf()))`
- `0x180011747`: `CHR(pJsonObject->GetNamedValue(HStringReference(JSON_LOCK_MESSAGE).Get(), pJsonValue.GetAddressOf()))`
- `0x180011789`: `CHR(pJsonValue->get_ValueType(&eValueType))`
- `0x1800117bb`: `CBR(eValueType == JsonValueType_String)`
- `0x180011813`: `CHR(pJsonValue->GetString(hstrMessage.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall TryGetLockMessageFromResponse(const WCHAR *a1, __int64 a2)
{
  int v3; // edx
  int v4; // ecx
  int ActivationFactory; // ebx
  char v6; // r8
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v9; // rax
  int v10; // edx
  int v11; // ecx
  char v12; // r8
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v15; // rax
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // edx
  int v23; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // r8
  int v26; // ecx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v30; // [rsp+0h] [rbp-98h] BYREF
  HSTRING string; // [rsp+30h] [rbp-68h] BYREF
  int v32; // [rsp+38h] [rbp-60h] BYREF
  __int64 v33; // [rsp+40h] [rbp-58h] BYREF
  __int64 v34; // [rsp+48h] [rbp-50h] BYREF
  __int64 v35; // [rsp+50h] [rbp-48h] BYREF
  const WCHAR *v36; // [rsp+58h] [rbp-40h] BYREF
  HSTRING_HEADER v37; // [rsp+60h] [rbp-38h] BYREF
  __int64 v38; // [rsp+78h] [rbp-20h]

  v36 = a1;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  string = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v37, L"Windows.Data.Json.JsonObject", 0x1Du, 0x1Cu);
  ActivationFactory = RoGetActivationFactory(v38, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v35);
  if ( ActivationFactory >= 0 )
  {
    v7 = v35;
    v8 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v35 + 48LL);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v37, &v36, v6);
    ActivationFactory = v8(v7, v9[1].Reserved.Reserved1, &v34);
    if ( ActivationFactory >= 0 )
    {
      v13 = v34;
      v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v34 + 48LL);
      v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v37, (const WCHAR **)off_18002B518, v12);
      ActivationFactory = v14(v13, v15[1].Reserved.Reserved1, &v33);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 48LL))(v33, &v32);
        if ( ActivationFactory >= 0 )
        {
          if ( v32 == 3 )
          {
            v20 = v33;
            v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 64LL);
            WindowsDeleteString(string);
            string = 0;
            ActivationFactory = v21(v20, &string);
            if ( ActivationFactory >= 0 )
            {
              try
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                std::wstring::assign(a2, (__int64)StringRawBuffer, v25);
              }
              catch ( std::bad_alloc )
              {
                LODWORD(v36) = -2147024882;
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v26,
                    (unsigned int)&v30,
                    -2147024882,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                    122,
                    "CHR(((HRESULT)0x8007000EL))");
                ActivationFactory = (int)v36;
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v23,
                v22,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                114,
                "CHR(pJsonValue->GetString(hstrMessage.GetAddressOf()))");
            }
          }
          else
          {
            ActivationFactory = -2147024809;
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v19,
                v18,
                -2147024809,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
                113,
                "CBR(eValueType == JsonValueType_String)");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v19,
            v18,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            112,
            "CHR(pJsonValue->get_ValueType(&eValueType))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v17,
          v16,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          111,
          "CHR(pJsonObject->GetNamedValue(HStringReference(JSON_LOCK_MESSAGE).Get(), pJsonValue.GetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        110,
        "CHR(pJsonObjectStatics->Parse(HStringReference(pwszResponse).Get(), pJsonObject.GetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v4,
      v3,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
      109,
      "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObjectStatics.GetAddressOf()))");
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  v27 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800115e0  mov     r11, rsp
0x1800115e3  mov     [r11+18h], rbx
0x1800115e7  mov     [r11+20h], rdi
0x1800115eb  push    r14
0x1800115ed  sub     rsp, 90h
0x1800115f4  mov     rax, cs:__security_cookie
0x1800115fb  xor     rax, rsp
0x1800115fe  mov     [rsp+98h+var_18], rax
0x180011606  mov     r14, rdx
0x180011609  mov     [r11-40h], rcx
0x18001160d  mov     qword ptr [r11-48h], 0
0x180011615  mov     qword ptr [r11-50h], 0
0x18001161d  mov     qword ptr [r11-58h], 0
0x180011625  mov     [rsp+98h+var_60], 0
0x18001162d  mov     qword ptr [r11-68h], 0
0x180011635  mov     qword ptr [r11-20h], 0
0x18001163d  mov     r9d, 1Ch; unsigned int
0x180011643  lea     r8d, [r9+1]; unsigned int
0x180011647  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001164e  lea     rcx, [r11-38h]; hstringHeader
0x180011652  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011657  lea     r8, [rsp+98h+var_48]
0x18001165c  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180011663  mov     rcx, [rsp+98h+var_20]
0x180011668  call    cs:__imp_RoGetActivationFactory
0x18001166e  mov     ebx, eax
0x180011670  test    eax, eax
0x180011672  jns     short loc_1800116A9
0x180011674  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001167b  jz      loc_18001184B
0x180011681  lea     rax, aChrGetactivati_0; "CHR(GetActivationFactory(HStringReferen"...
0x180011688  mov     [rsp+98h+var_70], rax
0x18001168d  mov     [rsp+98h+var_78], 16Dh
0x180011695  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001169c  mov     r8d, ebx
0x18001169f  call    McTemplateU0dsqs_EventWriteTransfer
0x1800116a4  jmp     loc_18001184B
0x1800116a9  mov     rdi, [rsp+98h+var_48]
0x1800116ae  mov     rax, [rdi]
0x1800116b1  mov     rbx, [rax+30h]
0x1800116b5  lea     rdx, [rsp+98h+var_40]
0x1800116ba  lea     rcx, [rsp+98h+var_38]
0x1800116bf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800116c4  nop
0x1800116c5  lea     r8, [rsp+98h+var_50]
0x1800116ca  mov     rdx, [rax+18h]
0x1800116ce  mov     rcx, rdi
0x1800116d1  mov     rax, rbx
0x1800116d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d9  mov     ebx, eax
0x1800116db  test    eax, eax
0x1800116dd  jns     short loc_180011702
0x1800116df  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800116e6  jz      loc_18001184B
0x1800116ec  lea     rax, aChrPjsonobject_3; "CHR(pJsonObjectStatics->Parse(HStringRe"...
0x1800116f3  mov     [rsp+98h+var_70], rax
0x1800116f8  mov     [rsp+98h+var_78], 16Eh
0x180011700  jmp     short loc_180011695
0x180011702  mov     rdi, [rsp+98h+var_50]
0x180011707  mov     rax, [rdi]
0x18001170a  mov     rbx, [rax+30h]
0x18001170e  lea     rdx, off_18002B518; "LockMessage"
0x180011715  lea     rcx, [rsp+98h+var_38]
0x18001171a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001171f  nop
0x180011720  lea     r8, [rsp+98h+var_58]
0x180011725  mov     rdx, [rax+18h]
0x180011729  mov     rcx, rdi
0x18001172c  mov     rax, rbx
0x18001172f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011734  mov     ebx, eax
0x180011736  test    eax, eax
0x180011738  jns     short loc_180011760
0x18001173a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011741  jz      loc_18001184B
0x180011747  lea     rax, aChrPjsonobject_4; "CHR(pJsonObject->GetNamedValue(HStringR"...
0x18001174e  mov     [rsp+98h+var_70], rax
0x180011753  mov     [rsp+98h+var_78], 16Fh
0x18001175b  jmp     loc_180011695
0x180011760  mov     rcx, [rsp+98h+var_58]
0x180011765  mov     rax, [rcx]
0x180011768  lea     rdx, [rsp+98h+var_60]
0x18001176d  mov     rax, [rax+30h]
0x180011771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011776  mov     ebx, eax
0x180011778  test    eax, eax
0x18001177a  jns     short loc_1800117A2
0x18001177c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011783  jz      loc_18001184B
0x180011789  lea     rax, aChrPjsonvalueG_0; "CHR(pJsonValue->get_ValueType(&eValueTy"...
0x180011790  mov     [rsp+98h+var_70], rax
0x180011795  mov     [rsp+98h+var_78], 170h
0x18001179d  jmp     loc_180011695
0x1800117a2  cmp     [rsp+98h+var_60], 3
0x1800117a7  jz      short loc_1800117D4
0x1800117a9  mov     ebx, 80070057h
0x1800117ae  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800117b5  jz      loc_18001184B
0x1800117bb  lea     rax, aCbrEvaluetypeJ; "CBR(eValueType == JsonValueType_String)"
0x1800117c2  mov     [rsp+98h+var_70], rax
0x1800117c7  mov     [rsp+98h+var_78], 171h
0x1800117cf  jmp     loc_180011695
0x1800117d4  mov     rdi, [rsp+98h+var_58]
0x1800117d9  mov     rax, [rdi]
0x1800117dc  mov     rbx, [rax+40h]
0x1800117e0  mov     rcx, [rsp+98h+string]; string
0x1800117e5  call    cs:__imp_WindowsDeleteString
0x1800117eb  mov     [rsp+98h+string], 0
0x1800117f4  lea     rdx, [rsp+98h+string]
0x1800117f9  mov     rcx, rdi
0x1800117fc  mov     rax, rbx
0x1800117ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011804  mov     ebx, eax
0x180011806  test    eax, eax
0x180011808  jns     short loc_18001182C
0x18001180a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011811  jz      short loc_18001184B
0x180011813  lea     rax, aChrPjsonvalueG; "CHR(pJsonValue->GetString(hstrMessage.G"...
0x18001181a  mov     [rsp+98h+var_70], rax
0x18001181f  mov     [rsp+98h+var_78], 172h
0x180011827  jmp     loc_180011695
0x18001182c  xor     edx, edx; length
0x18001182e  mov     rcx, [rsp+98h+string]; string
0x180011833  call    cs:__imp_WindowsGetStringRawBuffer
0x180011839  mov     rdx, rax
0x18001183c  mov     rcx, r14
0x18001183f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180011844  nop
0x180011845  jmp     short loc_18001184B
0x180011847  mov     ebx, dword ptr [rsp+98h+var_40]
0x18001184b  mov     rcx, [rsp+98h+string]; string
0x180011850  call    cs:__imp_WindowsDeleteString
0x180011856  mov     [rsp+98h+string], 0
0x18001185f  lea     rcx, [rsp+98h+var_58]
0x180011864  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011869  nop
0x18001186a  mov     rcx, [rsp+98h+var_50]
0x18001186f  test    rcx, rcx
0x180011872  jz      short loc_18001188A
0x180011874  mov     [rsp+98h+var_50], 0
0x18001187d  mov     rax, [rcx]
0x180011880  mov     rax, [rax+10h]
0x180011884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011889  nop
0x18001188a  mov     rcx, [rsp+98h+var_48]
0x18001188f  test    rcx, rcx
0x180011892  jz      short loc_1800118AA
0x180011894  mov     [rsp+98h+var_48], 0
0x18001189d  mov     rax, [rcx]
0x1800118a0  mov     rax, [rax+10h]
0x1800118a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118a9  nop
0x1800118aa  mov     eax, ebx
0x1800118ac  mov     rcx, [rsp+98h+var_18]
0x1800118b4  xor     rcx, rsp; StackCookie
0x1800118b7  call    __security_check_cookie
0x1800118bc  lea     r11, [rsp+98h+var_8]
0x1800118c4  mov     rbx, [r11+20h]
0x1800118c8  mov     rdi, [r11+28h]
0x1800118cc  mov     rsp, r11
0x1800118cf  pop     r14
0x1800118d1  retn
```
