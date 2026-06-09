# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000e430`
- end: `0x18000e450`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (__fastcall *__fastcall(const char *procedureName))()`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d3e0`
- `0x18000d420`
- `0x18000d830`
- `0x18000e000`
- `0x18000e714`
- `0x18000e774`
- `0x18000e7ec`

## callees

- `0x18000e400`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e449`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *procedureName)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, procedureName);
}

```

## disassembly

```asm
0x18000e430  push    rbx
0x18000e432  sub     rsp, 20h
0x18000e436  mov     rbx, procedureName
0x18000e439  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000e43e  mov     procedureName, rax
0x18000e441  mov     rdx, rbx
0x18000e444  add     rsp, 20h
0x18000e448  pop     rbx
0x18000e449  jmp     cs:__imp_GetProcAddress
```
