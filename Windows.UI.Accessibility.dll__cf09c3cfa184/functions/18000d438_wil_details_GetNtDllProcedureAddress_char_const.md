# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000d438`
- end: `0x18000d458`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009ca0`
- `0x18000be40`
- `0x18000be80`
- `0x18000d658`
- `0x18000d784`
- `0x18000d84c`
- `0x18000d8c4`
- `0x18000daa0`
- `0x18000db0c`

## callees

- `0x18000d408`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d451`

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
0x18000d438  push    rbx
0x18000d43a  sub     rsp, 20h
0x18000d43e  mov     rbx, rcx
0x18000d441  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000d446  mov     rcx, rax
0x18000d449  mov     rdx, rbx
0x18000d44c  add     rsp, 20h
0x18000d450  pop     rbx
0x18000d451  jmp     cs:__imp_GetProcAddress
```
