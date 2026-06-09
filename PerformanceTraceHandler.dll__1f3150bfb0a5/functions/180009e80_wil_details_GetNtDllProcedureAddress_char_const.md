# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009e80`
- end: `0x180009ea0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004968`
- `0x180007f60`
- `0x180007fa0`
- `0x180008828`
- `0x180009200`
- `0x18000a148`
- `0x18000a274`
- `0x18000a33c`
- `0x18000a3b4`

## callees

- `0x180009e50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e99`

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
0x180009e80  push    rbx
0x180009e82  sub     rsp, 20h
0x180009e86  mov     rbx, rcx
0x180009e89  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180009e8e  mov     rcx, rax
0x180009e91  mov     rdx, rbx
0x180009e94  add     rsp, 20h
0x180009e98  pop     rbx
0x180009e99  jmp     cs:__imp_GetProcAddress
```
