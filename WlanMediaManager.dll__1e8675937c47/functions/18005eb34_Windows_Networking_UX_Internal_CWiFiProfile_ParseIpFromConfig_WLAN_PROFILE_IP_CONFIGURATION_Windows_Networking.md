# Windows::Networking::UX::Internal::CWiFiProfile::_ParseIpFromConfig(_WLAN_PROFILE_IP_CONFIGURATION *,Windows::Networking::UX::IStaticIpConfig *)

- ea: `0x18005eb34`
- end: `0x18005efc6`
- name: `?_ParseIpFromConfig@CWiFiProfile@Internal@UX@Networking@Windows@@AEAAJPEAU_WLAN_PROFILE_IP_CONFIGURATION@@PEAUIStaticIpConfig@345@@Z`
- size: `1170`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CWiFiProfile *__hidden this, struct _WLAN_PROFILE_IP_CONFIGURATION *, struct Windows::Networking::UX::IStaticIpConfig *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18005c910`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x1800097b4`
- `0x18001668c`
- `0x18005cfec`
- `0x18005eb34`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x18005ecaa`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18005eed2`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18005ecaa`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18005eed2`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18005ebf6`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18005ee1e`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18005ebf6`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18005ee1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ecbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ee33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ee82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ec5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ecbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ee33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ee82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005eee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ec24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ecd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ee4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005eeff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ec24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ecd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ee4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005eeff`
- `wlanapi!WlanProfileIpConfigurationGetGatewayList` at `0x18005edaf`
- `wlanapi!WlanProfileIpConfigurationGetGatewayList` at `0x18005edaf`
- `wlanapi!WlanProfileIpConfigurationGetAddressList` at `0x18005eb74`
- `wlanapi!WlanProfileIpConfigurationGetAddressList` at `0x18005eb74`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall Windows::Networking::UX::Internal::CWiFiProfile::_ParseIpFromConfig(
        Windows::Networking::UX::Internal::CWiFiProfile *this,
        struct _WLAN_PROFILE_IP_CONFIGURATION *a2,
        struct Windows::Networking::UX::IStaticIpConfig *a3)
{
  unsigned int AddressList; // eax
  __int64 v6; // rdx
  unsigned int i; // edi
  __int64 v9; // rbx
  __int64 v10; // rsi
  unsigned int v11; // r12d
  LONG v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // ebx
  HRESULT v15; // eax
  __int64 v16; // rdx
  HSTRING v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned int j; // edi
  __int64 v21; // rbx
  __int64 v22; // rsi
  unsigned int v23; // r12d
  unsigned int v24; // [rsp+20h] [rbp-E0h]
  ULONG AddressStringLength; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR AddressString[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v31[28]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR sourceString[72]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v28 = 0;
  AddressList = WlanProfileIpConfigurationGetAddressList(a2, &v28);
  if ( AddressList )
  {
    v6 = 270;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
             (const char *)AddressList,
             v24);
  }
  else
  {
    for ( i = 0; i < *((_DWORD *)a2 + 1); ++i )
    {
      v9 = 136LL * i;
      v10 = v28;
      v11 = *(_DWORD *)(v9 + v28 + 128);
      if ( *(_WORD *)(v9 + v28) == 2 )
      {
        *(_OWORD *)AddressString = 0;
        memset(v31, 0, sizeof(v31));
        AddressStringLength = 22;
        v12 = RtlIpv4AddressToStringExW((const struct in_addr *)(v9 + v28 + 4), 0, AddressString, &AddressStringLength);
        if ( v12 < 0 )
        {
          v18 = 282;
          return wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)v18,
                   (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                   (const char *)(unsigned int)v12,
                   v24);
        }
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v13 = WindowsCreateString(AddressString, AddressStringLength, &string);
        v14 = v13;
        if ( v13 < 0 )
        {
          v16 = 285;
          goto LABEL_19;
        }
        v13 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, HSTRING, _QWORD))(*(_QWORD *)a3 + 104LL))(
                a3,
                string,
                v11);
        v14 = v13;
        if ( v13 < 0 )
        {
          v16 = 286;
LABEL_19:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
            (const char *)(unsigned int)v13,
            v24);
          v17 = string;
          goto LABEL_20;
        }
        WindowsDeleteString(string);
        string = 0;
      }
      else if ( *(_WORD *)(v9 + v28) == 23 )
      {
        memset_0(sourceString, 0, 0x82u);
        AddressStringLength = 65;
        v12 = RtlIpv6AddressToStringExW(
                (const struct in6_addr *)(v9 + v10 + 8),
                *(_DWORD *)(v9 + v10 + 24),
                0,
                sourceString,
                &AddressStringLength);
        if ( v12 < 0 )
        {
          v18 = 294;
          return wil::details::in1diag3::Return_NtStatus(
                   retaddr,
                   (void *)v18,
                   (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                   (const char *)(unsigned int)v12,
                   v24);
        }
        v27 = 0;
        WindowsDeleteString(0);
        v27 = 0;
        v15 = WindowsCreateString(sourceString, AddressStringLength, &v27);
        v14 = v15;
        if ( v15 < 0 )
        {
          v19 = 297;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
            (const char *)(unsigned int)v15,
            v24);
          v17 = v27;
LABEL_20:
          WindowsDeleteString(v17);
          return v14;
        }
        v15 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, HSTRING, _QWORD))(*(_QWORD *)a3 + 104LL))(
                a3,
                v27,
                v11);
        v14 = v15;
        if ( v15 < 0 )
        {
          v19 = 298;
          goto LABEL_25;
        }
        WindowsDeleteString(v27);
        v27 = 0;
      }
    }
    if ( *((_DWORD *)a2 + 3) )
    {
      v29 = 0;
      AddressList = WlanProfileIpConfigurationGetGatewayList(a2, &v29);
      if ( AddressList )
      {
        v6 = 306;
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v6,
                 (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                 (const char *)AddressList,
                 v24);
      }
      for ( j = 0; j < *((_DWORD *)a2 + 3); ++j )
      {
        v21 = 136LL * j;
        v22 = v29;
        v23 = *(_DWORD *)(v21 + v29 + 128);
        if ( *(_WORD *)(v21 + v29) == 2 )
        {
          *(_OWORD *)AddressString = 0;
          memset(v31, 0, sizeof(v31));
          AddressStringLength = 22;
          v12 = RtlIpv4AddressToStringExW(
                  (const struct in_addr *)(v21 + v29 + 4),
                  0,
                  AddressString,
                  &AddressStringLength);
          if ( v12 < 0 )
          {
            v18 = 318;
            return wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)v18,
                     (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                     (const char *)(unsigned int)v12,
                     v24);
          }
          v27 = 0;
          WindowsDeleteString(0);
          v27 = 0;
          v15 = WindowsCreateString(AddressString, AddressStringLength, &v27);
          v14 = v15;
          if ( v15 < 0 )
          {
            v19 = 321;
            goto LABEL_25;
          }
          v15 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, HSTRING, _QWORD))(*(_QWORD *)a3 + 120LL))(
                  a3,
                  v27,
                  v23);
          v14 = v15;
          if ( v15 < 0 )
          {
            v19 = 322;
            goto LABEL_25;
          }
          WindowsDeleteString(v27);
          v27 = 0;
        }
        else if ( *(_WORD *)(v21 + v29) == 23 )
        {
          memset_0(sourceString, 0, 0x82u);
          AddressStringLength = 65;
          v12 = RtlIpv6AddressToStringExW(
                  (const struct in6_addr *)(v21 + v22 + 8),
                  *(_DWORD *)(v21 + v22 + 24),
                  0,
                  sourceString,
                  &AddressStringLength);
          if ( v12 < 0 )
          {
            v18 = 330;
            return wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)v18,
                     (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprofile.cpp",
                     (const char *)(unsigned int)v12,
                     v24);
          }
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          v13 = WindowsCreateString(sourceString, AddressStringLength, &string);
          v14 = v13;
          if ( v13 < 0 )
          {
            v16 = 333;
            goto LABEL_19;
          }
          v13 = (*(__int64 (__fastcall **)(struct Windows::Networking::UX::IStaticIpConfig *, HSTRING, _QWORD))(*(_QWORD *)a3 + 120LL))(
                  a3,
                  string,
                  v23);
          v14 = v13;
          if ( v13 < 0 )
          {
            v16 = 334;
            goto LABEL_19;
          }
          WindowsDeleteString(string);
          string = 0;
        }
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18005eb34  mov     [rsp-8+arg_0], rbx
0x18005eb39  push    rbp
0x18005eb3a  push    rsi
0x18005eb3b  push    rdi
0x18005eb3c  push    r12
0x18005eb3e  push    r13
0x18005eb40  push    r14
0x18005eb42  push    r15
0x18005eb44  lea     rbp, [rsp-30h]
0x18005eb49  sub     rsp, 130h
0x18005eb50  mov     rax, cs:__security_cookie
0x18005eb57  xor     rax, rsp
0x18005eb5a  mov     [rbp+60h+var_40], rax
0x18005eb5e  mov     r15, r8
0x18005eb61  mov     r14, rdx
0x18005eb64  xor     r13d, r13d
0x18005eb67  mov     [rsp+160h+var_118], r13
0x18005eb6c  lea     rdx, [rsp+160h+var_118]
0x18005eb71  mov     rcx, r14
0x18005eb74  call    cs:__imp_WlanProfileIpConfigurationGetAddressList
0x18005eb7a  test    eax, eax
0x18005eb7c  jz      short loc_18005EB9B
0x18005eb7e  mov     edx, 10Eh; void *
0x18005eb83  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005eb8a  mov     r9d, eax; char *
0x18005eb8d  mov     rcx, [rbp+68h]; this
0x18005eb91  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005eb96  jmp     loc_18005EF9F
0x18005eb9b  mov     edi, r13d
0x18005eb9e  cmp     edi, [r14+4]
0x18005eba2  jnb     loc_18005ED98
0x18005eba8  mov     eax, edi
0x18005ebaa  imul    rbx, rax, 88h
0x18005ebb1  mov     rsi, [rsp+160h+var_118]
0x18005ebb6  mov     r12d, [rbx+rsi+80h]
0x18005ebbe  cmp     word ptr [rbx+rsi], 2
0x18005ebc3  jnz     loc_18005EC6A
0x18005ebc9  xorps   xmm0, xmm0
0x18005ebcc  movups  xmmword ptr [rsp+160h+AddressString], xmm0
0x18005ebd1  movups  xmmword ptr [rsp+160h+var_F8], xmm0
0x18005ebd6  movups  xmmword ptr [rsp+160h+var_F8+0Ch], xmm0
0x18005ebdb  mov     [rsp+160h+AddressStringLength], 16h
0x18005ebe3  xor     edx, edx; Port
0x18005ebe5  lea     rcx, [rsi+4]
0x18005ebe9  add     rcx, rbx; Address
0x18005ebec  lea     r9, [rsp+160h+AddressStringLength]; AddressStringLength
0x18005ebf1  lea     r8, [rsp+160h+AddressString]; AddressString
0x18005ebf6  call    cs:__imp_RtlIpv4AddressToStringExW
0x18005ebfc  test    eax, eax
0x18005ebfe  js      loc_18005ED4D
0x18005ec04  mov     [rsp+160h+string], r13
0x18005ec09  xor     ecx, ecx; string
0x18005ec0b  call    cs:__imp_WindowsDeleteString
0x18005ec11  mov     [rsp+160h+string], r13
0x18005ec16  lea     r8, [rsp+160h+string]; string
0x18005ec1b  mov     edx, [rsp+160h+AddressStringLength]; length
0x18005ec1f  lea     rcx, [rsp+160h+AddressString]; sourceString
0x18005ec24  call    cs:__imp_WindowsCreateString
0x18005ec2a  mov     ebx, eax
0x18005ec2c  test    eax, eax
0x18005ec2e  js      loc_18005ED22
0x18005ec34  mov     rax, [r15]
0x18005ec37  mov     r8d, r12d
0x18005ec3a  mov     rdx, [rsp+160h+string]
0x18005ec3f  mov     rcx, r15
0x18005ec42  mov     rax, [rax+68h]
0x18005ec46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ec4b  mov     ebx, eax
0x18005ec4d  test    eax, eax
0x18005ec4f  js      loc_18005ED1B
0x18005ec55  mov     rcx, [rsp+160h+string]; string
0x18005ec5a  call    cs:__imp_WindowsDeleteString
0x18005ec60  mov     [rsp+160h+string], r13
0x18005ec65  jmp     loc_18005ED14
0x18005ec6a  cmp     word ptr [rbx+rsi], 17h
0x18005ec6f  jnz     loc_18005ED14
0x18005ec75  xor     edx, edx; Val
0x18005ec77  mov     r8d, 82h; Size
0x18005ec7d  lea     rcx, [rbp+60h+sourceString]; void *
0x18005ec81  call    memset_0
0x18005ec86  mov     [rsp+160h+AddressStringLength], 41h ; 'A'
0x18005ec8e  xor     r8d, r8d; Port
0x18005ec91  lea     rcx, [rsi+8]
0x18005ec95  add     rcx, rbx; Address
0x18005ec98  lea     rax, [rsp+160h+AddressStringLength]
0x18005ec9d  mov     qword ptr [rsp+160h+var_140], rax; int
0x18005eca2  lea     r9, [rbp+60h+sourceString]; AddressString
0x18005eca6  mov     edx, [rbx+rsi+18h]; ScopeId
0x18005ecaa  call    cs:__imp_RtlIpv6AddressToStringExW
0x18005ecb0  test    eax, eax
0x18005ecb2  js      loc_18005ED91
0x18005ecb8  mov     [rsp+160h+var_120], r13
0x18005ecbd  xor     ecx, ecx; string
0x18005ecbf  call    cs:__imp_WindowsDeleteString
0x18005ecc5  mov     [rsp+160h+var_120], r13
0x18005ecca  lea     r8, [rsp+160h+var_120]; string
0x18005eccf  mov     edx, [rsp+160h+AddressStringLength]; length
0x18005ecd3  lea     rcx, [rbp+60h+sourceString]; sourceString
0x18005ecd7  call    cs:__imp_WindowsCreateString
0x18005ecdd  mov     ebx, eax
0x18005ecdf  test    eax, eax
0x18005ece1  js      loc_18005ED71
0x18005ece7  mov     rax, [r15]
0x18005ecea  mov     r8d, r12d
0x18005eced  mov     rdx, [rsp+160h+var_120]
0x18005ecf2  mov     rcx, r15
0x18005ecf5  mov     rax, [rax+68h]
0x18005ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecfe  mov     ebx, eax
0x18005ed00  test    eax, eax
0x18005ed02  js      short loc_18005ED6A
0x18005ed04  mov     rcx, [rsp+160h+var_120]; string
0x18005ed09  call    cs:__imp_WindowsDeleteString
0x18005ed0f  mov     [rsp+160h+var_120], r13
0x18005ed14  inc     edi
0x18005ed16  jmp     loc_18005EB9E
0x18005ed1b  mov     edx, 11Eh
0x18005ed20  jmp     short loc_18005ED27
0x18005ed22  mov     edx, 11Dh; void *
0x18005ed27  mov     r9d, eax; char *
0x18005ed2a  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005ed31  mov     rcx, [rbp+68h]; this
0x18005ed35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ed3a  nop
0x18005ed3b  mov     rcx, [rsp+160h+string]; string
0x18005ed40  call    cs:__imp_WindowsDeleteString
0x18005ed46  mov     eax, ebx
0x18005ed48  jmp     loc_18005EF9F
0x18005ed4d  mov     edx, 11Ah; void *
0x18005ed52  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005ed59  mov     r9d, eax; char *
0x18005ed5c  mov     rcx, [rbp+68h]; this
0x18005ed60  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005ed65  jmp     loc_18005EF9F
0x18005ed6a  mov     edx, 12Ah
0x18005ed6f  jmp     short loc_18005ED76
0x18005ed71  mov     edx, 129h; void *
0x18005ed76  mov     r9d, eax; char *
0x18005ed79  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005ed80  mov     rcx, [rbp+68h]; this
0x18005ed84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ed89  nop
0x18005ed8a  mov     rcx, [rsp+160h+var_120]
0x18005ed8f  jmp     short loc_18005ED40
0x18005ed91  mov     edx, 126h
0x18005ed96  jmp     short loc_18005ED52
0x18005ed98  cmp     [r14+0Ch], r13d
0x18005ed9c  jbe     loc_18005EF9D
0x18005eda2  mov     [rsp+160h+var_110], r13
0x18005eda7  lea     rdx, [rsp+160h+var_110]
0x18005edac  mov     rcx, r14
0x18005edaf  call    cs:__imp_WlanProfileIpConfigurationGetGatewayList
0x18005edb5  test    eax, eax
0x18005edb7  jz      short loc_18005EDC3
0x18005edb9  mov     edx, 132h
0x18005edbe  jmp     loc_18005EB83
0x18005edc3  mov     edi, r13d
0x18005edc6  cmp     edi, [r14+0Ch]
0x18005edca  jnb     loc_18005EF9D
0x18005edd0  mov     eax, edi
0x18005edd2  imul    rbx, rax, 88h
0x18005edd9  mov     rsi, [rsp+160h+var_110]
0x18005edde  mov     r12d, [rbx+rsi+80h]
0x18005ede6  cmp     word ptr [rbx+rsi], 2
0x18005edeb  jnz     loc_18005EE92
0x18005edf1  xorps   xmm0, xmm0
0x18005edf4  movups  xmmword ptr [rsp+160h+AddressString], xmm0
0x18005edf9  movups  xmmword ptr [rsp+160h+var_F8], xmm0
0x18005edfe  movups  xmmword ptr [rsp+160h+var_F8+0Ch], xmm0
0x18005ee03  mov     [rsp+160h+AddressStringLength], 16h
0x18005ee0b  xor     edx, edx; Port
0x18005ee0d  lea     rcx, [rsi+4]
0x18005ee11  add     rcx, rbx; Address
0x18005ee14  lea     r9, [rsp+160h+AddressStringLength]; AddressStringLength
0x18005ee19  lea     r8, [rsp+160h+AddressString]; AddressString
0x18005ee1e  call    cs:__imp_RtlIpv4AddressToStringExW
0x18005ee24  test    eax, eax
0x18005ee26  js      loc_18005EF64
0x18005ee2c  mov     [rsp+160h+var_120], r13
0x18005ee31  xor     ecx, ecx; string
0x18005ee33  call    cs:__imp_WindowsDeleteString
0x18005ee39  mov     [rsp+160h+var_120], r13
0x18005ee3e  lea     r8, [rsp+160h+var_120]; string
0x18005ee43  mov     edx, [rsp+160h+AddressStringLength]; length
0x18005ee47  lea     rcx, [rsp+160h+AddressString]; sourceString
0x18005ee4c  call    cs:__imp_WindowsCreateString
0x18005ee52  mov     ebx, eax
0x18005ee54  test    eax, eax
0x18005ee56  js      loc_18005EF46
0x18005ee5c  mov     rax, [r15]
0x18005ee5f  mov     r8d, r12d
0x18005ee62  mov     rdx, [rsp+160h+var_120]
0x18005ee67  mov     rcx, r15
0x18005ee6a  mov     rax, [rax+78h]
0x18005ee6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee73  mov     ebx, eax
0x18005ee75  test    eax, eax
0x18005ee77  js      loc_18005EF3F
0x18005ee7d  mov     rcx, [rsp+160h+var_120]; string
0x18005ee82  call    cs:__imp_WindowsDeleteString
0x18005ee88  mov     [rsp+160h+var_120], r13
0x18005ee8d  jmp     loc_18005EF38
0x18005ee92  cmp     word ptr [rbx+rsi], 17h
0x18005ee97  jnz     loc_18005EF38
0x18005ee9d  xor     edx, edx; Val
0x18005ee9f  mov     r8d, 82h; Size
0x18005eea5  lea     rcx, [rbp+60h+sourceString]; void *
0x18005eea9  call    memset_0
0x18005eeae  mov     [rsp+160h+AddressStringLength], 41h ; 'A'
0x18005eeb6  xor     r8d, r8d; Port
0x18005eeb9  lea     rcx, [rsi+8]
0x18005eebd  add     rcx, rbx; Address
0x18005eec0  lea     rax, [rsp+160h+AddressStringLength]
0x18005eec5  mov     qword ptr [rsp+160h+var_140], rax; int
0x18005eeca  lea     r9, [rbp+60h+sourceString]; AddressString
0x18005eece  mov     edx, [rbx+rsi+18h]; ScopeId
0x18005eed2  call    cs:__imp_RtlIpv6AddressToStringExW
0x18005eed8  test    eax, eax
0x18005eeda  js      loc_18005EF93
0x18005eee0  mov     [rsp+160h+string], r13
0x18005eee5  xor     ecx, ecx; string
0x18005eee7  call    cs:__imp_WindowsDeleteString
0x18005eeed  mov     [rsp+160h+string], r13
0x18005eef2  lea     r8, [rsp+160h+string]; string
0x18005eef7  mov     edx, [rsp+160h+AddressStringLength]; length
0x18005eefb  lea     rcx, [rbp+60h+sourceString]; sourceString
0x18005eeff  call    cs:__imp_WindowsCreateString
0x18005ef05  mov     ebx, eax
0x18005ef07  test    eax, eax
0x18005ef09  js      short loc_18005EF75
0x18005ef0b  mov     rax, [r15]
0x18005ef0e  mov     r8d, r12d
0x18005ef11  mov     rdx, [rsp+160h+string]
0x18005ef16  mov     rcx, r15
0x18005ef19  mov     rax, [rax+78h]
0x18005ef1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef22  mov     ebx, eax
0x18005ef24  test    eax, eax
0x18005ef26  js      short loc_18005EF6E
0x18005ef28  mov     rcx, [rsp+160h+string]; string
0x18005ef2d  call    cs:__imp_WindowsDeleteString
0x18005ef33  mov     [rsp+160h+string], r13
0x18005ef38  inc     edi
0x18005ef3a  jmp     loc_18005EDC6
0x18005ef3f  mov     edx, 142h
0x18005ef44  jmp     short loc_18005EF4B
0x18005ef46  mov     edx, 141h; void *
0x18005ef4b  mov     r9d, eax; char *
0x18005ef4e  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005ef55  mov     rcx, [rbp+68h]; this
0x18005ef59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ef5e  nop
0x18005ef5f  jmp     loc_18005ED8A
0x18005ef64  mov     edx, 13Eh
0x18005ef69  jmp     loc_18005ED52
0x18005ef6e  mov     edx, 14Eh
0x18005ef73  jmp     short loc_18005EF7A
0x18005ef75  mov     edx, 14Dh; void *
0x18005ef7a  mov     r9d, eax; char *
0x18005ef7d  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005ef84  mov     rcx, [rbp+68h]; this
0x18005ef88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ef8d  nop
0x18005ef8e  jmp     loc_18005ED3B
0x18005ef93  mov     edx, 14Ah
0x18005ef98  jmp     loc_18005ED52
0x18005ef9d  xor     eax, eax
0x18005ef9f  mov     rcx, [rbp+60h+var_40]
0x18005efa3  xor     rcx, rsp; StackCookie
0x18005efa6  call    __security_check_cookie
0x18005efab  mov     rbx, [rsp+160h+arg_0]
0x18005efb3  add     rsp, 130h
0x18005efba  pop     r15
0x18005efbc  pop     r14
0x18005efbe  pop     r13
0x18005efc0  pop     r12
0x18005efc2  pop     rdi
0x18005efc3  pop     rsi
0x18005efc4  pop     rbp
0x18005efc5  retn
```
