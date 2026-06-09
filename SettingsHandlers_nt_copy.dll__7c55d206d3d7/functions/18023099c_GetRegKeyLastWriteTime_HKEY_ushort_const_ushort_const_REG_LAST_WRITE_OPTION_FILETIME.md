# _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)

- ea: `0x18023099c`
- end: `0x180230bf7`
- name: `?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z`
- size: `603`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18022dda0`
- `0x1802306f0`
- `0x180230ca8`
- `0x180232424`

## callees

- `0x18000c840`
- `0x18005019c`
- `0x18022a458`
- `0x18023099c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180230b0b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180230b0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180230ab8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180230ab8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180230a44`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180230a44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180230b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180230b98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180230a5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180230a5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180230b67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180230bb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180230b67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180230bb5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180230b2f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180230b7b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180230b2f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180230b7b`

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
0x18023099c  mov     [rsp-8+arg_18], rbx
0x1802309a1  push    rbp
0x1802309a2  push    rsi
0x1802309a3  push    rdi
0x1802309a4  push    r14
0x1802309a6  push    r15
0x1802309a8  lea     rbp, [rsp-1B0h]
0x1802309b0  sub     rsp, 2B0h
0x1802309b7  mov     rax, cs:__security_cookie
0x1802309be  xor     rax, rsp
0x1802309c1  mov     [rbp+1D0h+var_30], rax
0x1802309c8  mov     rsi, [rbp+1D0h+lpFileTime2]
0x1802309cf  xor     r15d, r15d
0x1802309d2  mov     edi, r9d
0x1802309d5  mov     [rsp+2D0h+lpSubKey], r15
0x1802309da  mov     r9, r8
0x1802309dd  mov     [rbp+1D0h+var_250], r15
0x1802309e1  mov     r14, rcx
0x1802309e4  mov     [rbp+1D0h+var_248], r15
0x1802309e8  xor     eax, eax
0x1802309ea  lea     rcx, [rsp+2D0h+lpSubKey]
0x1802309ef  mov     r8, rdx
0x1802309f2  mov     [rsi], rax
0x1802309f5  lea     rdx, aSS; "%s\\%s"
0x1802309fc  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180230a01  mov     ebx, eax
0x180230a03  test    eax, eax
0x180230a05  js      loc_180230BC4
0x180230a0b  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x180230a10  lea     rax, [rsp+2D0h+hKey]
0x180230a15  xor     r8d, r8d; ulOptions
0x180230a18  mov     [rsp+2D0h+hKey], r15
0x180230a1d  mov     rcx, r14; hKey
0x180230a20  cmp     edi, 1
0x180230a23  jnz     short loc_180230A52
0x180230a25  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x180230a2a  xor     r9d, r9d; lpClass
0x180230a2d  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180230a32  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180230a37  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x180230a3f  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x180230a44  call    cs:__imp_RegCreateKeyExW
0x180230a4b  nop     dword ptr [rax+rax+00h]
0x180230a50  jmp     short loc_180230A69
0x180230a52  mov     r9d, 20019h; samDesired
0x180230a58  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x180230a5d  call    cs:__imp_RegOpenKeyExW
0x180230a64  nop     dword ptr [rax+rax+00h]
0x180230a69  mov     r14d, 80070000h
0x180230a6f  mov     ebx, eax
0x180230a71  test    eax, eax
0x180230a73  jle     short loc_180230A7B
0x180230a75  movzx   ebx, ax
0x180230a78  or      ebx, r14d
0x180230a7b  test    ebx, ebx
0x180230a7d  js      loc_180230BA6
0x180230a83  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180230a88  xor     r9d, r9d; lpReserved
0x180230a8b  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180230a90  xor     r8d, r8d; lpcchClass
0x180230a93  mov     [rsp+2D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180230a98  xor     edx, edx; lpClass
0x180230a9a  mov     [rsp+2D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180230a9f  mov     [rsp+2D0h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x180230aa4  mov     [rsp+2D0h+phkResult], r15; lpcValues
0x180230aa9  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x180230aae  mov     qword ptr [rsp+2D0h+samDesired], r15; lpcbMaxSubKeyLen
0x180230ab3  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpcSubKeys
0x180230ab8  call    cs:__imp_RegQueryInfoKeyW
0x180230abf  nop     dword ptr [rax+rax+00h]
0x180230ac4  mov     edi, eax
0x180230ac6  test    eax, eax
0x180230ac8  jle     short loc_180230AD0
0x180230aca  movzx   edi, ax
0x180230acd  or      edi, r14d
0x180230ad0  mov     ebx, r15d
0x180230ad3  jmp     short loc_180230B49
0x180230ad5  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180230ada  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x180230adf  mov     [rsp+2D0h+phkResult], rax; lpftLastWriteTime
0x180230ae4  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x180230ae9  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpcchClass
0x180230aee  lea     r8, [rbp+1D0h+Name]; lpName
0x180230af2  mov     qword ptr [rsp+2D0h+samDesired], r15; lpClass
0x180230af7  mov     edx, ebx; dwIndex
0x180230af9  mov     qword ptr [rsp+2D0h+dwOptions], r15; lpReserved
0x180230afe  mov     [rsp+2D0h+cchName], 104h
0x180230b06  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x180230b0b  call    cs:__imp_RegEnumKeyExW
0x180230b12  nop     dword ptr [rax+rax+00h]
0x180230b17  mov     edi, eax
0x180230b19  test    eax, eax
0x180230b1b  jle     short loc_180230B23
0x180230b1d  movzx   edi, ax
0x180230b20  or      edi, r14d
0x180230b23  test    edi, edi
0x180230b25  js      short loc_180230B47
0x180230b27  mov     rdx, rsi; lpFileTime2
0x180230b2a  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x180230b2f  call    cs:__imp_CompareFileTime
0x180230b36  nop     dword ptr [rax+rax+00h]
0x180230b3b  test    eax, eax
0x180230b3d  jle     short loc_180230B47
0x180230b3f  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x180230b44  mov     [rsi], rax
0x180230b47  inc     ebx
0x180230b49  test    edi, edi
0x180230b4b  jns     short loc_180230AD5
0x180230b4d  cmp     edi, 80070103h
0x180230b53  mov     ebx, r15d
0x180230b56  cmovnz  ebx, edi
0x180230b59  test    ebx, ebx
0x180230b5b  js      short loc_180230B93
0x180230b5d  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpSystemTimeAsFileTime
0x180230b62  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r15
0x180230b67  call    cs:__imp_GetSystemTimeAsFileTime
0x180230b6e  nop     dword ptr [rax+rax+00h]
0x180230b73  mov     rdx, rsi; lpFileTime2
0x180230b76  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x180230b7b  call    cs:__imp_CompareFileTime
0x180230b82  nop     dword ptr [rax+rax+00h]
0x180230b87  test    eax, eax
0x180230b89  jns     short loc_180230B93
0x180230b8b  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x180230b90  mov     [rsi], rax
0x180230b93  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180230b98  call    cs:__imp_RegCloseKey
0x180230b9f  nop     dword ptr [rax+rax+00h]
0x180230ba4  jmp     short loc_180230BC4
0x180230ba6  cmp     ebx, 80070002h
0x180230bac  jnz     short loc_180230BC4
0x180230bae  test    edi, edi
0x180230bb0  jnz     short loc_180230BC4
0x180230bb2  mov     rcx, rsi; lpSystemTimeAsFileTime
0x180230bb5  call    cs:__imp_GetSystemTimeAsFileTime
0x180230bbc  nop     dword ptr [rax+rax+00h]
0x180230bc1  mov     ebx, r15d
0x180230bc4  lea     rcx, [rsp+2D0h+lpSubKey]
0x180230bc9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180230bce  mov     eax, ebx
0x180230bd0  mov     rcx, [rbp+1D0h+var_30]
0x180230bd7  xor     rcx, rsp; StackCookie
0x180230bda  call    __security_check_cookie
0x180230bdf  mov     rbx, [rsp+2D0h+arg_18]
0x180230be7  add     rsp, 2B0h
0x180230bee  pop     r15
0x180230bf0  pop     r14
0x180230bf2  pop     rdi
0x180230bf3  pop     rsi
0x180230bf4  pop     rbp
0x180230bf5  retn
```
