# TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)

- ea: `0x1800876d8`
- end: `0x180087c02`
- name: `?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z`
- size: `1322`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082b60`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180008e30`
- `0x18001b230`
- `0x18001b838`
- `0x18001be60`
- `0x18001c044`
- `0x18004ca20`
- `0x180056b9c`
- `0x18008067c`
- `0x180081e5c`
- `0x1800825b0`
- `0x180083740`
- `0x180083af4`
- `0x180084c40`
- `0x180086b70`
- `0x180086bfc`
- `0x1800876d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18008784a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180087911`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18008784a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180087911`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800877c2`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800877c2`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800877d2`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x180087ad9`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800877d2`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x180087ad9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008792a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008792a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180087885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180087a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180087a6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180087885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180087a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180087a6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
wchar_t *__fastcall TryGetProfileDnsServerView(wchar_t *a1, GUID *a2, int a3)
{
  __int64 v6; // r9
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rdx
  ULONG64 v9; // rax
  unsigned int InterfaceDnsSettings; // eax
  __int64 v12; // rax
  wchar_t *v13; // r14
  __int64 v14; // rbx
  HRESULT v15; // eax
  HSTRING v16; // rcx
  __int64 v17; // r9
  int v18; // eax
  unsigned int v19; // ebx
  __m128i si128; // xmm6
  unsigned int v21; // r15d
  __int64 v22; // r14
  int v23; // eax
  int v24; // eax
  int WellKnownDnsServerTemplate; // eax
  const WCHAR *v26; // rax
  HRESULT v27; // eax
  const WCHAR *v28; // rcx
  __int64 v29; // rdx
  HRESULT v30; // eax
  int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // r8
  int View; // eax
  unsigned int v36[2]; // [rsp+20h] [rbp-128h] BYREF
  HSTRING v37[2]; // [rsp+28h] [rbp-120h] BYREF
  HSTRING v38; // [rsp+38h] [rbp-110h] BYREF
  HSTRING string; // [rsp+40h] [rbp-108h] BYREF
  int v40; // [rsp+48h] [rbp-100h]
  wchar_t *Context[2]; // [rsp+50h] [rbp-F8h] BYREF
  DNS_INTERFACE_SETTINGS Settings; // [rsp+60h] [rbp-E8h] BYREF
  unsigned int v43; // [rsp+C0h] [rbp-88h]
  __int64 v44; // [rsp+C8h] [rbp-80h]
  __int128 v45; // [rsp+D0h] [rbp-78h] BYREF
  UINT32 length[4]; // [rsp+E0h] [rbp-68h]
  GUID Interface; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  Context[1] = a1;
  *(_QWORD *)a1 = 0;
  v40 = 1;
  *(_QWORD *)v36 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
  *(_QWORD *)v36 = 0;
  Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(&Interface);
  if ( *(_QWORD *)&Interface.Data1 )
  {
    v6 = 0;
    *(_QWORD *)v36 = *(_QWORD *)&Interface.Data1;
  }
  else
  {
    v6 = 2147942414LL;
  }
  v7 = retaddr;
  if ( (int)v6 < 0 )
  {
    v8 = 171;
LABEL_40:
    wil::details::in1diag3::_Log_Hr(
      v7,
      (void *)v8,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)v6,
      v36[0]);
    goto LABEL_41;
  }
  memset_0(&Settings, 0, 0x70u);
  Settings.Version = 3;
  v9 = 8704;
  if ( a3 == 6 )
    v9 = 8705;
  Settings.Flags = v9;
  Interface = *a2;
  InterfaceDnsSettings = GetInterfaceDnsSettings(&Interface, &Settings);
  if ( InterfaceDnsSettings == 2 )
  {
    FreeInterfaceDnsSettings(&Settings);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
    return a1;
  }
  if ( InterfaceDnsSettings )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)InterfaceDnsSettings,
      v36[0]);
  if ( Settings.ProfileNameServer )
  {
    v12 = -1;
    do
      ++v12;
    while ( Settings.ProfileNameServer[v12] );
    if ( v12 )
    {
      *(_QWORD *)&Interface.Data1 = 0x3B002C0020LL;
      Context[0] = 0;
      v13 = wcstok_s(Settings.ProfileNameServer, (const wchar_t *)&Interface, Context);
      while ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v15 = WindowsCreateString(v13, v14, &string);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xCC,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v15,
            v36[0]);
        v37[0] = 0;
        v38 = 0;
        v16 = string;
        string = 0;
        v37[1] = v16;
        LOBYTE(v37[0]) = DnsServerIsWellKnownDoh(v16);
        HIDWORD(v37[0]) = 0;
        v45 = *(_OWORD *)v37;
        *(_QWORD *)length = 0;
        LOBYTE(v17) = 1;
        v18 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
                *(_QWORD *)v36,
                0,
                &v45,
                v17);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD2,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v18,
            v36[0]);
        v13 = wcstok_s(0, (const wchar_t *)&Interface, Context);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v37);
        WindowsDeleteString(string);
        string = 0;
      }
      v19 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( v19 < v43 )
      {
        v21 = *(_DWORD *)(v44 + 24LL * v19 + 4);
        v22 = *(_QWORD *)(v44 + 24LL * v19 + 16);
        *(_OWORD *)v37 = 0;
        v38 = 0;
        v23 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                *(_QWORD *)v36,
                v21,
                v37);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v23,
            v36[0]);
        v24 = HIDWORD(v37[0]);
        if ( (*(_BYTE *)(v22 + 8) & 4) != 0 )
        {
          v24 = HIDWORD(v37[0]) | 4;
          HIDWORD(v37[0]) |= 4u;
        }
        if ( (*(_BYTE *)(v22 + 8) & 1) != 0 )
        {
          v24 |= 1u;
          HIDWORD(v37[0]) = v24;
          if ( LOBYTE(v37[0]) )
          {
            v45 = 0;
            *(__m128i *)length = si128;
            LOWORD(v45) = 0;
            WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v37[1]);
            if ( WellKnownDnsServerTemplate < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xE8,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)WellKnownDnsServerTemplate,
                v36[0]);
            v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v45);
            v27 = WindowsCreateString(v26, length[0], &v38);
            if ( v27 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xE9,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v27,
                v36[0]);
            std::wstring::_Tidy_deallocate(&v45);
            v24 = HIDWORD(v37[0]);
          }
        }
        if ( (*(_BYTE *)(v22 + 8) & 2) != 0 )
        {
          HIDWORD(v37[0]) = v24 | 2;
          v28 = *(const WCHAR **)v22;
          v29 = -1;
          do
            ++v29;
          while ( v28[v29] );
          v30 = WindowsCreateString(v28, v29, &v38);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xF1,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v30,
              v36[0]);
        }
        v45 = *(_OWORD *)v37;
        *(_QWORD *)length = v38;
        v31 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(
                *(_QWORD *)v36,
                v21,
                &v45);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
            (const char *)(unsigned int)v31,
            v36[0]);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v37);
        ++v19;
      }
    }
  }
  FreeInterfaceDnsSettings(&Settings);
  v32 = *(_QWORD *)v36;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1, v33, v34);
  View = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(
           v32,
           a1);
  v7 = retaddr;
  if ( View < 0 )
  {
    v6 = (unsigned int)View;
    v8 = 250;
    goto LABEL_40;
  }
LABEL_41:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
  return a1;
}

```

## disassembly

```asm
0x1800876d8  mov     rax, rsp
0x1800876db  mov     [rax+18h], rbx
0x1800876df  push    rsi
0x1800876e0  push    rdi
0x1800876e1  push    r13
0x1800876e3  push    r14
0x1800876e5  push    r15
0x1800876e7  sub     rsp, 120h
0x1800876ee  movaps  xmmword ptr [rax-38h], xmm6
0x1800876f2  mov     rax, cs:__security_cookie
0x1800876f9  xor     rax, rsp
0x1800876fc  mov     [rsp+148h+var_48], rax
0x180087704  mov     ebx, r8d
0x180087707  mov     r14, rdx
0x18008770a  mov     rsi, rcx
0x18008770d  mov     [rsp+148h+var_F0], rcx
0x180087712  mov     [rsp+148h+var_100], 1
0x18008771a  xor     edi, edi
0x18008771c  mov     [rcx], rdi
0x18008771f  mov     [rsp+148h+var_100], 1
0x180087727  mov     qword ptr [rsp+148h+var_128], rdi
0x18008772c  lea     rcx, [rsp+148h+var_128]
0x180087731  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180087736  mov     qword ptr [rsp+148h+var_128], rdi; int
0x18008773b  lea     rcx, [rsp+148h+Interface]
0x180087743  call    ??$Make@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEBUDnsServerEqualityPredicate@2UX@Networking@5@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@@12@AEBUDnsServerEqualityPredicate@Internal@UX@Networking@Windows@@$$QEAUpermission@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@5Collections@Foundation@8@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission &&)
0x180087748  mov     rax, qword ptr [rsp+148h+Interface.Data1]
0x180087750  test    rax, rax
0x180087753  jz      short loc_18008775F
0x180087755  mov     r9d, edi
0x180087758  mov     qword ptr [rsp+148h+var_128], rax
0x18008775d  jmp     short loc_180087765
0x18008775f  mov     r9d, 8007000Eh
0x180087765  mov     rcx, [rsp+148h]
0x18008776d  test    r9d, r9d
0x180087770  jns     short loc_18008777C
0x180087772  mov     edx, 0ABh
0x180087777  jmp     loc_180087B13
0x18008777c  xor     edx, edx; Val
0x18008777e  lea     r8d, [rdx+70h]; Size
0x180087782  lea     rcx, [rsp+148h+Settings]; void *
0x180087787  call    memset_0
0x18008778c  nop
0x18008778d  mov     [rsp+148h+Settings.Version], 3
0x180087795  mov     eax, 2200h
0x18008779a  lea     ecx, [rax+1]
0x18008779d  cmp     ebx, 6
0x1800877a0  cmovz   eax, ecx
0x1800877a3  mov     [rsp+148h+Settings.Flags], rax
0x1800877a8  movups  xmm0, xmmword ptr [r14]
0x1800877ac  movdqu  xmmword ptr [rsp+148h+Interface.Data1], xmm0
0x1800877b5  lea     rdx, [rsp+148h+Settings]; Settings
0x1800877ba  lea     rcx, [rsp+148h+Interface]; Interface
0x1800877c2  call    cs:__imp_GetInterfaceDnsSettings
0x1800877c8  cmp     eax, 2
0x1800877cb  jnz     short loc_1800877EC
0x1800877cd  lea     rcx, [rsp+148h+Settings]; Settings
0x1800877d2  call    cs:__imp_FreeInterfaceDnsSettings
0x1800877d8  nop
0x1800877d9  lea     rcx, [rsp+148h+var_128]
0x1800877de  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x1800877e3  nop
0x1800877e4  mov     rax, rsi
0x1800877e7  jmp     loc_180087B2E
0x1800877ec  mov     rcx, [rsp+148h]; this
0x1800877f4  test    eax, eax
0x1800877f6  jnz     loc_180087B5B
0x1800877fc  mov     rcx, [rsp+148h+Settings.ProfileNameServer]; String
0x180087804  test    rcx, rcx
0x180087807  jz      loc_180087AD4
0x18008780d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180087811  mov     rax, r13
0x180087814  inc     rax
0x180087817  cmp     [rcx+rax*2], di
0x18008781b  jnz     short loc_180087814
0x18008781d  test    rax, rax
0x180087820  jz      loc_180087AD4
0x180087826  mov     rax, 3B002C0020h
0x180087830  mov     qword ptr [rsp+148h+Interface.Data1], rax
0x180087838  mov     [rsp+148h+Context], rdi
0x18008783d  lea     r8, [rsp+148h+Context]; Context
0x180087842  lea     rdx, [rsp+148h+Interface]; Delimiter
0x18008784a  call    cs:__imp_wcstok_s
0x180087850  mov     r14, rax
0x180087853  test    r14, r14
0x180087856  jz      loc_18008793A
0x18008785c  mov     rbx, r13
0x18008785f  inc     rbx
0x180087862  cmp     [r14+rbx*2], di
0x180087867  jnz     short loc_18008785F
0x180087869  mov     [rsp+148h+string], rdi
0x18008786e  xor     ecx, ecx; string
0x180087870  call    cs:__imp_WindowsDeleteString
0x180087876  mov     [rsp+148h+string], rdi
0x18008787b  lea     r8, [rsp+148h+string]; string
0x180087880  mov     edx, ebx; length
0x180087882  mov     rcx, r14; sourceString
0x180087885  call    cs:__imp_WindowsCreateString
0x18008788b  mov     rcx, [rsp+148h]; this
0x180087893  test    eax, eax
0x180087895  js      loc_180087B70
0x18008789b  xorps   xmm0, xmm0
0x18008789e  xor     ebx, ebx
0x1800878a0  movups  xmmword ptr [rsp+148h+var_120], xmm0
0x1800878a5  mov     [rsp+148h+var_110], rbx
0x1800878aa  mov     rcx, [rsp+148h+string]; HSTRING
0x1800878af  mov     [rsp+148h+string], rdi
0x1800878b4  mov     [rsp+148h+var_120+8], rcx
0x1800878b9  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x1800878be  mov     byte ptr [rsp+148h+var_120], al
0x1800878c2  mov     dword ptr [rsp+148h+var_120+4], edi
0x1800878c6  movups  xmm0, xmmword ptr [rsp+148h+var_120]
0x1800878cb  movaps  [rsp+148h+var_78], xmm0
0x1800878d3  mov     qword ptr [rsp+148h+length], rbx
0x1800878db  mov     r9b, 1
0x1800878de  lea     r8, [rsp+148h+var_78]
0x1800878e6  xor     edx, edx
0x1800878e8  mov     rcx, qword ptr [rsp+148h+var_128]
0x1800878ed  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x1800878f2  mov     rcx, [rsp+148h]; this
0x1800878fa  test    eax, eax
0x1800878fc  js      loc_180087B85
0x180087902  lea     r8, [rsp+148h+Context]; Context
0x180087907  lea     rdx, [rsp+148h+Interface]; Delimiter
0x18008790f  xor     ecx, ecx; String
0x180087911  call    cs:__imp_wcstok_s
0x180087917  mov     r14, rax
0x18008791a  lea     rcx, [rsp+148h+var_120]; struct Windows::Networking::UX::DnsServer *
0x18008791f  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180087924  nop
0x180087925  mov     rcx, [rsp+148h+string]; string
0x18008792a  call    cs:__imp_WindowsDeleteString
0x180087930  mov     [rsp+148h+string], rdi
0x180087935  jmp     loc_180087853
0x18008793a  mov     ebx, edi
0x18008793c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180087944  cmp     ebx, [rsp+148h+var_88]
0x18008794b  jnb     loc_180087AD4
0x180087951  mov     eax, ebx
0x180087953  lea     rcx, [rax+rax*2]
0x180087957  mov     rax, [rsp+148h+var_80]
0x18008795f  mov     r15d, [rax+rcx*8+4]
0x180087964  mov     r14, [rax+rcx*8+10h]
0x180087969  xorps   xmm0, xmm0
0x18008796c  xor     eax, eax
0x18008796e  movups  xmmword ptr [rsp+148h+var_120], xmm0
0x180087973  mov     [rsp+148h+var_110], rax
0x180087978  lea     r8, [rsp+148h+var_120]
0x18008797d  mov     edx, r15d
0x180087980  mov     rcx, qword ptr [rsp+148h+var_128]
0x180087985  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x18008798a  mov     rcx, [rsp+148h]; this
0x180087992  test    eax, eax
0x180087994  js      loc_180087B9A
0x18008799a  mov     eax, dword ptr [rsp+148h+var_120+4]
0x18008799e  test    byte ptr [r14+8], 4
0x1800879a3  jz      short loc_1800879AC
0x1800879a5  or      eax, 4
0x1800879a8  mov     dword ptr [rsp+148h+var_120+4], eax
0x1800879ac  test    byte ptr [r14+8], 1
0x1800879b1  jz      loc_180087A4A
0x1800879b7  or      eax, 1
0x1800879ba  mov     dword ptr [rsp+148h+var_120+4], eax
0x1800879be  cmp     byte ptr [rsp+148h+var_120], dil
0x1800879c3  jz      loc_180087A4A
0x1800879c9  xorps   xmm0, xmm0
0x1800879cc  movups  [rsp+148h+var_78], xmm0
0x1800879d4  movdqu  xmmword ptr [rsp+148h+length], xmm6
0x1800879dd  mov     word ptr [rsp+148h+var_78], di
0x1800879e5  lea     rdx, [rsp+148h+var_78]
0x1800879ed  mov     rcx, [rsp+148h+var_120+8]; string
0x1800879f2  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x1800879f7  mov     rcx, [rsp+148h]; this
0x1800879ff  test    eax, eax
0x180087a01  js      loc_180087BAF
0x180087a07  lea     rcx, [rsp+148h+var_78]
0x180087a0f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180087a14  mov     rcx, rax; sourceString
0x180087a17  lea     r8, [rsp+148h+var_110]; string
0x180087a1c  mov     edx, [rsp+148h+length]; length
0x180087a23  call    cs:__imp_WindowsCreateString
0x180087a29  mov     rcx, [rsp+148h]; this
0x180087a31  test    eax, eax
0x180087a33  js      loc_180087BC3
0x180087a39  lea     rcx, [rsp+148h+var_78]
0x180087a41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180087a46  mov     eax, dword ptr [rsp+148h+var_120+4]
0x180087a4a  test    byte ptr [r14+8], 2
0x180087a4f  jz      short loc_180087A82
0x180087a51  or      eax, 2
0x180087a54  mov     dword ptr [rsp+148h+var_120+4], eax
0x180087a58  mov     rcx, [r14]; sourceString
0x180087a5b  mov     rdx, r13
0x180087a5e  inc     rdx; length
0x180087a61  cmp     [rcx+rdx*2], di
0x180087a65  jnz     short loc_180087A5E
0x180087a67  lea     r8, [rsp+148h+var_110]; string
0x180087a6c  call    cs:__imp_WindowsCreateString
0x180087a72  mov     rcx, [rsp+148h]; this
0x180087a7a  test    eax, eax
0x180087a7c  js      loc_180087BD8
0x180087a82  movups  xmm0, xmmword ptr [rsp+148h+var_120]
0x180087a87  movaps  [rsp+148h+var_78], xmm0
0x180087a8f  movsd   xmm1, [rsp+148h+var_110]
0x180087a95  movsd   qword ptr [rsp+148h+length], xmm1
0x180087a9e  lea     r8, [rsp+148h+var_78]
0x180087aa6  mov     edx, r15d
0x180087aa9  mov     rcx, qword ptr [rsp+148h+var_128]
0x180087aae  call    ?SetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(uint,Windows::Networking::UX::DnsServer)
0x180087ab3  mov     rcx, [rsp+148h]; this
0x180087abb  test    eax, eax
0x180087abd  js      loc_180087BEC
0x180087ac3  lea     rcx, [rsp+148h+var_120]; struct Windows::Networking::UX::DnsServer *
0x180087ac8  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180087acd  inc     ebx
0x180087acf  jmp     loc_180087944
0x180087ad4  lea     rcx, [rsp+148h+Settings]; Settings
0x180087ad9  call    cs:__imp_FreeInterfaceDnsSettings
0x180087adf  nop
0x180087ae0  jmp     short loc_180087AE7
0x180087ae2  mov     rsi, [rsp+148h+var_F0]
0x180087ae7  mov     rbx, qword ptr [rsp+148h+var_128]
0x180087aec  mov     rcx, rsi
0x180087aef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180087af4  mov     rdx, rsi
0x180087af7  mov     rcx, rbx
0x180087afa  call    ?GetView@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> * *)
0x180087aff  mov     rcx, [rsp+148h]; this
0x180087b07  test    eax, eax
0x180087b09  jns     short loc_180087B20
0x180087b0b  mov     r9d, eax; char *
0x180087b0e  mov     edx, 0FAh; void *
0x180087b13  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087b1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087b1f  nop
0x180087b20  lea     rcx, [rsp+148h+var_128]
0x180087b25  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180087b2a  nop
0x180087b2b  mov     rax, rsi
0x180087b2e  mov     rcx, [rsp+148h+var_48]
0x180087b36  xor     rcx, rsp; StackCookie
0x180087b39  call    __security_check_cookie
0x180087b3e  lea     r11, [rsp+148h+var_28]
0x180087b46  mov     rbx, [r11+40h]
0x180087b4a  movaps  xmm6, xmmword ptr [r11-10h]
0x180087b4f  mov     rsp, r11
0x180087b52  pop     r15
0x180087b54  pop     r14
0x180087b56  pop     r13
0x180087b58  pop     rdi
0x180087b59  pop     rsi
0x180087b5a  retn
0x180087b5b  mov     r9d, eax; char *
0x180087b5e  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087b65  mov     edx, 0C0h; void *
0x180087b6a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180087b70  mov     r9d, eax; char *
0x180087b73  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087b7a  mov     edx, 0CCh; void *
0x180087b7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180087b85  mov     r9d, eax; char *
0x180087b88  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087b8f  mov     edx, 0D2h; void *
0x180087b94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180087b9a  mov     r9d, eax; char *
0x180087b9d  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087ba4  mov     edx, 0DCh; void *
0x180087ba9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180087baf  mov     r9d, eax; char *
0x180087bb2  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087bb9  mov     edx, 0E8h; void *
0x180087bbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180087bc3  mov     r9d, eax; char *
0x180087bc6  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087bcd  mov     edx, 0E9h; void *
0x180087bd2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180087bd8  mov     r9d, eax; char *
0x180087bdb  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087be2  mov     edx, 0F1h; void *
0x180087be7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180087bec  mov     r9d, eax; char *
0x180087bef  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087bf6  mov     edx, 0F4h; void *
0x180087bfb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
