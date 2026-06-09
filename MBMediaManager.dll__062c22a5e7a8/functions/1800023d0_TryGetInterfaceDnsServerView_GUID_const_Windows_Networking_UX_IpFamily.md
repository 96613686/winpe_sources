# TryGetInterfaceDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)

- ea: `0x1800023d0`
- end: `0x1800028cd`
- name: `?TryGetInterfaceDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z`
- size: `1277`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003108`
- `0x18002a068`

## callees

- `0x180002150`
- `0x1800023d0`
- `0x1800028d4`
- `0x18000352c`
- `0x1800035d0`
- `0x180003f40`
- `0x180004000`
- `0x18001bdb8`
- `0x18001ec40`
- `0x18001edf0`
- `0x18001eef4`
- `0x18001f5b8`
- `0x18001f7a4`
- `0x18001fa08`
- `0x180024fd0`
- `0x18002cd20`
- `0x18002d20c`
- `0x18002d8c8`
- `0x180036714`
- `0x180052638`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000255d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180002642`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000255d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180002642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000265b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000265b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800027c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800027c2`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800024be`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x1800024be`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800024ce`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x180002850`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x1800024ce`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x180002850`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall TryGetInterfaceDnsServerView(_QWORD *a1, GUID *a2, int a3)
{
  _QWORD *v5; // rsi
  void *v6; // rax
  __int64 v7; // rax
  __int64 v8; // r9
  wil::details::in1diag3 *v9; // rcx
  __int64 v10; // rdx
  ULONG64 v11; // rax
  unsigned int InterfaceDnsSettings; // eax
  __int64 v13; // rcx
  __int64 v15; // rax
  wchar_t *v16; // r14
  __int64 v17; // rbx
  HRESULT v18; // eax
  HSTRING v19; // rcx
  __int64 v20; // r9
  int v21; // eax
  unsigned int i; // ebx
  unsigned int v23; // r15d
  __int64 v24; // r14
  int v25; // eax
  int v26; // eax
  int WellKnownDnsServerTemplate; // eax
  const WCHAR *v28; // rcx
  HRESULT v29; // eax
  const WCHAR *v30; // rcx
  __int64 v31; // rdx
  HRESULT v32; // eax
  int v33; // eax
  const char *v34; // r9
  __int64 v35; // rbx
  int View; // eax
  unsigned int v37[2]; // [rsp+20h] [rbp-118h] BYREF
  HSTRING v38[2]; // [rsp+28h] [rbp-110h] BYREF
  HSTRING v39; // [rsp+38h] [rbp-100h] BYREF
  HSTRING string; // [rsp+40h] [rbp-F8h] BYREF
  int v41; // [rsp+48h] [rbp-F0h]
  wchar_t *Context; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD *v43; // [rsp+58h] [rbp-E0h]
  DNS_INTERFACE_SETTINGS Settings; // [rsp+60h] [rbp-D8h] BYREF
  unsigned int v45; // [rsp+B0h] [rbp-88h]
  __int64 v46; // [rsp+B8h] [rbp-80h]
  PCNZWCH sourceString[2]; // [rsp+D0h] [rbp-68h] BYREF
  UINT32 length[2]; // [rsp+E0h] [rbp-58h]
  unsigned __int64 v49; // [rsp+E8h] [rbp-50h]
  GUID Interface; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v5 = a1;
  v43 = a1;
  *a1 = 0;
  v41 = 1;
  *(_QWORD *)v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v37);
  *(_QWORD *)v37 = 0;
  v6 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6
    && (v7 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>(v6)) != 0 )
  {
    v8 = 0;
    *(_QWORD *)v37 = v7;
  }
  else
  {
    v8 = 2147942414LL;
  }
  v9 = retaddr;
  if ( (int)v8 < 0 )
  {
    v10 = 81;
    goto LABEL_54;
  }
  memset_0(&Settings, 0, 0x70u);
  Settings.Version = 3;
  v11 = 4098;
  if ( a3 == 6 )
    v11 = 4099;
  Settings.Flags = v11;
  Interface = *a2;
  InterfaceDnsSettings = GetInterfaceDnsSettings(&Interface, &Settings);
  if ( InterfaceDnsSettings != 2 )
  {
    try
    {
      if ( InterfaceDnsSettings )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
          (const char *)InterfaceDnsSettings,
          v37[0]);
      if ( Settings.NameServer )
      {
        v15 = -1;
        do
          ++v15;
        while ( Settings.NameServer[v15] );
        if ( v15 )
        {
          *(_QWORD *)&Interface.Data1 = 0x3B002C0020LL;
          Context = 0;
          v16 = wcstok_s(Settings.NameServer, (const wchar_t *)&Interface, &Context);
          while ( v16 )
          {
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            string = 0;
            WindowsDeleteString(0);
            string = 0;
            v18 = WindowsCreateString(v16, v17, &string);
            if ( v18 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x73,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v18,
                v37[0]);
            v38[0] = 0;
            v39 = 0;
            v19 = string;
            string = 0;
            v38[1] = v19;
            LOBYTE(v38[0]) = DnsServerIsWellKnownDoh(v19);
            HIDWORD(v38[0]) = 0;
            *(_OWORD *)sourceString = *(_OWORD *)v38;
            *(_QWORD *)length = 0;
            LOBYTE(v20) = 1;
            v21 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
                    *(_QWORD *)v37,
                    0,
                    sourceString,
                    v20);
            if ( v21 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x79,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v21,
                v37[0]);
            v16 = wcstok_s(0, (const wchar_t *)&Interface, &Context);
            FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v38);
            WindowsDeleteString(string);
            string = 0;
          }
          for ( i = 0; i < v45; ++i )
          {
            v23 = *(_DWORD *)(v46 + 24LL * i + 4);
            v24 = *(_QWORD *)(v46 + 24LL * i + 16);
            *(_OWORD *)v38 = 0;
            v39 = 0;
            v25 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                    *(_QWORD *)v37,
                    v23,
                    v38);
            if ( v25 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x83,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v25,
                v37[0]);
            v26 = HIDWORD(v38[0]);
            if ( (*(_BYTE *)(v24 + 8) & 4) != 0 )
            {
              v26 = HIDWORD(v38[0]) | 4;
              HIDWORD(v38[0]) |= 4u;
            }
            if ( (*(_BYTE *)(v24 + 8) & 1) != 0 )
            {
              v26 |= 1u;
              HIDWORD(v38[0]) = v26;
              if ( LOBYTE(v38[0]) )
              {
                std::wstring::wstring(sourceString);
                WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v38[1]);
                if ( WellKnownDnsServerTemplate < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x90,
                    (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                    (const char *)(unsigned int)WellKnownDnsServerTemplate,
                    v37[0]);
                v28 = (const WCHAR *)sourceString;
                if ( v49 > 7 )
                  v28 = sourceString[0];
                v29 = WindowsCreateString(v28, length[0], &v39);
                if ( v29 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x91,
                    (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                    (const char *)(unsigned int)v29,
                    v37[0]);
                std::wstring::_Tidy_deallocate(sourceString);
                v26 = HIDWORD(v38[0]);
              }
            }
            if ( (*(_BYTE *)(v24 + 8) & 2) != 0 )
            {
              HIDWORD(v38[0]) = v26 | 2;
              v30 = *(const WCHAR **)v24;
              v31 = -1;
              do
                ++v31;
              while ( v30[v31] );
              v32 = WindowsCreateString(v30, v31, &v39);
              if ( v32 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x99,
                  (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                  (const char *)(unsigned int)v32,
                  v37[0]);
            }
            *(_OWORD *)sourceString = *(_OWORD *)v38;
            *(_QWORD *)length = v39;
            v33 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(
                    *(_QWORD *)v37,
                    v23,
                    sourceString);
            if ( v33 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x9C,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v33,
                v37[0]);
            FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v38);
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
        v34);
      v5 = v43;
    }
    v35 = *(_QWORD *)v37;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
    View = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(
             v35,
             v5);
    v9 = retaddr;
    if ( View >= 0 )
      goto LABEL_55;
    v8 = (unsigned int)View;
    v10 = 162;
LABEL_54:
    wil::details::in1diag3::_Log_Hr(
      v9,
      (void *)v10,
      (int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)v8);
LABEL_55:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v37);
    return v5;
  }
  FreeInterfaceDnsSettings(&Settings);
  v13 = *(_QWORD *)v37;
  if ( *(_QWORD *)v37 )
  {
    *(_QWORD *)v37 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Networking::UX::DnsServer>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::DnsServer>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(v13);
  }
  return v5;
}

```

## disassembly

```asm
0x1800023d0  mov     [rsp+arg_10], rbx
0x1800023d5  push    rsi
0x1800023d6  push    rdi
0x1800023d7  push    r13
0x1800023d9  push    r14
0x1800023db  push    r15
0x1800023dd  sub     rsp, 110h
0x1800023e4  mov     rax, cs:__security_cookie
0x1800023eb  xor     rax, rsp
0x1800023ee  mov     [rsp+138h+var_38], rax
0x1800023f6  mov     ebx, r8d
0x1800023f9  mov     r14, rdx
0x1800023fc  mov     rsi, rcx
0x1800023ff  mov     [rsp+138h+var_E0], rcx
0x180002404  mov     [rsp+138h+var_F0], 1
0x18000240c  xor     edi, edi
0x18000240e  mov     [rcx], rdi
0x180002411  mov     [rsp+138h+var_F0], 1
0x180002419  mov     qword ptr [rsp+138h+var_118], rdi
0x18000241e  lea     rcx, [rsp+138h+var_118]
0x180002423  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x180002428  mov     qword ptr [rsp+138h+var_118], rdi; int
0x18000242d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002434  mov     ecx, 90h; unsigned __int64
0x180002439  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000243e  test    rax, rax
0x180002441  jz      short loc_18000245B
0x180002443  mov     rcx, rax
0x180002446  call    ??0?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@QEAA@AEBUDnsServerEqualityPredicate@1UX@Networking@4@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>(Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission)
0x18000244b  nop
0x18000244c  test    rax, rax
0x18000244f  jz      short loc_18000245B
0x180002451  mov     r9d, edi
0x180002454  mov     qword ptr [rsp+138h+var_118], rax
0x180002459  jmp     short loc_180002461
0x18000245b  mov     r9d, 8007000Eh
0x180002461  mov     rcx, [rsp+138h]
0x180002469  test    r9d, r9d
0x18000246c  jns     short loc_180002478
0x18000246e  mov     edx, 51h ; 'Q'
0x180002473  jmp     loc_18000288A
0x180002478  xor     edx, edx; Val
0x18000247a  lea     r8d, [rdx+70h]; Size
0x18000247e  lea     rcx, [rsp+138h+Settings]; void *
0x180002483  call    memset_0
0x180002488  nop
0x180002489  mov     [rsp+138h+Settings.Version], 3
0x180002491  mov     eax, 1002h
0x180002496  lea     ecx, [rax+1]
0x180002499  cmp     ebx, 6
0x18000249c  cmovz   eax, ecx
0x18000249f  mov     [rsp+138h+Settings.Flags], rax
0x1800024a4  movups  xmm0, xmmword ptr [r14]
0x1800024a8  movdqu  xmmword ptr [rsp+138h+Interface.Data1], xmm0
0x1800024b1  lea     rdx, [rsp+138h+Settings]; Settings
0x1800024b6  lea     rcx, [rsp+138h+Interface]; Interface
0x1800024be  call    cs:__imp_GetInterfaceDnsSettings
0x1800024c4  cmp     eax, 2
0x1800024c7  jnz     short loc_1800024F2
0x1800024c9  lea     rcx, [rsp+138h+Settings]; Settings
0x1800024ce  call    cs:__imp_FreeInterfaceDnsSettings
0x1800024d4  nop
0x1800024d5  mov     rcx, qword ptr [rsp+138h+var_118]
0x1800024da  test    rcx, rcx
0x1800024dd  jz      short loc_1800024EA
0x1800024df  mov     qword ptr [rsp+138h+var_118], rdi
0x1800024e4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$IIterable@UDnsServer@UX@Networking@Windows@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::Networking::UX::DnsServer>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::DnsServer>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x1800024e9  nop
0x1800024ea  mov     rax, rsi
0x1800024ed  jmp     loc_1800028A5
0x1800024f2  mov     rcx, [rsp+138h]; this
0x1800024fa  test    eax, eax
0x1800024fc  jz      short loc_180002512
0x1800024fe  mov     r9d, eax; char *
0x180002501  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180002508  mov     edx, 66h ; 'f'; void *
0x18000250d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180002512  mov     rcx, [rsp+138h+Settings.NameServer]; String
0x180002517  test    rcx, rcx
0x18000251a  jz      loc_18000284B
0x180002520  or      r13, 0FFFFFFFFFFFFFFFFh
0x180002524  mov     rax, r13
0x180002527  inc     rax
0x18000252a  cmp     [rcx+rax*2], di
0x18000252e  jnz     short loc_180002527
0x180002530  test    rax, rax
0x180002533  jz      loc_18000284B
0x180002539  mov     rax, 3B002C0020h
0x180002543  mov     qword ptr [rsp+138h+Interface.Data1], rax
0x18000254b  mov     [rsp+138h+Context], rdi
0x180002550  lea     r8, [rsp+138h+Context]; Context
0x180002555  lea     rdx, [rsp+138h+Interface]; Delimiter
0x18000255d  call    cs:__imp_wcstok_s
0x180002563  mov     r14, rax
0x180002566  test    r14, r14
0x180002569  jz      loc_18000266B
0x18000256f  mov     rbx, r13
0x180002572  inc     rbx
0x180002575  cmp     [r14+rbx*2], di
0x18000257a  jnz     short loc_180002572
0x18000257c  mov     [rsp+138h+string], rdi
0x180002581  xor     ecx, ecx; string
0x180002583  call    cs:__imp_WindowsDeleteString
0x180002589  mov     [rsp+138h+string], rdi
0x18000258e  lea     r8, [rsp+138h+string]; string
0x180002593  mov     edx, ebx; length
0x180002595  mov     rcx, r14; sourceString
0x180002598  call    cs:__imp_WindowsCreateString
0x18000259e  mov     rcx, [rsp+138h]; this
0x1800025a6  test    eax, eax
0x1800025a8  jns     short loc_1800025BE
0x1800025aa  mov     r9d, eax; char *
0x1800025ad  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800025b4  mov     edx, 73h ; 's'; void *
0x1800025b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800025be  xorps   xmm0, xmm0
0x1800025c1  xor     ebx, ebx
0x1800025c3  movups  xmmword ptr [rsp+138h+var_110], xmm0
0x1800025c8  mov     [rsp+138h+var_100], rbx
0x1800025cd  mov     rcx, [rsp+138h+string]; HSTRING
0x1800025d2  mov     [rsp+138h+string], rdi
0x1800025d7  mov     [rsp+138h+var_110+8], rcx
0x1800025dc  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x1800025e1  mov     byte ptr [rsp+138h+var_110], al
0x1800025e5  mov     dword ptr [rsp+138h+var_110+4], edi
0x1800025e9  movups  xmm0, xmmword ptr [rsp+138h+var_110]
0x1800025ee  movaps  xmmword ptr [rsp+138h+sourceString], xmm0
0x1800025f6  mov     qword ptr [rsp+138h+length], rbx
0x1800025fe  mov     r9b, 1
0x180002601  lea     r8, [rsp+138h+sourceString]
0x180002609  xor     edx, edx
0x18000260b  mov     rcx, qword ptr [rsp+138h+var_118]
0x180002610  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180002615  mov     rcx, [rsp+138h]; this
0x18000261d  test    eax, eax
0x18000261f  jns     short loc_180002633
0x180002621  mov     r9d, eax; char *
0x180002624  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18000262b  lea     edx, [rbx+79h]; void *
0x18000262e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002633  lea     r8, [rsp+138h+Context]; Context
0x180002638  lea     rdx, [rsp+138h+Interface]; Delimiter
0x180002640  xor     ecx, ecx; String
0x180002642  call    cs:__imp_wcstok_s
0x180002648  mov     r14, rax
0x18000264b  lea     rcx, [rsp+138h+var_110]; struct Windows::Networking::UX::DnsServer *
0x180002650  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180002655  nop
0x180002656  mov     rcx, [rsp+138h+string]; string
0x18000265b  call    cs:__imp_WindowsDeleteString
0x180002661  mov     [rsp+138h+string], rdi
0x180002666  jmp     loc_180002566
0x18000266b  mov     ebx, edi
0x18000266d  cmp     ebx, [rsp+138h+var_88]
0x180002674  jnb     loc_18000284B
0x18000267a  mov     eax, ebx
0x18000267c  lea     rcx, [rax+rax*2]
0x180002680  mov     rax, [rsp+138h+var_80]
0x180002688  mov     r15d, [rax+rcx*8+4]
0x18000268d  mov     r14, [rax+rcx*8+10h]
0x180002692  xorps   xmm0, xmm0
0x180002695  xor     eax, eax
0x180002697  movups  xmmword ptr [rsp+138h+var_110], xmm0
0x18000269c  mov     [rsp+138h+var_100], rax
0x1800026a1  lea     r8, [rsp+138h+var_110]
0x1800026a6  mov     edx, r15d
0x1800026a9  mov     rcx, qword ptr [rsp+138h+var_118]
0x1800026ae  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x1800026b3  mov     rcx, [rsp+138h]; this
0x1800026bb  test    eax, eax
0x1800026bd  jns     short loc_1800026D3
0x1800026bf  mov     r9d, eax; char *
0x1800026c2  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800026c9  mov     edx, 83h; void *
0x1800026ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800026d3  mov     eax, dword ptr [rsp+138h+var_110+4]
0x1800026d7  test    byte ptr [r14+8], 4
0x1800026dc  jz      short loc_1800026E5
0x1800026de  or      eax, 4
0x1800026e1  mov     dword ptr [rsp+138h+var_110+4], eax
0x1800026e5  test    byte ptr [r14+8], 1
0x1800026ea  jz      loc_1800027A0
0x1800026f0  or      eax, 1
0x1800026f3  mov     dword ptr [rsp+138h+var_110+4], eax
0x1800026f7  cmp     byte ptr [rsp+138h+var_110], dil
0x1800026fc  jz      loc_1800027A0
0x180002702  lea     rcx, [rsp+138h+sourceString]
0x18000270a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000270f  nop
0x180002710  lea     rdx, [rsp+138h+sourceString]
0x180002718  mov     rcx, [rsp+138h+var_110+8]; string
0x18000271d  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x180002722  mov     rcx, [rsp+138h]; this
0x18000272a  test    eax, eax
0x18000272c  jns     short loc_180002742
0x18000272e  mov     r9d, eax; char *
0x180002731  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180002738  mov     edx, 90h; void *
0x18000273d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002742  lea     rcx, [rsp+138h+sourceString]
0x18000274a  cmp     [rsp+138h+var_50], 7
0x180002753  cmova   rcx, [rsp+138h+sourceString]; sourceString
0x18000275c  lea     r8, [rsp+138h+var_100]; string
0x180002761  mov     edx, [rsp+138h+length]; length
0x180002768  call    cs:__imp_WindowsCreateString
0x18000276e  mov     rcx, [rsp+138h]; this
0x180002776  test    eax, eax
0x180002778  jns     short loc_18000278F
0x18000277a  mov     r9d, eax; char *
0x18000277d  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180002784  mov     edx, 91h; void *
0x180002789  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000278f  lea     rcx, [rsp+138h+sourceString]
0x180002797  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000279c  mov     eax, dword ptr [rsp+138h+var_110+4]
0x1800027a0  test    byte ptr [r14+8], 2
0x1800027a5  jz      short loc_1800027E8
0x1800027a7  or      eax, 2
0x1800027aa  mov     dword ptr [rsp+138h+var_110+4], eax
0x1800027ae  mov     rcx, [r14]; sourceString
0x1800027b1  mov     rdx, r13
0x1800027b4  inc     rdx; length
0x1800027b7  cmp     [rcx+rdx*2], di
0x1800027bb  jnz     short loc_1800027B4
0x1800027bd  lea     r8, [rsp+138h+var_100]; string
0x1800027c2  call    cs:__imp_WindowsCreateString
0x1800027c8  mov     rcx, [rsp+138h]; this
0x1800027d0  test    eax, eax
0x1800027d2  jns     short loc_1800027E8
0x1800027d4  mov     r9d, eax; char *
0x1800027d7  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800027de  mov     edx, 99h; void *
0x1800027e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800027e8  movups  xmm0, xmmword ptr [rsp+138h+var_110]
0x1800027ed  movaps  xmmword ptr [rsp+138h+sourceString], xmm0
0x1800027f5  movsd   xmm1, [rsp+138h+var_100]
0x1800027fb  movsd   qword ptr [rsp+138h+length], xmm1
0x180002804  lea     r8, [rsp+138h+sourceString]
0x18000280c  mov     edx, r15d
0x18000280f  mov     rcx, qword ptr [rsp+138h+var_118]
0x180002814  call    ?SetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(uint,Windows::Networking::UX::DnsServer)
0x180002819  mov     rcx, [rsp+138h]; this
0x180002821  test    eax, eax
0x180002823  jns     short loc_18000283A
0x180002825  mov     r9d, eax; char *
0x180002828  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18000282f  mov     edx, 9Ch; void *
0x180002834  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000283a  lea     rcx, [rsp+138h+var_110]; struct Windows::Networking::UX::DnsServer *
0x18000283f  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180002844  inc     ebx
0x180002846  jmp     loc_18000266D
0x18000284b  lea     rcx, [rsp+138h+Settings]; Settings
0x180002850  call    cs:__imp_FreeInterfaceDnsSettings
0x180002856  nop
0x180002857  jmp     short loc_18000285E
0x180002859  mov     rsi, [rsp+138h+var_E0]
0x18000285e  mov     rbx, qword ptr [rsp+138h+var_118]
0x180002863  mov     rcx, rsi
0x180002866  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000286b  mov     rdx, rsi
0x18000286e  mov     rcx, rbx
0x180002871  call    ?GetView@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> * *)
0x180002876  mov     rcx, [rsp+138h]; this
0x18000287e  test    eax, eax
0x180002880  jns     short loc_180002897
0x180002882  mov     r9d, eax; char *
0x180002885  mov     edx, 0A2h; void *
0x18000288a  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180002891  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002896  nop
0x180002897  lea     rcx, [rsp+138h+var_118]
0x18000289c  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x1800028a1  nop
0x1800028a2  mov     rax, rsi
0x1800028a5  mov     rcx, [rsp+138h+var_38]
0x1800028ad  xor     rcx, rsp; StackCookie
0x1800028b0  call    __security_check_cookie
0x1800028b5  mov     rbx, [rsp+138h+arg_10]
0x1800028bd  add     rsp, 110h
0x1800028c4  pop     r15
0x1800028c6  pop     r14
0x1800028c8  pop     r13
0x1800028ca  pop     rdi
0x1800028cb  pop     rsi
0x1800028cc  retn
```
