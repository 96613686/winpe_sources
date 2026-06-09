# Windows::Internal::CapabilityAccess::Private::FormatRecentActivityRecords(std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub,std::allocator<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x1800b2ddc`
- end: `0x1800b31e5`
- name: `?FormatRecentActivityRecords@Private@CapabilityAccess@Internal@Windows@@YAXAEBV?$vector@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091680`

## callees

- `0x1800094c0`
- `0x1800094e4`
- `0x18001c3b4`
- `0x18001f5f4`
- `0x18002392c`
- `0x180029408`
- `0x180033028`
- `0x1800467c8`
- `0x1800493d4`
- `0x180063510`
- `0x1800b2b58`
- `0x1800b2c54`
- `0x1800b2ca8`
- `0x1800b2d70`
- `0x1800b2ddc`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2e4e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2e4e`

## string_xrefs

- `0x1800b2e22`: `Windows.Data.Json.JsonValue`
- `0x1800b2ee4`: `Windows.Data.Json.JsonArray`
- `0x1800b3158`: `onecore\base\devices\cam\core\jsonhelpers.cpp`
- `0x1800b316d`: `onecore\base\devices\cam\core\jsonhelpers.cpp`
- `0x1800b317f`: `onecore\base\devices\cam\core\jsonhelpers.cpp`
- `0x1800b3194`: `onecore\base\devices\cam\core\jsonhelpers.cpp`
- `0x1800b31a9`: `onecore\base\devices\cam\core\jsonhelpers.cpp`
- `0x1800b31be`: `onecore\base\devices\cam\core\jsonhelpers.cpp`
- `0x1800b31d3`: `onecore\base\devices\cam\core\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::FormatRecentActivityRecords(__int64 *a1, __int64 *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  _QWORD *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // r15
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *); // rsi
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  _QWORD *v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 *v22; // rbx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rdi
  int v25; // eax
  __int64 v26; // r14
  __int64 (__fastcall *v27)(__int64, _QWORD, __int64); // rsi
  __int64 v28; // rdi
  __int64 AppName; // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 **v32; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v36; // [rsp+20h] [rbp-69h] BYREF
  __int64 v37; // [rsp+28h] [rbp-61h] BYREF
  __int128 v38; // [rsp+30h] [rbp-59h] BYREF
  __int64 v39; // [rsp+40h] [rbp-49h] BYREF
  __int64 v40; // [rsp+48h] [rbp-41h] BYREF
  __int64 v41; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v42[16]; // [rsp+58h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-21h] BYREF
  __int64 v44; // [rsp+80h] [rbp-9h]
  _BYTE v45[32]; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v37 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v4 = v44;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v37);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v36);
  v36 = 0;
  v40 = 0;
  v38 = 0;
  v6 = operator new(0x30u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *(_QWORD *)&v38 = v6;
  v7 = *a1;
  v8 = a1[1];
  if ( *a1 != v8 )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>>,0>>::_Find_lower_bound<unsigned __int64>(
        &v38,
        &hstringHeader,
        v7 + 48);
      v9 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
      if ( *(_BYTE *)(*(_QWORD *)&hstringHeader.Reserved.Reserved2[16] + 25LL)
        || *(_QWORD *)(v7 + 48) < *(_QWORD *)(*(_QWORD *)&hstringHeader.Reserved.Reserved2[16] + 32LL) )
      {
        v9 = v38;
      }
      if ( v9 == (_QWORD)v38 )
      {
        v39 = 0;
        v44 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonArray",
          0x1Cu,
          0x1Bu);
        v10 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(v44, &v39);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\jsonhelpers.cpp",
            (const char *)(unsigned int)v10,
            v36);
        v11 = std::map<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>::_Try_emplace<unsigned __int64 const &,>(
                &v38,
                v42,
                v7 + 48);
        v12 = *(_QWORD *)v11;
        v13 = v39;
        if ( *(_QWORD *)(*(_QWORD *)v11 + 40LL) != v39 )
        {
          if ( v39 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
          v41 = *(_QWORD *)(v12 + 40);
          *(_QWORD *)(v12 + 40) = v13;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      }
      v14 = v37;
      v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v37 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      v17 = *(_QWORD *)(v7 + 72);
      if ( v17 < 0 )
        v16 = *(_QWORD *)(v7 + 72) & 1LL | ((unsigned __int64)v17 >> 1);
      v18 = v15(v14, v16, &v36);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\jsonhelpers.cpp",
          (const char *)(unsigned int)v18,
          v36);
      v19 = (_QWORD *)std::map<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>::_Try_emplace<unsigned __int64 const &,>(
                        &v38,
                        v45,
                        v7 + 48);
      v20 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
              *v19 + 40LL,
              &v40);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\jsonhelpers.cpp",
          (const char *)(unsigned int)v20,
          v36);
      v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 104LL))(v40, v36);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x30,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\jsonhelpers.cpp",
          (const char *)(unsigned int)v21,
          v36);
      v7 += 80;
    }
    while ( v7 != v8 );
    v6 = (_QWORD *)v38;
  }
  v22 = (__int64 *)*v6;
  while ( !*((_BYTE *)v22 + 25) )
  {
    v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v22[5];
    v24 = **v23;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    v25 = v24(v23, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v36);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\jsonhelpers.cpp",
        (const char *)(unsigned int)v25,
        v36);
    v26 = *a2;
    v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a2 + 56LL);
    v28 = v36;
    AppName = Windows::Internal::CapabilityAccess::Private::SQL::GetAppName(v45, v22[4]);
    v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(AppName);
    v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v41);
    v31 = v27(v26, *(_QWORD *)(v30 + 24), v28);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\jsonhelpers.cpp",
        (const char *)(unsigned int)v31,
        v36);
    v44 = 0;
    std::wstring::_Tidy_deallocate(v45);
    v32 = (__int64 **)v22[2];
    if ( *((_BYTE *)v32 + 25) )
    {
      for ( i = (__int64 *)v22[1]; !*((_BYTE *)i + 25) && v22 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v22 = i;
      v22 = i;
    }
    else
    {
      v22 = (__int64 *)v22[2];
      for ( j = *v32; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v22 = j;
    }
  }
  std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>>,0>>(&v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
}

```

## disassembly

```asm
0x1800b2ddc  mov     [rsp-8+arg_10], rbx
0x1800b2de1  push    rbp
0x1800b2de2  push    rsi
0x1800b2de3  push    rdi
0x1800b2de4  push    r12
0x1800b2de6  push    r13
0x1800b2de8  push    r14
0x1800b2dea  push    r15
0x1800b2dec  lea     rbp, [rsp-27h]
0x1800b2df1  sub     rsp, 0B0h
0x1800b2df8  mov     rax, cs:__security_cookie
0x1800b2dff  xor     rax, rsp
0x1800b2e02  mov     [rbp+57h+var_38], rax
0x1800b2e06  mov     r12, rdx
0x1800b2e09  mov     rsi, rcx
0x1800b2e0c  xor     r13d, r13d
0x1800b2e0f  mov     [rbp+57h+var_B8], r13
0x1800b2e13  mov     [rbp+57h+var_60], r13
0x1800b2e17  lea     edi, [r13+1Bh]
0x1800b2e1b  mov     r9d, edi; unsigned int
0x1800b2e1e  lea     r8d, [r13+1Ch]; unsigned int
0x1800b2e22  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800b2e29  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b2e2d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b2e32  nop
0x1800b2e33  mov     rbx, [rbp+57h+var_60]
0x1800b2e37  lea     rcx, [rbp+57h+var_B8]
0x1800b2e3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2e40  lea     r8, [rbp+57h+var_B8]
0x1800b2e44  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800b2e4b  mov     rcx, rbx
0x1800b2e4e  call    cs:__imp_RoGetActivationFactory
0x1800b2e54  mov     rcx, [rbp+5Fh]; this
0x1800b2e58  test    eax, eax
0x1800b2e5a  js      loc_1800B316A
0x1800b2e60  mov     [rbp+57h+var_C0], r13
0x1800b2e64  mov     [rbp+57h+var_98], r13
0x1800b2e68  xorps   xmm0, xmm0
0x1800b2e6b  movdqu  [rbp+57h+var_B0], xmm0
0x1800b2e70  lea     ecx, [rdi+15h]; Size
0x1800b2e73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2e78  mov     [rax], rax
0x1800b2e7b  mov     [rax+8], rax
0x1800b2e7f  mov     [rax+10h], rax
0x1800b2e83  mov     word ptr [rax+18h], 101h
0x1800b2e89  mov     qword ptr [rbp+57h+var_B0], rax
0x1800b2e8d  mov     rdi, [rsi]
0x1800b2e90  mov     r15, [rsi+8]
0x1800b2e94  cmp     rdi, r15
0x1800b2e97  jz      loc_1800B3013
0x1800b2e9d  lea     r14, [rdi+30h]
0x1800b2ea1  mov     r8, r14
0x1800b2ea4  lea     rdx, [rbp+57h+hstringHeader]
0x1800b2ea8  lea     rcx, [rbp+57h+var_B0]
0x1800b2eac  call    ??$_Find_lower_bound@_K@?$_Tree@V?$_Tmap_traits@_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@std@@PEAX@std@@@1@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>>,0>>::_Find_lower_bound<unsigned __int64>(unsigned __int64 const &)
0x1800b2eb1  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x1800b2eb5  cmp     [rcx+19h], r13b
0x1800b2eb9  jnz     short loc_1800B2EC4
0x1800b2ebb  mov     rax, [rcx+20h]
0x1800b2ebf  cmp     [r14], rax
0x1800b2ec2  jnb     short loc_1800B2EC8
0x1800b2ec4  mov     rcx, qword ptr [rbp+57h+var_B0]
0x1800b2ec8  cmp     rcx, qword ptr [rbp+57h+var_B0]
0x1800b2ecc  jnz     loc_1800B2F5F
0x1800b2ed2  mov     [rbp+57h+var_A0], r13
0x1800b2ed6  mov     [rbp+57h+var_60], r13
0x1800b2eda  mov     r9d, 1Bh; unsigned int
0x1800b2ee0  lea     r8d, [r9+1]; unsigned int
0x1800b2ee4  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800b2eeb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b2eef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b2ef4  nop
0x1800b2ef5  lea     rdx, [rbp+57h+var_A0]
0x1800b2ef9  mov     rcx, [rbp+57h+var_60]
0x1800b2efd  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x1800b2f02  mov     rcx, [rbp+5Fh]; this
0x1800b2f06  test    eax, eax
0x1800b2f08  js      loc_1800B317C
0x1800b2f0e  mov     r8, r14
0x1800b2f11  lea     rdx, [rbp+57h+var_88]
0x1800b2f15  lea     rcx, [rbp+57h+var_B0]
0x1800b2f19  call    ??$_Try_emplace@AEB_K$$V@?$map@_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x1800b2f1e  mov     rsi, [rax]
0x1800b2f21  mov     rbx, [rbp+57h+var_A0]
0x1800b2f25  cmp     [rsi+28h], rbx
0x1800b2f29  jz      short loc_1800B2F56
0x1800b2f2b  test    rbx, rbx
0x1800b2f2e  jz      short loc_1800B2F40
0x1800b2f30  mov     rax, [rbx]
0x1800b2f33  mov     rcx, rbx
0x1800b2f36  mov     rax, [rax+8]
0x1800b2f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2f3f  nop
0x1800b2f40  mov     rax, [rsi+28h]
0x1800b2f44  mov     [rbp+57h+var_90], rax
0x1800b2f48  mov     [rsi+28h], rbx
0x1800b2f4c  lea     rcx, [rbp+57h+var_90]
0x1800b2f50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2f55  nop
0x1800b2f56  lea     rcx, [rbp+57h+var_A0]
0x1800b2f5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2f5f  mov     rbx, [rbp+57h+var_B8]
0x1800b2f63  mov     rax, [rbx]
0x1800b2f66  mov     rsi, [rax+48h]
0x1800b2f6a  lea     rcx, [rbp+57h+var_C0]
0x1800b2f6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2f73  mov     rax, [rdi+48h]
0x1800b2f77  xorps   xmm1, xmm1
0x1800b2f7a  test    rax, rax
0x1800b2f7d  js      short loc_1800B2F86
0x1800b2f7f  cvtsi2sd xmm1, rax
0x1800b2f84  jmp     short loc_1800B2F9B
0x1800b2f86  mov     rdx, rax
0x1800b2f89  shr     rdx, 1
0x1800b2f8c  and     eax, 1
0x1800b2f8f  or      rdx, rax
0x1800b2f92  cvtsi2sd xmm1, rdx
0x1800b2f97  addsd   xmm1, xmm1
0x1800b2f9b  lea     r8, [rbp+57h+var_C0]
0x1800b2f9f  mov     rcx, rbx
0x1800b2fa2  mov     rax, rsi
0x1800b2fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2faa  mov     rcx, [rbp+5Fh]; this
0x1800b2fae  test    eax, eax
0x1800b2fb0  js      loc_1800B31BB
0x1800b2fb6  mov     r8, r14
0x1800b2fb9  lea     rdx, [rbp+57h+var_58]
0x1800b2fbd  lea     rcx, [rbp+57h+var_B0]
0x1800b2fc1  call    ??$_Try_emplace@AEB_K$$V@?$map@_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x1800b2fc6  mov     rcx, [rax]
0x1800b2fc9  add     rcx, 28h ; '('
0x1800b2fcd  lea     rdx, [rbp+57h+var_98]
0x1800b2fd1  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800b2fd6  mov     rcx, [rbp+5Fh]; this
0x1800b2fda  test    eax, eax
0x1800b2fdc  js      loc_1800B31A6
0x1800b2fe2  mov     rcx, [rbp+57h+var_98]
0x1800b2fe6  mov     rax, [rcx]
0x1800b2fe9  mov     rdx, [rbp+57h+var_C0]
0x1800b2fed  mov     rax, [rax+68h]
0x1800b2ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ff6  mov     rcx, [rbp+5Fh]; this
0x1800b2ffa  test    eax, eax
0x1800b2ffc  js      loc_1800B3191
0x1800b3002  add     rdi, 50h ; 'P'
0x1800b3006  cmp     rdi, r15
0x1800b3009  jnz     loc_1800B2E9D
0x1800b300f  mov     rax, qword ptr [rbp+57h+var_B0]
0x1800b3013  mov     rbx, [rax]
0x1800b3016  cmp     [rbx+19h], r13b
0x1800b301a  jnz     loc_1800B3107
0x1800b3020  mov     rsi, [rbx+28h]
0x1800b3024  mov     rax, [rsi]
0x1800b3027  mov     rdi, [rax]
0x1800b302a  lea     rcx, [rbp+57h+var_C0]
0x1800b302e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b3033  lea     r8, [rbp+57h+var_C0]
0x1800b3037  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800b303e  mov     rcx, rsi
0x1800b3041  mov     rax, rdi
0x1800b3044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3049  nop
0x1800b304a  mov     rcx, [rbp+5Fh]; this
0x1800b304e  test    eax, eax
0x1800b3050  js      loc_1800B3155
0x1800b3056  mov     r14, [r12]
0x1800b305a  mov     rax, [r14]
0x1800b305d  mov     rsi, [rax+38h]
0x1800b3061  mov     rdi, [rbp+57h+var_C0]
0x1800b3065  mov     rdx, [rbx+20h]
0x1800b3069  lea     rcx, [rbp+57h+var_58]
0x1800b306d  call    ?GetAppName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetAppName(unsigned __int64)
0x1800b3072  nop
0x1800b3073  mov     rcx, rax
0x1800b3076  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b307b  mov     [rbp+57h+var_90], rax
0x1800b307f  lea     rdx, [rbp+57h+var_90]
0x1800b3083  lea     rcx, [rbp+57h+hstringHeader]
0x1800b3087  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b308c  nop
0x1800b308d  mov     r8, rdi
0x1800b3090  mov     rdx, [rax+18h]
0x1800b3094  mov     rcx, r14
0x1800b3097  mov     rax, rsi
0x1800b309a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b309f  mov     rcx, [rbp+5Fh]; this
0x1800b30a3  test    eax, eax
0x1800b30a5  js      loc_1800B31D0
0x1800b30ab  mov     [rbp+57h+var_60], r13
0x1800b30af  lea     rcx, [rbp+57h+var_58]
0x1800b30b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b30b8  mov     rcx, [rbx+10h]
0x1800b30bc  cmp     [rcx+19h], r13b
0x1800b30c0  jz      short loc_1800B30E3
0x1800b30c2  mov     rax, [rbx+8]
0x1800b30c6  jmp     short loc_1800B30D5
0x1800b30c8  cmp     rbx, [rax+10h]
0x1800b30cc  jnz     short loc_1800B30DB
0x1800b30ce  mov     rbx, rax
0x1800b30d1  mov     rax, [rax+8]
0x1800b30d5  cmp     [rax+19h], r13b
0x1800b30d9  jz      short loc_1800B30C8
0x1800b30db  mov     rbx, rax
0x1800b30de  jmp     loc_1800B3016
0x1800b30e3  mov     rbx, rcx
0x1800b30e6  mov     rcx, [rcx]
0x1800b30e9  cmp     [rcx+19h], r13b
0x1800b30ed  jnz     loc_1800B3016
0x1800b30f3  mov     rbx, rcx
0x1800b30f6  mov     rax, [rcx]
0x1800b30f9  mov     rcx, rax
0x1800b30fc  cmp     [rax+19h], r13b
0x1800b3100  jz      short loc_1800B30F3
0x1800b3102  jmp     loc_1800B3016
0x1800b3107  lea     rcx, [rbp+57h+var_B0]
0x1800b310b  call    ??1?$_Tree@V?$_Tmap_traits@_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>>,0>>(void)
0x1800b3110  nop
0x1800b3111  lea     rcx, [rbp+57h+var_98]
0x1800b3115  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b311a  nop
0x1800b311b  lea     rcx, [rbp+57h+var_C0]
0x1800b311f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b3124  nop
0x1800b3125  lea     rcx, [rbp+57h+var_B8]
0x1800b3129  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b312e  mov     rcx, [rbp+57h+var_38]
0x1800b3132  xor     rcx, rsp; StackCookie
0x1800b3135  call    __security_check_cookie
0x1800b313a  mov     rbx, [rsp+0E0h+arg_10]
0x1800b3142  add     rsp, 0B0h
0x1800b3149  pop     r15
0x1800b314b  pop     r14
0x1800b314d  pop     r13
0x1800b314f  pop     r12
0x1800b3151  pop     rdi
0x1800b3152  pop     rsi
0x1800b3153  pop     rbp
0x1800b3154  retn
0x1800b3155  mov     r9d, eax; char *
0x1800b3158  lea     r8, aOnecoreBaseDev_32; "onecore\\base\\devices\\cam\\core\\json"...
0x1800b315f  mov     edx, 35h ; '5'; void *
0x1800b3164  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b316a  mov     r9d, eax; char *
0x1800b316d  lea     r8, aOnecoreBaseDev_32; "onecore\\base\\devices\\cam\\core\\json"...
0x1800b3174  mov     edx, edi; void *
0x1800b3176  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b317c  mov     r9d, eax; char *
0x1800b317f  lea     r8, aOnecoreBaseDev_32; "onecore\\base\\devices\\cam\\core\\json"...
0x1800b3186  mov     edx, 29h ; ')'; void *
0x1800b318b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b3191  mov     r9d, eax; char *
0x1800b3194  lea     r8, aOnecoreBaseDev_32; "onecore\\base\\devices\\cam\\core\\json"...
0x1800b319b  mov     edx, 30h ; '0'; void *
0x1800b31a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b31a6  mov     r9d, eax; char *
0x1800b31a9  lea     r8, aOnecoreBaseDev_32; "onecore\\base\\devices\\cam\\core\\json"...
0x1800b31b0  mov     edx, 2Fh ; '/'; void *
0x1800b31b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b31bb  mov     r9d, eax; char *
0x1800b31be  lea     r8, aOnecoreBaseDev_32; "onecore\\base\\devices\\cam\\core\\json"...
0x1800b31c5  mov     edx, 2Eh ; '.'; void *
0x1800b31ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b31d0  mov     r9d, eax; char *
0x1800b31d3  lea     r8, aOnecoreBaseDev_32; "onecore\\base\\devices\\cam\\core\\json"...
0x1800b31da  mov     edx, 36h ; '6'; void *
0x1800b31df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
