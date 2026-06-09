# DdcDeviceInfoHelper::SLIsGenuineLocalWrapper(_GUID const *,_SL_GENUINE_STATE *,_tagSL_NONGENUINE_UI_OPTIONS *)

- ea: `0x18001ad10`
- end: `0x18001ae27`
- name: `?SLIsGenuineLocalWrapper@DdcDeviceInfoHelper@@CAJPEBU_GUID@@PEAW4_SL_GENUINE_STATE@@PEAU_tagSL_NONGENUINE_UI_OPTIONS@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(const struct _GUID *, enum _SL_GENUINE_STATE *, struct _tagSL_NONGENUINE_UI_OPTIONS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x1800050b8`
- `0x18001ad10`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ad8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ad8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ae14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ae14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ad2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ad2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad99`

## string_xrefs

- `0x18001ad6b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001ae02`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001ad1d`: `Slwga.dll`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::SLIsGenuineLocalWrapper(
        const struct _GUID *a1,
        enum _SL_GENUINE_STATE *a2,
        struct _tagSL_NONGENUINE_UI_OPTIONS *a3)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  signed int v6; // eax
  int v7; // edx
  int v8; // ecx
  signed int v9; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx

  Library = LoadLibraryExW(L"Slwga.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SLIsGenuineLocal");
    if ( ProcAddress )
    {
      v9 = ((__int64 (__fastcall *)(const GUID *, enum _SL_GENUINE_STATE *, _QWORD))ProcAddress)(&WINDOWS_SLID, a2, 0);
      if ( v9 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v15,
          v14,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          111,
          "CHR(pFunc(pAppId, pGenuineState, pUIOptions))");
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          110,
          "CBR(pFunc != nullptr)");
    }
    FreeLibrary(v5);
  }
  else
  {
    v6 = GetLastError();
    v9 = v6;
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        v9,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        107,
        "CBR(hModule != nullptr)");
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ad10  mov     [rsp+arg_0], rbx
0x18001ad15  push    rdi
0x18001ad16  sub     rsp, 30h
0x18001ad1a  mov     rbx, rdx
0x18001ad1d  lea     rcx, aSlwgaDll; "Slwga.dll"
0x18001ad24  xor     edx, edx; hFile
0x18001ad26  mov     r8d, 800h; dwFlags
0x18001ad2c  call    cs:__imp_LoadLibraryExW
0x18001ad32  mov     rdi, rax
0x18001ad35  test    rax, rax
0x18001ad38  jnz     short loc_18001AD84
0x18001ad3a  call    cs:__imp_GetLastError
0x18001ad40  mov     ebx, eax
0x18001ad42  test    eax, eax
0x18001ad44  jle     short loc_18001AD4F
0x18001ad46  movzx   ebx, ax
0x18001ad49  or      ebx, 80070000h
0x18001ad4f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ad56  jz      loc_18001AE1A
0x18001ad5c  lea     rax, aCbrHmoduleNull; "CBR(hModule != nullptr)"
0x18001ad63  mov     r8d, ebx
0x18001ad66  mov     [rsp+38h+var_10], rax
0x18001ad6b  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001ad72  mov     [rsp+38h+var_18], 66Bh
0x18001ad7a  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ad7f  jmp     loc_18001AE1A
0x18001ad84  lea     rdx, aSlisgenuineloc; "SLIsGenuineLocal"
0x18001ad8b  mov     rcx, rdi; hModule
0x18001ad8e  call    cs:__imp_GetProcAddress
0x18001ad94  test    rax, rax
0x18001ad97  jnz     short loc_18001ADCD
0x18001ad99  call    cs:__imp_GetLastError
0x18001ad9f  mov     ebx, eax
0x18001ada1  test    eax, eax
0x18001ada3  jle     short loc_18001ADAE
0x18001ada5  movzx   ebx, ax
0x18001ada8  or      ebx, 80070000h
0x18001adae  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001adb5  jz      short loc_18001AE11
0x18001adb7  lea     rax, aCbrPfuncNullpt; "CBR(pFunc != nullptr)"
0x18001adbe  mov     [rsp+38h+var_10], rax
0x18001adc3  mov     [rsp+38h+var_18], 66Eh
0x18001adcb  jmp     short loc_18001AE02
0x18001adcd  xor     r8d, r8d
0x18001add0  lea     rcx, WINDOWS_SLID
0x18001add7  mov     rdx, rbx
0x18001adda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001addf  mov     ebx, eax
0x18001ade1  test    eax, eax
0x18001ade3  jns     short loc_18001AE11
0x18001ade5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001adec  jz      short loc_18001AE11
0x18001adee  lea     rax, aChrPfuncPappid; "CHR(pFunc(pAppId, pGenuineState, pUIOpt"...
0x18001adf5  mov     [rsp+38h+var_10], rax
0x18001adfa  mov     [rsp+38h+var_18], 66Fh
0x18001ae02  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001ae09  mov     r8d, ebx
0x18001ae0c  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ae11  mov     rcx, rdi; hLibModule
0x18001ae14  call    cs:__imp_FreeLibrary
0x18001ae1a  mov     eax, ebx
0x18001ae1c  mov     rbx, [rsp+38h+arg_0]
0x18001ae21  add     rsp, 30h
0x18001ae25  pop     rdi
0x18001ae26  retn
```
