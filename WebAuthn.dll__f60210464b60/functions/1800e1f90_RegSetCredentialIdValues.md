# RegSetCredentialIdValues

- ea: `0x1800e1f90`
- end: `0x1800e2269`
- name: `RegSetCredentialIdValues`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e0f3c`

## callees

- `0x1800537a4`
- `0x1800dec74`
- `0x1800e1f90`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e2133`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e2133`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2043`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2088`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2043`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2088`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e20d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e2119`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e215e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e21a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e21e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e221f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e20d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e2119`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e215e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e21a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e21e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e221f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e2231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e2241`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e2231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e2241`

## string_xrefs

- `0x1800e2157`: `createTime`

## pseudocode

```c
__int64 __fastcall RegSetCredentialIdValues(
        __int64 a1,
        const BYTE *a2,
        const BYTE *a3,
        const BYTE *a4,
        BYTE *lpData,
        BYTE *a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[72]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  memset_0(SubKey, 0, 0x82u);
  v10 = ConvertCredentialIdToString(a1, SubKey);
  if ( !v10 )
  {
    v10 = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\CtapTest\\Credentials",
            0,
            0,
            0,
            0x2011Fu,
            0,
            &hKey,
            &dwDisposition);
    if ( !v10 )
    {
      v10 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2011Fu, 0, &phkResult, &dwDisposition);
      if ( !v10 )
      {
        v11 = -1;
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)&a2[2 * v12] );
        v10 = RegSetValueExW(phkResult, L"containerName", 0, 1u, a2, 2 * v12 + 2);
        if ( !v10 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&a3[2 * v13] );
          v10 = RegSetValueExW(phkResult, L"id", 0, 1u, a3, 2 * v13 + 2);
          if ( !v10 )
          {
            SystemTimeAsFileTime = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v10 = RegSetValueExW(phkResult, L"createTime", 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
            if ( !v10 )
            {
              if ( !a4 )
                goto LABEL_15;
              v14 = -1;
              do
                ++v14;
              while ( *(_WORD *)&a4[2 * v14] );
              v10 = RegSetValueExW(phkResult, L"name", 0, 1u, a4, 2 * v14 + 2);
              if ( !v10 )
              {
LABEL_15:
                if ( !lpData )
                  goto LABEL_19;
                v15 = -1;
                do
                  ++v15;
                while ( *(_WORD *)&lpData[2 * v15] );
                v10 = RegSetValueExW(phkResult, L"icon", 0, 1u, lpData, 2 * v15 + 2);
                if ( !v10 )
                {
LABEL_19:
                  if ( a6 )
                  {
                    do
                      ++v11;
                    while ( *(_WORD *)&a6[2 * v11] );
                    v10 = RegSetValueExW(phkResult, L"displayName", 0, 1u, a6, 2 * v11 + 2);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v10;
}

```

## disassembly

```asm
0x1800e1f90  push    rbp
0x1800e1f92  push    rbx
0x1800e1f93  push    rsi
0x1800e1f94  push    rdi
0x1800e1f95  push    r12
0x1800e1f97  push    r13
0x1800e1f99  push    r14
0x1800e1f9b  push    r15
0x1800e1f9d  lea     rbp, [rsp-18h]
0x1800e1fa2  sub     rsp, 118h
0x1800e1fa9  mov     rax, cs:__security_cookie
0x1800e1fb0  xor     rax, rsp
0x1800e1fb3  mov     [rbp+50h+var_50], rax
0x1800e1fb7  mov     r14, [rbp+50h+lpData]
0x1800e1fbe  xor     edi, edi
0x1800e1fc0  mov     r15, [rbp+50h+arg_28]
0x1800e1fc7  mov     r13, r8
0x1800e1fca  mov     r12, rdx
0x1800e1fcd  mov     [rsp+150h+hKey], rdi
0x1800e1fd2  mov     rbx, rcx
0x1800e1fd5  mov     [rsp+150h+var_100], rdi
0x1800e1fda  xor     edx, edx; Val
0x1800e1fdc  mov     [rsp+150h+dwDisposition], edi
0x1800e1fe0  mov     r8d, 82h; Size
0x1800e1fe6  lea     rcx, [rsp+150h+SubKey]; void *
0x1800e1feb  mov     rsi, r9
0x1800e1fee  call    memset_0
0x1800e1ff3  lea     rdx, [rsp+150h+SubKey]
0x1800e1ff8  mov     rcx, rbx
0x1800e1ffb  call    ConvertCredentialIdToString
0x1800e2000  mov     ebx, eax
0x1800e2002  test    eax, eax
0x1800e2004  jnz     loc_1800E2227
0x1800e200a  lea     rax, [rsp+150h+dwDisposition]
0x1800e200f  xor     r9d, r9d; lpClass
0x1800e2012  mov     [rsp+150h+lpdwDisposition], rax; lpdwDisposition
0x1800e2017  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\CtapTest\\Credenti"...
0x1800e201e  lea     rax, [rsp+150h+hKey]
0x1800e2023  xor     r8d, r8d; Reserved
0x1800e2026  mov     [rsp+150h+phkResult], rax; phkResult
0x1800e202b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800e2032  mov     [rsp+150h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800e2037  mov     [rsp+150h+samDesired], 2011Fh; samDesired
0x1800e203f  mov     [rsp+150h+dwOptions], edi; dwOptions
0x1800e2043  call    cs:__imp_RegCreateKeyExW
0x1800e2049  mov     ebx, eax
0x1800e204b  test    eax, eax
0x1800e204d  jnz     loc_1800E2227
0x1800e2053  mov     rcx, [rsp+150h+hKey]; hKey
0x1800e2058  lea     rax, [rsp+150h+dwDisposition]
0x1800e205d  mov     [rsp+150h+lpdwDisposition], rax; lpdwDisposition
0x1800e2062  lea     rdx, [rsp+150h+SubKey]; lpSubKey
0x1800e2067  lea     rax, [rsp+150h+var_100]
0x1800e206c  xor     r9d, r9d; lpClass
0x1800e206f  mov     [rsp+150h+phkResult], rax; phkResult
0x1800e2074  xor     r8d, r8d; Reserved
0x1800e2077  mov     [rsp+150h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800e207c  mov     [rsp+150h+samDesired], 2011Fh; samDesired
0x1800e2084  mov     [rsp+150h+dwOptions], edi; dwOptions
0x1800e2088  call    cs:__imp_RegCreateKeyExW
0x1800e208e  mov     ebx, eax
0x1800e2090  test    eax, eax
0x1800e2092  jnz     loc_1800E2227
0x1800e2098  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800e209c  mov     rax, rdi
0x1800e209f  xor     ecx, ecx
0x1800e20a1  inc     rax
0x1800e20a4  cmp     [r12+rax*2], cx
0x1800e20a9  jnz     short loc_1800E20A1
0x1800e20ab  mov     rcx, [rsp+150h+var_100]; hKey
0x1800e20b0  lea     eax, ds:2[rax*2]
0x1800e20b7  mov     [rsp+150h+samDesired], eax; cbData
0x1800e20bb  lea     rdx, aContainername; "containerName"
0x1800e20c2  mov     r9d, 1; dwType
0x1800e20c8  mov     qword ptr [rsp+150h+dwOptions], r12; lpData
0x1800e20cd  xor     r8d, r8d; Reserved
0x1800e20d0  call    cs:__imp_RegSetValueExW
0x1800e20d6  xor     r12d, r12d
0x1800e20d9  mov     ebx, eax
0x1800e20db  test    eax, eax
0x1800e20dd  jnz     loc_1800E2227
0x1800e20e3  mov     rax, rdi
0x1800e20e6  inc     rax
0x1800e20e9  cmp     [r13+rax*2+0], r12w
0x1800e20ef  jnz     short loc_1800E20E6
0x1800e20f1  mov     rcx, [rsp+150h+var_100]; hKey
0x1800e20f6  lea     eax, ds:2[rax*2]
0x1800e20fd  mov     [rsp+150h+samDesired], eax; cbData
0x1800e2101  lea     rdx, aId_0; "id"
0x1800e2108  mov     qword ptr [rsp+150h+dwOptions], r13; lpData
0x1800e210d  xor     r8d, r8d; Reserved
0x1800e2110  mov     r13d, 1
0x1800e2116  mov     r9d, r13d; dwType
0x1800e2119  call    cs:__imp_RegSetValueExW
0x1800e211f  mov     ebx, eax
0x1800e2121  test    eax, eax
0x1800e2123  jnz     loc_1800E2227
0x1800e2129  lea     rcx, [rsp+150h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800e212e  mov     qword ptr [rsp+150h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800e2133  call    cs:__imp_GetSystemTimeAsFileTime
0x1800e2139  mov     rcx, [rsp+150h+var_100]; hKey
0x1800e213e  lea     rax, [rsp+150h+SystemTimeAsFileTime]
0x1800e2143  mov     [rsp+150h+samDesired], 8; cbData
0x1800e214b  lea     r9d, [r13+2]; dwType
0x1800e214f  xor     r8d, r8d; Reserved
0x1800e2152  mov     qword ptr [rsp+150h+dwOptions], rax; lpData
0x1800e2157  lea     rdx, aCreatetime; "createTime"
0x1800e215e  call    cs:__imp_RegSetValueExW
0x1800e2164  mov     ebx, eax
0x1800e2166  test    eax, eax
0x1800e2168  jnz     loc_1800E2227
0x1800e216e  test    rsi, rsi
0x1800e2171  jz      short loc_1800E21AE
0x1800e2173  mov     rax, rdi
0x1800e2176  inc     rax
0x1800e2179  cmp     [rsi+rax*2], r12w
0x1800e217e  jnz     short loc_1800E2176
0x1800e2180  mov     rcx, [rsp+150h+var_100]; hKey
0x1800e2185  lea     eax, ds:2[rax*2]
0x1800e218c  mov     [rsp+150h+samDesired], eax; cbData
0x1800e2190  lea     rdx, aName_1; "name"
0x1800e2197  mov     r9d, r13d; dwType
0x1800e219a  mov     qword ptr [rsp+150h+dwOptions], rsi; lpData
0x1800e219f  xor     r8d, r8d; Reserved
0x1800e21a2  call    cs:__imp_RegSetValueExW
0x1800e21a8  mov     ebx, eax
0x1800e21aa  test    eax, eax
0x1800e21ac  jnz     short loc_1800E2227
0x1800e21ae  test    r14, r14
0x1800e21b1  jz      short loc_1800E21EE
0x1800e21b3  mov     rax, rdi
0x1800e21b6  inc     rax
0x1800e21b9  cmp     [r14+rax*2], r12w
0x1800e21be  jnz     short loc_1800E21B6
0x1800e21c0  mov     rcx, [rsp+150h+var_100]; hKey
0x1800e21c5  lea     eax, ds:2[rax*2]
0x1800e21cc  mov     [rsp+150h+samDesired], eax; cbData
0x1800e21d0  lea     rdx, aIcon_0; "icon"
0x1800e21d7  mov     r9d, r13d; dwType
0x1800e21da  mov     qword ptr [rsp+150h+dwOptions], r14; lpData
0x1800e21df  xor     r8d, r8d; Reserved
0x1800e21e2  call    cs:__imp_RegSetValueExW
0x1800e21e8  mov     ebx, eax
0x1800e21ea  test    eax, eax
0x1800e21ec  jnz     short loc_1800E2227
0x1800e21ee  test    r15, r15
0x1800e21f1  jz      short loc_1800E2227
0x1800e21f3  inc     rdi
0x1800e21f6  cmp     [r15+rdi*2], r12w
0x1800e21fb  jnz     short loc_1800E21F3
0x1800e21fd  mov     rcx, [rsp+150h+var_100]; hKey
0x1800e2202  lea     eax, ds:2[rdi*2]
0x1800e2209  mov     [rsp+150h+samDesired], eax; cbData
0x1800e220d  lea     rdx, aDisplayname_0; "displayName"
0x1800e2214  mov     r9d, r13d; dwType
0x1800e2217  mov     qword ptr [rsp+150h+dwOptions], r15; lpData
0x1800e221c  xor     r8d, r8d; Reserved
0x1800e221f  call    cs:__imp_RegSetValueExW
0x1800e2225  mov     ebx, eax
0x1800e2227  mov     rcx, [rsp+150h+hKey]; hKey
0x1800e222c  test    rcx, rcx
0x1800e222f  jz      short loc_1800E2237
0x1800e2231  call    cs:__imp_RegCloseKey
0x1800e2237  mov     rcx, [rsp+150h+var_100]; hKey
0x1800e223c  test    rcx, rcx
0x1800e223f  jz      short loc_1800E2247
0x1800e2241  call    cs:__imp_RegCloseKey
0x1800e2247  mov     eax, ebx
0x1800e2249  mov     rcx, [rbp+50h+var_50]
0x1800e224d  xor     rcx, rsp; StackCookie
0x1800e2250  call    __security_check_cookie
0x1800e2255  add     rsp, 118h
0x1800e225c  pop     r15
0x1800e225e  pop     r14
0x1800e2260  pop     r13
0x1800e2262  pop     r12
0x1800e2264  pop     rdi
0x1800e2265  pop     rsi
0x1800e2266  pop     rbx
0x1800e2267  pop     rbp
0x1800e2268  retn
```
