# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18001b9dc`
- end: `0x18001ba05`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006720`
- `0x18001ba0c`

## callees

- `0x18001b9dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b9f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b9f3`

## string_xrefs

- `0x18001b9ec`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = (HINSTANCE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x18001b9dc  sub     rsp, 28h
0x18001b9e0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b9e7  test    rax, rax
0x18001b9ea  jnz     short loc_18001BA00
0x18001b9ec  lea     rcx, ModuleName; "ntdll.dll"
0x18001b9f3  call    cs:__imp_GetModuleHandleW
0x18001b9f9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ba00  add     rsp, 28h
0x18001ba04  retn
```
