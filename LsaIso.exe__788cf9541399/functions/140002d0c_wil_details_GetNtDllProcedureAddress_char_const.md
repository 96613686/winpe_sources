# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140002d0c`
- end: `0x140002d2c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000bf00`
- `0x14000bf40`
- `0x14000c7d0`
- `0x140012240`
- `0x1400122a0`
- `0x140012318`

## callees

- `0x140002910`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002d25`

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
0x140002d0c  push    rbx
0x140002d0e  sub     rsp, 20h
0x140002d12  mov     rbx, rcx
0x140002d15  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140002d1a  mov     rcx, rax
0x140002d1d  mov     rdx, rbx
0x140002d20  add     rsp, 20h
0x140002d24  pop     rbx
0x140002d25  jmp     cs:__imp_GetProcAddress
```
