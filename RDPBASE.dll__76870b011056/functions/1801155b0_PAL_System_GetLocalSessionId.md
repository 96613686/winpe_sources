# PAL_System_GetLocalSessionId

- ea: `0x1801155b0`
- end: `0x18011562f`
- name: `PAL_System_GetLocalSessionId`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180113b6c`
- `0x1801155b0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801155e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801155e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180115616`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180115616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801155fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801155fe`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801155ca`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801155ca`

## string_xrefs

- `0x1801155bf`: `KERNEL32.DLL`
- `0x1801155d8`: `ProcessIdToSessionId`

## pseudocode

```c
__int64 __fastcall PAL_System_GetLocalSessionId(_DWORD *a1)
{
  unsigned int v2; // edi
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rsi
  DWORD CurrentProcessId; // eax
  __int64 result; // rax
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v8 = 0;
  LibraryW = LoadLibraryW(L"KERNEL32.DLL");
  v4 = LibraryW;
  if ( LibraryW )
  {
    v2 = 1;
    ProcAddress = GetProcAddress(LibraryW, "ProcessIdToSessionId");
    if ( ProcAddress && (unsigned int)PAL_System_Win32_IsTSOnWin2KOrGreater() )
    {
      CurrentProcessId = GetCurrentProcessId();
      ((void (__fastcall *)(_QWORD, int *))ProcAddress)(CurrentProcessId, &v8);
    }
    FreeLibrary(v4);
  }
  result = v2;
  *a1 = v8;
  return result;
}

```

## disassembly

```asm
0x1801155b0  push    rbx
0x1801155b2  push    rsi
0x1801155b3  push    rdi
0x1801155b4  push    r14
0x1801155b6  sub     rsp, 28h
0x1801155ba  mov     r14, rcx
0x1801155bd  xor     edi, edi
0x1801155bf  lea     rcx, aKernel32Dll_1; "KERNEL32.DLL"
0x1801155c6  mov     [rsp+48h+arg_0], edi
0x1801155ca  call    cs:__imp_LoadLibraryW
0x1801155d0  mov     rbx, rax
0x1801155d3  test    rax, rax
0x1801155d6  jz      short loc_18011561C
0x1801155d8  lea     rdx, aProcessidtoses; "ProcessIdToSessionId"
0x1801155df  mov     rcx, rax; hModule
0x1801155e2  mov     edi, 1
0x1801155e7  call    cs:__imp_GetProcAddress
0x1801155ed  mov     rsi, rax
0x1801155f0  test    rax, rax
0x1801155f3  jz      short loc_180115613
0x1801155f5  call    ?PAL_System_Win32_IsTSOnWin2KOrGreater@@YAHXZ; PAL_System_Win32_IsTSOnWin2KOrGreater(void)
0x1801155fa  test    eax, eax
0x1801155fc  jz      short loc_180115613
0x1801155fe  call    cs:__imp_GetCurrentProcessId
0x180115604  mov     ecx, eax
0x180115606  lea     rdx, [rsp+48h+arg_0]
0x18011560b  mov     rax, rsi
0x18011560e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115613  mov     rcx, rbx; hLibModule
0x180115616  call    cs:__imp_FreeLibrary
0x18011561c  mov     ecx, [rsp+48h+arg_0]
0x180115620  mov     eax, edi
0x180115622  mov     [r14], ecx
0x180115625  add     rsp, 28h
0x180115629  pop     r14
0x18011562b  pop     rdi
0x18011562c  pop     rsi
0x18011562d  pop     rbx
0x18011562e  retn
```
