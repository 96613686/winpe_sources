# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180018e1c`
- end: `0x180018e3c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013240`
- `0x180018cd4`
- `0x18001a478`
- `0x180025a60`
- `0x180025aa0`
- `0x180027634`
- `0x180028110`
- `0x18002b8bc`
- `0x18002ba4c`
- `0x18002bac4`

## callees

- `0x18002ae90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018e35`

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
0x180018e1c  push    rbx
0x180018e1e  sub     rsp, 20h
0x180018e22  mov     rbx, rcx
0x180018e25  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180018e2a  mov     rcx, rax
0x180018e2d  mov     rdx, rbx
0x180018e30  add     rsp, 20h
0x180018e34  pop     rbx
0x180018e35  jmp     cs:__imp_GetProcAddress
```
