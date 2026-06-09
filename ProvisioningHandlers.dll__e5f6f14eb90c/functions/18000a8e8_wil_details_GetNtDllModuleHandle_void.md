# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000a8e8`
- end: `0x18000a918`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005af0`
- `0x18000a920`

## callees

- `0x18000a8e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8ff`

## string_xrefs

- `0x18000a8f8`: `ntdll.dll`

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
0x18000a8e8  sub     rsp, 28h
0x18000a8ec  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a8f3  test    rax, rax
0x18000a8f6  jnz     short loc_18000A912
0x18000a8f8  lea     rcx, ModuleName; "ntdll.dll"
0x18000a8ff  call    cs:__imp_GetModuleHandleW
0x18000a906  nop     dword ptr [rax+rax+00h]
0x18000a90b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a912  add     rsp, 28h
0x18000a916  retn
```
