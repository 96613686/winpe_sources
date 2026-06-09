# SetInterfaceDns(Windows::Networking::UX::IpFamily,_GUID const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)

- ea: `0x180039ec0`
- end: `0x18003a37a`
- name: `?SetInterfaceDns@@YAXW4IpFamily@UX@Networking@Windows@@AEBU_GUID@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@4@@Z`
- size: `1210`
- prototype: `__int64 __fastcall(int, _OWORD *, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f65c`

## callees

- `0x180002520`
- `0x180002ea0`
- `0x1800030a0`
- `0x180004ba0`
- `0x18000b638`
- `0x18000d65c`
- `0x180013b8c`
- `0x18001a300`
- `0x18001d88c`
- `0x180039564`
- `0x18003959c`
- `0x180039614`
- `0x18003963c`
- `0x180039664`
- `0x1800397b4`
- `0x180039ae4`
- `0x180039b5c`
- `0x180039b98`
- `0x180039bb4`
- `0x180039ec0`
- `0x18003ae50`
- `0x180047010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a21e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a21e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18003a02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18003a05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18003a02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18003a05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a33f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a33f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a1cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a1cc`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x18003a2a2`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x18003a2a2`

## pseudocode

```c
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
    wil::details::in1diag3::_Throw_Hr(
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
  std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(&v36);
  std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(&v34);
  for ( i = 0; i < v26; ++i )
  {
    string[0] = 0;
    *(_OWORD *)v32 = 0;
    v33 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a3 + 48LL))(a3, i, v32);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
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
        wil::details::in1diag3::_Throw_Hr(
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
      wil::details::in1diag3::_Throw_Hr(
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
          &v36,
          *((_QWORD *)&v36 + 1),
          length);
      else
        std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(
          &v36,
          length);
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
      *v16 = &qword_180067F60;
      if ( (BYTE4(v32[0]) & 1) != 0 || (BYTE4(v32[0]) & 2) != 0 )
      {
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v33, length);
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v30,
          StringRawBuffer);
        if ( *((_QWORD *)&v34 + 1) == v35 )
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v34,
            *((_QWORD *)&v34 + 1),
            &v30);
        else
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v34,
            &v30);
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
    wil::details::in1diag3::_Throw_Hr(
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
      *((_QWORD *)&v34 + 1));
    std::_Deallocate<16>(v34, (v35 - v34) & 0xFFFFFFFFFFFFFFF8uLL);
    v34 = 0;
    v35 = 0;
  }
  if ( (_QWORD)v36 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>>(v36, *((_QWORD *)&v36 + 1));
    std::_Deallocate<16>(v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF8uLL);
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
0x180039ec0  mov     [rsp-8+arg_0], rbx
0x180039ec5  push    rbp
0x180039ec6  push    rsi
0x180039ec7  push    rdi
0x180039ec8  push    r12
0x180039eca  push    r13
0x180039ecc  push    r14
0x180039ece  push    r15
0x180039ed0  lea     rbp, [rsp-40h]
0x180039ed5  sub     rsp, 140h
0x180039edc  mov     rax, cs:__security_cookie
0x180039ee3  xor     rax, rsp
0x180039ee6  mov     [rbp+70h+var_40], rax
0x180039eea  mov     r15, r8
0x180039eed  mov     r12, rdx
0x180039ef0  mov     ebx, ecx
0x180039ef2  xor     r13d, r13d
0x180039ef5  mov     [rsp+170h+var_150], r13d; unsigned int
0x180039efa  mov     rax, [r8]
0x180039efd  lea     rdx, [rsp+170h+var_150]
0x180039f02  mov     rcx, r8
0x180039f05  mov     rax, [rax+38h]
0x180039f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f0e  mov     rcx, [rbp+78h]; this
0x180039f12  test    eax, eax
0x180039f14  jns     short loc_180039F2B
0x180039f16  mov     r9d, eax; char *
0x180039f19  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180039f20  mov     edx, 101h; void *
0x180039f25  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180039f2b  xor     edx, edx; Val
0x180039f2d  lea     r8d, [rdx+70h]; Size
0x180039f31  lea     rcx, [rbp+70h+Settings]; void *
0x180039f35  call    memset_0
0x180039f3a  mov     [rbp+70h+Settings.Version], 3
0x180039f41  mov     eax, 1002h
0x180039f46  lea     ecx, [rax+1]
0x180039f49  cmp     ebx, 6
0x180039f4c  cmovz   eax, ecx
0x180039f4f  mov     [rbp+70h+Settings.Flags], rax
0x180039f53  mov     ecx, [rsp+170h+var_150]
0x180039f57  mov     eax, 18h
0x180039f5c  mul     rcx
0x180039f5f  mov     rbx, rax
0x180039f62  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180039f69  cmovb   rbx, rax
0x180039f6d  mov     rcx, rbx; unsigned __int64
0x180039f70  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180039f75  mov     rsi, rax
0x180039f78  mov     r8, rbx; Size
0x180039f7b  xor     edx, edx; Val
0x180039f7d  mov     rcx, rax; void *
0x180039f80  call    memset_0
0x180039f85  mov     [rbp+70h+var_D8], rsi
0x180039f89  mov     [rsp+170h+string1], r13
0x180039f8e  mov     r14d, r13d
0x180039f91  lea     rcx, [rbp+70h+var_F0]
0x180039f95  call    ??0?$vector@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(void)
0x180039f9a  nop
0x180039f9b  lea     rcx, [rsp+170h+var_108]
0x180039fa0  call    ??0?$vector@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(void)
0x180039fa5  nop
0x180039fa6  mov     edi, r13d
0x180039fa9  cmp     [rsp+170h+var_150], r13d
0x180039fae  jbe     loc_18003A1BD
0x180039fb4  mov     [rsp+170h+string], r13
0x180039fb9  xorps   xmm0, xmm0
0x180039fbc  xor     eax, eax
0x180039fbe  movups  xmmword ptr [rsp+170h+var_120], xmm0
0x180039fc3  mov     [rsp+170h+var_110], rax
0x180039fc8  mov     rax, [r15]
0x180039fcb  lea     r8, [rsp+170h+var_120]
0x180039fd0  mov     edx, edi
0x180039fd2  mov     rcx, r15
0x180039fd5  mov     rax, [rax+30h]
0x180039fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fde  mov     rcx, [rbp+78h]; this
0x180039fe2  test    eax, eax
0x180039fe4  js      loc_18003A26D
0x180039fea  test    edi, edi
0x180039fec  jz      short loc_18003A03D
0x180039fee  mov     rcx, [rsp+170h+string]; string
0x180039ff3  call    cs:__imp_WindowsDeleteString
0x180039ff9  mov     [rsp+170h+string], r13
0x180039ffe  mov     [rbp+70h+string2], r13
0x18003a002  mov     r9d, 1; unsigned int
0x18003a008  lea     r8d, [r9+1]; unsigned int
0x18003a00c  lea     rdx, sourceString; ","
0x18003a013  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x18003a017  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003a01c  nop
0x18003a01d  lea     r8, [rsp+170h+string]; newString
0x18003a022  mov     rdx, [rbp+70h+string2]; string2
0x18003a026  mov     rcx, [rsp+170h+string1]; string1
0x18003a02b  call    cs:__imp_WindowsConcatString
0x18003a031  mov     rcx, [rbp+78h]; this
0x18003a035  test    eax, eax
0x18003a037  js      loc_18003A243
0x18003a03d  mov     rcx, [rsp+170h+string1]; string
0x18003a042  call    cs:__imp_WindowsDeleteString
0x18003a048  mov     [rsp+170h+string1], r13
0x18003a04d  lea     r8, [rsp+170h+string1]; newString
0x18003a052  mov     rdx, [rsp+170h+var_120+8]; string2
0x18003a057  mov     rcx, [rsp+170h+string]; string1
0x18003a05c  call    cs:__imp_WindowsConcatString
0x18003a062  mov     rcx, [rbp+78h]; this
0x18003a066  test    eax, eax
0x18003a068  js      loc_18003A258
0x18003a06e  cmp     dword ptr [rsp+170h+var_120+4], r13d
0x18003a073  jz      loc_18003A19B
0x18003a079  mov     ecx, 10h; Size
0x18003a07e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a083  xorps   xmm0, xmm0
0x18003a086  movups  xmmword ptr [rax], xmm0
0x18003a089  mov     qword ptr [rsp+170h+length], rax
0x18003a08e  mov     rdx, qword ptr [rbp+70h+var_F0+8]
0x18003a092  lea     rcx, [rbp+70h+var_F0]
0x18003a096  cmp     rdx, [rbp+70h+var_E0]
0x18003a09a  jz      short loc_18003A0A8
0x18003a09c  lea     rdx, [rsp+170h+length]
0x18003a0a1  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@?$vector@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> &&)
0x18003a0a6  jmp     short loc_18003A0B3
0x18003a0a8  lea     r8, [rsp+170h+length]
0x18003a0ad  call    ??$_Emplace_reallocate@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@?$vector@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_reallocate<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> * const,std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> &&)
0x18003a0b2  nop
0x18003a0b3  lea     rcx, [rsp+170h+length]
0x18003a0b8  call    ??1?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>::~unique_ptr<_DNS_DOH_SERVER_SETTINGS>(void)
0x18003a0bd  mov     rax, qword ptr [rbp+70h+var_F0+8]
0x18003a0c1  mov     rbx, [rax-8]
0x18003a0c5  mov     [rbx+8], r13
0x18003a0c9  mov     rax, r13
0x18003a0cc  mov     ecx, dword ptr [rsp+170h+var_120+4]
0x18003a0d0  test    cl, 1
0x18003a0d3  jz      short loc_18003A0E2
0x18003a0d5  mov     eax, 11h
0x18003a0da  mov     [rbx+8], rax
0x18003a0de  mov     ecx, dword ptr [rsp+170h+var_120+4]
0x18003a0e2  test    cl, 2
0x18003a0e5  jz      short loc_18003A0F3
0x18003a0e7  or      rax, 2
0x18003a0eb  mov     [rbx+8], rax
0x18003a0ef  mov     ecx, dword ptr [rsp+170h+var_120+4]
0x18003a0f3  test    cl, 4
0x18003a0f6  jz      short loc_18003A100
0x18003a0f8  or      rax, 4
0x18003a0fc  mov     [rbx+8], rax
0x18003a100  lea     rax, qword_180067F60
0x18003a107  mov     [rbx], rax
0x18003a10a  test    byte ptr [rsp+170h+var_120+4], 1
0x18003a10f  jnz     short loc_18003A118
0x18003a111  test    byte ptr [rsp+170h+var_120+4], 2
0x18003a116  jz      short loc_18003A179
0x18003a118  mov     [rsp+170h+length], r13d
0x18003a11d  lea     rdx, [rsp+170h+length]; length
0x18003a122  mov     rcx, [rsp+170h+var_110]; string
0x18003a127  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a12d  mov     rdx, rax
0x18003a130  lea     rcx, [rsp+170h+var_138]
0x18003a135  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003a13a  nop
0x18003a13b  mov     rdx, qword ptr [rsp+170h+var_108+8]
0x18003a140  lea     rcx, [rsp+170h+var_108]
0x18003a145  cmp     rdx, [rsp+170h+var_F8]
0x18003a14a  jz      short loc_18003A158
0x18003a14c  lea     rdx, [rsp+170h+var_138]
0x18003a151  call    ??$_Emplace_back_with_unused_capacity@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003a156  jmp     short loc_18003A163
0x18003a158  lea     r8, [rsp+170h+var_138]
0x18003a15d  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003a162  nop
0x18003a163  lea     rcx, [rsp+170h+var_138]
0x18003a168  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a16d  mov     rax, qword ptr [rsp+170h+var_108+8]
0x18003a172  mov     rcx, [rax-8]
0x18003a176  mov     [rbx], rcx
0x18003a179  movsxd  rax, r14d
0x18003a17c  lea     rcx, [rax+rax*2]
0x18003a180  mov     dword ptr [rsi+rcx*8], 1
0x18003a187  mov     [rsi+rcx*8+4], edi
0x18003a18b  mov     dword ptr [rsi+rcx*8+8], 1
0x18003a193  mov     [rsi+rcx*8+10h], rbx
0x18003a198  inc     r14d
0x18003a19b  lea     rcx, [rsp+170h+var_120]; struct Windows::Networking::UX::DnsServer *
0x18003a1a0  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18003a1a5  nop
0x18003a1a6  mov     rcx, [rsp+170h+string]; string
0x18003a1ab  call    cs:__imp_WindowsDeleteString
0x18003a1b1  inc     edi
0x18003a1b3  cmp     edi, [rsp+170h+var_150]
0x18003a1b7  jb      loc_180039FB4
0x18003a1bd  mov     [rsp+170h+var_14C], r13d
0x18003a1c2  lea     rdx, [rsp+170h+var_14C]; length
0x18003a1c7  mov     rcx, [rsp+170h+string1]; string
0x18003a1cc  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a1d2  mov     rdi, rax
0x18003a1d5  mov     edx, [rsp+170h+var_14C]
0x18003a1d9  inc     edx
0x18003a1db  mov     eax, 2
0x18003a1e0  mul     rdx
0x18003a1e3  mov     rbx, rax
0x18003a1e6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003a1ed  cmovb   rbx, rax
0x18003a1f1  mov     rcx, rbx; unsigned __int64
0x18003a1f4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003a1f9  mov     r15, rax
0x18003a1fc  mov     r8, rbx; Size
0x18003a1ff  xor     edx, edx; Val
0x18003a201  mov     rcx, rax; void *
0x18003a204  call    memset_0
0x18003a209  mov     [rsp+170h+var_138], r15
0x18003a20e  mov     rbx, [rbp+78h]
0x18003a212  mov     edx, [rsp+170h+var_14C]
0x18003a216  inc     edx
0x18003a218  mov     r8, rdi
0x18003a21b  mov     rcx, r15
0x18003a21e  call    cs:__imp__o_wcscpy_s
0x18003a224  test    eax, eax
0x18003a226  jz      short loc_18003A282
0x18003a228  mov     r9d, 80070057h; char *
0x18003a22e  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a235  mov     edx, 152h; void *
0x18003a23a  mov     rcx, rbx; this
0x18003a23d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a243  mov     r9d, eax; char *
0x18003a246  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a24d  mov     edx, 11Fh; void *
0x18003a252  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a258  mov     r9d, eax; char *
0x18003a25b  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a262  mov     edx, 121h; void *
0x18003a267  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a26d  mov     r9d, eax; char *
0x18003a270  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a277  mov     edx, 11Ch; void *
0x18003a27c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a282  mov     [rbp+70h+var_80], r14d
0x18003a286  mov     [rbp+70h+Settings.NameServer], r15
0x18003a28a  mov     [rbp+70h+var_78], rsi
0x18003a28e  movups  xmm0, xmmword ptr [r12]
0x18003a293  movdqu  xmmword ptr [rsp+170h+string], xmm0
0x18003a299  lea     rdx, [rbp+70h+Settings]; Settings
0x18003a29d  lea     rcx, [rsp+170h+string]; Interface
0x18003a2a2  call    cs:__imp_SetInterfaceDnsSettings
0x18003a2a8  mov     rcx, [rbp+78h]; this
0x18003a2ac  test    eax, eax
0x18003a2ae  jz      short loc_18003A2C5
0x18003a2b0  mov     r9d, eax; char *
0x18003a2b3  lea     r8, aOnecoreuapNetU_8; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18003a2ba  mov     edx, 15Ah; void *
0x18003a2bf  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003a2c5  lea     rcx, [rsp+170h+var_138]
0x18003a2ca  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18003a2cf  nop
0x18003a2d0  mov     rcx, qword ptr [rsp+170h+var_108]
0x18003a2d5  test    rcx, rcx
0x18003a2d8  jz      short loc_18003A308
0x18003a2da  mov     rdx, qword ptr [rsp+170h+var_108+8]
0x18003a2df  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18003a2e4  mov     rcx, qword ptr [rsp+170h+var_108]
0x18003a2e9  mov     rdx, [rsp+170h+var_F8]
0x18003a2ee  sub     rdx, rcx
0x18003a2f1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18003a2f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003a2fa  xorps   xmm0, xmm0
0x18003a2fd  movdqu  [rsp+170h+var_108], xmm0
0x18003a303  mov     [rsp+170h+var_F8], r13
0x18003a308  mov     rcx, qword ptr [rbp+70h+var_F0]
0x18003a30c  test    rcx, rcx
0x18003a30f  jz      short loc_18003A33A
0x18003a311  mov     rdx, qword ptr [rbp+70h+var_F0+8]
0x18003a315  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> *,std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> * const,std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>> &)
0x18003a31a  mov     rcx, qword ptr [rbp+70h+var_F0]
0x18003a31e  mov     rdx, [rbp+70h+var_E0]
0x18003a322  sub     rdx, rcx
0x18003a325  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18003a329  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003a32e  xorps   xmm0, xmm0
0x18003a331  movdqu  [rbp+70h+var_F0], xmm0
0x18003a336  mov     [rbp+70h+var_E0], r13
0x18003a33a  mov     rcx, [rsp+170h+string1]; string
0x18003a33f  call    cs:__imp_WindowsDeleteString
0x18003a345  mov     [rsp+170h+string1], r13
0x18003a34a  lea     rcx, [rbp+70h+var_D8]
0x18003a34e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18003a353  mov     rcx, [rbp+70h+var_40]
0x18003a357  xor     rcx, rsp; StackCookie
0x18003a35a  call    __security_check_cookie
0x18003a35f  mov     rbx, [rsp+170h+arg_0]
0x18003a367  add     rsp, 140h
0x18003a36e  pop     r15
0x18003a370  pop     r14
0x18003a372  pop     r13
0x18003a374  pop     r12
0x18003a376  pop     rdi
0x18003a377  pop     rsi
0x18003a378  pop     rbp
0x18003a379  retn
```
