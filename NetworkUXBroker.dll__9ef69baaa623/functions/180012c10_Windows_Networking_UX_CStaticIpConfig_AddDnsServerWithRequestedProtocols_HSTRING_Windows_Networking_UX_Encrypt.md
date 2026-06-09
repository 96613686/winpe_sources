# Windows::Networking::UX::CStaticIpConfig::AddDnsServerWithRequestedProtocols(HSTRING__ *,Windows::Networking::UX::EncryptedDnsProtocols)

- ea: `0x180012c10`
- end: `0x180012ef0`
- name: `?AddDnsServerWithRequestedProtocols@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@W4EncryptedDnsProtocols@234@@Z`
- size: `736`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002520`
- `0x18000e768`
- `0x18000f054`
- `0x18000f0b0`
- `0x180011c58`
- `0x180012c10`
- `0x180013b8c`
- `0x180016d54`
- `0x180019574`
- `0x18001abd4`
- `0x180039d00`
- `0x180039d8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012dbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012dbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012c7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012cc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012dfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012e81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012c7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012cc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012dfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012e81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ead`

## string_xrefs

- `0x180012c4d`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180012cab`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180012d5c`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180012dd3`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180012e61`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::AddDnsServerWithRequestedProtocols(
        __int64 a1,
        HSTRING a2,
        int a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  void *v10; // rdx
  const char *v11; // r9
  __int64 v12; // r9
  HSTRING v13; // rcx
  int WellKnownDnsServerTemplate; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ebx
  void *v18; // rdx
  const WCHAR *v19; // rax
  HRESULT v20; // eax
  unsigned int v21; // ebx
  void *v22; // rdx
  int v23; // eax
  unsigned int v24; // ebx
  void *v25; // rdx
  void *v26; // rdx
  HSTRING string; // [rsp+20h] [rbp-78h] BYREF
  HANDLE v28; // [rsp+28h] [rbp-70h] BYREF
  __int128 v29; // [rsp+30h] [rbp-68h] BYREF
  HSTRING v30; // [rsp+40h] [rbp-58h] BYREF
  __int128 v31; // [rsp+50h] [rbp-48h] BYREF
  UINT32 length[4]; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( (a3 & 2) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)0x80070057LL,
      (int)string);
    return 2147942487LL;
  }
  try
  {
    wil::run_as_self(&v28);
    WindowsDeleteString(0);
    string = 0;
    v8 = Windows::Networking::UX::CStaticIpConfig::ShortenIpString(v7, *(unsigned int *)(a1 + 32), a2, &string);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v8,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        &v28,
        v10);
      return v9;
    }
    v29 = 0;
    v30 = 0;
    LOBYTE(v29) = DnsServerIsWellKnownDoh(a2);
    v13 = string;
    string = 0;
    *((_QWORD *)&v29 + 1) = v13;
    DWORD1(v29) = a3;
    if ( (_BYTE)v29 && (a3 & 1) != 0 )
    {
      v31 = 0;
      *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v31) = 0;
      WellKnownDnsServerTemplate = GetWellKnownDnsServerTemplate(v13);
      v17 = WellKnownDnsServerTemplate;
      if ( WellKnownDnsServerTemplate < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB0,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)WellKnownDnsServerTemplate,
          (int)string);
        std::wstring::_Tidy_deallocate(&v31);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&v29);
        WindowsDeleteString(string);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
          &v28,
          v18);
        return v17;
      }
      v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v31, v15, v16);
      v20 = WindowsCreateString(v19, length[0], &v30);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)v20,
          (int)string);
        std::wstring::_Tidy_deallocate(&v31);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&v29);
        WindowsDeleteString(string);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
          &v28,
          v22);
        return v21;
      }
      std::wstring::_Tidy_deallocate(&v31);
    }
    v31 = v29;
    *(_QWORD *)length = v30;
    LOBYTE(v12) = 1;
    v23 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
            *(_QWORD *)(a1 + 72),
            0,
            &v31,
            v12);
    v24 = v23;
    if ( v23 >= 0 )
    {
      FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&v29);
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        &v28,
        v26);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v23,
        (int)string);
      FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&v29);
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        &v28,
        v25);
      result = v24;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB8,
                           (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180012c10  mov     [rsp+arg_18], rbx
0x180012c15  push    rsi
0x180012c16  push    rdi
0x180012c17  push    r14
0x180012c19  sub     rsp, 80h
0x180012c20  mov     rax, cs:__security_cookie
0x180012c27  xor     rax, rsp
0x180012c2a  mov     [rsp+98h+var_28], rax
0x180012c2f  mov     ebx, r8d
0x180012c32  mov     rsi, rdx
0x180012c35  mov     r14, rcx
0x180012c38  test    bl, 2
0x180012c3b  jz      short loc_180012C65
0x180012c3d  mov     rcx, [rsp+98h]; this
0x180012c45  mov     ebx, 80070057h
0x180012c4a  mov     r9d, ebx; char *
0x180012c4d  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012c54  mov     edx, 0A1h; void *
0x180012c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c5e  mov     eax, ebx
0x180012c60  jmp     loc_180012ECE
0x180012c65  lea     rcx, [rsp+98h+var_70]
0x180012c6a  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x180012c6f  mov     [rsp+98h+string], 0
0x180012c78  xor     ecx, ecx; string
0x180012c7a  call    cs:__imp_WindowsDeleteString
0x180012c80  mov     [rsp+98h+string], 0; int
0x180012c89  lea     r9, [rsp+98h+string]
0x180012c8e  mov     r8, rsi
0x180012c91  mov     edx, [r14+20h]
0x180012c95  call    ?ShortenIpString@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAPEAU6@@Z; Windows::Networking::UX::CStaticIpConfig::ShortenIpString(Windows::Networking::UX::IpFamily,HSTRING__ *,HSTRING__ * *)
0x180012c9a  mov     edi, eax
0x180012c9c  test    eax, eax
0x180012c9e  jns     short loc_180012CE1
0x180012ca0  mov     rcx, [rsp+98h]; this
0x180012ca8  mov     r9d, eax; char *
0x180012cab  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012cb2  mov     edx, 0A7h; void *
0x180012cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012cbc  mov     rcx, [rsp+98h+string]; string
0x180012cc1  call    cs:__imp_WindowsDeleteString
0x180012cc7  mov     [rsp+98h+string], 0
0x180012cd0  lea     rcx, [rsp+98h+var_70]
0x180012cd5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180012cda  mov     eax, edi
0x180012cdc  jmp     loc_180012ECE
0x180012ce1  xorps   xmm0, xmm0
0x180012ce4  xor     eax, eax
0x180012ce6  movups  [rsp+98h+var_68], xmm0
0x180012ceb  mov     [rsp+98h+var_58], rax
0x180012cf0  mov     rcx, rsi; HSTRING
0x180012cf3  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x180012cf8  mov     byte ptr [rsp+98h+var_68], al
0x180012cfc  mov     rcx, [rsp+98h+string]; string
0x180012d01  mov     [rsp+98h+string], 0; int
0x180012d0a  mov     qword ptr [rsp+98h+var_68+8], rcx
0x180012d0f  mov     dword ptr [rsp+98h+var_68+4], ebx
0x180012d13  test    al, al
0x180012d15  jz      loc_180012E27
0x180012d1b  test    bl, 1
0x180012d1e  jz      loc_180012E27
0x180012d24  xorps   xmm0, xmm0
0x180012d27  movups  [rsp+98h+var_48], xmm0
0x180012d2c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180012d34  movdqu  xmmword ptr [rsp+98h+length], xmm1
0x180012d3a  xor     eax, eax
0x180012d3c  mov     word ptr [rsp+98h+var_48], ax
0x180012d41  lea     rdx, [rsp+98h+var_48]
0x180012d46  call    ?GetWellKnownDnsServerTemplate@@YAJPEAUHSTRING__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWellKnownDnsServerTemplate(HSTRING__ *,std::wstring &)
0x180012d4b  mov     ebx, eax
0x180012d4d  test    eax, eax
0x180012d4f  jns     short loc_180012DA6
0x180012d51  mov     rcx, [rsp+98h]; this
0x180012d59  mov     r9d, eax; char *
0x180012d5c  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012d63  mov     edx, 0B0h; void *
0x180012d68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d6d  lea     rcx, [rsp+98h+var_48]
0x180012d72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012d77  lea     rcx, [rsp+98h+var_68]; struct Windows::Networking::UX::DnsServer *
0x180012d7c  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180012d81  mov     rcx, [rsp+98h+string]; string
0x180012d86  call    cs:__imp_WindowsDeleteString
0x180012d8c  mov     [rsp+98h+string], 0
0x180012d95  lea     rcx, [rsp+98h+var_70]
0x180012d9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180012d9f  mov     eax, ebx
0x180012da1  jmp     loc_180012ECE
0x180012da6  lea     rcx, [rsp+98h+var_48]
0x180012dab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012db0  mov     rcx, rax; sourceString
0x180012db3  lea     r8, [rsp+98h+var_58]; string
0x180012db8  mov     edx, [rsp+98h+length]; length
0x180012dbc  call    cs:__imp_WindowsCreateString
0x180012dc2  mov     ebx, eax
0x180012dc4  test    eax, eax
0x180012dc6  jns     short loc_180012E1D
0x180012dc8  mov     rcx, [rsp+98h]; this
0x180012dd0  mov     r9d, eax; char *
0x180012dd3  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012dda  mov     edx, 0B1h; void *
0x180012ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012de4  lea     rcx, [rsp+98h+var_48]
0x180012de9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012dee  lea     rcx, [rsp+98h+var_68]; struct Windows::Networking::UX::DnsServer *
0x180012df3  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180012df8  mov     rcx, [rsp+98h+string]; string
0x180012dfd  call    cs:__imp_WindowsDeleteString
0x180012e03  mov     [rsp+98h+string], 0
0x180012e0c  lea     rcx, [rsp+98h+var_70]
0x180012e11  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180012e16  mov     eax, ebx
0x180012e18  jmp     loc_180012ECE
0x180012e1d  lea     rcx, [rsp+98h+var_48]
0x180012e22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012e27  movups  xmm0, [rsp+98h+var_68]
0x180012e2c  movaps  [rsp+98h+var_48], xmm0
0x180012e31  movsd   xmm1, [rsp+98h+var_58]
0x180012e37  movsd   qword ptr [rsp+98h+length], xmm1
0x180012e3d  mov     r9b, 1
0x180012e40  lea     r8, [rsp+98h+var_48]
0x180012e45  xor     edx, edx
0x180012e47  mov     rcx, [r14+48h]
0x180012e4b  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180012e50  mov     ebx, eax
0x180012e52  test    eax, eax
0x180012e54  jns     short loc_180012E9E
0x180012e56  mov     rcx, [rsp+98h]; this
0x180012e5e  mov     r9d, eax; char *
0x180012e61  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012e68  mov     edx, 0B4h; void *
0x180012e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e72  lea     rcx, [rsp+98h+var_68]; struct Windows::Networking::UX::DnsServer *
0x180012e77  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180012e7c  mov     rcx, [rsp+98h+string]; string
0x180012e81  call    cs:__imp_WindowsDeleteString
0x180012e87  mov     [rsp+98h+string], 0
0x180012e90  lea     rcx, [rsp+98h+var_70]
0x180012e95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180012e9a  mov     eax, ebx
0x180012e9c  jmp     short loc_180012ECE
0x180012e9e  lea     rcx, [rsp+98h+var_68]; struct Windows::Networking::UX::DnsServer *
0x180012ea3  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180012ea8  mov     rcx, [rsp+98h+string]; string
0x180012ead  call    cs:__imp_WindowsDeleteString
0x180012eb3  mov     [rsp+98h+string], 0
0x180012ebc  lea     rcx, [rsp+98h+var_70]
0x180012ec1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180012ec6  xor     eax, eax
0x180012ec8  jmp     short loc_180012ECE
0x180012eca  mov     eax, dword ptr [rsp+98h+string]
0x180012ece  mov     rcx, [rsp+98h+var_28]
0x180012ed3  xor     rcx, rsp; StackCookie
0x180012ed6  call    __security_check_cookie
0x180012edb  mov     rbx, [rsp+98h+arg_18]
0x180012ee3  add     rsp, 80h
0x180012eea  pop     r14
0x180012eec  pop     rdi
0x180012eed  pop     rsi
0x180012eee  retn
```
