# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140007b18`
- end: `0x140007b38`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006c50`
- `0x1400076a0`

## callees

- `0x140007ae8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007b31`

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
0x140007b18  push    rbx
0x140007b1a  sub     rsp, 20h
0x140007b1e  mov     rbx, rcx
0x140007b21  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140007b26  mov     rcx, rax
0x140007b29  mov     rdx, rbx
0x140007b2c  add     rsp, 20h
0x140007b30  pop     rbx
0x140007b31  jmp     cs:__imp_GetProcAddress
```
