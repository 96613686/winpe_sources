# initialize_pointers

- ea: `0x140005930`
- end: `0x14000597c`
- name: `initialize_pointers`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000593d`
- `KERNEL32!GetModuleHandleW` at `0x14000593d`
- `KERNEL32!GetProcAddress` at `0x140005950`
- `KERNEL32!GetProcAddress` at `0x140005967`
- `KERNEL32!GetProcAddress` at `0x140005950`
- `KERNEL32!GetProcAddress` at `0x140005967`

## string_xrefs

- `0x140005956`: `GetTempPath2W`
- `0x140005936`: `kernel32.dll`

## pseudocode

```c
__int64 initialize_pointers()
{
  HMODULE ModuleHandleW; // rbx

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  qword_14003C160 = (__int64)GetProcAddress(ModuleHandleW, "GetSystemTimePreciseAsFileTime");
  qword_14003C168 = (__int64)GetProcAddress(ModuleHandleW, (LPCSTR)"GetTempPath2W");
  return 0;
}

```

## disassembly

```asm
0x140005930  push    rbx
0x140005932  sub     rsp, 20h
0x140005936  lea     rcx, ModuleName; "kernel32.dll"
0x14000593d  call    cs:__imp_GetModuleHandleW
0x140005943  mov     rcx, rax; hModule
0x140005946  lea     rdx, ProcName; "GetSystemTimePreciseAsFileTime"
0x14000594d  mov     rbx, rax
0x140005950  call    cs:__imp_GetProcAddress
0x140005956  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x14000595d  mov     rcx, rbx; hModule
0x140005960  mov     cs:qword_14003C160, rax
0x140005967  call    cs:__imp_GetProcAddress
0x14000596d  mov     cs:qword_14003C168, rax
0x140005974  xor     eax, eax
0x140005976  add     rsp, 20h
0x14000597a  pop     rbx
0x14000597b  retn
```
