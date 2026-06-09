# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180011540`
- end: `0x180011560`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000877c`
- `0x18000f0f0`
- `0x18000f130`
- `0x18000fe5c`
- `0x180011840`
- `0x1800118a0`
- `0x180011918`

## callees

- `0x180011510`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011559`

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
0x180011540  push    rbx
0x180011542  sub     rsp, 20h
0x180011546  mov     rbx, rcx
0x180011549  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001154e  mov     rcx, rax
0x180011551  mov     rdx, rbx
0x180011554  add     rsp, 20h
0x180011558  pop     rbx
0x180011559  jmp     cs:__imp_GetProcAddress
```
