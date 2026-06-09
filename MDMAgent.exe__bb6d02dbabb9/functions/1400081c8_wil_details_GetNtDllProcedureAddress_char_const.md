# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1400081c8`
- end: `0x1400081ed`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006c50`
- `0x140006c90`
- `0x140007b90`
- `0x1400124b8`
- `0x14001251c`
- `0x140012594`
- `0x140012624`
- `0x140012690`

## callees

- `0x140008190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400081e1`

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
0x1400081c8  push    rbx
0x1400081ca  sub     rsp, 20h
0x1400081ce  mov     rbx, rcx
0x1400081d1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1400081d6  mov     rcx, rax
0x1400081d9  mov     rdx, rbx
0x1400081dc  add     rsp, 20h
0x1400081e0  pop     rbx
0x1400081e1  jmp     cs:__imp_GetProcAddress
```
