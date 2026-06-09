# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140005ed0`
- end: `0x140005ef0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400053f0`
- `0x140005430`
- `0x14000d5e8`
- `0x14000d668`
- `0x14000d6e0`
- `0x14000d76c`
- `0x14000d7d8`

## callees

- `0x140005ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140005ee9`

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
0x140005ed0  push    rbx
0x140005ed2  sub     rsp, 20h
0x140005ed6  mov     rbx, rcx
0x140005ed9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140005ede  mov     rcx, rax
0x140005ee1  mov     rdx, rbx
0x140005ee4  add     rsp, 20h
0x140005ee8  pop     rbx
0x140005ee9  jmp     cs:__imp_GetProcAddress
```
