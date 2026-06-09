# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800144cc`
- end: `0x1800144ec`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d218`
- `0x180013120`
- `0x180013160`
- `0x180013820`
- `0x1800148a8`
- `0x1800149d4`
- `0x180014a9c`
- `0x180014b14`

## callees

- `0x18001449c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800144e5`

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
0x1800144cc  push    rbx
0x1800144ce  sub     rsp, 20h
0x1800144d2  mov     rbx, rcx
0x1800144d5  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800144da  mov     rcx, rax
0x1800144dd  mov     rdx, rbx
0x1800144e0  add     rsp, 20h
0x1800144e4  pop     rbx
0x1800144e5  jmp     cs:__imp_GetProcAddress
```
