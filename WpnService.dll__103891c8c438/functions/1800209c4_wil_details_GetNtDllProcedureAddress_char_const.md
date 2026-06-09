# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800209c4`
- end: `0x1800209e4`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800151d0`
- `0x18002094c`
- `0x180023a18`
- `0x180027920`
- `0x180027960`
- `0x180027d00`
- `0x18002a518`
- `0x18002b07c`
- `0x18002b1a8`
- `0x18002b4ac`

## callees

- `0x180027ed8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800209dd`

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
0x1800209c4  push    rbx
0x1800209c6  sub     rsp, 20h
0x1800209ca  mov     rbx, rcx
0x1800209cd  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800209d2  mov     rcx, rax
0x1800209d5  mov     rdx, rbx
0x1800209d8  add     rsp, 20h
0x1800209dc  pop     rbx
0x1800209dd  jmp     cs:__imp_GetProcAddress
```
