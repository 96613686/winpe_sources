# sub_1800BFBE0

- ea: `0x1800bfbe0`
- end: `0x1800bfce6`
- name: `sub_1800BFBE0`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800bfbe0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bfc7e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bfc7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bfcd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bfcd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bfc2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bfc2f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bfcbd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bfcbd`

## pseudocode

```c
bool __fastcall sub_1800BFBE0(__int64 a1, HKEY *a2, const WCHAR *a3, const WCHAR *a4, LPCVOID lpData, LSTATUS *a6)
{
  const WCHAR *v7; // rbx
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  LSTATUS Key; // eax
  bool v12; // bl
  LSTATUS v13; // eax
  tagPOINT hKey; // [rsp+50h] [rbp-38h] BYREF

  v7 = a3;
  hKey = 0;
  *a6 = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v9 = a3;
  else
    v9 = *(const WCHAR **)a3;
  v10 = RegOpenKeyExW(*a2, v9, 0, 0x20106u, (PHKEY)&hKey);
  *a6 = v10;
  if ( v10 != 2 )
    goto LABEL_9;
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(const WCHAR **)v7;
  Key = RegCreateKeyExW(*a2, v7, 0, 0, 0, 0x2011Bu, 0, (PHKEY)&hKey, 0);
  *a6 = Key;
  if ( Key )
  {
    v12 = 0;
  }
  else
  {
LABEL_9:
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v13 = RegSetKeyValueW(*(HKEY *)&hKey, 0, a4, 0xBu, lpData, 8u);
    *a6 = v13;
    v12 = v13 == 0;
  }
  if ( hKey )
    RegCloseKey(*(HKEY *)&hKey);
  return v12;
}

```

## disassembly

```asm
0x1800bfbe0  push    rbx
0x1800bfbe2  push    rsi
0x1800bfbe3  push    rdi
0x1800bfbe4  push    r14
0x1800bfbe6  sub     rsp, 68h
0x1800bfbea  mov     rsi, [rsp+88h+arg_28]
0x1800bfbf2  mov     rdi, r9
0x1800bfbf5  mov     rbx, r8
0x1800bfbf8  mov     qword ptr [rsp+88h+hKey.x], 0
0x1800bfc01  mov     r14, rdx
0x1800bfc04  mov     dword ptr [rsi], 0
0x1800bfc0a  cmp     qword ptr [r8+18h], 7
0x1800bfc0f  jbe     short loc_1800BFC16
0x1800bfc11  mov     rdx, [r8]
0x1800bfc14  jmp     short loc_1800BFC19
0x1800bfc16  mov     rdx, rbx; lpSubKey
0x1800bfc19  mov     rcx, [r14]; hKey
0x1800bfc1c  lea     rax, [rsp+88h+hKey]
0x1800bfc21  mov     r9d, 20106h; samDesired
0x1800bfc27  mov     [rsp+88h+phkResult], rax; phkResult
0x1800bfc2c  xor     r8d, r8d; ulOptions
0x1800bfc2f  call    cs:RegOpenKeyExW
0x1800bfc35  mov     [rsi], eax
0x1800bfc37  cmp     eax, 2
0x1800bfc3a  jnz     short loc_1800BFC8E
0x1800bfc3c  cmp     qword ptr [rbx+18h], 7
0x1800bfc41  jbe     short loc_1800BFC46
0x1800bfc43  mov     rbx, [rbx]
0x1800bfc46  mov     rcx, [r14]; hKey
0x1800bfc49  lea     rax, [rsp+88h+hKey]
0x1800bfc4e  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800bfc57  xor     r9d, r9d; lpClass
0x1800bfc5a  mov     [rsp+88h+var_50], rax; phkResult
0x1800bfc5f  xor     r8d, r8d; Reserved
0x1800bfc62  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800bfc6b  mov     rdx, rbx; lpSubKey
0x1800bfc6e  mov     [rsp+88h+samDesired], 2011Bh; samDesired
0x1800bfc76  mov     dword ptr [rsp+88h+phkResult], 0; dwOptions
0x1800bfc7e  call    cs:RegCreateKeyExW
0x1800bfc84  mov     [rsi], eax
0x1800bfc86  test    eax, eax
0x1800bfc88  jz      short loc_1800BFC8E
0x1800bfc8a  xor     bl, bl
0x1800bfc8c  jmp     short loc_1800BFCCA
0x1800bfc8e  cmp     qword ptr [rdi+18h], 7
0x1800bfc93  jbe     short loc_1800BFC98
0x1800bfc95  mov     rdi, [rdi]
0x1800bfc98  mov     rax, [rsp+88h+lpData]
0x1800bfca0  mov     r9d, 0Bh; dwType
0x1800bfca6  mov     rcx, qword ptr [rsp+88h+hKey.x]; hKey
0x1800bfcab  mov     r8, rdi; lpValueName
0x1800bfcae  mov     [rsp+88h+samDesired], 8; cbData
0x1800bfcb6  xor     edx, edx; lpSubKey
0x1800bfcb8  mov     [rsp+88h+phkResult], rax; lpData
0x1800bfcbd  call    cs:RegSetKeyValueW
0x1800bfcc3  test    eax, eax
0x1800bfcc5  mov     [rsi], eax
0x1800bfcc7  setz    bl
0x1800bfcca  mov     rcx, qword ptr [rsp+88h+hKey.x]; hKey
0x1800bfccf  test    rcx, rcx
0x1800bfcd2  jz      short loc_1800BFCDA
0x1800bfcd4  call    cs:RegCloseKey
0x1800bfcda  mov     al, bl
0x1800bfcdc  add     rsp, 68h
0x1800bfce0  pop     r14
0x1800bfce2  pop     rdi
0x1800bfce3  pop     rsi
0x1800bfce4  pop     rbx
0x1800bfce5  retn
```
