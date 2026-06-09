# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000d180`
- end: `0x18000d1a0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c290`
- `0x18000c2d0`
- `0x18001dab8`
- `0x180023598`
- `0x1800236c4`
- `0x180023b4c`
- `0x180023bc4`
- `0x180023da0`

## callees

- `0x18000d150`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d199`

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
0x18000d180  push    rbx
0x18000d182  sub     rsp, 20h
0x18000d186  mov     rbx, rcx
0x18000d189  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000d18e  mov     rcx, rax
0x18000d191  mov     rdx, rbx
0x18000d194  add     rsp, 20h
0x18000d198  pop     rbx
0x18000d199  jmp     cs:__imp_GetProcAddress
```
