# CVmSessionManager::LoadRdvVmTransport(void)

- ea: `0x180035a5c`
- end: `0x180035b39`
- name: `?LoadRdvVmTransport@CVmSessionManager@@AEAAJXZ`
- size: `221`
- prototype: `__int64 __fastcall(CVmSessionManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800358f0`

## callees

- `0x180003f30`
- `0x180035a5c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035a7a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035a7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035abf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035acd`

## string_xrefs

- `0x180035a71`: `RdvVmTransport.dll`
- `0x180035aa8`: `LoadLibrary failed: 0x%x in %s`
- `0x180035ab8`: `RdvTransport_CreateInstance`
- `0x180035b0f`: `RdvTransport_CreateInstance failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CVmSessionManager::LoadRdvVmTransport(CVmSessionManager *this)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  FARPROC ProcAddress; // rdi
  signed int v6; // eax
  int v7; // eax

  Library = LoadLibraryExW(L"RdvVmTransport.dll", 0, 0);
  *((_QWORD *)this + 200) = Library;
  if ( Library )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_6:
    ProcAddress = GetProcAddress(*((HMODULE *)this + 200), "RdvTransport_CreateInstance");
    if ( ProcAddress )
      goto LABEL_11;
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_11:
      v7 = ((__int64 (__fastcall *)(__int64, char *))ProcAddress)(1, (char *)this + 1592);
      v4 = v7;
      if ( v7 < 0 )
        _DbgPrintMessage(
          8,
          "RdvTransport_CreateInstance failed: 0x%x in %s",
          (unsigned int)v7,
          "CVmSessionManager::LoadRdvVmTransport");
    }
    else
    {
      _DbgPrintMessage(
        8,
        "GetProcAddress failed: 0x%x in %s",
        (unsigned int)v4,
        "CVmSessionManager::LoadRdvVmTransport");
    }
  }
  else
  {
    _DbgPrintMessage(8, "LoadLibrary failed: 0x%x in %s", (unsigned int)v4, "CVmSessionManager::LoadRdvVmTransport");
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180035a5c  mov     [rsp+arg_0], rbx
0x180035a61  mov     [rsp+arg_8], rsi
0x180035a66  push    rdi
0x180035a67  sub     rsp, 20h
0x180035a6b  mov     rsi, rcx
0x180035a6e  xor     r8d, r8d; dwFlags
0x180035a71  lea     rcx, LibFileName; "RdvVmTransport.dll"
0x180035a78  xor     edx, edx; hFile
0x180035a7a  call    cs:__imp_LoadLibraryExW
0x180035a80  mov     [rsi+640h], rax
0x180035a87  test    rax, rax
0x180035a8a  jnz     short loc_180035AB1
0x180035a8c  call    cs:__imp_GetLastError
0x180035a92  mov     ebx, eax
0x180035a94  test    eax, eax
0x180035a96  jle     short loc_180035AA1
0x180035a98  movzx   ebx, ax
0x180035a9b  or      ebx, 80070000h
0x180035aa1  test    ebx, ebx
0x180035aa3  jns     short loc_180035AB1
0x180035aa5  mov     r8d, ebx
0x180035aa8  lea     rdx, aLoadlibraryFai; "LoadLibrary failed: 0x%x in %s"
0x180035aaf  jmp     short loc_180035B16
0x180035ab1  mov     rcx, [rsi+640h]; hModule
0x180035ab8  lea     rdx, aRdvtransportCr; "RdvTransport_CreateInstance"
0x180035abf  call    cs:__imp_GetProcAddress
0x180035ac5  mov     rdi, rax
0x180035ac8  test    rax, rax
0x180035acb  jnz     short loc_180035AF2
0x180035acd  call    cs:__imp_GetLastError
0x180035ad3  mov     ebx, eax
0x180035ad5  test    eax, eax
0x180035ad7  jle     short loc_180035AE2
0x180035ad9  movzx   ebx, ax
0x180035adc  or      ebx, 80070000h
0x180035ae2  test    ebx, ebx
0x180035ae4  jns     short loc_180035AF2
0x180035ae6  mov     r8d, ebx
0x180035ae9  lea     rdx, aGetprocaddress; "GetProcAddress failed: 0x%x in %s"
0x180035af0  jmp     short loc_180035B16
0x180035af2  lea     rdx, [rsi+638h]
0x180035af9  mov     ecx, 1
0x180035afe  mov     rax, rdi
0x180035b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b06  mov     ebx, eax
0x180035b08  test    eax, eax
0x180035b0a  jns     short loc_180035B27
0x180035b0c  mov     r8d, eax
0x180035b0f  lea     rdx, aRdvtransportCr_0; "RdvTransport_CreateInstance failed: 0x%"...
0x180035b16  lea     r9, aCvmsessionmana; "CVmSessionManager::LoadRdvVmTransport"
0x180035b1d  mov     ecx, 8; int
0x180035b22  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180035b27  mov     rsi, [rsp+28h+arg_8]
0x180035b2c  mov     eax, ebx
0x180035b2e  mov     rbx, [rsp+28h+arg_0]
0x180035b33  add     rsp, 20h
0x180035b37  pop     rdi
0x180035b38  retn
```
