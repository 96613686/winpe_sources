# HampUsageInfoRegistryQuery

- ea: `0x18000d4b0`
- end: `0x18000d6b0`
- name: `HampUsageInfoRegistryQuery`
- size: `512`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __m128i *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012240`
- `0x180019cd0`

## callees

- `0x18000d4b0`
- `0x18001aec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d52f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d53f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d54f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d52f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d53f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d54f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d501`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d58c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d5c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d501`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d58c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d5c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d63b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d63b`

## pseudocode

```c
__int64 __fastcall HampUsageInfoRegistryQuery(HKEY a1, const WCHAR *a2, __m128i *a3)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  unsigned int v9; // edi
  LSTATUS Value; // eax
  __m128i v11; // xmm1
  HKEY hKey; // [rsp+30h] [rbp-68h] BYREF
  HKEY v13; // [rsp+38h] [rbp-60h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-58h] BYREF
  __m128i si128; // [rsp+48h] [rbp-50h] BYREF
  __m128i v16; // [rsp+58h] [rbp-40h]

  phkResult = 0;
  v13 = 0;
  hKey = 0;
  si128 = 0;
  v16 = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 1u, &phkResult);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0xC0070000;
  if ( v5 >= 0 )
  {
    v7 = RegOpenKeyExW(phkResult, L"V1", 0, 1u, &v13);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0xC0070000;
    if ( v5 >= 0 )
    {
      v8 = RegOpenKeyExW(v13, L"LU", 0, 0x20019u, &hKey);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0xC0070000;
      if ( v5 >= 0 )
      {
        v9 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v16 = si128;
        while ( v9 < 4 )
        {
          Value = RegQueryValueExW(
                    hKey,
                    (LPCWSTR)*(&LastUsageRegInfo + 3 * v9),
                    0,
                    0,
                    &si128.m128i_u8[*((unsigned int *)&LastUsageRegInfo + 6 * v9 + 3)],
                    (LPDWORD)&qword_18002E0D8[3 * v9 + 1]);
          v5 = Value;
          if ( Value > 0 )
            v5 = (unsigned __int16)Value | 0xC0070000;
          if ( v5 != -1073283070 && v5 < 0 )
            goto LABEL_4;
          ++v9;
        }
        v5 = 0;
        v11 = v16;
        *a3 = si128;
        a3[1] = v11;
      }
    }
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v13 )
    RegCloseKey(v13);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d4b0  mov     r11, rsp
0x18000d4b3  push    rbx
0x18000d4b4  sub     rsp, 90h
0x18000d4bb  mov     rax, cs:__security_cookie
0x18000d4c2  xor     rax, rsp
0x18000d4c5  mov     [rsp+98h+var_30], rax
0x18000d4ca  mov     [r11-10h], rbp
0x18000d4ce  lea     rax, [r11-58h]
0x18000d4d2  xorps   xmm0, xmm0
0x18000d4d5  mov     [r11-18h], rsi
0x18000d4d9  xor     ebp, ebp
0x18000d4db  mov     [r11-78h], rax
0x18000d4df  mov     rsi, r8
0x18000d4e2  mov     [r11-58h], rbp
0x18000d4e6  xor     r8d, r8d; ulOptions
0x18000d4e9  mov     [r11-60h], rbp
0x18000d4ed  mov     r9d, 1; samDesired
0x18000d4f3  mov     [r11-68h], rbp
0x18000d4f7  movups  [rsp+98h+var_50], xmm0
0x18000d4fc  movups  [rsp+98h+var_40], xmm0
0x18000d501  call    cs:__imp_RegOpenKeyExW
0x18000d507  mov     ebx, eax
0x18000d509  test    eax, eax
0x18000d50b  jg      loc_18000D680
0x18000d511  test    ebx, ebx
0x18000d513  jns     short loc_18000D56D
0x18000d515  mov     rcx, [rsp+98h+hKey]; hKey
0x18000d51a  mov     rsi, [rsp+98h+var_18]
0x18000d522  mov     rbp, [rsp+98h+var_10]
0x18000d52a  test    rcx, rcx
0x18000d52d  jz      short loc_18000D535
0x18000d52f  call    cs:__imp_RegCloseKey
0x18000d535  mov     rcx, [rsp+98h+var_60]; hKey
0x18000d53a  test    rcx, rcx
0x18000d53d  jz      short loc_18000D545
0x18000d53f  call    cs:__imp_RegCloseKey
0x18000d545  mov     rcx, [rsp+98h+var_58]; hKey
0x18000d54a  test    rcx, rcx
0x18000d54d  jz      short loc_18000D555
0x18000d54f  call    cs:__imp_RegCloseKey
0x18000d555  mov     eax, ebx
0x18000d557  mov     rcx, [rsp+98h+var_30]
0x18000d55c  xor     rcx, rsp; StackCookie
0x18000d55f  call    __security_check_cookie
0x18000d564  add     rsp, 90h
0x18000d56b  pop     rbx
0x18000d56c  retn
0x18000d56d  mov     rcx, [rsp+98h+var_58]; hKey
0x18000d572  lea     rax, [rsp+98h+var_60]
0x18000d577  mov     r9d, 1; samDesired
0x18000d57d  mov     [rsp+98h+phkResult], rax; phkResult
0x18000d582  xor     r8d, r8d; ulOptions
0x18000d585  lea     rdx, aV1; "V1"
0x18000d58c  call    cs:__imp_RegOpenKeyExW
0x18000d592  mov     ebx, eax
0x18000d594  test    eax, eax
0x18000d596  jg      loc_18000D68E
0x18000d59c  test    ebx, ebx
0x18000d59e  js      loc_18000D515
0x18000d5a4  mov     rcx, [rsp+98h+var_60]; hKey
0x18000d5a9  lea     rax, [rsp+98h+hKey]
0x18000d5ae  mov     r9d, 20019h; samDesired
0x18000d5b4  mov     [rsp+98h+phkResult], rax; phkResult
0x18000d5b9  xor     r8d, r8d; ulOptions
0x18000d5bc  lea     rdx, aLu; "LU"
0x18000d5c3  call    cs:__imp_RegOpenKeyExW
0x18000d5c9  mov     ebx, eax
0x18000d5cb  test    eax, eax
0x18000d5cd  jg      loc_18000D69C
0x18000d5d3  test    ebx, ebx
0x18000d5d5  js      loc_18000D515
0x18000d5db  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000d5e3  mov     [rsp+98h+var_20], rdi
0x18000d5e8  mov     edi, ebp
0x18000d5ea  mov     [rsp+98h+var_28], r14
0x18000d5ef  lea     r14, ?LastUsageRegInfo@@3PAU_HAM_LAST_USAGE_REG_INFO@@A; _HAM_LAST_USAGE_REG_INFO near * LastUsageRegInfo
0x18000d5f6  movdqu  [rsp+98h+var_50], xmm0
0x18000d5fc  movdqu  [rsp+98h+var_40], xmm0
0x18000d602  cmp     edi, 4
0x18000d605  jnb     short loc_18000D65E
0x18000d607  mov     eax, edi
0x18000d609  lea     r9, [r14+10h]
0x18000d60d  lea     r8, [rsp+98h+var_50]
0x18000d612  lea     rcx, [rax+rax*2]
0x18000d616  mov     eax, [r14+rcx*8+0Ch]
0x18000d61b  lea     r9, [r9+rcx*8]
0x18000d61f  mov     rdx, [r14+rcx*8]; lpValueName
0x18000d623  add     r8, rax
0x18000d626  mov     rcx, [rsp+98h+hKey]; hKey
0x18000d62b  mov     [rsp+98h+lpcbData], r9; lpcbData
0x18000d630  xor     r9d, r9d; lpType
0x18000d633  mov     [rsp+98h+phkResult], r8; lpData
0x18000d638  xor     r8d, r8d; lpReserved
0x18000d63b  call    cs:__imp_RegQueryValueExW
0x18000d641  mov     ebx, eax
0x18000d643  test    eax, eax
0x18000d645  jg      short loc_18000D653
0x18000d647  cmp     ebx, 0C0070002h
0x18000d64d  jnz     short loc_18000D6AA
0x18000d64f  inc     edi
0x18000d651  jmp     short loc_18000D602
0x18000d653  movzx   ebx, ax
0x18000d656  or      ebx, 0C0070000h
0x18000d65c  jmp     short loc_18000D647
0x18000d65e  movups  xmm0, [rsp+98h+var_50]
0x18000d663  mov     ebx, ebp
0x18000d665  movups  xmm1, [rsp+98h+var_40]
0x18000d66a  movups  xmmword ptr [rsi], xmm0
0x18000d66d  movups  xmmword ptr [rsi+10h], xmm1
0x18000d671  mov     rdi, [rsp+98h+var_20]
0x18000d676  mov     r14, [rsp+98h+var_28]
0x18000d67b  jmp     loc_18000D515
0x18000d680  movzx   ebx, ax
0x18000d683  or      ebx, 0C0070000h
0x18000d689  jmp     loc_18000D511
0x18000d68e  movzx   ebx, ax
0x18000d691  or      ebx, 0C0070000h
0x18000d697  jmp     loc_18000D59C
0x18000d69c  movzx   ebx, ax
0x18000d69f  or      ebx, 0C0070000h
0x18000d6a5  jmp     loc_18000D5D3
0x18000d6aa  test    ebx, ebx
0x18000d6ac  js      short loc_18000D671
0x18000d6ae  jmp     short loc_18000D64F
```
