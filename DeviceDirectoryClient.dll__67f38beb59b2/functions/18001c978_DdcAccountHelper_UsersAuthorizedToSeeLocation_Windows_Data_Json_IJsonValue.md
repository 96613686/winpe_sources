# DdcAccountHelper::UsersAuthorizedToSeeLocation(Windows::Data::Json::IJsonValue * *)

- ea: `0x18001c978`
- end: `0x18001cd11`
- name: `?UsersAuthorizedToSeeLocation@DdcAccountHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `921`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800101f0`

## callees

- `0x1800024c0`
- `0x1800035b0`
- `0x180004060`
- `0x180004d5c`
- `0x1800050b8`
- `0x180005a64`
- `0x180005a9c`
- `0x18000fc64`
- `0x18000fd48`
- `0x180013938`
- `0x180013ae8`
- `0x180013b38`
- `0x18001c978`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ca36`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ca36`
- `MdmCommon!MdmUsersAuthorizedToSeeLocation` at `0x18001caf9`
- `MdmCommon!MdmUsersAuthorizedToSeeLocation` at `0x18001caf9`

## string_xrefs

- `0x18001ca17`: `Windows.Data.Json.JsonValue`
- `0x18001ca75`: `Windows.Data.Json.JsonArray`
- `0x18001ca4f`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001cc57`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcaccounthelper.cpp`
- `0x18001cbd6`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))`
- `0x18001caa6`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pAuthorizedCids.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DdcAccountHelper::UsersAuthorizedToSeeLocation(struct Windows::Data::Json::IJsonValue **a1)
{
  int v2; // edx
  int v3; // ecx
  int ActivationFactory; // ebx
  int v5; // r8d
  __int64 i; // rsi
  __int64 v7; // r15
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, PVOID, __int64 *); // rbx
  char v10; // r8
  HSTRING_HEADER *v11; // rax
  struct Windows::Data::Json::IJsonValue *v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64); // rcx
  __int64 v14; // rcx
  char v16; // [rsp+20h] [rbp-49h]
  const char *v17; // [rsp+28h] [rbp-41h]
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-39h] BYREF
  struct Windows::Data::Json::IJsonValue *v19; // [rsp+38h] [rbp-31h] BYREF
  __int64 v20; // [rsp+40h] [rbp-29h] BYREF
  __int64 v21; // [rsp+48h] [rbp-21h] BYREF
  __int64 v22; // [rsp+50h] [rbp-19h] BYREF
  __int128 v23; // [rsp+58h] [rbp-11h] BYREF
  __int64 v24; // [rsp+68h] [rbp-1h]
  const WCHAR *v25; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+90h] [rbp+27h]

  v21 = 0;
  v20 = 0;
  v18 = 0;
  v22 = 0;
  v19 = 0;
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(&v23);
  if ( a1 )
  {
    if ( *a1 )
    {
      v5 = -2147024809;
      ActivationFactory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_34;
      v17 = "CBR(*ppAuthorizedCids == nullptr)";
      v16 = -68;
    }
    else
    {
      v27 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = RoGetActivationFactory(v27, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v20);
      if ( ActivationFactory >= 0 )
      {
        v27 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonArray",
          0x1Cu,
          0x1Bu);
        ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v27, &v18);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                                &v18,
                                (__int64)&v22);
          if ( ActivationFactory >= 0 )
          {
            ActivationFactory = MdmUsersAuthorizedToSeeLocation(&v23);
            if ( ActivationFactory >= 0 )
            {
              v7 = *((_QWORD *)&v23 + 1);
              for ( i = v23; i != v7; i += 32 )
              {
                v8 = v20;
                v9 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v20 + 80LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
                v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v25, v10);
                ActivationFactory = v9(v8, v11[1].Reserved.Reserved1, &v21);
                if ( ActivationFactory < 0 )
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_34;
                  v17 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(iter.c_str()).Get(), pCID.ReleaseAndGetAddressOf()))";
                  v16 = -58;
                  goto LABEL_8;
                }
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 104LL))(v22, v21);
                if ( ActivationFactory < 0 )
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_34;
                  v17 = "CHR(pAuthorizedCidsAsVector->Append(pCID.Get()))";
                  v16 = -57;
                  goto LABEL_8;
                }
              }
              ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                    &v18,
                                    (__int64)&v19);
              if ( ActivationFactory >= 0 )
              {
                v12 = v19;
                v19 = 0;
                *a1 = v12;
                goto LABEL_34;
              }
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_34;
              v17 = "CHR(pAuthorizedCids.As(&pAuthorizedCidsAsValue))";
              v16 = -54;
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_34;
              v17 = "CHR(MdmUsersAuthorizedToSeeLocation(&vAuthorizedCids))";
              v16 = -62;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_34;
            v17 = "CHR(pAuthorizedCids.As(&pAuthorizedCidsAsVector))";
            v16 = -64;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_34;
          v17 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pAuthorizedCids.GetAddressOf()))";
          v16 = -65;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_34;
        v17 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStati"
              "cs.GetAddressOf()))";
        v16 = -66;
      }
LABEL_8:
      v5 = ActivationFactory;
    }
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
      v16,
      v17);
  }
  else
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
        187,
        "CPR(ppAuthorizedCids)");
  }
LABEL_34:
  if ( (_QWORD)v23 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v23, *((_QWORD *)&v23 + 1));
    std::_Deallocate<16>((_QWORD *)v23, (v24 - v23) & 0xFFFFFFFFFFFFFFE0uLL);
    v23 = 0;
    v24 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v13 = v18;
  if ( v18 )
  {
    v18 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v13)[2])(v13);
  }
  v14 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001c978  mov     [rsp-8+arg_8], rbx
0x18001c97d  mov     [rsp-8+arg_10], rsi
0x18001c982  push    rbp
0x18001c983  push    rdi
0x18001c984  push    r12
0x18001c986  push    r14
0x18001c988  push    r15
0x18001c98a  lea     rbp, [rsp-37h]
0x18001c98f  sub     rsp, 0A0h
0x18001c996  mov     rax, cs:__security_cookie
0x18001c99d  xor     rax, rsp
0x18001c9a0  mov     [rbp+57h+var_28], rax
0x18001c9a4  mov     r14, rcx
0x18001c9a7  xor     r12d, r12d
0x18001c9aa  mov     [rbp+57h+var_78], r12
0x18001c9ae  mov     [rbp+57h+var_80], r12
0x18001c9b2  mov     [rbp+57h+var_90], r12
0x18001c9b6  mov     [rbp+57h+var_70], r12
0x18001c9ba  mov     [rbp+57h+var_88], r12
0x18001c9be  lea     rcx, [rbp+57h+var_68]
0x18001c9c2  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x18001c9c7  nop
0x18001c9c8  test    r14, r14
0x18001c9cb  jnz     short loc_18001C9FC
0x18001c9cd  mov     r8d, 80070057h
0x18001c9d3  mov     ebx, r8d
0x18001c9d6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c9dd  jz      loc_18001CC64
0x18001c9e3  lea     rax, aCprPpauthorize; "CPR(ppAuthorizedCids)"
0x18001c9ea  mov     [rsp+0C0h+var_98], rax
0x18001c9ef  mov     dword ptr [rsp+0C0h+var_A0], 0BBh
0x18001c9f7  jmp     loc_18001CC57
0x18001c9fc  cmp     [r14], r12
0x18001c9ff  jnz     loc_18001CC31
0x18001ca05  mov     [rbp+57h+var_30], r12
0x18001ca09  mov     edi, 1Bh
0x18001ca0e  mov     r9d, edi; unsigned int
0x18001ca11  lea     esi, [rdi+1]
0x18001ca14  mov     r8d, esi; unsigned int
0x18001ca17  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001ca1e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001ca22  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ca27  lea     r8, [rbp+57h+var_80]
0x18001ca2b  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001ca32  mov     rcx, [rbp+57h+var_30]
0x18001ca36  call    cs:__imp_RoGetActivationFactory
0x18001ca3c  mov     ebx, eax
0x18001ca3e  test    eax, eax
0x18001ca40  jns     short loc_18001CA6B
0x18001ca42  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ca49  jz      loc_18001CC64
0x18001ca4f  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001ca56  mov     [rsp+0C0h+var_98], rax
0x18001ca5b  mov     dword ptr [rsp+0C0h+var_A0], 0BEh
0x18001ca63  mov     r8d, ebx
0x18001ca66  jmp     loc_18001CC57
0x18001ca6b  mov     [rbp+57h+var_30], r12
0x18001ca6f  mov     r9d, edi; unsigned int
0x18001ca72  mov     r8d, esi; unsigned int
0x18001ca75  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18001ca7c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001ca80  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001ca85  nop
0x18001ca86  lea     rdx, [rbp+57h+var_90]
0x18001ca8a  mov     rcx, [rbp+57h+var_30]
0x18001ca8e  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x18001ca93  mov     ebx, eax
0x18001ca95  test    eax, eax
0x18001ca97  jns     short loc_18001CABC
0x18001ca99  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001caa0  jz      loc_18001CC64
0x18001caa6  lea     rax, aChrActivateins; "CHR(ActivateInstance(HStringReference(R"...
0x18001caad  mov     [rsp+0C0h+var_98], rax
0x18001cab2  mov     dword ptr [rsp+0C0h+var_A0], 0BFh
0x18001caba  jmp     short loc_18001CA63
0x18001cabc  lea     rdx, [rbp+57h+var_70]
0x18001cac0  lea     rcx, [rbp+57h+var_90]
0x18001cac4  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001cac9  mov     ebx, eax
0x18001cacb  test    eax, eax
0x18001cacd  jns     short loc_18001CAF5
0x18001cacf  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cad6  jz      loc_18001CC64
0x18001cadc  lea     rax, aChrPauthorized_0; "CHR(pAuthorizedCids.As(&pAuthorizedCids"...
0x18001cae3  mov     [rsp+0C0h+var_98], rax
0x18001cae8  mov     dword ptr [rsp+0C0h+var_A0], 0C0h
0x18001caf0  jmp     loc_18001CA63
0x18001caf5  lea     rcx, [rbp+57h+var_68]
0x18001caf9  call    cs:__imp_?MdmUsersAuthorizedToSeeLocation@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmUsersAuthorizedToSeeLocation(std::vector<std::wstring> *)
0x18001caff  mov     ebx, eax
0x18001cb01  test    eax, eax
0x18001cb03  jns     short loc_18001CB2B
0x18001cb05  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cb0c  jz      loc_18001CC64
0x18001cb12  lea     rax, aChrMdmusersaut; "CHR(MdmUsersAuthorizedToSeeLocation(&vA"...
0x18001cb19  mov     [rsp+0C0h+var_98], rax
0x18001cb1e  mov     dword ptr [rsp+0C0h+var_A0], 0C2h
0x18001cb26  jmp     loc_18001CA63
0x18001cb2b  mov     rsi, qword ptr [rbp+57h+var_68]
0x18001cb2f  mov     r15, qword ptr [rbp+57h+var_68+8]
0x18001cb33  cmp     rsi, r15
0x18001cb36  jz      loc_18001CBEF
0x18001cb3c  mov     rdi, [rbp+57h+var_80]
0x18001cb40  mov     rax, [rdi]
0x18001cb43  mov     rbx, [rax+50h]
0x18001cb47  lea     rcx, [rbp+57h+var_78]
0x18001cb4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cb50  mov     rcx, rsi
0x18001cb53  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cb58  mov     [rbp+57h+var_50], rax
0x18001cb5c  lea     rdx, [rbp+57h+var_50]
0x18001cb60  lea     rcx, [rbp+57h+hstringHeader]
0x18001cb64  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001cb69  nop
0x18001cb6a  lea     r8, [rbp+57h+var_78]
0x18001cb6e  mov     rdx, [rax+18h]
0x18001cb72  mov     rcx, rdi
0x18001cb75  mov     rax, rbx
0x18001cb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb7d  mov     ebx, eax
0x18001cb7f  test    eax, eax
0x18001cb81  js      short loc_18001CBC9
0x18001cb83  mov     rcx, [rbp+57h+var_70]
0x18001cb87  mov     rax, [rcx]
0x18001cb8a  mov     rdx, [rbp+57h+var_78]
0x18001cb8e  mov     rax, [rax+68h]
0x18001cb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb97  mov     ebx, eax
0x18001cb99  test    eax, eax
0x18001cb9b  js      short loc_18001CBA3
0x18001cb9d  add     rsi, 20h ; ' '
0x18001cba1  jmp     short loc_18001CB33
0x18001cba3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cbaa  jz      loc_18001CC64
0x18001cbb0  lea     rax, aChrPauthorized; "CHR(pAuthorizedCidsAsVector->Append(pCI"...
0x18001cbb7  mov     [rsp+0C0h+var_98], rax
0x18001cbbc  mov     dword ptr [rsp+0C0h+var_A0], 0C7h
0x18001cbc4  jmp     loc_18001CA63
0x18001cbc9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cbd0  jz      loc_18001CC64
0x18001cbd6  lea     rax, aChrPjsonvalues_66; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001cbdd  mov     [rsp+0C0h+var_98], rax
0x18001cbe2  mov     dword ptr [rsp+0C0h+var_A0], 0C6h
0x18001cbea  jmp     loc_18001CA63
0x18001cbef  lea     rdx, [rbp+57h+var_88]
0x18001cbf3  lea     rcx, [rbp+57h+var_90]
0x18001cbf7  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18001cbfc  mov     ebx, eax
0x18001cbfe  test    eax, eax
0x18001cc00  jns     short loc_18001CC24
0x18001cc02  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cc09  jz      short loc_18001CC64
0x18001cc0b  lea     rax, aChrPauthorized_1; "CHR(pAuthorizedCids.As(&pAuthorizedCids"...
0x18001cc12  mov     [rsp+0C0h+var_98], rax
0x18001cc17  mov     dword ptr [rsp+0C0h+var_A0], 0CAh
0x18001cc1f  jmp     loc_18001CA63
0x18001cc24  mov     rax, [rbp+57h+var_88]
0x18001cc28  mov     [rbp+57h+var_88], r12
0x18001cc2c  mov     [r14], rax
0x18001cc2f  jmp     short loc_18001CC64
0x18001cc31  mov     r8d, 80070057h
0x18001cc37  mov     ebx, r8d
0x18001cc3a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001cc41  jz      short loc_18001CC64
0x18001cc43  lea     rax, aCbrPpauthorize; "CBR(*ppAuthorizedCids == nullptr)"
0x18001cc4a  mov     [rsp+0C0h+var_98], rax
0x18001cc4f  mov     dword ptr [rsp+0C0h+var_A0], 0BCh
0x18001cc57  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001cc5e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cc63  nop
0x18001cc64  mov     rcx, qword ptr [rbp+57h+var_68]
0x18001cc68  test    rcx, rcx
0x18001cc6b  jz      short loc_18001CC96
0x18001cc6d  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x18001cc71  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18001cc76  mov     rcx, qword ptr [rbp+57h+var_68]
0x18001cc7a  mov     rdx, [rbp+57h+var_58]
0x18001cc7e  sub     rdx, rcx
0x18001cc81  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001cc85  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001cc8a  xorps   xmm0, xmm0
0x18001cc8d  movdqu  [rbp+57h+var_68], xmm0
0x18001cc92  mov     [rbp+57h+var_58], r12
0x18001cc96  lea     rcx, [rbp+57h+var_88]
0x18001cc9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cc9f  nop
0x18001cca0  lea     rcx, [rbp+57h+var_70]
0x18001cca4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cca9  nop
0x18001ccaa  mov     rcx, [rbp+57h+var_90]
0x18001ccae  test    rcx, rcx
0x18001ccb1  jz      short loc_18001CCC4
0x18001ccb3  mov     [rbp+57h+var_90], r12
0x18001ccb7  mov     rax, [rcx]
0x18001ccba  mov     rax, [rax+10h]
0x18001ccbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccc3  nop
0x18001ccc4  mov     rcx, [rbp+57h+var_80]
0x18001ccc8  test    rcx, rcx
0x18001cccb  jz      short loc_18001CCDE
0x18001cccd  mov     [rbp+57h+var_80], r12
0x18001ccd1  mov     rax, [rcx]
0x18001ccd4  mov     rax, [rax+10h]
0x18001ccd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccdd  nop
0x18001ccde  lea     rcx, [rbp+57h+var_78]
0x18001cce2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cce7  mov     eax, ebx
0x18001cce9  mov     rcx, [rbp+57h+var_28]
0x18001cced  xor     rcx, rsp; StackCookie
0x18001ccf0  call    __security_check_cookie
0x18001ccf5  lea     r11, [rsp+0C0h+var_20]
0x18001ccfd  mov     rbx, [r11+38h]
0x18001cd01  mov     rsi, [r11+40h]
0x18001cd05  mov     rsp, r11
0x18001cd08  pop     r15
0x18001cd0a  pop     r14
0x18001cd0c  pop     r12
0x18001cd0e  pop     rdi
0x18001cd0f  pop     rbp
0x18001cd10  retn
```
