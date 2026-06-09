# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000af90`
- end: `0x18000afb0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800055c4`
- `0x1800090a0`
- `0x1800090e0`
- `0x18000a770`
- `0x18000b224`
- `0x18000b350`
- `0x18000b40c`
- `0x18000b484`
- `0x18000b660`

## callees

- `0x18000af60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000afa9`

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
0x18000af90  push    rbx
0x18000af92  sub     rsp, 20h
0x18000af96  mov     rbx, rcx
0x18000af99  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000af9e  mov     rcx, rax
0x18000afa1  mov     rdx, rbx
0x18000afa4  add     rsp, 20h
0x18000afa8  pop     rbx
0x18000afa9  jmp     cs:__imp_GetProcAddress
```
