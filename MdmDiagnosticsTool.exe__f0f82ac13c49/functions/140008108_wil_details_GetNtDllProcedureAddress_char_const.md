# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x140008108`
- end: `0x140008128`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006290`

## callees

- `0x1400080d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008121`

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
0x140008108  push    rbx
0x14000810a  sub     rsp, 20h
0x14000810e  mov     rbx, rcx
0x140008111  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x140008116  mov     rcx, rax
0x140008119  mov     rdx, rbx
0x14000811c  add     rsp, 20h
0x140008120  pop     rbx
0x140008121  jmp     cs:__imp_GetProcAddress
```
