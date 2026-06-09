# ipx::mtf::CMtfInputTypeAttributes::ReadInFuzzyFactors(void)

- ea: `0x18000fb54`
- end: `0x18000fe4b`
- name: `?ReadInFuzzyFactors@CMtfInputTypeAttributes@mtf@ipx@@AEAAJXZ`
- size: `759`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfInputTypeAttributes *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f320`

## callees

- `0x18000fb54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fcdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fd35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fd8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fde5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fcdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fd35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fd8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fde5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fbd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fbd8`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfInputTypeAttributes::ReadInFuzzyFactors(ipx::mtf::CMtfInputTypeAttributes *this)
{
  __int64 v2; // rax
  const WCHAR *v3; // rcx
  __int64 v4; // rdx
  signed int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-2Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF

  hKey = 0;
  v2 = 2147483646;
  v3 = L"Software\\Microsoft\\MTFFuzzyFactors";
  v4 = 256;
  do
  {
    if ( !v2 )
      break;
    if ( !*v3 )
      break;
    ++v3;
    --v2;
    --v4;
  }
  while ( v4 );
  v5 = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
  {
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MTFFuzzyFactors", 0, 0x20019u, &hKey);
    if ( !hKey )
      goto LABEL_38;
    *(_DWORD *)Data = 0;
    cbData = 4;
    Type = 4;
    v6 = RegQueryValueExW(hKey, L"ProbabilityWeight", 0, &Type, Data, &cbData);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      if ( cbData )
        *((float *)this + 50) = (float)*(int *)Data / 100.0;
      v7 = RegQueryValueExW(hKey, L"EditDistanceWeight", 0, &Type, Data, &cbData);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 >= 0 )
      {
        if ( cbData )
          *((float *)this + 51) = (float)*(int *)Data / 100.0;
        v8 = RegQueryValueExW(hKey, L"AdjacentKeyFactor", 0, &Type, Data, &cbData);
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        if ( v5 >= 0 )
        {
          if ( cbData )
            *((float *)this + 52) = (float)*(int *)Data / 100.0;
          v9 = RegQueryValueExW(hKey, L"AccentCharFactor", 0, &Type, Data, &cbData);
          v5 = v9;
          if ( v9 > 0 )
            v5 = (unsigned __int16)v9 | 0x80070000;
          if ( v5 >= 0 )
          {
            if ( cbData )
              *((float *)this + 53) = (float)*(int *)Data / 100.0;
            v10 = RegQueryValueExW(hKey, L"SymbolInsertionFactor", 0, &Type, Data, &cbData);
            v5 = v10;
            if ( v10 > 0 )
              v5 = (unsigned __int16)v10 | 0x80070000;
            if ( v5 >= 0 )
            {
              if ( cbData )
                *((float *)this + 54) = (float)*(int *)Data / 100.0;
              v11 = RegQueryValueExW(hKey, L"HiraganaFuzzyFactor", 0, &Type, Data, &cbData);
              v5 = v11;
              if ( v11 > 0 )
                v5 = (unsigned __int16)v11 | 0x80070000;
              if ( v5 >= 0 && cbData )
                *((float *)this + 55) = (float)*(int *)Data / 100.0;
            }
          }
        }
      }
    }
    RegCloseKey(hKey);
    if ( v5 >= 0 )
LABEL_38:
      *((_DWORD *)this + 49) = 1;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000fb54  mov     [rsp-18h+arg_8], rbx
0x18000fb59  mov     [rsp-18h+arg_10], rsi
0x18000fb5e  push    rbp
0x18000fb5f  push    rdi
0x18000fb60  push    r14
0x18000fb62  mov     rbp, rsp
0x18000fb65  sub     rsp, 60h
0x18000fb69  xor     esi, esi
0x18000fb6b  movaps  [rsp+60h+var_10], xmm6
0x18000fb70  mov     rdi, rcx
0x18000fb73  mov     [rbp+hKey], rsi
0x18000fb77  mov     eax, 7FFFFFFEh
0x18000fb7c  lea     rcx, SubKey; "Software\\Microsoft\\MTFFuzzyFactors"
0x18000fb83  mov     edx, 100h
0x18000fb88  test    rax, rax
0x18000fb8b  jz      short loc_18000FB9F
0x18000fb8d  cmp     [rcx], si
0x18000fb90  jz      short loc_18000FB9F
0x18000fb92  add     rcx, 2
0x18000fb96  dec     rax
0x18000fb99  sub     rdx, 1
0x18000fb9d  jnz     short loc_18000FB88
0x18000fb9f  mov     rax, rdx
0x18000fba2  neg     rax
0x18000fba5  sbb     ebx, ebx
0x18000fba7  not     ebx
0x18000fba9  and     ebx, 8007007Ah
0x18000fbaf  test    rdx, rdx
0x18000fbb2  jz      loc_18000FE2F
0x18000fbb8  lea     rax, [rbp+hKey]
0x18000fbbc  mov     r9d, 20019h; samDesired
0x18000fbc2  xor     r8d, r8d; ulOptions
0x18000fbc5  mov     [rsp+60h+phkResult], rax; phkResult
0x18000fbca  lea     rdx, SubKey; "Software\\Microsoft\\MTFFuzzyFactors"
0x18000fbd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fbd8  call    cs:__imp_RegOpenKeyExW
0x18000fbde  mov     rcx, [rbp+hKey]; hKey
0x18000fbe2  test    rcx, rcx
0x18000fbe5  jz      loc_18000FE25
0x18000fbeb  mov     eax, 4
0x18000fbf0  mov     dword ptr [rbp+Data], esi
0x18000fbf3  mov     [rbp+cbData], eax
0x18000fbf6  lea     r9, [rbp+Type]; lpType
0x18000fbfa  mov     [rbp+Type], eax
0x18000fbfd  lea     rdx, aProbabilitywei; "ProbabilityWeight"
0x18000fc04  lea     rax, [rbp+cbData]
0x18000fc08  xor     r8d, r8d; lpReserved
0x18000fc0b  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000fc10  lea     rax, [rbp+Data]
0x18000fc14  mov     [rsp+60h+phkResult], rax; lpData
0x18000fc19  call    cs:__imp_RegQueryValueExW
0x18000fc1f  mov     ebx, eax
0x18000fc21  mov     r14d, 80070000h
0x18000fc27  test    eax, eax
0x18000fc29  jle     short loc_18000FC31
0x18000fc2b  movzx   ebx, ax
0x18000fc2e  or      ebx, r14d
0x18000fc31  test    ebx, ebx
0x18000fc33  js      loc_18000FE17
0x18000fc39  movss   xmm6, cs:__real@42c80000
0x18000fc41  cmp     [rbp+cbData], esi
0x18000fc44  jbe     short loc_18000FC5D
0x18000fc46  mov     eax, dword ptr [rbp+Data]
0x18000fc49  xorps   xmm0, xmm0
0x18000fc4c  cvtsi2ss xmm0, rax
0x18000fc51  divss   xmm0, xmm6
0x18000fc55  movss   dword ptr [rdi+0C8h], xmm0
0x18000fc5d  mov     rcx, [rbp+hKey]; hKey
0x18000fc61  lea     rax, [rbp+cbData]
0x18000fc65  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000fc6a  lea     r9, [rbp+Type]; lpType
0x18000fc6e  lea     rax, [rbp+Data]
0x18000fc72  xor     r8d, r8d; lpReserved
0x18000fc75  lea     rdx, aEditdistancewe; "EditDistanceWeight"
0x18000fc7c  mov     [rsp+60h+phkResult], rax; lpData
0x18000fc81  call    cs:__imp_RegQueryValueExW
0x18000fc87  mov     ebx, eax
0x18000fc89  test    eax, eax
0x18000fc8b  jle     short loc_18000FC93
0x18000fc8d  movzx   ebx, ax
0x18000fc90  or      ebx, r14d
0x18000fc93  test    ebx, ebx
0x18000fc95  js      loc_18000FE17
0x18000fc9b  cmp     [rbp+cbData], esi
0x18000fc9e  jbe     short loc_18000FCB7
0x18000fca0  mov     eax, dword ptr [rbp+Data]
0x18000fca3  xorps   xmm0, xmm0
0x18000fca6  cvtsi2ss xmm0, rax
0x18000fcab  divss   xmm0, xmm6
0x18000fcaf  movss   dword ptr [rdi+0CCh], xmm0
0x18000fcb7  mov     rcx, [rbp+hKey]; hKey
0x18000fcbb  lea     rax, [rbp+cbData]
0x18000fcbf  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000fcc4  lea     r9, [rbp+Type]; lpType
0x18000fcc8  lea     rax, [rbp+Data]
0x18000fccc  xor     r8d, r8d; lpReserved
0x18000fccf  lea     rdx, aAdjacentkeyfac; "AdjacentKeyFactor"
0x18000fcd6  mov     [rsp+60h+phkResult], rax; lpData
0x18000fcdb  call    cs:__imp_RegQueryValueExW
0x18000fce1  mov     ebx, eax
0x18000fce3  test    eax, eax
0x18000fce5  jle     short loc_18000FCED
0x18000fce7  movzx   ebx, ax
0x18000fcea  or      ebx, r14d
0x18000fced  test    ebx, ebx
0x18000fcef  js      loc_18000FE17
0x18000fcf5  cmp     [rbp+cbData], esi
0x18000fcf8  jbe     short loc_18000FD11
0x18000fcfa  mov     eax, dword ptr [rbp+Data]
0x18000fcfd  xorps   xmm0, xmm0
0x18000fd00  cvtsi2ss xmm0, rax
0x18000fd05  divss   xmm0, xmm6
0x18000fd09  movss   dword ptr [rdi+0D0h], xmm0
0x18000fd11  mov     rcx, [rbp+hKey]; hKey
0x18000fd15  lea     rax, [rbp+cbData]
0x18000fd19  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000fd1e  lea     r9, [rbp+Type]; lpType
0x18000fd22  lea     rax, [rbp+Data]
0x18000fd26  xor     r8d, r8d; lpReserved
0x18000fd29  lea     rdx, aAccentcharfact; "AccentCharFactor"
0x18000fd30  mov     [rsp+60h+phkResult], rax; lpData
0x18000fd35  call    cs:__imp_RegQueryValueExW
0x18000fd3b  mov     ebx, eax
0x18000fd3d  test    eax, eax
0x18000fd3f  jle     short loc_18000FD47
0x18000fd41  movzx   ebx, ax
0x18000fd44  or      ebx, r14d
0x18000fd47  test    ebx, ebx
0x18000fd49  js      loc_18000FE17
0x18000fd4f  cmp     [rbp+cbData], esi
0x18000fd52  jbe     short loc_18000FD6B
0x18000fd54  mov     eax, dword ptr [rbp+Data]
0x18000fd57  xorps   xmm0, xmm0
0x18000fd5a  cvtsi2ss xmm0, rax
0x18000fd5f  divss   xmm0, xmm6
0x18000fd63  movss   dword ptr [rdi+0D4h], xmm0
0x18000fd6b  mov     rcx, [rbp+hKey]; hKey
0x18000fd6f  lea     rax, [rbp+cbData]
0x18000fd73  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000fd78  lea     r9, [rbp+Type]; lpType
0x18000fd7c  lea     rax, [rbp+Data]
0x18000fd80  xor     r8d, r8d; lpReserved
0x18000fd83  lea     rdx, aSymbolinsertio; "SymbolInsertionFactor"
0x18000fd8a  mov     [rsp+60h+phkResult], rax; lpData
0x18000fd8f  call    cs:__imp_RegQueryValueExW
0x18000fd95  mov     ebx, eax
0x18000fd97  test    eax, eax
0x18000fd99  jle     short loc_18000FDA1
0x18000fd9b  movzx   ebx, ax
0x18000fd9e  or      ebx, r14d
0x18000fda1  test    ebx, ebx
0x18000fda3  js      short loc_18000FE17
0x18000fda5  cmp     [rbp+cbData], esi
0x18000fda8  jbe     short loc_18000FDC1
0x18000fdaa  mov     eax, dword ptr [rbp+Data]
0x18000fdad  xorps   xmm0, xmm0
0x18000fdb0  cvtsi2ss xmm0, rax
0x18000fdb5  divss   xmm0, xmm6
0x18000fdb9  movss   dword ptr [rdi+0D8h], xmm0
0x18000fdc1  mov     rcx, [rbp+hKey]; hKey
0x18000fdc5  lea     rax, [rbp+cbData]
0x18000fdc9  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000fdce  lea     r9, [rbp+Type]; lpType
0x18000fdd2  lea     rax, [rbp+Data]
0x18000fdd6  xor     r8d, r8d; lpReserved
0x18000fdd9  lea     rdx, aHiraganafuzzyf; "HiraganaFuzzyFactor"
0x18000fde0  mov     [rsp+60h+phkResult], rax; lpData
0x18000fde5  call    cs:__imp_RegQueryValueExW
0x18000fdeb  mov     ebx, eax
0x18000fded  test    eax, eax
0x18000fdef  jle     short loc_18000FDF7
0x18000fdf1  movzx   ebx, ax
0x18000fdf4  or      ebx, r14d
0x18000fdf7  test    ebx, ebx
0x18000fdf9  js      short loc_18000FE17
0x18000fdfb  cmp     [rbp+cbData], esi
0x18000fdfe  jbe     short loc_18000FE17
0x18000fe00  mov     eax, dword ptr [rbp+Data]
0x18000fe03  xorps   xmm0, xmm0
0x18000fe06  cvtsi2ss xmm0, rax
0x18000fe0b  divss   xmm0, xmm6
0x18000fe0f  movss   dword ptr [rdi+0DCh], xmm0
0x18000fe17  mov     rcx, [rbp+hKey]; hKey
0x18000fe1b  call    cs:__imp_RegCloseKey
0x18000fe21  test    ebx, ebx
0x18000fe23  js      short loc_18000FE2F
0x18000fe25  mov     dword ptr [rdi+0C4h], 1
0x18000fe2f  movaps  xmm6, [rsp+60h+var_10]
0x18000fe34  lea     r11, [rsp+60h+var_s0]
0x18000fe39  mov     rsi, [r11+30h]
0x18000fe3d  mov     eax, ebx
0x18000fe3f  mov     rbx, [r11+28h]
0x18000fe43  mov     rsp, r11
0x18000fe46  pop     r14
0x18000fe48  pop     rdi
0x18000fe49  pop     rbp
0x18000fe4a  retn
```
