# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180019230`
- end: `0x180019250`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bcdc`
- `0x1800166f0`
- `0x180016730`
- `0x180017164`
- `0x18001992c`
- `0x180019a58`
- `0x180019ee0`
- `0x180019f58`

## callees

- `0x180019200`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019249`

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
0x180019230  push    rbx
0x180019232  sub     rsp, 20h
0x180019236  mov     rbx, rcx
0x180019239  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001923e  mov     rcx, rax
0x180019241  mov     rdx, rbx
0x180019244  add     rsp, 20h
0x180019248  pop     rbx
0x180019249  jmp     cs:__imp_GetProcAddress
```
