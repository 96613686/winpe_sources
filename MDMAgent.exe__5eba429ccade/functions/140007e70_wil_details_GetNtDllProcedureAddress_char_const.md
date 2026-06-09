# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140007e70`
- end: `0x140007e90`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400069d0`
- `0x140006a10`
- `0x1400078b0`
- `0x140011ca0`
- `0x140011d00`
- `0x140011d78`
- `0x140011e04`
- `0x140011e70`

## callees

- `0x140007e40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e89`

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
0x140007e70  push    rbx
0x140007e72  sub     rsp, 20h
0x140007e76  mov     rbx, rcx
0x140007e79  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140007e7e  mov     rcx, rax
0x140007e81  mov     rdx, rbx
0x140007e84  add     rsp, 20h
0x140007e88  pop     rbx
0x140007e89  jmp     cs:__imp_GetProcAddress
```
