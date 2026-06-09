# Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(_IP_ADAPTER_UNICAST_ADDRESS_LH *)

- ea: `0x1800412cc`
- end: `0x180041518`
- name: `?AddIpAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_UNICAST_ADDRESS_LH@@@Z`
- size: `588`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_UNICAST_ADDRESS_LH *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041e58`

## callees

- `0x180002520`
- `0x18000a6e4`
- `0x180037c4c`
- `0x180040dbc`
- `0x1800412cc`
- `0x18004409c`
- `0x1800440e0`
- `0x180047010`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringExW` at `0x18004137e`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18004137e`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180041447`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180041447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800414c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800414c6`

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
      v12 = Microsoft::WRL::Wrappers::HString::Set<65>((Microsoft::WRL::Wrappers::HString *)&string, AddressString);
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
          v7 = Microsoft::WRL::Wrappers::HString::Set<65>((Microsoft::WRL::Wrappers::HString *)&string, AddressString);
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
0x1800412cc  mov     [rsp-8+arg_10], rbx
0x1800412d1  mov     [rsp-8+arg_18], rsi
0x1800412d6  push    rbp
0x1800412d7  push    rdi
0x1800412d8  push    r12
0x1800412da  lea     rbp, [rsp-47h]
0x1800412df  sub     rsp, 0E0h
0x1800412e6  mov     rax, cs:__security_cookie
0x1800412ed  xor     rax, rsp
0x1800412f0  mov     [rbp+57h+var_20], rax
0x1800412f4  mov     rdi, rdx
0x1800412f7  mov     rsi, rcx
0x1800412fa  lea     r12, WPP_GLOBAL_Control
0x180041301  mov     r9, cs:WPP_GLOBAL_Control
0x180041308  cmp     r9, r12
0x18004130b  jz      short loc_180041330
0x18004130d  test    byte ptr [r9+1Ch], 40h
0x180041312  jz      short loc_180041330
0x180041314  mov     edx, 19h
0x180041319  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180041320  mov     rcx, [r9+10h]
0x180041324  call    WPP_SF_
0x180041329  mov     r9, cs:WPP_GLOBAL_Control
0x180041330  mov     r10, [rdi+10h]
0x180041334  test    r10, r10
0x180041337  jz      loc_1800414D3
0x18004133d  xor     eax, eax
0x18004133f  mov     [rbp+57h+AddressString], ax
0x180041343  mov     [rbp+57h+AddressStringLength], 41h ; 'A'
0x18004134a  cmp     word ptr [r10], 2
0x18004134f  jnz     loc_1800413EB
0x180041355  cmp     dword ptr [rdi+24h], 4
0x180041359  jz      loc_1800414D3
0x18004135f  lea     rcx, [r10+4]; Address
0x180041363  cmp     byte ptr [rcx], 7Fh
0x180041366  jz      loc_1800414D3
0x18004136c  cmp     [rcx], eax
0x18004136e  jz      loc_1800414D3
0x180041374  xor     edx, edx; Port
0x180041376  lea     r9, [rbp+57h+AddressStringLength]; AddressStringLength
0x18004137a  lea     r8, [rbp+57h+AddressString]; AddressString
0x18004137e  call    cs:__imp_RtlIpv4AddressToStringExW
0x180041384  test    eax, eax
0x180041386  jnz     loc_1800414CC
0x18004138c  mov     [rbp+57h+string], 0
0x180041394  lea     rdx, [rbp+57h+AddressString]; unsigned __int16 *
0x180041398  lea     rcx, [rbp+57h+string]; this
0x18004139c  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800413a1  test    eax, eax
0x1800413a3  js      short loc_1800413BB
0x1800413a5  mov     rcx, [rsi+68h]
0x1800413a9  mov     rax, [rcx]
0x1800413ac  mov     rdx, [rbp+57h+string]
0x1800413b0  mov     rax, [rax+68h]
0x1800413b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413b9  jmp     short loc_1800413E6
0x1800413bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800413c2  cmp     rcx, r12
0x1800413c5  jz      short loc_1800413E6
0x1800413c7  test    byte ptr [rcx+1Ch], 2
0x1800413cb  jz      short loc_1800413E6
0x1800413cd  mov     edx, 1Ah
0x1800413d2  mov     r9d, eax
0x1800413d5  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800413dc  mov     rcx, [rcx+10h]
0x1800413e0  call    WPP_SF_d
0x1800413e5  nop
0x1800413e6  jmp     loc_1800414C2
0x1800413eb  cmp     word ptr [r10], 17h
0x1800413f0  jnz     loc_1800414D3
0x1800413f6  lea     rbx, [r10+8]
0x1800413fa  mov     rcx, rbx; a
0x1800413fd  call    IN6_IS_ADDR_LOOPBACK
0x180041402  test    al, al
0x180041404  jnz     loc_1800414D3
0x18004140a  call    IN6_IS_ADDR_UNSPECIFIED
0x18004140f  test    al, al
0x180041411  jnz     loc_1800414D3
0x180041417  cmp     byte ptr [rbx], 0FEh
0x18004141a  jnz     short loc_180041429
0x18004141c  mov     al, [rbx+1]
0x18004141f  and     al, 0C0h
0x180041421  cmp     al, 0C0h
0x180041423  jz      loc_1800414D3
0x180041429  cmp     dword ptr [rdi+24h], 5
0x18004142d  jz      loc_1800414D3
0x180041433  xor     r8d, r8d; Port
0x180041436  lea     rax, [rbp+57h+AddressStringLength]
0x18004143a  mov     [rsp+0F0h+var_D0], rax; AddressStringLength
0x18004143f  lea     r9, [rbp+57h+AddressString]; AddressString
0x180041443  mov     edx, [r10+18h]; ScopeId
0x180041447  call    cs:__imp_RtlIpv6AddressToStringExW
0x18004144d  test    eax, eax
0x18004144f  jnz     short loc_1800414CC
0x180041451  mov     [rbp+57h+string], 0
0x180041459  lea     rdx, [rbp+57h+AddressString]; unsigned __int16 *
0x18004145d  lea     rcx, [rbp+57h+string]; this
0x180041461  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180041466  test    eax, eax
0x180041468  js      short loc_180041497
0x18004146a  cmp     byte ptr [rbx], 0FEh
0x18004146d  jnz     short loc_180041481
0x18004146f  mov     al, [rbx+1]
0x180041472  and     al, 0C0h
0x180041474  cmp     al, 80h
0x180041476  jnz     short loc_180041481
0x180041478  mov     rcx, [rsi+0A0h]
0x18004147f  jmp     short loc_180041485
0x180041481  mov     rcx, [rsi+70h]
0x180041485  mov     rax, [rcx]
0x180041488  mov     rdx, [rbp+57h+string]
0x18004148c  mov     rax, [rax+68h]
0x180041490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041495  jmp     short loc_1800414C2
0x180041497  mov     rcx, cs:WPP_GLOBAL_Control
0x18004149e  cmp     rcx, r12
0x1800414a1  jz      short loc_1800414C2
0x1800414a3  test    byte ptr [rcx+1Ch], 2
0x1800414a7  jz      short loc_1800414C2
0x1800414a9  mov     edx, 1Bh
0x1800414ae  mov     r9d, eax
0x1800414b1  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800414b8  mov     rcx, [rcx+10h]
0x1800414bc  call    WPP_SF_d
0x1800414c1  nop
0x1800414c2  mov     rcx, [rbp+57h+string]; string
0x1800414c6  call    cs:__imp_WindowsDeleteString
0x1800414cc  mov     r9, cs:WPP_GLOBAL_Control
0x1800414d3  cmp     r9, r12
0x1800414d6  jz      short loc_1800414F4
0x1800414d8  test    byte ptr [r9+1Ch], 40h
0x1800414dd  jz      short loc_1800414F4
0x1800414df  mov     edx, 1Ch
0x1800414e4  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800414eb  mov     rcx, [r9+10h]
0x1800414ef  call    WPP_SF_
0x1800414f4  mov     rcx, [rbp+57h+var_20]
0x1800414f8  xor     rcx, rsp; StackCookie
0x1800414fb  call    __security_check_cookie
0x180041500  lea     r11, [rsp+0F0h+var_10]
0x180041508  mov     rbx, [r11+30h]
0x18004150c  mov     rsi, [r11+38h]
0x180041510  mov     rsp, r11
0x180041513  pop     r12
0x180041515  pop     rdi
0x180041516  pop     rbp
0x180041517  retn
```
