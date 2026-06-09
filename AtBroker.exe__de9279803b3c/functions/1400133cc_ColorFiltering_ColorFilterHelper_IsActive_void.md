# ColorFiltering::ColorFilterHelper::IsActive(void)

- ea: `0x1400133cc`
- end: `0x140013523`
- name: `?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ`
- size: `343`
- prototype: `char(void)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000b250`
- `0x1400143ac`
- `0x140014de8`
- `0x140014f18`
- `0x140015048`

## callees

- `0x1400133cc`
- `0x140014cbc`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140013440`
- `ADVAPI32!RegQueryValueExW` at `0x1400134bc`
- `ADVAPI32!RegQueryValueExW` at `0x140013440`
- `ADVAPI32!RegQueryValueExW` at `0x1400134bc`
- `ADVAPI32!RegOpenKeyExW` at `0x140013405`
- `ADVAPI32!RegOpenKeyExW` at `0x14001347d`
- `ADVAPI32!RegOpenKeyExW` at `0x140013405`
- `ADVAPI32!RegOpenKeyExW` at `0x14001347d`
- `ADVAPI32!RegCloseKey` at `0x1400134e5`
- `ADVAPI32!RegCloseKey` at `0x1400134f3`
- `ADVAPI32!RegCloseKey` at `0x140013505`
- `ADVAPI32!RegCloseKey` at `0x140013513`
- `ADVAPI32!RegCloseKey` at `0x1400134e5`
- `ADVAPI32!RegCloseKey` at `0x1400134f3`
- `ADVAPI32!RegCloseKey` at `0x140013505`
- `ADVAPI32!RegCloseKey` at `0x140013513`

## string_xrefs

- `0x1400133f7`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
char ColorFiltering::ColorFilterHelper::IsActive(void)
{
  HKEY v0; // rbx
  HKEY v1; // rdi
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  v0 = 0;
  Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
          0,
          1u,
          &hKey) )
  {
    v0 = hKey;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Active", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
    {
LABEL_11:
      if ( v0 )
        RegCloseKey(v0);
      return 1;
    }
  }
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\ColorFiltering", 0, 1u, &phkResult) )
  {
    v1 = phkResult;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(phkResult, L"Active", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(Data != 0);
      if ( Data )
      {
        if ( v1 )
          RegCloseKey(v1);
        goto LABEL_11;
      }
    }
    if ( v1 )
      RegCloseKey(v1);
  }
  if ( v0 )
    RegCloseKey(v0);
  return 0;
}

```

## disassembly

```asm
0x1400133cc  push    rbp
0x1400133ce  push    rbx
0x1400133cf  push    rdi
0x1400133d0  mov     rbp, rsp
0x1400133d3  sub     rsp, 40h
0x1400133d7  xor     ebx, ebx
0x1400133d9  mov     [rbp+Data], 0
0x1400133e0  lea     rax, [rbp+hKey]
0x1400133e4  mov     [rbp+hKey], rbx
0x1400133e8  mov     rdi, 0FFFFFFFF80000001h
0x1400133ef  mov     [rsp+40h+phkResult], rax; phkResult
0x1400133f4  xor     r8d, r8d; ulOptions
0x1400133f7  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400133fe  lea     r9d, [rbx+1]; samDesired
0x140013402  mov     rcx, rdi; hKey
0x140013405  call    cs:__imp_RegOpenKeyExW
0x14001340b  test    eax, eax
0x14001340d  jnz     short loc_140013459
0x14001340f  mov     rbx, [rbp+hKey]
0x140013413  lea     r9, [rbp+Type]; lpType
0x140013417  mov     [rbp+Type], eax
0x14001341a  lea     rdx, aActive_0; "Active"
0x140013421  lea     rax, [rbp+cbData]
0x140013425  mov     [rbp+cbData], 4
0x14001342c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140013431  xor     r8d, r8d; lpReserved
0x140013434  lea     rax, [rbp+Data]
0x140013438  mov     rcx, rbx; hKey
0x14001343b  mov     [rsp+40h+phkResult], rax; lpData
0x140013440  call    cs:__imp_RegQueryValueExW
0x140013446  test    eax, eax
0x140013448  jnz     short loc_140013459
0x14001344a  cmp     [rbp+Type], 4
0x14001344e  jnz     short loc_140013459
0x140013450  cmp     [rbp+Data], eax
0x140013453  jnz     loc_1400134EB
0x140013459  lea     rax, [rbp+var_10]
0x14001345d  mov     [rbp+var_10], 0
0x140013465  mov     r9d, 1; samDesired
0x14001346b  mov     [rsp+40h+phkResult], rax; phkResult
0x140013470  xor     r8d, r8d; ulOptions
0x140013473  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ColorFiltering"
0x14001347a  mov     rcx, rdi; hKey
0x14001347d  call    cs:__imp_RegOpenKeyExW
0x140013483  test    eax, eax
0x140013485  jnz     loc_14001350B
0x14001348b  mov     rdi, [rbp+var_10]
0x14001348f  lea     r9, [rbp+Type]; lpType
0x140013493  mov     [rbp+Type], eax
0x140013496  lea     rdx, aActive_0; "Active"
0x14001349d  lea     rax, [rbp+cbData]
0x1400134a1  mov     [rbp+cbData], 4
0x1400134a8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1400134ad  xor     r8d, r8d; lpReserved
0x1400134b0  lea     rax, [rbp+Data]
0x1400134b4  mov     rcx, rdi; hKey
0x1400134b7  mov     [rsp+40h+phkResult], rax; lpData
0x1400134bc  call    cs:__imp_RegQueryValueExW
0x1400134c2  test    eax, eax
0x1400134c4  jnz     short loc_1400134FD
0x1400134c6  cmp     [rbp+Type], 4
0x1400134ca  jnz     short loc_1400134FD
0x1400134cc  cmp     [rbp+Data], eax
0x1400134cf  setnz   cl; bool
0x1400134d2  call    ?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)
0x1400134d7  cmp     [rbp+Data], 0
0x1400134db  jz      short loc_1400134FD
0x1400134dd  test    rdi, rdi
0x1400134e0  jz      short loc_1400134EB
0x1400134e2  mov     rcx, rdi; hKey
0x1400134e5  call    cs:__imp_RegCloseKey
0x1400134eb  test    rbx, rbx
0x1400134ee  jz      short loc_1400134F9
0x1400134f0  mov     rcx, rbx; hKey
0x1400134f3  call    cs:__imp_RegCloseKey
0x1400134f9  mov     al, 1
0x1400134fb  jmp     short loc_14001351B
0x1400134fd  test    rdi, rdi
0x140013500  jz      short loc_14001350B
0x140013502  mov     rcx, rdi; hKey
0x140013505  call    cs:__imp_RegCloseKey
0x14001350b  test    rbx, rbx
0x14001350e  jz      short loc_140013519
0x140013510  mov     rcx, rbx; hKey
0x140013513  call    cs:__imp_RegCloseKey
0x140013519  xor     al, al
0x14001351b  add     rsp, 40h
0x14001351f  pop     rdi
0x140013520  pop     rbx
0x140013521  pop     rbp
0x140013522  retn
```
