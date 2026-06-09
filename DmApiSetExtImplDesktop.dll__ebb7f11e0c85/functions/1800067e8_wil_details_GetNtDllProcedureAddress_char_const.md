# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800067e8`
- end: `0x18000680d`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004e30`

## callees

- `0x1800067b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006801`

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
0x1800067e8  push    rbx
0x1800067ea  sub     rsp, 20h
0x1800067ee  mov     rbx, rcx
0x1800067f1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800067f6  mov     rcx, rax
0x1800067f9  mov     rdx, rbx
0x1800067fc  add     rsp, 20h
0x180006800  pop     rbx
0x180006801  jmp     cs:__imp_GetProcAddress
```
