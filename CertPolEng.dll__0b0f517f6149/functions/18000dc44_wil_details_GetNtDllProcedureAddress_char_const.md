# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000dc44`
- end: `0x18000dc64`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b5fc`
- `0x18000db80`
- `0x180011490`
- `0x1800114d0`
- `0x180012ee0`
- `0x18001300c`
- `0x1800130cc`
- `0x180013144`

## callees

- `0x180012ce0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc5d`

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
0x18000dc44  push    rbx
0x18000dc46  sub     rsp, 20h
0x18000dc4a  mov     rbx, rcx
0x18000dc4d  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000dc52  mov     rcx, rax
0x18000dc55  mov     rdx, rbx
0x18000dc58  add     rsp, 20h
0x18000dc5c  pop     rbx
0x18000dc5d  jmp     cs:__imp_GetProcAddress
```
