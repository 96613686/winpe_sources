# SetCallbackList

- ea: `0x18005af9c`
- end: `0x18005b237`
- name: `SetCallbackList`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005b620`

## callees

- `0x18005af9c`
- `0x18005cf68`
- `0x18005dbd0`
- `0x18005dd28`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b075`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b075`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005b042`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005b042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b1b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b1b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b205`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b01d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b176`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b01d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b176`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005b0f6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005b0f6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b1c2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b1e5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b1f0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b1c2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b1e5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005b1f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005b0ca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005b0d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005b0e0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005b0ca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005b0d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005b0e0`

## pseudocode

```c
LSTATUS __fastcall SetCallbackList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  __int64 v7; // r14
  const WCHAR *v8; // r15
  const WCHAR *v9; // r12
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // rbx
  HGLOBAL v13; // rsi
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[152]; // [rsp+70h] [rbp-90h] BYREF

  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  result = RegCreateKeyExW(a1, L"Callback", 0, (LPWSTR)&Class, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    do
    {
      cchName = 148;
      v4 = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0);
      if ( v4 )
        break;
      v4 = RegDeleteKeyExW(hKey, SubKey, 0, 0);
    }
    while ( !v4 );
    v5 = 0;
    if ( v4 != 259 )
      v5 = v4;
    if ( !v5 )
    {
      v6 = *a2;
      if ( v6 )
      {
        while ( 1 )
        {
          v7 = *(_QWORD *)(v6 + 16);
          v8 = &Class;
          v9 = &Class;
          if ( *(_QWORD *)(v7 + 8) )
            v8 = *(const WCHAR **)(v7 + 8);
          if ( *(_QWORD *)v7 )
            v9 = *(const WCHAR **)v7;
          v10 = lstrlenW(v9);
          v11 = lstrlenW(v8) + v10;
          v12 = (unsigned int)(lstrlenW(L"%s (%s)") + v11 + 1);
          v13 = GlobalAlloc(0x40u, 2 * v12);
          if ( !v13 )
            break;
          if ( StringCchPrintfExW((STRSAFE_LPWSTR)v13, (unsigned int)v12, 0, 0, 0x100u, L"%s (%s)", v8, v9) < 0 )
          {
            GlobalFree(v13);
            break;
          }
          v5 = RegCreateKeyExW(hKey, (LPCWSTR)v13, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &phkResult, &dwDisposition);
          if ( v5 )
          {
            GlobalFree(v13);
            goto LABEL_25;
          }
          v5 = SetRegDword(phkResult, L"DeviceType", *(unsigned int *)(v7 + 24));
          if ( !v5 )
            v5 = SetRegSz(phkResult, L"Number");
          RegCloseKey(phkResult);
          GlobalFree(v13);
          if ( !v5 )
          {
            v6 = *(_QWORD *)(v6 + 8);
            if ( v6 )
              continue;
          }
          goto LABEL_25;
        }
        v5 = 8;
      }
      else
      {
        v5 = 0;
      }
    }
LABEL_25:
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18005af9c  mov     [rsp-8+arg_10], rbx
0x18005afa1  push    rbp
0x18005afa2  push    rsi
0x18005afa3  push    rdi
0x18005afa4  push    r12
0x18005afa6  push    r13
0x18005afa8  push    r14
0x18005afaa  push    r15
0x18005afac  lea     rbp, [rsp-0B0h]
0x18005afb4  sub     rsp, 1B0h
0x18005afbb  mov     rax, cs:__security_cookie
0x18005afc2  xor     rax, rsp
0x18005afc5  mov     [rbp+0E0h+var_40], rax
0x18005afcc  xor     r13d, r13d
0x18005afcf  lea     rax, [rsp+1E0h+dwDisposition]
0x18005afd4  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18005afd9  lea     r9, Class; lpClass
0x18005afe0  lea     rax, [rsp+1E0h+hKey]
0x18005afe5  mov     [rsp+1E0h+cchName], r13d
0x18005afea  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18005afef  mov     rdi, rdx
0x18005aff2  mov     [rsp+1E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005aff7  lea     rdx, aCallback; "Callback"
0x18005affe  mov     [rsp+1E0h+samDesired], 2000Eh; samDesired
0x18005b006  xor     r8d, r8d; Reserved
0x18005b009  mov     [rsp+1E0h+dwOptions], r13d; dwOptions
0x18005b00e  mov     [rsp+1E0h+dwDisposition], r13d
0x18005b013  mov     [rsp+1E0h+hKey], r13
0x18005b018  mov     [rsp+1E0h+var_178], r13
0x18005b01d  call    cs:__imp_RegCreateKeyExW
0x18005b023  test    eax, eax
0x18005b025  jnz     loc_18005B20D
0x18005b02b  mov     ebx, 94h
0x18005b030  jmp     short loc_18005B04C
0x18005b032  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005b037  lea     rdx, [rsp+1E0h+SubKey]; lpSubKey
0x18005b03c  xor     r9d, r9d; Reserved
0x18005b03f  xor     r8d, r8d; samDesired
0x18005b042  call    cs:__imp_RegDeleteKeyExW
0x18005b048  test    eax, eax
0x18005b04a  jnz     short loc_18005B07F
0x18005b04c  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005b051  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x18005b056  mov     [rsp+1E0h+phkResult], r13; lpftLastWriteTime
0x18005b05b  lea     r8, [rsp+1E0h+SubKey]; lpName
0x18005b060  mov     [rsp+1E0h+lpSecurityAttributes], r13; lpcchClass
0x18005b065  xor     edx, edx; dwIndex
0x18005b067  mov     qword ptr [rsp+1E0h+samDesired], r13; lpClass
0x18005b06c  mov     qword ptr [rsp+1E0h+dwOptions], r13; lpReserved
0x18005b071  mov     [rsp+1E0h+cchName], ebx
0x18005b075  call    cs:__imp_RegEnumKeyExW
0x18005b07b  test    eax, eax
0x18005b07d  jz      short loc_18005B032
0x18005b07f  cmp     eax, 103h
0x18005b084  mov     ebx, r13d
0x18005b087  cmovnz  ebx, eax
0x18005b08a  test    ebx, ebx
0x18005b08c  jnz     loc_18005B200
0x18005b092  mov     rdi, [rdi]
0x18005b095  test    rdi, rdi
0x18005b098  jz      loc_18005B1FD
0x18005b09e  lea     rsi, aSS_0; "%s (%s)"
0x18005b0a5  mov     r14, [rdi+10h]
0x18005b0a9  lea     r15, Class
0x18005b0b0  lea     r12, Class
0x18005b0b7  cmp     [r14+8], r13
0x18005b0bb  cmovnz  r15, [r14+8]
0x18005b0c0  cmp     [r14], r13
0x18005b0c3  cmovnz  r12, [r14]
0x18005b0c7  mov     rcx, r12; lpString
0x18005b0ca  call    cs:__imp_lstrlenW
0x18005b0d0  mov     rcx, r15; lpString
0x18005b0d3  mov     ebx, eax
0x18005b0d5  call    cs:__imp_lstrlenW
0x18005b0db  mov     rcx, rsi; lpString
0x18005b0de  add     ebx, eax
0x18005b0e0  call    cs:__imp_lstrlenW
0x18005b0e6  lea     ecx, [rbx+1]
0x18005b0e9  add     ecx, eax
0x18005b0eb  mov     ebx, ecx
0x18005b0ed  lea     rdx, [rcx+rcx]; dwBytes
0x18005b0f1  mov     ecx, 40h ; '@'; uFlags
0x18005b0f6  call    cs:__imp_GlobalAlloc
0x18005b0fc  mov     rsi, rax
0x18005b0ff  test    rax, rax
0x18005b102  jz      loc_18005B1F6
0x18005b108  mov     [rsp+1E0h+phkResult], r12
0x18005b10d  lea     rax, aSS_0; "%s (%s)"
0x18005b114  mov     [rsp+1E0h+lpSecurityAttributes], r15
0x18005b119  xor     r9d, r9d; pcchRemaining
0x18005b11c  mov     qword ptr [rsp+1E0h+samDesired], rax; pszFormat
0x18005b121  xor     r8d, r8d; ppszDestEnd
0x18005b124  mov     edx, ebx; cchDest
0x18005b126  mov     [rsp+1E0h+dwOptions], 100h; dwFlags
0x18005b12e  mov     rcx, rsi; pszDest
0x18005b131  call    StringCchPrintfExW
0x18005b136  test    eax, eax
0x18005b138  js      loc_18005B1ED
0x18005b13e  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005b143  lea     rax, [rsp+1E0h+dwDisposition]
0x18005b148  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18005b14d  lea     r9, Class; lpClass
0x18005b154  lea     rax, [rsp+1E0h+var_178]
0x18005b159  xor     r8d, r8d; Reserved
0x18005b15c  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18005b161  mov     rdx, rsi; lpSubKey
0x18005b164  mov     [rsp+1E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005b169  mov     [rsp+1E0h+samDesired], 20006h; samDesired
0x18005b171  mov     [rsp+1E0h+dwOptions], r13d; dwOptions
0x18005b176  call    cs:__imp_RegCreateKeyExW
0x18005b17c  mov     ebx, eax
0x18005b17e  test    eax, eax
0x18005b180  jnz     short loc_18005B1E2
0x18005b182  mov     r8d, [r14+18h]
0x18005b186  lea     rdx, aDevicetype; "DeviceType"
0x18005b18d  mov     rcx, [rsp+1E0h+var_178]
0x18005b192  call    SetRegDword
0x18005b197  mov     ebx, eax
0x18005b199  test    eax, eax
0x18005b19b  jnz     short loc_18005B1B4
0x18005b19d  mov     r8, [r14+10h]
0x18005b1a1  lea     rdx, aNumber; "Number"
0x18005b1a8  mov     rcx, [rsp+1E0h+var_178]; hKey
0x18005b1ad  call    SetRegSz
0x18005b1b2  mov     ebx, eax
0x18005b1b4  mov     rcx, [rsp+1E0h+var_178]; hKey
0x18005b1b9  call    cs:__imp_RegCloseKey
0x18005b1bf  mov     rcx, rsi; hMem
0x18005b1c2  call    cs:__imp_GlobalFree
0x18005b1c8  test    ebx, ebx
0x18005b1ca  jnz     short loc_18005B200
0x18005b1cc  mov     rdi, [rdi+8]
0x18005b1d0  lea     rsi, aSS_0; "%s (%s)"
0x18005b1d7  test    rdi, rdi
0x18005b1da  jnz     loc_18005B0A5
0x18005b1e0  jmp     short loc_18005B200
0x18005b1e2  mov     rcx, rsi; hMem
0x18005b1e5  call    cs:__imp_GlobalFree
0x18005b1eb  jmp     short loc_18005B200
0x18005b1ed  mov     rcx, rsi; hMem
0x18005b1f0  call    cs:__imp_GlobalFree
0x18005b1f6  mov     ebx, 8
0x18005b1fb  jmp     short loc_18005B200
0x18005b1fd  mov     ebx, r13d
0x18005b200  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005b205  call    cs:__imp_RegCloseKey
0x18005b20b  mov     eax, ebx
0x18005b20d  mov     rcx, [rbp+0E0h+var_40]
0x18005b214  xor     rcx, rsp; StackCookie
0x18005b217  call    __security_check_cookie
0x18005b21c  mov     rbx, [rsp+1E0h+arg_10]
0x18005b224  add     rsp, 1B0h
0x18005b22b  pop     r15
0x18005b22d  pop     r14
0x18005b22f  pop     r13
0x18005b231  pop     r12
0x18005b233  pop     rdi
0x18005b234  pop     rsi
0x18005b235  pop     rbp
0x18005b236  retn
```
