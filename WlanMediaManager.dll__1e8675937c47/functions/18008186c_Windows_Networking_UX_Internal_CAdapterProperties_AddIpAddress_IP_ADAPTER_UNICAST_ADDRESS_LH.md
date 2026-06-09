# Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(_IP_ADAPTER_UNICAST_ADDRESS_LH *)

- ea: `0x18008186c`
- end: `0x180081ab8`
- name: `?AddIpAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_UNICAST_ADDRESS_LH@@@Z`
- size: `588`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_UNICAST_ADDRESS_LH *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180082b60`

## callees

- `0x180003ed0`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18001d6d0`
- `0x18008186c`
- `0x1800858a8`
- `0x1800858ec`
- `0x18008e010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x1800819e7`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800819e7`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18008191e`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18008191e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081a66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(
        Windows::Networking::UX::Internal::CAdapterProperties *this,
        struct _IP_ADAPTER_UNICAST_ADDRESS_LH *a2)
{
  PVOID *v4; // r9
  LPSOCKADDR lpSockaddr; // r10
  const struct in_addr *v6; // rcx
  int v7; // eax
  CHAR *v8; // rbx
  const IN6_ADDR *v9; // rcx
  const struct in6_addr *v10; // rcx
  __int64 v11; // r10
  int v12; // eax
  __int64 v13; // rcx
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  ULONG AddressStringLength; // [rsp+38h] [rbp-61h] BYREF
  WCHAR AddressString[72]; // [rsp+40h] [rbp-59h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  lpSockaddr = a2->Address.lpSockaddr;
  if ( lpSockaddr )
  {
    AddressString[0] = 0;
    AddressStringLength = 65;
    if ( lpSockaddr->sa_family != 2 )
    {
      if ( lpSockaddr->sa_family != 23 )
        goto LABEL_34;
      v8 = &lpSockaddr->sa_data[6];
      if ( IN6_IS_ADDR_LOOPBACK((const IN6_ADDR *)&lpSockaddr->sa_data[6])
        || IN6_IS_ADDR_UNSPECIFIED(v9)
        || *v8 == -2 && (v8[1] & 0xC0) == 0xC0 )
      {
        goto LABEL_34;
      }
      if ( a2->SuffixOrigin == NlsoRandom )
        goto LABEL_34;
      if ( RtlIpv6AddressToStringExW(v10, *(_DWORD *)(v11 + 24), 0, AddressString, &AddressStringLength) )
        goto LABEL_33;
      string = 0;
      v12 = Microsoft::WRL::Wrappers::HString::Set<65>(&string, AddressString);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_07bd92578572370284dbe53730fdfa75_Traceguids,
            (unsigned int)v12);
      }
      else
      {
        if ( *v8 == -2 && (v8[1] & 0xC0) == 0x80 )
          v13 = *((_QWORD *)this + 20);
        else
          v13 = *((_QWORD *)this + 14);
        (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v13 + 104LL))(v13, string);
      }
      goto LABEL_32;
    }
    if ( a2->SuffixOrigin != NlsoLinkLayerAddress )
    {
      v6 = (const struct in_addr *)&lpSockaddr->sa_data[2];
      if ( lpSockaddr->sa_data[2] != 127 )
      {
        if ( v6->S_un.S_addr )
        {
          if ( RtlIpv4AddressToStringExW(v6, 0, AddressString, &AddressStringLength) )
          {
LABEL_33:
            v4 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_34;
          }
          string = 0;
          v7 = Microsoft::WRL::Wrappers::HString::Set<65>(&string, AddressString);
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                WPP_07bd92578572370284dbe53730fdfa75_Traceguids,
                (unsigned int)v7);
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 13) + 104LL))(*((_QWORD *)this + 13), string);
          }
LABEL_32:
          WindowsDeleteString(string);
          goto LABEL_33;
        }
      }
    }
  }
LABEL_34:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
    WPP_SF_(v4[2], 28, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
}

```

## disassembly

```asm
0x18008186c  mov     [rsp-8+arg_10], rbx
0x180081871  mov     [rsp-8+arg_18], rsi
0x180081876  push    rbp
0x180081877  push    rdi
0x180081878  push    r12
0x18008187a  lea     rbp, [rsp-47h]
0x18008187f  sub     rsp, 0E0h
0x180081886  mov     rax, cs:__security_cookie
0x18008188d  xor     rax, rsp
0x180081890  mov     [rbp+57h+var_20], rax
0x180081894  mov     rdi, rdx
0x180081897  mov     rsi, rcx
0x18008189a  lea     r12, WPP_GLOBAL_Control
0x1800818a1  mov     r9, cs:WPP_GLOBAL_Control
0x1800818a8  cmp     r9, r12
0x1800818ab  jz      short loc_1800818D0
0x1800818ad  test    byte ptr [r9+1Ch], 40h
0x1800818b2  jz      short loc_1800818D0
0x1800818b4  mov     edx, 19h
0x1800818b9  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800818c0  mov     rcx, [r9+10h]
0x1800818c4  call    WPP_SF_
0x1800818c9  mov     r9, cs:WPP_GLOBAL_Control
0x1800818d0  mov     r10, [rdi+10h]
0x1800818d4  test    r10, r10
0x1800818d7  jz      loc_180081A73
0x1800818dd  xor     eax, eax
0x1800818df  mov     [rbp+57h+AddressString], ax
0x1800818e3  mov     [rbp+57h+AddressStringLength], 41h ; 'A'
0x1800818ea  cmp     word ptr [r10], 2
0x1800818ef  jnz     loc_18008198B
0x1800818f5  cmp     dword ptr [rdi+24h], 4
0x1800818f9  jz      loc_180081A73
0x1800818ff  lea     rcx, [r10+4]; Address
0x180081903  cmp     byte ptr [rcx], 7Fh
0x180081906  jz      loc_180081A73
0x18008190c  cmp     [rcx], eax
0x18008190e  jz      loc_180081A73
0x180081914  xor     edx, edx; Port
0x180081916  lea     r9, [rbp+57h+AddressStringLength]; AddressStringLength
0x18008191a  lea     r8, [rbp+57h+AddressString]; AddressString
0x18008191e  call    cs:__imp_RtlIpv4AddressToStringExW
0x180081924  test    eax, eax
0x180081926  jnz     loc_180081A6C
0x18008192c  mov     [rbp+57h+string], 0
0x180081934  lea     rdx, [rbp+57h+AddressString]
0x180081938  lea     rcx, [rbp+57h+string]
0x18008193c  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180081941  test    eax, eax
0x180081943  js      short loc_18008195B
0x180081945  mov     rcx, [rsi+68h]
0x180081949  mov     rax, [rcx]
0x18008194c  mov     rdx, [rbp+57h+string]
0x180081950  mov     rax, [rax+68h]
0x180081954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081959  jmp     short loc_180081986
0x18008195b  mov     rcx, cs:WPP_GLOBAL_Control
0x180081962  cmp     rcx, r12
0x180081965  jz      short loc_180081986
0x180081967  test    byte ptr [rcx+1Ch], 2
0x18008196b  jz      short loc_180081986
0x18008196d  mov     edx, 1Ah
0x180081972  mov     r9d, eax
0x180081975  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18008197c  mov     rcx, [rcx+10h]
0x180081980  call    WPP_SF_d
0x180081985  nop
0x180081986  jmp     loc_180081A62
0x18008198b  cmp     word ptr [r10], 17h
0x180081990  jnz     loc_180081A73
0x180081996  lea     rbx, [r10+8]
0x18008199a  mov     rcx, rbx; a
0x18008199d  call    IN6_IS_ADDR_LOOPBACK
0x1800819a2  test    al, al
0x1800819a4  jnz     loc_180081A73
0x1800819aa  call    IN6_IS_ADDR_UNSPECIFIED
0x1800819af  test    al, al
0x1800819b1  jnz     loc_180081A73
0x1800819b7  cmp     byte ptr [rbx], 0FEh
0x1800819ba  jnz     short loc_1800819C9
0x1800819bc  mov     al, [rbx+1]
0x1800819bf  and     al, 0C0h
0x1800819c1  cmp     al, 0C0h
0x1800819c3  jz      loc_180081A73
0x1800819c9  cmp     dword ptr [rdi+24h], 5
0x1800819cd  jz      loc_180081A73
0x1800819d3  xor     r8d, r8d; Port
0x1800819d6  lea     rax, [rbp+57h+AddressStringLength]
0x1800819da  mov     [rsp+0F0h+var_D0], rax; AddressStringLength
0x1800819df  lea     r9, [rbp+57h+AddressString]; AddressString
0x1800819e3  mov     edx, [r10+18h]; ScopeId
0x1800819e7  call    cs:__imp_RtlIpv6AddressToStringExW
0x1800819ed  test    eax, eax
0x1800819ef  jnz     short loc_180081A6C
0x1800819f1  mov     [rbp+57h+string], 0
0x1800819f9  lea     rdx, [rbp+57h+AddressString]
0x1800819fd  lea     rcx, [rbp+57h+string]
0x180081a01  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180081a06  test    eax, eax
0x180081a08  js      short loc_180081A37
0x180081a0a  cmp     byte ptr [rbx], 0FEh
0x180081a0d  jnz     short loc_180081A21
0x180081a0f  mov     al, [rbx+1]
0x180081a12  and     al, 0C0h
0x180081a14  cmp     al, 80h
0x180081a16  jnz     short loc_180081A21
0x180081a18  mov     rcx, [rsi+0A0h]
0x180081a1f  jmp     short loc_180081A25
0x180081a21  mov     rcx, [rsi+70h]
0x180081a25  mov     rax, [rcx]
0x180081a28  mov     rdx, [rbp+57h+string]
0x180081a2c  mov     rax, [rax+68h]
0x180081a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a35  jmp     short loc_180081A62
0x180081a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180081a3e  cmp     rcx, r12
0x180081a41  jz      short loc_180081A62
0x180081a43  test    byte ptr [rcx+1Ch], 2
0x180081a47  jz      short loc_180081A62
0x180081a49  mov     edx, 1Bh
0x180081a4e  mov     r9d, eax
0x180081a51  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180081a58  mov     rcx, [rcx+10h]
0x180081a5c  call    WPP_SF_d
0x180081a61  nop
0x180081a62  mov     rcx, [rbp+57h+string]; string
0x180081a66  call    cs:__imp_WindowsDeleteString
0x180081a6c  mov     r9, cs:WPP_GLOBAL_Control
0x180081a73  cmp     r9, r12
0x180081a76  jz      short loc_180081A94
0x180081a78  test    byte ptr [r9+1Ch], 40h
0x180081a7d  jz      short loc_180081A94
0x180081a7f  mov     edx, 1Ch
0x180081a84  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180081a8b  mov     rcx, [r9+10h]
0x180081a8f  call    WPP_SF_
0x180081a94  mov     rcx, [rbp+57h+var_20]
0x180081a98  xor     rcx, rsp; StackCookie
0x180081a9b  call    __security_check_cookie
0x180081aa0  lea     r11, [rsp+0F0h+var_10]
0x180081aa8  mov     rbx, [r11+30h]
0x180081aac  mov     rsi, [r11+38h]
0x180081ab0  mov     rsp, r11
0x180081ab3  pop     r12
0x180081ab5  pop     rdi
0x180081ab6  pop     rbp
0x180081ab7  retn
```
