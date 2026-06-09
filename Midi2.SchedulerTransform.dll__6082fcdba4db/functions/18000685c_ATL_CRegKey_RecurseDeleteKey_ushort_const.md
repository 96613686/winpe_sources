# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000685c`
- end: `0x1800069a3`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000685c`
- `0x180006d1c`

## callees

- `0x180002000`
- `0x180005020`
- `0x18000685c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800068da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006952`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006974`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800068da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006952`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800068bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800068bd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000693e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000693e`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x18000685c  mov     [rsp-8+arg_10], rbx
0x180006861  mov     [rsp-8+arg_18], rsi
0x180006866  push    rbp
0x180006867  push    rdi
0x180006868  push    r14
0x18000686a  lea     rbp, [rsp-180h]
0x180006872  sub     rsp, 280h
0x180006879  mov     rax, cs:__security_cookie
0x180006880  xor     rax, rsp
0x180006883  mov     [rbp+190h+var_20], rax
0x18000688a  xor     r14d, r14d
0x18000688d  lea     rax, [rsp+290h+var_230]
0x180006892  mov     rdi, rcx
0x180006895  mov     [rsp+290h+hKey], r14
0x18000689a  mov     rcx, [rcx]; hKey
0x18000689d  mov     r9d, 2001Fh; samDesired
0x1800068a3  xor     r8d, r8d; ulOptions
0x1800068a6  mov     [rsp+290h+var_240], r14
0x1800068ab  mov     [rsp+290h+var_238], r14
0x1800068b0  mov     rsi, rdx
0x1800068b3  mov     [rsp+290h+var_230], r14
0x1800068b8  mov     [rsp+290h+phkResult], rax; phkResult
0x1800068bd  call    cs:__imp_RegOpenKeyExW
0x1800068c3  mov     rcx, [rsp+290h+hKey]; hKey
0x1800068c8  mov     ebx, eax
0x1800068ca  test    eax, eax
0x1800068cc  jnz     loc_18000696F
0x1800068d2  mov     ebx, r14d
0x1800068d5  test    rcx, rcx
0x1800068d8  jz      short loc_1800068E2
0x1800068da  call    cs:__imp_RegCloseKey
0x1800068e0  mov     ebx, eax
0x1800068e2  mov     rcx, [rsp+290h+var_230]
0x1800068e7  mov     [rsp+290h+hKey], rcx
0x1800068ec  test    ebx, ebx
0x1800068ee  jnz     short loc_18000696F
0x1800068f0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800068f5  jmp     short loc_180006911
0x1800068f7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800068fc  lea     rcx, [rsp+290h+hKey]; this
0x180006901  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180006906  mov     rcx, [rsp+290h+hKey]; hKey
0x18000690b  mov     ebx, eax
0x18000690d  test    eax, eax
0x18000690f  jnz     short loc_18000696F
0x180006911  lea     rax, [rsp+290h+ftLastWriteTime]
0x180006916  mov     [rsp+290h+cchName], 100h
0x18000691e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180006923  lea     r9, [rsp+290h+cchName]; lpcchName
0x180006928  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000692d  lea     r8, [rsp+290h+Name]; lpName
0x180006932  mov     [rsp+290h+lpClass], r14; lpClass
0x180006937  xor     edx, edx; dwIndex
0x180006939  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000693e  call    cs:__imp_RegEnumKeyExW
0x180006944  test    eax, eax
0x180006946  jz      short loc_1800068F7
0x180006948  mov     rcx, [rsp+290h+hKey]; hKey
0x18000694d  test    rcx, rcx
0x180006950  jz      short loc_18000695D
0x180006952  call    cs:__imp_RegCloseKey
0x180006958  mov     [rsp+290h+hKey], r14
0x18000695d  mov     rdx, rsi; unsigned __int16 *
0x180006960  mov     rcx, rdi; this
0x180006963  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180006968  mov     rcx, [rsp+290h+hKey]; hKey
0x18000696d  mov     ebx, eax
0x18000696f  test    rcx, rcx
0x180006972  jz      short loc_18000697A
0x180006974  call    cs:__imp_RegCloseKey
0x18000697a  mov     eax, ebx
0x18000697c  mov     rcx, [rbp+190h+var_20]
0x180006983  xor     rcx, rsp; StackCookie
0x180006986  call    __security_check_cookie
0x18000698b  lea     r11, [rsp+290h+var_10]
0x180006993  mov     rbx, [r11+30h]
0x180006997  mov     rsi, [r11+38h]
0x18000699b  mov     rsp, r11
0x18000699e  pop     r14
0x1800069a0  pop     rdi
0x1800069a1  pop     rbp
0x1800069a2  retn
```
