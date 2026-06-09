# Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(sockaddr *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)

- ea: `0x180084ea8`
- end: `0x180085112`
- name: `?TryAddDnsAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAUsockaddr@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@1@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180082b60`

## callees

- `0x180003ed0`
- `0x18000de4c`
- `0x18001d6d0`
- `0x180081e5c`
- `0x180083af4`
- `0x180084ea8`
- `0x180085118`
- `0x1800858a8`
- `0x1800858ec`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x180085026`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180085026`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180084f4b`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180084f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800850c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800850c2`

## pseudocode

```c
char __fastcall Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  PVOID *v8; // r9
  LONG v9; // eax
  const struct in_addr *v10; // rcx
  __int64 v11; // rcx
  __int64 DnsServer; // rax
  __int64 v13; // r9
  __int128 v14; // xmm1
  __int64 v15; // xmm0_8
  HSTRING *v16; // rcx
  const IN6_ADDR *v17; // rcx
  const struct in6_addr *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r9
  __int128 v22; // xmm1
  __int64 v23; // xmm0_8
  HSTRING string; // [rsp+30h] [rbp-148h] BYREF
  ULONG AddressStringLength; // [rsp+38h] [rbp-140h] BYREF
  _QWORD v27[2]; // [rsp+40h] [rbp-138h] BYREF
  __int128 v28; // [rsp+50h] [rbp-128h] BYREF
  __int64 v29; // [rsp+60h] [rbp-118h]
  __int128 v30; // [rsp+70h] [rbp-108h] BYREF
  __int64 v31; // [rsp+80h] [rbp-F8h]
  _BYTE v32[32]; // [rsp+90h] [rbp-E8h] BYREF
  WCHAR AddressString[72]; // [rsp+B0h] [rbp-C8h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  LOBYTE(v9) = 0;
  AddressString[0] = 0;
  AddressStringLength = 65;
  if ( *(_WORD *)a2 == 2 )
  {
    v10 = (const struct in_addr *)(a2 + 4);
    if ( *(_BYTE *)(a2 + 4) != 127 && v10->S_un.S_addr )
    {
      v9 = RtlIpv4AddressToStringExW(v10, 0, AddressString, &AddressStringLength);
      if ( !v9 )
      {
        string = 0;
        if ( (int)Microsoft::WRL::Wrappers::HString::Set<65>(&string, AddressString) >= 0 )
        {
          v27[0] = string;
          DnsServer = Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(v11, v32, v27, a3);
          v14 = *(_OWORD *)DnsServer;
          v30 = *(_OWORD *)DnsServer;
          v15 = *(_QWORD *)(DnsServer + 16);
          v31 = v15;
          if ( *(_QWORD *)(DnsServer + 8) )
          {
            v28 = v14;
            v29 = v15;
            LOBYTE(v13) = 1;
            Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
              *(_QWORD *)(a1 + 136),
              0,
              &v28,
              v13);
          }
          v16 = (HSTRING *)&v30;
LABEL_20:
          FreeDnsServer(v16);
          goto LABEL_21;
        }
        goto LABEL_21;
      }
      goto LABEL_22;
    }
  }
  else if ( *(_WORD *)a2 == 23 )
  {
    LOBYTE(v9) = IN6_IS_ADDR_LOOPBACK((const IN6_ADDR *)(a2 + 8));
    if ( !(_BYTE)v9 )
    {
      LOBYTE(v9) = IN6_IS_ADDR_UNSPECIFIED(v17);
      if ( !(_BYTE)v9 )
      {
        v9 = RtlIpv6AddressToStringExW(v18, *(_DWORD *)(a2 + 24), 0, AddressString, &AddressStringLength);
        if ( !v9 )
        {
          string = 0;
          if ( (int)Microsoft::WRL::Wrappers::HString::Set<65>(&string, AddressString) >= 0 )
          {
            v27[0] = string;
            v20 = Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(v19, v32, v27, a4);
            v22 = *(_OWORD *)v20;
            v28 = *(_OWORD *)v20;
            v23 = *(_QWORD *)(v20 + 16);
            v29 = v23;
            if ( *(_QWORD *)(v20 + 8) )
            {
              v30 = v22;
              v31 = v23;
              LOBYTE(v21) = 1;
              Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
                *(_QWORD *)(a1 + 144),
                0,
                &v30,
                v21);
            }
            v16 = (HSTRING *)&v28;
            goto LABEL_20;
          }
LABEL_21:
          LOBYTE(v9) = WindowsDeleteString(string);
        }
LABEL_22:
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 )
    LOBYTE(v9) = WPP_SF_(v8[2], 34, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
  return v9;
}

```

## disassembly

```asm
0x180084ea8  push    rbx
0x180084eaa  push    rsi
0x180084eab  push    rdi
0x180084eac  push    r12
0x180084eae  push    r14
0x180084eb0  sub     rsp, 150h
0x180084eb7  mov     rax, cs:__security_cookie
0x180084ebe  xor     rax, rsp
0x180084ec1  mov     [rsp+178h+var_38], rax
0x180084ec9  mov     r14, r9
0x180084ecc  mov     rsi, r8
0x180084ecf  mov     rbx, rdx
0x180084ed2  mov     rdi, rcx
0x180084ed5  lea     r12, WPP_GLOBAL_Control
0x180084edc  mov     r9, cs:WPP_GLOBAL_Control
0x180084ee3  cmp     r9, r12
0x180084ee6  jz      short loc_180084F0B
0x180084ee8  test    byte ptr [r9+1Ch], 40h
0x180084eed  jz      short loc_180084F0B
0x180084eef  mov     edx, 21h ; '!'
0x180084ef4  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180084efb  mov     rcx, [r9+10h]
0x180084eff  call    WPP_SF_
0x180084f04  mov     r9, cs:WPP_GLOBAL_Control
0x180084f0b  xor     eax, eax
0x180084f0d  mov     [rsp+178h+AddressString], ax
0x180084f15  mov     [rsp+178h+AddressStringLength], 41h ; 'A'
0x180084f1d  cmp     word ptr [rbx], 2
0x180084f21  jnz     loc_180084FE6
0x180084f27  lea     rcx, [rbx+4]; Address
0x180084f2b  cmp     byte ptr [rcx], 7Fh
0x180084f2e  jz      loc_1800850CF
0x180084f34  cmp     [rcx], eax
0x180084f36  jz      loc_1800850CF
0x180084f3c  xor     edx, edx; Port
0x180084f3e  lea     r9, [rsp+178h+AddressStringLength]; AddressStringLength
0x180084f43  lea     r8, [rsp+178h+AddressString]; AddressString
0x180084f4b  call    cs:__imp_RtlIpv4AddressToStringExW
0x180084f51  test    eax, eax
0x180084f53  jnz     loc_1800850C8
0x180084f59  mov     [rsp+178h+string], 0
0x180084f62  lea     rdx, [rsp+178h+AddressString]
0x180084f6a  lea     rcx, [rsp+178h+string]
0x180084f6f  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180084f74  test    eax, eax
0x180084f76  js      loc_1800850BD
0x180084f7c  mov     rax, [rsp+178h+string]
0x180084f81  mov     [rsp+178h+var_138], rax
0x180084f86  mov     r9, rsi
0x180084f89  lea     r8, [rsp+178h+var_138]
0x180084f8e  lea     rdx, [rsp+178h+var_E8]
0x180084f96  call    ?TryGetDnsServer@CAdapterProperties@Internal@UX@Networking@Windows@@AEAA?AUDnsServer@345@AEBQEAUHSTRING__@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(HSTRING__ * const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x180084f9b  movups  xmm1, xmmword ptr [rax]
0x180084f9e  movups  [rsp+178h+var_108], xmm1
0x180084fa3  movsd   xmm0, qword ptr [rax+10h]
0x180084fa8  movsd   [rsp+178h+var_F8], xmm0
0x180084fb1  cmp     qword ptr [rax+8], 0
0x180084fb6  jz      short loc_180084FDC
0x180084fb8  movaps  [rsp+178h+var_128], xmm1
0x180084fbd  movaps  xmm1, xmm0
0x180084fc0  movsd   [rsp+178h+var_118], xmm1
0x180084fc6  mov     r9b, 1
0x180084fc9  lea     r8, [rsp+178h+var_128]
0x180084fce  xor     edx, edx
0x180084fd0  mov     rcx, [rdi+88h]
0x180084fd7  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180084fdc  lea     rcx, [rsp+178h+var_108]
0x180084fe1  jmp     loc_1800850B8
0x180084fe6  cmp     word ptr [rbx], 17h
0x180084fea  jnz     loc_1800850CF
0x180084ff0  lea     rcx, [rbx+8]; a
0x180084ff4  call    IN6_IS_ADDR_LOOPBACK
0x180084ff9  test    al, al
0x180084ffb  jnz     loc_1800850CF
0x180085001  call    IN6_IS_ADDR_UNSPECIFIED
0x180085006  test    al, al
0x180085008  jnz     loc_1800850CF
0x18008500e  xor     r8d, r8d; Port
0x180085011  lea     rax, [rsp+178h+AddressStringLength]
0x180085016  mov     [rsp+178h+var_158], rax; AddressStringLength
0x18008501b  lea     r9, [rsp+178h+AddressString]; AddressString
0x180085023  mov     edx, [rbx+18h]; ScopeId
0x180085026  call    cs:__imp_RtlIpv6AddressToStringExW
0x18008502c  test    eax, eax
0x18008502e  jnz     loc_1800850C8
0x180085034  mov     [rsp+178h+string], 0
0x18008503d  lea     rdx, [rsp+178h+AddressString]
0x180085045  lea     rcx, [rsp+178h+string]
0x18008504a  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x18008504f  test    eax, eax
0x180085051  js      short loc_1800850BD
0x180085053  mov     rax, [rsp+178h+string]
0x180085058  mov     [rsp+178h+var_138], rax
0x18008505d  mov     r9, r14
0x180085060  lea     r8, [rsp+178h+var_138]
0x180085065  lea     rdx, [rsp+178h+var_E8]
0x18008506d  call    ?TryGetDnsServer@CAdapterProperties@Internal@UX@Networking@Windows@@AEAA?AUDnsServer@345@AEBQEAUHSTRING__@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(HSTRING__ * const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x180085072  movups  xmm1, xmmword ptr [rax]
0x180085075  movups  [rsp+178h+var_128], xmm1
0x18008507a  movsd   xmm0, qword ptr [rax+10h]
0x18008507f  movsd   [rsp+178h+var_118], xmm0
0x180085085  cmp     qword ptr [rax+8], 0
0x18008508a  jz      short loc_1800850B3
0x18008508c  movaps  [rsp+178h+var_108], xmm1
0x180085091  movaps  xmm1, xmm0
0x180085094  movsd   [rsp+178h+var_F8], xmm1
0x18008509d  mov     r9b, 1
0x1800850a0  lea     r8, [rsp+178h+var_108]
0x1800850a5  xor     edx, edx
0x1800850a7  mov     rcx, [rdi+90h]
0x1800850ae  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x1800850b3  lea     rcx, [rsp+178h+var_128]; struct Windows::Networking::UX::DnsServer *
0x1800850b8  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x1800850bd  mov     rcx, [rsp+178h+string]; string
0x1800850c2  call    cs:__imp_WindowsDeleteString
0x1800850c8  mov     r9, cs:WPP_GLOBAL_Control
0x1800850cf  cmp     r9, r12
0x1800850d2  jz      short loc_1800850F1
0x1800850d4  test    byte ptr [r9+1Ch], 40h
0x1800850d9  jz      short loc_1800850F1
0x1800850db  mov     edx, 22h ; '"'
0x1800850e0  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800850e7  mov     rcx, [r9+10h]
0x1800850eb  call    WPP_SF_
0x1800850f0  nop
0x1800850f1  jmp     short $+2
0x1800850f3  mov     rcx, [rsp+178h+var_38]
0x1800850fb  xor     rcx, rsp; StackCookie
0x1800850fe  call    __security_check_cookie
0x180085103  add     rsp, 150h
0x18008510a  pop     r14
0x18008510c  pop     r12
0x18008510e  pop     rdi
0x18008510f  pop     rsi
0x180085110  pop     rbx
0x180085111  retn
```
