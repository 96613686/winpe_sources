# ConnectedStorage::BlobRecords::ParseJson(ConnectedStorage::SimpleHStringWrapper)

- ea: `0x18007a4c0`
- end: `0x18007a9ac`
- name: `?ParseJson@BlobRecords@ConnectedStorage@@QEAAXVSimpleHStringWrapper@2@@Z`
- size: `1260`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180071fb8`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x18000d2f4`
- `0x180011b94`
- `0x180011c0c`
- `0x1800124d0`
- `0x180012ed8`
- `0x180022dec`
- `0x18002a6a8`
- `0x180039534`
- `0x18003c1ac`
- `0x18003f9d8`
- `0x18005b0d4`
- `0x18006a484`
- `0x1800792a0`
- `0x180079e8c`
- `0x18007a18c`
- `0x18007a4c0`
- `0x18007adac`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a5cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a7d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a5cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a733`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a7d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a971`

## string_xrefs

- `0x18007a514`: `Windows.Data.Json.JsonObject`
- `0x18007a536`: `GetActivationFactory( HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), &jsonObjectStatics)`
- `0x18007a577`: `jsonObjectStatics->Parse( json.Get(), &jsonObject)`
- `0x18007a5d7`: `jsonObject->GetNamedArray( SimpleHStringWrapper(L"atoms").Get(), &atomsArray)`
- `0x18007a5fe`: `atomsArray.As(&atomsIterable)`
- `0x18007a63c`: `atomsIterable->First(&atomsIterator)`
- `0x18007a66a`: `atomsIterator->get_HasCurrent(&hasCurrent)`
- `0x18007a928`: `atomsIterator->get_Current(&currentValue)`
- `0x18007a8ec`: `atomsIterator->MoveNext(&hasCurrent)`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
HRESULT __fastcall ConnectedStorage::BlobRecords::ParseJson(__int64 a1, HSTRING *a2)
{
  int v4; // eax
  const unsigned __int16 *v5; // r8
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 *); // rbx
  int v8; // eax
  const unsigned __int16 *v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, _QWORD); // rbx
  HSTRING *v12; // rax
  int v13; // ebx
  const unsigned __int16 *v14; // r8
  int v15; // eax
  const unsigned __int16 *v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  const unsigned __int16 *v20; // r8
  int v21; // eax
  const unsigned __int16 *v22; // r8
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // eax
  const unsigned __int16 *v26; // r8
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *); // rbx
  int v29; // eax
  const unsigned __int16 *v30; // r8
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, HSTRING, HSTRING *); // rdi
  HSTRING *AddressOf; // rbx
  HSTRING *v34; // rax
  int v35; // ebx
  const unsigned __int16 *v36; // r8
  __int64 v37; // rsi
  __int64 (__fastcall *v38)(__int64, HSTRING, HSTRING *); // rdi
  HSTRING *v39; // rbx
  HSTRING *v40; // rax
  int v41; // ebx
  const unsigned __int16 *v42; // r8
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, HSTRING, double *); // rbx
  HSTRING *v45; // rax
  double v46; // xmm0_8
  __int128 v47; // xmm6
  __int64 v48; // rbx
  HSTRING *v49; // rax
  _QWORD *v50; // rax
  HSTRING v51; // rbx
  __int64 v52; // rax
  int v53; // eax
  const unsigned __int16 *v54; // r8
  HRESULT result; // eax
  __int64 v56; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v57; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v58; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING v59; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING v60; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v61; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+68h] [rbp-A0h] BYREF
  double v65; // [rsp+70h] [rbp-98h] BYREF
  __int64 v66; // [rsp+78h] [rbp-90h] BYREF
  __int64 v67; // [rsp+80h] [rbp-88h] BYREF
  HSTRING v68; // [rsp+88h] [rbp-80h] BYREF
  HSTRING v69; // [rsp+90h] [rbp-78h] BYREF
  HSTRING v70; // [rsp+98h] [rbp-70h] BYREF
  HSTRING newString[3]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v72[8]; // [rsp+B8h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v74; // [rsp+D8h] [rbp-30h]
  _BYTE v75[64]; // [rsp+E8h] [rbp-20h] BYREF

  newString[1] = (HSTRING)a2;
  v67 = 0;
  v74 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v74,
         (__int64)&v67);
  if ( v4 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v4,
      (int)L"GetActivationFactory( HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), &jsonObjectStatics)",
      v5);
  v63 = 0;
  v6 = v67;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v67 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  v8 = v7(v6, *a2, &v63);
  if ( v8 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v8,
      (int)L"jsonObjectStatics->Parse( json.Get(), &jsonObject)",
      v9);
  v62 = 0;
  v10 = v63;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v63 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  v12 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"atoms");
  v13 = v11(v10, *v12, &v62);
  WindowsDeleteString(string);
  if ( v13 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v13,
      (int)L"jsonObject->GetNamedArray( SimpleHStringWrapper(L\"atoms\").Get(), &atomsArray)",
      v14);
  v66 = 0;
  v15 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(
          &v62,
          (__int64)&v66);
  if ( v15 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v15,
      (int)L"atomsArray.As(&atomsIterable)",
      v16);
  v58 = 0;
  v17 = v66;
  v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  v19 = v18(v17, &v58);
  if ( v19 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v19,
      (int)L"atomsIterable->First(&atomsIterator)",
      v20);
  LOBYTE(v56) = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 56LL))(v58, &v56);
  if ( v21 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v21,
      (int)L"atomsIterator->get_HasCurrent(&hasCurrent)",
      v22);
  while ( (_BYTE)v56 )
  {
    v61 = 0;
    v23 = v58;
    v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    v25 = v24(v23, &v61);
    if ( v25 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v25,
        (int)L"atomsIterator->get_Current(&currentValue)",
        v26);
    v57 = 0;
    v27 = v61;
    v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 96LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    v29 = v28(v27, &v57);
    if ( v29 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v29,
        (int)L"currentValue->GetObject(&currentObject)",
        v30);
    v59 = 0;
    v31 = v57;
    v32 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v57 + 80LL);
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v59);
    v34 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v68, L"name");
    v35 = v32(v31, *v34, AddressOf);
    WindowsDeleteString(v68);
    v68 = 0;
    if ( v35 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v35,
        (int)L"currentObject->GetNamedString( SimpleHStringWrapper(L\"name\").Get(), atomName.GetAddressOf())",
        v36);
    v60 = 0;
    v37 = v57;
    v38 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v57 + 80LL);
    v39 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v60);
    v40 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v69, L"atom");
    v41 = v38(v37, *v40, v39);
    WindowsDeleteString(v69);
    v69 = 0;
    if ( v41 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v41,
        (int)L"currentObject->GetNamedString( SimpleHStringWrapper(L\"atom\").Get(), atomString.GetAddressOf())",
        v42);
    v65 = 0.0;
    v43 = v57;
    v44 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)v57 + 88LL);
    v45 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v70, L"size");
    LODWORD(v44) = v44(v43, *v45, &v65);
    WindowsDeleteString(v70);
    v70 = 0;
    if ( (int)v44 >= 0 )
    {
      v46 = v65;
    }
    else
    {
      v46 = 0.0;
      v65 = 0.0;
    }
    v47 = *(_OWORD *)ConnectedStorage::JsonValueToGuid(&hstringHeader, &v60);
    v48 = ConnectedStorage::BlobRecord::BlobRecord((ConnectedStorage::BlobRecord *)v75);
    v49 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, &v59);
    v50 = (_QWORD *)ConnectedStorage::BlobRecords::LowerBound(a1, v72, v49);
    std::vector<ConnectedStorage::BlobRecord>::insert(a1, &string, *v50, v48);
    ConnectedStorage::BlobRecord::~BlobRecord((ConnectedStorage::BlobRecord *)v75);
    v51 = string;
    ConnectedStorage::SimpleHStringWrapper::operator=((HSTRING *)string);
    *(_OWORD *)(std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(&string)
              + 8) = v47;
    v52 = ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v75);
    ConnectedStorage::Atom::operator=(v51 + 6, v52);
    ConnectedStorage::Atom::~Atom((ConnectedStorage::Atom *)v75);
    *((_DWORD *)v51 + 14) = (int)v46;
    v53 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 64LL))(v58, &v56);
    if ( v53 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v53,
        (int)L"atomsIterator->MoveNext(&hasCurrent)",
        v54);
    WindowsDeleteString(v60);
    v60 = 0;
    WindowsDeleteString(v59);
    v59 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  result = WindowsDeleteString(*a2);
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18007a4c0  mov     rax, rsp
0x18007a4c3  mov     [rax+18h], rbx
0x18007a4c7  mov     [rax+20h], rsi
0x18007a4cb  push    rbp
0x18007a4cc  push    rdi
0x18007a4cd  push    r12
0x18007a4cf  push    r14
0x18007a4d1  push    r15
0x18007a4d3  lea     rbp, [rax-78h]
0x18007a4d7  sub     rsp, 150h
0x18007a4de  movaps  xmmword ptr [rax-38h], xmm6
0x18007a4e2  movaps  xmmword ptr [rax-48h], xmm7
0x18007a4e6  mov     rax, cs:__security_cookie
0x18007a4ed  xor     rax, rsp
0x18007a4f0  mov     [rbp+70h+var_50], rax
0x18007a4f4  mov     r14, rdx
0x18007a4f7  mov     r15, rcx
0x18007a4fa  mov     [rbp+70h+var_D0], rdx
0x18007a4fe  xor     r12d, r12d
0x18007a501  mov     [rsp+170h+var_F8], r12
0x18007a506  mov     [rbp+70h+var_A0], r12
0x18007a50a  lea     r9d, [r12+1Ch]; unsigned int
0x18007a50f  lea     r8d, [r12+1Dh]; unsigned int
0x18007a514  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007a51b  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x18007a51f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007a524  lea     rdx, [rsp+170h+var_F8]
0x18007a529  mov     rcx, [rbp+70h+var_A0]
0x18007a52d  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x18007a532  test    eax, eax
0x18007a534  jns     short loc_18007A545
0x18007a536  lea     rdx, aGetactivationf_2; "GetActivationFactory( HStringReference("...
0x18007a53d  mov     ecx, eax; this
0x18007a53f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a545  mov     [rsp+170h+var_118], r12
0x18007a54a  mov     rdi, [rsp+170h+var_F8]
0x18007a54f  mov     rax, [rdi]
0x18007a552  mov     rbx, [rax+30h]
0x18007a556  lea     rcx, [rsp+170h+var_118]
0x18007a55b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a560  lea     r8, [rsp+170h+var_118]
0x18007a565  mov     rdx, [r14]
0x18007a568  mov     rcx, rdi
0x18007a56b  mov     rax, rbx
0x18007a56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a573  test    eax, eax
0x18007a575  jns     short loc_18007A586
0x18007a577  lea     rdx, aJsonobjectstat_0; "jsonObjectStatics->Parse( json.Get(), &"...
0x18007a57e  mov     ecx, eax; this
0x18007a580  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a586  mov     [rsp+170h+var_120], r12
0x18007a58b  mov     rdi, [rsp+170h+var_118]
0x18007a590  mov     rax, [rdi]
0x18007a593  mov     rbx, [rax+48h]
0x18007a597  lea     rcx, [rsp+170h+var_120]
0x18007a59c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a5a1  lea     rdx, aAtoms; "atoms"
0x18007a5a8  lea     rcx, [rsp+170h+string]; string
0x18007a5ad  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18007a5b2  nop
0x18007a5b3  lea     r8, [rsp+170h+var_120]
0x18007a5b8  mov     rdx, [rax]
0x18007a5bb  mov     rcx, rdi
0x18007a5be  mov     rax, rbx
0x18007a5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5c6  mov     ebx, eax
0x18007a5c8  mov     rcx, [rsp+170h+string]; string
0x18007a5cd  call    cs:__imp_WindowsDeleteString
0x18007a5d3  test    ebx, ebx
0x18007a5d5  jns     short loc_18007A5E6
0x18007a5d7  lea     rdx, aJsonobjectGetn_2; "jsonObject->GetNamedArray( SimpleHStrin"...
0x18007a5de  mov     ecx, ebx; this
0x18007a5e0  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a5e6  mov     [rsp+170h+var_100], r12
0x18007a5eb  lea     rdx, [rsp+170h+var_100]
0x18007a5f0  lea     rcx, [rsp+170h+var_120]
0x18007a5f5  call    ??$As@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>>)
0x18007a5fa  test    eax, eax
0x18007a5fc  jns     short loc_18007A60D
0x18007a5fe  lea     rdx, aAtomsarrayAsAt_0; "atomsArray.As(&atomsIterable)"
0x18007a605  mov     ecx, eax; this
0x18007a607  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a60d  mov     [rsp+170h+var_140], r12
0x18007a612  mov     rdi, [rsp+170h+var_100]
0x18007a617  mov     rax, [rdi]
0x18007a61a  mov     rbx, [rax+30h]
0x18007a61e  lea     rcx, [rsp+170h+var_140]
0x18007a623  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a628  lea     rdx, [rsp+170h+var_140]
0x18007a62d  mov     rcx, rdi
0x18007a630  mov     rax, rbx
0x18007a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a638  test    eax, eax
0x18007a63a  jns     short loc_18007A64B
0x18007a63c  lea     rdx, aAtomsiterableF; "atomsIterable->First(&atomsIterator)"
0x18007a643  mov     ecx, eax; this
0x18007a645  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a64b  mov     byte ptr [rsp+170h+var_150], r12b
0x18007a650  mov     rcx, [rsp+170h+var_140]
0x18007a655  mov     rax, [rcx]
0x18007a658  lea     rdx, [rsp+170h+var_150]
0x18007a65d  mov     rax, [rax+38h]
0x18007a661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a666  test    eax, eax
0x18007a668  jns     short loc_18007A679
0x18007a66a  lea     rdx, aAtomsiteratorG_0; "atomsIterator->get_HasCurrent(&hasCurre"...
0x18007a671  mov     ecx, eax; this
0x18007a673  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a679  xorps   xmm7, xmm7
0x18007a67c  cmp     byte ptr [rsp+170h+var_150], r12b
0x18007a681  jz      loc_18007A937
0x18007a687  mov     [rsp+170h+var_128], r12
0x18007a68c  mov     rdi, [rsp+170h+var_140]
0x18007a691  mov     rax, [rdi]
0x18007a694  mov     rbx, [rax+30h]
0x18007a698  lea     rcx, [rsp+170h+var_128]
0x18007a69d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a6a2  lea     rdx, [rsp+170h+var_128]
0x18007a6a7  mov     rcx, rdi
0x18007a6aa  mov     rax, rbx
0x18007a6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6b2  test    eax, eax
0x18007a6b4  js      loc_18007A928
0x18007a6ba  mov     [rsp+170h+var_148], r12
0x18007a6bf  mov     rdi, [rsp+170h+var_128]
0x18007a6c4  mov     rax, [rdi]
0x18007a6c7  mov     rbx, [rax+60h]
0x18007a6cb  lea     rcx, [rsp+170h+var_148]
0x18007a6d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a6d5  lea     rdx, [rsp+170h+var_148]
0x18007a6da  mov     rcx, rdi
0x18007a6dd  mov     rax, rbx
0x18007a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6e5  test    eax, eax
0x18007a6e7  js      loc_18007A919
0x18007a6ed  mov     [rsp+170h+var_138], r12
0x18007a6f2  mov     rsi, [rsp+170h+var_148]
0x18007a6f7  mov     rax, [rsi]
0x18007a6fa  mov     rdi, [rax+50h]
0x18007a6fe  lea     rcx, [rsp+170h+var_138]; this
0x18007a703  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18007a708  mov     rbx, rax
0x18007a70b  lea     rdx, aName; "name"
0x18007a712  lea     rcx, [rbp+70h+var_F0]; string
0x18007a716  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18007a71b  nop
0x18007a71c  mov     r8, rbx
0x18007a71f  mov     rdx, [rax]
0x18007a722  mov     rcx, rsi
0x18007a725  mov     rax, rdi
0x18007a728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a72d  mov     ebx, eax
0x18007a72f  mov     rcx, [rbp+70h+var_F0]; string
0x18007a733  call    cs:__imp_WindowsDeleteString
0x18007a739  mov     [rbp+70h+var_F0], r12
0x18007a73d  test    ebx, ebx
0x18007a73f  js      loc_18007A90A
0x18007a745  mov     [rsp+170h+var_130], r12
0x18007a74a  mov     rsi, [rsp+170h+var_148]
0x18007a74f  mov     rax, [rsi]
0x18007a752  mov     rdi, [rax+50h]
0x18007a756  lea     rcx, [rsp+170h+var_130]; this
0x18007a75b  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18007a760  mov     rbx, rax
0x18007a763  lea     rdx, aAtom; "atom"
0x18007a76a  lea     rcx, [rbp+70h+var_E8]; string
0x18007a76e  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18007a773  nop
0x18007a774  mov     r8, rbx
0x18007a777  mov     rdx, [rax]
0x18007a77a  mov     rcx, rsi
0x18007a77d  mov     rax, rdi
0x18007a780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a785  mov     ebx, eax
0x18007a787  mov     rcx, [rbp+70h+var_E8]; string
0x18007a78b  call    cs:__imp_WindowsDeleteString
0x18007a791  mov     [rbp+70h+var_E8], r12
0x18007a795  test    ebx, ebx
0x18007a797  js      loc_18007A8FB
0x18007a79d  movsd   [rsp+170h+var_108], xmm7
0x18007a7a3  mov     rdi, [rsp+170h+var_148]
0x18007a7a8  mov     rax, [rdi]
0x18007a7ab  mov     rbx, [rax+58h]
0x18007a7af  lea     rdx, aSize; "size"
0x18007a7b6  lea     rcx, [rbp+70h+var_E0]; string
0x18007a7ba  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18007a7bf  nop
0x18007a7c0  lea     r8, [rsp+170h+var_108]
0x18007a7c5  mov     rdx, [rax]
0x18007a7c8  mov     rcx, rdi
0x18007a7cb  mov     rax, rbx
0x18007a7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a7d3  mov     ebx, eax
0x18007a7d5  mov     rcx, [rbp+70h+var_E0]; string
0x18007a7d9  call    cs:__imp_WindowsDeleteString
0x18007a7df  mov     [rbp+70h+var_E0], r12
0x18007a7e3  test    ebx, ebx
0x18007a7e5  jns     short loc_18007A7F2
0x18007a7e7  movaps  xmm0, xmm7
0x18007a7ea  movsd   [rsp+170h+var_108], xmm7
0x18007a7f0  jmp     short loc_18007A7F8
0x18007a7f2  movsd   xmm0, [rsp+170h+var_108]
0x18007a7f8  cvttsd2si rdi, xmm0
0x18007a7fd  lea     rdx, [rsp+170h+var_130]
0x18007a802  lea     rcx, [rbp+70h+hstringHeader]
0x18007a806  call    ConnectedStorage__JsonValueToGuid
0x18007a80b  movups  xmm6, xmmword ptr [rax]
0x18007a80e  lea     rcx, [rbp+70h+var_90]; this
0x18007a812  call    ??0BlobRecord@ConnectedStorage@@QEAA@XZ; ConnectedStorage::BlobRecord::BlobRecord(void)
0x18007a817  mov     rbx, rax
0x18007a81a  lea     rdx, [rsp+170h+var_138]; struct ConnectedStorage::SimpleHStringWrapper *
0x18007a81f  lea     rcx, [rbp+70h+newString]; newString
0x18007a823  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18007a828  mov     r8, rax
0x18007a82b  lea     rdx, [rbp+70h+var_C0]
0x18007a82f  mov     rcx, r15
0x18007a832  call    ?LowerBound@BlobRecords@ConnectedStorage@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@std@@VSimpleHStringWrapper@2@@Z; ConnectedStorage::BlobRecords::LowerBound(ConnectedStorage::SimpleHStringWrapper)
0x18007a837  mov     r9, rbx
0x18007a83a  mov     r8, [rax]
0x18007a83d  lea     rdx, [rsp+170h+string]
0x18007a842  mov     rcx, r15
0x18007a845  call    ?insert@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@$$QEAUBlobRecord@ConnectedStorage@@@Z; std::vector<ConnectedStorage::BlobRecord>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::BlobRecord>>>,ConnectedStorage::BlobRecord &&)
0x18007a84a  nop
0x18007a84b  lea     rcx, [rbp+70h+var_90]; this
0x18007a84f  call    ??1BlobRecord@ConnectedStorage@@QEAA@XZ; ConnectedStorage::BlobRecord::~BlobRecord(void)
0x18007a854  lea     rdx, [rsp+170h+var_138]
0x18007a859  mov     rbx, [rsp+170h+string]
0x18007a85e  mov     rcx, rbx; newString
0x18007a861  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18007a866  lea     rcx, [rsp+170h+string]
0x18007a86b  call    ??$?C$$CBVUploadingContext@ConnectedStorage@@$0A@@?$shared_ptr@$$CBVUploadingContext@ConnectedStorage@@@std@@QEBAPEBVUploadingContext@ConnectedStorage@@XZ; std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(void)
0x18007a870  movdqu  xmmword ptr [rax+8], xmm6
0x18007a875  lea     rcx, [rbp+70h+var_90]; this
0x18007a879  call    ??0Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::Atom(void)
0x18007a87e  nop
0x18007a87f  lea     rcx, [rbx+18h]
0x18007a883  mov     rdx, rax
0x18007a886  call    ??4Atom@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::Atom::operator=(ConnectedStorage::Atom const &)
0x18007a88b  nop
0x18007a88c  lea     rcx, [rbp+70h+var_90]; this
0x18007a890  call    ??1Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::~Atom(void)
0x18007a895  mov     [rbx+38h], edi
0x18007a898  mov     rcx, [rsp+170h+var_140]
0x18007a89d  mov     rax, [rcx]
0x18007a8a0  lea     rdx, [rsp+170h+var_150]
0x18007a8a5  mov     rax, [rax+40h]
0x18007a8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a8ae  test    eax, eax
0x18007a8b0  js      short loc_18007A8EC
0x18007a8b2  mov     rcx, [rsp+170h+var_130]; string
0x18007a8b7  call    cs:__imp_WindowsDeleteString
0x18007a8bd  mov     [rsp+170h+var_130], r12
0x18007a8c2  mov     rcx, [rsp+170h+var_138]; string
0x18007a8c7  call    cs:__imp_WindowsDeleteString
0x18007a8cd  mov     [rsp+170h+var_138], r12
0x18007a8d2  lea     rcx, [rsp+170h+var_148]
0x18007a8d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a8dc  nop
0x18007a8dd  lea     rcx, [rsp+170h+var_128]
0x18007a8e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a8e7  jmp     loc_18007A67C
0x18007a8ec  lea     rdx, aAtomsiteratorM; "atomsIterator->MoveNext(&hasCurrent)"
0x18007a8f3  mov     ecx, eax; this
0x18007a8f5  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a8fb  lea     rdx, aCurrentobjectG_1; "currentObject->GetNamedString( SimpleHS"...
0x18007a902  mov     ecx, ebx; this
0x18007a904  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a90a  lea     rdx, aCurrentobjectG_0; "currentObject->GetNamedString( SimpleHS"...
0x18007a911  mov     ecx, ebx; this
0x18007a913  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a919  lea     rdx, aCurrentvalueGe; "currentValue->GetObject(&currentObject)"
0x18007a920  mov     ecx, eax; this
0x18007a922  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a928  lea     rdx, aAtomsiteratorG; "atomsIterator->get_Current(&currentValu"...
0x18007a92f  mov     ecx, eax; this
0x18007a931  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18007a937  lea     rcx, [rsp+170h+var_140]
0x18007a93c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a941  nop
0x18007a942  lea     rcx, [rsp+170h+var_100]
0x18007a947  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a94c  nop
0x18007a94d  lea     rcx, [rsp+170h+var_120]
0x18007a952  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a957  nop
0x18007a958  lea     rcx, [rsp+170h+var_118]
0x18007a95d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a962  nop
0x18007a963  lea     rcx, [rsp+170h+var_F8]
0x18007a968  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a96d  nop
0x18007a96e  mov     rcx, [r14]; string
0x18007a971  call    cs:__imp_WindowsDeleteString
0x18007a977  mov     [r14], r12
0x18007a97a  mov     rcx, [rbp+70h+var_50]
0x18007a97e  xor     rcx, rsp; StackCookie
0x18007a981  call    __security_check_cookie
0x18007a986  lea     r11, [rsp+170h+var_20]
0x18007a98e  mov     rbx, [r11+40h]
0x18007a992  mov     rsi, [r11+48h]
  ... truncated ...
```
