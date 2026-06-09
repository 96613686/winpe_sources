# Uev::ConfigUtil::SetConfigSZ(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &)

- ea: `0x14006e9c0`
- end: `0x14006ead1`
- name: `?SetConfigSZ@ConfigUtil@Uev@@UEAA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@11AEAJ@Z`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14006e9c0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006ea0f`
- `ADVAPI32!RegOpenKeyExW` at `0x14006ea0f`
- `ADVAPI32!RegCloseKey` at `0x14006eabf`
- `ADVAPI32!RegCloseKey` at `0x14006eabf`
- `ADVAPI32!RegCreateKeyExW` at `0x14006ea5e`
- `ADVAPI32!RegCreateKeyExW` at `0x14006ea5e`
- `ADVAPI32!RegSetKeyValueW` at `0x14006eaa8`
- `ADVAPI32!RegSetKeyValueW` at `0x14006eaa8`

## pseudocode

```c
bool __fastcall Uev::ConfigUtil::SetConfigSZ(
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
    v14 = RegSetKeyValueW(hKey[0], 0, a4, 1u, v13, 2 * *((_DWORD *)lpData + 4));
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
0x14006e9c0  push    rbx
0x14006e9c2  push    rsi
0x14006e9c3  push    rdi
0x14006e9c4  push    r14
0x14006e9c6  sub     rsp, 68h
0x14006e9ca  mov     rsi, [rsp+88h+arg_28]
0x14006e9d2  mov     rdi, r9
0x14006e9d5  mov     rbx, r8
0x14006e9d8  mov     [rsp+88h+hKey], 0
0x14006e9e1  mov     r14, rdx
0x14006e9e4  mov     dword ptr [rsi], 0
0x14006e9ea  cmp     qword ptr [r8+18h], 7
0x14006e9ef  jbe     short loc_14006E9F6
0x14006e9f1  mov     rdx, [r8]
0x14006e9f4  jmp     short loc_14006E9F9
0x14006e9f6  mov     rdx, rbx; lpSubKey
0x14006e9f9  mov     rcx, [r14]; hKey
0x14006e9fc  lea     rax, [rsp+88h+hKey]
0x14006ea01  mov     r9d, 20106h; samDesired
0x14006ea07  mov     [rsp+88h+phkResult], rax; phkResult
0x14006ea0c  xor     r8d, r8d; ulOptions
0x14006ea0f  call    cs:__imp_RegOpenKeyExW
0x14006ea15  mov     [rsi], eax
0x14006ea17  cmp     eax, 2
0x14006ea1a  jnz     short loc_14006EA6E
0x14006ea1c  cmp     qword ptr [rbx+18h], 7
0x14006ea21  jbe     short loc_14006EA26
0x14006ea23  mov     rbx, [rbx]
0x14006ea26  mov     rcx, [r14]; hKey
0x14006ea29  lea     rax, [rsp+88h+hKey]
0x14006ea2e  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x14006ea37  xor     r9d, r9d; lpClass
0x14006ea3a  mov     [rsp+88h+var_50], rax; phkResult
0x14006ea3f  xor     r8d, r8d; Reserved
0x14006ea42  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006ea4b  mov     rdx, rbx; lpSubKey
0x14006ea4e  mov     [rsp+88h+samDesired], 2011Bh; samDesired
0x14006ea56  mov     dword ptr [rsp+88h+phkResult], 0; dwOptions
0x14006ea5e  call    cs:__imp_RegCreateKeyExW
0x14006ea64  mov     [rsi], eax
0x14006ea66  test    eax, eax
0x14006ea68  jz      short loc_14006EA6E
0x14006ea6a  xor     bl, bl
0x14006ea6c  jmp     short loc_14006EAB5
0x14006ea6e  mov     rax, [rsp+88h+lpData]
0x14006ea76  mov     ecx, [rax+10h]
0x14006ea79  add     ecx, ecx
0x14006ea7b  cmp     qword ptr [rax+18h], 7
0x14006ea80  jbe     short loc_14006EA85
0x14006ea82  mov     rax, [rax]
0x14006ea85  cmp     qword ptr [rdi+18h], 7
0x14006ea8a  jbe     short loc_14006EA8F
0x14006ea8c  mov     rdi, [rdi]
0x14006ea8f  mov     [rsp+88h+samDesired], ecx; cbData
0x14006ea93  mov     r9d, 1; dwType
0x14006ea99  mov     rcx, [rsp+88h+hKey]; hKey
0x14006ea9e  mov     r8, rdi; lpValueName
0x14006eaa1  xor     edx, edx; lpSubKey
0x14006eaa3  mov     [rsp+88h+phkResult], rax; lpData
0x14006eaa8  call    cs:__imp_RegSetKeyValueW
0x14006eaae  test    eax, eax
0x14006eab0  mov     [rsi], eax
0x14006eab2  setz    bl
0x14006eab5  mov     rcx, [rsp+88h+hKey]; hKey
0x14006eaba  test    rcx, rcx
0x14006eabd  jz      short loc_14006EAC5
0x14006eabf  call    cs:__imp_RegCloseKey
0x14006eac5  mov     al, bl
0x14006eac7  add     rsp, 68h
0x14006eacb  pop     r14
0x14006eacd  pop     rdi
0x14006eace  pop     rsi
0x14006eacf  pop     rbx
0x14006ead0  retn
```
