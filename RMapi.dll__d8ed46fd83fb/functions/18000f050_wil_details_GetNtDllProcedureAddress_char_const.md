# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000f050`
- end: `0x18000f070`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ecb0`
- `0x18000ecf0`
- `0x180011960`
- `0x180016ef0`
- `0x18001701c`
- `0x1800174bc`
- `0x180017534`
- `0x180017710`

## callees

- `0x18000f020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f069`

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
0x18000f050  push    rbx
0x18000f052  sub     rsp, 20h
0x18000f056  mov     rbx, rcx
0x18000f059  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000f05e  mov     rcx, rax
0x18000f061  mov     rdx, rbx
0x18000f064  add     rsp, 20h
0x18000f068  pop     rbx
0x18000f069  jmp     cs:__imp_GetProcAddress
```
