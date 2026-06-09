# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800089f0`
- end: `0x180008a10`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800076c0`
- `0x180007700`
- `0x180008130`
- `0x18000a42c`
- `0x18000da64`
- `0x18000dac4`
- `0x18000db3c`
- `0x18000dbc8`

## callees

- `0x1800089c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a09`

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
0x1800089f0  push    rbx
0x1800089f2  sub     rsp, 20h
0x1800089f6  mov     rbx, rcx
0x1800089f9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800089fe  mov     rcx, rax
0x180008a01  mov     rdx, rbx
0x180008a04  add     rsp, 20h
0x180008a08  pop     rbx
0x180008a09  jmp     cs:__imp_GetProcAddress
```
