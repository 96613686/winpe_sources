# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000fc50`
- end: `0x18000fe3a`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `490`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e494`
- `0x18000fc50`

## callees

- `0x18000fc50`
- `0x180013840`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fd6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fd6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fd99`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fd99`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fdae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fdae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fcb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fcb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fdfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fd4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fdfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe0b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fd3a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fd3a`

## string_xrefs

- `0x18000fd65`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000fd77`: `RegDeleteKeyExW`
- `0x18000fd90`: `advapi32.dll`
- `0x18000fda4`: `RegDeleteKeyW`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  unsigned int v7; // edi
  unsigned int v8; // eax
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v11)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  DWORD LastError; // eax
  __int64 (__fastcall *v13)(HKEY, const unsigned __int16 *); // rax
  DWORD v14; // ebx
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
  if ( v5 )
  {
LABEL_21:
    if ( v6 )
      RegCloseKey(v6);
    return v7;
  }
  else
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
        goto LABEL_21;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    if ( !this[1] && !this[2] )
    {
      ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
      if ( ModuleHandleW )
      {
        this[1] = (HKEY)GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
      }
      else
      {
        Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
        if ( Library )
          this[2] = (HKEY)GetProcAddress(Library, "RegDeleteKeyW");
      }
    }
    v11 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))this[1];
    if ( v11 )
    {
      LastError = v11(*this, a2, 0, 0);
    }
    else
    {
      v13 = (__int64 (__fastcall *)(HKEY, const unsigned __int16 *))this[2];
      if ( v13 )
        LastError = v13(*this, a2);
      else
        LastError = GetLastError();
    }
    v14 = LastError;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v14;
  }
}

```

## disassembly

```asm
0x18000fc50  mov     [rsp-8+arg_10], rbx
0x18000fc55  mov     [rsp-8+arg_18], rsi
0x18000fc5a  push    rbp
0x18000fc5b  push    rdi
0x18000fc5c  push    r14
0x18000fc5e  lea     rbp, [rsp-180h]
0x18000fc66  sub     rsp, 280h
0x18000fc6d  mov     rax, cs:__security_cookie
0x18000fc74  xor     rax, rsp
0x18000fc77  mov     [rbp+190h+var_20], rax
0x18000fc7e  xor     r14d, r14d
0x18000fc81  lea     rax, [rsp+290h+var_230]
0x18000fc86  mov     rbx, rcx
0x18000fc89  mov     [rsp+290h+hKey], r14
0x18000fc8e  mov     rcx, [rcx]; hKey
0x18000fc91  mov     r9d, 2001Fh; samDesired
0x18000fc97  xor     r8d, r8d; ulOptions
0x18000fc9a  mov     [rsp+290h+var_240], r14
0x18000fc9f  mov     [rsp+290h+var_238], r14
0x18000fca4  mov     rsi, rdx
0x18000fca7  mov     [rsp+290h+var_230], r14
0x18000fcac  mov     [rsp+290h+phkResult], rax; phkResult
0x18000fcb1  call    cs:__imp_RegOpenKeyExW
0x18000fcb7  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fcbc  mov     edi, eax
0x18000fcbe  test    eax, eax
0x18000fcc0  jnz     loc_18000FE06
0x18000fcc6  mov     edi, r14d
0x18000fcc9  test    rcx, rcx
0x18000fccc  jz      short loc_18000FCD6
0x18000fcce  call    cs:__imp_RegCloseKey
0x18000fcd4  mov     edi, eax
0x18000fcd6  mov     rcx, [rsp+290h+var_230]
0x18000fcdb  mov     [rsp+290h+hKey], rcx
0x18000fce0  test    edi, edi
0x18000fce2  jnz     loc_18000FE06
0x18000fce8  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000fced  jmp     short loc_18000FD0D
0x18000fcef  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000fcf4  lea     rcx, [rsp+290h+hKey]; this
0x18000fcf9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000fcfe  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fd03  mov     edi, eax
0x18000fd05  test    eax, eax
0x18000fd07  jnz     loc_18000FE06
0x18000fd0d  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000fd12  mov     [rsp+290h+cchName], 100h
0x18000fd1a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000fd1f  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000fd24  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000fd29  lea     r8, [rsp+290h+Name]; lpName
0x18000fd2e  mov     [rsp+290h+lpClass], r14; lpClass
0x18000fd33  xor     edx, edx; dwIndex
0x18000fd35  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000fd3a  call    cs:__imp_RegEnumKeyExW
0x18000fd40  test    eax, eax
0x18000fd42  jz      short loc_18000FCEF
0x18000fd44  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fd49  test    rcx, rcx
0x18000fd4c  jz      short loc_18000FD59
0x18000fd4e  call    cs:__imp_RegCloseKey
0x18000fd54  mov     [rsp+290h+hKey], r14
0x18000fd59  cmp     [rbx+8], r14
0x18000fd5d  jnz     short loc_18000FDB8
0x18000fd5f  cmp     [rbx+10h], r14
0x18000fd63  jnz     short loc_18000FDB8
0x18000fd65  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000fd6c  call    cs:__imp_GetModuleHandleW
0x18000fd72  test    rax, rax
0x18000fd75  jz      short loc_18000FD8D
0x18000fd77  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000fd7e  mov     rcx, rax; hModule
0x18000fd81  call    cs:__imp_GetProcAddress
0x18000fd87  mov     [rbx+8], rax
0x18000fd8b  jmp     short loc_18000FDB8
0x18000fd8d  xor     r8d, r8d; dwFlags
0x18000fd90  lea     rcx, LibFileName; "advapi32.dll"
0x18000fd97  xor     edx, edx; hFile
0x18000fd99  call    cs:__imp_LoadLibraryExW
0x18000fd9f  test    rax, rax
0x18000fda2  jz      short loc_18000FDB8
0x18000fda4  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000fdab  mov     rcx, rax; hModule
0x18000fdae  call    cs:__imp_GetProcAddress
0x18000fdb4  mov     [rbx+10h], rax
0x18000fdb8  mov     rax, [rbx+8]
0x18000fdbc  test    rax, rax
0x18000fdbf  jz      short loc_18000FDD4
0x18000fdc1  mov     rcx, [rbx]
0x18000fdc4  xor     r9d, r9d
0x18000fdc7  xor     r8d, r8d
0x18000fdca  mov     rdx, rsi
0x18000fdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd2  jmp     short loc_18000FDF0
0x18000fdd4  mov     rax, [rbx+10h]
0x18000fdd8  test    rax, rax
0x18000fddb  jz      short loc_18000FDEA
0x18000fddd  mov     rcx, [rbx]
0x18000fde0  mov     rdx, rsi
0x18000fde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fde8  jmp     short loc_18000FDF0
0x18000fdea  call    cs:__imp_GetLastError
0x18000fdf0  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fdf5  mov     ebx, eax
0x18000fdf7  test    rcx, rcx
0x18000fdfa  jz      short loc_18000FE02
0x18000fdfc  call    cs:__imp_RegCloseKey
0x18000fe02  mov     eax, ebx
0x18000fe04  jmp     short loc_18000FE13
0x18000fe06  test    rcx, rcx
0x18000fe09  jz      short loc_18000FE11
0x18000fe0b  call    cs:__imp_RegCloseKey
0x18000fe11  mov     eax, edi
0x18000fe13  mov     rcx, [rbp+190h+var_20]
0x18000fe1a  xor     rcx, rsp; StackCookie
0x18000fe1d  call    __security_check_cookie
0x18000fe22  lea     r11, [rsp+290h+var_10]
0x18000fe2a  mov     rbx, [r11+30h]
0x18000fe2e  mov     rsi, [r11+38h]
0x18000fe32  mov     rsp, r11
0x18000fe35  pop     r14
0x18000fe37  pop     rdi
0x18000fe38  pop     rbp
0x18000fe39  retn
```
