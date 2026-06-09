# OpenPortOrAuthAppAddrToStringInt3

- ea: `0x18000c310`
- end: `0x18000cfdf`
- name: `OpenPortOrAuthAppAddrToStringInt3`
- size: `3279`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c2d0`
- `0x18000dc90`
- `0x180023d40`
- `0x180037a7c`

## callees

- `0x1800042c4`
- `0x18000c310`
- `0x18000cff0`
- `0x18001e9ac`
- `0x18001f650`
- `0x18001ffd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000cd1a`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18000cd1a`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000c4f7`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000c51a`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000cce6`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000cd36`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000c4f7`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000c51a`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000cce6`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000cd36`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c664`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c683`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000ce71`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c664`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c683`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000ce71`
- `WS2_32!__imp_htonl` at `0x18000c4e6`
- `WS2_32!__imp_htonl` at `0x18000c506`
- `WS2_32!__imp_htonl` at `0x18000ccd5`
- `WS2_32!__imp_htonl` at `0x18000cd22`
- `WS2_32!__imp_htonl` at `0x18000c4e6`
- `WS2_32!__imp_htonl` at `0x18000c506`
- `WS2_32!__imp_htonl` at `0x18000ccd5`
- `WS2_32!__imp_htonl` at `0x18000cd22`
- `fwbase!FwIcfIpV4SubNetsCanonize` at `0x18000c3d1`
- `fwbase!FwIcfIpV4SubNetsCanonize` at `0x18000c3d1`
- `fwbase!FwIcfIpV6SubNetsCanonize` at `0x18000c3f7`
- `fwbase!FwIcfIpV6SubNetsCanonize` at `0x18000c3f7`

## pseudocode

```c
__int64 __fastcall OpenPortOrAuthAppAddrToStringInt3(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        int a4,
        unsigned int a5,
        int a6,
        unsigned __int16 **a7,
        unsigned __int64 *a8)
{
  bool v12; // zf
  unsigned __int16 *v13; // r15
  size_t v14; // rsi
  int v15; // r14d
  __int64 v16; // r12
  __int64 v17; // rdi
  __int64 v18; // r12
  unsigned int j; // edi
  unsigned __int16 *v20; // r15
  unsigned __int64 v21; // rsi
  __int64 v23; // r14
  LPCOLESTR v24; // rcx
  __int64 v25; // rdx
  unsigned __int16 *v26; // rdi
  unsigned __int64 v27; // rbx
  u_long v28; // ecx
  unsigned int i; // eax
  _QWORD *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v35; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v37; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v38; // [rsp+78h] [rbp-88h]
  _DWORD v39[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  __int128 v41; // [rsp+90h] [rbp-70h] BYREF
  struct in_addr Addr; // [rsp+A0h] [rbp-60h] BYREF
  struct in6_addr v43; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR S[120]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v45[120]; // [rsp+1B0h] [rbp+B0h] BYREF

  v37 = a7;
  v38 = a8;
  v35 = a3;
  v36 = a2;
  *(_WORD *)&Addr.S_un.S_un_b.s_b2 = 0;
  Addr.S_un.S_un_b.s_b4 = 0;
  v43.u.Byte[0] = 0;
  *(_QWORD *)&v43.u.Byte[1] = 0;
  *(_DWORD *)((char *)&v43.u.Word[4] + 1) = 0;
  *(USHORT *)((char *)&v43.u.Word[6] + 1) = 0;
  v43.u.Byte[15] = 0;
  Addr.S_un.S_un_b.s_b1 = 0;
  memset_0(S, 0, 0xE4u);
  memset_0(v45, 0, 0xE4u);
  v39[0] = *(_DWORD *)(a1 + 8);
  v40 = *(_QWORD *)(a1 + 16);
  v39[1] = 0;
  v41 = 0;
  FwIcfIpV4SubNetsCanonize(v39);
  *(_DWORD *)(a1 + 8) = v39[0];
  *(_QWORD *)(a1 + 16) = v40;
  LODWORD(v41) = *(_DWORD *)(a1 + 40);
  *((_QWORD *)&v41 + 1) = *(_QWORD *)(a1 + 48);
  FwIcfIpV6SubNetsCanonize(&v41);
  v12 = (*(_BYTE *)a1 & 1) == 0;
  v13 = a2;
  *(_DWORD *)(a1 + 40) = v41;
  v14 = a3;
  *(_QWORD *)(a1 + 48) = *((_QWORD *)&v41 + 1);
  v33 = a2;
  v34 = a3;
  if ( !v12 || (*(_BYTE *)(a1 + 4) & 1) != 0 )
  {
    v15 = StringCchPrintfExW(
            a2,
            a3,
            &v33,
            &v34,
            0x800u,
            (wchar_t *)L"%s%s",
            L"LocalSubnet",
            &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 177;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  else
  {
    v15 = 0;
  }
  if ( (*(_BYTE *)a1 & 2) != 0 || (*(_BYTE *)(a1 + 4) & 2) != 0 )
  {
    v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s%s", L"DNS", &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 178;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  if ( (*(_BYTE *)a1 & 4) != 0 || (*(_BYTE *)(a1 + 4) & 4) != 0 )
  {
    v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s%s", L"DHCP", &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 179;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  if ( (*(_BYTE *)a1 & 8) != 0 || (*(_BYTE *)(a1 + 4) & 8) != 0 )
  {
    v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s%s", L"WINS", &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 180;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  if ( (*(_BYTE *)a1 & 0x10) != 0 || (*(_BYTE *)(a1 + 4) & 0x10) != 0 )
  {
    v15 = StringCchPrintfExW(
            v13,
            v14,
            &v33,
            &v34,
            0x800u,
            (wchar_t *)L"%s%s",
            L"DefaultGateway",
            &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 >= 0 )
    {
      v13 = v33;
      v14 = v34;
      goto LABEL_12;
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return (unsigned int)v15;
    v25 = 181;
LABEL_51:
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v15);
    return (unsigned int)v15;
  }
LABEL_12:
  if ( a5 < 0x214 )
    goto LABEL_13;
  if ( (*(_BYTE *)a1 & 0x20) != 0 || (*(_BYTE *)(a1 + 4) & 0x20) != 0 )
  {
    v15 = StringCchPrintfExW(
            v13,
            v14,
            &v33,
            &v34,
            0x800u,
            (wchar_t *)L"%s%s",
            L"IntrAnet",
            &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 182;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  if ( (*(_BYTE *)a1 & 0x40) != 0 || (*(_BYTE *)(a1 + 4) & 0x40) != 0 )
  {
    v15 = StringCchPrintfExW(
            v13,
            v14,
            &v33,
            &v34,
            0x800u,
            (wchar_t *)L"%s%s",
            L"IntErnet",
            &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 183;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  if ( *(char *)a1 < 0 || *(char *)(a1 + 4) < 0 )
  {
    v15 = StringCchPrintfExW(
            v13,
            v14,
            &v33,
            &v34,
            0x800u,
            (wchar_t *)L"%s%s",
            L"Ply2Renders",
            &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 184;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  if ( (*(_DWORD *)a1 & 0x100) == 0 && (*(_DWORD *)(a1 + 4) & 0x100) == 0 )
    goto LABEL_13;
  v15 = StringCchPrintfExW(
          v13,
          v14,
          &v33,
          &v34,
          0x800u,
          (wchar_t *)L"%s%s",
          L"RmtIntrAnet",
          &WF_ADDR_TOKEN_DELIMITER_STR);
  if ( v15 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return (unsigned int)v15;
    v25 = 185;
    goto LABEL_51;
  }
  v13 = v33;
  v14 = v34;
LABEL_13:
  if ( a5 >= 0x21E && ((*(_DWORD *)a1 & 0x200) != 0 || (*(_DWORD *)(a1 + 4) & 0x200) != 0) )
  {
    v15 = StringCchPrintfExW(
            v13,
            v14,
            &v33,
            &v34,
            0x800u,
            (wchar_t *)L"%s%s",
            L"CaptivePortal",
            &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 186;
      goto LABEL_51;
    }
    v13 = v33;
    v14 = v34;
  }
  v16 = 0;
  while ( (unsigned int)v16 < *(_DWORD *)(a1 + 8) )
  {
    Addr = (struct in_addr)htonl(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 8 * v16));
    RtlIpv4AddressToStringW(&Addr, S);
    v28 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 8 * v16 + 4);
    if ( a4 )
    {
      for ( i = 0; v28; v28 *= 2 )
        ++i;
      _o__ultow_s(i, v45, 114, 10);
    }
    else
    {
      Addr = (struct in_addr)htonl(v28);
      RtlIpv4AddressToStringW(&Addr, v45);
    }
    v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s/%s%s", S, v45, &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 187;
      goto LABEL_51;
    }
    v13 = v33;
    v16 = (unsigned int)(v16 + 1);
    v14 = v34;
  }
  v17 = 0;
  while ( (unsigned int)v17 < *(_DWORD *)(a1 + 24) )
  {
    Addr = (struct in_addr)htonl(*(_DWORD *)(*(_QWORD *)(a1 + 32) + 8 * v17));
    RtlIpv4AddressToStringW(&Addr, S);
    Addr = (struct in_addr)htonl(*(_DWORD *)(*(_QWORD *)(a1 + 32) + 8 * v17 + 4));
    RtlIpv4AddressToStringW(&Addr, v45);
    if ( a6 || *(_DWORD *)(*(_QWORD *)(a1 + 32) + 8 * v17) != *(_DWORD *)(*(_QWORD *)(a1 + 32) + 8 * v17 + 4) )
    {
      v15 = StringCchPrintfExW(
              v13,
              v14,
              &v33,
              &v34,
              0x800u,
              (wchar_t *)L"%s-%s%s",
              S,
              v45,
              &WF_ADDR_TOKEN_DELIMITER_STR);
      if ( v15 < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return (unsigned int)v15;
        v25 = 189;
        goto LABEL_51;
      }
    }
    else
    {
      v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s%s", S, &WF_ADDR_TOKEN_DELIMITER_STR);
      if ( v15 < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return (unsigned int)v15;
        v25 = 188;
        goto LABEL_51;
      }
    }
    v13 = v33;
    v17 = (unsigned int)(v17 + 1);
    v14 = v34;
  }
  v18 = 0;
  while ( (unsigned int)v18 < *(_DWORD *)(a1 + 40) )
  {
    v43 = *(struct in6_addr *)(*(_QWORD *)(a1 + 48) + 20 * v18);
    RtlIpv6AddressToStringW(&v43, S);
    LODWORD(v32) = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 20 * v18 + 16);
    v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s/%d%s", S, v32, &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return (unsigned int)v15;
      v25 = 190;
      goto LABEL_51;
    }
    v13 = v33;
    v18 = (unsigned int)(v18 + 1);
    v14 = v34;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= *(_DWORD *)(a1 + 56) )
    {
      if ( v35 == v14 )
      {
        v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s", L"*");
        if ( v15 < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v25 = 193;
            goto LABEL_51;
          }
          return (unsigned int)v15;
        }
        v20 = v33;
        v21 = v34;
      }
      else
      {
        v26 = v36;
        v27 = v35 - v14;
        if ( v36[v35 - v14 - 1] != 44 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v20 = v13 - 1;
        v26[v27 - 1] = 0;
        v21 = v14 + 1;
      }
      if ( v37 )
        *v37 = v20;
      if ( v38 )
        *v38 = v21;
      return (unsigned int)v15;
    }
    v23 = 32LL * j;
    v43 = *(struct in6_addr *)(*(_QWORD *)(a1 + 64) + v23);
    RtlIpv6AddressToStringW(&v43, S);
    v43 = *(struct in6_addr *)(*(_QWORD *)(a1 + 64) + v23 + 16);
    RtlIpv6AddressToStringW(&v43, v45);
    if ( a6 )
      break;
    v30 = (_QWORD *)(v23 + *(_QWORD *)(a1 + 64));
    v31 = *v30 - v30[2];
    if ( *v30 == v30[2] )
      v31 = v30[1] - v30[3];
    if ( v31 )
      break;
    v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s%s", S, &WF_ADDR_TOKEN_DELIMITER_STR);
    if ( v15 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v25 = 191;
        goto LABEL_51;
      }
      return (unsigned int)v15;
    }
LABEL_35:
    v13 = v33;
    v14 = v34;
  }
  v15 = StringCchPrintfExW(v13, v14, &v33, &v34, 0x800u, (wchar_t *)L"%s-%s%s", S, v45, &WF_ADDR_TOKEN_DELIMITER_STR);
  if ( v15 >= 0 )
    goto LABEL_35;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v25 = 192;
    goto LABEL_51;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000c310  mov     [rsp-8+arg_18], rbx
0x18000c315  push    rbp
0x18000c316  push    rsi
0x18000c317  push    rdi
0x18000c318  push    r12
0x18000c31a  push    r13
0x18000c31c  push    r14
0x18000c31e  push    r15
0x18000c320  lea     rbp, [rsp-1B0h]
0x18000c328  sub     rsp, 2B0h
0x18000c32f  mov     rax, cs:__security_cookie
0x18000c336  xor     rax, rsp
0x18000c339  mov     [rbp+1E0h+var_40], rax
0x18000c340  mov     rax, [rbp+1E0h+arg_30]
0x18000c347  mov     r14, r8
0x18000c34a  mov     [rsp+2E0h+var_270], rax
0x18000c34f  mov     r12, rdx
0x18000c352  mov     rax, [rbp+1E0h+arg_38]
0x18000c359  mov     rbx, rcx
0x18000c35c  mov     [rsp+2E0h+var_268], rax
0x18000c361  lea     rcx, [rbp+1E0h+S]; void *
0x18000c365  xor     eax, eax
0x18000c367  mov     [rsp+2E0h+var_280], r8
0x18000c36c  mov     [rsp+2E0h+var_278], rdx
0x18000c371  mov     r8d, 0E4h; Size
0x18000c377  xor     edx, edx; Val
0x18000c379  mov     word ptr [rbp+1E0h+Addr.S_un+1], ax
0x18000c37d  mov     byte ptr [rbp+1E0h+Addr.S_un+3], al
0x18000c380  mov     r13d, r9d
0x18000c383  mov     byte ptr [rbp+1E0h+var_238.u], al
0x18000c386  mov     qword ptr [rbp+1E0h+var_238.u+1], rax
0x18000c38a  mov     dword ptr [rbp+1E0h+var_238.u+9], eax
0x18000c38d  mov     word ptr [rbp+1E0h+var_238.u+0Dh], ax
0x18000c391  mov     byte ptr [rbp+1E0h+var_238.u+0Fh], al
0x18000c394  mov     byte ptr [rbp+1E0h+Addr.S_un], 0
0x18000c398  call    memset_0
0x18000c39d  xor     edx, edx; Val
0x18000c39f  lea     rcx, [rbp+1E0h+var_130]; void *
0x18000c3a6  mov     r8d, 0E4h; Size
0x18000c3ac  call    memset_0
0x18000c3b1  mov     eax, [rbx+8]
0x18000c3b4  lea     rcx, [rbp+1E0h+var_260]
0x18000c3b8  mov     [rbp+1E0h+var_260], eax
0x18000c3bb  xorps   xmm0, xmm0
0x18000c3be  mov     rax, [rbx+10h]
0x18000c3c2  mov     [rbp+1E0h+var_258], rax
0x18000c3c6  mov     [rbp+1E0h+var_25C], 0
0x18000c3cd  movups  [rbp+1E0h+var_250], xmm0
0x18000c3d1  call    cs:__imp_FwIcfIpV4SubNetsCanonize
0x18000c3d7  mov     eax, [rbp+1E0h+var_260]
0x18000c3da  lea     rcx, [rbp+1E0h+var_250]
0x18000c3de  mov     [rbx+8], eax
0x18000c3e1  mov     rax, [rbp+1E0h+var_258]
0x18000c3e5  mov     [rbx+10h], rax
0x18000c3e9  mov     eax, [rbx+28h]
0x18000c3ec  mov     dword ptr [rbp+1E0h+var_250], eax
0x18000c3ef  mov     rax, [rbx+30h]
0x18000c3f3  mov     qword ptr [rbp+1E0h+var_250+8], rax
0x18000c3f7  call    cs:__imp_FwIcfIpV6SubNetsCanonize
0x18000c3fd  test    byte ptr [rbx], 1
0x18000c400  lea     rcx, aSS_0; "%s%s"
0x18000c407  mov     eax, dword ptr [rbp+1E0h+var_250]
0x18000c40a  mov     r15, r12
0x18000c40d  mov     [rbx+28h], eax
0x18000c410  mov     rsi, r14
0x18000c413  mov     rax, qword ptr [rbp+1E0h+var_250+8]
0x18000c417  mov     [rbx+30h], rax
0x18000c41b  lea     rax, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; ushort const near * const WF_ADDR_TOKEN_DELIMITER_STR
0x18000c422  mov     [rsp+2E0h+var_290], r12
0x18000c427  mov     [rsp+2E0h+var_288], r14
0x18000c42c  jnz     loc_18000C6F1
0x18000c432  test    byte ptr [rbx+4], 1
0x18000c436  jnz     loc_18000C6F1
0x18000c43c  xor     r14d, r14d
0x18000c43f  test    byte ptr [rbx], 2
0x18000c442  jnz     loc_18000C928
0x18000c448  test    byte ptr [rbx+4], 2
0x18000c44c  jnz     loc_18000C928
0x18000c452  test    byte ptr [rbx], 4
0x18000c455  jnz     loc_18000C8B0
0x18000c45b  test    byte ptr [rbx+4], 4
0x18000c45f  jnz     loc_18000C8B0
0x18000c465  test    byte ptr [rbx], 8
0x18000c468  jnz     loc_18000C9D5
0x18000c46e  test    byte ptr [rbx+4], 8
0x18000c472  jnz     loc_18000C9D5
0x18000c478  test    byte ptr [rbx], 10h
0x18000c47b  jnz     loc_18000C838
0x18000c481  test    byte ptr [rbx+4], 10h
0x18000c485  jnz     loc_18000C838
0x18000c48b  mov     edi, [rbp+1E0h+arg_20]
0x18000c491  cmp     edi, 214h
0x18000c497  jnb     loc_18000CA82
0x18000c49d  lea     r12, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; ushort const near * const WF_ADDR_TOKEN_DELIMITER_STR
0x18000c4a4  cmp     edi, 21Eh
0x18000c4aa  jnb     loc_18000C781
0x18000c4b0  xor     r12d, r12d
0x18000c4b3  cmp     r12d, [rbx+8]
0x18000c4b7  jb      loc_18000CCC6
0x18000c4bd  mov     r13d, [rbp+1E0h+arg_28]
0x18000c4c4  lea     r12, aSSS_1; "%s-%s%s"
0x18000c4cb  xor     edi, edi
0x18000c4cd  cmp     edi, [rbx+18h]
0x18000c4d0  jnb     loc_18000C588
0x18000c4d6  mov     rcx, [rbx+20h]
0x18000c4da  lea     r14, ds:0[rdi*8]
0x18000c4e2  mov     ecx, [rcx+r14]; hostlong
0x18000c4e6  call    cs:__imp_htonl
0x18000c4ec  lea     rdx, [rbp+1E0h+S]; S
0x18000c4f0  mov     dword ptr [rbp+1E0h+Addr.S_un], eax
0x18000c4f3  lea     rcx, [rbp+1E0h+Addr]; Addr
0x18000c4f7  call    cs:__imp_RtlIpv4AddressToStringW
0x18000c4fd  mov     rcx, [rbx+20h]
0x18000c501  mov     ecx, [rcx+r14+4]; hostlong
0x18000c506  call    cs:__imp_htonl
0x18000c50c  lea     rdx, [rbp+1E0h+var_130]; S
0x18000c513  mov     dword ptr [rbp+1E0h+Addr.S_un], eax
0x18000c516  lea     rcx, [rbp+1E0h+Addr]; Addr
0x18000c51a  call    cs:__imp_RtlIpv4AddressToStringW
0x18000c520  test    r13d, r13d
0x18000c523  jz      loc_18000CDCA
0x18000c529  lea     rax, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; ushort const near * const WF_ADDR_TOKEN_DELIMITER_STR
0x18000c530  mov     rdx, rsi; unsigned __int64
0x18000c533  mov     [rsp+2E0h+var_2A0], rax
0x18000c538  lea     r9, [rsp+2E0h+var_288]; unsigned __int64 *
0x18000c53d  lea     rax, [rbp+1E0h+var_130]
0x18000c544  mov     rcx, r15; pszDest
0x18000c547  mov     [rsp+2E0h+var_2A8], rax
0x18000c54c  lea     r8, [rsp+2E0h+var_290]; unsigned __int16 **
0x18000c551  lea     rax, [rbp+1E0h+S]
0x18000c555  mov     [rsp+2E0h+var_2B0], rax
0x18000c55a  mov     [rsp+2E0h+var_2B8], r12; unsigned __int16 *
0x18000c55f  mov     [rsp+2E0h+var_2C0], 800h; unsigned int
0x18000c567  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c56c  mov     r14d, eax
0x18000c56f  test    eax, eax
0x18000c571  js      loc_18000C885
0x18000c577  mov     r15, [rsp+2E0h+var_290]
0x18000c57c  inc     edi
0x18000c57e  mov     rsi, [rsp+2E0h+var_288]
0x18000c583  jmp     loc_18000C4CD
0x18000c588  xor     r12d, r12d
0x18000c58b  cmp     r12d, [rbx+28h]
0x18000c58f  jb      loc_18000CE51
0x18000c595  xor     edi, edi
0x18000c597  lea     r12, aSSS_1; "%s-%s%s"
0x18000c59e  cmp     edi, [rbx+38h]
0x18000c5a1  jb      loc_18000C648
0x18000c5a7  mov     rbx, [rsp+2E0h+var_280]
0x18000c5ac  cmp     rbx, rsi
0x18000c5af  jnz     loc_18000C75A
0x18000c5b5  lea     rax, asc_18003D504; "*"
0x18000c5bc  mov     rdx, rsi; unsigned __int64
0x18000c5bf  mov     [rsp+2E0h+var_2B0], rax
0x18000c5c4  lea     r9, [rsp+2E0h+var_288]; unsigned __int64 *
0x18000c5c9  lea     rax, aS; "%s"
0x18000c5d0  mov     rcx, r15; pszDest
0x18000c5d3  mov     [rsp+2E0h+var_2B8], rax; unsigned __int16 *
0x18000c5d8  lea     r8, [rsp+2E0h+var_290]; unsigned __int16 **
0x18000c5dd  mov     [rsp+2E0h+var_2C0], 800h; unsigned int
0x18000c5e5  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c5ea  mov     r14d, eax
0x18000c5ed  test    eax, eax
0x18000c5ef  js      loc_18000C7FA
0x18000c5f5  mov     r15, [rsp+2E0h+var_290]
0x18000c5fa  mov     rsi, [rsp+2E0h+var_288]
0x18000c5ff  mov     rax, [rsp+2E0h+var_270]
0x18000c604  test    rax, rax
0x18000c607  jnz     loc_18000CFCF
0x18000c60d  mov     rax, [rsp+2E0h+var_268]
0x18000c612  test    rax, rax
0x18000c615  jnz     loc_18000CFD7
0x18000c61b  mov     eax, r14d
0x18000c61e  mov     rcx, [rbp+1E0h+var_40]
0x18000c625  xor     rcx, rsp; StackCookie
0x18000c628  call    __security_check_cookie
0x18000c62d  mov     rbx, [rsp+2E0h+arg_18]
0x18000c635  add     rsp, 2B0h
0x18000c63c  pop     r15
0x18000c63e  pop     r14
0x18000c640  pop     r13
0x18000c642  pop     r12
0x18000c644  pop     rdi
0x18000c645  pop     rsi
0x18000c646  pop     rbp
0x18000c647  retn
0x18000c648  mov     rax, [rbx+40h]
0x18000c64c  lea     rdx, [rbp+1E0h+S]; S
0x18000c650  mov     r14d, edi
0x18000c653  lea     rcx, [rbp+1E0h+var_238]; Addr
0x18000c657  shl     r14, 5
0x18000c65b  movups  xmm0, xmmword ptr [rax+r14]
0x18000c660  movups  xmmword ptr [rbp+1E0h+var_238.u], xmm0
0x18000c664  call    cs:__imp_RtlIpv6AddressToStringW
0x18000c66a  mov     rax, [rbx+40h]
0x18000c66e  lea     rdx, [rbp+1E0h+var_130]; S
0x18000c675  lea     rcx, [rbp+1E0h+var_238]; Addr
0x18000c679  movups  xmm0, xmmword ptr [rax+r14+10h]
0x18000c67f  movups  xmmword ptr [rbp+1E0h+var_238.u], xmm0
0x18000c683  call    cs:__imp_RtlIpv6AddressToStringW
0x18000c689  test    r13d, r13d
0x18000c68c  jz      loc_18000CF05
0x18000c692  lea     rax, ?WF_ADDR_TOKEN_DELIMITER_STR@@3QBGB; ushort const near * const WF_ADDR_TOKEN_DELIMITER_STR
0x18000c699  mov     rdx, rsi; unsigned __int64
0x18000c69c  mov     [rsp+2E0h+var_2A0], rax
0x18000c6a1  lea     r9, [rsp+2E0h+var_288]; unsigned __int64 *
0x18000c6a6  lea     rax, [rbp+1E0h+var_130]
0x18000c6ad  mov     rcx, r15; pszDest
0x18000c6b0  mov     [rsp+2E0h+var_2A8], rax
0x18000c6b5  lea     r8, [rsp+2E0h+var_290]; unsigned __int16 **
0x18000c6ba  lea     rax, [rbp+1E0h+S]
0x18000c6be  mov     [rsp+2E0h+var_2B0], rax
0x18000c6c3  mov     [rsp+2E0h+var_2B8], r12; unsigned __int16 *
0x18000c6c8  mov     [rsp+2E0h+var_2C0], 800h; unsigned int
0x18000c6d0  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c6d5  mov     r14d, eax
0x18000c6d8  test    eax, eax
0x18000c6da  js      loc_18000CF9A
0x18000c6e0  mov     r15, [rsp+2E0h+var_290]
0x18000c6e5  inc     edi
0x18000c6e7  mov     rsi, [rsp+2E0h+var_288]
0x18000c6ec  jmp     loc_18000C59E
0x18000c6f1  mov     [rsp+2E0h+var_2A8], rax
0x18000c6f6  lea     r9, [rsp+2E0h+var_288]; unsigned __int64 *
0x18000c6fb  lea     rax, aLocalsubnet; "LocalSubnet"
0x18000c702  mov     rdx, r14; unsigned __int64
0x18000c705  mov     [rsp+2E0h+var_2B0], rax
0x18000c70a  lea     r8, [rsp+2E0h+var_290]; unsigned __int16 **
0x18000c70f  mov     [rsp+2E0h+var_2B8], rcx; unsigned __int16 *
0x18000c714  mov     rcx, r12; pszDest
0x18000c717  mov     [rsp+2E0h+var_2C0], 800h; unsigned int
0x18000c71f  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c724  mov     r14d, eax
0x18000c727  test    eax, eax
0x18000c729  jns     loc_18000C90B
0x18000c72f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c736  lea     rax, WPP_GLOBAL_Control
0x18000c73d  cmp     rcx, rax
0x18000c740  jz      loc_18000C61B
0x18000c746  test    byte ptr [rcx+1Ch], 1
0x18000c74a  jz      loc_18000C61B
0x18000c750  mov     edx, 0B1h
0x18000c755  jmp     loc_18000C820
0x18000c75a  mov     rdi, [rsp+2E0h+var_278]
0x18000c75f  sub     rbx, rsi
0x18000c762  cmp     word ptr [rdi+rbx*2-2], 2Ch ; ','
0x18000c768  jnz     loc_18000CFC5
0x18000c76e  xor     eax, eax
0x18000c770  sub     r15, 2
0x18000c774  mov     [rdi+rbx*2-2], ax
0x18000c779  inc     rsi
0x18000c77c  jmp     loc_18000C5FF
0x18000c781  test    dword ptr [rbx], 200h
0x18000c787  jz      loc_18000CCA5
0x18000c78d  mov     [rsp+2E0h+var_2A8], r12
0x18000c792  lea     rax, aCaptiveportal; "CaptivePortal"
0x18000c799  mov     [rsp+2E0h+var_2B0], rax
0x18000c79e  lea     r9, [rsp+2E0h+var_288]; unsigned __int64 *
0x18000c7a3  lea     rax, aSS_0; "%s%s"
0x18000c7aa  mov     rdx, rsi; unsigned __int64
0x18000c7ad  mov     [rsp+2E0h+var_2B8], rax; unsigned __int16 *
0x18000c7b2  lea     r8, [rsp+2E0h+var_290]; unsigned __int16 **
0x18000c7b7  mov     rcx, r15; pszDest
0x18000c7ba  mov     [rsp+2E0h+var_2C0], 800h; unsigned int
0x18000c7c2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c7c7  mov     r14d, eax
0x18000c7ca  test    eax, eax
0x18000c7cc  jns     loc_18000CCB7
0x18000c7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7d9  lea     rax, WPP_GLOBAL_Control
0x18000c7e0  cmp     rcx, rax
0x18000c7e3  jz      loc_18000C61B
0x18000c7e9  test    byte ptr [rcx+1Ch], 1
0x18000c7ed  jz      loc_18000C61B
0x18000c7f3  mov     edx, 0BAh
0x18000c7f8  jmp     short loc_18000C820
0x18000c7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c801  lea     rax, WPP_GLOBAL_Control
0x18000c808  cmp     rcx, rax
0x18000c80b  jz      loc_18000C61B
0x18000c811  test    byte ptr [rcx+1Ch], 1
0x18000c815  jz      loc_18000C61B
0x18000c81b  mov     edx, 0C1h
0x18000c820  mov     rcx, [rcx+10h]
0x18000c824  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x18000c82b  mov     r9d, r14d
0x18000c82e  call    WPP_SF_d
0x18000c833  jmp     loc_18000C61B
0x18000c838  mov     [rsp+2E0h+var_2A8], rax
0x18000c83d  lea     r9, [rsp+2E0h+var_288]; unsigned __int64 *
0x18000c842  lea     rax, aDefaultgateway; "DefaultGateway"
0x18000c849  mov     rdx, rsi; unsigned __int64
0x18000c84c  mov     [rsp+2E0h+var_2B0], rax
0x18000c851  lea     r8, [rsp+2E0h+var_290]; unsigned __int16 **
0x18000c856  mov     [rsp+2E0h+var_2B8], rcx; unsigned __int16 *
0x18000c85b  mov     rcx, r15; pszDest
0x18000c85e  mov     [rsp+2E0h+var_2C0], 800h; unsigned int
0x18000c866  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c86b  mov     r14d, eax
0x18000c86e  test    eax, eax
  ... truncated ...
```
