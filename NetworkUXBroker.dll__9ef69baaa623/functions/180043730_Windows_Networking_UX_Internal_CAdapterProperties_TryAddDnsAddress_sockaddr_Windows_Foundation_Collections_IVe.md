# Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(sockaddr *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)

- ea: `0x180043730`
- end: `0x18004399a`
- name: `?TryAddDnsAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAUsockaddr@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@1@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041e58`

## callees

- `0x180002520`
- `0x18000a6e4`
- `0x180013b8c`
- `0x180016d54`
- `0x180040dbc`
- `0x180043730`
- `0x1800439a0`
- `0x18004409c`
- `0x1800440e0`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringExW` at `0x1800437d3`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800437d3`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800438ae`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800438ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004394a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004394a`

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
        if ( (int)Microsoft::WRL::Wrappers::HString::Set<65>(
                    (Microsoft::WRL::Wrappers::HString *)&string,
                    AddressString) >= 0 )
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
          if ( (int)Microsoft::WRL::Wrappers::HString::Set<65>(
                      (Microsoft::WRL::Wrappers::HString *)&string,
                      AddressString) >= 0 )
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
0x180043730  push    rbx
0x180043732  push    rsi
0x180043733  push    rdi
0x180043734  push    r12
0x180043736  push    r14
0x180043738  sub     rsp, 150h
0x18004373f  mov     rax, cs:__security_cookie
0x180043746  xor     rax, rsp
0x180043749  mov     [rsp+178h+var_38], rax
0x180043751  mov     r14, r9
0x180043754  mov     rsi, r8
0x180043757  mov     rbx, rdx
0x18004375a  mov     rdi, rcx
0x18004375d  lea     r12, WPP_GLOBAL_Control
0x180043764  mov     r9, cs:WPP_GLOBAL_Control
0x18004376b  cmp     r9, r12
0x18004376e  jz      short loc_180043793
0x180043770  test    byte ptr [r9+1Ch], 40h
0x180043775  jz      short loc_180043793
0x180043777  mov     edx, 21h ; '!'
0x18004377c  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180043783  mov     rcx, [r9+10h]
0x180043787  call    WPP_SF_
0x18004378c  mov     r9, cs:WPP_GLOBAL_Control
0x180043793  xor     eax, eax
0x180043795  mov     [rsp+178h+AddressString], ax
0x18004379d  mov     [rsp+178h+AddressStringLength], 41h ; 'A'
0x1800437a5  cmp     word ptr [rbx], 2
0x1800437a9  jnz     loc_18004386E
0x1800437af  lea     rcx, [rbx+4]; Address
0x1800437b3  cmp     byte ptr [rcx], 7Fh
0x1800437b6  jz      loc_180043957
0x1800437bc  cmp     [rcx], eax
0x1800437be  jz      loc_180043957
0x1800437c4  xor     edx, edx; Port
0x1800437c6  lea     r9, [rsp+178h+AddressStringLength]; AddressStringLength
0x1800437cb  lea     r8, [rsp+178h+AddressString]; AddressString
0x1800437d3  call    cs:__imp_RtlIpv4AddressToStringExW
0x1800437d9  test    eax, eax
0x1800437db  jnz     loc_180043950
0x1800437e1  mov     [rsp+178h+string], 0
0x1800437ea  lea     rdx, [rsp+178h+AddressString]; unsigned __int16 *
0x1800437f2  lea     rcx, [rsp+178h+string]; this
0x1800437f7  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800437fc  test    eax, eax
0x1800437fe  js      loc_180043945
0x180043804  mov     rax, [rsp+178h+string]
0x180043809  mov     [rsp+178h+var_138], rax
0x18004380e  mov     r9, rsi
0x180043811  lea     r8, [rsp+178h+var_138]
0x180043816  lea     rdx, [rsp+178h+var_E8]
0x18004381e  call    ?TryGetDnsServer@CAdapterProperties@Internal@UX@Networking@Windows@@AEAA?AUDnsServer@345@AEBQEAUHSTRING__@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(HSTRING__ * const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x180043823  movups  xmm1, xmmword ptr [rax]
0x180043826  movups  [rsp+178h+var_108], xmm1
0x18004382b  movsd   xmm0, qword ptr [rax+10h]
0x180043830  movsd   [rsp+178h+var_F8], xmm0
0x180043839  cmp     qword ptr [rax+8], 0
0x18004383e  jz      short loc_180043864
0x180043840  movaps  [rsp+178h+var_128], xmm1
0x180043845  movaps  xmm1, xmm0
0x180043848  movsd   [rsp+178h+var_118], xmm1
0x18004384e  mov     r9b, 1
0x180043851  lea     r8, [rsp+178h+var_128]
0x180043856  xor     edx, edx
0x180043858  mov     rcx, [rdi+88h]
0x18004385f  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180043864  lea     rcx, [rsp+178h+var_108]
0x180043869  jmp     loc_180043940
0x18004386e  cmp     word ptr [rbx], 17h
0x180043872  jnz     loc_180043957
0x180043878  lea     rcx, [rbx+8]; a
0x18004387c  call    IN6_IS_ADDR_LOOPBACK
0x180043881  test    al, al
0x180043883  jnz     loc_180043957
0x180043889  call    IN6_IS_ADDR_UNSPECIFIED
0x18004388e  test    al, al
0x180043890  jnz     loc_180043957
0x180043896  xor     r8d, r8d; Port
0x180043899  lea     rax, [rsp+178h+AddressStringLength]
0x18004389e  mov     [rsp+178h+var_158], rax; AddressStringLength
0x1800438a3  lea     r9, [rsp+178h+AddressString]; AddressString
0x1800438ab  mov     edx, [rbx+18h]; ScopeId
0x1800438ae  call    cs:__imp_RtlIpv6AddressToStringExW
0x1800438b4  test    eax, eax
0x1800438b6  jnz     loc_180043950
0x1800438bc  mov     [rsp+178h+string], 0
0x1800438c5  lea     rdx, [rsp+178h+AddressString]; unsigned __int16 *
0x1800438cd  lea     rcx, [rsp+178h+string]; this
0x1800438d2  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800438d7  test    eax, eax
0x1800438d9  js      short loc_180043945
0x1800438db  mov     rax, [rsp+178h+string]
0x1800438e0  mov     [rsp+178h+var_138], rax
0x1800438e5  mov     r9, r14
0x1800438e8  lea     r8, [rsp+178h+var_138]
0x1800438ed  lea     rdx, [rsp+178h+var_E8]
0x1800438f5  call    ?TryGetDnsServer@CAdapterProperties@Internal@UX@Networking@Windows@@AEAA?AUDnsServer@345@AEBQEAUHSTRING__@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(HSTRING__ * const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x1800438fa  movups  xmm1, xmmword ptr [rax]
0x1800438fd  movups  [rsp+178h+var_128], xmm1
0x180043902  movsd   xmm0, qword ptr [rax+10h]
0x180043907  movsd   [rsp+178h+var_118], xmm0
0x18004390d  cmp     qword ptr [rax+8], 0
0x180043912  jz      short loc_18004393B
0x180043914  movaps  [rsp+178h+var_108], xmm1
0x180043919  movaps  xmm1, xmm0
0x18004391c  movsd   [rsp+178h+var_F8], xmm1
0x180043925  mov     r9b, 1
0x180043928  lea     r8, [rsp+178h+var_108]
0x18004392d  xor     edx, edx
0x18004392f  mov     rcx, [rdi+90h]
0x180043936  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x18004393b  lea     rcx, [rsp+178h+var_128]; struct Windows::Networking::UX::DnsServer *
0x180043940  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x180043945  mov     rcx, [rsp+178h+string]; string
0x18004394a  call    cs:__imp_WindowsDeleteString
0x180043950  mov     r9, cs:WPP_GLOBAL_Control
0x180043957  cmp     r9, r12
0x18004395a  jz      short loc_180043979
0x18004395c  test    byte ptr [r9+1Ch], 40h
0x180043961  jz      short loc_180043979
0x180043963  mov     edx, 22h ; '"'
0x180043968  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18004396f  mov     rcx, [r9+10h]
0x180043973  call    WPP_SF_
0x180043978  nop
0x180043979  jmp     short $+2
0x18004397b  mov     rcx, [rsp+178h+var_38]
0x180043983  xor     rcx, rsp; StackCookie
0x180043986  call    __security_check_cookie
0x18004398b  add     rsp, 150h
0x180043992  pop     r14
0x180043994  pop     r12
0x180043996  pop     rdi
0x180043997  pop     rsi
0x180043998  pop     rbx
0x180043999  retn
```
