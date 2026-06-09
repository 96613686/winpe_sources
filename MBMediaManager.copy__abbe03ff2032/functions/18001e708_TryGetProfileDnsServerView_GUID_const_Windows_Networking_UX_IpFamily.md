# TryGetProfileDnsServerView(_GUID const &,Windows::Networking::UX::IpFamily)

- ea: `0x18001e708`
- end: `0x18001ec19`
- name: `?TryGetProfileDnsServerView@@YA?AV?$ComPtr@U?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBU_GUID@@W4IpFamily@UX@Networking@Windows@@@Z`
- size: `1297`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003108`

## callees

- `0x180002150`
- `0x1800028d4`
- `0x18000352c`
- `0x1800035d0`
- `0x180003f40`
- `0x180004000`
- `0x18001bdb8`
- `0x18001e708`
- `0x18001ec20`
- `0x18001ec40`
- `0x18001edf0`
- `0x18001eef4`
- `0x18001f5b8`
- `0x18001f7a4`
- `0x18001fa08`
- `0x18002cd20`
- `0x18002d20c`
- `0x18002d8c8`
- `0x180036714`
- `0x180052638`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001e8a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001e98e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001e8a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001e98e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e9a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e9a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e8e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001eab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001eb0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e8e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001eab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001eb0e`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x18001e80f`
- `IPHLPAPI!GetInterfaceDnsSettings` at `0x18001e80f`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18001e81f`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18001eb9c`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18001e81f`
- `IPHLPAPI!FreeInterfaceDnsSettings` at `0x18001eb9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall TryGetProfileDnsServerView(_QWORD *a1, GUID *a2, int a3)
{
  _QWORD *v5; // rsi
  HSTRING v6; // rax
  __int64 v7; // rbx
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
  const WCHAR *v27; // rcx
  HRESULT v28; // eax
  const WCHAR *v29; // rcx
  __int64 v30; // rdx
  HRESULT v31; // eax
  int v32; // eax
  const char *v33; // r9
  __int64 v34; // rbx
  int View; // eax
  unsigned int v36[2]; // [rsp+20h] [rbp-118h] BYREF
  HSTRING string; // [rsp+28h] [rbp-110h] BYREF
  HSTRING v38[2]; // [rsp+30h] [rbp-108h] BYREF
  HSTRING v39; // [rsp+40h] [rbp-F8h] BYREF
  int v40; // [rsp+48h] [rbp-F0h]
  wchar_t *Context; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD *v42; // [rsp+58h] [rbp-E0h]
  DNS_INTERFACE_SETTINGS Settings; // [rsp+60h] [rbp-D8h] BYREF
  unsigned int v44; // [rsp+C0h] [rbp-78h]
  __int64 v45; // [rsp+C8h] [rbp-70h]
  PCNZWCH sourceString[2]; // [rsp+D0h] [rbp-68h] BYREF
  UINT32 length[2]; // [rsp+E0h] [rbp-58h]
  unsigned __int64 v48; // [rsp+E8h] [rbp-50h]
  GUID Interface; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v5 = a1;
  v42 = a1;
  *a1 = 0;
  v40 = 1;
  *(_QWORD *)v36 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
  *(_QWORD *)v36 = 0;
  v6 = (HSTRING)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  string = v6;
  v7 = 0;
  if ( v6 )
  {
    v7 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>(v6);
    string = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>::~MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>(&string);
  if ( v7 )
  {
    v8 = 0;
    *(_QWORD *)v36 = v7;
  }
  else
  {
    v8 = 2147942414LL;
  }
  v9 = retaddr;
  if ( (int)v8 < 0 )
  {
    v10 = 171;
LABEL_53:
    wil::details::in1diag3::_Log_Hr(
      v9,
      (void *)v10,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      (const char *)v8,
      v36[0]);
    goto LABEL_54;
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
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
    return v5;
  }
  try
  {
    if ( InterfaceDnsSettings )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
        (const char *)InterfaceDnsSettings,
        v36[0]);
    if ( Settings.ProfileNameServer )
    {
      v14 = -1;
      do
        ++v14;
      while ( Settings.ProfileNameServer[v14] );
      if ( v14 )
      {
        *(_QWORD *)&Interface.Data1 = 0x3B002C0020LL;
        Context = 0;
        v15 = wcstok_s(Settings.ProfileNameServer, (const wchar_t *)&Interface, &Context);
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
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xCC,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v17,
              v36[0]);
          v38[0] = 0;
          v39 = 0;
          v18 = string;
          string = 0;
          v38[1] = v18;
          LOBYTE(v38[0]) = DnsServerIsWellKnownDoh(v18);
          HIDWORD(v38[0]) = 0;
          *(_OWORD *)sourceString = *(_OWORD *)v38;
          *(_QWORD *)length = 0;
          LOBYTE(v19) = 1;
          v20 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
                  *(_QWORD *)v36,
                  0,
                  sourceString,
                  v19);
          if ( v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD2,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v20,
              v36[0]);
          v15 = wcstok_s(0, (const wchar_t *)&Interface, &Context);
          FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v38);
          WindowsDeleteString(string);
          string = 0;
        }
        for ( i = 0; i < v44; ++i )
        {
          v22 = *(_DWORD *)(v45 + 24LL * i + 4);
          v23 = *(_QWORD *)(v45 + 24LL * i + 16);
          *(_OWORD *)v38 = 0;
          v39 = 0;
          v24 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                  *(_QWORD *)v36,
                  v22,
                  v38);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xDC,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v24,
              v36[0]);
          v25 = HIDWORD(v38[0]);
          if ( (*(_BYTE *)(v23 + 8) & 4) != 0 )
          {
            v25 = HIDWORD(v38[0]) | 4;
            HIDWORD(v38[0]) |= 4u;
          }
          if ( (*(_BYTE *)(v23 + 8) & 1) != 0 )
          {
            v25 |= 1u;
            HIDWORD(v38[0]) = v25;
            if ( LOBYTE(v38[0]) )
            {
              std::wstring::wstring(sourceString);
              WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v38[1]);
              if ( WellKnownDnsServerTemplate < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE8,
                  (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                  (const char *)(unsigned int)WellKnownDnsServerTemplate,
                  v36[0]);
              v27 = (const WCHAR *)sourceString;
              if ( v48 > 7 )
                v27 = sourceString[0];
              v28 = WindowsCreateString(v27, length[0], &v39);
              if ( v28 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xE9,
                  (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                  (const char *)(unsigned int)v28,
                  v36[0]);
              std::wstring::_Tidy_deallocate(sourceString);
              v25 = HIDWORD(v38[0]);
            }
          }
          if ( (*(_BYTE *)(v23 + 8) & 2) != 0 )
          {
            HIDWORD(v38[0]) = v25 | 2;
            v29 = *(const WCHAR **)v23;
            v30 = -1;
            do
              ++v30;
            while ( v29[v30] );
            v31 = WindowsCreateString(v29, v30, &v39);
            if ( v31 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xF1,
                (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
                (const char *)(unsigned int)v31,
                v36[0]);
          }
          *(_OWORD *)sourceString = *(_OWORD *)v38;
          *(_QWORD *)length = v39;
          v32 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(
                  *(_QWORD *)v36,
                  v22,
                  sourceString);
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xF4,
              (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
              (const char *)(unsigned int)v32,
              v36[0]);
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
      (void *)0xF8,
      (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
      v33);
    v5 = v42;
  }
  v34 = *(_QWORD *)v36;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
  View = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(
           v34,
           v5);
  v9 = retaddr;
  if ( View < 0 )
  {
    v8 = (unsigned int)View;
    v10 = 250;
    goto LABEL_53;
  }
LABEL_54:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(v36);
  return v5;
}

```

## disassembly

```asm
0x18001e708  mov     [rsp+arg_10], rbx
0x18001e70d  push    rsi
0x18001e70e  push    rdi
0x18001e70f  push    r13
0x18001e711  push    r14
0x18001e713  push    r15
0x18001e715  sub     rsp, 110h
0x18001e71c  mov     rax, cs:__security_cookie
0x18001e723  xor     rax, rsp
0x18001e726  mov     [rsp+138h+var_38], rax
0x18001e72e  mov     r14d, r8d
0x18001e731  mov     r15, rdx
0x18001e734  mov     rsi, rcx
0x18001e737  mov     [rsp+138h+var_E0], rcx
0x18001e73c  mov     [rsp+138h+var_F0], 1
0x18001e744  xor     edi, edi
0x18001e746  mov     [rcx], rdi
0x18001e749  mov     [rsp+138h+var_F0], 1
0x18001e751  mov     qword ptr [rsp+138h+var_118], rdi
0x18001e756  lea     rcx, [rsp+138h+var_118]
0x18001e75b  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18001e760  mov     qword ptr [rsp+138h+var_118], rdi
0x18001e765  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e76c  mov     ecx, 90h; unsigned __int64
0x18001e771  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e776  mov     [rsp+138h+string], rax
0x18001e77b  mov     ebx, edi
0x18001e77d  test    rax, rax
0x18001e780  jz      short loc_18001E792
0x18001e782  mov     rcx, rax
0x18001e785  call    ??0?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@QEAA@AEBUDnsServerEqualityPredicate@1UX@Networking@4@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>(Windows::Networking::UX::Internal::DnsServerEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::permission)
0x18001e78a  mov     rbx, rax
0x18001e78d  mov     [rsp+138h+string], rdi
0x18001e792  lea     rcx, [rsp+138h+string]
0x18001e797  call    ??1?$MakeAllocator@VMBMediaManager@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>::~MakeAllocator<Windows::Networking::UX::Internal::MBMediaManager>(void)
0x18001e79c  test    rbx, rbx
0x18001e79f  jnz     short loc_18001E7A9
0x18001e7a1  mov     r9d, 8007000Eh
0x18001e7a7  jmp     short loc_18001E7B1
0x18001e7a9  mov     r9d, edi
0x18001e7ac  mov     qword ptr [rsp+138h+var_118], rbx; int
0x18001e7b1  mov     rcx, [rsp+138h]
0x18001e7b9  test    r9d, r9d
0x18001e7bc  jns     short loc_18001E7C8
0x18001e7be  mov     edx, 0ABh
0x18001e7c3  jmp     loc_18001EBD6
0x18001e7c8  xor     edx, edx; Val
0x18001e7ca  lea     r8d, [rdx+70h]; Size
0x18001e7ce  lea     rcx, [rsp+138h+Settings]; void *
0x18001e7d3  call    memset_0
0x18001e7d8  nop
0x18001e7d9  mov     [rsp+138h+Settings.Version], 3
0x18001e7e1  mov     eax, 2200h
0x18001e7e6  lea     ecx, [rax+1]
0x18001e7e9  cmp     r14d, 6
0x18001e7ed  cmovz   eax, ecx
0x18001e7f0  mov     [rsp+138h+Settings.Flags], rax
0x18001e7f5  movups  xmm0, xmmword ptr [r15]
0x18001e7f9  movdqu  xmmword ptr [rsp+138h+Interface.Data1], xmm0
0x18001e802  lea     rdx, [rsp+138h+Settings]; Settings
0x18001e807  lea     rcx, [rsp+138h+Interface]; Interface
0x18001e80f  call    cs:__imp_GetInterfaceDnsSettings
0x18001e815  cmp     eax, 2
0x18001e818  jnz     short loc_18001E839
0x18001e81a  lea     rcx, [rsp+138h+Settings]; Settings
0x18001e81f  call    cs:__imp_FreeInterfaceDnsSettings
0x18001e825  nop
0x18001e826  lea     rcx, [rsp+138h+var_118]
0x18001e82b  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18001e830  nop
0x18001e831  mov     rax, rsi
0x18001e834  jmp     loc_18001EBF1
0x18001e839  mov     rcx, [rsp+138h]; this
0x18001e841  test    eax, eax
0x18001e843  jz      short loc_18001E859
0x18001e845  mov     r9d, eax; char *
0x18001e848  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001e84f  mov     edx, 0C0h; void *
0x18001e854  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001e859  mov     rcx, [rsp+138h+Settings.ProfileNameServer]; String
0x18001e861  test    rcx, rcx
0x18001e864  jz      loc_18001EB97
0x18001e86a  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001e86e  mov     rax, r13
0x18001e871  inc     rax
0x18001e874  cmp     [rcx+rax*2], di
0x18001e878  jnz     short loc_18001E871
0x18001e87a  test    rax, rax
0x18001e87d  jz      loc_18001EB97
0x18001e883  mov     rax, 3B002C0020h
0x18001e88d  mov     qword ptr [rsp+138h+Interface.Data1], rax
0x18001e895  mov     [rsp+138h+Context], rdi
0x18001e89a  lea     r8, [rsp+138h+Context]; Context
0x18001e89f  lea     rdx, [rsp+138h+Interface]; Delimiter
0x18001e8a7  call    cs:__imp_wcstok_s
0x18001e8ad  mov     r14, rax
0x18001e8b0  test    r14, r14
0x18001e8b3  jz      loc_18001E9B7
0x18001e8b9  mov     rbx, r13
0x18001e8bc  inc     rbx
0x18001e8bf  cmp     [r14+rbx*2], di
0x18001e8c4  jnz     short loc_18001E8BC
0x18001e8c6  mov     [rsp+138h+string], rdi
0x18001e8cb  xor     ecx, ecx; string
0x18001e8cd  call    cs:__imp_WindowsDeleteString
0x18001e8d3  mov     [rsp+138h+string], rdi
0x18001e8d8  lea     r8, [rsp+138h+string]; string
0x18001e8dd  mov     edx, ebx; length
0x18001e8df  mov     rcx, r14; sourceString
0x18001e8e2  call    cs:__imp_WindowsCreateString
0x18001e8e8  mov     rcx, [rsp+138h]; this
0x18001e8f0  test    eax, eax
0x18001e8f2  jns     short loc_18001E908
0x18001e8f4  mov     r9d, eax; char *
0x18001e8f7  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001e8fe  mov     edx, 0CCh; void *
0x18001e903  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e908  xorps   xmm0, xmm0
0x18001e90b  xor     ebx, ebx
0x18001e90d  movups  xmmword ptr [rsp+138h+var_108], xmm0
0x18001e912  mov     [rsp+138h+var_F8], rbx
0x18001e917  mov     rcx, [rsp+138h+string]; HSTRING
0x18001e91c  mov     [rsp+138h+string], rdi
0x18001e921  mov     [rsp+138h+var_108+8], rcx
0x18001e926  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x18001e92b  mov     byte ptr [rsp+138h+var_108], al
0x18001e92f  mov     dword ptr [rsp+138h+var_108+4], edi
0x18001e933  movups  xmm0, xmmword ptr [rsp+138h+var_108]
0x18001e938  movaps  xmmword ptr [rsp+138h+sourceString], xmm0
0x18001e940  mov     qword ptr [rsp+138h+length], rbx
0x18001e948  mov     r9b, 1
0x18001e94b  lea     r8, [rsp+138h+sourceString]
0x18001e953  xor     edx, edx
0x18001e955  mov     rcx, qword ptr [rsp+138h+var_118]
0x18001e95a  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x18001e95f  mov     rcx, [rsp+138h]; this
0x18001e967  test    eax, eax
0x18001e969  jns     short loc_18001E97F
0x18001e96b  mov     r9d, eax; char *
0x18001e96e  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001e975  mov     edx, 0D2h; void *
0x18001e97a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e97f  lea     r8, [rsp+138h+Context]; Context
0x18001e984  lea     rdx, [rsp+138h+Interface]; Delimiter
0x18001e98c  xor     ecx, ecx; String
0x18001e98e  call    cs:__imp_wcstok_s
0x18001e994  mov     r14, rax
0x18001e997  lea     rcx, [rsp+138h+var_108]; struct Windows::Networking::UX::DnsServer *
0x18001e99c  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18001e9a1  nop
0x18001e9a2  mov     rcx, [rsp+138h+string]; string
0x18001e9a7  call    cs:__imp_WindowsDeleteString
0x18001e9ad  mov     [rsp+138h+string], rdi
0x18001e9b2  jmp     loc_18001E8B0
0x18001e9b7  mov     ebx, edi
0x18001e9b9  cmp     ebx, [rsp+138h+var_78]
0x18001e9c0  jnb     loc_18001EB97
0x18001e9c6  mov     eax, ebx
0x18001e9c8  lea     rcx, [rax+rax*2]
0x18001e9cc  mov     rax, [rsp+138h+var_70]
0x18001e9d4  mov     r15d, [rax+rcx*8+4]
0x18001e9d9  mov     r14, [rax+rcx*8+10h]
0x18001e9de  xorps   xmm0, xmm0
0x18001e9e1  xor     eax, eax
0x18001e9e3  movups  xmmword ptr [rsp+138h+var_108], xmm0
0x18001e9e8  mov     [rsp+138h+var_F8], rax
0x18001e9ed  lea     r8, [rsp+138h+var_108]
0x18001e9f2  mov     edx, r15d
0x18001e9f5  mov     rcx, qword ptr [rsp+138h+var_118]
0x18001e9fa  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x18001e9ff  mov     rcx, [rsp+138h]; this
0x18001ea07  test    eax, eax
0x18001ea09  jns     short loc_18001EA1F
0x18001ea0b  mov     r9d, eax; char *
0x18001ea0e  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001ea15  mov     edx, 0DCh; void *
0x18001ea1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea1f  mov     eax, dword ptr [rsp+138h+var_108+4]
0x18001ea23  test    byte ptr [r14+8], 4
0x18001ea28  jz      short loc_18001EA31
0x18001ea2a  or      eax, 4
0x18001ea2d  mov     dword ptr [rsp+138h+var_108+4], eax
0x18001ea31  test    byte ptr [r14+8], 1
0x18001ea36  jz      loc_18001EAEC
0x18001ea3c  or      eax, 1
0x18001ea3f  mov     dword ptr [rsp+138h+var_108+4], eax
0x18001ea43  cmp     byte ptr [rsp+138h+var_108], dil
0x18001ea48  jz      loc_18001EAEC
0x18001ea4e  lea     rcx, [rsp+138h+sourceString]
0x18001ea56  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ea5b  nop
0x18001ea5c  lea     rdx, [rsp+138h+sourceString]
0x18001ea64  mov     rcx, [rsp+138h+var_108+8]; string
0x18001ea69  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x18001ea6e  mov     rcx, [rsp+138h]; this
0x18001ea76  test    eax, eax
0x18001ea78  jns     short loc_18001EA8E
0x18001ea7a  mov     r9d, eax; char *
0x18001ea7d  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001ea84  mov     edx, 0E8h; void *
0x18001ea89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea8e  lea     rcx, [rsp+138h+sourceString]
0x18001ea96  cmp     [rsp+138h+var_50], 7
0x18001ea9f  cmova   rcx, [rsp+138h+sourceString]; sourceString
0x18001eaa8  lea     r8, [rsp+138h+var_F8]; string
0x18001eaad  mov     edx, [rsp+138h+length]; length
0x18001eab4  call    cs:__imp_WindowsCreateString
0x18001eaba  mov     rcx, [rsp+138h]; this
0x18001eac2  test    eax, eax
0x18001eac4  jns     short loc_18001EADB
0x18001eac6  mov     r9d, eax; char *
0x18001eac9  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001ead0  mov     edx, 0E9h; void *
0x18001ead5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eadb  lea     rcx, [rsp+138h+sourceString]
0x18001eae3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eae8  mov     eax, dword ptr [rsp+138h+var_108+4]
0x18001eaec  test    byte ptr [r14+8], 2
0x18001eaf1  jz      short loc_18001EB34
0x18001eaf3  or      eax, 2
0x18001eaf6  mov     dword ptr [rsp+138h+var_108+4], eax
0x18001eafa  mov     rcx, [r14]; sourceString
0x18001eafd  mov     rdx, r13
0x18001eb00  inc     rdx; length
0x18001eb03  cmp     [rcx+rdx*2], di
0x18001eb07  jnz     short loc_18001EB00
0x18001eb09  lea     r8, [rsp+138h+var_F8]; string
0x18001eb0e  call    cs:__imp_WindowsCreateString
0x18001eb14  mov     rcx, [rsp+138h]; this
0x18001eb1c  test    eax, eax
0x18001eb1e  jns     short loc_18001EB34
0x18001eb20  mov     r9d, eax; char *
0x18001eb23  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001eb2a  mov     edx, 0F1h; void *
0x18001eb2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eb34  movups  xmm0, xmmword ptr [rsp+138h+var_108]
0x18001eb39  movaps  xmmword ptr [rsp+138h+sourceString], xmm0
0x18001eb41  movsd   xmm1, [rsp+138h+var_F8]
0x18001eb47  movsd   qword ptr [rsp+138h+length], xmm1
0x18001eb50  lea     r8, [rsp+138h+sourceString]
0x18001eb58  mov     edx, r15d
0x18001eb5b  mov     rcx, qword ptr [rsp+138h+var_118]
0x18001eb60  call    ?SetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::SetAt(uint,Windows::Networking::UX::DnsServer)
0x18001eb65  mov     rcx, [rsp+138h]; this
0x18001eb6d  test    eax, eax
0x18001eb6f  jns     short loc_18001EB86
0x18001eb71  mov     r9d, eax; char *
0x18001eb74  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001eb7b  mov     edx, 0F4h; void *
0x18001eb80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eb86  lea     rcx, [rsp+138h+var_108]; struct Windows::Networking::UX::DnsServer *
0x18001eb8b  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18001eb90  inc     ebx
0x18001eb92  jmp     loc_18001E9B9
0x18001eb97  lea     rcx, [rsp+138h+Settings]; Settings
0x18001eb9c  call    cs:__imp_FreeInterfaceDnsSettings
0x18001eba2  nop
0x18001eba3  jmp     short loc_18001EBAA
0x18001eba5  mov     rsi, [rsp+138h+var_E0]
0x18001ebaa  mov     rbx, qword ptr [rsp+138h+var_118]
0x18001ebaf  mov     rcx, rsi
0x18001ebb2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ebb7  mov     rdx, rsi
0x18001ebba  mov     rcx, rbx
0x18001ebbd  call    ?GetView@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> * *)
0x18001ebc2  mov     rcx, [rsp+138h]; this
0x18001ebca  test    eax, eax
0x18001ebcc  jns     short loc_18001EBE3
0x18001ebce  mov     r9d, eax; char *
0x18001ebd1  mov     edx, 0FAh; void *
0x18001ebd6  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18001ebdd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ebe2  nop
0x18001ebe3  lea     rcx, [rsp+138h+var_118]
0x18001ebe8  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,0>>::InternalRelease(void)
0x18001ebed  nop
0x18001ebee  mov     rax, rsi
0x18001ebf1  mov     rcx, [rsp+138h+var_38]
0x18001ebf9  xor     rcx, rsp; StackCookie
0x18001ebfc  call    __security_check_cookie
0x18001ec01  mov     rbx, [rsp+138h+arg_10]
0x18001ec09  add     rsp, 110h
0x18001ec10  pop     r15
0x18001ec12  pop     r14
0x18001ec14  pop     r13
0x18001ec16  pop     rdi
0x18001ec17  pop     rsi
0x18001ec18  retn
```
