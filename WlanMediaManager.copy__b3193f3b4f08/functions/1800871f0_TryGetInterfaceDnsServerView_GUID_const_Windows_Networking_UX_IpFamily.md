# TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)

- ea: `0x1800871f0`
- end: `0x1800876cf`
- name: `?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z`
- size: `1247`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007d734`
- `0x180082b60`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180008e30`
- `0x180011a64`
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
- `0x1800871f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180087369`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18008744e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180087369`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18008744e`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800872d4`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800872d4`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800872e4`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x180087652`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800872e4`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x180087652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008738f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087467`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008738f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180087467`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800873a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008756a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800875c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800873a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008756a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800875c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall TryGetInterfaceDnsServerView(_QWORD *a1, GUID *a2, int a3)
{
  _QWORD *v5; // rsi
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
  unsigned int i; // ebx
  unsigned int v20; // r15d
  __int64 v21; // r14
  int v22; // eax
  int v23; // eax
  int WellKnownDnsServerTemplate; // eax
  const WCHAR *v25; // rax
  HRESULT v26; // eax
  const WCHAR *v27; // rcx
  __int64 v28; // rdx
  HRESULT v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // rbx
  int View; // eax
  unsigned int v36[2]; // [rsp+20h] [rbp-118h] BYREF
  HSTRING v37[2]; // [rsp+28h] [rbp-110h] BYREF
  HSTRING v38; // [rsp+38h] [rbp-100h] BYREF
  HSTRING string; // [rsp+40h] [rbp-F8h] BYREF
  int v40; // [rsp+48h] [rbp-F0h]
  wchar_t *Context; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD *v42; // [rsp+58h] [rbp-E0h]
  DNS_INTERFACE_SETTINGS Settings; // [rsp+60h] [rbp-D8h] BYREF
  unsigned int v44; // [rsp+B0h] [rbp-88h]
  __int64 v45; // [rsp+B8h] [rbp-80h]
  __int128 v46; // [rsp+D0h] [rbp-68h] BYREF
  UINT32 length[4]; // [rsp+E0h] [rbp-58h]
  GUID Interface; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v5 = a1;
  v42 = a1;
  *a1 = 0;
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
    v8 = 81;
LABEL_49:
    wil::details::in1diag3::_Log_Hr(
      v7,
      (void *)v8,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)v6,
      v36[0]);
    goto LABEL_50;
  }
  memset_0(&Settings, 0, 0x70u);
  Settings.Version = 3;
  v9 = 4098;
  if ( a3 == 6 )
    v9 = 4099;
  Settings.Flags = v9;
  Interface = *a2;
  InterfaceDnsSettings = GetInterfaceDnsSettings(&Interface, &Settings);
  if ( InterfaceDnsSettings == 2 )
  {
    FreeInterfaceDnsSettings(&Settings);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
    return v5;
  }
  try
  {
    if ( InterfaceDnsSettings )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
        (const char *)InterfaceDnsSettings,
        v36[0]);
    if ( Settings.NameServer )
    {
      v12 = -1;
      do
        ++v12;
      while ( Settings.NameServer[v12] );
      if ( v12 )
      {
        *(_QWORD *)&Interface.Data1 = 0x3B002C0020LL;
        Context = 0;
        v13 = wcstok_s(Settings.NameServer, (const wchar_t *)&Interface, &Context);
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
              (void *)0x73,
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
          v46 = *(_OWORD *)v37;
          *(_QWORD *)length = 0;
          LOBYTE(v17) = 1;
          v18 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
                  *(_QWORD *)v36,
                  0,
                  &v46,
                  v17);
          if ( v18 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x79,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v18,
              v36[0]);
          v13 = wcstok_s(0, (const wchar_t *)&Interface, &Context);
          FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v37);
          WindowsDeleteString(string);
          string = 0;
        }
        for ( i = 0; i < v44; ++i )
        {
          v20 = *(_DWORD *)(v45 + 24LL * i + 4);
          v21 = *(_QWORD *)(v45 + 24LL * i + 16);
          *(_OWORD *)v37 = 0;
          v38 = 0;
          v22 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                  *(_QWORD *)v36,
                  v20,
                  v37);
          if ( v22 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x83,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v22,
              v36[0]);
          v23 = HIDWORD(v37[0]);
          if ( (*(_BYTE *)(v21 + 8) & 4) != 0 )
          {
            v23 = HIDWORD(v37[0]) | 4;
            HIDWORD(v37[0]) |= 4u;
          }
          if ( (*(_BYTE *)(v21 + 8) & 1) != 0 )
          {
            v23 |= 1u;
            HIDWORD(v37[0]) = v23;
            if ( LOBYTE(v37[0]) )
            {
              std::wstring::wstring(&v46);
              WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v37[1]);
              if ( WellKnownDnsServerTemplate < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x90,
                  (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                  (const char *)(unsigned int)WellKnownDnsServerTemplate,
                  v36[0]);
              v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v46);
              v26 = WindowsCreateString(v25, length[0], &v38);
              if ( v26 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x91,
                  (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                  (const char *)(unsigned int)v26,
                  v36[0]);
              std::wstring::_Tidy_deallocate(&v46);
              v23 = HIDWORD(v37[0]);
            }
          }
          if ( (*(_BYTE *)(v21 + 8) & 2) != 0 )
          {
            HIDWORD(v37[0]) = v23 | 2;
            v27 = *(const WCHAR **)v21;
            v28 = -1;
            do
              ++v28;
            while ( v27[v28] );
            v29 = WindowsCreateString(v27, v28, &v38);
            if ( v29 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x99,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v29,
                v36[0]);
          }
          v46 = *(_OWORD *)v37;
          *(_QWORD *)length = v38;
          v30 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(
                  *(_QWORD *)v36,
                  v20,
                  &v46);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x9C,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v30,
              v36[0]);
          FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v37);
        }
      }
    }
    FreeInterfaceDnsSettings(&Settings);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      v33);
    v5 = v42;
  }
  v34 = *(_QWORD *)v36;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v5, v31, v32);
  View = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(
           v34,
           v5);
  v7 = retaddr;
  if ( View < 0 )
  {
    v6 = (unsigned int)View;
    v8 = 162;
    goto LABEL_49;
  }
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
  return v5;
}

```

## disassembly

```asm
0x1800871f0  mov     [rsp+arg_10], rbx
0x1800871f5  push    rsi
0x1800871f6  push    rdi
0x1800871f7  push    r13
0x1800871f9  push    r14
0x1800871fb  push    r15
0x1800871fd  sub     rsp, 110h
0x180087204  mov     rax, cs:__security_cookie
0x18008720b  xor     rax, rsp
0x18008720e  mov     [rsp+138h+var_38], rax
0x180087216  mov     ebx, r8d
0x180087219  mov     r14, rdx
0x18008721c  mov     rsi, rcx
0x18008721f  mov     [rsp+138h+var_E0], rcx
0x180087224  mov     [rsp+138h+var_F0], 1
0x18008722c  xor     edi, edi
0x18008722e  mov     [rcx], rdi
0x180087231  mov     [rsp+138h+var_F0], 1
0x180087239  mov     qword ptr [rsp+138h+var_118], rdi
0x18008723e  lea     rcx, [rsp+138h+var_118]
0x180087243  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180087248  mov     qword ptr [rsp+138h+var_118], rdi; int
0x18008724d  lea     rcx, [rsp+138h+Interface]
0x180087255  call    ??$Make@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEBUDnsServerEqualityPredicate@2UX@Networking@5@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@@12@AEBUDnsServerEqualityPredicate@Internal@UX@Networking@Windows@@$$QEAUpermission@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@5Collections@Foundation@8@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission &&)
0x18008725a  mov     rax, qword ptr [rsp+138h+Interface.Data1]
0x180087262  test    rax, rax
0x180087265  jz      short loc_180087271
0x180087267  mov     r9d, edi
0x18008726a  mov     qword ptr [rsp+138h+var_118], rax
0x18008726f  jmp     short loc_180087277
0x180087271  mov     r9d, 8007000Eh
0x180087277  mov     rcx, [rsp+138h]
0x18008727f  test    r9d, r9d
0x180087282  jns     short loc_18008728E
0x180087284  mov     edx, 51h ; 'Q'
0x180087289  jmp     loc_18008768C
0x18008728e  xor     edx, edx; Val
0x180087290  lea     r8d, [rdx+70h]; Size
0x180087294  lea     rcx, [rsp+138h+Settings]; void *
0x180087299  call    memset_0
0x18008729e  nop
0x18008729f  mov     [rsp+138h+Settings.Version], 3
0x1800872a7  mov     eax, 1002h
0x1800872ac  lea     ecx, [rax+1]
0x1800872af  cmp     ebx, 6
0x1800872b2  cmovz   eax, ecx
0x1800872b5  mov     [rsp+138h+Settings.Flags], rax
0x1800872ba  movups  xmm0, xmmword ptr [r14]
0x1800872be  movdqu  xmmword ptr [rsp+138h+Interface.Data1], xmm0
0x1800872c7  lea     rdx, [rsp+138h+Settings]; Settings
0x1800872cc  lea     rcx, [rsp+138h+Interface]; Interface
0x1800872d4  call    cs:__imp_GetInterfaceDnsSettings
0x1800872da  cmp     eax, 2
0x1800872dd  jnz     short loc_1800872FE
0x1800872df  lea     rcx, [rsp+138h+Settings]; Settings
0x1800872e4  call    cs:__imp_FreeInterfaceDnsSettings
0x1800872ea  nop
0x1800872eb  lea     rcx, [rsp+138h+var_118]
0x1800872f0  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x1800872f5  nop
0x1800872f6  mov     rax, rsi
0x1800872f9  jmp     loc_1800876A7
0x1800872fe  mov     rcx, [rsp+138h]; this
0x180087306  test    eax, eax
0x180087308  jz      short loc_18008731E
0x18008730a  mov     r9d, eax; char *
0x18008730d  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087314  mov     edx, 66h ; 'f'; void *
0x180087319  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18008731e  mov     rcx, [rsp+138h+Settings.NameServer]; String
0x180087323  test    rcx, rcx
0x180087326  jz      loc_18008764D
0x18008732c  or      r13, 0FFFFFFFFFFFFFFFFh
0x180087330  mov     rax, r13
0x180087333  inc     rax
0x180087336  cmp     [rcx+rax*2], di
0x18008733a  jnz     short loc_180087333
0x18008733c  test    rax, rax
0x18008733f  jz      loc_18008764D
0x180087345  mov     rax, 3B002C0020h
0x18008734f  mov     qword ptr [rsp+138h+Interface.Data1], rax
0x180087357  mov     [rsp+138h+Context], rdi
0x18008735c  lea     r8, [rsp+138h+Context]; Context
0x180087361  lea     rdx, [rsp+138h+Interface]; Delimiter
0x180087369  call    cs:__imp_wcstok_s
0x18008736f  mov     r14, rax
0x180087372  test    r14, r14
0x180087375  jz      loc_180087477
0x18008737b  mov     rbx, r13
0x18008737e  inc     rbx
0x180087381  cmp     [r14+rbx*2], di
0x180087386  jnz     short loc_18008737E
0x180087388  mov     [rsp+138h+string], rdi
0x18008738d  xor     ecx, ecx; string
0x18008738f  call    cs:__imp_WindowsDeleteString
0x180087395  mov     [rsp+138h+string], rdi
0x18008739a  lea     r8, [rsp+138h+string]; string
0x18008739f  mov     edx, ebx; length
0x1800873a1  mov     rcx, r14; sourceString
0x1800873a4  call    cs:__imp_WindowsCreateString
0x1800873aa  mov     rcx, [rsp+138h]; this
0x1800873b2  test    eax, eax
0x1800873b4  jns     short loc_1800873CA
0x1800873b6  mov     r9d, eax; char *
0x1800873b9  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800873c0  mov     edx, 73h ; 's'; void *
0x1800873c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800873ca  xorps   xmm0, xmm0
0x1800873cd  xor     ebx, ebx
0x1800873cf  movups  xmmword ptr [rsp+138h+var_110], xmm0
0x1800873d4  mov     [rsp+138h+var_100], rbx
0x1800873d9  mov     rcx, [rsp+138h+string]; HSTRING
0x1800873de  mov     [rsp+138h+string], rdi
0x1800873e3  mov     [rsp+138h+var_110+8], rcx
0x1800873e8  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x1800873ed  mov     byte ptr [rsp+138h+var_110], al
0x1800873f1  mov     dword ptr [rsp+138h+var_110+4], edi
0x1800873f5  movups  xmm0, xmmword ptr [rsp+138h+var_110]
0x1800873fa  movaps  [rsp+138h+var_68], xmm0
0x180087402  mov     qword ptr [rsp+138h+length], rbx
0x18008740a  mov     r9b, 1
0x18008740d  lea     r8, [rsp+138h+var_68]
0x180087415  xor     edx, edx
0x180087417  mov     rcx, qword ptr [rsp+138h+var_118]
0x18008741c  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180087421  mov     rcx, [rsp+138h]; this
0x180087429  test    eax, eax
0x18008742b  jns     short loc_18008743F
0x18008742d  mov     r9d, eax; char *
0x180087430  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087437  lea     edx, [rbx+79h]; void *
0x18008743a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008743f  lea     r8, [rsp+138h+Context]; Context
0x180087444  lea     rdx, [rsp+138h+Interface]; Delimiter
0x18008744c  xor     ecx, ecx; String
0x18008744e  call    cs:__imp_wcstok_s
0x180087454  mov     r14, rax
0x180087457  lea     rcx, [rsp+138h+var_110]; struct Windows::Networking::UX::DnsServer *
0x18008745c  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180087461  nop
0x180087462  mov     rcx, [rsp+138h+string]; string
0x180087467  call    cs:__imp_WindowsDeleteString
0x18008746d  mov     [rsp+138h+string], rdi
0x180087472  jmp     loc_180087372
0x180087477  mov     ebx, edi
0x180087479  cmp     ebx, [rsp+138h+var_88]
0x180087480  jnb     loc_18008764D
0x180087486  mov     eax, ebx
0x180087488  lea     rcx, [rax+rax*2]
0x18008748c  mov     rax, [rsp+138h+var_80]
0x180087494  mov     r15d, [rax+rcx*8+4]
0x180087499  mov     r14, [rax+rcx*8+10h]
0x18008749e  xorps   xmm0, xmm0
0x1800874a1  xor     eax, eax
0x1800874a3  movups  xmmword ptr [rsp+138h+var_110], xmm0
0x1800874a8  mov     [rsp+138h+var_100], rax
0x1800874ad  lea     r8, [rsp+138h+var_110]
0x1800874b2  mov     edx, r15d
0x1800874b5  mov     rcx, qword ptr [rsp+138h+var_118]
0x1800874ba  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x1800874bf  mov     rcx, [rsp+138h]; this
0x1800874c7  test    eax, eax
0x1800874c9  jns     short loc_1800874DF
0x1800874cb  mov     r9d, eax; char *
0x1800874ce  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800874d5  mov     edx, 83h; void *
0x1800874da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800874df  mov     eax, dword ptr [rsp+138h+var_110+4]
0x1800874e3  test    byte ptr [r14+8], 4
0x1800874e8  jz      short loc_1800874F1
0x1800874ea  or      eax, 4
0x1800874ed  mov     dword ptr [rsp+138h+var_110+4], eax
0x1800874f1  test    byte ptr [r14+8], 1
0x1800874f6  jz      loc_1800875A2
0x1800874fc  or      eax, 1
0x1800874ff  mov     dword ptr [rsp+138h+var_110+4], eax
0x180087503  cmp     byte ptr [rsp+138h+var_110], dil
0x180087508  jz      loc_1800875A2
0x18008750e  lea     rcx, [rsp+138h+var_68]
0x180087516  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008751b  nop
0x18008751c  lea     rdx, [rsp+138h+var_68]
0x180087524  mov     rcx, [rsp+138h+var_110+8]; string
0x180087529  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x18008752e  mov     rcx, [rsp+138h]; this
0x180087536  test    eax, eax
0x180087538  jns     short loc_18008754E
0x18008753a  mov     r9d, eax; char *
0x18008753d  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087544  mov     edx, 90h; void *
0x180087549  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008754e  lea     rcx, [rsp+138h+var_68]
0x180087556  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008755b  mov     rcx, rax; sourceString
0x18008755e  lea     r8, [rsp+138h+var_100]; string
0x180087563  mov     edx, [rsp+138h+length]; length
0x18008756a  call    cs:__imp_WindowsCreateString
0x180087570  mov     rcx, [rsp+138h]; this
0x180087578  test    eax, eax
0x18008757a  jns     short loc_180087591
0x18008757c  mov     r9d, eax; char *
0x18008757f  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087586  mov     edx, 91h; void *
0x18008758b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180087591  lea     rcx, [rsp+138h+var_68]
0x180087599  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008759e  mov     eax, dword ptr [rsp+138h+var_110+4]
0x1800875a2  test    byte ptr [r14+8], 2
0x1800875a7  jz      short loc_1800875EA
0x1800875a9  or      eax, 2
0x1800875ac  mov     dword ptr [rsp+138h+var_110+4], eax
0x1800875b0  mov     rcx, [r14]; sourceString
0x1800875b3  mov     rdx, r13
0x1800875b6  inc     rdx; length
0x1800875b9  cmp     [rcx+rdx*2], di
0x1800875bd  jnz     short loc_1800875B6
0x1800875bf  lea     r8, [rsp+138h+var_100]; string
0x1800875c4  call    cs:__imp_WindowsCreateString
0x1800875ca  mov     rcx, [rsp+138h]; this
0x1800875d2  test    eax, eax
0x1800875d4  jns     short loc_1800875EA
0x1800875d6  mov     r9d, eax; char *
0x1800875d9  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800875e0  mov     edx, 99h; void *
0x1800875e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800875ea  movups  xmm0, xmmword ptr [rsp+138h+var_110]
0x1800875ef  movaps  [rsp+138h+var_68], xmm0
0x1800875f7  movsd   xmm1, [rsp+138h+var_100]
0x1800875fd  movsd   qword ptr [rsp+138h+length], xmm1
0x180087606  lea     r8, [rsp+138h+var_68]
0x18008760e  mov     edx, r15d
0x180087611  mov     rcx, qword ptr [rsp+138h+var_118]
0x180087616  call    ?SetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(uint,Windows::Networking::UX::DnsServer)
0x18008761b  mov     rcx, [rsp+138h]; this
0x180087623  test    eax, eax
0x180087625  jns     short loc_18008763C
0x180087627  mov     r9d, eax; char *
0x18008762a  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087631  mov     edx, 9Ch; void *
0x180087636  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008763c  lea     rcx, [rsp+138h+var_110]; struct Windows::Networking::UX::DnsServer *
0x180087641  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180087646  inc     ebx
0x180087648  jmp     loc_180087479
0x18008764d  lea     rcx, [rsp+138h+Settings]; Settings
0x180087652  call    cs:__imp_FreeInterfaceDnsSettings
0x180087658  nop
0x180087659  jmp     short loc_180087660
0x18008765b  mov     rsi, [rsp+138h+var_E0]
0x180087660  mov     rbx, qword ptr [rsp+138h+var_118]
0x180087665  mov     rcx, rsi
0x180087668  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008766d  mov     rdx, rsi
0x180087670  mov     rcx, rbx
0x180087673  call    ?GetView@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> * *)
0x180087678  mov     rcx, [rsp+138h]; this
0x180087680  test    eax, eax
0x180087682  jns     short loc_180087699
0x180087684  mov     r9d, eax; char *
0x180087687  mov     edx, 0A2h; void *
0x18008768c  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180087693  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087698  nop
0x180087699  lea     rcx, [rsp+138h+var_118]
0x18008769e  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x1800876a3  nop
0x1800876a4  mov     rax, rsi
0x1800876a7  mov     rcx, [rsp+138h+var_38]
0x1800876af  xor     rcx, rsp; StackCookie
0x1800876b2  call    __security_check_cookie
0x1800876b7  mov     rbx, [rsp+138h+arg_10]
0x1800876bf  add     rsp, 110h
0x1800876c6  pop     r15
0x1800876c8  pop     r14
0x1800876ca  pop     r13
0x1800876cc  pop     rdi
0x1800876cd  pop     rsi
0x1800876ce  retn
```
