# CheckKey

- ea: `0x180075d9c`
- end: `0x180075f89`
- name: `CheckKey`
- size: `493`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180076820`

## callees

- `0x18007593c`
- `0x180075d9c`
- `0x180076028`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180075eda`
- `KERNEL32!GetLastError` at `0x180075eda`
- `ADVAPI32!RegOpenKeyExW` at `0x180075dfc`
- `ADVAPI32!RegOpenKeyExW` at `0x180075dfc`
- `ADVAPI32!RegCloseKey` at `0x180075e3d`
- `ADVAPI32!RegCloseKey` at `0x180075e3d`
- `ADVAPI32!RegEnumKeyExW` at `0x180075f2f`
- `ADVAPI32!RegEnumKeyExW` at `0x180075f2f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180075e93`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180075e93`

## string_xrefs

- `0x180075e11`: `Error %d opening [%s]\n`

## pseudocode

```c
__int64 __fastcall CheckKey(WCHAR *Src, int a2)
{
  REGSAM v3; // r9d
  const wchar_t *v4; // r9
  int v5; // r8d
  __int64 KeyInfo; // rax
  __int64 v8; // rbx
  DWORD cSubKeys; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+98h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( a2 == 13 )
  {
    v3 = 983359;
  }
  else
  {
    v3 = 983103;
    if ( a2 == 12 )
      v3 = 983615;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, Src + 8, 0, v3, &hKey) )
  {
    v4 = L"Error %d opening [%s]\n";
    v5 = 953;
LABEL_7:
    dprintf(5, (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c", v5, (_DWORD)v4);
    goto LABEL_8;
  }
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    v4 = L"Error %d querying key [%s]\n";
    v5 = 971;
    goto LABEL_7;
  }
  if ( !cSubKeys )
    goto LABEL_8;
  KeyInfo = AllocateKeyInfo(Src);
  v8 = KeyInfo;
  if ( !KeyInfo )
  {
    GetLastError();
    v4 = L"Error [%d] not enough memory [%s]\n";
    v5 = 984;
    goto LABEL_7;
  }
  cbMaxSubKeyLen = *(_DWORD *)(KeyInfo + 40) - *(_DWORD *)(KeyInfo + 32);
  if ( !RegEnumKeyExW(
          hKey,
          0,
          (LPWSTR)(*(_QWORD *)(KeyInfo + 24) + 2LL * *(unsigned int *)(KeyInfo + 32)),
          &cbMaxSubKeyLen,
          0,
          0,
          0,
          0) )
  {
    *(_DWORD *)(v8 + 36) = cbMaxSubKeyLen;
    *(_QWORD *)(v8 + 16) = hKey;
    return v8;
  }
  dprintf(
    5,
    (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
    1001,
    (unsigned int)L"Error %d enumerating [%s]\n");
  FreeKeyInfo((HLOCAL)v8);
LABEL_8:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180075d9c  push    rbp
0x180075d9e  push    rbx
0x180075d9f  push    rsi
0x180075da0  push    rdi
0x180075da1  push    r14
0x180075da3  mov     rbp, rsp
0x180075da6  sub     rsp, 60h
0x180075daa  xor     r14d, r14d
0x180075dad  mov     [rbp+hKey], 0FFFFFFFFFFFFFFFFh
0x180075db5  mov     [rbp+cSubKeys], r14d
0x180075db9  mov     rsi, r8
0x180075dbc  mov     [rbp+cbMaxSubKeyLen], r14d
0x180075dc0  mov     rdi, rcx
0x180075dc3  cmp     edx, 0Dh
0x180075dc6  jnz     short loc_180075DD0
0x180075dc8  mov     r9d, 0F013Fh
0x180075dce  jmp     short loc_180075DE2
0x180075dd0  cmp     edx, 0Ch
0x180075dd3  mov     eax, 0F023Fh
0x180075dd8  mov     r9d, 0F003Fh
0x180075dde  cmovz   r9d, eax; samDesired
0x180075de2  lea     rbx, [rcx+10h]
0x180075de6  xor     r8d, r8d; ulOptions
0x180075de9  lea     rax, [rbp+hKey]
0x180075ded  mov     rdx, rbx; lpSubKey
0x180075df0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075df7  mov     [rsp+60h+phkResult], rax; phkResult
0x180075dfc  call    cs:__imp_RegOpenKeyExW
0x180075e03  nop     dword ptr [rax+rax+00h]
0x180075e08  test    eax, eax
0x180075e0a  jz      short loc_180075E57
0x180075e0c  mov     [rsp+60h+lpcbMaxSubKeyLen], rbx
0x180075e11  lea     r9, aErrorDOpeningS; "Error %d opening [%s]\n"
0x180075e18  mov     r8d, 3B9h
0x180075e1e  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075e25  mov     dword ptr [rsp+60h+phkResult], eax
0x180075e29  mov     ecx, 5
0x180075e2e  call    dprintf
0x180075e33  mov     rcx, [rbp+hKey]; hKey
0x180075e37  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180075e3b  jz      short loc_180075E49
0x180075e3d  call    cs:__imp_RegCloseKey
0x180075e44  nop     dword ptr [rax+rax+00h]
0x180075e49  xor     eax, eax
0x180075e4b  add     rsp, 60h
0x180075e4f  pop     r14
0x180075e51  pop     rdi
0x180075e52  pop     rsi
0x180075e53  pop     rbx
0x180075e54  pop     rbp
0x180075e55  retn
0x180075e57  mov     rcx, [rbp+hKey]; hKey
0x180075e5b  lea     rax, [rbp+cbMaxSubKeyLen]
0x180075e5f  mov     [rsp+60h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180075e64  xor     r9d, r9d; lpReserved
0x180075e67  mov     [rsp+60h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180075e6c  xor     r8d, r8d; lpcchClass
0x180075e6f  mov     [rsp+60h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180075e74  xor     edx, edx; lpClass
0x180075e76  mov     [rsp+60h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180075e7b  mov     [rsp+60h+lpcValues], r14; lpcValues
0x180075e80  mov     [rsp+60h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180075e85  mov     [rsp+60h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180075e8a  lea     rax, [rbp+cSubKeys]
0x180075e8e  mov     [rsp+60h+phkResult], rax; lpcSubKeys
0x180075e93  call    cs:__imp_RegQueryInfoKeyW
0x180075e9a  nop     dword ptr [rax+rax+00h]
0x180075e9f  test    eax, eax
0x180075ea1  jz      short loc_180075EBA
0x180075ea3  mov     [rsp+60h+lpcbMaxSubKeyLen], rdi
0x180075ea8  lea     r9, aErrorDQuerying; "Error %d querying key [%s]\n"
0x180075eaf  mov     r8d, 3CBh
0x180075eb5  jmp     loc_180075E1E
0x180075eba  cmp     [rbp+cSubKeys], r14d
0x180075ebe  jz      loc_180075E33
0x180075ec4  mov     edx, [rbp+cbMaxSubKeyLen]
0x180075ec7  mov     r8, rsi
0x180075eca  mov     rcx, rdi; Src
0x180075ecd  call    AllocateKeyInfo
0x180075ed2  mov     rbx, rax
0x180075ed5  test    rax, rax
0x180075ed8  jnz     short loc_180075EFD
0x180075eda  call    cs:__imp_GetLastError
0x180075ee1  nop     dword ptr [rax+rax+00h]
0x180075ee6  lea     r9, aErrorDNotEnoug; "Error [%d] not enough memory [%s]\n"
0x180075eed  mov     [rsp+60h+lpcbMaxSubKeyLen], rdi
0x180075ef2  mov     r8d, 3D8h
0x180075ef8  jmp     loc_180075E1E
0x180075efd  mov     eax, [rax+28h]
0x180075f00  lea     r9, [rbp+cbMaxSubKeyLen]; lpcchName
0x180075f04  sub     eax, [rbx+20h]
0x180075f07  xor     edx, edx; dwIndex
0x180075f09  mov     [rbp+cbMaxSubKeyLen], eax
0x180075f0c  mov     ecx, [rbx+20h]
0x180075f0f  mov     rax, [rbx+18h]
0x180075f13  mov     [rsp+60h+lpcValues], r14; lpftLastWriteTime
0x180075f18  mov     [rsp+60h+lpcbMaxClassLen], r14; lpcchClass
0x180075f1d  mov     [rsp+60h+lpcbMaxSubKeyLen], r14; lpClass
0x180075f22  lea     r8, [rax+rcx*2]; lpName
0x180075f26  mov     [rsp+60h+phkResult], r14; lpReserved
0x180075f2b  mov     rcx, [rbp+hKey]; hKey
0x180075f2f  call    cs:__imp_RegEnumKeyExW
0x180075f36  nop     dword ptr [rax+rax+00h]
0x180075f3b  test    eax, eax
0x180075f3d  jz      short loc_180075F73
0x180075f3f  mov     [rsp+60h+lpcbMaxSubKeyLen], rdi
0x180075f44  lea     r9, aErrorDEnumerat_0; "Error %d enumerating [%s]\n"
0x180075f4b  mov     r8d, 3E9h
0x180075f51  mov     dword ptr [rsp+60h+phkResult], eax
0x180075f55  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075f5c  mov     ecx, 5
0x180075f61  call    dprintf
0x180075f66  mov     rcx, rbx; hMem
0x180075f69  call    FreeKeyInfo
0x180075f6e  jmp     loc_180075E33
0x180075f73  mov     eax, [rbp+cbMaxSubKeyLen]
0x180075f76  mov     [rbx+24h], eax
0x180075f79  mov     rax, [rbp+hKey]
0x180075f7d  mov     [rbx+10h], rax
0x180075f81  mov     rax, rbx
0x180075f84  jmp     loc_180075E4B
```
