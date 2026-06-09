# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1800a5508`
- end: `0x1800a5531`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800a3b10`
- `0x1800a5538`

## callees

- `0x1800a5508`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a551f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a551f`

## string_xrefs

- `0x1800a5518`: `ntdll.dll`

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
0x1800a5508  sub     rsp, 28h
0x1800a550c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800a5513  test    rax, rax
0x1800a5516  jnz     short loc_1800A552C
0x1800a5518  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800a551f  call    cs:__imp_GetModuleHandleW
0x1800a5525  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800a552c  add     rsp, 28h
0x1800a5530  retn
```
