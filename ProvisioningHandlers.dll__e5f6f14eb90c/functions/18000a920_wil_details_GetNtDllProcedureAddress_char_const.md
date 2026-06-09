# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000a920`
- end: `0x18000a945`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800046f4`
- `0x180008820`
- `0x180008860`
- `0x18000ab28`
- `0x18000ac54`
- `0x18000ad20`
- `0x18000ad98`
- `0x18000af78`

## callees

- `0x18000a8e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a939`

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
0x18000a920  push    rbx
0x18000a922  sub     rsp, 20h
0x18000a926  mov     rbx, rcx
0x18000a929  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000a92e  mov     rcx, rax
0x18000a931  mov     rdx, rbx
0x18000a934  add     rsp, 20h
0x18000a938  pop     rbx
0x18000a939  jmp     cs:__imp_GetProcAddress
```
