# SetValueData(HKEY__ *,ushort const *,uchar const *,ulong)

- ea: `0x180013b88`
- end: `0x180013c8f`
- name: `?SetValueData@@YAHPEAUHKEY__@@PEBGPEBEK@Z`
- size: `263`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800135d8`

## callees

- `0x1800035c8`
- `0x180013b88`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180013c26`
- `ADVAPI32!RegCreateKeyExW` at `0x180013c26`
- `ADVAPI32!RegCloseKey` at `0x180013c5a`
- `ADVAPI32!RegCloseKey` at `0x180013c5a`
- `ADVAPI32!RegSetValueExW` at `0x180013c49`
- `ADVAPI32!RegSetValueExW` at `0x180013c49`

## pseudocode

```c
__int64 __fastcall SetValueData(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData, DWORD cbData)
{
  unsigned int v4; // ebx
  unsigned int v9; // edi
  DWORD dwDisposition; // [rsp+50h] [rbp-78h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-70h] BYREF
  WCHAR SubKey[16]; // [rsp+60h] [rbp-68h] BYREF

  v4 = 0;
  hKeya = 0;
  dwDisposition = 0;
  v9 = 0;
  do
  {
    if ( v9 >= 0x40 )
      break;
    StringCchPrintfW(SubKey, 0x10u, L"%lu", v9);
    if ( !RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &hKeya, &dwDisposition) )
    {
      if ( !RegSetValueExW(hKeya, lpValueName, 0, 3u, lpData, cbData) )
        v4 = 1;
      RegCloseKey(hKeya);
    }
    ++v9;
  }
  while ( !v4 );
  return v4;
}

```

## disassembly

```asm
0x180013b88  push    rbx
0x180013b8a  push    rbp
0x180013b8b  push    rsi
0x180013b8c  push    rdi
0x180013b8d  push    r13
0x180013b8f  push    r14
0x180013b91  push    r15
0x180013b93  sub     rsp, 90h
0x180013b9a  mov     rax, cs:__security_cookie
0x180013ba1  xor     rax, rsp
0x180013ba4  mov     [rsp+0C8h+var_48], rax
0x180013bac  xor     ebx, ebx
0x180013bae  mov     r14d, r9d
0x180013bb1  mov     rbp, r8
0x180013bb4  mov     [rsp+0C8h+hKey], rbx
0x180013bb9  mov     rsi, rdx
0x180013bbc  mov     [rsp+0C8h+dwDisposition], ebx
0x180013bc0  mov     r15, rcx
0x180013bc3  xor     edi, edi
0x180013bc5  lea     r13d, [rbx+1]
0x180013bc9  cmp     edi, 40h ; '@'
0x180013bcc  jnb     loc_180013C6B
0x180013bd2  mov     r9d, edi
0x180013bd5  lea     r8, aLu; "%lu"
0x180013bdc  mov     edx, 10h; unsigned __int64
0x180013be1  lea     rcx, [rsp+0C8h+SubKey]; unsigned __int16 *
0x180013be6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013beb  lea     rax, [rsp+0C8h+dwDisposition]
0x180013bf0  xor     r9d, r9d; lpClass
0x180013bf3  mov     [rsp+0C8h+lpdwDisposition], rax; lpdwDisposition
0x180013bf8  lea     rdx, [rsp+0C8h+SubKey]; lpSubKey
0x180013bfd  lea     rax, [rsp+0C8h+hKey]
0x180013c02  xor     r8d, r8d; Reserved
0x180013c05  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180013c0a  mov     rcx, r15; hKey
0x180013c0d  mov     [rsp+0C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013c16  mov     [rsp+0C8h+samDesired], 20006h; samDesired
0x180013c1e  mov     [rsp+0C8h+dwOptions], 0; dwOptions
0x180013c26  call    cs:__imp_RegCreateKeyExW
0x180013c2c  test    eax, eax
0x180013c2e  jnz     short loc_180013C60
0x180013c30  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180013c35  lea     r9d, [rax+3]; dwType
0x180013c39  mov     [rsp+0C8h+samDesired], r14d; cbData
0x180013c3e  xor     r8d, r8d; Reserved
0x180013c41  mov     rdx, rsi; lpValueName
0x180013c44  mov     qword ptr [rsp+0C8h+dwOptions], rbp; lpData
0x180013c49  call    cs:__imp_RegSetValueExW
0x180013c4f  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180013c54  test    eax, eax
0x180013c56  cmovz   ebx, r13d
0x180013c5a  call    cs:__imp_RegCloseKey
0x180013c60  add     edi, r13d
0x180013c63  test    ebx, ebx
0x180013c65  jz      loc_180013BC9
0x180013c6b  mov     eax, ebx
0x180013c6d  mov     rcx, [rsp+0C8h+var_48]
0x180013c75  xor     rcx, rsp; StackCookie
0x180013c78  call    __security_check_cookie
0x180013c7d  add     rsp, 90h
0x180013c84  pop     r15
0x180013c86  pop     r14
0x180013c88  pop     r13
0x180013c8a  pop     rdi
0x180013c8b  pop     rsi
0x180013c8c  pop     rbp
0x180013c8d  pop     rbx
0x180013c8e  retn
```
