# Windows::Networking::UX::CStaticIpConfig::AddDnsServerWithRequestedProtocolsAndTemplate(HSTRING__ *,HSTRING__ *,Windows::Networking::UX::EncryptedDnsProtocols)

- ea: `0x180012f00`
- end: `0x180013110`
- name: `?AddDnsServerWithRequestedProtocolsAndTemplate@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@0W4EncryptedDnsProtocols@234@@Z`
- size: `528`
- prototype: `int __high(HSTRING, HSTRING, enum Windows::Networking::UX::EncryptedDnsProtocols)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002520`
- `0x18000e768`
- `0x18000f054`
- `0x18000f0b0`
- `0x180011c58`
- `0x180012f00`
- `0x180013b8c`
- `0x180016d54`
- `0x180019574`
- `0x18001abd4`
- `0x180039d00`
- `0x180039d8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180012fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180012fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180013043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180013043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800130db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012f42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800130db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800130a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800130a3`

## string_xrefs

- `0x180012f6a`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x18001300a`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x1800130b8`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::AddDnsServerWithRequestedProtocolsAndTemplate(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        int a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  HRESULT WellKnownDnsServerTemplate; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  const WCHAR *v17; // rax
  __int64 v18; // rcx
  HRESULT v19; // eax
  __int64 v20; // rdx
  void *v21; // rdx
  HSTRING v23; // [rsp+20h] [rbp-59h] BYREF
  HSTRING v24[2]; // [rsp+28h] [rbp-51h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  HANDLE v26[2]; // [rsp+40h] [rbp-39h] BYREF
  __int128 v27; // [rsp+50h] [rbp-29h] BYREF
  HSTRING v28; // [rsp+60h] [rbp-19h]
  __int128 v29; // [rsp+70h] [rbp-9h] BYREF
  UINT32 length[4]; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  wil::run_as_self(v26);
  v23 = 0;
  WindowsDeleteString(0);
  v8 = *(unsigned int *)(a1 + 32);
  v23 = 0;
  v10 = Windows::Networking::UX::CStaticIpConfig::ShortenIpString(v9, v8, a2, &v23);
  v11 = v10;
  if ( v10 >= 0 )
  {
    string = 0;
    *(_OWORD *)v24 = 0;
    LOBYTE(v24[0]) = DnsServerIsWellKnownDoh(a2);
    v24[1] = v23;
    v23 = 0;
    HIDWORD(v24[0]) = a4;
    if ( WindowsIsStringEmpty(a3) )
    {
      if ( LOBYTE(v24[0]) && (BYTE4(v24[0]) & 1) != 0 )
      {
        v29 = 0;
        LOWORD(v29) = 0;
        *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
        WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v24[1]);
        v11 = WellKnownDnsServerTemplate;
        if ( WellKnownDnsServerTemplate < 0 )
        {
          v16 = 203;
LABEL_8:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
            (const char *)(unsigned int)WellKnownDnsServerTemplate,
            (int)v23);
          std::wstring::_Tidy_deallocate(&v29);
LABEL_9:
          FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v24);
          goto LABEL_21;
        }
        v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v29, v14, v15);
        WellKnownDnsServerTemplate = WindowsCreateString(v17, length[0], &string);
        v11 = WellKnownDnsServerTemplate;
        if ( WellKnownDnsServerTemplate < 0 )
        {
          v16 = 204;
          goto LABEL_8;
        }
        std::wstring::_Tidy_deallocate(&v29);
      }
    }
    else if ( (BYTE4(v24[0]) & 1) != 0 || (BYTE4(v24[0]) & 2) != 0 )
    {
      v19 = WindowsDuplicateString(a3, &string);
      v11 = v19;
      if ( v19 < 0 )
      {
        v20 = 209;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)v19,
          (int)v23);
        goto LABEL_9;
      }
    }
    v18 = *(_QWORD *)(a1 + 72);
    LOBYTE(v12) = 1;
    v27 = *(_OWORD *)v24;
    v28 = string;
    v19 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
            v18,
            0,
            &v27,
            v12);
    v11 = v19;
    if ( v19 >= 0 )
    {
      FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v24);
      v11 = 0;
      goto LABEL_21;
    }
    v20 = 212;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0,
    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
    (const char *)(unsigned int)v10,
    (int)v23);
LABEL_21:
  WindowsDeleteString(v23);
  v23 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
    v26,
    v21);
  return v11;
}

```

## disassembly

```asm
0x180012f00  push    rbp
0x180012f02  push    rbx
0x180012f03  push    rsi
0x180012f04  push    rdi
0x180012f05  push    r14
0x180012f07  push    r15
0x180012f09  lea     rbp, [rsp-2Fh]
0x180012f0e  sub     rsp, 0A8h
0x180012f15  mov     rax, cs:__security_cookie
0x180012f1c  xor     rax, rsp
0x180012f1f  mov     [rbp+57h+var_40], rax
0x180012f23  mov     r15, rcx
0x180012f26  mov     r14d, r9d
0x180012f29  lea     rcx, [rbp+57h+var_90]
0x180012f2d  mov     rdi, r8
0x180012f30  mov     rsi, rdx
0x180012f33  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x180012f38  xor     ecx, ecx; string
0x180012f3a  mov     [rbp+57h+var_B0], 0
0x180012f42  call    cs:__imp_WindowsDeleteString
0x180012f48  mov     edx, [r15+20h]
0x180012f4c  lea     r9, [rbp+57h+var_B0]
0x180012f50  mov     r8, rsi
0x180012f53  mov     [rbp+57h+var_B0], 0
0x180012f5b  call    ?ShortenIpString@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAPEAU6@@Z; Windows::Networking::UX::CStaticIpConfig::ShortenIpString(Windows::Networking::UX::IpFamily,HSTRING__ *,HSTRING__ * *)
0x180012f60  mov     ebx, eax
0x180012f62  test    eax, eax
0x180012f64  jns     short loc_180012F83
0x180012f66  mov     rcx, [rbp+5Fh]; this
0x180012f6a  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012f71  mov     r9d, eax; char *
0x180012f74  mov     edx, 0C0h; void *
0x180012f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f7e  jmp     loc_1800130D7
0x180012f83  xorps   xmm0, xmm0
0x180012f86  xor     eax, eax
0x180012f88  mov     rcx, rsi; HSTRING
0x180012f8b  mov     [rbp+57h+string], rax
0x180012f8f  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180012f93  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x180012f98  mov     byte ptr [rbp+57h+var_A8], al
0x180012f9b  mov     rcx, rdi; string
0x180012f9e  mov     rax, [rbp+57h+var_B0]
0x180012fa2  mov     [rbp+57h+var_A8+8], rax
0x180012fa6  mov     [rbp+57h+var_B0], 0
0x180012fae  mov     dword ptr [rbp+57h+var_A8+4], r14d
0x180012fb2  call    cs:__imp_WindowsIsStringEmpty
0x180012fb8  test    eax, eax
0x180012fba  jz      loc_180013090
0x180012fc0  cmp     byte ptr [rbp+57h+var_A8], 0
0x180012fc4  jz      loc_18001305F
0x180012fca  test    byte ptr [rbp+57h+var_A8+4], 1
0x180012fce  jz      loc_18001305F
0x180012fd4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180012fdc  lea     rdx, [rbp+57h+var_60]
0x180012fe0  mov     rcx, [rbp+57h+var_A8+8]; string
0x180012fe4  xorps   xmm0, xmm0
0x180012fe7  xor     eax, eax
0x180012fe9  movups  [rbp+57h+var_60], xmm0
0x180012fed  mov     word ptr [rbp+57h+var_60], ax
0x180012ff1  movdqu  xmmword ptr [rbp+57h+length], xmm1
0x180012ff6  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x180012ffb  mov     ebx, eax
0x180012ffd  test    eax, eax
0x180012fff  jns     short loc_180013030
0x180013001  mov     edx, 0CBh; void *
0x180013006  mov     rcx, [rbp+5Fh]; this
0x18001300a  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180013011  mov     r9d, eax; char *
0x180013014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013019  lea     rcx, [rbp+57h+var_60]
0x18001301d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013022  lea     rcx, [rbp+57h+var_A8]; struct Windows::Networking::UX::DnsServer *
0x180013026  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18001302b  jmp     loc_1800130D7
0x180013030  lea     rcx, [rbp+57h+var_60]
0x180013034  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013039  mov     edx, [rbp+57h+length]; length
0x18001303c  lea     r8, [rbp+57h+string]; string
0x180013040  mov     rcx, rax; sourceString
0x180013043  call    cs:__imp_WindowsCreateString
0x180013049  mov     ebx, eax
0x18001304b  test    eax, eax
0x18001304d  jns     short loc_180013056
0x18001304f  mov     edx, 0CCh
0x180013054  jmp     short loc_180013006
0x180013056  lea     rcx, [rbp+57h+var_60]
0x18001305a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001305f  movups  xmm0, xmmword ptr [rbp+57h+var_A8]
0x180013063  lea     r8, [rbp+57h+var_80]
0x180013067  mov     rcx, [r15+48h]
0x18001306b  movsd   xmm1, [rbp+57h+string]
0x180013070  mov     r9b, 1
0x180013073  xor     edx, edx
0x180013075  movaps  [rbp+57h+var_80], xmm0
0x180013079  movsd   [rbp+57h+var_70], xmm1
0x18001307e  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180013083  mov     ebx, eax
0x180013085  test    eax, eax
0x180013087  jns     short loc_1800130CC
0x180013089  mov     edx, 0D4h
0x18001308e  jmp     short loc_1800130B4
0x180013090  test    byte ptr [rbp+57h+var_A8+4], 1
0x180013094  jnz     short loc_18001309C
0x180013096  test    byte ptr [rbp+57h+var_A8+4], 2
0x18001309a  jz      short loc_18001305F
0x18001309c  lea     rdx, [rbp+57h+string]; newString
0x1800130a0  mov     rcx, rdi; string
0x1800130a3  call    cs:__imp_WindowsDuplicateString
0x1800130a9  mov     ebx, eax
0x1800130ab  test    eax, eax
0x1800130ad  jns     short loc_18001305F
0x1800130af  mov     edx, 0D1h; void *
0x1800130b4  mov     rcx, [rbp+5Fh]; this
0x1800130b8  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800130bf  mov     r9d, eax; char *
0x1800130c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130c7  jmp     loc_180013022
0x1800130cc  lea     rcx, [rbp+57h+var_A8]; struct Windows::Networking::UX::DnsServer *
0x1800130d0  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x1800130d5  xor     ebx, ebx
0x1800130d7  mov     rcx, [rbp+57h+var_B0]; string
0x1800130db  call    cs:__imp_WindowsDeleteString
0x1800130e1  lea     rcx, [rbp+57h+var_90]
0x1800130e5  mov     [rbp+57h+var_B0], 0
0x1800130ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800130f2  mov     eax, ebx
0x1800130f4  mov     rcx, [rbp+57h+var_40]
0x1800130f8  xor     rcx, rsp; StackCookie
0x1800130fb  call    __security_check_cookie
0x180013100  add     rsp, 0A8h
0x180013107  pop     r15
0x180013109  pop     r14
0x18001310b  pop     rdi
0x18001310c  pop     rsi
0x18001310d  pop     rbx
0x18001310e  pop     rbp
0x18001310f  retn
```
