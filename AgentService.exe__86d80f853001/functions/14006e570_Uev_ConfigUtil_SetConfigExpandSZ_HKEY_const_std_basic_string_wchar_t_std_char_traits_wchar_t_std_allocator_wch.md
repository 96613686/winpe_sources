# Uev::ConfigUtil::SetConfigExpandSZ(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &)

- ea: `0x14006e570`
- end: `0x14006e681`
- name: `?SetConfigExpandSZ@ConfigUtil@Uev@@UEAA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@11AEAJ@Z`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14006e570`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006e5bf`
- `ADVAPI32!RegOpenKeyExW` at `0x14006e5bf`
- `ADVAPI32!RegCloseKey` at `0x14006e66f`
- `ADVAPI32!RegCloseKey` at `0x14006e66f`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e60e`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e60e`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e658`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e658`

## pseudocode

```c
bool __fastcall Uev::ConfigUtil::SetConfigExpandSZ(
        __int64 a1,
        HKEY *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const void **lpData,
        LSTATUS *a6)
{
  const WCHAR *v7; // rbx
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  LSTATUS Key; // eax
  bool v12; // bl
  const void *v13; // rax
  LSTATUS v14; // eax
  HKEY hKey[7]; // [rsp+50h] [rbp-38h] BYREF

  v7 = a3;
  hKey[0] = 0;
  *a6 = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v9 = a3;
  else
    v9 = *(const WCHAR **)a3;
  v10 = RegOpenKeyExW(*a2, v9, 0, 0x20106u, hKey);
  *a6 = v10;
  if ( v10 != 2 )
    goto LABEL_9;
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(const WCHAR **)v7;
  Key = RegCreateKeyExW(*a2, v7, 0, 0, 0, 0x2011Bu, 0, hKey, 0);
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
    v14 = RegSetKeyValueW(hKey[0], 0, a4, 2u, v13, 2 * *((_DWORD *)lpData + 4));
    *a6 = v14;
    v12 = v14 == 0;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v12;
}

```

## disassembly

```asm
0x14006e570  push    rbx
0x14006e572  push    rsi
0x14006e573  push    rdi
0x14006e574  push    r14
0x14006e576  sub     rsp, 68h
0x14006e57a  mov     rsi, [rsp+88h+arg_28]
0x14006e582  mov     rdi, r9
0x14006e585  mov     rbx, r8
0x14006e588  mov     [rsp+88h+hKey], 0
0x14006e591  mov     r14, rdx
0x14006e594  mov     dword ptr [rsi], 0
0x14006e59a  cmp     qword ptr [r8+18h], 7
0x14006e59f  jbe     short loc_14006E5A6
0x14006e5a1  mov     rdx, [r8]
0x14006e5a4  jmp     short loc_14006E5A9
0x14006e5a6  mov     rdx, rbx; lpSubKey
0x14006e5a9  mov     rcx, [r14]; hKey
0x14006e5ac  lea     rax, [rsp+88h+hKey]
0x14006e5b1  mov     r9d, 20106h; samDesired
0x14006e5b7  mov     [rsp+88h+phkResult], rax; phkResult
0x14006e5bc  xor     r8d, r8d; ulOptions
0x14006e5bf  call    cs:__imp_RegOpenKeyExW
0x14006e5c5  mov     [rsi], eax
0x14006e5c7  cmp     eax, 2
0x14006e5ca  jnz     short loc_14006E61E
0x14006e5cc  cmp     qword ptr [rbx+18h], 7
0x14006e5d1  jbe     short loc_14006E5D6
0x14006e5d3  mov     rbx, [rbx]
0x14006e5d6  mov     rcx, [r14]; hKey
0x14006e5d9  lea     rax, [rsp+88h+hKey]
0x14006e5de  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x14006e5e7  xor     r9d, r9d; lpClass
0x14006e5ea  mov     [rsp+88h+var_50], rax; phkResult
0x14006e5ef  xor     r8d, r8d; Reserved
0x14006e5f2  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006e5fb  mov     rdx, rbx; lpSubKey
0x14006e5fe  mov     [rsp+88h+samDesired], 2011Bh; samDesired
0x14006e606  mov     dword ptr [rsp+88h+phkResult], 0; dwOptions
0x14006e60e  call    cs:__imp_RegCreateKeyExW
0x14006e614  mov     [rsi], eax
0x14006e616  test    eax, eax
0x14006e618  jz      short loc_14006E61E
0x14006e61a  xor     bl, bl
0x14006e61c  jmp     short loc_14006E665
0x14006e61e  mov     rax, [rsp+88h+lpData]
0x14006e626  mov     ecx, [rax+10h]
0x14006e629  add     ecx, ecx
0x14006e62b  cmp     qword ptr [rax+18h], 7
0x14006e630  jbe     short loc_14006E635
0x14006e632  mov     rax, [rax]
0x14006e635  cmp     qword ptr [rdi+18h], 7
0x14006e63a  jbe     short loc_14006E63F
0x14006e63c  mov     rdi, [rdi]
0x14006e63f  mov     [rsp+88h+samDesired], ecx; cbData
0x14006e643  mov     r9d, 2; dwType
0x14006e649  mov     rcx, [rsp+88h+hKey]; hKey
0x14006e64e  mov     r8, rdi; lpValueName
0x14006e651  xor     edx, edx; lpSubKey
0x14006e653  mov     [rsp+88h+phkResult], rax; lpData
0x14006e658  call    cs:__imp_RegSetKeyValueW
0x14006e65e  test    eax, eax
0x14006e660  mov     [rsi], eax
0x14006e662  setz    bl
0x14006e665  mov     rcx, [rsp+88h+hKey]; hKey
0x14006e66a  test    rcx, rcx
0x14006e66d  jz      short loc_14006E675
0x14006e66f  call    cs:__imp_RegCloseKey
0x14006e675  mov     al, bl
0x14006e677  add     rsp, 68h
0x14006e67b  pop     r14
0x14006e67d  pop     rdi
0x14006e67e  pop     rsi
0x14006e67f  pop     rbx
0x14006e680  retn
```
