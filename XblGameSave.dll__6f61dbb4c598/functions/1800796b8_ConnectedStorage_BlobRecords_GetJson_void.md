# ConnectedStorage::BlobRecords::GetJson(void)

- ea: `0x1800796b8`
- end: `0x180079c72`
- name: `?GetJson@BlobRecords@ConnectedStorage@@QEBA?AVSimpleHStringWrapper@2@XZ`
- size: `1466`
- prototype: `struct ConnectedStorage::SimpleHStringWrapper __high(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007bca8`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x180022dec`
- `0x18002a6a8`
- `0x180078244`
- `0x1800782e4`
- `0x180078384`
- `0x1800783d4`
- `0x1800796b8`
- `0x180079db8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180079777`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180079777`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800799bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800799bd`

## string_xrefs

- `0x180079724`: `Windows.Data.Json.JsonValue`
- `0x180079706`: `Windows.Data.Json.JsonObject`
- `0x18007973f`: `Windows.Data.Json.JsonArray`
- `0x180079b82`: `GetActivationFactory( runtimeClassJsonValue.Get(), &jsonValueStatics)`
- `0x180079b91`: `ActivateInstance( runtimeClassJsonArray.Get(), &atomsArray)`
- `0x180079baf`: `ActivateInstance( runtimeClassJsonObject.Get(), &jsonObject)`
- `0x180079c27`: `ActivateInstance( runtimeClassJsonObject.Get(), &jsonObject)`
- `0x180079c18`: `jsonObject.As(&jsonMap)`
- `0x180079c36`: `jsonObject.As(&jsonMap)`
- `0x180079c09`: `jsonValueStatics->CreateStringValue( blob.Name.Get(), &jsonNameValue)`
- `0x180079bfa`: `jsonMap->Insert( HStringReference(L"name").Get(), jsonNameValue.Get(), &replaced)`
- `0x180079beb`: `jsonValueStatics->CreateStringValue( atomGuidString.Get(), &jsonAtomValue)`
- `0x180079bdc`: `jsonMap->Insert( HStringReference(L"atom").Get(), jsonAtomValue.Get(), &replaced)`
- `0x180079bcd`: `jsonObject.As(&jsonValue)`
- `0x180079c63`: `jsonObject.As(&jsonValue)`
- `0x180079bbe`: `atomsVector->Append( jsonValue.Get())`
- `0x180079c54`: `jsonMap->Insert( HStringReference(L"atoms").Get(), atomsValue.Get(), &replaced)`
- `0x180079b73`: `jsonValue->Stringify(stringified.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
ConnectedStorage::SimpleHStringWrapper *__fastcall ConnectedStorage::BlobRecords::GetJson(
        _QWORD *a1,
        ConnectedStorage::SimpleHStringWrapper *a2)
{
  int v4; // r14d
  __int64 v5; // rbx
  int ActivationFactory; // eax
  const unsigned __int16 *v7; // r8
  int v8; // eax
  const unsigned __int16 *v9; // r8
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  int v12; // eax
  const unsigned __int16 *v13; // r8
  _QWORD *v14; // r15
  _QWORD *v15; // r12
  int v16; // eax
  const unsigned __int16 *v17; // r8
  int v18; // eax
  const unsigned __int16 *v19; // r8
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  int v22; // eax
  const unsigned __int16 *v23; // r8
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v26; // rbx
  int v27; // eax
  const unsigned __int16 *v28; // r8
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING, __int64 *); // rbx
  int v31; // eax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v35; // rbx
  int v36; // eax
  const unsigned __int16 *v37; // r8
  int v38; // eax
  const unsigned __int16 *v39; // r8
  int v40; // eax
  const unsigned __int16 *v41; // r8
  int v42; // eax
  const unsigned __int16 *v43; // r8
  int v44; // eax
  const unsigned __int16 *v45; // r8
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v47)(_QWORD, GUID *, __int64 *); // rdi
  int v48; // eax
  const unsigned __int16 *v49; // r8
  __int64 v50; // rsi
  __int64 (__fastcall *v51)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v52; // rbx
  int v53; // eax
  const unsigned __int16 *v54; // r8
  int v55; // eax
  const unsigned __int16 *v56; // r8
  __int64 v57; // rdi
  __int64 (__fastcall *v58)(__int64, HSTRING *); // rbx
  HSTRING *AddressOf; // rax
  int v60; // eax
  const unsigned __int16 *v61; // r8
  _BYTE v63[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v64; // [rsp+34h] [rbp-CCh]
  __int64 v65; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v66; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v68; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v69; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v70)(_QWORD, GUID *, __int64); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v71; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v72)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-90h] BYREF
  __int64 v73; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall ***v74)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  __int64 v75; // [rsp+88h] [rbp-78h] BYREF
  __int64 v76; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v77[2]; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER v78; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v79; // [rsp+C0h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+E0h] [rbp-20h]
  HSTRING_HEADER v82; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v83; // [rsp+100h] [rbp+0h]
  HSTRING_HEADER v84; // [rsp+108h] [rbp+8h] BYREF
  __int64 v85; // [rsp+120h] [rbp+20h]

  v77[1] = a2;
  v4 = 0;
  v64 = 0;
  v81 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v83 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v82, L"Windows.Data.Json.JsonValue", 0x1Cu, 0x1Bu);
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v84, L"Windows.Data.Json.JsonArray", 0x1Cu, 0x1Bu);
  v63[0] = 0;
  v65 = 0;
  v5 = v83;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v65);
  if ( ActivationFactory < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)ActivationFactory,
      (int)L"GetActivationFactory( runtimeClassJsonValue.Get(), &jsonValueStatics)",
      v7);
  v74 = 0;
  v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(v85, &v74);
  if ( v8 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v8,
      (int)L"ActivateInstance( runtimeClassJsonArray.Get(), &atomsArray)",
      v9);
  v73 = 0;
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v74;
  v11 = **v74;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  v12 = v11(v10, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v73);
  if ( v12 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v12,
      (int)L"atomsArray.As(&atomsVector)",
      v13);
  v14 = (_QWORD *)*a1;
  v15 = (_QWORD *)a1[1];
  while ( v14 != v15 )
  {
    v70 = 0;
    v16 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v81, &v70);
    if ( v16 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v16,
        (int)L"ActivateInstance( runtimeClassJsonObject.Get(), &jsonObject)",
        v17);
    v69 = 0;
    v18 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
            &v70,
            (__int64)&v69);
    if ( v18 < 0 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v18, (int)L"jsonObject.As(&jsonMap)", v19);
    v68 = 0;
    v20 = v65;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    v22 = v21(v20, *v14, &v68);
    if ( v22 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v22,
        (int)L"jsonValueStatics->CreateStringValue( blob.Name.Get(), &jsonNameValue)",
        v23);
    v24 = v69;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v69 + 80LL);
    v26 = v68;
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v78, L"name", 5u, 4u);
    v27 = v25(v24, v79, v26, v63);
    if ( v27 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v27,
        (int)L"jsonMap->Insert( HStringReference(L\"name\").Get(), jsonNameValue.Get(), &replaced)",
        v28);
    v4 |= 2u;
    ConnectedStorage::GuidToJsonValue(&string);
    v64 = v4;
    v66 = 0;
    v29 = v65;
    v30 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v65 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v31 = v30(v29, string, &v66);
    if ( v31 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v31,
        (int)L"jsonValueStatics->CreateStringValue( atomGuidString.Get(), &jsonAtomValue)",
        v32);
    v33 = v69;
    v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v69 + 80LL);
    v35 = v66;
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v78, L"atom", 5u, 4u);
    v36 = v34(v33, v79, v35, v63);
    if ( v36 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v36,
        (int)L"jsonMap->Insert( HStringReference(L\"atom\").Get(), jsonAtomValue.Get(), &replaced)",
        v37);
    v75 = 0;
    v38 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
            &v70,
            (__int64)&v75);
    if ( v38 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v38,
        (int)L"jsonObject.As(&jsonValue)",
        v39);
    v40 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 104LL))(v73, v75);
    if ( v40 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v40,
        (int)L"atomsVector->Append( jsonValue.Get())",
        v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    v14 += 8;
  }
  v72 = 0;
  v42 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v81, &v72);
  if ( v42 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v42,
      (int)L"ActivateInstance( runtimeClassJsonObject.Get(), &jsonObject)",
      v43);
  v77[0] = 0;
  v44 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
          &v72,
          (__int64)v77);
  if ( v44 < 0 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v44, (int)L"jsonObject.As(&jsonMap)", v45);
  v71 = 0;
  v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v74;
  v47 = **v74;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  v48 = v47(v46, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v71);
  if ( v48 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v48,
      (int)L"atomsArray.As(&atomsValue)",
      v49);
  v50 = v77[0];
  v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v77[0] + 80LL);
  v52 = v71;
  v79 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v78, L"atoms", 6u, 5u);
  v53 = v51(v50, v79, v52, v63);
  if ( v53 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v53,
      (int)L"jsonMap->Insert( HStringReference(L\"atoms\").Get(), atomsValue.Get(), &replaced)",
      v54);
  v76 = 0;
  v55 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
          &v72,
          (__int64)&v76);
  if ( v55 < 0 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v55, (int)L"jsonObject.As(&jsonValue)", v56);
  *(_QWORD *)a2 = 0;
  v64 = v4 | 1;
  v57 = v76;
  v58 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v76 + 56LL);
  AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf(a2);
  v60 = v58(v57, AddressOf);
  if ( v60 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v60,
      (int)L"jsonValue->Stringify(stringified.GetAddressOf())",
      v61);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v77);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  return a2;
}

```

## disassembly

```asm
0x1800796b8  mov     [rsp-8+arg_10], rbx
0x1800796bd  push    rbp
0x1800796be  push    rsi
0x1800796bf  push    rdi
0x1800796c0  push    r12
0x1800796c2  push    r13
0x1800796c4  push    r14
0x1800796c6  push    r15
0x1800796c8  lea     rbp, [rsp-30h]
0x1800796cd  sub     rsp, 130h
0x1800796d4  mov     rax, cs:__security_cookie
0x1800796db  xor     rax, rsp
0x1800796de  mov     [rbp+60h+var_38], rax
0x1800796e2  mov     r13, rdx
0x1800796e5  mov     rsi, rcx
0x1800796e8  mov     [rbp+60h+var_C0], rdx
0x1800796ec  xor     r15d, r15d
0x1800796ef  mov     r14d, r15d
0x1800796f2  mov     [rsp+160h+var_12C], r15d
0x1800796f7  mov     [rbp+60h+var_80], r15
0x1800796fb  lea     edi, [r15+1Ch]
0x1800796ff  mov     r9d, edi; unsigned int
0x180079702  lea     r8d, [r15+1Dh]; unsigned int
0x180079706  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007970d  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x180079711  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180079716  nop
0x180079717  mov     [rbp+60h+var_60], r15
0x18007971b  lea     ebx, [rdi-1]
0x18007971e  mov     r9d, ebx; unsigned int
0x180079721  mov     r8d, edi; unsigned int
0x180079724  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18007972b  lea     rcx, [rbp+60h+var_78]; hstringHeader
0x18007972f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180079734  nop
0x180079735  mov     [rbp+60h+var_40], r15
0x180079739  mov     r9d, ebx; unsigned int
0x18007973c  mov     r8d, edi; unsigned int
0x18007973f  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x180079746  lea     rcx, [rbp+60h+var_58]; hstringHeader
0x18007974a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007974f  nop
0x180079750  mov     [rsp+160h+var_130], r15b
0x180079755  mov     [rsp+160h+var_128], r15
0x18007975a  mov     rbx, [rbp+60h+var_60]
0x18007975e  lea     rcx, [rsp+160h+var_128]
0x180079763  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079768  lea     r8, [rsp+160h+var_128]
0x18007976d  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180079774  mov     rcx, rbx
0x180079777  call    cs:__imp_RoGetActivationFactory
0x18007977d  test    eax, eax
0x18007977f  js      loc_180079B82
0x180079785  mov     [rbp+60h+var_E0], r15
0x180079789  lea     rdx, [rbp+60h+var_E0]
0x18007978d  mov     rcx, [rbp+60h+var_40]
0x180079791  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x180079796  test    eax, eax
0x180079798  js      loc_180079B91
0x18007979e  mov     [rsp+160h+var_E8], r15
0x1800797a3  mov     rbx, [rbp+60h+var_E0]
0x1800797a7  mov     rax, [rbx]
0x1800797aa  mov     rdi, [rax]
0x1800797ad  lea     rcx, [rsp+160h+var_E8]
0x1800797b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800797b7  lea     r8, [rsp+160h+var_E8]
0x1800797bc  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x1800797c3  mov     rcx, rbx
0x1800797c6  mov     rax, rdi
0x1800797c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797ce  nop
0x1800797cf  test    eax, eax
0x1800797d1  js      loc_180079BA0
0x1800797d7  mov     r15, [rsi]
0x1800797da  mov     r12, [rsi+8]
0x1800797de  xor     esi, esi
0x1800797e0  jmp     loc_1800799EC
0x1800797e5  mov     [rsp+160h+var_100], rsi
0x1800797ea  lea     rdx, [rsp+160h+var_100]
0x1800797ef  mov     rcx, [rbp+60h+var_80]
0x1800797f3  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800797f8  test    eax, eax
0x1800797fa  js      loc_180079C27
0x180079800  mov     [rsp+160h+var_108], rsi
0x180079805  lea     rdx, [rsp+160h+var_108]
0x18007980a  lea     rcx, [rsp+160h+var_100]
0x18007980f  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180079814  test    eax, eax
0x180079816  js      loc_180079C18
0x18007981c  mov     [rsp+160h+var_110], rsi
0x180079821  mov     rdi, [rsp+160h+var_128]
0x180079826  mov     rax, [rdi]
0x180079829  mov     rbx, [rax+50h]
0x18007982d  lea     rcx, [rsp+160h+var_110]
0x180079832  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079837  lea     r8, [rsp+160h+var_110]
0x18007983c  mov     rdx, [r15]
0x18007983f  mov     rcx, rdi
0x180079842  mov     rax, rbx
0x180079845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007984a  test    eax, eax
0x18007984c  js      loc_180079C09
0x180079852  mov     rsi, [rsp+160h+var_108]
0x180079857  mov     rax, [rsi]
0x18007985a  mov     rdi, [rax+50h]
0x18007985e  mov     rbx, [rsp+160h+var_110]
0x180079863  mov     [rbp+60h+var_A0], 0
0x18007986b  mov     r9d, 4; unsigned int
0x180079871  lea     r8d, [r9+1]; unsigned int
0x180079875  lea     rdx, aName; "name"
0x18007987c  lea     rcx, [rbp+60h+var_B8]; hstringHeader
0x180079880  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180079885  nop
0x180079886  lea     r9, [rsp+160h+var_130]
0x18007988b  mov     r8, rbx
0x18007988e  mov     rdx, [rbp+60h+var_A0]
0x180079892  mov     rcx, rsi
0x180079895  mov     rax, rdi
0x180079898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007989d  nop
0x18007989e  test    eax, eax
0x1800798a0  js      loc_180079BFA
0x1800798a6  mov     rax, [r15+20h]
0x1800798aa  test    rax, rax
0x1800798ad  jz      short loc_1800798B9
0x1800798af  cmp     dword ptr [rax+8], 0
0x1800798b3  jz      short loc_1800798B9
0x1800798b5  mov     al, 1
0x1800798b7  jmp     short loc_1800798BB
0x1800798b9  xor     al, al
0x1800798bb  or      r14d, 2
0x1800798bf  lea     rcx, [rsp+160h+string]; string
0x1800798c4  test    al, al
0x1800798c6  lea     rdx, [r15+28h]
0x1800798ca  jnz     short loc_1800798D0
0x1800798cc  lea     rdx, [r15+8]
0x1800798d0  call    ConnectedStorage__GuidToJsonValue
0x1800798d5  mov     [rsp+160h+var_12C], r14d
0x1800798da  mov     [rsp+160h+var_120], 0
0x1800798e3  mov     rdi, [rsp+160h+var_128]
0x1800798e8  mov     rax, [rdi]
0x1800798eb  mov     rbx, [rax+50h]
0x1800798ef  lea     rcx, [rsp+160h+var_120]
0x1800798f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800798f9  lea     r8, [rsp+160h+var_120]
0x1800798fe  mov     rdx, [rsp+160h+string]
0x180079903  mov     rcx, rdi
0x180079906  mov     rax, rbx
0x180079909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007990e  test    eax, eax
0x180079910  js      loc_180079BEB
0x180079916  mov     rsi, [rsp+160h+var_108]
0x18007991b  mov     rax, [rsi]
0x18007991e  mov     rdi, [rax+50h]
0x180079922  mov     rbx, [rsp+160h+var_120]
0x180079927  mov     [rbp+60h+var_A0], 0
0x18007992f  mov     r9d, 4; unsigned int
0x180079935  lea     r8d, [r9+1]; unsigned int
0x180079939  lea     rdx, aAtom; "atom"
0x180079940  lea     rcx, [rbp+60h+var_B8]; hstringHeader
0x180079944  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180079949  nop
0x18007994a  lea     r9, [rsp+160h+var_130]
0x18007994f  mov     r8, rbx
0x180079952  mov     rdx, [rbp+60h+var_A0]
0x180079956  mov     rcx, rsi
0x180079959  mov     rax, rdi
0x18007995c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079961  nop
0x180079962  xor     esi, esi
0x180079964  test    eax, eax
0x180079966  js      loc_180079BDC
0x18007996c  mov     [rbp+60h+var_D8], rsi
0x180079970  lea     rdx, [rbp+60h+var_D8]
0x180079974  lea     rcx, [rsp+160h+var_100]
0x180079979  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18007997e  test    eax, eax
0x180079980  js      loc_180079BCD
0x180079986  mov     rcx, [rsp+160h+var_E8]
0x18007998b  mov     rax, [rcx]
0x18007998e  mov     rdx, [rbp+60h+var_D8]
0x180079992  mov     rax, [rax+68h]
0x180079996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007999b  test    eax, eax
0x18007999d  js      loc_180079BBE
0x1800799a3  lea     rcx, [rbp+60h+var_D8]
0x1800799a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800799ac  nop
0x1800799ad  lea     rcx, [rsp+160h+var_120]
0x1800799b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800799b7  nop
0x1800799b8  mov     rcx, [rsp+160h+string]; string
0x1800799bd  call    cs:__imp_WindowsDeleteString
0x1800799c3  mov     [rsp+160h+string], rsi
0x1800799c8  lea     rcx, [rsp+160h+var_110]
0x1800799cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800799d2  nop
0x1800799d3  lea     rcx, [rsp+160h+var_108]
0x1800799d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800799dd  nop
0x1800799de  lea     rcx, [rsp+160h+var_100]
0x1800799e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800799e8  add     r15, 40h ; '@'
0x1800799ec  cmp     r15, r12
0x1800799ef  jnz     loc_1800797E5
0x1800799f5  mov     [rsp+160h+var_F0], rsi
0x1800799fa  lea     rdx, [rsp+160h+var_F0]
0x1800799ff  mov     rcx, [rbp+60h+var_80]
0x180079a03  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180079a08  test    eax, eax
0x180079a0a  js      loc_180079BAF
0x180079a10  mov     [rbp+60h+var_C8], rsi
0x180079a14  lea     rdx, [rbp+60h+var_C8]
0x180079a18  lea     rcx, [rsp+160h+var_F0]
0x180079a1d  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180079a22  test    eax, eax
0x180079a24  js      loc_180079C36
0x180079a2a  mov     [rsp+160h+var_F8], rsi
0x180079a2f  mov     rbx, [rbp+60h+var_E0]
0x180079a33  mov     rax, [rbx]
0x180079a36  mov     rdi, [rax]
0x180079a39  lea     rcx, [rsp+160h+var_F8]
0x180079a3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079a43  lea     r8, [rsp+160h+var_F8]
0x180079a48  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180079a4f  mov     rcx, rbx
0x180079a52  mov     rax, rdi
0x180079a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a5a  nop
0x180079a5b  test    eax, eax
0x180079a5d  js      loc_180079C45
0x180079a63  mov     rsi, [rbp+60h+var_C8]
0x180079a67  mov     rax, [rsi]
0x180079a6a  mov     rdi, [rax+50h]
0x180079a6e  mov     rbx, [rsp+160h+var_F8]
0x180079a73  xor     r15d, r15d
0x180079a76  mov     [rbp+60h+var_A0], r15
0x180079a7a  lea     r9d, [r15+5]; unsigned int
0x180079a7e  lea     r8d, [r15+6]; unsigned int
0x180079a82  lea     rdx, aAtoms; "atoms"
0x180079a89  lea     rcx, [rbp+60h+var_B8]; hstringHeader
0x180079a8d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180079a92  nop
0x180079a93  lea     r9, [rsp+160h+var_130]
0x180079a98  mov     r8, rbx
0x180079a9b  mov     rdx, [rbp+60h+var_A0]
0x180079a9f  mov     rcx, rsi
0x180079aa2  mov     rax, rdi
0x180079aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079aaa  nop
0x180079aab  test    eax, eax
0x180079aad  js      loc_180079C54
0x180079ab3  mov     [rbp+60h+var_D0], r15
0x180079ab7  lea     rdx, [rbp+60h+var_D0]
0x180079abb  lea     rcx, [rsp+160h+var_F0]
0x180079ac0  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180079ac5  test    eax, eax
0x180079ac7  js      loc_180079C63
0x180079acd  mov     [r13+0], r15
0x180079ad1  or      r14d, 1
0x180079ad5  mov     [rsp+160h+var_12C], r14d
0x180079ada  mov     rdi, [rbp+60h+var_D0]
0x180079ade  mov     rax, [rdi]
0x180079ae1  mov     rbx, [rax+38h]
0x180079ae5  mov     rcx, r13; this
0x180079ae8  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180079aed  mov     rdx, rax
0x180079af0  mov     rcx, rdi
0x180079af3  mov     rax, rbx
0x180079af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079afb  test    eax, eax
0x180079afd  js      short loc_180079B73
0x180079aff  lea     rcx, [rbp+60h+var_D0]
0x180079b03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079b08  nop
0x180079b09  lea     rcx, [rsp+160h+var_F8]
0x180079b0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079b13  nop
0x180079b14  lea     rcx, [rbp+60h+var_C8]
0x180079b18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079b1d  nop
0x180079b1e  lea     rcx, [rsp+160h+var_F0]
0x180079b23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079b28  nop
0x180079b29  lea     rcx, [rsp+160h+var_E8]
0x180079b2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079b33  nop
0x180079b34  lea     rcx, [rbp+60h+var_E0]
0x180079b38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079b3d  nop
0x180079b3e  lea     rcx, [rsp+160h+var_128]
0x180079b43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079b48  nop
0x180079b49  mov     rax, r13
0x180079b4c  mov     rcx, [rbp+60h+var_38]
0x180079b50  xor     rcx, rsp; StackCookie
0x180079b53  call    __security_check_cookie
0x180079b58  mov     rbx, [rsp+160h+arg_10]
0x180079b60  add     rsp, 130h
0x180079b67  pop     r15
  ... truncated ...
```
