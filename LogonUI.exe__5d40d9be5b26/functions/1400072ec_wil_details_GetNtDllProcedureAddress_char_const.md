# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1400072ec`
- end: `0x14000730c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400017b4`
- `0x1400061d0`
- `0x140006210`
- `0x1400066a8`
- `0x1400076d0`
- `0x140007730`
- `0x1400077a8`

## callees

- `0x1400072bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007305`

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
0x1400072ec  push    rbx
0x1400072ee  sub     rsp, 20h
0x1400072f2  mov     rbx, rcx
0x1400072f5  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1400072fa  mov     rcx, rax
0x1400072fd  mov     rdx, rbx
0x140007300  add     rsp, 20h
0x140007304  pop     rbx
0x140007305  jmp     cs:__imp_GetProcAddress
```
