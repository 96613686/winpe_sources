# Windows::Networking::UX::CStaticIpConfig::AddDnsServerArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0> *)

- ea: `0x18001281c`
- end: `0x180012bfd`
- name: `?AddDnsServerArrayToJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@4@@Z`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019960`

## callees

- `0x18000c824`
- `0x18000c844`
- `0x18000cd70`
- `0x18000ce20`
- `0x18000ced4`
- `0x18000d528`
- `0x18000d5e4`
- `0x18000d620`
- `0x18000d6a4`
- `0x18000e768`
- `0x18000e8b8`
- `0x18000f12c`
- `0x18000f1d0`
- `0x18000f228`
- `0x18001281c`
- `0x180013b8c`
- `0x180014df0`
- `0x18001a900`
- `0x180047010`

## string_xrefs

- `0x1800129f2`: `dohTemplate`
- `0x180012a50`: `encryptedDnsProtocols`
- `0x180012861`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x1800128d0`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::AddDnsServerArrayToJsonObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Size; // eax
  const char *v7; // r9
  unsigned int v8; // ebx
  __int64 result; // rax
  unsigned int i; // edi
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // r8d
  struct winrt::impl::hstring_header *hstring_on_heap; // rax
  unsigned int v15; // r8d
  struct winrt::impl::hstring_header *v16; // rax
  __int64 *StringValue; // rax
  double v18; // xmm0_8
  __int64 *NumberValue; // rax
  __int64 *BooleanValue; // rax
  struct IUnknown v21; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+28h] [rbp-B0h] BYREF
  struct IUnknown v23; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+40h] [rbp-98h] BYREF
  __int128 v26; // [rsp+48h] [rbp-90h] BYREF
  __int64 v27; // [rsp+58h] [rbp-80h]
  _QWORD v28[4]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v29[8]; // [rsp+80h] [rbp-58h] BYREF
  _BYTE v30[8]; // [rsp+88h] [rbp-50h] BYREF
  bool v31[8]; // [rsp+90h] [rbp-48h] BYREF
  __int64 v32; // [rsp+98h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  __int64 v34; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v35; // [rsp+F0h] [rbp+18h] BYREF

  HIDWORD(v35) = HIDWORD(a3);
  v34 = a1;
  LODWORD(v35) = 0;
  Size = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::get_Size(
           a4,
           &v35);
  v8 = Size;
  if ( Size >= 0 )
  {
    try
    {
      if ( (_DWORD)v35 )
      {
        winrt::Windows::Data::Json::JsonArray::JsonArray(&v23);
        for ( i = 0; i < (unsigned int)v35; ++i )
        {
          v26 = 0;
          v27 = 0;
          v11 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                  a4,
                  i,
                  &v26);
          v12 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x30E,
              (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
              (const char *)(unsigned int)v11,
              (int)v21.lpVtbl);
            FreeDnsServer((HSTRING *)&v26);
            winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v23);
            result = v12;
            goto LABEL_27;
          }
          winrt::Windows::Data::Json::JsonObject::JsonObject(&v21);
          v22 = 0;
          hstring_on_heap = (struct winrt::impl::hstring_header *)*((_QWORD *)&v26 + 1);
          if ( *((_QWORD *)&v26 + 1) )
          {
            if ( (**((_BYTE **)&v26 + 1) & 1) != 0 )
              hstring_on_heap = winrt::impl::create_hstring_on_heap(
                                  *(winrt::impl **)(*((_QWORD *)&v26 + 1) + 16LL),
                                  (winrt::impl *)*(unsigned int *)(*((_QWORD *)&v26 + 1) + 4LL),
                                  v13);
            else
              _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 24LL));
          }
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v22, hstring_on_heap);
          v32 = v22;
          winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v34);
          winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"address");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v21,
            v28,
            &v34);
          v16 = (struct winrt::impl::hstring_header *)v27;
          if ( v27 )
          {
            if ( (*(_BYTE *)v27 & 1) != 0 )
              v16 = winrt::impl::create_hstring_on_heap(
                      *(winrt::impl **)(v27 + 16),
                      (winrt::impl *)*(unsigned int *)(v27 + 4),
                      v15);
            else
              _InterlockedIncrement((volatile signed __int32 *)(v27 + 24));
          }
          winrt::handle_type<winrt::impl::hstring_traits>::attach(&v22, v16);
          v28[0] = v22;
          StringValue = (__int64 *)winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)v29);
          winrt::Windows::Data::Json::JsonValue::operator=(&v34, StringValue);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v29);
          winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"dohTemplate");
          v18 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                  &v21,
                  v28,
                  &v34);
          NumberValue = (__int64 *)winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v18);
          winrt::Windows::Data::Json::JsonValue::operator=(&v34, NumberValue);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v30);
          winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"encryptedDnsProtocols");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v21,
            v28,
            &v34);
          BooleanValue = (__int64 *)winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v31);
          winrt::Windows::Data::Json::JsonValue::operator=(&v34, BooleanValue);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)v31);
          winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"isWellKnownDoh");
          winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
            &v21,
            v28,
            &v34);
          if ( v21.lpVtbl )
          {
            v25 = 0;
            (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, __int64 *))v21.lpVtbl->QueryInterface)(
              v21.lpVtbl,
              winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
              &v25);
            v24 = v25;
          }
          else
          {
            v24 = 0;
          }
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
            &v23,
            &v24);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v24);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v34);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v22);
          winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v21);
          FreeDnsServer((HSTRING *)&v26);
        }
        v35 = 0;
        if ( v23.lpVtbl )
          (*(void (__fastcall **)(struct IUnknownVtbl *, __int64 *, __int64 *))v23.lpVtbl->QueryInterface)(
            v23.lpVtbl,
            winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
            &v35);
        winrt::param::hstring::hstring((winrt::param::hstring *)v28, L"dnsServers");
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          a2,
          v28,
          &v35);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v35);
        winrt::Windows::Data::Json::IJsonObject::~IJsonObject((winrt::Windows::Data::Json::IJsonObject *)&v23);
      }
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(v35) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x329,
                       (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                       v7);
      return (unsigned int)v35;
    }
LABEL_27:
    ;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)Size,
      (int)v21.lpVtbl);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18001281c  mov     rax, rsp
0x18001281f  mov     [rax+10h], rbx
0x180012823  mov     [rax+18h], r8
0x180012827  mov     [rax+8], rcx
0x18001282b  push    rdi
0x18001282c  push    r14
0x18001282e  push    r15
0x180012830  sub     rsp, 0C0h
0x180012837  mov     r14, r9
0x18001283a  mov     r15, rdx
0x18001283d  mov     dword ptr [rax+18h], 0
0x180012844  lea     rdx, [rax+18h]
0x180012848  mov     rcx, r9
0x18001284b  call    ?get_Size@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::get_Size(uint *)
0x180012850  mov     ebx, eax
0x180012852  test    eax, eax
0x180012854  jns     short loc_180012879
0x180012856  mov     rcx, [rsp+0D8h]; this
0x18001285e  mov     r9d, eax; char *
0x180012861  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012868  mov     edx, 306h; void *
0x18001286d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012872  mov     eax, ebx
0x180012874  jmp     loc_180012BE7
0x180012879  cmp     dword ptr [rsp+0D8h+arg_10], 0
0x180012881  jbe     loc_180012BDC
0x180012887  lea     rcx, [rsp+0D8h+var_A8]; this
0x18001288c  call    ??0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonArray::JsonArray(void)
0x180012891  nop
0x180012892  xor     edi, edi
0x180012894  cmp     edi, dword ptr [rsp+0D8h+arg_10]
0x18001289b  jnb     loc_180012B5D
0x1800128a1  xorps   xmm0, xmm0
0x1800128a4  xor     eax, eax
0x1800128a6  movups  [rsp+0D8h+var_90], xmm0
0x1800128ab  mov     [rsp+0D8h+var_80], rax
0x1800128b0  lea     r8, [rsp+0D8h+var_90]
0x1800128b5  mov     edx, edi
0x1800128b7  mov     rcx, r14
0x1800128ba  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x1800128bf  mov     ebx, eax
0x1800128c1  test    eax, eax
0x1800128c3  jns     short loc_1800128FE
0x1800128c5  mov     rcx, [rsp+0D8h]; this
0x1800128cd  mov     r9d, eax; char *
0x1800128d0  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800128d7  mov     edx, 30Eh; void *
0x1800128dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128e1  nop
0x1800128e2  lea     rcx, [rsp+0D8h+var_90]; struct Windows::Networking::UX::DnsServer *
0x1800128e7  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x1800128ec  nop
0x1800128ed  lea     rcx, [rsp+0D8h+var_A8]; this
0x1800128f2  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x1800128f7  mov     eax, ebx
0x1800128f9  jmp     loc_180012BE7
0x1800128fe  lea     rcx, [rsp+0D8h+var_B8]; this
0x180012903  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x180012908  nop
0x180012909  mov     [rsp+0D8h+var_B0], 0
0x180012912  mov     rax, qword ptr [rsp+0D8h+var_90+8]
0x180012917  test    rax, rax
0x18001291a  jz      short loc_180012933
0x18001291c  test    byte ptr [rax], 1
0x18001291f  jnz     short loc_180012927
0x180012921  lock inc dword ptr [rax+18h]
0x180012925  jmp     short loc_180012933
0x180012927  mov     edx, [rax+4]; winrt::impl *
0x18001292a  mov     rcx, [rax+10h]; this
0x18001292e  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180012933  mov     rdx, rax
0x180012936  lea     rcx, [rsp+0D8h+var_B0]
0x18001293b  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180012940  mov     rax, [rsp+0D8h+var_B0]
0x180012945  mov     [rsp+0D8h+var_40], rax
0x18001294d  lea     rdx, [rsp+0D8h+var_40]
0x180012955  lea     rcx, [rsp+0D8h+arg_0]; struct winrt::param::hstring *
0x18001295d  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x180012962  nop
0x180012963  lea     rdx, aAddress; "address"
0x18001296a  lea     rcx, [rsp+0D8h+var_78]; this
0x18001296f  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180012974  lea     r8, [rsp+0D8h+arg_0]
0x18001297c  lea     rdx, [rsp+0D8h+var_78]
0x180012981  lea     rcx, [rsp+0D8h+var_B8]
0x180012986  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001298b  mov     rax, [rsp+0D8h+var_80]
0x180012990  test    rax, rax
0x180012993  jz      short loc_1800129AC
0x180012995  test    byte ptr [rax], 1
0x180012998  jnz     short loc_1800129A0
0x18001299a  lock inc dword ptr [rax+18h]
0x18001299e  jmp     short loc_1800129AC
0x1800129a0  mov     edx, [rax+4]; winrt::impl *
0x1800129a3  mov     rcx, [rax+10h]; this
0x1800129a7  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x1800129ac  mov     rdx, rax
0x1800129af  lea     rcx, [rsp+0D8h+var_B0]
0x1800129b4  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800129b9  mov     rax, [rsp+0D8h+var_B0]
0x1800129be  mov     [rsp+0D8h+var_78], rax
0x1800129c3  lea     rdx, [rsp+0D8h+var_78]
0x1800129c8  lea     rcx, [rsp+0D8h+var_58]; struct winrt::param::hstring *
0x1800129d0  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800129d5  mov     rdx, rax
0x1800129d8  lea     rcx, [rsp+0D8h+arg_0]
0x1800129e0  call    ??4JsonValue@Json@Data@Windows@winrt@@QEAAAEAU01234@$$QEAU01234@@Z; winrt::Windows::Data::Json::JsonValue::operator=(winrt::Windows::Data::Json::JsonValue &&)
0x1800129e5  lea     rcx, [rsp+0D8h+var_58]; this
0x1800129ed  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x1800129f2  lea     rdx, aDohtemplate; "dohTemplate"
0x1800129f9  lea     rcx, [rsp+0D8h+var_78]; this
0x1800129fe  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180012a03  lea     r8, [rsp+0D8h+arg_0]
0x180012a0b  lea     rdx, [rsp+0D8h+var_78]
0x180012a10  lea     rcx, [rsp+0D8h+var_B8]
0x180012a15  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180012a1a  mov     eax, dword ptr [rsp+0D8h+var_90+4]
0x180012a1e  xorps   xmm1, xmm1
0x180012a21  cvtsi2sd xmm1, rax
0x180012a26  lea     rcx, [rsp+0D8h+var_50]
0x180012a2e  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x180012a33  mov     rdx, rax
0x180012a36  lea     rcx, [rsp+0D8h+arg_0]
0x180012a3e  call    ??4JsonValue@Json@Data@Windows@winrt@@QEAAAEAU01234@$$QEAU01234@@Z; winrt::Windows::Data::Json::JsonValue::operator=(winrt::Windows::Data::Json::JsonValue &&)
0x180012a43  lea     rcx, [rsp+0D8h+var_50]; this
0x180012a4b  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180012a50  lea     rdx, aEncrypteddnspr; "encryptedDnsProtocols"
0x180012a57  lea     rcx, [rsp+0D8h+var_78]; this
0x180012a5c  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180012a61  lea     r8, [rsp+0D8h+arg_0]
0x180012a69  lea     rdx, [rsp+0D8h+var_78]
0x180012a6e  lea     rcx, [rsp+0D8h+var_B8]
0x180012a73  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180012a78  cmp     byte ptr [rsp+0D8h+var_90], 0
0x180012a7d  setnz   dl
0x180012a80  lea     rcx, [rsp+0D8h+var_48]; bool
0x180012a88  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180012a8d  mov     rdx, rax
0x180012a90  lea     rcx, [rsp+0D8h+arg_0]
0x180012a98  call    ??4JsonValue@Json@Data@Windows@winrt@@QEAAAEAU01234@$$QEAU01234@@Z; winrt::Windows::Data::Json::JsonValue::operator=(winrt::Windows::Data::Json::JsonValue &&)
0x180012a9d  lea     rcx, [rsp+0D8h+var_48]; this
0x180012aa5  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180012aaa  lea     rdx, aIswellknowndoh; "isWellKnownDoh"
0x180012ab1  lea     rcx, [rsp+0D8h+var_78]; this
0x180012ab6  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180012abb  lea     r8, [rsp+0D8h+arg_0]
0x180012ac3  lea     rdx, [rsp+0D8h+var_78]
0x180012ac8  lea     rcx, [rsp+0D8h+var_B8]
0x180012acd  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180012ad2  mov     rcx, [rsp+0D8h+var_B8]
0x180012ad7  test    rcx, rcx
0x180012ada  jnz     short loc_180012AE3
0x180012adc  mov     [rsp+0D8h+var_A0], rcx
0x180012ae1  jmp     short loc_180012B0D
0x180012ae3  mov     [rsp+0D8h+var_98], 0
0x180012aec  mov     rax, [rcx]
0x180012aef  lea     r8, [rsp+0D8h+var_98]
0x180012af4  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180012afb  mov     rax, [rax]
0x180012afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b03  mov     rax, [rsp+0D8h+var_98]
0x180012b08  mov     [rsp+0D8h+var_A0], rax
0x180012b0d  lea     rdx, [rsp+0D8h+var_A0]
0x180012b12  lea     rcx, [rsp+0D8h+var_A8]
0x180012b17  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(winrt::Windows::Data::Json::IJsonValue const &)
0x180012b1c  nop
0x180012b1d  lea     rcx, [rsp+0D8h+var_A0]; this
0x180012b22  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180012b27  nop
0x180012b28  lea     rcx, [rsp+0D8h+arg_0]; this
0x180012b30  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180012b35  nop
0x180012b36  lea     rcx, [rsp+0D8h+var_B0]
0x180012b3b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180012b40  nop
0x180012b41  lea     rcx, [rsp+0D8h+var_B8]; this
0x180012b46  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180012b4b  nop
0x180012b4c  lea     rcx, [rsp+0D8h+var_90]; struct Windows::Networking::UX::DnsServer *
0x180012b51  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180012b56  inc     edi
0x180012b58  jmp     loc_180012894
0x180012b5d  mov     rcx, [rsp+0D8h+var_A8]
0x180012b62  mov     [rsp+0D8h+arg_10], 0
0x180012b6e  test    rcx, rcx
0x180012b71  jz      short loc_180012B9D
0x180012b73  mov     rax, [rcx]
0x180012b76  lea     r8, [rsp+0D8h+arg_10]
0x180012b7e  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180012b85  mov     rax, [rax]
0x180012b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b8d  mov     rax, [rsp+0D8h+arg_10]
0x180012b95  mov     [rsp+0D8h+arg_10], rax
0x180012b9d  lea     rdx, aDnsservers; "dnsServers"
0x180012ba4  lea     rcx, [rsp+0D8h+var_78]; this
0x180012ba9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180012bae  lea     r8, [rsp+0D8h+arg_10]
0x180012bb6  lea     rdx, [rsp+0D8h+var_78]
0x180012bbb  mov     rcx, r15
0x180012bbe  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180012bc3  nop
0x180012bc4  lea     rcx, [rsp+0D8h+arg_10]; this
0x180012bcc  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180012bd1  nop
0x180012bd2  lea     rcx, [rsp+0D8h+var_A8]; this
0x180012bd7  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180012bdc  xor     eax, eax
0x180012bde  jmp     short loc_180012BE7
0x180012be0  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x180012be7  mov     rbx, [rsp+0D8h+arg_8]
0x180012bef  add     rsp, 0C0h
0x180012bf6  pop     r15
0x180012bf8  pop     r14
0x180012bfa  pop     rdi
0x180012bfb  retn
```
