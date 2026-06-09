# Windows::Networking::UX::Internal::CAdapterProperties::AddGateway(_IP_ADAPTER_GATEWAY_ADDRESS_LH *)

- ea: `0x1800410ec`
- end: `0x1800412c3`
- name: `?AddGateway@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_GATEWAY_ADDRESS_LH@@@Z`
- size: `471`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_GATEWAY_ADDRESS_LH *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041e58`

## callees

- `0x180002520`
- `0x18000a6e4`
- `0x180037c4c`
- `0x180040dbc`
- `0x1800410ec`
- `0x18004409c`
- `0x1800440e0`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringExW` at `0x180041190`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180041190`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18004122c`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18004122c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800411dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800411dc`

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
      v12 = Microsoft::WRL::Wrappers::HString::Set<65>(
              (Windows::Networking::UX::Internal::CAdapterProperties *)((char *)this + 128),
              AddressString);
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
      v8 = Microsoft::WRL::Wrappers::HString::Set<65>(
             (Windows::Networking::UX::Internal::CAdapterProperties *)((char *)this + 120),
             AddressString);
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
0x1800410ec  mov     [rsp+arg_10], rbx
0x1800410f1  mov     [rsp+arg_18], rsi
0x1800410f6  push    rdi
0x1800410f7  sub     rsp, 0E0h
0x1800410fe  mov     rax, cs:__security_cookie
0x180041105  xor     rax, rsp
0x180041108  mov     [rsp+0E8h+var_18], rax
0x180041110  mov     rbx, rdx
0x180041113  mov     rdi, rcx
0x180041116  mov     r10, cs:WPP_GLOBAL_Control
0x18004111d  lea     rsi, WPP_GLOBAL_Control
0x180041124  cmp     r10, rsi
0x180041127  jz      short loc_18004114C
0x180041129  test    byte ptr [r10+1Ch], 40h
0x18004112e  jz      short loc_18004114C
0x180041130  mov     rcx, [r10+10h]
0x180041134  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18004113b  mov     edx, 1Dh
0x180041140  call    WPP_SF_
0x180041145  mov     r10, cs:WPP_GLOBAL_Control
0x18004114c  mov     r11, [rbx+10h]
0x180041150  test    r11, r11
0x180041153  jz      loc_18004127D
0x180041159  xor     eax, eax
0x18004115b  mov     [rsp+0E8h+AddressStringLength], 41h ; 'A'
0x180041163  cmp     word ptr [r11], 2
0x180041168  mov     [rsp+0E8h+AddressString], ax
0x18004116d  jnz     short loc_1800411E7
0x18004116f  lea     rcx, [r11+4]; Address
0x180041173  cmp     byte ptr [rcx], 7Fh
0x180041176  jz      loc_18004127D
0x18004117c  cmp     [rcx], eax
0x18004117e  jz      loc_18004127D
0x180041184  xor     edx, edx; Port
0x180041186  lea     r9, [rsp+0E8h+AddressStringLength]; AddressStringLength
0x18004118b  lea     r8, [rsp+0E8h+AddressString]; AddressString
0x180041190  call    cs:__imp_RtlIpv4AddressToStringExW
0x180041196  test    eax, eax
0x180041198  jnz     loc_180041276
0x18004119e  lea     rcx, [rdi+78h]; this
0x1800411a2  lea     rdx, [rsp+0E8h+AddressString]; unsigned __int16 *
0x1800411a7  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800411ac  test    eax, eax
0x1800411ae  jns     short loc_1800411DA
0x1800411b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800411b7  cmp     rcx, rsi
0x1800411ba  jz      short loc_1800411DA
0x1800411bc  test    byte ptr [rcx+1Ch], 2
0x1800411c0  jz      short loc_1800411DA
0x1800411c2  mov     rcx, [rcx+10h]
0x1800411c6  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800411cd  mov     edx, 1Eh
0x1800411d2  mov     r9d, eax
0x1800411d5  call    WPP_SF_d
0x1800411da  xor     ecx, ecx; string
0x1800411dc  call    cs:__imp_WindowsDeleteString
0x1800411e2  jmp     loc_180041276
0x1800411e7  cmp     word ptr [r11], 17h
0x1800411ec  jnz     loc_18004127D
0x1800411f2  lea     rcx, [r11+8]; a
0x1800411f6  call    IN6_IS_ADDR_LOOPBACK
0x1800411fb  test    al, al
0x1800411fd  jnz     short loc_18004127D
0x1800411ff  call    IN6_IS_ADDR_UNSPECIFIED
0x180041204  test    al, al
0x180041206  jnz     short loc_18004127D
0x180041208  cmp     byte ptr [rcx], 0FEh
0x18004120b  jnz     short loc_180041216
0x18004120d  mov     al, [rcx+1]
0x180041210  and     al, 0C0h
0x180041212  cmp     al, 0C0h
0x180041214  jz      short loc_18004127D
0x180041216  mov     edx, [r11+18h]; ScopeId
0x18004121a  lea     rax, [rsp+0E8h+AddressStringLength]
0x18004121f  xor     r8d, r8d; Port
0x180041222  mov     [rsp+0E8h+var_C8], rax; AddressStringLength
0x180041227  lea     r9, [rsp+0E8h+AddressString]; AddressString
0x18004122c  call    cs:__imp_RtlIpv6AddressToStringExW
0x180041232  test    eax, eax
0x180041234  jnz     short loc_180041276
0x180041236  lea     rcx, [rdi+80h]; this
0x18004123d  lea     rdx, [rsp+0E8h+AddressString]; unsigned __int16 *
0x180041242  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180041247  test    eax, eax
0x180041249  jns     short loc_180041276
0x18004124b  mov     r10, cs:WPP_GLOBAL_Control
0x180041252  cmp     r10, rsi
0x180041255  jz      short loc_18004129E
0x180041257  test    byte ptr [r10+1Ch], 2
0x18004125c  jz      short loc_18004127D
0x18004125e  mov     rcx, [r10+10h]
0x180041262  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180041269  mov     edx, 1Fh
0x18004126e  mov     r9d, eax
0x180041271  call    WPP_SF_d
0x180041276  mov     r10, cs:WPP_GLOBAL_Control
0x18004127d  cmp     r10, rsi
0x180041280  jz      short loc_18004129E
0x180041282  test    byte ptr [r10+1Ch], 40h
0x180041287  jz      short loc_18004129E
0x180041289  mov     rcx, [r10+10h]
0x18004128d  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180041294  mov     edx, 20h ; ' '
0x180041299  call    WPP_SF_
0x18004129e  mov     rcx, [rsp+0E8h+var_18]
0x1800412a6  xor     rcx, rsp; StackCookie
0x1800412a9  call    __security_check_cookie
0x1800412ae  lea     r11, [rsp+0E8h+var_8]
0x1800412b6  mov     rbx, [r11+20h]
0x1800412ba  mov     rsi, [r11+28h]
0x1800412be  mov     rsp, r11
0x1800412c1  pop     rdi
0x1800412c2  retn
```
