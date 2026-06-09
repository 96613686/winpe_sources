# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180016fd0`
- end: `0x180016ff0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011850`
- `0x1800147d0`
- `0x180014810`
- `0x1800178a4`
- `0x180017904`
- `0x18001797c`
- `0x180017a08`

## callees

- `0x180016fa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016fe9`

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
0x180016fd0  push    rbx
0x180016fd2  sub     rsp, 20h
0x180016fd6  mov     rbx, rcx
0x180016fd9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180016fde  mov     rcx, rax
0x180016fe1  mov     rdx, rbx
0x180016fe4  add     rsp, 20h
0x180016fe8  pop     rbx
0x180016fe9  jmp     cs:__imp_GetProcAddress
```
