# Windows::Networking::UX::Internal::CWiFiProfile::_ParseDnsFromConfig(_WLAN_PROFILE_IP_CONFIGURATION *,Windows::Networking::UX::IStaticIpConfig *)

- ea: `0x18005e7d0`
- end: `0x18005eb2c`
- name: `?_ParseDnsFromConfig@CWiFiProfile@Internal@UX@Networking@Windows@@AEAAJPEAU_WLAN_PROFILE_IP_CONFIGURATION@@PEAUIStaticIpConfig@345@@Z`
- size: `860`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CWiFiProfile *__hidden this, struct _WLAN_PROFILE_IP_CONFIGURATION *, struct Windows::Networking::UX::IStaticIpConfig *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005c910`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x1800097b4`
- `0x18001668c`
- `0x18005cfec`
- `0x18005e7d0`
- `0x18007a42c`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x18005e95d`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18005e95d`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18005e8c3`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18005e8c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e8d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e970`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eabb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eaf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e8d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e970`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ea8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eabb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eaf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005e8f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005e98c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ea00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005e8f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005e98c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ea00`
- `wlanapi!WlanProfileIpConfigurationGetDnsServerConfigurationList` at `0x18005e850`
- `wlanapi!WlanProfileIpConfigurationGetDnsServerConfigurationList` at `0x18005e850`
- `wlanapi!WlanProfileIpConfigurationGetDnsServerList` at `0x18005e81c`
- `wlanapi!WlanProfileIpConfigurationGetDnsServerList` at `0x18005e81c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall Windows::Networking::UX::Internal::CWiFiProfile::_ParseDnsFromConfig(
        Windows::Networking::UX::Internal::CWiFiProfile *this,
        struct _WLAN_PROFILE_IP_CONFIGURATION *a2,
        struct Windows::Networking::UX::IStaticIpConfig *a3)
{
  unsigned int DnsServerList; // eax
  __int64 v6; // rdx
  unsigned int i; // edi
  unsigned __int64 v9; // rbx
  __int64 v10; // r14
  int v11; // eax
  LONG v12; // eax
  HRESULT v13; // eax
  int v14; // ebx
  __int64 v15; // rdx
  int v16; // ecx
  unsigned int v17; // ebx
  HRESULT v18; // eax
  HRESULT v19; // r14d
  int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v24; // [rsp+38h] [rbp-C8h] BYREF
  ULONG AddressStringLength; // [rsp+40h] [rbp-C0h] BYREF
  ULONG length; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR AddressString[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v30[28]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR sourceString[72]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v28 = 0;
  v27 = 0;
  DnsServerList = WlanProfileIpConfigurationGetDnsServerList(a2, &v28);
  if ( DnsServerList )
  {
    v6 = 345;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
             (const char *)DnsServerList,
             v22);
  }
  if ( *(_DWORD *)a2 )
  {
    DnsServerList = WlanProfileIpConfigurationGetDnsServerConfigurationList(a2, &v27);
    if ( DnsServerList )
    {
      v6 = 348;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v6,
               (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
               (const char *)DnsServerList,
               v22);
    }
  }
  for ( i = 0; i < *((_DWORD *)a2 + 5); ++i )
  {
    v9 = (unsigned __int64)i << 7;
    v10 = v28;
    string = 0;
    v11 = *(unsigned __int16 *)(v9 + v28);
    if ( (_WORD)v11 == 2 )
    {
      *(_OWORD *)AddressString = 0;
      memset(v30, 0, sizeof(v30));
      AddressStringLength = 22;
      v12 = RtlIpv4AddressToStringExW((const struct in_addr *)(v9 + v28 + 4), 0, AddressString, &AddressStringLength);
      if ( v12 < 0 )
      {
        v21 = 362;
LABEL_32:
        v14 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v21,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                (const char *)(unsigned int)v12,
                v22);
        goto LABEL_33;
      }
      WindowsDeleteString(string);
      string = 0;
      v13 = WindowsCreateString(AddressString, AddressStringLength, &string);
      v14 = v13;
      if ( v13 < 0 )
      {
        v15 = 364;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
          (const char *)(unsigned int)v13,
          v22);
LABEL_33:
        WindowsDeleteString(string);
        return v14;
      }
    }
    else
    {
      if ( v11 != 23 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(2, *(unsigned __int16 *)(v9 + v28));
        goto LABEL_26;
      }
      memset_0(sourceString, 0, 0x82u);
      length = 65;
      v12 = RtlIpv6AddressToStringExW(
              (const struct in6_addr *)(v9 + v10 + 8),
              *(_DWORD *)(v9 + v10 + 24),
              0,
              sourceString,
              &length);
      if ( v12 < 0 )
      {
        v21 = 372;
        goto LABEL_32;
      }
      WindowsDeleteString(string);
      string = 0;
      v13 = WindowsCreateString(sourceString, length, &string);
      v14 = v13;
      if ( v13 < 0 )
      {
        v15 = 374;
        goto LABEL_13;
      }
    }
    if ( v27 )
    {
      v16 = *(_DWORD *)(4104LL * i + v27 + 4);
      v17 = (v16 & 1) != 0;
      if ( (v16 & 2) != 0 )
        v17 |= 2u;
      if ( (v16 & 4) != 0 )
        v17 |= 4u;
      v24 = 0;
      WindowsDeleteString(0);
      v24 = 0;
      v18 = WindowsCreateString((PCNZWCH)(4104LL * i + v27 + 8), 0x800u, &v24);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x190,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
          (const char *)(unsigned int)v18,
          v22);
        WindowsDeleteString(v24);
        v24 = 0;
        v14 = v19;
        goto LABEL_33;
      }
      v20 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, HSTRING, HSTRING, _QWORD))(*(_QWORD *)a3 + 144LL))(
              a3,
              string,
              v24,
              v17);
      v14 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x192,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
          (const char *)(unsigned int)v20,
          v22);
        WindowsDeleteString(v24);
        v24 = 0;
        goto LABEL_33;
      }
      WindowsDeleteString(v24);
      v24 = 0;
    }
LABEL_26:
    WindowsDeleteString(string);
  }
  return 0;
}

```

## disassembly

```asm
0x18005e7d0  mov     [rsp-8+arg_0], rbx
0x18005e7d5  mov     [rsp-8+arg_18], rsi
0x18005e7da  push    rbp
0x18005e7db  push    rdi
0x18005e7dc  push    r12
0x18005e7de  push    r14
0x18005e7e0  push    r15
0x18005e7e2  lea     rbp, [rsp-30h]
0x18005e7e7  sub     rsp, 130h
0x18005e7ee  mov     rax, cs:__security_cookie
0x18005e7f5  xor     rax, rsp
0x18005e7f8  mov     [rbp+50h+var_30], rax
0x18005e7fc  mov     r12, r8
0x18005e7ff  mov     rsi, rdx
0x18005e802  mov     [rsp+150h+var_100], 0
0x18005e80b  mov     [rsp+150h+var_108], 0
0x18005e814  lea     rdx, [rsp+150h+var_100]
0x18005e819  mov     rcx, rsi
0x18005e81c  call    cs:__imp_WlanProfileIpConfigurationGetDnsServerList
0x18005e822  test    eax, eax
0x18005e824  jz      short loc_18005E843
0x18005e826  mov     edx, 159h; void *
0x18005e82b  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005e832  mov     r9d, eax; char *
0x18005e835  mov     rcx, [rbp+58h]; this
0x18005e839  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005e83e  jmp     loc_18005EB04
0x18005e843  cmp     dword ptr [rsi], 0
0x18005e846  jz      short loc_18005E861
0x18005e848  lea     rdx, [rsp+150h+var_108]
0x18005e84d  mov     rcx, rsi
0x18005e850  call    cs:__imp_WlanProfileIpConfigurationGetDnsServerConfigurationList
0x18005e856  test    eax, eax
0x18005e858  jz      short loc_18005E861
0x18005e85a  mov     edx, 15Ch
0x18005e85f  jmp     short loc_18005E82B
0x18005e861  xor     edi, edi
0x18005e863  mov     ecx, 2
0x18005e868  cmp     edi, [rsi+14h]
0x18005e86b  jnb     loc_18005EB02
0x18005e871  mov     r15d, edi
0x18005e874  mov     ebx, edi
0x18005e876  shl     rbx, 7
0x18005e87a  mov     r14, [rsp+150h+var_100]
0x18005e87f  mov     [rsp+150h+string], 0
0x18005e888  movzx   eax, word ptr [rbx+r14]
0x18005e88d  cmp     ax, cx
0x18005e890  jnz     loc_18005E920
0x18005e896  xorps   xmm0, xmm0
0x18005e899  movups  xmmword ptr [rsp+150h+AddressString], xmm0
0x18005e89e  movups  xmmword ptr [rsp+150h+var_E8], xmm0
0x18005e8a3  movups  xmmword ptr [rsp+150h+var_E8+0Ch], xmm0
0x18005e8a8  mov     [rsp+150h+AddressStringLength], 16h
0x18005e8b0  xor     edx, edx; Port
0x18005e8b2  lea     rcx, [r14+4]
0x18005e8b6  add     rcx, rbx; Address
0x18005e8b9  lea     r9, [rsp+150h+AddressStringLength]; AddressStringLength
0x18005e8be  lea     r8, [rsp+150h+AddressString]; AddressString
0x18005e8c3  call    cs:__imp_RtlIpv4AddressToStringExW
0x18005e8c9  test    eax, eax
0x18005e8cb  js      loc_18005EA67
0x18005e8d1  mov     rcx, [rsp+150h+string]; string
0x18005e8d6  call    cs:__imp_WindowsDeleteString
0x18005e8dc  mov     [rsp+150h+string], 0
0x18005e8e5  lea     r8, [rsp+150h+string]; string
0x18005e8ea  mov     edx, [rsp+150h+AddressStringLength]; length
0x18005e8ee  lea     rcx, [rsp+150h+AddressString]; sourceString
0x18005e8f3  call    cs:__imp_WindowsCreateString
0x18005e8f9  mov     ebx, eax
0x18005e8fb  test    eax, eax
0x18005e8fd  jns     loc_18005E99C
0x18005e903  mov     edx, 16Ch; void *
0x18005e908  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005e90f  mov     r9d, eax; char *
0x18005e912  mov     rcx, [rbp+58h]; this
0x18005e916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e91b  jmp     loc_18005EAF3
0x18005e920  cmp     eax, 17h
0x18005e923  jnz     loc_18005EA4D
0x18005e929  xor     edx, edx; Val
0x18005e92b  lea     r8d, [rax+6Bh]; Size
0x18005e92f  lea     rcx, [rbp+50h+sourceString]; void *
0x18005e933  call    memset_0
0x18005e938  mov     [rsp+150h+length], 41h ; 'A'
0x18005e940  xor     r8d, r8d; Port
0x18005e943  lea     rcx, [r14+8]
0x18005e947  add     rcx, rbx; Address
0x18005e94a  lea     rax, [rsp+150h+length]
0x18005e94f  mov     qword ptr [rsp+150h+var_130], rax; int
0x18005e954  lea     r9, [rbp+50h+sourceString]; AddressString
0x18005e958  mov     edx, [rbx+r14+18h]; ScopeId
0x18005e95d  call    cs:__imp_RtlIpv6AddressToStringExW
0x18005e963  test    eax, eax
0x18005e965  js      loc_18005EAD9
0x18005e96b  mov     rcx, [rsp+150h+string]; string
0x18005e970  call    cs:__imp_WindowsDeleteString
0x18005e976  mov     [rsp+150h+string], 0
0x18005e97f  lea     r8, [rsp+150h+string]; string
0x18005e984  mov     edx, [rsp+150h+length]; length
0x18005e988  lea     rcx, [rbp+50h+sourceString]; sourceString
0x18005e98c  call    cs:__imp_WindowsCreateString
0x18005e992  mov     ebx, eax
0x18005e994  test    eax, eax
0x18005e996  js      loc_18005EACF
0x18005e99c  mov     rax, [rsp+150h+var_108]
0x18005e9a1  test    rax, rax
0x18005e9a4  jz      loc_18005EA55
0x18005e9aa  xor     ebx, ebx
0x18005e9ac  imul    r14, r15, 1008h
0x18005e9b3  mov     ecx, [r14+rax+4]
0x18005e9b8  lea     eax, [rbx+1]
0x18005e9bb  test    al, cl
0x18005e9bd  cmovnz  ebx, eax
0x18005e9c0  test    cl, 2
0x18005e9c3  jz      short loc_18005E9C8
0x18005e9c5  or      ebx, 2
0x18005e9c8  test    cl, 4
0x18005e9cb  jz      short loc_18005E9D0
0x18005e9cd  or      ebx, 4
0x18005e9d0  mov     [rsp+150h+var_118], 0
0x18005e9d9  xor     ecx, ecx; string
0x18005e9db  call    cs:__imp_WindowsDeleteString
0x18005e9e1  mov     [rsp+150h+var_118], 0
0x18005e9ea  mov     rcx, [rsp+150h+var_108]
0x18005e9ef  add     rcx, 8
0x18005e9f3  add     rcx, r14; sourceString
0x18005e9f6  lea     r8, [rsp+150h+var_118]; string
0x18005e9fb  mov     edx, 800h; length
0x18005ea00  call    cs:__imp_WindowsCreateString
0x18005ea06  mov     r14d, eax
0x18005ea09  test    eax, eax
0x18005ea0b  js      loc_18005EA9D
0x18005ea11  mov     rax, [r12]
0x18005ea15  mov     r9d, ebx
0x18005ea18  mov     r8, [rsp+150h+var_118]
0x18005ea1d  mov     rdx, [rsp+150h+string]
0x18005ea22  mov     rcx, r12
0x18005ea25  mov     rax, [rax+90h]
0x18005ea2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea31  mov     ebx, eax
0x18005ea33  test    eax, eax
0x18005ea35  js      short loc_18005EA6E
0x18005ea37  mov     rcx, [rsp+150h+var_118]; string
0x18005ea3c  call    cs:__imp_WindowsDeleteString
0x18005ea42  mov     [rsp+150h+var_118], 0
0x18005ea4b  jmp     short loc_18005EA55
0x18005ea4d  mov     edx, eax
0x18005ea4f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18005ea54  nop
0x18005ea55  mov     rcx, [rsp+150h+string]; string
0x18005ea5a  call    cs:__imp_WindowsDeleteString
0x18005ea60  inc     edi
0x18005ea62  jmp     loc_18005E863
0x18005ea67  mov     edx, 16Ah
0x18005ea6c  jmp     short loc_18005EADE
0x18005ea6e  mov     rcx, [rbp+58h]; this
0x18005ea72  mov     r9d, eax; char *
0x18005ea75  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005ea7c  mov     edx, 192h; void *
0x18005ea81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ea86  nop
0x18005ea87  mov     rcx, [rsp+150h+var_118]; string
0x18005ea8c  call    cs:__imp_WindowsDeleteString
0x18005ea92  mov     [rsp+150h+var_118], 0
0x18005ea9b  jmp     short loc_18005EAF3
0x18005ea9d  mov     rcx, [rbp+58h]; this
0x18005eaa1  mov     r9d, r14d; char *
0x18005eaa4  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005eaab  mov     edx, 190h; void *
0x18005eab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eab5  nop
0x18005eab6  mov     rcx, [rsp+150h+var_118]; string
0x18005eabb  call    cs:__imp_WindowsDeleteString
0x18005eac1  mov     [rsp+150h+var_118], 0
0x18005eaca  mov     ebx, r14d
0x18005eacd  jmp     short loc_18005EAF3
0x18005eacf  mov     edx, 176h
0x18005ead4  jmp     loc_18005E908
0x18005ead9  mov     edx, 174h; void *
0x18005eade  mov     r9d, eax; char *
0x18005eae1  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005eae8  mov     rcx, [rbp+58h]; this
0x18005eaec  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005eaf1  mov     ebx, eax
0x18005eaf3  mov     rcx, [rsp+150h+string]; string
0x18005eaf8  call    cs:__imp_WindowsDeleteString
0x18005eafe  mov     eax, ebx
0x18005eb00  jmp     short loc_18005EB04
0x18005eb02  xor     eax, eax
0x18005eb04  mov     rcx, [rbp+50h+var_30]
0x18005eb08  xor     rcx, rsp; StackCookie
0x18005eb0b  call    __security_check_cookie
0x18005eb10  lea     r11, [rsp+150h+var_20]
0x18005eb18  mov     rbx, [r11+30h]
0x18005eb1c  mov     rsi, [r11+48h]
0x18005eb20  mov     rsp, r11
0x18005eb23  pop     r15
0x18005eb25  pop     r14
0x18005eb27  pop     r12
0x18005eb29  pop     rdi
0x18005eb2a  pop     rbp
0x18005eb2b  retn
```
