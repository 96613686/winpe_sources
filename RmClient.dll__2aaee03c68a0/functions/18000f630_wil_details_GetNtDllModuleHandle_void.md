# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000f630`
- end: `0x18000f659`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001307c`
- `0x1800161e0`

## callees

- `0x18000f630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f647`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f647`

## string_xrefs

- `0x18000f640`: `ntdll.dll`

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
0x18000f630  sub     rsp, 28h
0x18000f634  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f63b  test    rax, rax
0x18000f63e  jnz     short loc_18000F654
0x18000f640  lea     rcx, ModuleName; "ntdll.dll"
0x18000f647  call    cs:__imp_GetModuleHandleW
0x18000f64d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f654  add     rsp, 28h
0x18000f658  retn
```
