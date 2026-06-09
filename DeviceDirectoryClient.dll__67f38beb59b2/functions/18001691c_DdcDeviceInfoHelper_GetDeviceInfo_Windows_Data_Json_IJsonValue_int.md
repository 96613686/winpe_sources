# DdcDeviceInfoHelper::GetDeviceInfo(Windows::Data::Json::IJsonValue * *,int)

- ea: `0x18001691c`
- end: `0x180016a9d`
- name: `?GetDeviceInfo@DdcDeviceInfoHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@H@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c034`
- `0x18000ca4c`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fd48`
- `0x1800139c8`
- `0x180013b38`
- `0x18001691c`
- `0x180016aa4`
- `0x1800183c4`
- `0x18002a010`

## string_xrefs

- `0x18001695d`: `Windows.Data.Json.JsonObject`
- `0x18001698e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pDeviceInfo.GetAddressOf()))`
- `0x1800169a2`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetDeviceInfo(struct Windows::Data::Json::IJsonValue **a1, int a2)
{
  int v4; // edx
  int v5; // ecx
  int DeviceInfoLight; // ebx
  int v7; // edx
  int v8; // ecx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  struct Windows::Data::Json::IJsonValue *v13; // rax
  struct Windows::Data::Json::IJsonObject *v14; // rcx
  struct Windows::Data::Json::IJsonObject *v16; // [rsp+30h] [rbp-48h] BYREF
  struct Windows::Data::Json::IJsonValue *v17; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  __int64 v19; // [rsp+58h] [rbp-20h]

  v16 = 0;
  v17 = 0;
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  DeviceInfoLight = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v19, &v16);
  if ( DeviceInfoLight >= 0 )
  {
    DeviceInfoLight = DdcDeviceInfoHelper::GetDeviceInfoLight(v16);
    if ( DeviceInfoLight >= 0 )
    {
      if ( a2 || (DeviceInfoLight = DdcDeviceInfoHelper::GetDeviceInfoHeavy(v16), DeviceInfoLight >= 0) )
      {
        DeviceInfoLight = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v16,
                            (__int64)&v17);
        if ( DeviceInfoLight >= 0 )
        {
          v13 = v17;
          v17 = 0;
          *a1 = v13;
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v12,
            v11,
            DeviceInfoLight,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            90,
            "CHR(pDeviceInfo.As(&pDeviceInfoAsValue))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          DeviceInfoLight,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          87,
          "CHR(GetDeviceInfoHeavy(pDeviceInfo.Get()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        DeviceInfoLight,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        83,
        "CHR(GetDeviceInfoLight(pDeviceInfo.Get()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      DeviceInfoLight,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      81,
      "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pDeviceInfo.GetAddressOf()))");
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v14 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)DeviceInfoLight;
}

```

## disassembly

```asm
0x18001691c  push    rbp
0x18001691e  push    rbx
0x18001691f  push    rsi
0x180016920  push    rdi
0x180016921  mov     rbp, rsp
0x180016924  sub     rsp, 78h
0x180016928  mov     rax, cs:__security_cookie
0x18001692f  xor     rax, rsp
0x180016932  mov     [rbp+var_18], rax
0x180016936  mov     edi, edx
0x180016938  mov     rsi, rcx
0x18001693b  mov     [rbp+var_48], 0
0x180016943  mov     [rbp+var_40], 0
0x18001694b  mov     [rbp+var_20], 0
0x180016953  mov     r9d, 1Ch; unsigned int
0x180016959  lea     r8d, [r9+1]; unsigned int
0x18001695d  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180016964  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180016968  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001696d  nop
0x18001696e  lea     rdx, [rbp+var_48]
0x180016972  mov     rcx, [rbp+var_20]
0x180016976  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18001697b  mov     ebx, eax
0x18001697d  test    eax, eax
0x18001697f  jns     short loc_1800169B6
0x180016981  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016988  jz      loc_180016A5E
0x18001698e  lea     rax, aChrActivateins_6; "CHR(ActivateInstance(HStringReference(R"...
0x180016995  mov     [rsp+78h+var_50], rax
0x18001699a  mov     [rsp+78h+var_58], 51h ; 'Q'
0x1800169a2  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800169a9  mov     r8d, ebx
0x1800169ac  call    McTemplateU0dsqs_EventWriteTransfer
0x1800169b1  jmp     loc_180016A5E
0x1800169b6  mov     rcx, [rbp+var_48]; struct Windows::Data::Json::IJsonObject *
0x1800169ba  call    ?GetDeviceInfoLight@DdcDeviceInfoHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z; DdcDeviceInfoHelper::GetDeviceInfoLight(Windows::Data::Json::IJsonObject *)
0x1800169bf  mov     ebx, eax
0x1800169c1  test    eax, eax
0x1800169c3  jns     short loc_1800169E8
0x1800169c5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800169cc  jz      loc_180016A5E
0x1800169d2  lea     rax, aChrGetdevicein; "CHR(GetDeviceInfoLight(pDeviceInfo.Get("...
0x1800169d9  mov     [rsp+78h+var_50], rax
0x1800169de  mov     [rsp+78h+var_58], 53h ; 'S'
0x1800169e6  jmp     short loc_1800169A2
0x1800169e8  test    edi, edi
0x1800169ea  jnz     short loc_180016A1A
0x1800169ec  mov     rcx, [rbp+var_48]; struct Windows::Data::Json::IJsonObject *
0x1800169f0  call    ?GetDeviceInfoHeavy@DdcDeviceInfoHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z; DdcDeviceInfoHelper::GetDeviceInfoHeavy(Windows::Data::Json::IJsonObject *)
0x1800169f5  mov     ebx, eax
0x1800169f7  test    eax, eax
0x1800169f9  jns     short loc_180016A1A
0x1800169fb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016a02  jz      short loc_180016A5E
0x180016a04  lea     rax, aChrGetdevicein_0; "CHR(GetDeviceInfoHeavy(pDeviceInfo.Get("...
0x180016a0b  mov     [rsp+78h+var_50], rax
0x180016a10  mov     [rsp+78h+var_58], 57h ; 'W'
0x180016a18  jmp     short loc_1800169A2
0x180016a1a  lea     rdx, [rbp+var_40]
0x180016a1e  lea     rcx, [rbp+var_48]
0x180016a22  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180016a27  mov     ebx, eax
0x180016a29  test    eax, eax
0x180016a2b  jns     short loc_180016A4F
0x180016a2d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016a34  jz      short loc_180016A5E
0x180016a36  lea     rax, aChrPdeviceinfo_9; "CHR(pDeviceInfo.As(&pDeviceInfoAsValue)"...
0x180016a3d  mov     [rsp+78h+var_50], rax
0x180016a42  mov     [rsp+78h+var_58], 5Ah ; 'Z'
0x180016a4a  jmp     loc_1800169A2
0x180016a4f  mov     rax, [rbp+var_40]
0x180016a53  mov     [rbp+var_40], 0
0x180016a5b  mov     [rsi], rax
0x180016a5e  lea     rcx, [rbp+var_40]
0x180016a62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016a67  nop
0x180016a68  mov     rcx, [rbp+var_48]
0x180016a6c  test    rcx, rcx
0x180016a6f  jz      short loc_180016A86
0x180016a71  mov     [rbp+var_48], 0
0x180016a79  mov     rax, [rcx]
0x180016a7c  mov     rax, [rax+10h]
0x180016a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a85  nop
0x180016a86  mov     eax, ebx
0x180016a88  mov     rcx, [rbp+var_18]
0x180016a8c  xor     rcx, rsp; StackCookie
0x180016a8f  call    __security_check_cookie
0x180016a94  add     rsp, 78h
0x180016a98  pop     rdi
0x180016a99  pop     rsi
0x180016a9a  pop     rbx
0x180016a9b  pop     rbp
0x180016a9c  retn
```
