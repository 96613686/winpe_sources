# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000c630`
- end: `0x14000c650`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000a1b0`
- `0x14000a1f0`
- `0x14000c858`
- `0x14000c8b8`
- `0x14000c930`
- `0x14000c9bc`
- `0x14000ca28`

## callees

- `0x14000c600`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c649`

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
0x14000c630  push    rbx
0x14000c632  sub     rsp, 20h
0x14000c636  mov     rbx, rcx
0x14000c639  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000c63e  mov     rcx, rax
0x14000c641  mov     rdx, rbx
0x14000c644  add     rsp, 20h
0x14000c648  pop     rbx
0x14000c649  jmp     cs:__imp_GetProcAddress
```
