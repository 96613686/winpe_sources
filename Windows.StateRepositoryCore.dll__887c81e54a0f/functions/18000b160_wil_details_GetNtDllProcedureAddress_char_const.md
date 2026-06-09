# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000b160`
- end: `0x18000b180`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009430`
- `0x180009470`
- `0x18000b550`
- `0x18000b67c`
- `0x18000bafc`
- `0x18000bb74`
- `0x18000bd50`
- `0x18000bdbc`

## callees

- `0x18000b130`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b179`

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
0x18000b160  push    rbx
0x18000b162  sub     rsp, 20h
0x18000b166  mov     rbx, rcx
0x18000b169  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000b16e  mov     rcx, rax
0x18000b171  mov     rdx, rbx
0x18000b174  add     rsp, 20h
0x18000b178  pop     rbx
0x18000b179  jmp     cs:__imp_GetProcAddress
```
