# _parseTrafficDescriptor(IXMLDOMNode *,WWAN_PROFILE *,int,ulong)

- ea: `0x180011ba0`
- end: `0x180011eb1`
- name: `?_parseTrafficDescriptor@@YAKPEAUIXMLDOMNode@@PEAUWWAN_PROFILE@@HK@Z`
- size: `785`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct WWAN_PROFILE *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001670`
- `0x18000bbd8`
- `0x180011ba0`
- `0x180012968`
- `0x180012bc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180011c3d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180011c3d`

## string_xrefs

- `0x180011be2`: `MBNProfileV9:OSId`
- `0x180011bee`: `MBNProfileV4:OSId`
- `0x180011bf5`: `MBNProfile:OSId`
- `0x180011e34`: `MBNProfileV9:IPDescriptor`
- `0x180011e40`: `MBNProfileV4:IPDescriptor`
- `0x180011e47`: `MBNProfile:IPDescriptor`

## pseudocode

```c
unsigned int __fastcall _parseTrafficDescriptor(
        struct IXMLDOMNode *a1,
        struct WWAN_PROFILE *a2,
        __int64 a3,
        unsigned int a4)
{
  const unsigned __int16 *v7; // rdx
  int v8; // esi
  unsigned int result; // eax
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rdx
  int v16[4]; // [rsp+40h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-29h] BYREF

  v16[0] = 0;
  if ( a4 < 3 )
  {
    v7 = L"MBNProfileV4:OSId";
    if ( a4 != 2 )
      v7 = L"MBNProfile:OSId";
  }
  else
  {
    v7 = L"MBNProfileV9:OSId";
  }
  v8 = 1;
  result = XcGetNodeStringValue(a1, v7, sz, 0x28u, 1, 0, v16);
  if ( !result )
  {
    if ( v16[0] )
    {
      if ( IIDFromString(sz, (LPIID)a2 + 329) )
        return 1206;
      *((_DWORD *)a2 + 1314) |= 0x8000u;
    }
    if ( a4 < 3 )
    {
      v10 = L"MBNProfileV4:OSAppId";
      if ( a4 != 2 )
        v10 = L"MBNProfile:OSAppId";
    }
    else
    {
      v10 = L"MBNProfileV9:OSAppId";
    }
    result = XcGetNodeStringValue(a1, v10, (unsigned __int16 *)a2 + 2640, 0x80u, 1, 0, v16);
    if ( !result )
    {
      if ( v16[0] )
        *((_DWORD *)a2 + 1314) |= 0x800u;
      if ( a4 < 3 )
      {
        v11 = L"MBNProfileV4:MatchAllRule";
        if ( a4 != 2 )
          v11 = L"MBNProfile:MatchAllRule";
      }
      else
      {
        v11 = L"MBNProfileV9:MatchAllRule";
      }
      result = XcGetNodeEnumValue(
                 a1,
                 v11,
                 (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                 4u,
                 (unsigned int *)a2 + 1315,
                 1,
                 0,
                 v16);
      if ( !result )
      {
        if ( a4 < 3 )
        {
          v12 = L"MBNProfileV4:DNN";
          if ( a4 != 2 )
            v12 = L"MBNProfile:DNN";
        }
        else
        {
          v12 = L"MBNProfileV9:DNN";
        }
        result = XcGetNodeStringValue(a1, v12, (unsigned __int16 *)a2 + 2770, 0x65u, 1, 0, v16);
        if ( !result )
        {
          if ( v16[0] )
            *((_DWORD *)a2 + 1314) |= 0x1000u;
          if ( a4 < 3 )
          {
            v13 = L"MBNProfileV4:DestinationFQDN";
            if ( a4 != 2 )
              v13 = L"MBNProfile:DestinationFQDN";
          }
          else
          {
            v13 = L"MBNProfileV9:DestinationFQDN";
          }
          result = XcGetNodeStringValue(a1, v13, (unsigned __int16 *)a2 + 2871, 0x104u, 1, 0, v16);
          if ( !result )
          {
            if ( v16[0] )
              *((_DWORD *)a2 + 1314) |= 0x2000u;
            if ( a4 < 3 )
            {
              v14 = L"MBNProfileV4:ConnectionCapabilities";
              if ( a4 != 2 )
                v14 = L"MBNProfile:ConnectionCapabilities";
            }
            else
            {
              v14 = L"MBNProfileV9:ConnectionCapabilities";
            }
            result = _parseNode(
                       a1,
                       v14,
                       1,
                       (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))_parseConnectionCapabilities,
                       a2,
                       0,
                       a4);
            if ( !result )
            {
              if ( *((_DWORD *)a2 + 1384) )
                *((_DWORD *)a2 + 1314) |= 0x10000u;
              if ( a4 < 3 )
              {
                v15 = L"MBNProfileV4:IPDescriptor";
                if ( a4 != 2 )
                  v15 = L"MBNProfile:IPDescriptor";
              }
              else
              {
                v15 = L"MBNProfileV9:IPDescriptor";
              }
              result = _parseNode(
                         a1,
                         v15,
                         1,
                         (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))parseIPDescriptor,
                         a2,
                         0,
                         a4);
              if ( !*((_DWORD *)a2 + 1314) && !*((_DWORD *)a2 + 1315) )
                v8 = 0;
              *((_DWORD *)a2 + 1313) = v8;
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
0x180011ba0  mov     [rsp-8+arg_10], rbx
0x180011ba5  mov     [rsp-8+arg_18], rsi
0x180011baa  push    rbp
0x180011bab  push    rdi
0x180011bac  push    r12
0x180011bae  push    r14
0x180011bb0  push    r15
0x180011bb2  lea     rbp, [rsp-37h]
0x180011bb7  sub     rsp, 0B0h
0x180011bbe  mov     rax, cs:__security_cookie
0x180011bc5  xor     rax, rsp
0x180011bc8  mov     [rbp+57h+var_30], rax
0x180011bcc  xor     r12d, r12d
0x180011bcf  mov     edi, r9d
0x180011bd2  mov     [rbp+57h+var_90], r12d
0x180011bd6  mov     rbx, rdx
0x180011bd9  mov     r14, rcx
0x180011bdc  cmp     r9d, 3
0x180011be0  jb      short loc_180011BEB
0x180011be2  lea     rdx, aMbnprofilev9Os; "MBNProfileV9:OSId"
0x180011be9  jmp     short loc_180011C00
0x180011beb  cmp     edi, 2
0x180011bee  lea     rdx, aMbnprofilev4Os; "MBNProfileV4:OSId"
0x180011bf5  lea     rax, aMbnprofileOsid; "MBNProfile:OSId"
0x180011bfc  cmovnz  rdx, rax; unsigned __int16 *
0x180011c00  mov     esi, 1
0x180011c05  lea     rax, [rbp+57h+var_90]
0x180011c09  mov     [rsp+0D0h+var_A0], rax; int *
0x180011c0e  lea     r8, [rbp+57h+sz]; unsigned __int16 *
0x180011c12  mov     [rsp+0D0h+var_A8], r12; unsigned __int16 *
0x180011c17  mov     dword ptr [rsp+0D0h+var_B0], esi; int
0x180011c1b  lea     r9d, [rsi+27h]; unsigned __int64
0x180011c1f  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180011c24  test    eax, eax
0x180011c26  jnz     loc_180011E89
0x180011c2c  cmp     [rbp+57h+var_90], r12d
0x180011c30  jz      short loc_180011C59
0x180011c32  lea     rdx, [rbx+1490h]; lpiid
0x180011c39  lea     rcx, [rbp+57h+sz]; lpsz
0x180011c3d  call    cs:__imp_IIDFromString
0x180011c43  test    eax, eax
0x180011c45  jz      short loc_180011C51
0x180011c47  mov     eax, 4B6h
0x180011c4c  jmp     loc_180011E89
0x180011c51  bts     dword ptr [rbx+1488h], 0Fh
0x180011c59  lea     r8, [rbx+14A0h]; unsigned __int16 *
0x180011c60  cmp     edi, 3
0x180011c63  jb      short loc_180011C6E
0x180011c65  lea     rdx, aMbnprofilev9Os_0; "MBNProfileV9:OSAppId"
0x180011c6c  jmp     short loc_180011C83
0x180011c6e  cmp     edi, 2
0x180011c71  lea     rdx, aMbnprofilev4Os_0; "MBNProfileV4:OSAppId"
0x180011c78  lea     rax, aMbnprofileOsap; "MBNProfile:OSAppId"
0x180011c7f  cmovnz  rdx, rax; unsigned __int16 *
0x180011c83  lea     rax, [rbp+57h+var_90]
0x180011c87  mov     r9d, 80h; unsigned __int64
0x180011c8d  mov     [rsp+0D0h+var_A0], rax; int *
0x180011c92  mov     rcx, r14; struct IXMLDOMNode *
0x180011c95  mov     [rsp+0D0h+var_A8], r12; unsigned __int16 *
0x180011c9a  mov     dword ptr [rsp+0D0h+var_B0], esi; int
0x180011c9e  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180011ca3  test    eax, eax
0x180011ca5  jnz     loc_180011E89
0x180011cab  cmp     [rbp+57h+var_90], r12d
0x180011caf  jz      short loc_180011CB9
0x180011cb1  bts     dword ptr [rbx+1488h], 0Bh
0x180011cb9  lea     r15, [rbx+148Ch]
0x180011cc0  cmp     edi, 3
0x180011cc3  jb      short loc_180011CCE
0x180011cc5  lea     rdx, aMbnprofilev9Ma; "MBNProfileV9:MatchAllRule"
0x180011ccc  jmp     short loc_180011CE3
0x180011cce  cmp     edi, 2
0x180011cd1  lea     rdx, aMbnprofilev4Ma; "MBNProfileV4:MatchAllRule"
0x180011cd8  lea     rax, aMbnprofileMatc; "MBNProfile:MatchAllRule"
0x180011cdf  cmovnz  rdx, rax; unsigned __int16 *
0x180011ce3  lea     rax, [rbp+57h+var_90]
0x180011ce7  mov     r9d, 4; unsigned int
0x180011ced  mov     [rsp+0D0h+var_98], rax; int *
0x180011cf2  lea     r8, off_180015490; struct _XC_STRING_VALUE_MAPPING *
0x180011cf9  mov     dword ptr [rsp+0D0h+var_A0], r12d; unsigned int
0x180011cfe  mov     rcx, r14; struct IXMLDOMNode *
0x180011d01  mov     dword ptr [rsp+0D0h+var_A8], esi; int
0x180011d05  mov     [rsp+0D0h+var_B0], r15; unsigned int *
0x180011d0a  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x180011d0f  test    eax, eax
0x180011d11  jnz     loc_180011E89
0x180011d17  lea     r8, [rbx+15A4h]; unsigned __int16 *
0x180011d1e  cmp     edi, 3
0x180011d21  jb      short loc_180011D2C
0x180011d23  lea     rdx, aMbnprofilev9Dn; "MBNProfileV9:DNN"
0x180011d2a  jmp     short loc_180011D41
0x180011d2c  cmp     edi, 2
0x180011d2f  lea     rdx, aMbnprofilev4Dn_1; "MBNProfileV4:DNN"
0x180011d36  lea     rax, aMbnprofileDnn; "MBNProfile:DNN"
0x180011d3d  cmovnz  rdx, rax; unsigned __int16 *
0x180011d41  lea     rax, [rbp+57h+var_90]
0x180011d45  mov     r9d, 65h ; 'e'; unsigned __int64
0x180011d4b  mov     [rsp+0D0h+var_A0], rax; int *
0x180011d50  mov     rcx, r14; struct IXMLDOMNode *
0x180011d53  mov     [rsp+0D0h+var_A8], r12; unsigned __int16 *
0x180011d58  mov     dword ptr [rsp+0D0h+var_B0], esi; int
0x180011d5c  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180011d61  test    eax, eax
0x180011d63  jnz     loc_180011E89
0x180011d69  cmp     [rbp+57h+var_90], r12d
0x180011d6d  jz      short loc_180011D77
0x180011d6f  bts     dword ptr [rbx+1488h], 0Ch
0x180011d77  lea     r8, [rbx+166Eh]; unsigned __int16 *
0x180011d7e  cmp     edi, 3
0x180011d81  jb      short loc_180011D8C
0x180011d83  lea     rdx, aMbnprofilev9De_0; "MBNProfileV9:DestinationFQDN"
0x180011d8a  jmp     short loc_180011DA1
0x180011d8c  cmp     edi, 2
0x180011d8f  lea     rdx, aMbnprofilev4De_0; "MBNProfileV4:DestinationFQDN"
0x180011d96  lea     rax, aMbnprofileDest; "MBNProfile:DestinationFQDN"
0x180011d9d  cmovnz  rdx, rax; unsigned __int16 *
0x180011da1  lea     rax, [rbp+57h+var_90]
0x180011da5  mov     r9d, 104h; unsigned __int64
0x180011dab  mov     [rsp+0D0h+var_A0], rax; int *
0x180011db0  mov     rcx, r14; struct IXMLDOMNode *
0x180011db3  mov     [rsp+0D0h+var_A8], r12; unsigned __int16 *
0x180011db8  mov     dword ptr [rsp+0D0h+var_B0], esi; int
0x180011dbc  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180011dc1  test    eax, eax
0x180011dc3  jnz     loc_180011E89
0x180011dc9  cmp     [rbp+57h+var_90], r12d
0x180011dcd  jz      short loc_180011DD7
0x180011dcf  bts     dword ptr [rbx+1488h], 0Dh
0x180011dd7  cmp     edi, 3
0x180011dda  jb      short loc_180011DE5
0x180011ddc  lea     rdx, aMbnprofilev9Co; "MBNProfileV9:ConnectionCapabilities"
0x180011de3  jmp     short loc_180011DFA
0x180011de5  cmp     edi, 2
0x180011de8  lea     rdx, aMbnprofilev4Co; "MBNProfileV4:ConnectionCapabilities"
0x180011def  lea     rax, aMbnprofileConn_1; "MBNProfile:ConnectionCapabilities"
0x180011df6  cmovnz  rdx, rax; unsigned __int16 *
0x180011dfa  mov     dword ptr [rsp+0D0h+var_A0], edi; unsigned int
0x180011dfe  lea     r9, ?_parseConnectionCapabilities@@YAKPEAUIXMLDOMNode@@PEAUWWAN_PROFILE@@HK@Z; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x180011e05  mov     dword ptr [rsp+0D0h+var_A8], r12d; int
0x180011e0a  mov     r8d, esi; int
0x180011e0d  mov     rcx, r14; struct IXMLDOMNode *
0x180011e10  mov     [rsp+0D0h+var_B0], rbx; struct WWAN_PROFILE *
0x180011e15  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x180011e1a  test    eax, eax
0x180011e1c  jnz     short loc_180011E89
0x180011e1e  cmp     [rbx+15A0h], r12d
0x180011e25  jz      short loc_180011E2F
0x180011e27  bts     dword ptr [rbx+1488h], 10h
0x180011e2f  cmp     edi, 3
0x180011e32  jb      short loc_180011E3D
0x180011e34  lea     rdx, aMbnprofilev9Ip_3; "MBNProfileV9:IPDescriptor"
0x180011e3b  jmp     short loc_180011E52
0x180011e3d  cmp     edi, 2
0x180011e40  lea     rdx, aMbnprofilev4Ip_4; "MBNProfileV4:IPDescriptor"
0x180011e47  lea     rax, aMbnprofileIpde; "MBNProfile:IPDescriptor"
0x180011e4e  cmovnz  rdx, rax; unsigned __int16 *
0x180011e52  mov     dword ptr [rsp+0D0h+var_A0], edi; unsigned int
0x180011e56  lea     r9, _parseIPDescriptor; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x180011e5d  mov     dword ptr [rsp+0D0h+var_A8], r12d; int
0x180011e62  mov     r8d, esi; int
0x180011e65  mov     rcx, r14; struct IXMLDOMNode *
0x180011e68  mov     [rsp+0D0h+var_B0], rbx; struct WWAN_PROFILE *
0x180011e6d  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x180011e72  cmp     [rbx+1488h], r12d
0x180011e79  jnz     short loc_180011E83
0x180011e7b  cmp     [r15], r12d
0x180011e7e  jnz     short loc_180011E83
0x180011e80  mov     esi, r12d
0x180011e83  mov     [rbx+1484h], esi
0x180011e89  mov     rcx, [rbp+57h+var_30]
0x180011e8d  xor     rcx, rsp; StackCookie
0x180011e90  call    __security_check_cookie
0x180011e95  lea     r11, [rsp+0D0h+var_20]
0x180011e9d  mov     rbx, [r11+40h]
0x180011ea1  mov     rsi, [r11+48h]
0x180011ea5  mov     rsp, r11
0x180011ea8  pop     r15
0x180011eaa  pop     r14
0x180011eac  pop     r12
0x180011eae  pop     rdi
0x180011eaf  pop     rbp
0x180011eb0  retn
```
