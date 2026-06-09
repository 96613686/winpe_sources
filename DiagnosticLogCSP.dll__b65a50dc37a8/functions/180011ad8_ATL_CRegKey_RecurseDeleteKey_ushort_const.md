# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180011ad8`
- end: `0x180011d05`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `557`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800094c8`
- `0x180011734`
- `0x180011ad8`

## callees

- `0x180001b90`
- `0x180011ad8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011c45`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011c45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ca2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011bce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011bce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011be8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ccf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011be8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011cba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ccf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b39`

## string_xrefs

- `0x180011c05`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180011c1d`: `RegDeleteKeyExW`
- `0x180011c3e`: `advapi32.dll`
- `0x180011c56`: `RegDeleteKeyW`

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
0x180011ad8  mov     [rsp-8+arg_10], rbx
0x180011add  mov     [rsp-8+arg_18], rsi
0x180011ae2  push    rbp
0x180011ae3  push    rdi
0x180011ae4  push    r14
0x180011ae6  lea     rbp, [rsp-180h]
0x180011aee  sub     rsp, 280h
0x180011af5  mov     rax, cs:__security_cookie
0x180011afc  xor     rax, rsp
0x180011aff  mov     [rbp+190h+var_20], rax
0x180011b06  mov     rsi, rdx
0x180011b09  mov     rbx, rcx
0x180011b0c  xor     r14d, r14d
0x180011b0f  mov     [rsp+290h+hKey], r14
0x180011b14  mov     [rsp+290h+var_240], r14
0x180011b19  mov     [rsp+290h+var_238], r14
0x180011b1e  mov     [rsp+290h+var_230], r14
0x180011b23  lea     rax, [rsp+290h+var_230]
0x180011b28  mov     [rsp+290h+phkResult], rax; phkResult
0x180011b2d  mov     r9d, 2001Fh; samDesired
0x180011b33  xor     r8d, r8d; ulOptions
0x180011b36  mov     rcx, [rcx]; hKey
0x180011b39  call    cs:__imp_RegOpenKeyExW
0x180011b40  nop     dword ptr [rax+rax+00h]
0x180011b45  mov     edi, eax
0x180011b47  mov     rcx, [rsp+290h+hKey]; hKey
0x180011b4c  test    eax, eax
0x180011b4e  jnz     loc_180011CCA
0x180011b54  mov     edi, r14d
0x180011b57  test    rcx, rcx
0x180011b5a  jz      short loc_180011B6A
0x180011b5c  call    cs:__imp_RegCloseKey
0x180011b63  nop     dword ptr [rax+rax+00h]
0x180011b68  mov     edi, eax
0x180011b6a  mov     rcx, [rsp+290h+var_230]
0x180011b6f  mov     [rsp+290h+hKey], rcx
0x180011b74  test    edi, edi
0x180011b76  jnz     loc_180011CCA
0x180011b7c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180011b81  jmp     short loc_180011BA1
0x180011b83  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180011b88  lea     rcx, [rsp+290h+hKey]; this
0x180011b8d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180011b92  mov     edi, eax
0x180011b94  mov     rcx, [rsp+290h+hKey]; hKey
0x180011b99  test    eax, eax
0x180011b9b  jnz     loc_180011CCA
0x180011ba1  lea     rax, [rsp+290h+ftLastWriteTime]
0x180011ba6  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180011bab  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180011bb0  mov     [rsp+290h+lpClass], r14; lpClass
0x180011bb5  mov     [rsp+290h+phkResult], r14; lpReserved
0x180011bba  mov     [rsp+290h+cchName], 100h
0x180011bc2  lea     r9, [rsp+290h+cchName]; lpcchName
0x180011bc7  lea     r8, [rsp+290h+Name]; lpName
0x180011bcc  xor     edx, edx; dwIndex
0x180011bce  call    cs:__imp_RegEnumKeyExW
0x180011bd5  nop     dword ptr [rax+rax+00h]
0x180011bda  test    eax, eax
0x180011bdc  jz      short loc_180011B83
0x180011bde  mov     rcx, [rsp+290h+hKey]; hKey
0x180011be3  test    rcx, rcx
0x180011be6  jz      short loc_180011BF9
0x180011be8  call    cs:__imp_RegCloseKey
0x180011bef  nop     dword ptr [rax+rax+00h]
0x180011bf4  mov     [rsp+290h+hKey], r14
0x180011bf9  cmp     [rbx+8], r14
0x180011bfd  jnz     short loc_180011C70
0x180011bff  cmp     [rbx+10h], r14
0x180011c03  jnz     short loc_180011C70
0x180011c05  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180011c0c  call    cs:__imp_GetModuleHandleW
0x180011c13  nop     dword ptr [rax+rax+00h]
0x180011c18  test    rax, rax
0x180011c1b  jz      short loc_180011C39
0x180011c1d  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180011c24  mov     rcx, rax; hModule
0x180011c27  call    cs:__imp_GetProcAddress
0x180011c2e  nop     dword ptr [rax+rax+00h]
0x180011c33  mov     [rbx+8], rax
0x180011c37  jmp     short loc_180011C70
0x180011c39  xor     r8d, r8d; dwFlags
0x180011c3c  xor     edx, edx; hFile
0x180011c3e  lea     rcx, LibFileName; "advapi32.dll"
0x180011c45  call    cs:__imp_LoadLibraryExW
0x180011c4c  nop     dword ptr [rax+rax+00h]
0x180011c51  test    rax, rax
0x180011c54  jz      short loc_180011C70
0x180011c56  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180011c5d  mov     rcx, rax; hModule
0x180011c60  call    cs:__imp_GetProcAddress
0x180011c67  nop     dword ptr [rax+rax+00h]
0x180011c6c  mov     [rbx+10h], rax
0x180011c70  mov     rax, [rbx+8]
0x180011c74  test    rax, rax
0x180011c77  jz      short loc_180011C8C
0x180011c79  xor     r9d, r9d
0x180011c7c  xor     r8d, r8d
0x180011c7f  mov     rdx, rsi
0x180011c82  mov     rcx, [rbx]
0x180011c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c8a  jmp     short loc_180011CAE
0x180011c8c  mov     rax, [rbx+10h]
0x180011c90  test    rax, rax
0x180011c93  jz      short loc_180011CA2
0x180011c95  mov     rdx, rsi
0x180011c98  mov     rcx, [rbx]
0x180011c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca0  jmp     short loc_180011CAE
0x180011ca2  call    cs:__imp_GetLastError
0x180011ca9  nop     dword ptr [rax+rax+00h]
0x180011cae  mov     ebx, eax
0x180011cb0  mov     rcx, [rsp+290h+hKey]; hKey
0x180011cb5  test    rcx, rcx
0x180011cb8  jz      short loc_180011CC6
0x180011cba  call    cs:__imp_RegCloseKey
0x180011cc1  nop     dword ptr [rax+rax+00h]
0x180011cc6  mov     eax, ebx
0x180011cc8  jmp     short loc_180011CDD
0x180011cca  test    rcx, rcx
0x180011ccd  jz      short loc_180011CDB
0x180011ccf  call    cs:__imp_RegCloseKey
0x180011cd6  nop     dword ptr [rax+rax+00h]
0x180011cdb  mov     eax, edi
0x180011cdd  mov     rcx, [rbp+190h+var_20]
0x180011ce4  xor     rcx, rsp; StackCookie
0x180011ce7  call    __security_check_cookie
0x180011cec  lea     r11, [rsp+290h+var_10]
0x180011cf4  mov     rbx, [r11+30h]
0x180011cf8  mov     rsi, [r11+38h]
0x180011cfc  mov     rsp, r11
0x180011cff  pop     r14
0x180011d01  pop     rdi
0x180011d02  pop     rbp
0x180011d03  retn
```
