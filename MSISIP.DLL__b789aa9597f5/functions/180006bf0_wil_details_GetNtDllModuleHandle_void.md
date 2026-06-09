# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180006bf0`
- end: `0x180006c19`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cdec`

## callees

- `0x180006bf0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180006c07`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180006c07`

## string_xrefs

- `0x180006c00`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = (HINSTANCE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180006bf0  sub     rsp, 28h
0x180006bf4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006bfb  test    rax, rax
0x180006bfe  jnz     short loc_180006C14
0x180006c00  lea     rcx, ModuleName; "ntdll.dll"
0x180006c07  call    cs:__imp_GetModuleHandleW
0x180006c0d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c14  add     rsp, 28h
0x180006c18  retn
```
