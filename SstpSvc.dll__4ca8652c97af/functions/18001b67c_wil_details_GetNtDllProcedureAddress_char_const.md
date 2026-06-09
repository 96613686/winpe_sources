# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001b67c`
- end: `0x18001b69c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017504`
- `0x18001a380`
- `0x18001a3c0`
- `0x18001b8e0`
- `0x18001b940`
- `0x18001b9b8`
- `0x18001ba44`

## callees

- `0x18001b64c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b695`

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
0x18001b67c  push    rbx
0x18001b67e  sub     rsp, 20h
0x18001b682  mov     rbx, rcx
0x18001b685  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001b68a  mov     rcx, rax
0x18001b68d  mov     rdx, rbx
0x18001b690  add     rsp, 20h
0x18001b694  pop     rbx
0x18001b695  jmp     cs:__imp_GetProcAddress
```
