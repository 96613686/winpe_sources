# _generateIPDescriptorNode(IXMLDOMDocument2 *,IXMLDOMNode *,IP_DESCRIPTOR *,ulong)

- ea: `0x18000f854`
- end: `0x18000fc00`
- name: `?_generateIPDescriptorNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUIP_DESCRIPTOR@@K@Z`
- size: `940`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IP_DESCRIPTOR *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800103ac`

## callees

- `0x180001670`
- `0x180002034`
- `0x18000f854`
- `0x180011f90`
- `0x180012260`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringW` at `0x18000f8ba`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000f91a`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000f8ba`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000f91a`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000f977`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000f977`

## string_xrefs

- `0x18000f89e`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000f8a5`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000f8d0`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000f930`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000f98d`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000f9e2`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fa28`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fa6b`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000faae`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000faf1`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fb34`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fb73`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fbad`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x18000fa37`: `ProtocolId`
- `0x18000fb43`: `TypeofService`

## pseudocode

```c
unsigned int __fastcall _generateIPDescriptorNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct IP_DESCRIPTOR *a3,
        unsigned int a4)
{
  OLECHAR *v8; // rsi
  OLECHAR *v9; // r9
  unsigned int result; // eax
  OLECHAR *v11; // r9
  OLECHAR *v12; // r9
  OLECHAR *v13; // r9
  OLECHAR *v14; // r9
  OLECHAR *v15; // r9
  OLECHAR *v16; // r9
  OLECHAR *v17; // r9
  OLECHAR *v18; // r9
  OLECHAR *v19; // r9
  struct IXMLDOMNode **v20; // [rsp+28h] [rbp-B0h]
  WCHAR S[48]; // [rsp+40h] [rbp-98h] BYREF

  memset_0(S, 0, 0x5Cu);
  v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  if ( (*(_BYTE *)a3 & 0x40) == 0 )
    goto LABEL_69;
  RtlIpv4AddressToStringW((const struct in_addr *)a3 + 5, S);
  if ( a4 < 3 )
  {
    v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  result = XcAddChildElement(a1, a2, (OLECHAR *)L"IPv4", v9, S, 0);
  if ( !result )
  {
LABEL_69:
    if ( (*(_DWORD *)a3 & 0x200) == 0 )
      goto LABEL_70;
    RtlIpv4AddressToStringW((const struct in_addr *)a3 + 6, S);
    if ( a4 < 3 )
    {
      v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    result = XcAddChildElement(a1, a2, (OLECHAR *)L"IPv4MaskField", v11, S, 0);
    if ( !result )
    {
LABEL_70:
      if ( *(char *)a3 >= 0 )
        goto LABEL_71;
      RtlIpv6AddressToStringW((const struct in6_addr *)((char *)a3 + 28), S);
      if ( a4 < 3 )
      {
        v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      else
      {
        v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
      }
      result = XcAddChildElement(a1, a2, (OLECHAR *)L"IPv6", v12, S, 0);
      if ( !result )
      {
LABEL_71:
        if ( (*(_DWORD *)a3 & 0x400) == 0 )
          goto LABEL_72;
        if ( a4 < 3 )
        {
          v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( a4 != 2 )
            v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v13 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"IPv6PreFixLength", v13, *((unsigned __int8 *)a3 + 44), v20);
        if ( !result )
        {
LABEL_72:
          if ( (*(_DWORD *)a3 & 0x100) == 0 )
            goto LABEL_73;
          if ( a4 < 3 )
          {
            v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
            if ( a4 != 2 )
              v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
          }
          else
          {
            v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
          }
          result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"ProtocolId", v14, *((unsigned __int8 *)a3 + 45), v20);
          if ( !result )
          {
LABEL_73:
            if ( (*(_BYTE *)a3 & 1) == 0 )
              goto LABEL_74;
            if ( a4 < 3 )
            {
              v15 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
              if ( a4 != 2 )
                v15 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
            }
            else
            {
              v15 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
            }
            result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"SinglePort", v15, *((unsigned __int16 *)a3 + 2), v20);
            if ( !result )
            {
LABEL_74:
              if ( (*(_BYTE *)a3 & 2) == 0 )
                goto LABEL_75;
              if ( a4 < 3 )
              {
                v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
                if ( a4 != 2 )
                  v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
              }
              else
              {
                v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
              }
              result = XcAddChildElementDWORD(
                         a1,
                         a2,
                         (OLECHAR *)L"PortRangeLow",
                         v16,
                         *((unsigned __int16 *)a3 + 3),
                         v20);
              if ( !result )
              {
LABEL_75:
                if ( (*(_BYTE *)a3 & 4) == 0 )
                  goto LABEL_76;
                if ( a4 < 3 )
                {
                  v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
                  if ( a4 != 2 )
                    v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
                }
                else
                {
                  v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
                }
                result = XcAddChildElementDWORD(
                           a1,
                           a2,
                           (OLECHAR *)L"PortRangeHigh",
                           v17,
                           *((unsigned __int16 *)a3 + 4),
                           v20);
                if ( !result )
                {
LABEL_76:
                  if ( (*(_BYTE *)a3 & 8) == 0 )
                    goto LABEL_77;
                  if ( a4 < 3 )
                  {
                    v18 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
                    if ( a4 != 2 )
                      v18 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
                  }
                  else
                  {
                    v18 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
                  }
                  result = XcAddChildElementDWORD(
                             a1,
                             a2,
                             (OLECHAR *)L"TypeofService",
                             v18,
                             *((unsigned __int16 *)a3 + 5),
                             v20);
                  if ( !result )
                  {
LABEL_77:
                    if ( (*(_BYTE *)a3 & 0x10) == 0 )
                      goto LABEL_78;
                    if ( a4 < 3 )
                    {
                      v19 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
                      if ( a4 != 2 )
                        v19 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
                    }
                    else
                    {
                      v19 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
                    }
                    result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"FlowLabel", v19, *((_DWORD *)a3 + 3), v20);
                    if ( !result )
                    {
LABEL_78:
                      if ( (*(_BYTE *)a3 & 0x20) == 0 )
                        return 0;
                      if ( a4 < 3 )
                      {
                        v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
                        if ( a4 != 2 )
                          v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
                      }
                      result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"IPSecType", v8, *((_DWORD *)a3 + 4), v20);
                      if ( !result )
                        return 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f854  mov     [rsp+arg_18], rbx
0x18000f859  push    rbp
0x18000f85a  push    rsi
0x18000f85b  push    rdi
0x18000f85c  push    r13
0x18000f85e  push    r14
0x18000f860  sub     rsp, 0B0h
0x18000f867  mov     rax, cs:__security_cookie
0x18000f86e  xor     rax, rsp
0x18000f871  mov     [rsp+0D8h+var_38], rax
0x18000f879  mov     edi, r9d
0x18000f87c  mov     rbx, r8
0x18000f87f  mov     r14, rdx
0x18000f882  mov     rbp, rcx
0x18000f885  mov     [rsp+0D8h+var_A8], 0
0x18000f88e  xor     edx, edx; Val
0x18000f890  lea     r8d, [rdx+5Ch]; Size
0x18000f894  lea     rcx, [rsp+0D8h+S]; void *
0x18000f899  call    memset_0
0x18000f89e  lea     rsi, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000f8a5  lea     r13, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000f8ac  test    byte ptr [rbx], 40h
0x18000f8af  jz      short loc_18000F909
0x18000f8b1  lea     rcx, [rbx+14h]; Addr
0x18000f8b5  lea     rdx, [rsp+0D8h+S]; S
0x18000f8ba  call    cs:__imp_RtlIpv4AddressToStringW
0x18000f8c0  cmp     edi, 3
0x18000f8c3  jb      short loc_18000F8CA
0x18000f8c5  mov     r9, rsi
0x18000f8c8  jmp     short loc_18000F8DB
0x18000f8ca  mov     r9, r13
0x18000f8cd  cmp     edi, 2
0x18000f8d0  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000f8d7  cmovnz  r9, rax; OLECHAR *
0x18000f8db  mov     [rsp+0D8h+var_B0], 0; struct IXMLDOMNode **
0x18000f8e4  lea     rax, [rsp+0D8h+S]
0x18000f8e9  mov     [rsp+0D8h+var_B8], rax; OLECHAR *
0x18000f8ee  lea     r8, aIpv4; "IPv4"
0x18000f8f5  mov     rdx, r14; struct IXMLDOMNode *
0x18000f8f8  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f8fb  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f900  test    eax, eax
0x18000f902  jz      short loc_18000F909
0x18000f904  jmp     loc_18000FBD9
0x18000f909  test    dword ptr [rbx], 200h
0x18000f90f  jz      short loc_18000F969
0x18000f911  lea     rcx, [rbx+18h]; Addr
0x18000f915  lea     rdx, [rsp+0D8h+S]; S
0x18000f91a  call    cs:__imp_RtlIpv4AddressToStringW
0x18000f920  cmp     edi, 3
0x18000f923  jb      short loc_18000F92A
0x18000f925  mov     r9, rsi
0x18000f928  jmp     short loc_18000F93B
0x18000f92a  mov     r9, r13
0x18000f92d  cmp     edi, 2
0x18000f930  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000f937  cmovnz  r9, rax; OLECHAR *
0x18000f93b  mov     [rsp+0D8h+var_B0], 0; struct IXMLDOMNode **
0x18000f944  lea     rax, [rsp+0D8h+S]
0x18000f949  mov     [rsp+0D8h+var_B8], rax; OLECHAR *
0x18000f94e  lea     r8, aIpv4maskfield; "IPv4MaskField"
0x18000f955  mov     rdx, r14; struct IXMLDOMNode *
0x18000f958  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f95b  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f960  test    eax, eax
0x18000f962  jz      short loc_18000F969
0x18000f964  jmp     loc_18000FBD9
0x18000f969  test    byte ptr [rbx], 80h
0x18000f96c  jz      short loc_18000F9C6
0x18000f96e  lea     rcx, [rbx+1Ch]; Addr
0x18000f972  lea     rdx, [rsp+0D8h+S]; S
0x18000f977  call    cs:__imp_RtlIpv6AddressToStringW
0x18000f97d  cmp     edi, 3
0x18000f980  jb      short loc_18000F987
0x18000f982  mov     r9, rsi
0x18000f985  jmp     short loc_18000F998
0x18000f987  mov     r9, r13
0x18000f98a  cmp     edi, 2
0x18000f98d  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000f994  cmovnz  r9, rax; OLECHAR *
0x18000f998  mov     [rsp+0D8h+var_B0], 0; struct IXMLDOMNode **
0x18000f9a1  lea     rax, [rsp+0D8h+S]
0x18000f9a6  mov     [rsp+0D8h+var_B8], rax; OLECHAR *
0x18000f9ab  lea     r8, aIpv6; "IPv6"
0x18000f9b2  mov     rdx, r14; struct IXMLDOMNode *
0x18000f9b5  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f9b8  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f9bd  test    eax, eax
0x18000f9bf  jz      short loc_18000F9C6
0x18000f9c1  jmp     loc_18000FBD9
0x18000f9c6  test    dword ptr [rbx], 400h
0x18000f9cc  jz      short loc_18000FA0C
0x18000f9ce  movzx   eax, byte ptr [rbx+2Ch]
0x18000f9d2  cmp     edi, 3
0x18000f9d5  jb      short loc_18000F9DC
0x18000f9d7  mov     r9, rsi
0x18000f9da  jmp     short loc_18000F9ED
0x18000f9dc  mov     r9, r13
0x18000f9df  cmp     edi, 2
0x18000f9e2  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000f9e9  cmovnz  r9, rcx; OLECHAR *
0x18000f9ed  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000f9f1  lea     r8, aIpv6prefixleng; "IPv6PreFixLength"
0x18000f9f8  mov     rdx, r14; struct IXMLDOMNode *
0x18000f9fb  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f9fe  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fa03  test    eax, eax
0x18000fa05  jz      short loc_18000FA0C
0x18000fa07  jmp     loc_18000FBD9
0x18000fa0c  test    dword ptr [rbx], 100h
0x18000fa12  jz      short loc_18000FA52
0x18000fa14  movzx   eax, byte ptr [rbx+2Dh]
0x18000fa18  cmp     edi, 3
0x18000fa1b  jb      short loc_18000FA22
0x18000fa1d  mov     r9, rsi
0x18000fa20  jmp     short loc_18000FA33
0x18000fa22  mov     r9, r13
0x18000fa25  cmp     edi, 2
0x18000fa28  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fa2f  cmovnz  r9, rcx; OLECHAR *
0x18000fa33  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000fa37  lea     r8, aProtocolid; "ProtocolId"
0x18000fa3e  mov     rdx, r14; struct IXMLDOMNode *
0x18000fa41  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000fa44  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fa49  test    eax, eax
0x18000fa4b  jz      short loc_18000FA52
0x18000fa4d  jmp     loc_18000FBD9
0x18000fa52  test    byte ptr [rbx], 1
0x18000fa55  jz      short loc_18000FA95
0x18000fa57  movzx   eax, word ptr [rbx+4]
0x18000fa5b  cmp     edi, 3
0x18000fa5e  jb      short loc_18000FA65
0x18000fa60  mov     r9, rsi
0x18000fa63  jmp     short loc_18000FA76
0x18000fa65  mov     r9, r13
0x18000fa68  cmp     edi, 2
0x18000fa6b  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fa72  cmovnz  r9, rcx; OLECHAR *
0x18000fa76  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000fa7a  lea     r8, aSingleport; "SinglePort"
0x18000fa81  mov     rdx, r14; struct IXMLDOMNode *
0x18000fa84  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000fa87  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fa8c  test    eax, eax
0x18000fa8e  jz      short loc_18000FA95
0x18000fa90  jmp     loc_18000FBD9
0x18000fa95  test    byte ptr [rbx], 2
0x18000fa98  jz      short loc_18000FAD8
0x18000fa9a  movzx   eax, word ptr [rbx+6]
0x18000fa9e  cmp     edi, 3
0x18000faa1  jb      short loc_18000FAA8
0x18000faa3  mov     r9, rsi
0x18000faa6  jmp     short loc_18000FAB9
0x18000faa8  mov     r9, r13
0x18000faab  cmp     edi, 2
0x18000faae  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fab5  cmovnz  r9, rcx; OLECHAR *
0x18000fab9  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000fabd  lea     r8, aPortrangelow; "PortRangeLow"
0x18000fac4  mov     rdx, r14; struct IXMLDOMNode *
0x18000fac7  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000faca  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000facf  test    eax, eax
0x18000fad1  jz      short loc_18000FAD8
0x18000fad3  jmp     loc_18000FBD9
0x18000fad8  test    byte ptr [rbx], 4
0x18000fadb  jz      short loc_18000FB1B
0x18000fadd  movzx   eax, word ptr [rbx+8]
0x18000fae1  cmp     edi, 3
0x18000fae4  jb      short loc_18000FAEB
0x18000fae6  mov     r9, rsi
0x18000fae9  jmp     short loc_18000FAFC
0x18000faeb  mov     r9, r13
0x18000faee  cmp     edi, 2
0x18000faf1  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000faf8  cmovnz  r9, rcx; OLECHAR *
0x18000fafc  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000fb00  lea     r8, aPortrangehigh; "PortRangeHigh"
0x18000fb07  mov     rdx, r14; struct IXMLDOMNode *
0x18000fb0a  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000fb0d  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fb12  test    eax, eax
0x18000fb14  jz      short loc_18000FB1B
0x18000fb16  jmp     loc_18000FBD9
0x18000fb1b  test    byte ptr [rbx], 8
0x18000fb1e  jz      short loc_18000FB5B
0x18000fb20  movzx   eax, word ptr [rbx+0Ah]
0x18000fb24  cmp     edi, 3
0x18000fb27  jb      short loc_18000FB2E
0x18000fb29  mov     r9, rsi
0x18000fb2c  jmp     short loc_18000FB3F
0x18000fb2e  mov     r9, r13
0x18000fb31  cmp     edi, 2
0x18000fb34  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fb3b  cmovnz  r9, rcx; OLECHAR *
0x18000fb3f  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000fb43  lea     r8, aTypeofservice; "TypeofService"
0x18000fb4a  mov     rdx, r14; struct IXMLDOMNode *
0x18000fb4d  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000fb50  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fb55  test    eax, eax
0x18000fb57  jz      short loc_18000FB5B
0x18000fb59  jmp     short loc_18000FBD9
0x18000fb5b  test    byte ptr [rbx], 10h
0x18000fb5e  jz      short loc_18000FB9A
0x18000fb60  mov     eax, [rbx+0Ch]
0x18000fb63  cmp     edi, 3
0x18000fb66  jb      short loc_18000FB6D
0x18000fb68  mov     r9, rsi
0x18000fb6b  jmp     short loc_18000FB7E
0x18000fb6d  mov     r9, r13
0x18000fb70  cmp     edi, 2
0x18000fb73  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fb7a  cmovnz  r9, rcx; OLECHAR *
0x18000fb7e  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000fb82  lea     r8, aFlowlabel; "FlowLabel"
0x18000fb89  mov     rdx, r14; struct IXMLDOMNode *
0x18000fb8c  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000fb8f  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fb94  test    eax, eax
0x18000fb96  jz      short loc_18000FB9A
0x18000fb98  jmp     short loc_18000FBD9
0x18000fb9a  test    byte ptr [rbx], 20h
0x18000fb9d  jz      short loc_18000FBD7
0x18000fb9f  mov     eax, [rbx+10h]
0x18000fba2  cmp     edi, 3
0x18000fba5  jnb     short loc_18000FBB8
0x18000fba7  mov     rsi, r13
0x18000fbaa  cmp     edi, 2
0x18000fbad  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000fbb4  cmovnz  rsi, rcx
0x18000fbb8  mov     dword ptr [rsp+0D8h+var_B8], eax; unsigned int
0x18000fbbc  mov     r9, rsi; OLECHAR *
0x18000fbbf  lea     r8, aIpsectype; "IPSecType"
0x18000fbc6  mov     rdx, r14; struct IXMLDOMNode *
0x18000fbc9  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000fbcc  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000fbd1  test    eax, eax
0x18000fbd3  jz      short loc_18000FBD7
0x18000fbd5  jmp     short loc_18000FBD9
0x18000fbd7  xor     eax, eax
0x18000fbd9  mov     rcx, [rsp+0D8h+var_38]
0x18000fbe1  xor     rcx, rsp; StackCookie
0x18000fbe4  call    __security_check_cookie
0x18000fbe9  mov     rbx, [rsp+0D8h+arg_18]
0x18000fbf1  add     rsp, 0B0h
0x18000fbf8  pop     r14
0x18000fbfa  pop     r13
0x18000fbfc  pop     rdi
0x18000fbfd  pop     rsi
0x18000fbfe  pop     rbp
0x18000fbff  retn
```
