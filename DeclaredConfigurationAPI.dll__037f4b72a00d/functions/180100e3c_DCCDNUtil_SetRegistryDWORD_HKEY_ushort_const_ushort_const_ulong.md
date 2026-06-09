# DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180100e3c`
- end: `0x180100fd0`
- name: `?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `404`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `57`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005e76c`
- `0x180061a38`
- `0x180063350`
- `0x180065ce0`
- `0x180066550`
- `0x180067160`
- `0x18007cbd0`
- `0x180080e90`
- `0x180082930`
- `0x180084280`
- `0x180084fe0`
- `0x180086350`
- `0x180086c10`
- `0x1800882a0`
- `0x18008ffe8`
- `0x180091eec`
- `0x1800933a0`
- `0x18009468c`
- `0x18009a828`
- `0x18009aaf0`
- `0x18009ad78`
- `0x18009b2e4`
- `0x18009bae8`
- `0x18009c3e4`
- `0x18009d6dc`
- `0x18009e3f0`
- `0x18009e728`
- `0x1800ab0f0`
- `0x1800ab610`
- `0x1800abbe0`
- `0x1800b85c0`
- `0x1800b8fac`
- `0x1800baca4`
- `0x1800c7600`
- `0x1800ced20`
- `0x1800cedd0`
- `0x1800d1b94`
- `0x1800d24e4`
- `0x1800d32a0`
- `0x1800d8844`
- `0x1800d943c`
- `0x1800da8b4`
- `0x1800dd884`
- `0x1800dd9b8`
- `0x1800ddd9c`
- `0x1800e3758`
- `0x1800f23d0`
- `0x1800f2730`
- `0x1800f29e8`
- `0x1800fea9c`

## callees

- `0x1800117dc`
- `0x180100e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180100f77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180100f77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180100f3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180100f3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180100eb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180100eb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100f9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100fb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100f9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100fb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180100ef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180100ef8`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_SetRegistryDWORD(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  __int64 v6; // rdx
  int Key; // ebx
  int v8; // r14d
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  int v12; // [rsp+20h] [rbp-40h]
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HKEY phkResult; // [rsp+80h] [rbp+20h] BYREF
  int Data; // [rsp+98h] [rbp+38h] BYREF

  Data = a4;
  phkResult = a1;
  hKey[0] = 0;
  if ( !a1 )
  {
    v6 = 239;
LABEL_3:
    Key = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      v12);
    return (unsigned int)Key;
  }
  if ( !a3 )
  {
    v6 = 240;
    goto LABEL_3;
  }
  v8 = 0;
  if ( !a2 )
  {
    hKey[0] = a1;
LABEL_20:
    Key = 0;
    v10 = RegSetValueExW(a1, a3, 0, 4u, (const BYTE *)&Data, 4u);
    if ( v10 )
    {
      if ( v10 > 0 )
        Key = (unsigned __int16)v10 | 0x80070000;
      else
        Key = v10;
    }
    if ( !a2 )
      goto LABEL_27;
    goto LABEL_25;
  }
  if ( a1 == HKEY_CURRENT_USER )
  {
    v9 = RegOpenCurrentUser(0x20106u, &phkResult);
    Key = v9;
    if ( v9 )
    {
      if ( v9 <= 0 )
        goto LABEL_25;
      Key = (unsigned __int16)v9;
      goto LABEL_11;
    }
    a1 = phkResult;
    v8 = 1;
  }
  Key = RegOpenKeyExW(a1, a2, 0, 0x20106u, hKey);
  if ( Key == 2 )
    Key = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 0x20106u, 0, hKey, 0);
  if ( !Key )
  {
    a1 = hKey[0];
    goto LABEL_20;
  }
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key;
LABEL_11:
    Key |= 0x80070000;
  }
LABEL_25:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
LABEL_27:
  if ( v8 == 1 && phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180100e3c  mov     rax, rsp
0x180100e3f  mov     [rax+10h], rbx
0x180100e43  mov     [rax+18h], rsi
0x180100e47  mov     [rax+20h], r9d
0x180100e4b  mov     [rax+8], rcx
0x180100e4f  push    rbp
0x180100e50  push    rdi
0x180100e51  push    r14
0x180100e53  mov     rbp, rsp
0x180100e56  sub     rsp, 60h
0x180100e5a  mov     [rbp+hKey], 0
0x180100e62  mov     rsi, r8
0x180100e65  mov     rdi, rdx
0x180100e68  test    rcx, rcx
0x180100e6b  jnz     short loc_180100E8F
0x180100e6d  mov     edx, 0EFh; void *
0x180100e72  mov     rcx, [rbp+18h]; this
0x180100e76  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180100e7d  mov     ebx, 80070057h
0x180100e82  mov     r9d, ebx; char *
0x180100e85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100e8a  jmp     loc_180100FB9
0x180100e8f  test    rsi, rsi
0x180100e92  jnz     short loc_180100E9B
0x180100e94  mov     edx, 0F0h
0x180100e99  jmp     short loc_180100E72
0x180100e9b  xor     r14d, r14d
0x180100e9e  test    rdi, rdi
0x180100ea1  jz      loc_180100F59
0x180100ea7  cmp     rcx, 0FFFFFFFF80000001h
0x180100eae  jnz     short loc_180100EE3
0x180100eb0  lea     rdx, [rbp+phkResult]; phkResult
0x180100eb4  mov     ecx, 20106h; samDesired
0x180100eb9  call    cs:__imp_RegOpenCurrentUser
0x180100ebf  mov     ebx, eax
0x180100ec1  test    eax, eax
0x180100ec3  jz      short loc_180100ED9
0x180100ec5  jle     loc_180100F95
0x180100ecb  movzx   ebx, ax
0x180100ece  or      ebx, 80070000h
0x180100ed4  jmp     loc_180100F95
0x180100ed9  mov     rcx, [rbp+phkResult]; hKey
0x180100edd  mov     r14d, 1
0x180100ee3  lea     rax, [rbp+hKey]
0x180100ee7  mov     r9d, 20106h; samDesired
0x180100eed  xor     r8d, r8d; ulOptions
0x180100ef0  mov     [rsp+60h+var_40], rax; phkResult
0x180100ef5  mov     rdx, rdi; lpSubKey
0x180100ef8  call    cs:__imp_RegOpenKeyExW
0x180100efe  mov     ebx, eax
0x180100f00  cmp     eax, 2
0x180100f03  jnz     short loc_180100F45
0x180100f05  mov     rcx, [rbp+phkResult]; hKey
0x180100f09  lea     rax, [rbp+hKey]
0x180100f0d  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180100f16  xor     r9d, r9d; lpClass
0x180100f19  mov     [rsp+60h+var_28], rax; phkResult
0x180100f1e  xor     r8d, r8d; Reserved
0x180100f21  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180100f2a  mov     rdx, rdi; lpSubKey
0x180100f2d  mov     [rsp+60h+samDesired], 20106h; samDesired
0x180100f35  mov     dword ptr [rsp+60h+var_40], 0; dwOptions
0x180100f3d  call    cs:__imp_RegCreateKeyExW
0x180100f43  mov     ebx, eax
0x180100f45  test    ebx, ebx
0x180100f47  jz      short loc_180100F53
0x180100f49  jle     short loc_180100F95
0x180100f4b  movzx   ebx, bx
0x180100f4e  jmp     loc_180100ECE
0x180100f53  mov     rcx, [rbp+hKey]; hKey
0x180100f57  jmp     short loc_180100F5D
0x180100f59  mov     [rbp+hKey], rcx
0x180100f5d  lea     rax, [rbp+Data]
0x180100f61  xor     ebx, ebx
0x180100f63  xor     r8d, r8d; Reserved
0x180100f66  mov     rdx, rsi; lpValueName
0x180100f69  lea     r9d, [rbx+4]; dwType
0x180100f6d  mov     [rsp+60h+samDesired], r9d; cbData
0x180100f72  mov     [rsp+60h+var_40], rax; lpData
0x180100f77  call    cs:__imp_RegSetValueExW
0x180100f7d  test    eax, eax
0x180100f7f  jz      short loc_180100F90
0x180100f81  jg      short loc_180100F87
0x180100f83  mov     ebx, eax
0x180100f85  jmp     short loc_180100F90
0x180100f87  movzx   ebx, ax
0x180100f8a  or      ebx, 80070000h
0x180100f90  test    rdi, rdi
0x180100f93  jz      short loc_180100FA4
0x180100f95  mov     rcx, [rbp+hKey]; hKey
0x180100f99  test    rcx, rcx
0x180100f9c  jz      short loc_180100FA4
0x180100f9e  call    cs:__imp_RegCloseKey
0x180100fa4  cmp     r14d, 1
0x180100fa8  jnz     short loc_180100FB9
0x180100faa  mov     rcx, [rbp+phkResult]; hKey
0x180100fae  test    rcx, rcx
0x180100fb1  jz      short loc_180100FB9
0x180100fb3  call    cs:__imp_RegCloseKey
0x180100fb9  lea     r11, [rsp+60h+var_s0]
0x180100fbe  mov     eax, ebx
0x180100fc0  mov     rbx, [r11+28h]
0x180100fc4  mov     rsi, [r11+30h]
0x180100fc8  mov     rsp, r11
0x180100fcb  pop     r14
0x180100fcd  pop     rdi
0x180100fce  pop     rbp
0x180100fcf  retn
```
