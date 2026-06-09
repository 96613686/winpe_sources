# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180007aa0`
- end: `0x180007ac0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005450`
- `0x180006b40`
- `0x180006b80`
- `0x1800075e0`
- `0x18002b404`
- `0x18002b530`
- `0x18002b5ec`
- `0x18002b664`
- `0x18002b6f0`
- `0x18002b75c`

## callees

- `0x180007a70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ab9`

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
0x180007aa0  push    rbx
0x180007aa2  sub     rsp, 20h
0x180007aa6  mov     rbx, rcx
0x180007aa9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180007aae  mov     rcx, rax
0x180007ab1  mov     rdx, rbx
0x180007ab4  add     rsp, 20h
0x180007ab8  pop     rbx
0x180007ab9  jmp     cs:__imp_GetProcAddress
```
