# Uev::ConfigUtil::SetConfigDWORD(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong const &,long &)

- ea: `0x14006e460`
- end: `0x14006e563`
- name: `?SetConfigDWORD@ConfigUtil@Uev@@UEAA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEBKAEAJ@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14006e460`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006e4af`
- `ADVAPI32!RegOpenKeyExW` at `0x14006e4af`
- `ADVAPI32!RegCloseKey` at `0x14006e551`
- `ADVAPI32!RegCloseKey` at `0x14006e551`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e4fe`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e4fe`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e53a`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e53a`

## pseudocode

```c
bool __fastcall Uev::ConfigUtil::SetConfigDWORD(
        __int64 a1,
        HKEY *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        LPCVOID lpData,
        LSTATUS *a6)
{
  const WCHAR *v7; // rbx
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  LSTATUS Key; // eax
  bool v12; // bl
  LSTATUS v13; // eax
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
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v13 = RegSetKeyValueW(hKey[0], 0, a4, 4u, lpData, 4u);
    *a6 = v13;
    v12 = v13 == 0;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v12;
}

```

## disassembly

```asm
0x14006e460  push    rbx
0x14006e462  push    rsi
0x14006e463  push    rdi
0x14006e464  push    r14
0x14006e466  sub     rsp, 68h
0x14006e46a  mov     rsi, [rsp+88h+arg_28]
0x14006e472  mov     rdi, r9
0x14006e475  mov     rbx, r8
0x14006e478  mov     [rsp+88h+hKey], 0
0x14006e481  mov     r14, rdx
0x14006e484  mov     dword ptr [rsi], 0
0x14006e48a  cmp     qword ptr [r8+18h], 7
0x14006e48f  jbe     short loc_14006E496
0x14006e491  mov     rdx, [r8]
0x14006e494  jmp     short loc_14006E499
0x14006e496  mov     rdx, rbx; lpSubKey
0x14006e499  mov     rcx, [r14]; hKey
0x14006e49c  lea     rax, [rsp+88h+hKey]
0x14006e4a1  mov     r9d, 20106h; samDesired
0x14006e4a7  mov     [rsp+88h+phkResult], rax; phkResult
0x14006e4ac  xor     r8d, r8d; ulOptions
0x14006e4af  call    cs:__imp_RegOpenKeyExW
0x14006e4b5  mov     [rsi], eax
0x14006e4b7  cmp     eax, 2
0x14006e4ba  jnz     short loc_14006E50E
0x14006e4bc  cmp     qword ptr [rbx+18h], 7
0x14006e4c1  jbe     short loc_14006E4C6
0x14006e4c3  mov     rbx, [rbx]
0x14006e4c6  mov     rcx, [r14]; hKey
0x14006e4c9  lea     rax, [rsp+88h+hKey]
0x14006e4ce  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x14006e4d7  xor     r9d, r9d; lpClass
0x14006e4da  mov     [rsp+88h+var_50], rax; phkResult
0x14006e4df  xor     r8d, r8d; Reserved
0x14006e4e2  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006e4eb  mov     rdx, rbx; lpSubKey
0x14006e4ee  mov     [rsp+88h+samDesired], 2011Bh; samDesired
0x14006e4f6  mov     dword ptr [rsp+88h+phkResult], 0; dwOptions
0x14006e4fe  call    cs:__imp_RegCreateKeyExW
0x14006e504  mov     [rsi], eax
0x14006e506  test    eax, eax
0x14006e508  jz      short loc_14006E50E
0x14006e50a  xor     bl, bl
0x14006e50c  jmp     short loc_14006E547
0x14006e50e  cmp     qword ptr [rdi+18h], 7
0x14006e513  jbe     short loc_14006E518
0x14006e515  mov     rdi, [rdi]
0x14006e518  mov     rax, [rsp+88h+lpData]
0x14006e520  mov     r9d, 4; dwType
0x14006e526  mov     rcx, [rsp+88h+hKey]; hKey
0x14006e52b  mov     r8, rdi; lpValueName
0x14006e52e  mov     [rsp+88h+samDesired], r9d; cbData
0x14006e533  xor     edx, edx; lpSubKey
0x14006e535  mov     [rsp+88h+phkResult], rax; lpData
0x14006e53a  call    cs:__imp_RegSetKeyValueW
0x14006e540  test    eax, eax
0x14006e542  mov     [rsi], eax
0x14006e544  setz    bl
0x14006e547  mov     rcx, [rsp+88h+hKey]; hKey
0x14006e54c  test    rcx, rcx
0x14006e54f  jz      short loc_14006E557
0x14006e551  call    cs:__imp_RegCloseKey
0x14006e557  mov     al, bl
0x14006e559  add     rsp, 68h
0x14006e55d  pop     r14
0x14006e55f  pop     rdi
0x14006e560  pop     rsi
0x14006e561  pop     rbx
0x14006e562  retn
```
