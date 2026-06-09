# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800071c0`
- end: `0x1800071e0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006810`

## callees

- `0x180007190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071d9`

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
0x1800071c0  push    rbx
0x1800071c2  sub     rsp, 20h
0x1800071c6  mov     rbx, rcx
0x1800071c9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800071ce  mov     rcx, rax
0x1800071d1  mov     rdx, rbx
0x1800071d4  add     rsp, 20h
0x1800071d8  pop     rbx
0x1800071d9  jmp     cs:__imp_GetProcAddress
```
