# WsRestoreGlobalMappingsFromRegistry

- ea: `0x18000d904`
- end: `0x18000da89`
- name: `WsRestoreGlobalMappingsFromRegistry`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002d530`

## callees

- `0x18000d904`
- `0x18001e420`
- `0x1800299a4`
- `0x18002e2b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000d9ee`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000d9ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d967`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d9d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d967`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d9d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da4d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d9a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000d9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da58`

## pseudocode

```c
LSTATUS WsRestoreGlobalMappingsFromRegistry()
{
  DWORD v0; // ebx
  LSTATUS result; // eax
  char v2; // cl
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h]
  WCHAR v7; // [rsp+60h] [rbp-A0h] BYREF
  int v8; // [rsp+62h] [rbp-9Eh]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  phkResult = 0;
  hMem = 0;
  cchName = 0;
  v0 = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\NetworkProvider\\GlobalMappings",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    while ( 1 )
    {
      cchName = 261;
      result = RegEnumKeyExW(hKey, v0, Name, &cchName, 0, 0, 0, 0);
      if ( result )
        break;
      if ( cchName && !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
      {
        if ( Name[1] || !(unsigned int)_o_iswalpha(Name[0]) )
        {
          v2 = 0;
        }
        else
        {
          v2 = 1;
          v7 = Name[0];
          v8 = 58;
        }
        if ( (unsigned int)ReadConnectionInfoFromRegistry(
                             phkResult,
                             (STRSAFE_LPCWSTR)((unsigned __int64)&v7 & -(__int64)(v2 != 0))) )
        {
          RegCloseKey(phkResult);
        }
        else
        {
          WsRestoreGlobalMapping(hMem);
          RegCloseKey(phkResult);
          LocalFree(hMem);
        }
      }
      ++v0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d904  mov     [rsp-8+arg_0], rbx
0x18000d909  mov     [rsp-8+arg_8], rdi
0x18000d90e  push    rbp
0x18000d90f  lea     rbp, [rsp-190h]
0x18000d917  sub     rsp, 290h
0x18000d91e  mov     rax, cs:__security_cookie
0x18000d925  xor     rax, rsp
0x18000d928  mov     [rbp+190h+var_10], rax
0x18000d92f  xor     edi, edi
0x18000d931  lea     rax, [rsp+290h+hKey]
0x18000d936  mov     r9d, 20019h; samDesired
0x18000d93c  mov     [rsp+290h+hKey], rdi
0x18000d941  xor     r8d, r8d; ulOptions
0x18000d944  mov     [rsp+290h+var_248], rdi
0x18000d949  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x18000d950  mov     [rsp+290h+hMem], rdi
0x18000d955  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d95c  mov     [rsp+290h+cchName], edi
0x18000d960  mov     ebx, edi
0x18000d962  mov     [rsp+290h+phkResult], rax; phkResult
0x18000d967  call    cs:__imp_RegOpenKeyExW
0x18000d96d  test    eax, eax
0x18000d96f  jnz     loc_18000DA65
0x18000d975  mov     rcx, [rsp+290h+hKey]; hKey
0x18000d97a  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000d97f  mov     [rsp+290h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18000d984  lea     r8, [rsp+290h+Name]; lpName
0x18000d989  mov     [rsp+290h+lpcchClass], rdi; lpcchClass
0x18000d98e  mov     edx, ebx; dwIndex
0x18000d990  mov     [rsp+290h+lpClass], rdi; lpClass
0x18000d995  mov     [rsp+290h+phkResult], rdi; lpReserved
0x18000d99a  mov     [rsp+290h+cchName], 105h
0x18000d9a2  call    cs:__imp_RegEnumKeyExW
0x18000d9a8  test    eax, eax
0x18000d9aa  jnz     loc_18000DA65
0x18000d9b0  cmp     [rsp+290h+cchName], 1
0x18000d9b5  jb      loc_18000DA5E
0x18000d9bb  mov     rcx, [rsp+290h+hKey]; hKey
0x18000d9c0  lea     rax, [rsp+290h+var_248]
0x18000d9c5  mov     r9d, 20019h; samDesired
0x18000d9cb  mov     [rsp+290h+phkResult], rax; phkResult
0x18000d9d0  xor     r8d, r8d; ulOptions
0x18000d9d3  lea     rdx, [rsp+290h+Name]; lpSubKey
0x18000d9d8  call    cs:__imp_RegOpenKeyExW
0x18000d9de  test    eax, eax
0x18000d9e0  jnz     short loc_18000DA5E
0x18000d9e2  cmp     [rsp+290h+var_21E], di
0x18000d9e7  jnz     short loc_18000DA0E
0x18000d9e9  movzx   ecx, [rsp+290h+Name]
0x18000d9ee  call    cs:__imp__o_iswalpha
0x18000d9f4  test    eax, eax
0x18000d9f6  jz      short loc_18000DA0E
0x18000d9f8  movzx   eax, [rsp+290h+Name]
0x18000d9fd  mov     cl, 1
0x18000d9ff  mov     [rsp+290h+var_230], ax
0x18000da04  mov     [rsp+290h+var_22E], 3Ah ; ':'
0x18000da0c  jmp     short loc_18000DA11
0x18000da0e  mov     cl, dil
0x18000da11  neg     cl
0x18000da13  lea     rax, [rsp+290h+var_230]
0x18000da18  mov     rcx, [rsp+290h+var_248]; hKey
0x18000da1d  lea     r8, [rsp+290h+hMem]
0x18000da22  sbb     rdx, rdx
0x18000da25  and     rdx, rax; pszSrc
0x18000da28  call    ReadConnectionInfoFromRegistry
0x18000da2d  test    eax, eax
0x18000da2f  jz      short loc_18000DA3E
0x18000da31  mov     rcx, [rsp+290h+var_248]; hKey
0x18000da36  call    cs:__imp_RegCloseKey
0x18000da3c  jmp     short loc_18000DA5E
0x18000da3e  mov     rcx, [rsp+290h+hMem]
0x18000da43  call    WsRestoreGlobalMapping
0x18000da48  mov     rcx, [rsp+290h+var_248]; hKey
0x18000da4d  call    cs:__imp_RegCloseKey
0x18000da53  mov     rcx, [rsp+290h+hMem]; hMem
0x18000da58  call    cs:__imp_LocalFree
0x18000da5e  inc     ebx
0x18000da60  jmp     loc_18000D975
0x18000da65  mov     rcx, [rbp+190h+var_10]
0x18000da6c  xor     rcx, rsp; StackCookie
0x18000da6f  call    __security_check_cookie
0x18000da74  lea     r11, [rsp+290h+var_s0]
0x18000da7c  mov     rbx, [r11+10h]
0x18000da80  mov     rdi, [r11+18h]
0x18000da84  mov     rsp, r11
0x18000da87  pop     rbp
0x18000da88  retn
```
