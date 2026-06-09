# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140005fd0`
- end: `0x140005ff0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400054e0`
- `0x140005520`
- `0x14000b290`
- `0x14000b3bc`
- `0x14000b49c`
- `0x14000b514`
- `0x14000b6ec`
- `0x14000b758`

## callees

- `0x140005fa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140005fe9`

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
0x140005fd0  push    rbx
0x140005fd2  sub     rsp, 20h
0x140005fd6  mov     rbx, rcx
0x140005fd9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140005fde  mov     rcx, rax
0x140005fe1  mov     rdx, rbx
0x140005fe4  add     rsp, 20h
0x140005fe8  pop     rbx
0x140005fe9  jmp     cs:__imp_GetProcAddress
```
