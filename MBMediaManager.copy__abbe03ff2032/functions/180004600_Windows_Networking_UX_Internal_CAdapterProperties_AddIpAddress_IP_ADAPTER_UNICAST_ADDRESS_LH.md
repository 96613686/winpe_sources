# Windows::Networking::UX::Internal::CAdapterProperties::AddIpAddress(_IP_ADAPTER_UNICAST_ADDRESS_LH *)

- ea: `0x180004600`
- end: `0x180004878`
- name: `?AddIpAddress@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAXPEAU_IP_ADAPTER_UNICAST_ADDRESS_LH@@@Z`
- size: `632`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_UNICAST_ADDRESS_LH *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003108`

## callees

- `0x180004600`
- `0x180004880`
- `0x180005be0`
- `0x180005c80`
- `0x180005d10`
- `0x18002673c`
- `0x18002cd20`
- `0x180059010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExW` at `0x180004778`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180004778`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800046b3`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800046b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800047a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800047a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800047bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800047bc`

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
  unsigned __int64 v12; // rdi
  HRESULT v13; // eax
  __int64 v14; // rcx
  HSTRING string; // [rsp+30h] [rbp-79h] BYREF
  ULONG AddressStringLength; // [rsp+38h] [rbp-71h] BYREF
  WCHAR AddressString[72]; // [rsp+40h] [rbp-69h] BYREF

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
        goto LABEL_38;
      v8 = &lpSockaddr->sa_data[6];
      if ( IN6_IS_ADDR_LOOPBACK((const IN6_ADDR *)&lpSockaddr->sa_data[6])
        || IN6_IS_ADDR_UNSPECIFIED(v9)
        || *v8 == -2 && (v8[1] & 0xC0) == 0xC0 )
      {
        goto LABEL_38;
      }
      if ( a2->SuffixOrigin == NlsoRandom )
        goto LABEL_38;
      if ( RtlIpv6AddressToStringExW(v10, *(_DWORD *)(v11 + 24), 0, AddressString, &AddressStringLength) )
        goto LABEL_37;
      string = 0;
      v12 = -1;
      do
        ++v12;
      while ( AddressString[v12] );
      if ( v12 > 0xFFFFFFFF )
      {
        v13 = -2147024362;
      }
      else
      {
        WindowsDeleteString(0);
        string = 0;
        v13 = WindowsCreateString(AddressString, v12, &string);
        if ( v13 >= 0 )
        {
          if ( *v8 == -2 && (v8[1] & 0xC0) == 0x80 )
            v14 = *((_QWORD *)this + 20);
          else
            v14 = *((_QWORD *)this + 14);
          (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v14 + 104LL))(v14, string);
          goto LABEL_36;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_07bd92578572370284dbe53730fdfa75_Traceguids,
          (unsigned int)v13);
      goto LABEL_36;
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
LABEL_37:
            v4 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_38;
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
LABEL_36:
          WindowsDeleteString(string);
          goto LABEL_37;
        }
      }
    }
  }
LABEL_38:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
    WPP_SF_(v4[2], 28, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
}

```

## disassembly

```asm
0x180004600  mov     [rsp-8+arg_10], rbx
0x180004605  push    rbp
0x180004606  push    rsi
0x180004607  push    rdi
0x180004608  push    r12
0x18000460a  push    r14
0x18000460c  lea     rbp, [rsp-37h]
0x180004611  sub     rsp, 0E0h
0x180004618  mov     rax, cs:__security_cookie
0x18000461f  xor     rax, rsp
0x180004622  mov     [rbp+57h+var_30], rax
0x180004626  mov     rdi, rdx
0x180004629  mov     rsi, rcx
0x18000462c  lea     r12, WPP_GLOBAL_Control
0x180004633  mov     r9, cs:WPP_GLOBAL_Control
0x18000463a  cmp     r9, r12
0x18000463d  jz      short loc_180004662
0x18000463f  test    byte ptr [r9+1Ch], 40h
0x180004644  jz      short loc_180004662
0x180004646  mov     edx, 19h
0x18000464b  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180004652  mov     rcx, [r9+10h]
0x180004656  call    WPP_SF_
0x18000465b  mov     r9, cs:WPP_GLOBAL_Control
0x180004662  mov     r10, [rdi+10h]
0x180004666  xor     r14d, r14d
0x180004669  test    r10, r10
0x18000466c  jz      loc_180004834
0x180004672  mov     [rbp+57h+AddressString], r14w
0x180004677  mov     [rbp+57h+AddressStringLength], 41h ; 'A'
0x18000467e  cmp     word ptr [r10], 2
0x180004683  jnz     loc_18000471C
0x180004689  cmp     dword ptr [rdi+24h], 4
0x18000468d  jz      loc_180004834
0x180004693  lea     rcx, [r10+4]; Address
0x180004697  cmp     byte ptr [rcx], 7Fh
0x18000469a  jz      loc_180004834
0x1800046a0  cmp     [rcx], r14d
0x1800046a3  jz      loc_180004834
0x1800046a9  xor     edx, edx; Port
0x1800046ab  lea     r9, [rbp+57h+AddressStringLength]; AddressStringLength
0x1800046af  lea     r8, [rbp+57h+AddressString]; AddressString
0x1800046b3  call    cs:__imp_RtlIpv4AddressToStringExW
0x1800046b9  test    eax, eax
0x1800046bb  jnz     loc_18000482D
0x1800046c1  mov     [rbp+57h+string], r14
0x1800046c5  lea     rdx, [rbp+57h+AddressString]
0x1800046c9  lea     rcx, [rbp+57h+string]
0x1800046cd  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800046d2  test    eax, eax
0x1800046d4  js      short loc_1800046EC
0x1800046d6  mov     rcx, [rsi+68h]
0x1800046da  mov     rax, [rcx]
0x1800046dd  mov     rdx, [rbp+57h+string]
0x1800046e1  mov     rax, [rax+68h]
0x1800046e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ea  jmp     short loc_180004717
0x1800046ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046f3  cmp     rcx, r12
0x1800046f6  jz      short loc_180004717
0x1800046f8  test    byte ptr [rcx+1Ch], 2
0x1800046fc  jz      short loc_180004717
0x1800046fe  mov     edx, 1Ah
0x180004703  mov     r9d, eax
0x180004706  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18000470d  mov     rcx, [rcx+10h]
0x180004711  call    WPP_SF_d
0x180004716  nop
0x180004717  jmp     loc_180004823
0x18000471c  cmp     word ptr [r10], 17h
0x180004721  jnz     loc_180004834
0x180004727  lea     rbx, [r10+8]
0x18000472b  mov     rcx, rbx; a
0x18000472e  call    IN6_IS_ADDR_LOOPBACK
0x180004733  test    al, al
0x180004735  jnz     loc_180004834
0x18000473b  call    IN6_IS_ADDR_UNSPECIFIED
0x180004740  test    al, al
0x180004742  jnz     loc_180004834
0x180004748  cmp     byte ptr [rbx], 0FEh
0x18000474b  jnz     short loc_18000475A
0x18000474d  mov     al, [rbx+1]
0x180004750  and     al, 0C0h
0x180004752  cmp     al, 0C0h
0x180004754  jz      loc_180004834
0x18000475a  cmp     dword ptr [rdi+24h], 5
0x18000475e  jz      loc_180004834
0x180004764  xor     r8d, r8d; Port
0x180004767  lea     rax, [rbp+57h+AddressStringLength]
0x18000476b  mov     [rsp+100h+var_E0], rax; AddressStringLength
0x180004770  lea     r9, [rbp+57h+AddressString]; AddressString
0x180004774  mov     edx, [r10+18h]; ScopeId
0x180004778  call    cs:__imp_RtlIpv6AddressToStringExW
0x18000477e  test    eax, eax
0x180004780  jnz     loc_18000482D
0x180004786  mov     [rbp+57h+string], r14
0x18000478a  lea     rax, [rbp+57h+AddressString]
0x18000478e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004792  inc     rdi
0x180004795  cmp     [rax+rdi*2], r14w
0x18000479a  jnz     short loc_180004792
0x18000479c  mov     eax, 0FFFFFFFFh
0x1800047a1  cmp     rdi, rax
0x1800047a4  ja      short loc_1800047F3
0x1800047a6  xor     ecx, ecx; string
0x1800047a8  call    cs:__imp_WindowsDeleteString
0x1800047ae  mov     [rbp+57h+string], r14
0x1800047b2  mov     edx, edi; length
0x1800047b4  lea     r8, [rbp+57h+string]; string
0x1800047b8  lea     rcx, [rbp+57h+AddressString]; sourceString
0x1800047bc  call    cs:__imp_WindowsCreateString
0x1800047c2  test    eax, eax
0x1800047c4  js      short loc_1800047F8
0x1800047c6  cmp     byte ptr [rbx], 0FEh
0x1800047c9  jnz     short loc_1800047DD
0x1800047cb  mov     al, [rbx+1]
0x1800047ce  and     al, 0C0h
0x1800047d0  cmp     al, 80h
0x1800047d2  jnz     short loc_1800047DD
0x1800047d4  mov     rcx, [rsi+0A0h]
0x1800047db  jmp     short loc_1800047E1
0x1800047dd  mov     rcx, [rsi+70h]
0x1800047e1  mov     rax, [rcx]
0x1800047e4  mov     rdx, [rbp+57h+string]
0x1800047e8  mov     rax, [rax+68h]
0x1800047ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f1  jmp     short loc_180004823
0x1800047f3  mov     eax, 80070216h
0x1800047f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047ff  cmp     rcx, r12
0x180004802  jz      short loc_180004823
0x180004804  test    byte ptr [rcx+1Ch], 2
0x180004808  jz      short loc_180004823
0x18000480a  mov     edx, 1Bh
0x18000480f  mov     r9d, eax
0x180004812  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180004819  mov     rcx, [rcx+10h]
0x18000481d  call    WPP_SF_d
0x180004822  nop
0x180004823  mov     rcx, [rbp+57h+string]; string
0x180004827  call    cs:__imp_WindowsDeleteString
0x18000482d  mov     r9, cs:WPP_GLOBAL_Control
0x180004834  cmp     r9, r12
0x180004837  jz      short loc_180004855
0x180004839  test    byte ptr [r9+1Ch], 40h
0x18000483e  jz      short loc_180004855
0x180004840  mov     edx, 1Ch
0x180004845  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18000484c  mov     rcx, [r9+10h]
0x180004850  call    WPP_SF_
0x180004855  mov     rcx, [rbp+57h+var_30]
0x180004859  xor     rcx, rsp; StackCookie
0x18000485c  call    __security_check_cookie
0x180004861  mov     rbx, [rsp+100h+arg_10]
0x180004869  add     rsp, 0E0h
0x180004870  pop     r14
0x180004872  pop     r12
0x180004874  pop     rdi
0x180004875  pop     rsi
0x180004876  pop     rbp
0x180004877  retn
```
