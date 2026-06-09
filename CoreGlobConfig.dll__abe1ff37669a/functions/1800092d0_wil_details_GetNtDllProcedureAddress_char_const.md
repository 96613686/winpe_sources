# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800092d0`
- end: `0x1800092f0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006c10`
- `0x1800082c0`
- `0x180008300`
- `0x180008e10`
- `0x180020a78`
- `0x180020ba4`
- `0x18002102c`
- `0x1800210a4`
- `0x180021280`
- `0x1800212ec`

## callees

- `0x1800092a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800092e9`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, a1);
}

```

## disassembly

```asm
0x1800092d0  push    rbx
0x1800092d2  sub     rsp, 20h
0x1800092d6  mov     rbx, rcx
0x1800092d9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800092de  mov     rcx, rax
0x1800092e1  mov     rdx, rbx
0x1800092e4  add     rsp, 20h
0x1800092e8  pop     rbx
0x1800092e9  jmp     cs:__imp_GetProcAddress
```
