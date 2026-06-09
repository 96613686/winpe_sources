# SetInterfaceDns(Windows::Networking::UX::IpFamily,_GUID const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)

- ea: `0x18002711c`
- end: `0x1800275e2`
- name: `?SetInterfaceDns@@YAXW4IpFamily@UX@Networking@Windows@@AEBU_GUID@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@4@@Z`
- size: `1222`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028aa8`

## callees

- `0x18000352c`
- `0x180016600`
- `0x18001f8c8`
- `0x180023018`
- `0x18002711c`
- `0x18002c8b4`
- `0x18002cd20`
- `0x18002d6a0`
- `0x18002d8c8`
- `0x18002ddf8`
- `0x180035c60`
- `0x180036714`
- `0x180052638`
- `0x180055570`
- `0x1800555a8`
- `0x1800555e0`
- `0x180055724`
- `0x1800558e8`
- `0x180055904`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180027480`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180027480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002724d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002729c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002740d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002724d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002729c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002740d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180027285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800272b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180027285`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800272b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002742e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002742e`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x180027504`
- `IPHLPAPI!SetInterfaceDnsSettings` at `0x180027504`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SetInterfaceDns(int a1, _OWORD *a2, __int64 a3)
{
  int v6; // eax
  ULONG64 v7; // rax
  unsigned __int64 v8; // rbx
  void *v9; // rsi
  int v10; // r15d
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
  void *v23; // r14
  unsigned int v24; // eax
  unsigned int v26; // [rsp+20h] [rbp-E0h] BYREF
  UINT32 v27; // [rsp+24h] [rbp-DCh] BYREF
  HSTRING string1; // [rsp+28h] [rbp-D8h] BYREF
  UINT32 length[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *v30; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int128 v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h]
  HSTRING string[2]; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v36[2]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v37; // [rsp+90h] [rbp-70h]
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
  std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(&v33);
  std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(&v31);
  for ( i = 0; i < v26; ++i )
  {
    string[0] = 0;
    *(_OWORD *)v36 = 0;
    v37 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a3 + 48LL))(a3, i, v36);
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
    v14 = WindowsConcatString(string[0], v36[1], &string1);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\net\\ux\\dnshelper\\lib\\dnshelper.cpp",
        (const char *)(unsigned int)v14,
        v26);
    if ( HIDWORD(v36[0]) )
    {
      v15 = operator new(0x10u);
      *v15 = 0;
      *(_QWORD *)length = v15;
      if ( *((_QWORD *)&v33 + 1) == v34 )
      {
        std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_reallocate<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(
          &v33,
          *((_QWORD *)&v33 + 1),
          length);
      }
      else
      {
        *(_QWORD *)length = 0;
        **((_QWORD **)&v33 + 1) = v15;
        *((_QWORD *)&v33 + 1) += 8LL;
      }
      std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>::~unique_ptr<_DNS_DOH_SERVER_SETTINGS>(length);
      v16 = *(_QWORD **)(*((_QWORD *)&v33 + 1) - 8LL);
      v16[1] = 0;
      v17 = 0;
      v18 = BYTE4(v36[0]);
      if ( (BYTE4(v36[0]) & 1) != 0 )
      {
        v17 = 17;
        v16[1] = 17;
        v18 = BYTE4(v36[0]);
      }
      if ( (v18 & 2) != 0 )
      {
        v17 |= 2uLL;
        v16[1] = v17;
        v18 = BYTE4(v36[0]);
      }
      if ( (v18 & 4) != 0 )
        v16[1] = v17 | 4;
      *v16 = &sourceString;
      if ( (BYTE4(v36[0]) & 1) != 0 || (BYTE4(v36[0]) & 2) != 0 )
      {
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v37, length);
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v30,
          StringRawBuffer);
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v31,
            *((_QWORD *)&v31 + 1),
            &v30);
        }
        else
        {
          **((_QWORD **)&v31 + 1) = v30;
          v30 = 0;
          *((_QWORD *)&v31 + 1) += 8LL;
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
        *v16 = *(_QWORD *)(*((_QWORD *)&v31 + 1) - 8LL);
      }
      v20 = 3LL * v10;
      *((_DWORD *)v9 + 2 * v20) = 1;
      *((_DWORD *)v9 + 2 * v20 + 1) = i;
      *((_DWORD *)v9 + 2 * v20 + 2) = 1;
      *((_QWORD *)v9 + v20 + 2) = v16;
      ++v10;
    }
    FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v36);
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
  if ( (_QWORD)v31 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
      v31,
      *((_QWORD *)&v31 + 1));
    std::_Deallocate<16>(v31, (v32 - v31) & 0xFFFFFFFFFFFFFFF8uLL);
    v31 = 0;
    v32 = 0;
  }
  if ( (_QWORD)v33 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>>(v33, *((_QWORD *)&v33 + 1));
    std::_Deallocate<16>(v33, (v34 - v33) & 0xFFFFFFFFFFFFFFF8uLL);
    v33 = 0;
    v34 = 0;
  }
  WindowsDeleteString(string1);
  string1 = 0;
  return std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v38);
}

```

## disassembly

```asm
0x18002711c  mov     [rsp-8+arg_0], rbx
0x180027121  push    rbp
0x180027122  push    rsi
0x180027123  push    rdi
0x180027124  push    r12
0x180027126  push    r13
0x180027128  push    r14
0x18002712a  push    r15
0x18002712c  lea     rbp, [rsp-40h]
0x180027131  sub     rsp, 140h
0x180027138  mov     rax, cs:__security_cookie
0x18002713f  xor     rax, rsp
0x180027142  mov     [rbp+70h+var_40], rax
0x180027146  mov     r14, r8
0x180027149  mov     r12, rdx
0x18002714c  mov     ebx, ecx
0x18002714e  xor     r13d, r13d
0x180027151  mov     [rsp+170h+var_150], r13d; unsigned int
0x180027156  mov     rax, [r8]
0x180027159  lea     rdx, [rsp+170h+var_150]
0x18002715e  mov     rcx, r8
0x180027161  mov     rax, [rax+38h]
0x180027165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002716a  mov     rcx, [rbp+78h]; this
0x18002716e  test    eax, eax
0x180027170  jns     short loc_180027187
0x180027172  mov     r9d, eax; char *
0x180027175  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18002717c  mov     edx, 101h; void *
0x180027181  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027187  xor     edx, edx; Val
0x180027189  lea     r8d, [rdx+70h]; Size
0x18002718d  lea     rcx, [rbp+70h+Settings]; void *
0x180027191  call    memset_0
0x180027196  mov     [rbp+70h+Settings.Version], 3
0x18002719d  mov     eax, 1002h
0x1800271a2  lea     ecx, [rax+1]
0x1800271a5  cmp     ebx, 6
0x1800271a8  cmovz   eax, ecx
0x1800271ab  mov     [rbp+70h+Settings.Flags], rax
0x1800271af  mov     ecx, [rsp+170h+var_150]
0x1800271b3  mov     eax, 18h
0x1800271b8  mul     rcx
0x1800271bb  mov     rbx, rax
0x1800271be  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800271c5  cmovb   rbx, rax
0x1800271c9  mov     rcx, rbx; unsigned __int64
0x1800271cc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800271d1  mov     rsi, rax
0x1800271d4  mov     r8, rbx; Size
0x1800271d7  xor     edx, edx; Val
0x1800271d9  mov     rcx, rax; void *
0x1800271dc  call    memset_0
0x1800271e1  mov     [rbp+70h+var_D8], rsi
0x1800271e5  mov     [rsp+170h+string1], r13
0x1800271ea  mov     r15d, r13d
0x1800271ed  lea     rcx, [rsp+170h+var_118]
0x1800271f2  call    ??0?$vector@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(void)
0x1800271f7  nop
0x1800271f8  lea     rcx, [rsp+170h+var_130]
0x1800271fd  call    ??0?$vector@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(void)
0x180027202  nop
0x180027203  mov     edi, r13d
0x180027206  cmp     [rsp+170h+var_150], r13d
0x18002720b  jbe     loc_18002741F
0x180027211  mov     [rsp+170h+string], r13
0x180027216  xorps   xmm0, xmm0
0x180027219  xor     eax, eax
0x18002721b  movups  xmmword ptr [rbp+70h+var_F0], xmm0
0x18002721f  mov     [rbp+70h+var_E0], rax
0x180027223  mov     rax, [r14]
0x180027226  lea     r8, [rbp+70h+var_F0]
0x18002722a  mov     edx, edi
0x18002722c  mov     rcx, r14
0x18002722f  mov     rax, [rax+30h]
0x180027233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027238  mov     rcx, [rbp+78h]; this
0x18002723c  test    eax, eax
0x18002723e  js      loc_1800274CF
0x180027244  test    edi, edi
0x180027246  jz      short loc_180027297
0x180027248  mov     rcx, [rsp+170h+string]; string
0x18002724d  call    cs:__imp_WindowsDeleteString
0x180027253  mov     [rsp+170h+string], r13
0x180027258  mov     [rbp+70h+string2], r13
0x18002725c  mov     r9d, 1; unsigned int
0x180027262  lea     r8d, [r9+1]; unsigned int
0x180027266  lea     rdx, asc_180065D74; ","
0x18002726d  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x180027271  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027276  nop
0x180027277  lea     r8, [rsp+170h+string]; newString
0x18002727c  mov     rdx, [rbp+70h+string2]; string2
0x180027280  mov     rcx, [rsp+170h+string1]; string1
0x180027285  call    cs:__imp_WindowsConcatString
0x18002728b  mov     rcx, [rbp+78h]; this
0x18002728f  test    eax, eax
0x180027291  js      loc_1800274A5
0x180027297  mov     rcx, [rsp+170h+string1]; string
0x18002729c  call    cs:__imp_WindowsDeleteString
0x1800272a2  mov     [rsp+170h+string1], r13
0x1800272a7  lea     r8, [rsp+170h+string1]; newString
0x1800272ac  mov     rdx, [rbp+70h+var_F0+8]; string2
0x1800272b0  mov     rcx, [rsp+170h+string]; string1
0x1800272b5  call    cs:__imp_WindowsConcatString
0x1800272bb  mov     rcx, [rbp+78h]; this
0x1800272bf  test    eax, eax
0x1800272c1  js      loc_1800274BA
0x1800272c7  cmp     dword ptr [rbp+70h+var_F0+4], r13d
0x1800272cb  jz      loc_1800273FE
0x1800272d1  mov     ecx, 10h; Size
0x1800272d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800272db  xorps   xmm0, xmm0
0x1800272de  movups  xmmword ptr [rax], xmm0
0x1800272e1  mov     qword ptr [rsp+170h+length], rax
0x1800272e6  mov     rdx, qword ptr [rsp+170h+var_118+8]
0x1800272eb  cmp     rdx, [rsp+170h+var_108]
0x1800272f0  jz      short loc_180027302
0x1800272f2  mov     qword ptr [rsp+170h+length], r13
0x1800272f7  mov     [rdx], rax
0x1800272fa  add     qword ptr [rsp+170h+var_118+8], 8
0x180027300  jmp     short loc_180027312
0x180027302  lea     r8, [rsp+170h+length]
0x180027307  lea     rcx, [rsp+170h+var_118]
0x18002730c  call    ??$_Emplace_reallocate@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@?$vector@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>::_Emplace_reallocate<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> * const,std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> &&)
0x180027311  nop
0x180027312  lea     rcx, [rsp+170h+length]
0x180027317  call    ??1?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@QEAA@XZ; std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>::~unique_ptr<_DNS_DOH_SERVER_SETTINGS>(void)
0x18002731c  mov     rax, qword ptr [rsp+170h+var_118+8]
0x180027321  mov     rbx, [rax-8]
0x180027325  mov     [rbx+8], r13
0x180027329  mov     rax, r13
0x18002732c  mov     ecx, dword ptr [rbp+70h+var_F0+4]
0x18002732f  test    cl, 1
0x180027332  jz      short loc_180027340
0x180027334  mov     eax, 11h
0x180027339  mov     [rbx+8], rax
0x18002733d  mov     ecx, dword ptr [rbp+70h+var_F0+4]
0x180027340  test    cl, 2
0x180027343  jz      short loc_180027350
0x180027345  or      rax, 2
0x180027349  mov     [rbx+8], rax
0x18002734d  mov     ecx, dword ptr [rbp+70h+var_F0+4]
0x180027350  test    cl, 4
0x180027353  jz      short loc_18002735D
0x180027355  or      rax, 4
0x180027359  mov     [rbx+8], rax
0x18002735d  lea     rax, sourceString
0x180027364  mov     [rbx], rax
0x180027367  test    byte ptr [rbp+70h+var_F0+4], 1
0x18002736b  jnz     short loc_180027373
0x18002736d  test    byte ptr [rbp+70h+var_F0+4], 2
0x180027371  jz      short loc_1800273DC
0x180027373  mov     [rsp+170h+length], r13d
0x180027378  lea     rdx, [rsp+170h+length]; length
0x18002737d  mov     rcx, [rbp+70h+var_E0]; string
0x180027381  call    cs:__imp_WindowsGetStringRawBuffer
0x180027387  mov     rdx, rax
0x18002738a  lea     rcx, [rsp+170h+var_138]
0x18002738f  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180027394  nop
0x180027395  mov     rdx, qword ptr [rsp+170h+var_130+8]
0x18002739a  cmp     rdx, [rsp+170h+var_120]
0x18002739f  jz      short loc_1800273B6
0x1800273a1  mov     rax, [rsp+170h+var_138]
0x1800273a6  mov     [rdx], rax
0x1800273a9  mov     [rsp+170h+var_138], r13
0x1800273ae  add     qword ptr [rsp+170h+var_130+8], 8
0x1800273b4  jmp     short loc_1800273C6
0x1800273b6  lea     r8, [rsp+170h+var_138]
0x1800273bb  lea     rcx, [rsp+170h+var_130]
0x1800273c0  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800273c5  nop
0x1800273c6  lea     rcx, [rsp+170h+var_138]
0x1800273cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800273d0  mov     rax, qword ptr [rsp+170h+var_130+8]
0x1800273d5  mov     rcx, [rax-8]
0x1800273d9  mov     [rbx], rcx
0x1800273dc  movsxd  rax, r15d
0x1800273df  lea     rcx, [rax+rax*2]
0x1800273e3  mov     dword ptr [rsi+rcx*8], 1
0x1800273ea  mov     [rsi+rcx*8+4], edi
0x1800273ee  mov     dword ptr [rsi+rcx*8+8], 1
0x1800273f6  mov     [rsi+rcx*8+10h], rbx
0x1800273fb  inc     r15d
0x1800273fe  lea     rcx, [rbp+70h+var_F0]; struct Windows::Networking::UX::DnsServer *
0x180027402  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180027407  nop
0x180027408  mov     rcx, [rsp+170h+string]; string
0x18002740d  call    cs:__imp_WindowsDeleteString
0x180027413  inc     edi
0x180027415  cmp     edi, [rsp+170h+var_150]
0x180027419  jb      loc_180027211
0x18002741f  mov     [rsp+170h+var_14C], r13d
0x180027424  lea     rdx, [rsp+170h+var_14C]; length
0x180027429  mov     rcx, [rsp+170h+string1]; string
0x18002742e  call    cs:__imp_WindowsGetStringRawBuffer
0x180027434  mov     rdi, rax
0x180027437  mov     edx, [rsp+170h+var_14C]
0x18002743b  inc     edx
0x18002743d  mov     eax, 2
0x180027442  mul     rdx
0x180027445  mov     rbx, rax
0x180027448  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002744f  cmovb   rbx, rax
0x180027453  mov     rcx, rbx; unsigned __int64
0x180027456  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002745b  mov     r14, rax
0x18002745e  mov     r8, rbx; Size
0x180027461  xor     edx, edx; Val
0x180027463  mov     rcx, rax; void *
0x180027466  call    memset_0
0x18002746b  mov     [rsp+170h+var_138], r14
0x180027470  mov     rbx, [rbp+78h]
0x180027474  mov     edx, [rsp+170h+var_14C]
0x180027478  inc     edx
0x18002747a  mov     r8, rdi
0x18002747d  mov     rcx, r14
0x180027480  call    cs:__imp__o_wcscpy_s
0x180027486  test    eax, eax
0x180027488  jz      short loc_1800274E4
0x18002748a  mov     r9d, 80070057h; char *
0x180027490  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x180027497  mov     edx, 152h; void *
0x18002749c  mov     rcx, rbx; this
0x18002749f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800274a5  mov     r9d, eax; char *
0x1800274a8  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800274af  mov     edx, 11Fh; void *
0x1800274b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800274ba  mov     r9d, eax; char *
0x1800274bd  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800274c4  mov     edx, 121h; void *
0x1800274c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800274cf  mov     r9d, eax; char *
0x1800274d2  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x1800274d9  mov     edx, 11Ch; void *
0x1800274de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800274e4  mov     [rbp+70h+var_80], r15d
0x1800274e8  mov     [rbp+70h+Settings.NameServer], r14
0x1800274ec  mov     [rbp+70h+var_78], rsi
0x1800274f0  movups  xmm0, xmmword ptr [r12]
0x1800274f5  movdqu  xmmword ptr [rsp+170h+string], xmm0
0x1800274fb  lea     rdx, [rbp+70h+Settings]; Settings
0x1800274ff  lea     rcx, [rsp+170h+string]; Interface
0x180027504  call    cs:__imp_SetInterfaceDnsSettings
0x18002750a  mov     rcx, [rbp+78h]; this
0x18002750e  test    eax, eax
0x180027510  jz      short loc_180027527
0x180027512  mov     r9d, eax; char *
0x180027515  lea     r8, aOnecoreuapNetU_10; "onecoreuap\\net\\ux\\dnshelper\\lib\\dn"...
0x18002751c  mov     edx, 15Ah; void *
0x180027521  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180027527  lea     rcx, [rsp+170h+var_138]
0x18002752c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180027531  nop
0x180027532  mov     rcx, qword ptr [rsp+170h+var_130]
0x180027537  test    rcx, rcx
0x18002753a  jz      short loc_18002756A
0x18002753c  mov     rdx, qword ptr [rsp+170h+var_130+8]
0x180027541  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x180027546  mov     rcx, qword ptr [rsp+170h+var_130]
0x18002754b  mov     rdx, [rsp+170h+var_120]
0x180027550  sub     rdx, rcx
0x180027553  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180027557  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002755c  xorps   xmm0, xmm0
0x18002755f  movdqu  [rsp+170h+var_130], xmm0
0x180027565  mov     [rsp+170h+var_120], r13
0x18002756a  mov     rcx, qword ptr [rsp+170h+var_118]
0x18002756f  test    rcx, rcx
0x180027572  jz      short loc_1800275A2
0x180027574  mov     rdx, qword ptr [rsp+170h+var_118+8]
0x180027579  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@U_DNS_DOH_SERVER_SETTINGS@@U?$default_delete@U_DNS_DOH_SERVER_SETTINGS@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>>>(std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> *,std::unique_ptr<_DNS_DOH_SERVER_SETTINGS> * const,std::allocator<std::unique_ptr<_DNS_DOH_SERVER_SETTINGS>> &)
0x18002757e  mov     rcx, qword ptr [rsp+170h+var_118]
0x180027583  mov     rdx, [rsp+170h+var_108]
0x180027588  sub     rdx, rcx
0x18002758b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002758f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180027594  xorps   xmm0, xmm0
0x180027597  movdqu  [rsp+170h+var_118], xmm0
0x18002759d  mov     [rsp+170h+var_108], r13
0x1800275a2  mov     rcx, [rsp+170h+string1]; string
0x1800275a7  call    cs:__imp_WindowsDeleteString
0x1800275ad  mov     [rsp+170h+string1], r13
0x1800275b2  lea     rcx, [rbp+70h+var_D8]
0x1800275b6  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800275bb  mov     rcx, [rbp+70h+var_40]
0x1800275bf  xor     rcx, rsp; StackCookie
0x1800275c2  call    __security_check_cookie
0x1800275c7  mov     rbx, [rsp+170h+arg_0]
0x1800275cf  add     rsp, 140h
0x1800275d6  pop     r15
0x1800275d8  pop     r14
0x1800275da  pop     r13
0x1800275dc  pop     r12
0x1800275de  pop     rdi
0x1800275df  pop     rsi
0x1800275e0  pop     rbp
0x1800275e1  retn
  ... truncated ...
```
