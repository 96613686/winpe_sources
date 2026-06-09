# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180036bfc`
- end: `0x180036c2c`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180035650`
- `0x180036c34`

## callees

- `0x180036bfc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036c13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036c13`

## string_xrefs

- `0x180036c0c`: `ntdll.dll`

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
0x180036bfc  sub     rsp, 28h
0x180036c00  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180036c07  test    rax, rax
0x180036c0a  jnz     short loc_180036C26
0x180036c0c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180036c13  call    cs:__imp_GetModuleHandleW
0x180036c1a  nop     dword ptr [rax+rax+00h]
0x180036c1f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180036c26  add     rsp, 28h
0x180036c2a  retn
```
