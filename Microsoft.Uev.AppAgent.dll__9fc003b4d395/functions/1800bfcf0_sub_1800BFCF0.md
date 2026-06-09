# sub_1800BFCF0

- ea: `0x1800bfcf0`
- end: `0x1800bfe01`
- name: `sub_1800BFCF0`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800bfcf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bfd8e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bfd8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bfdef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bfdef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bfd3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bfd3f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bfdd8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bfdd8`

## pseudocode

```c
bool __fastcall sub_1800BFCF0(__int64 a1, HKEY *a2, const WCHAR *a3, const WCHAR *a4, const void **lpData, LSTATUS *a6)
{
  const WCHAR *v7; // rbx
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  LSTATUS Key; // eax
  bool v12; // bl
  const void *v13; // rax
  LSTATUS v14; // eax
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
    v13 = lpData;
    if ( (unsigned __int64)lpData[3] > 7 )
      v13 = *lpData;
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v14 = RegSetKeyValueW(*(HKEY *)&hKey, 0, a4, 1u, v13, 2 * *((_DWORD *)lpData + 4));
    *a6 = v14;
    v12 = v14 == 0;
  }
  if ( hKey )
    RegCloseKey(*(HKEY *)&hKey);
  return v12;
}

```

## disassembly

```asm
0x1800bfcf0  push    rbx
0x1800bfcf2  push    rsi
0x1800bfcf3  push    rdi
0x1800bfcf4  push    r14
0x1800bfcf6  sub     rsp, 68h
0x1800bfcfa  mov     rsi, [rsp+88h+arg_28]
0x1800bfd02  mov     rdi, r9
0x1800bfd05  mov     rbx, r8
0x1800bfd08  mov     qword ptr [rsp+88h+hKey.x], 0
0x1800bfd11  mov     r14, rdx
0x1800bfd14  mov     dword ptr [rsi], 0
0x1800bfd1a  cmp     qword ptr [r8+18h], 7
0x1800bfd1f  jbe     short loc_1800BFD26
0x1800bfd21  mov     rdx, [r8]
0x1800bfd24  jmp     short loc_1800BFD29
0x1800bfd26  mov     rdx, rbx; lpSubKey
0x1800bfd29  mov     rcx, [r14]; hKey
0x1800bfd2c  lea     rax, [rsp+88h+hKey]
0x1800bfd31  mov     r9d, 20106h; samDesired
0x1800bfd37  mov     [rsp+88h+phkResult], rax; phkResult
0x1800bfd3c  xor     r8d, r8d; ulOptions
0x1800bfd3f  call    cs:RegOpenKeyExW
0x1800bfd45  mov     [rsi], eax
0x1800bfd47  cmp     eax, 2
0x1800bfd4a  jnz     short loc_1800BFD9E
0x1800bfd4c  cmp     qword ptr [rbx+18h], 7
0x1800bfd51  jbe     short loc_1800BFD56
0x1800bfd53  mov     rbx, [rbx]
0x1800bfd56  mov     rcx, [r14]; hKey
0x1800bfd59  lea     rax, [rsp+88h+hKey]
0x1800bfd5e  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800bfd67  xor     r9d, r9d; lpClass
0x1800bfd6a  mov     [rsp+88h+var_50], rax; phkResult
0x1800bfd6f  xor     r8d, r8d; Reserved
0x1800bfd72  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800bfd7b  mov     rdx, rbx; lpSubKey
0x1800bfd7e  mov     [rsp+88h+samDesired], 2011Bh; samDesired
0x1800bfd86  mov     dword ptr [rsp+88h+phkResult], 0; dwOptions
0x1800bfd8e  call    cs:RegCreateKeyExW
0x1800bfd94  mov     [rsi], eax
0x1800bfd96  test    eax, eax
0x1800bfd98  jz      short loc_1800BFD9E
0x1800bfd9a  xor     bl, bl
0x1800bfd9c  jmp     short loc_1800BFDE5
0x1800bfd9e  mov     rax, [rsp+88h+lpData]
0x1800bfda6  mov     ecx, [rax+10h]
0x1800bfda9  add     ecx, ecx
0x1800bfdab  cmp     qword ptr [rax+18h], 7
0x1800bfdb0  jbe     short loc_1800BFDB5
0x1800bfdb2  mov     rax, [rax]
0x1800bfdb5  cmp     qword ptr [rdi+18h], 7
0x1800bfdba  jbe     short loc_1800BFDBF
0x1800bfdbc  mov     rdi, [rdi]
0x1800bfdbf  mov     [rsp+88h+samDesired], ecx; cbData
0x1800bfdc3  mov     r9d, 1; dwType
0x1800bfdc9  mov     rcx, qword ptr [rsp+88h+hKey.x]; hKey
0x1800bfdce  mov     r8, rdi; lpValueName
0x1800bfdd1  xor     edx, edx; lpSubKey
0x1800bfdd3  mov     [rsp+88h+phkResult], rax; lpData
0x1800bfdd8  call    cs:RegSetKeyValueW
0x1800bfdde  test    eax, eax
0x1800bfde0  mov     [rsi], eax
0x1800bfde2  setz    bl
0x1800bfde5  mov     rcx, qword ptr [rsp+88h+hKey.x]; hKey
0x1800bfdea  test    rcx, rcx
0x1800bfded  jz      short loc_1800BFDF5
0x1800bfdef  call    cs:RegCloseKey
0x1800bfdf5  mov     al, bl
0x1800bfdf7  add     rsp, 68h
0x1800bfdfb  pop     r14
0x1800bfdfd  pop     rdi
0x1800bfdfe  pop     rsi
0x1800bfdff  pop     rbx
0x1800bfe00  retn
```
