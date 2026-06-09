# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180008524`
- end: `0x18000854d`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d000`
- `0x18000f610`

## callees

- `0x180008524`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000853b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000853b`

## string_xrefs

- `0x180008534`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

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
0x180008524  sub     rsp, 28h
0x180008528  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000852f  test    rax, rax
0x180008532  jnz     short loc_180008548
0x180008534  lea     rcx, ModuleName; "ntdll.dll"
0x18000853b  call    cs:__imp_GetModuleHandleW
0x180008541  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008548  add     rsp, 28h
0x18000854c  retn
```
