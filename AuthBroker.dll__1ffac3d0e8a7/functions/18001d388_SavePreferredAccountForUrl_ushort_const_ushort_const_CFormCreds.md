# SavePreferredAccountForUrl(ushort const *,ushort const *,CFormCreds *)

- ea: `0x18001d388`
- end: `0x18001d54c`
- name: `?SavePreferredAccountForUrl@@YAKPEBG0PEAVCFormCreds@@@Z`
- size: `452`
- prototype: `unsigned int __fastcall(const wchar_t *lpwszUrl, const wchar_t *lpwszUserName, CFormCreds *pThis)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014090`
- `0x18001d150`

## callees

- `0x18001d388`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d50e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d51e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d50e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d51e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d4fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d4fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d404`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d448`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d404`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d448`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d493`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d493`
- `ntdll!_wcsicmp` at `0x18001d4c3`
- `ntdll!_wcsicmp` at `0x18001d4c3`

## string_xrefs

- `0x18001d3d1`: `Software\Microsoft\Web Authentication Broker`

## pseudocode

```c
__int64 __fastcall SavePreferredAccountForUrl(const wchar_t *lpwszUrl, const wchar_t *lpwszUserName, CFormCreds *pThis)
{
  unsigned int v6; // ebx
  __int64 v7; // rbx
  __int64 v8; // rax
  unsigned int dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int dwType; // [rsp+54h] [rbp-ACh] BYREF
  HKEY__ *hSiteKey; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int dwSize; // [rsp+60h] [rbp-A0h] BYREF
  HKEY__ *hWABRootKey; // [rsp+68h] [rbp-98h] BYREF
  wchar_t wzValue[264]; // [rsp+70h] [rbp-90h] BYREF

  hWABRootKey = 0;
  hSiteKey = 0;
  dwDisposition = 0;
  v6 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Web Authentication Broker",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hWABRootKey,
         0);
  if ( !v6 )
  {
    v6 = RegCreateKeyExW(hWABRootKey, lpwszUrl, 0, 0, 0, 0xF003Fu, 0, &hSiteKey, &dwDisposition);
    if ( !v6 )
    {
      v7 = -1;
      if ( dwDisposition == 2 )
      {
        dwType = 0;
        dwSize = 520;
        if ( !RegQueryValueExW(hSiteKey, 0, 0, &dwType, (LPBYTE)wzValue, &dwSize) && dwType == 1 )
        {
          v8 = -1;
          do
            ++v8;
          while ( wzValue[v8] );
          if ( v8 && _wcsicmp(wzValue, lpwszUserName) )
            pThis->_fAccountSwitched = 1;
        }
      }
      do
        ++v7;
      while ( lpwszUserName[v7] );
      v6 = RegSetValueExW(hSiteKey, 0, 0, 1u, (const BYTE *)lpwszUserName, 2 * v7 + 2);
    }
  }
  if ( hSiteKey )
    RegCloseKey(hSiteKey);
  if ( hWABRootKey )
    RegCloseKey(hWABRootKey);
  return v6;
}

```

## disassembly

```asm
0x18001d388  mov     [rsp-8+arg_18], rbx
0x18001d38d  push    rbp
0x18001d38e  push    rsi
0x18001d38f  push    rdi
0x18001d390  push    r14
0x18001d392  push    r15
0x18001d394  lea     rbp, [rsp-190h]
0x18001d39c  sub     rsp, 290h
0x18001d3a3  mov     rax, cs:__security_cookie
0x18001d3aa  xor     rax, rsp
0x18001d3ad  mov     [rbp+1B0h+var_30], rax
0x18001d3b4  xor     r15d, r15d
0x18001d3b7  lea     rax, [rsp+2B0h+hWABRootKey]
0x18001d3bc  mov     [rsp+2B0h+lpdwDisposition], r15; lpdwDisposition
0x18001d3c1  mov     r14, pThis
0x18001d3c4  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001d3c9  mov     rdi, lpwszUserName
0x18001d3cc  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001d3d1  lea     lpwszUserName, aSoftwareMicros_5; "Software\\Microsoft\\Web Authentication"...
0x18001d3d8  mov     rsi, lpwszUrl
0x18001d3db  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x18001d3e3  xor     r9d, r9d; lpClass
0x18001d3e6  mov     [rsp+2B0h+dwOptions], r15d; dwOptions
0x18001d3eb  xor     r8d, r8d; Reserved
0x18001d3ee  mov     [rsp+2B0h+hWABRootKey], r15
0x18001d3f3  mov     lpwszUrl, 0FFFFFFFF80000001h; hKey
0x18001d3fa  mov     [rsp+2B0h+hSiteKey], r15
0x18001d3ff  mov     [rsp+2B0h+dwDisposition], r15d
0x18001d404  call    cs:__imp_RegCreateKeyExW
0x18001d40a  mov     ebx, eax
0x18001d40c  test    eax, eax
0x18001d40e  jnz     $Cleanup_13
0x18001d414  mov     lpwszUrl, [rsp+2B0h+hWABRootKey]; hKey
0x18001d419  lea     rax, [rsp+2B0h+dwDisposition]
0x18001d41e  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x18001d423  xor     r9d, r9d; lpClass
0x18001d426  lea     rax, [rsp+2B0h+hSiteKey]
0x18001d42b  xor     r8d, r8d; Reserved
0x18001d42e  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001d433  mov     lpwszUserName, rsi; lpSubKey
0x18001d436  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001d43b  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x18001d443  mov     [rsp+2B0h+dwOptions], r15d; dwOptions
0x18001d448  call    cs:__imp_RegCreateKeyExW
0x18001d44e  mov     ebx, eax
0x18001d450  test    eax, eax
0x18001d452  jnz     $Cleanup_13
0x18001d458  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001d45c  cmp     [rsp+2B0h+dwDisposition], 2
0x18001d461  jnz     short loc_18001D4D2
0x18001d463  mov     lpwszUrl, [rsp+2B0h+hSiteKey]; hKey
0x18001d468  lea     rax, [rsp+2B0h+dwSize]
0x18001d46d  mov     qword ptr [rsp+2B0h+samDesired], rax; lpcbData
0x18001d472  lea     r9, [rsp+2B0h+dwType]; lpType
0x18001d477  lea     rax, [rsp+2B0h+wzValue]
0x18001d47c  mov     [rsp+2B0h+dwType], r15d
0x18001d481  xor     r8d, r8d; lpReserved
0x18001d484  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x18001d489  xor     edx, edx; lpValueName
0x18001d48b  mov     [rsp+2B0h+dwSize], 208h
0x18001d493  call    cs:__imp_RegQueryValueExW
0x18001d499  test    eax, eax
0x18001d49b  jnz     short loc_18001D4D2
0x18001d49d  cmp     [rsp+2B0h+dwType], 1
0x18001d4a2  jnz     short loc_18001D4D2
0x18001d4a4  lea     lpwszUrl, [rsp+2B0h+wzValue]
0x18001d4a9  mov     rax, rbx
0x18001d4ac  inc     rax
0x18001d4af  cmp     [lpwszUrl+rax*2], r15w
0x18001d4b4  jnz     short loc_18001D4AC
0x18001d4b6  test    rax, rax
0x18001d4b9  jz      short loc_18001D4D2
0x18001d4bb  mov     lpwszUserName, rdi; String2
0x18001d4be  lea     lpwszUrl, [rsp+2B0h+wzValue]; String1
0x18001d4c3  call    cs:__imp__wcsicmp
0x18001d4c9  test    eax, eax
0x18001d4cb  jz      short loc_18001D4D2
0x18001d4cd  mov     byte ptr [r14+70h], 1
0x18001d4d2  inc     rbx
0x18001d4d5  cmp     [rdi+rbx*2], r15w
0x18001d4da  jnz     short loc_18001D4D2
0x18001d4dc  mov     lpwszUrl, [rsp+2B0h+hSiteKey]; hKey
0x18001d4e1  lea     eax, ds:2[rbx*2]
0x18001d4e8  mov     [rsp+2B0h+samDesired], eax; cbData
0x18001d4ec  mov     r9d, 1; dwType
0x18001d4f2  xor     r8d, r8d; Reserved
0x18001d4f5  mov     qword ptr [rsp+2B0h+dwOptions], rdi; lpData
0x18001d4fa  xor     edx, edx; lpValueName
0x18001d4fc  call    cs:__imp_RegSetValueExW
0x18001d502  mov     ebx, eax
0x18001d504  mov     lpwszUrl, [rsp+2B0h+hSiteKey]; hKey
0x18001d509  test    lpwszUrl, lpwszUrl
0x18001d50c  jz      short loc_18001D514
0x18001d50e  call    cs:__imp_RegCloseKey
0x18001d514  mov     lpwszUrl, [rsp+2B0h+hWABRootKey]; hKey
0x18001d519  test    lpwszUrl, lpwszUrl
0x18001d51c  jz      short loc_18001D524
0x18001d51e  call    cs:__imp_RegCloseKey
0x18001d524  mov     eax, ebx
0x18001d526  mov     lpwszUrl, [rbp+1B0h+var_30]
0x18001d52d  xor     lpwszUrl, rsp; StackCookie
0x18001d530  call    __security_check_cookie
0x18001d535  mov     rbx, [rsp+2B0h+arg_18]
0x18001d53d  add     rsp, 290h
0x18001d544  pop     r15
0x18001d546  pop     r14
0x18001d548  pop     rdi
0x18001d549  pop     rsi
0x18001d54a  pop     rbp
0x18001d54b  retn
```
