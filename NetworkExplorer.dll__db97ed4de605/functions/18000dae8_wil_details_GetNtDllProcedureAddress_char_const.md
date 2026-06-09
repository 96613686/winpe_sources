# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000dae8`
- end: `0x18000db08`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b390`
- `0x18000c4d0`

## callees

- `0x18000dab8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db01`

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
0x18000dae8  push    rbx
0x18000daea  sub     rsp, 20h
0x18000daee  mov     rbx, rcx
0x18000daf1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000daf6  mov     rcx, rax
0x18000daf9  mov     rdx, rbx
0x18000dafc  add     rsp, 20h
0x18000db00  pop     rbx
0x18000db01  jmp     cs:__imp_GetProcAddress
```
