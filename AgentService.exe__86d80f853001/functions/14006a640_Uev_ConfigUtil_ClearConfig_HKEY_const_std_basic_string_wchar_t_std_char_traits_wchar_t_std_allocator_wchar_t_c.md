# Uev::ConfigUtil::ClearConfig(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &)

- ea: `0x14006a640`
- end: `0x14006a6e5`
- name: `?ClearConfig@ConfigUtil@Uev@@UEAA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAJ@Z`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14006a640`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006a692`
- `ADVAPI32!RegOpenKeyExW` at `0x14006a692`
- `ADVAPI32!RegCloseKey` at `0x14006a6cc`
- `ADVAPI32!RegCloseKey` at `0x14006a6cc`
- `ADVAPI32!RegDeleteValueW` at `0x14006a6b1`
- `ADVAPI32!RegDeleteValueW` at `0x14006a6b1`

## pseudocode

```c
bool __fastcall Uev::ConfigUtil::ClearConfig(__int64 a1, HKEY *a2, __int64 a3, const WCHAR *a4, LSTATUS *a5)
{
  const WCHAR *v6; // rax
  bool v7; // di
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  v6 = (const WCHAR *)a3;
  hKey = 0;
  v7 = 1;
  *a5 = 0;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v6 = *(const WCHAR **)a3;
  v8 = RegOpenKeyExW(*a2, v6, 0, 0x20106u, &hKey);
  *a5 = v8;
  if ( v8 != 2 )
  {
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v9 = RegDeleteValueW(hKey, a4);
    *a5 = v9;
    v7 = (v9 & 0xFFFFFFFD) == 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x14006a640  mov     [rsp+arg_0], rbx
0x14006a645  mov     [rsp+arg_8], rsi
0x14006a64a  push    rdi
0x14006a64b  sub     rsp, 40h
0x14006a64f  mov     rsi, [rsp+48h+arg_20]
0x14006a654  mov     rbx, r9
0x14006a657  mov     rax, r8
0x14006a65a  mov     [rsp+48h+hKey], 0
0x14006a663  mov     r10, rdx
0x14006a666  mov     dil, 1
0x14006a669  mov     dword ptr [rsi], 0
0x14006a66f  cmp     qword ptr [r8+18h], 7
0x14006a674  jbe     short loc_14006A679
0x14006a676  mov     rax, [r8]
0x14006a679  lea     rcx, [rsp+48h+hKey]
0x14006a67e  mov     r9d, 20106h; samDesired
0x14006a684  mov     [rsp+48h+phkResult], rcx; phkResult
0x14006a689  xor     r8d, r8d; ulOptions
0x14006a68c  mov     rcx, [r10]; hKey
0x14006a68f  mov     rdx, rax; lpSubKey
0x14006a692  call    cs:__imp_RegOpenKeyExW
0x14006a698  mov     [rsi], eax
0x14006a69a  cmp     eax, 2
0x14006a69d  jz      short loc_14006A6C2
0x14006a69f  cmp     qword ptr [rbx+18h], 7
0x14006a6a4  jbe     short loc_14006A6A9
0x14006a6a6  mov     rbx, [rbx]
0x14006a6a9  mov     rcx, [rsp+48h+hKey]; hKey
0x14006a6ae  mov     rdx, rbx; lpValueName
0x14006a6b1  call    cs:__imp_RegDeleteValueW
0x14006a6b7  test    eax, 0FFFFFFFDh
0x14006a6bc  mov     [rsi], eax
0x14006a6be  setz    dil
0x14006a6c2  mov     rcx, [rsp+48h+hKey]; hKey
0x14006a6c7  test    rcx, rcx
0x14006a6ca  jz      short loc_14006A6D2
0x14006a6cc  call    cs:__imp_RegCloseKey
0x14006a6d2  mov     rbx, [rsp+48h+arg_0]
0x14006a6d7  mov     al, dil
0x14006a6da  mov     rsi, [rsp+48h+arg_8]
0x14006a6df  add     rsp, 40h
0x14006a6e3  pop     rdi
0x14006a6e4  retn
```
