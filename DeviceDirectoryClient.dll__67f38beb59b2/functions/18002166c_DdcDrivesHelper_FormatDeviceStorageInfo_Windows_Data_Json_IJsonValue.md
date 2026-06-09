# DdcDrivesHelper::FormatDeviceStorageInfo(Windows::Data::Json::IJsonValue * *)

- ea: `0x18002166c`
- end: `0x180021af3`
- name: `?FormatDeviceStorageInfo@DdcDrivesHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `1159`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c034`

## callees

- `0x1800024c0`
- `0x1800035b0`
- `0x180004060`
- `0x1800050b8`
- `0x180005a9c`
- `0x18000fc64`
- `0x18000fd48`
- `0x180013938`
- `0x1800139c8`
- `0x180013ae8`
- `0x180013b38`
- `0x180020a10`
- `0x180020d2c`
- `0x18002166c`
- `0x180021f0c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021729`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021729`

## string_xrefs

- `0x18002170a`: `Windows.Data.Json.JsonValue`
- `0x18002176b`: `Windows.Data.Json.JsonObject`
- `0x1800217bc`: `Windows.Data.Json.JsonArray`
- `0x180021742`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18002179c`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x1800219d5`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x1800216d6`: `CPR(ppJsonValue)`
- `0x180021a0d`: `CBR(*ppJsonValue == nullptr)`
- `0x1800217ed`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))`
- `0x180021826`: `CHR(pJsonArray.As(&pJsonArrayAsVector))`
- `0x1800218e3`: `CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))`
- `0x180021942`: `CHR(pJsonArray.As(&pJsonArrayAsValue))`
- `0x180021a21`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdriveshelper.cpp`
- `0x180021909`: `CHR(pVolInfo->Format(pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800219a0`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_DRIVE_INFO).Get(), pJsonArrayAsValue.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcDrivesHelper::FormatDeviceStorageInfo(struct Windows::Data::Json::IJsonValue **a1)
{
  int v2; // edx
  int v3; // ecx
  int ActivationFactory; // ebx
  int v5; // r8d
  __int128 v6; // rdi
  VolInfo *v7; // rbx
  char v8; // r8
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64); // rdi
  __int64 v11; // rbx
  HSTRING_HEADER *v12; // rax
  struct Windows::Data::Json::IJsonValue *v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64); // rcx
  __int64 v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // rcx
  char v18; // [rsp+20h] [rbp-69h]
  const char *v19; // [rsp+28h] [rbp-61h]
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-59h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-51h] BYREF
  struct Windows::Data::Json::IJsonValue *v22; // [rsp+40h] [rbp-49h] BYREF
  struct Windows::Data::Json::IJsonValue *v23; // [rsp+48h] [rbp-41h] BYREF
  __int64 v24; // [rsp+50h] [rbp-39h] BYREF
  __int64 v25; // [rsp+58h] [rbp-31h] BYREF
  __int64 v26; // [rsp+60h] [rbp-29h] BYREF
  __int128 v27; // [rsp+68h] [rbp-21h] BYREF
  __int64 v28; // [rsp+78h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v30; // [rsp+98h] [rbp+Fh]

  v23 = 0;
  v21 = 0;
  v26 = 0;
  v25 = 0;
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(&v27);
  v24 = 0;
  v20 = 0;
  v22 = 0;
  if ( a1 )
  {
    if ( *a1 )
    {
      v5 = -2147024809;
      ActivationFactory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_43;
      v19 = "CBR(*ppJsonValue == nullptr)";
      v18 = 37;
    }
    else
    {
      v30 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = RoGetActivationFactory(v30, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v24);
      if ( ActivationFactory >= 0 )
      {
        v30 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonObject",
          0x1Du,
          0x1Cu);
        ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v30, &v20);
        if ( ActivationFactory >= 0 )
        {
          v30 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Data.Json.JsonArray",
            0x1Cu,
            0x1Bu);
          ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v30, &v21);
          if ( ActivationFactory >= 0 )
          {
            ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                                  &v21,
                                  (__int64)&v26);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = DdcDrivesHelper::GetDrivesInfo(&v27);
              if ( ActivationFactory >= 0 )
              {
                v6 = v27;
                if ( (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 3 )
                {
                  while ( (_QWORD)v6 != *((_QWORD *)&v6 + 1) )
                  {
                    v7 = *(VolInfo **)v6;
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
                    ActivationFactory = VolInfo::Format(v7, &v23);
                    if ( ActivationFactory < 0 )
                    {
                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                        goto LABEL_43;
                      v19 = "CHR(pVolInfo->Format(pJsonValue.ReleaseAndGetAddressOf()))";
                      v18 = 51;
                      goto LABEL_8;
                    }
                    ActivationFactory = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v26 + 104LL))(
                                          v26,
                                          v23);
                    if ( ActivationFactory < 0 )
                    {
                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                        goto LABEL_43;
                      v19 = "CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))";
                      v18 = 52;
                      goto LABEL_8;
                    }
                    *(_QWORD *)&v6 = v6 + 8;
                  }
                }
                ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                      &v21,
                                      (__int64)&v25);
                if ( ActivationFactory >= 0 )
                {
                  v9 = v20;
                  v10 = (*v20)[7];
                  v11 = v25;
                  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                          &hstringHeader,
                          (const WCHAR **)off_18002B740,
                          v8);
                  ActivationFactory = v10(v9, (GUID *)v12[1].Reserved.Reserved1, v11);
                  if ( ActivationFactory >= 0 )
                  {
                    ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                          &v20,
                                          (__int64)&v22);
                    if ( ActivationFactory >= 0 )
                    {
                      v13 = v22;
                      v22 = 0;
                      *a1 = v13;
                      goto LABEL_43;
                    }
                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_43;
                    v19 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
                    v18 = 60;
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_43;
                    v19 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_DRIVE_INFO).Get(), pJsonArrayAsValue.Get()))";
                    v18 = 57;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_43;
                  v19 = "CHR(pJsonArray.As(&pJsonArrayAsValue))";
                  v18 = 56;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_43;
                v19 = "CHR(GetDrivesInfo(vVolumeInfo))";
                v18 = 46;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_43;
              v19 = "CHR(pJsonArray.As(&pJsonArrayAsVector))";
              v18 = 44;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_43;
            v19 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))";
            v18 = 43;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_43;
          v19 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
          v18 = 40;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_43;
        v19 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStati"
              "cs.GetAddressOf()))";
        v18 = 39;
      }
LABEL_8:
      v5 = ActivationFactory;
    }
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
      v18,
      v19);
  }
  else
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
        36,
        "CPR(ppJsonValue)");
  }
LABEL_43:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v14 = v20;
  if ( v20 )
  {
    v20 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v14)[2])(v14);
  }
  v15 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( (_QWORD)v27 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<VolInfo>>>(v27, *((__int64 *)&v27 + 1));
    std::_Deallocate<16>((_QWORD *)v27, (v28 - v27) & 0xFFFFFFFFFFFFFFF8uLL);
    v27 = 0;
    v28 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v16)[2])(v16);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002166c  push    rbp
0x18002166e  push    rbx
0x18002166f  push    rsi
0x180021670  push    rdi
0x180021671  push    r14
0x180021673  push    r15
0x180021675  lea     rbp, [rsp-2Fh]
0x18002167a  sub     rsp, 0B8h
0x180021681  mov     rax, cs:__security_cookie
0x180021688  xor     rax, rsp
0x18002168b  mov     [rbp+57h+var_40], rax
0x18002168f  mov     r14, rcx
0x180021692  xor     r15d, r15d
0x180021695  mov     [rbp+57h+var_98], r15
0x180021699  mov     [rbp+57h+var_A8], r15
0x18002169d  mov     [rbp+57h+var_80], r15
0x1800216a1  mov     [rbp+57h+var_88], r15
0x1800216a5  lea     rcx, [rbp+57h+var_78]
0x1800216a9  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x1800216ae  nop
0x1800216af  mov     [rbp+57h+var_90], r15
0x1800216b3  mov     [rbp+57h+var_B0], r15
0x1800216b7  mov     [rbp+57h+var_A0], r15
0x1800216bb  test    r14, r14
0x1800216be  jnz     short loc_1800216EF
0x1800216c0  mov     r8d, 80070057h
0x1800216c6  mov     ebx, r8d
0x1800216c9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800216d0  jz      loc_180021A2E
0x1800216d6  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x1800216dd  mov     [rsp+0E0h+var_B8], rax
0x1800216e2  mov     dword ptr [rsp+0E0h+var_C0], 24h ; '$'
0x1800216ea  jmp     loc_180021A21
0x1800216ef  cmp     [r14], r15
0x1800216f2  jnz     loc_1800219FB
0x1800216f8  mov     [rbp+57h+var_48], r15
0x1800216fc  mov     esi, 1Bh
0x180021701  mov     r9d, esi; unsigned int
0x180021704  lea     edi, [rsi+1]
0x180021707  mov     r8d, edi; unsigned int
0x18002170a  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180021711  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180021715  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002171a  lea     r8, [rbp+57h+var_90]
0x18002171e  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180021725  mov     rcx, [rbp+57h+var_48]
0x180021729  call    cs:__imp_RoGetActivationFactory
0x18002172f  mov     ebx, eax
0x180021731  test    eax, eax
0x180021733  jns     short loc_18002175E
0x180021735  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002173c  jz      loc_180021A2E
0x180021742  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180021749  mov     [rsp+0E0h+var_B8], rax
0x18002174e  mov     dword ptr [rsp+0E0h+var_C0], 27h ; '''
0x180021756  mov     r8d, ebx
0x180021759  jmp     loc_180021A21
0x18002175e  mov     [rbp+57h+var_48], r15
0x180021762  mov     r9d, edi; unsigned int
0x180021765  mov     r8d, 1Dh; unsigned int
0x18002176b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180021772  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180021776  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002177b  nop
0x18002177c  lea     rdx, [rbp+57h+var_B0]
0x180021780  mov     rcx, [rbp+57h+var_48]
0x180021784  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180021789  mov     ebx, eax
0x18002178b  test    eax, eax
0x18002178d  jns     short loc_1800217B2
0x18002178f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021796  jz      loc_180021A2E
0x18002179c  lea     rax, aChrActivateins_5; "CHR(ActivateInstance(HStringReference(R"...
0x1800217a3  mov     [rsp+0E0h+var_B8], rax
0x1800217a8  mov     dword ptr [rsp+0E0h+var_C0], 28h ; '('
0x1800217b0  jmp     short loc_180021756
0x1800217b2  mov     [rbp+57h+var_48], r15
0x1800217b6  mov     r9d, esi; unsigned int
0x1800217b9  mov     r8d, edi; unsigned int
0x1800217bc  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800217c3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800217c7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800217cc  nop
0x1800217cd  lea     rdx, [rbp+57h+var_A8]
0x1800217d1  mov     rcx, [rbp+57h+var_48]
0x1800217d5  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x1800217da  mov     ebx, eax
0x1800217dc  test    eax, eax
0x1800217de  jns     short loc_180021806
0x1800217e0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800217e7  jz      loc_180021A2E
0x1800217ed  lea     rax, aChrActivateins_9; "CHR(ActivateInstance(HStringReference(R"...
0x1800217f4  mov     [rsp+0E0h+var_B8], rax
0x1800217f9  mov     dword ptr [rsp+0E0h+var_C0], 2Bh ; '+'
0x180021801  jmp     loc_180021756
0x180021806  lea     rdx, [rbp+57h+var_80]
0x18002180a  lea     rcx, [rbp+57h+var_A8]
0x18002180e  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180021813  mov     ebx, eax
0x180021815  test    eax, eax
0x180021817  jns     short loc_18002183F
0x180021819  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021820  jz      loc_180021A2E
0x180021826  lea     rax, aChrPjsonarrayA; "CHR(pJsonArray.As(&pJsonArrayAsVector))"
0x18002182d  mov     [rsp+0E0h+var_B8], rax
0x180021832  mov     dword ptr [rsp+0E0h+var_C0], 2Ch ; ','
0x18002183a  jmp     loc_180021756
0x18002183f  lea     rcx, [rbp+57h+var_78]
0x180021843  call    ?GetDrivesInfo@DdcDrivesHelper@@CAJAEAV?$vector@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@@2@@std@@@Z; DdcDrivesHelper::GetDrivesInfo(std::vector<std::unique_ptr<VolInfo>> &)
0x180021848  mov     ebx, eax
0x18002184a  test    eax, eax
0x18002184c  jns     short loc_180021874
0x18002184e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021855  jz      loc_180021A2E
0x18002185b  lea     rax, aChrGetdrivesin; "CHR(GetDrivesInfo(vVolumeInfo))"
0x180021862  mov     [rsp+0E0h+var_B8], rax
0x180021867  mov     dword ptr [rsp+0E0h+var_C0], 2Eh ; '.'
0x18002186f  jmp     loc_180021756
0x180021874  mov     rdi, qword ptr [rbp+57h+var_78]
0x180021878  mov     rsi, qword ptr [rbp+57h+var_78+8]
0x18002187c  mov     rax, rsi
0x18002187f  sub     rax, rdi
0x180021882  sar     rax, 3
0x180021886  test    rax, rax
0x180021889  jz      loc_180021922
0x18002188f  cmp     rdi, rsi
0x180021892  jz      loc_180021922
0x180021898  mov     rbx, [rdi]
0x18002189b  lea     rcx, [rbp+57h+var_98]
0x18002189f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800218a4  lea     rdx, [rbp+57h+var_98]; struct Windows::Data::Json::IJsonValue **
0x1800218a8  mov     rcx, rbx; this
0x1800218ab  call    ?Format@VolInfo@@QEAAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z; VolInfo::Format(Windows::Data::Json::IJsonValue * *)
0x1800218b0  mov     ebx, eax
0x1800218b2  test    eax, eax
0x1800218b4  js      short loc_1800218FC
0x1800218b6  mov     rcx, [rbp+57h+var_80]
0x1800218ba  mov     rax, [rcx]
0x1800218bd  mov     rdx, [rbp+57h+var_98]
0x1800218c1  mov     rax, [rax+68h]
0x1800218c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ca  mov     ebx, eax
0x1800218cc  test    eax, eax
0x1800218ce  js      short loc_1800218D6
0x1800218d0  add     rdi, 8
0x1800218d4  jmp     short loc_18002188F
0x1800218d6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800218dd  jz      loc_180021A2E
0x1800218e3  lea     rax, aChrPjsonarraya; "CHR(pJsonArrayAsVector->Append(pJsonVal"...
0x1800218ea  mov     [rsp+0E0h+var_B8], rax
0x1800218ef  mov     dword ptr [rsp+0E0h+var_C0], 34h ; '4'
0x1800218f7  jmp     loc_180021756
0x1800218fc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021903  jz      loc_180021A2E
0x180021909  lea     rax, aChrPvolinfoFor; "CHR(pVolInfo->Format(pJsonValue.Release"...
0x180021910  mov     [rsp+0E0h+var_B8], rax
0x180021915  mov     dword ptr [rsp+0E0h+var_C0], 33h ; '3'
0x18002191d  jmp     loc_180021756
0x180021922  lea     rdx, [rbp+57h+var_88]
0x180021926  lea     rcx, [rbp+57h+var_A8]
0x18002192a  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18002192f  mov     ebx, eax
0x180021931  test    eax, eax
0x180021933  jns     short loc_18002195B
0x180021935  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002193c  jz      loc_180021A2E
0x180021942  lea     rax, aChrPjsonarrayA_0; "CHR(pJsonArray.As(&pJsonArrayAsValue))"
0x180021949  mov     [rsp+0E0h+var_B8], rax
0x18002194e  mov     dword ptr [rsp+0E0h+var_C0], 38h ; '8'
0x180021956  jmp     loc_180021756
0x18002195b  mov     rsi, [rbp+57h+var_B0]
0x18002195f  mov     rax, [rsi]
0x180021962  mov     rdi, [rax+38h]
0x180021966  mov     rbx, [rbp+57h+var_88]
0x18002196a  lea     rdx, off_18002B740; "StorageDrivesInfo"
0x180021971  lea     rcx, [rbp+57h+hstringHeader]
0x180021975  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002197a  nop
0x18002197b  mov     r8, rbx
0x18002197e  mov     rdx, [rax+18h]
0x180021982  mov     rcx, rsi
0x180021985  mov     rax, rdi
0x180021988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002198d  mov     ebx, eax
0x18002198f  test    eax, eax
0x180021991  jns     short loc_1800219B9
0x180021993  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002199a  jz      loc_180021A2E
0x1800219a0  lea     rax, aChrPjsonobject_21; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800219a7  mov     [rsp+0E0h+var_B8], rax
0x1800219ac  mov     dword ptr [rsp+0E0h+var_C0], 39h ; '9'
0x1800219b4  jmp     loc_180021756
0x1800219b9  lea     rdx, [rbp+57h+var_A0]
0x1800219bd  lea     rcx, [rbp+57h+var_B0]
0x1800219c1  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800219c6  mov     ebx, eax
0x1800219c8  test    eax, eax
0x1800219ca  jns     short loc_1800219EE
0x1800219cc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800219d3  jz      short loc_180021A2E
0x1800219d5  lea     rax, aChrPjsonobject_7; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x1800219dc  mov     [rsp+0E0h+var_B8], rax
0x1800219e1  mov     dword ptr [rsp+0E0h+var_C0], 3Ch ; '<'
0x1800219e9  jmp     loc_180021756
0x1800219ee  mov     rax, [rbp+57h+var_A0]
0x1800219f2  mov     [rbp+57h+var_A0], r15
0x1800219f6  mov     [r14], rax
0x1800219f9  jmp     short loc_180021A2E
0x1800219fb  mov     r8d, 80070057h
0x180021a01  mov     ebx, r8d
0x180021a04  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021a0b  jz      short loc_180021A2E
0x180021a0d  lea     rax, aCbrPpjsonvalue_0; "CBR(*ppJsonValue == nullptr)"
0x180021a14  mov     [rsp+0E0h+var_B8], rax
0x180021a19  mov     dword ptr [rsp+0E0h+var_C0], 25h ; '%'
0x180021a21  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180021a28  call    McTemplateU0dsqs_EventWriteTransfer
0x180021a2d  nop
0x180021a2e  lea     rcx, [rbp+57h+var_A0]
0x180021a32  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021a37  nop
0x180021a38  mov     rcx, [rbp+57h+var_B0]
0x180021a3c  test    rcx, rcx
0x180021a3f  jz      short loc_180021A52
0x180021a41  mov     [rbp+57h+var_B0], r15
0x180021a45  mov     rax, [rcx]
0x180021a48  mov     rax, [rax+10h]
0x180021a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a51  nop
0x180021a52  mov     rcx, [rbp+57h+var_90]
0x180021a56  test    rcx, rcx
0x180021a59  jz      short loc_180021A6C
0x180021a5b  mov     [rbp+57h+var_90], r15
0x180021a5f  mov     rax, [rcx]
0x180021a62  mov     rax, [rax+10h]
0x180021a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a6b  nop
0x180021a6c  mov     rcx, qword ptr [rbp+57h+var_78]
0x180021a70  test    rcx, rcx
0x180021a73  jz      short loc_180021A9E
0x180021a75  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x180021a79  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UVolInfo@@U?$default_delete@UVolInfo@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<VolInfo>>>(std::unique_ptr<VolInfo> *,std::unique_ptr<VolInfo> * const,std::allocator<std::unique_ptr<VolInfo>> &)
0x180021a7e  mov     rcx, qword ptr [rbp+57h+var_78]
0x180021a82  mov     rdx, [rbp+57h+var_68]
0x180021a86  sub     rdx, rcx
0x180021a89  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180021a8d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021a92  xorps   xmm0, xmm0
0x180021a95  movdqu  [rbp+57h+var_78], xmm0
0x180021a9a  mov     [rbp+57h+var_68], r15
0x180021a9e  lea     rcx, [rbp+57h+var_88]
0x180021aa2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021aa7  nop
0x180021aa8  lea     rcx, [rbp+57h+var_80]
0x180021aac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021ab1  nop
0x180021ab2  mov     rcx, [rbp+57h+var_A8]
0x180021ab6  test    rcx, rcx
0x180021ab9  jz      short loc_180021ACC
0x180021abb  mov     [rbp+57h+var_A8], r15
0x180021abf  mov     rax, [rcx]
0x180021ac2  mov     rax, [rax+10h]
0x180021ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021acb  nop
0x180021acc  lea     rcx, [rbp+57h+var_98]
0x180021ad0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021ad5  mov     eax, ebx
0x180021ad7  mov     rcx, [rbp+57h+var_40]
0x180021adb  xor     rcx, rsp; StackCookie
0x180021ade  call    __security_check_cookie
0x180021ae3  add     rsp, 0B8h
0x180021aea  pop     r15
0x180021aec  pop     r14
0x180021aee  pop     rdi
0x180021aef  pop     rsi
0x180021af0  pop     rbx
0x180021af1  pop     rbp
0x180021af2  retn
```
