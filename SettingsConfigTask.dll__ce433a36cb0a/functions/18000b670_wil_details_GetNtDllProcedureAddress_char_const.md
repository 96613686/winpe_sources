# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000b670`
- end: `0x18000b690`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004668`
- `0x180009750`
- `0x180009790`
- `0x18000a13c`
- `0x18000ac50`
- `0x18000ba2c`
- `0x18000bb58`
- `0x18000bf44`
- `0x18000bfbc`

## callees

- `0x18000b640`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b689`

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
0x18000b670  push    rbx
0x18000b672  sub     rsp, 20h
0x18000b676  mov     rbx, rcx
0x18000b679  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000b67e  mov     rcx, rax
0x18000b681  mov     rdx, rbx
0x18000b684  add     rsp, 20h
0x18000b688  pop     rbx
0x18000b689  jmp     cs:__imp_GetProcAddress
```
