# _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)

- ea: `0x180068c24`
- end: `0x180068e48`
- name: `?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z`
- size: `548`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066250`
- `0x180068988`
- `0x180068ef4`
- `0x180069d44`

## callees

- `0x18001e260`
- `0x180043c30`
- `0x180063758`
- `0x180068c24`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180068dd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180068e0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180068dd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180068e0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068cdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068cdf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068ccc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068ccc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180068d81`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180068d81`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180068d34`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180068d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068df6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068df6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180068d9f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180068ddf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180068d9f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180068ddf`

## pseudocode

```c
__int64 __fastcall _GetRegKeyLastWriteTime(HKEY a1, __int64 a2, __int64 a3, int a4, PFILETIME lpFileTime2)
{
  signed int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS InfoKeyW; // eax
  signed int v10; // edi
  DWORD v11; // ebx
  LSTATUS v12; // eax
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  memset(lpSubKey, 0, sizeof(lpSubKey));
  *lpFileTime2 = 0;
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
         lpSubKey,
         L"%s\\%s",
         a2,
         a3);
  if ( v7 >= 0 )
  {
    hKey = 0;
    if ( a4 == 1 )
      v8 = RegCreateKeyExW(a1, lpSubKey[0], 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    else
      v8 = RegOpenKeyExW(a1, lpSubKey[0], 0, 0x20019u, &hKey);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 < 0 )
    {
      if ( v7 == -2147024894 && !a4 )
      {
        GetSystemTimeAsFileTime(lpFileTime2);
        v7 = 0;
      }
    }
    else
    {
      InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, lpFileTime2);
      v10 = InfoKeyW;
      if ( InfoKeyW > 0 )
        v10 = (unsigned __int16)InfoKeyW | 0x80070000;
      v11 = 0;
      while ( v10 >= 0 )
      {
        cchName = 260;
        ftLastWriteTime = 0;
        v12 = RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
        v10 = v12;
        if ( v12 > 0 )
          v10 = (unsigned __int16)v12 | 0x80070000;
        if ( v10 >= 0 && CompareFileTime(&ftLastWriteTime, lpFileTime2) > 0 )
          *lpFileTime2 = ftLastWriteTime;
        ++v11;
      }
      v7 = 0;
      if ( v10 != -2147024637 )
        v7 = v10;
      if ( v7 >= 0 )
      {
        ftLastWriteTime = 0;
        GetSystemTimeAsFileTime(&ftLastWriteTime);
        if ( CompareFileTime(&ftLastWriteTime, lpFileTime2) < 0 )
          *lpFileTime2 = ftLastWriteTime;
      }
      RegCloseKey(hKey);
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180068c24  mov     [rsp-8+arg_18], rbx
0x180068c29  push    rbp
0x180068c2a  push    rsi
0x180068c2b  push    rdi
0x180068c2c  push    r14
0x180068c2e  push    r15
0x180068c30  lea     rbp, [rsp-1B0h]
0x180068c38  sub     rsp, 2B0h
0x180068c3f  mov     rax, cs:__security_cookie
0x180068c46  xor     rax, rsp
0x180068c49  mov     [rbp+1D0h+var_30], rax
0x180068c50  mov     rsi, [rbp+1D0h+lpFileTime2]
0x180068c57  xor     r15d, r15d
0x180068c5a  mov     edi, r9d
0x180068c5d  mov     [rsp+2D0h+lpSubKey], r15
0x180068c62  mov     r9, r8
0x180068c65  mov     [rbp+1D0h+var_250], r15
0x180068c69  mov     r14, rcx
0x180068c6c  mov     [rbp+1D0h+var_248], r15
0x180068c70  xor     eax, eax
0x180068c72  lea     rcx, [rsp+2D0h+lpSubKey]
0x180068c77  mov     r8, rdx
0x180068c7a  mov     [rsi], rax
0x180068c7d  lea     rdx, aSS; "%s\\%s"
0x180068c84  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180068c89  mov     ebx, eax
0x180068c8b  test    eax, eax
0x180068c8d  js      loc_180068E16
0x180068c93  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x180068c98  lea     rax, [rsp+2D0h+hKey]
0x180068c9d  xor     r8d, r8d; ulOptions
0x180068ca0  mov     [rsp+2D0h+hKey], r15
0x180068ca5  mov     rcx, r14; hKey
0x180068ca8  cmp     edi, 1
0x180068cab  jnz     short loc_180068CD4
0x180068cad  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180068cb2  xor     r9d, r9d; lpClass
0x180068cb5  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180068cba  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180068cbf  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x180068cc7  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180068ccc  call    cs:__imp_RegCreateKeyExW
0x180068cd2  jmp     short loc_180068CE5
0x180068cd4  mov     r9d, 20019h; samDesired
0x180068cda  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x180068cdf  call    cs:__imp_RegOpenKeyExW
0x180068ce5  mov     r14d, 80070000h
0x180068ceb  mov     ebx, eax
0x180068ced  test    eax, eax
0x180068cef  jle     short loc_180068CF7
0x180068cf1  movzx   ebx, ax
0x180068cf4  or      ebx, r14d
0x180068cf7  test    ebx, ebx
0x180068cf9  js      loc_180068DFE
0x180068cff  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180068d04  xor     r9d, r9d; lpReserved
0x180068d07  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180068d0c  xor     r8d, r8d; lpcchClass
0x180068d0f  mov     [rsp+2D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180068d14  xor     edx, edx; lpClass
0x180068d16  mov     [rsp+2D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180068d1b  mov     [rsp+2D0h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x180068d20  mov     [rsp+2D0h+phkResult], r15; lpcValues
0x180068d25  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x180068d2a  mov     qword ptr [rsp+2D0h+samDesired], r15; lpcbMaxSubKeyLen
0x180068d2f  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpcSubKeys
0x180068d34  call    cs:__imp_RegQueryInfoKeyW
0x180068d3a  mov     edi, eax
0x180068d3c  test    eax, eax
0x180068d3e  jle     short loc_180068D46
0x180068d40  movzx   edi, ax
0x180068d43  or      edi, r14d
0x180068d46  mov     ebx, r15d
0x180068d49  jmp     short loc_180068DB3
0x180068d4b  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180068d50  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x180068d55  mov     [rsp+2D0h+phkResult], rax; lpftLastWriteTime
0x180068d5a  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x180068d5f  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcchClass
0x180068d64  lea     r8, [rbp+1D0h+Name]; lpName
0x180068d68  mov     qword ptr [rsp+2D0h+samDesired], r15; lpClass
0x180068d6d  mov     edx, ebx; dwIndex
0x180068d6f  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpReserved
0x180068d74  mov     [rsp+2D0h+cchName], 104h
0x180068d7c  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x180068d81  call    cs:__imp_RegEnumKeyExW
0x180068d87  mov     edi, eax
0x180068d89  test    eax, eax
0x180068d8b  jle     short loc_180068D93
0x180068d8d  movzx   edi, ax
0x180068d90  or      edi, r14d
0x180068d93  test    edi, edi
0x180068d95  js      short loc_180068DB1
0x180068d97  mov     rdx, rsi; lpFileTime2
0x180068d9a  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x180068d9f  call    cs:__imp_CompareFileTime
0x180068da5  test    eax, eax
0x180068da7  jle     short loc_180068DB1
0x180068da9  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x180068dae  mov     [rsi], rax
0x180068db1  inc     ebx
0x180068db3  test    edi, edi
0x180068db5  jns     short loc_180068D4B
0x180068db7  cmp     edi, 80070103h
0x180068dbd  mov     ebx, r15d
0x180068dc0  cmovnz  ebx, edi
0x180068dc3  test    ebx, ebx
0x180068dc5  js      short loc_180068DF1
0x180068dc7  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpSystemTimeAsFileTime
0x180068dcc  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x180068dd1  call    cs:__imp_GetSystemTimeAsFileTime
0x180068dd7  mov     rdx, rsi; lpFileTime2
0x180068dda  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x180068ddf  call    cs:__imp_CompareFileTime
0x180068de5  test    eax, eax
0x180068de7  jns     short loc_180068DF1
0x180068de9  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x180068dee  mov     [rsi], rax
0x180068df1  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180068df6  call    cs:__imp_RegCloseKey
0x180068dfc  jmp     short loc_180068E16
0x180068dfe  cmp     ebx, 80070002h
0x180068e04  jnz     short loc_180068E16
0x180068e06  test    edi, edi
0x180068e08  jnz     short loc_180068E16
0x180068e0a  mov     rcx, rsi; lpSystemTimeAsFileTime
0x180068e0d  call    cs:__imp_GetSystemTimeAsFileTime
0x180068e13  mov     ebx, r15d
0x180068e16  lea     rcx, [rsp+2D0h+lpSubKey]
0x180068e1b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180068e20  mov     eax, ebx
0x180068e22  mov     rcx, [rbp+1D0h+var_30]
0x180068e29  xor     rcx, rsp; StackCookie
0x180068e2c  call    __security_check_cookie
0x180068e31  mov     rbx, [rsp+2D0h+arg_18]
0x180068e39  add     rsp, 2B0h
0x180068e40  pop     r15
0x180068e42  pop     r14
0x180068e44  pop     rdi
0x180068e45  pop     rsi
0x180068e46  pop     rbp
0x180068e47  retn
```
