# initialize_pointers

- ea: `0x180034e60`
- end: `0x180034eac`
- name: `initialize_pointers`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180034e6d`
- `KERNEL32!GetModuleHandleW` at `0x180034e6d`
- `KERNEL32!GetProcAddress` at `0x180034e80`
- `KERNEL32!GetProcAddress` at `0x180034e97`
- `KERNEL32!GetProcAddress` at `0x180034e80`
- `KERNEL32!GetProcAddress` at `0x180034e97`

## string_xrefs

- `0x180034e66`: `kernel32.dll`
- `0x180034e86`: `GetTempPath2W`

## pseudocode

```c
__int64 initialize_pointers()
{
  HMODULE ModuleHandleW; // rbx

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  qword_180059540 = (__int64)GetProcAddress(ModuleHandleW, "GetSystemTimePreciseAsFileTime");
  qword_180059548 = (__int64)GetProcAddress(ModuleHandleW, "GetTempPath2W");
  return 0;
}

```

## disassembly

```asm
0x180034e60  push    rbx
0x180034e62  sub     rsp, 20h
0x180034e66  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180034e6d  call    cs:__imp_GetModuleHandleW
0x180034e73  mov     rcx, rax; hModule
0x180034e76  lea     rdx, aGetsystemtimep; "GetSystemTimePreciseAsFileTime"
0x180034e7d  mov     rbx, rax
0x180034e80  call    cs:__imp_GetProcAddress
0x180034e86  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180034e8d  mov     rcx, rbx; hModule
0x180034e90  mov     cs:qword_180059540, rax
0x180034e97  call    cs:__imp_GetProcAddress
0x180034e9d  mov     cs:qword_180059548, rax
0x180034ea4  xor     eax, eax
0x180034ea6  add     rsp, 20h
0x180034eaa  pop     rbx
0x180034eab  retn
```
