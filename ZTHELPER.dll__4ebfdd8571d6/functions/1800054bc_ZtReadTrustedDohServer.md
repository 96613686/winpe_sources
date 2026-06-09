# ZtReadTrustedDohServer

- ea: `0x1800054bc`
- end: `0x18000591d`
- name: `ZtReadTrustedDohServer`
- size: `1121`
- prototype: `ULONG __fastcall(HKEY hKey, const wchar_t *, _OWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005d90`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x18000549c`
- `0x1800054bc`
- `0x1800072b0`
- `0x180009eac`
- `0x18000c750`
- `0x18000efc8`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`
- `0x18001553c`
- `0x180015694`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800055ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000565a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800056cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000573a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800057c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800055ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000565a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800056cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000573a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800057c8`

## string_xrefs

- `0x1800055d2`: `DohTemplate`
- `0x180005650`: `DohTemplate`

## pseudocode

```c
ULONG __fastcall ZtReadTrustedDohServer(HKEY hKey, const wchar_t *a2, _OWORD *a3)
{
  BYTE *lpData; // r15
  __int64 v7; // r12
  signed int v8; // ebx
  int v9; // eax
  LSTATUS Value; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // r8
  unsigned __int16 v16; // ax
  int v17; // eax
  BYTE *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  ULONG v22; // eax
  DWORD Type; // [rsp+40h] [rbp-49h] BYREF
  DWORD cbData[2]; // [rsp+44h] [rbp-45h] BYREF
  int v26; // [rsp+4Ch] [rbp-3Dh]
  BYTE v27[4]; // [rsp+50h] [rbp-39h] BYREF
  BYTE v28[12]; // [rsp+54h] [rbp-35h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v30; // [rsp+70h] [rbp-19h] BYREF
  __int128 v31; // [rsp+80h] [rbp-9h]
  __int128 v32; // [rsp+90h] [rbp+7h]

  lpData = 0;
  v26 = 0;
  Type = 0;
  cbData[0] = 0;
  *(_DWORD *)v27 = 0;
  v7 = 64;
  *(_DWORD *)v28 = 0xFFFF;
  memset_0(Data, 0, 0x40u);
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qSq(1026, 0x3Du, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, hKey, a2, a3);
  WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(a3);
  if ( !hKey )
  {
    v8 = -2147024809;
    v26 = 555;
    goto LABEL_61;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    v26 = 556;
    goto LABEL_61;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    v26 = 557;
    goto LABEL_61;
  }
  v9 = DnsConvertStringToSockaddr(a2, &v30);
  v8 = v9;
  if ( v9 > 0 )
    v8 = (unsigned __int16)v9 | 0x80070000;
  if ( v8 < 0 )
  {
    v26 = 563;
    goto LABEL_61;
  }
  *(_DWORD *)Data = 1;
  LODWORD(v32) = 1;
  Value = RegQueryValueExW(hKey, L"DohTemplate", 0, 0, 0, cbData);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 < 0 )
  {
    v26 = 576;
    goto LABEL_61;
  }
  lpData = (BYTE *)Dns_Allocate(cbData[0]);
  if ( !lpData )
  {
    v8 = -2147024809;
    v26 = 579;
    goto LABEL_61;
  }
  Type = 0;
  v11 = RegQueryValueExW(hKey, L"DohTemplate", 0, &Type, lpData, cbData);
  v8 = v11;
  if ( v11 > 0 )
    v8 = (unsigned __int16)v11 | 0x80070000;
  if ( v8 < 0 )
  {
    v26 = 587;
    goto LABEL_61;
  }
  if ( Type != 1 )
  {
    v8 = -2147024809;
    v26 = 589;
    goto LABEL_61;
  }
  *((_QWORD *)&v32 + 1) = lpData;
  cbData[0] = 8;
  lpData = 0;
  Type = 0;
  v12 = RegQueryValueExW(hKey, L"DohFlags", 0, &Type, &Data[8], cbData);
  v8 = v12;
  if ( v12 != 2 )
  {
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
    {
      v26 = 608;
      goto LABEL_61;
    }
    if ( Type != 11 )
    {
      v8 = -2147024809;
      v26 = 610;
      goto LABEL_61;
    }
  }
  Type = 0;
  cbData[0] = 4;
  v13 = RegQueryValueExW(hKey, L"DohPort", 0, &Type, v27, cbData);
  v8 = v13;
  if ( v13 != 2 )
  {
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 < 0 )
    {
      v26 = 628;
      goto LABEL_61;
    }
    if ( Type != 4 )
    {
      v8 = -2147024809;
      v26 = 630;
      goto LABEL_61;
    }
    if ( *(_DWORD *)v27 > 0xFFFFu )
    {
      v8 = -2147024809;
      v26 = 632;
      goto LABEL_61;
    }
    WORD6(v31) = *(_WORD *)v27;
  }
  Type = 0;
  cbData[0] = 4;
  v14 = RegQueryValueExW(hKey, L"Priority", 0, &Type, v28, cbData);
  v8 = v14;
  if ( v14 == 2 )
  {
    v16 = HIWORD(v31);
  }
  else
  {
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    if ( v8 < 0 )
    {
      v26 = 652;
      goto LABEL_61;
    }
    if ( Type != 4 )
    {
      v8 = -2147024809;
      v26 = 654;
      goto LABEL_61;
    }
    v16 = *(_WORD *)v28;
    if ( *(_DWORD *)v28 > 0xFFFFu )
    {
      v8 = -2147024809;
      v26 = 656;
      goto LABEL_61;
    }
    HIWORD(v31) = *(_WORD *)v28;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_SSidd(WORD6(v31), 0x3Eu, v15, a2, *((const wchar_t **)&v32 + 1), *(_QWORD *)&Data[8], WORD6(v31), v16);
  v17 = ZtValidateTrustedServers(1, Data);
  v8 = v17;
  if ( v17 > 0 )
    v8 = (unsigned __int16)v17 | 0x80070000;
  if ( v8 >= 0 )
  {
    v18 = Data;
    v19 = v30;
    *a3 = *(_OWORD *)Data;
    v20 = v31;
    a3[1] = v19;
    v21 = v32;
    a3[2] = v20;
    a3[3] = v21;
    do
    {
      *v18++ = 0;
      --v7;
    }
    while ( v7 );
  }
  else
  {
    v26 = 673;
  }
LABEL_61:
  Dns_Free(lpData);
  DnsFreeZtTrustedServerMembers((__int64)Data);
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v22 = WX_WIN32_FROM_HR(v8);
    WPP_SF_d(1026, 0x3Fu, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v22);
  }
  return WX_WIN32_FROM_HR(v8);
}

```

## disassembly

```asm
0x1800054bc  push    rbp
0x1800054be  push    rbx
0x1800054bf  push    rsi
0x1800054c0  push    rdi
0x1800054c1  push    r12
0x1800054c3  push    r14
0x1800054c5  push    r15
0x1800054c7  lea     rbp, [rsp-27h]
0x1800054cc  sub     rsp, 0B0h
0x1800054d3  mov     rax, cs:__security_cookie
0x1800054da  xor     rax, rsp
0x1800054dd  mov     [rbp+57h+var_40], rax
0x1800054e1  xor     r15d, r15d
0x1800054e4  mov     [rbp+57h+var_94], 0
0x1800054eb  mov     rsi, r8
0x1800054ee  mov     [rbp+57h+Type], 0
0x1800054f5  mov     r14, rdx
0x1800054f8  mov     [rbp+57h+cbData], 0
0x1800054ff  mov     rdi, rcx
0x180005502  mov     dword ptr [rbp+57h+var_90], 0
0x180005509  lea     r12d, [r15+40h]
0x18000550d  mov     dword ptr [rbp+57h+var_8C], 0FFFFh
0x180005514  mov     r8d, r12d; Size
0x180005517  lea     rcx, [rbp+57h+Data]; void *
0x18000551b  xor     edx, edx; Val
0x18000551d  call    memset_0
0x180005522  test    byte ptr cs:xmmword_18001F260, 4
0x180005529  jz      short loc_18000554D
0x18000552b  lea     edx, [r15+3Dh]
0x18000552f  mov     [rsp+0E0h+lpcbData], rsi
0x180005534  mov     ecx, 402h
0x180005539  mov     [rsp+0E0h+lpData], r14
0x18000553e  mov     r9, rdi
0x180005541  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180005548  call    WPP_SF_qSq
0x18000554d  mov     rcx, rsi
0x180005550  call    ??$WxZeroOut@U_DNS_ZT_TRUSTED_SERVER@@@@YAXPEAU_DNS_ZT_TRUSTED_SERVER@@@Z; WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(_DNS_ZT_TRUSTED_SERVER *)
0x180005555  test    rdi, rdi
0x180005558  jnz     short loc_18000556B
0x18000555a  mov     ebx, 80070057h
0x18000555f  mov     [rbp+57h+var_94], 22Bh
0x180005566  jmp     loc_1800058BE
0x18000556b  test    r14, r14
0x18000556e  jnz     short loc_180005581
0x180005570  mov     ebx, 80070057h
0x180005575  mov     [rbp+57h+var_94], 22Ch
0x18000557c  jmp     loc_1800058BE
0x180005581  test    rsi, rsi
0x180005584  jnz     short loc_180005597
0x180005586  mov     ebx, 80070057h
0x18000558b  mov     [rbp+57h+var_94], 22Dh
0x180005592  jmp     loc_1800058BE
0x180005597  lea     rdx, [rbp+57h+var_70]
0x18000559b  mov     rcx, r14
0x18000559e  call    DnsConvertStringToSockaddr
0x1800055a3  mov     ebx, eax
0x1800055a5  test    eax, eax
0x1800055a7  jle     short loc_1800055B2
0x1800055a9  movzx   ebx, ax
0x1800055ac  or      ebx, 80070000h
0x1800055b2  test    ebx, ebx
0x1800055b4  jns     short loc_1800055C2
0x1800055b6  mov     [rbp+57h+var_94], 233h
0x1800055bd  jmp     loc_1800058BE
0x1800055c2  lea     rax, [rbp+57h+cbData]
0x1800055c6  mov     dword ptr [rbp+57h+Data], 1
0x1800055cd  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800055d2  lea     rdx, aDohtemplate; "DohTemplate"
0x1800055d9  xor     r9d, r9d; lpType
0x1800055dc  mov     [rsp+0E0h+lpData], r15; lpData
0x1800055e1  xor     r8d, r8d; lpReserved
0x1800055e4  mov     dword ptr [rbp+57h+var_50], 1
0x1800055eb  mov     rcx, rdi; hKey
0x1800055ee  call    cs:__imp_RegQueryValueExW
0x1800055f4  mov     ebx, eax
0x1800055f6  test    eax, eax
0x1800055f8  jle     short loc_180005603
0x1800055fa  movzx   ebx, ax
0x1800055fd  or      ebx, 80070000h
0x180005603  test    ebx, ebx
0x180005605  jns     short loc_180005613
0x180005607  mov     [rbp+57h+var_94], 240h
0x18000560e  jmp     loc_1800058BE
0x180005613  mov     ecx, [rbp+57h+cbData]
0x180005616  call    Dns_Allocate
0x18000561b  mov     r15, rax
0x18000561e  test    rax, rax
0x180005621  jnz     short loc_180005634
0x180005623  mov     ebx, 80070057h
0x180005628  mov     [rbp+57h+var_94], 243h
0x18000562f  jmp     loc_1800058BE
0x180005634  lea     rax, [rbp+57h+cbData]
0x180005638  mov     [rbp+57h+Type], 0
0x18000563f  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180005644  lea     r9, [rbp+57h+Type]; lpType
0x180005648  xor     r8d, r8d; lpReserved
0x18000564b  mov     [rsp+0E0h+lpData], r15; lpData
0x180005650  lea     rdx, aDohtemplate; "DohTemplate"
0x180005657  mov     rcx, rdi; hKey
0x18000565a  call    cs:__imp_RegQueryValueExW
0x180005660  mov     ebx, eax
0x180005662  test    eax, eax
0x180005664  jle     short loc_18000566F
0x180005666  movzx   ebx, ax
0x180005669  or      ebx, 80070000h
0x18000566f  test    ebx, ebx
0x180005671  jns     short loc_18000567F
0x180005673  mov     [rbp+57h+var_94], 24Bh
0x18000567a  jmp     loc_1800058BE
0x18000567f  cmp     [rbp+57h+Type], 1
0x180005683  jz      short loc_180005696
0x180005685  mov     ebx, 80070057h
0x18000568a  mov     [rbp+57h+var_94], 24Dh
0x180005691  jmp     loc_1800058BE
0x180005696  lea     rax, [rbp+57h+cbData]
0x18000569a  mov     qword ptr [rbp+57h+var_50+8], r15
0x18000569e  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800056a3  lea     r9, [rbp+57h+Type]; lpType
0x1800056a7  lea     rax, [rbp+57h+Data+8]
0x1800056ab  mov     [rbp+57h+cbData], 8
0x1800056b2  xor     r15d, r15d
0x1800056b5  mov     [rsp+0E0h+lpData], rax; lpData
0x1800056ba  xor     r8d, r8d; lpReserved
0x1800056bd  mov     [rbp+57h+Type], r15d
0x1800056c1  lea     rdx, aDohflags; "DohFlags"
0x1800056c8  mov     rcx, rdi; hKey
0x1800056cb  call    cs:__imp_RegQueryValueExW
0x1800056d1  mov     ebx, eax
0x1800056d3  cmp     eax, 2
0x1800056d6  jz      short loc_18000570C
0x1800056d8  test    eax, eax
0x1800056da  jle     short loc_1800056E5
0x1800056dc  movzx   ebx, ax
0x1800056df  or      ebx, 80070000h
0x1800056e5  test    ebx, ebx
0x1800056e7  jns     short loc_1800056F5
0x1800056e9  mov     [rbp+57h+var_94], 260h
0x1800056f0  jmp     loc_1800058BE
0x1800056f5  cmp     [rbp+57h+Type], 0Bh
0x1800056f9  jz      short loc_18000570C
0x1800056fb  mov     ebx, 80070057h
0x180005700  mov     [rbp+57h+var_94], 262h
0x180005707  jmp     loc_1800058BE
0x18000570c  lea     rax, [rbp+57h+cbData]
0x180005710  mov     [rbp+57h+Type], r15d
0x180005714  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180005719  lea     r9, [rbp+57h+Type]; lpType
0x18000571d  lea     rax, [rbp+57h+var_90]
0x180005721  mov     [rbp+57h+cbData], 4
0x180005728  xor     r8d, r8d; lpReserved
0x18000572b  mov     [rsp+0E0h+lpData], rax; lpData
0x180005730  lea     rdx, aDohport; "DohPort"
0x180005737  mov     rcx, rdi; hKey
0x18000573a  call    cs:__imp_RegQueryValueExW
0x180005740  mov     ebx, eax
0x180005742  cmp     eax, 2
0x180005745  jz      short loc_18000579A
0x180005747  test    eax, eax
0x180005749  jle     short loc_180005754
0x18000574b  movzx   ebx, ax
0x18000574e  or      ebx, 80070000h
0x180005754  test    ebx, ebx
0x180005756  jns     short loc_180005764
0x180005758  mov     [rbp+57h+var_94], 274h
0x18000575f  jmp     loc_1800058BE
0x180005764  cmp     [rbp+57h+Type], 4
0x180005768  jz      short loc_18000577B
0x18000576a  mov     ebx, 80070057h
0x18000576f  mov     [rbp+57h+var_94], 276h
0x180005776  jmp     loc_1800058BE
0x18000577b  mov     eax, dword ptr [rbp+57h+var_90]
0x18000577e  cmp     eax, 0FFFFh
0x180005783  jbe     short loc_180005796
0x180005785  mov     ebx, 80070057h
0x18000578a  mov     [rbp+57h+var_94], 278h
0x180005791  jmp     loc_1800058BE
0x180005796  mov     [rbp+57h+var_54], ax
0x18000579a  lea     rax, [rbp+57h+cbData]
0x18000579e  mov     [rbp+57h+Type], r15d
0x1800057a2  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800057a7  lea     r9, [rbp+57h+Type]; lpType
0x1800057ab  lea     rax, [rbp+57h+var_8C]
0x1800057af  mov     [rbp+57h+cbData], 4
0x1800057b6  xor     r8d, r8d; lpReserved
0x1800057b9  mov     [rsp+0E0h+lpData], rax; lpData
0x1800057be  lea     rdx, aPriority; "Priority"
0x1800057c5  mov     rcx, rdi; hKey
0x1800057c8  call    cs:__imp_RegQueryValueExW
0x1800057ce  mov     ebx, eax
0x1800057d0  cmp     eax, 2
0x1800057d3  jz      short loc_18000582A
0x1800057d5  test    eax, eax
0x1800057d7  jle     short loc_1800057E2
0x1800057d9  movzx   ebx, ax
0x1800057dc  or      ebx, 80070000h
0x1800057e2  test    ebx, ebx
0x1800057e4  jns     short loc_1800057F2
0x1800057e6  mov     [rbp+57h+var_94], 28Ch
0x1800057ed  jmp     loc_1800058BE
0x1800057f2  cmp     [rbp+57h+Type], 4
0x1800057f6  jz      short loc_180005809
0x1800057f8  mov     ebx, 80070057h
0x1800057fd  mov     [rbp+57h+var_94], 28Eh
0x180005804  jmp     loc_1800058BE
0x180005809  mov     eax, dword ptr [rbp+57h+var_8C]
0x18000580c  cmp     eax, 0FFFFh
0x180005811  jbe     short loc_180005824
0x180005813  mov     ebx, 80070057h
0x180005818  mov     [rbp+57h+var_94], 290h
0x18000581f  jmp     loc_1800058BE
0x180005824  mov     [rbp+57h+var_52], ax
0x180005828  jmp     short loc_18000582E
0x18000582a  movzx   eax, [rbp+57h+var_52]
0x18000582e  test    byte ptr cs:xmmword_18001F260, 4
0x180005835  jz      short loc_180005865
0x180005837  movzx   ecx, [rbp+57h+var_54]
0x18000583b  mov     edx, 3Eh ; '>'
0x180005840  movzx   eax, ax
0x180005843  mov     r9, r14
0x180005846  mov     [rsp+0E0h+var_A8], eax
0x18000584a  mov     rax, qword ptr [rbp+57h+Data+8]
0x18000584e  mov     [rsp+0E0h+var_B0], ecx
0x180005852  mov     [rsp+0E0h+lpcbData], rax
0x180005857  mov     rax, qword ptr [rbp+57h+var_50+8]
0x18000585b  mov     [rsp+0E0h+lpData], rax
0x180005860  call    WPP_SF_SSidd
0x180005865  lea     rdx, [rbp+57h+Data]
0x180005869  mov     ecx, 1
0x18000586e  call    ZtValidateTrustedServers
0x180005873  mov     ebx, eax
0x180005875  test    eax, eax
0x180005877  jle     short loc_180005882
0x180005879  movzx   ebx, ax
0x18000587c  or      ebx, 80070000h
0x180005882  test    ebx, ebx
0x180005884  jns     short loc_18000588F
0x180005886  mov     [rbp+57h+var_94], 2A1h
0x18000588d  jmp     short loc_1800058BE
0x18000588f  movaps  xmm0, xmmword ptr [rbp+57h+Data]
0x180005893  lea     rax, [rbp+57h+Data]
0x180005897  movaps  xmm1, [rbp+57h+var_70]
0x18000589b  movaps  xmmword ptr [rsi], xmm0
0x18000589e  movaps  xmm0, xmmword ptr [rbp-9]
0x1800058a2  movaps  xmmword ptr [rsi+10h], xmm1
0x1800058a6  movaps  xmm1, [rbp+57h+var_50]
0x1800058aa  movaps  xmmword ptr [rsi+20h], xmm0
0x1800058ae  movaps  xmmword ptr [rsi+30h], xmm1
0x1800058b2  mov     [rax], r15b
0x1800058b5  inc     rax
0x1800058b8  sub     r12, 1
0x1800058bc  jnz     short loc_1800058B2
0x1800058be  mov     rcx, r15; lpMem
0x1800058c1  call    Dns_Free
0x1800058c6  lea     rcx, [rbp+57h+Data]
0x1800058ca  call    DnsFreeZtTrustedServerMembers
0x1800058cf  test    byte ptr cs:xmmword_18001F260, 4
0x1800058d6  jz      short loc_1800058F8
0x1800058d8  mov     ecx, ebx
0x1800058da  call    WX_WIN32_FROM_HR
0x1800058df  mov     r9d, eax
0x1800058e2  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x1800058e9  mov     edx, 3Fh ; '?'
0x1800058ee  mov     ecx, 402h
0x1800058f3  call    WPP_SF_d
0x1800058f8  mov     ecx, ebx
0x1800058fa  call    WX_WIN32_FROM_HR
0x1800058ff  mov     rcx, [rbp+57h+var_40]
0x180005903  xor     rcx, rsp; StackCookie
0x180005906  call    __security_check_cookie
0x18000590b  add     rsp, 0B0h
0x180005912  pop     r15
0x180005914  pop     r14
0x180005916  pop     r12
0x180005918  pop     rdi
0x180005919  pop     rsi
0x18000591a  pop     rbx
0x18000591b  pop     rbp
0x18000591c  retn
```
