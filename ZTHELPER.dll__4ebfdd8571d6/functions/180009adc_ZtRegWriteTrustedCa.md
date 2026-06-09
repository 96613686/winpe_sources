# ZtRegWriteTrustedCa

- ea: `0x180009adc`
- end: `0x180009d10`
- name: `ZtRegWriteTrustedCa`
- size: `564`
- prototype: `__int64 __fastcall(__int64, __int64, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005134`

## callees

- `0x180009adc`
- `0x18000cdd8`
- `0x18000cee8`
- `0x1800125d4`
- `0x180015008`
- `0x180015094`
- `0x1800154c8`
- `0x180015864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cf4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009bd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009c47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009bd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009c47`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180009ba2`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180009ba2`

## pseudocode

```c
__int64 __fastcall ZtRegWriteTrustedCa(__int64 a1, __int64 a2, HKEY a3)
{
  unsigned int v6; // ebx
  int Key; // eax
  LSTATUS v8; // eax
  USHORT v9; // dx
  USHORT v10; // dx
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  int v13; // [rsp+90h] [rbp+30h] BYREF
  BYTE *lpData; // [rsp+A8h] [rbp+48h] BYREF

  hKey[0] = 0;
  lpData = 0;
  v13 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 0xEu, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, a1);
  if ( !a1 )
  {
    v6 = 87;
    goto LABEL_23;
  }
  Key = DnsRegDeleteTree(a3, L"ZtTrustedCa");
  v6 = Key;
  if ( Key )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_23;
    v10 = 15;
    goto LABEL_22;
  }
  if ( !*(_QWORD *)(a1 + 16) )
    goto LABEL_23;
  Key = RegCreateKeyExInternalW(a3, L"ZtTrustedCa", 0, 0, 0, 196639, 0, hKey, 0, a2);
  v6 = Key;
  if ( Key )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_23;
    v10 = 16;
LABEL_22:
    WPP_SF_d(1026, v10, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, Key);
    goto LABEL_23;
  }
  v8 = RegSetValueExW(hKey[0], L"Flags", 0, 0xBu, (const BYTE *)(a1 + 8), 8u);
  v6 = v8;
  if ( v8 )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_23;
    v9 = 17;
    goto LABEL_17;
  }
  v6 = DnsZtCertHashListToString(*(_QWORD *)(a1 + 16), *(unsigned int *)(a1 + 24), &lpData, &v13);
  if ( !v6 )
  {
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_S(1026, 0x12u, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, (const wchar_t *)lpData);
    v8 = RegSetValueExW(hKey[0], L"CertHashes", 0, 1u, lpData, 2 * v13);
    v6 = v8;
    if ( v8 )
    {
      if ( (xmmword_18001F260 & 4) != 0 )
      {
        v9 = 19;
LABEL_17:
        WPP_SF_DS(1026, v9, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, v8, L"Flags");
      }
    }
  }
LABEL_23:
  Dns_Free(lpData);
  lpData = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x14u, (ULONGLONG)WPP_2074faa7941838f94d01dce17c4721b7_Traceguids, v6);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v6;
}

```

## disassembly

```asm
0x180009adc  mov     [rsp-28h+arg_8], rbx
0x180009ae1  push    rbp
0x180009ae2  push    rsi
0x180009ae3  push    rdi
0x180009ae4  push    r13
0x180009ae6  push    r14
0x180009ae8  mov     rbp, rsp
0x180009aeb  sub     rsp, 60h
0x180009aef  mov     rsi, r8
0x180009af2  mov     [rbp+hKey], 0
0x180009afa  mov     r14, rdx
0x180009afd  mov     [rbp+arg_18], 0
0x180009b05  mov     rdi, rcx
0x180009b08  mov     [rbp+arg_0], 0
0x180009b0f  test    byte ptr cs:xmmword_18001F260, 4
0x180009b16  mov     r13d, 402h
0x180009b1c  jz      short loc_180009B35
0x180009b1e  mov     edx, 0Eh
0x180009b23  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009b2a  mov     ecx, r13d
0x180009b2d  mov     r9, rdi
0x180009b30  call    WPP_SF_q
0x180009b35  test    rdi, rdi
0x180009b38  jnz     short loc_180009B42
0x180009b3a  lea     ebx, [rdi+57h]
0x180009b3d  jmp     loc_180009CBA
0x180009b42  lea     rdx, aZttrustedca; "ZtTrustedCa"
0x180009b49  mov     rcx, rsi; hKey
0x180009b4c  call    DnsRegDeleteTree
0x180009b51  mov     ebx, eax
0x180009b53  test    eax, eax
0x180009b55  jnz     loc_180009C9A
0x180009b5b  cmp     qword ptr [rdi+10h], 0
0x180009b60  jz      loc_180009CBA
0x180009b66  mov     [rsp+60h+var_18], r14
0x180009b6b  lea     rax, [rbp+hKey]
0x180009b6f  mov     [rsp+60h+var_20], 0
0x180009b78  lea     rdx, aZttrustedca; "ZtTrustedCa"
0x180009b7f  mov     [rsp+60h+var_28], rax
0x180009b84  xor     r9d, r9d
0x180009b87  mov     [rsp+60h+var_30], 0
0x180009b90  xor     r8d, r8d
0x180009b93  mov     [rsp+60h+cbData], 3001Fh
0x180009b9b  mov     rcx, rsi
0x180009b9e  mov     dword ptr [rsp+60h+lpData], ebx
0x180009ba2  call    cs:__imp_RegCreateKeyExInternalW
0x180009ba8  mov     ebx, eax
0x180009baa  test    eax, eax
0x180009bac  jnz     loc_180009C8A
0x180009bb2  mov     rcx, [rbp+hKey]; hKey
0x180009bb6  lea     rax, [rdi+8]
0x180009bba  lea     rsi, aFlags; "Flags"
0x180009bc1  mov     [rsp+60h+cbData], 8; cbData
0x180009bc9  mov     rdx, rsi; lpValueName
0x180009bcc  mov     [rsp+60h+lpData], rax; lpData
0x180009bd1  lea     r9d, [rbx+0Bh]; dwType
0x180009bd5  xor     r8d, r8d; Reserved
0x180009bd8  call    cs:__imp_RegSetValueExW
0x180009bde  mov     ebx, eax
0x180009be0  test    eax, eax
0x180009be2  jnz     short loc_180009C63
0x180009be4  mov     edx, [rdi+18h]
0x180009be7  lea     r9, [rbp+arg_0]
0x180009beb  mov     rcx, [rdi+10h]
0x180009bef  lea     r8, [rbp+arg_18]
0x180009bf3  call    DnsZtCertHashListToString
0x180009bf8  mov     ebx, eax
0x180009bfa  test    eax, eax
0x180009bfc  jnz     loc_180009CBA
0x180009c02  test    byte ptr cs:xmmword_18001F260, 4
0x180009c09  jz      short loc_180009C21
0x180009c0b  mov     r9, [rbp+arg_18]
0x180009c0f  lea     edx, [rax+12h]
0x180009c12  mov     ecx, r13d
0x180009c15  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009c1c  call    WPP_SF_S
0x180009c21  mov     rdx, [rbp+arg_18]
0x180009c25  mov     r9d, 1; dwType
0x180009c2b  mov     eax, [rbp+arg_0]
0x180009c2e  xor     r8d, r8d; Reserved
0x180009c31  mov     rcx, [rbp+hKey]; hKey
0x180009c35  add     eax, eax
0x180009c37  mov     [rsp+60h+cbData], eax; cbData
0x180009c3b  mov     [rsp+60h+lpData], rdx; lpData
0x180009c40  lea     rdx, aCerthashes; "CertHashes"
0x180009c47  call    cs:__imp_RegSetValueExW
0x180009c4d  mov     ebx, eax
0x180009c4f  test    eax, eax
0x180009c51  jz      short loc_180009CBA
0x180009c53  test    byte ptr cs:xmmword_18001F260, 4
0x180009c5a  jz      short loc_180009CBA
0x180009c5c  mov     edx, 13h
0x180009c61  jmp     short loc_180009C71
0x180009c63  test    byte ptr cs:xmmword_18001F260, 4
0x180009c6a  jz      short loc_180009CBA
0x180009c6c  mov     edx, 11h
0x180009c71  mov     ecx, r13d
0x180009c74  mov     [rsp+60h+lpData], rsi
0x180009c79  mov     r9d, eax
0x180009c7c  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009c83  call    WPP_SF_DS
0x180009c88  jmp     short loc_180009CBA
0x180009c8a  test    byte ptr cs:xmmword_18001F260, 4
0x180009c91  jz      short loc_180009CBA
0x180009c93  mov     edx, 10h
0x180009c98  jmp     short loc_180009CA8
0x180009c9a  test    byte ptr cs:xmmword_18001F260, 4
0x180009ca1  jz      short loc_180009CBA
0x180009ca3  mov     edx, 0Fh
0x180009ca8  mov     r9d, eax
0x180009cab  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009cb2  mov     ecx, r13d
0x180009cb5  call    WPP_SF_d
0x180009cba  mov     rcx, [rbp+arg_18]; lpMem
0x180009cbe  call    Dns_Free
0x180009cc3  mov     [rbp+arg_18], 0
0x180009ccb  test    byte ptr cs:xmmword_18001F260, 4
0x180009cd2  jz      short loc_180009CEB
0x180009cd4  mov     edx, 14h
0x180009cd9  lea     r8, WPP_2074faa7941838f94d01dce17c4721b7_Traceguids
0x180009ce0  mov     ecx, r13d
0x180009ce3  mov     r9d, ebx
0x180009ce6  call    WPP_SF_d
0x180009ceb  mov     rcx, [rbp+hKey]; hKey
0x180009cef  test    rcx, rcx
0x180009cf2  jz      short loc_180009CFA
0x180009cf4  call    cs:__imp_RegCloseKey
0x180009cfa  mov     eax, ebx
0x180009cfc  mov     rbx, [rsp+60h+arg_8]
0x180009d04  add     rsp, 60h
0x180009d08  pop     r14
0x180009d0a  pop     r13
0x180009d0c  pop     rdi
0x180009d0d  pop     rsi
0x180009d0e  pop     rbp
0x180009d0f  retn
```
