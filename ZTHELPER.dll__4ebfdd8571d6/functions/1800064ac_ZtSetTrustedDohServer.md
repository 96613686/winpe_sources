# ZtSetTrustedDohServer

- ea: `0x1800064ac`
- end: `0x1800066eb`
- name: `ZtSetTrustedDohServer`
- size: `575`
- prototype: `__int64 __fastcall(__int64, HKEY, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006940`

## callees

- `0x1800064ac`
- `0x18000e344`
- `0x180015008`
- `0x180015398`
- `0x1800154c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800065d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800065d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006563`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800065aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006617`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006648`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006563`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800065aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006617`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006648`

## string_xrefs

- `0x180006542`: `DohTemplate`

## pseudocode

```c
__int64 __fastcall ZtSetTrustedDohServer(__int64 a1, HKEY a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  const wchar_t *v8; // rbp
  LSTATUS v9; // eax
  USHORT v10; // dx
  LSTATUS v11; // eax
  DWORD cbData; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+80h] [rbp+18h] BYREF
  int lpData; // [rsp+88h] [rbp+20h] BYREF

  cbData = 0;
  Data = 0;
  lpData = 0xFFFF;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qq(1026, 0x23u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, a1, a2);
  if ( !a1 || (v6 = *(_QWORD *)(a1 + 56)) == 0 || !a2 )
  {
    v5 = 87;
    goto LABEL_26;
  }
  v7 = Dns_CheckedStringLengthBytes(v6, 0xFFFF, a3, &cbData);
  v5 = v7;
  if ( v7 )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      return v5;
    WPP_SF_d(1026, 0x24u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v7);
    goto LABEL_26;
  }
  v8 = L"DohTemplate";
  v9 = RegSetValueExW(a2, L"DohTemplate", 0, 1u, *(const BYTE **)(a1 + 56), cbData);
  v5 = v9;
  if ( !v9 )
  {
    if ( *(_WORD *)(a1 + 44) )
    {
      v8 = L"DohPort";
      Data = *(unsigned __int16 *)(a1 + 44);
      v9 = RegSetValueExW(a2, L"DohPort", 0, 4u, (const BYTE *)&Data, 4u);
      v5 = v9;
      if ( v9 )
      {
        if ( (xmmword_18001F260 & 4) == 0 )
          return v5;
        v10 = 38;
        goto LABEL_22;
      }
    }
    else
    {
      v5 = RegDeleteValueW(a2, L"DohPort");
      if ( (v5 & 0xFFFFFFFD) != 0 )
        goto LABEL_26;
    }
    v8 = L"Priority";
    lpData = *(unsigned __int16 *)(a1 + 46);
    v9 = RegSetValueExW(a2, L"Priority", 0, 4u, (const BYTE *)&lpData, 4u);
    v5 = v9;
    if ( !v9 )
    {
      v11 = RegSetValueExW(a2, L"DohFlags", 0, 0xBu, (const BYTE *)(a1 + 8), 8u);
      v5 = v11;
      if ( v11 )
      {
        if ( (xmmword_18001F260 & 4) == 0 )
          return v5;
        WPP_SF_DS(1026, 0x28u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v11, L"DohFlags");
      }
      goto LABEL_26;
    }
    if ( (xmmword_18001F260 & 4) == 0 )
      return v5;
    v10 = 39;
    goto LABEL_22;
  }
  if ( (xmmword_18001F260 & 4) == 0 )
    return v5;
  v10 = 37;
LABEL_22:
  WPP_SF_DS(1026, v10, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v9, v8);
LABEL_26:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x29u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800064ac  mov     rax, rsp
0x1800064af  mov     [rax+10h], rbx
0x1800064b3  push    rbp
0x1800064b4  push    rsi
0x1800064b5  push    rdi
0x1800064b6  push    r12
0x1800064b8  push    r13
0x1800064ba  push    r14
0x1800064bc  push    r15
0x1800064be  sub     rsp, 30h
0x1800064c2  xor     r15d, r15d
0x1800064c5  mov     ebx, 0FFFFh
0x1800064ca  mov     [rax+8], r15d
0x1800064ce  mov     rsi, rdx
0x1800064d1  mov     [rax+18h], r15d
0x1800064d5  mov     rdi, rcx
0x1800064d8  mov     [rax+20h], ebx
0x1800064db  lea     r14d, [r15+4]
0x1800064df  mov     r12d, 402h
0x1800064e5  test    byte ptr cs:xmmword_18001F260, r14b
0x1800064ec  lea     r13, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x1800064f3  jz      short loc_18000650B
0x1800064f5  lea     edx, [r15+23h]
0x1800064f9  mov     [rax-48h], rsi
0x1800064fd  mov     ecx, r12d
0x180006500  mov     r9, rdi
0x180006503  mov     r8, r13
0x180006506  call    WPP_SF_qq
0x18000650b  test    rdi, rdi
0x18000650e  jnz     short loc_18000651A
0x180006510  mov     ebx, 57h ; 'W'
0x180006515  jmp     loc_1800066B8
0x18000651a  mov     rcx, [rdi+38h]
0x18000651e  test    rcx, rcx
0x180006521  jz      short loc_180006510
0x180006523  test    rsi, rsi
0x180006526  jz      short loc_180006510
0x180006528  lea     r9, [rsp+68h+arg_0]
0x18000652d  mov     edx, ebx
0x18000652f  call    Dns_CheckedStringLengthBytes
0x180006534  mov     ebx, eax
0x180006536  test    eax, eax
0x180006538  jnz     loc_18000669C
0x18000653e  mov     eax, [rsp+68h+arg_0]
0x180006542  lea     rbp, aDohtemplate; "DohTemplate"
0x180006549  mov     [rsp+68h+cbData], eax; cbData
0x18000654d  lea     r9d, [rbx+1]; dwType
0x180006551  mov     rax, [rdi+38h]
0x180006555  xor     r8d, r8d; Reserved
0x180006558  mov     rdx, rbp; lpValueName
0x18000655b  mov     [rsp+68h+lpData], rax; lpData
0x180006560  mov     rcx, rsi; hKey
0x180006563  call    cs:__imp_RegSetValueExW
0x180006569  mov     ebx, eax
0x18000656b  test    eax, eax
0x18000656d  jnz     loc_180006679
0x180006573  mov     rcx, rsi; hKey
0x180006576  cmp     [rdi+2Ch], r15w
0x18000657b  jz      short loc_1800065CD
0x18000657d  movzx   eax, word ptr [rdi+2Ch]
0x180006581  lea     rbp, aDohport; "DohPort"
0x180006588  mov     [rsp+68h+Data], eax
0x18000658f  mov     r9d, r14d; dwType
0x180006592  lea     rax, [rsp+68h+Data]
0x18000659a  mov     [rsp+68h+cbData], r14d; cbData
0x18000659f  xor     r8d, r8d; Reserved
0x1800065a2  mov     [rsp+68h+lpData], rax; lpData
0x1800065a7  mov     rdx, rbp; lpValueName
0x1800065aa  call    cs:__imp_RegSetValueExW
0x1800065b0  mov     ebx, eax
0x1800065b2  test    eax, eax
0x1800065b4  jz      short loc_1800065E7
0x1800065b6  test    byte ptr cs:xmmword_18001F260, r14b
0x1800065bd  jz      loc_1800066D4
0x1800065c3  mov     edx, 26h ; '&'
0x1800065c8  jmp     loc_180006687
0x1800065cd  lea     rdx, aDohport; "DohPort"
0x1800065d4  call    cs:__imp_RegDeleteValueW
0x1800065da  mov     ebx, eax
0x1800065dc  test    eax, 0FFFFFFFDh
0x1800065e1  jnz     loc_1800066B8
0x1800065e7  movzx   eax, word ptr [rdi+2Eh]
0x1800065eb  lea     rbp, aPriority; "Priority"
0x1800065f2  mov     [rsp+68h+arg_18], eax
0x1800065f9  mov     r9d, r14d; dwType
0x1800065fc  lea     rax, [rsp+68h+arg_18]
0x180006604  mov     [rsp+68h+cbData], r14d; cbData
0x180006609  xor     r8d, r8d; Reserved
0x18000660c  mov     [rsp+68h+lpData], rax; lpData
0x180006611  mov     rdx, rbp; lpValueName
0x180006614  mov     rcx, rsi; hKey
0x180006617  call    cs:__imp_RegSetValueExW
0x18000661d  mov     ebx, eax
0x18000661f  test    eax, eax
0x180006621  jnz     short loc_180006669
0x180006623  lea     rax, [rdi+8]
0x180006627  mov     [rsp+68h+cbData], 8; cbData
0x18000662f  lea     rdi, aDohflags; "DohFlags"
0x180006636  mov     [rsp+68h+lpData], rax; lpData
0x18000663b  mov     rdx, rdi; lpValueName
0x18000663e  lea     r9d, [rbx+0Bh]; dwType
0x180006642  xor     r8d, r8d; Reserved
0x180006645  mov     rcx, rsi; hKey
0x180006648  call    cs:__imp_RegSetValueExW
0x18000664e  mov     ebx, eax
0x180006650  test    eax, eax
0x180006652  jz      short loc_1800066B8
0x180006654  test    byte ptr cs:xmmword_18001F260, r14b
0x18000665b  jz      short loc_1800066D4
0x18000665d  mov     edx, 28h ; '('
0x180006662  mov     [rsp+68h+lpData], rdi
0x180006667  jmp     short loc_18000668C
0x180006669  test    byte ptr cs:xmmword_18001F260, r14b
0x180006670  jz      short loc_1800066D4
0x180006672  mov     edx, 27h ; '''
0x180006677  jmp     short loc_180006687
0x180006679  test    byte ptr cs:xmmword_18001F260, r14b
0x180006680  jz      short loc_1800066D4
0x180006682  mov     edx, 25h ; '%'
0x180006687  mov     [rsp+68h+lpData], rbp
0x18000668c  mov     ecx, r12d
0x18000668f  mov     r9d, eax
0x180006692  mov     r8, r13
0x180006695  call    WPP_SF_DS
0x18000669a  jmp     short loc_1800066B8
0x18000669c  test    byte ptr cs:xmmword_18001F260, r14b
0x1800066a3  jz      short loc_1800066D4
0x1800066a5  mov     edx, 24h ; '$'
0x1800066aa  mov     ecx, r12d
0x1800066ad  mov     r9d, eax
0x1800066b0  mov     r8, r13
0x1800066b3  call    WPP_SF_d
0x1800066b8  test    byte ptr cs:xmmword_18001F260, r14b
0x1800066bf  jz      short loc_1800066D4
0x1800066c1  mov     edx, 29h ; ')'
0x1800066c6  mov     ecx, r12d
0x1800066c9  mov     r9d, ebx
0x1800066cc  mov     r8, r13
0x1800066cf  call    WPP_SF_d
0x1800066d4  mov     eax, ebx
0x1800066d6  mov     rbx, [rsp+68h+arg_8]
0x1800066db  add     rsp, 30h
0x1800066df  pop     r15
0x1800066e1  pop     r14
0x1800066e3  pop     r13
0x1800066e5  pop     r12
0x1800066e7  pop     rdi
0x1800066e8  pop     rsi
0x1800066e9  pop     rbp
0x1800066ea  retn
```
