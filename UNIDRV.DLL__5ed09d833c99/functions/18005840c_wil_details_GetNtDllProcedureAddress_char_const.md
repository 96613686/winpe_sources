# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18005840c`
- end: `0x180058431`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800529ec`
- `0x180056fe0`
- `0x180057020`
- `0x180058718`
- `0x180058844`
- `0x180058910`
- `0x180058988`
- `0x180058b68`

## callees

- `0x1800583d4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180058425`

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
0x18005840c  push    rbx
0x18005840e  sub     rsp, 20h
0x180058412  mov     rbx, rcx
0x180058415  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18005841a  mov     rcx, rax
0x18005841d  mov     rdx, rbx
0x180058420  add     rsp, 20h
0x180058424  pop     rbx
0x180058425  jmp     cs:__imp_GetProcAddress
```
