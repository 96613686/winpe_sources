# CVaultConfiguration::ReadConfiguration(VaultConfigType)

- ea: `0x180002494`
- end: `0x180002609`
- name: `?ReadConfiguration@CVaultConfiguration@@SAXW4VaultConfigType@@@Z`
- size: `373`
- prototype: `LSTATUS __fastcall(DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001aa0`

## callees

- `0x180002494`
- `0x18003b8a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002578`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002578`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800024cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800024cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
LSTATUS __fastcall CVaultConfiguration::ReadConfiguration(DWORD a1)
{
  LSTATUS result; // eax
  __int64 v2; // rdi
  unsigned __int64 i; // rbx
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  int v6; // eax
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  Type = a1;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Vault", 0, 0x20019u, &hKey);
  if ( !result )
  {
    v2 = 0;
    for ( i = 0; *(_DWORD *)((char *)&CVaultConfiguration::x_cfgValues + i * 4); i += 6LL )
    {
LABEL_18:
      if ( ++v2 == 9 )
        return RegCloseKey(hKey);
    }
    v4 = (&off_18004E710)[i / 2];
    Data = 0;
    Type = 0;
    cbData = 4;
    v5 = RegQueryValueExW(hKey, v4, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v5 )
    {
      if ( Type == 4 )
      {
        v6 = Data;
        if ( Data >= LODWORD(qword_18004E708[i / 2]) && Data <= HIDWORD(qword_18004E708[i / 2]) )
          goto LABEL_17;
        goto LABEL_16;
      }
      LOBYTE(v5) = 87;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_6b691a4982cb392c2bda4b5bed01ac0c_Traceguids,
        (unsigned int)(&off_18004E710)[i / 2],
        v5);
LABEL_16:
    v6 = dword_18004E704[i];
LABEL_17:
    *((_DWORD *)&CVaultConfiguration::m_vaultConfig + v2) = v6;
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return WPP_SF_SD(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             10,
             (unsigned int)WPP_6b691a4982cb392c2bda4b5bed01ac0c_Traceguids,
             (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Vault",
             result);
  return result;
}

```

## disassembly

```asm
0x180002494  mov     [rsp-28h+Type], ecx
0x180002498  push    rbp
0x180002499  push    rbx
0x18000249a  push    rsi
0x18000249b  push    rdi
0x18000249c  push    r14
0x18000249e  mov     rbp, rsp
0x1800024a1  sub     rsp, 30h
0x1800024a5  lea     rax, [rbp+hKey]
0x1800024a9  mov     [rbp+hKey], 0
0x1800024b1  mov     r9d, 20019h; samDesired
0x1800024b7  mov     [rsp+30h+phkResult], rax; phkResult
0x1800024bc  xor     r8d, r8d; ulOptions
0x1800024bf  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800024c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800024cd  call    cs:__imp_RegOpenKeyExW
0x1800024d3  test    eax, eax
0x1800024d5  jz      short loc_18000251D
0x1800024d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024de  lea     rsi, WPP_GLOBAL_Control
0x1800024e5  cmp     rcx, rsi
0x1800024e8  jz      short loc_1800024F0
0x1800024ea  test    byte ptr [rcx+1Ch], 4
0x1800024ee  jnz     short loc_1800024FB
0x1800024f0  add     rsp, 30h
0x1800024f4  pop     r14
0x1800024f6  pop     rdi
0x1800024f7  pop     rsi
0x1800024f8  pop     rbx
0x1800024f9  pop     rbp
0x1800024fa  retn
0x1800024fb  mov     rcx, [rcx+10h]
0x1800024ff  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180002506  mov     edx, 0Ah
0x18000250b  mov     dword ptr [rsp+30h+phkResult], eax
0x18000250f  lea     r8, WPP_6b691a4982cb392c2bda4b5bed01ac0c_Traceguids
0x180002516  call    WPP_SF_SD
0x18000251b  jmp     short loc_1800024F0
0x18000251d  xor     edi, edi
0x18000251f  lea     rsi, WPP_GLOBAL_Control
0x180002526  xor     ebx, ebx
0x180002528  lea     r14, __ImageBase
0x18000252f  cmp     dword ptr [rbx+r14+4E700h], 0
0x180002538  jnz     loc_1800025E9
0x18000253e  mov     rdx, [rbx+r14+4E710h]; lpValueName
0x180002546  lea     rax, [rbp+cbData]
0x18000254a  mov     rcx, [rbp+hKey]; hKey
0x18000254e  lea     r9, [rbp+Type]; lpType
0x180002552  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180002557  xor     r8d, r8d; lpReserved
0x18000255a  lea     rax, [rbp+Data]
0x18000255e  mov     [rbp+Data], 0
0x180002565  mov     [rsp+30h+phkResult], rax; lpData
0x18000256a  mov     [rbp+Type], 0
0x180002571  mov     [rbp+cbData], 4
0x180002578  call    cs:__imp_RegQueryValueExW
0x18000257e  test    eax, eax
0x180002580  jnz     short loc_18000258D
0x180002582  cmp     [rbp+Type], 4
0x180002586  jz      short loc_1800025C2
0x180002588  mov     eax, 57h ; 'W'
0x18000258d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002594  cmp     rcx, rsi
0x180002597  jz      short loc_1800025D9
0x180002599  test    byte ptr [rcx+1Ch], 4
0x18000259d  jz      short loc_1800025D9
0x18000259f  mov     r9, [rbx+r14+4E710h]
0x1800025a7  lea     r8, WPP_6b691a4982cb392c2bda4b5bed01ac0c_Traceguids
0x1800025ae  mov     rcx, [rcx+10h]
0x1800025b2  mov     edx, 0Bh
0x1800025b7  mov     dword ptr [rsp+30h+phkResult], eax
0x1800025bb  call    WPP_SF_SD
0x1800025c0  jmp     short loc_1800025D9
0x1800025c2  mov     eax, [rbp+Data]
0x1800025c5  cmp     eax, [rbx+r14+4E708h]
0x1800025cd  jb      short loc_1800025D9
0x1800025cf  cmp     eax, [rbx+r14+4E70Ch]
0x1800025d7  jbe     short loc_1800025E1
0x1800025d9  mov     eax, [rbx+r14+4E704h]
0x1800025e1  mov     rva ?m_vaultConfig@CVaultConfiguration@@0V1@A[r14+rdi*4], eax; CVaultConfiguration CVaultConfiguration::m_vaultConfig ...
0x1800025e9  inc     rdi
0x1800025ec  add     rbx, 18h
0x1800025f0  cmp     rdi, 9
0x1800025f4  jnz     loc_18000252F
0x1800025fa  mov     rcx, [rbp+hKey]; hKey
0x1800025fe  call    cs:__imp_RegCloseKey
0x180002604  jmp     loc_1800024F0
```
