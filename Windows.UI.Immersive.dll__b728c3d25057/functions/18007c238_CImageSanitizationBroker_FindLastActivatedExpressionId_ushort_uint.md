# CImageSanitizationBroker::_FindLastActivatedExpressionId(ushort *,uint)

- ea: `0x18007c238`
- end: `0x18007c43b`
- name: `?_FindLastActivatedExpressionId@CImageSanitizationBroker@@AEAAJPEAGI@Z`
- size: `515`
- prototype: `int(CImageSanitizationBroker *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800363a0`

## callees

- `0x180015580`
- `0x180030674`
- `0x180050ba0`
- `0x18007c238`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007c2e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007c2e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c40f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c40f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c285`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c285`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007c3b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007c3b9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007c3db`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007c3db`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18007c33d`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18007c33d`

## pseudocode

```c
__int64 __fastcall CImageSanitizationBroker::_FindLastActivatedExpressionId(
        CImageSanitizationBroker *this,
        unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  DWORD i; // edi
  LSTATUS v7; // eax
  bool v8; // sf
  LSTATUS ValueW; // eax
  bool v10; // sf
  HKEY hKey; // [rsp+60h] [rbp-59h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v14; // [rsp+6Ch] [rbp-4Dh] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-49h] BYREF
  DWORD pcchName; // [rsp+74h] [rbp-45h] BYREF
  FILETIME pvData; // [rsp+78h] [rbp-41h] BYREF
  FILETIME FileTime1; // [rsp+80h] [rbp-39h] BYREF
  WCHAR pszName[32]; // [rsp+90h] [rbp-29h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent",
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_25;
  cSubKeys = 0;
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v4 = v5;
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x80070000;
  if ( v4 >= 0 )
  {
    v4 = -2147023728;
    FileTime1 = 0;
    for ( i = 0; ((int)(v4 + 0x80000000) < 0 || v4 == -2147023728) && i < cSubKeys; ++i )
    {
      pcchName = 32;
      v7 = SHEnumKeyExW(hKey, i, pszName, &pcchName);
      v8 = v7 < 0;
      if ( v7 > 0 )
        v8 = 1;
      if ( !v8 )
      {
        v14 = 0;
        pvData = 0;
        if ( (int)SHRegGetDWORD(hKey, pszName, L"HEALS", &v14) >= 0 && (v14 & 0x140) == 0 )
        {
          pcbData = 8;
          ValueW = RegGetValueW(hKey, pszName, L"LastActivated", 8u, 0, &pvData, &pcbData);
          v10 = ValueW < 0;
          if ( ValueW > 0 )
            v10 = 1;
          if ( !v10 && pcbData == 8 && CompareFileTime(&FileTime1, &pvData) < 0 )
          {
            v4 = StringCchCopyW(a2, 0x20u, pszName);
            if ( v4 >= 0 )
              FileTime1 = pvData;
          }
        }
      }
    }
  }
  RegCloseKey(hKey);
  if ( v4 < 0 )
LABEL_25:
    *a2 = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007c238  push    rbp
0x18007c23a  push    rbx
0x18007c23b  push    rsi
0x18007c23c  push    rdi
0x18007c23d  push    r14
0x18007c23f  push    r15
0x18007c241  lea     rbp, [rsp-2Fh]
0x18007c246  sub     rsp, 0E8h
0x18007c24d  mov     rax, cs:__security_cookie
0x18007c254  xor     rax, rsp
0x18007c257  mov     [rbp+57h+var_40], rax
0x18007c25b  mov     rsi, rdx
0x18007c25e  lea     rax, [rbp+57h+hKey]
0x18007c262  xor     r14d, r14d
0x18007c265  mov     [rsp+110h+phkResult], rax; phkResult
0x18007c26a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007c271  mov     [rbp+57h+hKey], r14
0x18007c275  mov     r9d, 20019h; samDesired
0x18007c27b  xor     r8d, r8d; ulOptions
0x18007c27e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c285  call    cs:__imp_RegOpenKeyExW
0x18007c28b  mov     ebx, eax
0x18007c28d  mov     r15d, 80070000h
0x18007c293  test    eax, eax
0x18007c295  jle     short loc_18007C29D
0x18007c297  movzx   ebx, ax
0x18007c29a  or      ebx, r15d
0x18007c29d  test    ebx, ebx
0x18007c29f  js      loc_18007C419
0x18007c2a5  mov     rcx, [rbp+57h+hKey]; hKey
0x18007c2a9  lea     rax, [rbp+57h+cSubKeys]
0x18007c2ad  mov     [rsp+110h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18007c2b2  xor     r9d, r9d; lpReserved
0x18007c2b5  mov     [rsp+110h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18007c2ba  xor     r8d, r8d; lpcchClass
0x18007c2bd  mov     [rsp+110h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18007c2c2  xor     edx, edx; lpClass
0x18007c2c4  mov     [rsp+110h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18007c2c9  mov     [rsp+110h+lpcValues], r14; lpcValues
0x18007c2ce  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18007c2d3  mov     [rsp+110h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18007c2d8  mov     [rsp+110h+phkResult], rax; lpcSubKeys
0x18007c2dd  mov     [rbp+57h+cSubKeys], r14d
0x18007c2e1  call    cs:__imp_RegQueryInfoKeyW
0x18007c2e7  mov     ebx, eax
0x18007c2e9  test    eax, eax
0x18007c2eb  jle     short loc_18007C2F3
0x18007c2ed  movzx   ebx, ax
0x18007c2f0  or      ebx, r15d
0x18007c2f3  test    ebx, ebx
0x18007c2f5  js      loc_18007C40B
0x18007c2fb  mov     ebx, 80070490h
0x18007c300  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x18007c304  mov     edi, r14d
0x18007c307  mov     ecx, 80000000h
0x18007c30c  lea     eax, [rbx+rcx]
0x18007c30f  test    ecx, eax
0x18007c311  jnz     short loc_18007C31F
0x18007c313  cmp     ebx, 80070490h
0x18007c319  jnz     loc_18007C40B
0x18007c31f  cmp     edi, [rbp+57h+cSubKeys]
0x18007c322  jnb     loc_18007C40B
0x18007c328  mov     rcx, [rbp+57h+hKey]; hkey
0x18007c32c  lea     r9, [rbp+57h+pcchName]; pcchName
0x18007c330  lea     r8, [rbp+57h+pszName]; pszName
0x18007c334  mov     [rbp+57h+pcchName], 20h ; ' '
0x18007c33b  mov     edx, edi; dwIndex
0x18007c33d  call    cs:__imp_SHEnumKeyExW
0x18007c343  test    eax, eax
0x18007c345  jle     short loc_18007C34F
0x18007c347  movzx   eax, ax
0x18007c34a  or      eax, r15d
0x18007c34d  test    eax, eax
0x18007c34f  js      loc_18007C404
0x18007c355  mov     rcx, [rbp+57h+hKey]; HKEY
0x18007c359  lea     r9, [rbp+57h+var_A4]; unsigned int *
0x18007c35d  lea     r8, aHeals; "HEALS"
0x18007c364  mov     [rbp+57h+var_A4], r14d
0x18007c368  lea     rdx, [rbp+57h+pszName]; unsigned __int16 *
0x18007c36c  mov     [rbp+57h+pvData], r14
0x18007c370  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18007c375  test    eax, eax
0x18007c377  js      loc_18007C404
0x18007c37d  test    [rbp+57h+var_A4], 140h
0x18007c384  jnz     short loc_18007C404
0x18007c386  mov     rcx, [rbp+57h+hKey]; hkey
0x18007c38a  lea     rax, [rbp+57h+pcbData]
0x18007c38e  mov     [rsp+110h+lpcbMaxClassLen], rax; pcbData
0x18007c393  lea     r8, aLastactivated; "LastActivated"
0x18007c39a  lea     rax, [rbp+57h+pvData]
0x18007c39e  mov     [rbp+57h+pcbData], 8
0x18007c3a5  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; pvData
0x18007c3aa  lea     rdx, [rbp+57h+pszName]; lpSubKey
0x18007c3ae  mov     r9d, 8; dwFlags
0x18007c3b4  mov     [rsp+110h+phkResult], r14; pdwType
0x18007c3b9  call    cs:__imp_RegGetValueW
0x18007c3bf  test    eax, eax
0x18007c3c1  jle     short loc_18007C3CB
0x18007c3c3  movzx   eax, ax
0x18007c3c6  or      eax, r15d
0x18007c3c9  test    eax, eax
0x18007c3cb  js      short loc_18007C404
0x18007c3cd  cmp     [rbp+57h+pcbData], 8
0x18007c3d1  jnz     short loc_18007C404
0x18007c3d3  lea     rdx, [rbp+57h+pvData]; lpFileTime2
0x18007c3d7  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x18007c3db  call    cs:__imp_CompareFileTime
0x18007c3e1  test    eax, eax
0x18007c3e3  jns     short loc_18007C404
0x18007c3e5  lea     r8, [rbp+57h+pszName]; unsigned __int16 *
0x18007c3e9  mov     edx, 20h ; ' '; unsigned __int64
0x18007c3ee  mov     rcx, rsi; unsigned __int16 *
0x18007c3f1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007c3f6  mov     ebx, eax
0x18007c3f8  test    eax, eax
0x18007c3fa  js      short loc_18007C404
0x18007c3fc  mov     rax, [rbp+57h+pvData]
0x18007c400  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rax
0x18007c404  inc     edi
0x18007c406  jmp     loc_18007C307
0x18007c40b  mov     rcx, [rbp+57h+hKey]; hKey
0x18007c40f  call    cs:__imp_RegCloseKey
0x18007c415  test    ebx, ebx
0x18007c417  jns     short loc_18007C41D
0x18007c419  mov     [rsi], r14w
0x18007c41d  mov     eax, ebx
0x18007c41f  mov     rcx, [rbp+57h+var_40]
0x18007c423  xor     rcx, rsp; StackCookie
0x18007c426  call    __security_check_cookie
0x18007c42b  add     rsp, 0E8h
0x18007c432  pop     r15
0x18007c434  pop     r14
0x18007c436  pop     rdi
0x18007c437  pop     rsi
0x18007c438  pop     rbx
0x18007c439  pop     rbp
0x18007c43a  retn
```
