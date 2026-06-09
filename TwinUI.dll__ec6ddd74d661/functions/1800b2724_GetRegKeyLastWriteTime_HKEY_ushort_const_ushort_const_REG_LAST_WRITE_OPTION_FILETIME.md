# _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)

- ea: `0x1800b2724`
- end: `0x1800b298d`
- name: `?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z`
- size: `617`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c574`
- `0x18010f600`
- `0x18037e840`
- `0x18037f3f8`

## callees

- `0x1800b2724`
- `0x1800f9388`
- `0x180142e10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b28ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b293d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b28ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b293d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b2893`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b2893`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b27cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b27cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2920`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2920`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b27e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b27e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b2840`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b2840`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b28b7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b2903`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b28b7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b2903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b2958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b2958`

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
  if ( lpSubKey[0] )
    CoTaskMemFree((LPVOID)lpSubKey[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b2724  mov     [rsp-8+arg_18], rbx
0x1800b2729  push    rbp
0x1800b272a  push    rsi
0x1800b272b  push    rdi
0x1800b272c  push    r12
0x1800b272e  push    r14
0x1800b2730  lea     rbp, [rsp-1B0h]
0x1800b2738  sub     rsp, 2B0h
0x1800b273f  mov     rax, cs:__security_cookie
0x1800b2746  xor     rax, rsp
0x1800b2749  mov     [rbp+1D0h+var_30], rax
0x1800b2750  mov     rsi, [rbp+1D0h+lpFileTime2]
0x1800b2757  xor     r12d, r12d
0x1800b275a  mov     edi, r9d
0x1800b275d  mov     [rsp+2D0h+lpSubKey], r12
0x1800b2762  mov     r9, r8
0x1800b2765  mov     [rbp+1D0h+var_250], r12
0x1800b2769  mov     r14, rcx
0x1800b276c  mov     [rbp+1D0h+var_248], r12
0x1800b2770  xor     eax, eax
0x1800b2772  lea     rcx, [rsp+2D0h+lpSubKey]
0x1800b2777  mov     r8, rdx
0x1800b277a  mov     [rsi], rax
0x1800b277d  lea     rdx, aSS_2; "%s\\%s"
0x1800b2784  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800b2789  mov     ebx, eax
0x1800b278b  test    eax, eax
0x1800b278d  js      loc_1800B294C
0x1800b2793  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x1800b2798  lea     rax, [rsp+2D0h+hKey]
0x1800b279d  xor     r8d, r8d; ulOptions
0x1800b27a0  mov     [rsp+2D0h+hKey], r12
0x1800b27a5  mov     rcx, r14; hKey
0x1800b27a8  cmp     edi, 1
0x1800b27ab  jnz     short loc_1800B27DA
0x1800b27ad  mov     [rsp+2D0h+lpdwDisposition], r12; lpdwDisposition
0x1800b27b2  xor     r9d, r9d; lpClass
0x1800b27b5  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800b27ba  mov     [rsp+2D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800b27bf  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x1800b27c7  mov     [rsp+2D0h+dwOptions], r12d; dwOptions
0x1800b27cc  call    cs:__imp_RegCreateKeyExW
0x1800b27d3  nop     dword ptr [rax+rax+00h]
0x1800b27d8  jmp     short loc_1800B27F1
0x1800b27da  mov     r9d, 20019h; samDesired
0x1800b27e0  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x1800b27e5  call    cs:__imp_RegOpenKeyExW
0x1800b27ec  nop     dword ptr [rax+rax+00h]
0x1800b27f1  mov     r14d, 80070000h
0x1800b27f7  mov     ebx, eax
0x1800b27f9  test    eax, eax
0x1800b27fb  jle     short loc_1800B2803
0x1800b27fd  movzx   ebx, ax
0x1800b2800  or      ebx, r14d
0x1800b2803  test    ebx, ebx
0x1800b2805  js      loc_1800B292E
0x1800b280b  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b2810  xor     r9d, r9d; lpReserved
0x1800b2813  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800b2818  xor     r8d, r8d; lpcchClass
0x1800b281b  mov     [rsp+2D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800b2820  xor     edx, edx; lpClass
0x1800b2822  mov     [rsp+2D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800b2827  mov     [rsp+2D0h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x1800b282c  mov     [rsp+2D0h+phkResult], r12; lpcValues
0x1800b2831  mov     [rsp+2D0h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x1800b2836  mov     qword ptr [rsp+2D0h+samDesired], r12; lpcbMaxSubKeyLen
0x1800b283b  mov     qword ptr [rsp+2D0h+dwOptions], r12; lpcSubKeys
0x1800b2840  call    cs:__imp_RegQueryInfoKeyW
0x1800b2847  nop     dword ptr [rax+rax+00h]
0x1800b284c  mov     edi, eax
0x1800b284e  test    eax, eax
0x1800b2850  jle     short loc_1800B2858
0x1800b2852  movzx   edi, ax
0x1800b2855  or      edi, r14d
0x1800b2858  mov     ebx, r12d
0x1800b285b  jmp     short loc_1800B28D1
0x1800b285d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b2862  lea     rax, [rsp+2D0h+ftLastWriteTime]
0x1800b2867  mov     [rsp+2D0h+phkResult], rax; lpftLastWriteTime
0x1800b286c  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800b2871  mov     [rsp+2D0h+lpSecurityAttributes], r12; lpcchClass
0x1800b2876  lea     r8, [rbp+1D0h+Name]; lpName
0x1800b287a  mov     qword ptr [rsp+2D0h+samDesired], r12; lpClass
0x1800b287f  mov     edx, ebx; dwIndex
0x1800b2881  mov     qword ptr [rsp+2D0h+dwOptions], r12; lpReserved
0x1800b2886  mov     [rsp+2D0h+cchName], 104h
0x1800b288e  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r12
0x1800b2893  call    cs:__imp_RegEnumKeyExW
0x1800b289a  nop     dword ptr [rax+rax+00h]
0x1800b289f  mov     edi, eax
0x1800b28a1  test    eax, eax
0x1800b28a3  jle     short loc_1800B28AB
0x1800b28a5  movzx   edi, ax
0x1800b28a8  or      edi, r14d
0x1800b28ab  test    edi, edi
0x1800b28ad  js      short loc_1800B28CF
0x1800b28af  mov     rdx, rsi; lpFileTime2
0x1800b28b2  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x1800b28b7  call    cs:__imp_CompareFileTime
0x1800b28be  nop     dword ptr [rax+rax+00h]
0x1800b28c3  test    eax, eax
0x1800b28c5  jle     short loc_1800B28CF
0x1800b28c7  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x1800b28cc  mov     [rsi], rax
0x1800b28cf  inc     ebx
0x1800b28d1  test    edi, edi
0x1800b28d3  jns     short loc_1800B285D
0x1800b28d5  cmp     edi, 80070103h
0x1800b28db  mov     ebx, r12d
0x1800b28de  cmovnz  ebx, edi
0x1800b28e1  test    ebx, ebx
0x1800b28e3  js      short loc_1800B291B
0x1800b28e5  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpSystemTimeAsFileTime
0x1800b28ea  mov     qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime], r12
0x1800b28ef  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b28f6  nop     dword ptr [rax+rax+00h]
0x1800b28fb  mov     rdx, rsi; lpFileTime2
0x1800b28fe  lea     rcx, [rsp+2D0h+ftLastWriteTime]; lpFileTime1
0x1800b2903  call    cs:__imp_CompareFileTime
0x1800b290a  nop     dword ptr [rax+rax+00h]
0x1800b290f  test    eax, eax
0x1800b2911  jns     short loc_1800B291B
0x1800b2913  mov     rax, qword ptr [rsp+2D0h+ftLastWriteTime.dwLowDateTime]
0x1800b2918  mov     [rsi], rax
0x1800b291b  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800b2920  call    cs:__imp_RegCloseKey
0x1800b2927  nop     dword ptr [rax+rax+00h]
0x1800b292c  jmp     short loc_1800B294C
0x1800b292e  cmp     ebx, 80070002h
0x1800b2934  jnz     short loc_1800B294C
0x1800b2936  test    edi, edi
0x1800b2938  jnz     short loc_1800B294C
0x1800b293a  mov     rcx, rsi; lpSystemTimeAsFileTime
0x1800b293d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b2944  nop     dword ptr [rax+rax+00h]
0x1800b2949  mov     ebx, r12d
0x1800b294c  cmp     [rsp+2D0h+lpSubKey], r12
0x1800b2951  jz      short loc_1800B2964
0x1800b2953  mov     rcx, [rsp+2D0h+lpSubKey]; pv
0x1800b2958  call    cs:__imp_CoTaskMemFree
0x1800b295f  nop     dword ptr [rax+rax+00h]
0x1800b2964  mov     eax, ebx
0x1800b2966  mov     rcx, [rbp+1D0h+var_30]
0x1800b296d  xor     rcx, rsp; StackCookie
0x1800b2970  call    __security_check_cookie
0x1800b2975  mov     rbx, [rsp+2D0h+arg_18]
0x1800b297d  add     rsp, 2B0h
0x1800b2984  pop     r14
0x1800b2986  pop     r12
0x1800b2988  pop     rdi
0x1800b2989  pop     rsi
0x1800b298a  pop     rbp
0x1800b298b  retn
```
