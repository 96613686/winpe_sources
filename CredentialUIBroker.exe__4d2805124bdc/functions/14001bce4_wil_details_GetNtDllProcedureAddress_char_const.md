# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14001bce4`
- end: `0x14001bd04`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140013750`
- `0x140013790`
- `0x1400179d0`
- `0x14001c6b0`
- `0x14001c7dc`
- `0x14001cc5c`
- `0x14001ccd4`
- `0x14001ceac`
- `0x14001cf18`

## callees

- `0x14001bcb4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001bcfd`

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
0x14001bce4  push    rbx
0x14001bce6  sub     rsp, 20h
0x14001bcea  mov     rbx, rcx
0x14001bced  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14001bcf2  mov     rcx, rax
0x14001bcf5  mov     rdx, rbx
0x14001bcf8  add     rsp, 20h
0x14001bcfc  pop     rbx
0x14001bcfd  jmp     cs:__imp_GetProcAddress
```
