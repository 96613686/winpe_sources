# TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)

- ea: `0x18003a438`
- end: `0x18003a917`
- name: `?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z`
- size: `1247`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e424`
- `0x180041e58`

## callees

- `0x180002520`
- `0x1800030a0`
- `0x18000955c`
- `0x180009588`
- `0x18000f054`
- `0x18000f0b0`
- `0x18001060c`
- `0x1800118e8`
- `0x180013b8c`
- `0x180014df0`
- `0x180015eb0`
- `0x180016d54`
- `0x1800192f0`
- `0x18001a2d0`
- `0x18001a300`
- `0x180039d00`
- `0x180039d8c`
- `0x18003a438`
- `0x18003ae50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003a5b1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003a696`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003a5b1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003a696`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a5ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a7b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a80c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a5ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a7b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a80c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a6af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a6af`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x18003a51c`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x18003a51c`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003a52c`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003a89a`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003a52c`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18003a89a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall TryGetInterfaceDnsServerView(_QWORD *a1, GUID *a2, int a3)
{
  _QWORD *v5; // rsi
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
  unsigned int i; // ebx
  unsigned int v22; // r15d
  __int64 v23; // r14
  int v24; // eax
  int v25; // eax
  int WellKnownDnsServerTemplate; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  const WCHAR *v29; // rax
  HRESULT v30; // eax
  const WCHAR *v31; // rcx
  __int64 v32; // rdx
  HRESULT v33; // eax
  int v34; // eax
  const char *v35; // r9
  __int64 v36; // rbx
  int View; // eax
  unsigned int v38[2]; // [rsp+20h] [rbp-118h] BYREF
  HSTRING v39[2]; // [rsp+28h] [rbp-110h] BYREF
  HSTRING v40; // [rsp+38h] [rbp-100h] BYREF
  HSTRING string; // [rsp+40h] [rbp-F8h] BYREF
  int v42; // [rsp+48h] [rbp-F0h]
  wchar_t *Context; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD *v44; // [rsp+58h] [rbp-E0h]
  DNS_INTERFACE_SETTINGS Settings; // [rsp+60h] [rbp-D8h] BYREF
  unsigned int v46; // [rsp+B0h] [rbp-88h]
  __int64 v47; // [rsp+B8h] [rbp-80h]
  __int128 v48; // [rsp+D0h] [rbp-68h] BYREF
  UINT32 length[4]; // [rsp+E0h] [rbp-58h]
  GUID Interface; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v5 = a1;
  v44 = a1;
  *a1 = 0;
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
    v10 = 81;
LABEL_49:
    wil::details::in1diag3::_Log_Hr(
      v9,
      (void *)v10,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)v8,
      v38[0]);
    goto LABEL_50;
  }
  memset_0(&Settings, 0, 0x70u);
  Settings.Version = 3;
  v11 = 4098;
  if ( a3 == 6 )
    v11 = 4099;
  Settings.Flags = v11;
  Interface = *a2;
  InterfaceDnsSettings = GetInterfaceDnsSettings(&Interface, &Settings);
  if ( InterfaceDnsSettings == 2 )
  {
    FreeInterfaceDnsSettings(&Settings);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v38);
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
        v38[0]);
    if ( Settings.NameServer )
    {
      v14 = -1;
      do
        ++v14;
      while ( Settings.NameServer[v14] );
      if ( v14 )
      {
        *(_QWORD *)&Interface.Data1 = 0x3B002C0020LL;
        Context = 0;
        v15 = wcstok_s(Settings.NameServer, (const wchar_t *)&Interface, &Context);
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
              (void *)0x73,
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
          v48 = *(_OWORD *)v39;
          *(_QWORD *)length = 0;
          LOBYTE(v19) = 1;
          v20 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
                  *(_QWORD *)v38,
                  0,
                  &v48,
                  v19);
          if ( v20 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x79,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v20,
              v38[0]);
          v15 = wcstok_s(0, (const wchar_t *)&Interface, &Context);
          FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v39);
          WindowsDeleteString(string);
          string = 0;
        }
        for ( i = 0; i < v46; ++i )
        {
          v22 = *(_DWORD *)(v47 + 24LL * i + 4);
          v23 = *(_QWORD *)(v47 + 24LL * i + 16);
          *(_OWORD *)v39 = 0;
          v40 = 0;
          v24 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                  *(_QWORD *)v38,
                  v22,
                  v39);
          if ( v24 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x83,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v24,
              v38[0]);
          v25 = HIDWORD(v39[0]);
          if ( (*(_BYTE *)(v23 + 8) & 4) != 0 )
          {
            v25 = HIDWORD(v39[0]) | 4;
            HIDWORD(v39[0]) |= 4u;
          }
          if ( (*(_BYTE *)(v23 + 8) & 1) != 0 )
          {
            v25 |= 1u;
            HIDWORD(v39[0]) = v25;
            if ( LOBYTE(v39[0]) )
            {
              std::wstring::wstring(&v48);
              WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v39[1]);
              if ( WellKnownDnsServerTemplate < 0 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0x90,
                  (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                  (const char *)(unsigned int)WellKnownDnsServerTemplate,
                  v38[0]);
              v29 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v48, v27, v28);
              v30 = WindowsCreateString(v29, length[0], &v40);
              if ( v30 < 0 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0x91,
                  (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                  (const char *)(unsigned int)v30,
                  v38[0]);
              std::wstring::_Tidy_deallocate(&v48);
              v25 = HIDWORD(v39[0]);
            }
          }
          if ( (*(_BYTE *)(v23 + 8) & 2) != 0 )
          {
            HIDWORD(v39[0]) = v25 | 2;
            v31 = *(const WCHAR **)v23;
            v32 = -1;
            do
              ++v32;
            while ( v31[v32] );
            v33 = WindowsCreateString(v31, v32, &v40);
            if ( v33 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x99,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v33,
                v38[0]);
          }
          v48 = *(_OWORD *)v39;
          *(_QWORD *)length = v40;
          v34 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(
                  *(_QWORD *)v38,
                  v22,
                  &v48);
          if ( v34 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x9C,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v34,
              v38[0]);
          FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v39);
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
      v35);
    v5 = v44;
  }
  v36 = *(_QWORD *)v38;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v5);
  View = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(
           v36,
           v5);
  v9 = retaddr;
  if ( View < 0 )
  {
    v8 = (unsigned int)View;
    v10 = 162;
    goto LABEL_49;
  }
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v38);
  return v5;
}

```

## disassembly

```asm
0x18003a438  mov     [rsp+arg_10], rbx
0x18003a43d  push    rsi
0x18003a43e  push    rdi
0x18003a43f  push    r13
0x18003a441  push    r14
0x18003a443  push    r15
0x18003a445  sub     rsp, 110h
0x18003a44c  mov     rax, cs:__security_cookie
0x18003a453  xor     rax, rsp
0x18003a456  mov     [rsp+138h+var_38], rax
0x18003a45e  mov     ebx, r8d
0x18003a461  mov     r14, rdx
0x18003a464  mov     rsi, rcx
0x18003a467  mov     [rsp+138h+var_E0], rcx
0x18003a46c  mov     [rsp+138h+var_F0], 1
0x18003a474  xor     edi, edi
0x18003a476  mov     [rcx], rdi
0x18003a479  mov     [rsp+138h+var_F0], 1
0x18003a481  mov     qword ptr [rsp+138h+var_118], rdi
0x18003a486  lea     rcx, [rsp+138h+var_118]
0x18003a48b  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003a490  mov     qword ptr [rsp+138h+var_118], rdi; int
0x18003a495  lea     rcx, [rsp+138h+Interface]
0x18003a49d  call    ??$Make@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEBUDnsServerEqualityPredicate@2UX@Networking@5@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@@12@AEBUDnsServerEqualityPredicate@Internal@UX@Networking@Windows@@$$QEAUpermission@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@5Collections@Foundation@8@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>,Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission>(Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission &&)
0x18003a4a2  mov     rax, qword ptr [rsp+138h+Interface.Data1]
0x18003a4aa  test    rax, rax
0x18003a4ad  jz      short loc_18003A4B9
0x18003a4af  mov     r9d, edi
0x18003a4b2  mov     qword ptr [rsp+138h+var_118], rax
0x18003a4b7  jmp     short loc_18003A4BF
0x18003a4b9  mov     r9d, 8007000Eh
0x18003a4bf  mov     rcx, [rsp+138h]
0x18003a4c7  test    r9d, r9d
0x18003a4ca  jns     short loc_18003A4D6
0x18003a4cc  mov     edx, 51h ; 'Q'
0x18003a4d1  jmp     loc_18003A8D4
0x18003a4d6  xor     edx, edx; Val
0x18003a4d8  lea     r8d, [rdx+70h]; Size
0x18003a4dc  lea     rcx, [rsp+138h+Settings]; void *
0x18003a4e1  call    memset_0
0x18003a4e6  nop
0x18003a4e7  mov     [rsp+138h+Settings.Version], 3
0x18003a4ef  mov     eax, 1002h
0x18003a4f4  lea     ecx, [rax+1]
0x18003a4f7  cmp     ebx, 6
0x18003a4fa  cmovz   eax, ecx
0x18003a4fd  mov     [rsp+138h+Settings.Flags], rax
0x18003a502  movups  xmm0, xmmword ptr [r14]
0x18003a506  movdqu  xmmword ptr [rsp+138h+Interface.Data1], xmm0
0x18003a50f  lea     rdx, [rsp+138h+Settings]; Settings
0x18003a514  lea     rcx, [rsp+138h+Interface]; Interface
0x18003a51c  call    cs:__imp_GetInterfaceDnsSettings
0x18003a522  cmp     eax, 2
0x18003a525  jnz     short loc_18003A546
0x18003a527  lea     rcx, [rsp+138h+Settings]; Settings
0x18003a52c  call    cs:__imp_FreeInterfaceDnsSettings
0x18003a532  nop
0x18003a533  lea     rcx, [rsp+138h+var_118]
0x18003a538  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003a53d  nop
0x18003a53e  mov     rax, rsi
0x18003a541  jmp     loc_18003A8EF
0x18003a546  mov     rcx, [rsp+138h]; this
0x18003a54e  test    eax, eax
0x18003a550  jz      short loc_18003A566
0x18003a552  mov     r9d, eax; char *
0x18003a555  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a55c  mov     edx, 66h ; 'f'; void *
0x18003a561  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003a566  mov     rcx, [rsp+138h+Settings.NameServer]; String
0x18003a56b  test    rcx, rcx
0x18003a56e  jz      loc_18003A895
0x18003a574  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003a578  mov     rax, r13
0x18003a57b  inc     rax
0x18003a57e  cmp     [rcx+rax*2], di
0x18003a582  jnz     short loc_18003A57B
0x18003a584  test    rax, rax
0x18003a587  jz      loc_18003A895
0x18003a58d  mov     rax, 3B002C0020h
0x18003a597  mov     qword ptr [rsp+138h+Interface.Data1], rax
0x18003a59f  mov     [rsp+138h+Context], rdi
0x18003a5a4  lea     r8, [rsp+138h+Context]; Context
0x18003a5a9  lea     rdx, [rsp+138h+Interface]; Delimiter
0x18003a5b1  call    cs:__imp_wcstok_s
0x18003a5b7  mov     r14, rax
0x18003a5ba  test    r14, r14
0x18003a5bd  jz      loc_18003A6BF
0x18003a5c3  mov     rbx, r13
0x18003a5c6  inc     rbx
0x18003a5c9  cmp     [r14+rbx*2], di
0x18003a5ce  jnz     short loc_18003A5C6
0x18003a5d0  mov     [rsp+138h+string], rdi
0x18003a5d5  xor     ecx, ecx; string
0x18003a5d7  call    cs:__imp_WindowsDeleteString
0x18003a5dd  mov     [rsp+138h+string], rdi
0x18003a5e2  lea     r8, [rsp+138h+string]; string
0x18003a5e7  mov     edx, ebx; length
0x18003a5e9  mov     rcx, r14; sourceString
0x18003a5ec  call    cs:__imp_WindowsCreateString
0x18003a5f2  mov     rcx, [rsp+138h]; this
0x18003a5fa  test    eax, eax
0x18003a5fc  jns     short loc_18003A612
0x18003a5fe  mov     r9d, eax; char *
0x18003a601  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a608  mov     edx, 73h ; 's'; void *
0x18003a60d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a612  xorps   xmm0, xmm0
0x18003a615  xor     ebx, ebx
0x18003a617  movups  xmmword ptr [rsp+138h+var_110], xmm0
0x18003a61c  mov     [rsp+138h+var_100], rbx
0x18003a621  mov     rcx, [rsp+138h+string]; HSTRING
0x18003a626  mov     [rsp+138h+string], rdi
0x18003a62b  mov     [rsp+138h+var_110+8], rcx
0x18003a630  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x18003a635  mov     byte ptr [rsp+138h+var_110], al
0x18003a639  mov     dword ptr [rsp+138h+var_110+4], edi
0x18003a63d  movups  xmm0, xmmword ptr [rsp+138h+var_110]
0x18003a642  movaps  [rsp+138h+var_68], xmm0
0x18003a64a  mov     qword ptr [rsp+138h+length], rbx
0x18003a652  mov     r9b, 1
0x18003a655  lea     r8, [rsp+138h+var_68]
0x18003a65d  xor     edx, edx
0x18003a65f  mov     rcx, qword ptr [rsp+138h+var_118]
0x18003a664  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x18003a669  mov     rcx, [rsp+138h]; this
0x18003a671  test    eax, eax
0x18003a673  jns     short loc_18003A687
0x18003a675  mov     r9d, eax; char *
0x18003a678  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a67f  lea     edx, [rbx+79h]; void *
0x18003a682  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a687  lea     r8, [rsp+138h+Context]; Context
0x18003a68c  lea     rdx, [rsp+138h+Interface]; Delimiter
0x18003a694  xor     ecx, ecx; String
0x18003a696  call    cs:__imp_wcstok_s
0x18003a69c  mov     r14, rax
0x18003a69f  lea     rcx, [rsp+138h+var_110]; struct Windows::Networking::UX::DnsServer *
0x18003a6a4  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18003a6a9  nop
0x18003a6aa  mov     rcx, [rsp+138h+string]; string
0x18003a6af  call    cs:__imp_WindowsDeleteString
0x18003a6b5  mov     [rsp+138h+string], rdi
0x18003a6ba  jmp     loc_18003A5BA
0x18003a6bf  mov     ebx, edi
0x18003a6c1  cmp     ebx, [rsp+138h+var_88]
0x18003a6c8  jnb     loc_18003A895
0x18003a6ce  mov     eax, ebx
0x18003a6d0  lea     rcx, [rax+rax*2]
0x18003a6d4  mov     rax, [rsp+138h+var_80]
0x18003a6dc  mov     r15d, [rax+rcx*8+4]
0x18003a6e1  mov     r14, [rax+rcx*8+10h]
0x18003a6e6  xorps   xmm0, xmm0
0x18003a6e9  xor     eax, eax
0x18003a6eb  movups  xmmword ptr [rsp+138h+var_110], xmm0
0x18003a6f0  mov     [rsp+138h+var_100], rax
0x18003a6f5  lea     r8, [rsp+138h+var_110]
0x18003a6fa  mov     edx, r15d
0x18003a6fd  mov     rcx, qword ptr [rsp+138h+var_118]
0x18003a702  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x18003a707  mov     rcx, [rsp+138h]; this
0x18003a70f  test    eax, eax
0x18003a711  jns     short loc_18003A727
0x18003a713  mov     r9d, eax; char *
0x18003a716  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a71d  mov     edx, 83h; void *
0x18003a722  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a727  mov     eax, dword ptr [rsp+138h+var_110+4]
0x18003a72b  test    byte ptr [r14+8], 4
0x18003a730  jz      short loc_18003A739
0x18003a732  or      eax, 4
0x18003a735  mov     dword ptr [rsp+138h+var_110+4], eax
0x18003a739  test    byte ptr [r14+8], 1
0x18003a73e  jz      loc_18003A7EA
0x18003a744  or      eax, 1
0x18003a747  mov     dword ptr [rsp+138h+var_110+4], eax
0x18003a74b  cmp     byte ptr [rsp+138h+var_110], dil
0x18003a750  jz      loc_18003A7EA
0x18003a756  lea     rcx, [rsp+138h+var_68]
0x18003a75e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a763  nop
0x18003a764  lea     rdx, [rsp+138h+var_68]
0x18003a76c  mov     rcx, [rsp+138h+var_110+8]; string
0x18003a771  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x18003a776  mov     rcx, [rsp+138h]; this
0x18003a77e  test    eax, eax
0x18003a780  jns     short loc_18003A796
0x18003a782  mov     r9d, eax; char *
0x18003a785  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a78c  mov     edx, 90h; void *
0x18003a791  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a796  lea     rcx, [rsp+138h+var_68]
0x18003a79e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003a7a3  mov     rcx, rax; sourceString
0x18003a7a6  lea     r8, [rsp+138h+var_100]; string
0x18003a7ab  mov     edx, [rsp+138h+length]; length
0x18003a7b2  call    cs:__imp_WindowsCreateString
0x18003a7b8  mov     rcx, [rsp+138h]; this
0x18003a7c0  test    eax, eax
0x18003a7c2  jns     short loc_18003A7D9
0x18003a7c4  mov     r9d, eax; char *
0x18003a7c7  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a7ce  mov     edx, 91h; void *
0x18003a7d3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a7d9  lea     rcx, [rsp+138h+var_68]
0x18003a7e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a7e6  mov     eax, dword ptr [rsp+138h+var_110+4]
0x18003a7ea  test    byte ptr [r14+8], 2
0x18003a7ef  jz      short loc_18003A832
0x18003a7f1  or      eax, 2
0x18003a7f4  mov     dword ptr [rsp+138h+var_110+4], eax
0x18003a7f8  mov     rcx, [r14]; sourceString
0x18003a7fb  mov     rdx, r13
0x18003a7fe  inc     rdx; length
0x18003a801  cmp     [rcx+rdx*2], di
0x18003a805  jnz     short loc_18003A7FE
0x18003a807  lea     r8, [rsp+138h+var_100]; string
0x18003a80c  call    cs:__imp_WindowsCreateString
0x18003a812  mov     rcx, [rsp+138h]; this
0x18003a81a  test    eax, eax
0x18003a81c  jns     short loc_18003A832
0x18003a81e  mov     r9d, eax; char *
0x18003a821  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a828  mov     edx, 99h; void *
0x18003a82d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a832  movups  xmm0, xmmword ptr [rsp+138h+var_110]
0x18003a837  movaps  [rsp+138h+var_68], xmm0
0x18003a83f  movsd   xmm1, [rsp+138h+var_100]
0x18003a845  movsd   qword ptr [rsp+138h+length], xmm1
0x18003a84e  lea     r8, [rsp+138h+var_68]
0x18003a856  mov     edx, r15d
0x18003a859  mov     rcx, qword ptr [rsp+138h+var_118]
0x18003a85e  call    ?SetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(uint,Windows::Networking::UX::DnsServer)
0x18003a863  mov     rcx, [rsp+138h]; this
0x18003a86b  test    eax, eax
0x18003a86d  jns     short loc_18003A884
0x18003a86f  mov     r9d, eax; char *
0x18003a872  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a879  mov     edx, 9Ch; void *
0x18003a87e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a884  lea     rcx, [rsp+138h+var_110]; struct Windows::Networking::UX::DnsServer *
0x18003a889  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18003a88e  inc     ebx
0x18003a890  jmp     loc_18003A6C1
0x18003a895  lea     rcx, [rsp+138h+Settings]; Settings
0x18003a89a  call    cs:__imp_FreeInterfaceDnsSettings
0x18003a8a0  nop
0x18003a8a1  jmp     short loc_18003A8A8
0x18003a8a3  mov     rsi, [rsp+138h+var_E0]
0x18003a8a8  mov     rbx, qword ptr [rsp+138h+var_118]
0x18003a8ad  mov     rcx, rsi
0x18003a8b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a8b5  mov     rdx, rsi
0x18003a8b8  mov     rcx, rbx
0x18003a8bb  call    ?GetView@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> * *)
0x18003a8c0  mov     rcx, [rsp+138h]; this
0x18003a8c8  test    eax, eax
0x18003a8ca  jns     short loc_18003A8E1
0x18003a8cc  mov     r9d, eax; char *
0x18003a8cf  mov     edx, 0A2h; void *
0x18003a8d4  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a8db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a8e0  nop
0x18003a8e1  lea     rcx, [rsp+138h+var_118]
0x18003a8e6  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18003a8eb  nop
0x18003a8ec  mov     rax, rsi
0x18003a8ef  mov     rcx, [rsp+138h+var_38]
0x18003a8f7  xor     rcx, rsp; StackCookie
0x18003a8fa  call    __security_check_cookie
0x18003a8ff  mov     rbx, [rsp+138h+arg_10]
0x18003a907  add     rsp, 110h
0x18003a90e  pop     r15
0x18003a910  pop     r14
0x18003a912  pop     r13
0x18003a914  pop     rdi
0x18003a915  pop     rsi
0x18003a916  retn
```
