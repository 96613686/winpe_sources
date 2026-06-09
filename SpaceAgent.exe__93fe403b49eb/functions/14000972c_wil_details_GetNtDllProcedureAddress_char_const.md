# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000972c`
- end: `0x14000974c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140004660`
- `0x1400079f0`
- `0x140007a30`
- `0x140008838`
- `0x140009a1c`
- `0x140009b48`
- `0x140009c0c`
- `0x140009c84`

## callees

- `0x1400096fc`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140009745`

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
0x14000972c  push    rbx
0x14000972e  sub     rsp, 20h
0x140009732  mov     rbx, rcx
0x140009735  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000973a  mov     rcx, rax
0x14000973d  mov     rdx, rbx
0x140009740  add     rsp, 20h
0x140009744  pop     rbx
0x140009745  jmp     cs:__imp_GetProcAddress
```
