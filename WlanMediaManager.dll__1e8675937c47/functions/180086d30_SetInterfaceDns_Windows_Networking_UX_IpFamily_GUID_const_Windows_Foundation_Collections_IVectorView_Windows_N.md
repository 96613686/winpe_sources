# SetInterfaceDns(Windows::Networking::UX::IpFamily,_GUID const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)

- ea: `0x180086d30`
- end: `0x1800871ea`
- name: `?SetInterfaceDns@@YAXW4IpFamily@UX@Networking@Windows@@AEBU_GUID@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@4@@Z`
- size: `1210`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e920`

## callees

- `0x180003ed0`
- `0x1800043ec`
- `0x180004a70`
- `0x1800061a4`
- `0x18000b5e0`
- `0x18000b86c`
- `0x18001be60`
- `0x1800236f0`
- `0x18002a40c`
- `0x18003a158`
- `0x18004ca20`
- `0x180057620`
- `0x180081e5c`
- `0x1800865c4`
- `0x1800865fc`
- `0x180086634`
- `0x18008665c`
- `0x1800867ac`
- `0x1800869ac`
- `0x180086a24`
- `0x180086d30`
- `0x18008e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008708e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008708e`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x180087112`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x180087112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180086e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180086ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180086e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180086ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008703c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008703c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086e63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008701b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800871af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086e63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008701b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800871af`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SetInterfaceDns(int a1, _OWORD *a2, __int64 a3)
{
  int v6; // eax
  ULONG64 v7; // rax
  unsigned __int64 v8; // rbx
  void *v9; // rsi
  int v10; // r14d
  unsigned int i; // edi
  int v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // eax
  _OWORD *v15; // rax
  _QWORD *v16; // rbx
  __int64 v17; // rax
  char v18; // cl
  PCWSTR StringRawBuffer; // rax
  __int64 v20; // rcx
  PCWSTR v21; // rdi
  unsigned __int64 v22; // rbx
  void *v23; // r15
  unsigned int v24; // eax
  unsigned int v26; // [rsp+20h] [rbp-E0h] BYREF
  UINT32 v27; // [rsp+24h] [rbp-DCh] BYREF
  HSTRING string1; // [rsp+28h] [rbp-D8h] BYREF
  UINT32 length[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *v30; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v33; // [rsp+60h] [rbp-A0h]
  __int128 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  void *v38; // [rsp+98h] [rbp-68h] BYREF
  DNS_INTERFACE_SETTINGS Settings; // [rsp+A0h] [rbp-60h] BYREF
  int v40; // [rsp+F0h] [rbp-10h]
  void *v41; // [rsp+F8h] [rbp-8h]
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  HSTRING string2; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a3 + 56LL))(a3, &v26);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)(unsigned int)v6,
      v26);
  memset_0(&Settings, 0, 0x70u);
  Settings.Version = 3;
  v7 = 4098;
  if ( a1 == 6 )
    v7 = 4099;
  Settings.Flags = v7;
  v8 = saturated_mul(v26, 0x18u);
  v9 = operator new[](v8);
  memset_0(v9, 0, v8);
  v38 = v9;
  string1 = 0;
  v10 = 0;
  std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(&v36);
  std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(&v34);
  for ( i = 0; i < v26; ++i )
  {
    string[0] = 0;
    *(_OWORD *)v32 = 0;
    v33 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a3 + 48LL))(a3, i, v32);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
        (const char *)(unsigned int)v12,
        v26);
    if ( i )
    {
      WindowsDeleteString(string[0]);
      string[0] = 0;
      string2 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L",", 2u, 1u);
      v13 = WindowsConcatString(string1, string2, string);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
          (const char *)(unsigned int)v13,
          v26);
    }
    WindowsDeleteString(string1);
    string1 = 0;
    v14 = WindowsConcatString(string[0], v32[1], &string1);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
        (const char *)(unsigned int)v14,
        v26);
    if ( HIDWORD(v32[0]) )
    {
      v15 = operator new(0x10u);
      *v15 = 0;
      *(_QWORD *)length = v15;
      if ( *((_QWORD *)&v36 + 1) == v37 )
        std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_reallocate<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(
          (__int64 *)&v36,
          *((__int64 *)&v36 + 1),
          (__int64 *)length);
      else
        std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(
          (__int64)&v36,
          (__int64 *)length);
      std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>::~unique_ptr<_DNS_DOH_SERVER_SETTINGS>(length);
      v16 = *(_QWORD **)(*((_QWORD *)&v36 + 1) - 8LL);
      v16[1] = 0;
      v17 = 0;
      v18 = BYTE4(v32[0]);
      if ( (BYTE4(v32[0]) & 1) != 0 )
      {
        v17 = 17;
        v16[1] = 17;
        v18 = BYTE4(v32[0]);
      }
      if ( (v18 & 2) != 0 )
      {
        v17 |= 2uLL;
        v16[1] = v17;
        v18 = BYTE4(v32[0]);
      }
      if ( (v18 & 4) != 0 )
        v16[1] = v17 | 4;
      *v16 = &qword_18009D0D0;
      if ( (BYTE4(v32[0]) & 1) != 0 || (BYTE4(v32[0]) & 2) != 0 )
      {
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v33, length);
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v30,
          (__int64)StringRawBuffer);
        if ( *((_QWORD *)&v34 + 1) == v35 )
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (__int64 *)&v34,
            *((__int64 *)&v34 + 1),
            (__int64 *)&v30);
        else
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (__int64)&v34,
            (__int64 *)&v30);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
        *v16 = *(_QWORD *)(*((_QWORD *)&v34 + 1) - 8LL);
      }
      v20 = 3LL * v10;
      *((_DWORD *)v9 + 2 * v20) = 1;
      *((_DWORD *)v9 + 2 * v20 + 1) = i;
      *((_DWORD *)v9 + 2 * v20 + 2) = 1;
      *((_QWORD *)v9 + v20 + 2) = v16;
      ++v10;
    }
    FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v32);
    WindowsDeleteString(string[0]);
  }
  v27 = 0;
  v21 = WindowsGetStringRawBuffer(string1, &v27);
  v22 = saturated_mul(v27 + 1, 2u);
  v23 = operator new[](v22);
  memset_0(v23, 0, v22);
  v30 = v23;
  if ( (unsigned int)_o_wcscpy_s(v23, v27 + 1, v21) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)0x80070057LL,
      v26);
  v40 = v10;
  Settings.NameServer = (PWSTR)v23;
  v41 = v9;
  *(_OWORD *)string = *a2;
  v24 = SetInterfaceDnsSettings((GUID *)string, &Settings);
  if ( v24 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)v24,
      v26);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v30);
  if ( (_QWORD)v34 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
      v34,
      *((__int64 *)&v34 + 1));
    std::_Deallocate<16>((void *)v34, (struct std::nothrow_t *)((v35 - v34) & 0xFFFFFFFFFFFFFFF8uLL));
    v34 = 0;
    v35 = 0;
  }
  if ( (_QWORD)v36 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>>(v36, *((__int64 *)&v36 + 1));
    std::_Deallocate<16>((void *)v36, (struct std::nothrow_t *)((v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL));
    v36 = 0;
    v37 = 0;
  }
  WindowsDeleteString(string1);
  string1 = 0;
  return std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v38);
}

```

## disassembly

```asm
0x180086d30  mov     [rsp-8+arg_0], rbx
0x180086d35  push    rbp
0x180086d36  push    rsi
0x180086d37  push    rdi
0x180086d38  push    r12
0x180086d3a  push    r13
0x180086d3c  push    r14
0x180086d3e  push    r15
0x180086d40  lea     rbp, [rsp-40h]
0x180086d45  sub     rsp, 140h
0x180086d4c  mov     rax, cs:__security_cookie
0x180086d53  xor     rax, rsp
0x180086d56  mov     [rbp+70h+var_40], rax
0x180086d5a  mov     r15, r8
0x180086d5d  mov     r12, rdx
0x180086d60  mov     ebx, ecx
0x180086d62  xor     r13d, r13d
0x180086d65  mov     [rsp+170h+var_150], r13d; unsigned int
0x180086d6a  mov     rax, [r8]
0x180086d6d  lea     rdx, [rsp+170h+var_150]
0x180086d72  mov     rcx, r8
0x180086d75  mov     rax, [rax+38h]
0x180086d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d7e  mov     rcx, [rbp+78h]; this
0x180086d82  test    eax, eax
0x180086d84  jns     short loc_180086D9B
0x180086d86  mov     r9d, eax; char *
0x180086d89  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180086d90  mov     edx, 101h; void *
0x180086d95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180086d9b  xor     edx, edx; Val
0x180086d9d  lea     r8d, [rdx+70h]; Size
0x180086da1  lea     rcx, [rbp+70h+Settings]; void *
0x180086da5  call    memset_0
0x180086daa  mov     [rbp+70h+Settings.Version], 3
0x180086db1  mov     eax, 1002h
0x180086db6  lea     ecx, [rax+1]
0x180086db9  cmp     ebx, 6
0x180086dbc  cmovz   eax, ecx
0x180086dbf  mov     [rbp+70h+Settings.Flags], rax
0x180086dc3  mov     ecx, [rsp+170h+var_150]
0x180086dc7  mov     eax, 18h
0x180086dcc  mul     rcx
0x180086dcf  mov     rbx, rax
0x180086dd2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180086dd9  cmovb   rbx, rax
0x180086ddd  mov     rcx, rbx; unsigned __int64
0x180086de0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180086de5  mov     rsi, rax
0x180086de8  mov     r8, rbx; Size
0x180086deb  xor     edx, edx; Val
0x180086ded  mov     rcx, rax; void *
0x180086df0  call    memset_0
0x180086df5  mov     [rbp+70h+var_D8], rsi
0x180086df9  mov     [rsp+170h+string1], r13
0x180086dfe  mov     r14d, r13d
0x180086e01  lea     rcx, [rbp+70h+var_F0]
0x180086e05  call    ??0?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(void)
0x180086e0a  nop
0x180086e0b  lea     rcx, [rsp+170h+var_108]
0x180086e10  call    ??0?$vector@PEAVProfile@Internal@UX@Networking@Windows@@V?$allocator@PEAVProfile@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Networking::UX::Internal::Profile *>::vector<Windows::Networking::UX::Internal::Profile *>(void)
0x180086e15  nop
0x180086e16  mov     edi, r13d
0x180086e19  cmp     [rsp+170h+var_150], r13d
0x180086e1e  jbe     loc_18008702D
0x180086e24  mov     [rsp+170h+string], r13
0x180086e29  xorps   xmm0, xmm0
0x180086e2c  xor     eax, eax
0x180086e2e  movups  xmmword ptr [rsp+170h+var_120], xmm0
0x180086e33  mov     [rsp+170h+var_110], rax
0x180086e38  mov     rax, [r15]
0x180086e3b  lea     r8, [rsp+170h+var_120]
0x180086e40  mov     edx, edi
0x180086e42  mov     rcx, r15
0x180086e45  mov     rax, [rax+30h]
0x180086e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086e4e  mov     rcx, [rbp+78h]; this
0x180086e52  test    eax, eax
0x180086e54  js      loc_1800870DD
0x180086e5a  test    edi, edi
0x180086e5c  jz      short loc_180086EAD
0x180086e5e  mov     rcx, [rsp+170h+string]; string
0x180086e63  call    cs:__imp_WindowsDeleteString
0x180086e69  mov     [rsp+170h+string], r13
0x180086e6e  mov     [rbp+70h+string2], r13
0x180086e72  mov     r9d, 1; unsigned int
0x180086e78  lea     r8d, [r9+1]; unsigned int
0x180086e7c  lea     rdx, sourceString; ","
0x180086e83  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x180086e87  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180086e8c  nop
0x180086e8d  lea     r8, [rsp+170h+string]; newString
0x180086e92  mov     rdx, [rbp+70h+string2]; string2
0x180086e96  mov     rcx, [rsp+170h+string1]; string1
0x180086e9b  call    cs:__imp_WindowsConcatString
0x180086ea1  mov     rcx, [rbp+78h]; this
0x180086ea5  test    eax, eax
0x180086ea7  js      loc_1800870B3
0x180086ead  mov     rcx, [rsp+170h+string1]; string
0x180086eb2  call    cs:__imp_WindowsDeleteString
0x180086eb8  mov     [rsp+170h+string1], r13
0x180086ebd  lea     r8, [rsp+170h+string1]; newString
0x180086ec2  mov     rdx, [rsp+170h+var_120+8]; string2
0x180086ec7  mov     rcx, [rsp+170h+string]; string1
0x180086ecc  call    cs:__imp_WindowsConcatString
0x180086ed2  mov     rcx, [rbp+78h]; this
0x180086ed6  test    eax, eax
0x180086ed8  js      loc_1800870C8
0x180086ede  cmp     dword ptr [rsp+170h+var_120+4], r13d
0x180086ee3  jz      loc_18008700B
0x180086ee9  mov     ecx, 10h; Size
0x180086eee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180086ef3  xorps   xmm0, xmm0
0x180086ef6  movups  xmmword ptr [rax], xmm0
0x180086ef9  mov     qword ptr [rsp+170h+length], rax
0x180086efe  mov     rdx, qword ptr [rbp+70h+var_F0+8]
0x180086f02  lea     rcx, [rbp+70h+var_F0]
0x180086f06  cmp     rdx, [rbp+70h+var_E0]
0x180086f0a  jz      short loc_180086F18
0x180086f0c  lea     rdx, [rsp+170h+length]
0x180086f11  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@?$vector@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> &&)
0x180086f16  jmp     short loc_180086F23
0x180086f18  lea     r8, [rsp+170h+length]
0x180086f1d  call    ??$_Emplace_reallocate@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@?$vector@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_reallocate<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> * const,std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> &&)
0x180086f22  nop
0x180086f23  lea     rcx, [rsp+170h+length]
0x180086f28  call    ??1?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>::~unique_ptr<_DNS_DOH_SERVER_SETTINGS>(void)
0x180086f2d  mov     rax, qword ptr [rbp+70h+var_F0+8]
0x180086f31  mov     rbx, [rax-8]
0x180086f35  mov     [rbx+8], r13
0x180086f39  mov     rax, r13
0x180086f3c  mov     ecx, dword ptr [rsp+170h+var_120+4]
0x180086f40  test    cl, 1
0x180086f43  jz      short loc_180086F52
0x180086f45  mov     eax, 11h
0x180086f4a  mov     [rbx+8], rax
0x180086f4e  mov     ecx, dword ptr [rsp+170h+var_120+4]
0x180086f52  test    cl, 2
0x180086f55  jz      short loc_180086F63
0x180086f57  or      rax, 2
0x180086f5b  mov     [rbx+8], rax
0x180086f5f  mov     ecx, dword ptr [rsp+170h+var_120+4]
0x180086f63  test    cl, 4
0x180086f66  jz      short loc_180086F70
0x180086f68  or      rax, 4
0x180086f6c  mov     [rbx+8], rax
0x180086f70  lea     rax, qword_18009D0D0
0x180086f77  mov     [rbx], rax
0x180086f7a  test    byte ptr [rsp+170h+var_120+4], 1
0x180086f7f  jnz     short loc_180086F88
0x180086f81  test    byte ptr [rsp+170h+var_120+4], 2
0x180086f86  jz      short loc_180086FE9
0x180086f88  mov     [rsp+170h+length], r13d
0x180086f8d  lea     rdx, [rsp+170h+length]; length
0x180086f92  mov     rcx, [rsp+170h+var_110]; string
0x180086f97  call    cs:__imp_WindowsGetStringRawBuffer
0x180086f9d  mov     rdx, rax
0x180086fa0  lea     rcx, [rsp+170h+var_138]
0x180086fa5  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180086faa  nop
0x180086fab  mov     rdx, qword ptr [rsp+170h+var_108+8]
0x180086fb0  lea     rcx, [rsp+170h+var_108]
0x180086fb5  cmp     rdx, [rsp+170h+var_F8]
0x180086fba  jz      short loc_180086FC8
0x180086fbc  lea     rdx, [rsp+170h+var_138]
0x180086fc1  call    ??$_Emplace_back_with_unused_capacity@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180086fc6  jmp     short loc_180086FD3
0x180086fc8  lea     r8, [rsp+170h+var_138]
0x180086fcd  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180086fd2  nop
0x180086fd3  lea     rcx, [rsp+170h+var_138]
0x180086fd8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180086fdd  mov     rax, qword ptr [rsp+170h+var_108+8]
0x180086fe2  mov     rcx, [rax-8]
0x180086fe6  mov     [rbx], rcx
0x180086fe9  movsxd  rax, r14d
0x180086fec  lea     rcx, [rax+rax*2]
0x180086ff0  mov     dword ptr [rsi+rcx*8], 1
0x180086ff7  mov     [rsi+rcx*8+4], edi
0x180086ffb  mov     dword ptr [rsi+rcx*8+8], 1
0x180087003  mov     [rsi+rcx*8+10h], rbx
0x180087008  inc     r14d
0x18008700b  lea     rcx, [rsp+170h+var_120]; struct Windows::Networking::UX::DnsServer *
0x180087010  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180087015  nop
0x180087016  mov     rcx, [rsp+170h+string]; string
0x18008701b  call    cs:__imp_WindowsDeleteString
0x180087021  inc     edi
0x180087023  cmp     edi, [rsp+170h+var_150]
0x180087027  jb      loc_180086E24
0x18008702d  mov     [rsp+170h+var_14C], r13d
0x180087032  lea     rdx, [rsp+170h+var_14C]; length
0x180087037  mov     rcx, [rsp+170h+string1]; string
0x18008703c  call    cs:__imp_WindowsGetStringRawBuffer
0x180087042  mov     rdi, rax
0x180087045  mov     edx, [rsp+170h+var_14C]
0x180087049  inc     edx
0x18008704b  mov     eax, 2
0x180087050  mul     rdx
0x180087053  mov     rbx, rax
0x180087056  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18008705d  cmovb   rbx, rax
0x180087061  mov     rcx, rbx; unsigned __int64
0x180087064  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180087069  mov     r15, rax
0x18008706c  mov     r8, rbx; Size
0x18008706f  xor     edx, edx; Val
0x180087071  mov     rcx, rax; void *
0x180087074  call    memset_0
0x180087079  mov     [rsp+170h+var_138], r15
0x18008707e  mov     rbx, [rbp+78h]
0x180087082  mov     edx, [rsp+170h+var_14C]
0x180087086  inc     edx
0x180087088  mov     r8, rdi
0x18008708b  mov     rcx, r15
0x18008708e  call    cs:__imp__o_wcscpy_s
0x180087094  test    eax, eax
0x180087096  jz      short loc_1800870F2
0x180087098  mov     r9d, 80070057h; char *
0x18008709e  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800870a5  mov     edx, 152h; void *
0x1800870aa  mov     rcx, rbx; this
0x1800870ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800870b3  mov     r9d, eax; char *
0x1800870b6  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800870bd  mov     edx, 11Fh; void *
0x1800870c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800870c8  mov     r9d, eax; char *
0x1800870cb  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800870d2  mov     edx, 121h; void *
0x1800870d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800870dd  mov     r9d, eax; char *
0x1800870e0  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800870e7  mov     edx, 11Ch; void *
0x1800870ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800870f2  mov     [rbp+70h+var_80], r14d
0x1800870f6  mov     [rbp+70h+Settings.NameServer], r15
0x1800870fa  mov     [rbp+70h+var_78], rsi
0x1800870fe  movups  xmm0, xmmword ptr [r12]
0x180087103  movdqu  xmmword ptr [rsp+170h+string], xmm0
0x180087109  lea     rdx, [rbp+70h+Settings]; Settings
0x18008710d  lea     rcx, [rsp+170h+string]; Interface
0x180087112  call    cs:__imp_SetInterfaceDnsSettings
0x180087118  mov     rcx, [rbp+78h]; this
0x18008711c  test    eax, eax
0x18008711e  jz      short loc_180087135
0x180087120  mov     r9d, eax; char *
0x180087123  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18008712a  mov     edx, 15Ah; void *
0x18008712f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180087135  lea     rcx, [rsp+170h+var_138]
0x18008713a  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18008713f  nop
0x180087140  mov     rcx, qword ptr [rsp+170h+var_108]
0x180087145  test    rcx, rcx
0x180087148  jz      short loc_180087178
0x18008714a  mov     rdx, qword ptr [rsp+170h+var_108+8]
0x18008714f  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x180087154  mov     rcx, qword ptr [rsp+170h+var_108]
0x180087159  mov     rdx, [rsp+170h+var_F8]
0x18008715e  sub     rdx, rcx
0x180087161  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180087165  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008716a  xorps   xmm0, xmm0
0x18008716d  movdqu  [rsp+170h+var_108], xmm0
0x180087173  mov     [rsp+170h+var_F8], r13
0x180087178  mov     rcx, qword ptr [rbp+70h+var_F0]
0x18008717c  test    rcx, rcx
0x18008717f  jz      short loc_1800871AA
0x180087181  mov     rdx, qword ptr [rbp+70h+var_F0+8]
0x180087185  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> *,std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> * const,std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>> &)
0x18008718a  mov     rcx, qword ptr [rbp+70h+var_F0]
0x18008718e  mov     rdx, [rbp+70h+var_E0]
0x180087192  sub     rdx, rcx
0x180087195  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180087199  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008719e  xorps   xmm0, xmm0
0x1800871a1  movdqu  [rbp+70h+var_F0], xmm0
0x1800871a6  mov     [rbp+70h+var_E0], r13
0x1800871aa  mov     rcx, [rsp+170h+string1]; string
0x1800871af  call    cs:__imp_WindowsDeleteString
0x1800871b5  mov     [rsp+170h+string1], r13
0x1800871ba  lea     rcx, [rbp+70h+var_D8]
0x1800871be  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800871c3  mov     rcx, [rbp+70h+var_40]
0x1800871c7  xor     rcx, rsp; StackCookie
0x1800871ca  call    __security_check_cookie
0x1800871cf  mov     rbx, [rsp+170h+arg_0]
0x1800871d7  add     rsp, 140h
0x1800871de  pop     r15
0x1800871e0  pop     r14
0x1800871e2  pop     r13
0x1800871e4  pop     r12
0x1800871e6  pop     rdi
0x1800871e7  pop     rsi
0x1800871e8  pop     rbp
0x1800871e9  retn
```
