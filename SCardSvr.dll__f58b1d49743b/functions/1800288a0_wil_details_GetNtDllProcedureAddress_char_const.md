# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800288a0`
- end: `0x1800288c0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001c1b8`
- `0x180027000`
- `0x180027040`
- `0x180028dfc`
- `0x180028f28`
- `0x180028fec`
- `0x180029064`
- `0x180029240`

## callees

- `0x180028870`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800288b9`

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
0x1800288a0  push    rbx
0x1800288a2  sub     rsp, 20h
0x1800288a6  mov     rbx, rcx
0x1800288a9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800288ae  mov     rcx, rax
0x1800288b1  mov     rdx, rbx
0x1800288b4  add     rsp, 20h
0x1800288b8  pop     rbx
0x1800288b9  jmp     cs:__imp_GetProcAddress
```
