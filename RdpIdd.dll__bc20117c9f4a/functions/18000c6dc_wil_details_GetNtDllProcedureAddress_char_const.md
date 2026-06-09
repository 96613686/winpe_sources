# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000c6dc`
- end: `0x18000c722`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `70`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b040`
- `0x18000b080`
- `0x180038e74`
- `0x180038fa0`
- `0x180039068`
- `0x1800390e0`
- `0x180039170`
- `0x1800391dc`

## callees

- `0x18000c6dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c6f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c6f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c716`

## string_xrefs

- `0x18000c6f1`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, a1);
}

```

## disassembly

```asm
0x18000c6dc  push    rbx
0x18000c6de  sub     rsp, 20h
0x18000c6e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c6e9  mov     rbx, rcx
0x18000c6ec  test    rax, rax
0x18000c6ef  jnz     short loc_18000C70B
0x18000c6f1  lea     rcx, ModuleName; "ntdll.dll"
0x18000c6f8  call    cs:__imp_GetModuleHandleW
0x18000c6ff  nop     dword ptr [rax+rax+00h]
0x18000c704  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c70b  mov     rdx, rbx
0x18000c70e  mov     rcx, rax
0x18000c711  add     rsp, 20h
0x18000c715  pop     rbx
0x18000c716  jmp     cs:__imp_GetProcAddress
```
