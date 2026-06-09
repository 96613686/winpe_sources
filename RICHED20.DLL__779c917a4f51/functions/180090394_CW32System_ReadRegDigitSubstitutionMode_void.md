# CW32System::ReadRegDigitSubstitutionMode(void)

- ea: `0x180090394`
- end: `0x180090495`
- name: `?ReadRegDigitSubstitutionMode@CW32System@@SAEXZ`
- size: `257`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180041c94`

## callees

- `0x18003ff74`
- `0x180045f24`
- `0x18005e85c`
- `0x18008f6a0`
- `0x180090394`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x1800903d0`
- `KERNEL32!GetThreadLocale` at `0x1800903d0`
- `ADVAPI32!RegOpenKeyExA` at `0x18009042a`
- `ADVAPI32!RegOpenKeyExA` at `0x18009042a`
- `ADVAPI32!RegQueryValueExA` at `0x180090463`
- `ADVAPI32!RegQueryValueExA` at `0x180090463`
- `ADVAPI32!RegCloseKey` at `0x180090486`
- `ADVAPI32!RegCloseKey` at `0x180090486`

## pseudocode

```c
char CW32System::ReadRegDigitSubstitutionMode(void)
{
  char v0; // bl
  LCID ThreadLocale; // eax
  unsigned int v2; // edx
  BYTE Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v0 = 0;
  Type = 0;
  cbData = 0;
  if ( !CW32System::OnWin9xFE() && !CW32System::OnWinNTFE() )
  {
    ThreadLocale = GetThreadLocale();
    if ( ((unsigned int)CW32System::IsBiDiLcid(ThreadLocale)
       || (v2 & 0x3FF) == 0x1E
       || (v2 & 0x3FF) == 0x2A
       || (unsigned int)CW32System::IsIndicLcid(v2))
      && !RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\International", 0, 1u, &hKey) )
    {
      cbData = 2;
      if ( !RegQueryValueExA(hKey, "NumShape", 0, &Type, &Data, &cbData) && Data > 0x2Fu )
      {
        v0 = Data - 47;
        if ( (unsigned __int8)(Data - 47) > 3u )
          v0 = 2;
      }
      RegCloseKey(hKey);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180090394  push    rbx
0x180090396  push    rsi
0x180090397  sub     rsp, 38h
0x18009039b  mov     [rsp+48h+hKey], 0
0x1800903a4  xor     bl, bl
0x1800903a6  mov     [rsp+48h+Type], 0
0x1800903ae  mov     [rsp+48h+cbData], 0
0x1800903b6  call    ?OnWin9xFE@CW32System@@SA_NXZ; CW32System::OnWin9xFE(void)
0x1800903bb  test    al, al
0x1800903bd  jnz     loc_18009048C
0x1800903c3  call    ?OnWinNTFE@CW32System@@SA_NXZ; CW32System::OnWinNTFE(void)
0x1800903c8  test    al, al
0x1800903ca  jnz     loc_18009048C
0x1800903d0  call    cs:__imp_GetThreadLocale
0x1800903d6  mov     ecx, eax; unsigned int
0x1800903d8  mov     edx, eax
0x1800903da  call    ?IsBiDiLcid@CW32System@@SAHK@Z; CW32System::IsBiDiLcid(ulong)
0x1800903df  test    eax, eax
0x1800903e1  jnz     short loc_180090409
0x1800903e3  movzx   ecx, dx
0x1800903e6  mov     eax, 3FFh
0x1800903eb  and     cx, ax
0x1800903ee  cmp     cx, 1Eh
0x1800903f2  jz      short loc_180090409
0x1800903f4  cmp     cx, 2Ah ; '*'
0x1800903f8  jz      short loc_180090409
0x1800903fa  mov     ecx, edx; unsigned int
0x1800903fc  call    ?IsIndicLcid@CW32System@@SAHK@Z; CW32System::IsIndicLcid(ulong)
0x180090401  test    eax, eax
0x180090403  jz      loc_18009048C
0x180090409  lea     rax, [rsp+48h+hKey]
0x18009040e  mov     r9d, 1; samDesired
0x180090414  xor     r8d, r8d; ulOptions
0x180090417  mov     [rsp+48h+phkResult], rax; phkResult
0x18009041c  lea     rdx, SubKey; "Control Panel\\International"
0x180090423  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009042a  call    cs:__imp_RegOpenKeyExA
0x180090430  test    eax, eax
0x180090432  jnz     short loc_18009048C
0x180090434  mov     rcx, [rsp+48h+hKey]; hKey
0x180090439  lea     esi, [rax+2]
0x18009043c  lea     rax, [rsp+48h+cbData]
0x180090441  mov     [rsp+48h+cbData], esi
0x180090445  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18009044a  lea     r9, [rsp+48h+Type]; lpType
0x18009044f  lea     rax, [rsp+48h+Data]
0x180090454  xor     r8d, r8d; lpReserved
0x180090457  lea     rdx, ValueName; "NumShape"
0x18009045e  mov     [rsp+48h+phkResult], rax; lpData
0x180090463  call    cs:__imp_RegQueryValueExA
0x180090469  test    eax, eax
0x18009046b  jnz     short loc_180090481
0x18009046d  movzx   eax, word ptr [rsp+48h+Data]
0x180090472  cmp     al, 2Fh ; '/'
0x180090474  jbe     short loc_180090481
0x180090476  sub     al, 2Fh ; '/'
0x180090478  movzx   ebx, al
0x18009047b  cmp     bl, 3
0x18009047e  cmova   ebx, esi
0x180090481  mov     rcx, [rsp+48h+hKey]; hKey
0x180090486  call    cs:__imp_RegCloseKey
0x18009048c  mov     al, bl
0x18009048e  add     rsp, 38h
0x180090492  pop     rsi
0x180090493  pop     rbx
0x180090494  retn
```
