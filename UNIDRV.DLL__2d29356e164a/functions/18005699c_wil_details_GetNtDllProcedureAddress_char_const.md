# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18005699c`
- end: `0x1800569bc`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800511c4`
- `0x180055460`
- `0x1800554a0`
- `0x180056ca0`
- `0x180056dcc`
- `0x180056e8c`
- `0x180056f04`
- `0x1800570dc`

## callees

- `0x18005696c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800569b5`

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
0x18005699c  push    rbx
0x18005699e  sub     rsp, 20h
0x1800569a2  mov     rbx, rcx
0x1800569a5  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800569aa  mov     rcx, rax
0x1800569ad  mov     rdx, rbx
0x1800569b0  add     rsp, 20h
0x1800569b4  pop     rbx
0x1800569b5  jmp     cs:__imp_GetProcAddress
```
