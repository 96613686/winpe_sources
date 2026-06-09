# SHGetViewStream

- ea: `0x1801e2048`
- end: `0x1801e22c2`
- name: `SHGetViewStream`
- size: `634`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, DWORD grfMode, PCWSTR pszValue)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801d2338`

## callees

- `0x1800688b0`
- `0x1800749f0`
- `0x18013f7d0`
- `0x1801e2048`
- `0x180210010`

## import_xrefs

- `SHCORE!SHGetValueW` at `0x1801e20c0`
- `SHCORE!SHGetValueW` at `0x1801e20c0`
- `SHELL32!__imp_OpenRegStream` at `0x1801e2275`
- `SHELL32!__imp_OpenRegStream` at `0x1801e2275`
- `SHELL32!__imp_ILGetSize` at `0x1801e213f`
- `SHELL32!__imp_ILGetSize` at `0x1801e213f`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x1801e218f`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x1801e218f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801e2252`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801e2252`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e2261`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e2281`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e2261`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e2281`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e2208`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e2208`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801e2220`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801e2220`

## pseudocode

```c
IStream *__fastcall SHGetViewStream(LPCITEMIDLIST pidl, DWORD grfMode, PCWSTR pszValue)
{
  IStream *v6; // rsi
  __int64 v7; // r12
  int v8; // edi
  HKEY v9; // rax
  HKEY v10; // rbx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v15; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[32]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[64]; // [rsp+A0h] [rbp-60h] BYREF

  cchValueName = 4;
  v6 = 0;
  if ( !dword_180293368
    && SHGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StreamMRU",
         L"MRU Size",
         0,
         &dword_180293368,
         &cchValueName) )
  {
    dword_180293368 = 200;
  }
  v15 = 0;
  if ( (int)IECreateInstance(&CLSID_MruLongList, &v15) >= 0 )
  {
    if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64, __int64, const WCHAR *, _QWORD))(*(_QWORD *)v15 + 24LL))(
           v15,
           (unsigned int)dword_180293368,
           3,
           -2147483647,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StreamMRU",
           0) >= 0 )
    {
      v7 = ILGetSize(pidl);
      v16 = 0;
      if ( (*(int (__fastcall **)(LPVOID, LPCITEMIDLIST, __int64, int *))(*(_QWORD *)v15 + 48LL))(v15, pidl, v7, &v16) >= 0 )
      {
        v8 = 1;
        goto LABEL_9;
      }
      v8 = 0;
      if ( (grfMode & 3) != 0 )
      {
LABEL_9:
        LODWORD(v9) = SHGetShellKeyEx((LPCWSTR)1);
        v10 = v9;
        if ( v9 )
        {
          v13 = 0;
          if ( (*(int (__fastcall **)(LPVOID, LPCITEMIDLIST, _QWORD, unsigned int *))(*(_QWORD *)v15 + 32LL))(
                 v15,
                 pidl,
                 (unsigned int)v7,
                 &v13) >= 0 )
          {
            phkResult = 0;
            StringCchPrintfW(SubKey, 0x20u, L"%d", v13);
            if ( !v8 && !RegOpenKeyExW(v10, SubKey, 0, 3u, &phkResult) )
            {
              do
                cchValueName = 64;
              while ( !RegEnumValueW(phkResult, 0, ValueName, &cchValueName, 0, 0, 0, 0)
                   && !RegDeleteValueW(phkResult, ValueName) );
              RegCloseKey(phkResult);
            }
            v6 = OpenRegStream(v10, SubKey, pszValue, grfMode);
          }
          RegCloseKey(v10);
        }
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return v6;
}

```

## disassembly

```asm
0x1801e2048  mov     [rsp-8+arg_18], rbx
0x1801e204d  push    rbp
0x1801e204e  push    rsi
0x1801e204f  push    rdi
0x1801e2050  push    r12
0x1801e2052  push    r13
0x1801e2054  push    r14
0x1801e2056  push    r15
0x1801e2058  lea     rbp, [rsp-30h]
0x1801e205d  sub     rsp, 130h
0x1801e2064  mov     rax, cs:__security_cookie
0x1801e206b  xor     rax, rsp
0x1801e206e  mov     [rbp+60h+var_40], rax
0x1801e2072  xor     ebx, ebx
0x1801e2074  mov     [rsp+160h+cchValueName], 4
0x1801e207c  cmp     cs:dword_180293368, ebx
0x1801e2082  mov     r13, r8
0x1801e2085  mov     r14d, edx
0x1801e2088  mov     r15, rcx
0x1801e208b  mov     esi, ebx
0x1801e208d  mov     r12, 0FFFFFFFF80000001h
0x1801e2094  jnz     short loc_1801E20D4
0x1801e2096  lea     rax, [rsp+160h+cchValueName]
0x1801e209b  xor     r9d, r9d; pdwType
0x1801e209e  mov     [rsp+160h+pcbData], rax; pcbData
0x1801e20a3  lea     r8, aMruSize; "MRU Size"
0x1801e20aa  lea     rax, dword_180293368
0x1801e20b1  mov     rcx, r12; hkey
0x1801e20b4  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e20bb  mov     [rsp+160h+pvData], rax; pvData
0x1801e20c0  call    cs:__imp_SHGetValueW
0x1801e20c6  test    eax, eax
0x1801e20c8  jz      short loc_1801E20D4
0x1801e20ca  mov     cs:dword_180293368, 0C8h
0x1801e20d4  lea     rax, [rsp+160h+var_110]
0x1801e20d9  mov     [rsp+160h+var_110], rbx
0x1801e20de  mov     edi, 3
0x1801e20e3  mov     [rsp+160h+pvData], rax; LPVOID *
0x1801e20e8  mov     r8d, edi
0x1801e20eb  lea     r9, _GUID_d2c22919_91f5_4284_8807_58a2d64e561c
0x1801e20f2  lea     rcx, CLSID_MruLongList; rclsid
0x1801e20f9  call    IECreateInstance
0x1801e20fe  test    eax, eax
0x1801e2100  js      loc_1801E2298
0x1801e2106  mov     rcx, [rsp+160h+var_110]
0x1801e210b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e2112  mov     [rsp+160h+pcbData], rbx
0x1801e2117  mov     r9, r12
0x1801e211a  mov     [rsp+160h+pvData], rdx
0x1801e211f  mov     r8d, edi
0x1801e2122  mov     edx, cs:dword_180293368
0x1801e2128  mov     rax, [rcx]
0x1801e212b  mov     rax, [rax+18h]
0x1801e212f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2134  test    eax, eax
0x1801e2136  js      loc_1801E2287
0x1801e213c  mov     rcx, r15; pidl
0x1801e213f  call    cs:__imp_ILGetSize
0x1801e2145  mov     rcx, [rsp+160h+var_110]
0x1801e214a  lea     r9, [rsp+160h+var_108]
0x1801e214f  mov     r12d, eax
0x1801e2152  mov     [rsp+160h+var_108], ebx
0x1801e2156  mov     r8d, r12d
0x1801e2159  mov     rdx, [rcx]
0x1801e215c  mov     rax, [rdx+30h]
0x1801e2160  mov     rdx, r15
0x1801e2163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2168  lea     ecx, [rdi-2]; pszPath
0x1801e216b  test    eax, eax
0x1801e216d  js      short loc_1801E2173
0x1801e216f  mov     edi, ecx
0x1801e2171  jmp     short loc_1801E217F
0x1801e2173  mov     edi, ebx
0x1801e2175  test    r14b, 3
0x1801e2179  jz      loc_1801E2287
0x1801e217f  mov     r9d, 20019h
0x1801e2185  lea     rdx, aStreams; "Streams"
0x1801e218c  mov     r8d, ecx
0x1801e218f  call    cs:__imp_SHGetShellKeyEx
0x1801e2195  mov     rbx, rax
0x1801e2198  test    rax, rax
0x1801e219b  jz      loc_1801E2287
0x1801e21a1  mov     rcx, [rsp+160h+var_110]
0x1801e21a6  lea     r9, [rsp+160h+var_11C]
0x1801e21ab  mov     [rsp+160h+var_11C], esi
0x1801e21af  mov     rdx, r15
0x1801e21b2  mov     r8, [rcx]
0x1801e21b5  mov     rax, [r8+20h]
0x1801e21b9  mov     r8d, r12d
0x1801e21bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e21c1  xor     r15d, r15d
0x1801e21c4  test    eax, eax
0x1801e21c6  js      loc_1801E227E
0x1801e21cc  mov     r9d, [rsp+160h+var_11C]
0x1801e21d1  lea     r8, aD; "%d"
0x1801e21d8  lea     edx, [r15+20h]; unsigned __int64
0x1801e21dc  mov     [rsp+160h+phkResult], r15
0x1801e21e1  lea     rcx, [rsp+160h+SubKey]; unsigned __int16 *
0x1801e21e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801e21eb  test    edi, edi
0x1801e21ed  jnz     short loc_1801E2267
0x1801e21ef  lea     rax, [rsp+160h+phkResult]
0x1801e21f4  xor     r8d, r8d; ulOptions
0x1801e21f7  lea     r9d, [r15+3]; samDesired
0x1801e21fb  mov     [rsp+160h+pvData], rax; phkResult
0x1801e2200  lea     rdx, [rsp+160h+SubKey]; lpSubKey
0x1801e2205  mov     rcx, rbx; hKey
0x1801e2208  call    cs:__imp_RegOpenKeyExW
0x1801e220e  test    eax, eax
0x1801e2210  jnz     short loc_1801E2267
0x1801e2212  lea     edi, [rax+40h]
0x1801e2215  jmp     short loc_1801E222A
0x1801e2217  mov     rcx, [rsp+160h+phkResult]; hKey
0x1801e221c  lea     rdx, [rbp+60h+ValueName]; lpValueName
0x1801e2220  call    cs:__imp_RegDeleteValueW
0x1801e2226  test    eax, eax
0x1801e2228  jnz     short loc_1801E225C
0x1801e222a  mov     rcx, [rsp+160h+phkResult]; hKey
0x1801e222f  lea     r9, [rsp+160h+cchValueName]; lpcchValueName
0x1801e2234  mov     [rsp+160h+lpcbData], r15; lpcbData
0x1801e2239  lea     r8, [rbp+60h+ValueName]; lpValueName
0x1801e223d  mov     [rsp+160h+lpData], r15; lpData
0x1801e2242  xor     edx, edx; dwIndex
0x1801e2244  mov     [rsp+160h+pcbData], r15; lpType
0x1801e2249  mov     [rsp+160h+pvData], r15; lpReserved
0x1801e224e  mov     [rsp+160h+cchValueName], edi
0x1801e2252  call    cs:__imp_RegEnumValueW
0x1801e2258  test    eax, eax
0x1801e225a  jz      short loc_1801E2217
0x1801e225c  mov     rcx, [rsp+160h+phkResult]; hKey
0x1801e2261  call    cs:__imp_RegCloseKey
0x1801e2267  mov     r9d, r14d; grfMode
0x1801e226a  lea     rdx, [rsp+160h+SubKey]; pszSubkey
0x1801e226f  mov     r8, r13; pszValue
0x1801e2272  mov     rcx, rbx; hkey
0x1801e2275  call    cs:__imp_OpenRegStream
0x1801e227b  mov     rsi, rax
0x1801e227e  mov     rcx, rbx; hKey
0x1801e2281  call    cs:__imp_RegCloseKey
0x1801e2287  mov     rcx, [rsp+160h+var_110]
0x1801e228c  mov     rdx, [rcx]
0x1801e228f  mov     rax, [rdx+10h]
0x1801e2293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2298  mov     rax, rsi
0x1801e229b  mov     rcx, [rbp+60h+var_40]
0x1801e229f  xor     rcx, rsp; StackCookie
0x1801e22a2  call    __security_check_cookie
0x1801e22a7  mov     rbx, [rsp+160h+arg_18]
0x1801e22af  add     rsp, 130h
0x1801e22b6  pop     r15
0x1801e22b8  pop     r14
0x1801e22ba  pop     r13
0x1801e22bc  pop     r12
0x1801e22be  pop     rdi
0x1801e22bf  pop     rsi
0x1801e22c0  pop     rbp
0x1801e22c1  retn
```
