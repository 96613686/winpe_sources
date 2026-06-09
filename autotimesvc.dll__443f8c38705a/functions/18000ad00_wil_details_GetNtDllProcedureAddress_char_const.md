# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000ad00`
- end: `0x18000ad20`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800091c0`
- `0x180009200`

## callees

- `0x18000acd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad19`

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
0x18000ad00  push    rbx
0x18000ad02  sub     rsp, 20h
0x18000ad06  mov     rbx, rcx
0x18000ad09  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000ad0e  mov     rcx, rax
0x18000ad11  mov     rdx, rbx
0x18000ad14  add     rsp, 20h
0x18000ad18  pop     rbx
0x18000ad19  jmp     cs:__imp_GetProcAddress
```
