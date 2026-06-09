# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180006d98`
- end: `0x180006dbd`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005460`

## callees

- `0x180006d60`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180006db1`

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
0x180006d98  push    rbx
0x180006d9a  sub     rsp, 20h
0x180006d9e  mov     rbx, rcx
0x180006da1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180006da6  mov     rcx, rax
0x180006da9  mov     rdx, rbx
0x180006dac  add     rsp, 20h
0x180006db0  pop     rbx
0x180006db1  jmp     cs:__imp_GetProcAddress
```
