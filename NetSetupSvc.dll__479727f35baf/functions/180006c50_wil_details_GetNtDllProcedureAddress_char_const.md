# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180006c50`
- end: `0x180006c70`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005c60`
- `0x180005ca0`
- `0x180006760`
- `0x180008f14`
- `0x18000e024`
- `0x18000e150`
- `0x18000e5ec`
- `0x18000e664`
- `0x18000e840`

## callees

- `0x180006c20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c69`

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
0x180006c50  push    rbx
0x180006c52  sub     rsp, 20h
0x180006c56  mov     rbx, rcx
0x180006c59  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180006c5e  mov     rcx, rax
0x180006c61  mov     rdx, rbx
0x180006c64  add     rsp, 20h
0x180006c68  pop     rbx
0x180006c69  jmp     cs:__imp_GetProcAddress
```
