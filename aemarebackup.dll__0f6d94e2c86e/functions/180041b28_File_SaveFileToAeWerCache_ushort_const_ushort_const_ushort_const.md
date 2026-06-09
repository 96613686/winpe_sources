# File::SaveFileToAeWerCache(ushort const *,ushort const *,ushort const *)

- ea: `0x180041b28`
- end: `0x180041ea6`
- name: `?SaveFileToAeWerCache@File@@CAXPEBG00@Z`
- size: `894`
- prototype: `void __fastcall(LPCWSTR lpSubKey, _WORD *lpData, _WORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041eac`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000d62c`
- `0x180041b28`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041c41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041c41`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041e54`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041e54`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041bf8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041bf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041ce9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041d61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041ce9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d4e`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180041d0f`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180041d0f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041da0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041da0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ce1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ce1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e76`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041ded`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041e27`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041ded`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041e27`

## string_xrefs

- `0x180041bf1`: `ntdll.dll`
- `0x180041baa`: `%s\appcompat`
- `0x180041bc8`: `StringCchPrintf for appCompatDirectory [%#x]`
- `0x180041bd5`: `File::SaveFileToAeWerCache`
- `0x180041c22`: `File::SaveFileToAeWerCache`
- `0x180041e44`: `File::SaveFileToAeWerCache`
- `0x180041c15`: `LoadLibraryEx for ntdll.dll failed [%d]`
- `0x180041c92`: `Amcache.hve`
- `0x180041daa`: `Failed to open file key [%d]`

## pseudocode

```c
void __fastcall File::SaveFileToAeWerCache(LPCWSTR lpSubKey, _WORD *lpData, _WORD *a3)
{
  int v6; // eax
  HMODULE Library; // rax
  HMODULE v8; // rbx
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax
  unsigned __int16 *v11; // r9
  LSTATUS AppKeyW; // eax
  const char *v13; // r9
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  DWORD Reserved[2]; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[264]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v22[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR File[264]; // [rsp+490h] [rbp+390h] BYREF

  memset_0(v22, 0, 0x208u);
  memset_0(v21, 0, 0x208u);
  memset_0(File, 0, 0x208u);
  hKey[0] = 0;
  phkResult = 0;
  v6 = StringCchPrintfW(v21, 0x104u, L"%s\\appcompat", 2147352624);
  if ( v6 < 0 )
  {
    AslLogCallPrintf(1, "File::SaveFileToAeWerCache", 1349, "StringCchPrintf for appCompatDirectory [%#x]", v6);
    goto LABEL_30;
  }
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v8 = Library;
  hKey[1] = (HKEY)Library;
  if ( !Library )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "File::SaveFileToAeWerCache", 1356, "LoadLibraryEx for ntdll.dll failed [%d]", LastError);
    goto LABEL_30;
  }
  ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
  if ( ProcAddress )
    ((void (__fastcall *)(unsigned __int16 *, _QWORD, unsigned __int16 *, __int64, _WORD *, int, _QWORD))ProcAddress)(
      v21,
      0,
      v21,
      1,
      v22,
      520,
      0);
  v11 = v22;
  if ( !v22[0] )
    v11 = v21;
  AppKeyW = StringCchPrintfW(File, 0x104u, L"%ls\\programs\\%ls", v11, L"Amcache.hve");
  if ( AppKeyW >= 0 )
  {
    hKey[0] = 0;
    AppKeyW = RegLoadAppKeyW(File, hKey, 0xF003Fu, 0, 0);
    if ( AppKeyW )
    {
      if ( AppKeyW == 5 || AppKeyW == 2 )
      {
        v14 = 1390;
        v15 = 3;
      }
      else
      {
        v14 = 1394;
        v15 = 1;
      }
      v13 = "RegLoadAppKey failed [%d]";
      goto LABEL_28;
    }
    phkResult = 0;
    AppKeyW = RegCreateKeyExW(hKey[0], L"Root\\InventoryApplicationFile", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    if ( AppKeyW )
    {
      v13 = "Failed to open file key [%d]";
      v14 = 1403;
    }
    else
    {
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( lpData[v17] );
      AppKeyW = RegSetKeyValueW(phkResult, lpSubKey, L"ProgramId", 1u, lpData, 2 * v17);
      if ( AppKeyW )
      {
        v14 = 1411;
      }
      else
      {
        do
          ++v16;
        while ( a3[v16] );
        AppKeyW = RegSetKeyValueW(phkResult, lpSubKey, L"FileId", 1u, a3, 2 * v16);
        if ( !AppKeyW )
          goto LABEL_29;
        v14 = 1419;
      }
      v13 = "Failed to set program id [%d]";
    }
  }
  else
  {
    v13 = "StringCchPrintf [%#x]";
    v14 = 1381;
  }
  v15 = 1;
LABEL_28:
  Reserved[0] = AppKeyW;
  AslLogCallPrintf(v15, "File::SaveFileToAeWerCache", v14, v13, *(_QWORD *)Reserved);
LABEL_29:
  FreeLibrary(v8);
LABEL_30:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
}

```

## disassembly

```asm
0x180041b28  mov     [rsp-8+arg_18], rbx
0x180041b2d  push    rbp
0x180041b2e  push    rsi
0x180041b2f  push    rdi
0x180041b30  push    r12
0x180041b32  push    r13
0x180041b34  push    r14
0x180041b36  push    r15
0x180041b38  lea     rbp, [rsp-5B0h]
0x180041b40  sub     rsp, 6B0h
0x180041b47  mov     rax, cs:__security_cookie
0x180041b4e  xor     rax, rsp
0x180041b51  mov     [rbp+5E0h+var_40], rax
0x180041b58  mov     r12, r8
0x180041b5b  mov     r15, rdx
0x180041b5e  mov     r13, rcx
0x180041b61  mov     r14d, 208h
0x180041b67  mov     r8d, r14d; Size
0x180041b6a  xor     edx, edx; Val
0x180041b6c  lea     rcx, [rbp+5E0h+var_460]; void *
0x180041b73  call    memset_0
0x180041b78  mov     r8d, r14d; Size
0x180041b7b  xor     edx, edx; Val
0x180041b7d  lea     rcx, [rsp+6E0h+var_670]; void *
0x180041b82  call    memset_0
0x180041b87  mov     r8d, r14d; Size
0x180041b8a  xor     edx, edx; Val
0x180041b8c  lea     rcx, [rbp+5E0h+File]; void *
0x180041b93  call    memset_0
0x180041b98  xor     edi, edi
0x180041b9a  mov     [rsp+6E0h+hKey], rdi
0x180041b9f  mov     [rsp+6E0h+var_690], rdi
0x180041ba4  mov     r9d, 7FFE0030h
0x180041baa  lea     r8, aSAppcompat; "%s\\appcompat"
0x180041bb1  mov     edx, 104h; unsigned __int64
0x180041bb6  lea     rcx, [rsp+6E0h+var_670]; unsigned __int16 *
0x180041bbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041bc0  test    eax, eax
0x180041bc2  jns     short loc_180041BE9
0x180041bc4  mov     [rsp+6E0h+Reserved], eax
0x180041bc8  lea     r9, aStringcchprint_2; "StringCchPrintf for appCompatDirectory "...
0x180041bcf  mov     r8d, 545h
0x180041bd5  lea     rdx, aFileSavefileto_0; "File::SaveFileToAeWerCache"
0x180041bdc  lea     ecx, [rdi+1]
0x180041bdf  call    AslLogCallPrintf
0x180041be4  jmp     loc_180041E5B
0x180041be9  xor     edx, edx; hFile
0x180041beb  mov     r8d, 800h; dwFlags
0x180041bf1  lea     rcx, LibFileName; "ntdll.dll"
0x180041bf8  call    cs:__imp_LoadLibraryExW
0x180041bfe  mov     rbx, rax
0x180041c01  mov     [rsp+6E0h+var_680], rax
0x180041c06  test    rax, rax
0x180041c09  jnz     short loc_180041C37
0x180041c0b  call    cs:__imp_GetLastError
0x180041c11  mov     [rsp+6E0h+Reserved], eax
0x180041c15  lea     r9, aLoadlibraryexF; "LoadLibraryEx for ntdll.dll failed [%d]"
0x180041c1c  mov     r8d, 54Ch
0x180041c22  lea     rdx, aFileSavefileto_0; "File::SaveFileToAeWerCache"
0x180041c29  lea     ecx, [rbx+1]
0x180041c2c  call    AslLogCallPrintf
0x180041c31  nop
0x180041c32  jmp     loc_180041E5B
0x180041c37  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180041c3e  mov     rcx, rbx; hModule
0x180041c41  call    cs:__imp_GetProcAddress
0x180041c47  mov     esi, 1
0x180041c4c  test    rax, rax
0x180041c4f  jz      short loc_180041C7B
0x180041c51  mov     [rsp+6E0h+lpSecurityAttributes], rdi
0x180041c56  mov     [rsp+6E0h+samDesired], r14d
0x180041c5b  lea     rcx, [rbp+5E0h+var_460]
0x180041c62  mov     qword ptr [rsp+6E0h+Reserved], rcx
0x180041c67  mov     r9d, esi
0x180041c6a  lea     r8, [rsp+6E0h+var_670]
0x180041c6f  xor     edx, edx
0x180041c71  lea     rcx, [rsp+6E0h+var_670]
0x180041c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c7b  lea     r9, [rbp+5E0h+var_460]
0x180041c82  lea     rax, [rsp+6E0h+var_670]
0x180041c87  cmp     [rbp+5E0h+var_460], di
0x180041c8e  cmovz   r9, rax
0x180041c92  lea     rax, aAmcacheHve; "Amcache.hve"
0x180041c99  mov     qword ptr [rsp+6E0h+Reserved], rax
0x180041c9e  lea     r8, aLsProgramsLs; "%ls\\programs\\%ls"
0x180041ca5  mov     edx, 104h; unsigned __int64
0x180041caa  lea     rcx, [rbp+5E0h+File]; unsigned __int16 *
0x180041cb1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041cb6  test    eax, eax
0x180041cb8  jns     short loc_180041CCC
0x180041cba  lea     r9, aStringcchprint_1; "StringCchPrintf [%#x]"
0x180041cc1  mov     r8d, 565h
0x180041cc7  jmp     loc_180041E3E
0x180041ccc  mov     r14, [rsp+6E0h+hKey]
0x180041cd1  test    r14, r14
0x180041cd4  jz      short loc_180041CF1
0x180041cd6  call    cs:__imp_GetLastError
0x180041cdc  mov     edi, eax
0x180041cde  mov     rcx, r14; hKey
0x180041ce1  call    cs:__imp_RegCloseKey
0x180041ce7  mov     ecx, edi; dwErrCode
0x180041ce9  call    cs:__imp_SetLastError
0x180041cef  xor     edi, edi
0x180041cf1  mov     [rsp+6E0h+hKey], rdi
0x180041cf6  mov     [rsp+6E0h+Reserved], edi; Reserved
0x180041cfa  xor     r9d, r9d; dwOptions
0x180041cfd  mov     r8d, 0F003Fh; samDesired
0x180041d03  lea     rdx, [rsp+6E0h+hKey]; phkResult
0x180041d08  lea     rcx, [rbp+5E0h+File]; lpFile
0x180041d0f  call    cs:__imp_RegLoadAppKeyW
0x180041d15  test    eax, eax
0x180041d17  jz      short loc_180041D44
0x180041d19  cmp     eax, 5
0x180041d1c  jz      short loc_180041D2D
0x180041d1e  cmp     eax, 2
0x180041d21  jz      short loc_180041D2D
0x180041d23  mov     r8d, 572h
0x180041d29  mov     ecx, esi
0x180041d2b  jmp     short loc_180041D38
0x180041d2d  mov     r8d, 56Eh
0x180041d33  mov     ecx, 3
0x180041d38  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x180041d3f  jmp     loc_180041E40
0x180041d44  mov     r14, [rsp+6E0h+var_690]
0x180041d49  test    r14, r14
0x180041d4c  jz      short loc_180041D69
0x180041d4e  call    cs:__imp_GetLastError
0x180041d54  mov     edi, eax
0x180041d56  mov     rcx, r14; hKey
0x180041d59  call    cs:__imp_RegCloseKey
0x180041d5f  mov     ecx, edi; dwErrCode
0x180041d61  call    cs:__imp_SetLastError
0x180041d67  xor     edi, edi
0x180041d69  mov     [rsp+6E0h+var_690], rdi
0x180041d6e  mov     [rsp+6E0h+lpdwDisposition], rdi; lpdwDisposition
0x180041d73  lea     rax, [rsp+6E0h+var_690]
0x180041d78  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180041d7d  mov     [rsp+6E0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180041d82  mov     [rsp+6E0h+samDesired], 0F003Fh; samDesired
0x180041d8a  mov     [rsp+6E0h+Reserved], edi; dwOptions
0x180041d8e  xor     r9d, r9d; lpClass
0x180041d91  xor     r8d, r8d; Reserved
0x180041d94  lea     rdx, aRootInventorya; "Root\\InventoryApplicationFile"
0x180041d9b  mov     rcx, [rsp+6E0h+hKey]; hKey
0x180041da0  call    cs:__imp_RegCreateKeyExW
0x180041da6  test    eax, eax
0x180041da8  jz      short loc_180041DBC
0x180041daa  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x180041db1  mov     r8d, 57Bh
0x180041db7  jmp     loc_180041E3E
0x180041dbc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041dc0  mov     rax, rdi
0x180041dc3  xor     r14d, r14d
0x180041dc6  inc     rax
0x180041dc9  cmp     [r15+rax*2], r14w
0x180041dce  jnz     short loc_180041DC6
0x180041dd0  add     eax, eax
0x180041dd2  mov     [rsp+6E0h+samDesired], eax; cbData
0x180041dd6  mov     qword ptr [rsp+6E0h+Reserved], r15; lpData
0x180041ddb  mov     r9d, esi; dwType
0x180041dde  lea     r8, aProgramid_0; "ProgramId"
0x180041de5  mov     rdx, r13; lpSubKey
0x180041de8  mov     rcx, [rsp+6E0h+var_690]; hKey
0x180041ded  call    cs:__imp_RegSetKeyValueW
0x180041df3  test    eax, eax
0x180041df5  jz      short loc_180041DFF
0x180041df7  mov     r8d, 583h
0x180041dfd  jmp     short loc_180041E37
0x180041dff  inc     rdi
0x180041e02  cmp     [r12+rdi*2], r14w
0x180041e07  jnz     short loc_180041DFF
0x180041e09  lea     eax, [rdi+rdi]
0x180041e0c  mov     [rsp+6E0h+samDesired], eax; cbData
0x180041e10  mov     qword ptr [rsp+6E0h+Reserved], r12; lpData
0x180041e15  mov     r9d, esi; dwType
0x180041e18  lea     r8, aFileid; "FileId"
0x180041e1f  mov     rdx, r13; lpSubKey
0x180041e22  mov     rcx, [rsp+6E0h+var_690]; hKey
0x180041e27  call    cs:__imp_RegSetKeyValueW
0x180041e2d  test    eax, eax
0x180041e2f  jz      short loc_180041E51
0x180041e31  mov     r8d, 58Bh
0x180041e37  lea     r9, aFailedToSetPro; "Failed to set program id [%d]"
0x180041e3e  mov     ecx, esi
0x180041e40  mov     [rsp+6E0h+Reserved], eax
0x180041e44  lea     rdx, aFileSavefileto_0; "File::SaveFileToAeWerCache"
0x180041e4b  call    AslLogCallPrintf
0x180041e50  nop
0x180041e51  mov     rcx, rbx; hLibModule
0x180041e54  call    cs:__imp_FreeLibrary
0x180041e5a  nop
0x180041e5b  mov     rcx, [rsp+6E0h+var_690]; hKey
0x180041e60  test    rcx, rcx
0x180041e63  jz      short loc_180041E6C
0x180041e65  call    cs:__imp_RegCloseKey
0x180041e6b  nop
0x180041e6c  mov     rcx, [rsp+6E0h+hKey]; hKey
0x180041e71  test    rcx, rcx
0x180041e74  jz      short loc_180041E7C
0x180041e76  call    cs:__imp_RegCloseKey
0x180041e7c  mov     rcx, [rbp+5E0h+var_40]
0x180041e83  xor     rcx, rsp; StackCookie
0x180041e86  call    __security_check_cookie
0x180041e8b  mov     rbx, [rsp+6E0h+arg_18]
0x180041e93  add     rsp, 6B0h
0x180041e9a  pop     r15
0x180041e9c  pop     r14
0x180041e9e  pop     r13
0x180041ea0  pop     r12
0x180041ea2  pop     rdi
0x180041ea3  pop     rsi
0x180041ea4  pop     rbp
0x180041ea5  retn
```
