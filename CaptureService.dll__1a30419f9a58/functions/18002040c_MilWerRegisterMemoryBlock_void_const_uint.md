# MilWerRegisterMemoryBlock(void const *,uint)

- ea: `0x18002040c`
- end: `0x180020457`
- name: `?MilWerRegisterMemoryBlock@@YAXPEBXI@Z`
- size: `75`
- prototype: `void __fastcall(const void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800200c0`

## callees

- `0x18002040c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020437`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020437`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020422`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020422`

## string_xrefs

- `0x18002041b`: `kernel32.dll`

## pseudocode

```c
void __fastcall MilWerRegisterMemoryBlock(const void *a1, unsigned int a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WerRegisterMemoryBlock");
    if ( ProcAddress )
      ((void (__fastcall *)(const void *, _QWORD))ProcAddress)(a1, a2);
  }
}

```

## disassembly

```asm
0x18002040c  mov     [rsp+arg_0], rbx
0x180020411  push    rdi
0x180020412  sub     rsp, 20h
0x180020416  mov     rdi, rcx
0x180020419  mov     ebx, edx
0x18002041b  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180020422  call    cs:__imp_GetModuleHandleW
0x180020428  test    rax, rax
0x18002042b  jz      short loc_18002044C
0x18002042d  lea     rdx, ProcName; "WerRegisterMemoryBlock"
0x180020434  mov     rcx, rax; hModule
0x180020437  call    cs:__imp_GetProcAddress
0x18002043d  test    rax, rax
0x180020440  jz      short loc_18002044C
0x180020442  mov     edx, ebx
0x180020444  mov     rcx, rdi
0x180020447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002044c  mov     rbx, [rsp+28h+arg_0]
0x180020451  add     rsp, 20h
0x180020455  pop     rdi
0x180020456  retn
```
