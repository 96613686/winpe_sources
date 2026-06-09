# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1400077f0`
- end: `0x140007810`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140003030`
- `0x140005ff0`
- `0x140006030`
- `0x140007a90`
- `0x140007af0`
- `0x140007b68`
- `0x140007bf4`

## callees

- `0x1400077c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007809`

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
0x1400077f0  push    rbx
0x1400077f2  sub     rsp, 20h
0x1400077f6  mov     rbx, rcx
0x1400077f9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1400077fe  mov     rcx, rax
0x140007801  mov     rdx, rbx
0x140007804  add     rsp, 20h
0x140007808  pop     rbx
0x140007809  jmp     cs:__imp_GetProcAddress
```
