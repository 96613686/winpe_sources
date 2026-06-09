# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000a0c8`
- end: `0x18000a0e8`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009200`
- `0x180009b30`

## callees

- `0x18000a098`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0e1`

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
0x18000a0c8  push    rbx
0x18000a0ca  sub     rsp, 20h
0x18000a0ce  mov     rbx, rcx
0x18000a0d1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000a0d6  mov     rcx, rax
0x18000a0d9  mov     rdx, rbx
0x18000a0dc  add     rsp, 20h
0x18000a0e0  pop     rbx
0x18000a0e1  jmp     cs:__imp_GetProcAddress
```
