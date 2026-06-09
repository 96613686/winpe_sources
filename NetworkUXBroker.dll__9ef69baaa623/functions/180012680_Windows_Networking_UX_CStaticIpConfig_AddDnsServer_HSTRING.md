# Windows::Networking::UX::CStaticIpConfig::AddDnsServer(HSTRING__ *)

- ea: `0x180012680`
- end: `0x180012816`
- name: `?AddDnsServer@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(Windows::Networking::UX::CStaticIpConfig *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000e768`
- `0x180011c58`
- `0x180012680`
- `0x180013b8c`
- `0x180016d54`
- `0x180019574`
- `0x18001abd4`
- `0x180039d00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800126ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800126f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800126ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800126f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800127db`

## string_xrefs

- `0x1800126e0`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180012783`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::AddDnsServer(
        Windows::Networking::UX::CStaticIpConfig *this,
        HSTRING a2)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  void *v7; // rdx
  const char *v8; // r9
  __int64 result; // rax
  HSTRING v10; // rax
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rdx
  void *v15; // rdx
  int v16[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+30h] [rbp-38h]
  __int128 v18; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF
  HANDLE v22; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    wil::run_as_self(&v22);
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v5 = Windows::Networking::UX::CStaticIpConfig::ShortenIpString(v4, *((unsigned int *)this + 8), a2, &string);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v17 = 0;
      v16[0] = DnsServerIsWellKnownDoh(a2);
      v10 = string;
      string = 0;
      *(_QWORD *)&v16[2] = v10;
      v16[1] = 0;
      v18 = *(_OWORD *)v16;
      v19 = 0;
      LOBYTE(v11) = 1;
      v12 = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 9),
              0,
              &v18,
              v11);
      v13 = v12;
      if ( v12 >= 0 )
      {
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v16);
        WindowsDeleteString(string);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
          &v22,
          v15);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x95,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)v12,
          v16[0]);
        FreeDnsServer((struct Windows::Networking::UX::DnsServer *)v16);
        WindowsDeleteString(string);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
          &v22,
          v14);
        result = v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v5,
        v16[0]);
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        &v22,
        v7);
      result = v6;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x99,
                        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                        v8);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x180012680  mov     rax, rsp
0x180012683  mov     [rax+8], rbx
0x180012687  mov     [rax+10h], rsi
0x18001268b  push    rdi
0x18001268c  sub     rsp, 60h
0x180012690  mov     rdi, rdx
0x180012693  mov     rsi, rcx
0x180012696  lea     rcx, [rax+20h]
0x18001269a  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18001269f  mov     [rsp+68h+string], 0
0x1800126ab  xor     ecx, ecx; string
0x1800126ad  call    cs:__imp_WindowsDeleteString
0x1800126b3  mov     [rsp+68h+string], 0
0x1800126bf  lea     r9, [rsp+68h+string]
0x1800126c7  mov     r8, rdi
0x1800126ca  mov     edx, [rsi+20h]
0x1800126cd  call    ?ShortenIpString@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAPEAU6@@Z; Windows::Networking::UX::CStaticIpConfig::ShortenIpString(Windows::Networking::UX::IpFamily,HSTRING__ *,HSTRING__ * *)
0x1800126d2  mov     ebx, eax
0x1800126d4  test    eax, eax
0x1800126d6  jns     short loc_18001271F
0x1800126d8  mov     rcx, [rsp+68h]; this
0x1800126dd  mov     r9d, eax; char *
0x1800126e0  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800126e7  mov     edx, 90h; void *
0x1800126ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126f1  mov     rcx, [rsp+68h+string]; string
0x1800126f9  call    cs:__imp_WindowsDeleteString
0x1800126ff  mov     [rsp+68h+string], 0
0x18001270b  lea     rcx, [rsp+68h+arg_18]
0x180012713  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180012718  mov     eax, ebx
0x18001271a  jmp     loc_180012805
0x18001271f  xorps   xmm0, xmm0
0x180012722  xor     ebx, ebx
0x180012724  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180012729  mov     [rsp+68h+var_38], rbx
0x18001272e  mov     rcx, rdi; HSTRING
0x180012731  call    ?DnsServerIsWellKnownDoh@@YA_NPEAUHSTRING__@@@Z; DnsServerIsWellKnownDoh(HSTRING__ *)
0x180012736  mov     byte ptr [rsp+68h+var_48], al; int
0x18001273a  mov     rax, [rsp+68h+string]
0x180012742  mov     [rsp+68h+string], rbx
0x18001274a  mov     qword ptr [rsp+68h+var_48+8], rax
0x18001274f  mov     [rsp+68h+var_48+4], ebx
0x180012753  movups  xmm0, xmmword ptr [rsp+68h+var_48]
0x180012758  movaps  [rsp+68h+var_28], xmm0
0x18001275d  mov     [rsp+68h+var_18], rbx
0x180012762  mov     r9b, 1
0x180012765  lea     r8, [rsp+68h+var_28]
0x18001276a  xor     edx, edx
0x18001276c  mov     rcx, [rsi+48h]
0x180012770  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180012775  mov     ebx, eax
0x180012777  test    eax, eax
0x180012779  jns     short loc_1800127C9
0x18001277b  mov     rcx, [rsp+68h]; this
0x180012780  mov     r9d, eax; char *
0x180012783  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x18001278a  mov     edx, 95h; void *
0x18001278f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012794  lea     rcx, [rsp+68h+var_48]; struct Windows::Networking::UX::DnsServer *
0x180012799  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18001279e  mov     rcx, [rsp+68h+string]; string
0x1800127a6  call    cs:__imp_WindowsDeleteString
0x1800127ac  mov     [rsp+68h+string], 0
0x1800127b8  lea     rcx, [rsp+68h+arg_18]
0x1800127c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800127c5  mov     eax, ebx
0x1800127c7  jmp     short loc_180012805
0x1800127c9  lea     rcx, [rsp+68h+var_48]; struct Windows::Networking::UX::DnsServer *
0x1800127ce  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x1800127d3  mov     rcx, [rsp+68h+string]; string
0x1800127db  call    cs:__imp_WindowsDeleteString
0x1800127e1  mov     [rsp+68h+string], 0
0x1800127ed  lea     rcx, [rsp+68h+arg_18]
0x1800127f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800127fa  xor     eax, eax
0x1800127fc  jmp     short loc_180012805
0x1800127fe  mov     eax, dword ptr [rsp+68h+string]
0x180012805  mov     rbx, [rsp+68h+arg_0]
0x18001280a  mov     rsi, [rsp+68h+arg_8]
0x18001280f  add     rsp, 60h
0x180012813  pop     rdi
0x180012814  retn
```
