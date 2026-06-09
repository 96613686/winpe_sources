# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000adb0`
- end: `0x18000add0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800091e0`
- `0x180009220`
- `0x18000a590`
- `0x18000b060`
- `0x18000b18c`
- `0x18000b24c`
- `0x18000b2c4`
- `0x18000b4a0`
- `0x18000b50c`

## callees

- `0x18000ad80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000adc9`

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
0x18000adb0  push    rbx
0x18000adb2  sub     rsp, 20h
0x18000adb6  mov     rbx, rcx
0x18000adb9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000adbe  mov     rcx, rax
0x18000adc1  mov     rdx, rbx
0x18000adc4  add     rsp, 20h
0x18000adc8  pop     rbx
0x18000adc9  jmp     cs:__imp_GetProcAddress
```
