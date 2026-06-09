# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002b9e8`
- end: `0x18002ba0d`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180027280`
- `0x1800272d0`
- `0x18002bd98`
- `0x18002bdf8`
- `0x18002be70`
- `0x18002befc`
- `0x18002bf68`

## callees

- `0x18002b9b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ba01`

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
0x18002b9e8  push    rbx
0x18002b9ea  sub     rsp, 20h
0x18002b9ee  mov     rbx, rcx
0x18002b9f1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002b9f6  mov     rcx, rax
0x18002b9f9  mov     rdx, rbx
0x18002b9fc  add     rsp, 20h
0x18002ba00  pop     rbx
0x18002ba01  jmp     cs:__imp_GetProcAddress
```
