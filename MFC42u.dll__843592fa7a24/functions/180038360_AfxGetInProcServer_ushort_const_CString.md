# AfxGetInProcServer(ushort const *,CString &)

- ea: `0x180038360`
- end: `0x180038488`
- name: `?AfxGetInProcServer@@YAHPEBGAEAVCString@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, struct CString *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038ad0`

## callees

- `0x18000c0a0`
- `0x18000c860`
- `0x180038360`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003844e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038462`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003844e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038462`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800383bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800383ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038415`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800383bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800383ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038415`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003843f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003843f`

## string_xrefs

- `0x1800383b1`: `CLSID`

## pseudocode

```c
__int64 __fastcall AfxGetInProcServer(LPCWSTR lpSubKey, struct CString *this)
{
  unsigned int v4; // ebx
  BYTE *Buffer; // r14
  HKEY v7; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v4 = 0;
  Buffer = (BYTE *)CString::GetBuffer(this, 260);
  cbData = 520;
  Type = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, &hKey) )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
    {
      v7 = 0;
      if ( !RegOpenKeyExW(phkResult, L"InProcServer32", 0, 0x20019u, &v7) )
      {
        LOBYTE(v4) = RegQueryValueExW(v7, &Data, 0, &Type, Buffer, &cbData) == 0;
        RegCloseKey(v7);
      }
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  CString::ReleaseBuffer(this, -1);
  return v4;
}

```

## disassembly

```asm
0x180038360  mov     [rsp-18h+arg_0], rbx
0x180038365  mov     [rsp-18h+arg_8], rsi
0x18003836a  push    rbp
0x18003836b  push    rdi
0x18003836c  push    r14
0x18003836e  mov     rbp, rsp
0x180038371  sub     rsp, 50h
0x180038375  mov     rdi, rdx
0x180038378  mov     [rbp+hKey], 0
0x180038380  mov     rsi, rcx
0x180038383  mov     edx, 104h; int
0x180038388  mov     rcx, rdi; this
0x18003838b  xor     ebx, ebx
0x18003838d  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x180038392  mov     r14, rax
0x180038395  mov     [rbp+cbData], 208h
0x18003839c  lea     rax, [rbp+hKey]
0x1800383a0  mov     [rbp+Type], ebx
0x1800383a3  mov     r9d, 20019h; samDesired
0x1800383a9  mov     [rsp+50h+phkResult], rax; phkResult
0x1800383ae  xor     r8d, r8d; ulOptions
0x1800383b1  lea     rdx, aClsid_1; "CLSID"
0x1800383b8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800383bf  call    cs:__imp_RegOpenKeyExW
0x1800383c5  test    eax, eax
0x1800383c7  jnz     loc_180038468
0x1800383cd  mov     rcx, [rbp+hKey]; hKey
0x1800383d1  lea     rax, [rbp+var_18]
0x1800383d5  mov     r9d, 20019h; samDesired
0x1800383db  mov     [rsp+50h+phkResult], rax; phkResult
0x1800383e0  xor     r8d, r8d; ulOptions
0x1800383e3  mov     [rbp+var_18], rbx
0x1800383e7  mov     rdx, rsi; lpSubKey
0x1800383ea  call    cs:__imp_RegOpenKeyExW
0x1800383f0  test    eax, eax
0x1800383f2  jnz     short loc_18003845E
0x1800383f4  mov     rcx, [rbp+var_18]; hKey
0x1800383f8  lea     rax, [rbp+var_20]
0x1800383fc  mov     r9d, 20019h; samDesired
0x180038402  mov     [rsp+50h+phkResult], rax; phkResult
0x180038407  xor     r8d, r8d; ulOptions
0x18003840a  mov     [rbp+var_20], rbx
0x18003840e  lea     rdx, aInprocserver32_1; "InProcServer32"
0x180038415  call    cs:__imp_RegOpenKeyExW
0x18003841b  test    eax, eax
0x18003841d  jnz     short loc_180038454
0x18003841f  mov     rcx, [rbp+var_20]; hKey
0x180038423  lea     rax, [rbp+cbData]
0x180038427  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003842c  lea     r9, [rbp+Type]; lpType
0x180038430  xor     r8d, r8d; lpReserved
0x180038433  mov     [rsp+50h+phkResult], r14; lpData
0x180038438  lea     rdx, Data; lpValueName
0x18003843f  call    cs:__imp_RegQueryValueExW
0x180038445  mov     rcx, [rbp+var_20]; hKey
0x180038449  test    eax, eax
0x18003844b  setz    bl
0x18003844e  call    cs:__imp_RegCloseKey
0x180038454  mov     rcx, [rbp+var_18]; hKey
0x180038458  call    cs:__imp_RegCloseKey
0x18003845e  mov     rcx, [rbp+hKey]; hKey
0x180038462  call    cs:__imp_RegCloseKey
0x180038468  or      edx, 0FFFFFFFFh; int
0x18003846b  mov     rcx, rdi; this
0x18003846e  call    ?ReleaseBuffer@CString@@QEAAXH@Z; CString::ReleaseBuffer(int)
0x180038473  mov     rsi, [rsp+50h+arg_8]
0x180038478  mov     eax, ebx
0x18003847a  mov     rbx, [rsp+50h+arg_0]
0x18003847f  add     rsp, 50h
0x180038483  pop     r14
0x180038485  pop     rdi
0x180038486  pop     rbp
0x180038487  retn
```
