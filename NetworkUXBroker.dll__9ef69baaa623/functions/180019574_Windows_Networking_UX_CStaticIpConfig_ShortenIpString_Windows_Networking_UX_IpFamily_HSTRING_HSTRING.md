# Windows::Networking::UX::CStaticIpConfig::ShortenIpString(Windows::Networking::UX::IpFamily,HSTRING__ *,HSTRING__ * *)

- ea: `0x180019574`
- end: `0x180019749`
- name: `?ShortenIpString@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAPEAU6@@Z`
- size: `469`
- prototype: `int __high(enum Windows::Networking::UX::IpFamily, HSTRING, HSTRING *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800125b0`
- `0x180012680`
- `0x180012c10`
- `0x180012f00`
- `0x180013120`

## callees

- `0x180002520`
- `0x18000e768`
- `0x18001918c`
- `0x180019574`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800196f7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800196f7`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800195e0`
- `ntdll!RtlIpv4StringToAddressExW` at `0x1800195e0`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180019618`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180019618`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180019698`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180019698`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800196c7`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800196c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180019643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180019710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180019643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180019710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800195cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800195cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019680`

## string_xrefs

- `0x1800195f3`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x18001965c`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
int __fastcall Windows::Networking::UX::CStaticIpConfig::ShortenIpString(__int64 a1, int a2, HSTRING a3, HSTRING *a4)
{
  const WCHAR *StringRawBuffer; // rax
  LONG v6; // eax
  __int64 v7; // rdx
  __int64 v9; // rdx
  HRESULT String; // ebx
  __int64 v11; // rdx
  const WCHAR *v12; // rax
  wchar_t *v13; // rax
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-E0h]
  USHORT Port[2]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG AddressStringLength; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t Delimiter[4]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *Context; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v20; // [rsp+48h] [rbp-B8h]
  in_addr Address[9]; // [rsp+4Ah] [rbp-B6h] BYREF
  WCHAR AddressString[72]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+18h]

  AddressStringLength = 65;
  v20 = 0;
  Port[0] = 0;
  memset(Address, 0, 26);
  if ( a2 == 4 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v6 = RtlIpv4StringToAddressExW(StringRawBuffer, 1u, (struct in_addr *)&Address[0].S_un.S_un_w.s_w2, Port);
    if ( v6 < 0 )
    {
      v7 = 649;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v7,
               (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
               (const char *)(unsigned int)v6,
               v15);
    }
    v6 = RtlIpv4AddressToStringExW(
           (const struct in_addr *)&Address[0].S_un.S_un_w.s_w2,
           0,
           AddressString,
           &AddressStringLength);
    if ( v6 < 0 )
    {
      v7 = 650;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v7,
               (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
               (const char *)(unsigned int)v6,
               v15);
    }
    v9 = -1;
    do
      ++v9;
    while ( AddressString[v9] );
    String = WindowsCreateString(AddressString, v9, a4);
    if ( String < 0 )
    {
      v11 = 651;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)String,
        v15);
      return String;
    }
  }
  else if ( a2 == 6 )
  {
    v12 = WindowsGetStringRawBuffer(a3, 0);
    v6 = RtlIpv6StringToAddressExW(
           v12,
           (struct in6_addr *)&Address[1].S_un.S_un_w.s_w2,
           (PULONG)&Address[5].S_un.S_un_w.s_w2,
           Port);
    if ( v6 < 0 )
    {
      v7 = 656;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v7,
               (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
               (const char *)(unsigned int)v6,
               v15);
    }
    v6 = RtlIpv6AddressToStringExW(
           (const struct in6_addr *)&Address[1].S_un.S_un_w.s_w2,
           *(ULONG *)&Address[5].S_un.S_un_w.s_w2,
           0,
           AddressString,
           &AddressStringLength);
    if ( v6 < 0 )
    {
      v7 = 658;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v7,
               (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
               (const char *)(unsigned int)v6,
               v15);
    }
    wcscpy(Delimiter, L"%");
    Context = 0;
    v13 = wcstok_s(AddressString, Delimiter, &Context);
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    String = WindowsCreateString(v13, v14, a4);
    if ( String < 0 )
    {
      v11 = 663;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019574  mov     [rsp-8+arg_0], rbx
0x180019579  mov     [rsp-8+arg_8], rdi
0x18001957e  push    rbp
0x18001957f  lea     rbp, [rsp-10h]
0x180019584  sub     rsp, 110h
0x18001958b  mov     rax, cs:__security_cookie
0x180019592  xor     rax, rsp
0x180019595  mov     [rbp+10h+var_10], rax
0x180019599  xor     edi, edi
0x18001959b  mov     [rsp+110h+AddressStringLength], 41h ; 'A'
0x1800195a3  mov     [rsp+110h+var_C8], di
0x1800195a8  xorps   xmm0, xmm0
0x1800195ab  mov     [rsp+110h+Port], di
0x1800195b0  mov     rbx, r9
0x1800195b3  movups  xmmword ptr [rsp+110h+Address.S_un], xmm0
0x1800195b8  movups  xmmword ptr [rsp+110h+Address.S_un+0Ah], xmm0
0x1800195bd  cmp     edx, 4
0x1800195c0  jnz     loc_180019672
0x1800195c6  xor     edx, edx; length
0x1800195c8  mov     rcx, r8; string
0x1800195cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800195d1  lea     r9, [rsp+110h+Port]; Port
0x1800195d6  mov     dl, 1; Strict
0x1800195d8  mov     rcx, rax; AddressString
0x1800195db  lea     r8, [rsp+110h+Address.S_un+2]; Address
0x1800195e0  call    cs:__imp_RtlIpv4StringToAddressExW
0x1800195e6  test    eax, eax
0x1800195e8  jns     short loc_180019607
0x1800195ea  mov     edx, 289h; void *
0x1800195ef  mov     rcx, [rbp+18h]; this
0x1800195f3  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800195fa  mov     r9d, eax; char *
0x1800195fd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019602  jmp     loc_180019728
0x180019607  xor     edx, edx; Port
0x180019609  lea     r9, [rsp+110h+AddressStringLength]; AddressStringLength
0x18001960e  lea     r8, [rsp+110h+AddressString]; AddressString
0x180019613  lea     rcx, [rsp+110h+Address.S_un+2]; Address
0x180019618  call    cs:__imp_RtlIpv4AddressToStringExW
0x18001961e  test    eax, eax
0x180019620  jns     short loc_180019629
0x180019622  mov     edx, 28Ah
0x180019627  jmp     short loc_1800195EF
0x180019629  lea     rax, [rsp+110h+AddressString]
0x18001962e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019632  inc     rdx; length
0x180019635  cmp     [rax+rdx*2], di
0x180019639  jnz     short loc_180019632
0x18001963b  mov     r8, rbx; string
0x18001963e  lea     rcx, [rsp+110h+AddressString]; sourceString
0x180019643  call    cs:__imp_WindowsCreateString
0x180019649  mov     ebx, eax
0x18001964b  test    eax, eax
0x18001964d  jns     loc_180019726
0x180019653  mov     edx, 28Bh; void *
0x180019658  mov     rcx, [rbp+18h]; this
0x18001965c  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019663  mov     r9d, ebx; char *
0x180019666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001966b  mov     eax, ebx
0x18001966d  jmp     loc_180019728
0x180019672  cmp     edx, 6
0x180019675  jnz     loc_180019726
0x18001967b  xor     edx, edx; length
0x18001967d  mov     rcx, r8; string
0x180019680  call    cs:__imp_WindowsGetStringRawBuffer
0x180019686  mov     rcx, rax; AddressString
0x180019689  lea     r9, [rsp+110h+Port]; Port
0x18001968e  lea     r8, [rsp+110h+ScopeId]; ScopeId
0x180019693  lea     rdx, [rsp+110h+Address.S_un+6]; Address
0x180019698  call    cs:__imp_RtlIpv6StringToAddressExW
0x18001969e  test    eax, eax
0x1800196a0  jns     short loc_1800196AC
0x1800196a2  mov     edx, 290h
0x1800196a7  jmp     loc_1800195EF
0x1800196ac  mov     edx, [rsp+110h+ScopeId]; ScopeId
0x1800196b0  lea     rax, [rsp+110h+AddressStringLength]
0x1800196b5  xor     r8d, r8d; Port
0x1800196b8  mov     qword ptr [rsp+110h+var_F0], rax; AddressStringLength
0x1800196bd  lea     r9, [rsp+110h+AddressString]; AddressString
0x1800196c2  lea     rcx, [rsp+110h+Address.S_un+6]; Address
0x1800196c7  call    cs:__imp_RtlIpv6AddressToStringExW
0x1800196cd  test    eax, eax
0x1800196cf  jns     short loc_1800196DB
0x1800196d1  mov     edx, 292h
0x1800196d6  jmp     loc_1800195EF
0x1800196db  lea     r8, [rsp+110h+Context]; Context
0x1800196e0  mov     dword ptr [rsp+110h+Delimiter], 25h ; '%'
0x1800196e8  lea     rdx, [rsp+110h+Delimiter]; Delimiter
0x1800196ed  mov     [rsp+110h+Context], rdi
0x1800196f2  lea     rcx, [rsp+110h+AddressString]; String
0x1800196f7  call    cs:__imp_wcstok_s
0x1800196fd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019701  inc     rdx; length
0x180019704  cmp     [rax+rdx*2], di
0x180019708  jnz     short loc_180019701
0x18001970a  mov     r8, rbx; string
0x18001970d  mov     rcx, rax; sourceString
0x180019710  call    cs:__imp_WindowsCreateString
0x180019716  mov     ebx, eax
0x180019718  test    eax, eax
0x18001971a  jns     short loc_180019726
0x18001971c  mov     edx, 297h
0x180019721  jmp     loc_180019658
0x180019726  xor     eax, eax
0x180019728  mov     rcx, [rbp+10h+var_10]
0x18001972c  xor     rcx, rsp; StackCookie
0x18001972f  call    __security_check_cookie
0x180019734  lea     r11, [rsp+110h+var_s0]
0x18001973c  mov     rbx, [r11+10h]
0x180019740  mov     rdi, [r11+18h]
0x180019744  mov     rsp, r11
0x180019747  pop     rbp
0x180019748  retn
```
