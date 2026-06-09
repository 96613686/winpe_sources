# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180007920`
- end: `0x180007940`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006cc0`
- `0x180006d00`
- `0x180007fc8`
- `0x18000b740`
- `0x18000b86c`
- `0x18000bcec`
- `0x18000bd64`
- `0x18000bf40`

## callees

- `0x1800078f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007939`

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
0x180007920  push    rbx
0x180007922  sub     rsp, 20h
0x180007926  mov     rbx, rcx
0x180007929  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000792e  mov     rcx, rax
0x180007931  mov     rdx, rbx
0x180007934  add     rsp, 20h
0x180007938  pop     rbx
0x180007939  jmp     cs:__imp_GetProcAddress
```
