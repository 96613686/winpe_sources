# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800076b0`
- end: `0x1800076d0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800067d0`
- `0x180006810`
- `0x180007200`
- `0x180007d70`
- `0x18000b114`
- `0x18000b174`
- `0x18000b1ec`
- `0x18000b278`

## callees

- `0x180007680`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076c9`

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
0x1800076b0  push    rbx
0x1800076b2  sub     rsp, 20h
0x1800076b6  mov     rbx, rcx
0x1800076b9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800076be  mov     rcx, rax
0x1800076c1  mov     rdx, rbx
0x1800076c4  add     rsp, 20h
0x1800076c8  pop     rbx
0x1800076c9  jmp     cs:__imp_GetProcAddress
```
