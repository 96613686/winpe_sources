# DdcDeviceInfoHelper::QueryPhoneInformationWrapper(_PHONE_INFORMATION_KEY,ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x18001ab0c`
- end: `0x18001ac3b`
- name: `?QueryPhoneInformationWrapper@DdcDeviceInfoHelper@@CAJW4_PHONE_INFORMATION_KEY@@PEAG_KPEA_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800190fc`

## callees

- `0x1800050b8`
- `0x18001ab0c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ab92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ab92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ac23`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ac23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ab30`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ab30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab9d`

## string_xrefs

- `0x18001ab6f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001abcf`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001ab1e`: `phoneinfo.dll`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::QueryPhoneInformationWrapper(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  signed int v8; // eax
  int v9; // edx
  int v10; // ecx
  unsigned int v11; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // edx
  int v17; // ecx

  Library = LoadLibraryExW(L"phoneinfo.dll", 0, 0x800u);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "QueryPhoneInformation");
    if ( ProcAddress )
    {
      if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64, __int64))ProcAddress)(15, a2, 512, a4) )
      {
        v11 = 0;
      }
      else
      {
        v11 = -2147467259;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v17,
            v16,
            -2147467259,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            250,
            "CBR(pFunc(phoneKey, pwszPhoneInfo, phoneInfoSize, pOutputSize))");
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v15,
          v14,
          v11,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          249,
          "CBR(pFunc != nullptr)");
    }
    FreeLibrary(v7);
  }
  else
  {
    v8 = GetLastError();
    v11 = v8;
    if ( v8 > 0 )
      v11 = (unsigned __int16)v8 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        v9,
        v11,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        246,
        "CBR(hModule != nullptr)");
  }
  return v11;
}

```

## disassembly

```asm
0x18001ab0c  mov     [rsp+arg_0], rbx
0x18001ab11  mov     [rsp+arg_8], rsi
0x18001ab16  push    rdi
0x18001ab17  sub     rsp, 30h
0x18001ab1b  mov     rsi, rdx
0x18001ab1e  lea     rcx, LibFileName; "phoneinfo.dll"
0x18001ab25  xor     edx, edx; hFile
0x18001ab27  mov     r8d, 800h; dwFlags
0x18001ab2d  mov     rbx, r9
0x18001ab30  call    cs:__imp_LoadLibraryExW
0x18001ab36  mov     rdi, rax
0x18001ab39  test    rax, rax
0x18001ab3c  jnz     short loc_18001AB88
0x18001ab3e  call    cs:__imp_GetLastError
0x18001ab44  mov     ebx, eax
0x18001ab46  test    eax, eax
0x18001ab48  jle     short loc_18001AB53
0x18001ab4a  movzx   ebx, ax
0x18001ab4d  or      ebx, 80070000h
0x18001ab53  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ab5a  jz      loc_18001AC29
0x18001ab60  lea     rax, aCbrHmoduleNull; "CBR(hModule != nullptr)"
0x18001ab67  mov     r8d, ebx
0x18001ab6a  mov     [rsp+38h+var_10], rax
0x18001ab6f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001ab76  mov     [rsp+38h+var_18], 4F6h
0x18001ab7e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ab83  jmp     loc_18001AC29
0x18001ab88  lea     rdx, aQueryphoneinfo; "QueryPhoneInformation"
0x18001ab8f  mov     rcx, rdi; hModule
0x18001ab92  call    cs:__imp_GetProcAddress
0x18001ab98  test    rax, rax
0x18001ab9b  jnz     short loc_18001ABE0
0x18001ab9d  call    cs:__imp_GetLastError
0x18001aba3  mov     ebx, eax
0x18001aba5  test    eax, eax
0x18001aba7  jle     short loc_18001ABB2
0x18001aba9  movzx   ebx, ax
0x18001abac  or      ebx, 80070000h
0x18001abb2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001abb9  jz      short loc_18001AC20
0x18001abbb  lea     rax, aCbrPfuncNullpt; "CBR(pFunc != nullptr)"
0x18001abc2  mov     [rsp+38h+var_10], rax
0x18001abc7  mov     [rsp+38h+var_18], 4F9h
0x18001abcf  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001abd6  mov     r8d, ebx
0x18001abd9  call    McTemplateU0dsqs_EventWriteTransfer
0x18001abde  jmp     short loc_18001AC20
0x18001abe0  mov     r9, rbx
0x18001abe3  mov     r8d, 200h
0x18001abe9  mov     rdx, rsi
0x18001abec  mov     ecx, 0Fh
0x18001abf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abf6  test    eax, eax
0x18001abf8  jnz     short loc_18001AC1E
0x18001abfa  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ac01  mov     ebx, 80004005h
0x18001ac06  jz      short loc_18001AC20
0x18001ac08  lea     rax, aCbrPfuncPhonek; "CBR(pFunc(phoneKey, pwszPhoneInfo, phon"...
0x18001ac0f  mov     [rsp+38h+var_10], rax
0x18001ac14  mov     [rsp+38h+var_18], 4FAh
0x18001ac1c  jmp     short loc_18001ABCF
0x18001ac1e  xor     ebx, ebx
0x18001ac20  mov     rcx, rdi; hLibModule
0x18001ac23  call    cs:__imp_FreeLibrary
0x18001ac29  mov     rsi, [rsp+38h+arg_8]
0x18001ac2e  mov     eax, ebx
0x18001ac30  mov     rbx, [rsp+38h+arg_0]
0x18001ac35  add     rsp, 30h
0x18001ac39  pop     rdi
0x18001ac3a  retn
```
