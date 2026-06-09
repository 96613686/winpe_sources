# ZtSetTrustedDotServer

- ea: `0x1800066f4`
- end: `0x18000693a`
- name: `ZtSetTrustedDotServer`
- size: `582`
- prototype: `__int64 __fastcall(__int64, HKEY, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006940`

## callees

- `0x1800066f4`
- `0x18000e344`
- `0x180015008`
- `0x180015398`
- `0x1800154c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006841`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006841`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800067d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006817`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006884`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800068b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800067d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006817`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006884`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800068b5`

## pseudocode

```c
__int64 __fastcall ZtSetTrustedDotServer(__int64 a1, HKEY a2, __int64 a3)
{
  DWORD cbData; // ebx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  const wchar_t *v9; // rbp
  LSTATUS v10; // eax
  USHORT v11; // dx
  LSTATUS v12; // eax
  DWORD v14; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+80h] [rbp+18h] BYREF
  int lpData; // [rsp+88h] [rbp+20h] BYREF

  lpData = 0xFFFF;
  cbData = 0;
  Data = 0;
  v14 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qq(1026, 0x2Au, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, a1, a2);
  if ( !a1 || !a2 )
  {
    v6 = 87;
    goto LABEL_26;
  }
  v7 = *(_QWORD *)(a1 + 56);
  if ( !v7 )
  {
LABEL_11:
    v9 = L"DotHostname";
    v10 = RegSetValueExW(a2, L"DotHostname", 0, 1u, *(const BYTE **)(a1 + 56), cbData);
    v6 = v10;
    if ( !v10 )
    {
      if ( *(_WORD *)(a1 + 44) )
      {
        v9 = L"DotPort";
        Data = *(unsigned __int16 *)(a1 + 44);
        v10 = RegSetValueExW(a2, L"DotPort", 0, 4u, (const BYTE *)&Data, 4u);
        v6 = v10;
        if ( v10 )
        {
          if ( (xmmword_18001F260 & 4) == 0 )
            return v6;
          v11 = 45;
          goto LABEL_25;
        }
      }
      else
      {
        v6 = RegDeleteValueW(a2, L"DotPort");
        if ( (v6 & 0xFFFFFFFD) != 0 )
          goto LABEL_26;
      }
      v9 = L"Priority";
      lpData = *(unsigned __int16 *)(a1 + 46);
      v10 = RegSetValueExW(a2, L"Priority", 0, 4u, (const BYTE *)&lpData, 4u);
      v6 = v10;
      if ( !v10 )
      {
        v12 = RegSetValueExW(a2, L"DotFlags", 0, 0xBu, (const BYTE *)(a1 + 8), 8u);
        v6 = v12;
        if ( v12 )
        {
          if ( (xmmword_18001F260 & 4) == 0 )
            return v6;
          WPP_SF_DS(1026, 0x2Fu, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v12, L"DotFlags");
        }
        goto LABEL_26;
      }
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      v11 = 46;
      goto LABEL_25;
    }
    if ( (xmmword_18001F260 & 4) == 0 )
      return v6;
    v11 = 44;
LABEL_25:
    WPP_SF_DS(1026, v11, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v10, v9);
    goto LABEL_26;
  }
  v8 = Dns_CheckedStringLengthBytes(v7, 0xFFFFFFFFLL, a3, &v14);
  v6 = v8;
  if ( !v8 )
  {
    cbData = v14;
    goto LABEL_11;
  }
  if ( (xmmword_18001F260 & 4) == 0 )
    return v6;
  WPP_SF_d(1026, 0x2Bu, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v8);
LABEL_26:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x30u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800066f4  mov     rax, rsp
0x1800066f7  mov     [rax+10h], rbx
0x1800066fb  push    rbp
0x1800066fc  push    rsi
0x1800066fd  push    rdi
0x1800066fe  push    r12
0x180006700  push    r13
0x180006702  push    r14
0x180006704  push    r15
0x180006706  sub     rsp, 30h
0x18000670a  xor     r15d, r15d
0x18000670d  mov     dword ptr [rax+20h], 0FFFFh
0x180006714  mov     ebx, r15d
0x180006717  mov     [rax+18h], r15d
0x18000671b  mov     [rax+8], ebx
0x18000671e  mov     rsi, rdx
0x180006721  mov     rdi, rcx
0x180006724  lea     r14d, [r15+4]
0x180006728  mov     r12d, 402h
0x18000672e  test    byte ptr cs:xmmword_18001F260, r14b
0x180006735  lea     r13, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x18000673c  jz      short loc_180006754
0x18000673e  lea     edx, [r15+2Ah]
0x180006742  mov     [rax-48h], rsi
0x180006746  mov     ecx, r12d
0x180006749  mov     r9, rdi
0x18000674c  mov     r8, r13
0x18000674f  call    WPP_SF_qq
0x180006754  test    rdi, rdi
0x180006757  jnz     short loc_180006763
0x180006759  mov     ebx, 57h ; 'W'
0x18000675e  jmp     loc_180006907
0x180006763  test    rsi, rsi
0x180006766  jz      short loc_180006759
0x180006768  mov     rcx, [rdi+38h]
0x18000676c  test    rcx, rcx
0x18000676f  jz      short loc_1800067AD
0x180006771  lea     r9, [rsp+68h+arg_0]
0x180006776  or      edx, 0FFFFFFFFh
0x180006779  call    Dns_CheckedStringLengthBytes
0x18000677e  mov     ebx, eax
0x180006780  test    eax, eax
0x180006782  jz      short loc_1800067A9
0x180006784  test    byte ptr cs:xmmword_18001F260, r14b
0x18000678b  jz      loc_180006923
0x180006791  mov     edx, 2Bh ; '+'
0x180006796  mov     ecx, r12d
0x180006799  mov     r9d, eax
0x18000679c  mov     r8, r13
0x18000679f  call    WPP_SF_d
0x1800067a4  jmp     loc_180006907
0x1800067a9  mov     ebx, [rsp+68h+arg_0]
0x1800067ad  mov     rax, [rdi+38h]
0x1800067b1  lea     rbp, aDothostname; "DotHostname"
0x1800067b8  mov     rdx, rbp; lpValueName
0x1800067bb  mov     [rsp+68h+cbData], ebx; cbData
0x1800067bf  mov     r9d, 1; dwType
0x1800067c5  mov     [rsp+68h+lpData], rax; lpData
0x1800067ca  xor     r8d, r8d; Reserved
0x1800067cd  mov     rcx, rsi; hKey
0x1800067d0  call    cs:__imp_RegSetValueExW
0x1800067d6  mov     ebx, eax
0x1800067d8  test    eax, eax
0x1800067da  jnz     loc_1800068E6
0x1800067e0  mov     rcx, rsi; hKey
0x1800067e3  cmp     [rdi+2Ch], r15w
0x1800067e8  jz      short loc_18000683A
0x1800067ea  movzx   eax, word ptr [rdi+2Ch]
0x1800067ee  lea     rbp, aDotport; "DotPort"
0x1800067f5  mov     [rsp+68h+Data], eax
0x1800067fc  mov     r9d, r14d; dwType
0x1800067ff  lea     rax, [rsp+68h+Data]
0x180006807  mov     [rsp+68h+cbData], r14d; cbData
0x18000680c  xor     r8d, r8d; Reserved
0x18000680f  mov     [rsp+68h+lpData], rax; lpData
0x180006814  mov     rdx, rbp; lpValueName
0x180006817  call    cs:__imp_RegSetValueExW
0x18000681d  mov     ebx, eax
0x18000681f  test    eax, eax
0x180006821  jz      short loc_180006854
0x180006823  test    byte ptr cs:xmmword_18001F260, r14b
0x18000682a  jz      loc_180006923
0x180006830  mov     edx, 2Dh ; '-'
0x180006835  jmp     loc_1800068F4
0x18000683a  lea     rdx, aDotport; "DotPort"
0x180006841  call    cs:__imp_RegDeleteValueW
0x180006847  mov     ebx, eax
0x180006849  test    eax, 0FFFFFFFDh
0x18000684e  jnz     loc_180006907
0x180006854  movzx   eax, word ptr [rdi+2Eh]
0x180006858  lea     rbp, aPriority; "Priority"
0x18000685f  mov     [rsp+68h+arg_18], eax
0x180006866  mov     r9d, r14d; dwType
0x180006869  lea     rax, [rsp+68h+arg_18]
0x180006871  mov     [rsp+68h+cbData], r14d; cbData
0x180006876  xor     r8d, r8d; Reserved
0x180006879  mov     [rsp+68h+lpData], rax; lpData
0x18000687e  mov     rdx, rbp; lpValueName
0x180006881  mov     rcx, rsi; hKey
0x180006884  call    cs:__imp_RegSetValueExW
0x18000688a  mov     ebx, eax
0x18000688c  test    eax, eax
0x18000688e  jnz     short loc_1800068D6
0x180006890  lea     rax, [rdi+8]
0x180006894  mov     [rsp+68h+cbData], 8; cbData
0x18000689c  lea     rdi, aDotflags; "DotFlags"
0x1800068a3  mov     [rsp+68h+lpData], rax; lpData
0x1800068a8  mov     rdx, rdi; lpValueName
0x1800068ab  lea     r9d, [rbx+0Bh]; dwType
0x1800068af  xor     r8d, r8d; Reserved
0x1800068b2  mov     rcx, rsi; hKey
0x1800068b5  call    cs:__imp_RegSetValueExW
0x1800068bb  mov     ebx, eax
0x1800068bd  test    eax, eax
0x1800068bf  jz      short loc_180006907
0x1800068c1  test    byte ptr cs:xmmword_18001F260, r14b
0x1800068c8  jz      short loc_180006923
0x1800068ca  mov     edx, 2Fh ; '/'
0x1800068cf  mov     [rsp+68h+lpData], rdi
0x1800068d4  jmp     short loc_1800068F9
0x1800068d6  test    byte ptr cs:xmmword_18001F260, r14b
0x1800068dd  jz      short loc_180006923
0x1800068df  mov     edx, 2Eh ; '.'
0x1800068e4  jmp     short loc_1800068F4
0x1800068e6  test    byte ptr cs:xmmword_18001F260, r14b
0x1800068ed  jz      short loc_180006923
0x1800068ef  mov     edx, 2Ch ; ','
0x1800068f4  mov     [rsp+68h+lpData], rbp
0x1800068f9  mov     r9d, eax
0x1800068fc  mov     r8, r13
0x1800068ff  mov     ecx, r12d
0x180006902  call    WPP_SF_DS
0x180006907  test    byte ptr cs:xmmword_18001F260, r14b
0x18000690e  jz      short loc_180006923
0x180006910  mov     edx, 30h ; '0'
0x180006915  mov     ecx, r12d
0x180006918  mov     r9d, ebx
0x18000691b  mov     r8, r13
0x18000691e  call    WPP_SF_d
0x180006923  mov     eax, ebx
0x180006925  mov     rbx, [rsp+68h+arg_8]
0x18000692a  add     rsp, 30h
0x18000692e  pop     r15
0x180006930  pop     r14
0x180006932  pop     r13
0x180006934  pop     r12
0x180006936  pop     rdi
0x180006937  pop     rsi
0x180006938  pop     rbp
0x180006939  retn
```
