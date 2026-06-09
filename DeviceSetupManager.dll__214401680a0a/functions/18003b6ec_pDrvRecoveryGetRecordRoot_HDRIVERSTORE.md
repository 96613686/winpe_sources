# pDrvRecoveryGetRecordRoot(HDRIVERSTORE__ *)

- ea: `0x18003b6ec`
- end: `0x18003b85f`
- name: `?pDrvRecoveryGetRecordRoot@@YAPEAUHKEY__@@PEAUHDRIVERSTORE__@@@Z`
- size: `371`
- prototype: `HKEY __fastcall(struct HDRIVERSTORE__ *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003a9ac`
- `0x18003abbc`
- `0x18003b868`
- `0x18003b988`

## callees

- `0x18001af70`
- `0x18001b9dc`
- `0x18003b6ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b834`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b769`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b7cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b7cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b812`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b82c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b82c`
- `drvstore!DriverStoreGetParameter` at `0x18003b75f`
- `drvstore!DriverStoreGetParameter` at `0x18003b75f`

## string_xrefs

- `0x18003b792`: `\Registry\Machine\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY __fastcall pDrvRecoveryGetRecordRoot(struct HDRIVERSTORE__ *a1)
{
  DWORD LastError; // eax
  LSTATUS v2; // ebx
  int v4; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v5; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v7; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[18]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[246]; // [rsp+94h] [rbp-6Ch] BYREF

  v4 = 0;
  v5 = 0;
  hKey = 0;
  v7 = 0;
  if ( !(unsigned int)DriverStoreGetParameter(a1, DEVPKEY_DriverStore_SystemRegHiveKeyPath, &v4, String1, 520, &v5, 0) )
  {
    LastError = GetLastError();
LABEL_3:
    v2 = LastError;
    goto LABEL_11;
  }
  if ( v4 == 18 && v5 >= 2 )
  {
    if ( wcsnicmp(String1, L"\\Registry\\Machine\\", 0x12u) )
    {
      v2 = 50;
    }
    else
    {
      v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 4u, &hKey);
      if ( !v2 )
      {
        LastError = RegCreateKeyExW(hKey, L"DriverRecovery", 0, 0, 0, 0x2001Fu, 0, &v7, 0);
        goto LABEL_3;
      }
    }
  }
  else
  {
    v2 = 13;
  }
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(v2);
  return v7;
}

```

## disassembly

```asm
0x18003b6ec  mov     [rsp-8+arg_8], rbx
0x18003b6f1  push    rbp
0x18003b6f2  lea     rbp, [rsp-190h]
0x18003b6fa  sub     rsp, 290h
0x18003b701  mov     rax, cs:__security_cookie
0x18003b708  xor     rax, rsp
0x18003b70b  mov     [rbp+190h+var_10], rax
0x18003b712  lea     rax, [rsp+290h+var_23C]
0x18003b717  mov     dword ptr [rsp+290h+lpSecurityAttributes], 0
0x18003b71f  mov     qword ptr [rsp+290h+samDesired], rax
0x18003b724  lea     r9, [rsp+290h+String1]
0x18003b729  lea     r8, [rsp+290h+var_240]
0x18003b72e  mov     dword ptr [rsp+290h+phkResult], 208h
0x18003b736  lea     rdx, DEVPKEY_DriverStore_SystemRegHiveKeyPath
0x18003b73d  mov     [rsp+290h+var_240], 0
0x18003b745  mov     [rsp+290h+var_23C], 0
0x18003b74d  mov     [rsp+290h+hKey], 0
0x18003b756  mov     [rsp+290h+var_230], 0
0x18003b75f  call    cs:__imp_DriverStoreGetParameter
0x18003b765  test    eax, eax
0x18003b767  jnz     short loc_18003B776
0x18003b769  call    cs:__imp_GetLastError
0x18003b76f  mov     ebx, eax
0x18003b771  jmp     loc_18003B822
0x18003b776  mov     r8d, 12h; MaxCount
0x18003b77c  cmp     [rsp+290h+var_240], r8d
0x18003b781  jnz     loc_18003B81D
0x18003b787  cmp     [rsp+290h+var_23C], 2
0x18003b78c  jb      loc_18003B81D
0x18003b792  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\"
0x18003b799  lea     rcx, [rsp+290h+String1]; String1
0x18003b79e  call    _wcsnicmp
0x18003b7a3  test    eax, eax
0x18003b7a5  jz      short loc_18003B7AE
0x18003b7a7  mov     ebx, 32h ; '2'
0x18003b7ac  jmp     short loc_18003B822
0x18003b7ae  lea     rax, [rsp+290h+hKey]
0x18003b7b3  mov     r9d, 4; samDesired
0x18003b7b9  xor     r8d, r8d; ulOptions
0x18003b7bc  mov     [rsp+290h+phkResult], rax; phkResult
0x18003b7c1  lea     rdx, [rbp+190h+SubKey]; lpSubKey
0x18003b7c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b7cc  call    cs:__imp_RegOpenKeyExW
0x18003b7d2  mov     ebx, eax
0x18003b7d4  test    eax, eax
0x18003b7d6  jnz     short loc_18003B822
0x18003b7d8  mov     rcx, [rsp+290h+hKey]; hKey
0x18003b7dd  lea     rax, [rsp+290h+var_230]
0x18003b7e2  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x18003b7eb  lea     rdx, aDriverrecovery; "DriverRecovery"
0x18003b7f2  mov     [rsp+290h+var_258], rax; phkResult
0x18003b7f7  xor     r9d, r9d; lpClass
0x18003b7fa  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003b803  xor     r8d, r8d; Reserved
0x18003b806  mov     [rsp+290h+samDesired], 2001Fh; samDesired
0x18003b80e  mov     dword ptr [rsp+290h+phkResult], ebx; dwOptions
0x18003b812  call    cs:__imp_RegCreateKeyExW
0x18003b818  jmp     loc_18003B76F
0x18003b81d  mov     ebx, 0Dh
0x18003b822  mov     rcx, [rsp+290h+hKey]; hKey
0x18003b827  test    rcx, rcx
0x18003b82a  jz      short loc_18003B832
0x18003b82c  call    cs:__imp_RegCloseKey
0x18003b832  mov     ecx, ebx; dwErrCode
0x18003b834  call    cs:__imp_SetLastError
0x18003b83a  mov     rax, [rsp+290h+var_230]
0x18003b83f  mov     rcx, [rbp+190h+var_10]
0x18003b846  xor     rcx, rsp; StackCookie
0x18003b849  call    __security_check_cookie
0x18003b84e  mov     rbx, [rsp+290h+arg_8]
0x18003b856  add     rsp, 290h
0x18003b85d  pop     rbp
0x18003b85e  retn
```
