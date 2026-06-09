# _parseIPDescriptor

- ea: `0x180010c60`
- end: `0x18001115c`
- name: `_parseIPDescriptor`
- size: `1276`
- prototype: `int __fastcall(struct IXMLDOMNode *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001670`
- `0x180002034`
- `0x180010c60`
- `0x18001288c`
- `0x180012bc8`

## import_xrefs

- `ntdll!RtlIpv6StringToAddressW` at `0x180010e17`
- `ntdll!RtlIpv6StringToAddressW` at `0x180010e17`
- `ntdll!RtlIpv4StringToAddressW` at `0x180010d1f`
- `ntdll!RtlIpv4StringToAddressW` at `0x180010d9c`
- `ntdll!RtlIpv4StringToAddressW` at `0x180010d1f`
- `ntdll!RtlIpv4StringToAddressW` at `0x180010d9c`

## string_xrefs

- `0x180010e95`: `MBNProfileV9:ProtocolId`
- `0x180010ea1`: `MBNProfileV4:ProtocolId`
- `0x180010ea8`: `MBNProfile:ProtocolId`
- `0x180011025`: `MBNProfileV9:TypeofService`
- `0x180011031`: `MBNProfileV4:TypeofService`
- `0x180011038`: `MBNProfile:TypeofService`

## pseudocode

```c
int __fastcall parseIPDescriptor(struct IXMLDOMNode *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  const unsigned __int16 *v7; // rdx
  int result; // eax
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdx
  __int64 v11; // r9
  const unsigned __int16 *v12; // rdx
  __int64 v13; // r9
  const unsigned __int16 *v14; // rdx
  __int64 v15; // r9
  const unsigned __int16 *v16; // rdx
  __int64 v17; // r9
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r9
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r9
  const unsigned __int16 *v22; // rdx
  __int64 v23; // r9
  const unsigned __int16 *v24; // rdx
  __int64 v25; // r9
  const unsigned __int16 *v26; // rdx
  int v27; // [rsp+40h] [rbp-69h] BYREF
  LPCWSTR Terminator; // [rsp+48h] [rbp-61h] BYREF
  WCHAR S[64]; // [rsp+50h] [rbp-59h] BYREF

  memset_0(S, 0, sizeof(S));
  *(_DWORD *)(a2 + 5256) |= 0x4000u;
  Terminator = 0;
  v27 = 0;
  if ( a4 < 3 )
  {
    v7 = L"MBNProfileV4:IPv4";
    if ( a4 != 2 )
      v7 = L"MBNProfile:IPv4";
  }
  else
  {
    v7 = L"MBNProfileV9:IPv4";
  }
  result = XcGetNodeStringValue(a1, v7, S, 0x40u, 1, 0, &v27);
  if ( !result )
  {
    if ( v27 )
    {
      result = RtlIpv4StringToAddressW(S, 1u, &Terminator, (struct in_addr *)(a2 + 6284));
      if ( result )
        return result;
      *(_DWORD *)(a2 + 6264) |= 0x40u;
    }
    if ( a4 < 3 )
    {
      v9 = L"MBNProfileV4:IPv4MaskField";
      if ( a4 != 2 )
        v9 = L"MBNProfile:IPv4MaskField";
    }
    else
    {
      v9 = L"MBNProfileV9:IPv4MaskField";
    }
    result = XcGetNodeStringValue(a1, v9, S, 0x40u, 1, 0, &v27);
    if ( !result )
    {
      if ( v27 )
      {
        result = RtlIpv4StringToAddressW(S, 1u, &Terminator, (struct in_addr *)(a2 + 6288));
        if ( result )
          return result;
        *(_DWORD *)(a2 + 6264) |= 0x200u;
      }
      if ( a4 < 3 )
      {
        v10 = L"MBNProfileV4:IPv6";
        if ( a4 != 2 )
          v10 = L"MBNProfile:IPv6";
      }
      else
      {
        v10 = L"MBNProfileV9:IPv6";
      }
      result = XcGetNodeStringValue(a1, v10, S, 0x40u, 1, 0, &v27);
      if ( !result )
      {
        if ( v27 )
        {
          result = RtlIpv6StringToAddressW(S, &Terminator, (struct in6_addr *)(a2 + 6292));
          if ( result )
            return result;
          *(_DWORD *)(a2 + 6264) |= 0x80u;
        }
        if ( a4 < 3 )
        {
          v12 = L"MBNProfileV4:IPv6PreFixLength";
          if ( a4 != 2 )
            v12 = L"MBNProfile:IPv6PreFixLength";
        }
        else
        {
          v12 = L"MBNProfileV9:IPv6PreFixLength";
        }
        result = XcGetNodeDWORDValue(a1, v12, (unsigned int *)(a2 + 6308), v11, 0xFFu, 1, 0, &v27);
        if ( !result )
        {
          if ( v27 )
            *(_DWORD *)(a2 + 6264) |= 0x400u;
          if ( a4 < 3 )
          {
            v14 = L"MBNProfileV4:ProtocolId";
            if ( a4 != 2 )
              v14 = L"MBNProfile:ProtocolId";
          }
          else
          {
            v14 = L"MBNProfileV9:ProtocolId";
          }
          result = XcGetNodeDWORDValue(a1, v14, (unsigned int *)(a2 + 6309), v13, 0xFFu, 1, 0, &v27);
          if ( !result )
          {
            if ( v27 )
              *(_DWORD *)(a2 + 6264) |= 0x100u;
            if ( a4 < 3 )
            {
              v16 = L"MBNProfileV4:SinglePort";
              if ( a4 != 2 )
                v16 = L"MBNProfile:SinglePort";
            }
            else
            {
              v16 = L"MBNProfileV9:SinglePort";
            }
            result = XcGetNodeDWORDValue(a1, v16, (unsigned int *)(a2 + 6268), v15, 0xFFFFu, 1, 0, &v27);
            if ( !result )
            {
              if ( v27 )
                *(_DWORD *)(a2 + 6264) |= 1u;
              if ( a4 < 3 )
              {
                v18 = L"MBNProfileV4:PortRangeLow";
                if ( a4 != 2 )
                  v18 = L"MBNProfile:PortRangeLow";
              }
              else
              {
                v18 = L"MBNProfileV9:PortRangeLow";
              }
              result = XcGetNodeDWORDValue(a1, v18, (unsigned int *)(a2 + 6270), v17, 0xFFFFu, 1, 0, &v27);
              if ( !result )
              {
                if ( v27 )
                  *(_DWORD *)(a2 + 6264) |= 2u;
                if ( a4 < 3 )
                {
                  v20 = L"MBNProfileV4:PortRangeHigh";
                  if ( a4 != 2 )
                    v20 = L"MBNProfile:PortRangeHigh";
                }
                else
                {
                  v20 = L"MBNProfileV9:PortRangeHigh";
                }
                result = XcGetNodeDWORDValue(a1, v20, (unsigned int *)(a2 + 6272), v19, 0xFFFFu, 1, 0, &v27);
                if ( !result )
                {
                  if ( v27 )
                    *(_DWORD *)(a2 + 6264) |= 4u;
                  if ( a4 < 3 )
                  {
                    v22 = L"MBNProfileV4:TypeofService";
                    if ( a4 != 2 )
                      v22 = L"MBNProfile:TypeofService";
                  }
                  else
                  {
                    v22 = L"MBNProfileV9:TypeofService";
                  }
                  result = XcGetNodeDWORDValue(a1, v22, (unsigned int *)(a2 + 6274), v21, 0xFFFFu, 1, 0, &v27);
                  if ( !result )
                  {
                    if ( v27 )
                      *(_DWORD *)(a2 + 6264) |= 8u;
                    if ( a4 < 3 )
                    {
                      v24 = L"MBNProfileV4:FlowLabel";
                      if ( a4 != 2 )
                        v24 = L"MBNProfile:FlowLabel";
                    }
                    else
                    {
                      v24 = L"MBNProfileV9:FlowLabel";
                    }
                    result = XcGetNodeDWORDValue(a1, v24, (unsigned int *)(a2 + 6276), v23, 0xFFFFFFu, 1, 0, &v27);
                    if ( !result )
                    {
                      if ( v27 )
                        *(_DWORD *)(a2 + 6264) |= 0x10u;
                      if ( a4 < 3 )
                      {
                        v26 = L"MBNProfileV4:IPSecType";
                        if ( a4 != 2 )
                          v26 = L"MBNProfile:IPSecType";
                      }
                      else
                      {
                        v26 = L"MBNProfileV9:IPSecType";
                      }
                      result = XcGetNodeDWORDValue(a1, v26, (unsigned int *)(a2 + 6280), v25, 0xFFFFFFFF, 1, 0, &v27);
                      if ( !result )
                      {
                        if ( v27 )
                          *(_DWORD *)(a2 + 6264) |= 0x20u;
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
  }
  return result;
}

```

## disassembly

```asm
0x180010c60  mov     [rsp-8+arg_10], rbx
0x180010c65  push    rbp
0x180010c66  push    rsi
0x180010c67  push    rdi
0x180010c68  push    r13
0x180010c6a  push    r14
0x180010c6c  lea     rbp, [rsp-37h]
0x180010c71  sub     rsp, 0E0h
0x180010c78  mov     rax, cs:__security_cookie
0x180010c7f  xor     rax, rsp
0x180010c82  mov     [rbp+57h+var_30], rax
0x180010c86  mov     rbx, rdx
0x180010c89  mov     rsi, rcx
0x180010c8c  xor     edx, edx; Val
0x180010c8e  lea     rcx, [rbp+57h+S]; void *
0x180010c92  mov     r8d, 80h; Size
0x180010c98  mov     edi, r9d
0x180010c9b  call    memset_0
0x180010ca0  bts     dword ptr [rbx+1488h], 0Eh
0x180010ca8  xor     r14d, r14d
0x180010cab  mov     [rbp+57h+Terminator], r14
0x180010caf  mov     [rbp+57h+var_C0], r14d
0x180010cb3  cmp     edi, 3
0x180010cb6  jb      short loc_180010CC1
0x180010cb8  lea     rdx, aMbnprofilev9Ip_0; "MBNProfileV9:IPv4"
0x180010cbf  jmp     short loc_180010CD6
0x180010cc1  cmp     edi, 2
0x180010cc4  lea     rdx, aMbnprofilev4Ip; "MBNProfileV4:IPv4"
0x180010ccb  lea     rax, aMbnprofileIpv4; "MBNProfile:IPv4"
0x180010cd2  cmovnz  rdx, rax; unsigned __int16 *
0x180010cd6  mov     r13d, 1
0x180010cdc  lea     rax, [rbp+57h+var_C0]
0x180010ce0  mov     [rsp+100h+var_D0], rax; int *
0x180010ce5  lea     r8, [rbp+57h+S]; unsigned __int16 *
0x180010ce9  mov     [rsp+100h+var_D8], r14; unsigned __int16 *
0x180010cee  mov     rcx, rsi; struct IXMLDOMNode *
0x180010cf1  mov     [rsp+100h+var_E0], r13d; int
0x180010cf6  lea     r9d, [r13+3Fh]; unsigned __int64
0x180010cfa  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180010cff  test    eax, eax
0x180010d01  jnz     loc_180011139
0x180010d07  cmp     [rbp+57h+var_C0], r14d
0x180010d0b  jz      short loc_180010D34
0x180010d0d  lea     r9, [rbx+188Ch]; Addr
0x180010d14  mov     dl, r13b; Strict
0x180010d17  lea     r8, [rbp+57h+Terminator]; Terminator
0x180010d1b  lea     rcx, [rbp+57h+S]; S
0x180010d1f  call    cs:__imp_RtlIpv4StringToAddressW
0x180010d25  test    eax, eax
0x180010d27  jnz     loc_180011139
0x180010d2d  or      dword ptr [rbx+1878h], 40h
0x180010d34  cmp     edi, 3
0x180010d37  jb      short loc_180010D42
0x180010d39  lea     rdx, aMbnprofilev9Ip; "MBNProfileV9:IPv4MaskField"
0x180010d40  jmp     short loc_180010D57
0x180010d42  cmp     edi, 2
0x180010d45  lea     rdx, aMbnprofilev4Ip_5; "MBNProfileV4:IPv4MaskField"
0x180010d4c  lea     rax, aMbnprofileIpv4_0; "MBNProfile:IPv4MaskField"
0x180010d53  cmovnz  rdx, rax; unsigned __int16 *
0x180010d57  lea     rax, [rbp+57h+var_C0]
0x180010d5b  mov     r9d, 40h ; '@'; unsigned __int64
0x180010d61  mov     [rsp+100h+var_D0], rax; int *
0x180010d66  lea     r8, [rbp+57h+S]; unsigned __int16 *
0x180010d6a  mov     [rsp+100h+var_D8], r14; unsigned __int16 *
0x180010d6f  mov     rcx, rsi; struct IXMLDOMNode *
0x180010d72  mov     [rsp+100h+var_E0], r13d; int
0x180010d77  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180010d7c  test    eax, eax
0x180010d7e  jnz     loc_180011139
0x180010d84  cmp     [rbp+57h+var_C0], r14d
0x180010d88  jz      short loc_180010DB2
0x180010d8a  lea     r9, [rbx+1890h]; Addr
0x180010d91  mov     dl, r13b; Strict
0x180010d94  lea     r8, [rbp+57h+Terminator]; Terminator
0x180010d98  lea     rcx, [rbp+57h+S]; S
0x180010d9c  call    cs:__imp_RtlIpv4StringToAddressW
0x180010da2  test    eax, eax
0x180010da4  jnz     loc_180011139
0x180010daa  bts     dword ptr [rbx+1878h], 9
0x180010db2  cmp     edi, 3
0x180010db5  jb      short loc_180010DC0
0x180010db7  lea     rdx, aMbnprofilev9Ip_4; "MBNProfileV9:IPv6"
0x180010dbe  jmp     short loc_180010DD5
0x180010dc0  cmp     edi, 2
0x180010dc3  lea     rdx, aMbnprofilev4Ip_0; "MBNProfileV4:IPv6"
0x180010dca  lea     rax, aMbnprofileIpv6_0; "MBNProfile:IPv6"
0x180010dd1  cmovnz  rdx, rax; unsigned __int16 *
0x180010dd5  lea     rax, [rbp+57h+var_C0]
0x180010dd9  mov     r9d, 40h ; '@'; unsigned __int64
0x180010ddf  mov     [rsp+100h+var_D0], rax; int *
0x180010de4  lea     r8, [rbp+57h+S]; unsigned __int16 *
0x180010de8  mov     [rsp+100h+var_D8], r14; unsigned __int16 *
0x180010ded  mov     rcx, rsi; struct IXMLDOMNode *
0x180010df0  mov     [rsp+100h+var_E0], r13d; int
0x180010df5  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180010dfa  test    eax, eax
0x180010dfc  jnz     loc_180011139
0x180010e02  cmp     [rbp+57h+var_C0], r14d
0x180010e06  jz      short loc_180010E2D
0x180010e08  lea     r8, [rbx+1894h]; Addr
0x180010e0f  lea     rdx, [rbp+57h+Terminator]; Terminator
0x180010e13  lea     rcx, [rbp+57h+S]; S
0x180010e17  call    cs:__imp_RtlIpv6StringToAddressW
0x180010e1d  test    eax, eax
0x180010e1f  jnz     loc_180011139
0x180010e25  bts     dword ptr [rbx+1878h], 7
0x180010e2d  cmp     edi, 3
0x180010e30  jb      short loc_180010E3B
0x180010e32  lea     rdx, aMbnprofilev9Ip_2; "MBNProfileV9:IPv6PreFixLength"
0x180010e39  jmp     short loc_180010E50
0x180010e3b  cmp     edi, 2
0x180010e3e  lea     rdx, aMbnprofilev4Ip_3; "MBNProfileV4:IPv6PreFixLength"
0x180010e45  lea     rax, aMbnprofileIpv6; "MBNProfile:IPv6PreFixLength"
0x180010e4c  cmovnz  rdx, rax; unsigned __int16 *
0x180010e50  lea     rax, [rbp+57h+var_C0]
0x180010e54  mov     rcx, rsi; struct IXMLDOMNode *
0x180010e57  mov     [rsp+100h+var_C8], rax; int *
0x180010e5c  lea     r8, [rbx+18A4h]; unsigned int *
0x180010e63  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x180010e68  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x180010e6d  mov     [rsp+100h+var_E0], 0FFh; unsigned int
0x180010e75  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180010e7a  test    eax, eax
0x180010e7c  jnz     loc_180011139
0x180010e82  cmp     [rbp+57h+var_C0], r14d
0x180010e86  jz      short loc_180010E90
0x180010e88  bts     dword ptr [rbx+1878h], 0Ah
0x180010e90  cmp     edi, 3
0x180010e93  jb      short loc_180010E9E
0x180010e95  lea     rdx, aMbnprofilev9Pr_3; "MBNProfileV9:ProtocolId"
0x180010e9c  jmp     short loc_180010EB3
0x180010e9e  cmp     edi, 2
0x180010ea1  lea     rdx, aMbnprofilev4Pr_3; "MBNProfileV4:ProtocolId"
0x180010ea8  lea     rax, aMbnprofileProt; "MBNProfile:ProtocolId"
0x180010eaf  cmovnz  rdx, rax; unsigned __int16 *
0x180010eb3  lea     rax, [rbp+57h+var_C0]
0x180010eb7  mov     rcx, rsi; struct IXMLDOMNode *
0x180010eba  mov     [rsp+100h+var_C8], rax; int *
0x180010ebf  lea     r8, [rbx+18A5h]; unsigned int *
0x180010ec6  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x180010ecb  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x180010ed0  mov     [rsp+100h+var_E0], 0FFh; unsigned int
0x180010ed8  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180010edd  test    eax, eax
0x180010edf  jnz     loc_180011139
0x180010ee5  cmp     [rbp+57h+var_C0], r14d
0x180010ee9  jz      short loc_180010EF3
0x180010eeb  bts     dword ptr [rbx+1878h], 8
0x180010ef3  cmp     edi, 3
0x180010ef6  jb      short loc_180010F01
0x180010ef8  lea     rdx, aMbnprofilev9Si_0; "MBNProfileV9:SinglePort"
0x180010eff  jmp     short loc_180010F16
0x180010f01  cmp     edi, 2
0x180010f04  lea     rdx, aMbnprofilev4Si_0; "MBNProfileV4:SinglePort"
0x180010f0b  lea     rax, aMbnprofileSing; "MBNProfile:SinglePort"
0x180010f12  cmovnz  rdx, rax; unsigned __int16 *
0x180010f16  lea     rax, [rbp+57h+var_C0]
0x180010f1a  mov     rcx, rsi; struct IXMLDOMNode *
0x180010f1d  mov     [rsp+100h+var_C8], rax; int *
0x180010f22  lea     r8, [rbx+187Ch]; unsigned int *
0x180010f29  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x180010f2e  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x180010f33  mov     [rsp+100h+var_E0], 0FFFFh; unsigned int
0x180010f3b  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180010f40  test    eax, eax
0x180010f42  jnz     loc_180011139
0x180010f48  cmp     [rbp+57h+var_C0], r14d
0x180010f4c  jz      short loc_180010F55
0x180010f4e  or      [rbx+1878h], r13d
0x180010f55  cmp     edi, 3
0x180010f58  jb      short loc_180010F63
0x180010f5a  lea     rdx, aMbnprofilev9Po_0; "MBNProfileV9:PortRangeLow"
0x180010f61  jmp     short loc_180010F78
0x180010f63  cmp     edi, 2
0x180010f66  lea     rdx, aMbnprofilev4Po; "MBNProfileV4:PortRangeLow"
0x180010f6d  lea     rax, aMbnprofilePort_0; "MBNProfile:PortRangeLow"
0x180010f74  cmovnz  rdx, rax; unsigned __int16 *
0x180010f78  lea     rax, [rbp+57h+var_C0]
0x180010f7c  mov     rcx, rsi; struct IXMLDOMNode *
0x180010f7f  mov     [rsp+100h+var_C8], rax; int *
0x180010f84  lea     r8, [rbx+187Eh]; unsigned int *
0x180010f8b  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x180010f90  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x180010f95  mov     [rsp+100h+var_E0], 0FFFFh; unsigned int
0x180010f9d  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180010fa2  test    eax, eax
0x180010fa4  jnz     loc_180011139
0x180010faa  cmp     [rbp+57h+var_C0], r14d
0x180010fae  jz      short loc_180010FB7
0x180010fb0  or      dword ptr [rbx+1878h], 2
0x180010fb7  lea     r8, [rbx+1880h]; unsigned int *
0x180010fbe  cmp     edi, 3
0x180010fc1  jb      short loc_180010FCC
0x180010fc3  lea     rdx, aMbnprofilev9Po; "MBNProfileV9:PortRangeHigh"
0x180010fca  jmp     short loc_180010FE1
0x180010fcc  cmp     edi, 2
0x180010fcf  lea     rdx, aMbnprofilev4Po_0; "MBNProfileV4:PortRangeHigh"
0x180010fd6  lea     rax, aMbnprofilePort; "MBNProfile:PortRangeHigh"
0x180010fdd  cmovnz  rdx, rax; unsigned __int16 *
0x180010fe1  lea     rax, [rbp+57h+var_C0]
0x180010fe5  mov     rcx, rsi; struct IXMLDOMNode *
0x180010fe8  mov     [rsp+100h+var_C8], rax; int *
0x180010fed  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x180010ff2  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x180010ff7  mov     [rsp+100h+var_E0], 0FFFFh; unsigned int
0x180010fff  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180011004  test    eax, eax
0x180011006  jnz     loc_180011139
0x18001100c  cmp     [rbp+57h+var_C0], r14d
0x180011010  jz      short loc_180011019
0x180011012  or      dword ptr [rbx+1878h], 4
0x180011019  lea     r8, [rbx+1882h]; unsigned int *
0x180011020  cmp     edi, 3
0x180011023  jb      short loc_18001102E
0x180011025  lea     rdx, aMbnprofilev9Ty; "MBNProfileV9:TypeofService"
0x18001102c  jmp     short loc_180011043
0x18001102e  cmp     edi, 2
0x180011031  lea     rdx, aMbnprofilev4Ty; "MBNProfileV4:TypeofService"
0x180011038  lea     rax, aMbnprofileType; "MBNProfile:TypeofService"
0x18001103f  cmovnz  rdx, rax; unsigned __int16 *
0x180011043  lea     rax, [rbp+57h+var_C0]
0x180011047  mov     rcx, rsi; struct IXMLDOMNode *
0x18001104a  mov     [rsp+100h+var_C8], rax; int *
0x18001104f  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x180011054  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x180011059  mov     [rsp+100h+var_E0], 0FFFFh; unsigned int
0x180011061  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180011066  test    eax, eax
0x180011068  jnz     loc_180011139
0x18001106e  cmp     [rbp+57h+var_C0], r14d
0x180011072  jz      short loc_18001107B
0x180011074  or      dword ptr [rbx+1878h], 8
0x18001107b  lea     r8, [rbx+1884h]; unsigned int *
0x180011082  cmp     edi, 3
0x180011085  jb      short loc_180011090
0x180011087  lea     rdx, aMbnprofilev9Fl; "MBNProfileV9:FlowLabel"
0x18001108e  jmp     short loc_1800110A5
0x180011090  cmp     edi, 2
0x180011093  lea     rdx, aMbnprofilev4Fl; "MBNProfileV4:FlowLabel"
0x18001109a  lea     rax, aMbnprofileFlow; "MBNProfile:FlowLabel"
0x1800110a1  cmovnz  rdx, rax; unsigned __int16 *
0x1800110a5  lea     rax, [rbp+57h+var_C0]
0x1800110a9  mov     rcx, rsi; struct IXMLDOMNode *
0x1800110ac  mov     [rsp+100h+var_C8], rax; int *
0x1800110b1  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x1800110b6  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x1800110bb  mov     [rsp+100h+var_E0], 0FFFFFFh; unsigned int
0x1800110c3  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x1800110c8  test    eax, eax
0x1800110ca  jnz     short loc_180011139
0x1800110cc  cmp     [rbp+57h+var_C0], r14d
0x1800110d0  jz      short loc_1800110D9
0x1800110d2  or      dword ptr [rbx+1878h], 10h
0x1800110d9  lea     r8, [rbx+1888h]; unsigned int *
0x1800110e0  cmp     edi, 3
0x1800110e3  jb      short loc_1800110EE
0x1800110e5  lea     rdx, aMbnprofilev9Ip_1; "MBNProfileV9:IPSecType"
0x1800110ec  jmp     short loc_180011103
0x1800110ee  cmp     edi, 2
0x1800110f1  lea     rdx, aMbnprofilev4Ip_1; "MBNProfileV4:IPSecType"
0x1800110f8  lea     rax, aMbnprofileIpse; "MBNProfile:IPSecType"
0x1800110ff  cmovnz  rdx, rax; unsigned __int16 *
0x180011103  lea     rax, [rbp+57h+var_C0]
0x180011107  mov     rcx, rsi; struct IXMLDOMNode *
0x18001110a  mov     [rsp+100h+var_C8], rax; int *
0x18001110f  mov     dword ptr [rsp+100h+var_D0], r14d; unsigned int
0x180011114  mov     dword ptr [rsp+100h+var_D8], r13d; int
0x180011119  mov     [rsp+100h+var_E0], 0FFFFFFFFh; unsigned int
0x180011121  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180011126  test    eax, eax
0x180011128  jnz     short loc_180011139
0x18001112a  cmp     [rbp+57h+var_C0], r14d
0x18001112e  jz      short loc_180011137
0x180011130  or      dword ptr [rbx+1878h], 20h
0x180011137  xor     eax, eax
0x180011139  mov     rcx, [rbp+57h+var_30]
0x18001113d  xor     rcx, rsp; StackCookie
0x180011140  call    __security_check_cookie
0x180011145  mov     rbx, [rsp+100h+arg_10]
0x18001114d  add     rsp, 0E0h
0x180011154  pop     r14
0x180011156  pop     r13
0x180011158  pop     rdi
0x180011159  pop     rsi
0x18001115a  pop     rbp
0x18001115b  retn
```
