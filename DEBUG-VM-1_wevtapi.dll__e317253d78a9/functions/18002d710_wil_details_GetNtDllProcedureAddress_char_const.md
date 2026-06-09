# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002d710`
- end: `0x18002d730`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180020948`
- `0x18002c3d0`
- `0x18002c410`
- `0x18002ca6c`
- `0x18002d908`
- `0x18002da34`
- `0x18002dafc`
- `0x18002db74`

## callees

- `0x18002d6e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d729`

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
0x18002d710  push    rbx
0x18002d712  sub     rsp, 20h
0x18002d716  mov     rbx, rcx
0x18002d719  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002d71e  mov     rcx, rax
0x18002d721  mov     rdx, rbx
0x18002d724  add     rsp, 20h
0x18002d728  pop     rbx
0x18002d729  jmp     cs:__imp_GetProcAddress
```
