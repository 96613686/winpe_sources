# _ThunkCOMServerDllMain

- ea: `0x140005484`
- end: `0x1400054e7`
- name: `_ThunkCOMServerDllMain`
- size: `99`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400054fc`

## callees

- `0x140005484`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400054bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400054bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400054a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400054a7`

## string_xrefs

- `0x140005495`: `browserbroker.dll`
- `0x1400054b2`: `COMServerDllMain`

## pseudocode

```c
__int64 __fastcall ThunkCOMServerDllMain(unsigned int a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v8 = -2147418113;
  ModuleHandleW = GetModuleHandleW(L"browserbroker.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "COMServerDllMain");
    if ( ProcAddress )
      return ((unsigned int (__fastcall *)(_QWORD, __int64, __int64, __int64))ProcAddress)(a1, a2, a3, a4);
  }
  return v8;
}

```

## disassembly

```asm
0x140005484  push    rbx
0x140005486  push    rbp
0x140005487  push    rsi
0x140005488  push    rdi
0x140005489  push    r14
0x14000548b  sub     rsp, 30h
0x14000548f  mov     r14d, ecx
0x140005492  mov     rdi, r9
0x140005495  lea     rcx, LibFileName; "browserbroker.dll"
0x14000549c  mov     rsi, r8
0x14000549f  mov     rbp, rdx
0x1400054a2  mov     ebx, 8000FFFFh
0x1400054a7  call    cs:__imp_GetModuleHandleW
0x1400054ad  test    rax, rax
0x1400054b0  jz      short loc_1400054DA
0x1400054b2  lea     rdx, aComserverdllma; "COMServerDllMain"
0x1400054b9  mov     rcx, rax; hModule
0x1400054bc  call    cs:__imp_GetProcAddress
0x1400054c2  test    rax, rax
0x1400054c5  jz      short loc_1400054DA
0x1400054c7  mov     r9, rdi
0x1400054ca  mov     r8, rsi
0x1400054cd  mov     rdx, rbp
0x1400054d0  mov     ecx, r14d
0x1400054d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054d8  mov     ebx, eax
0x1400054da  mov     eax, ebx
0x1400054dc  add     rsp, 30h
0x1400054e0  pop     r14
0x1400054e2  pop     rdi
0x1400054e3  pop     rsi
0x1400054e4  pop     rbp
0x1400054e5  pop     rbx
0x1400054e6  retn
```
