# Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(sockaddr *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)

- ea: `0x18000414c`
- end: `0x1800043ed`
- name: `?TryAddDnsAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAUsockaddr@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@1@Z`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003108`

## callees

- `0x18000352c`
- `0x18000414c`
- `0x1800043f4`
- `0x180004880`
- `0x180005be0`
- `0x180005d10`
- `0x18001eef4`
- `0x18002673c`
- `0x18002cd20`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x1800042cf`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800042cf`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800041f4`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800041f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000439b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000439b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000431f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000431f`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::CAdapterProperties::TryAddDnsAddress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  PVOID *v8; // r9
  const struct in_addr *v9; // rcx
  __int64 v10; // rcx
  __int64 DnsServer; // rax
  __int64 v12; // r9
  __int128 v13; // xmm1
  HSTRING v14; // xmm0_8
  const IN6_ADDR *v15; // rcx
  const struct in6_addr *v16; // rcx
  HSTRING v17; // rcx
  unsigned __int64 v18; // rbx
  HRESULT v19; // eax
  _QWORD *v20; // rax
  __int64 v21; // r9
  HSTRING v22; // rbx
  HSTRING v23; // rdi
  HSTRING string; // [rsp+30h] [rbp-148h] BYREF
  ULONG AddressStringLength; // [rsp+38h] [rbp-140h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-138h] BYREF
  __int128 v27; // [rsp+50h] [rbp-128h] BYREF
  HSTRING v28; // [rsp+60h] [rbp-118h]
  __int128 v29; // [rsp+70h] [rbp-108h] BYREF
  HSTRING v30; // [rsp+80h] [rbp-F8h]
  _BYTE v31[24]; // [rsp+88h] [rbp-F0h] BYREF
  WCHAR AddressString[72]; // [rsp+A0h] [rbp-D8h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  AddressString[0] = 0;
  AddressStringLength = 65;
  if ( *(_WORD *)a2 == 2 )
  {
    v9 = (const struct in_addr *)(a2 + 4);
    if ( *(_BYTE *)(a2 + 4) != 127 && v9->S_un.S_addr )
    {
      if ( !RtlIpv4AddressToStringExW(v9, 0, AddressString, &AddressStringLength) )
      {
        string = 0;
        if ( (int)Microsoft::WRL::Wrappers::HString::Set<65>(&string, AddressString) >= 0 )
        {
          v26[0] = string;
          DnsServer = Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(v10, v31, v26, a3);
          v13 = *(_OWORD *)DnsServer;
          v29 = *(_OWORD *)DnsServer;
          v14 = *(HSTRING *)(DnsServer + 16);
          v30 = v14;
          if ( *(_QWORD *)(DnsServer + 8) )
          {
            v27 = v13;
            v28 = v14;
            LOBYTE(v12) = 1;
            Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
              *(_QWORD *)(a1 + 136),
              0,
              &v27,
              v12);
          }
          FreeDnsServer((struct Windows::Networking::UX::DnsServer *)&v29);
        }
        goto LABEL_25;
      }
      goto LABEL_27;
    }
  }
  else if ( *(_WORD *)a2 == 23 && !IN6_IS_ADDR_LOOPBACK((const IN6_ADDR *)(a2 + 8)) && !IN6_IS_ADDR_UNSPECIFIED(v15) )
  {
    if ( !RtlIpv6AddressToStringExW(v16, *(_DWORD *)(a2 + 24), 0, AddressString, &AddressStringLength) )
    {
      v17 = 0;
      string = 0;
      v18 = -1;
      do
        ++v18;
      while ( AddressString[v18] );
      if ( v18 > 0xFFFFFFFF )
      {
        v19 = -2147024362;
      }
      else
      {
        WindowsDeleteString(0);
        string = 0;
        v19 = WindowsCreateString(AddressString, v18, &string);
        v17 = string;
      }
      if ( v19 < 0 )
        goto LABEL_26;
      v26[0] = v17;
      v20 = (_QWORD *)Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(v17, v31, v26, a4);
      v22 = (HSTRING)v20[1];
      v23 = (HSTRING)v20[2];
      if ( v22 )
      {
        *(_QWORD *)&v27 = *v20;
        *((_QWORD *)&v27 + 1) = v22;
        v28 = v23;
        LOBYTE(v21) = 1;
        Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(
          *(_QWORD *)(a1 + 144),
          0,
          &v27,
          v21);
      }
      WindowsDeleteString(v22);
      WindowsDeleteString(v23);
LABEL_25:
      v17 = string;
LABEL_26:
      WindowsDeleteString(v17);
    }
LABEL_27:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 )
    WPP_SF_(v8[2], 34, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
}

```

## disassembly

```asm
0x18000414c  push    rbx
0x18000414e  push    rsi
0x18000414f  push    rdi
0x180004150  push    r12
0x180004152  push    r14
0x180004154  push    r15
0x180004156  sub     rsp, 148h
0x18000415d  mov     rax, cs:__security_cookie
0x180004164  xor     rax, rsp
0x180004167  mov     [rsp+178h+var_48], rax
0x18000416f  mov     r14, r9
0x180004172  mov     rdi, r8
0x180004175  mov     rbx, rdx
0x180004178  mov     rsi, rcx
0x18000417b  lea     r12, WPP_GLOBAL_Control
0x180004182  mov     r9, cs:WPP_GLOBAL_Control
0x180004189  cmp     r9, r12
0x18000418c  jz      short loc_1800041B1
0x18000418e  test    byte ptr [r9+1Ch], 40h
0x180004193  jz      short loc_1800041B1
0x180004195  mov     edx, 21h ; '!'
0x18000419a  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800041a1  mov     rcx, [r9+10h]
0x1800041a5  call    WPP_SF_
0x1800041aa  mov     r9, cs:WPP_GLOBAL_Control
0x1800041b1  xor     r15d, r15d
0x1800041b4  mov     [rsp+178h+AddressString], r15w
0x1800041bd  mov     [rsp+178h+AddressStringLength], 41h ; 'A'
0x1800041c5  cmp     word ptr [rbx], 2
0x1800041c9  jnz     loc_18000428F
0x1800041cf  lea     rcx, [rbx+4]; Address
0x1800041d3  cmp     byte ptr [rcx], 7Fh
0x1800041d6  jz      loc_1800043A8
0x1800041dc  cmp     [rcx], r15d
0x1800041df  jz      loc_1800043A8
0x1800041e5  xor     edx, edx; Port
0x1800041e7  lea     r9, [rsp+178h+AddressStringLength]; AddressStringLength
0x1800041ec  lea     r8, [rsp+178h+AddressString]; AddressString
0x1800041f4  call    cs:__imp_RtlIpv4AddressToStringExW
0x1800041fa  test    eax, eax
0x1800041fc  jnz     loc_1800043A1
0x180004202  mov     [rsp+178h+string], r15
0x180004207  lea     rdx, [rsp+178h+AddressString]
0x18000420f  lea     rcx, [rsp+178h+string]
0x180004214  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180004219  test    eax, eax
0x18000421b  js      loc_180004396
0x180004221  mov     rax, [rsp+178h+string]
0x180004226  mov     [rsp+178h+var_138], rax
0x18000422b  mov     r9, rdi
0x18000422e  lea     r8, [rsp+178h+var_138]
0x180004233  lea     rdx, [rsp+178h+var_F0]
0x18000423b  call    ?TryGetDnsServer@CAdapterProperties@Internal@UX@Networking@Windows@@AEAA?AUDnsServer@345@AEBQEAUHSTRING__@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(HSTRING__ * const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x180004240  movups  xmm1, xmmword ptr [rax]
0x180004243  movups  [rsp+178h+var_108], xmm1
0x180004248  movsd   xmm0, qword ptr [rax+10h]
0x18000424d  movsd   [rsp+178h+var_F8], xmm0
0x180004256  cmp     [rax+8], r15
0x18000425a  jz      short loc_180004280
0x18000425c  movaps  [rsp+178h+var_128], xmm1
0x180004261  movaps  xmm1, xmm0
0x180004264  movsd   [rsp+178h+var_118], xmm1
0x18000426a  mov     r9b, 1
0x18000426d  lea     r8, [rsp+178h+var_128]
0x180004272  xor     edx, edx
0x180004274  mov     rcx, [rsi+88h]
0x18000427b  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180004280  lea     rcx, [rsp+178h+var_108]; struct Windows::Networking::UX::DnsServer *
0x180004285  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18000428a  jmp     loc_180004396
0x18000428f  cmp     word ptr [rbx], 17h
0x180004293  jnz     loc_1800043A8
0x180004299  lea     rcx, [rbx+8]; a
0x18000429d  call    IN6_IS_ADDR_LOOPBACK
0x1800042a2  test    al, al
0x1800042a4  jnz     loc_1800043A8
0x1800042aa  call    IN6_IS_ADDR_UNSPECIFIED
0x1800042af  test    al, al
0x1800042b1  jnz     loc_1800043A8
0x1800042b7  xor     r8d, r8d; Port
0x1800042ba  lea     rax, [rsp+178h+AddressStringLength]
0x1800042bf  mov     [rsp+178h+var_158], rax; AddressStringLength
0x1800042c4  lea     r9, [rsp+178h+AddressString]; AddressString
0x1800042cc  mov     edx, [rbx+18h]; ScopeId
0x1800042cf  call    cs:__imp_RtlIpv6AddressToStringExW
0x1800042d5  test    eax, eax
0x1800042d7  jnz     loc_1800043A1
0x1800042dd  mov     rcx, r15; string
0x1800042e0  mov     [rsp+178h+string], rcx
0x1800042e5  lea     rax, [rsp+178h+AddressString]
0x1800042ed  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800042f1  inc     rbx
0x1800042f4  cmp     [rax+rbx*2], r15w
0x1800042f9  jnz     short loc_1800042F1
0x1800042fb  mov     eax, 0FFFFFFFFh
0x180004300  cmp     rbx, rax
0x180004303  ja      short loc_18000432C
0x180004305  call    cs:__imp_WindowsDeleteString
0x18000430b  mov     [rsp+178h+string], r15
0x180004310  mov     edx, ebx; length
0x180004312  lea     r8, [rsp+178h+string]; string
0x180004317  lea     rcx, [rsp+178h+AddressString]; sourceString
0x18000431f  call    cs:__imp_WindowsCreateString
0x180004325  mov     rcx, [rsp+178h+string]
0x18000432a  jmp     short loc_180004331
0x18000432c  mov     eax, 80070216h
0x180004331  test    eax, eax
0x180004333  js      short loc_18000439B
0x180004335  mov     [rsp+178h+var_138], rcx
0x18000433a  mov     r9, r14
0x18000433d  lea     r8, [rsp+178h+var_138]
0x180004342  lea     rdx, [rsp+178h+var_F0]
0x18000434a  call    ?TryGetDnsServer@CAdapterProperties@Internal@UX@Networking@Windows@@AEAA?AUDnsServer@345@AEBQEAUHSTRING__@@PEAU?$IVectorView@UDnsServer@UX@Networking@Windows@@@Collections@Foundation@5@@Z; Windows::Networking::UX::Internal::CAdapterProperties::TryGetDnsServer(HSTRING__ * const &,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::DnsServer> *)
0x18000434f  mov     rdx, [rax]
0x180004352  mov     rbx, [rax+8]
0x180004356  mov     rdi, [rax+10h]
0x18000435a  test    rbx, rbx
0x18000435d  jz      short loc_180004384
0x18000435f  mov     qword ptr [rsp+178h+var_128], rdx
0x180004364  mov     qword ptr [rsp+178h+var_128+8], rbx
0x180004369  mov     [rsp+178h+var_118], rdi
0x18000436e  mov     r9b, 1
0x180004371  lea     r8, [rsp+178h+var_128]
0x180004376  xor     edx, edx
0x180004378  mov     rcx, [rsi+90h]
0x18000437f  call    ?InsertAtInternal@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUDnsServer@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::DnsServer,bool)
0x180004384  mov     rcx, rbx; string
0x180004387  call    cs:__imp_WindowsDeleteString
0x18000438d  mov     rcx, rdi; string
0x180004390  call    cs:__imp_WindowsDeleteString
0x180004396  mov     rcx, [rsp+178h+string]; string
0x18000439b  call    cs:__imp_WindowsDeleteString
0x1800043a1  mov     r9, cs:WPP_GLOBAL_Control
0x1800043a8  cmp     r9, r12
0x1800043ab  jz      short loc_1800043CA
0x1800043ad  test    byte ptr [r9+1Ch], 40h
0x1800043b2  jz      short loc_1800043CA
0x1800043b4  mov     edx, 22h ; '"'
0x1800043b9  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800043c0  mov     rcx, [r9+10h]
0x1800043c4  call    WPP_SF_
0x1800043c9  nop
0x1800043ca  jmp     short $+2
0x1800043cc  mov     rcx, [rsp+178h+var_48]
0x1800043d4  xor     rcx, rsp; StackCookie
0x1800043d7  call    __security_check_cookie
0x1800043dc  add     rsp, 148h
0x1800043e3  pop     r15
0x1800043e5  pop     r14
0x1800043e7  pop     r12
0x1800043e9  pop     rdi
0x1800043ea  pop     rsi
0x1800043eb  pop     rbx
0x1800043ec  retn
```
