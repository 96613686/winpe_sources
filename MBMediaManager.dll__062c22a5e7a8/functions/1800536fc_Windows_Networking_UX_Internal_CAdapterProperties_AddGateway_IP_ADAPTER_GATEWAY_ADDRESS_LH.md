# Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(_IP_ADAPTER_GATEWAY_ADDRESS_LH *)

- ea: `0x1800536fc`
- end: `0x1800538d3`
- name: `?AddGateway@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_GATEWAY_ADDRESS_LH@@@Z`
- size: `471`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003108`

## callees

- `0x180004880`
- `0x180005be0`
- `0x180005c80`
- `0x180005d10`
- `0x18002673c`
- `0x18002cd20`
- `0x1800536fc`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x18005383c`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18005383c`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800537a0`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800537a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800537ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800537ec`

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
0x1800536fc  mov     [rsp+arg_10], rbx
0x180053701  mov     [rsp+arg_18], rsi
0x180053706  push    rdi
0x180053707  sub     rsp, 0E0h
0x18005370e  mov     rax, cs:__security_cookie
0x180053715  xor     rax, rsp
0x180053718  mov     [rsp+0E8h+var_18], rax
0x180053720  mov     rbx, rdx
0x180053723  mov     rdi, rcx
0x180053726  mov     r10, cs:WPP_GLOBAL_Control
0x18005372d  lea     rsi, WPP_GLOBAL_Control
0x180053734  cmp     r10, rsi
0x180053737  jz      short loc_18005375C
0x180053739  test    byte ptr [r10+1Ch], 40h
0x18005373e  jz      short loc_18005375C
0x180053740  mov     rcx, [r10+10h]
0x180053744  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18005374b  mov     edx, 1Dh
0x180053750  call    WPP_SF_
0x180053755  mov     r10, cs:WPP_GLOBAL_Control
0x18005375c  mov     r11, [rbx+10h]
0x180053760  test    r11, r11
0x180053763  jz      loc_18005388D
0x180053769  xor     eax, eax
0x18005376b  mov     [rsp+0E8h+AddressStringLength], 41h ; 'A'
0x180053773  cmp     word ptr [r11], 2
0x180053778  mov     [rsp+0E8h+AddressString], ax
0x18005377d  jnz     short loc_1800537F7
0x18005377f  lea     rcx, [r11+4]; Address
0x180053783  cmp     byte ptr [rcx], 7Fh
0x180053786  jz      loc_18005388D
0x18005378c  cmp     [rcx], eax
0x18005378e  jz      loc_18005388D
0x180053794  xor     edx, edx; Port
0x180053796  lea     r9, [rsp+0E8h+AddressStringLength]; AddressStringLength
0x18005379b  lea     r8, [rsp+0E8h+AddressString]; AddressString
0x1800537a0  call    cs:__imp_RtlIpv4AddressToStringExW
0x1800537a6  test    eax, eax
0x1800537a8  jnz     loc_180053886
0x1800537ae  lea     rcx, [rdi+78h]
0x1800537b2  lea     rdx, [rsp+0E8h+AddressString]
0x1800537b7  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800537bc  test    eax, eax
0x1800537be  jns     short loc_1800537EA
0x1800537c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800537c7  cmp     rcx, rsi
0x1800537ca  jz      short loc_1800537EA
0x1800537cc  test    byte ptr [rcx+1Ch], 2
0x1800537d0  jz      short loc_1800537EA
0x1800537d2  mov     rcx, [rcx+10h]
0x1800537d6  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800537dd  mov     edx, 1Eh
0x1800537e2  mov     r9d, eax
0x1800537e5  call    WPP_SF_d
0x1800537ea  xor     ecx, ecx; string
0x1800537ec  call    cs:__imp_WindowsDeleteString
0x1800537f2  jmp     loc_180053886
0x1800537f7  cmp     word ptr [r11], 17h
0x1800537fc  jnz     loc_18005388D
0x180053802  lea     rcx, [r11+8]; a
0x180053806  call    IN6_IS_ADDR_LOOPBACK
0x18005380b  test    al, al
0x18005380d  jnz     short loc_18005388D
0x18005380f  call    IN6_IS_ADDR_UNSPECIFIED
0x180053814  test    al, al
0x180053816  jnz     short loc_18005388D
0x180053818  cmp     byte ptr [rcx], 0FEh
0x18005381b  jnz     short loc_180053826
0x18005381d  mov     al, [rcx+1]
0x180053820  and     al, 0C0h
0x180053822  cmp     al, 0C0h
0x180053824  jz      short loc_18005388D
0x180053826  mov     edx, [r11+18h]; ScopeId
0x18005382a  lea     rax, [rsp+0E8h+AddressStringLength]
0x18005382f  xor     r8d, r8d; Port
0x180053832  mov     [rsp+0E8h+var_C8], rax; AddressStringLength
0x180053837  lea     r9, [rsp+0E8h+AddressString]; AddressString
0x18005383c  call    cs:__imp_RtlIpv6AddressToStringExW
0x180053842  test    eax, eax
0x180053844  jnz     short loc_180053886
0x180053846  lea     rcx, [rdi+80h]
0x18005384d  lea     rdx, [rsp+0E8h+AddressString]
0x180053852  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180053857  test    eax, eax
0x180053859  jns     short loc_180053886
0x18005385b  mov     r10, cs:WPP_GLOBAL_Control
0x180053862  cmp     r10, rsi
0x180053865  jz      short loc_1800538AE
0x180053867  test    byte ptr [r10+1Ch], 2
0x18005386c  jz      short loc_18005388D
0x18005386e  mov     rcx, [r10+10h]
0x180053872  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180053879  mov     edx, 1Fh
0x18005387e  mov     r9d, eax
0x180053881  call    WPP_SF_d
0x180053886  mov     r10, cs:WPP_GLOBAL_Control
0x18005388d  cmp     r10, rsi
0x180053890  jz      short loc_1800538AE
0x180053892  test    byte ptr [r10+1Ch], 40h
0x180053897  jz      short loc_1800538AE
0x180053899  mov     rcx, [r10+10h]
0x18005389d  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800538a4  mov     edx, 20h ; ' '
0x1800538a9  call    WPP_SF_
0x1800538ae  mov     rcx, [rsp+0E8h+var_18]
0x1800538b6  xor     rcx, rsp; StackCookie
0x1800538b9  call    __security_check_cookie
0x1800538be  lea     r11, [rsp+0E8h+var_8]
0x1800538c6  mov     rbx, [r11+20h]
0x1800538ca  mov     rsi, [r11+28h]
0x1800538ce  mov     rsp, r11
0x1800538d1  pop     rdi
0x1800538d2  retn
```
