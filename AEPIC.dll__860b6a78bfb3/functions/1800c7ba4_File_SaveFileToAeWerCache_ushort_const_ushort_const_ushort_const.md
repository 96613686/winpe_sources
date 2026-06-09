# File::SaveFileToAeWerCache(ushort const *,ushort const *,ushort const *)

- ea: `0x1800c7ba4`
- end: `0x1800c7ef9`
- name: `?SaveFileToAeWerCache@File@@CAXPEBG00@Z`
- size: `853`
- prototype: `void __fastcall(LPCWSTR lpSubKey, _WORD *lpData, _WORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c7f00`

## callees

- `0x180005890`
- `0x180006938`
- `0x1800081e8`
- `0x1800088e0`
- `0x18000cb74`
- `0x180010390`
- `0x1800295dc`
- `0x1800c31cc`
- `0x1800c7ba4`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c7c71`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c7c71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c7ca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c7ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7c81`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800c7d79`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800c7d79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c7e0d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c7e0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7dc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7dc5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c7e54`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c7e8e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c7e54`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c7e8e`

## string_xrefs

- `0x1800c7c6a`: `ntdll.dll`
- `0x1800c7cf9`: `Amcache.hve`
- `0x1800c7e17`: `Failed to open file key [%d]`
- `0x1800c7c3f`: `StringCchPrintf for appCompatDirectory [%#x]`
- `0x1800c7c21`: `%s\appcompat`
- `0x1800c7c87`: `LoadLibraryEx for ntdll.dll failed [%d]`
- `0x1800c7c4c`: `File::SaveFileToAeWerCache`
- `0x1800c7eab`: `File::SaveFileToAeWerCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall File::SaveFileToAeWerCache(LPCWSTR lpSubKey, _WORD *lpData, _WORD *a3)
{
  int v6; // eax
  HMODULE Library; // rax
  int LastError; // eax
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  FARPROC ProcAddress; // rax
  unsigned __int16 *v13; // r9
  __int64 v14; // rdi
  __int64 v15; // rax
  DWORD Reserved[2]; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HMODULE v18; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20[264]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v21[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR File[264]; // [rsp+490h] [rbp+390h] BYREF

  memset_0(v21, 0, 0x208u);
  memset_0(v20, 0, 0x208u);
  memset_0(File, 0, 0x208u);
  hKey = 0;
  phkResult = 0;
  v6 = StringCchPrintfW(v20, 0x104u, L"%s\\appcompat", 2147352624);
  if ( v6 >= 0 )
  {
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v18 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
      if ( ProcAddress )
        ((void (__fastcall *)(unsigned __int16 *, _QWORD, unsigned __int16 *, __int64, _WORD *, int, _QWORD))ProcAddress)(
          v20,
          0,
          v20,
          1,
          v21,
          520,
          0);
      v13 = v21;
      if ( !v21[0] )
        v13 = v20;
      LastError = StringCchPrintfW(File, 0x104u, L"%ls\\programs\\%ls", v13, L"Amcache.hve");
      if ( LastError >= 0 )
      {
        hKey = 0;
        LastError = RegLoadAppKeyW(File, &hKey, 0xF003Fu, 0, 0);
        if ( LastError )
        {
          if ( LastError == 5 || LastError == 2 )
          {
            v10 = 1390;
            v11 = 3;
          }
          else
          {
            v10 = 1394;
            v11 = 1;
          }
          v9 = "RegLoadAppKey failed [%d]";
          goto LABEL_28;
        }
        phkResult = 0;
        LastError = RegCreateKeyExW(hKey, L"Root\\InventoryApplicationFile", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
        if ( LastError )
        {
          v9 = "Failed to open file key [%d]";
          v10 = 1403;
        }
        else
        {
          v14 = -1;
          v15 = -1;
          do
            ++v15;
          while ( lpData[v15] );
          LastError = RegSetKeyValueW(phkResult, lpSubKey, L"ProgramId", 1u, lpData, 2 * v15);
          if ( LastError )
          {
            v10 = 1411;
          }
          else
          {
            do
              ++v14;
            while ( a3[v14] );
            LastError = RegSetKeyValueW(phkResult, lpSubKey, L"FileId", 1u, a3, 2 * v14);
            if ( !LastError )
              goto LABEL_29;
            v10 = 1419;
          }
          v9 = "Failed to set program id [%d]";
        }
      }
      else
      {
        v9 = "StringCchPrintf [%#x]";
        v10 = 1381;
      }
      v11 = 1;
    }
    else
    {
      LastError = GetLastError();
      v9 = "LoadLibraryEx for ntdll.dll failed [%d]";
      v10 = 1356;
      v11 = 1;
    }
LABEL_28:
    Reserved[0] = LastError;
    AslLogCallPrintf(v11, "File::SaveFileToAeWerCache", v10, v9, *(_QWORD *)Reserved);
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v18);
    goto LABEL_30;
  }
  AslLogCallPrintf(1, "File::SaveFileToAeWerCache", 1349, "StringCchPrintf for appCompatDirectory [%#x]", v6);
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800c7ba4  push    rbp
0x1800c7ba6  push    rbx
0x1800c7ba7  push    rsi
0x1800c7ba8  push    rdi
0x1800c7ba9  push    r12
0x1800c7bab  push    r14
0x1800c7bad  push    r15
0x1800c7baf  lea     rbp, [rsp-5B0h]
0x1800c7bb7  sub     rsp, 6B0h
0x1800c7bbe  mov     rax, cs:__security_cookie
0x1800c7bc5  xor     rax, rsp
0x1800c7bc8  mov     [rbp+5E0h+var_40], rax
0x1800c7bcf  mov     r14, r8
0x1800c7bd2  mov     rsi, rdx
0x1800c7bd5  mov     r15, rcx
0x1800c7bd8  mov     edi, 208h
0x1800c7bdd  mov     r8d, edi; Size
0x1800c7be0  xor     edx, edx; Val
0x1800c7be2  lea     rcx, [rbp+5E0h+var_460]; void *
0x1800c7be9  call    memset_0
0x1800c7bee  mov     r8d, edi; Size
0x1800c7bf1  xor     edx, edx; Val
0x1800c7bf3  lea     rcx, [rsp+6E0h+var_670]; void *
0x1800c7bf8  call    memset_0
0x1800c7bfd  mov     r8d, edi; Size
0x1800c7c00  xor     edx, edx; Val
0x1800c7c02  lea     rcx, [rbp+5E0h+File]; void *
0x1800c7c09  call    memset_0
0x1800c7c0e  xor     r12d, r12d
0x1800c7c11  mov     [rsp+6E0h+hKey], r12
0x1800c7c16  mov     [rsp+6E0h+var_690], r12
0x1800c7c1b  mov     r9d, 7FFE0030h
0x1800c7c21  lea     r8, aSAppcompat; "%s\\appcompat"
0x1800c7c28  mov     edx, 104h; unsigned __int64
0x1800c7c2d  lea     rcx, [rsp+6E0h+var_670]; unsigned __int16 *
0x1800c7c32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c7c37  test    eax, eax
0x1800c7c39  jns     short loc_1800C7C62
0x1800c7c3b  mov     [rsp+6E0h+Reserved], eax
0x1800c7c3f  lea     r9, aStringcchprint_4; "StringCchPrintf for appCompatDirectory "...
0x1800c7c46  mov     r8d, 545h
0x1800c7c4c  lea     rdx, aFileSavefileto_0; "File::SaveFileToAeWerCache"
0x1800c7c53  lea     ecx, [r12+1]
0x1800c7c58  call    AslLogCallPrintf
0x1800c7c5d  jmp     loc_1800C7EC3
0x1800c7c62  xor     edx, edx; hFile
0x1800c7c64  mov     r8d, 800h; dwFlags
0x1800c7c6a  lea     rcx, LibFileName; "ntdll.dll"
0x1800c7c71  call    cs:__imp_LoadLibraryExW
0x1800c7c77  mov     [rsp+6E0h+var_688], rax
0x1800c7c7c  test    rax, rax
0x1800c7c7f  jnz     short loc_1800C7C9E
0x1800c7c81  call    cs:__imp_GetLastError
0x1800c7c87  lea     r9, aLoadlibraryexF; "LoadLibraryEx for ntdll.dll failed [%d]"
0x1800c7c8e  mov     r8d, 54Ch
0x1800c7c94  mov     ecx, 1
0x1800c7c99  jmp     loc_1800C7EA7
0x1800c7c9e  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x1800c7ca5  mov     rcx, rax; hModule
0x1800c7ca8  call    cs:__imp_GetProcAddress
0x1800c7cae  mov     ebx, 1
0x1800c7cb3  test    rax, rax
0x1800c7cb6  jz      short loc_1800C7CE1
0x1800c7cb8  mov     [rsp+6E0h+lpSecurityAttributes], r12
0x1800c7cbd  mov     [rsp+6E0h+samDesired], edi
0x1800c7cc1  lea     rcx, [rbp+5E0h+var_460]
0x1800c7cc8  mov     qword ptr [rsp+6E0h+Reserved], rcx
0x1800c7ccd  mov     r9d, ebx
0x1800c7cd0  lea     r8, [rsp+6E0h+var_670]
0x1800c7cd5  xor     edx, edx
0x1800c7cd7  lea     rcx, [rsp+6E0h+var_670]
0x1800c7cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7ce1  lea     r9, [rbp+5E0h+var_460]
0x1800c7ce8  lea     rax, [rsp+6E0h+var_670]
0x1800c7ced  cmp     [rbp+5E0h+var_460], r12w
0x1800c7cf5  cmovz   r9, rax
0x1800c7cf9  lea     rax, aAmcacheHve; "Amcache.hve"
0x1800c7d00  mov     qword ptr [rsp+6E0h+Reserved], rax
0x1800c7d05  lea     r8, aLsProgramsLs; "%ls\\programs\\%ls"
0x1800c7d0c  mov     edx, 104h; unsigned __int64
0x1800c7d11  lea     rcx, [rbp+5E0h+File]; unsigned __int16 *
0x1800c7d18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c7d1d  test    eax, eax
0x1800c7d1f  jns     short loc_1800C7D33
0x1800c7d21  lea     r9, aStringcchprint_3; "StringCchPrintf [%#x]"
0x1800c7d28  mov     r8d, 565h
0x1800c7d2e  jmp     loc_1800C7EA5
0x1800c7d33  mov     rdi, [rsp+6E0h+hKey]
0x1800c7d38  test    rdi, rdi
0x1800c7d3b  jz      short loc_1800C7D5A
0x1800c7d3d  lea     rcx, [rsp+6E0h+var_678]; this
0x1800c7d42  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c7d47  mov     rcx, rdi; hKey
0x1800c7d4a  call    cs:__imp_RegCloseKey
0x1800c7d50  lea     rcx, [rsp+6E0h+var_678]; this
0x1800c7d55  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c7d5a  mov     [rsp+6E0h+hKey], r12
0x1800c7d5f  mov     [rsp+6E0h+Reserved], r12d; Reserved
0x1800c7d64  xor     r9d, r9d; dwOptions
0x1800c7d67  mov     r8d, 0F003Fh; samDesired
0x1800c7d6d  lea     rdx, [rsp+6E0h+hKey]; phkResult
0x1800c7d72  lea     rcx, [rbp+5E0h+File]; lpFile
0x1800c7d79  call    cs:__imp_RegLoadAppKeyW
0x1800c7d7f  test    eax, eax
0x1800c7d81  jz      short loc_1800C7DAE
0x1800c7d83  cmp     eax, 5
0x1800c7d86  jz      short loc_1800C7D97
0x1800c7d88  cmp     eax, 2
0x1800c7d8b  jz      short loc_1800C7D97
0x1800c7d8d  mov     r8d, 572h
0x1800c7d93  mov     ecx, ebx
0x1800c7d95  jmp     short loc_1800C7DA2
0x1800c7d97  mov     r8d, 56Eh
0x1800c7d9d  mov     ecx, 3
0x1800c7da2  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x1800c7da9  jmp     loc_1800C7EA7
0x1800c7dae  mov     rdi, [rsp+6E0h+var_690]
0x1800c7db3  test    rdi, rdi
0x1800c7db6  jz      short loc_1800C7DD5
0x1800c7db8  lea     rcx, [rsp+6E0h+var_678]; this
0x1800c7dbd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c7dc2  mov     rcx, rdi; hKey
0x1800c7dc5  call    cs:__imp_RegCloseKey
0x1800c7dcb  lea     rcx, [rsp+6E0h+var_678]; this
0x1800c7dd0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c7dd5  mov     [rsp+6E0h+var_690], r12
0x1800c7dda  mov     [rsp+6E0h+lpdwDisposition], r12; lpdwDisposition
0x1800c7ddf  lea     rax, [rsp+6E0h+var_690]
0x1800c7de4  mov     [rsp+6E0h+phkResult], rax; phkResult
0x1800c7de9  mov     [rsp+6E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800c7dee  mov     [rsp+6E0h+samDesired], 0F003Fh; samDesired
0x1800c7df6  mov     [rsp+6E0h+Reserved], r12d; dwOptions
0x1800c7dfb  xor     r9d, r9d; lpClass
0x1800c7dfe  xor     r8d, r8d; Reserved
0x1800c7e01  lea     rdx, aRootInventorya; "Root\\InventoryApplicationFile"
0x1800c7e08  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1800c7e0d  call    cs:__imp_RegCreateKeyExW
0x1800c7e13  test    eax, eax
0x1800c7e15  jz      short loc_1800C7E26
0x1800c7e17  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x1800c7e1e  mov     r8d, 57Bh
0x1800c7e24  jmp     short loc_1800C7EA5
0x1800c7e26  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c7e2a  mov     rax, rdi
0x1800c7e2d  inc     rax
0x1800c7e30  cmp     [rsi+rax*2], r12w
0x1800c7e35  jnz     short loc_1800C7E2D
0x1800c7e37  add     eax, eax
0x1800c7e39  mov     [rsp+6E0h+samDesired], eax; cbData
0x1800c7e3d  mov     qword ptr [rsp+6E0h+Reserved], rsi; lpData
0x1800c7e42  mov     r9d, ebx; dwType
0x1800c7e45  lea     r8, aProgramid; "ProgramId"
0x1800c7e4c  mov     rdx, r15; lpSubKey
0x1800c7e4f  mov     rcx, [rsp+6E0h+var_690]; hKey
0x1800c7e54  call    cs:__imp_RegSetKeyValueW
0x1800c7e5a  test    eax, eax
0x1800c7e5c  jz      short loc_1800C7E66
0x1800c7e5e  mov     r8d, 583h
0x1800c7e64  jmp     short loc_1800C7E9E
0x1800c7e66  inc     rdi
0x1800c7e69  cmp     [r14+rdi*2], r12w
0x1800c7e6e  jnz     short loc_1800C7E66
0x1800c7e70  lea     eax, [rdi+rdi]
0x1800c7e73  mov     [rsp+6E0h+samDesired], eax; cbData
0x1800c7e77  mov     qword ptr [rsp+6E0h+Reserved], r14; lpData
0x1800c7e7c  mov     r9d, ebx; dwType
0x1800c7e7f  lea     r8, aFileid; "FileId"
0x1800c7e86  mov     rdx, r15; lpSubKey
0x1800c7e89  mov     rcx, [rsp+6E0h+var_690]; hKey
0x1800c7e8e  call    cs:__imp_RegSetKeyValueW
0x1800c7e94  test    eax, eax
0x1800c7e96  jz      short loc_1800C7EB8
0x1800c7e98  mov     r8d, 58Bh
0x1800c7e9e  lea     r9, aFailedToSetPro; "Failed to set program id [%d]"
0x1800c7ea5  mov     ecx, ebx
0x1800c7ea7  mov     [rsp+6E0h+Reserved], eax
0x1800c7eab  lea     rdx, aFileSavefileto_0; "File::SaveFileToAeWerCache"
0x1800c7eb2  call    AslLogCallPrintf
0x1800c7eb7  nop
0x1800c7eb8  lea     rcx, [rsp+6E0h+var_688]
0x1800c7ebd  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800c7ec2  nop
0x1800c7ec3  lea     rcx, [rsp+6E0h+var_690]
0x1800c7ec8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c7ecd  nop
0x1800c7ece  lea     rcx, [rsp+6E0h+hKey]
0x1800c7ed3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c7ed8  mov     rcx, [rbp+5E0h+var_40]
0x1800c7edf  xor     rcx, rsp; StackCookie
0x1800c7ee2  call    __security_check_cookie
0x1800c7ee7  add     rsp, 6B0h
0x1800c7eee  pop     r15
0x1800c7ef0  pop     r14
0x1800c7ef2  pop     r12
0x1800c7ef4  pop     rdi
0x1800c7ef5  pop     rsi
0x1800c7ef6  pop     rbx
0x1800c7ef7  pop     rbp
0x1800c7ef8  retn
```
