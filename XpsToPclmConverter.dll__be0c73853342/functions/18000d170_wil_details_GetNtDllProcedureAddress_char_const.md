# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000d170`
- end: `0x18000d190`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000875c`
- `0x18000b8e0`
- `0x18000b920`
- `0x18000d404`
- `0x18000d464`
- `0x18000d4dc`
- `0x18000d568`

## callees

- `0x18000d140`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d189`

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
0x18000d170  push    rbx
0x18000d172  sub     rsp, 20h
0x18000d176  mov     rbx, rcx
0x18000d179  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000d17e  mov     rcx, rax
0x18000d181  mov     rdx, rbx
0x18000d184  add     rsp, 20h
0x18000d188  pop     rbx
0x18000d189  jmp     cs:__imp_GetProcAddress
```
