# DCCDNUtil_SetRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x1801011cc`
- end: `0x180101363`
- name: `?DCCDNUtil_SetRegistryQWORD@@YAJPEAUHKEY__@@PEBG1_K@Z`
- size: `407`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18006037c`
- `0x180086c10`
- `0x18009c3e4`
- `0x18009d6dc`
- `0x1800b85c0`
- `0x1800d32a0`
- `0x1800e3758`

## callees

- `0x1800117dc`
- `0x1801011cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010130a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010130a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801012cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801012cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180101249`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180101249`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101346`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101346`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180101288`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180101288`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_SetRegistryQWORD(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4)
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
  __int64 Data; // [rsp+98h] [rbp+38h] BYREF

  Data = a4;
  phkResult = a1;
  hKey[0] = 0;
  if ( !a1 )
  {
    v6 = 386;
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
    v6 = 387;
    goto LABEL_3;
  }
  v8 = 0;
  if ( !a2 )
  {
    hKey[0] = a1;
LABEL_20:
    Key = 0;
    v10 = RegSetValueExW(a1, a3, 0, 0xBu, (const BYTE *)&Data, 8u);
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
0x1801011cc  mov     rax, rsp
0x1801011cf  mov     [rax+10h], rbx
0x1801011d3  mov     [rax+18h], rsi
0x1801011d7  mov     [rax+20h], r9
0x1801011db  mov     [rax+8], rcx
0x1801011df  push    rbp
0x1801011e0  push    rdi
0x1801011e1  push    r14
0x1801011e3  mov     rbp, rsp
0x1801011e6  sub     rsp, 60h
0x1801011ea  mov     [rbp+hKey], 0
0x1801011f2  mov     rsi, r8
0x1801011f5  mov     rdi, rdx
0x1801011f8  test    rcx, rcx
0x1801011fb  jnz     short loc_18010121F
0x1801011fd  mov     edx, 182h; void *
0x180101202  mov     rcx, [rbp+18h]; this
0x180101206  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18010120d  mov     ebx, 80070057h
0x180101212  mov     r9d, ebx; char *
0x180101215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010121a  jmp     loc_18010134C
0x18010121f  test    rsi, rsi
0x180101222  jnz     short loc_18010122B
0x180101224  mov     edx, 183h
0x180101229  jmp     short loc_180101202
0x18010122b  xor     r14d, r14d
0x18010122e  test    rdi, rdi
0x180101231  jz      loc_1801012E9
0x180101237  cmp     rcx, 0FFFFFFFF80000001h
0x18010123e  jnz     short loc_180101273
0x180101240  lea     rdx, [rbp+phkResult]; phkResult
0x180101244  mov     ecx, 20106h; samDesired
0x180101249  call    cs:__imp_RegOpenCurrentUser
0x18010124f  mov     ebx, eax
0x180101251  test    eax, eax
0x180101253  jz      short loc_180101269
0x180101255  jle     loc_180101328
0x18010125b  movzx   ebx, ax
0x18010125e  or      ebx, 80070000h
0x180101264  jmp     loc_180101328
0x180101269  mov     rcx, [rbp+phkResult]; hKey
0x18010126d  mov     r14d, 1
0x180101273  lea     rax, [rbp+hKey]
0x180101277  mov     r9d, 20106h; samDesired
0x18010127d  xor     r8d, r8d; ulOptions
0x180101280  mov     [rsp+60h+var_40], rax; phkResult
0x180101285  mov     rdx, rdi; lpSubKey
0x180101288  call    cs:__imp_RegOpenKeyExW
0x18010128e  mov     ebx, eax
0x180101290  cmp     eax, 2
0x180101293  jnz     short loc_1801012D5
0x180101295  mov     rcx, [rbp+phkResult]; hKey
0x180101299  lea     rax, [rbp+hKey]
0x18010129d  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1801012a6  xor     r9d, r9d; lpClass
0x1801012a9  mov     [rsp+60h+var_28], rax; phkResult
0x1801012ae  xor     r8d, r8d; Reserved
0x1801012b1  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801012ba  mov     rdx, rdi; lpSubKey
0x1801012bd  mov     [rsp+60h+samDesired], 20106h; samDesired
0x1801012c5  mov     dword ptr [rsp+60h+var_40], 0; dwOptions
0x1801012cd  call    cs:__imp_RegCreateKeyExW
0x1801012d3  mov     ebx, eax
0x1801012d5  test    ebx, ebx
0x1801012d7  jz      short loc_1801012E3
0x1801012d9  jle     short loc_180101328
0x1801012db  movzx   ebx, bx
0x1801012de  jmp     loc_18010125E
0x1801012e3  mov     rcx, [rbp+hKey]; hKey
0x1801012e7  jmp     short loc_1801012ED
0x1801012e9  mov     [rbp+hKey], rcx
0x1801012ed  lea     rax, [rbp+Data]
0x1801012f1  mov     [rsp+60h+samDesired], 8; cbData
0x1801012f9  xor     ebx, ebx
0x1801012fb  mov     [rsp+60h+var_40], rax; lpData
0x180101300  xor     r8d, r8d; Reserved
0x180101303  mov     rdx, rsi; lpValueName
0x180101306  lea     r9d, [rbx+0Bh]; dwType
0x18010130a  call    cs:__imp_RegSetValueExW
0x180101310  test    eax, eax
0x180101312  jz      short loc_180101323
0x180101314  jg      short loc_18010131A
0x180101316  mov     ebx, eax
0x180101318  jmp     short loc_180101323
0x18010131a  movzx   ebx, ax
0x18010131d  or      ebx, 80070000h
0x180101323  test    rdi, rdi
0x180101326  jz      short loc_180101337
0x180101328  mov     rcx, [rbp+hKey]; hKey
0x18010132c  test    rcx, rcx
0x18010132f  jz      short loc_180101337
0x180101331  call    cs:__imp_RegCloseKey
0x180101337  cmp     r14d, 1
0x18010133b  jnz     short loc_18010134C
0x18010133d  mov     rcx, [rbp+phkResult]; hKey
0x180101341  test    rcx, rcx
0x180101344  jz      short loc_18010134C
0x180101346  call    cs:__imp_RegCloseKey
0x18010134c  lea     r11, [rsp+60h+var_s0]
0x180101351  mov     eax, ebx
0x180101353  mov     rbx, [r11+28h]
0x180101357  mov     rsi, [r11+30h]
0x18010135b  mov     rsp, r11
0x18010135e  pop     r14
0x180101360  pop     rdi
0x180101361  pop     rbp
0x180101362  retn
```
