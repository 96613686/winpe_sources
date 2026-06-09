# File::SaveFileToAeWerCache(ushort const *,ushort const *,ushort const *)

- ea: `0x18004fcd0`
- end: `0x180050029`
- name: `?SaveFileToAeWerCache@File@@CAXPEBG00@Z`
- size: `857`
- prototype: `void __fastcall(LPCWSTR lpSubKey, LPCVOID lpData, LPCVOID)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004fb1c`

## callees

- `0x180015eec`
- `0x1800197d4`
- `0x18004826c`
- `0x1800487ac`
- `0x18004fcd0`
- `0x180050030`
- `0x18005005c`
- `0x180059920`
- `0x18005a8bc`
- `0x180130010`

## import_xrefs

- `ADVAPI32!RegLoadAppKeyW` at `0x18004fea9`
- `ADVAPI32!RegLoadAppKeyW` at `0x18004fea9`
- `ADVAPI32!RegCreateKeyExW` at `0x18004ff3d`
- `ADVAPI32!RegCreateKeyExW` at `0x18004ff3d`
- `ADVAPI32!RegSetKeyValueW` at `0x18004ff84`
- `ADVAPI32!RegSetKeyValueW` at `0x18004ffbe`
- `ADVAPI32!RegSetKeyValueW` at `0x18004ff84`
- `ADVAPI32!RegSetKeyValueW` at `0x18004ffbe`
- `ADVAPI32!RegCloseKey` at `0x18004fe7a`
- `ADVAPI32!RegCloseKey` at `0x18004fef5`
- `ADVAPI32!RegCloseKey` at `0x18004fe7a`
- `ADVAPI32!RegCloseKey` at `0x18004fef5`
- `KERNEL32!LoadLibraryExW` at `0x18004fda4`
- `KERNEL32!LoadLibraryExW` at `0x18004fda4`
- `KERNEL32!GetProcAddress` at `0x18004fddb`
- `KERNEL32!GetProcAddress` at `0x18004fddb`
- `KERNEL32!GetLastError` at `0x18004fdb4`
- `KERNEL32!GetLastError` at `0x18004fdb4`

## string_xrefs

- `0x18004fd9d`: `ntdll.dll`
- `0x18004fdba`: `LoadLibraryEx for ntdll.dll failed [%d]`
- `0x18004fd7f`: `File::SaveFileToAeWerCache`
- `0x18004ffdb`: `File::SaveFileToAeWerCache`
- `0x18004ff47`: `Failed to open file key [%d]`
- `0x18004fd72`: `StringCchPrintf for appCompatDirectory [%#x]`
- `0x18004fd55`: `%s\appcompat`
- `0x18004fe29`: `Amcache.hve`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall File::SaveFileToAeWerCache(LPCWSTR lpSubKey, _WORD *lpData, _WORD *a3)
{
  HMODULE Library; // rax
  const char *v7; // r9
  int v8; // r8d
  int v9; // ecx
  FARPROC ProcAddress; // rax
  unsigned __int16 *v11; // r9
  LSTATUS AppKeyW; // eax
  __int64 v13; // rdi
  __int64 v14; // rax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HMODULE v16; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v18[264]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v19[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR File[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  hKey[2] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  memset_0(v19, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  memset_0(File, 0, 0x208u);
  hKey[0] = 0;
  phkResult = 0;
  if ( (int)StringCchPrintfW(v18, 0x104u, L"%s\\appcompat", 2147352624) >= 0 )
  {
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v16 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
      if ( ProcAddress )
        ((void (__fastcall *)(unsigned __int16 *, _QWORD, unsigned __int16 *, __int64, _WORD *, int, _QWORD))ProcAddress)(
          v18,
          0,
          v18,
          1,
          v19,
          520,
          0);
      v11 = v19;
      if ( !v19[0] )
        v11 = v18;
      if ( (int)StringCchPrintfW(File, 0x104u, L"%ls\\programs\\%ls", v11, L"Amcache.hve") >= 0 )
      {
        hKey[0] = 0;
        AppKeyW = RegLoadAppKeyW(File, hKey, 0xF003Fu, 0, 0);
        if ( AppKeyW )
        {
          if ( AppKeyW == 5 || AppKeyW == 2 )
          {
            v8 = 1390;
            v9 = 3;
          }
          else
          {
            v8 = 1394;
            v9 = 1;
          }
          v7 = "RegLoadAppKey failed [%d]";
          goto LABEL_28;
        }
        phkResult = 0;
        if ( RegCreateKeyExW(hKey[0], L"Root\\InventoryApplicationFile", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0) )
        {
          v7 = "Failed to open file key [%d]";
          v8 = 1403;
        }
        else
        {
          v13 = -1;
          v14 = -1;
          do
            ++v14;
          while ( lpData[v14] );
          if ( RegSetKeyValueW(phkResult, lpSubKey, L"ProgramId", 1u, lpData, 2 * v14) )
          {
            v8 = 1411;
          }
          else
          {
            do
              ++v13;
            while ( a3[v13] );
            if ( !RegSetKeyValueW(phkResult, lpSubKey, L"FileId", 1u, a3, 2 * v13) )
              goto LABEL_29;
            v8 = 1419;
          }
          v7 = "Failed to set program id [%d]";
        }
      }
      else
      {
        v7 = "StringCchPrintf [%#x]";
        v8 = 1381;
      }
      v9 = 1;
    }
    else
    {
      GetLastError();
      v7 = "LoadLibraryEx for ntdll.dll failed [%d]";
      v8 = 1356;
      v9 = 1;
    }
LABEL_28:
    AslLogCallPrintf(v9, (unsigned int)"File::SaveFileToAeWerCache", v8, (_DWORD)v7);
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v16);
    goto LABEL_30;
  }
  AslLogCallPrintf(
    1,
    (unsigned int)"File::SaveFileToAeWerCache",
    1349,
    (unsigned int)"StringCchPrintf for appCompatDirectory [%#x]");
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
}

```

## disassembly

```asm
0x18004fcd0  push    rbp
0x18004fcd2  push    rbx
0x18004fcd3  push    rsi
0x18004fcd4  push    rdi
0x18004fcd5  push    r12
0x18004fcd7  push    r14
0x18004fcd9  push    r15
0x18004fcdb  lea     rbp, [rsp-5C0h]
0x18004fce3  sub     rsp, 6C0h
0x18004fcea  mov     [rsp+6F0h+var_680], 0FFFFFFFFFFFFFFFEh
0x18004fcf3  mov     rax, cs:__security_cookie
0x18004fcfa  xor     rax, rsp
0x18004fcfd  mov     [rbp+5F0h+var_40], rax
0x18004fd04  mov     r14, r8
0x18004fd07  mov     rsi, rdx
0x18004fd0a  mov     r15, rcx
0x18004fd0d  mov     edi, 208h
0x18004fd12  mov     r8d, edi; Size
0x18004fd15  xor     edx, edx; Val
0x18004fd17  lea     rcx, [rbp+5F0h+var_460]; void *
0x18004fd1e  call    memset_0
0x18004fd23  mov     r8d, edi; Size
0x18004fd26  xor     edx, edx; Val
0x18004fd28  lea     rcx, [rbp+5F0h+var_670]; void *
0x18004fd2c  call    memset_0
0x18004fd31  mov     r8d, edi; Size
0x18004fd34  xor     edx, edx; Val
0x18004fd36  lea     rcx, [rbp+5F0h+File]; void *
0x18004fd3d  call    memset_0
0x18004fd42  xor     r12d, r12d
0x18004fd45  mov     [rsp+6F0h+hKey], r12
0x18004fd4a  mov     [rsp+6F0h+var_6A0], r12
0x18004fd4f  mov     r9d, 7FFE0030h
0x18004fd55  lea     r8, aSAppcompat; "%s\\appcompat"
0x18004fd5c  mov     edx, 104h; unsigned __int64
0x18004fd61  lea     rcx, [rbp+5F0h+var_670]; unsigned __int16 *
0x18004fd65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fd6a  test    eax, eax
0x18004fd6c  jns     short loc_18004FD95
0x18004fd6e  mov     [rsp+6F0h+Reserved], eax
0x18004fd72  lea     r9, aStringcchprint_3; "StringCchPrintf for appCompatDirectory "...
0x18004fd79  mov     r8d, 545h
0x18004fd7f  lea     rdx, aFileSavefileto_0; "File::SaveFileToAeWerCache"
0x18004fd86  lea     ecx, [r12+1]
0x18004fd8b  call    AslLogCallPrintf
0x18004fd90  jmp     loc_18004FFF3
0x18004fd95  xor     edx, edx; hFile
0x18004fd97  mov     r8d, 800h; dwFlags
0x18004fd9d  lea     rcx, LibFileName; "ntdll.dll"
0x18004fda4  call    cs:__imp_LoadLibraryExW
0x18004fdaa  mov     [rsp+6F0h+var_698], rax
0x18004fdaf  test    rax, rax
0x18004fdb2  jnz     short loc_18004FDD1
0x18004fdb4  call    cs:__imp_GetLastError
0x18004fdba  lea     r9, aLoadlibraryexF; "LoadLibraryEx for ntdll.dll failed [%d]"
0x18004fdc1  mov     r8d, 54Ch
0x18004fdc7  mov     ecx, 1
0x18004fdcc  jmp     loc_18004FFD7
0x18004fdd1  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18004fdd8  mov     rcx, rax; hModule
0x18004fddb  call    cs:__imp_GetProcAddress
0x18004fde1  mov     ebx, 1
0x18004fde6  test    rax, rax
0x18004fde9  jz      short loc_18004FE12
0x18004fdeb  mov     [rsp+6F0h+lpSecurityAttributes], r12
0x18004fdf0  mov     [rsp+6F0h+samDesired], edi
0x18004fdf4  lea     rcx, [rbp+5F0h+var_460]
0x18004fdfb  mov     qword ptr [rsp+6F0h+Reserved], rcx
0x18004fe00  mov     r9d, ebx
0x18004fe03  lea     r8, [rbp+5F0h+var_670]
0x18004fe07  xor     edx, edx
0x18004fe09  lea     rcx, [rbp+5F0h+var_670]
0x18004fe0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe12  lea     r9, [rbp+5F0h+var_460]
0x18004fe19  lea     rax, [rbp+5F0h+var_670]
0x18004fe1d  cmp     [rbp+5F0h+var_460], r12w
0x18004fe25  cmovz   r9, rax
0x18004fe29  lea     rax, aAmcacheHve; "Amcache.hve"
0x18004fe30  mov     qword ptr [rsp+6F0h+Reserved], rax
0x18004fe35  lea     r8, aLsProgramsLs; "%ls\\programs\\%ls"
0x18004fe3c  mov     edx, 104h; unsigned __int64
0x18004fe41  lea     rcx, [rbp+5F0h+File]; unsigned __int16 *
0x18004fe48  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fe4d  test    eax, eax
0x18004fe4f  jns     short loc_18004FE63
0x18004fe51  lea     r9, aStringcchprint_2; "StringCchPrintf [%#x]"
0x18004fe58  mov     r8d, 565h
0x18004fe5e  jmp     loc_18004FFD5
0x18004fe63  mov     rdi, [rsp+6F0h+hKey]
0x18004fe68  test    rdi, rdi
0x18004fe6b  jz      short loc_18004FE8A
0x18004fe6d  lea     rcx, [rsp+6F0h+var_688]; this
0x18004fe72  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004fe77  mov     rcx, rdi; hKey
0x18004fe7a  call    cs:__imp_RegCloseKey
0x18004fe80  lea     rcx, [rsp+6F0h+var_688]; this
0x18004fe85  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004fe8a  mov     [rsp+6F0h+hKey], r12
0x18004fe8f  mov     [rsp+6F0h+Reserved], r12d; Reserved
0x18004fe94  xor     r9d, r9d; dwOptions
0x18004fe97  mov     r8d, 0F003Fh; samDesired
0x18004fe9d  lea     rdx, [rsp+6F0h+hKey]; phkResult
0x18004fea2  lea     rcx, [rbp+5F0h+File]; lpFile
0x18004fea9  call    cs:__imp_RegLoadAppKeyW
0x18004feaf  test    eax, eax
0x18004feb1  jz      short loc_18004FEDE
0x18004feb3  cmp     eax, 5
0x18004feb6  jz      short loc_18004FEC7
0x18004feb8  cmp     eax, 2
0x18004febb  jz      short loc_18004FEC7
0x18004febd  mov     r8d, 572h
0x18004fec3  mov     ecx, ebx
0x18004fec5  jmp     short loc_18004FED2
0x18004fec7  mov     r8d, 56Eh
0x18004fecd  mov     ecx, 3
0x18004fed2  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x18004fed9  jmp     loc_18004FFD7
0x18004fede  mov     rdi, [rsp+6F0h+var_6A0]
0x18004fee3  test    rdi, rdi
0x18004fee6  jz      short loc_18004FF05
0x18004fee8  lea     rcx, [rsp+6F0h+var_688]; this
0x18004feed  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004fef2  mov     rcx, rdi; hKey
0x18004fef5  call    cs:__imp_RegCloseKey
0x18004fefb  lea     rcx, [rsp+6F0h+var_688]; this
0x18004ff00  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004ff05  mov     [rsp+6F0h+var_6A0], r12
0x18004ff0a  mov     [rsp+6F0h+lpdwDisposition], r12; lpdwDisposition
0x18004ff0f  lea     rax, [rsp+6F0h+var_6A0]
0x18004ff14  mov     [rsp+6F0h+phkResult], rax; phkResult
0x18004ff19  mov     [rsp+6F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18004ff1e  mov     [rsp+6F0h+samDesired], 0F003Fh; samDesired
0x18004ff26  mov     [rsp+6F0h+Reserved], r12d; dwOptions
0x18004ff2b  xor     r9d, r9d; lpClass
0x18004ff2e  xor     r8d, r8d; Reserved
0x18004ff31  lea     rdx, aRootInventorya; "Root\\InventoryApplicationFile"
0x18004ff38  mov     rcx, [rsp+6F0h+hKey]; hKey
0x18004ff3d  call    cs:__imp_RegCreateKeyExW
0x18004ff43  test    eax, eax
0x18004ff45  jz      short loc_18004FF56
0x18004ff47  lea     r9, aFailedToOpenFi_0; "Failed to open file key [%d]"
0x18004ff4e  mov     r8d, 57Bh
0x18004ff54  jmp     short loc_18004FFD5
0x18004ff56  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004ff5a  mov     rax, rdi
0x18004ff5d  inc     rax
0x18004ff60  cmp     [rsi+rax*2], r12w
0x18004ff65  jnz     short loc_18004FF5D
0x18004ff67  add     eax, eax
0x18004ff69  mov     [rsp+6F0h+samDesired], eax; cbData
0x18004ff6d  mov     qword ptr [rsp+6F0h+Reserved], rsi; lpData
0x18004ff72  mov     r9d, ebx; dwType
0x18004ff75  lea     r8, ValueName; "ProgramId"
0x18004ff7c  mov     rdx, r15; lpSubKey
0x18004ff7f  mov     rcx, [rsp+6F0h+var_6A0]; hKey
0x18004ff84  call    cs:__imp_RegSetKeyValueW
0x18004ff8a  test    eax, eax
0x18004ff8c  jz      short loc_18004FF96
0x18004ff8e  mov     r8d, 583h
0x18004ff94  jmp     short loc_18004FFCE
0x18004ff96  inc     rdi
0x18004ff99  cmp     [r14+rdi*2], r12w
0x18004ff9e  jnz     short loc_18004FF96
0x18004ffa0  lea     eax, [rdi+rdi]
0x18004ffa3  mov     [rsp+6F0h+samDesired], eax; cbData
0x18004ffa7  mov     qword ptr [rsp+6F0h+Reserved], r14; lpData
0x18004ffac  mov     r9d, ebx; dwType
0x18004ffaf  lea     r8, aFileid_0; "FileId"
0x18004ffb6  mov     rdx, r15; lpSubKey
0x18004ffb9  mov     rcx, [rsp+6F0h+var_6A0]; hKey
0x18004ffbe  call    cs:__imp_RegSetKeyValueW
0x18004ffc4  test    eax, eax
0x18004ffc6  jz      short loc_18004FFE8
0x18004ffc8  mov     r8d, 58Bh
0x18004ffce  lea     r9, aFailedToSetPro; "Failed to set program id [%d]"
0x18004ffd5  mov     ecx, ebx
0x18004ffd7  mov     [rsp+6F0h+Reserved], eax
0x18004ffdb  lea     rdx, aFileSavefileto_0; "File::SaveFileToAeWerCache"
0x18004ffe2  call    AslLogCallPrintf
0x18004ffe7  nop
0x18004ffe8  lea     rcx, [rsp+6F0h+var_698]
0x18004ffed  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18004fff2  nop
0x18004fff3  lea     rcx, [rsp+6F0h+var_6A0]
0x18004fff8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004fffd  nop
0x18004fffe  lea     rcx, [rsp+6F0h+hKey]
0x180050003  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050008  mov     rcx, [rbp+5F0h+var_40]
0x18005000f  xor     rcx, rsp; StackCookie
0x180050012  call    __security_check_cookie
0x180050017  add     rsp, 6C0h
0x18005001e  pop     r15
0x180050020  pop     r14
0x180050022  pop     r12
0x180050024  pop     rdi
0x180050025  pop     rsi
0x180050026  pop     rbx
0x180050027  pop     rbp
0x180050028  retn
```
