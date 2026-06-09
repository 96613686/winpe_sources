# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1400066b0`
- end: `0x1400066d0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400056e0`
- `0x140005730`
- `0x1400120a0`
- `0x140012120`
- `0x140012198`
- `0x140012224`
- `0x140012288`

## callees

- `0x140006680`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400066c9`

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
0x1400066b0  push    rbx
0x1400066b2  sub     rsp, 20h
0x1400066b6  mov     rbx, rcx
0x1400066b9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1400066be  mov     rcx, rax
0x1400066c1  mov     rdx, rbx
0x1400066c4  add     rsp, 20h
0x1400066c8  pop     rbx
0x1400066c9  jmp     cs:__imp_GetProcAddress
```
