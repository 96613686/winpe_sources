# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140006bd0`
- end: `0x140006bf0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400056d0`
- `0x140005710`
- `0x1400133dc`
- `0x140013508`
- `0x14001398c`
- `0x140013a04`
- `0x140013be0`
- `0x140013c4c`

## callees

- `0x140006ba0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140006be9`

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
0x140006bd0  push    rbx
0x140006bd2  sub     rsp, 20h
0x140006bd6  mov     rbx, rcx
0x140006bd9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140006bde  mov     rcx, rax
0x140006be1  mov     rdx, rbx
0x140006be4  add     rsp, 20h
0x140006be8  pop     rbx
0x140006be9  jmp     cs:__imp_GetProcAddress
```
