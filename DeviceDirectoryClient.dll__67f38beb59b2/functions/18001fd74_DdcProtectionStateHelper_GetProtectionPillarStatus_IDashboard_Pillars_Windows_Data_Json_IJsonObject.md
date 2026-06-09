# DdcProtectionStateHelper::GetProtectionPillarStatus(IDashboard *,Pillars,Windows::Data::Json::IJsonObject *)

- ea: `0x18001fd74`
- end: `0x180020061`
- name: `?GetProtectionPillarStatus@DdcProtectionStateHelper@@CAJPEAUIDashboard@@W4Pillars@@PEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `749`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020068`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x18001f6fc`
- `0x18001f734`
- `0x18001fc54`
- `0x18001fd74`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fe7b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fe7b`

## string_xrefs

- `0x18001fe5c`: `Windows.Data.Json.JsonValue`
- `0x18001fe94`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18002000d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001fde7`: `CHR(GetProtectionPillarFieldNames(ePillar, &pwszJsonHealth, &pwszJsonStatus))`
- `0x18001fef5`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszHealthAsString).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001ff4c`: `CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonHealth).Get(), pJsonValue.Get()))`
- `0x18001ffa9`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszStatusAsString).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001fff9`: `CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonStatus).Get(), pJsonValue.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcProtectionStateHelper::GetProtectionPillarStatus(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // edx
  int v7; // ecx
  int ProtectionPillarFieldNames; // ebx
  __int64 v9; // rcx
  int v10; // r8d
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, __int64 *); // rbx
  char v15; // r8
  HSTRING_HEADER *v16; // rax
  int v17; // edx
  int v18; // ecx
  char v19; // r8
  __int64 (__fastcall *v20)(__int64, PVOID, __int64); // rdi
  __int64 v21; // rbx
  HSTRING_HEADER *v22; // rax
  int v23; // edx
  int v24; // ecx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, PVOID, __int64 *); // rbx
  char v27; // r8
  HSTRING_HEADER *v28; // rax
  int v29; // edx
  int v30; // ecx
  char v31; // r8
  __int64 (__fastcall *v32)(__int64, PVOID, __int64); // rdi
  __int64 v33; // rbx
  HSTRING_HEADER *v34; // rax
  int v35; // edx
  int v36; // ecx
  __int64 v37; // rcx
  __int64 v39; // [rsp+30h] [rbp-29h] BYREF
  __int64 v40; // [rsp+38h] [rbp-21h] BYREF
  __int64 v41; // [rsp+40h] [rbp-19h] BYREF
  const wchar_t *v42; // [rsp+48h] [rbp-11h] BYREF
  const wchar_t *v43; // [rsp+50h] [rbp-9h] BYREF
  const WCHAR *PillarHealthMapping; // [rsp+58h] [rbp-1h] BYREF
  const WCHAR *PillarStatusFlagMapping; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v47; // [rsp+80h] [rbp+27h]

  v42 = 0;
  v43 = 0;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  ProtectionPillarFieldNames = DdcProtectionStateHelper::GetProtectionPillarFieldNames(a2, &v42, &v43);
  if ( ProtectionPillarFieldNames >= 0 )
  {
    if ( a1 && (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a1 + 48LL))(a1, a2, &v40) >= 0 )
    {
      v9 = HIDWORD(v40);
    }
    else
    {
      v40 = 0x100000000LL;
      v9 = 1;
    }
    PillarHealthMapping = (const WCHAR *)GetPillarHealthMapping(v9);
    PillarStatusFlagMapping = GetPillarStatusFlagMapping(v10);
    v47 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ProtectionPillarFieldNames = RoGetActivationFactory(v47, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v41);
    if ( ProtectionPillarFieldNames >= 0 )
    {
      v13 = v41;
      v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v41 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &PillarHealthMapping, v15);
      ProtectionPillarFieldNames = v14(v13, v16[1].Reserved.Reserved1, &v39);
      if ( ProtectionPillarFieldNames >= 0 )
      {
        v20 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
        v21 = v39;
        v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v42, v19);
        ProtectionPillarFieldNames = v20(a3, v22[1].Reserved.Reserved1, v21);
        if ( ProtectionPillarFieldNames >= 0 )
        {
          v25 = v41;
          v26 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v41 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  &PillarStatusFlagMapping,
                  v27);
          ProtectionPillarFieldNames = v26(v25, v28[1].Reserved.Reserved1, &v39);
          if ( ProtectionPillarFieldNames >= 0 )
          {
            v32 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
            v33 = v39;
            v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v43, v31);
            ProtectionPillarFieldNames = v32(a3, v34[1].Reserved.Reserved1, v33);
            if ( ProtectionPillarFieldNames < 0
              && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v36,
                v35,
                ProtectionPillarFieldNames,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                165,
                "CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonStatus).Get(), pJsonValue.Get()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v30,
              v29,
              ProtectionPillarFieldNames,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
              164,
              "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszStatusAsString).Get(), pJsonValue.ReleaseAnd"
              "GetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v24,
            v23,
            ProtectionPillarFieldNames,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
            163,
            "CHR(pProtectionState->SetNamedValue(HStringReference(pwszJsonHealth).Get(), pJsonValue.Get()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v18,
          v17,
          ProtectionPillarFieldNames,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          162,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszHealthAsString).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        ProtectionPillarFieldNames,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        161,
        "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      ProtectionPillarFieldNames,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      147,
      "CHR(GetProtectionPillarFieldNames(ePillar, &pwszJsonHealth, &pwszJsonStatus))");
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  v37 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return (unsigned int)ProtectionPillarFieldNames;
}

```

## disassembly

```asm
0x18001fd74  push    rbp
0x18001fd76  push    rbx
0x18001fd77  push    rsi
0x18001fd78  push    rdi
0x18001fd79  push    r14
0x18001fd7b  lea     rbp, [rsp-37h]
0x18001fd80  sub     rsp, 90h
0x18001fd87  mov     rax, cs:__security_cookie
0x18001fd8e  xor     rax, rsp
0x18001fd91  mov     [rbp+57h+var_28], rax
0x18001fd95  mov     r14, r8
0x18001fd98  mov     esi, edx
0x18001fd9a  mov     rdi, rcx
0x18001fd9d  mov     [rbp+57h+var_68], 0
0x18001fda5  mov     [rbp+57h+var_60], 0
0x18001fdad  mov     [rbp+57h+var_78], 0
0x18001fdb5  mov     [rbp+57h+var_70], 0
0x18001fdbd  mov     [rbp+57h+var_80], 0
0x18001fdc5  lea     r8, [rbp+57h+var_60]
0x18001fdc9  lea     rdx, [rbp+57h+var_68]
0x18001fdcd  mov     ecx, esi
0x18001fdcf  call    ?GetProtectionPillarFieldNames@DdcProtectionStateHelper@@CAJW4Pillars@@PEAPEBG1@Z; DdcProtectionStateHelper::GetProtectionPillarFieldNames(Pillars,ushort const * *,ushort const * *)
0x18001fdd4  mov     ebx, eax
0x18001fdd6  test    eax, eax
0x18001fdd8  jns     short loc_18001FE00
0x18001fdda  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001fde1  jz      loc_18002001D
0x18001fde7  lea     rax, aChrGetprotecti_4; "CHR(GetProtectionPillarFieldNames(ePill"...
0x18001fdee  mov     [rsp+0B0h+var_88], rax
0x18001fdf3  mov     [rsp+0B0h+var_90], 293h
0x18001fdfb  jmp     loc_18002000D
0x18001fe00  test    rdi, rdi
0x18001fe03  jz      short loc_18001FE27
0x18001fe05  mov     rax, [rdi]
0x18001fe08  lea     r8, [rbp+57h+var_78]
0x18001fe0c  mov     edx, esi
0x18001fe0e  mov     rcx, rdi
0x18001fe11  mov     rax, [rax+30h]
0x18001fe15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe1a  test    eax, eax
0x18001fe1c  js      short loc_18001FE27
0x18001fe1e  mov     ecx, dword ptr [rbp+57h+var_78+4]
0x18001fe21  mov     r8d, dword ptr [rbp+57h+var_78]
0x18001fe25  jmp     short loc_18001FE35
0x18001fe27  xor     r8d, r8d
0x18001fe2a  mov     dword ptr [rbp+57h+var_78], r8d
0x18001fe2e  lea     ecx, [r8+1]
0x18001fe32  mov     dword ptr [rbp+57h+var_78+4], ecx
0x18001fe35  call    ?GetPillarHealthMapping@@YAPEBGW4PillarHealth@@@Z; GetPillarHealthMapping(PillarHealth)
0x18001fe3a  mov     [rbp+57h+var_58], rax
0x18001fe3e  mov     ecx, r8d
0x18001fe41  call    ?GetPillarStatusFlagMapping@@YAPEBGW4PillarStatusFlag@@@Z; GetPillarStatusFlagMapping(PillarStatusFlag)
0x18001fe46  mov     [rbp+57h+var_50], rax
0x18001fe4a  mov     [rbp+57h+var_30], 0
0x18001fe52  mov     r9d, 1Bh; unsigned int
0x18001fe58  lea     r8d, [r9+1]; unsigned int
0x18001fe5c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001fe63  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001fe67  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001fe6c  lea     r8, [rbp+57h+var_70]
0x18001fe70  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001fe77  mov     rcx, [rbp+57h+var_30]
0x18001fe7b  call    cs:__imp_RoGetActivationFactory
0x18001fe81  mov     ebx, eax
0x18001fe83  test    eax, eax
0x18001fe85  jns     short loc_18001FEAD
0x18001fe87  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001fe8e  jz      loc_18002001D
0x18001fe94  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001fe9b  mov     [rsp+0B0h+var_88], rax
0x18001fea0  mov     [rsp+0B0h+var_90], 2A1h
0x18001fea8  jmp     loc_18002000D
0x18001fead  mov     rdi, [rbp+57h+var_70]
0x18001feb1  mov     rax, [rdi]
0x18001feb4  mov     rbx, [rax+50h]
0x18001feb8  lea     rcx, [rbp+57h+var_80]
0x18001febc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fec1  lea     rdx, [rbp+57h+var_58]
0x18001fec5  lea     rcx, [rbp+57h+hstringHeader]
0x18001fec9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001fece  nop
0x18001fecf  lea     r8, [rbp+57h+var_80]
0x18001fed3  mov     rdx, [rax+18h]
0x18001fed7  mov     rcx, rdi
0x18001feda  mov     rax, rbx
0x18001fedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fee2  mov     ebx, eax
0x18001fee4  test    eax, eax
0x18001fee6  jns     short loc_18001FF0E
0x18001fee8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001feef  jz      loc_18002001D
0x18001fef5  lea     rax, aChrPjsonvalues_32; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001fefc  mov     [rsp+0B0h+var_88], rax
0x18001ff01  mov     [rsp+0B0h+var_90], 2A2h
0x18001ff09  jmp     loc_18002000D
0x18001ff0e  mov     rax, [r14]
0x18001ff11  mov     rdi, [rax+38h]
0x18001ff15  mov     rbx, [rbp+57h+var_80]
0x18001ff19  lea     rdx, [rbp+57h+var_68]
0x18001ff1d  lea     rcx, [rbp+57h+hstringHeader]
0x18001ff21  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ff26  nop
0x18001ff27  mov     r8, rbx
0x18001ff2a  mov     rdx, [rax+18h]
0x18001ff2e  mov     rcx, r14
0x18001ff31  mov     rax, rdi
0x18001ff34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff39  mov     ebx, eax
0x18001ff3b  test    eax, eax
0x18001ff3d  jns     short loc_18001FF65
0x18001ff3f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ff46  jz      loc_18002001D
0x18001ff4c  lea     rax, aChrPprotection_19; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001ff53  mov     [rsp+0B0h+var_88], rax
0x18001ff58  mov     [rsp+0B0h+var_90], 2A3h
0x18001ff60  jmp     loc_18002000D
0x18001ff65  mov     rdi, [rbp+57h+var_70]
0x18001ff69  mov     rax, [rdi]
0x18001ff6c  mov     rbx, [rax+50h]
0x18001ff70  lea     rcx, [rbp+57h+var_80]
0x18001ff74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ff79  lea     rdx, [rbp+57h+var_50]
0x18001ff7d  lea     rcx, [rbp+57h+hstringHeader]
0x18001ff81  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ff86  nop
0x18001ff87  lea     r8, [rbp+57h+var_80]
0x18001ff8b  mov     rdx, [rax+18h]
0x18001ff8f  mov     rcx, rdi
0x18001ff92  mov     rax, rbx
0x18001ff95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff9a  mov     ebx, eax
0x18001ff9c  test    eax, eax
0x18001ff9e  jns     short loc_18001FFBF
0x18001ffa0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ffa7  jz      short loc_18002001D
0x18001ffa9  lea     rax, aChrPjsonvalues_35; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001ffb0  mov     [rsp+0B0h+var_88], rax
0x18001ffb5  mov     [rsp+0B0h+var_90], 2A4h
0x18001ffbd  jmp     short loc_18002000D
0x18001ffbf  mov     rax, [r14]
0x18001ffc2  mov     rdi, [rax+38h]
0x18001ffc6  mov     rbx, [rbp+57h+var_80]
0x18001ffca  lea     rdx, [rbp+57h+var_60]
0x18001ffce  lea     rcx, [rbp+57h+hstringHeader]
0x18001ffd2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ffd7  nop
0x18001ffd8  mov     r8, rbx
0x18001ffdb  mov     rdx, [rax+18h]
0x18001ffdf  mov     rcx, r14
0x18001ffe2  mov     rax, rdi
0x18001ffe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffea  mov     ebx, eax
0x18001ffec  test    eax, eax
0x18001ffee  jns     short loc_18002001D
0x18001fff0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001fff7  jz      short loc_18002001D
0x18001fff9  lea     rax, aChrPprotection_7; "CHR(pProtectionState->SetNamedValue(HSt"...
0x180020000  mov     [rsp+0B0h+var_88], rax
0x180020005  mov     [rsp+0B0h+var_90], 2A5h
0x18002000d  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180020014  mov     r8d, ebx
0x180020017  call    McTemplateU0dsqs_EventWriteTransfer
0x18002001c  nop
0x18002001d  lea     rcx, [rbp+57h+var_80]
0x180020021  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020026  nop
0x180020027  mov     rcx, [rbp+57h+var_70]
0x18002002b  test    rcx, rcx
0x18002002e  jz      short loc_180020045
0x180020030  mov     [rbp+57h+var_70], 0
0x180020038  mov     rax, [rcx]
0x18002003b  mov     rax, [rax+10h]
0x18002003f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020044  nop
0x180020045  mov     eax, ebx
0x180020047  mov     rcx, [rbp+57h+var_28]
0x18002004b  xor     rcx, rsp; StackCookie
0x18002004e  call    __security_check_cookie
0x180020053  add     rsp, 90h
0x18002005a  pop     r14
0x18002005c  pop     rdi
0x18002005d  pop     rsi
0x18002005e  pop     rbx
0x18002005f  pop     rbp
0x180020060  retn
```
