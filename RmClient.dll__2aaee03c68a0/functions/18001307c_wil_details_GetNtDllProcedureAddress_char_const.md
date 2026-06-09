# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001307c`
- end: `0x18001309c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005bc0`
- `0x180006bf8`
- `0x180013004`
- `0x1800134fc`
- `0x180016fa0`
- `0x180016fe0`
- `0x180017a58`

## callees

- `0x18000f630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013095`

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
0x18001307c  push    rbx
0x18001307e  sub     rsp, 20h
0x180013082  mov     rbx, rcx
0x180013085  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001308a  mov     rcx, rax
0x18001308d  mov     rdx, rbx
0x180013090  add     rsp, 20h
0x180013094  pop     rbx
0x180013095  jmp     cs:__imp_GetProcAddress
```
