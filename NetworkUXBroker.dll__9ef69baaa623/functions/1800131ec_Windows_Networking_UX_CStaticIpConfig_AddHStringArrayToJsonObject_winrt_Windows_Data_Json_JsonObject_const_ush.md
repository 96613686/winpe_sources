# Windows::Networking::UX::CStaticIpConfig::AddHStringArrayToJsonObject(winrt::Windows::Data::Json::JsonObject const &,ushort const * const,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *)

- ea: `0x1800131ec`
- end: `0x1800133f7`
- name: `?AddHStringArrayToJsonObject@CStaticIpConfig@UX@Networking@Windows@@AEAAJAEBUJsonObject@Json@Data@4winrt@@QEBGPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180019960`

## callees

- `0x18000c824`
- `0x18000cd70`
- `0x18000ce20`
- `0x18000d528`
- `0x18000d6a4`
- `0x18000e768`
- `0x18000e8b8`
- `0x18000f1d0`
- `0x1800131ec`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001328b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013359`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001328b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800132da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013359`

## string_xrefs

- `0x180013236`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x1800132c0`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::AddHStringArrayToJsonObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // eax
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 result; // rax
  __int64 v8; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    v4 = (*(__int64 (**)(void))(*(_QWORD *)a4 + 56LL))();
    v6 = v4;
    if ( v4 >= 0 )
    {
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D1,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v4,
        v8);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2E6,
                           (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800131ec  mov     r11, rsp
0x1800131ef  mov     [r11+10h], rbx
0x1800131f3  mov     [r11+18h], rsi
0x1800131f7  mov     [r11+8], rcx
0x1800131fb  push    rdi
0x1800131fc  push    r14
0x1800131fe  push    r15
0x180013200  sub     rsp, 60h
0x180013204  mov     rsi, r9
0x180013207  mov     r14, r8
0x18001320a  mov     r15, rdx
0x18001320d  mov     dword ptr [r11+8], 0
0x180013215  mov     rax, [r9]
0x180013218  lea     rdx, [r11+8]
0x18001321c  mov     rcx, r9
0x18001321f  mov     rax, [rax+38h]
0x180013223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013228  mov     ebx, eax
0x18001322a  test    eax, eax
0x18001322c  jns     short loc_18001324E
0x18001322e  mov     rcx, [rsp+78h]; this
0x180013233  mov     r9d, eax; char *
0x180013236  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x18001323d  mov     edx, 2D1h; void *
0x180013242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013247  mov     eax, ebx
0x180013249  jmp     loc_1800133E0
0x18001324e  cmp     [rsp+78h+arg_0], 0
0x180013256  jbe     loc_1800133D5
0x18001325c  lea     rcx, [rsp+78h+var_58]; this
0x180013261  call    ??0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonArray::JsonArray(void)
0x180013266  nop
0x180013267  xor     edi, edi
0x180013269  mov     [rsp+78h+string], 0
0x180013275  cmp     edi, [rsp+78h+arg_0]
0x18001327c  jnb     loc_180013366
0x180013282  mov     rax, [rsi]
0x180013285  mov     rbx, [rax+30h]
0x180013289  xor     ecx, ecx; string
0x18001328b  call    cs:__imp_WindowsDeleteString
0x180013291  mov     [rsp+78h+string], 0
0x18001329d  lea     r8, [rsp+78h+string]
0x1800132a5  mov     edx, edi
0x1800132a7  mov     rcx, rsi
0x1800132aa  mov     rax, rbx
0x1800132ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132b2  mov     ebx, eax
0x1800132b4  test    eax, eax
0x1800132b6  jns     short loc_1800132FD
0x1800132b8  mov     rcx, [rsp+78h]; this
0x1800132bd  mov     r9d, eax; char *
0x1800132c0  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800132c7  mov     edx, 2D9h; void *
0x1800132cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800132d1  nop
0x1800132d2  mov     rcx, [rsp+78h+string]; string
0x1800132da  call    cs:__imp_WindowsDeleteString
0x1800132e0  mov     [rsp+78h+string], 0
0x1800132ec  lea     rcx, [rsp+78h+var_58]; this
0x1800132f1  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x1800132f6  mov     eax, ebx
0x1800132f8  jmp     loc_1800133E0
0x1800132fd  mov     rax, [rsp+78h+string]
0x180013305  mov     [rsp+78h+string], 0
0x180013311  mov     [rsp+78h+var_48], rax
0x180013316  mov     [rsp+78h+var_40], rax
0x18001331b  lea     rdx, [rsp+78h+var_40]
0x180013320  lea     rcx, [rsp+78h+var_50]; struct winrt::param::hstring *
0x180013325  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x18001332a  nop
0x18001332b  lea     rdx, [rsp+78h+var_50]
0x180013330  lea     rcx, [rsp+78h+var_58]
0x180013335  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(winrt::Windows::Data::Json::IJsonValue const &)
0x18001333a  nop
0x18001333b  lea     rcx, [rsp+78h+var_50]; this
0x180013340  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x180013345  nop
0x180013346  lea     rcx, [rsp+78h+var_48]
0x18001334b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180013350  nop
0x180013351  mov     rcx, [rsp+78h+string]; string
0x180013359  call    cs:__imp_WindowsDeleteString
0x18001335f  inc     edi
0x180013361  jmp     loc_180013269
0x180013366  mov     rcx, [rsp+78h+var_58]
0x18001336b  test    rcx, rcx
0x18001336e  jz      short loc_18001339A
0x180013370  mov     rax, [rcx]
0x180013373  lea     r8, [rsp+78h+string]
0x18001337b  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180013382  mov     rax, [rax]
0x180013385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001338a  mov     rax, [rsp+78h+string]
0x180013392  mov     [rsp+78h+string], rax
0x18001339a  mov     rdx, r14; unsigned __int16 *
0x18001339d  lea     rcx, [rsp+78h+var_40]; this
0x1800133a2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800133a7  lea     r8, [rsp+78h+string]
0x1800133af  lea     rdx, [rsp+78h+var_40]
0x1800133b4  mov     rcx, r15
0x1800133b7  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800133bc  nop
0x1800133bd  lea     rcx, [rsp+78h+string]; this
0x1800133c5  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x1800133ca  nop
0x1800133cb  lea     rcx, [rsp+78h+var_58]; this
0x1800133d0  call    ??1IJsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::IJsonObject::~IJsonObject(void)
0x1800133d5  xor     eax, eax
0x1800133d7  jmp     short loc_1800133E0
0x1800133d9  mov     eax, [rsp+78h+arg_0]
0x1800133e0  lea     r11, [rsp+78h+var_18]
0x1800133e5  mov     rbx, [r11+28h]
0x1800133e9  mov     rsi, [r11+30h]
0x1800133ed  mov     rsp, r11
0x1800133f0  pop     r15
0x1800133f2  pop     r14
0x1800133f4  pop     rdi
0x1800133f5  retn
```
