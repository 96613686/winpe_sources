# ZtReadTrustedDotServer

- ea: `0x180005924`
- end: `0x180005d89`
- name: `ZtReadTrustedDotServer`
- size: `1125`
- prototype: `ULONG __fastcall(HKEY hKey, const wchar_t *, _OWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005d90`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x18000549c`
- `0x180005924`
- `0x1800072b0`
- `0x180009eac`
- `0x18000c750`
- `0x18000efc8`
- `0x180012564`
- `0x1800125d4`
- `0x180012614`
- `0x180015008`
- `0x18001553c`
- `0x180015694`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005a40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ab6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005b27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005b96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005c34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005a40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005ab6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005b27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005b96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005c34`

## pseudocode

```c
ULONG __fastcall ZtReadTrustedDotServer(HKEY hKey, const wchar_t *a2, _OWORD *a3)
{
  BYTE *lpData; // r12
  __int64 v7; // r14
  signed int v8; // ebx
  int v9; // eax
  LSTATUS Value; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  int v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // r8
  unsigned __int16 v17; // ax
  int v18; // eax
  BYTE *v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  ULONG v23; // eax
  DWORD Type; // [rsp+40h] [rbp-49h] BYREF
  DWORD cbData[2]; // [rsp+44h] [rbp-45h] BYREF
  int v27; // [rsp+4Ch] [rbp-3Dh]
  BYTE v28[4]; // [rsp+50h] [rbp-39h] BYREF
  BYTE v29[12]; // [rsp+54h] [rbp-35h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v31; // [rsp+70h] [rbp-19h] BYREF
  __int128 v32; // [rsp+80h] [rbp-9h]
  __int128 v33; // [rsp+90h] [rbp+7h]

  lpData = 0;
  v27 = 0;
  Type = 0;
  cbData[0] = 0;
  *(_DWORD *)v28 = 0;
  v7 = 64;
  *(_DWORD *)v29 = 0xFFFF;
  memset_0(Data, 0, 0x40u);
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qSq(1026, 0x40u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, hKey, a2, a3);
  WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(a3);
  if ( !hKey )
  {
    v8 = -2147024809;
    v27 = 717;
    goto LABEL_62;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    v27 = 718;
    goto LABEL_62;
  }
  v9 = DnsConvertStringToSockaddr(a2, &v31);
  v8 = v9;
  if ( v9 > 0 )
    v8 = (unsigned __int16)v9 | 0x80070000;
  if ( v8 < 0 )
  {
    v27 = 724;
    goto LABEL_62;
  }
  *(_DWORD *)Data = 1;
  LODWORD(v33) = 2;
  Value = RegQueryValueExW(hKey, L"DotHostname", 0, 0, 0, cbData);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 < 0 )
  {
    v27 = 740;
    goto LABEL_62;
  }
  if ( cbData[0] )
  {
    lpData = (BYTE *)Dns_Allocate(cbData[0]);
    if ( !lpData )
    {
      v8 = -2147024809;
      v27 = 745;
      goto LABEL_62;
    }
    Type = 0;
    v11 = RegQueryValueExW(hKey, L"DotHostname", 0, &Type, lpData, cbData);
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( v8 < 0 )
    {
      v27 = 753;
      goto LABEL_62;
    }
    if ( Type != 1 )
    {
      v8 = -2147024809;
      v27 = 755;
      goto LABEL_62;
    }
  }
  *((_QWORD *)&v33 + 1) = lpData;
  cbData[0] = 8;
  lpData = 0;
  Type = 0;
  v12 = RegQueryValueExW(hKey, L"DotFlags", 0, &Type, &Data[8], cbData);
  v8 = v12;
  if ( v12 != 2 )
  {
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
    {
      v27 = 775;
      goto LABEL_62;
    }
    if ( Type != 11 )
    {
      v8 = -2147024809;
      v27 = 776;
      goto LABEL_62;
    }
  }
  Type = 0;
  cbData[0] = 4;
  v13 = RegQueryValueExW(hKey, L"DotPort", 0, &Type, v28, cbData);
  v8 = v13;
  if ( v13 != 2 )
  {
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 < 0 )
    {
      v27 = 794;
      goto LABEL_62;
    }
    if ( Type != 4 )
    {
      v8 = -2147024809;
      v27 = 796;
      goto LABEL_62;
    }
    v14 = DnsValidateDotPort(*(unsigned int *)v28);
    v8 = v14;
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    if ( v8 < 0 )
    {
      v27 = 798;
      goto LABEL_62;
    }
    WORD6(v32) = *(_WORD *)v28;
  }
  Type = 0;
  cbData[0] = 4;
  v15 = RegQueryValueExW(hKey, L"Priority", 0, &Type, v29, cbData);
  v8 = v15;
  if ( v15 == 2 )
  {
    v17 = HIWORD(v32);
  }
  else
  {
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    if ( v8 < 0 )
    {
      v27 = 818;
      goto LABEL_62;
    }
    if ( Type != 4 )
    {
      v8 = -2147024809;
      v27 = 820;
      goto LABEL_62;
    }
    v17 = *(_WORD *)v29;
    if ( *(_DWORD *)v29 > 0xFFFFu )
    {
      v8 = -2147024809;
      v27 = 822;
      goto LABEL_62;
    }
    HIWORD(v32) = *(_WORD *)v29;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_SSidd(WORD6(v32), 0x41u, v16, a2, *((const wchar_t **)&v33 + 1), *(_QWORD *)&Data[8], WORD6(v32), v17);
  v18 = ZtValidateTrustedServers(1, Data);
  v8 = v18;
  if ( v18 > 0 )
    v8 = (unsigned __int16)v18 | 0x80070000;
  if ( v8 >= 0 )
  {
    v19 = Data;
    v20 = v31;
    *a3 = *(_OWORD *)Data;
    v21 = v32;
    a3[1] = v20;
    v22 = v33;
    a3[2] = v21;
    a3[3] = v22;
    do
    {
      *v19++ = 0;
      --v7;
    }
    while ( v7 );
  }
  else
  {
    v27 = 839;
  }
LABEL_62:
  Dns_Free(lpData);
  DnsFreeZtTrustedServerMembers((__int64)Data);
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v23 = WX_WIN32_FROM_HR(v8);
    WPP_SF_d(1026, 0x42u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v23);
  }
  return WX_WIN32_FROM_HR(v8);
}

```

## disassembly

```asm
0x180005924  push    rbp
0x180005926  push    rbx
0x180005927  push    rsi
0x180005928  push    rdi
0x180005929  push    r12
0x18000592b  push    r14
0x18000592d  push    r15
0x18000592f  lea     rbp, [rsp-27h]
0x180005934  sub     rsp, 0B0h
0x18000593b  mov     rax, cs:__security_cookie
0x180005942  xor     rax, rsp
0x180005945  mov     [rbp+57h+var_40], rax
0x180005949  xor     r12d, r12d
0x18000594c  mov     [rbp+57h+var_94], 0
0x180005953  mov     rsi, r8
0x180005956  mov     [rbp+57h+Type], 0
0x18000595d  mov     r15, rdx
0x180005960  mov     [rbp+57h+cbData], 0
0x180005967  mov     rdi, rcx
0x18000596a  mov     dword ptr [rbp+57h+var_90], 0
0x180005971  lea     r14d, [r12+40h]
0x180005976  mov     dword ptr [rbp+57h+var_8C], 0FFFFh
0x18000597d  mov     r8d, r14d; Size
0x180005980  lea     rcx, [rbp+57h+Data]; void *
0x180005984  xor     edx, edx; Val
0x180005986  call    memset_0
0x18000598b  test    byte ptr cs:xmmword_18001F260, 4
0x180005992  jz      short loc_1800059B5
0x180005994  mov     edx, r14d
0x180005997  mov     [rsp+0E0h+lpcbData], rsi
0x18000599c  mov     ecx, 402h
0x1800059a1  mov     [rsp+0E0h+lpData], r15
0x1800059a6  mov     r9, rdi
0x1800059a9  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x1800059b0  call    WPP_SF_qSq
0x1800059b5  mov     rcx, rsi
0x1800059b8  call    ??$WxZeroOut@U_DNS_ZT_TRUSTED_SERVER@@@@YAXPEAU_DNS_ZT_TRUSTED_SERVER@@@Z; WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(_DNS_ZT_TRUSTED_SERVER *)
0x1800059bd  test    rdi, rdi
0x1800059c0  jnz     short loc_1800059D3
0x1800059c2  mov     ebx, 80070057h
0x1800059c7  mov     [rbp+57h+var_94], 2CDh
0x1800059ce  jmp     loc_180005D2A
0x1800059d3  test    rsi, rsi
0x1800059d6  jnz     short loc_1800059E9
0x1800059d8  mov     ebx, 80070057h
0x1800059dd  mov     [rbp+57h+var_94], 2CEh
0x1800059e4  jmp     loc_180005D2A
0x1800059e9  lea     rdx, [rbp+57h+var_70]
0x1800059ed  mov     rcx, r15
0x1800059f0  call    DnsConvertStringToSockaddr
0x1800059f5  mov     ebx, eax
0x1800059f7  test    eax, eax
0x1800059f9  jle     short loc_180005A04
0x1800059fb  movzx   ebx, ax
0x1800059fe  or      ebx, 80070000h
0x180005a04  test    ebx, ebx
0x180005a06  jns     short loc_180005A14
0x180005a08  mov     [rbp+57h+var_94], 2D4h
0x180005a0f  jmp     loc_180005D2A
0x180005a14  lea     rax, [rbp+57h+cbData]
0x180005a18  mov     dword ptr [rbp+57h+Data], 1
0x180005a1f  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180005a24  lea     rdx, aDothostname; "DotHostname"
0x180005a2b  xor     r9d, r9d; lpType
0x180005a2e  mov     [rsp+0E0h+lpData], r12; lpData
0x180005a33  xor     r8d, r8d; lpReserved
0x180005a36  mov     dword ptr [rbp+57h+var_50], 2
0x180005a3d  mov     rcx, rdi; hKey
0x180005a40  call    cs:__imp_RegQueryValueExW
0x180005a46  mov     ebx, eax
0x180005a48  test    eax, eax
0x180005a4a  jle     short loc_180005A55
0x180005a4c  movzx   ebx, ax
0x180005a4f  or      ebx, 80070000h
0x180005a55  test    ebx, ebx
0x180005a57  jns     short loc_180005A65
0x180005a59  mov     [rbp+57h+var_94], 2E4h
0x180005a60  jmp     loc_180005D2A
0x180005a65  mov     eax, [rbp+57h+cbData]
0x180005a68  test    eax, eax
0x180005a6a  jz      loc_180005AF2
0x180005a70  mov     ecx, eax
0x180005a72  call    Dns_Allocate
0x180005a77  mov     r12, rax
0x180005a7a  test    rax, rax
0x180005a7d  jnz     short loc_180005A90
0x180005a7f  mov     ebx, 80070057h
0x180005a84  mov     [rbp+57h+var_94], 2E9h
0x180005a8b  jmp     loc_180005D2A
0x180005a90  lea     rax, [rbp+57h+cbData]
0x180005a94  mov     [rbp+57h+Type], 0
0x180005a9b  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180005aa0  lea     r9, [rbp+57h+Type]; lpType
0x180005aa4  xor     r8d, r8d; lpReserved
0x180005aa7  mov     [rsp+0E0h+lpData], r12; lpData
0x180005aac  lea     rdx, aDothostname; "DotHostname"
0x180005ab3  mov     rcx, rdi; hKey
0x180005ab6  call    cs:__imp_RegQueryValueExW
0x180005abc  mov     ebx, eax
0x180005abe  test    eax, eax
0x180005ac0  jle     short loc_180005ACB
0x180005ac2  movzx   ebx, ax
0x180005ac5  or      ebx, 80070000h
0x180005acb  test    ebx, ebx
0x180005acd  jns     short loc_180005ADB
0x180005acf  mov     [rbp+57h+var_94], 2F1h
0x180005ad6  jmp     loc_180005D2A
0x180005adb  cmp     [rbp+57h+Type], 1
0x180005adf  jz      short loc_180005AF2
0x180005ae1  mov     ebx, 80070057h
0x180005ae6  mov     [rbp+57h+var_94], 2F3h
0x180005aed  jmp     loc_180005D2A
0x180005af2  lea     rax, [rbp+57h+cbData]
0x180005af6  mov     qword ptr [rbp+57h+var_50+8], r12
0x180005afa  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180005aff  lea     r9, [rbp+57h+Type]; lpType
0x180005b03  lea     rax, [rbp+57h+Data+8]
0x180005b07  mov     [rbp+57h+cbData], 8
0x180005b0e  xor     r12d, r12d
0x180005b11  mov     [rsp+0E0h+lpData], rax; lpData
0x180005b16  xor     r8d, r8d; lpReserved
0x180005b19  mov     [rbp+57h+Type], r12d
0x180005b1d  lea     rdx, aDotflags; "DotFlags"
0x180005b24  mov     rcx, rdi; hKey
0x180005b27  call    cs:__imp_RegQueryValueExW
0x180005b2d  mov     ebx, eax
0x180005b2f  cmp     eax, 2
0x180005b32  jz      short loc_180005B68
0x180005b34  test    eax, eax
0x180005b36  jle     short loc_180005B41
0x180005b38  movzx   ebx, ax
0x180005b3b  or      ebx, 80070000h
0x180005b41  test    ebx, ebx
0x180005b43  jns     short loc_180005B51
0x180005b45  mov     [rbp+57h+var_94], 307h
0x180005b4c  jmp     loc_180005D2A
0x180005b51  cmp     [rbp+57h+Type], 0Bh
0x180005b55  jz      short loc_180005B68
0x180005b57  mov     ebx, 80070057h
0x180005b5c  mov     [rbp+57h+var_94], 308h
0x180005b63  jmp     loc_180005D2A
0x180005b68  lea     rax, [rbp+57h+cbData]
0x180005b6c  mov     [rbp+57h+Type], r12d
0x180005b70  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180005b75  lea     r9, [rbp+57h+Type]; lpType
0x180005b79  lea     rax, [rbp+57h+var_90]
0x180005b7d  mov     [rbp+57h+cbData], 4
0x180005b84  xor     r8d, r8d; lpReserved
0x180005b87  mov     [rsp+0E0h+lpData], rax; lpData
0x180005b8c  lea     rdx, aDotport; "DotPort"
0x180005b93  mov     rcx, rdi; hKey
0x180005b96  call    cs:__imp_RegQueryValueExW
0x180005b9c  mov     ebx, eax
0x180005b9e  cmp     eax, 2
0x180005ba1  jz      short loc_180005C06
0x180005ba3  test    eax, eax
0x180005ba5  jle     short loc_180005BB0
0x180005ba7  movzx   ebx, ax
0x180005baa  or      ebx, 80070000h
0x180005bb0  test    ebx, ebx
0x180005bb2  jns     short loc_180005BC0
0x180005bb4  mov     [rbp+57h+var_94], 31Ah
0x180005bbb  jmp     loc_180005D2A
0x180005bc0  cmp     [rbp+57h+Type], 4
0x180005bc4  jz      short loc_180005BD7
0x180005bc6  mov     ebx, 80070057h
0x180005bcb  mov     [rbp+57h+var_94], 31Ch
0x180005bd2  jmp     loc_180005D2A
0x180005bd7  mov     ecx, dword ptr [rbp+57h+var_90]
0x180005bda  call    DnsValidateDotPort
0x180005bdf  mov     ebx, eax
0x180005be1  test    eax, eax
0x180005be3  jle     short loc_180005BEE
0x180005be5  movzx   ebx, ax
0x180005be8  or      ebx, 80070000h
0x180005bee  test    ebx, ebx
0x180005bf0  jns     short loc_180005BFE
0x180005bf2  mov     [rbp+57h+var_94], 31Eh
0x180005bf9  jmp     loc_180005D2A
0x180005bfe  movzx   eax, word ptr [rbp+57h+var_90]
0x180005c02  mov     [rbp+57h+var_54], ax
0x180005c06  lea     rax, [rbp+57h+cbData]
0x180005c0a  mov     [rbp+57h+Type], r12d
0x180005c0e  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180005c13  lea     r9, [rbp+57h+Type]; lpType
0x180005c17  lea     rax, [rbp+57h+var_8C]
0x180005c1b  mov     [rbp+57h+cbData], 4
0x180005c22  xor     r8d, r8d; lpReserved
0x180005c25  mov     [rsp+0E0h+lpData], rax; lpData
0x180005c2a  lea     rdx, aPriority; "Priority"
0x180005c31  mov     rcx, rdi; hKey
0x180005c34  call    cs:__imp_RegQueryValueExW
0x180005c3a  mov     ebx, eax
0x180005c3c  cmp     eax, 2
0x180005c3f  jz      short loc_180005C96
0x180005c41  test    eax, eax
0x180005c43  jle     short loc_180005C4E
0x180005c45  movzx   ebx, ax
0x180005c48  or      ebx, 80070000h
0x180005c4e  test    ebx, ebx
0x180005c50  jns     short loc_180005C5E
0x180005c52  mov     [rbp+57h+var_94], 332h
0x180005c59  jmp     loc_180005D2A
0x180005c5e  cmp     [rbp+57h+Type], 4
0x180005c62  jz      short loc_180005C75
0x180005c64  mov     ebx, 80070057h
0x180005c69  mov     [rbp+57h+var_94], 334h
0x180005c70  jmp     loc_180005D2A
0x180005c75  mov     eax, dword ptr [rbp+57h+var_8C]
0x180005c78  cmp     eax, 0FFFFh
0x180005c7d  jbe     short loc_180005C90
0x180005c7f  mov     ebx, 80070057h
0x180005c84  mov     [rbp+57h+var_94], 336h
0x180005c8b  jmp     loc_180005D2A
0x180005c90  mov     [rbp+57h+var_52], ax
0x180005c94  jmp     short loc_180005C9A
0x180005c96  movzx   eax, [rbp+57h+var_52]
0x180005c9a  test    byte ptr cs:xmmword_18001F260, 4
0x180005ca1  jz      short loc_180005CD1
0x180005ca3  movzx   ecx, [rbp+57h+var_54]
0x180005ca7  mov     edx, 41h ; 'A'
0x180005cac  movzx   eax, ax
0x180005caf  mov     r9, r15
0x180005cb2  mov     [rsp+0E0h+var_A8], eax
0x180005cb6  mov     rax, qword ptr [rbp+57h+Data+8]
0x180005cba  mov     [rsp+0E0h+var_B0], ecx
0x180005cbe  mov     [rsp+0E0h+lpcbData], rax
0x180005cc3  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180005cc7  mov     [rsp+0E0h+lpData], rax
0x180005ccc  call    WPP_SF_SSidd
0x180005cd1  lea     rdx, [rbp+57h+Data]
0x180005cd5  mov     ecx, 1
0x180005cda  call    ZtValidateTrustedServers
0x180005cdf  mov     ebx, eax
0x180005ce1  test    eax, eax
0x180005ce3  jle     short loc_180005CEE
0x180005ce5  movzx   ebx, ax
0x180005ce8  or      ebx, 80070000h
0x180005cee  test    ebx, ebx
0x180005cf0  jns     short loc_180005CFB
0x180005cf2  mov     [rbp+57h+var_94], 347h
0x180005cf9  jmp     short loc_180005D2A
0x180005cfb  movaps  xmm0, xmmword ptr [rbp+57h+Data]
0x180005cff  lea     rax, [rbp+57h+Data]
0x180005d03  movaps  xmm1, [rbp+57h+var_70]
0x180005d07  movaps  xmmword ptr [rsi], xmm0
0x180005d0a  movaps  xmm0, xmmword ptr [rbp-9]
0x180005d0e  movaps  xmmword ptr [rsi+10h], xmm1
0x180005d12  movaps  xmm1, [rbp+57h+var_50]
0x180005d16  movaps  xmmword ptr [rsi+20h], xmm0
0x180005d1a  movaps  xmmword ptr [rsi+30h], xmm1
0x180005d1e  mov     [rax], r12b
0x180005d21  inc     rax
0x180005d24  sub     r14, 1
0x180005d28  jnz     short loc_180005D1E
0x180005d2a  mov     rcx, r12; lpMem
0x180005d2d  call    Dns_Free
0x180005d32  lea     rcx, [rbp+57h+Data]
0x180005d36  call    DnsFreeZtTrustedServerMembers
0x180005d3b  test    byte ptr cs:xmmword_18001F260, 4
0x180005d42  jz      short loc_180005D64
0x180005d44  mov     ecx, ebx
0x180005d46  call    WX_WIN32_FROM_HR
0x180005d4b  mov     r9d, eax
0x180005d4e  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180005d55  mov     edx, 42h ; 'B'
0x180005d5a  mov     ecx, 402h
0x180005d5f  call    WPP_SF_d
0x180005d64  mov     ecx, ebx
0x180005d66  call    WX_WIN32_FROM_HR
0x180005d6b  mov     rcx, [rbp+57h+var_40]
0x180005d6f  xor     rcx, rsp; StackCookie
0x180005d72  call    __security_check_cookie
0x180005d77  add     rsp, 0B0h
0x180005d7e  pop     r15
0x180005d80  pop     r14
0x180005d82  pop     r12
0x180005d84  pop     rdi
0x180005d85  pop     rsi
0x180005d86  pop     rbx
0x180005d87  pop     rbp
0x180005d88  retn
```
