# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800090d0`
- end: `0x1800090f0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800036f4`
- `0x1800074f0`
- `0x180007530`
- `0x180007e74`
- `0x180008760`
- `0x1800093dc`
- `0x18000943c`
- `0x1800094b4`

## callees

- `0x1800090a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800090e9`

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
0x1800090d0  push    rbx
0x1800090d2  sub     rsp, 20h
0x1800090d6  mov     rbx, rcx
0x1800090d9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800090de  mov     rcx, rax
0x1800090e1  mov     rdx, rbx
0x1800090e4  add     rsp, 20h
0x1800090e8  pop     rbx
0x1800090e9  jmp     cs:__imp_GetProcAddress
```
