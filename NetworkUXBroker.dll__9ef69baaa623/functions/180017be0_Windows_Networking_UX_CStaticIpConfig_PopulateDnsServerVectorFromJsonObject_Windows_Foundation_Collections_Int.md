# Windows::Networking::UX::CStaticIpConfig::PopulateDnsServerVectorFromJsonObject(Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0> *,ushort const * const,winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x180017be0`
- end: `0x180017e2d`
- name: `?PopulateDnsServerVectorFromJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJPEAV?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@4@QEBGAEBUJsonObject@Json@Data@4winrt@@@Z`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014590`

## callees

- `0x18000cd70`
- `0x18000ce20`
- `0x18000cf18`
- `0x18000def4`
- `0x18000df58`
- `0x18000dfac`
- `0x18000e768`
- `0x18000e900`
- `0x18000f1d0`
- `0x180013b8c`
- `0x1800156e4`
- `0x18001587c`
- `0x180016d54`
- `0x180017be0`

## string_xrefs

- `0x180017cf1`: `dohTemplate`
- `0x180017c85`: `encryptedDnsProtocols`
- `0x180017d8b`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::PopulateDnsServerVectorFromJsonObject(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // esi
  __int64 *NamedString; // rax
  __int64 v6; // rcx
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // r9
  int v10; // eax
  unsigned int v11; // edi
  const char *v12; // r9
  __int64 result; // rax
  int v14; // ebx
  int v15; // [rsp+20h] [rbp-98h] BYREF
  __int128 v16; // [rsp+28h] [rbp-90h] BYREF
  __int64 v17; // [rsp+38h] [rbp-80h]
  __int128 v18; // [rsp+40h] [rbp-78h] BYREF
  __int64 v19; // [rsp+50h] [rbp-68h]
  _BYTE v20[8]; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v21[8]; // [rsp+68h] [rbp-50h] BYREF
  __int64 *v22; // [rsp+70h] [rbp-48h] BYREF
  int v23; // [rsp+78h] [rbp-40h]
  _BYTE v24[56]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  __int64 v26; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v27; // [rsp+D0h] [rbp+18h] BYREF

  v27 = a3;
  v26 = a1;
  winrt::param::hstring::hstring((winrt::param::hstring *)v24, L"dnsServers");
  try
  {
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray();
    v22 = &v26;
    v14 = 0;
    v23 = 0;
    v4 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v26);
    while ( v14 != v4 )
    {
      winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*((__int64)&v22, (__int64)&v15);
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(&v15, &v27);
      v16 = 0;
      v17 = 0;
      winrt::param::hstring::hstring((winrt::param::hstring *)&v18, L"encryptedDnsProtocols");
      DWORD1(v16) = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                           &v27,
                           &v18);
      winrt::param::hstring::hstring((winrt::param::hstring *)&v18, L"address");
      NamedString = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                 &v27,
                                 v20,
                                 &v18);
      v6 = *NamedString;
      *NamedString = 0;
      *((_QWORD *)&v16 + 1) = v6;
      winrt::handle_type<winrt::impl::hstring_traits>::close(v20);
      winrt::param::hstring::hstring((winrt::param::hstring *)&v18, L"dohTemplate");
      v7 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                        &v27,
                        v21,
                        &v18);
      v8 = *v7;
      *v7 = 0;
      v17 = v8;
      winrt::handle_type<winrt::impl::hstring_traits>::close(v21);
      winrt::param::hstring::hstring((winrt::param::hstring *)&v18, L"isWellKnownDoh");
      LOBYTE(v16) = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
                      &v27,
                      &v18);
      v18 = v16;
      v19 = v8;
      LOBYTE(v9) = 1;
      v10 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
              a2,
              0,
              &v18,
              v9);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x35B,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)v10,
          v15);
        FreeDnsServer((HSTRING *)&v16);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v27);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v15);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v26);
        return v11;
      }
      FreeDnsServer((HSTRING *)&v16);
      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v27);
      winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v15);
      v23 = ++v14;
    }
    winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v26);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x360,
                     (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                     v12);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x180017be0  mov     rax, rsp
0x180017be3  mov     [rax+10h], rbx
0x180017be7  mov     [rax+18h], r8
0x180017beb  mov     [rax+8], rcx
0x180017bef  push    rsi
0x180017bf0  push    rdi
0x180017bf1  push    r14
0x180017bf3  sub     rsp, 0A0h
0x180017bfa  mov     rbx, r9
0x180017bfd  mov     r14, rdx
0x180017c00  lea     rdx, aDnsservers; "dnsServers"
0x180017c07  lea     rcx, [rax-38h]; this
0x180017c0b  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180017c10  lea     r8, [rsp+0B8h+var_38]
0x180017c18  lea     rdx, [rsp+0B8h+arg_0]
0x180017c20  mov     rcx, rbx
0x180017c23  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x180017c28  nop
0x180017c29  lea     rax, [rsp+0B8h+arg_0]
0x180017c31  mov     [rsp+0B8h+var_48], rax
0x180017c36  xor     ebx, ebx
0x180017c38  mov     [rsp+0B8h+var_40], ebx
0x180017c3c  lea     rcx, [rsp+0B8h+arg_0]
0x180017c44  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180017c49  mov     esi, eax
0x180017c4b  cmp     ebx, esi
0x180017c4d  jz      loc_180017E00
0x180017c53  lea     rdx, [rsp+0B8h+var_98]
0x180017c58  lea     rcx, [rsp+0B8h+var_48]
0x180017c5d  call    ??D?$fast_iterator@UJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA?AUIJsonValue@Json@Data@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(void)
0x180017c62  nop
0x180017c63  lea     rdx, [rsp+0B8h+arg_10]
0x180017c6b  lea     rcx, [rsp+0B8h+var_98]
0x180017c70  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x180017c75  nop
0x180017c76  xorps   xmm0, xmm0
0x180017c79  xor     eax, eax
0x180017c7b  movups  [rsp+0B8h+var_90], xmm0
0x180017c80  mov     [rsp+0B8h+var_80], rax
0x180017c85  lea     rdx, aEncrypteddnspr; "encryptedDnsProtocols"
0x180017c8c  lea     rcx, [rsp+0B8h+var_78]; this
0x180017c91  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180017c96  lea     rdx, [rsp+0B8h+var_78]
0x180017c9b  lea     rcx, [rsp+0B8h+arg_10]
0x180017ca3  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x180017ca8  cvttsd2si eax, xmm0
0x180017cac  mov     dword ptr [rsp+0B8h+var_90+4], eax
0x180017cb0  lea     rdx, aAddress; "address"
0x180017cb7  lea     rcx, [rsp+0B8h+var_78]; this
0x180017cbc  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180017cc1  lea     r8, [rsp+0B8h+var_78]
0x180017cc6  lea     rdx, [rsp+0B8h+var_58]
0x180017ccb  lea     rcx, [rsp+0B8h+arg_10]
0x180017cd3  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x180017cd8  mov     rcx, [rax]
0x180017cdb  mov     qword ptr [rax], 0
0x180017ce2  mov     qword ptr [rsp+0B8h+var_90+8], rcx
0x180017ce7  lea     rcx, [rsp+0B8h+var_58]
0x180017cec  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180017cf1  lea     rdx, aDohtemplate; "dohTemplate"
0x180017cf8  lea     rcx, [rsp+0B8h+var_78]; this
0x180017cfd  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180017d02  lea     r8, [rsp+0B8h+var_78]
0x180017d07  lea     rdx, [rsp+0B8h+var_50]
0x180017d0c  lea     rcx, [rsp+0B8h+arg_10]
0x180017d14  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x180017d19  mov     rdi, [rax]
0x180017d1c  mov     qword ptr [rax], 0
0x180017d23  mov     [rsp+0B8h+var_80], rdi
0x180017d28  lea     rcx, [rsp+0B8h+var_50]
0x180017d2d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180017d32  lea     rdx, aIswellknowndoh; "isWellKnownDoh"
0x180017d39  lea     rcx, [rsp+0B8h+var_78]; this
0x180017d3e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180017d43  lea     rdx, [rsp+0B8h+var_78]
0x180017d48  lea     rcx, [rsp+0B8h+arg_10]
0x180017d50  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(winrt::param::hstring const &)
0x180017d55  mov     byte ptr [rsp+0B8h+var_90], al
0x180017d59  movups  xmm0, [rsp+0B8h+var_90]
0x180017d5e  movaps  [rsp+0B8h+var_78], xmm0
0x180017d63  mov     [rsp+0B8h+var_68], rdi
0x180017d68  mov     r9b, 1
0x180017d6b  lea     r8, [rsp+0B8h+var_78]
0x180017d70  xor     edx, edx
0x180017d72  mov     rcx, r14
0x180017d75  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180017d7a  mov     edi, eax
0x180017d7c  test    eax, eax
0x180017d7e  jns     short loc_180017DD2
0x180017d80  mov     rcx, [rsp+0B8h]; this
0x180017d88  mov     r9d, eax; char *
0x180017d8b  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180017d92  mov     edx, 35Bh; void *
0x180017d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d9c  nop
0x180017d9d  lea     rcx, [rsp+0B8h+var_90]; struct Windows::Networking::UX::DnsServer *
0x180017da2  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180017da7  nop
0x180017da8  lea     rcx, [rsp+0B8h+arg_10]; this
0x180017db0  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180017db5  nop
0x180017db6  lea     rcx, [rsp+0B8h+var_98]; this
0x180017dbb  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180017dc0  nop
0x180017dc1  lea     rcx, [rsp+0B8h+arg_0]; this
0x180017dc9  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180017dce  mov     eax, edi
0x180017dd0  jmp     short loc_180017E18
0x180017dd2  lea     rcx, [rsp+0B8h+var_90]; struct Windows::Networking::UX::DnsServer *
0x180017dd7  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180017ddc  nop
0x180017ddd  lea     rcx, [rsp+0B8h+arg_10]; this
0x180017de5  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180017dea  nop
0x180017deb  lea     rcx, [rsp+0B8h+var_98]; this
0x180017df0  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180017df5  inc     ebx
0x180017df7  mov     [rsp+0B8h+var_40], ebx
0x180017dfb  jmp     loc_180017C4B
0x180017e00  lea     rcx, [rsp+0B8h+arg_0]; this
0x180017e08  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180017e0d  xor     eax, eax
0x180017e0f  jmp     short loc_180017E18
0x180017e11  mov     eax, dword ptr [rsp+0B8h+arg_10]
0x180017e18  mov     rbx, [rsp+0B8h+arg_8]
0x180017e20  add     rsp, 0A0h
0x180017e27  pop     r14
0x180017e29  pop     rdi
0x180017e2a  pop     rsi
0x180017e2b  retn
```
