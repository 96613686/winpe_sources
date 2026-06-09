# IERegGetBoolWithPoliciesW(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800c4458`
- end: `0x1800c46c6`
- name: `?IERegGetBoolWithPoliciesW@@YAHPEBG00H@Z`
- size: `622`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c3f28`
- `0x1800c4204`

## callees

- `0x1800c4458`
- `0x18013f7d0`
- `0x1802084bc`

## import_xrefs

- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x1800c4564`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x1800c4564`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c45db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4640`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c45db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4640`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4514`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4590`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4514`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4590`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c45ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4616`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c45ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c4616`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c44c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c46b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c44c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c46b1`

## string_xrefs

- `0x1800c449b`: `Security_HKLM_Only`
- `0x1800c4556`: `Enable Browser Extensions`
- `0x1800c45c3`: `Enable Browser Extensions`
- `0x1800c460f`: `Enable Browser Extensions`
- `0x1800c467b`: `Enable Browser Extensions`

## pseudocode

```c
__int64 __fastcall IERegGetBoolWithPoliciesW(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // esi
  unsigned int v4; // edi
  LSTATUS v5; // ebx
  int v7; // eax
  int v8; // eax
  LSTATUS ValueW; // eax
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int16 Data[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  pvData = 0;
  pcbData = 4;
  cbData = 0;
  v10 = 1;
  Type = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Internet Explorer\\Main",
          L"Security_HKLM_Only",
          0x18u,
          0,
          &pvData,
          &pcbData) )
    v3 = pvData;
  phkResult = 0;
  v4 = 1;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 1u, &phkResult);
  if ( !v5 )
  {
    cbData = 520;
    v5 = RegQueryValueExW(phkResult, L"Enable Browser Extensions", 0, &Type, (LPBYTE)Data, &cbData);
    if ( !v5 )
    {
      v7 = IERegValueToBoolW(Type, Data, &v10);
      v4 = v10;
      v5 = v7;
    }
    RegCloseKey(phkResult);
  }
  if ( !v3 )
  {
    if ( !v5 )
      return v4;
    if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 1u, &phkResult) )
      return SHRegGetBoolValueFromHKCUHKLM(
               L"Software\\Microsoft\\Internet Explorer\\Main",
               L"Enable Browser Extensions",
               1);
    cbData = 520;
    v5 = RegQueryValueExW(phkResult, L"Enable Browser Extensions", 0, &Type, (LPBYTE)Data, &cbData);
    if ( !v5 )
    {
      v8 = IERegValueToBoolW(Type, Data, &v10);
      v4 = v10;
      v5 = v8;
    }
    RegCloseKey(phkResult);
  }
  if ( !v5 )
    return v4;
  if ( !v3 )
    return SHRegGetBoolValueFromHKCUHKLM(
             L"Software\\Microsoft\\Internet Explorer\\Main",
             L"Enable Browser Extensions",
             1);
  v10 = 0;
  cbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Internet Explorer\\Main",
             L"Enable Browser Extensions",
             0x18u,
             0,
             &v10,
             &cbData);
  v4 = v10;
  if ( ValueW )
    return 1;
  return v4;
}

```

## disassembly

```asm
0x1800c4458  push    rbp
0x1800c445a  push    rbx
0x1800c445b  push    rsi
0x1800c445c  push    rdi
0x1800c445d  push    r12
0x1800c445f  lea     rbp, [rsp-180h]
0x1800c4467  sub     rsp, 280h
0x1800c446e  mov     rax, cs:__security_cookie
0x1800c4475  xor     rax, rsp
0x1800c4478  mov     [rbp+1A0h+var_30], rax
0x1800c447f  xor     esi, esi
0x1800c4481  mov     [rsp+2A0h+var_248], 0
0x1800c4489  lea     rax, [rsp+2A0h+var_244]
0x1800c448e  mov     [rsp+2A0h+var_244], 4
0x1800c4496  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800c449b  lea     r8, aSecurityHklmOn; "Security_HKLM_Only"
0x1800c44a2  lea     rax, [rsp+2A0h+var_248]
0x1800c44a7  mov     rbx, 0FFFFFFFF80000002h
0x1800c44ae  mov     [rsp+2A0h+pvData], rax; pvData
0x1800c44b3  lea     r9d, [rsi+18h]; dwFlags
0x1800c44b7  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Internet"...
0x1800c44be  mov     [rsp+2A0h+pdwType], rsi; pdwType
0x1800c44c3  mov     rcx, rbx; hkey
0x1800c44c6  call    cs:__imp_RegGetValueW
0x1800c44cc  mov     r12d, 1
0x1800c44d2  mov     [rsp+2A0h+cbData], 0
0x1800c44da  test    eax, eax
0x1800c44dc  mov     [rsp+2A0h+var_260], r12d
0x1800c44e1  lea     rax, [rsp+2A0h+phkResult]
0x1800c44e6  mov     [rsp+2A0h+Type], 0
0x1800c44ee  cmovz   esi, [rsp+2A0h+var_248]
0x1800c44f3  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Internet"...
0x1800c44fa  xor     r8d, r8d; ulOptions
0x1800c44fd  mov     [rsp+2A0h+phkResult], 0
0x1800c4506  mov     r9d, r12d; samDesired
0x1800c4509  mov     [rsp+2A0h+pdwType], rax; phkResult
0x1800c450e  mov     rcx, rbx; hKey
0x1800c4511  mov     edi, r12d
0x1800c4514  call    cs:__imp_RegOpenKeyExW
0x1800c451a  mov     ebx, eax
0x1800c451c  test    eax, eax
0x1800c451e  jz      loc_1800C45E6
0x1800c4524  test    esi, esi
0x1800c4526  jz      short loc_1800C456E
0x1800c4528  test    ebx, ebx
0x1800c452a  jnz     short loc_1800C454B
0x1800c452c  mov     eax, edi
0x1800c452e  mov     rcx, [rbp+1A0h+var_30]
0x1800c4535  xor     rcx, rsp; StackCookie
0x1800c4538  call    __security_check_cookie
0x1800c453d  add     rsp, 280h
0x1800c4544  pop     r12
0x1800c4546  pop     rdi
0x1800c4547  pop     rsi
0x1800c4548  pop     rbx
0x1800c4549  pop     rbp
0x1800c454a  retn
0x1800c454b  test    esi, esi
0x1800c454d  jnz     loc_1800C4669
0x1800c4553  mov     r8d, r12d; fDefault
0x1800c4556  lea     rdx, aEnableBrowserE; "Enable Browser Extensions"
0x1800c455d  lea     rcx, pszKey; "Software\\Microsoft\\Internet Explorer"...
0x1800c4564  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x1800c456a  mov     edi, eax
0x1800c456c  jmp     short loc_1800C452C
0x1800c456e  test    ebx, ebx
0x1800c4570  jz      short loc_1800C452C
0x1800c4572  lea     rax, [rsp+2A0h+phkResult]
0x1800c4577  mov     r9d, r12d; samDesired
0x1800c457a  xor     r8d, r8d; ulOptions
0x1800c457d  mov     [rsp+2A0h+pdwType], rax; phkResult
0x1800c4582  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Internet"...
0x1800c4589  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c4590  call    cs:__imp_RegOpenKeyExW
0x1800c4596  test    eax, eax
0x1800c4598  jnz     short loc_1800C4553
0x1800c459a  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800c459f  lea     rax, [rsp+2A0h+cbData]
0x1800c45a4  mov     [rsp+2A0h+pvData], rax; lpcbData
0x1800c45a9  lea     r9, [rsp+2A0h+Type]; lpType
0x1800c45ae  lea     rax, [rsp+2A0h+Data]
0x1800c45b3  mov     [rsp+2A0h+cbData], 208h
0x1800c45bb  xor     r8d, r8d; lpReserved
0x1800c45be  mov     [rsp+2A0h+pdwType], rax; lpData
0x1800c45c3  lea     rdx, aEnableBrowserE; "Enable Browser Extensions"
0x1800c45ca  call    cs:__imp_RegQueryValueExW
0x1800c45d0  mov     ebx, eax
0x1800c45d2  test    eax, eax
0x1800c45d4  jz      short loc_1800C464B
0x1800c45d6  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800c45db  call    cs:__imp_RegCloseKey
0x1800c45e1  jmp     loc_1800C4528
0x1800c45e6  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800c45eb  lea     rax, [rsp+2A0h+cbData]
0x1800c45f0  mov     [rsp+2A0h+pvData], rax; lpcbData
0x1800c45f5  lea     r9, [rsp+2A0h+Type]; lpType
0x1800c45fa  lea     rax, [rsp+2A0h+Data]
0x1800c45ff  mov     [rsp+2A0h+cbData], 208h
0x1800c4607  xor     r8d, r8d; lpReserved
0x1800c460a  mov     [rsp+2A0h+pdwType], rax; lpData
0x1800c460f  lea     rdx, aEnableBrowserE; "Enable Browser Extensions"
0x1800c4616  call    cs:__imp_RegQueryValueExW
0x1800c461c  mov     ebx, eax
0x1800c461e  test    eax, eax
0x1800c4620  jnz     short loc_1800C463B
0x1800c4622  mov     ecx, [rsp+2A0h+Type]; unsigned int
0x1800c4626  lea     r8, [rsp+2A0h+var_260]; int *
0x1800c462b  lea     rdx, [rsp+2A0h+Data]; unsigned __int16 *
0x1800c4630  call    ?IERegValueToBoolW@@YAJKPEBGAEAH@Z; IERegValueToBoolW(ulong,ushort const *,int &)
0x1800c4635  mov     edi, [rsp+2A0h+var_260]
0x1800c4639  mov     ebx, eax
0x1800c463b  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1800c4640  call    cs:__imp_RegCloseKey
0x1800c4646  jmp     loc_1800C4524
0x1800c464b  mov     ecx, [rsp+2A0h+Type]; unsigned int
0x1800c464f  lea     r8, [rsp+2A0h+var_260]; int *
0x1800c4654  lea     rdx, [rsp+2A0h+Data]; unsigned __int16 *
0x1800c4659  call    ?IERegValueToBoolW@@YAJKPEBGAEAH@Z; IERegValueToBoolW(ulong,ushort const *,int &)
0x1800c465e  mov     edi, [rsp+2A0h+var_260]
0x1800c4662  mov     ebx, eax
0x1800c4664  jmp     loc_1800C45D6
0x1800c4669  lea     rax, [rsp+2A0h+cbData]
0x1800c466e  mov     [rsp+2A0h+var_260], 0
0x1800c4676  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800c467b  lea     r8, aEnableBrowserE; "Enable Browser Extensions"
0x1800c4682  lea     rax, [rsp+2A0h+var_260]
0x1800c4687  mov     [rsp+2A0h+cbData], 4
0x1800c468f  mov     [rsp+2A0h+pvData], rax; pvData
0x1800c4694  lea     rdx, pszKey; "Software\\Microsoft\\Internet Explorer"...
0x1800c469b  mov     r9d, 18h; dwFlags
0x1800c46a1  mov     [rsp+2A0h+pdwType], 0; pdwType
0x1800c46aa  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800c46b1  call    cs:__imp_RegGetValueW
0x1800c46b7  mov     edi, [rsp+2A0h+var_260]
0x1800c46bb  test    eax, eax
0x1800c46bd  cmovnz  edi, r12d
0x1800c46c1  jmp     loc_1800C452C
```
