# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000e400`
- end: `0x18000e429`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE__ *__fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800043a0`
- `0x18000af00`
- `0x18000e430`

## callees

- `0x18000e400`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e417`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e417`

## string_xrefs

- `0x18000e410`: `ntdll.dll`

## pseudocode

```c
HMODULE __fastcall wil_details_GetNtDllModuleHandle()
{
  HMODULE result; // rax

  result = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000e400  sub     rsp, 28h
0x18000e404  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e40b  test    rax, rax
0x18000e40e  jnz     short loc_18000E424
0x18000e410  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e417  call    cs:__imp_GetModuleHandleW
0x18000e41d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e424  add     rsp, 28h
0x18000e428  retn
```
