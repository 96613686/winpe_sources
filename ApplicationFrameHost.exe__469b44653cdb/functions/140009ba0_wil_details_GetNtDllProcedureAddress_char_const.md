# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140009ba0`
- end: `0x140009bc0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140002e24`
- `0x140008370`
- `0x1400083b0`
- `0x140009e28`
- `0x140009e88`
- `0x140009f00`
- `0x140009f8c`

## callees

- `0x140009b70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009bb9`

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
0x140009ba0  push    rbx
0x140009ba2  sub     rsp, 20h
0x140009ba6  mov     rbx, rcx
0x140009ba9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140009bae  mov     rcx, rax
0x140009bb1  mov     rdx, rbx
0x140009bb4  add     rsp, 20h
0x140009bb8  pop     rbx
0x140009bb9  jmp     cs:__imp_GetProcAddress
```
