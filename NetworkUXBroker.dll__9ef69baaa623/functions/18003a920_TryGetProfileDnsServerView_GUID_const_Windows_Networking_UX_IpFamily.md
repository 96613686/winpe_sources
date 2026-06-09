# TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)

- ea: `0x18003a920`
- end: `0x18003ae4a`
- name: `?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z`
- size: `1322`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041e58`

## callees

- `0x180002520`
- `0x1800030a0`
- `0x18000955c`
- `0x180009588`
- `0x18000f054`
- `0x18000f0b0`
- `0x18001060c`
- `0x180013b8c`
- `0x180014df0`
- `0x180015eb0`
- `0x180016d54`
- `0x1800192f0`
- `0x18001a2d0`
- `0x18001a300`
- `0x180039d00`
- `0x180039d8c`
- `0x18003a920`
- `0x18003ae50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003aa92`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003ab59`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003aa92`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003ab59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003aacd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ac6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003acb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003aacd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003ac6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003acb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab72`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x18003aa0a`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x18003aa0a`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003aa1a`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003ad21`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003aa1a`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003ad21`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
wchar_t *__fastcall TryGetProfileDnsServerView(wchar_t *a1, GUID *a2, int a3)
{
  __int64 v6; // rdx
  void *v7; // r8
  __int64 v8; // r9
  wil::details::in1diag3 *v9; // rcx
  __int64 v10; // rdx
  ULONG64 v11; // rax
  unsigned int InterfaceDnsSettings; // eax
  __int64 v14; // rax
  wchar_t *v15; // r14
  __int64 v16; // rbx
  HRESULT v17; // eax
  HSTRING v18; // rcx
  __int64 v19; // r9
  int v20; // eax
  unsigned int v21; // ebx
  __m128i si128; // xmm6
  unsigned int v23; // r15d
  __int64 v24; // r14
  int v25; // eax
  int v26; // eax
  int WellKnownDnsServerTemplate; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  const WCHAR *v30; // rax
  HRESULT v31; // eax
  const WCHAR *v32; // rcx
  __int64 v33; // rdx
  HRESULT v34; // eax
  int v35; // eax
  __int64 v36; // rbx
  int View; // eax
  unsigned int v38[2]; // [rsp+20h] [rbp-128h] BYREF
  HSTRING v39[2]; // [rsp+28h] [rbp-120h] BYREF
  HSTRING v40; // [rsp+38h] [rbp-110h] BYREF
  HSTRING string; // [rsp+40h] [rbp-108h] BYREF
  int v42; // [rsp+48h] [rbp-100h]
  wchar_t *Context[2]; // [rsp+50h] [rbp-F8h] BYREF
  DNS_INTERFACE_SETTINGS Settings; // [rsp+60h] [rbp-E8h] BYREF
  unsigned int v45; // [rsp+C0h] [rbp-88h]
  __int64 v46; // [rsp+C8h] [rbp-80h]
  __int128 v47; // [rsp+D0h] [rbp-78h] BYREF
  UINT32 length[4]; // [rsp+E0h] [rbp-68h]
  GUID Interface; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  Context[1] = a1;
  *(_QWORD *)a1 = 0;
  v42 = 1;
  *(_QWORD *)v38 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v38);
  *(_QWORD *)v38 = 0;
  Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(
    &Interface,
    v6,
    v7);
  if ( *(_QWORD *)&Interface.Data1 )
  {
    v8 = 0;
    *(_QWORD *)v38 = *(_QWORD *)&Interface.Data1;
  }
  else
  {
    v8 = 2147942414LL;
  }
  v9 = retaddr;
  if ( (int)v8 < 0 )
  {
    v10 = 171;
LABEL_40:
    wil::details::in1diag3::_Log_Hr(
      v9,
      (void *)v10,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)v8,
      v38[0]);
    goto LABEL_41;
  }
  memset_0(&Settings, 0, 0x70u);
  Settings.Version = 3;
  v11 = 8704;
  if ( a3 == 6 )
    v11 = 8705;
  Settings.Flags = v11;
  Interface = *a2;
  InterfaceDnsSettings = GetInterfaceDnsSettings(&Interface, &Settings);
  if ( InterfaceDnsSettings == 2 )
  {
    FreeInterfaceDnsSettings(&Settings);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v38);
    return a1;
  }
  if ( InterfaceDnsSettings )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)InterfaceDnsSettings,
      v38[0]);
  if ( Settings.ProfileNameServer )
  {
    v14 = -1;
    do
      ++v14;
    while ( Settings.ProfileNameServer[v14] );
    if ( v14 )
    {
      *(_QWORD *)&Interface.Data1 = 0x3B002C0020LL;
      Context[0] = 0;
      v15 = wcstok_s(Settings.ProfileNameServer, (const wchar_t *)&Interface, Context);
      while ( v15 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v17 = WindowsCreateString(v15, v16, &string);
        if ( v17 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xCC,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v17,
            v38[0]);
        v39[0] = 0;
        v40 = 0;
        v18 = string;
        string = 0;
        v39[1] = v18;
        LOBYTE(v39[0]) = DnsServerIsWellKnownDoh(v18);
        HIDWORD(v39[0]) = 0;
        v47 = *(_OWORD *)v39;
        *(_QWORD *)length = 0;
        LOBYTE(v19) = 1;
        v20 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
                *(_QWORD *)v38,
                0,
                &v47,
                v19);
        if ( v20 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xD2,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v20,
            v38[0]);
        v15 = wcstok_s(0, (const wchar_t *)&Interface, Context);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v39);
        WindowsDeleteString(string);
        string = 0;
      }
      v21 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( v21 < v45 )
      {
        v23 = *(_DWORD *)(v46 + 24LL * v21 + 4);
        v24 = *(_QWORD *)(v46 + 24LL * v21 + 16);
        *(_OWORD *)v39 = 0;
        v40 = 0;
        v25 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                *(_QWORD *)v38,
                v23,
                v39);
        if ( v25 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v25,
            v38[0]);
        v26 = HIDWORD(v39[0]);
        if ( (*(_BYTE *)(v24 + 8) & 4) != 0 )
        {
          v26 = HIDWORD(v39[0]) | 4;
          HIDWORD(v39[0]) |= 4u;
        }
        if ( (*(_BYTE *)(v24 + 8) & 1) != 0 )
        {
          v26 |= 1u;
          HIDWORD(v39[0]) = v26;
          if ( LOBYTE(v39[0]) )
          {
            v47 = 0;
            *(__m128i *)length = si128;
            LOWORD(v47) = 0;
            WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v39[1]);
            if ( WellKnownDnsServerTemplate < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0xE8,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)WellKnownDnsServerTemplate,
                v38[0]);
            v30 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v47, v28, v29);
            v31 = WindowsCreateString(v30, length[0], &v40);
            if ( v31 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0xE9,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v31,
                v38[0]);
            std::wstring::_Tidy_deallocate(&v47);
            v26 = HIDWORD(v39[0]);
          }
        }
        if ( (*(_BYTE *)(v24 + 8) & 2) != 0 )
        {
          HIDWORD(v39[0]) = v26 | 2;
          v32 = *(const WCHAR **)v24;
          v33 = -1;
          do
            ++v33;
          while ( v32[v33] );
          v34 = WindowsCreateString(v32, v33, &v40);
          if ( v34 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0xF1,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v34,
              v38[0]);
        }
        v47 = *(_OWORD *)v39;
        *(_QWORD *)length = v40;
        v35 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(
                *(_QWORD *)v38,
                v23,
                &v47);
        if ( v35 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v35,
            v38[0]);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v39);
        ++v21;
      }
    }
  }
  FreeInterfaceDnsSettings(&Settings);
  v36 = *(_QWORD *)v38;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  View = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(
           v36,
           a1);
  v9 = retaddr;
  if ( View < 0 )
  {
    v8 = (unsigned int)View;
    v10 = 250;
    goto LABEL_40;
  }
LABEL_41:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v38);
  return a1;
}

```

## disassembly

```asm
0x18003a920  mov     rax, rsp
0x18003a923  mov     [rax+18h], rbx
0x18003a927  push    rsi
0x18003a928  push    rdi
0x18003a929  push    r13
0x18003a92b  push    r14
0x18003a92d  push    r15
0x18003a92f  sub     rsp, 120h
0x18003a936  movaps  xmmword ptr [rax-38h], xmm6
0x18003a93a  mov     rax, cs:__security_cookie
0x18003a941  xor     rax, rsp
0x18003a944  mov     [rsp+148h+var_48], rax
0x18003a94c  mov     ebx, r8d
0x18003a94f  mov     r14, rdx
0x18003a952  mov     rsi, rcx
0x18003a955  mov     [rsp+148h+var_F0], rcx
0x18003a95a  mov     [rsp+148h+var_100], 1
0x18003a962  xor     edi, edi
0x18003a964  mov     [rcx], rdi
0x18003a967  mov     [rsp+148h+var_100], 1
0x18003a96f  mov     qword ptr [rsp+148h+var_128], rdi
0x18003a974  lea     rcx, [rsp+148h+var_128]
0x18003a979  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003a97e  mov     qword ptr [rsp+148h+var_128], rdi; int
0x18003a983  lea     rcx, [rsp+148h+Interface]
0x18003a98b  call    ??$Make@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEBUDnsServerEqualityPredicate@2UX@Networking@5@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@@12@AEBUDnsServerEqualityPredicate@Internal@UX@Networking@Windows@@$$QEAUpermission@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@5Collections@Foundation@8@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission &&)
0x18003a990  mov     rax, qword ptr [rsp+148h+Interface.Data1]
0x18003a998  test    rax, rax
0x18003a99b  jz      short loc_18003A9A7
0x18003a99d  mov     r9d, edi
0x18003a9a0  mov     qword ptr [rsp+148h+var_128], rax
0x18003a9a5  jmp     short loc_18003A9AD
0x18003a9a7  mov     r9d, 8007000Eh
0x18003a9ad  mov     rcx, [rsp+148h]
0x18003a9b5  test    r9d, r9d
0x18003a9b8  jns     short loc_18003A9C4
0x18003a9ba  mov     edx, 0ABh
0x18003a9bf  jmp     loc_18003AD5B
0x18003a9c4  xor     edx, edx; Val
0x18003a9c6  lea     r8d, [rdx+70h]; Size
0x18003a9ca  lea     rcx, [rsp+148h+Settings]; void *
0x18003a9cf  call    memset_0
0x18003a9d4  nop
0x18003a9d5  mov     [rsp+148h+Settings.Version], 3
0x18003a9dd  mov     eax, 2200h
0x18003a9e2  lea     ecx, [rax+1]
0x18003a9e5  cmp     ebx, 6
0x18003a9e8  cmovz   eax, ecx
0x18003a9eb  mov     [rsp+148h+Settings.Flags], rax
0x18003a9f0  movups  xmm0, xmmword ptr [r14]
0x18003a9f4  movdqu  xmmword ptr [rsp+148h+Interface.Data1], xmm0
0x18003a9fd  lea     rdx, [rsp+148h+Settings]; Settings
0x18003aa02  lea     rcx, [rsp+148h+Interface]; Interface
0x18003aa0a  call    cs:__imp_GetInterfaceDnsSettings
0x18003aa10  cmp     eax, 2
0x18003aa13  jnz     short loc_18003AA34
0x18003aa15  lea     rcx, [rsp+148h+Settings]; Settings
0x18003aa1a  call    cs:__imp_FreeInterfaceDnsSettings
0x18003aa20  nop
0x18003aa21  lea     rcx, [rsp+148h+var_128]
0x18003aa26  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003aa2b  nop
0x18003aa2c  mov     rax, rsi
0x18003aa2f  jmp     loc_18003AD76
0x18003aa34  mov     rcx, [rsp+148h]; this
0x18003aa3c  test    eax, eax
0x18003aa3e  jnz     loc_18003ADA3
0x18003aa44  mov     rcx, [rsp+148h+Settings.ProfileNameServer]; String
0x18003aa4c  test    rcx, rcx
0x18003aa4f  jz      loc_18003AD1C
0x18003aa55  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003aa59  mov     rax, r13
0x18003aa5c  inc     rax
0x18003aa5f  cmp     [rcx+rax*2], di
0x18003aa63  jnz     short loc_18003AA5C
0x18003aa65  test    rax, rax
0x18003aa68  jz      loc_18003AD1C
0x18003aa6e  mov     rax, 3B002C0020h
0x18003aa78  mov     qword ptr [rsp+148h+Interface.Data1], rax
0x18003aa80  mov     [rsp+148h+Context], rdi
0x18003aa85  lea     r8, [rsp+148h+Context]; Context
0x18003aa8a  lea     rdx, [rsp+148h+Interface]; Delimiter
0x18003aa92  call    cs:__imp_wcstok_s
0x18003aa98  mov     r14, rax
0x18003aa9b  test    r14, r14
0x18003aa9e  jz      loc_18003AB82
0x18003aaa4  mov     rbx, r13
0x18003aaa7  inc     rbx
0x18003aaaa  cmp     [r14+rbx*2], di
0x18003aaaf  jnz     short loc_18003AAA7
0x18003aab1  mov     [rsp+148h+string], rdi
0x18003aab6  xor     ecx, ecx; string
0x18003aab8  call    cs:__imp_WindowsDeleteString
0x18003aabe  mov     [rsp+148h+string], rdi
0x18003aac3  lea     r8, [rsp+148h+string]; string
0x18003aac8  mov     edx, ebx; length
0x18003aaca  mov     rcx, r14; sourceString
0x18003aacd  call    cs:__imp_WindowsCreateString
0x18003aad3  mov     rcx, [rsp+148h]; this
0x18003aadb  test    eax, eax
0x18003aadd  js      loc_18003ADB8
0x18003aae3  xorps   xmm0, xmm0
0x18003aae6  xor     ebx, ebx
0x18003aae8  movups  xmmword ptr [rsp+148h+var_120], xmm0
0x18003aaed  mov     [rsp+148h+var_110], rbx
0x18003aaf2  mov     rcx, [rsp+148h+string]; HSTRING
0x18003aaf7  mov     [rsp+148h+string], rdi
0x18003aafc  mov     [rsp+148h+var_120+8], rcx
0x18003ab01  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x18003ab06  mov     byte ptr [rsp+148h+var_120], al
0x18003ab0a  mov     dword ptr [rsp+148h+var_120+4], edi
0x18003ab0e  movups  xmm0, xmmword ptr [rsp+148h+var_120]
0x18003ab13  movaps  [rsp+148h+var_78], xmm0
0x18003ab1b  mov     qword ptr [rsp+148h+length], rbx
0x18003ab23  mov     r9b, 1
0x18003ab26  lea     r8, [rsp+148h+var_78]
0x18003ab2e  xor     edx, edx
0x18003ab30  mov     rcx, qword ptr [rsp+148h+var_128]
0x18003ab35  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x18003ab3a  mov     rcx, [rsp+148h]; this
0x18003ab42  test    eax, eax
0x18003ab44  js      loc_18003ADCD
0x18003ab4a  lea     r8, [rsp+148h+Context]; Context
0x18003ab4f  lea     rdx, [rsp+148h+Interface]; Delimiter
0x18003ab57  xor     ecx, ecx; String
0x18003ab59  call    cs:__imp_wcstok_s
0x18003ab5f  mov     r14, rax
0x18003ab62  lea     rcx, [rsp+148h+var_120]; struct Windows::Networking::UX::DnsServer *
0x18003ab67  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18003ab6c  nop
0x18003ab6d  mov     rcx, [rsp+148h+string]; string
0x18003ab72  call    cs:__imp_WindowsDeleteString
0x18003ab78  mov     [rsp+148h+string], rdi
0x18003ab7d  jmp     loc_18003AA9B
0x18003ab82  mov     ebx, edi
0x18003ab84  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003ab8c  cmp     ebx, [rsp+148h+var_88]
0x18003ab93  jnb     loc_18003AD1C
0x18003ab99  mov     eax, ebx
0x18003ab9b  lea     rcx, [rax+rax*2]
0x18003ab9f  mov     rax, [rsp+148h+var_80]
0x18003aba7  mov     r15d, [rax+rcx*8+4]
0x18003abac  mov     r14, [rax+rcx*8+10h]
0x18003abb1  xorps   xmm0, xmm0
0x18003abb4  xor     eax, eax
0x18003abb6  movups  xmmword ptr [rsp+148h+var_120], xmm0
0x18003abbb  mov     [rsp+148h+var_110], rax
0x18003abc0  lea     r8, [rsp+148h+var_120]
0x18003abc5  mov     edx, r15d
0x18003abc8  mov     rcx, qword ptr [rsp+148h+var_128]
0x18003abcd  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x18003abd2  mov     rcx, [rsp+148h]; this
0x18003abda  test    eax, eax
0x18003abdc  js      loc_18003ADE2
0x18003abe2  mov     eax, dword ptr [rsp+148h+var_120+4]
0x18003abe6  test    byte ptr [r14+8], 4
0x18003abeb  jz      short loc_18003ABF4
0x18003abed  or      eax, 4
0x18003abf0  mov     dword ptr [rsp+148h+var_120+4], eax
0x18003abf4  test    byte ptr [r14+8], 1
0x18003abf9  jz      loc_18003AC92
0x18003abff  or      eax, 1
0x18003ac02  mov     dword ptr [rsp+148h+var_120+4], eax
0x18003ac06  cmp     byte ptr [rsp+148h+var_120], dil
0x18003ac0b  jz      loc_18003AC92
0x18003ac11  xorps   xmm0, xmm0
0x18003ac14  movups  [rsp+148h+var_78], xmm0
0x18003ac1c  movdqu  xmmword ptr [rsp+148h+length], xmm6
0x18003ac25  mov     word ptr [rsp+148h+var_78], di
0x18003ac2d  lea     rdx, [rsp+148h+var_78]
0x18003ac35  mov     rcx, [rsp+148h+var_120+8]; string
0x18003ac3a  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x18003ac3f  mov     rcx, [rsp+148h]; this
0x18003ac47  test    eax, eax
0x18003ac49  js      loc_18003ADF7
0x18003ac4f  lea     rcx, [rsp+148h+var_78]
0x18003ac57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ac5c  mov     rcx, rax; sourceString
0x18003ac5f  lea     r8, [rsp+148h+var_110]; string
0x18003ac64  mov     edx, [rsp+148h+length]; length
0x18003ac6b  call    cs:__imp_WindowsCreateString
0x18003ac71  mov     rcx, [rsp+148h]; this
0x18003ac79  test    eax, eax
0x18003ac7b  js      loc_18003AE0B
0x18003ac81  lea     rcx, [rsp+148h+var_78]
0x18003ac89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ac8e  mov     eax, dword ptr [rsp+148h+var_120+4]
0x18003ac92  test    byte ptr [r14+8], 2
0x18003ac97  jz      short loc_18003ACCA
0x18003ac99  or      eax, 2
0x18003ac9c  mov     dword ptr [rsp+148h+var_120+4], eax
0x18003aca0  mov     rcx, [r14]; sourceString
0x18003aca3  mov     rdx, r13
0x18003aca6  inc     rdx; length
0x18003aca9  cmp     [rcx+rdx*2], di
0x18003acad  jnz     short loc_18003ACA6
0x18003acaf  lea     r8, [rsp+148h+var_110]; string
0x18003acb4  call    cs:__imp_WindowsCreateString
0x18003acba  mov     rcx, [rsp+148h]; this
0x18003acc2  test    eax, eax
0x18003acc4  js      loc_18003AE20
0x18003acca  movups  xmm0, xmmword ptr [rsp+148h+var_120]
0x18003accf  movaps  [rsp+148h+var_78], xmm0
0x18003acd7  movsd   xmm1, [rsp+148h+var_110]
0x18003acdd  movsd   qword ptr [rsp+148h+length], xmm1
0x18003ace6  lea     r8, [rsp+148h+var_78]
0x18003acee  mov     edx, r15d
0x18003acf1  mov     rcx, qword ptr [rsp+148h+var_128]
0x18003acf6  call    ?SetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(uint,Windows::Networking::UX::DnsServer)
0x18003acfb  mov     rcx, [rsp+148h]; this
0x18003ad03  test    eax, eax
0x18003ad05  js      loc_18003AE34
0x18003ad0b  lea     rcx, [rsp+148h+var_120]; struct Windows::Networking::UX::DnsServer *
0x18003ad10  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18003ad15  inc     ebx
0x18003ad17  jmp     loc_18003AB8C
0x18003ad1c  lea     rcx, [rsp+148h+Settings]; Settings
0x18003ad21  call    cs:__imp_FreeInterfaceDnsSettings
0x18003ad27  nop
0x18003ad28  jmp     short loc_18003AD2F
0x18003ad2a  mov     rsi, [rsp+148h+var_F0]
0x18003ad2f  mov     rbx, qword ptr [rsp+148h+var_128]
0x18003ad34  mov     rcx, rsi
0x18003ad37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ad3c  mov     rdx, rsi
0x18003ad3f  mov     rcx, rbx
0x18003ad42  call    ?GetView@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> * *)
0x18003ad47  mov     rcx, [rsp+148h]; this
0x18003ad4f  test    eax, eax
0x18003ad51  jns     short loc_18003AD68
0x18003ad53  mov     r9d, eax; char *
0x18003ad56  mov     edx, 0FAh; void *
0x18003ad5b  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003ad62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ad67  nop
0x18003ad68  lea     rcx, [rsp+148h+var_128]
0x18003ad6d  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003ad72  nop
0x18003ad73  mov     rax, rsi
0x18003ad76  mov     rcx, [rsp+148h+var_48]
0x18003ad7e  xor     rcx, rsp; StackCookie
0x18003ad81  call    __security_check_cookie
0x18003ad86  lea     r11, [rsp+148h+var_28]
0x18003ad8e  mov     rbx, [r11+40h]
0x18003ad92  movaps  xmm6, xmmword ptr [r11-10h]
0x18003ad97  mov     rsp, r11
0x18003ad9a  pop     r15
0x18003ad9c  pop     r14
0x18003ad9e  pop     r13
0x18003ada0  pop     rdi
0x18003ada1  pop     rsi
0x18003ada2  retn
0x18003ada3  mov     r9d, eax; char *
0x18003ada6  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003adad  mov     edx, 0C0h; void *
0x18003adb2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003adb8  mov     r9d, eax; char *
0x18003adbb  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003adc2  mov     edx, 0CCh; void *
0x18003adc7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003adcd  mov     r9d, eax; char *
0x18003add0  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003add7  mov     edx, 0D2h; void *
0x18003addc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ade2  mov     r9d, eax; char *
0x18003ade5  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003adec  mov     edx, 0DCh; void *
0x18003adf1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003adf7  mov     r9d, eax; char *
0x18003adfa  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003ae01  mov     edx, 0E8h; void *
0x18003ae06  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ae0b  mov     r9d, eax; char *
0x18003ae0e  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003ae15  mov     edx, 0E9h; void *
0x18003ae1a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ae20  mov     r9d, eax; char *
0x18003ae23  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003ae2a  mov     edx, 0F1h; void *
0x18003ae2f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ae34  mov     r9d, eax; char *
0x18003ae37  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003ae3e  mov     edx, 0F4h; void *
0x18003ae43  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
