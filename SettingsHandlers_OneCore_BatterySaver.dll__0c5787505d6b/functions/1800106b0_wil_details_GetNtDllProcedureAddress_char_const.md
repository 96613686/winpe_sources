# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800106b0`
- end: `0x1800106d0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b564`
- `0x18000eaf0`
- `0x18000eb30`
- `0x18000f400`
- `0x18000fe80`
- `0x180010938`
- `0x180010a64`
- `0x180010b2c`
- `0x180010ba4`

## callees

- `0x180010680`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800106c9`

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
0x1800106b0  push    rbx
0x1800106b2  sub     rsp, 20h
0x1800106b6  mov     rbx, rcx
0x1800106b9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800106be  mov     rcx, rax
0x1800106c1  mov     rdx, rbx
0x1800106c4  add     rsp, 20h
0x1800106c8  pop     rbx
0x1800106c9  jmp     cs:__imp_GetProcAddress
```
