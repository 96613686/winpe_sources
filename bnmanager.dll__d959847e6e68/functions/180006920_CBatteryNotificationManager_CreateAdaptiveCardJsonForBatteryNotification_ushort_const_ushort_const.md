# CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification(ushort const *,ushort const *)

- ea: `0x180006920`
- end: `0x180006e66`
- name: `?CreateAdaptiveCardJsonForBatteryNotification@CBatteryNotificationManager@@CA?AUIJsonValue@Json@Data@Windows@winrt@@PEBG0@Z`
- size: `1350`
- prototype: `int ***__fastcall(int ***, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007250`

## callees

- `0x180003730`
- `0x180006920`
- `0x1800071ac`
- `0x1800082fc`
- `0x180008364`
- `0x18000bde4`
- `0x18000c010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006958`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006c45`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006d29`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006958`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006c45`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006d29`

## pseudocode

```c
int ***__fastcall CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification(
        int ***a1,
        const wchar_t *a2,
        const wchar_t *a3)
{
  int v6; // eax
  int **v7; // rcx
  int v8; // ebx
  __int64 v9; // rsi
  int v10; // ebx
  int v11; // eax
  __int64 **NamedArray; // rax
  __int64 *v13; // rcx
  __int64 *ObjectAt; // rax
  __int64 v15; // r14
  __int64 *v16; // rax
  __int64 v17; // rdi
  __int64 *v18; // rbx
  __int64 *v19; // rbx
  __int64 *v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rbx
  int v23; // eax
  __int64 *v24; // r15
  __int64 *StringValue; // rsi
  int v26; // eax
  __int64 v28; // [rsp+20h] [rbp-89h] BYREF
  __int64 v29; // [rsp+28h] [rbp-81h] BYREF
  __int64 v30; // [rsp+30h] [rbp-79h] BYREF
  int *v31; // [rsp+38h] [rbp-71h] BYREF
  int v32; // [rsp+40h] [rbp-69h] BYREF
  int v33; // [rsp+44h] [rbp-65h]
  const wchar_t *v34; // [rsp+50h] [rbp-59h]
  __int128 *v35; // [rsp+58h] [rbp-51h] BYREF
  __int128 v36; // [rsp+60h] [rbp-49h] BYREF
  const wchar_t *v37; // [rsp+70h] [rbp-39h]
  int v38; // [rsp+78h] [rbp-31h]
  __int64 v39; // [rsp+80h] [rbp-29h] BYREF
  __int64 v40; // [rsp+88h] [rbp-21h] BYREF
  int **v41; // [rsp+90h] [rbp-19h] BYREF
  int **v42; // [rsp+98h] [rbp-11h] BYREF
  __int64 *v43; // [rsp+A0h] [rbp-9h]
  int *v44; // [rsp+A8h] [rbp-1h]
  int v45; // [rsp+B0h] [rbp+7h] BYREF
  int v46; // [rsp+B4h] [rbp+Bh]
  const wchar_t *v47; // [rsp+C0h] [rbp+17h]
  int **v48; // [rsp+128h] [rbp+7Fh] BYREF

  v38 = 0;
  if ( aTypeAdaptiveca[1966] )
    abort();
  v32 = 1;
  v33 = 1966;
  v34 = L"\n"
         "{\n"
         "    \"type\":\"AdaptiveCard\",\n"
         "    \"version\":\"1.0\",\n"
         "    \"body\":\n"
         "    [\n"
         "        {\n"
         "            \"type\":\"ColumnSet\",\n"
         "            \"columns\":\n"
         "            [\n"
         "                {\n"
         "                    \"type\":\"Column\",\n"
         "                    \"width\":\"24px\",\n"
         "                    \"verticalContentAlignment\":\"center\",\n"
         "                    \"items\":\n"
         "                    [\n"
         "                        {\n"
         "                            \"type\":\"TextBlock\",\n"
         "                            \"id\":\"LowBatteryGlyph\",\n"
         "                            \"size\":\"large\",\n"
         "                            \"weight\":\"bolder\",\n"
         "                            \"text\":\"glyph:0xE85A\"\n"
         "                        }\n"
         "                    ]\n"
         "                },\n"
         "                {\n"
         "                    \"type\":\"Column\",\n"
         "                    \"items\":\n"
         "                    [\n"
         "                        {\n"
         "                            \"type\":\"TextBlock\",\n"
         "                            \"id\":\"TitleText\",\n"
         "                            \"size\":\"large\",\n"
         "                            \"weight\":\"bolder\",\n"
         "                            \"wrap\":true,\n"
         "                            \"text\":\"\"\n"
         "                        }\n"
         "                    ]\n"
         "                }\n"
         "            ]\n"
         "        },\n"
         "        {\n"
         "            \"type\":\"TextBlock\",\n"
         "            \"id\":\"BodyText\",\n"
         "            \"wrap\":true,\n"
         "            \"spacing\":\"medium\",\n"
         "            \"text\":\"\"\n"
         "        },\n"
         "        {\n"
         "            \"type\":\"ColumnSet\",\n"
         "            \"id\":\"Buttons\",\n"
         "            \"spacing\":\"large\",\n"
         "            \"columns\":\n"
         "            [\n"
         "                {\n"
         "                    \"type\":\"Column\"\n"
         "                },\n"
         "                {\n"
         "                    \"type\":\"Column\",\n"
         "                    \"id\":\"Button1\",\n"
         "                    \"items\":\n"
         "                    [\n"
         "                        {\n"
         "                            \"type\":\"TextBlock\",\n"
         "                            \"id\":\"1\",\n"
         "                            \"text\":\"defaultButton:Close\"\n"
         "                        }\n"
         "                    ]\n"
         "                }\n"
         "            ]\n"
         "        }\n"
         "    ],\n"
         "    \"actions\":[]\n"
         "}";
  v31 = &v32;
  v48 = &v31;
  v43 = &qword_180014788;
  _InterlockedIncrement64(&qword_180014788);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
  {
    v48 = 0;
    LODWORD(v35) = 0;
    v36 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, int *, int ***))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                            + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
           v31,
           &v48);
    if ( v6 < 0 )
      winrt::throw_hresult((unsigned int)v6, &v35);
    v7 = v48;
    v8 = 28;
    v9 = -1;
    _InterlockedAdd64(&qword_180014788, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    v9 = -1;
    _InterlockedAdd64(&qword_180014788, 0xFFFFFFFFFFFFFFFFuLL);
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_fa5bfa998c3b0e5f1b75589fad572465_ &>(
      0,
      &v41,
      &v48);
    v8 = 4;
    v7 = v41;
  }
  *a1 = v7;
  v10 = v8 | 3;
  v38 = v10;
  v42 = 0;
  LODWORD(v35) = 0;
  v36 = 0;
  v11 = (*((__int64 (__fastcall **)(int **, int ***))*v7 + 12))(v7, &v42);
  if ( v11 < 0 )
    winrt::throw_hresult((unsigned int)v11, &v35);
  v38 = v10 | 0x20;
  v41 = v42;
  v32 = 1;
  v33 = 4;
  v34 = L"body";
  v31 = &v32;
  NamedArray = (__int64 **)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                             &v41,
                             &v40,
                             &v31);
  v43 = *NamedArray;
  v13 = v43;
  *NamedArray = 0;
  v48 = (int **)v13;
  if ( v40 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v40);
  ObjectAt = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(
                          &v48,
                          &v28,
                          0);
  v15 = *ObjectAt;
  *ObjectAt = 0;
  v29 = v15;
  if ( v28 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
  *(_QWORD *)&v36 = 0x700000001LL;
  v37 = L"columns";
  v35 = &v36;
  v16 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                     &v29,
                     &v40,
                     &v35);
  v17 = *v16;
  *v16 = 0;
  v30 = v17;
  if ( v40 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v40);
  v18 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(
                     &v30,
                     &v28,
                     1);
  if ( &v29 != v18 )
  {
    if ( v15 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v29);
    v15 = *v18;
    *v18 = 0;
    v29 = v15;
  }
  if ( v28 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
  v32 = 1;
  v33 = 5;
  v34 = L"items";
  v31 = &v32;
  v19 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
                     &v29,
                     &v28,
                     &v31);
  if ( &v30 != v19 )
  {
    if ( v17 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v30);
    v17 = *v19;
    *v19 = 0;
    v30 = v17;
  }
  if ( v28 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
  v20 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(
                     &v30,
                     &v28,
                     0);
  if ( &v29 != v20 )
  {
    if ( v15 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v29);
    v15 = *v20;
    *v20 = 0;
    v29 = v15;
  }
  if ( v28 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
  v21 = -1;
  do
    ++v21;
  while ( a2[v21] );
  if ( (_DWORD)v21 )
  {
    if ( a2[(unsigned int)v21] )
      abort();
    v32 = 1;
    v33 = v21;
    v34 = a2;
    v31 = &v32;
  }
  else
  {
    v31 = 0;
  }
  winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v39);
  v45 = 1;
  v46 = 4;
  v47 = L"text";
  v44 = &v45;
  LODWORD(v35) = 0;
  v36 = 0;
  v22 = v39;
  v23 = (*(__int64 (__fastcall **)(__int64, int *, __int64))(*(_QWORD *)v15 + 56LL))(v15, &v45, v39);
  if ( v23 < 0 )
    winrt::throw_hresult((unsigned int)v23, &v35);
  v24 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(
                     &v48,
                     &v28,
                     1);
  if ( &v29 != v24 )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v29);
    v15 = *v24;
    *v24 = 0;
    v29 = v15;
  }
  if ( v28 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
  do
    ++v9;
  while ( a3[v9] );
  if ( (_DWORD)v9 )
  {
    if ( a3[(unsigned int)v9] )
      abort();
    LODWORD(v36) = 1;
    DWORD1(v36) = v9;
    v37 = a3;
    v35 = &v36;
  }
  else
  {
    v35 = 0;
  }
  StringValue = (__int64 *)winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v28);
  if ( &v39 != StringValue )
  {
    if ( v22 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v39);
    v22 = *StringValue;
    *StringValue = 0;
    v39 = v22;
  }
  if ( v28 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
  v45 = 1;
  v46 = 4;
  v47 = L"text";
  v44 = &v45;
  LODWORD(v35) = 0;
  v36 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, int *, __int64))(*(_QWORD *)v15 + 56LL))(v15, &v45, v22);
  if ( v26 < 0 )
    winrt::throw_hresult((unsigned int)v26, &v35);
  if ( v22 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v39);
  if ( v17 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v30);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v29);
  if ( v43 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v48);
  if ( v42 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v41);
  return a1;
}

```

## disassembly

```asm
0x180006920  mov     [rsp-8+arg_8], rbx
0x180006925  mov     [rsp-8+arg_0], rcx
0x18000692a  push    rbp
0x18000692b  push    rsi
0x18000692c  push    rdi
0x18000692d  push    r12
0x18000692f  push    r13
0x180006931  push    r14
0x180006933  push    r15
0x180006935  lea     rbp, [rsp-27h]
0x18000693a  sub     rsp, 0D0h
0x180006941  mov     r12, r8
0x180006944  mov     r15, rdx
0x180006947  mov     r13, rcx
0x18000694a  xor     edi, edi
0x18000694c  mov     [rbp+57h+var_88], edi
0x18000694f  cmp     word ptr cs:aTypeAdaptiveca+0F5Ch, di; ""
0x180006956  jz      short loc_18000695F
0x180006958  call    cs:__imp_abort
0x18000695f  mov     [rbp+57h+var_C0], 1
0x180006966  mov     [rbp+57h+var_BC], 7AEh
0x18000696d  lea     rax, aTypeAdaptiveca; "\n{\n    \"type\":\"AdaptiveCard\",\n  "...
0x180006974  mov     [rbp+57h+var_B0], rax
0x180006978  lea     rax, [rbp+57h+var_C0]
0x18000697c  mov     [rbp+57h+var_C8], rax
0x180006980  lea     rax, [rbp+57h+var_C8]
0x180006984  mov     [rbp+57h+arg_18], rax
0x180006988  lea     rax, qword_180014788
0x18000698f  mov     [rbp+57h+var_60], rax
0x180006993  lock inc cs:qword_180014788
0x18000699b  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x1800069a2  mov     r14d, 4
0x1800069a8  test    rcx, rcx
0x1800069ab  jz      short loc_1800069EE
0x1800069ad  mov     [rbp+57h+arg_18], rdi
0x1800069b1  mov     dword ptr [rbp+57h+var_A8], edi
0x1800069b4  xorps   xmm0, xmm0
0x1800069b7  movdqu  [rbp+57h+var_A0], xmm0
0x1800069bc  mov     rax, [rcx]
0x1800069bf  lea     r8, [rbp+57h+arg_18]
0x1800069c3  mov     rdx, [rbp+57h+var_C8]
0x1800069c7  mov     rax, [rax+30h]
0x1800069cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d0  test    eax, eax
0x1800069d2  js      loc_180006E42
0x1800069d8  mov     rcx, [rbp+57h+arg_18]
0x1800069dc  lea     ebx, [r14+18h]
0x1800069e0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800069e4  lock add cs:qword_180014788, rsi
0x1800069ec  jmp     short loc_180006A0E
0x1800069ee  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800069f2  lock add cs:qword_180014788, rsi
0x1800069fa  lea     r8, [rbp+57h+arg_18]
0x1800069fe  lea     rdx, [rbp+57h+var_70]
0x180006a02  call    ??$call@AEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@Z
0x180006a07  mov     ebx, r14d
0x180006a0a  mov     rcx, [rbp+57h+var_70]
0x180006a0e  or      ebx, 2
0x180006a11  mov     [r13+0], rcx
0x180006a15  or      ebx, 1
0x180006a18  mov     [rbp+57h+var_88], ebx
0x180006a1b  mov     [rbp+57h+var_68], rdi
0x180006a1f  mov     dword ptr [rbp+57h+var_A8], edi
0x180006a22  xorps   xmm0, xmm0
0x180006a25  movdqu  [rbp+57h+var_A0], xmm0
0x180006a2a  mov     rax, [rcx]
0x180006a2d  lea     rdx, [rbp+57h+var_68]
0x180006a31  mov     rax, [rax+60h]
0x180006a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a3a  test    eax, eax
0x180006a3c  js      loc_180006E4E
0x180006a42  or      ebx, 20h
0x180006a45  mov     [rbp+57h+var_88], ebx
0x180006a48  mov     rax, [rbp+57h+var_68]
0x180006a4c  mov     [rbp+57h+var_70], rax
0x180006a50  mov     [rbp+57h+var_C0], 1
0x180006a57  mov     [rbp+57h+var_BC], r14d
0x180006a5b  lea     rax, aBody; "body"
0x180006a62  mov     [rbp+57h+var_B0], rax
0x180006a66  lea     rax, [rbp+57h+var_C0]
0x180006a6a  mov     [rbp+57h+var_C8], rax
0x180006a6e  lea     r8, [rbp+57h+var_C8]
0x180006a72  lea     rdx, [rbp+57h+var_78]
0x180006a76  lea     rcx, [rbp+57h+var_70]
0x180006a7a  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x180006a7f  mov     rcx, [rax]
0x180006a82  mov     [rbp+57h+var_60], rcx
0x180006a86  mov     [rax], rdi
0x180006a89  mov     [rbp+57h+arg_18], rcx
0x180006a8d  cmp     [rbp+57h+var_78], rdi
0x180006a91  jz      short loc_180006A9C
0x180006a93  lea     rcx, [rbp+57h+var_78]
0x180006a97  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006a9c  xor     r8d, r8d
0x180006a9f  lea     rdx, [rsp+100h+var_E0]
0x180006aa4  lea     rcx, [rbp+57h+arg_18]
0x180006aa8  call    ?GetObjectAt@?$consume_Windows_Data_Json_IJsonArray@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(uint)
0x180006aad  mov     r14, [rax]
0x180006ab0  mov     [rax], rdi
0x180006ab3  mov     [rsp+100h+var_D8], r14
0x180006ab8  cmp     [rsp+100h+var_E0], rdi
0x180006abd  jz      short loc_180006AC9
0x180006abf  lea     rcx, [rsp+100h+var_E0]
0x180006ac4  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006ac9  mov     dword ptr [rbp+57h+var_A0], 1
0x180006ad0  mov     dword ptr [rbp+57h+var_A0+4], 7
0x180006ad7  lea     rax, aColumns; "columns"
0x180006ade  mov     [rbp+57h+var_90], rax
0x180006ae2  lea     rax, [rbp+57h+var_A0]
0x180006ae6  mov     [rbp+57h+var_A8], rax
0x180006aea  lea     r8, [rbp+57h+var_A8]
0x180006aee  lea     rdx, [rbp+57h+var_78]
0x180006af2  lea     rcx, [rsp+100h+var_D8]
0x180006af7  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x180006afc  mov     rdi, [rax]
0x180006aff  xor     ecx, ecx
0x180006b01  mov     [rax], rcx
0x180006b04  mov     [rbp+57h+var_D0], rdi
0x180006b08  cmp     [rbp+57h+var_78], rcx
0x180006b0c  jz      short loc_180006B17
0x180006b0e  lea     rcx, [rbp+57h+var_78]
0x180006b12  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006b17  mov     r8d, 1
0x180006b1d  lea     rdx, [rsp+100h+var_E0]
0x180006b22  lea     rcx, [rbp+57h+var_D0]
0x180006b26  call    ?GetObjectAt@?$consume_Windows_Data_Json_IJsonArray@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(uint)
0x180006b2b  mov     rbx, rax
0x180006b2e  lea     rax, [rsp+100h+var_D8]
0x180006b33  cmp     rax, rbx
0x180006b36  jz      short loc_180006B56
0x180006b38  test    r14, r14
0x180006b3b  jz      short loc_180006B47
0x180006b3d  lea     rcx, [rsp+100h+var_D8]
0x180006b42  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006b47  mov     r14, [rbx]
0x180006b4a  mov     qword ptr [rbx], 0
0x180006b51  mov     [rsp+100h+var_D8], r14
0x180006b56  cmp     [rsp+100h+var_E0], 0
0x180006b5c  jz      short loc_180006B68
0x180006b5e  lea     rcx, [rsp+100h+var_E0]
0x180006b63  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006b68  mov     [rbp+57h+var_C0], 1
0x180006b6f  mov     [rbp+57h+var_BC], 5
0x180006b76  lea     rax, aItems; "items"
0x180006b7d  mov     [rbp+57h+var_B0], rax
0x180006b81  lea     rax, [rbp+57h+var_C0]
0x180006b85  mov     [rbp+57h+var_C8], rax
0x180006b89  lea     r8, [rbp+57h+var_C8]
0x180006b8d  lea     rdx, [rsp+100h+var_E0]
0x180006b92  lea     rcx, [rsp+100h+var_D8]
0x180006b97  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x180006b9c  mov     rbx, rax
0x180006b9f  lea     rax, [rbp+57h+var_D0]
0x180006ba3  cmp     rax, rbx
0x180006ba6  jz      short loc_180006BC4
0x180006ba8  test    rdi, rdi
0x180006bab  jz      short loc_180006BB6
0x180006bad  lea     rcx, [rbp+57h+var_D0]
0x180006bb1  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006bb6  mov     rdi, [rbx]
0x180006bb9  mov     qword ptr [rbx], 0
0x180006bc0  mov     [rbp+57h+var_D0], rdi
0x180006bc4  cmp     [rsp+100h+var_E0], 0
0x180006bca  jz      short loc_180006BD6
0x180006bcc  lea     rcx, [rsp+100h+var_E0]
0x180006bd1  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006bd6  xor     r8d, r8d
0x180006bd9  lea     rdx, [rsp+100h+var_E0]
0x180006bde  lea     rcx, [rbp+57h+var_D0]
0x180006be2  call    ?GetObjectAt@?$consume_Windows_Data_Json_IJsonArray@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(uint)
0x180006be7  mov     rbx, rax
0x180006bea  lea     rax, [rsp+100h+var_D8]
0x180006bef  cmp     rax, rbx
0x180006bf2  jz      short loc_180006C12
0x180006bf4  test    r14, r14
0x180006bf7  jz      short loc_180006C03
0x180006bf9  lea     rcx, [rsp+100h+var_D8]
0x180006bfe  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006c03  mov     r14, [rbx]
0x180006c06  mov     qword ptr [rbx], 0
0x180006c0d  mov     [rsp+100h+var_D8], r14
0x180006c12  xor     ebx, ebx
0x180006c14  cmp     [rsp+100h+var_E0], rbx
0x180006c19  jz      short loc_180006C25
0x180006c1b  lea     rcx, [rsp+100h+var_E0]
0x180006c20  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006c25  mov     rcx, rsi
0x180006c28  inc     rcx
0x180006c2b  cmp     [r15+rcx*2], bx
0x180006c30  jnz     short loc_180006C28
0x180006c32  test    ecx, ecx
0x180006c34  jnz     short loc_180006C3C
0x180006c36  mov     [rbp+57h+var_C8], rbx
0x180006c3a  jmp     short loc_180006C62
0x180006c3c  mov     eax, ecx
0x180006c3e  cmp     [r15+rax*2], bx
0x180006c43  jz      short loc_180006C4C
0x180006c45  call    cs:__imp_abort
0x180006c4c  mov     [rbp+57h+var_C0], 1
0x180006c53  mov     [rbp+57h+var_BC], ecx
0x180006c56  mov     [rbp+57h+var_B0], r15
0x180006c5a  lea     rax, [rbp+57h+var_C0]
0x180006c5e  mov     [rbp+57h+var_C8], rax
0x180006c62  lea     rdx, [rbp+57h+var_C8]
0x180006c66  lea     rcx, [rbp+57h+var_80]; struct winrt::param::hstring *
0x180006c6a  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180006c6f  nop
0x180006c70  mov     [rbp+57h+var_50], 1
0x180006c77  mov     [rbp+57h+var_4C], 4
0x180006c7e  lea     rax, aText; "text"
0x180006c85  mov     [rbp+57h+var_40], rax
0x180006c89  lea     rax, [rbp+57h+var_50]
0x180006c8d  mov     [rbp+57h+var_58], rax
0x180006c91  mov     dword ptr [rbp+57h+var_A8], ebx
0x180006c94  xorps   xmm0, xmm0
0x180006c97  movdqu  [rbp+57h+var_A0], xmm0
0x180006c9c  mov     rax, [r14]
0x180006c9f  mov     rbx, [rbp+57h+var_80]
0x180006ca3  mov     r8, rbx
0x180006ca6  lea     rdx, [rbp+57h+var_50]
0x180006caa  mov     rcx, r14
0x180006cad  mov     rax, [rax+38h]
0x180006cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb6  test    eax, eax
0x180006cb8  js      loc_180006E5A
0x180006cbe  mov     r8d, 1
0x180006cc4  lea     rdx, [rsp+100h+var_E0]
0x180006cc9  lea     rcx, [rbp+57h+arg_18]
0x180006ccd  call    ?GetObjectAt@?$consume_Windows_Data_Json_IJsonArray@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(uint)
0x180006cd2  mov     r15, rax
0x180006cd5  lea     rax, [rsp+100h+var_D8]
0x180006cda  cmp     rax, r15
0x180006cdd  jz      short loc_180006CF8
0x180006cdf  lea     rcx, [rsp+100h+var_D8]
0x180006ce4  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006ce9  mov     r14, [r15]
0x180006cec  mov     qword ptr [r15], 0
0x180006cf3  mov     [rsp+100h+var_D8], r14
0x180006cf8  xor     r15d, r15d
0x180006cfb  cmp     [rsp+100h+var_E0], r15
0x180006d00  jz      short loc_180006D0C
0x180006d02  lea     rcx, [rsp+100h+var_E0]
0x180006d07  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006d0c  inc     rsi
0x180006d0f  cmp     [r12+rsi*2], r15w
0x180006d14  jnz     short loc_180006D0C
0x180006d16  test    esi, esi
0x180006d18  jnz     short loc_180006D20
0x180006d1a  mov     [rbp+57h+var_A8], r15
0x180006d1e  jmp     short loc_180006D46
0x180006d20  mov     eax, esi
0x180006d22  cmp     [r12+rax*2], r15w
0x180006d27  jz      short loc_180006D30
0x180006d29  call    cs:__imp_abort
0x180006d30  mov     dword ptr [rbp+57h+var_A0], 1
0x180006d37  mov     dword ptr [rbp+57h+var_A0+4], esi
0x180006d3a  mov     [rbp+57h+var_90], r12
0x180006d3e  lea     rax, [rbp+57h+var_A0]
0x180006d42  mov     [rbp+57h+var_A8], rax
0x180006d46  lea     rdx, [rbp+57h+var_A8]
0x180006d4a  lea     rcx, [rsp+100h+var_E0]; struct winrt::param::hstring *
0x180006d4f  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180006d54  mov     rsi, rax
0x180006d57  lea     rax, [rbp+57h+var_80]
0x180006d5b  cmp     rax, rsi
0x180006d5e  jz      short loc_180006D78
0x180006d60  test    rbx, rbx
0x180006d63  jz      short loc_180006D6E
0x180006d65  lea     rcx, [rbp+57h+var_80]
0x180006d69  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006d6e  mov     rbx, [rsi]
0x180006d71  mov     [rsi], r15
0x180006d74  mov     [rbp+57h+var_80], rbx
0x180006d78  cmp     [rsp+100h+var_E0], r15
0x180006d7d  jz      short loc_180006D89
0x180006d7f  lea     rcx, [rsp+100h+var_E0]
0x180006d84  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006d89  mov     [rbp+57h+var_50], 1
0x180006d90  mov     [rbp+57h+var_4C], 4
0x180006d97  lea     rax, aText; "text"
0x180006d9e  mov     [rbp+57h+var_40], rax
0x180006da2  lea     rax, [rbp+57h+var_50]
0x180006da6  mov     [rbp+57h+var_58], rax
0x180006daa  mov     dword ptr [rbp+57h+var_A8], r15d
0x180006dae  xorps   xmm0, xmm0
0x180006db1  movdqu  [rbp+57h+var_A0], xmm0
0x180006db6  mov     rax, [r14]
0x180006db9  mov     r8, rbx
0x180006dbc  lea     rdx, [rbp+57h+var_50]
0x180006dc0  mov     rcx, r14
0x180006dc3  mov     rax, [rax+38h]
0x180006dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dcc  test    eax, eax
0x180006dce  js      short loc_180006E36
0x180006dd0  test    rbx, rbx
0x180006dd3  jz      short loc_180006DDF
0x180006dd5  lea     rcx, [rbp+57h+var_80]
0x180006dd9  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180006dde  nop
0x180006ddf  test    rdi, rdi
  ... truncated ...
```
