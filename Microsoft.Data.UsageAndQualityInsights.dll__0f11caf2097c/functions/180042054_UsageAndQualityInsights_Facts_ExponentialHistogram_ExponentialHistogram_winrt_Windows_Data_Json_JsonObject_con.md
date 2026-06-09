# UsageAndQualityInsights::Facts::ExponentialHistogram::ExponentialHistogram(winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x180042054`
- end: `0x18004241e`
- name: `??0ExponentialHistogram@Facts@UsageAndQualityInsights@@QEAA@AEBUJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `970`
- prototype: `__int64 __fastcall(UsageAndQualityInsights::Facts::ExponentialHistogram *__hidden this, const struct winrt::Windows::Data::Json::JsonObject *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049a7c`

## callees

- `0x1800038b8`
- `0x180003f70`
- `0x18000c844`
- `0x18001112c`
- `0x1800163f8`
- `0x180016680`
- `0x180027fdc`
- `0x18002804c`
- `0x180028190`
- `0x18002a9c8`
- `0x180042054`
- `0x180048498`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004208c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800420d4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180042116`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180042184`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800421f9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004208c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800420d4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180042116`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180042184`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800421f9`

## string_xrefs

- `0x180042267`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
UsageAndQualityInsights::Facts::ExponentialHistogram *__fastcall UsageAndQualityInsights::Facts::ExponentialHistogram::ExponentialHistogram(
        UsageAndQualityInsights::Facts::ExponentialHistogram *this,
        const struct winrt::Windows::Data::Json::JsonObject *a2)
{
  double NamedNumber; // xmm0_8
  double v5; // xmm1_8
  char *v6; // rsi
  _QWORD *v7; // rax
  unsigned int v8; // r14d
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  int Number; // r13d
  __int64 v13; // rax
  double v14; // xmm6_8
  __int64 *v15; // rcx
  __int64 *v16; // rax
  int v17; // r15d
  __int64 *v18; // r12
  __int64 v19; // rbx
  double *v20; // rax
  _QWORD *v22; // [rsp+28h] [rbp-79h] BYREF
  _QWORD v23[2]; // [rsp+30h] [rbp-71h] BYREF
  const wchar_t *v24; // [rsp+40h] [rbp-61h]
  __int64 v25; // [rsp+48h] [rbp-59h] BYREF
  __int64 v26; // [rsp+50h] [rbp-51h] BYREF
  __int64 v27; // [rsp+58h] [rbp-49h] BYREF
  __int64 v28; // [rsp+60h] [rbp-41h] BYREF
  __int64 v29; // [rsp+68h] [rbp-39h] BYREF
  __int64 v30; // [rsp+70h] [rbp-31h]
  __int64 *v31; // [rsp+78h] [rbp-29h] BYREF
  int v32; // [rsp+80h] [rbp-21h]
  int v33; // [rsp+84h] [rbp-1Dh]
  char *v34; // [rsp+88h] [rbp-19h]
  __int64 v35; // [rsp+90h] [rbp-11h]
  _DWORD *v36; // [rsp+98h] [rbp-9h] BYREF
  _DWORD v37[4]; // [rsp+A0h] [rbp-1h] BYREF
  const wchar_t *v38; // [rsp+B0h] [rbp+Fh]
  int v39; // [rsp+118h] [rbp+77h]
  __int64 v40; // [rsp+120h] [rbp+7Fh] BYREF

  if ( aCapacity[8] )
    abort();
  v23[0] = 0x800000001LL;
  v24 = L"capacity";
  v22 = v23;
  *(_DWORD *)this = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                           a2,
                           &v22);
  if ( aType[4] )
    abort();
  v23[0] = 0x400000001LL;
  v24 = L"type";
  v22 = v23;
  *((_BYTE *)this + 4) = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                                a2,
                                &v22);
  if ( aScale[5] )
    abort();
  v23[0] = 0x500000001LL;
  v24 = L"scale";
  v22 = v23;
  NamedNumber = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                  a2,
                  &v22);
  *((_DWORD *)this + 2) = (int)NamedNumber;
  v5 = pow(2.0, (double)-(int)NamedNumber);
  *((double *)this + 2) = pow(2.0, v5);
  if ( aZerobucket[10] )
    abort();
  v23[0] = 0xA00000001LL;
  v24 = L"zeroBucket";
  v22 = v23;
  *((double *)this + 3) = (double)(int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                                         a2,
                                         &v22);
  v6 = (char *)this + 32;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v7 = operator new(0x30u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  *((_QWORD *)this + 4) = v7;
  if ( aPositivebucket[14] )
    abort();
  v37[0] = 1;
  v37[1] = 14;
  v38 = L"positiveBucket";
  v36 = v37;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
    a2,
    &v40,
    &v36);
  v8 = 0;
  v9 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v40);
  v39 = v9;
  while ( v8 != v9 )
  {
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
      &v40,
      &v27,
      v8);
    v25 = 0;
    LODWORD(v22) = 530;
    v23[0] = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v23[1] = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 88LL))(v27, &v25);
    if ( v10 < 0 )
      winrt::throw_hresult((unsigned int)v10, &v22);
    v26 = v25;
    v11 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
            &v26,
            &v28,
            0);
    Number = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(v11);
    if ( v28 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v28);
    v13 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
            &v26,
            &v29,
            1);
    v14 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(v13);
    if ( v29 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v29);
    v15 = *(__int64 **)v6;
    v16 = *(__int64 **)(*(_QWORD *)v6 + 8LL);
    v17 = 0;
    v30 = 0;
    if ( *((_BYTE *)v16 + 25) )
    {
      v18 = v16;
    }
    else
    {
      do
      {
        v18 = v16;
        v22 = v16;
        if ( *((_DWORD *)v16 + 8) >= Number )
        {
          v17 = 1;
          v15 = v16;
          v16 = (__int64 *)*v16;
        }
        else
        {
          v17 = 0;
          v16 = (__int64 *)v16[2];
        }
      }
      while ( !*((_BYTE *)v16 + 25) );
    }
    if ( *((_BYTE *)v15 + 25) || Number < *((_DWORD *)v15 + 8) )
    {
      if ( *((_QWORD *)this + 5) == 0x555555555555555LL )
        std::_Throw_tree_length_error();
      v19 = *(_QWORD *)v6;
      v34 = (char *)this + 32;
      v35 = 0;
      v20 = (double *)operator new(0x30u);
      *((_DWORD *)v20 + 8) = Number;
      v20[5] = v14;
      *(_QWORD *)v20 = v19;
      *((_QWORD *)v20 + 1) = v19;
      *((_QWORD *)v20 + 2) = v19;
      *((_WORD *)v20 + 12) = 0;
      v35 = 0;
      v31 = v18;
      v32 = v17;
      v33 = v30;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(
        (char *)this + 32,
        &v31,
        v20);
    }
    if ( v25 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v26);
    if ( v27 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v27);
    ++v8;
    v9 = v39;
  }
  if ( v40 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v40);
  return this;
}

```

## disassembly

```asm
0x180042054  mov     rax, rsp
0x180042057  mov     [rax+10h], rbx
0x18004205b  mov     [rax+8], rcx
0x18004205f  push    rbp
0x180042060  push    rsi
0x180042061  push    rdi
0x180042062  push    r12
0x180042064  push    r13
0x180042066  push    r14
0x180042068  push    r15
0x18004206a  lea     rbp, [rax-5Fh]
0x18004206e  sub     rsp, 0C0h
0x180042075  movaps  xmmword ptr [rax-48h], xmm6
0x180042079  mov     rbx, rdx
0x18004207c  mov     rdi, rcx
0x18004207f  xor     r12d, r12d
0x180042082  cmp     word ptr cs:aCapacity+10h, r12w; ""
0x18004208a  jz      short loc_180042093
0x18004208c  call    cs:__imp_abort
0x180042093  mov     r15d, 1
0x180042099  mov     dword ptr [rbp+57h+var_C8], r15d
0x18004209d  mov     dword ptr [rbp+57h+var_C8+4], 8
0x1800420a4  lea     rax, aCapacity; "capacity"
0x1800420ab  mov     [rbp+57h+var_B8], rax
0x1800420af  lea     rax, [rbp+57h+var_C8]
0x1800420b3  mov     [rbp+57h+var_D0], rax
0x1800420b7  lea     rdx, [rbp+57h+var_D0]
0x1800420bb  mov     rcx, rbx
0x1800420be  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x1800420c3  cvttsd2si rax, xmm0
0x1800420c8  mov     [rdi], eax
0x1800420ca  cmp     word ptr cs:aType+8, r12w; ""
0x1800420d2  jz      short loc_1800420DB
0x1800420d4  call    cs:__imp_abort
0x1800420db  mov     dword ptr [rbp+57h+var_C8], r15d
0x1800420df  mov     dword ptr [rbp+57h+var_C8+4], 4
0x1800420e6  lea     rax, aType; "type"
0x1800420ed  mov     [rbp+57h+var_B8], rax
0x1800420f1  lea     rax, [rbp+57h+var_C8]
0x1800420f5  mov     [rbp+57h+var_D0], rax
0x1800420f9  lea     rdx, [rbp+57h+var_D0]
0x1800420fd  mov     rcx, rbx
0x180042100  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x180042105  cvttsd2si eax, xmm0
0x180042109  mov     [rdi+4], al
0x18004210c  cmp     word ptr cs:aScale+0Ah, r12w; ""
0x180042114  jz      short loc_18004211D
0x180042116  call    cs:__imp_abort
0x18004211d  mov     dword ptr [rbp+57h+var_C8], r15d
0x180042121  mov     dword ptr [rbp+57h+var_C8+4], 5
0x180042128  lea     rax, aScale; "scale"
0x18004212f  mov     [rbp+57h+var_B8], rax
0x180042133  lea     rax, [rbp+57h+var_C8]
0x180042137  mov     [rbp+57h+var_D0], rax
0x18004213b  lea     rdx, [rbp+57h+var_D0]
0x18004213f  mov     rcx, rbx
0x180042142  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x180042147  cvttsd2si eax, xmm0
0x18004214b  mov     [rdi+8], eax
0x18004214e  neg     eax
0x180042150  movd    xmm1, eax
0x180042154  cvtdq2pd xmm1, xmm1; Y
0x180042158  movsd   xmm0, cs:__real@4000000000000000; X
0x180042160  call    pow
0x180042165  movaps  xmm1, xmm0; Y
0x180042168  movsd   xmm0, cs:__real@4000000000000000; X
0x180042170  call    pow
0x180042175  movsd   qword ptr [rdi+10h], xmm0
0x18004217a  cmp     word ptr cs:aZerobucket+14h, r12w; ""
0x180042182  jz      short loc_18004218B
0x180042184  call    cs:__imp_abort
0x18004218b  mov     dword ptr [rbp+57h+var_C8], r15d
0x18004218f  mov     dword ptr [rbp+57h+var_C8+4], 0Ah
0x180042196  lea     rax, aZerobucket; "zeroBucket"
0x18004219d  mov     [rbp+57h+var_B8], rax
0x1800421a1  lea     rax, [rbp+57h+var_C8]
0x1800421a5  mov     [rbp+57h+var_D0], rax
0x1800421a9  lea     rdx, [rbp+57h+var_D0]
0x1800421ad  mov     rcx, rbx
0x1800421b0  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x1800421b5  cvttsd2si eax, xmm0
0x1800421b9  movd    xmm1, eax
0x1800421bd  cvtdq2pd xmm1, xmm1
0x1800421c1  movsd   qword ptr [rdi+18h], xmm1
0x1800421c6  lea     rsi, [rdi+20h]
0x1800421ca  mov     [rsi], r12
0x1800421cd  mov     [rsi+8], r12
0x1800421d1  mov     ecx, 30h ; '0'; Size
0x1800421d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800421db  mov     [rax], rax
0x1800421de  mov     [rax+8], rax
0x1800421e2  mov     [rax+10h], rax
0x1800421e6  mov     word ptr [rax+18h], 101h
0x1800421ec  mov     [rsi], rax
0x1800421ef  cmp     word ptr cs:aPositivebucket+1Ch, r12w; ""
0x1800421f7  jz      short loc_180042200
0x1800421f9  call    cs:__imp_abort
0x180042200  mov     [rbp+57h+var_58], r15d
0x180042204  mov     [rbp+57h+var_54], 0Eh
0x18004220b  lea     rax, aPositivebucket; "positiveBucket"
0x180042212  mov     [rbp+57h+var_48], rax
0x180042216  lea     rax, [rbp+57h+var_58]
0x18004221a  mov     [rbp+57h+var_60], rax
0x18004221e  lea     r8, [rbp+57h+var_60]
0x180042222  lea     rdx, [rbp+57h+arg_18]
0x180042226  mov     rcx, rbx
0x180042229  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x18004222e  nop
0x18004222f  mov     r14d, r12d
0x180042232  lea     rcx, [rbp+57h+arg_18]
0x180042236  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x18004223b  mov     [rbp+57h+arg_10], eax
0x18004223e  cmp     r14d, eax
0x180042241  jz      loc_1800423D9
0x180042247  mov     r8d, r14d
0x18004224a  lea     rdx, [rbp+57h+var_A0]
0x18004224e  lea     rcx, [rbp+57h+arg_18]
0x180042252  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(uint)
0x180042257  nop
0x180042258  mov     [rbp+57h+var_B0], r12
0x18004225c  mov     rcx, [rbp+57h+var_A0]
0x180042260  mov     dword ptr [rbp+57h+var_D0], 212h
0x180042267  lea     rax, aOnecoreuapInte_0; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x18004226e  mov     [rbp+57h+var_C8], rax
0x180042272  mov     [rbp+57h+var_C0], r12
0x180042276  mov     rax, [rcx]
0x180042279  lea     rdx, [rbp+57h+var_B0]
0x18004227d  mov     rax, [rax+58h]
0x180042281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042286  test    eax, eax
0x180042288  js      loc_18004240C
0x18004228e  mov     rax, [rbp+57h+var_B0]
0x180042292  mov     [rbp+57h+var_A8], rax
0x180042296  xor     r8d, r8d
0x180042299  lea     rdx, [rbp+57h+var_98]
0x18004229d  lea     rcx, [rbp+57h+var_A8]
0x1800422a1  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(uint)
0x1800422a6  nop
0x1800422a7  mov     rcx, rax
0x1800422aa  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x1800422af  cvttsd2si r13d, xmm0
0x1800422b4  cmp     [rbp+57h+var_98], r12
0x1800422b8  jz      short loc_1800422C3
0x1800422ba  lea     rcx, [rbp+57h+var_98]
0x1800422be  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800422c3  mov     r8d, r15d
0x1800422c6  lea     rdx, [rbp+57h+var_90]
0x1800422ca  lea     rcx, [rbp+57h+var_A8]
0x1800422ce  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(uint)
0x1800422d3  nop
0x1800422d4  mov     rcx, rax
0x1800422d7  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x1800422dc  movaps  xmm6, xmm0
0x1800422df  cmp     [rbp+57h+var_90], r12
0x1800422e3  jz      short loc_1800422EE
0x1800422e5  lea     rcx, [rbp+57h+var_90]
0x1800422e9  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800422ee  mov     rcx, [rsi]
0x1800422f1  mov     rax, [rcx+8]
0x1800422f5  mov     r15d, r12d
0x1800422f8  xor     edx, edx
0x1800422fa  mov     [rbp+57h+var_88], rdx
0x1800422fe  cmp     [rax+19h], r12b
0x180042302  jnz     short loc_18004232D
0x180042304  mov     r12, rax
0x180042307  mov     [rbp+57h+var_D0], rax
0x18004230b  cmp     [rax+20h], r13d
0x18004230f  jge     short loc_18004231A
0x180042311  xor     r15d, r15d
0x180042314  mov     rax, [rax+10h]
0x180042318  jmp     short loc_180042326
0x18004231a  mov     r15d, 1
0x180042320  mov     rcx, rax
0x180042323  mov     rax, [rax]
0x180042326  cmp     [rax+19h], dl
0x180042329  jz      short loc_180042304
0x18004232b  jmp     short loc_180042330
0x18004232d  mov     r12, rax
0x180042330  cmp     [rcx+19h], dl
0x180042333  jnz     short loc_18004233B
0x180042335  cmp     r13d, [rcx+20h]
0x180042339  jge     short loc_1800423A6
0x18004233b  mov     rax, 555555555555555h
0x180042345  cmp     [rsi+8], rax
0x180042349  jz      loc_180042418
0x18004234f  mov     rbx, [rsi]
0x180042352  mov     [rbp+57h+var_70], rsi
0x180042356  mov     [rbp+57h+var_68], 0
0x18004235e  mov     ecx, 30h ; '0'; Size
0x180042363  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042368  nop
0x180042369  mov     [rax+20h], r13d
0x18004236d  movsd   qword ptr [rax+28h], xmm6
0x180042372  mov     [rax], rbx
0x180042375  mov     [rax+8], rbx
0x180042379  mov     [rax+10h], rbx
0x18004237d  xor     ecx, ecx
0x18004237f  mov     [rax+18h], cx
0x180042383  mov     [rbp+57h+var_68], rcx
0x180042387  mov     [rbp+57h+var_80], r12
0x18004238b  mov     [rbp+57h+var_78], r15d
0x18004238f  mov     rcx, [rbp+57h+var_88]
0x180042393  mov     [rbp+57h+var_74], ecx
0x180042396  mov     r8, rax
0x180042399  lea     rdx, [rbp+57h+var_80]
0x18004239d  mov     rcx, rsi
0x1800423a0  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration>>,void *> * const)
0x1800423a5  nop
0x1800423a6  xor     r12d, r12d
0x1800423a9  cmp     [rbp+57h+var_B0], r12
0x1800423ad  jz      short loc_1800423B9
0x1800423af  lea     rcx, [rbp+57h+var_A8]
0x1800423b3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800423b8  nop
0x1800423b9  cmp     [rbp+57h+var_A0], r12
0x1800423bd  jz      short loc_1800423C8
0x1800423bf  lea     rcx, [rbp+57h+var_A0]
0x1800423c3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800423c8  mov     r15d, 1
0x1800423ce  add     r14d, r15d
0x1800423d1  mov     eax, [rbp+57h+arg_10]
0x1800423d4  jmp     loc_18004223E
0x1800423d9  cmp     [rbp+57h+arg_18], r12
0x1800423dd  jz      short loc_1800423E9
0x1800423df  lea     rcx, [rbp+57h+arg_18]
0x1800423e3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800423e8  nop
0x1800423e9  mov     rax, rdi
0x1800423ec  lea     r11, [rsp+0F0h+var_30]
0x1800423f4  mov     rbx, [r11+48h]
0x1800423f8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800423fd  mov     rsp, r11
0x180042400  pop     r15
0x180042402  pop     r14
0x180042404  pop     r13
0x180042406  pop     r12
0x180042408  pop     rdi
0x180042409  pop     rsi
0x18004240a  pop     rbp
0x18004240b  retn
0x18004240c  lea     rdx, [rbp+57h+var_D0]
0x180042410  mov     ecx, eax
0x180042412  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180042418  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
