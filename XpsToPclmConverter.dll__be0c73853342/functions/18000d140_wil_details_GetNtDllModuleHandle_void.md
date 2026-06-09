# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000d140`
- end: `0x18000d169`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800093a0`
- `0x18000d170`

## callees

- `0x18000d140`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d157`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d157`

## string_xrefs

- `0x18000d150`: `ntdll.dll`

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
0x18000d140  sub     rsp, 28h
0x18000d144  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d14b  test    rax, rax
0x18000d14e  jnz     short loc_18000D164
0x18000d150  lea     rcx, ModuleName; "ntdll.dll"
0x18000d157  call    cs:__imp_GetModuleHandleW
0x18000d15d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d164  add     rsp, 28h
0x18000d168  retn
```
