# initialize_pointers

- ea: `0x18004df60`
- end: `0x18004dfac`
- name: `initialize_pointers`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18004df80`
- `KERNEL32!GetProcAddress` at `0x18004df97`
- `KERNEL32!GetProcAddress` at `0x18004df80`
- `KERNEL32!GetProcAddress` at `0x18004df97`
- `KERNEL32!GetModuleHandleW` at `0x18004df6d`
- `KERNEL32!GetModuleHandleW` at `0x18004df6d`

## string_xrefs

- `0x18004df66`: `kernel32.dll`
- `0x18004df86`: `GetTempPath2W`

## pseudocode

```c
__int64 initialize_pointers()
{
  HMODULE ModuleHandleW; // rbx

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  qword_180086390 = (__int64)GetProcAddress(ModuleHandleW, "GetSystemTimePreciseAsFileTime");
  qword_180086398 = (__int64)GetProcAddress(ModuleHandleW, "GetTempPath2W");
  return 0;
}

```

## disassembly

```asm
0x18004df60  push    rbx
0x18004df62  sub     rsp, 20h
0x18004df66  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18004df6d  call    cs:__imp_GetModuleHandleW
0x18004df73  mov     rcx, rax; hModule
0x18004df76  lea     rdx, aGetsystemtimep; "GetSystemTimePreciseAsFileTime"
0x18004df7d  mov     rbx, rax
0x18004df80  call    cs:__imp_GetProcAddress
0x18004df86  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18004df8d  mov     rcx, rbx; hModule
0x18004df90  mov     cs:qword_180086390, rax
0x18004df97  call    cs:__imp_GetProcAddress
0x18004df9d  mov     cs:qword_180086398, rax
0x18004dfa4  xor     eax, eax
0x18004dfa6  add     rsp, 20h
0x18004dfaa  pop     rbx
0x18004dfab  retn
```
