# Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(_IP_ADAPTER_GATEWAY_ADDRESS_LH *)

- ea: `0x18008168c`
- end: `0x180081863`
- name: `?AddGateway@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_GATEWAY_ADDRESS_LH@@@Z`
- size: `471`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180082b60`

## callees

- `0x180003ed0`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18001d6d0`
- `0x18008168c`
- `0x1800858a8`
- `0x1800858ec`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x1800817cc`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800817cc`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180081730`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180081730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008177c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008177c`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(
        Windows::Networking::UX::Internal::CAdapterProperties *this,
        struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *a2)
{
  PVOID *v4; // r10
  LPSOCKADDR lpSockaddr; // r11
  bool v6; // zf
  const struct in_addr *v7; // rcx
  int v8; // eax
  const IN6_ADDR *v9; // rcx
  const struct in6_addr *v10; // rcx
  __int64 v11; // r11
  int v12; // eax
  ULONG AddressStringLength[4]; // [rsp+30h] [rbp-B8h] BYREF
  WCHAR AddressString[72]; // [rsp+40h] [rbp-A8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  lpSockaddr = a2->Address.lpSockaddr;
  if ( !lpSockaddr )
    goto LABEL_25;
  AddressStringLength[0] = 65;
  v6 = lpSockaddr->sa_family == 2;
  AddressString[0] = 0;
  if ( !v6 )
  {
    if ( lpSockaddr->sa_family != 23
      || IN6_IS_ADDR_LOOPBACK((const IN6_ADDR *)&lpSockaddr->sa_data[6])
      || IN6_IS_ADDR_UNSPECIFIED(v9)
      || v10->u.Byte[0] == 0xFE && (v10->u.Byte[1] & 0xC0) == 0xC0 )
    {
      goto LABEL_25;
    }
    if ( !RtlIpv6AddressToStringExW(v10, *(_DWORD *)(v11 + 24), 0, AddressString, AddressStringLength) )
    {
      v12 = Microsoft::WRL::Wrappers::HString::Set<65>((char *)this + 128, AddressString);
      if ( v12 < 0 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_25;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_07bd92578572370284dbe53730fdfa75_Traceguids,
          (unsigned int)v12);
      }
    }
LABEL_24:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v7 = (const struct in_addr *)&lpSockaddr->sa_data[2];
  if ( lpSockaddr->sa_data[2] != 127 && v7->S_un.S_addr )
  {
    if ( !RtlIpv4AddressToStringExW(v7, 0, AddressString, AddressStringLength) )
    {
      v8 = Microsoft::WRL::Wrappers::HString::Set<65>((char *)this + 120, AddressString);
      if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_07bd92578572370284dbe53730fdfa75_Traceguids,
          (unsigned int)v8);
      WindowsDeleteString(0);
    }
    goto LABEL_24;
  }
LABEL_25:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
    WPP_SF_(v4[2], 32, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
}

```

## disassembly

```asm
0x18008168c  mov     [rsp+arg_10], rbx
0x180081691  mov     [rsp+arg_18], rsi
0x180081696  push    rdi
0x180081697  sub     rsp, 0E0h
0x18008169e  mov     rax, cs:__security_cookie
0x1800816a5  xor     rax, rsp
0x1800816a8  mov     [rsp+0E8h+var_18], rax
0x1800816b0  mov     rbx, rdx
0x1800816b3  mov     rdi, rcx
0x1800816b6  mov     r10, cs:WPP_GLOBAL_Control
0x1800816bd  lea     rsi, WPP_GLOBAL_Control
0x1800816c4  cmp     r10, rsi
0x1800816c7  jz      short loc_1800816EC
0x1800816c9  test    byte ptr [r10+1Ch], 40h
0x1800816ce  jz      short loc_1800816EC
0x1800816d0  mov     rcx, [r10+10h]
0x1800816d4  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800816db  mov     edx, 1Dh
0x1800816e0  call    WPP_SF_
0x1800816e5  mov     r10, cs:WPP_GLOBAL_Control
0x1800816ec  mov     r11, [rbx+10h]
0x1800816f0  test    r11, r11
0x1800816f3  jz      loc_18008181D
0x1800816f9  xor     eax, eax
0x1800816fb  mov     [rsp+0E8h+AddressStringLength], 41h ; 'A'
0x180081703  cmp     word ptr [r11], 2
0x180081708  mov     [rsp+0E8h+AddressString], ax
0x18008170d  jnz     short loc_180081787
0x18008170f  lea     rcx, [r11+4]; Address
0x180081713  cmp     byte ptr [rcx], 7Fh
0x180081716  jz      loc_18008181D
0x18008171c  cmp     [rcx], eax
0x18008171e  jz      loc_18008181D
0x180081724  xor     edx, edx; Port
0x180081726  lea     r9, [rsp+0E8h+AddressStringLength]; AddressStringLength
0x18008172b  lea     r8, [rsp+0E8h+AddressString]; AddressString
0x180081730  call    cs:__imp_RtlIpv4AddressToStringExW
0x180081736  test    eax, eax
0x180081738  jnz     loc_180081816
0x18008173e  lea     rcx, [rdi+78h]
0x180081742  lea     rdx, [rsp+0E8h+AddressString]
0x180081747  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x18008174c  test    eax, eax
0x18008174e  jns     short loc_18008177A
0x180081750  mov     rcx, cs:WPP_GLOBAL_Control
0x180081757  cmp     rcx, rsi
0x18008175a  jz      short loc_18008177A
0x18008175c  test    byte ptr [rcx+1Ch], 2
0x180081760  jz      short loc_18008177A
0x180081762  mov     rcx, [rcx+10h]
0x180081766  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18008176d  mov     edx, 1Eh
0x180081772  mov     r9d, eax
0x180081775  call    WPP_SF_d
0x18008177a  xor     ecx, ecx; string
0x18008177c  call    cs:__imp_WindowsDeleteString
0x180081782  jmp     loc_180081816
0x180081787  cmp     word ptr [r11], 17h
0x18008178c  jnz     loc_18008181D
0x180081792  lea     rcx, [r11+8]; a
0x180081796  call    IN6_IS_ADDR_LOOPBACK
0x18008179b  test    al, al
0x18008179d  jnz     short loc_18008181D
0x18008179f  call    IN6_IS_ADDR_UNSPECIFIED
0x1800817a4  test    al, al
0x1800817a6  jnz     short loc_18008181D
0x1800817a8  cmp     byte ptr [rcx], 0FEh
0x1800817ab  jnz     short loc_1800817B6
0x1800817ad  mov     al, [rcx+1]
0x1800817b0  and     al, 0C0h
0x1800817b2  cmp     al, 0C0h
0x1800817b4  jz      short loc_18008181D
0x1800817b6  mov     edx, [r11+18h]; ScopeId
0x1800817ba  lea     rax, [rsp+0E8h+AddressStringLength]
0x1800817bf  xor     r8d, r8d; Port
0x1800817c2  mov     [rsp+0E8h+var_C8], rax; AddressStringLength
0x1800817c7  lea     r9, [rsp+0E8h+AddressString]; AddressString
0x1800817cc  call    cs:__imp_RtlIpv6AddressToStringExW
0x1800817d2  test    eax, eax
0x1800817d4  jnz     short loc_180081816
0x1800817d6  lea     rcx, [rdi+80h]
0x1800817dd  lea     rdx, [rsp+0E8h+AddressString]
0x1800817e2  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800817e7  test    eax, eax
0x1800817e9  jns     short loc_180081816
0x1800817eb  mov     r10, cs:WPP_GLOBAL_Control
0x1800817f2  cmp     r10, rsi
0x1800817f5  jz      short loc_18008183E
0x1800817f7  test    byte ptr [r10+1Ch], 2
0x1800817fc  jz      short loc_18008181D
0x1800817fe  mov     rcx, [r10+10h]
0x180081802  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180081809  mov     edx, 1Fh
0x18008180e  mov     r9d, eax
0x180081811  call    WPP_SF_d
0x180081816  mov     r10, cs:WPP_GLOBAL_Control
0x18008181d  cmp     r10, rsi
0x180081820  jz      short loc_18008183E
0x180081822  test    byte ptr [r10+1Ch], 40h
0x180081827  jz      short loc_18008183E
0x180081829  mov     rcx, [r10+10h]
0x18008182d  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180081834  mov     edx, 20h ; ' '
0x180081839  call    WPP_SF_
0x18008183e  mov     rcx, [rsp+0E8h+var_18]
0x180081846  xor     rcx, rsp; StackCookie
0x180081849  call    __security_check_cookie
0x18008184e  lea     r11, [rsp+0E8h+var_8]
0x180081856  mov     rbx, [r11+20h]
0x18008185a  mov     rsi, [r11+28h]
0x18008185e  mov     rsp, r11
0x180081861  pop     rdi
0x180081862  retn
```
