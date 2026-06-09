# mmGetProfileIntA

- ea: `0x180006a44`
- end: `0x180006bdf`
- name: `mmGetProfileIntA`
- size: `411`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009b20`
- `0x18000a060`

## callees

- `0x180001460`
- `0x180006a44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180006bae`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180006bae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006bbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006bbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180006b8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180006b8e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x180006b54`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x180006b54`

## pseudocode

```c
__int64 __fastcall mmGetProfileIntA(__int64 a1, const CHAR *a2, unsigned int a3)
{
  __int64 v4; // r10
  __int64 v6; // r8
  const char *v7; // r9
  __int64 v8; // rax
  CHAR *v9; // rcx
  bool v10; // zf
  CHAR *v11; // rax
  __int64 v12; // r8
  CHAR *v13; // rax
  __int64 v14; // r9
  CHAR *v15; // rcx
  const char *v16; // rax
  __int64 v17; // rdx
  CHAR *v18; // rax
  HKEY v19; // rbx
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD Type[4]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF

  Type[0] = 0;
  *(_DWORD *)Data = 0;
  v4 = 2147483646;
  cbData = 0;
  phkResult = 0;
  v6 = 260;
  v7 = "Software\\Microsoft\\Multimedia\\";
  v8 = 2147483646;
  v9 = SubKey;
  do
  {
    if ( !v8 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v8;
    --v6;
  }
  while ( v6 );
  v10 = v6 == 0;
  v11 = v9 - 1;
  v12 = 260;
  if ( !v10 )
    v11 = v9;
  *v11 = 0;
  v13 = SubKey;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = (260 - v12) & -(__int64)(v12 != 0);
  if ( v12 )
  {
    v15 = &SubKey[v14];
    v16 = "avifile";
    v17 = 260 - v14;
    if ( 260 != v14 )
    {
      do
      {
        if ( !v4 )
          break;
        if ( !*v16 )
          break;
        *v15++ = *v16++;
        --v4;
        --v17;
      }
      while ( v17 );
    }
    v18 = v15 - 1;
    if ( v17 )
      v18 = v15;
    *v18 = 0;
  }
  RegOpenKeyA(HKEY_CURRENT_USER, SubKey, &phkResult);
  v19 = phkResult;
  if ( phkResult )
  {
    cbData = 4;
    if ( !RegQueryValueExA(phkResult, a2, 0, Type, Data, &cbData) )
    {
      if ( Type[0] - 3 <= 1 )
      {
        a3 = *(_DWORD *)Data;
      }
      else if ( Type[0] == 1 )
      {
        a3 = atoi((const char *)Data);
      }
    }
    RegCloseKey(v19);
  }
  return a3;
}

```

## disassembly

```asm
0x180006a44  push    rbp
0x180006a46  push    rbx
0x180006a47  push    rsi
0x180006a48  push    rdi
0x180006a49  lea     rbp, [rsp-78h]
0x180006a4e  sub     rsp, 178h
0x180006a55  mov     rax, cs:__security_cookie
0x180006a5c  xor     rax, rsp
0x180006a5f  mov     [rbp+90h+var_30], rax
0x180006a63  mov     rsi, rdx
0x180006a66  mov     [rsp+190h+Type], 0
0x180006a6e  mov     edx, 104h
0x180006a73  mov     dword ptr [rsp+190h+Data], 0
0x180006a7b  mov     r10d, 7FFFFFFEh
0x180006a81  mov     [rsp+190h+cbData], 0
0x180006a89  mov     edi, r8d
0x180006a8c  mov     [rsp+190h+phkResult], 0
0x180006a95  mov     r8d, edx
0x180006a98  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Multimedia\\"
0x180006a9f  mov     eax, r10d
0x180006aa2  lea     rcx, [rsp+190h+SubKey]
0x180006aa7  test    rax, rax
0x180006aaa  jz      short loc_180006AC6
0x180006aac  mov     r11b, [r9]
0x180006aaf  test    r11b, r11b
0x180006ab2  jz      short loc_180006AC6
0x180006ab4  mov     [rcx], r11b
0x180006ab7  inc     r9
0x180006aba  inc     rcx
0x180006abd  dec     rax
0x180006ac0  sub     r8, 1
0x180006ac4  jnz     short loc_180006AA7
0x180006ac6  test    r8, r8
0x180006ac9  lea     rax, [rcx-1]
0x180006acd  mov     r8, rdx
0x180006ad0  cmovnz  rax, rcx
0x180006ad4  mov     byte ptr [rax], 0
0x180006ad7  lea     rax, [rsp+190h+SubKey]
0x180006adc  cmp     byte ptr [rax], 0
0x180006adf  jz      short loc_180006AEA
0x180006ae1  inc     rax
0x180006ae4  sub     r8, 1
0x180006ae8  jnz     short loc_180006ADC
0x180006aea  mov     rcx, rdx
0x180006aed  mov     rax, r8
0x180006af0  sub     rcx, r8
0x180006af3  neg     rax
0x180006af6  sbb     r9, r9
0x180006af9  and     r9, rcx
0x180006afc  test    r8, r8
0x180006aff  jz      short loc_180006B43
0x180006b01  lea     rcx, [rsp+190h+SubKey]
0x180006b06  lea     rcx, [rcx+r9]
0x180006b0a  lea     rax, aAvifile; "avifile"
0x180006b11  sub     rdx, r9
0x180006b14  jz      short loc_180006B35
0x180006b16  test    r10, r10
0x180006b19  jz      short loc_180006B35
0x180006b1b  mov     r8b, [rax]
0x180006b1e  test    r8b, r8b
0x180006b21  jz      short loc_180006B35
0x180006b23  mov     [rcx], r8b
0x180006b26  inc     rax
0x180006b29  inc     rcx
0x180006b2c  dec     r10
0x180006b2f  sub     rdx, 1
0x180006b33  jnz     short loc_180006B16
0x180006b35  test    rdx, rdx
0x180006b38  lea     rax, [rcx-1]
0x180006b3c  cmovnz  rax, rcx
0x180006b40  mov     byte ptr [rax], 0
0x180006b43  lea     r8, [rsp+190h+phkResult]; phkResult
0x180006b48  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006b4f  lea     rdx, [rsp+190h+SubKey]; lpSubKey
0x180006b54  call    cs:__imp_RegOpenKeyA
0x180006b5a  mov     rbx, [rsp+190h+phkResult]
0x180006b5f  test    rbx, rbx
0x180006b62  jz      short loc_180006BC5
0x180006b64  lea     rax, [rsp+190h+cbData]
0x180006b69  mov     [rsp+190h+cbData], 4
0x180006b71  mov     [rsp+190h+lpcbData], rax; lpcbData
0x180006b76  lea     r9, [rsp+190h+Type]; lpType
0x180006b7b  lea     rax, [rsp+190h+Data]
0x180006b80  xor     r8d, r8d; lpReserved
0x180006b83  mov     rdx, rsi; lpValueName
0x180006b86  mov     [rsp+190h+lpData], rax; lpData
0x180006b8b  mov     rcx, rbx; hKey
0x180006b8e  call    cs:__imp_RegQueryValueExA
0x180006b94  test    eax, eax
0x180006b96  jnz     short loc_180006BBC
0x180006b98  mov     ecx, [rsp+190h+Type]
0x180006b9c  lea     eax, [rcx-3]
0x180006b9f  cmp     eax, 1
0x180006ba2  jbe     short loc_180006BB8
0x180006ba4  cmp     ecx, 1
0x180006ba7  jnz     short loc_180006BBC
0x180006ba9  lea     rcx, [rsp+190h+Data]; String
0x180006bae  call    cs:__imp_atoi
0x180006bb4  mov     edi, eax
0x180006bb6  jmp     short loc_180006BBC
0x180006bb8  mov     edi, dword ptr [rsp+190h+Data]
0x180006bbc  mov     rcx, rbx; hKey
0x180006bbf  call    cs:__imp_RegCloseKey
0x180006bc5  mov     eax, edi
0x180006bc7  mov     rcx, [rbp+90h+var_30]
0x180006bcb  xor     rcx, rsp; StackCookie
0x180006bce  call    __security_check_cookie
0x180006bd3  add     rsp, 178h
0x180006bda  pop     rdi
0x180006bdb  pop     rsi
0x180006bdc  pop     rbx
0x180006bdd  pop     rbp
0x180006bde  retn
```
