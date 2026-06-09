# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000e678`
- end: `0x18000e698`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e4d0`

## callees

- `0x18000e648`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e691`

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
0x18000e678  push    rbx
0x18000e67a  sub     rsp, 20h
0x18000e67e  mov     rbx, rcx
0x18000e681  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000e686  mov     rcx, rax
0x18000e689  mov     rdx, rbx
0x18000e68c  add     rsp, 20h
0x18000e690  pop     rbx
0x18000e691  jmp     cs:__imp_GetProcAddress
```
