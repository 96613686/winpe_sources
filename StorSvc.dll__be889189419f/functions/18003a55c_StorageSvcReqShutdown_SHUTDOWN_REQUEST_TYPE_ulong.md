# StorageSvcReqShutdown(SHUTDOWN_REQUEST_TYPE,ulong)

- ea: `0x18003a55c`
- end: `0x18003a61e`
- name: `?StorageSvcReqShutdown@@YAJW4SHUTDOWN_REQUEST_TYPE@@K@Z`
- size: `194`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003a4c0`

## callees

- `0x18003a55c`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a5d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a5d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a575`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a575`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a60b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a60b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5df`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18003a5a9`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18003a5a9`

## string_xrefs

- `0x18003a568`: `ShellChromeAPI.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 StorageSvcReqShutdown()
{
  HMODULE Library; // rdi
  signed int v1; // eax
  unsigned int v2; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax

  Library = LoadLibraryExW(L"ShellChromeAPI.dll", 0, 0x800u);
  if ( Library || GetLastError() == 126 && InitiateSystemShutdownExW(0, 0, 0, 1, 1, 0x80020004) )
  {
    ProcAddress = GetProcAddress(Library, "Shell_RequestShutdownEx");
    if ( ProcAddress )
    {
      v2 = 0;
      ((void (__fastcall *)(__int64, __int64))ProcAddress)(1, 106);
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( Library )
      FreeLibrary(Library);
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x18003a55c  mov     [rsp+arg_0], rbx
0x18003a561  push    rdi
0x18003a562  sub     rsp, 30h
0x18003a566  xor     edx, edx; hFile
0x18003a568  lea     rcx, aShellchromeapi; "ShellChromeAPI.dll"
0x18003a56f  mov     r8d, 800h; dwFlags
0x18003a575  call    cs:__imp_LoadLibraryExW
0x18003a57b  mov     rdi, rax
0x18003a57e  test    rax, rax
0x18003a581  jnz     short loc_18003A5CA
0x18003a583  call    cs:__imp_GetLastError
0x18003a589  cmp     eax, 7Eh ; '~'
0x18003a58c  jnz     short loc_18003A5B3
0x18003a58e  mov     [rsp+38h+dwReason], 80020004h; dwReason
0x18003a596  lea     r9d, [rdi+1]; bForceAppsClosed
0x18003a59a  xor     r8d, r8d; dwTimeout
0x18003a59d  mov     [rsp+38h+bRebootAfterShutdown], 1; bRebootAfterShutdown
0x18003a5a5  xor     edx, edx; lpMessage
0x18003a5a7  xor     ecx, ecx; lpMachineName
0x18003a5a9  call    cs:__imp_InitiateSystemShutdownExW
0x18003a5af  test    eax, eax
0x18003a5b1  jnz     short loc_18003A5CA
0x18003a5b3  call    cs:__imp_GetLastError
0x18003a5b9  mov     ebx, eax
0x18003a5bb  test    eax, eax
0x18003a5bd  jle     short loc_18003A611
0x18003a5bf  movzx   ebx, ax
0x18003a5c2  or      ebx, 80070000h
0x18003a5c8  jmp     short loc_18003A611
0x18003a5ca  lea     rdx, aShellRequestsh; "Shell_RequestShutdownEx"
0x18003a5d1  mov     rcx, rdi; hModule
0x18003a5d4  call    cs:__imp_GetProcAddress
0x18003a5da  test    rax, rax
0x18003a5dd  jnz     short loc_18003A5F6
0x18003a5df  call    cs:__imp_GetLastError
0x18003a5e5  mov     ebx, eax
0x18003a5e7  test    eax, eax
0x18003a5e9  jle     short loc_18003A603
0x18003a5eb  movzx   ebx, ax
0x18003a5ee  or      ebx, 80070000h
0x18003a5f4  jmp     short loc_18003A603
0x18003a5f6  xor     ebx, ebx
0x18003a5f8  lea     edx, [rbx+6Ah]
0x18003a5fb  lea     ecx, [rbx+1]
0x18003a5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a603  test    rdi, rdi
0x18003a606  jz      short loc_18003A611
0x18003a608  mov     rcx, rdi; hLibModule
0x18003a60b  call    cs:__imp_FreeLibrary
0x18003a611  mov     eax, ebx
0x18003a613  mov     rbx, [rsp+38h+arg_0]
0x18003a618  add     rsp, 30h
0x18003a61c  pop     rdi
0x18003a61d  retn
```
