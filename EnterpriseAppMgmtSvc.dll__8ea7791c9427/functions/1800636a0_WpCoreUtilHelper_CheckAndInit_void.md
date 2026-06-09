# WpCoreUtilHelper::CheckAndInit(void)

- ea: `0x1800636a0`
- end: `0x1800637fc`
- name: `?CheckAndInit@WpCoreUtilHelper@@AEAAJXZ`
- size: `348`
- prototype: `__int64 __fastcall(WpCoreUtilHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800159a4`

## callees

- `0x1800636a0`
- `0x180063804`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800636c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800636c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006370a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006372e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063752`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063772`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063792`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800637b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006370a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006372e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063752`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063772`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063792`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800637b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800636e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800636e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800637c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800637c4`

## string_xrefs

- `0x1800636bb`: `wpcoreutil.dll`
- `0x180063700`: `CreateStreamOnFile`
- `0x1800637ab`: `MoveFileInheritSecurityW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WpCoreUtilHelper::CheckAndInit(WpCoreUtilHelper *this)
{
  signed int v1; // ebx
  HMODULE Library; // rbx
  signed int LastError; // eax

  if ( byte_180090CF8 )
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
      || (qword_180090D00 = (__int64)GetProcAddress(Library, "CreateStreamOnFile")) != 0
      && (qword_180090D08 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetAppStorageFolder")) != 0
      && (qword_180090D10 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetStorageDeviceInfo")) != 0
      && (qword_180090D18 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetStorageSettings")) != 0
      && (qword_180090D20 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "GetStorageStateName")) != 0
      && (qword_180090D28 = (__int64)GetProcAddress(s_WpCoreUtilHelper, "MoveFileInheritSecurityW")) != 0 )
    {
      v1 = 0;
      byte_180090CF8 = 1;
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
0x1800636a0  push    rbx
0x1800636a2  sub     rsp, 20h
0x1800636a6  cmp     cs:byte_180090CF8, 0
0x1800636ad  jz      short loc_1800636B9
0x1800636af  mov     ebx, 1
0x1800636b4  jmp     loc_1800637F4
0x1800636b9  xor     edx, edx; hFile
0x1800636bb  lea     rcx, aWpcoreutilDll; "wpcoreutil.dll"
0x1800636c2  mov     r8d, 800h; dwFlags
0x1800636c8  call    cs:__imp_LoadLibraryExW
0x1800636ce  mov     rbx, rax
0x1800636d1  mov     rax, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; WpCoreUtilHelper s_WpCoreUtilHelper
0x1800636d8  cmp     rbx, rax
0x1800636db  jz      short loc_1800636F4
0x1800636dd  test    rax, rax
0x1800636e0  jz      short loc_1800636EB
0x1800636e2  mov     rcx, rax; hLibModule
0x1800636e5  call    cs:__imp_FreeLibrary
0x1800636eb  mov     cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A, rbx; WpCoreUtilHelper s_WpCoreUtilHelper
0x1800636f2  jmp     short loc_1800636F7
0x1800636f4  mov     rbx, rax
0x1800636f7  test    rbx, rbx
0x1800636fa  jz      loc_1800637EB
0x180063700  lea     rdx, aCreatestreamon; "CreateStreamOnFile"
0x180063707  mov     rcx, rbx; hModule
0x18006370a  call    cs:__imp_GetProcAddress
0x180063710  mov     cs:qword_180090D00, rax
0x180063717  test    rax, rax
0x18006371a  jz      loc_1800637C4
0x180063720  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x180063727  lea     rdx, aGetappstoragef; "GetAppStorageFolder"
0x18006372e  call    cs:__imp_GetProcAddress
0x180063734  mov     cs:qword_180090D08, rax
0x18006373b  test    rax, rax
0x18006373e  jz      loc_1800637C4
0x180063744  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x18006374b  lea     rdx, aGetstoragedevi; "GetStorageDeviceInfo"
0x180063752  call    cs:__imp_GetProcAddress
0x180063758  mov     cs:qword_180090D10, rax
0x18006375f  test    rax, rax
0x180063762  jz      short loc_1800637C4
0x180063764  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x18006376b  lea     rdx, aGetstoragesett; "GetStorageSettings"
0x180063772  call    cs:__imp_GetProcAddress
0x180063778  mov     cs:qword_180090D18, rax
0x18006377f  test    rax, rax
0x180063782  jz      short loc_1800637C4
0x180063784  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x18006378b  lea     rdx, aGetstoragestat; "GetStorageStateName"
0x180063792  call    cs:__imp_GetProcAddress
0x180063798  mov     cs:qword_180090D20, rax
0x18006379f  test    rax, rax
0x1800637a2  jz      short loc_1800637C4
0x1800637a4  mov     rcx, cs:?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; hModule
0x1800637ab  lea     rdx, aMovefileinheri; "MoveFileInheritSecurityW"
0x1800637b2  call    cs:__imp_GetProcAddress
0x1800637b8  mov     cs:qword_180090D28, rax
0x1800637bf  test    rax, rax
0x1800637c2  jnz     short loc_1800637EB
0x1800637c4  call    cs:__imp_GetLastError
0x1800637ca  mov     ebx, eax
0x1800637cc  test    eax, eax
0x1800637ce  jle     short loc_1800637D9
0x1800637d0  movzx   ebx, ax
0x1800637d3  or      ebx, 80070000h
0x1800637d9  test    ebx, ebx
0x1800637db  jns     short loc_1800637F4
0x1800637dd  lea     rcx, ?s_WpCoreUtilHelper@@3VWpCoreUtilHelper@@A; this
0x1800637e4  call    ?Uninitialize@WpCoreUtilHelper@@AEAAXXZ; WpCoreUtilHelper::Uninitialize(void)
0x1800637e9  jmp     short loc_1800637F4
0x1800637eb  xor     ebx, ebx
0x1800637ed  mov     cs:byte_180090CF8, 1
0x1800637f4  mov     eax, ebx
0x1800637f6  add     rsp, 20h
0x1800637fa  pop     rbx
0x1800637fb  retn
```
