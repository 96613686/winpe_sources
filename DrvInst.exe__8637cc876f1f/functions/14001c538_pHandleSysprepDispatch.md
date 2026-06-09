# pHandleSysprepDispatch

- ea: `0x14001c538`
- end: `0x14001c5dd`
- name: `pHandleSysprepDispatch`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140009820`

## callees

- `0x14001c538`
- `0x140020f3c`
- `0x140047010`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x14001c569`
- `ntdll!DbgPrintEx` at `0x14001c569`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c5ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c5ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c5ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001c5ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001c58b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001c58b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c5b8`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001c547`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001c547`

## string_xrefs

- `0x14001c57e`: `sppnp.dll`
- `0x14001c55f`: `\nDRVINST.EXE: Entering debugger while dispatching sysprep task.`

## pseudocode

```c
__int64 __fastcall pHandleSysprepDispatch(int a1, __int64 a2, __int64 a3)
{
  DWORD v4; // ebx
  HMODULE Library; // rax
  HMODULE v6; // rdi
  __int64 (*ProcAddress)(void); // rax
  DWORD LastError; // eax

  DevRtlSetThreadLogToken(a3);
  if ( (unsigned int)DoDebugBreak(L"DebugSysprep") )
  {
    DbgPrintEx(0x23u, 0, "\nDRVINST.EXE: Entering debugger while dispatching sysprep task.");
    __debugbreak();
  }
  if ( a1 == 6 )
  {
    Library = LoadLibraryExW(L"sppnp.dll", 0, 0x800u);
    v6 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "Sysprep_Generalize_Pnp_Drivers");
      if ( ProcAddress )
        LastError = ProcAddress();
      else
        LastError = GetLastError();
      v4 = LastError;
      FreeLibrary(v6);
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x14001c538  mov     [rsp+arg_0], rbx
0x14001c53d  push    rdi
0x14001c53e  sub     rsp, 20h
0x14001c542  mov     ebx, ecx
0x14001c544  mov     rcx, r8
0x14001c547  call    cs:__imp_DevRtlSetThreadLogToken
0x14001c54d  lea     rcx, aDebugsysprep; "DebugSysprep"
0x14001c554  call    DoDebugBreak
0x14001c559  test    eax, eax
0x14001c55b  jz      short loc_14001C570
0x14001c55d  xor     edx, edx; Level
0x14001c55f  lea     r8, aDrvinstExeEnte_2; "\nDRVINST.EXE: Entering debugger while "...
0x14001c566  lea     ecx, [rdx+23h]; ComponentId
0x14001c569  call    cs:__imp_DbgPrintEx
0x14001c56f  int     3; Trap to Debugger
0x14001c570  cmp     ebx, 6
0x14001c573  jz      short loc_14001C57C
0x14001c575  mov     ebx, 57h ; 'W'
0x14001c57a  jmp     short loc_14001C5D0
0x14001c57c  xor     edx, edx; hFile
0x14001c57e  lea     rcx, aSppnpDll; "sppnp.dll"
0x14001c585  mov     r8d, 800h; dwFlags
0x14001c58b  call    cs:__imp_LoadLibraryExW
0x14001c591  mov     rdi, rax
0x14001c594  test    rax, rax
0x14001c597  jnz     short loc_14001C5A3
0x14001c599  call    cs:__imp_GetLastError
0x14001c59f  mov     ebx, eax
0x14001c5a1  jmp     short loc_14001C5D0
0x14001c5a3  lea     rdx, aSysprepGeneral; "Sysprep_Generalize_Pnp_Drivers"
0x14001c5aa  mov     rcx, rdi; hModule
0x14001c5ad  call    cs:__imp_GetProcAddress
0x14001c5b3  test    rax, rax
0x14001c5b6  jnz     short loc_14001C5C0
0x14001c5b8  call    cs:__imp_GetLastError
0x14001c5be  jmp     short loc_14001C5C5
0x14001c5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c5c5  mov     ebx, eax
0x14001c5c7  mov     rcx, rdi; hLibModule
0x14001c5ca  call    cs:__imp_FreeLibrary
0x14001c5d0  mov     eax, ebx
0x14001c5d2  mov     rbx, [rsp+28h+arg_0]
0x14001c5d7  add     rsp, 20h
0x14001c5db  pop     rdi
0x14001c5dc  retn
```
