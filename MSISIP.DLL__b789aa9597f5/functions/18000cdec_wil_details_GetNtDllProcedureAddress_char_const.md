# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000cdec`
- end: `0x18000ce0c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c300`
- `0x18000c350`
- `0x18000cf98`
- `0x18000cff8`
- `0x18000d070`
- `0x18000d0fc`
- `0x18000d168`

## callees

- `0x180006bf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000ce05`

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
0x18000cdec  push    rbx
0x18000cdee  sub     rsp, 20h
0x18000cdf2  mov     rbx, rcx
0x18000cdf5  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000cdfa  mov     rcx, rax
0x18000cdfd  mov     rdx, rbx
0x18000ce00  add     rsp, 20h
0x18000ce04  pop     rbx
0x18000ce05  jmp     cs:__imp_GetProcAddress
```
