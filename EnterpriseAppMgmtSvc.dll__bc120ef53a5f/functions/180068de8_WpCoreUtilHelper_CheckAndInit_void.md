# WpCoreUtilHelper::CheckAndInit(void)

- ea: `0x180068de8`
- end: `0x180068f7b`
- name: `?CheckAndInit@WpCoreUtilHelper@@AEAAJXZ`
- size: `403`
- prototype: `__int64 __fastcall(WpCoreUtilHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800166d8`

## callees

- `0x180068de8`
- `0x180068f84`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180068e10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180068e10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068e5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068e88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068eb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068ed8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068efe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068f24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068e5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068e88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068eb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068ed8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068efe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068f24`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180068e33`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180068e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068f3c`

## string_xrefs

- `0x180068e03`: `wpcoreutil.dll`
- `0x180068e54`: `CreateStreamOnFile`
- `0x180068f1d`: `MoveFileInheritSecurityW`

## pseudocode

```c
__int64 __fastcall WpCoreUtilHelper::CheckAndInit(WpCoreUtilHelper *this)
{
  signed int v1; // ebx
  HMODULE Library; // rbx
  signed int LastError; // eax

  if ( byte_180096CF8 )
  {
    return 1;
  }
  else
  {
    Library = LoadLibraryExW(L"wpcoreutil.dll", 0, 0x800u);
    if ( Library == s_WpCoreUtilHelper )
    {
      Library = s_WpCoreUtilHelper;
    }
    else
    {
      if ( s_WpCoreUtilHelper )
        FreeLibrary(s_WpCoreUtilHelper);
      s_WpCoreUtilHelper = Library;
    }
    if ( !Library
      || (qword_180096D00 = (__int64)GetProcAddress(Library, "CreateStreamOnFile")) != 0
      && (qword_180096D08 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetAppStorageFolder")) != 0
      && (qword_180096D10 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetStorageDeviceInfo")) != 0
      && (qword_180096D18 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetStorageSettings")) != 0
      && (qword_180096D20 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetStorageStateName")) != 0
      && (qword_180096D28 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "MoveFileInheritSecurityW")) != 0 )
    {
      v1 = 0;
      byte_180096CF8 = 1;
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 < 0 )
        WpCoreUtilHelper::Uninitialize((WpCoreUtilHelper *)&s_WpCoreUtilHelper);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180068de8  push    rbx
0x180068dea  sub     rsp, 20h
0x180068dee  cmp     cs:byte_180096CF8, 0
0x180068df5  jz      short loc_180068E01
0x180068df7  mov     ebx, 1
0x180068dfc  jmp     loc_180068F72
0x180068e01  xor     edx, edx; hFile
0x180068e03  lea     rcx, aWpcoreutilDll; "wpcoreutil.dll"
0x180068e0a  mov     r8d, 800h; dwFlags
0x180068e10  call    cs:__imp_LoadLibraryExW
0x180068e17  nop     dword ptr [rax+rax+00h]
0x180068e1c  mov     rbx, rax
0x180068e1f  mov     rax, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; WpCoreUtilHelper s_WpCoreUtilHelper
0x180068e26  cmp     rbx, rax
0x180068e29  jz      short loc_180068E48
0x180068e2b  test    rax, rax
0x180068e2e  jz      short loc_180068E3F
0x180068e30  mov     rcx, rax; hLibModule
0x180068e33  call    cs:__imp_FreeLibrary
0x180068e3a  nop     dword ptr [rax+rax+00h]
0x180068e3f  mov     cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A, rbx; WpCoreUtilHelper s_WpCoreUtilHelper
0x180068e46  jmp     short loc_180068E4B
0x180068e48  mov     rbx, rax
0x180068e4b  test    rbx, rbx
0x180068e4e  jz      loc_180068F69
0x180068e54  lea     rdx, aCreatestreamon; "CreateStreamOnFile"
0x180068e5b  mov     rcx, rbx; hModule
0x180068e5e  call    cs:__imp_GetProcAddress
0x180068e65  nop     dword ptr [rax+rax+00h]
0x180068e6a  mov     cs:qword_180096D00, rax
0x180068e71  test    rax, rax
0x180068e74  jz      loc_180068F3C
0x180068e7a  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x180068e81  lea     rdx, aGetappstoragef; "GetAppStorageFolder"
0x180068e88  call    cs:__imp_GetProcAddress
0x180068e8f  nop     dword ptr [rax+rax+00h]
0x180068e94  mov     cs:qword_180096D08, rax
0x180068e9b  test    rax, rax
0x180068e9e  jz      loc_180068F3C
0x180068ea4  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x180068eab  lea     rdx, aGetstoragedevi; "GetStorageDeviceInfo"
0x180068eb2  call    cs:__imp_GetProcAddress
0x180068eb9  nop     dword ptr [rax+rax+00h]
0x180068ebe  mov     cs:qword_180096D10, rax
0x180068ec5  test    rax, rax
0x180068ec8  jz      short loc_180068F3C
0x180068eca  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x180068ed1  lea     rdx, aGetstoragesett; "GetStorageSettings"
0x180068ed8  call    cs:__imp_GetProcAddress
0x180068edf  nop     dword ptr [rax+rax+00h]
0x180068ee4  mov     cs:qword_180096D18, rax
0x180068eeb  test    rax, rax
0x180068eee  jz      short loc_180068F3C
0x180068ef0  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x180068ef7  lea     rdx, aGetstoragestat; "GetStorageStateName"
0x180068efe  call    cs:__imp_GetProcAddress
0x180068f05  nop     dword ptr [rax+rax+00h]
0x180068f0a  mov     cs:qword_180096D20, rax
0x180068f11  test    rax, rax
0x180068f14  jz      short loc_180068F3C
0x180068f16  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x180068f1d  lea     rdx, aMovefileinheri; "MoveFileInheritSecurityW"
0x180068f24  call    cs:__imp_GetProcAddress
0x180068f2b  nop     dword ptr [rax+rax+00h]
0x180068f30  mov     cs:qword_180096D28, rax
0x180068f37  test    rax, rax
0x180068f3a  jnz     short loc_180068F69
0x180068f3c  call    cs:__imp_GetLastError
0x180068f43  nop     dword ptr [rax+rax+00h]
0x180068f48  mov     ebx, eax
0x180068f4a  test    eax, eax
0x180068f4c  jle     short loc_180068F57
0x180068f4e  movzx   ebx, ax
0x180068f51  or      ebx, 80070000h
0x180068f57  test    ebx, ebx
0x180068f59  jns     short loc_180068F72
0x180068f5b  lea     rcx, ?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; this
0x180068f62  call    ?Uninitialize@WpCoreUtilHelper@@AEAAXXZ; WpCoreUtilHelper::Uninitialize(void)
0x180068f67  jmp     short loc_180068F72
0x180068f69  xor     ebx, ebx
0x180068f6b  mov     cs:byte_180096CF8, 1
0x180068f72  mov     eax, ebx
0x180068f74  add     rsp, 20h
0x180068f78  pop     rbx
0x180068f79  retn
```
