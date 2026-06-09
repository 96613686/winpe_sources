# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000a360`
- end: `0x18000a380`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004ec0`
- `0x1800087e0`
- `0x180008820`
- `0x180009144`
- `0x18000a5e8`
- `0x18000a714`
- `0x18000a7dc`
- `0x18000a854`

## callees

- `0x18000a330`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a379`

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
0x18000a360  push    rbx
0x18000a362  sub     rsp, 20h
0x18000a366  mov     rbx, rcx
0x18000a369  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000a36e  mov     rcx, rax
0x18000a371  mov     rdx, rbx
0x18000a374  add     rsp, 20h
0x18000a378  pop     rbx
0x18000a379  jmp     cs:__imp_GetProcAddress
```
