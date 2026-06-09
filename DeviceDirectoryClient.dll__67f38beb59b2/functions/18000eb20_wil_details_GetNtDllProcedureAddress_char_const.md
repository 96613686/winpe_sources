# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000eb20`
- end: `0x18000eb40`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008a00`
- `0x18000d0b0`
- `0x18000d0f0`
- `0x18000ed94`
- `0x18000eec0`
- `0x18000ef7c`
- `0x18000eff4`
- `0x18000f1d0`

## callees

- `0x18000eaf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eb39`

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
0x18000eb20  push    rbx
0x18000eb22  sub     rsp, 20h
0x18000eb26  mov     rbx, rcx
0x18000eb29  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000eb2e  mov     rcx, rax
0x18000eb31  mov     rdx, rbx
0x18000eb34  add     rsp, 20h
0x18000eb38  pop     rbx
0x18000eb39  jmp     cs:__imp_GetProcAddress
```
