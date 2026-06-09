# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180079b94`
- end: `0x180079bb4`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180078f90`

## callees

- `0x180079b64`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079bad`

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
0x180079b94  push    rbx
0x180079b96  sub     rsp, 20h
0x180079b9a  mov     rbx, rcx
0x180079b9d  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180079ba2  mov     rcx, rax
0x180079ba5  mov     rdx, rbx
0x180079ba8  add     rsp, 20h
0x180079bac  pop     rbx
0x180079bad  jmp     cs:__imp_GetProcAddress
```
