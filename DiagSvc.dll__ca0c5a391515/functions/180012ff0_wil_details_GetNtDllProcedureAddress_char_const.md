# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180012ff0`
- end: `0x180013010`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009f38`
- `0x180010280`
- `0x1800102c0`
- `0x1800131f4`
- `0x180013320`
- `0x18001379c`
- `0x180013814`
- `0x1800139f0`

## callees

- `0x180012fc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013009`

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
0x180012ff0  push    rbx
0x180012ff2  sub     rsp, 20h
0x180012ff6  mov     rbx, rcx
0x180012ff9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180012ffe  mov     rcx, rax
0x180013001  mov     rdx, rbx
0x180013004  add     rsp, 20h
0x180013008  pop     rbx
0x180013009  jmp     cs:__imp_GetProcAddress
```
