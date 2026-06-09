# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000a010`
- end: `0x18000a030`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003940`
- `0x180009120`
- `0x180009160`
- `0x18000cb5c`
- `0x18000f394`
- `0x18000f3f4`
- `0x18000f46c`

## callees

- `0x180009fe0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a029`

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
0x18000a010  push    rbx
0x18000a012  sub     rsp, 20h
0x18000a016  mov     rbx, rcx
0x18000a019  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000a01e  mov     rcx, rax
0x18000a021  mov     rdx, rbx
0x18000a024  add     rsp, 20h
0x18000a028  pop     rbx
0x18000a029  jmp     cs:__imp_GetProcAddress
```
