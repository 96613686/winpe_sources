# initialize_pointers

- ea: `0x180018120`
- end: `0x18001816c`
- name: `initialize_pointers`
- size: `76`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180018140`
- `KERNEL32!GetProcAddress` at `0x180018157`
- `KERNEL32!GetProcAddress` at `0x180018140`
- `KERNEL32!GetProcAddress` at `0x180018157`
- `KERNEL32!GetModuleHandleW` at `0x18001812d`
- `KERNEL32!GetModuleHandleW` at `0x18001812d`

## string_xrefs

- `0x180018126`: `kernel32.dll`
- `0x180018146`: `GetTempPath2W`

## pseudocode

```c
__int64 initialize_pointers()
{
  HMODULE ModuleHandleW; // rbx

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  qword_18002DE60 = (__int64)GetProcAddress(ModuleHandleW, "GetSystemTimePreciseAsFileTime");
  qword_18002DE68 = (__int64)GetProcAddress(ModuleHandleW, "GetTempPath2W");
  return 0;
}

```

## disassembly

```asm
0x180018120  push    rbx
0x180018122  sub     rsp, 20h
0x180018126  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18001812d  call    cs:__imp_GetModuleHandleW
0x180018133  mov     rcx, rax; hModule
0x180018136  lea     rdx, aGetsystemtimep; "GetSystemTimePreciseAsFileTime"
0x18001813d  mov     rbx, rax
0x180018140  call    cs:__imp_GetProcAddress
0x180018146  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18001814d  mov     rcx, rbx; hModule
0x180018150  mov     cs:qword_18002DE60, rax
0x180018157  call    cs:__imp_GetProcAddress
0x18001815d  mov     cs:qword_18002DE68, rax
0x180018164  xor     eax, eax
0x180018166  add     rsp, 20h
0x18001816a  pop     rbx
0x18001816b  retn
```
