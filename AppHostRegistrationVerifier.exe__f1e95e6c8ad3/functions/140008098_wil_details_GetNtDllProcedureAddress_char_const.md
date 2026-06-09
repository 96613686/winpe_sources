# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140008098`
- end: `0x1400080b8`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006ad0`
- `0x140006b10`
- `0x140007590`

## callees

- `0x140008068`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400080b1`

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
0x140008098  push    rbx
0x14000809a  sub     rsp, 20h
0x14000809e  mov     rbx, rcx
0x1400080a1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1400080a6  mov     rcx, rax
0x1400080a9  mov     rdx, rbx
0x1400080ac  add     rsp, 20h
0x1400080b0  pop     rbx
0x1400080b1  jmp     cs:__imp_GetProcAddress
```
