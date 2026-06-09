# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180011208`
- end: `0x1800113f2`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `490`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009260`
- `0x180010e98`
- `0x180011208`

## callees

- `0x180001b60`
- `0x180011208`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011324`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011324`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011351`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011351`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011339`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011366`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011339`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800112f2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800112f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011286`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011286`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011269`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011269`

## string_xrefs

- `0x18001131d`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001132f`: `RegDeleteKeyExW`
- `0x18001134a`: `advapi32.dll`
- `0x18001135c`: `RegDeleteKeyW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  HKEY v5; // rcx
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v8)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  DWORD LastError; // eax
  __int64 (__fastcall *v10)(HKEY, const unsigned __int16 *); // rax
  DWORD v11; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  phkResult = 0;
  v4 = RegOpenKeyExW(*this, a2, 0, 0x2001Fu, &phkResult);
  v5 = 0;
  if ( v4 )
  {
LABEL_21:
    if ( v5 )
      RegCloseKey(v5);
    return v4;
  }
  else
  {
    v5 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v5, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v5 = hKey[0];
      if ( v4 )
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
    v8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))this[1];
    if ( v8 )
    {
      LastError = v8(*this, a2, 0, 0);
    }
    else
    {
      v10 = (__int64 (__fastcall *)(HKEY, const unsigned __int16 *))this[2];
      if ( v10 )
        LastError = v10(*this, a2);
      else
        LastError = GetLastError();
    }
    v11 = LastError;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v11;
  }
}

```

## disassembly

```asm
0x180011208  mov     [rsp-8+arg_10], rbx
0x18001120d  mov     [rsp-8+arg_18], rsi
0x180011212  push    rbp
0x180011213  push    rdi
0x180011214  push    r14
0x180011216  lea     rbp, [rsp-180h]
0x18001121e  sub     rsp, 280h
0x180011225  mov     rax, cs:__security_cookie
0x18001122c  xor     rax, rsp
0x18001122f  mov     [rbp+190h+var_20], rax
0x180011236  mov     rsi, rdx
0x180011239  mov     rbx, rcx
0x18001123c  xor     r14d, r14d
0x18001123f  mov     [rsp+290h+hKey], r14
0x180011244  mov     [rsp+290h+var_240], r14
0x180011249  mov     [rsp+290h+var_238], r14
0x18001124e  mov     [rsp+290h+var_230], r14
0x180011253  lea     rax, [rsp+290h+var_230]
0x180011258  mov     [rsp+290h+phkResult], rax; phkResult
0x18001125d  mov     r9d, 2001Fh; samDesired
0x180011263  xor     r8d, r8d; ulOptions
0x180011266  mov     rcx, [rcx]; hKey
0x180011269  call    cs:__imp_RegOpenKeyExW
0x18001126f  mov     edi, eax
0x180011271  mov     rcx, [rsp+290h+hKey]; hKey
0x180011276  test    eax, eax
0x180011278  jnz     loc_1800113BE
0x18001127e  mov     edi, r14d
0x180011281  test    rcx, rcx
0x180011284  jz      short loc_18001128E
0x180011286  call    cs:__imp_RegCloseKey
0x18001128c  mov     edi, eax
0x18001128e  mov     rcx, [rsp+290h+var_230]
0x180011293  mov     [rsp+290h+hKey], rcx
0x180011298  test    edi, edi
0x18001129a  jnz     loc_1800113BE
0x1800112a0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800112a5  jmp     short loc_1800112C5
0x1800112a7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800112ac  lea     rcx, [rsp+290h+hKey]; this
0x1800112b1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800112b6  mov     edi, eax
0x1800112b8  mov     rcx, [rsp+290h+hKey]; hKey
0x1800112bd  test    eax, eax
0x1800112bf  jnz     loc_1800113BE
0x1800112c5  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800112ca  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800112cf  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800112d4  mov     [rsp+290h+lpClass], r14; lpClass
0x1800112d9  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800112de  mov     [rsp+290h+cchName], 100h
0x1800112e6  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800112eb  lea     r8, [rsp+290h+Name]; lpName
0x1800112f0  xor     edx, edx; dwIndex
0x1800112f2  call    cs:__imp_RegEnumKeyExW
0x1800112f8  test    eax, eax
0x1800112fa  jz      short loc_1800112A7
0x1800112fc  mov     rcx, [rsp+290h+hKey]; hKey
0x180011301  test    rcx, rcx
0x180011304  jz      short loc_180011311
0x180011306  call    cs:__imp_RegCloseKey
0x18001130c  mov     [rsp+290h+hKey], r14
0x180011311  cmp     [rbx+8], r14
0x180011315  jnz     short loc_180011370
0x180011317  cmp     [rbx+10h], r14
0x18001131b  jnz     short loc_180011370
0x18001131d  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180011324  call    cs:__imp_GetModuleHandleW
0x18001132a  test    rax, rax
0x18001132d  jz      short loc_180011345
0x18001132f  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180011336  mov     rcx, rax; hModule
0x180011339  call    cs:__imp_GetProcAddress
0x18001133f  mov     [rbx+8], rax
0x180011343  jmp     short loc_180011370
0x180011345  xor     r8d, r8d; dwFlags
0x180011348  xor     edx, edx; hFile
0x18001134a  lea     rcx, LibFileName; "advapi32.dll"
0x180011351  call    cs:__imp_LoadLibraryExW
0x180011357  test    rax, rax
0x18001135a  jz      short loc_180011370
0x18001135c  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180011363  mov     rcx, rax; hModule
0x180011366  call    cs:__imp_GetProcAddress
0x18001136c  mov     [rbx+10h], rax
0x180011370  mov     rax, [rbx+8]
0x180011374  test    rax, rax
0x180011377  jz      short loc_18001138C
0x180011379  xor     r9d, r9d
0x18001137c  xor     r8d, r8d
0x18001137f  mov     rdx, rsi
0x180011382  mov     rcx, [rbx]
0x180011385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001138a  jmp     short loc_1800113A8
0x18001138c  mov     rax, [rbx+10h]
0x180011390  test    rax, rax
0x180011393  jz      short loc_1800113A2
0x180011395  mov     rdx, rsi
0x180011398  mov     rcx, [rbx]
0x18001139b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113a0  jmp     short loc_1800113A8
0x1800113a2  call    cs:__imp_GetLastError
0x1800113a8  mov     ebx, eax
0x1800113aa  mov     rcx, [rsp+290h+hKey]; hKey
0x1800113af  test    rcx, rcx
0x1800113b2  jz      short loc_1800113BA
0x1800113b4  call    cs:__imp_RegCloseKey
0x1800113ba  mov     eax, ebx
0x1800113bc  jmp     short loc_1800113CB
0x1800113be  test    rcx, rcx
0x1800113c1  jz      short loc_1800113C9
0x1800113c3  call    cs:__imp_RegCloseKey
0x1800113c9  mov     eax, edi
0x1800113cb  mov     rcx, [rbp+190h+var_20]
0x1800113d2  xor     rcx, rsp; StackCookie
0x1800113d5  call    __security_check_cookie
0x1800113da  lea     r11, [rsp+290h+var_10]
0x1800113e2  mov     rbx, [r11+30h]
0x1800113e6  mov     rsi, [r11+38h]
0x1800113ea  mov     rsp, r11
0x1800113ed  pop     r14
0x1800113ef  pop     rdi
0x1800113f0  pop     rbp
0x1800113f1  retn
```
