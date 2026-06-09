# _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)

- ea: `0x180049b78`
- end: `0x180049d9c`
- name: `?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047670`
- `0x1800498dc`
- `0x180049e48`
- `0x18004b120`

## callees

- `0x1800120dc`
- `0x180044888`
- `0x180049b78`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049d25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049d25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049d61`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180049c88`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180049c88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049c20`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049c20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049d4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049c33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049c33`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180049cd5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180049cd5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049cf3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049d33`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049cf3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049d33`

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
0x180049b78  mov     [rsp-8+arg_18], rbx
0x180049b7d  push    rbp
0x180049b7e  push    rsi
0x180049b7f  push    rdi
0x180049b80  push    r14
0x180049b82  push    r15
0x180049b84  lea     rbp, [rsp-1B0h]
0x180049b8c  sub     rsp, 2B0h
0x180049b93  mov     rax, cs:__security_cookie
0x180049b9a  xor     rax, rsp
0x180049b9d  mov     [rbp+1D0h+var_30], rax
0x180049ba4  mov     rsi, [rbp+1D0h+lpFileTime2]
0x180049bab  xor     r15d, r15d
0x180049bae  mov     edi, r9d
0x180049bb1  mov     [rsp+2D0h+lpSubKey], r15
0x180049bb6  mov     r9, r8
0x180049bb9  mov     [rbp+1D0h+var_250], r15
0x180049bbd  mov     r14, rcx
0x180049bc0  mov     [rbp+1D0h+var_248], r15
0x180049bc4  xor     eax, eax
0x180049bc6  lea     rcx, [rsp+2D0h+lpSubKey]
0x180049bcb  mov     r8, rdx
0x180049bce  mov     [rsi], rax
0x180049bd1  lea     rdx, aSS; "%s\\%s"
0x180049bd8  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180049bdd  mov     ebx, eax
0x180049bdf  test    eax, eax
0x180049be1  js      loc_180049D6A
0x180049be7  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x180049bec  lea     rax, [rsp+2D0h+hKey]
0x180049bf1  xor     r8d, r8d; ulOptions
0x180049bf4  mov     [rsp+2D0h+hKey], r15
0x180049bf9  mov     rcx, r14; hKey
0x180049bfc  cmp     edi, 1
0x180049bff  jnz     short loc_180049C28
0x180049c01  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180049c06  xor     r9d, r9d; lpClass
0x180049c09  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180049c0e  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180049c13  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x180049c1b  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180049c20  call    cs:__imp_RegCreateKeyExW
0x180049c26  jmp     short loc_180049C39
0x180049c28  mov     r9d, 20019h; samDesired
0x180049c2e  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x180049c33  call    cs:__imp_RegOpenKeyExW
0x180049c39  mov     r14d, 80070000h
0x180049c3f  mov     ebx, eax
0x180049c41  test    eax, eax
0x180049c43  jle     short loc_180049C4B
0x180049c45  movzx   ebx, ax
0x180049c48  or      ebx, r14d
0x180049c4b  test    ebx, ebx
0x180049c4d  js      loc_180049D52
0x180049c53  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180049c58  xor     r9d, r9d; lpReserved
0x180049c5b  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180049c60  xor     r8d, r8d; lpcchClass
0x180049c63  mov     [rsp+2D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180049c68  xor     edx, edx; lpClass
0x180049c6a  mov     [rsp+2D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180049c6f  mov     [rsp+2D0h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x180049c74  mov     [rsp+2D0h+phkResult], r15; lpcValues
0x180049c79  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x180049c7e  mov     qword ptr [rsp+2D0h+samDesired], r15; lpcbMaxSubKeyLen
0x180049c83  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpcSubKeys
0x180049c88  call    cs:__imp_RegQueryInfoKeyW
0x180049c8e  mov     edi, eax
0x180049c90  test    eax, eax
0x180049c92  jle     short loc_180049C9A
0x180049c94  movzx   edi, ax
0x180049c97  or      edi, r14d
0x180049c9a  mov     ebx, r15d
0x180049c9d  jmp     short loc_180049D07
0x180049c9f  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180049ca4  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x180049ca9  mov     [rsp+2D0h+phkResult], rax; lpftLastWriteTime
0x180049cae  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x180049cb3  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcchClass
0x180049cb8  lea     r8, [rbp+1D0h+Name]; lpName
0x180049cbc  mov     qword ptr [rsp+2D0h+samDesired], r15; lpClass
0x180049cc1  mov     edx, ebx; dwIndex
0x180049cc3  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpReserved
0x180049cc8  mov     [rsp+2D0h+cchName], 104h
0x180049cd0  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x180049cd5  call    cs:__imp_RegEnumKeyExW
0x180049cdb  mov     edi, eax
0x180049cdd  test    eax, eax
0x180049cdf  jle     short loc_180049CE7
0x180049ce1  movzx   edi, ax
0x180049ce4  or      edi, r14d
0x180049ce7  test    edi, edi
0x180049ce9  js      short loc_180049D05
0x180049ceb  mov     rdx, rsi; lpFileTime2
0x180049cee  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x180049cf3  call    cs:__imp_CompareFileTime
0x180049cf9  test    eax, eax
0x180049cfb  jle     short loc_180049D05
0x180049cfd  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x180049d02  mov     [rsi], rax
0x180049d05  inc     ebx
0x180049d07  test    edi, edi
0x180049d09  jns     short loc_180049C9F
0x180049d0b  cmp     edi, 80070103h
0x180049d11  mov     ebx, r15d
0x180049d14  cmovnz  ebx, edi
0x180049d17  test    ebx, ebx
0x180049d19  js      short loc_180049D45
0x180049d1b  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpSystemTimeAsFileTime
0x180049d20  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x180049d25  call    cs:__imp_GetSystemTimeAsFileTime
0x180049d2b  mov     rdx, rsi; lpFileTime2
0x180049d2e  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x180049d33  call    cs:__imp_CompareFileTime
0x180049d39  test    eax, eax
0x180049d3b  jns     short loc_180049D45
0x180049d3d  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x180049d42  mov     [rsi], rax
0x180049d45  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180049d4a  call    cs:__imp_RegCloseKey
0x180049d50  jmp     short loc_180049D6A
0x180049d52  cmp     ebx, 80070002h
0x180049d58  jnz     short loc_180049D6A
0x180049d5a  test    edi, edi
0x180049d5c  jnz     short loc_180049D6A
0x180049d5e  mov     rcx, rsi; lpSystemTimeAsFileTime
0x180049d61  call    cs:__imp_GetSystemTimeAsFileTime
0x180049d67  mov     ebx, r15d
0x180049d6a  lea     rcx, [rsp+2D0h+lpSubKey]
0x180049d6f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180049d74  mov     eax, ebx
0x180049d76  mov     rcx, [rbp+1D0h+var_30]
0x180049d7d  xor     rcx, rsp; StackCookie
0x180049d80  call    __security_check_cookie
0x180049d85  mov     rbx, [rsp+2D0h+arg_18]
0x180049d8d  add     rsp, 2B0h
0x180049d94  pop     r15
0x180049d96  pop     r14
0x180049d98  pop     rdi
0x180049d99  pop     rsi
0x180049d9a  pop     rbp
0x180049d9b  retn
```
