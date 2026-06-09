# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180005940`
- end: `0x180005965`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004d70`
- `0x180004db0`
- `0x1800120f8`
- `0x180012224`
- `0x1800126bc`
- `0x180012734`
- `0x180012914`
- `0x180012980`

## callees

- `0x180005908`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005959`

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
0x180005940  push    rbx
0x180005942  sub     rsp, 20h
0x180005946  mov     rbx, rcx
0x180005949  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000594e  mov     rcx, rax
0x180005951  mov     rdx, rbx
0x180005954  add     rsp, 20h
0x180005958  pop     rbx
0x180005959  jmp     cs:__imp_GetProcAddress
```
